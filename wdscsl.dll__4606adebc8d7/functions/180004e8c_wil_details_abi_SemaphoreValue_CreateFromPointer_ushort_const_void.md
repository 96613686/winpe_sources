# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180004e8c`
- end: `0x180005042`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003b34`
- `0x180003f2c`

## callees

- `0x180004e8c`
- `0x180006608`
- `0x180009a04`
- `0x18000ab24`
- `0x18000b818`
- `0x18000bae8`
- `0x18000d700`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180004f4e`
- `KERNEL32!CreateSemaphoreExW` at `0x180004fcd`
- `KERNEL32!CreateSemaphoreExW` at `0x180004f4e`
- `KERNEL32!CreateSemaphoreExW` at `0x180004fcd`
- `KERNEL32!GetLastError` at `0x180004f87`
- `KERNEL32!GetLastError` at `0x180004ff6`
- `KERNEL32!GetLastError` at `0x180004f87`
- `KERNEL32!GetLastError` at `0x180004ff6`

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
0x180004e8c  mov     [rsp+arg_8], rbx
0x180004e91  mov     [rsp+arg_18], rbp
0x180004e96  push    rsi
0x180004e97  push    rdi
0x180004e98  push    r14
0x180004e9a  sub     rsp, 250h
0x180004ea1  mov     rax, cs:__security_cookie
0x180004ea8  xor     rax, rsp
0x180004eab  mov     [rsp+268h+var_28], rax
0x180004eb3  mov     rbx, r8
0x180004eb6  mov     rbp, rcx
0x180004eb9  mov     r8, rdx
0x180004ebc  test    bl, 3
0x180004ebf  jnz     loc_18000503C
0x180004ec5  lea     rax, [rsp+268h+Name]
0x180004eca  shr     rbx, 2
0x180004ece  sub     r8, rax
0x180004ed1  lea     rcx, [rsp+268h+Name]
0x180004ed6  xor     r14d, r14d
0x180004ed9  mov     edx, 104h
0x180004ede  lea     edi, [r14+1]
0x180004ee2  lea     rax, [rdx+7FFFFEFAh]
0x180004ee9  test    rax, rax
0x180004eec  jz      short loc_180004F04
0x180004eee  movzx   eax, word ptr [r8+rcx]
0x180004ef3  test    ax, ax
0x180004ef6  jz      short loc_180004F04
0x180004ef8  mov     [rcx], ax
0x180004efb  add     rcx, 2
0x180004eff  sub     rdx, rdi; unsigned __int64
0x180004f02  jnz     short loc_180004EE2
0x180004f04  lea     rax, [rcx-2]
0x180004f08  test    rdx, rdx
0x180004f0b  lea     r8, aP0; "_p0"
0x180004f12  cmovnz  rax, rcx
0x180004f16  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180004f1b  mov     [rax], r14w
0x180004f1f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004f24  mov     rsi, rbx
0x180004f27  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004f2f  mov     r8d, edi
0x180004f32  shr     rsi, 1Fh
0x180004f36  and     ebx, 7FFFFFFFh
0x180004f3c  mov     [rsp+268h+dwFlags], r14d; int
0x180004f41  lea     r9, [rsp+268h+Name]; lpName
0x180004f46  mov     edx, ebx; lInitialCount
0x180004f48  cmova   r8d, ebx; lMaximumCount
0x180004f4c  xor     ecx, ecx; lpSemaphoreAttributes
0x180004f4e  call    cs:__imp_CreateSemaphoreExW
0x180004f55  nop     dword ptr [rax+rax+00h]
0x180004f5a  mov     rbx, rax
0x180004f5d  test    rax, rax
0x180004f60  jnz     short loc_180004F87
0x180004f62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004f67  mov     ebx, eax
0x180004f69  test    eax, eax
0x180004f6b  jns     short loc_180004F9E
0x180004f6d  mov     edx, 88h; void *
0x180004f72  mov     rcx, [rsp+268h]; this
0x180004f7a  mov     r9d, eax; char *
0x180004f7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f82  jmp     loc_180005011
0x180004f87  call    cs:__imp_GetLastError
0x180004f8e  nop     dword ptr [rax+rax+00h]
0x180004f93  mov     rdx, rbx
0x180004f96  mov     rcx, rbp
0x180004f99  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004f9e  lea     r8, asc_180011420; "h"
0x180004fa5  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180004faa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004faf  test    esi, esi
0x180004fb1  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004fb9  lea     r9, [rsp+268h+Name]; lpName
0x180004fbe  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x180004fc3  cmovnz  edi, esi
0x180004fc6  mov     edx, esi; lInitialCount
0x180004fc8  mov     r8d, edi; lMaximumCount
0x180004fcb  xor     ecx, ecx; lpSemaphoreAttributes
0x180004fcd  call    cs:__imp_CreateSemaphoreExW
0x180004fd4  nop     dword ptr [rax+rax+00h]
0x180004fd9  mov     rbx, rax
0x180004fdc  test    rax, rax
0x180004fdf  jnz     short loc_180004FF6
0x180004fe1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004fe6  mov     ebx, eax
0x180004fe8  test    eax, eax
0x180004fea  jns     short loc_18000500E
0x180004fec  mov     edx, 8Dh
0x180004ff1  jmp     loc_180004F72
0x180004ff6  call    cs:__imp_GetLastError
0x180004ffd  nop     dword ptr [rax+rax+00h]
0x180005002  mov     rdx, rbx
0x180005005  lea     rcx, [rbp+8]
0x180005009  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000500e  mov     ebx, r14d
0x180005011  mov     eax, ebx
0x180005013  mov     rcx, [rsp+268h+var_28]
0x18000501b  xor     rcx, rsp; StackCookie
0x18000501e  call    __security_check_cookie
0x180005023  lea     r11, [rsp+268h+var_18]
0x18000502b  mov     rbx, [r11+28h]
0x18000502f  mov     rbp, [r11+38h]
0x180005033  mov     rsp, r11
0x180005036  pop     r14
0x180005038  pop     rdi
0x180005039  pop     rsi
0x18000503a  retn
0x18000503c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
