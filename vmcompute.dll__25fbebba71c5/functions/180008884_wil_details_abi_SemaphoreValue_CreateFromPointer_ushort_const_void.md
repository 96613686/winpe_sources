# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180008884`
- end: `0x180008a44`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `448`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000704c`
- `0x180007474`

## callees

- `0x180002f50`
- `0x180008884`
- `0x180009768`
- `0x18000c294`
- `0x18000cb6c`
- `0x18000e638`
- `0x18000ebb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008943`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800089d0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180008943`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800089d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // rdi
  wil::details *v19; // rcx
  HANDLE v20; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v6 = a3 >> 2;
  v7 = Name;
  v8 = 2147483646;
  v9 = 260;
  v10 = 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = 1;
  if ( (v6 & 0x7FFFFFFF) != 0 )
    v12 = v6 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, v6 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
LABEL_15:
    StringCchCatW(Name, 0x104u, L"h");
    v18 = v6 >> 31;
    if ( (_DWORD)v18 )
      v10 = v18;
    v20 = CreateSemaphoreExW(0, v18, v10, Name, 0, 0x1F0003u);
    if ( v20 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v20);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v19);
      v16 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v17 = 144;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
  v16 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v17 = 139;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"wil",
    (const char *)(unsigned int)LastErrorFailHr,
    dwFlags);
  return v16;
}

```

## disassembly

```asm
0x180008884  mov     [rsp+arg_8], rbx
0x180008889  push    rbp
0x18000888a  push    rsi
0x18000888b  push    rdi
0x18000888c  push    r14
0x18000888e  push    r15
0x180008890  sub     rsp, 250h
0x180008897  mov     rax, cs:__security_cookie
0x18000889e  xor     rax, rsp
0x1800088a1  mov     [rsp+278h+var_38], rax
0x1800088a9  mov     rdi, r8
0x1800088ac  mov     rbp, rcx
0x1800088af  mov     r8, rdx
0x1800088b2  test    dil, 3
0x1800088b6  jnz     loc_180008A3E
0x1800088bc  shr     rdi, 2
0x1800088c0  lea     rax, [rsp+278h+Name]
0x1800088c5  xor     r14d, r14d
0x1800088c8  mov     r15d, 104h
0x1800088ce  mov     ecx, 7FFFFFFEh
0x1800088d3  mov     edx, r15d
0x1800088d6  lea     esi, [r14+1]
0x1800088da  test    rcx, rcx
0x1800088dd  jz      short loc_1800088FD
0x1800088df  movzx   r9d, word ptr [r8]
0x1800088e3  test    r9w, r9w
0x1800088e7  jz      short loc_1800088FD
0x1800088e9  mov     [rax], r9w
0x1800088ed  add     r8, 2
0x1800088f1  add     rax, 2
0x1800088f5  sub     rcx, rsi
0x1800088f8  sub     rdx, rsi
0x1800088fb  jnz     short loc_1800088DA
0x1800088fd  test    rdx, rdx
0x180008900  lea     rcx, [rax-2]
0x180008904  lea     r8, aP0; "_p0"
0x18000890b  mov     rdx, r15; unsigned __int64
0x18000890e  cmovnz  rcx, rax
0x180008912  mov     [rcx], r14w
0x180008916  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000891b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008920  mov     edx, edi
0x180008922  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000892a  and     edx, 7FFFFFFFh; lInitialCount
0x180008930  mov     [rsp+278h+dwFlags], r14d; int
0x180008935  mov     r8d, esi
0x180008938  lea     r9, [rsp+278h+Name]; lpName
0x18000893d  cmova   r8d, edx; lMaximumCount
0x180008941  xor     ecx, ecx; lpSemaphoreAttributes
0x180008943  call    cs:__imp_CreateSemaphoreExW
0x18000894a  nop     dword ptr [rax+rax+00h]
0x18000894f  mov     rbx, rax
0x180008952  test    rax, rax
0x180008955  jnz     short loc_180008983
0x180008957  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000895c  mov     ebx, eax
0x18000895e  test    eax, eax
0x180008960  jns     short loc_18000899A
0x180008962  mov     edx, 8Bh; void *
0x180008967  mov     rcx, [rsp+278h]; this
0x18000896f  lea     r8, aWil; "wil"
0x180008976  mov     r9d, eax; char *
0x180008979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000897e  jmp     loc_180008A14
0x180008983  call    cs:__imp_GetLastError
0x18000898a  nop     dword ptr [rax+rax+00h]
0x18000898f  mov     rdx, rbx
0x180008992  mov     rcx, rbp
0x180008995  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000899a  lea     r8, asc_18008E420; "h"
0x1800089a1  mov     rdx, r15; unsigned __int64
0x1800089a4  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800089a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800089ae  shr     rdi, 1Fh
0x1800089b2  lea     r9, [rsp+278h+Name]; lpName
0x1800089b7  test    edi, edi
0x1800089b9  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800089c1  mov     edx, edi; lInitialCount
0x1800089c3  mov     [rsp+278h+dwFlags], r14d; dwFlags
0x1800089c8  cmovnz  esi, edi
0x1800089cb  xor     ecx, ecx; lpSemaphoreAttributes
0x1800089cd  mov     r8d, esi; lMaximumCount
0x1800089d0  call    cs:__imp_CreateSemaphoreExW
0x1800089d7  nop     dword ptr [rax+rax+00h]
0x1800089dc  mov     rbx, rax
0x1800089df  test    rax, rax
0x1800089e2  jnz     short loc_1800089F9
0x1800089e4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800089e9  mov     ebx, eax
0x1800089eb  test    eax, eax
0x1800089ed  jns     short loc_180008A11
0x1800089ef  mov     edx, 90h
0x1800089f4  jmp     loc_180008967
0x1800089f9  call    cs:__imp_GetLastError
0x180008a00  nop     dword ptr [rax+rax+00h]
0x180008a05  lea     rcx, [rbp+8]
0x180008a09  mov     rdx, rbx
0x180008a0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008a11  mov     ebx, r14d
0x180008a14  mov     eax, ebx
0x180008a16  mov     rcx, [rsp+278h+var_38]
0x180008a1e  xor     rcx, rsp; StackCookie
0x180008a21  call    __security_check_cookie
0x180008a26  mov     rbx, [rsp+278h+arg_8]
0x180008a2e  add     rsp, 250h
0x180008a35  pop     r15
0x180008a37  pop     r14
0x180008a39  pop     rdi
0x180008a3a  pop     rsi
0x180008a3b  pop     rbp
0x180008a3c  retn
0x180008a3e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
