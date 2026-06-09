# UpdateServiceCheckPoint(ServiceContext *)

- ea: `0x18000b03c`
- end: `0x18000b05c`
- name: `?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z`
- size: `32`
- prototype: `void __fastcall(struct ServiceContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000a768`
- `0x18002d870`

## callees

- `0x18000b03c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b051`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b051`

## pseudocode

```c
void __fastcall UpdateServiceCheckPoint(struct ServiceContext *a1)
{
  struct _SERVICE_STATUS *v1; // rdx

  v1 = (struct _SERVICE_STATUS *)*((_QWORD *)a1 + 3);
  if ( v1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v1->dwCheckPoint);
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)a1 + 2), v1);
  }
}

```

## disassembly

```asm
0x18000b03c  sub     rsp, 28h
0x18000b040  mov     rdx, [rcx+18h]; lpServiceStatus
0x18000b044  test    rdx, rdx
0x18000b047  jz      short loc_18000B057
0x18000b049  lock inc dword ptr [rdx+14h]
0x18000b04d  mov     rcx, [rcx+10h]; hServiceStatus
0x18000b051  call    cs:__imp_SetServiceStatus
0x18000b057  add     rsp, 28h
0x18000b05b  retn
```
