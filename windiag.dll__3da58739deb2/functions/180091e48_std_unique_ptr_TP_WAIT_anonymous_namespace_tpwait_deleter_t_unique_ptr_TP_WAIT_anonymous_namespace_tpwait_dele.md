# std::unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_::_unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_

- ea: `0x180091e48`
- end: `0x180091e81`
- name: `std::unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_::_unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009b338`

## callees

- `0x180091e48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180091e5e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180091e5e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180091e75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180091e75`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180091e6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180091e6c`

## pseudocode

```c
void __fastcall std::unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_::_unique_ptr__TP_WAIT__anonymous_namespace_::tpwait_deleter_t_(
        PTP_WAIT *a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolWait(*a1, 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
}

```

## disassembly

```asm
0x180091e48  push    rbx
0x180091e4a  sub     rsp, 20h
0x180091e4e  mov     rbx, [rcx]
0x180091e51  test    rbx, rbx
0x180091e54  jz      short loc_180091E7B
0x180091e56  xor     r8d, r8d; pftTimeout
0x180091e59  xor     edx, edx; h
0x180091e5b  mov     rcx, rbx; pwa
0x180091e5e  call    cs:__imp_SetThreadpoolWait
0x180091e64  mov     edx, 1; fCancelPendingCallbacks
0x180091e69  mov     rcx, rbx; pwa
0x180091e6c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180091e72  mov     rcx, rbx; pwa
0x180091e75  call    cs:__imp_CloseThreadpoolWait
0x180091e7b  add     rsp, 20h
0x180091e7f  pop     rbx
0x180091e80  retn
```
