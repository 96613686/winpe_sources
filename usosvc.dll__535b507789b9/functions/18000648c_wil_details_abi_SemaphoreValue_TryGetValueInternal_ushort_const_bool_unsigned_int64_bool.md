# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000648c`
- end: `0x18000671b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003f78`
- `0x18000b35c`

## callees

- `0x1800026d0`
- `0x180004fb4`
- `0x1800059a4`
- `0x1800059c4`
- `0x180006304`
- `0x18000648c`
- `0x18000687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000659c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006520`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000659c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006669`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000656d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000662d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000665a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000656d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000662d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000665a`

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
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000648c  push    rbp
0x18000648e  push    rbx
0x18000648f  push    rsi
0x180006490  push    rdi
0x180006491  push    r14
0x180006493  push    r15
0x180006495  lea     rbp, [rsp-158h]
0x18000649d  sub     rsp, 258h
0x1800064a4  mov     rax, cs:__security_cookie
0x1800064ab  xor     rax, rsp
0x1800064ae  mov     [rbp+180h+var_40], rax
0x1800064b5  xor     r15d, r15d
0x1800064b8  lea     rax, [rsp+280h+Name]
0x1800064bd  mov     [r8], r15
0x1800064c0  mov     r14, r8
0x1800064c3  mov     edx, 104h
0x1800064c8  mov     r9d, 7FFFFFFEh
0x1800064ce  test    r9, r9
0x1800064d1  jz      short loc_1800064F2
0x1800064d3  movzx   r8d, word ptr [rcx]
0x1800064d7  test    r8w, r8w
0x1800064db  jz      short loc_1800064F2
0x1800064dd  mov     [rax], r8w
0x1800064e1  add     rcx, 2
0x1800064e5  add     rax, 2
0x1800064e9  dec     r9
0x1800064ec  sub     rdx, 1; unsigned __int64
0x1800064f0  jnz     short loc_1800064CE
0x1800064f2  test    rdx, rdx
0x1800064f5  lea     rcx, [rax-2]
0x1800064f9  lea     r8, aP0; "_p0"
0x180006500  cmovnz  rcx, rax
0x180006504  mov     [rcx], r15w
0x180006508  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000650d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006512  mov     esi, 1F0003h
0x180006517  lea     r8, [rsp+280h+Name]; lpName
0x18000651c  mov     ecx, esi; dwDesiredAccess
0x18000651e  xor     edx, edx; bInheritHandle
0x180006520  call    cs:__imp_OpenSemaphoreW
0x180006526  mov     rbx, rax
0x180006529  test    rax, rax
0x18000652c  jz      loc_180006669
0x180006532  lea     rdx, [rsp+280h+var_25C]; int *
0x180006537  mov     [rsp+280h+var_25C], r15d
0x18000653c  mov     rcx, rax; hHandle
0x18000653f  mov     [rsp+280h+var_260], r15d; int
0x180006544  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006549  mov     edi, eax
0x18000654b  test    eax, eax
0x18000654d  jns     short loc_180006582
0x18000654f  mov     rcx, [rbp+188h]; this
0x180006556  lea     r8, aWil; "wil"
0x18000655d  mov     r9d, eax; char *
0x180006560  mov     edx, 0D6h; void *
0x180006565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000656a  mov     rcx, rbx; hObject
0x18000656d  call    cs:__imp_CloseHandle
0x180006573  test    eax, eax
0x180006575  jz      loc_1800066E5
0x18000657b  mov     eax, edi
0x18000657d  jmp     loc_180006690
0x180006582  lea     r8, asc_180010D68; "h"
0x180006589  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000658e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006593  lea     r8, [rsp+280h+Name]; lpName
0x180006598  xor     edx, edx; bInheritHandle
0x18000659a  mov     ecx, esi; dwDesiredAccess
0x18000659c  call    cs:__imp_OpenSemaphoreW
0x1800065a2  mov     rdi, rax
0x1800065a5  test    rax, rax
0x1800065a8  jz      loc_18000663D
0x1800065ae  lea     rdx, [rsp+280h+var_260]; int *
0x1800065b3  mov     rcx, rax; hHandle
0x1800065b6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800065bb  mov     esi, eax
0x1800065bd  test    eax, eax
0x1800065bf  jns     short loc_180006605
0x1800065c1  mov     rcx, [rbp+188h]; this
0x1800065c8  lea     r8, aWil; "wil"
0x1800065cf  mov     r9d, eax; char *
0x1800065d2  mov     edx, 0DEh; void *
0x1800065d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065dc  mov     rcx, rdi; hObject
0x1800065df  call    cs:__imp_CloseHandle
0x1800065e5  test    eax, eax
0x1800065e7  jz      loc_1800066F7
0x1800065ed  mov     rcx, rbx; hObject
0x1800065f0  call    cs:__imp_CloseHandle
0x1800065f6  test    eax, eax
0x1800065f8  jz      loc_180006709
0x1800065fe  mov     eax, esi
0x180006600  jmp     loc_180006690
0x180006605  mov     rcx, rdi; hObject
0x180006608  call    cs:__imp_CloseHandle
0x18000660e  test    eax, eax
0x180006610  jz      loc_1800066AF
0x180006616  movsxd  rax, [rsp+280h+var_25C]
0x18000661b  movsxd  rcx, [rsp+280h+var_260]
0x180006620  shl     rcx, 1Fh
0x180006624  or      rcx, rax
0x180006627  mov     [r14], rcx
0x18000662a  mov     rcx, rbx; hObject
0x18000662d  call    cs:__imp_CloseHandle
0x180006633  test    eax, eax
0x180006635  jz      loc_1800066C1
0x18000663b  jmp     short loc_180006674
0x18000663d  mov     rcx, [rbp+188h]; this
0x180006644  lea     r8, aWil; "wil"
0x18000664b  mov     edx, 0DCh; void *
0x180006650  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006655  mov     rcx, rbx; hObject
0x180006658  mov     edi, eax
0x18000665a  call    cs:__imp_CloseHandle
0x180006660  test    eax, eax
0x180006662  jz      short loc_1800066D3
0x180006664  jmp     loc_18000657B
0x180006669  call    cs:__imp_GetLastError
0x18000666f  cmp     eax, 2
0x180006672  jnz     short loc_180006678
0x180006674  xor     eax, eax
0x180006676  jmp     short loc_180006690
0x180006678  mov     rcx, [rbp+188h]; this
0x18000667f  lea     r8, aWil; "wil"
0x180006686  mov     edx, 0D0h; void *
0x18000668b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006690  mov     rcx, [rbp+180h+var_40]
0x180006697  xor     rcx, rsp; StackCookie
0x18000669a  call    __security_check_cookie
0x18000669f  add     rsp, 258h
0x1800066a6  pop     r15
0x1800066a8  pop     r14
0x1800066aa  pop     rdi
0x1800066ab  pop     rsi
0x1800066ac  pop     rbx
0x1800066ad  pop     rbp
0x1800066ae  retn
0x1800066af  mov     rcx, [rbp+188h]; this
0x1800066b6  mov     edx, 0A0Bh; void *
0x1800066bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066c1  mov     rcx, [rbp+188h]; this
0x1800066c8  mov     edx, 0A0Bh; void *
0x1800066cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066d3  mov     rcx, [rbp+188h]; this
0x1800066da  mov     edx, 0A0Bh; void *
0x1800066df  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066e5  mov     rcx, [rbp+188h]; this
0x1800066ec  mov     edx, 0A0Bh; void *
0x1800066f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800066f7  mov     rcx, [rbp+188h]; this
0x1800066fe  mov     edx, 0A0Bh; void *
0x180006703  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006709  mov     rcx, [rbp+188h]; this
0x180006710  mov     edx, 0A0Bh; void *
0x180006715  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
