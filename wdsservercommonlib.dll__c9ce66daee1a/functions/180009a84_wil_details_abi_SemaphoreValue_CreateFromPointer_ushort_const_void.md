# wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)

- ea: `0x180009a84`
- end: `0x180009c41`
- name: `?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z`
- size: `445`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009110`
- `0x180009508`

## callees

- `0x180009a84`
- `0x18000a688`
- `0x18000c788`
- `0x18000cd48`
- `0x18000da68`
- `0x18000dd20`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009b84`
- `KERNEL32!GetLastError` at `0x180009bf6`
- `KERNEL32!GetLastError` at `0x180009b84`
- `KERNEL32!GetLastError` at `0x180009bf6`
- `KERNEL32!CreateSemaphoreExW` at `0x180009b4b`
- `KERNEL32!CreateSemaphoreExW` at `0x180009bcd`
- `KERNEL32!CreateSemaphoreExW` at `0x180009b4b`
- `KERNEL32!CreateSemaphoreExW` at `0x180009bcd`

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
0x180009a84  mov     [rsp+arg_8], rbx
0x180009a89  push    rbp
0x180009a8a  push    rsi
0x180009a8b  push    rdi
0x180009a8c  push    r14
0x180009a8e  push    r15
0x180009a90  sub     rsp, 250h
0x180009a97  mov     rax, cs:__security_cookie
0x180009a9e  xor     rax, rsp
0x180009aa1  mov     [rsp+278h+var_38], rax
0x180009aa9  mov     rbx, r8
0x180009aac  mov     rbp, rcx
0x180009aaf  mov     r8, rdx
0x180009ab2  test    bl, 3
0x180009ab5  jnz     loc_180009C3B
0x180009abb  lea     rax, [rsp+278h+Name]
0x180009ac0  shr     rbx, 2
0x180009ac4  sub     r8, rax
0x180009ac7  lea     rcx, [rsp+278h+Name]
0x180009acc  xor     r14d, r14d
0x180009acf  mov     r15d, 104h
0x180009ad5  mov     edx, r15d
0x180009ad8  lea     edi, [r14+1]
0x180009adc  lea     rax, [rdx+7FFFFEFAh]
0x180009ae3  test    rax, rax
0x180009ae6  jz      short loc_180009AFE
0x180009ae8  movzx   eax, word ptr [r8+rcx]
0x180009aed  test    ax, ax
0x180009af0  jz      short loc_180009AFE
0x180009af2  mov     [rcx], ax
0x180009af5  add     rcx, 2
0x180009af9  sub     rdx, rdi
0x180009afc  jnz     short loc_180009ADC
0x180009afe  test    rdx, rdx
0x180009b01  lea     rax, [rcx-2]
0x180009b05  lea     r8, aP0; "_p0"
0x180009b0c  mov     rdx, r15; unsigned __int64
0x180009b0f  cmovnz  rax, rcx
0x180009b13  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180009b18  mov     [rax], r14w
0x180009b1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009b21  mov     rsi, rbx
0x180009b24  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009b2c  mov     r8d, edi
0x180009b2f  shr     rsi, 1Fh
0x180009b33  and     ebx, 7FFFFFFFh
0x180009b39  mov     [rsp+278h+dwFlags], r14d; int
0x180009b3e  lea     r9, [rsp+278h+Name]; lpName
0x180009b43  mov     edx, ebx; lInitialCount
0x180009b45  cmova   r8d, ebx; lMaximumCount
0x180009b49  xor     ecx, ecx; lpSemaphoreAttributes
0x180009b4b  call    cs:__imp_CreateSemaphoreExW
0x180009b52  nop     dword ptr [rax+rax+00h]
0x180009b57  mov     rbx, rax
0x180009b5a  test    rax, rax
0x180009b5d  jnz     short loc_180009B84
0x180009b5f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009b64  mov     ebx, eax
0x180009b66  test    eax, eax
0x180009b68  jns     short loc_180009B9B
0x180009b6a  mov     edx, 88h; void *
0x180009b6f  mov     rcx, [rsp+278h]; this
0x180009b77  mov     r9d, eax; char *
0x180009b7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b7f  jmp     loc_180009C11
0x180009b84  call    cs:__imp_GetLastError
0x180009b8b  nop     dword ptr [rax+rax+00h]
0x180009b90  mov     rdx, rbx
0x180009b93  mov     rcx, rbp
0x180009b96  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009b9b  lea     r8, asc_180033858; "h"
0x180009ba2  mov     rdx, r15; unsigned __int64
0x180009ba5  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180009baa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009baf  test    esi, esi
0x180009bb1  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009bb9  lea     r9, [rsp+278h+Name]; lpName
0x180009bbe  mov     [rsp+278h+dwFlags], r14d; dwFlags
0x180009bc3  cmovnz  edi, esi
0x180009bc6  mov     edx, esi; lInitialCount
0x180009bc8  mov     r8d, edi; lMaximumCount
0x180009bcb  xor     ecx, ecx; lpSemaphoreAttributes
0x180009bcd  call    cs:__imp_CreateSemaphoreExW
0x180009bd4  nop     dword ptr [rax+rax+00h]
0x180009bd9  mov     rbx, rax
0x180009bdc  test    rax, rax
0x180009bdf  jnz     short loc_180009BF6
0x180009be1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009be6  mov     ebx, eax
0x180009be8  test    eax, eax
0x180009bea  jns     short loc_180009C0E
0x180009bec  mov     edx, 8Dh
0x180009bf1  jmp     loc_180009B6F
0x180009bf6  call    cs:__imp_GetLastError
0x180009bfd  nop     dword ptr [rax+rax+00h]
0x180009c02  mov     rdx, rbx
0x180009c05  lea     rcx, [rbp+8]
0x180009c09  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009c0e  mov     ebx, r14d
0x180009c11  mov     eax, ebx
0x180009c13  mov     rcx, [rsp+278h+var_38]
0x180009c1b  xor     rcx, rsp; StackCookie
0x180009c1e  call    __security_check_cookie
0x180009c23  mov     rbx, [rsp+278h+arg_8]
0x180009c2b  add     rsp, 250h
0x180009c32  pop     r15
0x180009c34  pop     r14
0x180009c36  pop     rdi
0x180009c37  pop     rsi
0x180009c38  pop     rbp
0x180009c39  retn
0x180009c3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
