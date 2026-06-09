# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005710`
- end: `0x180005985`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000383c`
- `0x18001a148`

## callees

- `0x180004840`
- `0x180005210`
- `0x180005230`
- `0x18000554c`
- `0x180005710`
- `0x180005adc`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057a7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005822`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800057a7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000585e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000586f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005884`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000585e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000586f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005884`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cb`

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
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180005710  push    rbp
0x180005712  push    rbx
0x180005713  push    rsi
0x180005714  push    rdi
0x180005715  push    r14
0x180005717  push    r15
0x180005719  lea     rbp, [rsp-158h]
0x180005721  sub     rsp, 258h
0x180005728  mov     rax, cs:__security_cookie
0x18000572f  xor     rax, rsp
0x180005732  mov     [rbp+180h+var_40], rax
0x180005739  xor     r15d, r15d
0x18000573c  lea     rax, [rsp+280h+Name]
0x180005741  mov     esi, 104h
0x180005746  mov     [r8], r15
0x180005749  mov     edx, esi
0x18000574b  mov     r14, r8
0x18000574e  mov     r9d, 7FFFFFFEh
0x180005754  test    r9, r9
0x180005757  jz      short loc_180005778
0x180005759  movzx   r8d, word ptr [rcx]
0x18000575d  test    r8w, r8w
0x180005761  jz      short loc_180005778
0x180005763  mov     [rax], r8w
0x180005767  add     rcx, 2
0x18000576b  add     rax, 2
0x18000576f  dec     r9
0x180005772  sub     rdx, 1
0x180005776  jnz     short loc_180005754
0x180005778  test    rdx, rdx
0x18000577b  lea     rcx, [rax-2]
0x18000577f  lea     r8, aP0; "_p0"
0x180005786  mov     rdx, rsi; unsigned __int64
0x180005789  cmovnz  rcx, rax
0x18000578d  mov     [rcx], r15w
0x180005791  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005796  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000579b  lea     r8, [rsp+280h+Name]; lpName
0x1800057a0  xor     edx, edx; bInheritHandle
0x1800057a2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800057a7  call    cs:__imp_OpenSemaphoreW
0x1800057ad  mov     rbx, rax
0x1800057b0  test    rax, rax
0x1800057b3  jz      loc_1800058DA
0x1800057b9  lea     rdx, [rsp+280h+var_25C]; int *
0x1800057be  mov     [rsp+280h+var_25C], r15d
0x1800057c3  mov     rcx, rax; hHandle
0x1800057c6  mov     [rsp+280h+var_260], r15d; int
0x1800057cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800057d0  mov     edi, eax
0x1800057d2  test    eax, eax
0x1800057d4  jns     short loc_180005802
0x1800057d6  mov     rcx, [rbp+188h]; this
0x1800057dd  mov     r9d, eax; char *
0x1800057e0  mov     edx, 0D6h; void *
0x1800057e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057ea  mov     rcx, rbx; hObject
0x1800057ed  call    cs:__imp_CloseHandle
0x1800057f3  test    eax, eax
0x1800057f5  jz      loc_18000594F
0x1800057fb  mov     eax, edi
0x1800057fd  jmp     loc_1800058FA
0x180005802  lea     r8, asc_180020BC8; "h"
0x180005809  mov     rdx, rsi; unsigned __int64
0x18000580c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005811  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005816  lea     r8, [rsp+280h+Name]; lpName
0x18000581b  xor     edx, edx; bInheritHandle
0x18000581d  mov     ecx, 1F0003h; dwDesiredAccess
0x180005822  call    cs:__imp_OpenSemaphoreW
0x180005828  mov     rdi, rax
0x18000582b  test    rax, rax
0x18000582e  jz      loc_1800058B5
0x180005834  lea     rdx, [rsp+280h+var_260]; int *
0x180005839  mov     rcx, rax; hHandle
0x18000583c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005841  mov     esi, eax
0x180005843  test    eax, eax
0x180005845  jns     short loc_180005881
0x180005847  mov     rcx, [rbp+188h]; this
0x18000584e  mov     r9d, eax; char *
0x180005851  mov     edx, 0DEh; void *
0x180005856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000585b  mov     rcx, rdi; hObject
0x18000585e  call    cs:__imp_CloseHandle
0x180005864  test    eax, eax
0x180005866  jz      loc_180005961
0x18000586c  mov     rcx, rbx; hObject
0x18000586f  call    cs:__imp_CloseHandle
0x180005875  test    eax, eax
0x180005877  jz      loc_180005973
0x18000587d  mov     eax, esi
0x18000587f  jmp     short loc_1800058FA
0x180005881  mov     rcx, rdi; hObject
0x180005884  call    cs:__imp_CloseHandle
0x18000588a  test    eax, eax
0x18000588c  jz      loc_180005919
0x180005892  movsxd  rax, [rsp+280h+var_25C]
0x180005897  movsxd  rcx, [rsp+280h+var_260]
0x18000589c  shl     rcx, 1Fh
0x1800058a0  or      rcx, rax
0x1800058a3  mov     [r14], rcx
0x1800058a6  mov     rcx, rbx; hObject
0x1800058a9  call    cs:__imp_CloseHandle
0x1800058af  test    eax, eax
0x1800058b1  jz      short loc_18000592B
0x1800058b3  jmp     short loc_1800058E5
0x1800058b5  mov     rcx, [rbp+188h]; this
0x1800058bc  mov     edx, 0DCh; void *
0x1800058c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800058c6  mov     rcx, rbx; hObject
0x1800058c9  mov     edi, eax
0x1800058cb  call    cs:__imp_CloseHandle
0x1800058d1  test    eax, eax
0x1800058d3  jz      short loc_18000593D
0x1800058d5  jmp     loc_1800057FB
0x1800058da  call    cs:__imp_GetLastError
0x1800058e0  cmp     eax, 2
0x1800058e3  jnz     short loc_1800058E9
0x1800058e5  xor     eax, eax
0x1800058e7  jmp     short loc_1800058FA
0x1800058e9  mov     rcx, [rbp+188h]; this
0x1800058f0  mov     edx, 0D0h; void *
0x1800058f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800058fa  mov     rcx, [rbp+180h+var_40]
0x180005901  xor     rcx, rsp; StackCookie
0x180005904  call    __security_check_cookie
0x180005909  add     rsp, 258h
0x180005910  pop     r15
0x180005912  pop     r14
0x180005914  pop     rdi
0x180005915  pop     rsi
0x180005916  pop     rbx
0x180005917  pop     rbp
0x180005918  retn
0x180005919  mov     rcx, [rbp+188h]; this
0x180005920  mov     edx, 0A0Bh; void *
0x180005925  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000592b  mov     rcx, [rbp+188h]; this
0x180005932  mov     edx, 0A0Bh; void *
0x180005937  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000593d  mov     rcx, [rbp+188h]; this
0x180005944  mov     edx, 0A0Bh; void *
0x180005949  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000594f  mov     rcx, [rbp+188h]; this
0x180005956  mov     edx, 0A0Bh; void *
0x18000595b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005961  mov     rcx, [rbp+188h]; this
0x180005968  mov     edx, 0A0Bh; void *
0x18000596d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005973  mov     rcx, [rbp+188h]; this
0x18000597a  mov     edx, 0A0Bh; void *
0x18000597f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
