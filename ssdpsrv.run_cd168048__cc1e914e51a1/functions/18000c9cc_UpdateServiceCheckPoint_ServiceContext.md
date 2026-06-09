# UpdateServiceCheckPoint(ServiceContext *)

- ea: `0x18000c9cc`
- end: `0x18000c9f3`
- name: `?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z`
- size: `39`
- prototype: `void __fastcall(struct ServiceContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000c078`
- `0x18002f900`

## callees

- `0x18000c9cc`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c9e1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c9e1`

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
0x18000c9cc  sub     rsp, 28h
0x18000c9d0  mov     rdx, [rcx+18h]; lpServiceStatus
0x18000c9d4  test    rdx, rdx
0x18000c9d7  jz      short loc_18000C9ED
0x18000c9d9  lock inc dword ptr [rdx+14h]
0x18000c9dd  mov     rcx, [rcx+10h]; hServiceStatus
0x18000c9e1  call    cs:__imp_SetServiceStatus
0x18000c9e8  nop     dword ptr [rax+rax+00h]
0x18000c9ed  add     rsp, 28h
0x18000c9f1  retn
```
