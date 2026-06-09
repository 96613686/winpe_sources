# ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z

- ea: `0x18000a904`
- end: `0x18000abba`
- name: `?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180009600`

## callees

- `0x180009428`
- `0x180009eb8`
- `0x18000a904`
- `0x18000ace0`
- `0x18000aff4`
- `0x18000bf5c`
- `0x18000c468`
- `0x18000c590`
- `0x18000c836`
- `0x18000c860`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000aad5`
- `KERNEL32!HeapFree` at `0x18000aad5`
- `KERNEL32!GetProcessHeap` at `0x18000aac1`
- `KERNEL32!GetProcessHeap` at `0x18000aac1`
- `KERNEL32!GetLastError` at `0x18000aa20`
- `KERNEL32!GetLastError` at `0x18000aae9`
- `KERNEL32!GetLastError` at `0x18000aa20`
- `KERNEL32!GetLastError` at `0x18000aae9`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a9fa`
- `KERNEL32!CreateSemaphoreExW` at `0x18000aa6e`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a9fa`
- `KERNEL32!CreateSemaphoreExW` at `0x18000aa6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rax
  wil::details::in1diag3 *v7; // rcx
  unsigned int v8; // r8d
  _DWORD *v9; // rbx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rdx
  WCHAR *v12; // rcx
  __int64 v13; // rdi
  WCHAR v14; // ax
  WCHAR *v15; // rax
  unsigned __int64 v16; // r14
  LONG v17; // esi
  LONG v18; // r8d
  wil::details *v19; // rcx
  HANDLE Semaphore; // rdi
  int LastErrorFailHr; // eax
  unsigned __int64 v22; // rdx
  unsigned int v23; // r8d
  unsigned int v24; // edi
  __int64 v25; // rdx
  LONG v26; // r8d
  wil::details *v27; // rcx
  HANDLE v28; // rdi
  unsigned int v29; // r8d
  HANDLE ProcessHeap; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-E0h]
  __int128 v35; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v36; // [rsp+40h] [rbp-C0h]
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a3 = 0;
  v6 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, (unsigned __int64)a3);
  v9 = (_DWORD *)v6;
  v36 = v6;
  if ( v6 )
  {
    v35 = 0;
    if ( (v6 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v7);
    v10 = v6 >> 2;
    v11 = 260;
    v12 = Name;
    v13 = a1 - (_QWORD)Name;
    do
    {
      if ( v11 == -2147483386 )
        break;
      v14 = *(WCHAR *)((char *)v12 + v13);
      if ( !v14 )
        break;
      *v12++ = v14;
      --v11;
    }
    while ( v11 );
    v15 = v12 - 1;
    if ( v11 )
      v15 = v12;
    *v15 = 0;
    StringCchCatW(Name, v11, L"_p0");
    v16 = v10 >> 31;
    v17 = v10 & 0x7FFFFFFF;
    v18 = 1;
    if ( v17 )
      v18 = v17;
    Semaphore = CreateSemaphoreExW(0, v17, v18, Name, 0, 0x1F0003u);
    if ( Semaphore )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v35,
        Semaphore);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v19);
      v24 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v25 = 136;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          v23,
          (const char *)(unsigned int)LastErrorFailHr,
          dwFlagsa);
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v29, (const char *)v24, dwFlagsb);
        wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v35);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        return v24;
      }
    }
    StringCchCatW(Name, v22, L"h");
    v26 = 1;
    if ( (_DWORD)v16 )
      v26 = v16;
    v28 = CreateSemaphoreExW(0, v16, v26, Name, 0, 0x1F0003u);
    if ( v28 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)&v35 + 8,
        v28);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v27);
      v24 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v25 = 141;
        goto LABEL_20;
      }
    }
    *v9 = 1;
    *((_QWORD *)v9 + 1) = *a2;
    *a2 = 0;
    *((_QWORD *)v9 + 2) = v35;
    *(_QWORD *)&v35 = 0;
    *((_QWORD *)v9 + 3) = *((_QWORD *)&v35 + 1);
    *((_QWORD *)&v35 + 1) = 0;
    memset_0((char *)v9 + 34, 0, 0x56u);
    *((_WORD *)v9 + 16) = 88;
    v9[9] = 1;
    memset_0(v9 + 10, 0, 0x50u);
    *a3 = v9;
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v35);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v8, (const char *)0x8007000ELL, dwFlags);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000a904  mov     [rsp-8+arg_0], rbx
0x18000a909  push    rbp
0x18000a90a  push    rsi
0x18000a90b  push    rdi
0x18000a90c  push    r12
0x18000a90e  push    r13
0x18000a910  push    r14
0x18000a912  push    r15
0x18000a914  lea     rbp, [rsp-170h]
0x18000a91c  sub     rsp, 270h
0x18000a923  mov     rax, cs:__security_cookie
0x18000a92a  xor     rax, rsp
0x18000a92d  mov     [rbp+1A0h+var_40], rax
0x18000a934  mov     r15, r8
0x18000a937  mov     r12, rdx
0x18000a93a  mov     rdi, rcx
0x18000a93d  xor     r13d, r13d
0x18000a940  mov     [r8], r13
0x18000a943  lea     edx, [r13+78h]; dwBytes
0x18000a947  lea     ecx, [rdx-70h]; dwFlags
0x18000a94a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a94f  mov     rbx, rax
0x18000a952  mov     [rsp+2A0h+var_260], rax
0x18000a957  test    rax, rax
0x18000a95a  jz      loc_18000AB6D
0x18000a960  xorps   xmm0, xmm0
0x18000a963  movdqu  [rsp+2A0h+var_270], xmm0
0x18000a969  test    bl, 3
0x18000a96c  jnz     loc_18000ABB4
0x18000a972  mov     rsi, rax
0x18000a975  shr     rsi, 2
0x18000a979  mov     edx, 104h
0x18000a97e  lea     rcx, [rsp+2A0h+Name]
0x18000a983  lea     rax, [rsp+2A0h+Name]
0x18000a988  sub     rdi, rax
0x18000a98b  lea     rax, [rdx+7FFFFEFAh]
0x18000a992  test    rax, rax
0x18000a995  jz      short loc_18000A9AD
0x18000a997  movzx   eax, word ptr [rdi+rcx]
0x18000a99b  test    ax, ax
0x18000a99e  jz      short loc_18000A9AD
0x18000a9a0  mov     [rcx], ax
0x18000a9a3  add     rcx, 2
0x18000a9a7  sub     rdx, 1; unsigned __int64
0x18000a9ab  jnz     short loc_18000A98B
0x18000a9ad  lea     rax, [rcx-2]
0x18000a9b1  test    rdx, rdx
0x18000a9b4  cmovnz  rax, rcx
0x18000a9b8  mov     [rax], r13w
0x18000a9bc  lea     r8, aP0; "_p0"
0x18000a9c3  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18000a9c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a9cd  mov     r14, rsi
0x18000a9d0  shr     r14, 1Fh
0x18000a9d4  and     esi, 7FFFFFFFh
0x18000a9da  mov     r8d, 1
0x18000a9e0  cmova   r8d, esi; lMaximumCount
0x18000a9e4  mov     [rsp+2A0h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a9ec  mov     [rsp+2A0h+dwFlags], r13d; dwFlags
0x18000a9f1  lea     r9, [rsp+2A0h+Name]; lpName
0x18000a9f6  mov     edx, esi; lInitialCount
0x18000a9f8  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a9fa  call    cs:__imp_CreateSemaphoreExW
0x18000aa01  nop     dword ptr [rax+rax+00h]
0x18000aa06  mov     rdi, rax
0x18000aa09  test    rax, rax
0x18000aa0c  jnz     short loc_18000AA20
0x18000aa0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aa13  mov     edi, eax
0x18000aa15  test    eax, eax
0x18000aa17  jns     short loc_18000AA39
0x18000aa19  mov     edx, 88h
0x18000aa1e  jmp     short loc_18000AA92
0x18000aa20  call    cs:__imp_GetLastError
0x18000aa27  nop     dword ptr [rax+rax+00h]
0x18000aa2c  mov     rdx, rdi
0x18000aa2f  lea     rcx, [rsp+2A0h+var_270]
0x18000aa34  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000aa39  lea     r8, asc_180011490; "h"
0x18000aa40  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18000aa45  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aa4a  mov     r8d, 1
0x18000aa50  test    r14d, r14d
0x18000aa53  cmovnz  r8d, r14d; lMaximumCount
0x18000aa57  mov     [rsp+2A0h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000aa5f  mov     [rsp+2A0h+dwFlags], r13d; int
0x18000aa64  lea     r9, [rsp+2A0h+Name]; lpName
0x18000aa69  mov     edx, r14d; lInitialCount
0x18000aa6c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000aa6e  call    cs:__imp_CreateSemaphoreExW
0x18000aa75  nop     dword ptr [rax+rax+00h]
0x18000aa7a  mov     rdi, rax
0x18000aa7d  test    rax, rax
0x18000aa80  jnz     short loc_18000AAE9
0x18000aa82  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aa87  mov     edi, eax
0x18000aa89  test    eax, eax
0x18000aa8b  jns     short loc_18000AB02
0x18000aa8d  mov     edx, 8Dh; void *
0x18000aa92  mov     r9d, eax; char *
0x18000aa95  mov     rcx, [rbp+1A8h]; this
0x18000aa9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaa1  mov     rcx, [rbp+1A8h]; this
0x18000aaa8  mov     r9d, edi; char *
0x18000aaab  mov     edx, 14Bh; void *
0x18000aab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aab5  nop
0x18000aab6  lea     rcx, [rsp+2A0h+var_270]; this
0x18000aabb  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000aac0  nop
0x18000aac1  call    cs:__imp_GetProcessHeap
0x18000aac8  nop     dword ptr [rax+rax+00h]
0x18000aacd  mov     rcx, rax; hHeap
0x18000aad0  mov     r8, rbx; lpMem
0x18000aad3  xor     edx, edx; dwFlags
0x18000aad5  call    cs:__imp_HeapFree
0x18000aadc  nop     dword ptr [rax+rax+00h]
0x18000aae1  nop
0x18000aae2  mov     eax, edi
0x18000aae4  jmp     loc_18000AB89
0x18000aae9  call    cs:__imp_GetLastError
0x18000aaf0  nop     dword ptr [rax+rax+00h]
0x18000aaf5  mov     rdx, rdi
0x18000aaf8  lea     rcx, [rsp+2A0h+var_270+8]
0x18000aafd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ab02  mov     dword ptr [rbx], 1
0x18000ab08  mov     rax, [r12]
0x18000ab0c  mov     [rbx+8], rax
0x18000ab10  mov     [r12], r13
0x18000ab14  mov     rax, qword ptr [rsp+2A0h+var_270]
0x18000ab19  mov     [rbx+10h], rax
0x18000ab1d  mov     qword ptr [rsp+2A0h+var_270], r13
0x18000ab22  mov     rax, qword ptr [rsp+2A0h+var_270+8]
0x18000ab27  mov     [rbx+18h], rax
0x18000ab2b  mov     qword ptr [rsp+2A0h+var_270+8], r13
0x18000ab30  lea     rcx, [rbx+22h]; void *
0x18000ab34  xor     edx, edx; Val
0x18000ab36  lea     r8d, [rdx+56h]; Size
0x18000ab3a  call    memset_0
0x18000ab3f  mov     word ptr [rbx+20h], 58h ; 'X'
0x18000ab45  mov     dword ptr [rbx+24h], 1
0x18000ab4c  lea     rcx, [rbx+28h]; void *
0x18000ab50  xor     edx, edx; Val
0x18000ab52  lea     r8d, [rdx+50h]; Size
0x18000ab56  call    memset_0
0x18000ab5b  mov     [r15], rbx
0x18000ab5e  lea     rcx, [rsp+2A0h+var_270]; this
0x18000ab63  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ab68  nop
0x18000ab69  xor     eax, eax
0x18000ab6b  jmp     short loc_18000AB89
0x18000ab6d  mov     rcx, [rbp+1A8h]; this
0x18000ab74  mov     ebx, 8007000Eh
0x18000ab79  mov     r9d, ebx; char *
0x18000ab7c  mov     edx, 148h; void *
0x18000ab81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab86  nop
0x18000ab87  mov     eax, ebx
0x18000ab89  mov     rcx, [rbp+1A0h+var_40]
0x18000ab90  xor     rcx, rsp; StackCookie
0x18000ab93  call    __security_check_cookie
0x18000ab98  mov     rbx, [rsp+2A0h+arg_0]
0x18000aba0  add     rsp, 270h
0x18000aba7  pop     r15
0x18000aba9  pop     r14
0x18000abab  pop     r13
0x18000abad  pop     r12
0x18000abaf  pop     rdi
0x18000abb0  pop     rsi
0x18000abb1  pop     rbp
0x18000abb2  retn
0x18000abb4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
