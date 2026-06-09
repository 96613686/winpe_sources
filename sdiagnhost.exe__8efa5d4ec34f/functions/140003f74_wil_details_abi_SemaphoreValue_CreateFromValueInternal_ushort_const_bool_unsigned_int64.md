# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003f74`
- end: `0x140004181`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003bd0`

## callees

- `0x140003f74`
- `0x140004760`
- `0x14000553c`
- `0x140006810`
- `0x140006e2c`
- `0x140006e3c`
- `0x140007770`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140004087`
- `KERNEL32!CloseHandle` at `0x140004111`
- `KERNEL32!CloseHandle` at `0x140004087`
- `KERNEL32!CloseHandle` at `0x140004111`
- `KERNEL32!SetLastError` at `0x140004098`
- `KERNEL32!SetLastError` at `0x14000411d`
- `KERNEL32!SetLastError` at `0x140004098`
- `KERNEL32!SetLastError` at `0x14000411d`
- `KERNEL32!CreateSemaphoreExW` at `0x140004038`
- `KERNEL32!CreateSemaphoreExW` at `0x1400040d4`
- `KERNEL32!CreateSemaphoreExW` at `0x140004038`
- `KERNEL32!CreateSemaphoreExW` at `0x1400040d4`
- `KERNEL32!GetLastError` at `0x14000406d`
- `KERNEL32!GetLastError` at `0x14000407b`
- `KERNEL32!GetLastError` at `0x1400040f7`
- `KERNEL32!GetLastError` at `0x140004106`
- `KERNEL32!GetLastError` at `0x14000406d`
- `KERNEL32!GetLastError` at `0x14000407b`
- `KERNEL32!GetLastError` at `0x1400040f7`
- `KERNEL32!GetLastError` at `0x140004106`

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
0x140003f74  mov     [rsp+arg_8], rbx
0x140003f79  mov     [rsp+arg_10], rbp
0x140003f7e  push    rsi
0x140003f7f  push    rdi
0x140003f80  push    r12
0x140003f82  push    r14
0x140003f84  push    r15
0x140003f86  sub     rsp, 250h
0x140003f8d  mov     rax, cs:__security_cookie
0x140003f94  xor     rax, rsp
0x140003f97  mov     [rsp+278h+var_38], rax
0x140003f9f  mov     rax, 0C000000000000000h
0x140003fa9  mov     rbp, r9
0x140003fac  mov     r8, rdx
0x140003faf  mov     rdi, rcx
0x140003fb2  test    rax, r9
0x140003fb5  jnz     loc_140004168
0x140003fbb  xor     r12d, r12d
0x140003fbe  lea     rax, [rsp+278h+Name]
0x140003fc3  mov     ecx, 7FFFFFFEh
0x140003fc8  mov     edx, 104h
0x140003fcd  lea     esi, [r12+1]
0x140003fd2  test    rcx, rcx
0x140003fd5  jz      short loc_140003FF5
0x140003fd7  movzx   r9d, word ptr [r8]
0x140003fdb  test    r9w, r9w
0x140003fdf  jz      short loc_140003FF5
0x140003fe1  mov     [rax], r9w
0x140003fe5  add     r8, 2
0x140003fe9  add     rax, 2
0x140003fed  sub     rcx, rsi
0x140003ff0  sub     rdx, rsi; unsigned __int64
0x140003ff3  jnz     short loc_140003FD2
0x140003ff5  test    rdx, rdx
0x140003ff8  lea     rcx, [rax-2]
0x140003ffc  lea     r8, aP0; "_p0"
0x140004003  cmovnz  rcx, rax
0x140004007  mov     [rcx], r12w
0x14000400b  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004010  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004015  mov     edx, ebp
0x140004017  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000401f  and     edx, 7FFFFFFFh; lInitialCount
0x140004025  mov     [rsp+278h+dwFlags], r12d; int
0x14000402a  mov     r8d, esi
0x14000402d  lea     r9, [rsp+278h+Name]; lpName
0x140004032  cmova   r8d, edx; lMaximumCount
0x140004036  xor     ecx, ecx; lpSemaphoreAttributes
0x140004038  call    cs:__imp_CreateSemaphoreExW
0x14000403e  mov     r15, rax
0x140004041  test    rax, rax
0x140004044  jnz     short loc_14000406D
0x140004046  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000404b  mov     ebx, eax
0x14000404d  test    eax, eax
0x14000404f  jns     short loc_1400040A1
0x140004051  mov     edx, 8Bh; void *
0x140004056  mov     rcx, [rsp+278h]; this
0x14000405e  mov     r9d, ebx; char *
0x140004061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004066  mov     eax, ebx
0x140004068  jmp     loc_140004129
0x14000406d  call    cs:__imp_GetLastError
0x140004073  mov     rbx, [rdi]
0x140004076  test    rbx, rbx
0x140004079  jz      short loc_14000409E
0x14000407b  call    cs:__imp_GetLastError
0x140004081  mov     rcx, rbx; hObject
0x140004084  mov     r14d, eax
0x140004087  call    cs:__imp_CloseHandle
0x14000408d  test    eax, eax
0x14000408f  jz      loc_14000416E
0x140004095  mov     ecx, r14d; dwErrCode
0x140004098  call    cs:__imp_SetLastError
0x14000409e  mov     [rdi], r15
0x1400040a1  lea     r8, asc_14000B118; "h"
0x1400040a8  shr     rbp, 1Fh
0x1400040ac  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1400040b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400040b6  test    ebp, ebp
0x1400040b8  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400040c0  lea     r9, [rsp+278h+Name]; lpName
0x1400040c5  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x1400040ca  cmovnz  esi, ebp
0x1400040cd  mov     edx, ebp; lInitialCount
0x1400040cf  mov     r8d, esi; lMaximumCount
0x1400040d2  xor     ecx, ecx; lpSemaphoreAttributes
0x1400040d4  call    cs:__imp_CreateSemaphoreExW
0x1400040da  mov     rsi, rax
0x1400040dd  test    rax, rax
0x1400040e0  jnz     short loc_1400040F7
0x1400040e2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400040e7  mov     ebx, eax
0x1400040e9  test    eax, eax
0x1400040eb  jns     short loc_140004127
0x1400040ed  mov     edx, 90h
0x1400040f2  jmp     loc_140004056
0x1400040f7  call    cs:__imp_GetLastError
0x1400040fd  mov     rbx, [rdi+8]
0x140004101  test    rbx, rbx
0x140004104  jz      short loc_140004123
0x140004106  call    cs:__imp_GetLastError
0x14000410c  mov     rcx, rbx; hObject
0x14000410f  mov     ebp, eax
0x140004111  call    cs:__imp_CloseHandle
0x140004117  test    eax, eax
0x140004119  jz      short loc_140004155
0x14000411b  mov     ecx, ebp; dwErrCode
0x14000411d  call    cs:__imp_SetLastError
0x140004123  mov     [rdi+8], rsi
0x140004127  xor     eax, eax
0x140004129  mov     rcx, [rsp+278h+var_38]
0x140004131  xor     rcx, rsp; StackCookie
0x140004134  call    __security_check_cookie
0x140004139  lea     r11, [rsp+278h+var_28]
0x140004141  mov     rbx, [r11+38h]
0x140004145  mov     rbp, [r11+40h]
0x140004149  mov     rsp, r11
0x14000414c  pop     r15
0x14000414e  pop     r14
0x140004150  pop     r12
0x140004152  pop     rdi
0x140004153  pop     rsi
0x140004154  retn
0x140004155  mov     rcx, [rsp+278h]; this
0x14000415d  mov     edx, 0A0Bh; void *
0x140004162  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004168  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000416e  mov     rcx, [rsp+278h]; this
0x140004176  mov     edx, 0A0Bh; void *
0x14000417b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
