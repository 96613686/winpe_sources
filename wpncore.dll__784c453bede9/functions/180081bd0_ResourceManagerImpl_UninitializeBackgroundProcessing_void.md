# ResourceManagerImpl::UninitializeBackgroundProcessing(void)

- ea: `0x180081bd0`
- end: `0x180081c7a`
- name: `?UninitializeBackgroundProcessing@ResourceManagerImpl@@UEAAXXZ`
- size: `170`
- prototype: `void(ResourceManagerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002ee38`
- `0x180081bd0`
- `0x180081c80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180081be3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180081be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081bed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180081bfe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180081bfe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180081c08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180081c08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081c1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081c38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081c1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081c38`

## pseudocode

```c
void __fastcall ResourceManagerImpl::UninitializeBackgroundProcessing(ResourceManagerImpl *this)
{
  void *v2; // rcx
  struct _TP_WORK *v3; // rcx
  char *v4; // rcx
  char *v5; // rcx
  EnergySaverAllowlistManager *v6; // rcx
  int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 != (void *)-1LL && !SetEvent(v2) )
    GetLastError();
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 13);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 0);
    CloseThreadpoolWork(*((PTP_WORK *)this + 13));
  }
  v4 = (char *)*((_QWORD *)this + 12);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 12) = 0;
  }
  v5 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 10) = 0;
  }
  v6 = (EnergySaverAllowlistManager *)*((_QWORD *)this + 21);
  if ( v6 )
  {
    v7 = EnergySaverAllowlistManager::Shutdown(v6);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
        (const char *)(unsigned int)v7,
        v8);
  }
}

```

## disassembly

```asm
0x180081bd0  push    rbx; int
0x180081bd2  sub     rsp, 20h
0x180081bd6  mov     rbx, rcx
0x180081bd9  mov     rcx, [rcx+60h]; hEvent
0x180081bdd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180081be1  jz      short loc_180081BF3
0x180081be3  call    cs:__imp_SetEvent
0x180081be9  test    eax, eax
0x180081beb  jnz     short loc_180081BF3
0x180081bed  call    cs:__imp_GetLastError
0x180081bf3  mov     rcx, [rbx+68h]; pwk
0x180081bf7  test    rcx, rcx
0x180081bfa  jz      short loc_180081C0E
0x180081bfc  xor     edx, edx; fCancelPendingCallbacks
0x180081bfe  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180081c04  mov     rcx, [rbx+68h]; pwk
0x180081c08  call    cs:__imp_CloseThreadpoolWork
0x180081c0e  mov     rcx, [rbx+60h]; hObject
0x180081c12  lea     rax, [rcx-1]
0x180081c16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081c1a  ja      short loc_180081C2A
0x180081c1c  call    cs:__imp_CloseHandle
0x180081c22  mov     qword ptr [rbx+60h], 0
0x180081c2a  mov     rcx, [rbx+50h]; hObject
0x180081c2e  lea     rax, [rcx-1]
0x180081c32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081c36  ja      short loc_180081C46
0x180081c38  call    cs:__imp_CloseHandle
0x180081c3e  mov     qword ptr [rbx+50h], 0
0x180081c46  mov     rcx, [rbx+0A8h]; this
0x180081c4d  test    rcx, rcx
0x180081c50  jz      short loc_180081C74
0x180081c52  call    ?Shutdown@EnergySaverAllowlistManager@@QEAAJXZ; EnergySaverAllowlistManager::Shutdown(void)
0x180081c57  test    eax, eax
0x180081c59  jns     short loc_180081C74
0x180081c5b  mov     rcx, [rsp+28h]; this
0x180081c60  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180081c67  mov     r9d, eax; char *
0x180081c6a  mov     edx, 0B0h; void *
0x180081c6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180081c74  add     rsp, 20h
0x180081c78  pop     rbx
0x180081c79  retn
```
