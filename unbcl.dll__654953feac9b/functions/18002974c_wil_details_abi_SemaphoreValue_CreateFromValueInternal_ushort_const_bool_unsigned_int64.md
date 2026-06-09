# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x18002974c`
- end: `0x180029975`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `553`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027620`

## callees

- `0x18002974c`
- `0x18002ccb8`
- `0x18002fcac`
- `0x1800308c4`
- `0x180030f64`
- `0x180030f74`
- `0x180069020`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180029872`
- `KERNEL32!CloseHandle` at `0x18002990d`
- `KERNEL32!CloseHandle` at `0x180029872`
- `KERNEL32!CloseHandle` at `0x18002990d`
- `KERNEL32!GetLastError` at `0x18002984f`
- `KERNEL32!GetLastError` at `0x18002985d`
- `KERNEL32!GetLastError` at `0x1800298ea`
- `KERNEL32!GetLastError` at `0x1800298f9`
- `KERNEL32!GetLastError` at `0x18002984f`
- `KERNEL32!GetLastError` at `0x18002985d`
- `KERNEL32!GetLastError` at `0x1800298ea`
- `KERNEL32!GetLastError` at `0x1800298f9`
- `KERNEL32!SetLastError` at `0x18002988b`
- `KERNEL32!SetLastError` at `0x180029921`
- `KERNEL32!SetLastError` at `0x18002988b`
- `KERNEL32!SetLastError` at `0x180029921`
- `KERNEL32!CreateSemaphoreExW` at `0x18002981a`
- `KERNEL32!CreateSemaphoreExW` at `0x1800298c7`
- `KERNEL32!CreateSemaphoreExW` at `0x18002981a`
- `KERNEL32!CreateSemaphoreExW` at `0x1800298c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        WCHAR *a2,
        __int64 a3,
        unsigned __int64 a4)
{
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rax
  LONG v10; // esi
  WCHAR v11; // r9
  WCHAR *v12; // rcx
  LONG v13; // r8d
  wil::details *v14; // rcx
  HANDLE Semaphore; // r15
  unsigned __int64 v16; // rdx
  int LastErrorFailHr; // ebx
  unsigned int v18; // r8d
  __int64 v19; // rdx
  void *v21; // rbx
  DWORD LastError; // r14d
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned __int64 v25; // rbp
  wil::details *v26; // rcx
  HANDLE v27; // rbp
  void *v28; // rbx
  DWORD v29; // esi
  unsigned int v30; // r8d
  const char *v31; // r9
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  __int64 v33; // [rsp+38h] [rbp-250h]
  WCHAR Name[264]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  HIWORD(v33) = -1;
  if ( (a4 & 0xC000000000000000uLL) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  v7 = 2147483646;
  v8 = 260;
  v9 = Name;
  v10 = 1;
  do
  {
    if ( !v7 )
      break;
    v11 = *a2;
    if ( !*a2 )
      break;
    ++a2;
    *v9++ = v11;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  StringCchCatW(Name, v8, L"_p0");
  v13 = 1;
  if ( (a4 & 0x7FFFFFFF) != 0 )
    v13 = a4 & 0x7FFFFFFF;
  Semaphore = CreateSemaphoreExW(0, a4 & 0x7FFFFFFF, v13, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v21 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v21) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Semaphore;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v14);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 139;
LABEL_13:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v19, v18, (const char *)(unsigned int)LastErrorFailHr, dwFlags);
      return (unsigned int)LastErrorFailHr;
    }
  }
  v25 = a4 >> 31;
  StringCchCatW(Name, v16, L"h");
  if ( (_DWORD)v25 )
    v10 = v25;
  v27 = CreateSemaphoreExW(0, v25, v10, Name, 0, 0x1F0003u);
  if ( v27 )
  {
    GetLastError();
    v28 = (void *)*((_QWORD *)this + 1);
    if ( v28 )
    {
      v29 = GetLastError();
      if ( !CloseHandle(v28) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
      SetLastError(v29);
    }
    *((_QWORD *)this + 1) = v27;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v26);
    if ( LastErrorFailHr < 0 )
    {
      v19 = 144;
      goto LABEL_13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002974c  mov     rax, rsp
0x18002974f  push    rsi
0x180029750  push    rdi
0x180029751  push    r12
0x180029753  push    r14
0x180029755  push    r15
0x180029757  sub     rsp, 260h
0x18002975e  mov     [rsp+288h+var_250], 0FFFFFFFFFFFFFFFEh
0x180029767  mov     [rax+10h], rbx
0x18002976b  mov     [rax+18h], rbp
0x18002976f  mov     rax, cs:__security_cookie
0x180029776  xor     rax, rsp
0x180029779  mov     [rsp+288h+var_38], rax
0x180029781  mov     rbp, r9
0x180029784  mov     r8, rdx
0x180029787  mov     rdi, rcx
0x18002978a  mov     rax, 0C000000000000000h
0x180029794  test    rax, r9
0x180029797  jnz     loc_180029964
0x18002979d  mov     ecx, 7FFFFFFEh
0x1800297a2  mov     edx, 104h
0x1800297a7  lea     rax, [rsp+288h+Name]
0x1800297ac  xor     r12d, r12d
0x1800297af  lea     esi, [r12+1]
0x1800297b4  test    rcx, rcx
0x1800297b7  jz      short loc_1800297D7
0x1800297b9  movzx   r9d, word ptr [r8]
0x1800297bd  test    r9w, r9w
0x1800297c1  jz      short loc_1800297D7
0x1800297c3  add     r8, 2
0x1800297c7  mov     [rax], r9w
0x1800297cb  add     rax, 2
0x1800297cf  sub     rcx, rsi
0x1800297d2  sub     rdx, rsi; unsigned __int64
0x1800297d5  jnz     short loc_1800297B4
0x1800297d7  lea     rcx, [rax-2]
0x1800297db  test    rdx, rdx
0x1800297de  cmovnz  rcx, rax
0x1800297e2  mov     [rcx], r12w
0x1800297e6  lea     r8, aP0; "_p0"
0x1800297ed  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800297f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800297f7  mov     edx, ebp
0x1800297f9  and     edx, 7FFFFFFFh; lInitialCount
0x1800297ff  mov     r8d, esi
0x180029802  cmova   r8d, edx; lMaximumCount
0x180029806  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18002980e  mov     [rsp+288h+dwFlags], r12d; int
0x180029813  lea     r9, [rsp+288h+Name]; lpName
0x180029818  xor     ecx, ecx; lpSemaphoreAttributes
0x18002981a  call    cs:__imp_CreateSemaphoreExW
0x180029820  mov     r15, rax
0x180029823  test    rax, rax
0x180029826  jnz     short loc_18002984F
0x180029828  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002982d  mov     ebx, eax
0x18002982f  test    eax, eax
0x180029831  jns     short loc_180029894
0x180029833  mov     edx, 8Bh; void *
0x180029838  mov     r9d, ebx; char *
0x18002983b  mov     rcx, [rsp+288h]; this
0x180029843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029848  mov     eax, ebx
0x18002984a  jmp     loc_18002992D
0x18002984f  call    cs:__imp_GetLastError
0x180029855  mov     rbx, [rdi]
0x180029858  test    rbx, rbx
0x18002985b  jz      short loc_180029891
0x18002985d  call    cs:__imp_GetLastError
0x180029863  mov     r14d, eax
0x180029866  mov     [rsp+288h+var_258], r12b
0x18002986b  mov     [rsp+288h+var_254], eax
0x18002986f  mov     rcx, rbx; hObject
0x180029872  call    cs:__imp_CloseHandle
0x180029878  mov     rcx, [rsp+288h]; this
0x180029880  test    eax, eax
0x180029882  jz      loc_18002996A
0x180029888  mov     ecx, r14d; dwErrCode
0x18002988b  call    cs:__imp_SetLastError
0x180029891  mov     [rdi], r15
0x180029894  shr     rbp, 1Fh
0x180029898  lea     r8, asc_180080CB0; "h"
0x18002989f  lea     rcx, [rsp+288h+Name]; unsigned __int16 *
0x1800298a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800298a9  test    ebp, ebp
0x1800298ab  cmovnz  esi, ebp
0x1800298ae  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800298b6  mov     [rsp+288h+dwFlags], r12d; dwFlags
0x1800298bb  lea     r9, [rsp+288h+Name]; lpName
0x1800298c0  mov     r8d, esi; lMaximumCount
0x1800298c3  mov     edx, ebp; lInitialCount
0x1800298c5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800298c7  call    cs:__imp_CreateSemaphoreExW
0x1800298cd  mov     rbp, rax
0x1800298d0  test    rax, rax
0x1800298d3  jnz     short loc_1800298EA
0x1800298d5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800298da  mov     ebx, eax
0x1800298dc  test    eax, eax
0x1800298de  jns     short loc_18002992B
0x1800298e0  mov     edx, 90h
0x1800298e5  jmp     loc_180029838
0x1800298ea  call    cs:__imp_GetLastError
0x1800298f0  mov     rbx, [rdi+8]
0x1800298f4  test    rbx, rbx
0x1800298f7  jz      short loc_180029927
0x1800298f9  call    cs:__imp_GetLastError
0x1800298ff  mov     esi, eax
0x180029901  mov     [rsp+288h+var_258], r12b
0x180029906  mov     [rsp+288h+var_254], eax
0x18002990a  mov     rcx, rbx; hObject
0x18002990d  call    cs:__imp_CloseHandle
0x180029913  mov     rcx, [rsp+288h]; this
0x18002991b  test    eax, eax
0x18002991d  jz      short loc_180029959
0x18002991f  mov     ecx, esi; dwErrCode
0x180029921  call    cs:__imp_SetLastError
0x180029927  mov     [rdi+8], rbp
0x18002992b  xor     eax, eax
0x18002992d  mov     rcx, [rsp+288h+var_38]
0x180029935  xor     rcx, rsp; StackCookie
0x180029938  call    __security_check_cookie
0x18002993d  lea     r11, [rsp+288h+var_28]
0x180029945  mov     rbx, [r11+38h]
0x180029949  mov     rbp, [r11+40h]
0x18002994d  mov     rsp, r11
0x180029950  pop     r15
0x180029952  pop     r14
0x180029954  pop     r12
0x180029956  pop     rdi
0x180029957  pop     rsi
0x180029958  retn
0x180029959  mov     edx, 0A0Bh; void *
0x18002995e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180029964  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002996a  mov     edx, 0A0Bh; void *
0x18002996f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
