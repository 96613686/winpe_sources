# TaDllRegisterServer(uint,_GUID *)

- ea: `0x18000e280`
- end: `0x18000e43a`
- name: `?TaDllRegisterServer@@YAJIPEAU_GUID@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007620`

## callees

- `0x18000e280`
- `0x18000eef0`
- `0x180010250`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x18000e3da`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000e3da`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18000e3f0`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x18000e3f0`
- `KERNEL32!GetModuleFileNameW` at `0x18000e357`
- `KERNEL32!GetModuleFileNameW` at `0x18000e357`
- `KERNEL32!GetLastError` at `0x18000e361`
- `KERNEL32!GetLastError` at `0x18000e361`
- `KERNEL32!MultiByteToWideChar` at `0x18000e3c7`
- `KERNEL32!MultiByteToWideChar` at `0x18000e3c7`
- `KERNEL32!GetModuleFileNameA` at `0x18000e392`
- `KERNEL32!GetModuleFileNameA` at `0x18000e392`

## pseudocode

```c
signed int __fastcall TaDllRegisterServer(__int64 a1, struct _GUID *a2)
{
  int v2; // r14d
  struct TaClassTable near **v3; // rbx
  int v4; // edi
  char v5; // si
  struct TaClassTable near *v6; // rax
  signed int result; // eax
  ITypeLib *pptlib; // [rsp+30h] [rbp-D0h] BYREF
  CHAR MultiByteStr[260]; // [rsp+40h] [rbp-C0h] BYREF
  char v10; // [rsp+144h] [rbp+44h]
  WCHAR Filename[260]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v12; // [rsp+358h] [rbp+258h]

  v2 = 0;
  v3 = &g_TaClassTable;
  v4 = 0;
  v5 = 0;
  if ( !(_DWORD)g_TaClassTable )
    return -2147220991;
  do
  {
    v6 = v3[1];
    if ( v6 )
    {
      LOBYTE(a2) = 1;
      if ( ((int (__fastcall *)(struct TaClassTable near *, struct _GUID *))v6)(v3[2], a2) < 0 )
        goto LABEL_7;
      ++v2;
      if ( *(_DWORD *)v3 != 1 )
        v5 = 1;
      if ( TaRegisterCLSIDInCategory(*(const struct _GUID **)v3[2], 0, 0) < 0 )
LABEL_7:
        ++v4;
    }
    v3 += 3;
  }
  while ( *(_DWORD *)v3 );
  if ( !v2 || v4 >= 1 )
    return -2147220991;
  if ( !v5 )
    return 0;
  pptlib = 0;
  if ( Global::g_fWindowsNT )
  {
    v12 = 0;
    if ( !GetModuleFileNameW(Global::g_hInstance, Filename, 0x105u) )
      goto LABEL_14;
    if ( !v12 )
      goto LABEL_22;
    return -2147024774;
  }
  v10 = 0;
  if ( GetModuleFileNameA(Global::g_hInstance, MultiByteStr, 0x105u) )
  {
    if ( v10 )
      return -2147024774;
    if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, Filename, 261) )
    {
LABEL_22:
      result = LoadTypeLib(Filename, &pptlib);
      if ( result < 0 )
        return result;
      if ( RegisterTypeLib(pptlib, Filename, 0) < 0 )
        return -2147220992;
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      return 0;
    }
  }
LABEL_14:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e280  push    rbp
0x18000e282  push    rbx
0x18000e283  push    rsi
0x18000e284  push    rdi
0x18000e285  push    r12
0x18000e287  push    r14
0x18000e289  lea     rbp, [rsp-278h]
0x18000e291  sub     rsp, 378h
0x18000e298  mov     rax, cs:__security_cookie
0x18000e29f  xor     rax, rsp
0x18000e2a2  mov     [rbp+2A0h+var_40], rax
0x18000e2a9  xor     r14d, r14d
0x18000e2ac  lea     rbx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x18000e2b3  xor     edi, edi
0x18000e2b5  xor     sil, sil
0x18000e2b8  cmp     cs:?g_TaClassTable@@3PAUTaClassTable@@A, edi; TaClassTable near * g_TaClassTable
0x18000e2be  jz      loc_18000E416
0x18000e2c4  lea     r12d, [r14+1]
0x18000e2c8  mov     rax, [rbx+8]
0x18000e2cc  test    rax, rax
0x18000e2cf  jz      short loc_18000E307
0x18000e2d1  mov     rcx, [rbx+10h]
0x18000e2d5  mov     dl, r12b
0x18000e2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2dd  test    eax, eax
0x18000e2df  js      short loc_18000E304
0x18000e2e1  mov     rcx, [rbx+10h]
0x18000e2e5  add     r14d, r12d
0x18000e2e8  cmp     [rbx], r12d
0x18000e2eb  movzx   esi, sil
0x18000e2ef  cmovnz  esi, r12d
0x18000e2f3  xor     r8d, r8d; struct _GUID *
0x18000e2f6  mov     rcx, [rcx]; struct _GUID *
0x18000e2f9  xor     edx, edx; unsigned int
0x18000e2fb  call    ?TaRegisterCLSIDInCategory@@YAJAEBU_GUID@@IPEAU1@@Z; TaRegisterCLSIDInCategory(_GUID const &,uint,_GUID *)
0x18000e300  test    eax, eax
0x18000e302  jns     short loc_18000E307
0x18000e304  add     edi, r12d
0x18000e307  add     rbx, 18h
0x18000e30b  cmp     dword ptr [rbx], 0
0x18000e30e  jnz     short loc_18000E2C8
0x18000e310  test    r14d, r14d
0x18000e313  jz      loc_18000E416
0x18000e319  cmp     edi, r12d
0x18000e31c  jge     loc_18000E416
0x18000e322  test    sil, sil
0x18000e325  jz      loc_18000E412
0x18000e32b  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x18000e332  mov     r8d, 105h; nSize
0x18000e338  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x18000e33f  mov     [rsp+3A0h+pptlib], 0
0x18000e348  jz      short loc_18000E389
0x18000e34a  xor     eax, eax
0x18000e34c  lea     rdx, [rbp+2A0h+Filename]; lpFilename
0x18000e350  mov     [rbp+2A0h+var_48], ax
0x18000e357  call    cs:__imp_GetModuleFileNameW
0x18000e35d  test    eax, eax
0x18000e35f  jnz     short loc_18000E37C
0x18000e361  call    cs:__imp_GetLastError
0x18000e367  test    eax, eax
0x18000e369  jle     loc_18000E41B
0x18000e36f  movzx   eax, ax
0x18000e372  or      eax, 80070000h
0x18000e377  jmp     loc_18000E41B
0x18000e37c  xor     eax, eax
0x18000e37e  cmp     ax, [rbp+2A0h+var_48]
0x18000e385  jnz     short loc_18000E3A2
0x18000e387  jmp     short loc_18000E3D1
0x18000e389  lea     rdx, [rsp+3A0h+MultiByteStr]; lpFilename
0x18000e38e  mov     [rbp+2A0h+var_25C], 0
0x18000e392  call    cs:__imp_GetModuleFileNameA
0x18000e398  test    eax, eax
0x18000e39a  jz      short loc_18000E361
0x18000e39c  cmp     [rbp+2A0h+var_25C], 0
0x18000e3a0  jz      short loc_18000E3A9
0x18000e3a2  mov     eax, 8007007Ah
0x18000e3a7  jmp     short loc_18000E41B
0x18000e3a9  lea     rax, [rbp+2A0h+Filename]
0x18000e3ad  mov     [rsp+3A0h+cchWideChar], 105h; cchWideChar
0x18000e3b5  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000e3b9  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x18000e3be  lea     r8, [rsp+3A0h+MultiByteStr]; lpMultiByteStr
0x18000e3c3  xor     edx, edx; dwFlags
0x18000e3c5  xor     ecx, ecx; CodePage
0x18000e3c7  call    cs:__imp_MultiByteToWideChar
0x18000e3cd  test    eax, eax
0x18000e3cf  jz      short loc_18000E361
0x18000e3d1  lea     rdx, [rsp+3A0h+pptlib]; pptlib
0x18000e3d6  lea     rcx, [rbp+2A0h+Filename]; szFile
0x18000e3da  call    cs:__imp_LoadTypeLib
0x18000e3e0  test    eax, eax
0x18000e3e2  js      short loc_18000E41B
0x18000e3e4  mov     rcx, [rsp+3A0h+pptlib]; ptlib
0x18000e3e9  lea     rdx, [rbp+2A0h+Filename]; szFullPath
0x18000e3ed  xor     r8d, r8d; szHelpDir
0x18000e3f0  call    cs:__imp_RegisterTypeLib
0x18000e3f6  test    eax, eax
0x18000e3f8  jns     short loc_18000E401
0x18000e3fa  mov     eax, 80040200h
0x18000e3ff  jmp     short loc_18000E41B
0x18000e401  mov     rcx, [rsp+3A0h+pptlib]
0x18000e406  mov     rax, [rcx]
0x18000e409  mov     rax, [rax+10h]
0x18000e40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e412  xor     eax, eax
0x18000e414  jmp     short loc_18000E41B
0x18000e416  mov     eax, 80040201h
0x18000e41b  mov     rcx, [rbp+2A0h+var_40]
0x18000e422  xor     rcx, rsp; StackCookie
0x18000e425  call    __security_check_cookie
0x18000e42a  add     rsp, 378h
0x18000e431  pop     r14
0x18000e433  pop     r12
0x18000e435  pop     rdi
0x18000e436  pop     rsi
0x18000e437  pop     rbx
0x18000e438  pop     rbp
0x18000e439  retn
```
