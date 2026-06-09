# CGetPrincipalNameTask::_GetExplicitPrincipalName(ushort const *,ushort const *,Windows::Internal::String &)

- ea: `0x1800ce0dc`
- end: `0x1800ce1e5`
- name: `?_GetExplicitPrincipalName@CGetPrincipalNameTask@@AEAAJPEBG0AEAVString@Internal@Windows@@@Z`
- size: `265`
- prototype: `int(CGetPrincipalNameTask *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::String *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ce7a8`

## callees

- `0x18006f694`
- `0x1800ce0dc`

## import_xrefs

- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800ce1ba`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800ce1ba`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800ce1cb`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x1800ce1cb`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800ce15d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800ce15d`
- `NTDSAPI!DsBindW` at `0x1800ce104`
- `NTDSAPI!DsBindW` at `0x1800ce104`

## pseudocode

```c

```
