# VerifyTrustDownLevel

- ea: `0x14000b8c8`
- end: `0x14000bb30`
- name: `VerifyTrustDownLevel`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140006f7c`

## callees

- `0x14000b184`
- `0x14000b4c8`
- `0x14000b8c8`
- `0x14001755a`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000b9e2`
- `msvcrt!wcsrchr` at `0x14000b9e2`
- `KERNEL32!GetLastError` at `0x14000b983`
- `KERNEL32!GetLastError` at `0x14000b983`
- `KERNEL32!CloseHandle` at `0x14000baf7`
- `KERNEL32!CloseHandle` at `0x14000baf7`
- `KERNEL32!GetProcAddress` at `0x14000b975`
- `KERNEL32!GetProcAddress` at `0x14000b9ad`
- `KERNEL32!GetProcAddress` at `0x14000b9c7`
- `KERNEL32!GetProcAddress` at `0x14000b975`
- `KERNEL32!GetProcAddress` at `0x14000b9ad`
- `KERNEL32!GetProcAddress` at `0x14000b9c7`
- `KERNEL32!FreeLibrary` at `0x14000bb0a`
- `KERNEL32!FreeLibrary` at `0x14000bb0a`

## string_xrefs

- `0x14000b936`: `wintrust.dll`

## pseudocode

```c
__int64 __fastcall VerifyTrustDownLevel(wchar_t *a1, const void *a2, int a3, __int64 a4, int a5)
{
  void *v5; // rdi
  FARPROC v6; // r15
  unsigned int v7; // esi
  int v8; // ebx
  FARPROC ProcAddress; // r13
  signed int LastError; // eax
  FARPROC v11; // r12
  wchar_t *v12; // rdi
  wchar_t *v13; // rax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h]
  void *v19; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-B0h]
  LPCVOID lpBuffer; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+78h] [rbp-88h]
  _DWORD v25[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 *v26; // [rsp+B8h] [rbp-48h]
  int v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  __int64 v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  _DWORD v31[4]; // [rsp+F0h] [rbp-10h] BYREF

  lpBuffer = a2;
  v18 = a3;
  Str = a1;
  v22 = a4;
  v31[0] = 11191659;
  v31[1] = 298896708;
  v31[2] = -1073692020;
  v31[3] = -292175281;
  memset_0(v25, 0, 0x58u);
  v5 = 0;
  v23 = 0;
  v19 = 0;
  v6 = 0;
  v24 = 0;
  hModule = 0;
  v7 = 0;
  v16 = 0;
  v8 = SafeLoadLibrary("wintrust.dll", &hModule);
  if ( v8 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "WinVerifyTrust");
    if ( ProcAddress
      && (v11 = GetProcAddress(hModule, "WintrustGetRegPolicyFlags")) != 0
      && (v6 = GetProcAddress(hModule, "WintrustSetRegPolicyFlags")) != 0 )
    {
      v12 = Str;
      v13 = wcsrchr(Str, 0x2Eu);
      v8 = SafeCreateTempFile(v13, lpBuffer, v18, &v19, 0);
      if ( v8 < 0 )
      {
        v5 = v19;
      }
      else
      {
        memset_0(v25, 0, 0x58u);
        *((_QWORD *)&v23 + 1) = v12;
        v5 = v19;
        v25[0] = 88;
        v26 = &v23;
        v25[7] = 0;
        v27 = 0;
        v28 = 0;
        v29 = 0;
        v25[6] = 2 - (a5 != 0);
        v30 = 0;
        v25[8] = 1;
        *(_QWORD *)&v23 = 32;
        *((_QWORD *)&v24 + 1) = v22;
        *(_QWORD *)&v24 = v19;
        if ( a5
          || (((void (__fastcall *)(int *))v11)(&v16), v7 = v16 | 0x40000, (v16 | 0x40000) == v16)
          || ((unsigned int (__fastcall *)(_QWORD))v6)(v7) )
        {
          v14 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v31, v25);
          v8 = v14;
          if ( !v14 )
            goto LABEL_16;
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          if ( v8 >= 0 )
LABEL_16:
            v8 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v16 != v7 )
    v6();
  if ( v5 )
    CloseHandle(v5);
  if ( hModule )
    FreeLibrary(hModule);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000b8c8  push    rbp
0x14000b8ca  push    rbx
0x14000b8cb  push    rsi
0x14000b8cc  push    rdi
0x14000b8cd  push    r12
0x14000b8cf  push    r13
0x14000b8d1  push    r15
0x14000b8d3  lea     rbp, [rsp-10h]
0x14000b8d8  sub     rsp, 110h
0x14000b8df  mov     rax, cs:__security_cookie
0x14000b8e6  xor     rax, rsp
0x14000b8e9  mov     [rbp+40h+var_40], rax
0x14000b8ed  mov     [rsp+140h+lpBuffer], rdx
0x14000b8f2  xor     edx, edx; Val
0x14000b8f4  mov     [rsp+140h+var_100], r8d
0x14000b8f9  mov     [rsp+140h+Str], rcx
0x14000b8fe  lea     rcx, [rbp+40h+var_B0]; void *
0x14000b902  mov     [rsp+140h+var_E0], r9
0x14000b907  lea     r8d, [rdx+58h]; Size
0x14000b90b  mov     [rbp+40h+var_50], 0AAC56Bh
0x14000b912  mov     [rbp+40h+var_4C], 11D0CD44h
0x14000b919  mov     [rbp+40h+var_48], 0C000C28Ch
0x14000b920  mov     [rbp+40h+var_44], 0EE95C24Fh
0x14000b927  call    memset_0
0x14000b92c  xorps   xmm0, xmm0
0x14000b92f  lea     rdx, [rsp+140h+hModule]
0x14000b934  xor     edi, edi
0x14000b936  lea     rcx, aWintrustDll; "wintrust.dll"
0x14000b93d  movups  [rsp+140h+var_D8], xmm0
0x14000b942  mov     [rsp+140h+var_F8], rdi
0x14000b947  xor     r15d, r15d
0x14000b94a  movups  [rsp+140h+var_C8], xmm0
0x14000b94f  mov     [rsp+140h+hModule], rdi
0x14000b954  xor     esi, esi
0x14000b956  mov     [rsp+140h+var_110], edi
0x14000b95a  call    SafeLoadLibrary
0x14000b95f  mov     ebx, eax
0x14000b961  test    eax, eax
0x14000b963  js      loc_14000BADF
0x14000b969  mov     rcx, [rsp+140h+hModule]; hModule
0x14000b96e  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x14000b975  call    cs:__imp_GetProcAddress
0x14000b97b  mov     r13, rax
0x14000b97e  test    rax, rax
0x14000b981  jnz     short loc_14000B9A1
0x14000b983  call    cs:__imp_GetLastError
0x14000b989  mov     ebx, eax
0x14000b98b  test    eax, eax
0x14000b98d  jle     loc_14000BADF
0x14000b993  movzx   ebx, ax
0x14000b996  or      ebx, 80070000h
0x14000b99c  jmp     loc_14000BADF
0x14000b9a1  mov     rcx, [rsp+140h+hModule]; hModule
0x14000b9a6  lea     rdx, aWintrustgetreg; "WintrustGetRegPolicyFlags"
0x14000b9ad  call    cs:__imp_GetProcAddress
0x14000b9b3  mov     r12, rax
0x14000b9b6  test    rax, rax
0x14000b9b9  jz      short loc_14000B983
0x14000b9bb  mov     rcx, [rsp+140h+hModule]; hModule
0x14000b9c0  lea     rdx, aWintrustsetreg; "WintrustSetRegPolicyFlags"
0x14000b9c7  call    cs:__imp_GetProcAddress
0x14000b9cd  mov     r15, rax
0x14000b9d0  test    rax, rax
0x14000b9d3  jz      short loc_14000B983
0x14000b9d5  mov     rdi, [rsp+140h+Str]
0x14000b9da  mov     edx, 2Eh ; '.'; Ch
0x14000b9df  mov     rcx, rdi; Str
0x14000b9e2  call    cs:__imp_wcsrchr
0x14000b9e8  mov     r8d, [rsp+140h+var_100]
0x14000b9ed  lea     r9, [rsp+140h+var_F8]
0x14000b9f2  mov     rdx, [rsp+140h+lpBuffer]; lpBuffer
0x14000b9f7  mov     rcx, rax; lpWideCharStr
0x14000b9fa  mov     [rsp+140h+lpPathName], rsi; lpPathName
0x14000b9ff  call    SafeCreateTempFile
0x14000ba04  mov     ebx, eax
0x14000ba06  test    eax, eax
0x14000ba08  js      loc_14000BADA
0x14000ba0e  mov     ebx, 58h ; 'X'
0x14000ba13  lea     rcx, [rbp+40h+var_B0]; void *
0x14000ba17  mov     r8d, ebx; Size
0x14000ba1a  xor     edx, edx; Val
0x14000ba1c  call    memset_0
0x14000ba21  mov     edx, [rbp+40h+arg_20]
0x14000ba24  xor     r8d, r8d
0x14000ba27  mov     eax, edx
0x14000ba29  mov     qword ptr [rsp+140h+var_D8+8], rdi
0x14000ba2e  mov     rdi, [rsp+140h+var_F8]
0x14000ba33  neg     eax
0x14000ba35  lea     rax, [rsp+140h+var_D8]
0x14000ba3a  mov     [rbp+40h+var_B0], ebx
0x14000ba3d  sbb     ecx, ecx
0x14000ba3f  mov     [rbp+40h+var_88], rax
0x14000ba43  mov     rax, [rsp+140h+var_E0]
0x14000ba48  add     ecx, 2
0x14000ba4b  mov     [rbp+40h+var_94], r8d
0x14000ba4f  mov     [rbp+40h+var_80], r8d
0x14000ba53  mov     [rbp+40h+var_78], r8
0x14000ba57  mov     [rbp+40h+var_70], r8
0x14000ba5b  mov     [rbp+40h+var_98], ecx
0x14000ba5e  mov     [rbp+40h+var_68], r8d
0x14000ba62  mov     [rbp+40h+var_90], 1
0x14000ba69  mov     qword ptr [rsp+140h+var_D8], 20h ; ' '
0x14000ba72  mov     qword ptr [rbp+40h+var_C8+8], rax
0x14000ba76  mov     qword ptr [rsp+140h+var_C8], rdi
0x14000ba7b  test    edx, edx
0x14000ba7d  jnz     short loc_14000BAAF
0x14000ba7f  lea     rcx, [rsp+140h+var_110]
0x14000ba84  mov     rax, r12
0x14000ba87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba8c  mov     esi, [rsp+140h+var_110]
0x14000ba90  bts     esi, 12h
0x14000ba94  cmp     esi, [rsp+140h+var_110]
0x14000ba98  jz      short loc_14000BAAF
0x14000ba9a  mov     ecx, esi
0x14000ba9c  mov     rax, r15
0x14000ba9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000baa4  test    eax, eax
0x14000baa6  jnz     short loc_14000BAAF
0x14000baa8  mov     ebx, 80004005h
0x14000baad  jmp     short loc_14000BADF
0x14000baaf  lea     r8, [rbp+40h+var_B0]
0x14000bab3  xor     ecx, ecx
0x14000bab5  lea     rdx, [rbp+40h+var_50]
0x14000bab9  mov     rax, r13
0x14000babc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bac1  mov     ebx, eax
0x14000bac3  test    eax, eax
0x14000bac5  jz      short loc_14000BAD6
0x14000bac7  jle     short loc_14000BAD2
0x14000bac9  movzx   ebx, ax
0x14000bacc  or      ebx, 80070000h
0x14000bad2  test    ebx, ebx
0x14000bad4  js      short loc_14000BADF
0x14000bad6  xor     ebx, ebx
0x14000bad8  jmp     short loc_14000BADF
0x14000bada  mov     rdi, [rsp+140h+var_F8]
0x14000badf  mov     ecx, [rsp+140h+var_110]
0x14000bae3  cmp     ecx, esi
0x14000bae5  jz      short loc_14000BAEF
0x14000bae7  mov     rax, r15
0x14000baea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000baef  test    rdi, rdi
0x14000baf2  jz      short loc_14000BAFD
0x14000baf4  mov     rcx, rdi; hObject
0x14000baf7  call    cs:__imp_CloseHandle
0x14000bafd  cmp     [rsp+140h+hModule], 0
0x14000bb03  jz      short loc_14000BB10
0x14000bb05  mov     rcx, [rsp+140h+hModule]; hLibModule
0x14000bb0a  call    cs:__imp_FreeLibrary
0x14000bb10  mov     eax, ebx
0x14000bb12  mov     rcx, [rbp+40h+var_40]
0x14000bb16  xor     rcx, rsp; StackCookie
0x14000bb19  call    __security_check_cookie
0x14000bb1e  add     rsp, 110h
0x14000bb25  pop     r15
0x14000bb27  pop     r13
0x14000bb29  pop     r12
0x14000bb2b  pop     rdi
0x14000bb2c  pop     rsi
0x14000bb2d  pop     rbx
0x14000bb2e  pop     rbp
0x14000bb2f  retn
```
