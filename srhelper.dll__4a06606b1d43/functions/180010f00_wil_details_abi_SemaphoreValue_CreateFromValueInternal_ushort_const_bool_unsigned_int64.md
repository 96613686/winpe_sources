# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180010f00`
- end: `0x18001110d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001078c`
- `0x180010b30`

## callees

- `0x18000e280`
- `0x180010f00`
- `0x180011c88`
- `0x180013b10`
- `0x18001498c`
- `0x18001499c`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010ff9`
- `KERNEL32!GetLastError` at `0x180011007`
- `KERNEL32!GetLastError` at `0x180011083`
- `KERNEL32!GetLastError` at `0x180011092`
- `KERNEL32!GetLastError` at `0x180010ff9`
- `KERNEL32!GetLastError` at `0x180011007`
- `KERNEL32!GetLastError` at `0x180011083`
- `KERNEL32!GetLastError` at `0x180011092`
- `KERNEL32!CloseHandle` at `0x180011013`
- `KERNEL32!CloseHandle` at `0x18001109d`
- `KERNEL32!CloseHandle` at `0x180011013`
- `KERNEL32!CloseHandle` at `0x18001109d`
- `KERNEL32!SetLastError` at `0x180011024`
- `KERNEL32!SetLastError` at `0x1800110a9`
- `KERNEL32!SetLastError` at `0x180011024`
- `KERNEL32!SetLastError` at `0x1800110a9`
- `KERNEL32!CreateSemaphoreExW` at `0x180010fc4`
- `KERNEL32!CreateSemaphoreExW` at `0x180011060`
- `KERNEL32!CreateSemaphoreExW` at `0x180010fc4`
- `KERNEL32!CreateSemaphoreExW` at `0x180011060`

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
  __int64 v22; // r8
  const char *v23; // r9
  unsigned __int64 v24; // rbp
  wil::details *v25; // rcx
  HANDLE v26; // rsi
  void *v27; // rbx
  DWORD v28; // ebp
  __int64 v29; // r8
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
0x180010f00  mov     [rsp+arg_8], rbx
0x180010f05  mov     [rsp+arg_10], rbp
0x180010f0a  push    rsi
0x180010f0b  push    rdi
0x180010f0c  push    r12
0x180010f0e  push    r14
0x180010f10  push    r15
0x180010f12  sub     rsp, 250h
0x180010f19  mov     rax, cs:__security_cookie
0x180010f20  xor     rax, rsp
0x180010f23  mov     [rsp+278h+var_38], rax
0x180010f2b  mov     rax, 0C000000000000000h
0x180010f35  mov     rbp, r9
0x180010f38  mov     r8, rdx
0x180010f3b  mov     rdi, rcx
0x180010f3e  test    rax, r9
0x180010f41  jnz     loc_1800110F4
0x180010f47  xor     r12d, r12d
0x180010f4a  lea     rax, [rsp+278h+Name]
0x180010f4f  mov     ecx, 7FFFFFFEh
0x180010f54  mov     edx, 104h
0x180010f59  lea     esi, [r12+1]
0x180010f5e  test    rcx, rcx
0x180010f61  jz      short loc_180010F81
0x180010f63  movzx   r9d, word ptr [r8]
0x180010f67  test    r9w, r9w
0x180010f6b  jz      short loc_180010F81
0x180010f6d  mov     [rax], r9w
0x180010f71  add     r8, 2
0x180010f75  add     rax, 2
0x180010f79  sub     rcx, rsi
0x180010f7c  sub     rdx, rsi; unsigned __int64
0x180010f7f  jnz     short loc_180010F5E
0x180010f81  test    rdx, rdx
0x180010f84  lea     rcx, [rax-2]
0x180010f88  lea     r8, aP0; "_p0"
0x180010f8f  cmovnz  rcx, rax
0x180010f93  mov     [rcx], r12w
0x180010f97  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180010f9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010fa1  mov     edx, ebp
0x180010fa3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180010fab  and     edx, 7FFFFFFFh; lInitialCount
0x180010fb1  mov     [rsp+278h+dwFlags], r12d; int
0x180010fb6  mov     r8d, esi
0x180010fb9  lea     r9, [rsp+278h+Name]; lpName
0x180010fbe  cmova   r8d, edx; lMaximumCount
0x180010fc2  xor     ecx, ecx; lpSemaphoreAttributes
0x180010fc4  call    cs:__imp_CreateSemaphoreExW
0x180010fca  mov     r15, rax
0x180010fcd  test    rax, rax
0x180010fd0  jnz     short loc_180010FF9
0x180010fd2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010fd7  mov     ebx, eax
0x180010fd9  test    eax, eax
0x180010fdb  jns     short loc_18001102D
0x180010fdd  mov     edx, 8Bh; void *
0x180010fe2  mov     rcx, [rsp+278h]; this
0x180010fea  mov     r9d, ebx; char *
0x180010fed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ff2  mov     eax, ebx
0x180010ff4  jmp     loc_1800110B5
0x180010ff9  call    cs:__imp_GetLastError
0x180010fff  mov     rbx, [rdi]
0x180011002  test    rbx, rbx
0x180011005  jz      short loc_18001102A
0x180011007  call    cs:__imp_GetLastError
0x18001100d  mov     rcx, rbx; hObject
0x180011010  mov     r14d, eax
0x180011013  call    cs:__imp_CloseHandle
0x180011019  test    eax, eax
0x18001101b  jz      loc_1800110FA
0x180011021  mov     ecx, r14d; dwErrCode
0x180011024  call    cs:__imp_SetLastError
0x18001102a  mov     [rdi], r15
0x18001102d  lea     r8, asc_18001A518; "h"
0x180011034  shr     rbp, 1Fh
0x180011038  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18001103d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011042  test    ebp, ebp
0x180011044  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001104c  lea     r9, [rsp+278h+Name]; lpName
0x180011051  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180011056  cmovnz  esi, ebp
0x180011059  mov     edx, ebp; lInitialCount
0x18001105b  mov     r8d, esi; lMaximumCount
0x18001105e  xor     ecx, ecx; lpSemaphoreAttributes
0x180011060  call    cs:__imp_CreateSemaphoreExW
0x180011066  mov     rsi, rax
0x180011069  test    rax, rax
0x18001106c  jnz     short loc_180011083
0x18001106e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011073  mov     ebx, eax
0x180011075  test    eax, eax
0x180011077  jns     short loc_1800110B3
0x180011079  mov     edx, 90h
0x18001107e  jmp     loc_180010FE2
0x180011083  call    cs:__imp_GetLastError
0x180011089  mov     rbx, [rdi+8]
0x18001108d  test    rbx, rbx
0x180011090  jz      short loc_1800110AF
0x180011092  call    cs:__imp_GetLastError
0x180011098  mov     rcx, rbx; hObject
0x18001109b  mov     ebp, eax
0x18001109d  call    cs:__imp_CloseHandle
0x1800110a3  test    eax, eax
0x1800110a5  jz      short loc_1800110E1
0x1800110a7  mov     ecx, ebp; dwErrCode
0x1800110a9  call    cs:__imp_SetLastError
0x1800110af  mov     [rdi+8], rsi
0x1800110b3  xor     eax, eax
0x1800110b5  mov     rcx, [rsp+278h+var_38]
0x1800110bd  xor     rcx, rsp; StackCookie
0x1800110c0  call    __security_check_cookie
0x1800110c5  lea     r11, [rsp+278h+var_28]
0x1800110cd  mov     rbx, [r11+38h]
0x1800110d1  mov     rbp, [r11+40h]
0x1800110d5  mov     rsp, r11
0x1800110d8  pop     r15
0x1800110da  pop     r14
0x1800110dc  pop     r12
0x1800110de  pop     rdi
0x1800110df  pop     rsi
0x1800110e0  retn
0x1800110e1  mov     rcx, [rsp+278h]; this
0x1800110e9  mov     edx, 0A0Bh; void *
0x1800110ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800110f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800110fa  mov     rcx, [rsp+278h]; this
0x180011102  mov     edx, 0A0Bh; void *
0x180011107  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
