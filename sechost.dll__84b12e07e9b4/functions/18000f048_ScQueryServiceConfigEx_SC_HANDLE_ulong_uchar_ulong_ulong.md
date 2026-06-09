# ScQueryServiceConfigEx(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)

- ea: `0x18000f048`
- end: `0x18000f12a`
- name: `?ScQueryServiceConfigEx@@YAHPEAUSC_HANDLE__@@KPEAEKPEAK@Z`
- size: `226`
- prototype: `int(struct SC_HANDLE__ *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000e4e0`
- `0x180039c00`

## callees

- `0x18000f048`
- `0x1800176dc`
- `0x18004a974`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f116`
- `RPCRT4!NdrClientCall2` at `0x18000f095`
- `RPCRT4!NdrClientCall2` at `0x18000f095`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe70`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe70`

## pseudocode

```c

```
