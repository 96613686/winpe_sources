# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18000f484`
- end: `0x18000f73a`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e580`
- `0x180052f48`

## callees

- `0x18000f484`
- `0x18000f740`
- `0x180053080`
- `0x180053bd8`
- `0x18005bb30`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f56f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f5e6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f56f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000f5e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5f8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  WCHAR *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  LONG v11; // edi
  bool v12; // zf
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r8
  LONG v17; // r8d
  wil::details *v18; // rcx
  HANDLE Semaphore; // rsi
  unsigned __int64 v20; // rbp
  WCHAR *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  wil::details *v24; // rcx
  HANDLE v25; // rbx
  const wchar_t *v27; // r9
  __int64 v28; // rcx
  WCHAR *v29; // rdx
  __int64 v30; // rax
  WCHAR *v31; // rcx
  int LastErrorFailHr; // eax
  unsigned int v33; // esi
  WCHAR *v34; // rax
  const wchar_t *v35; // rcx
  __int64 v36; // rbx
  WCHAR *v37; // rcx
  int v38; // eax
  unsigned int v39; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(this);
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
    v27 = L"_p0";
    v28 = 2147483646;
    v29 = &Name[v16];
    v30 = 260 - v16;
    if ( v16 != 260 )
    {
      do
      {
        if ( !v28 )
          break;
        if ( !*v27 )
          break;
        *v29++ = *v27++;
        --v28;
        --v30;
      }
      while ( v30 );
    }
    v31 = v29 - 1;
    if ( v30 )
      v31 = v29;
    *v31 = 0;
  }
  v17 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v17 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v17, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v18);
    v33 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v33;
    }
  }
  v20 = a4 >> 31;
  v21 = Name;
  v22 = 260;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v22;
  }
  while ( v22 );
  v23 = (260 - v22) & -(__int64)(v22 != 0);
  if ( v22 )
  {
    v34 = &Name[v23];
    v35 = L"h";
    v36 = 260 - v23;
    if ( 260 != v23 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v35 )
          break;
        *v34++ = *v35++;
        --v8;
        --v36;
      }
      while ( v36 );
    }
    v37 = v34 - 1;
    if ( v36 )
      v37 = v34;
    *v37 = 0;
  }
  if ( (_DWORD)v20 )
    v11 = v20;
  v25 = CreateSemaphoreExW(0, v20, v11, Name, 0, 0x1F0003u);
  if ( v25 )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v25);
    return 0;
  }
  v38 = wil::details::GetLastErrorFailHr(v24);
  v39 = v38;
  if ( v38 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"wil",
    (const char *)(unsigned int)v38,
    dwFlagsa);
  return v39;
}

```

## disassembly

```asm
0x18000f484  mov     [rsp+arg_8], rbx
0x18000f489  mov     [rsp+arg_10], rbp
0x18000f48e  push    rsi
0x18000f48f  push    rdi
0x18000f490  push    r12
0x18000f492  push    r14
0x18000f494  push    r15
0x18000f496  sub     rsp, 250h
0x18000f49d  mov     rax, cs:__security_cookie
0x18000f4a4  xor     rax, rsp
0x18000f4a7  mov     [rsp+278h+var_38], rax
0x18000f4af  mov     rax, 0C000000000000000h
0x18000f4b9  mov     rbp, r9
0x18000f4bc  mov     r8, rdx
0x18000f4bf  mov     r15, rcx
0x18000f4c2  test    rax, r9
0x18000f4c5  jnz     loc_18000F734
0x18000f4cb  xor     r12d, r12d
0x18000f4ce  lea     rax, [rsp+278h+Name]
0x18000f4d3  mov     r14d, 7FFFFFFEh
0x18000f4d9  mov     ebx, 104h
0x18000f4de  mov     ecx, r14d
0x18000f4e1  mov     edx, ebx
0x18000f4e3  lea     edi, [r12+1]
0x18000f4e8  test    rcx, rcx
0x18000f4eb  jz      short loc_18000F50B
0x18000f4ed  movzx   r9d, word ptr [r8]
0x18000f4f1  test    r9w, r9w
0x18000f4f5  jz      short loc_18000F50B
0x18000f4f7  mov     [rax], r9w
0x18000f4fb  add     r8, 2
0x18000f4ff  add     rax, 2
0x18000f503  sub     rcx, rdi
0x18000f506  sub     rdx, rdi
0x18000f509  jnz     short loc_18000F4E8
0x18000f50b  test    rdx, rdx
0x18000f50e  lea     rcx, [rax-2]
0x18000f512  mov     rdx, rbx
0x18000f515  cmovnz  rcx, rax
0x18000f519  lea     rax, [rsp+278h+Name]
0x18000f51e  mov     [rcx], r12w
0x18000f522  cmp     [rax], r12w
0x18000f526  jz      short loc_18000F531
0x18000f528  add     rax, 2
0x18000f52c  sub     rdx, rdi
0x18000f52f  jnz     short loc_18000F522
0x18000f531  mov     rcx, rbx
0x18000f534  mov     rax, rdx
0x18000f537  sub     rcx, rdx
0x18000f53a  neg     rax
0x18000f53d  sbb     r8, r8
0x18000f540  and     r8, rcx
0x18000f543  test    rdx, rdx
0x18000f546  jnz     loc_18000F60E
0x18000f54c  mov     edx, ebp
0x18000f54e  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000f556  and     edx, 7FFFFFFFh; lInitialCount
0x18000f55c  mov     [rsp+278h+dwFlags], r12d; int
0x18000f561  mov     r8d, edi
0x18000f564  lea     r9, [rsp+278h+Name]; lpName
0x18000f569  cmova   r8d, edx; lMaximumCount
0x18000f56d  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f56f  call    cs:__imp_CreateSemaphoreExW
0x18000f575  mov     rsi, rax
0x18000f578  test    rax, rax
0x18000f57b  jz      loc_18000F660
0x18000f581  call    cs:__imp_GetLastError
0x18000f587  mov     rdx, rsi
0x18000f58a  mov     rcx, r15
0x18000f58d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f592  shr     rbp, 1Fh
0x18000f596  lea     rax, [rsp+278h+Name]
0x18000f59b  mov     rdx, rbx
0x18000f59e  cmp     [rax], r12w
0x18000f5a2  jz      short loc_18000F5AD
0x18000f5a4  add     rax, 2
0x18000f5a8  sub     rdx, rdi
0x18000f5ab  jnz     short loc_18000F59E
0x18000f5ad  mov     rcx, rbx
0x18000f5b0  mov     rax, rdx
0x18000f5b3  sub     rcx, rdx
0x18000f5b6  neg     rax
0x18000f5b9  sbb     r8, r8
0x18000f5bc  and     r8, rcx
0x18000f5bf  test    rdx, rdx
0x18000f5c2  jnz     loc_18000F6B9
0x18000f5c8  test    ebp, ebp
0x18000f5ca  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000f5d2  lea     r9, [rsp+278h+Name]; lpName
0x18000f5d7  mov     [rsp+278h+dwFlags], r12d; int
0x18000f5dc  cmovnz  edi, ebp
0x18000f5df  mov     edx, ebp; lInitialCount
0x18000f5e1  mov     r8d, edi; lMaximumCount
0x18000f5e4  xor     ecx, ecx; lpSemaphoreAttributes
0x18000f5e6  call    cs:__imp_CreateSemaphoreExW
0x18000f5ec  mov     rbx, rax
0x18000f5ef  test    rax, rax
0x18000f5f2  jz      loc_18000F702
0x18000f5f8  call    cs:__imp_GetLastError
0x18000f5fe  lea     rcx, [r15+8]
0x18000f602  mov     rdx, rbx
0x18000f605  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f60a  xor     eax, eax
0x18000f60c  jmp     short loc_18000F68D
0x18000f60e  mov     rax, rbx
0x18000f611  lea     rdx, [rsp+278h+Name]
0x18000f616  lea     r9, aP0; "_p0"
0x18000f61d  mov     rcx, r14
0x18000f620  lea     rdx, [rdx+r8*2]
0x18000f624  sub     rax, r8
0x18000f627  jz      short loc_18000F64C
0x18000f629  test    rcx, rcx
0x18000f62c  jz      short loc_18000F64C
0x18000f62e  movzx   r8d, word ptr [r9]
0x18000f632  test    r8w, r8w
0x18000f636  jz      short loc_18000F64C
0x18000f638  mov     [rdx], r8w
0x18000f63c  add     r9, 2
0x18000f640  add     rdx, 2
0x18000f644  sub     rcx, rdi
0x18000f647  sub     rax, rdi
0x18000f64a  jnz     short loc_18000F629
0x18000f64c  test    rax, rax
0x18000f64f  lea     rcx, [rdx-2]
0x18000f653  cmovnz  rcx, rdx
0x18000f657  mov     [rcx], r12w
0x18000f65b  jmp     loc_18000F54C
0x18000f660  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f665  mov     esi, eax
0x18000f667  test    eax, eax
0x18000f669  jns     loc_18000F592
0x18000f66f  mov     rcx, [rsp+278h]; this
0x18000f677  lea     r8, aWil; "wil"
0x18000f67e  mov     r9d, eax; char *
0x18000f681  mov     edx, 8Bh; void *
0x18000f686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f68b  mov     eax, esi
0x18000f68d  mov     rcx, [rsp+278h+var_38]
0x18000f695  xor     rcx, rsp; StackCookie
0x18000f698  call    __security_check_cookie
0x18000f69d  lea     r11, [rsp+278h+var_28]
0x18000f6a5  mov     rbx, [r11+38h]
0x18000f6a9  mov     rbp, [r11+40h]
0x18000f6ad  mov     rsp, r11
0x18000f6b0  pop     r15
0x18000f6b2  pop     r14
0x18000f6b4  pop     r12
0x18000f6b6  pop     rdi
0x18000f6b7  pop     rsi
0x18000f6b8  retn
0x18000f6b9  lea     rax, [rsp+278h+Name]
0x18000f6be  lea     rax, [rax+r8*2]
0x18000f6c2  lea     rcx, asc_1800ABBA8; "h"
0x18000f6c9  sub     rbx, r8
0x18000f6cc  jz      short loc_18000F6EE
0x18000f6ce  test    r14, r14
0x18000f6d1  jz      short loc_18000F6EE
0x18000f6d3  movzx   edx, word ptr [rcx]
0x18000f6d6  test    dx, dx
0x18000f6d9  jz      short loc_18000F6EE
0x18000f6db  mov     [rax], dx
0x18000f6de  add     rcx, 2
0x18000f6e2  add     rax, 2
0x18000f6e6  sub     r14, rdi
0x18000f6e9  sub     rbx, rdi
0x18000f6ec  jnz     short loc_18000F6CE
0x18000f6ee  test    rbx, rbx
0x18000f6f1  lea     rcx, [rax-2]
0x18000f6f5  cmovnz  rcx, rax
0x18000f6f9  mov     [rcx], r12w
0x18000f6fd  jmp     loc_18000F5C8
0x18000f702  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f707  mov     ebx, eax
0x18000f709  test    eax, eax
0x18000f70b  jns     loc_18000F60A
0x18000f711  mov     rcx, [rsp+278h]; this
0x18000f719  lea     r8, aWil; "wil"
0x18000f720  mov     r9d, eax; char *
0x18000f723  mov     edx, 90h; void *
0x18000f728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f72d  mov     eax, ebx
0x18000f72f  jmp     loc_18000F68D
0x18000f734  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
