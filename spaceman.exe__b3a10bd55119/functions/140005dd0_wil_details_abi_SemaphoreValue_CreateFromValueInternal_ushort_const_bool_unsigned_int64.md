# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140005dd0`
- end: `0x140005fdd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400054ac`
- `0x140005850`

## callees

- `0x140005dd0`
- `0x140006b58`
- `0x1400089e0`
- `0x140009000`
- `0x14000a00c`
- `0x14000a01c`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f62`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005e94`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005f30`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005e94`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f6d`

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
0x140005dd0  mov     [rsp+arg_8], rbx
0x140005dd5  mov     [rsp+arg_10], rbp
0x140005dda  push    rsi
0x140005ddb  push    rdi
0x140005ddc  push    r12
0x140005dde  push    r14
0x140005de0  push    r15
0x140005de2  sub     rsp, 250h
0x140005de9  mov     rax, cs:__security_cookie
0x140005df0  xor     rax, rsp
0x140005df3  mov     [rsp+278h+var_38], rax
0x140005dfb  mov     rax, 0C000000000000000h
0x140005e05  mov     rbp, r9
0x140005e08  mov     r8, rdx
0x140005e0b  mov     rdi, rcx
0x140005e0e  test    rax, r9
0x140005e11  jnz     loc_140005FC4
0x140005e17  xor     r12d, r12d
0x140005e1a  lea     rax, [rsp+278h+Name]
0x140005e1f  mov     ecx, 7FFFFFFEh
0x140005e24  mov     edx, 104h
0x140005e29  lea     esi, [r12+1]
0x140005e2e  test    rcx, rcx
0x140005e31  jz      short loc_140005E51
0x140005e33  movzx   r9d, word ptr [r8]
0x140005e37  test    r9w, r9w
0x140005e3b  jz      short loc_140005E51
0x140005e3d  mov     [rax], r9w
0x140005e41  add     r8, 2
0x140005e45  add     rax, 2
0x140005e49  sub     rcx, rsi
0x140005e4c  sub     rdx, rsi; unsigned __int64
0x140005e4f  jnz     short loc_140005E2E
0x140005e51  test    rdx, rdx
0x140005e54  lea     rcx, [rax-2]
0x140005e58  lea     r8, aP0; "_p0"
0x140005e5f  cmovnz  rcx, rax
0x140005e63  mov     [rcx], r12w
0x140005e67  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140005e6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005e71  mov     edx, ebp
0x140005e73  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005e7b  and     edx, 7FFFFFFFh; lInitialCount
0x140005e81  mov     [rsp+278h+dwFlags], r12d; int
0x140005e86  mov     r8d, esi
0x140005e89  lea     r9, [rsp+278h+Name]; lpName
0x140005e8e  cmova   r8d, edx; lMaximumCount
0x140005e92  xor     ecx, ecx; lpSemaphoreAttributes
0x140005e94  call    cs:__imp_CreateSemaphoreExW
0x140005e9a  mov     r15, rax
0x140005e9d  test    rax, rax
0x140005ea0  jnz     short loc_140005EC9
0x140005ea2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005ea7  mov     ebx, eax
0x140005ea9  test    eax, eax
0x140005eab  jns     short loc_140005EFD
0x140005ead  mov     edx, 8Bh; void *
0x140005eb2  mov     rcx, [rsp+278h]; this
0x140005eba  mov     r9d, ebx; char *
0x140005ebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005ec2  mov     eax, ebx
0x140005ec4  jmp     loc_140005F85
0x140005ec9  call    cs:__imp_GetLastError
0x140005ecf  mov     rbx, [rdi]
0x140005ed2  test    rbx, rbx
0x140005ed5  jz      short loc_140005EFA
0x140005ed7  call    cs:__imp_GetLastError
0x140005edd  mov     rcx, rbx; hObject
0x140005ee0  mov     r14d, eax
0x140005ee3  call    cs:__imp_CloseHandle
0x140005ee9  test    eax, eax
0x140005eeb  jz      loc_140005FCA
0x140005ef1  mov     ecx, r14d; dwErrCode
0x140005ef4  call    cs:__imp_SetLastError
0x140005efa  mov     [rdi], r15
0x140005efd  lea     r8, asc_14000FE38; "h"
0x140005f04  shr     rbp, 1Fh
0x140005f08  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140005f0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f12  test    ebp, ebp
0x140005f14  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005f1c  lea     r9, [rsp+278h+Name]; lpName
0x140005f21  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140005f26  cmovnz  esi, ebp
0x140005f29  mov     edx, ebp; lInitialCount
0x140005f2b  mov     r8d, esi; lMaximumCount
0x140005f2e  xor     ecx, ecx; lpSemaphoreAttributes
0x140005f30  call    cs:__imp_CreateSemaphoreExW
0x140005f36  mov     rsi, rax
0x140005f39  test    rax, rax
0x140005f3c  jnz     short loc_140005F53
0x140005f3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005f43  mov     ebx, eax
0x140005f45  test    eax, eax
0x140005f47  jns     short loc_140005F83
0x140005f49  mov     edx, 90h
0x140005f4e  jmp     loc_140005EB2
0x140005f53  call    cs:__imp_GetLastError
0x140005f59  mov     rbx, [rdi+8]
0x140005f5d  test    rbx, rbx
0x140005f60  jz      short loc_140005F7F
0x140005f62  call    cs:__imp_GetLastError
0x140005f68  mov     rcx, rbx; hObject
0x140005f6b  mov     ebp, eax
0x140005f6d  call    cs:__imp_CloseHandle
0x140005f73  test    eax, eax
0x140005f75  jz      short loc_140005FB1
0x140005f77  mov     ecx, ebp; dwErrCode
0x140005f79  call    cs:__imp_SetLastError
0x140005f7f  mov     [rdi+8], rsi
0x140005f83  xor     eax, eax
0x140005f85  mov     rcx, [rsp+278h+var_38]
0x140005f8d  xor     rcx, rsp; StackCookie
0x140005f90  call    __security_check_cookie
0x140005f95  lea     r11, [rsp+278h+var_28]
0x140005f9d  mov     rbx, [r11+38h]
0x140005fa1  mov     rbp, [r11+40h]
0x140005fa5  mov     rsp, r11
0x140005fa8  pop     r15
0x140005faa  pop     r14
0x140005fac  pop     r12
0x140005fae  pop     rdi
0x140005faf  pop     rsi
0x140005fb0  retn
0x140005fb1  mov     rcx, [rsp+278h]; this
0x140005fb9  mov     edx, 0A0Bh; void *
0x140005fbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005fc4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005fca  mov     rcx, [rsp+278h]; this
0x140005fd2  mov     edx, 0A0Bh; void *
0x140005fd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
