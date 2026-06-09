# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000555c`
- end: `0x1800057c8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800036bc`

## callees

- `0x180004620`
- `0x180005074`
- `0x180005094`
- `0x1800053ac`
- `0x18000555c`
- `0x180005934`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005665`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800055f0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000571d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000571d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000570e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000555c  push    rbp
0x18000555e  push    rbx
0x18000555f  push    rsi
0x180005560  push    rdi
0x180005561  push    r14
0x180005563  push    r15
0x180005565  lea     rbp, [rsp-158h]
0x18000556d  sub     rsp, 258h
0x180005574  mov     rax, cs:__security_cookie
0x18000557b  xor     rax, rsp
0x18000557e  mov     [rbp+180h+var_40], rax
0x180005585  xor     r15d, r15d
0x180005588  lea     rax, [rsp+280h+Name]
0x18000558d  mov     [r8], r15
0x180005590  mov     r14, r8
0x180005593  mov     edx, 104h
0x180005598  mov     r9d, 7FFFFFFEh
0x18000559e  test    r9, r9
0x1800055a1  jz      short loc_1800055C2
0x1800055a3  movzx   r8d, word ptr [rcx]
0x1800055a7  test    r8w, r8w
0x1800055ab  jz      short loc_1800055C2
0x1800055ad  mov     [rax], r8w
0x1800055b1  add     rcx, 2
0x1800055b5  add     rax, 2
0x1800055b9  dec     r9
0x1800055bc  sub     rdx, 1; unsigned __int64
0x1800055c0  jnz     short loc_18000559E
0x1800055c2  test    rdx, rdx
0x1800055c5  lea     rcx, [rax-2]
0x1800055c9  lea     r8, aP0; "_p0"
0x1800055d0  cmovnz  rcx, rax
0x1800055d4  mov     [rcx], r15w
0x1800055d8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800055dd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800055e2  mov     esi, 1F0003h
0x1800055e7  lea     r8, [rsp+280h+Name]; lpName
0x1800055ec  mov     ecx, esi; dwDesiredAccess
0x1800055ee  xor     edx, edx; bInheritHandle
0x1800055f0  call    cs:__imp_OpenSemaphoreW
0x1800055f6  mov     rbx, rax
0x1800055f9  test    rax, rax
0x1800055fc  jz      loc_18000571D
0x180005602  lea     rdx, [rsp+280h+var_25C]; int *
0x180005607  mov     [rsp+280h+var_25C], r15d
0x18000560c  mov     rcx, rax; hHandle
0x18000560f  mov     [rsp+280h+var_260], r15d; int
0x180005614  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005619  mov     edi, eax
0x18000561b  test    eax, eax
0x18000561d  jns     short loc_18000564B
0x18000561f  mov     rcx, [rbp+188h]; this
0x180005626  mov     r9d, eax; char *
0x180005629  mov     edx, 0D6h; void *
0x18000562e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005633  mov     rcx, rbx; hObject
0x180005636  call    cs:__imp_CloseHandle
0x18000563c  test    eax, eax
0x18000563e  jz      loc_180005792
0x180005644  mov     eax, edi
0x180005646  jmp     loc_18000573D
0x18000564b  lea     r8, asc_18001F838; "h"
0x180005652  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005657  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000565c  lea     r8, [rsp+280h+Name]; lpName
0x180005661  xor     edx, edx; bInheritHandle
0x180005663  mov     ecx, esi; dwDesiredAccess
0x180005665  call    cs:__imp_OpenSemaphoreW
0x18000566b  mov     rdi, rax
0x18000566e  test    rax, rax
0x180005671  jz      loc_1800056F8
0x180005677  lea     rdx, [rsp+280h+var_260]; int *
0x18000567c  mov     rcx, rax; hHandle
0x18000567f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005684  mov     esi, eax
0x180005686  test    eax, eax
0x180005688  jns     short loc_1800056C4
0x18000568a  mov     rcx, [rbp+188h]; this
0x180005691  mov     r9d, eax; char *
0x180005694  mov     edx, 0DEh; void *
0x180005699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000569e  mov     rcx, rdi; hObject
0x1800056a1  call    cs:__imp_CloseHandle
0x1800056a7  test    eax, eax
0x1800056a9  jz      loc_1800057A4
0x1800056af  mov     rcx, rbx; hObject
0x1800056b2  call    cs:__imp_CloseHandle
0x1800056b8  test    eax, eax
0x1800056ba  jz      loc_1800057B6
0x1800056c0  mov     eax, esi
0x1800056c2  jmp     short loc_18000573D
0x1800056c4  mov     rcx, rdi; hObject
0x1800056c7  call    cs:__imp_CloseHandle
0x1800056cd  test    eax, eax
0x1800056cf  jz      loc_18000575C
0x1800056d5  movsxd  rax, [rsp+280h+var_25C]
0x1800056da  movsxd  rcx, [rsp+280h+var_260]
0x1800056df  shl     rcx, 1Fh
0x1800056e3  or      rcx, rax
0x1800056e6  mov     [r14], rcx
0x1800056e9  mov     rcx, rbx; hObject
0x1800056ec  call    cs:__imp_CloseHandle
0x1800056f2  test    eax, eax
0x1800056f4  jz      short loc_18000576E
0x1800056f6  jmp     short loc_180005728
0x1800056f8  mov     rcx, [rbp+188h]; this
0x1800056ff  mov     edx, 0DCh; void *
0x180005704  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005709  mov     rcx, rbx; hObject
0x18000570c  mov     edi, eax
0x18000570e  call    cs:__imp_CloseHandle
0x180005714  test    eax, eax
0x180005716  jz      short loc_180005780
0x180005718  jmp     loc_180005644
0x18000571d  call    cs:__imp_GetLastError
0x180005723  cmp     eax, 2
0x180005726  jnz     short loc_18000572C
0x180005728  xor     eax, eax
0x18000572a  jmp     short loc_18000573D
0x18000572c  mov     rcx, [rbp+188h]; this
0x180005733  mov     edx, 0D0h; void *
0x180005738  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000573d  mov     rcx, [rbp+180h+var_40]
0x180005744  xor     rcx, rsp; StackCookie
0x180005747  call    __security_check_cookie
0x18000574c  add     rsp, 258h
0x180005753  pop     r15
0x180005755  pop     r14
0x180005757  pop     rdi
0x180005758  pop     rsi
0x180005759  pop     rbx
0x18000575a  pop     rbp
0x18000575b  retn
0x18000575c  mov     rcx, [rbp+188h]; this
0x180005763  mov     edx, 0A0Bh; void *
0x180005768  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000576e  mov     rcx, [rbp+188h]; this
0x180005775  mov     edx, 0A0Bh; void *
0x18000577a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005780  mov     rcx, [rbp+188h]; this
0x180005787  mov     edx, 0A0Bh; void *
0x18000578c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005792  mov     rcx, [rbp+188h]; this
0x180005799  mov     edx, 0A0Bh; void *
0x18000579e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057a4  mov     rcx, [rbp+188h]; this
0x1800057ab  mov     edx, 0A0Bh; void *
0x1800057b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057b6  mov     rcx, [rbp+188h]; this
0x1800057bd  mov     edx, 0A0Bh; void *
0x1800057c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
