# VerifyTrust

- ea: `0x180008c5c`
- end: `0x180008e9c`
- name: `VerifyTrust`
- size: `576`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180008af0`
- `0x180008bc0`

## callees

- `0x180008c5c`
- `0x18000d17e`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180008d81`
- `msvcrt!strcpy_s` at `0x180008d81`
- `KERNEL32!GetLastError` at `0x180008d3d`
- `KERNEL32!GetLastError` at `0x180008d3d`
- `KERNEL32!LoadLibraryExA` at `0x180008d93`
- `KERNEL32!LoadLibraryExA` at `0x180008d93`
- `KERNEL32!GetSystemDirectoryA` at `0x180008d33`
- `KERNEL32!GetSystemDirectoryA` at `0x180008d33`
- `KERNEL32!GetProcAddress` at `0x180008dab`
- `KERNEL32!GetProcAddress` at `0x180008dc3`
- `KERNEL32!GetProcAddress` at `0x180008ddf`
- `KERNEL32!GetProcAddress` at `0x180008dab`
- `KERNEL32!GetProcAddress` at `0x180008dc3`
- `KERNEL32!GetProcAddress` at `0x180008ddf`
- `KERNEL32!FreeLibrary` at `0x180008e6a`
- `KERNEL32!FreeLibrary` at `0x180008e6a`

## string_xrefs

- `0x180008d74`: `\wintrust.dll`

## pseudocode

```c
__int64 __fastcall VerifyTrust(__int64 a1, __int64 a2, int a3)
{
  HMODULE v3; // rsi
  FARPROC v7; // r12
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  UINT SystemDirectoryA; // eax
  signed int LastError; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // r15
  FARPROC v14; // rdi
  int v15; // eax
  bool v16; // sf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v19[5]; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+70h] [rbp-90h]
  _QWORD *v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+98h] [rbp-68h]
  _DWORD v31[4]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR Buffer[288]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v31[0] = 11191659;
  v31[1] = 298896708;
  v31[2] = -1073692020;
  v31[3] = -292175281;
  v18 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(&v20, 0, 0x58u);
  v19[1] = a2;
  v19[2] = a1;
  v19[0] = 32;
  v19[3] = 0;
  v20 = 88;
  v23 = 2 - (a3 != 0);
  v9 = 1;
  v21 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v26 = v19;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  SystemDirectoryA = GetSystemDirectoryA(Buffer, 0x105u);
  if ( !SystemDirectoryA )
    goto LABEL_2;
  if ( SystemDirectoryA >= 0x105 )
  {
    v9 = -2147024774;
    goto LABEL_19;
  }
  strcpy_s(&Buffer[SystemDirectoryA], 275LL - SystemDirectoryA, "\\wintrust.dll");
  Library = LoadLibraryExA(Buffer, 0, 0x800u);
  v3 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "WinVerifyTrust")) != 0
    && (v14 = GetProcAddress(v3, "WintrustGetRegPolicyFlags")) != 0
    && (v7 = GetProcAddress(v3, "WintrustSetRegPolicyFlags")) != 0 )
  {
    if ( a3
      || (((void (__fastcall *)(int *))v14)(&v18), v8 = v18 | 0x40000, (v18 | 0x40000) == v18)
      || ((unsigned int (__fastcall *)(_QWORD))v7)(v8) )
    {
      v15 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, int *))ProcAddress)(0, v31, &v20);
      v16 = v15 < 0;
      if ( !v15 )
        goto LABEL_18;
      if ( v15 > 0 )
        v16 = 1;
      if ( !v16 )
LABEL_18:
        v9 = 0;
    }
    else
    {
      v9 = -2147467259;
    }
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_19:
  if ( v18 != v8 )
    v7();
  if ( v3 )
    FreeLibrary(v3);
  return v9;
}

```

## disassembly

```asm
0x180008c5c  mov     [rsp-8+arg_10], rbx
0x180008c61  push    rbp
0x180008c62  push    rsi
0x180008c63  push    rdi
0x180008c64  push    r12
0x180008c66  push    r13
0x180008c68  push    r14
0x180008c6a  push    r15
0x180008c6c  lea     rbp, [rsp-0F0h]
0x180008c74  sub     rsp, 1F0h
0x180008c7b  mov     rax, cs:__security_cookie
0x180008c82  xor     rax, rsp
0x180008c85  mov     [rbp+120h+var_40], rax
0x180008c8c  xor     esi, esi
0x180008c8e  mov     [rbp+120h+var_170], 0AAC56Bh
0x180008c95  mov     r13d, r8d
0x180008c98  mov     [rbp+120h+var_16C], 11D0CD44h
0x180008c9f  mov     rdi, rdx
0x180008ca2  mov     [rbp+120h+var_168], 0C000C28Ch
0x180008ca9  mov     rbx, rcx
0x180008cac  mov     [rbp+120h+var_164], 0EE95C24Fh
0x180008cb3  lea     r15d, [rsi+58h]
0x180008cb7  mov     [rsp+220h+var_200], esi
0x180008cbb  mov     r8d, r15d; Size
0x180008cbe  lea     rcx, [rsp+220h+var_1D0]; void *
0x180008cc3  xor     edx, edx; Val
0x180008cc5  xor     r12d, r12d
0x180008cc8  xor     r14d, r14d
0x180008ccb  call    memset_0
0x180008cd0  mov     eax, r13d
0x180008cd3  mov     [rsp+220h+var_1F0], rdi
0x180008cd8  neg     eax
0x180008cda  mov     [rsp+220h+var_1E8], rbx
0x180008cdf  lea     rax, [rsp+220h+var_1F8]
0x180008ce4  mov     [rsp+220h+var_1F8], 20h ; ' '
0x180008ced  sbb     ecx, ecx
0x180008cef  mov     [rsp+220h+var_1E0], rsi
0x180008cf4  add     ecx, 2
0x180008cf7  mov     [rsp+220h+var_1D0], r15d
0x180008cfc  mov     [rsp+220h+var_1B8], ecx
0x180008d00  lea     ebx, [rsi+1]
0x180008d03  mov     edi, 105h
0x180008d08  mov     [rsp+220h+var_1C8], rsi
0x180008d0d  lea     rcx, [rbp+120h+Buffer]; lpBuffer
0x180008d11  mov     [rsp+220h+var_1C0], rsi
0x180008d16  mov     edx, edi; uSize
0x180008d18  mov     [rsp+220h+var_1B4], esi
0x180008d1c  mov     [rsp+220h+var_1B0], ebx
0x180008d20  mov     [rsp+220h+var_1A8], rax
0x180008d25  mov     [rbp+120h+var_1A0], esi
0x180008d28  mov     [rbp+120h+var_198], rsi
0x180008d2c  mov     [rbp+120h+var_190], rsi
0x180008d30  mov     [rbp+120h+var_188], esi
0x180008d33  call    cs:__imp_GetSystemDirectoryA
0x180008d39  test    eax, eax
0x180008d3b  jnz     short loc_180008D5B
0x180008d3d  call    cs:__imp_GetLastError
0x180008d43  mov     ebx, eax
0x180008d45  test    eax, eax
0x180008d47  jle     loc_180008E51
0x180008d4d  movzx   ebx, ax
0x180008d50  or      ebx, 80070000h
0x180008d56  jmp     loc_180008E51
0x180008d5b  cmp     eax, edi
0x180008d5d  jb      short loc_180008D69
0x180008d5f  mov     ebx, 8007007Ah
0x180008d64  jmp     loc_180008E51
0x180008d69  mov     eax, eax
0x180008d6b  lea     rcx, [rbp+120h+Buffer]
0x180008d6f  mov     edx, 113h
0x180008d74  lea     r8, aWintrustDll; "\\wintrust.dll"
0x180008d7b  sub     rdx, rax; SizeInBytes
0x180008d7e  add     rcx, rax; Destination
0x180008d81  call    cs:__imp_strcpy_s
0x180008d87  xor     edx, edx; hFile
0x180008d89  lea     rcx, [rbp+120h+Buffer]; lpLibFileName
0x180008d8d  mov     r8d, 800h; dwFlags
0x180008d93  call    cs:__imp_LoadLibraryExA
0x180008d99  mov     rsi, rax
0x180008d9c  test    rax, rax
0x180008d9f  jz      short loc_180008D3D
0x180008da1  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x180008da8  mov     rcx, rax; hModule
0x180008dab  call    cs:__imp_GetProcAddress
0x180008db1  mov     r15, rax
0x180008db4  test    rax, rax
0x180008db7  jz      short loc_180008D3D
0x180008db9  lea     rdx, aWintrustgetreg; "WintrustGetRegPolicyFlags"
0x180008dc0  mov     rcx, rsi; hModule
0x180008dc3  call    cs:__imp_GetProcAddress
0x180008dc9  mov     rdi, rax
0x180008dcc  test    rax, rax
0x180008dcf  jz      loc_180008D3D
0x180008dd5  lea     rdx, aWintrustsetreg; "WintrustSetRegPolicyFlags"
0x180008ddc  mov     rcx, rsi; hModule
0x180008ddf  call    cs:__imp_GetProcAddress
0x180008de5  mov     r12, rax
0x180008de8  test    rax, rax
0x180008deb  jz      loc_180008D3D
0x180008df1  test    r13d, r13d
0x180008df4  jnz     short loc_180008E2A
0x180008df6  lea     rcx, [rsp+220h+var_200]
0x180008dfb  mov     rax, rdi
0x180008dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e03  mov     r14d, [rsp+220h+var_200]
0x180008e08  bts     r14d, 12h
0x180008e0d  cmp     r14d, [rsp+220h+var_200]
0x180008e12  jz      short loc_180008E2A
0x180008e14  mov     ecx, r14d
0x180008e17  mov     rax, r12
0x180008e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1f  test    eax, eax
0x180008e21  jnz     short loc_180008E2A
0x180008e23  mov     ebx, 80004005h
0x180008e28  jmp     short loc_180008E51
0x180008e2a  lea     r8, [rsp+220h+var_1D0]
0x180008e2f  xor     ecx, ecx
0x180008e31  lea     rdx, [rbp+120h+var_170]
0x180008e35  mov     rax, r15
0x180008e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e3d  test    eax, eax
0x180008e3f  jz      short loc_180008E4F
0x180008e41  jle     short loc_180008E4D
0x180008e43  movzx   eax, ax
0x180008e46  or      eax, 80070000h
0x180008e4b  test    eax, eax
0x180008e4d  js      short loc_180008E51
0x180008e4f  xor     ebx, ebx
0x180008e51  mov     ecx, [rsp+220h+var_200]
0x180008e55  cmp     ecx, r14d
0x180008e58  jz      short loc_180008E62
0x180008e5a  mov     rax, r12
0x180008e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e62  test    rsi, rsi
0x180008e65  jz      short loc_180008E70
0x180008e67  mov     rcx, rsi; hLibModule
0x180008e6a  call    cs:__imp_FreeLibrary
0x180008e70  mov     eax, ebx
0x180008e72  mov     rcx, [rbp+120h+var_40]
0x180008e79  xor     rcx, rsp; StackCookie
0x180008e7c  call    __security_check_cookie
0x180008e81  mov     rbx, [rsp+220h+arg_10]
0x180008e89  add     rsp, 1F0h
0x180008e90  pop     r15
0x180008e92  pop     r14
0x180008e94  pop     r13
0x180008e96  pop     r12
0x180008e98  pop     rdi
0x180008e99  pop     rsi
0x180008e9a  pop     rbp
0x180008e9b  retn
```
