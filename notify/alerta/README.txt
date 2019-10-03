[{"status": "resolved", "labels": {"instance": "{\"cluster\": \"gpthml\", \"host\": \"compute02\"}", "event": "ceph_pg_non_active_clean_alert-cluster=gpthml", "environment": "Production", "severity": "ok", "service": "ceph_pgmap", "group": "backend_service", "customer": "VNA"}, "annotations": {"summary": "OK | CEPH cluster gpthml alert - non-good ( not active, clean, scrub) ratio: 0.00%!", "value": "['time', 'value']:[['2019-10-03T09:20:30Z', 0]]"}}]

curl -XPOST http://localhost:8000/alert \
-H 'Authorization: Key e3a07d26-dfa9-4776-88fa-b3f72a8633e0' \
-H 'Content-type: application/json' \
-d '{
      "attributes": {
        "region": "EU"
      },
      "correlate": [
        "HttpServerError",
        "HttpServerOK"
      ],
      "environment": "Production",
      "event": "HttpServerErssrors",
      "group": "Web",
      "origin": "curl",
      "resource": "web02",
      "service": [
        "example.com"
      ],
      "severity": "major",
      "tags": [
        "dc1"
      ],
      "text": "Site is down.",
      "type": "exceptionAlert",
      "value": "Bad Gateway (501)",
      "origin": "vna"
    }'