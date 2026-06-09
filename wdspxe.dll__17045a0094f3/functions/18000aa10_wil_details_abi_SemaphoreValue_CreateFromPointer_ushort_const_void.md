# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x18000aa10`
- end: `0x18000abc6`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000a204`
- `0x18000a5fc`

## callees

- `0x18000aa10`
- `0x18000bc24`
- `0x18000ea18`
- `0x18000fc3c`
- `0x180010a38`
- `0x180010d18`
- `0x180011a90`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x18000aad2`
- `KERNEL32!CreateSemaphoreExW` at `0x18000ab51`
- `KERNEL32!CreateSemaphoreExW` at `0x18000aad2`
- `KERNEL32!CreateSemaphoreExW` at `0x18000ab51`
- `KERNEL32!GetLastError` at `0x18000ab0b`
- `KERNEL32!GetLastError` at `0x18000ab7a`
- `KERNEL32!GetLastError` at `0x18000ab0b`
- `KERNEL32!GetLastError` at `0x18000ab7a`

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
0x18000aa10  mov     [rsp+arg_8], rbx
0x18000aa15  mov     [rsp+arg_18], rbp
0x18000aa1a  push    rsi
0x18000aa1b  push    rdi
0x18000aa1c  push    r14
0x18000aa1e  sub     rsp, 250h
0x18000aa25  mov     rax, cs:__security_cookie
0x18000aa2c  xor     rax, rsp
0x18000aa2f  mov     [rsp+268h+var_28], rax
0x18000aa37  mov     rbx, r8
0x18000aa3a  mov     rbp, rcx
0x18000aa3d  mov     r8, rdx
0x18000aa40  test    bl, 3
0x18000aa43  jnz     loc_18000ABC0
0x18000aa49  lea     rax, [rsp+268h+Name]
0x18000aa4e  shr     rbx, 2
0x18000aa52  sub     r8, rax
0x18000aa55  lea     rcx, [rsp+268h+Name]
0x18000aa5a  xor     r14d, r14d
0x18000aa5d  mov     edx, 104h
0x18000aa62  lea     edi, [r14+1]
0x18000aa66  lea     rax, [rdx+7FFFFEFAh]
0x18000aa6d  test    rax, rax
0x18000aa70  jz      short loc_18000AA88
0x18000aa72  movzx   eax, word ptr [r8+rcx]
0x18000aa77  test    ax, ax
0x18000aa7a  jz      short loc_18000AA88
0x18000aa7c  mov     [rcx], ax
0x18000aa7f  add     rcx, 2
0x18000aa83  sub     rdx, rdi; unsigned __int64
0x18000aa86  jnz     short loc_18000AA66
0x18000aa88  lea     rax, [rcx-2]
0x18000aa8c  test    rdx, rdx
0x18000aa8f  lea     r8, aP0; "_p0"
0x18000aa96  cmovnz  rax, rcx
0x18000aa9a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000aa9f  mov     [rax], r14w
0x18000aaa3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aaa8  mov     rsi, rbx
0x18000aaab  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000aab3  mov     r8d, edi
0x18000aab6  shr     rsi, 1Fh
0x18000aaba  and     ebx, 7FFFFFFFh
0x18000aac0  mov     [rsp+268h+dwFlags], r14d; int
0x18000aac5  lea     r9, [rsp+268h+Name]; lpName
0x18000aaca  mov     edx, ebx; lInitialCount
0x18000aacc  cmova   r8d, ebx; lMaximumCount
0x18000aad0  xor     ecx, ecx; lpSemaphoreAttributes
0x18000aad2  call    cs:__imp_CreateSemaphoreExW
0x18000aad9  nop     dword ptr [rax+rax+00h]
0x18000aade  mov     rbx, rax
0x18000aae1  test    rax, rax
0x18000aae4  jnz     short loc_18000AB0B
0x18000aae6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aaeb  mov     ebx, eax
0x18000aaed  test    eax, eax
0x18000aaef  jns     short loc_18000AB22
0x18000aaf1  mov     edx, 88h; void *
0x18000aaf6  mov     rcx, [rsp+268h]; this
0x18000aafe  mov     r9d, eax; char *
0x18000ab01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab06  jmp     loc_18000AB95
0x18000ab0b  call    cs:__imp_GetLastError
0x18000ab12  nop     dword ptr [rax+rax+00h]
0x18000ab17  mov     rdx, rbx
0x18000ab1a  mov     rcx, rbp
0x18000ab1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ab22  lea     r8, asc_180017258; "h"
0x18000ab29  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18000ab2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ab33  test    esi, esi
0x18000ab35  mov     [rsp+268h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000ab3d  lea     r9, [rsp+268h+Name]; lpName
0x18000ab42  mov     [rsp+268h+dwFlags], r14d; dwFlags
0x18000ab47  cmovnz  edi, esi
0x18000ab4a  mov     edx, esi; lInitialCount
0x18000ab4c  mov     r8d, edi; lMaximumCount
0x18000ab4f  xor     ecx, ecx; lpSemaphoreAttributes
0x18000ab51  call    cs:__imp_CreateSemaphoreExW
0x18000ab58  nop     dword ptr [rax+rax+00h]
0x18000ab5d  mov     rbx, rax
0x18000ab60  test    rax, rax
0x18000ab63  jnz     short loc_18000AB7A
0x18000ab65  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ab6a  mov     ebx, eax
0x18000ab6c  test    eax, eax
0x18000ab6e  jns     short loc_18000AB92
0x18000ab70  mov     edx, 8Dh
0x18000ab75  jmp     loc_18000AAF6
0x18000ab7a  call    cs:__imp_GetLastError
0x18000ab81  nop     dword ptr [rax+rax+00h]
0x18000ab86  mov     rdx, rbx
0x18000ab89  lea     rcx, [rbp+8]
0x18000ab8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ab92  mov     ebx, r14d
0x18000ab95  mov     eax, ebx
0x18000ab97  mov     rcx, [rsp+268h+var_28]
0x18000ab9f  xor     rcx, rsp; StackCookie
0x18000aba2  call    __security_check_cookie
0x18000aba7  lea     r11, [rsp+268h+var_18]
0x18000abaf  mov     rbx, [r11+28h]
0x18000abb3  mov     rbp, [r11+38h]
0x18000abb7  mov     rsp, r11
0x18000abba  pop     r14
0x18000abbc  pop     rdi
0x18000abbd  pop     rsi
0x18000abbe  retn
0x18000abc0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
