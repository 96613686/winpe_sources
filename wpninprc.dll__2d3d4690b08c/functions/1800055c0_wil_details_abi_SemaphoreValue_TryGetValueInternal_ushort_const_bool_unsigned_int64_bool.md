# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800055c0`
- end: `0x18000582c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004144`

## callees

- `0x180001510`
- `0x180004be0`
- `0x1800052ac`
- `0x1800052cc`
- `0x180005510`
- `0x1800055c0`
- `0x180005920`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000572b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000569a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000572b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005781`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005654`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056c9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005654`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800056c9`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
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
0x1800055c0  push    rbp
0x1800055c2  push    rbx
0x1800055c3  push    rsi
0x1800055c4  push    rdi
0x1800055c5  push    r14
0x1800055c7  push    r15
0x1800055c9  lea     rbp, [rsp-158h]
0x1800055d1  sub     rsp, 258h
0x1800055d8  mov     rax, cs:__security_cookie
0x1800055df  xor     rax, rsp
0x1800055e2  mov     [rbp+180h+var_40], rax
0x1800055e9  xor     r15d, r15d
0x1800055ec  lea     rax, [rsp+280h+Name]
0x1800055f1  mov     [r8], r15
0x1800055f4  mov     r14, r8
0x1800055f7  mov     edx, 104h
0x1800055fc  mov     r9d, 7FFFFFFEh
0x180005602  test    r9, r9
0x180005605  jz      short loc_180005626
0x180005607  movzx   r8d, word ptr [rcx]
0x18000560b  test    r8w, r8w
0x18000560f  jz      short loc_180005626
0x180005611  mov     [rax], r8w
0x180005615  add     rcx, 2
0x180005619  add     rax, 2
0x18000561d  dec     r9
0x180005620  sub     rdx, 1; unsigned __int64
0x180005624  jnz     short loc_180005602
0x180005626  test    rdx, rdx
0x180005629  lea     rcx, [rax-2]
0x18000562d  lea     r8, aP0; "_p0"
0x180005634  cmovnz  rcx, rax
0x180005638  mov     [rcx], r15w
0x18000563c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005641  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005646  mov     esi, 1F0003h
0x18000564b  lea     r8, [rsp+280h+Name]; lpName
0x180005650  mov     ecx, esi; dwDesiredAccess
0x180005652  xor     edx, edx; bInheritHandle
0x180005654  call    cs:__imp_OpenSemaphoreW
0x18000565a  mov     rbx, rax
0x18000565d  test    rax, rax
0x180005660  jz      loc_180005781
0x180005666  lea     rdx, [rsp+280h+var_25C]; int *
0x18000566b  mov     [rsp+280h+var_25C], r15d
0x180005670  mov     rcx, rax; hHandle
0x180005673  mov     [rsp+280h+var_260], r15d; int
0x180005678  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000567d  mov     edi, eax
0x18000567f  test    eax, eax
0x180005681  jns     short loc_1800056AF
0x180005683  mov     rcx, [rbp+188h]; this
0x18000568a  mov     r9d, eax; char *
0x18000568d  mov     edx, 0D6h; void *
0x180005692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005697  mov     rcx, rbx; hObject
0x18000569a  call    cs:__imp_CloseHandle
0x1800056a0  test    eax, eax
0x1800056a2  jz      loc_1800057F6
0x1800056a8  mov     eax, edi
0x1800056aa  jmp     loc_1800057A1
0x1800056af  lea     r8, asc_180008968; "h"
0x1800056b6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800056bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800056c0  lea     r8, [rsp+280h+Name]; lpName
0x1800056c5  xor     edx, edx; bInheritHandle
0x1800056c7  mov     ecx, esi; dwDesiredAccess
0x1800056c9  call    cs:__imp_OpenSemaphoreW
0x1800056cf  mov     rdi, rax
0x1800056d2  test    rax, rax
0x1800056d5  jz      loc_18000575C
0x1800056db  lea     rdx, [rsp+280h+var_260]; int *
0x1800056e0  mov     rcx, rax; hHandle
0x1800056e3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800056e8  mov     esi, eax
0x1800056ea  test    eax, eax
0x1800056ec  jns     short loc_180005728
0x1800056ee  mov     rcx, [rbp+188h]; this
0x1800056f5  mov     r9d, eax; char *
0x1800056f8  mov     edx, 0DEh; void *
0x1800056fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005702  mov     rcx, rdi; hObject
0x180005705  call    cs:__imp_CloseHandle
0x18000570b  test    eax, eax
0x18000570d  jz      loc_180005808
0x180005713  mov     rcx, rbx; hObject
0x180005716  call    cs:__imp_CloseHandle
0x18000571c  test    eax, eax
0x18000571e  jz      loc_18000581A
0x180005724  mov     eax, esi
0x180005726  jmp     short loc_1800057A1
0x180005728  mov     rcx, rdi; hObject
0x18000572b  call    cs:__imp_CloseHandle
0x180005731  test    eax, eax
0x180005733  jz      loc_1800057C0
0x180005739  movsxd  rax, [rsp+280h+var_25C]
0x18000573e  movsxd  rcx, [rsp+280h+var_260]
0x180005743  shl     rcx, 1Fh
0x180005747  or      rcx, rax
0x18000574a  mov     [r14], rcx
0x18000574d  mov     rcx, rbx; hObject
0x180005750  call    cs:__imp_CloseHandle
0x180005756  test    eax, eax
0x180005758  jz      short loc_1800057D2
0x18000575a  jmp     short loc_18000578C
0x18000575c  mov     rcx, [rbp+188h]; this
0x180005763  mov     edx, 0DCh; void *
0x180005768  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000576d  mov     rcx, rbx; hObject
0x180005770  mov     edi, eax
0x180005772  call    cs:__imp_CloseHandle
0x180005778  test    eax, eax
0x18000577a  jz      short loc_1800057E4
0x18000577c  jmp     loc_1800056A8
0x180005781  call    cs:__imp_GetLastError
0x180005787  cmp     eax, 2
0x18000578a  jnz     short loc_180005790
0x18000578c  xor     eax, eax
0x18000578e  jmp     short loc_1800057A1
0x180005790  mov     rcx, [rbp+188h]; this
0x180005797  mov     edx, 0D0h; void *
0x18000579c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800057a1  mov     rcx, [rbp+180h+var_40]
0x1800057a8  xor     rcx, rsp; StackCookie
0x1800057ab  call    __security_check_cookie
0x1800057b0  add     rsp, 258h
0x1800057b7  pop     r15
0x1800057b9  pop     r14
0x1800057bb  pop     rdi
0x1800057bc  pop     rsi
0x1800057bd  pop     rbx
0x1800057be  pop     rbp
0x1800057bf  retn
0x1800057c0  mov     rcx, [rbp+188h]; this
0x1800057c7  mov     edx, 0A0Bh; void *
0x1800057cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057d2  mov     rcx, [rbp+188h]; this
0x1800057d9  mov     edx, 0A0Bh; void *
0x1800057de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057e4  mov     rcx, [rbp+188h]; this
0x1800057eb  mov     edx, 0A0Bh; void *
0x1800057f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800057f6  mov     rcx, [rbp+188h]; this
0x1800057fd  mov     edx, 0A0Bh; void *
0x180005802  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005808  mov     rcx, [rbp+188h]; this
0x18000580f  mov     edx, 0A0Bh; void *
0x180005814  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000581a  mov     rcx, [rbp+188h]; this
0x180005821  mov     edx, 0A0Bh; void *
0x180005826  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
