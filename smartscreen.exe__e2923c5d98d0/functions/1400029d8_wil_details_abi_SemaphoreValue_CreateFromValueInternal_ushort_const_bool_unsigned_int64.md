# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400029d8`
- end: `0x140002c30`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `600`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400030a8`

## callees

- `0x1400029d8`
- `0x140002c38`
- `0x14000cec0`
- `0x140016ce4`
- `0x140016da0`
- `0x140025aa0`
- `0x14002e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002b04`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002bbc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002b04`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140002bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bf5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  LONG v11; // ebx
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  const wchar_t *v17; // rcx
  WCHAR *v18; // rdx
  __int64 v19; // rax
  WCHAR *v20; // rcx
  LONG v21; // r8d
  wil::details *v22; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v25; // esi
  unsigned __int64 v27; // rbp
  WCHAR *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  wil::details *v31; // rcx
  HANDLE v32; // rbx
  int v33; // eax
  unsigned int v34; // ebx
  size_t dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = Name;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = 260;
  v11 = 1;
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *v7++ = *a2++;
    --v9;
    --v10;
  }
  while ( v10 );
  v12 = v10 == 0;
  v13 = v7 - 1;
  v14 = 260;
  if ( !v12 )
    v13 = v7;
  v15 = Name;
  *v13 = 0;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = (260 - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v17 = L"_p0";
    v18 = &Name[v16];
    v19 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v8;
        --v19;
      }
      while ( v19 );
    }
    v20 = v18 - 1;
    if ( v19 )
      v20 = v18;
    *v20 = 0;
  }
  v21 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v21 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v21, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v22);
    v25 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v25;
    }
  }
  v27 = a4 >> 31;
  v28 = Name;
  v29 = 260;
  do
  {
    if ( !*v28 )
      break;
    ++v28;
    --v29;
  }
  while ( v29 );
  if ( v29 )
  {
    v30 = (260 - v29) & -(__int64)(v29 != 0);
    StringCopyWorkerW(&Name[v30], 260 - v30, (size_t *)v30, L"h", dwFlags);
  }
  if ( (_DWORD)v27 )
    v11 = v27;
  v32 = CreateSemaphoreExW(0, v27, v11, Name, 0, 0x1F0003u);
  if ( v32 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v32);
  }
  else
  {
    v33 = wil::details::GetLastErrorFailHr(v31);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"wil",
        (const char *)(unsigned int)v33,
        dwFlagsa);
      return v34;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400029d8  mov     [rsp+arg_8], rbx
0x1400029dd  push    rbp
0x1400029de  push    rsi
0x1400029df  push    rdi
0x1400029e0  push    r14
0x1400029e2  push    r15
0x1400029e4  sub     rsp, 250h
0x1400029eb  mov     rax, cs:__security_cookie
0x1400029f2  xor     rax, rsp
0x1400029f5  mov     [rsp+278h+var_38], rax
0x1400029fd  mov     rax, 0C000000000000000h
0x140002a07  mov     rbp, r9
0x140002a0a  mov     r8, rdx
0x140002a0d  mov     r14, rcx
0x140002a10  test    rax, r9
0x140002a13  jz      short loc_140002A1B
0x140002a15  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002a1b  xor     r15d, r15d
0x140002a1e  lea     rax, [rsp+278h+Name]
0x140002a23  mov     r9d, 7FFFFFFEh
0x140002a29  mov     edi, 104h
0x140002a2e  mov     ecx, r9d
0x140002a31  mov     edx, edi
0x140002a33  lea     ebx, [r15+1]
0x140002a37  test    rcx, rcx
0x140002a3a  jz      short loc_140002A5A
0x140002a3c  movzx   r10d, word ptr [r8]
0x140002a40  test    r10w, r10w
0x140002a44  jz      short loc_140002A5A
0x140002a46  mov     [rax], r10w
0x140002a4a  add     r8, 2
0x140002a4e  add     rax, 2
0x140002a52  sub     rcx, rbx
0x140002a55  sub     rdx, rbx
0x140002a58  jnz     short loc_140002A37
0x140002a5a  test    rdx, rdx
0x140002a5d  lea     rcx, [rax-2]
0x140002a61  mov     rdx, rdi
0x140002a64  cmovnz  rcx, rax
0x140002a68  lea     rax, [rsp+278h+Name]
0x140002a6d  mov     [rcx], r15w
0x140002a71  cmp     [rax], r15w
0x140002a75  jz      short loc_140002A80
0x140002a77  add     rax, 2
0x140002a7b  sub     rdx, rbx
0x140002a7e  jnz     short loc_140002A71
0x140002a80  mov     rcx, rdi
0x140002a83  mov     rax, rdx
0x140002a86  sub     rcx, rdx
0x140002a89  neg     rax
0x140002a8c  sbb     r8, r8
0x140002a8f  and     r8, rcx
0x140002a92  test    rdx, rdx
0x140002a95  jz      short loc_140002AE1
0x140002a97  mov     rax, rdi
0x140002a9a  lea     rdx, [rsp+278h+Name]
0x140002a9f  lea     rcx, aP0; "_p0"
0x140002aa6  lea     rdx, [rdx+r8*2]
0x140002aaa  sub     rax, r8
0x140002aad  jz      short loc_140002AD2
0x140002aaf  test    r9, r9
0x140002ab2  jz      short loc_140002AD2
0x140002ab4  movzx   r8d, word ptr [rcx]
0x140002ab8  test    r8w, r8w
0x140002abc  jz      short loc_140002AD2
0x140002abe  mov     [rdx], r8w
0x140002ac2  add     rcx, 2
0x140002ac6  add     rdx, 2
0x140002aca  sub     r9, rbx
0x140002acd  sub     rax, rbx
0x140002ad0  jnz     short loc_140002AAF
0x140002ad2  test    rax, rax
0x140002ad5  lea     rcx, [rdx-2]
0x140002ad9  cmovnz  rcx, rdx
0x140002add  mov     [rcx], r15w
0x140002ae1  mov     edx, ebp
0x140002ae3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002aeb  and     edx, 7FFFFFFFh; lInitialCount
0x140002af1  mov     dword ptr [rsp+278h+dwFlags], r15d; int
0x140002af6  mov     r8d, ebx
0x140002af9  lea     r9, [rsp+278h+Name]; lpName
0x140002afe  cmova   r8d, edx; lMaximumCount
0x140002b02  xor     ecx, ecx; lpSemaphoreAttributes
0x140002b04  call    cs:__imp_CreateSemaphoreExW
0x140002b0a  mov     rsi, rax
0x140002b0d  test    rax, rax
0x140002b10  jnz     short loc_140002B40
0x140002b12  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002b17  mov     esi, eax
0x140002b19  test    eax, eax
0x140002b1b  jns     short loc_140002B51
0x140002b1d  mov     rcx, [rsp+278h]; this
0x140002b25  lea     r8, aWil; "wil"
0x140002b2c  mov     r9d, eax; char *
0x140002b2f  mov     edx, 8Bh; void *
0x140002b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002b39  mov     eax, esi
0x140002b3b  jmp     loc_140002C09
0x140002b40  call    cs:__imp_GetLastError
0x140002b46  mov     rdx, rsi
0x140002b49  mov     rcx, r14
0x140002b4c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140002b51  shr     rbp, 1Fh
0x140002b55  lea     rax, [rsp+278h+Name]
0x140002b5a  mov     rdx, rdi
0x140002b5d  cmp     [rax], r15w
0x140002b61  jz      short loc_140002B6C
0x140002b63  add     rax, 2
0x140002b67  sub     rdx, rbx
0x140002b6a  jnz     short loc_140002B5D
0x140002b6c  mov     rcx, rdi
0x140002b6f  mov     rax, rdx
0x140002b72  sub     rcx, rdx
0x140002b75  neg     rax
0x140002b78  sbb     r8, r8
0x140002b7b  and     r8, rcx; pcchNewDestLength
0x140002b7e  test    rdx, rdx
0x140002b81  jz      short loc_140002B9E
0x140002b83  sub     rdi, r8
0x140002b86  lea     rcx, [rsp+278h+Name]
0x140002b8b  lea     rcx, [rcx+r8*2]; pszDest
0x140002b8f  mov     rdx, rdi; cchDest
0x140002b92  lea     r9, pszSrc; "h"
0x140002b99  call    StringCopyWorkerW
0x140002b9e  test    ebp, ebp
0x140002ba0  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140002ba8  lea     r9, [rsp+278h+Name]; lpName
0x140002bad  mov     dword ptr [rsp+278h+dwFlags], r15d; int
0x140002bb2  cmovnz  ebx, ebp
0x140002bb5  mov     edx, ebp; lInitialCount
0x140002bb7  mov     r8d, ebx; lMaximumCount
0x140002bba  xor     ecx, ecx; lpSemaphoreAttributes
0x140002bbc  call    cs:__imp_CreateSemaphoreExW
0x140002bc2  mov     rbx, rax
0x140002bc5  test    rax, rax
0x140002bc8  jnz     short loc_140002BF5
0x140002bca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002bcf  mov     ebx, eax
0x140002bd1  test    eax, eax
0x140002bd3  jns     short loc_140002C07
0x140002bd5  mov     rcx, [rsp+278h]; this
0x140002bdd  lea     r8, aWil; "wil"
0x140002be4  mov     r9d, eax; char *
0x140002be7  mov     edx, 90h; void *
0x140002bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002bf1  mov     eax, ebx
0x140002bf3  jmp     short loc_140002C09
0x140002bf5  call    cs:__imp_GetLastError
0x140002bfb  lea     rcx, [r14+8]
0x140002bff  mov     rdx, rbx
0x140002c02  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140002c07  xor     eax, eax
0x140002c09  mov     rcx, [rsp+278h+var_38]
0x140002c11  xor     rcx, rsp; StackCookie
0x140002c14  call    __security_check_cookie
0x140002c19  mov     rbx, [rsp+278h+arg_8]
0x140002c21  add     rsp, 250h
0x140002c28  pop     r15
0x140002c2a  pop     r14
0x140002c2c  pop     rdi
0x140002c2d  pop     rsi
0x140002c2e  pop     rbp
0x140002c2f  retn
```
