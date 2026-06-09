# std::_Ref_count_obj2<sync_q<etw_event>>::_Destroy(void)

- ea: `0x18004a9e0`
- end: `0x18004aa34`
- name: `?_Destroy@?$_Ref_count_obj2@U?$sync_q@Uetw_event@@@@@std@@EEAAXXZ`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180049374`
- `0x18004a9e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004aa01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004aa01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004aa18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004aa18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004aa0f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18004aa0f`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<sync_q<etw_event>>::_Destroy(__int64 a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *(struct _TP_WAIT **)(a1 + 216);
  if ( v1 )
  {
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 216), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  return std::deque<etw_event>::~deque<etw_event>(a1 + 168);
}

```

## disassembly

```asm
0x18004a9e0  mov     [rsp+arg_0], rbx
0x18004a9e5  push    rdi
0x18004a9e6  sub     rsp, 20h
0x18004a9ea  mov     rbx, [rcx+0D8h]
0x18004a9f1  mov     rdi, rcx
0x18004a9f4  test    rbx, rbx
0x18004a9f7  jz      short loc_18004AA1E
0x18004a9f9  xor     r8d, r8d; pftTimeout
0x18004a9fc  xor     edx, edx; h
0x18004a9fe  mov     rcx, rbx; pwa
0x18004aa01  call    cs:__imp_SetThreadpoolWait
0x18004aa07  mov     edx, 1; fCancelPendingCallbacks
0x18004aa0c  mov     rcx, rbx; pwa
0x18004aa0f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18004aa15  mov     rcx, rbx; pwa
0x18004aa18  call    cs:__imp_CloseThreadpoolWait
0x18004aa1e  lea     rcx, [rdi+0A8h]
0x18004aa25  mov     rbx, [rsp+28h+arg_0]
0x18004aa2a  add     rsp, 20h
0x18004aa2e  pop     rdi
0x18004aa2f  jmp     ??1?$deque@Uetw_event@@V?$allocator@Uetw_event@@@std@@@std@@QEAA@XZ; std::deque<etw_event>::~deque<etw_event>(void)
```
