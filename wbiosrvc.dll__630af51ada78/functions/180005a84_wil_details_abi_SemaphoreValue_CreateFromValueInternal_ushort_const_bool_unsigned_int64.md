# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180005a84`
- end: `0x180005c2b`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `423`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000592c`
- `0x18005cc74`

## callees

- `0x180003c20`
- `0x180004d04`
- `0x180005a84`
- `0x180005c34`
- `0x18005388c`
- `0x180056c88`
- `0x180056ce0`
- `0x180068f60`
- `0x18006cad8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b7d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bb6`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // edi
  bool v11; // zf
  WCHAR *v12; // rcx
  __int64 v13; // r8
  WCHAR *v14; // rax
  __int64 v15; // r9
  LONG v16; // r8d
  wil::details *v17; // rcx
  HANDLE Semaphore; // rbx
  unsigned __int64 v19; // rdx
  int LastErrorFailHr; // ebx
  __int64 v21; // rdx
  unsigned __int64 v23; // rsi
  size_t dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
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
  v11 = v9 == 0;
  v12 = v7 - 1;
  v13 = 260;
  if ( !v11 )
    v12 = v7;
  v14 = Name;
  *v12 = 0;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  if ( v13 )
  {
    v15 = (260 - v13) & -(__int64)(v13 != 0);
    StringCopyWorkerW(&Name[v15], 260 - v15, (size_t *)v13, L"_p0", dwFlags);
  }
  v16 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v16 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v16, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v17);
    if ( LastErrorFailHr < 0 )
    {
      v21 = 139;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlagsa);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v23 = a4 >> 31;
  StringCchCatW(Name, v19, L"h");
  if ( (_DWORD)v23 )
    v10 = v23;
  LastErrorFailHr = _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                      (char *)this + 8,
                      (unsigned int)v23,
                      v10,
                      Name);
  if ( LastErrorFailHr < 0 )
  {
    v21 = 144;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x180005a84  mov     [rsp+arg_8], rbx
0x180005a89  mov     [rsp+arg_10], rbp
0x180005a8e  push    rsi
0x180005a8f  push    rdi
0x180005a90  push    r14
0x180005a92  sub     rsp, 260h
0x180005a99  mov     rax, cs:__security_cookie
0x180005aa0  xor     rax, rsp
0x180005aa3  mov     [rsp+278h+var_28], rax
0x180005aab  mov     rax, 0C000000000000000h
0x180005ab5  mov     rsi, r9
0x180005ab8  mov     r10, rdx
0x180005abb  mov     rbp, rcx
0x180005abe  test    rax, r9
0x180005ac1  jz      short loc_180005AC9
0x180005ac3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005ac9  xor     r14d, r14d
0x180005acc  lea     rax, [rsp+278h+Name]
0x180005ad1  mov     edx, 104h
0x180005ad6  mov     ecx, 7FFFFFFEh
0x180005adb  mov     r8d, edx
0x180005ade  lea     edi, [r14+1]
0x180005ae2  test    rcx, rcx
0x180005ae5  jz      short loc_180005B05
0x180005ae7  movzx   r9d, word ptr [r10]
0x180005aeb  test    r9w, r9w
0x180005aef  jz      short loc_180005B05
0x180005af1  mov     [rax], r9w
0x180005af5  add     r10, 2
0x180005af9  add     rax, 2
0x180005afd  sub     rcx, rdi
0x180005b00  sub     r8, rdi
0x180005b03  jnz     short loc_180005AE2
0x180005b05  test    r8, r8
0x180005b08  lea     rcx, [rax-2]
0x180005b0c  mov     r8, rdx
0x180005b0f  cmovnz  rcx, rax
0x180005b13  lea     rax, [rsp+278h+Name]
0x180005b18  mov     [rcx], r14w
0x180005b1c  cmp     [rax], r14w
0x180005b20  jz      short loc_180005B2B
0x180005b22  add     rax, 2
0x180005b26  sub     r8, rdi; pcchNewDestLength
0x180005b29  jnz     short loc_180005B1C
0x180005b2b  mov     rcx, rdx
0x180005b2e  mov     rax, r8
0x180005b31  sub     rcx, r8
0x180005b34  neg     rax
0x180005b37  sbb     r9, r9
0x180005b3a  and     r9, rcx
0x180005b3d  test    r8, r8
0x180005b40  jz      short loc_180005B5A
0x180005b42  sub     rdx, r9; cchDest
0x180005b45  lea     rcx, [rsp+278h+Name]
0x180005b4a  lea     rcx, [rcx+r9*2]; pszDest
0x180005b4e  lea     r9, aP0; "_p0"
0x180005b55  call    StringCopyWorkerW
0x180005b5a  mov     edx, esi
0x180005b5c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005b64  and     edx, 7FFFFFFFh; lInitialCount
0x180005b6a  mov     dword ptr [rsp+278h+dwFlags], r14d; int
0x180005b6f  mov     r8d, edi
0x180005b72  lea     r9, [rsp+278h+Name]; lpName
0x180005b77  cmova   r8d, edx; lMaximumCount
0x180005b7b  xor     ecx, ecx; lpSemaphoreAttributes
0x180005b7d  call    cs:__imp_CreateSemaphoreExW
0x180005b83  mov     rbx, rax
0x180005b86  test    rax, rax
0x180005b89  jnz     short loc_180005BB6
0x180005b8b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005b90  mov     ebx, eax
0x180005b92  test    eax, eax
0x180005b94  jns     short loc_180005BC7
0x180005b96  mov     edx, 8Bh; void *
0x180005b9b  mov     rcx, [rsp+278h]; this
0x180005ba3  lea     r8, aWil; "wil"
0x180005baa  mov     r9d, ebx; char *
0x180005bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bb2  mov     eax, ebx
0x180005bb4  jmp     short loc_180005C03
0x180005bb6  call    cs:__imp_GetLastError
0x180005bbc  mov     rdx, rbx
0x180005bbf  mov     rcx, rbp
0x180005bc2  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005bc7  lea     r8, asc_1800DCDDC; "h"
0x180005bce  shr     rsi, 1Fh
0x180005bd2  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180005bd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005bdc  test    esi, esi
0x180005bde  lea     rcx, [rbp+8]
0x180005be2  lea     r9, [rsp+278h+Name]
0x180005be7  mov     edx, esi
0x180005be9  cmovnz  edi, esi
0x180005bec  mov     r8d, edi
0x180005bef  call    ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180005bf4  mov     ebx, eax
0x180005bf6  test    eax, eax
0x180005bf8  jns     short loc_180005C01
0x180005bfa  mov     edx, 90h
0x180005bff  jmp     short loc_180005B9B
0x180005c01  xor     eax, eax
0x180005c03  mov     rcx, [rsp+278h+var_28]
0x180005c0b  xor     rcx, rsp; StackCookie
0x180005c0e  call    __security_check_cookie
0x180005c13  lea     r11, [rsp+278h+var_18]
0x180005c1b  mov     rbx, [r11+28h]
0x180005c1f  mov     rbp, [r11+30h]
0x180005c23  mov     rsp, r11
0x180005c26  pop     r14
0x180005c28  pop     rdi
0x180005c29  pop     rsi
0x180005c2a  retn
```
