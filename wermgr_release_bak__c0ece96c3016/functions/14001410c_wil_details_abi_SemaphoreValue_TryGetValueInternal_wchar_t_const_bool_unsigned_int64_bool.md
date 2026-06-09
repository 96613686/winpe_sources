# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14001410c`
- end: `0x1400143d5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `713`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140010778`
- `0x140010b80`

## callees

- `0x140003200`
- `0x14000a070`
- `0x14000a62c`
- `0x140011d60`
- `0x140013444`
- `0x14001410c`
- `0x1400148d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400141f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001426f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400142bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400142ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400141f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001426f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400142bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400142ea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400141a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140014224`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400141a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140014224`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  HANDLE v16; // rax
  unsigned int v17; // r8d
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  wil::details *v27; // [rsp+20h] [rbp-E0h]
  wil::details *v28; // [rsp+20h] [rbp-E0h]
  wil::details *v29; // [rsp+20h] [rbp-E0h]
  wil::details *v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+28h] [rbp-D8h]
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33[3]; // [rsp+34h] [rbp-CCh] BYREF
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
  StringCchCatW(Name, v6, (wchar_t *)L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag4::Return_GetLastError(
               retaddr,
               (void *)0xD0,
               v26,
               "wil::details_abi::SemaphoreValue::TryGetValueInternal",
               (const char *)v27);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    LODWORD(v27) = ValueFromSemaphore;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetValueInternal",
      v27,
      v31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v14,
        "wil::details::CloseHandle",
        (const char *)v28);
    return LastError;
  }
  StringCchCatW(Name, v12, (wchar_t *)L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag4::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  v17,
                  "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                  (const char *)v27);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v25,
        "wil::details::CloseHandle",
        (const char *)v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v23,
        "wil::details::CloseHandle",
        (const char *)v27);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v24,
        "wil::details::CloseHandle",
        (const char *)v27);
    return 0;
  }
  LODWORD(v27) = v19;
  wil::details::in1diag4::Return_Hr(
    retaddr,
    (void *)0xDE,
    (unsigned int)"wil",
    "wil::details_abi::SemaphoreValue::TryGetValueInternal",
    v27,
    v31);
  if ( !CloseHandle(v18) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v21,
      "wil::details::CloseHandle",
      (const char *)v29);
  if ( !CloseHandle(v10) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v22,
      "wil::details::CloseHandle",
      (const char *)v29);
  return v20;
}

```

## disassembly

```asm
0x14001410c  push    rbp
0x14001410e  push    rbx
0x14001410f  push    rsi
0x140014110  push    rdi
0x140014111  push    r14
0x140014113  push    r15
0x140014115  lea     rbp, [rsp-168h]
0x14001411d  sub     rsp, 268h
0x140014124  mov     rax, cs:__security_cookie
0x14001412b  xor     rax, rsp
0x14001412e  mov     [rbp+190h+var_40], rax
0x140014135  xor     r15d, r15d
0x140014138  lea     rax, [rsp+290h+Name]
0x14001413d  mov     [r8], r15
0x140014140  mov     r14, r8
0x140014143  mov     edx, 104h
0x140014148  mov     r9d, 7FFFFFFEh
0x14001414e  test    r9, r9
0x140014151  jz      short loc_140014172
0x140014153  movzx   r8d, word ptr [rcx]
0x140014157  test    r8w, r8w
0x14001415b  jz      short loc_140014172
0x14001415d  mov     [rax], r8w
0x140014161  add     rcx, 2
0x140014165  add     rax, 2
0x140014169  dec     r9
0x14001416c  sub     rdx, 1; unsigned __int64
0x140014170  jnz     short loc_14001414E
0x140014172  test    rdx, rdx
0x140014175  lea     rcx, [rax-2]
0x140014179  lea     r8, aP0; "_p0"
0x140014180  cmovnz  rcx, rax
0x140014184  mov     [rcx], r15w
0x140014188  lea     rcx, [rsp+290h+Name]; wchar_t *
0x14001418d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140014192  mov     esi, 1F0003h
0x140014197  lea     r8, [rsp+290h+Name]; lpName
0x14001419c  mov     ecx, esi; dwDesiredAccess
0x14001419e  xor     edx, edx; bInheritHandle
0x1400141a0  call    cs:__imp_OpenSemaphoreW
0x1400141a6  mov     rbx, rax
0x1400141a9  test    rax, rax
0x1400141ac  jz      loc_1400142F9
0x1400141b2  lea     rdx, [rsp+290h+var_25C]; int *
0x1400141b7  mov     [rsp+290h+var_25C], r15d
0x1400141bc  mov     rcx, rax; hHandle
0x1400141bf  mov     [rsp+290h+var_260], r15d
0x1400141c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400141c9  mov     edi, eax
0x1400141cb  test    eax, eax
0x1400141cd  jns     short loc_14001420A
0x1400141cf  mov     rcx, [rbp+198h]; this
0x1400141d6  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x1400141dd  lea     r8, aWil; "wil"
0x1400141e4  mov     dword ptr [rsp+290h+var_270], eax; char *
0x1400141e8  mov     edx, 0D6h; void *
0x1400141ed  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x1400141f2  mov     rcx, rbx; hObject
0x1400141f5  call    cs:__imp_CloseHandle
0x1400141fb  test    eax, eax
0x1400141fd  jz      loc_14001438A
0x140014203  mov     eax, edi
0x140014205  jmp     loc_140014320
0x14001420a  lea     r8, asc_1400245D4; "h"
0x140014211  lea     rcx, [rsp+290h+Name]; wchar_t *
0x140014216  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001421b  lea     r8, [rsp+290h+Name]; lpName
0x140014220  xor     edx, edx; bInheritHandle
0x140014222  mov     ecx, esi; dwDesiredAccess
0x140014224  call    cs:__imp_OpenSemaphoreW
0x14001422a  mov     rdi, rax
0x14001422d  test    rax, rax
0x140014230  jz      loc_1400142CD
0x140014236  lea     rdx, [rsp+290h+var_260]; int *
0x14001423b  mov     rcx, rax; hHandle
0x14001423e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140014243  mov     esi, eax
0x140014245  test    eax, eax
0x140014247  jns     short loc_140014295
0x140014249  mov     rcx, [rbp+198h]; this
0x140014250  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x140014257  lea     r8, aWil; "wil"
0x14001425e  mov     dword ptr [rsp+290h+var_270], eax; char *
0x140014262  mov     edx, 0DEh; void *
0x140014267  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14001426c  mov     rcx, rdi; hObject
0x14001426f  call    cs:__imp_CloseHandle
0x140014275  test    eax, eax
0x140014277  jz      loc_1400143A3
0x14001427d  mov     rcx, rbx; hObject
0x140014280  call    cs:__imp_CloseHandle
0x140014286  test    eax, eax
0x140014288  jz      loc_1400143BC
0x14001428e  mov     eax, esi
0x140014290  jmp     loc_140014320
0x140014295  mov     rcx, rdi; hObject
0x140014298  call    cs:__imp_CloseHandle
0x14001429e  test    eax, eax
0x1400142a0  jz      loc_14001433F
0x1400142a6  movsxd  rax, [rsp+290h+var_25C]
0x1400142ab  movsxd  rcx, [rsp+290h+var_260]
0x1400142b0  shl     rcx, 1Fh
0x1400142b4  or      rcx, rax
0x1400142b7  mov     [r14], rcx
0x1400142ba  mov     rcx, rbx; hObject
0x1400142bd  call    cs:__imp_CloseHandle
0x1400142c3  test    eax, eax
0x1400142c5  jz      loc_140014358
0x1400142cb  jmp     short loc_140014304
0x1400142cd  mov     rcx, [rbp+198h]; this
0x1400142d4  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x1400142db  mov     edx, 0DCh; void *
0x1400142e0  call    ?Return_GetLastError@in1diag4@details@wil@@YAJPEAXIPEBD1@Z; wil::details::in1diag4::Return_GetLastError(void *,uint,char const *,char const *)
0x1400142e5  mov     rcx, rbx; hObject
0x1400142e8  mov     edi, eax
0x1400142ea  call    cs:__imp_CloseHandle
0x1400142f0  test    eax, eax
0x1400142f2  jz      short loc_140014371
0x1400142f4  jmp     loc_140014203
0x1400142f9  call    cs:__imp_GetLastError
0x1400142ff  cmp     eax, 2
0x140014302  jnz     short loc_140014308
0x140014304  xor     eax, eax
0x140014306  jmp     short loc_140014320
0x140014308  mov     rcx, [rbp+198h]; this
0x14001430f  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x140014316  mov     edx, 0D0h; void *
0x14001431b  call    ?Return_GetLastError@in1diag4@details@wil@@YAJPEAXIPEBD1@Z; wil::details::in1diag4::Return_GetLastError(void *,uint,char const *,char const *)
0x140014320  mov     rcx, [rbp+190h+var_40]
0x140014327  xor     rcx, rsp; StackCookie
0x14001432a  call    __security_check_cookie
0x14001432f  add     rsp, 268h
0x140014336  pop     r15
0x140014338  pop     r14
0x14001433a  pop     rdi
0x14001433b  pop     rsi
0x14001433c  pop     rbx
0x14001433d  pop     rbp
0x14001433e  retn
0x14001433f  mov     rcx, [rbp+198h]; this
0x140014346  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14001434d  mov     edx, 0A0Bh; void *
0x140014352  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140014358  mov     rcx, [rbp+198h]; this
0x14001435f  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140014366  mov     edx, 0A0Bh; void *
0x14001436b  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140014371  mov     rcx, [rbp+198h]; this
0x140014378  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14001437f  mov     edx, 0A0Bh; void *
0x140014384  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x14001438a  mov     rcx, [rbp+198h]; this
0x140014391  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140014398  mov     edx, 0A0Bh; void *
0x14001439d  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x1400143a3  mov     rcx, [rbp+198h]; this
0x1400143aa  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400143b1  mov     edx, 0A0Bh; void *
0x1400143b6  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x1400143bc  mov     rcx, [rbp+198h]; this
0x1400143c3  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x1400143ca  mov     edx, 0A0Bh; void *
0x1400143cf  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
