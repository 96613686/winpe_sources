# W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)

- ea: `0x1800069cc`
- end: `0x180006a1f`
- name: `?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, struct W3WP_HOST_WORKITEM *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ea4`
- `0x18000b34c`
- `0x18000b4ec`
- `0x18000b630`

## callees

- `0x1800069cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069fd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800069ed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800069ed`

## pseudocode

```c
signed int __fastcall W3WP_HOST::QueueWorkItem(W3WP_HOST *this, struct W3WP_HOST_WORKITEM *a2)
{
  signed int result; // eax

  if ( W3WP_HOST_WORKITEM::sm_ShutdownCalled == 1 )
    return -2147418113;
  if ( QueueUserWorkItem(W3WP_HOST::ExecuteWorkItem, a2, 0x10u) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800069cc  sub     rsp, 28h
0x1800069d0  cmp     cs:?sm_ShutdownCalled@W3WP_HOST_WORKITEM@@0HA, 1; int W3WP_HOST_WORKITEM::sm_ShutdownCalled
0x1800069d7  jnz     short loc_1800069E0
0x1800069d9  mov     eax, 8000FFFFh
0x1800069de  jmp     short loc_180006A19
0x1800069e0  mov     r8d, 10h; Flags
0x1800069e6  lea     rcx, ?ExecuteWorkItem@W3WP_HOST@@SAKPEAX@Z; Function
0x1800069ed  call    cs:__imp_QueueUserWorkItem
0x1800069f4  nop     dword ptr [rax+rax+00h]
0x1800069f9  test    eax, eax
0x1800069fb  jnz     short loc_180006A17
0x1800069fd  call    cs:__imp_GetLastError
0x180006a04  nop     dword ptr [rax+rax+00h]
0x180006a09  test    eax, eax
0x180006a0b  jle     short loc_180006A19
0x180006a0d  movzx   eax, ax
0x180006a10  or      eax, 80070000h
0x180006a15  jmp     short loc_180006A19
0x180006a17  xor     eax, eax
0x180006a19  add     rsp, 28h
0x180006a1d  retn
```
