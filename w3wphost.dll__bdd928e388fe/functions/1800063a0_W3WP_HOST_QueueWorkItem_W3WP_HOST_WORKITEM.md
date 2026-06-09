# W3WP_HOST::QueueWorkItem(W3WP_HOST_WORKITEM *)

- ea: `0x1800063a0`
- end: `0x1800063e6`
- name: `?QueueWorkItem@W3WP_HOST@@QEAAJPEAVW3WP_HOST_WORKITEM@@@Z`
- size: `70`
- prototype: `signed int __fastcall(W3WP_HOST *this, struct W3WP_HOST_WORKITEM *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006830`
- `0x18000a638`
- `0x18000a7b0`
- `0x18000a8e0`

## callees

- `0x1800063a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063cb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800063c1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800063c1`

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
0x1800063a0  sub     rsp, 28h
0x1800063a4  cmp     cs:?sm_ShutdownCalled@W3WP_HOST_WORKITEM@@0HA, 1; int W3WP_HOST_WORKITEM::sm_ShutdownCalled
0x1800063ab  jnz     short loc_1800063B4
0x1800063ad  mov     eax, 8000FFFFh
0x1800063b2  jmp     short loc_1800063E1
0x1800063b4  mov     r8d, 10h; Flags
0x1800063ba  lea     rcx, ?ExecuteWorkItem@W3WP_HOST@@SAKPEAX@Z; Function
0x1800063c1  call    cs:__imp_QueueUserWorkItem
0x1800063c7  test    eax, eax
0x1800063c9  jnz     short loc_1800063DF
0x1800063cb  call    cs:__imp_GetLastError
0x1800063d1  test    eax, eax
0x1800063d3  jle     short loc_1800063E1
0x1800063d5  movzx   eax, ax
0x1800063d8  or      eax, 80070000h
0x1800063dd  jmp     short loc_1800063E1
0x1800063df  xor     eax, eax
0x1800063e1  add     rsp, 28h
0x1800063e5  retn
```
