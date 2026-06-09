# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180008288`
- end: `0x18000843e`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000794c`
- `0x180007d44`

## callees

- `0x180008288`
- `0x180009508`
- `0x18000cb0c`
- `0x18000d934`
- `0x18000eab4`
- `0x18000ee68`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008383`
- `KERNEL32!GetLastError` at `0x1800083f2`
- `KERNEL32!GetLastError` at `0x180008383`
- `KERNEL32!GetLastError` at `0x1800083f2`
- `KERNEL32!CreateSemaphoreExW` at `0x18000834a`
- `KERNEL32!CreateSemaphoreExW` at `0x1800083c9`
- `KERNEL32!CreateSemaphoreExW` at `0x18000834a`
- `KERNEL32!CreateSemaphoreExW` at `0x1800083c9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromPointer(
        wil::details_abi::SemaphoreValue *this,
        char *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v4; // rbx
  signed __int64 v5; // r8
  WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rsi
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned __int64 v17; // rdx
  unsigned int v18; // r8d
  unsigned int v19; // ebx
  __int64 v20; // rdx
  wil::details *v21; // rcx
  HANDLE v22; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( (a3 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v4 = a3 >> 2;
  v5 = a2 - (char *)Name;
  v6 = Name;
  v7 = 260;
  v8 = 1;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v5);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v7;
  }
  while ( v7 );
  v10 = v6 - 1;
  if ( v7 )
    v10 = v6;
  *v10 = 0;
  StringCchCatW(Name, v7, L"_p0");
  v11 = 1;
  v12 = v4 >> 31;
  v13 = v4 & 0x7FFFFFFF;
  if ( v13 )
    v11 = v13;
  Semaphore = CreateSemaphoreExW(0, v13, v11, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
LABEL_15:
    StringCchCatW(Name, v17, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v22 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v22 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v22);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v21);
      v19 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v20 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v19 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v20 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v20, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v19;
}

```

## disassembly

```asm
0x180008288  mov     [rsp+arg_8], rbx
0x18000828d  mov     [rsp+arg_18], rbp
0x180008292  push    rsi
0x180008293  push    rdi
0x180008294  push    r14
0x180008296  sub     rsp, 250h
0x18000829d  mov     rax, cs:__security_cookie
0x1800082a4  xor     rax, rsp
0x1800082a7  mov     [rsp+268h+var_28], rax
0x1800082af  mov     rbx, r8
0x1800082b2  mov     rbp, rcx
0x1800082b5  mov     r8, rdx
0x1800082b8  test    bl, 3
0x1800082bb  jnz     loc_180008438
0x1800082c1  lea     rax, [rsp+268h+Name]
0x1800082c6  shr     rbx, 2
0x1800082ca  sub     r8, rax
0x1800082cd  lea     rcx, [rsp+268h+Name]
0x1800082d2  xor     r14d, r14d
0x1800082d5  mov     edx, 104h
0x1800082da  lea     edi, [r14+1]
0x1800082de  lea     rax, [rdx+7FFFFEFAh]
0x1800082e5  test    rax, rax
0x1800082e8  jz      short loc_180008300
0x1800082ea  movzx   eax, word ptr [r8+rcx]
0x1800082ef  test    ax, ax
0x1800082f2  jz      short loc_180008300
0x1800082f4  mov     [rcx], ax
0x1800082f7  add     rcx, 2
0x1800082fb  sub     rdx, rdi; unsigned __int64
0x1800082fe  jnz     short loc_1800082DE
0x180008300  lea     rax, [rcx-2]
0x180008304  test    rdx, rdx
0x180008307  lea     r8, aP0; "_p0"
0x18000830e  cmovnz  rax, rcx
0x180008312  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180008317  mov     [rax], r14w
0x18000831b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008320  mov     rsi, rbx
0x180008323  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000832b  mov     r8d, edi
0x18000832e  shr     rsi, 1Fh
0x180008332  and     ebx, 7FFFFFFFh
0x180008338  mov     [rsp+268h+dwFlags], r14d; int
0x18000833d  lea     r9, [rsp+268h+Name]; lpName
0x180008342  mov     edx, ebx; lInitialCount
0x180008344  cmova   r8d, ebx; lMaximumCount
0x180008348  xor     ecx, ecx; lpSemaphoreAttributes
0x18000834a  call    cs:__imp_CreateSemaphoreExW
0x180008351  nop     dword ptr [rax+rax+00h]
0x180008356  mov     rbx, rax
0x180008359  test    rax, rax
0x18000835c  jnz     short loc_180008383
0x18000835e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008363  mov     ebx, eax
0x180008365  test    eax, eax
0x180008367  jns     short loc_18000839A
0x180008369  mov     edx, 88h; void *
0x18000836e  mov     rcx, [rsp+268h]; this
0x180008376  mov     r9d, eax; char *
0x180008379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000837e  jmp     loc_18000840D
0x180008383  call    cs:__imp_GetLastError
0x18000838a  nop     dword ptr [rax+rax+00h]
0x18000838f  mov     rdx, rbx
0x180008392  mov     rcx, rbp
0x180008395  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000839a  lea     r8, asc_180020AB8; "h"
0x1800083a1  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x1800083a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800083ab  test    esi, esi
0x1800083ad  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800083b5  lea     r9, [rsp+268h+Name]; lpName
0x1800083ba  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x1800083bf  cmovnz  edi, esi
0x1800083c2  mov     edx, esi; lInitialCount
0x1800083c4  mov     r8d, edi; lMaximumCount
0x1800083c7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800083c9  call    cs:__imp_CreateSemaphoreExW
0x1800083d0  nop     dword ptr [rax+rax+00h]
0x1800083d5  mov     rbx, rax
0x1800083d8  test    rax, rax
0x1800083db  jnz     short loc_1800083F2
0x1800083dd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800083e2  mov     ebx, eax
0x1800083e4  test    eax, eax
0x1800083e6  jns     short loc_18000840A
0x1800083e8  mov     edx, 8Dh
0x1800083ed  jmp     loc_18000836E
0x1800083f2  call    cs:__imp_GetLastError
0x1800083f9  nop     dword ptr [rax+rax+00h]
0x1800083fe  mov     rdx, rbx
0x180008401  lea     rcx, [rbp+8]
0x180008405  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000840a  mov     ebx, r14d
0x18000840d  mov     eax, ebx
0x18000840f  mov     rcx, [rsp+268h+var_28]
0x180008417  xor     rcx, rsp; StackCookie
0x18000841a  call    __security_check_cookie
0x18000841f  lea     r11, [rsp+268h+var_18]
0x180008427  mov     rbx, [r11+28h]
0x18000842b  mov     rbp, [r11+38h]
0x18000842f  mov     rsp, r11
0x180008432  pop     r14
0x180008434  pop     rdi
0x180008435  pop     rsi
0x180008436  retn
0x180008438  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
