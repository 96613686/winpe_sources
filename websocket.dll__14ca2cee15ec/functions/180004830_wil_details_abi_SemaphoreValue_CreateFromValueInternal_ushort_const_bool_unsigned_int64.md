# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x180004830`
- end: `0x180004a3d`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e4c`
- `0x1800041f0`

## callees

- `0x180001670`
- `0x180004830`
- `0x180005678`
- `0x180007b90`
- `0x180007fac`
- `0x180008d08`
- `0x180008d18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004954`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800048f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004990`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800048f4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800049cd`

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
0x180004830  mov     [rsp+arg_8], rbx
0x180004835  mov     [rsp+arg_10], rbp
0x18000483a  push    rsi
0x18000483b  push    rdi
0x18000483c  push    r12
0x18000483e  push    r14
0x180004840  push    r15
0x180004842  sub     rsp, 250h
0x180004849  mov     rax, cs:__security_cookie
0x180004850  xor     rax, rsp
0x180004853  mov     [rsp+278h+var_38], rax
0x18000485b  mov     rax, 0C000000000000000h
0x180004865  mov     rbp, r9
0x180004868  mov     r8, rdx
0x18000486b  mov     rdi, rcx
0x18000486e  test    rax, r9
0x180004871  jnz     loc_180004A24
0x180004877  xor     r12d, r12d
0x18000487a  lea     rax, [rsp+278h+Name]
0x18000487f  mov     ecx, 7FFFFFFEh
0x180004884  mov     edx, 104h
0x180004889  lea     esi, [r12+1]
0x18000488e  test    rcx, rcx
0x180004891  jz      short loc_1800048B1
0x180004893  movzx   r9d, word ptr [r8]
0x180004897  test    r9w, r9w
0x18000489b  jz      short loc_1800048B1
0x18000489d  mov     [rax], r9w
0x1800048a1  add     r8, 2
0x1800048a5  add     rax, 2
0x1800048a9  sub     rcx, rsi
0x1800048ac  sub     rdx, rsi; unsigned __int64
0x1800048af  jnz     short loc_18000488E
0x1800048b1  test    rdx, rdx
0x1800048b4  lea     rcx, [rax-2]
0x1800048b8  lea     r8, aP0; "_p0"
0x1800048bf  cmovnz  rcx, rax
0x1800048c3  mov     [rcx], r12w
0x1800048c7  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x1800048cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800048d1  mov     edx, ebp
0x1800048d3  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800048db  and     edx, 7FFFFFFFh; lInitialCount
0x1800048e1  mov     [rsp+278h+dwFlags], r12d; int
0x1800048e6  mov     r8d, esi
0x1800048e9  lea     r9, [rsp+278h+Name]; lpName
0x1800048ee  cmova   r8d, edx; lMaximumCount
0x1800048f2  xor     ecx, ecx; lpSemaphoreAttributes
0x1800048f4  call    cs:__imp_CreateSemaphoreExW
0x1800048fa  mov     r15, rax
0x1800048fd  test    rax, rax
0x180004900  jnz     short loc_180004929
0x180004902  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004907  mov     ebx, eax
0x180004909  test    eax, eax
0x18000490b  jns     short loc_18000495D
0x18000490d  mov     edx, 8Bh; void *
0x180004912  mov     rcx, [rsp+278h]; this
0x18000491a  mov     r9d, ebx; char *
0x18000491d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004922  mov     eax, ebx
0x180004924  jmp     loc_1800049E5
0x180004929  call    cs:__imp_GetLastError
0x18000492f  mov     rbx, [rdi]
0x180004932  test    rbx, rbx
0x180004935  jz      short loc_18000495A
0x180004937  call    cs:__imp_GetLastError
0x18000493d  mov     rcx, rbx; hObject
0x180004940  mov     r14d, eax
0x180004943  call    cs:__imp_CloseHandle
0x180004949  test    eax, eax
0x18000494b  jz      loc_180004A2A
0x180004951  mov     ecx, r14d; dwErrCode
0x180004954  call    cs:__imp_SetLastError
0x18000495a  mov     [rdi], r15
0x18000495d  lea     r8, asc_18000FDC8; "h"
0x180004964  shr     rbp, 1Fh
0x180004968  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000496d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004972  test    ebp, ebp
0x180004974  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000497c  lea     r9, [rsp+278h+Name]; lpName
0x180004981  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x180004986  cmovnz  esi, ebp
0x180004989  mov     edx, ebp; lInitialCount
0x18000498b  mov     r8d, esi; lMaximumCount
0x18000498e  xor     ecx, ecx; lpSemaphoreAttributes
0x180004990  call    cs:__imp_CreateSemaphoreExW
0x180004996  mov     rsi, rax
0x180004999  test    rax, rax
0x18000499c  jnz     short loc_1800049B3
0x18000499e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800049a3  mov     ebx, eax
0x1800049a5  test    eax, eax
0x1800049a7  jns     short loc_1800049E3
0x1800049a9  mov     edx, 90h
0x1800049ae  jmp     loc_180004912
0x1800049b3  call    cs:__imp_GetLastError
0x1800049b9  mov     rbx, [rdi+8]
0x1800049bd  test    rbx, rbx
0x1800049c0  jz      short loc_1800049DF
0x1800049c2  call    cs:__imp_GetLastError
0x1800049c8  mov     rcx, rbx; hObject
0x1800049cb  mov     ebp, eax
0x1800049cd  call    cs:__imp_CloseHandle
0x1800049d3  test    eax, eax
0x1800049d5  jz      short loc_180004A11
0x1800049d7  mov     ecx, ebp; dwErrCode
0x1800049d9  call    cs:__imp_SetLastError
0x1800049df  mov     [rdi+8], rsi
0x1800049e3  xor     eax, eax
0x1800049e5  mov     rcx, [rsp+278h+var_38]
0x1800049ed  xor     rcx, rsp; StackCookie
0x1800049f0  call    __security_check_cookie
0x1800049f5  lea     r11, [rsp+278h+var_28]
0x1800049fd  mov     rbx, [r11+38h]
0x180004a01  mov     rbp, [r11+40h]
0x180004a05  mov     rsp, r11
0x180004a08  pop     r15
0x180004a0a  pop     r14
0x180004a0c  pop     r12
0x180004a0e  pop     rdi
0x180004a0f  pop     rsi
0x180004a10  retn
0x180004a11  mov     rcx, [rsp+278h]; this
0x180004a19  mov     edx, 0A0Bh; void *
0x180004a1e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004a24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a2a  mov     rcx, [rsp+278h]; this
0x180004a32  mov     edx, 0A0Bh; void *
0x180004a37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
