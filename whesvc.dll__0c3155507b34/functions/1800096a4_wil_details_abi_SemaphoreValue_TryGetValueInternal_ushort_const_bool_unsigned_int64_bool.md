# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800096a4`
- end: `0x18000993c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007864`
- `0x18000c5c4`

## callees

- `0x1800032e0`
- `0x1800088e0`
- `0x180009024`
- `0x180009044`
- `0x180009478`
- `0x1800096a4`
- `0x180009d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000988a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000988a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000973b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097bd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000973b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800097bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000984e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000987b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000984e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000987b`

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
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
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
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
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
0x1800096a4  push    rbp
0x1800096a6  push    rbx
0x1800096a7  push    rsi
0x1800096a8  push    rdi
0x1800096a9  push    r14
0x1800096ab  push    r15
0x1800096ad  lea     rbp, [rsp-158h]
0x1800096b5  sub     rsp, 258h
0x1800096bc  mov     rax, cs:__security_cookie
0x1800096c3  xor     rax, rsp
0x1800096c6  mov     [rbp+180h+var_40], rax
0x1800096cd  xor     r15d, r15d
0x1800096d0  lea     rax, [rsp+280h+Name]
0x1800096d5  mov     esi, 104h
0x1800096da  mov     [r8], r15
0x1800096dd  mov     edx, esi
0x1800096df  mov     r14, r8
0x1800096e2  mov     r9d, 7FFFFFFEh
0x1800096e8  test    r9, r9
0x1800096eb  jz      short loc_18000970C
0x1800096ed  movzx   r8d, word ptr [rcx]
0x1800096f1  test    r8w, r8w
0x1800096f5  jz      short loc_18000970C
0x1800096f7  mov     [rax], r8w
0x1800096fb  add     rcx, 2
0x1800096ff  add     rax, 2
0x180009703  dec     r9
0x180009706  sub     rdx, 1
0x18000970a  jnz     short loc_1800096E8
0x18000970c  test    rdx, rdx
0x18000970f  lea     rcx, [rax-2]
0x180009713  lea     r8, aP0; "_p0"
0x18000971a  mov     rdx, rsi; unsigned __int64
0x18000971d  cmovnz  rcx, rax
0x180009721  mov     [rcx], r15w
0x180009725  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000972a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000972f  lea     r8, [rsp+280h+Name]; lpName
0x180009734  xor     edx, edx; bInheritHandle
0x180009736  mov     ecx, 1F0003h; dwDesiredAccess
0x18000973b  call    cs:__imp_OpenSemaphoreW
0x180009741  mov     rbx, rax
0x180009744  test    rax, rax
0x180009747  jz      loc_18000988A
0x18000974d  lea     rdx, [rsp+280h+var_25C]; int *
0x180009752  mov     [rsp+280h+var_25C], r15d
0x180009757  mov     rcx, rax; hHandle
0x18000975a  mov     [rsp+280h+var_260], r15d; int
0x18000975f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009764  mov     edi, eax
0x180009766  test    eax, eax
0x180009768  jns     short loc_18000979D
0x18000976a  mov     rcx, [rbp+188h]; this
0x180009771  lea     r8, aWil; "wil"
0x180009778  mov     r9d, eax; char *
0x18000977b  mov     edx, 0D6h; void *
0x180009780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009785  mov     rcx, rbx; hObject
0x180009788  call    cs:__imp_CloseHandle
0x18000978e  test    eax, eax
0x180009790  jz      loc_180009906
0x180009796  mov     eax, edi
0x180009798  jmp     loc_1800098B1
0x18000979d  lea     r8, asc_18002B510; "h"
0x1800097a4  mov     rdx, rsi; unsigned __int64
0x1800097a7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800097ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800097b1  lea     r8, [rsp+280h+Name]; lpName
0x1800097b6  xor     edx, edx; bInheritHandle
0x1800097b8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800097bd  call    cs:__imp_OpenSemaphoreW
0x1800097c3  mov     rdi, rax
0x1800097c6  test    rax, rax
0x1800097c9  jz      loc_18000985E
0x1800097cf  lea     rdx, [rsp+280h+var_260]; int *
0x1800097d4  mov     rcx, rax; hHandle
0x1800097d7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800097dc  mov     esi, eax
0x1800097de  test    eax, eax
0x1800097e0  jns     short loc_180009826
0x1800097e2  mov     rcx, [rbp+188h]; this
0x1800097e9  lea     r8, aWil; "wil"
0x1800097f0  mov     r9d, eax; char *
0x1800097f3  mov     edx, 0DEh; void *
0x1800097f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097fd  mov     rcx, rdi; hObject
0x180009800  call    cs:__imp_CloseHandle
0x180009806  test    eax, eax
0x180009808  jz      loc_180009918
0x18000980e  mov     rcx, rbx; hObject
0x180009811  call    cs:__imp_CloseHandle
0x180009817  test    eax, eax
0x180009819  jz      loc_18000992A
0x18000981f  mov     eax, esi
0x180009821  jmp     loc_1800098B1
0x180009826  mov     rcx, rdi; hObject
0x180009829  call    cs:__imp_CloseHandle
0x18000982f  test    eax, eax
0x180009831  jz      loc_1800098D0
0x180009837  movsxd  rax, [rsp+280h+var_25C]
0x18000983c  movsxd  rcx, [rsp+280h+var_260]
0x180009841  shl     rcx, 1Fh
0x180009845  or      rcx, rax
0x180009848  mov     [r14], rcx
0x18000984b  mov     rcx, rbx; hObject
0x18000984e  call    cs:__imp_CloseHandle
0x180009854  test    eax, eax
0x180009856  jz      loc_1800098E2
0x18000985c  jmp     short loc_180009895
0x18000985e  mov     rcx, [rbp+188h]; this
0x180009865  lea     r8, aWil; "wil"
0x18000986c  mov     edx, 0DCh; void *
0x180009871  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009876  mov     rcx, rbx; hObject
0x180009879  mov     edi, eax
0x18000987b  call    cs:__imp_CloseHandle
0x180009881  test    eax, eax
0x180009883  jz      short loc_1800098F4
0x180009885  jmp     loc_180009796
0x18000988a  call    cs:__imp_GetLastError
0x180009890  cmp     eax, 2
0x180009893  jnz     short loc_180009899
0x180009895  xor     eax, eax
0x180009897  jmp     short loc_1800098B1
0x180009899  mov     rcx, [rbp+188h]; this
0x1800098a0  lea     r8, aWil; "wil"
0x1800098a7  mov     edx, 0D0h; void *
0x1800098ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800098b1  mov     rcx, [rbp+180h+var_40]
0x1800098b8  xor     rcx, rsp; StackCookie
0x1800098bb  call    __security_check_cookie
0x1800098c0  add     rsp, 258h
0x1800098c7  pop     r15
0x1800098c9  pop     r14
0x1800098cb  pop     rdi
0x1800098cc  pop     rsi
0x1800098cd  pop     rbx
0x1800098ce  pop     rbp
0x1800098cf  retn
0x1800098d0  mov     rcx, [rbp+188h]; this
0x1800098d7  mov     edx, 0A0Bh; void *
0x1800098dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098e2  mov     rcx, [rbp+188h]; this
0x1800098e9  mov     edx, 0A0Bh; void *
0x1800098ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800098f4  mov     rcx, [rbp+188h]; this
0x1800098fb  mov     edx, 0A0Bh; void *
0x180009900  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009906  mov     rcx, [rbp+188h]; this
0x18000990d  mov     edx, 0A0Bh; void *
0x180009912  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009918  mov     rcx, [rbp+188h]; this
0x18000991f  mov     edx, 0A0Bh; void *
0x180009924  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000992a  mov     rcx, [rbp+188h]; this
0x180009931  mov     edx, 0A0Bh; void *
0x180009936  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
