# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003ad0`
- end: `0x140003cdd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400036fc`
- `0x140009214`

## callees

- `0x140001ee0`
- `0x140003ad0`
- `0x140004698`
- `0x140005b54`
- `0x140005e68`
- `0x14000635c`
- `0x14000636c`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140003b94`
- `KERNEL32!CreateSemaphoreExW` at `0x140003c30`
- `KERNEL32!CreateSemaphoreExW` at `0x140003b94`
- `KERNEL32!CreateSemaphoreExW` at `0x140003c30`
- `KERNEL32!SetLastError` at `0x140003bf4`
- `KERNEL32!SetLastError` at `0x140003c79`
- `KERNEL32!SetLastError` at `0x140003bf4`
- `KERNEL32!SetLastError` at `0x140003c79`
- `KERNEL32!GetLastError` at `0x140003bc9`
- `KERNEL32!GetLastError` at `0x140003bd7`
- `KERNEL32!GetLastError` at `0x140003c53`
- `KERNEL32!GetLastError` at `0x140003c62`
- `KERNEL32!GetLastError` at `0x140003bc9`
- `KERNEL32!GetLastError` at `0x140003bd7`
- `KERNEL32!GetLastError` at `0x140003c53`
- `KERNEL32!GetLastError` at `0x140003c62`
- `KERNEL32!CloseHandle` at `0x140003be3`
- `KERNEL32!CloseHandle` at `0x140003c6d`
- `KERNEL32!CloseHandle` at `0x140003be3`
- `KERNEL32!CloseHandle` at `0x140003c6d`

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
  unsigned __int64 v9; // rdx
  LONG v10; // esi
  WCHAR *v11; // rcx
  LONG v12; // r8d
  wil::details *v13; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v15; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  void *v20; // rbx
  DWORD LastError; // r14d
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  unsigned int v29; // r8d
  const char *v30; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-258h]
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
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
  v11 = v7 - 1;
  if ( v9 )
    v11 = v7;
  *v11 = 0;
  StringCchCatW(Name, v9, L"_p0");
  v12 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v12 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v12, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v20 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v20) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v18, v17, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v24 = a4 >> 31;
  StringCchCatW(Name, v15, L"h");
  if ( (_DWORD)v24 )
    v10 = v24;
  v26 = CreateSemaphoreExW(0, v24, v10, Name, 0, 0x1F0003u);
  if ( v26 )
  {
    GetLastError();
    v27 = (void *)*((_QWORD *)this + 1);
    if ( v27 )
    {
      v28 = GetLastError();
      if ( !CloseHandle(v27) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      SetLastError(v28);
    }
    *((_QWORD *)this + 1) = v26;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v25);
    if ( LastErrorFailHr < 0 )
    {
      v18 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003ad0  mov     [rsp+arg_8], rbx
0x140003ad5  mov     [rsp+arg_10], rbp
0x140003ada  push    rsi
0x140003adb  push    rdi
0x140003adc  push    r12
0x140003ade  push    r14
0x140003ae0  push    r15
0x140003ae2  sub     rsp, 250h
0x140003ae9  mov     rax, cs:__security_cookie
0x140003af0  xor     rax, rsp
0x140003af3  mov     [rsp+278h+var_38], rax
0x140003afb  mov     rax, 0C000000000000000h
0x140003b05  mov     rbp, r9
0x140003b08  mov     r8, rdx
0x140003b0b  mov     rdi, rcx
0x140003b0e  test    rax, r9
0x140003b11  jnz     loc_140003CC4
0x140003b17  xor     r12d, r12d
0x140003b1a  lea     rax, [rsp+278h+Name]
0x140003b1f  mov     ecx, 7FFFFFFEh
0x140003b24  mov     edx, 104h
0x140003b29  lea     esi, [r12+1]
0x140003b2e  test    rcx, rcx
0x140003b31  jz      short loc_140003B51
0x140003b33  movzx   r9d, word ptr [r8]
0x140003b37  test    r9w, r9w
0x140003b3b  jz      short loc_140003B51
0x140003b3d  mov     [rax], r9w
0x140003b41  add     r8, 2
0x140003b45  add     rax, 2
0x140003b49  sub     rcx, rsi
0x140003b4c  sub     rdx, rsi; unsigned __int64
0x140003b4f  jnz     short loc_140003B2E
0x140003b51  test    rdx, rdx
0x140003b54  lea     rcx, [rax-2]
0x140003b58  lea     r8, aP0; "_p0"
0x140003b5f  cmovnz  rcx, rax
0x140003b63  mov     [rcx], r12w
0x140003b67  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003b6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003b71  mov     edx, ebp
0x140003b73  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003b7b  and     edx, 7FFFFFFFh; lInitialCount
0x140003b81  mov     [rsp+278h+dwFlags], r12d; int
0x140003b86  mov     r8d, esi
0x140003b89  lea     r9, [rsp+278h+Name]; lpName
0x140003b8e  cmova   r8d, edx; lMaximumCount
0x140003b92  xor     ecx, ecx; lpSemaphoreAttributes
0x140003b94  call    cs:__imp_CreateSemaphoreExW
0x140003b9a  mov     r15, rax
0x140003b9d  test    rax, rax
0x140003ba0  jnz     short loc_140003BC9
0x140003ba2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003ba7  mov     ebx, eax
0x140003ba9  test    eax, eax
0x140003bab  jns     short loc_140003BFD
0x140003bad  mov     edx, 8Bh; void *
0x140003bb2  mov     rcx, [rsp+278h]; this
0x140003bba  mov     r9d, ebx; char *
0x140003bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003bc2  mov     eax, ebx
0x140003bc4  jmp     loc_140003C85
0x140003bc9  call    cs:__imp_GetLastError
0x140003bcf  mov     rbx, [rdi]
0x140003bd2  test    rbx, rbx
0x140003bd5  jz      short loc_140003BFA
0x140003bd7  call    cs:__imp_GetLastError
0x140003bdd  mov     rcx, rbx; hObject
0x140003be0  mov     r14d, eax
0x140003be3  call    cs:__imp_CloseHandle
0x140003be9  test    eax, eax
0x140003beb  jz      loc_140003CCA
0x140003bf1  mov     ecx, r14d; dwErrCode
0x140003bf4  call    cs:__imp_SetLastError
0x140003bfa  mov     [rdi], r15
0x140003bfd  lea     r8, asc_140019528; "h"
0x140003c04  shr     rbp, 1Fh
0x140003c08  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140003c0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003c12  test    ebp, ebp
0x140003c14  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140003c1c  lea     r9, [rsp+278h+Name]; lpName
0x140003c21  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140003c26  cmovnz  esi, ebp
0x140003c29  mov     edx, ebp; lInitialCount
0x140003c2b  mov     r8d, esi; lMaximumCount
0x140003c2e  xor     ecx, ecx; lpSemaphoreAttributes
0x140003c30  call    cs:__imp_CreateSemaphoreExW
0x140003c36  mov     rsi, rax
0x140003c39  test    rax, rax
0x140003c3c  jnz     short loc_140003C53
0x140003c3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003c43  mov     ebx, eax
0x140003c45  test    eax, eax
0x140003c47  jns     short loc_140003C83
0x140003c49  mov     edx, 90h
0x140003c4e  jmp     loc_140003BB2
0x140003c53  call    cs:__imp_GetLastError
0x140003c59  mov     rbx, [rdi+8]
0x140003c5d  test    rbx, rbx
0x140003c60  jz      short loc_140003C7F
0x140003c62  call    cs:__imp_GetLastError
0x140003c68  mov     rcx, rbx; hObject
0x140003c6b  mov     ebp, eax
0x140003c6d  call    cs:__imp_CloseHandle
0x140003c73  test    eax, eax
0x140003c75  jz      short loc_140003CB1
0x140003c77  mov     ecx, ebp; dwErrCode
0x140003c79  call    cs:__imp_SetLastError
0x140003c7f  mov     [rdi+8], rsi
0x140003c83  xor     eax, eax
0x140003c85  mov     rcx, [rsp+278h+var_38]
0x140003c8d  xor     rcx, rsp; StackCookie
0x140003c90  call    __security_check_cookie
0x140003c95  lea     r11, [rsp+278h+var_28]
0x140003c9d  mov     rbx, [r11+38h]
0x140003ca1  mov     rbp, [r11+40h]
0x140003ca5  mov     rsp, r11
0x140003ca8  pop     r15
0x140003caa  pop     r14
0x140003cac  pop     r12
0x140003cae  pop     rdi
0x140003caf  pop     rsi
0x140003cb0  retn
0x140003cb1  mov     rcx, [rsp+278h]; this
0x140003cb9  mov     edx, 0A0Bh; void *
0x140003cbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003cc4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003cca  mov     rcx, [rsp+278h]; this
0x140003cd2  mov     edx, 0A0Bh; void *
0x140003cd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
