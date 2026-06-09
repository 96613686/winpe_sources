# ScInitializeNotify(void)

- ea: `0x18003bf3c`
- end: `0x18003bf9a`
- name: `?ScInitializeNotify@@YAKXZ`
- size: `94`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013f34`

## callees

- `0x18003bf3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bf8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bf58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bf58`
- `RPCRT4!UuidCreate` at `0x18003bf6d`
- `RPCRT4!UuidCreate` at `0x18003bf6d`

## pseudocode

```c
__int64 ScInitializeNotify(void)
{
  unsigned int v1; // ebx
  RPC_STATUS v2; // eax

  if ( g_fNotificationInitialized )
    return 0;
  v1 = 0;
  EnterCriticalSection(&SccCritsec);
  if ( !g_fNotificationInitialized )
  {
    v2 = UuidCreate(&g_SccClientProcessGuid);
    if ( v2 )
      v1 = v2;
    else
      g_fNotificationInitialized = 1;
  }
  LeaveCriticalSection(&SccCritsec);
  return v1;
}

```

## disassembly

```asm
0x18003bf3c  push    rbx
0x18003bf3e  sub     rsp, 20h
0x18003bf42  cmp     cs:?g_fNotificationInitialized@@3HA, 0; int g_fNotificationInitialized
0x18003bf49  jz      short loc_18003BF4F
0x18003bf4b  xor     eax, eax
0x18003bf4d  jmp     short loc_18003BF94
0x18003bf4f  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003bf56  xor     ebx, ebx
0x18003bf58  call    cs:__imp_EnterCriticalSection
0x18003bf5e  cmp     cs:?g_fNotificationInitialized@@3HA, ebx; int g_fNotificationInitialized
0x18003bf64  jnz     short loc_18003BF85
0x18003bf66  lea     rcx, ?g_SccClientProcessGuid@@3U_GUID@@A; Uuid
0x18003bf6d  call    cs:__imp_UuidCreate
0x18003bf73  test    eax, eax
0x18003bf75  jz      short loc_18003BF7B
0x18003bf77  mov     ebx, eax
0x18003bf79  jmp     short loc_18003BF85
0x18003bf7b  mov     cs:?g_fNotificationInitialized@@3HA, 1; int g_fNotificationInitialized
0x18003bf85  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003bf8c  call    cs:__imp_LeaveCriticalSection
0x18003bf92  mov     eax, ebx
0x18003bf94  add     rsp, 20h
0x18003bf98  pop     rbx
0x18003bf99  retn
```
