# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e098`
- end: `0x18000e353`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `699`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009b78`
- `0x180009f58`

## callees

- `0x18000b92c`
- `0x18000d95c`
- `0x18000d97c`
- `0x18000dccc`
- `0x18000e098`
- `0x18000f210`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e12c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e1a9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e12c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e277`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e23b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e216`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e23b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e268`

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
  HANDLE v17; // rax
  unsigned int v18; // r8d
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // esi
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  unsigned int v28; // r8d
  wil::details *v29; // [rsp+20h] [rbp-E0h]
  wil::details *v30; // [rsp+20h] [rbp-E0h]
  wil::details *v31; // [rsp+20h] [rbp-E0h]
  wil::details *v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+28h] [rbp-D8h]
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+298h] [rbp+198h]

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
      return wil::details::in1diag4::Return_GetLastError(
               retaddr,
               (void *)0xD0,
               v28,
               "wil::details_abi::SemaphoreValue::TryGetValueInternal",
               (const char *)v29);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    LODWORD(v29) = ValueFromSemaphore;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0xD6,
      v13,
      "wil::details_abi::SemaphoreValue::TryGetValueInternal",
      v29,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v15,
        "wil::details::CloseHandle",
        (const char *)v30);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag4::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  v18,
                  "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                  (const char *)v29);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v27,
        "wil::details::CloseHandle",
        (const char *)v32);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v34);
  v22 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v25,
        "wil::details::CloseHandle",
        (const char *)v29);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v26,
        "wil::details::CloseHandle",
        (const char *)v29);
    return 0;
  }
  LODWORD(v29) = v20;
  wil::details::in1diag4::Return_Hr(
    retaddr,
    (void *)0xDE,
    v21,
    "wil::details_abi::SemaphoreValue::TryGetValueInternal",
    v29,
    v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v23,
      "wil::details::CloseHandle",
      (const char *)v31);
  if ( !CloseHandle(v10) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v24,
      "wil::details::CloseHandle",
      (const char *)v31);
  return v22;
}

```

## disassembly

```asm
0x18000e098  push    rbp
0x18000e09a  push    rbx
0x18000e09b  push    rsi
0x18000e09c  push    rdi
0x18000e09d  push    r14
0x18000e09f  push    r15
0x18000e0a1  lea     rbp, [rsp-168h]
0x18000e0a9  sub     rsp, 268h
0x18000e0b0  mov     rax, cs:__security_cookie
0x18000e0b7  xor     rax, rsp
0x18000e0ba  mov     [rbp+190h+var_40], rax
0x18000e0c1  xor     r15d, r15d
0x18000e0c4  lea     rax, [rsp+290h+Name]
0x18000e0c9  mov     [r8], r15
0x18000e0cc  mov     r14, r8
0x18000e0cf  mov     edx, 104h
0x18000e0d4  mov     r9d, 7FFFFFFEh
0x18000e0da  test    r9, r9
0x18000e0dd  jz      short loc_18000E0FE
0x18000e0df  movzx   r8d, word ptr [rcx]
0x18000e0e3  test    r8w, r8w
0x18000e0e7  jz      short loc_18000E0FE
0x18000e0e9  mov     [rax], r8w
0x18000e0ed  add     rcx, 2
0x18000e0f1  add     rax, 2
0x18000e0f5  dec     r9
0x18000e0f8  sub     rdx, 1; unsigned __int64
0x18000e0fc  jnz     short loc_18000E0DA
0x18000e0fe  test    rdx, rdx
0x18000e101  lea     rcx, [rax-2]
0x18000e105  lea     r8, aP0; "_p0"
0x18000e10c  cmovnz  rcx, rax
0x18000e110  mov     [rcx], r15w
0x18000e114  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000e119  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e11e  mov     esi, 1F0003h
0x18000e123  lea     r8, [rsp+290h+Name]; lpName
0x18000e128  mov     ecx, esi; dwDesiredAccess
0x18000e12a  xor     edx, edx; bInheritHandle
0x18000e12c  call    cs:__imp_OpenSemaphoreW
0x18000e132  mov     rbx, rax
0x18000e135  test    rax, rax
0x18000e138  jz      loc_18000E277
0x18000e13e  lea     rdx, [rsp+290h+var_25C]; int *
0x18000e143  mov     [rsp+290h+var_25C], r15d
0x18000e148  mov     rcx, rax; hHandle
0x18000e14b  mov     [rsp+290h+var_260], r15d
0x18000e150  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e155  mov     edi, eax
0x18000e157  test    eax, eax
0x18000e159  jns     short loc_18000E18F
0x18000e15b  mov     rcx, [rbp+198h]; this
0x18000e162  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000e169  mov     edx, 0D6h; void *
0x18000e16e  mov     dword ptr [rsp+290h+var_270], eax; char *
0x18000e172  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000e177  mov     rcx, rbx; hObject
0x18000e17a  call    cs:__imp_CloseHandle
0x18000e180  test    eax, eax
0x18000e182  jz      loc_18000E308
0x18000e188  mov     eax, edi
0x18000e18a  jmp     loc_18000E29E
0x18000e18f  lea     r8, asc_180016E84; "h"
0x18000e196  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000e19b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e1a0  lea     r8, [rsp+290h+Name]; lpName
0x18000e1a5  xor     edx, edx; bInheritHandle
0x18000e1a7  mov     ecx, esi; dwDesiredAccess
0x18000e1a9  call    cs:__imp_OpenSemaphoreW
0x18000e1af  mov     rdi, rax
0x18000e1b2  test    rax, rax
0x18000e1b5  jz      loc_18000E24B
0x18000e1bb  lea     rdx, [rsp+290h+var_260]; int *
0x18000e1c0  mov     rcx, rax; hHandle
0x18000e1c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e1c8  mov     esi, eax
0x18000e1ca  test    eax, eax
0x18000e1cc  jns     short loc_18000E213
0x18000e1ce  mov     rcx, [rbp+198h]; this
0x18000e1d5  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000e1dc  mov     edx, 0DEh; void *
0x18000e1e1  mov     dword ptr [rsp+290h+var_270], eax; char *
0x18000e1e5  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000e1ea  mov     rcx, rdi; hObject
0x18000e1ed  call    cs:__imp_CloseHandle
0x18000e1f3  test    eax, eax
0x18000e1f5  jz      loc_18000E321
0x18000e1fb  mov     rcx, rbx; hObject
0x18000e1fe  call    cs:__imp_CloseHandle
0x18000e204  test    eax, eax
0x18000e206  jz      loc_18000E33A
0x18000e20c  mov     eax, esi
0x18000e20e  jmp     loc_18000E29E
0x18000e213  mov     rcx, rdi; hObject
0x18000e216  call    cs:__imp_CloseHandle
0x18000e21c  test    eax, eax
0x18000e21e  jz      loc_18000E2BD
0x18000e224  movsxd  rax, [rsp+290h+var_25C]
0x18000e229  movsxd  rcx, [rsp+290h+var_260]
0x18000e22e  shl     rcx, 1Fh
0x18000e232  or      rcx, rax
0x18000e235  mov     [r14], rcx
0x18000e238  mov     rcx, rbx; hObject
0x18000e23b  call    cs:__imp_CloseHandle
0x18000e241  test    eax, eax
0x18000e243  jz      loc_18000E2D6
0x18000e249  jmp     short loc_18000E282
0x18000e24b  mov     rcx, [rbp+198h]; this
0x18000e252  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000e259  mov     edx, 0DCh; void *
0x18000e25e  call    ?Return_GetLastError@in1diag4@details@wil@@YAJPEAXIPEBD1@Z; wil::details::in1diag4::Return_GetLastError(void *,uint,char const *,char const *)
0x18000e263  mov     rcx, rbx; hObject
0x18000e266  mov     edi, eax
0x18000e268  call    cs:__imp_CloseHandle
0x18000e26e  test    eax, eax
0x18000e270  jz      short loc_18000E2EF
0x18000e272  jmp     loc_18000E188
0x18000e277  call    cs:__imp_GetLastError
0x18000e27d  cmp     eax, 2
0x18000e280  jnz     short loc_18000E286
0x18000e282  xor     eax, eax
0x18000e284  jmp     short loc_18000E29E
0x18000e286  mov     rcx, [rbp+198h]; this
0x18000e28d  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000e294  mov     edx, 0D0h; void *
0x18000e299  call    ?Return_GetLastError@in1diag4@details@wil@@YAJPEAXIPEBD1@Z; wil::details::in1diag4::Return_GetLastError(void *,uint,char const *,char const *)
0x18000e29e  mov     rcx, [rbp+190h+var_40]
0x18000e2a5  xor     rcx, rsp; StackCookie
0x18000e2a8  call    __security_check_cookie
0x18000e2ad  add     rsp, 268h
0x18000e2b4  pop     r15
0x18000e2b6  pop     r14
0x18000e2b8  pop     rdi
0x18000e2b9  pop     rsi
0x18000e2ba  pop     rbx
0x18000e2bb  pop     rbp
0x18000e2bc  retn
0x18000e2bd  mov     rcx, [rbp+198h]; this
0x18000e2c4  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e2cb  mov     edx, 0A0Bh; void *
0x18000e2d0  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000e2d6  mov     rcx, [rbp+198h]; this
0x18000e2dd  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e2e4  mov     edx, 0A0Bh; void *
0x18000e2e9  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000e2ef  mov     rcx, [rbp+198h]; this
0x18000e2f6  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e2fd  mov     edx, 0A0Bh; void *
0x18000e302  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000e308  mov     rcx, [rbp+198h]; this
0x18000e30f  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e316  mov     edx, 0A0Bh; void *
0x18000e31b  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000e321  mov     rcx, [rbp+198h]; this
0x18000e328  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e32f  mov     edx, 0A0Bh; void *
0x18000e334  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000e33a  mov     rcx, [rbp+198h]; this
0x18000e341  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000e348  mov     edx, 0A0Bh; void *
0x18000e34d  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
