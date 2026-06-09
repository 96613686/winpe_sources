# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000a5c4`
- end: `0x18000a781`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `445`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009c54`
- `0x18000a04c`

## callees

- `0x18000a5c4`
- `0x18000b1c8`
- `0x18000d2c8`
- `0x18000d888`
- `0x18000e5a8`
- `0x18000e860`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a6c4`
- `KERNEL32!GetLastError` at `0x18000a736`
- `KERNEL32!GetLastError` at `0x18000a6c4`
- `KERNEL32!GetLastError` at `0x18000a736`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a68b`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a70d`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a68b`
- `KERNEL32!CreateSemaphoreExW` at `0x18000a70d`

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
  __int64 v7; // rdx
  LONG v8; // edi
  WCHAR v9; // ax
  WCHAR *v10; // rax
  LONG v11; // r8d
  unsigned __int64 v12; // rsi
  LONG v13; // ebx
  wil::details *v14; // rcx
  HANDLE Semaphore; // rbx
  int LastErrorFailHr; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  __int64 v19; // rdx
  wil::details *v20; // rcx
  HANDLE v21; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

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
  StringCchCatW(Name, 0x104u, L"_p0");
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
    StringCchCatW(Name, 0x104u, L"h");
    if ( (_DWORD)v12 )
      v8 = v12;
    v21 = CreateSemaphoreExW(0, v12, v8, Name, 0, 0x1F0003u);
    if ( v21 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v21);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v20);
      v18 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v19 = 141;
        goto LABEL_13;
      }
    }
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
  v18 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_15;
  v19 = 136;
LABEL_13:
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
  return v18;
}

```

## disassembly

```asm
0x18000a5c4  mov     [rsp+arg_8], rbx
0x18000a5c9  push    rbp
0x18000a5ca  push    rsi
0x18000a5cb  push    rdi
0x18000a5cc  push    r14
0x18000a5ce  push    r15
0x18000a5d0  sub     rsp, 250h
0x18000a5d7  mov     rax, cs:__security_cookie
0x18000a5de  xor     rax, rsp
0x18000a5e1  mov     [rsp+278h+var_38], rax
0x18000a5e9  mov     rbx, r8
0x18000a5ec  mov     rbp, rcx
0x18000a5ef  mov     r8, rdx
0x18000a5f2  test    bl, 3
0x18000a5f5  jnz     loc_18000A77B
0x18000a5fb  lea     rax, [rsp+278h+Name]
0x18000a600  shr     rbx, 2
0x18000a604  sub     r8, rax
0x18000a607  lea     rcx, [rsp+278h+Name]
0x18000a60c  xor     r14d, r14d
0x18000a60f  mov     r15d, 104h
0x18000a615  mov     edx, r15d
0x18000a618  lea     edi, [r14+1]
0x18000a61c  lea     rax, [rdx+7FFFFEFAh]
0x18000a623  test    rax, rax
0x18000a626  jz      short loc_18000A63E
0x18000a628  movzx   eax, word ptr [r8+rcx]
0x18000a62d  test    ax, ax
0x18000a630  jz      short loc_18000A63E
0x18000a632  mov     [rcx], ax
0x18000a635  add     rcx, 2
0x18000a639  sub     rdx, rdi
0x18000a63c  jnz     short loc_18000A61C
0x18000a63e  test    rdx, rdx
0x18000a641  lea     rax, [rcx-2]
0x18000a645  lea     r8, aP0; "_p0"
0x18000a64c  mov     rdx, r15; unsigned __int64
0x18000a64f  cmovnz  rax, rcx
0x18000a653  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a658  mov     [rax], r14w
0x18000a65c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a661  mov     rsi, rbx
0x18000a664  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a66c  mov     r8d, edi
0x18000a66f  shr     rsi, 1Fh
0x18000a673  and     ebx, 7FFFFFFFh
0x18000a679  mov     [rsp+278h+dwFlags], r14d; int
0x18000a67e  lea     r9, [rsp+278h+Name]; lpName
0x18000a683  mov     edx, ebx; lInitialCount
0x18000a685  cmova   r8d, ebx; lMaximumCount
0x18000a689  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a68b  call    cs:__imp_CreateSemaphoreExW
0x18000a692  nop     dword ptr [rax+rax+00h]
0x18000a697  mov     rbx, rax
0x18000a69a  test    rax, rax
0x18000a69d  jnz     short loc_18000A6C4
0x18000a69f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a6a4  mov     ebx, eax
0x18000a6a6  test    eax, eax
0x18000a6a8  jns     short loc_18000A6DB
0x18000a6aa  mov     edx, 88h; void *
0x18000a6af  mov     rcx, [rsp+278h]; this
0x18000a6b7  mov     r9d, eax; char *
0x18000a6ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6bf  jmp     loc_18000A751
0x18000a6c4  call    cs:__imp_GetLastError
0x18000a6cb  nop     dword ptr [rax+rax+00h]
0x18000a6d0  mov     rdx, rbx
0x18000a6d3  mov     rcx, rbp
0x18000a6d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a6db  lea     r8, asc_180035DC8; "h"
0x18000a6e2  mov     rdx, r15; unsigned __int64
0x18000a6e5  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000a6ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a6ef  test    esi, esi
0x18000a6f1  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000a6f9  lea     r9, [rsp+278h+Name]; lpName
0x18000a6fe  mov     [rsp+278h+dwFlags], r14d; dwFlags
0x18000a703  cmovnz  edi, esi
0x18000a706  mov     edx, esi; lInitialCount
0x18000a708  mov     r8d, edi; lMaximumCount
0x18000a70b  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a70d  call    cs:__imp_CreateSemaphoreExW
0x18000a714  nop     dword ptr [rax+rax+00h]
0x18000a719  mov     rbx, rax
0x18000a71c  test    rax, rax
0x18000a71f  jnz     short loc_18000A736
0x18000a721  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a726  mov     ebx, eax
0x18000a728  test    eax, eax
0x18000a72a  jns     short loc_18000A74E
0x18000a72c  mov     edx, 8Dh
0x18000a731  jmp     loc_18000A6AF
0x18000a736  call    cs:__imp_GetLastError
0x18000a73d  nop     dword ptr [rax+rax+00h]
0x18000a742  mov     rdx, rbx
0x18000a745  lea     rcx, [rbp+8]
0x18000a749  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a74e  mov     ebx, r14d
0x18000a751  mov     eax, ebx
0x18000a753  mov     rcx, [rsp+278h+var_38]
0x18000a75b  xor     rcx, rsp; StackCookie
0x18000a75e  call    __security_check_cookie
0x18000a763  mov     rbx, [rsp+278h+arg_8]
0x18000a76b  add     rsp, 250h
0x18000a772  pop     r15
0x18000a774  pop     r14
0x18000a776  pop     rdi
0x18000a777  pop     rsi
0x18000a778  pop     rbp
0x18000a779  retn
0x18000a77b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
