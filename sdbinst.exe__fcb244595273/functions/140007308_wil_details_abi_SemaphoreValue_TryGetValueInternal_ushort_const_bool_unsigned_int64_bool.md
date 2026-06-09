# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007308`
- end: `0x1400075a0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003410`

## callees

- `0x140004b1c`
- `0x140006824`
- `0x140006844`
- `0x140006f60`
- `0x140007308`
- `0x140007d64`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400074ee`
- `KERNEL32!GetLastError` at `0x1400074ee`
- `KERNEL32!OpenSemaphoreW` at `0x14000739f`
- `KERNEL32!OpenSemaphoreW` at `0x140007421`
- `KERNEL32!OpenSemaphoreW` at `0x14000739f`
- `KERNEL32!OpenSemaphoreW` at `0x140007421`
- `KERNEL32!CloseHandle` at `0x1400073ec`
- `KERNEL32!CloseHandle` at `0x140007464`
- `KERNEL32!CloseHandle` at `0x140007475`
- `KERNEL32!CloseHandle` at `0x14000748d`
- `KERNEL32!CloseHandle` at `0x1400074b2`
- `KERNEL32!CloseHandle` at `0x1400074df`
- `KERNEL32!CloseHandle` at `0x1400073ec`
- `KERNEL32!CloseHandle` at `0x140007464`
- `KERNEL32!CloseHandle` at `0x140007475`
- `KERNEL32!CloseHandle` at `0x14000748d`
- `KERNEL32!CloseHandle` at `0x1400074b2`
- `KERNEL32!CloseHandle` at `0x1400074df`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x140007308  push    rbp
0x14000730a  push    rbx
0x14000730b  push    rsi
0x14000730c  push    rdi
0x14000730d  push    r14
0x14000730f  push    r15
0x140007311  lea     rbp, [rsp-158h]
0x140007319  sub     rsp, 258h
0x140007320  mov     rax, cs:__security_cookie
0x140007327  xor     rax, rsp
0x14000732a  mov     [rbp+180h+var_40], rax
0x140007331  xor     r15d, r15d
0x140007334  lea     rax, [rsp+280h+Name]
0x140007339  mov     esi, 104h
0x14000733e  mov     [r8], r15
0x140007341  mov     edx, esi
0x140007343  mov     r14, r8
0x140007346  mov     r9d, 7FFFFFFEh
0x14000734c  test    r9, r9
0x14000734f  jz      short loc_140007370
0x140007351  movzx   r8d, word ptr [rcx]
0x140007355  test    r8w, r8w
0x140007359  jz      short loc_140007370
0x14000735b  mov     [rax], r8w
0x14000735f  add     rcx, 2
0x140007363  add     rax, 2
0x140007367  dec     r9
0x14000736a  sub     rdx, 1
0x14000736e  jnz     short loc_14000734C
0x140007370  test    rdx, rdx
0x140007373  lea     rcx, [rax-2]
0x140007377  lea     r8, aP0; "_p0"
0x14000737e  mov     rdx, rsi; unsigned __int64
0x140007381  cmovnz  rcx, rax
0x140007385  mov     [rcx], r15w
0x140007389  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000738e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007393  lea     r8, [rsp+280h+Name]; lpName
0x140007398  xor     edx, edx; bInheritHandle
0x14000739a  mov     ecx, 1F0003h; dwDesiredAccess
0x14000739f  call    cs:__imp_OpenSemaphoreW
0x1400073a5  mov     rbx, rax
0x1400073a8  test    rax, rax
0x1400073ab  jz      loc_1400074EE
0x1400073b1  lea     rdx, [rsp+280h+var_25C]; int *
0x1400073b6  mov     [rsp+280h+var_25C], r15d
0x1400073bb  mov     rcx, rax; hHandle
0x1400073be  mov     [rsp+280h+var_260], r15d; int
0x1400073c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400073c8  mov     edi, eax
0x1400073ca  test    eax, eax
0x1400073cc  jns     short loc_140007401
0x1400073ce  mov     rcx, [rbp+188h]; this
0x1400073d5  lea     r8, aWil; "wil"
0x1400073dc  mov     r9d, eax; char *
0x1400073df  mov     edx, 0D6h; void *
0x1400073e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400073e9  mov     rcx, rbx; hObject
0x1400073ec  call    cs:__imp_CloseHandle
0x1400073f2  test    eax, eax
0x1400073f4  jz      loc_14000756A
0x1400073fa  mov     eax, edi
0x1400073fc  jmp     loc_140007515
0x140007401  lea     r8, asc_1400329A0; "h"
0x140007408  mov     rdx, rsi; unsigned __int64
0x14000740b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007410  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007415  lea     r8, [rsp+280h+Name]; lpName
0x14000741a  xor     edx, edx; bInheritHandle
0x14000741c  mov     ecx, 1F0003h; dwDesiredAccess
0x140007421  call    cs:__imp_OpenSemaphoreW
0x140007427  mov     rdi, rax
0x14000742a  test    rax, rax
0x14000742d  jz      loc_1400074C2
0x140007433  lea     rdx, [rsp+280h+var_260]; int *
0x140007438  mov     rcx, rax; hHandle
0x14000743b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140007440  mov     esi, eax
0x140007442  test    eax, eax
0x140007444  jns     short loc_14000748A
0x140007446  mov     rcx, [rbp+188h]; this
0x14000744d  lea     r8, aWil; "wil"
0x140007454  mov     r9d, eax; char *
0x140007457  mov     edx, 0DEh; void *
0x14000745c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007461  mov     rcx, rdi; hObject
0x140007464  call    cs:__imp_CloseHandle
0x14000746a  test    eax, eax
0x14000746c  jz      loc_14000757C
0x140007472  mov     rcx, rbx; hObject
0x140007475  call    cs:__imp_CloseHandle
0x14000747b  test    eax, eax
0x14000747d  jz      loc_14000758E
0x140007483  mov     eax, esi
0x140007485  jmp     loc_140007515
0x14000748a  mov     rcx, rdi; hObject
0x14000748d  call    cs:__imp_CloseHandle
0x140007493  test    eax, eax
0x140007495  jz      loc_140007534
0x14000749b  movsxd  rax, [rsp+280h+var_25C]
0x1400074a0  movsxd  rcx, [rsp+280h+var_260]
0x1400074a5  shl     rcx, 1Fh
0x1400074a9  or      rcx, rax
0x1400074ac  mov     [r14], rcx
0x1400074af  mov     rcx, rbx; hObject
0x1400074b2  call    cs:__imp_CloseHandle
0x1400074b8  test    eax, eax
0x1400074ba  jz      loc_140007546
0x1400074c0  jmp     short loc_1400074F9
0x1400074c2  mov     rcx, [rbp+188h]; this
0x1400074c9  lea     r8, aWil; "wil"
0x1400074d0  mov     edx, 0DCh; void *
0x1400074d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400074da  mov     rcx, rbx; hObject
0x1400074dd  mov     edi, eax
0x1400074df  call    cs:__imp_CloseHandle
0x1400074e5  test    eax, eax
0x1400074e7  jz      short loc_140007558
0x1400074e9  jmp     loc_1400073FA
0x1400074ee  call    cs:__imp_GetLastError
0x1400074f4  cmp     eax, 2
0x1400074f7  jnz     short loc_1400074FD
0x1400074f9  xor     eax, eax
0x1400074fb  jmp     short loc_140007515
0x1400074fd  mov     rcx, [rbp+188h]; this
0x140007504  lea     r8, aWil; "wil"
0x14000750b  mov     edx, 0D0h; void *
0x140007510  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007515  mov     rcx, [rbp+180h+var_40]
0x14000751c  xor     rcx, rsp; StackCookie
0x14000751f  call    __security_check_cookie
0x140007524  add     rsp, 258h
0x14000752b  pop     r15
0x14000752d  pop     r14
0x14000752f  pop     rdi
0x140007530  pop     rsi
0x140007531  pop     rbx
0x140007532  pop     rbp
0x140007533  retn
0x140007534  mov     rcx, [rbp+188h]; this
0x14000753b  mov     edx, 0A0Bh; void *
0x140007540  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007546  mov     rcx, [rbp+188h]; this
0x14000754d  mov     edx, 0A0Bh; void *
0x140007552  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007558  mov     rcx, [rbp+188h]; this
0x14000755f  mov     edx, 0A0Bh; void *
0x140007564  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000756a  mov     rcx, [rbp+188h]; this
0x140007571  mov     edx, 0A0Bh; void *
0x140007576  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000757c  mov     rcx, [rbp+188h]; this
0x140007583  mov     edx, 0A0Bh; void *
0x140007588  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000758e  mov     rcx, [rbp+188h]; this
0x140007595  mov     edx, 0A0Bh; void *
0x14000759a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
