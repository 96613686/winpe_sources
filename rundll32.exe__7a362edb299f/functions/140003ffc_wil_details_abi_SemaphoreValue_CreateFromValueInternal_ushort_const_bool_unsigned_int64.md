# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x140003ffc`
- end: `0x140004209`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003b94`
- `0x14000897c`

## callees

- `0x1400015a0`
- `0x140003ffc`
- `0x140004c88`
- `0x140005ed8`
- `0x140006204`
- `0x140006ce8`
- `0x140006cf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400040c0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000415c`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400040c0`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000415c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000417f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000418e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400040f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000417f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000418e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004120`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400041a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004120`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400041a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000410f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000410f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004199`

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
0x140003ffc  mov     [rsp+arg_8], rbx
0x140004001  mov     [rsp+arg_10], rbp
0x140004006  push    rsi
0x140004007  push    rdi
0x140004008  push    r12
0x14000400a  push    r14
0x14000400c  push    r15
0x14000400e  sub     rsp, 250h
0x140004015  mov     rax, cs:__security_cookie
0x14000401c  xor     rax, rsp
0x14000401f  mov     [rsp+278h+var_38], rax
0x140004027  mov     rax, 0C000000000000000h
0x140004031  mov     rbp, r9
0x140004034  mov     r8, rdx
0x140004037  mov     rdi, rcx
0x14000403a  test    rax, r9
0x14000403d  jnz     loc_1400041F0
0x140004043  xor     r12d, r12d
0x140004046  lea     rax, [rsp+278h+Name]
0x14000404b  mov     ecx, 7FFFFFFEh
0x140004050  mov     edx, 104h
0x140004055  lea     esi, [r12+1]
0x14000405a  test    rcx, rcx
0x14000405d  jz      short loc_14000407D
0x14000405f  movzx   r9d, word ptr [r8]
0x140004063  test    r9w, r9w
0x140004067  jz      short loc_14000407D
0x140004069  mov     [rax], r9w
0x14000406d  add     r8, 2
0x140004071  add     rax, 2
0x140004075  sub     rcx, rsi
0x140004078  sub     rdx, rsi; unsigned __int64
0x14000407b  jnz     short loc_14000405A
0x14000407d  test    rdx, rdx
0x140004080  lea     rcx, [rax-2]
0x140004084  lea     r8, aP0; "_p0"
0x14000408b  cmovnz  rcx, rax
0x14000408f  mov     [rcx], r12w
0x140004093  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004098  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000409d  mov     edx, ebp
0x14000409f  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400040a7  and     edx, 7FFFFFFFh; lInitialCount
0x1400040ad  mov     [rsp+278h+dwFlags], r12d; int
0x1400040b2  mov     r8d, esi
0x1400040b5  lea     r9, [rsp+278h+Name]; lpName
0x1400040ba  cmova   r8d, edx; lMaximumCount
0x1400040be  xor     ecx, ecx; lpSemaphoreAttributes
0x1400040c0  call    cs:__imp_CreateSemaphoreExW
0x1400040c6  mov     r15, rax
0x1400040c9  test    rax, rax
0x1400040cc  jnz     short loc_1400040F5
0x1400040ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400040d3  mov     ebx, eax
0x1400040d5  test    eax, eax
0x1400040d7  jns     short loc_140004129
0x1400040d9  mov     edx, 8Bh; void *
0x1400040de  mov     rcx, [rsp+278h]; this
0x1400040e6  mov     r9d, ebx; char *
0x1400040e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400040ee  mov     eax, ebx
0x1400040f0  jmp     loc_1400041B1
0x1400040f5  call    cs:__imp_GetLastError
0x1400040fb  mov     rbx, [rdi]
0x1400040fe  test    rbx, rbx
0x140004101  jz      short loc_140004126
0x140004103  call    cs:__imp_GetLastError
0x140004109  mov     rcx, rbx; hObject
0x14000410c  mov     r14d, eax
0x14000410f  call    cs:__imp_CloseHandle
0x140004115  test    eax, eax
0x140004117  jz      loc_1400041F6
0x14000411d  mov     ecx, r14d; dwErrCode
0x140004120  call    cs:__imp_SetLastError
0x140004126  mov     [rdi], r15
0x140004129  lea     r8, asc_14000E1B8; "h"
0x140004130  shr     rbp, 1Fh
0x140004134  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140004139  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000413e  test    ebp, ebp
0x140004140  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140004148  lea     r9, [rsp+278h+Name]; lpName
0x14000414d  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140004152  cmovnz  esi, ebp
0x140004155  mov     edx, ebp; lInitialCount
0x140004157  mov     r8d, esi; lMaximumCount
0x14000415a  xor     ecx, ecx; lpSemaphoreAttributes
0x14000415c  call    cs:__imp_CreateSemaphoreExW
0x140004162  mov     rsi, rax
0x140004165  test    rax, rax
0x140004168  jnz     short loc_14000417F
0x14000416a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000416f  mov     ebx, eax
0x140004171  test    eax, eax
0x140004173  jns     short loc_1400041AF
0x140004175  mov     edx, 90h
0x14000417a  jmp     loc_1400040DE
0x14000417f  call    cs:__imp_GetLastError
0x140004185  mov     rbx, [rdi+8]
0x140004189  test    rbx, rbx
0x14000418c  jz      short loc_1400041AB
0x14000418e  call    cs:__imp_GetLastError
0x140004194  mov     rcx, rbx; hObject
0x140004197  mov     ebp, eax
0x140004199  call    cs:__imp_CloseHandle
0x14000419f  test    eax, eax
0x1400041a1  jz      short loc_1400041DD
0x1400041a3  mov     ecx, ebp; dwErrCode
0x1400041a5  call    cs:__imp_SetLastError
0x1400041ab  mov     [rdi+8], rsi
0x1400041af  xor     eax, eax
0x1400041b1  mov     rcx, [rsp+278h+var_38]
0x1400041b9  xor     rcx, rsp; StackCookie
0x1400041bc  call    __security_check_cookie
0x1400041c1  lea     r11, [rsp+278h+var_28]
0x1400041c9  mov     rbx, [r11+38h]
0x1400041cd  mov     rbp, [r11+40h]
0x1400041d1  mov     rsp, r11
0x1400041d4  pop     r15
0x1400041d6  pop     r14
0x1400041d8  pop     r12
0x1400041da  pop     rdi
0x1400041db  pop     rsi
0x1400041dc  retn
0x1400041dd  mov     rcx, [rsp+278h]; this
0x1400041e5  mov     edx, 0A0Bh; void *
0x1400041ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400041f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400041f6  mov     rcx, [rsp+278h]; this
0x1400041fe  mov     edx, 0A0Bh; void *
0x140004203  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
