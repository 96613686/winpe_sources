# wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)

- ea: `0x1400093d0`
- end: `0x1400095dd`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z`
- size: `525`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *this, WCHAR *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008c5c`
- `0x140009000`

## callees

- `0x140005d74`
- `0x1400093d0`
- `0x14000a158`
- `0x14000bf30`
- `0x14000cdac`
- `0x14000cdbc`
- `0x140010980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400094c9`
- `KERNEL32!GetLastError` at `0x1400094d7`
- `KERNEL32!GetLastError` at `0x140009553`
- `KERNEL32!GetLastError` at `0x140009562`
- `KERNEL32!GetLastError` at `0x1400094c9`
- `KERNEL32!GetLastError` at `0x1400094d7`
- `KERNEL32!GetLastError` at `0x140009553`
- `KERNEL32!GetLastError` at `0x140009562`
- `KERNEL32!CreateSemaphoreExW` at `0x140009494`
- `KERNEL32!CreateSemaphoreExW` at `0x140009530`
- `KERNEL32!CreateSemaphoreExW` at `0x140009494`
- `KERNEL32!CreateSemaphoreExW` at `0x140009530`
- `KERNEL32!SetLastError` at `0x1400094f4`
- `KERNEL32!SetLastError` at `0x140009579`
- `KERNEL32!SetLastError` at `0x1400094f4`
- `KERNEL32!SetLastError` at `0x140009579`
- `KERNEL32!CloseHandle` at `0x1400094e3`
- `KERNEL32!CloseHandle` at `0x14000956d`
- `KERNEL32!CloseHandle` at `0x1400094e3`
- `KERNEL32!CloseHandle` at `0x14000956d`

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
0x1400093d0  mov     [rsp+arg_8], rbx
0x1400093d5  mov     [rsp+arg_10], rbp
0x1400093da  push    rsi
0x1400093db  push    rdi
0x1400093dc  push    r12
0x1400093de  push    r14
0x1400093e0  push    r15
0x1400093e2  sub     rsp, 250h
0x1400093e9  mov     rax, cs:__security_cookie
0x1400093f0  xor     rax, rsp
0x1400093f3  mov     [rsp+278h+var_38], rax
0x1400093fb  mov     rax, 0C000000000000000h
0x140009405  mov     rbp, r9
0x140009408  mov     r8, rdx
0x14000940b  mov     rdi, rcx
0x14000940e  test    rax, r9
0x140009411  jnz     loc_1400095C4
0x140009417  xor     r12d, r12d
0x14000941a  lea     rax, [rsp+278h+Name]
0x14000941f  mov     ecx, 7FFFFFFEh
0x140009424  mov     edx, 104h
0x140009429  lea     esi, [r12+1]
0x14000942e  test    rcx, rcx
0x140009431  jz      short loc_140009451
0x140009433  movzx   r9d, word ptr [r8]
0x140009437  test    r9w, r9w
0x14000943b  jz      short loc_140009451
0x14000943d  mov     [rax], r9w
0x140009441  add     r8, 2
0x140009445  add     rax, 2
0x140009449  sub     rcx, rsi
0x14000944c  sub     rdx, rsi; unsigned __int64
0x14000944f  jnz     short loc_14000942E
0x140009451  test    rdx, rdx
0x140009454  lea     rcx, [rax-2]
0x140009458  lea     r8, aP0; "_p0"
0x14000945f  cmovnz  rcx, rax
0x140009463  mov     [rcx], r12w
0x140009467  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000946c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009471  mov     edx, ebp
0x140009473  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000947b  and     edx, 7FFFFFFFh; lInitialCount
0x140009481  mov     [rsp+278h+dwFlags], r12d; int
0x140009486  mov     r8d, esi
0x140009489  lea     r9, [rsp+278h+Name]; lpName
0x14000948e  cmova   r8d, edx; lMaximumCount
0x140009492  xor     ecx, ecx; lpSemaphoreAttributes
0x140009494  call    cs:__imp_CreateSemaphoreExW
0x14000949a  mov     r15, rax
0x14000949d  test    rax, rax
0x1400094a0  jnz     short loc_1400094C9
0x1400094a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400094a7  mov     ebx, eax
0x1400094a9  test    eax, eax
0x1400094ab  jns     short loc_1400094FD
0x1400094ad  mov     edx, 8Bh; void *
0x1400094b2  mov     rcx, [rsp+278h]; this
0x1400094ba  mov     r9d, ebx; char *
0x1400094bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400094c2  mov     eax, ebx
0x1400094c4  jmp     loc_140009585
0x1400094c9  call    cs:__imp_GetLastError
0x1400094cf  mov     rbx, [rdi]
0x1400094d2  test    rbx, rbx
0x1400094d5  jz      short loc_1400094FA
0x1400094d7  call    cs:__imp_GetLastError
0x1400094dd  mov     rcx, rbx; hObject
0x1400094e0  mov     r14d, eax
0x1400094e3  call    cs:__imp_CloseHandle
0x1400094e9  test    eax, eax
0x1400094eb  jz      loc_1400095CA
0x1400094f1  mov     ecx, r14d; dwErrCode
0x1400094f4  call    cs:__imp_SetLastError
0x1400094fa  mov     [rdi], r15
0x1400094fd  lea     r8, asc_140013628; "h"
0x140009504  shr     rbp, 1Fh
0x140009508  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x14000950d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009512  test    ebp, ebp
0x140009514  mov     [rsp+278h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000951c  lea     r9, [rsp+278h+Name]; lpName
0x140009521  mov     [rsp+278h+dwFlags], r12d; dwFlags
0x140009526  cmovnz  esi, ebp
0x140009529  mov     edx, ebp; lInitialCount
0x14000952b  mov     r8d, esi; lMaximumCount
0x14000952e  xor     ecx, ecx; lpSemaphoreAttributes
0x140009530  call    cs:__imp_CreateSemaphoreExW
0x140009536  mov     rsi, rax
0x140009539  test    rax, rax
0x14000953c  jnz     short loc_140009553
0x14000953e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009543  mov     ebx, eax
0x140009545  test    eax, eax
0x140009547  jns     short loc_140009583
0x140009549  mov     edx, 90h
0x14000954e  jmp     loc_1400094B2
0x140009553  call    cs:__imp_GetLastError
0x140009559  mov     rbx, [rdi+8]
0x14000955d  test    rbx, rbx
0x140009560  jz      short loc_14000957F
0x140009562  call    cs:__imp_GetLastError
0x140009568  mov     rcx, rbx; hObject
0x14000956b  mov     ebp, eax
0x14000956d  call    cs:__imp_CloseHandle
0x140009573  test    eax, eax
0x140009575  jz      short loc_1400095B1
0x140009577  mov     ecx, ebp; dwErrCode
0x140009579  call    cs:__imp_SetLastError
0x14000957f  mov     [rdi+8], rsi
0x140009583  xor     eax, eax
0x140009585  mov     rcx, [rsp+278h+var_38]
0x14000958d  xor     rcx, rsp; StackCookie
0x140009590  call    __security_check_cookie
0x140009595  lea     r11, [rsp+278h+var_28]
0x14000959d  mov     rbx, [r11+38h]
0x1400095a1  mov     rbp, [r11+40h]
0x1400095a5  mov     rsp, r11
0x1400095a8  pop     r15
0x1400095aa  pop     r14
0x1400095ac  pop     r12
0x1400095ae  pop     rdi
0x1400095af  pop     rsi
0x1400095b0  retn
0x1400095b1  mov     rcx, [rsp+278h]; this
0x1400095b9  mov     edx, 0A0Bh; void *
0x1400095be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400095c4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400095ca  mov     rcx, [rsp+278h]; this
0x1400095d2  mov     edx, 0A0Bh; void *
0x1400095d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
