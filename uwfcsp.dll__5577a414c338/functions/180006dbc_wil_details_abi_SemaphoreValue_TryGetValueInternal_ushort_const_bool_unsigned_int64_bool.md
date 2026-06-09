# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006dbc`
- end: `0x180007036`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004f1c`

## callees

- `0x180005e84`
- `0x1800068d4`
- `0x1800068f4`
- `0x180006c0c`
- `0x180006dbc`
- `0x180007238`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ecc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f7c`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180006dbc  push    rbp
0x180006dbe  push    rbx
0x180006dbf  push    rsi
0x180006dc0  push    rdi
0x180006dc1  push    r14
0x180006dc3  push    r15
0x180006dc5  lea     rbp, [rsp-158h]
0x180006dcd  sub     rsp, 258h
0x180006dd4  mov     rax, cs:__security_cookie
0x180006ddb  xor     rax, rsp
0x180006dde  mov     [rbp+180h+var_40], rax
0x180006de5  xor     r15d, r15d
0x180006de8  lea     rax, [rsp+280h+Name]
0x180006ded  mov     [r8], r15
0x180006df0  mov     r14, r8
0x180006df3  mov     edx, 104h
0x180006df8  mov     r9d, 7FFFFFFEh
0x180006dfe  test    r9, r9
0x180006e01  jz      short loc_180006E22
0x180006e03  movzx   r8d, word ptr [rcx]
0x180006e07  test    r8w, r8w
0x180006e0b  jz      short loc_180006E22
0x180006e0d  mov     [rax], r8w
0x180006e11  add     rcx, 2
0x180006e15  add     rax, 2
0x180006e19  dec     r9
0x180006e1c  sub     rdx, 1; unsigned __int64
0x180006e20  jnz     short loc_180006DFE
0x180006e22  test    rdx, rdx
0x180006e25  lea     rcx, [rax-2]
0x180006e29  lea     r8, aP0; "_p0"
0x180006e30  cmovnz  rcx, rax
0x180006e34  mov     [rcx], r15w
0x180006e38  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006e42  mov     esi, 1F0003h
0x180006e47  lea     r8, [rsp+280h+Name]; lpName
0x180006e4c  mov     ecx, esi; dwDesiredAccess
0x180006e4e  xor     edx, edx; bInheritHandle
0x180006e50  call    cs:__imp_OpenSemaphoreW
0x180006e56  mov     rbx, rax
0x180006e59  test    rax, rax
0x180006e5c  jz      loc_180006F8B
0x180006e62  lea     rdx, [rsp+280h+var_25C]; int *
0x180006e67  mov     [rsp+280h+var_25C], r15d
0x180006e6c  mov     rcx, rax; hHandle
0x180006e6f  mov     [rsp+280h+var_260], r15d; int
0x180006e74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e79  mov     edi, eax
0x180006e7b  test    eax, eax
0x180006e7d  jns     short loc_180006EB2
0x180006e7f  mov     rcx, [rbp+188h]; this
0x180006e86  lea     r8, aWil; "wil"
0x180006e8d  mov     r9d, eax; char *
0x180006e90  mov     edx, 0D6h; void *
0x180006e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e9a  mov     rcx, rbx; hObject
0x180006e9d  call    cs:__imp_CloseHandle
0x180006ea3  test    eax, eax
0x180006ea5  jz      loc_180007000
0x180006eab  mov     eax, edi
0x180006ead  jmp     loc_180006FAB
0x180006eb2  lea     r8, asc_18001F1F0; "h"
0x180006eb9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006ebe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ec3  lea     r8, [rsp+280h+Name]; lpName
0x180006ec8  xor     edx, edx; bInheritHandle
0x180006eca  mov     ecx, esi; dwDesiredAccess
0x180006ecc  call    cs:__imp_OpenSemaphoreW
0x180006ed2  mov     rdi, rax
0x180006ed5  test    rax, rax
0x180006ed8  jz      loc_180006F66
0x180006ede  lea     rdx, [rsp+280h+var_260]; int *
0x180006ee3  mov     rcx, rax; hHandle
0x180006ee6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006eeb  mov     esi, eax
0x180006eed  test    eax, eax
0x180006eef  jns     short loc_180006F32
0x180006ef1  mov     rcx, [rbp+188h]; this
0x180006ef8  lea     r8, aWil; "wil"
0x180006eff  mov     r9d, eax; char *
0x180006f02  mov     edx, 0DEh; void *
0x180006f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f0c  mov     rcx, rdi; hObject
0x180006f0f  call    cs:__imp_CloseHandle
0x180006f15  test    eax, eax
0x180006f17  jz      loc_180007012
0x180006f1d  mov     rcx, rbx; hObject
0x180006f20  call    cs:__imp_CloseHandle
0x180006f26  test    eax, eax
0x180006f28  jz      loc_180007024
0x180006f2e  mov     eax, esi
0x180006f30  jmp     short loc_180006FAB
0x180006f32  mov     rcx, rdi; hObject
0x180006f35  call    cs:__imp_CloseHandle
0x180006f3b  test    eax, eax
0x180006f3d  jz      loc_180006FCA
0x180006f43  movsxd  rax, [rsp+280h+var_25C]
0x180006f48  movsxd  rcx, [rsp+280h+var_260]
0x180006f4d  shl     rcx, 1Fh
0x180006f51  or      rcx, rax
0x180006f54  mov     [r14], rcx
0x180006f57  mov     rcx, rbx; hObject
0x180006f5a  call    cs:__imp_CloseHandle
0x180006f60  test    eax, eax
0x180006f62  jz      short loc_180006FDC
0x180006f64  jmp     short loc_180006F96
0x180006f66  mov     rcx, [rbp+188h]; this
0x180006f6d  mov     edx, 0DCh; void *
0x180006f72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f77  mov     rcx, rbx; hObject
0x180006f7a  mov     edi, eax
0x180006f7c  call    cs:__imp_CloseHandle
0x180006f82  test    eax, eax
0x180006f84  jz      short loc_180006FEE
0x180006f86  jmp     loc_180006EAB
0x180006f8b  call    cs:__imp_GetLastError
0x180006f91  cmp     eax, 2
0x180006f94  jnz     short loc_180006F9A
0x180006f96  xor     eax, eax
0x180006f98  jmp     short loc_180006FAB
0x180006f9a  mov     rcx, [rbp+188h]; this
0x180006fa1  mov     edx, 0D0h; void *
0x180006fa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006fab  mov     rcx, [rbp+180h+var_40]
0x180006fb2  xor     rcx, rsp; StackCookie
0x180006fb5  call    __security_check_cookie
0x180006fba  add     rsp, 258h
0x180006fc1  pop     r15
0x180006fc3  pop     r14
0x180006fc5  pop     rdi
0x180006fc6  pop     rsi
0x180006fc7  pop     rbx
0x180006fc8  pop     rbp
0x180006fc9  retn
0x180006fca  mov     rcx, [rbp+188h]; this
0x180006fd1  mov     edx, 0A0Bh; void *
0x180006fd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fdc  mov     rcx, [rbp+188h]; this
0x180006fe3  mov     edx, 0A0Bh; void *
0x180006fe8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fee  mov     rcx, [rbp+188h]; this
0x180006ff5  mov     edx, 0A0Bh; void *
0x180006ffa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007000  mov     rcx, [rbp+188h]; this
0x180007007  mov     edx, 0A0Bh; void *
0x18000700c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007012  mov     rcx, [rbp+188h]; this
0x180007019  mov     edx, 0A0Bh; void *
0x18000701e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007024  mov     rcx, [rbp+188h]; this
0x18000702b  mov     edx, 0A0Bh; void *
0x180007030  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
