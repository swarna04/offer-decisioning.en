---
keywords: Experience Platform;home;popular topics;offer decisioning;delete placements
solution: Experience Platform
product: experience platform
title: delete placements
topic: API guide
description: Placements are containers that are used to showcase your offers.
---

# Delete a placement

It may occasionally be necessary to remove (DELETE) a placement. Only placements that you create in the tenant container may be deleted. This is done by performing a DELETE request to the [!DNL Offer Library] API using the instance ID of the placement you wish to delete.

**API format**

```http
DELETE /{ENDPOINT_PATH}/{CONTAINER_ID}/instances/{INSTANCE_ID}
```

| Parameter | Description | Example |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | The endpoint path for repository APIs. | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | The container where the placements are located. | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{INSTANCE_ID}` | The instance id of the placement you wish to update. | `9aa58fd0-13d7-11eb-928b-576735ea4db8` |

**Request**

```shell
curl -X DELETE \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/9aa58fd0-13d7-11eb-928b-576735ea4db8' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**Response**

A successful response returns HTTP status 202 (No Content) and a blank body.

You can confirm the deletion by attempting a lookup (GET) request to the placement. You will need to include an Accept header in the request, but should receive an HTTP status 404 (Not Found) because the placement has been removed from the container.