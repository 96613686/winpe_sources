# Windows::UI::Core::CCoreWindowStatic::GetForCurrentThread(Windows::UI::Core::ICoreWindow * *)

- ea: `0x18002b0f0`
- end: `0x18002b1e4`
- name: `?GetForCurrentThread@CCoreWindowStatic@Core@UI@Windows@@EEAAJPEAPEAUICoreWindow@234@@Z`
- size: `244`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreWindowStatic *__hidden this, struct Windows::UI::Core::ICoreWindow **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002b0f0`
- `0x180050360`
- `0x180071c10`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002b113`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002b113`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b17c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b17c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b101`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1b8`

## string_xrefs

- `0x18002b153`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreWindowStatic::GetForCurrentThread(
        Windows::UI::Core::CCoreWindowStatic *this,
        struct Windows::UI::Core::ICoreWindow **a2)
{
  DWORD CurrentThreadId; // eax
  DWORD v4; // edi
  struct Windows::UI::Core::CoreWindowEntry *i; // rbx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v9; // rbx
  DWORD v10; // eax
  int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct Windows::UI::Core::ICoreWindow *v13; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  *a2 = 0;
  v4 = CurrentThreadId;
  AcquireSRWLockShared(&Windows::UI::Core::WindowServer::s_srwEntryLock);
  for ( i = Windows::UI::Core::WindowServer::s_pCoreWindowEntryList;
        i;
        i = (struct Windows::UI::Core::CoreWindowEntry *)*((_QWORD *)i + 2) )
  {
    if ( *(_DWORD *)i == v4 )
    {
      v6 = *((_QWORD *)i + 1);
      v13 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *, struct Windows::UI::Core::ICoreWindow **))(*(_QWORD *)v6 + 24LL))(
             v6,
             &GUID_79b9d5f2_879e_4b89_b798_79e47598030c,
             &v13);
      if ( v7 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x21CC,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)(unsigned int)v7,
          v11);
      if ( v13 )
      {
        *a2 = v13;
        break;
      }
    }
  }
  ReleaseSRWLockShared(&Windows::UI::Core::WindowServer::s_srwEntryLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = (__int64)*a2;
    v10 = GetCurrentThreadId();
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, v10, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b0f0  push    rbx
0x18002b0f2  push    rbp
0x18002b0f3  push    rsi
0x18002b0f4  push    rdi
0x18002b0f5  sub     rsp, 38h
0x18002b0f9  xor     ebp, ebp
0x18002b0fb  mov     rsi, rdx
0x18002b0fe  mov     [rdx], rbp
0x18002b101  call    cs:__imp_GetCurrentThreadId
0x18002b107  lea     rcx, ?s_srwEntryLock@WindowServer@Core@UI@Windows@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18002b10e  mov     [rsi], rbp
0x18002b111  mov     edi, eax
0x18002b113  call    cs:__imp_AcquireSRWLockShared
0x18002b119  mov     rbx, cs:?s_pCoreWindowEntryList@WindowServer@Core@UI@Windows@@0PEAUCoreWindowEntry@234@EA; Windows::UI::Core::CoreWindowEntry * Windows::UI::Core::WindowServer::s_pCoreWindowEntryList
0x18002b120  test    rbx, rbx
0x18002b123  jz      short loc_18002B175
0x18002b125  cmp     [rbx], edi
0x18002b127  jnz     short loc_18002B1A6
0x18002b129  mov     rcx, [rbx+8]
0x18002b12d  lea     r8, [rsp+58h+arg_8]
0x18002b132  mov     [rsp+58h+arg_8], rbp
0x18002b137  lea     rdx, _GUID_79b9d5f2_879e_4b89_b798_79e47598030c
0x18002b13e  mov     rax, [rcx]
0x18002b141  mov     rax, [rax+18h]
0x18002b145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b14a  test    eax, eax
0x18002b14c  jns     short loc_18002B168
0x18002b14e  mov     rcx, [rsp+58h]; this
0x18002b153  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002b15a  mov     r9d, eax; char *
0x18002b15d  mov     edx, 21CCh; void *
0x18002b162  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002b168  mov     rax, [rsp+58h+arg_8]
0x18002b16d  test    rax, rax
0x18002b170  jz      short loc_18002B1A6
0x18002b172  mov     [rsi], rax
0x18002b175  lea     rcx, ?s_srwEntryLock@WindowServer@Core@UI@Windows@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18002b17c  call    cs:__imp_ReleaseSRWLockShared
0x18002b182  mov     rax, cs:WPP_GLOBAL_Control
0x18002b189  lea     rcx, WPP_GLOBAL_Control
0x18002b190  cmp     rax, rcx
0x18002b193  jz      short loc_18002B19B
0x18002b195  test    byte ptr [rax+1Ch], 2
0x18002b199  jnz     short loc_18002B1AF
0x18002b19b  xor     eax, eax
0x18002b19d  add     rsp, 38h
0x18002b1a1  pop     rdi
0x18002b1a2  pop     rsi
0x18002b1a3  pop     rbp
0x18002b1a4  pop     rbx
0x18002b1a5  retn
0x18002b1a6  mov     rbx, [rbx+10h]
0x18002b1aa  jmp     loc_18002B120
0x18002b1af  cmp     byte ptr [rax+19h], 5
0x18002b1b3  jb      short loc_18002B19B
0x18002b1b5  mov     rbx, [rsi]
0x18002b1b8  call    cs:__imp_GetCurrentThreadId
0x18002b1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c5  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x18002b1cc  mov     edx, 34h ; '4'
0x18002b1d1  mov     qword ptr [rsp+58h+var_38], rbx
0x18002b1d6  mov     r9d, eax
0x18002b1d9  mov     rcx, [rcx+10h]
0x18002b1dd  call    WPP_SF_Dq
0x18002b1e2  jmp     short loc_18002B19B
```
