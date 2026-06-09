# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1800044e8`
- end: `0x1800046f5`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const unsigned __int16 *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004144`

## callees

- `0x180001510`
- `0x1800044e8`
- `0x180004998`
- `0x1800052cc`
- `0x180005510`
- `0x180005910`
- `0x180005920`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004685`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000466b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000466b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000467a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000460c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004691`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000460c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004691`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800045ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004648`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800045ac`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180004648`

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
0x1800044e8  mov     [rsp+arg_8], rbx
0x1800044ed  mov     [rsp+arg_10], rbp
0x1800044f2  push    rsi
0x1800044f3  push    rdi
0x1800044f4  push    r12
0x1800044f6  push    r14
0x1800044f8  push    r15
0x1800044fa  sub     rsp, 250h
0x180004501  mov     rax, cs:__security_cookie
0x180004508  xor     rax, rsp
0x18000450b  mov     [rsp+278h+var_38], rax
0x180004513  mov     rax, 0C000000000000000h
0x18000451d  mov     rbp, r9
0x180004520  mov     r8, rdx
0x180004523  mov     rdi, rcx
0x180004526  test    rax, r9
0x180004529  jnz     loc_1800046DC
0x18000452f  xor     r12d, r12d
0x180004532  lea     rax, [rsp+278h+Name]
0x180004537  mov     ecx, 7FFFFFFEh
0x18000453c  mov     edx, 104h
0x180004541  lea     esi, [r12+1]
0x180004546  test    rcx, rcx
0x180004549  jz      short loc_180004569
0x18000454b  movzx   r9d, word ptr [r8]
0x18000454f  test    r9w, r9w
0x180004553  jz      short loc_180004569
0x180004555  mov     [rax], r9w
0x180004559  add     r8, 2
0x18000455d  add     rax, 2
0x180004561  sub     rcx, rsi
0x180004564  sub     rdx, rsi; unsigned __int64
0x180004567  jnz     short loc_180004546
0x180004569  test    rdx, rdx
0x18000456c  lea     rcx, [rax-2]
0x180004570  lea     r8, aP0; "_p0"
0x180004577  cmovnz  rcx, rax
0x18000457b  mov     [rcx], r12w
0x18000457f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004584  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004589  mov     edx, ebp
0x18000458b  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004593  and     edx, 7FFFFFFFh; lInitialCount
0x180004599  mov     [rsp+278h+dwFlags], r12d; int
0x18000459e  mov     r8d, esi
0x1800045a1  lea     r9, [rsp+278h+Name]; lpName
0x1800045a6  cmova   r8d, edx; lMaximumCount
0x1800045aa  xor     ecx, ecx; lpSemaphoreAttributes
0x1800045ac  call    cs:__imp_CreateSemaphoreExW
0x1800045b2  mov     r15, rax
0x1800045b5  test    rax, rax
0x1800045b8  jnz     short loc_1800045E1
0x1800045ba  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800045bf  mov     ebx, eax
0x1800045c1  test    eax, eax
0x1800045c3  jns     short loc_180004615
0x1800045c5  mov     edx, 8Bh; void *
0x1800045ca  mov     rcx, [rsp+278h]; this
0x1800045d2  mov     r9d, ebx; char *
0x1800045d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045da  mov     eax, ebx
0x1800045dc  jmp     loc_18000469D
0x1800045e1  call    cs:__imp_GetLastError
0x1800045e7  mov     rbx, [rdi]
0x1800045ea  test    rbx, rbx
0x1800045ed  jz      short loc_180004612
0x1800045ef  call    cs:__imp_GetLastError
0x1800045f5  mov     rcx, rbx; hObject
0x1800045f8  mov     r14d, eax
0x1800045fb  call    cs:__imp_CloseHandle
0x180004601  test    eax, eax
0x180004603  jz      loc_1800046E2
0x180004609  mov     ecx, r14d; dwErrCode
0x18000460c  call    cs:__imp_SetLastError
0x180004612  mov     [rdi], r15
0x180004615  lea     r8, asc_180008968; "h"
0x18000461c  shr     rbp, 1Fh
0x180004620  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x180004625  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000462a  test    ebp, ebp
0x18000462c  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180004634  lea     r9, [rsp+278h+Name]; lpName
0x180004639  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x18000463e  cmovnz  esi, ebp
0x180004641  mov     edx, ebp; lInitialCount
0x180004643  mov     r8d, esi; lMaximumCount
0x180004646  xor     ecx, ecx; lpSemaphoreAttributes
0x180004648  call    cs:__imp_CreateSemaphoreExW
0x18000464e  mov     rsi, rax
0x180004651  test    rax, rax
0x180004654  jnz     short loc_18000466B
0x180004656  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000465b  mov     ebx, eax
0x18000465d  test    eax, eax
0x18000465f  jns     short loc_18000469B
0x180004661  mov     edx, 90h
0x180004666  jmp     loc_1800045CA
0x18000466b  call    cs:__imp_GetLastError
0x180004671  mov     rbx, [rdi+8]
0x180004675  test    rbx, rbx
0x180004678  jz      short loc_180004697
0x18000467a  call    cs:__imp_GetLastError
0x180004680  mov     rcx, rbx; hObject
0x180004683  mov     ebp, eax
0x180004685  call    cs:__imp_CloseHandle
0x18000468b  test    eax, eax
0x18000468d  jz      short loc_1800046C9
0x18000468f  mov     ecx, ebp; dwErrCode
0x180004691  call    cs:__imp_SetLastError
0x180004697  mov     [rdi+8], rsi
0x18000469b  xor     eax, eax
0x18000469d  mov     rcx, [rsp+278h+var_38]
0x1800046a5  xor     rcx, rsp; StackCookie
0x1800046a8  call    __security_check_cookie
0x1800046ad  lea     r11, [rsp+278h+var_28]
0x1800046b5  mov     rbx, [r11+38h]
0x1800046b9  mov     rbp, [r11+40h]
0x1800046bd  mov     rsp, r11
0x1800046c0  pop     r15
0x1800046c2  pop     r14
0x1800046c4  pop     r12
0x1800046c6  pop     rdi
0x1800046c7  pop     rsi
0x1800046c8  retn
0x1800046c9  mov     rcx, [rsp+278h]; this
0x1800046d1  mov     edx, 0A0Bh; void *
0x1800046d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800046dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800046e2  mov     rcx, [rsp+278h]; this
0x1800046ea  mov     edx, 0A0Bh; void *
0x1800046ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
