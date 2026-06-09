# Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)

- ea: `0x18000f048`
- end: `0x18000f112`
- name: `?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z`
- size: `202`
- prototype: `__int64 __fastcall(struct Windows::UI::Core::ICoreWindow **)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e130`
- `0x18000e620`
- `0x18000ed50`
- `0x18004d010`
- `0x18004e9a0`
- `0x180079a60`
- `0x180081cc0`
- `0x1800824a0`
- `0x180082eb0`
- `0x180085354`

## callees

- `0x18000f048`
- `0x180050360`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f078`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f078`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f0e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f0e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f108`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f05f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f05f`

## string_xrefs

- `0x18000f0c4`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::WindowServer::GetWindowForThread(struct Windows::UI::Core::ICoreWindow **a1)
{
  DWORD CurrentThreadId; // esi
  struct Windows::UI::Core::CoreWindowEntry *i; // rbx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct Windows::UI::Core::ICoreWindow *v8; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v9; // [rsp+48h] [rbp+10h]

  *a1 = 0;
  CurrentThreadId = GetCurrentThreadId();
  *a1 = 0;
  AcquireSRWLockShared(&Windows::UI::Core::WindowServer::s_srwEntryLock);
  v9 = &Windows::UI::Core::WindowServer::s_srwEntryLock;
  for ( i = Windows::UI::Core::WindowServer::s_pCoreWindowEntryList;
        i;
        i = (struct Windows::UI::Core::CoreWindowEntry *)*((_QWORD *)i + 2) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
    {
      v8 = 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct Windows::UI::Core::ICoreWindow **))(**((_QWORD **)i + 1)
                                                                                               + 24LL))(
             *((_QWORD *)i + 1),
             &GUID_79b9d5f2_879e_4b89_b798_79e47598030c,
             &v8);
      if ( v4 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x21CC,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)(unsigned int)v4,
          v6);
      if ( v8 )
      {
        *a1 = v8;
        ReleaseSRWLockShared(&Windows::UI::Core::WindowServer::s_srwEntryLock);
        return 1;
      }
    }
  }
  ReleaseSRWLockShared(&Windows::UI::Core::WindowServer::s_srwEntryLock);
  return 0;
}

```

## disassembly

```asm
0x18000f048  mov     [rsp+arg_10], rbx
0x18000f04d  push    rsi
0x18000f04e  push    rdi
0x18000f04f  push    r14; int
0x18000f051  sub     rsp, 20h
0x18000f055  mov     rdi, rcx
0x18000f058  mov     qword ptr [rcx], 0
0x18000f05f  call    cs:__imp_GetCurrentThreadId
0x18000f065  mov     esi, eax
0x18000f067  mov     qword ptr [rdi], 0
0x18000f06e  lea     r14, ?s_srwEntryLock@WindowServer@Core@UI@Windows@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock Windows::UI::Core::WindowServer::s_srwEntryLock
0x18000f075  mov     rcx, r14; SRWLock
0x18000f078  call    cs:__imp_AcquireSRWLockShared
0x18000f07e  mov     [rsp+38h+arg_8], r14
0x18000f083  mov     rbx, cs:?s_pCoreWindowEntryList@WindowServer@Core@UI@Windows@@0PEAUCoreWindowEntry@234@EA; Windows::UI::Core::CoreWindowEntry * Windows::UI::Core::WindowServer::s_pCoreWindowEntryList
0x18000f08a  test    rbx, rbx
0x18000f08d  jz      short loc_18000F105
0x18000f08f  cmp     [rbx], esi
0x18000f091  jnz     short loc_18000F0FF
0x18000f093  mov     [rsp+38h+arg_0], 0
0x18000f09c  mov     rcx, [rbx+8]
0x18000f0a0  mov     rax, [rcx]
0x18000f0a3  lea     r8, [rsp+38h+arg_0]
0x18000f0a8  lea     rdx, _GUID_79b9d5f2_879e_4b89_b798_79e47598030c
0x18000f0af  mov     rax, [rax+18h]
0x18000f0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0b8  test    eax, eax
0x18000f0ba  jns     short loc_18000F0D6
0x18000f0bc  mov     rcx, [rsp+38h]; this
0x18000f0c1  mov     r9d, eax; char *
0x18000f0c4  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18000f0cb  mov     edx, 21CCh; void *
0x18000f0d0  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000f0d6  mov     rax, [rsp+38h+arg_0]
0x18000f0db  test    rax, rax
0x18000f0de  jz      short loc_18000F0FF
0x18000f0e0  mov     [rdi], rax
0x18000f0e3  mov     rcx, r14; SRWLock
0x18000f0e6  call    cs:__imp_ReleaseSRWLockShared
0x18000f0ec  mov     eax, 1
0x18000f0f1  mov     rbx, [rsp+38h+arg_10]
0x18000f0f6  add     rsp, 20h
0x18000f0fa  pop     r14
0x18000f0fc  pop     rdi
0x18000f0fd  pop     rsi
0x18000f0fe  retn
0x18000f0ff  mov     rbx, [rbx+10h]
0x18000f103  jmp     short loc_18000F08A
0x18000f105  mov     rcx, r14; SRWLock
0x18000f108  call    cs:__imp_ReleaseSRWLockShared
0x18000f10e  xor     eax, eax
0x18000f110  jmp     short loc_18000F0F1
```
