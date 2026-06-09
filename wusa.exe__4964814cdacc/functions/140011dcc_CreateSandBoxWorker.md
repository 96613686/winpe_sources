# CreateSandBoxWorker

- ea: `0x140011dcc`
- end: `0x1400121ea`
- name: `CreateSandBoxWorker`
- size: `1054`
- prototype: `__int64 __fastcall(const char *, WCHAR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140013020`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x14000e280`
- `0x140011d18`
- `0x140011dcc`
- `0x140012818`
- `0x140012a80`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x140011f1b`
- `ADVAPI32!CryptAcquireContextW` at `0x140011f1b`
- `ADVAPI32!CryptGenRandom` at `0x140011f62`
- `ADVAPI32!CryptGenRandom` at `0x140011f62`
- `ADVAPI32!DecryptFileA` at `0x1400120cd`
- `ADVAPI32!DecryptFileA` at `0x1400120cd`
- `ADVAPI32!CryptReleaseContext` at `0x14001216d`
- `ADVAPI32!CryptReleaseContext` at `0x14001216d`
- `KERNEL32!LocalFree` at `0x140011edf`
- `KERNEL32!LocalFree` at `0x1400121b2`
- `KERNEL32!LocalFree` at `0x140011edf`
- `KERNEL32!LocalFree` at `0x1400121b2`
- `KERNEL32!CreateDirectoryA` at `0x140012048`
- `KERNEL32!CreateDirectoryA` at `0x140012048`
- `KERNEL32!GetFileAttributesA` at `0x140012094`
- `KERNEL32!GetFileAttributesA` at `0x140012094`
- `KERNEL32!MultiByteToWideChar` at `0x140012116`
- `KERNEL32!MultiByteToWideChar` at `0x140012116`
- `KERNEL32!GetLastError` at `0x140011f25`
- `KERNEL32!GetLastError` at `0x140011f6c`
- `KERNEL32!GetLastError` at `0x140012052`
- `KERNEL32!GetLastError` at `0x14001209f`
- `KERNEL32!GetLastError` at `0x1400120d7`
- `KERNEL32!GetLastError` at `0x140012120`
- `KERNEL32!GetLastError` at `0x140011f25`
- `KERNEL32!GetLastError` at `0x140011f6c`
- `KERNEL32!GetLastError` at `0x140012052`
- `KERNEL32!GetLastError` at `0x14001209f`
- `KERNEL32!GetLastError` at `0x1400120d7`
- `KERNEL32!GetLastError` at `0x140012120`

## string_xrefs

- `0x140011e8e`: `Failed to build security attributes, error code %u`
- `0x140011e99`: `CSecurityAttribute::GetSecurityAttributes`
- `0x140011ecb`: `CSecurityAttribute::GetSecurityAttributes`
- `0x140011e3f`: `Failed to allocate memory for temp path`
- `0x140011e35`: `CreateSandBoxWorker`
- `0x140011e6c`: `CreateSandBoxWorker`
- `0x140011ee5`: `Failed to build security attribute for sandbox`
- `0x140012031`: `Failed to build sandbox directory name`
- `0x140012020`: `Failed to build sandbox full path`
- `0x140012067`: `Failed to create directory %S, error code %u`
- `0x1400120b4`: `Failed to get directory attributes for %s, error code 0X%x`
- `0x1400120ec`: `Failed to decrypt directory %S, error code %u`

## pseudocode

```c
__int64 __fastcall CreateSandBoxWorker(const char *a1, WCHAR *a2)
{
  char *v3; // rax
  char *v4; // rsi
  signed int v5; // ebx
  __int64 v6; // r15
  struct _SECURITY_ATTRIBUTES *v7; // r14
  int v8; // eax
  HLOCAL v9; // r14
  const char *v10; // r8
  __int64 v11; // rdx
  signed int LastError; // eax
  signed int v13; // eax
  __int64 v14; // r9
  const char *v15; // r8
  __int64 v16; // rdx
  int v17; // r12d
  signed int v18; // eax
  const char *v19; // r8
  __int64 v20; // rdx
  DWORD FileAttributesA; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  HLOCAL v25; // rsi
  HLOCAL hMem; // [rsp+30h] [rbp-79h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-71h] BYREF
  LPWSTR lpWideCharStr; // [rsp+40h] [rbp-69h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes[2]; // [rsp+48h] [rbp-61h] BYREF
  __int128 v31; // [rsp+58h] [rbp-51h]
  __int128 v32; // [rsp+68h] [rbp-41h]
  int v33; // [rsp+78h] [rbp-31h]
  _OWORD v34[2]; // [rsp+80h] [rbp-29h] BYREF
  char v35; // [rsp+A0h] [rbp-9h]
  BYTE pbBuffer[32]; // [rsp+A8h] [rbp-1h] BYREF

  lpWideCharStr = a2;
  phProv = 0;
  v33 = 256;
  *(_OWORD *)lpSecurityAttributes = 0;
  v31 = 0;
  v32 = 0;
  v3 = (char *)operator new(0x104u);
  v4 = v3;
  if ( !v3 )
  {
    WusaLogDebugEventA(L"CreateSandBoxWorker", 381, "Failed to allocate memory for temp path");
    v5 = -2147024882;
LABEL_54:
    hMem = 0;
    WusaGetErrorMessage(v5, (unsigned __int16 **)&hMem);
    v25 = hMem;
    WusaLogDebugEventA(L"CreateSandBoxWorker", 442, "Exit with error code 0X%x (%ls)", v5, (const wchar_t *)hMem);
    if ( v25 )
      LocalFree(v25);
    goto LABEL_56;
  }
  v6 = 0;
  memset_0(v3, 0, 0x104u);
  v7 = lpSecurityAttributes[0];
  if ( !lpSecurityAttributes[0] )
  {
    v8 = CSecurityAttribute::SecurityAttributeBuild((CSecurityAttribute *)lpSecurityAttributes);
    v5 = v8;
    if ( v8 < 0 )
    {
      WusaLogDebugEventA(
        L"CSecurityAttribute::GetSecurityAttributes",
        63,
        "Failed to build security attributes, error code %u",
        v8);
      hMem = 0;
      WusaGetErrorMessage(v5, (unsigned __int16 **)&hMem);
      v9 = hMem;
      WusaLogDebugEventA(
        L"CSecurityAttribute::GetSecurityAttributes",
        69,
        "Exit with error code 0X%x (%ls)",
        v5,
        (const wchar_t *)hMem);
      if ( v9 )
        LocalFree(v9);
      v10 = "Failed to build security attribute for sandbox";
      v11 = 385;
LABEL_8:
      WusaLogDebugEventA(L"CreateSandBoxWorker", v11, v10);
      goto LABEL_51;
    }
    v7 = lpSecurityAttributes[0];
  }
  if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v10 = "Failed to acquire a key container handle";
    v11 = 392;
    if ( v5 >= 0 )
      v5 = -2147467259;
    goto LABEL_8;
  }
  LODWORD(hMem) = 1;
  if ( !CryptGenRandom(phProv, 0x10u, pbBuffer) )
  {
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    v15 = "Failed to generate a random number";
    v16 = 397;
    if ( v5 >= 0 )
      v5 = -2147467259;
    goto LABEL_21;
  }
  v35 = 0;
  memset(v34, 0, sizeof(v34));
  v17 = (pbBuffer[0] & 7) + 9;
  if ( (pbBuffer[0] & 7) != 0xFFFFFFF7 )
  {
    while ( 1 )
    {
      v5 = StringCchPrintfA((char *)v34 + 2 * (int)v6, 3u, "%02x", pbBuffer[v6]);
      if ( v5 < 0 )
        break;
      v6 = (unsigned int)(v6 + 1);
      if ( (int)v6 >= v17 )
        goto LABEL_25;
    }
    v15 = "Failed to build sandbox directory name";
    v16 = 406;
    goto LABEL_21;
  }
LABEL_25:
  v5 = StringCchPrintfA(v4, 0x104u, "%s%s", a1, (const char *)v34);
  if ( v5 < 0 )
  {
    v15 = "Failed to build sandbox full path";
    v16 = 414;
LABEL_21:
    WusaLogDebugEventA(L"CreateSandBoxWorker", v16, v15, v14);
    goto LABEL_50;
  }
  if ( CreateDirectoryA(v4, v7) )
  {
    FileAttributesA = GetFileAttributesA(v4);
    if ( FileAttributesA == -1 )
    {
      v22 = GetLastError();
      v5 = v22;
      if ( v22 > 0 )
        v5 = (unsigned __int16)v22 | 0x80070000;
      v19 = "Failed to get directory attributes for %s, error code 0X%x";
      v20 = 420;
    }
    else
    {
      if ( (FileAttributesA & 0x4000) == 0 || DecryptFileA(v4, 0) )
      {
        if ( !MultiByteToWideChar(0, 0, v4, -1, lpWideCharStr, 260) )
        {
          v24 = GetLastError();
          v5 = v24;
          if ( v24 > 0 )
            v5 = (unsigned __int16)v24 | 0x80070000;
          if ( v5 >= 0 )
            v5 = -2147467259;
          WusaLogDebugEventA(L"CreateSandBoxWorker", 431, "Failed to convert ANSI to Unicode for %s", v4);
        }
        goto LABEL_50;
      }
      v23 = GetLastError();
      v5 = v23;
      if ( v23 > 0 )
        v5 = (unsigned __int16)v23 | 0x80070000;
      v19 = "Failed to decrypt directory %S, error code %u";
      v20 = 425;
    }
  }
  else
  {
    v18 = GetLastError();
    v5 = v18;
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
    v19 = "Failed to create directory %S, error code %u";
    v20 = 417;
  }
  if ( v5 >= 0 )
    v5 = -2147467259;
  WusaLogDebugEventA(L"CreateSandBoxWorker", v20, v19, v4);
LABEL_50:
  LODWORD(v6) = (_DWORD)hMem;
LABEL_51:
  operator delete(v4);
  if ( (_DWORD)v6 )
    CryptReleaseContext(phProv, 0);
  if ( v5 < 0 )
    goto LABEL_54;
LABEL_56:
  CSecurityAttribute::Clean((CSecurityAttribute *)lpSecurityAttributes);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011dcc  mov     [rsp-8+arg_10], rbx
0x140011dd1  push    rbp
0x140011dd2  push    rsi
0x140011dd3  push    rdi
0x140011dd4  push    r12
0x140011dd6  push    r13
0x140011dd8  push    r14
0x140011dda  push    r15
0x140011ddc  lea     rbp, [rsp-27h]
0x140011de1  sub     rsp, 0D0h
0x140011de8  mov     rax, cs:__security_cookie
0x140011def  xor     rax, rsp
0x140011df2  mov     [rbp+57h+var_38], rax
0x140011df6  xorps   xmm0, xmm0
0x140011df9  mov     [rbp+57h+lpWideCharStr], rdx
0x140011dfd  mov     r13, rcx
0x140011e00  mov     [rbp+57h+phProv], 0
0x140011e08  xorps   xmm1, xmm1
0x140011e0b  mov     [rbp+57h+var_88], 100h
0x140011e12  mov     ebx, 104h
0x140011e17  mov     ecx, ebx; Size
0x140011e19  movdqu  xmmword ptr [rbp+57h+lpSecurityAttributes], xmm0
0x140011e1e  movdqu  [rbp+57h+var_A8], xmm1
0x140011e23  movdqu  [rbp+57h+var_98], xmm0
0x140011e28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011e2d  mov     rsi, rax
0x140011e30  test    rax, rax
0x140011e33  jnz     short loc_140011E58
0x140011e35  lea     rdi, aCreatesandboxw; "CreateSandBoxWorker"
0x140011e3c  mov     rcx, rdi
0x140011e3f  lea     r8, aFailedToAlloca_3; "Failed to allocate memory for temp path"
0x140011e46  lea     edx, [rbx+79h]
0x140011e49  call    WusaLogDebugEventA
0x140011e4e  mov     ebx, 8007000Eh
0x140011e53  jmp     loc_140012177
0x140011e58  mov     r8, rbx; Size
0x140011e5b  xor     edx, edx; Val
0x140011e5d  mov     rcx, rsi; void *
0x140011e60  xor     r15d, r15d
0x140011e63  call    memset_0
0x140011e68  mov     r14, [rbp+57h+lpSecurityAttributes]
0x140011e6c  lea     rdi, aCreatesandboxw; "CreateSandBoxWorker"
0x140011e73  test    r14, r14
0x140011e76  jnz     loc_140011F02
0x140011e7c  lea     rcx, [rbp+57h+lpSecurityAttributes]; this
0x140011e80  call    ?SecurityAttributeBuild@CSecurityAttribute@@AEAAJXZ; CSecurityAttribute::SecurityAttributeBuild(void)
0x140011e85  mov     ebx, eax
0x140011e87  test    eax, eax
0x140011e89  jns     short loc_140011EFE
0x140011e8b  mov     r9d, eax
0x140011e8e  lea     r8, aFailedToBuildS_2; "Failed to build security attributes, er"...
0x140011e95  lea     edx, [r15+3Fh]
0x140011e99  lea     rcx, aCsecurityattri_0; "CSecurityAttribute::GetSecurityAttribut"...
0x140011ea0  call    WusaLogDebugEventA
0x140011ea5  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x140011ea9  mov     [rbp+57h+hMem], r15
0x140011ead  mov     ecx, ebx; dwMessageId
0x140011eaf  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140011eb4  mov     r14, [rbp+57h+hMem]
0x140011eb8  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140011ebf  mov     r9d, ebx
0x140011ec2  mov     qword ptr [rsp+100h+dwFlags], r14
0x140011ec7  lea     edx, [r15+45h]
0x140011ecb  lea     rcx, aCsecurityattri_0; "CSecurityAttribute::GetSecurityAttribut"...
0x140011ed2  call    WusaLogDebugEventA
0x140011ed7  test    r14, r14
0x140011eda  jz      short loc_140011EE5
0x140011edc  mov     rcx, r14; hMem
0x140011edf  call    cs:__imp_LocalFree
0x140011ee5  lea     r8, aFailedToBuildS_0; "Failed to build security attribute for "...
0x140011eec  mov     edx, 181h
0x140011ef1  mov     rcx, rdi
0x140011ef4  call    WusaLogDebugEventA
0x140011ef9  jmp     loc_14001215A
0x140011efe  mov     r14, [rbp+57h+lpSecurityAttributes]
0x140011f02  mov     ebx, 1
0x140011f07  mov     [rsp+100h+dwFlags], 0F0000000h; dwFlags
0x140011f0f  mov     r9d, ebx; dwProvType
0x140011f12  lea     rcx, [rbp+57h+phProv]; phProv
0x140011f16  xor     r8d, r8d; szProvider
0x140011f19  xor     edx, edx; szContainer
0x140011f1b  call    cs:__imp_CryptAcquireContextW
0x140011f21  test    eax, eax
0x140011f23  jnz     short loc_140011F52
0x140011f25  call    cs:__imp_GetLastError
0x140011f2b  mov     ebx, eax
0x140011f2d  test    eax, eax
0x140011f2f  jle     short loc_140011F3A
0x140011f31  movzx   ebx, ax
0x140011f34  or      ebx, 80070000h
0x140011f3a  test    ebx, ebx
0x140011f3c  lea     r8, aFailedToAcquir; "Failed to acquire a key container handl"...
0x140011f43  mov     eax, 80004005h
0x140011f48  mov     edx, 188h
0x140011f4d  cmovns  ebx, eax
0x140011f50  jmp     short loc_140011EF1
0x140011f52  mov     rcx, [rbp+57h+phProv]; hProv
0x140011f56  lea     r8, [rbp+57h+pbBuffer]; pbBuffer
0x140011f5a  mov     edx, 10h; dwLen
0x140011f5f  mov     dword ptr [rbp+57h+hMem], ebx
0x140011f62  call    cs:__imp_CryptGenRandom
0x140011f68  test    eax, eax
0x140011f6a  jnz     short loc_140011FA4
0x140011f6c  call    cs:__imp_GetLastError
0x140011f72  mov     ebx, eax
0x140011f74  test    eax, eax
0x140011f76  jle     short loc_140011F81
0x140011f78  movzx   ebx, ax
0x140011f7b  or      ebx, 80070000h
0x140011f81  test    ebx, ebx
0x140011f83  lea     r8, aFailedToGenera_0; "Failed to generate a random number"
0x140011f8a  mov     eax, 80004005h
0x140011f8f  mov     edx, 18Dh
0x140011f94  cmovns  ebx, eax
0x140011f97  mov     rcx, rdi
0x140011f9a  call    WusaLogDebugEventA
0x140011f9f  jmp     loc_140012156
0x140011fa4  movzx   r12d, [rbp+57h+pbBuffer]
0x140011fa9  xor     eax, eax
0x140011fab  xorps   xmm0, xmm0
0x140011fae  mov     [rbp+57h+var_60], al
0x140011fb1  and     r12d, 7
0x140011fb5  movups  [rbp+57h+var_80], xmm0
0x140011fb9  movups  [rbp+57h+var_70], xmm0
0x140011fbd  add     r12d, 9
0x140011fc1  jz      short loc_140011FF6
0x140011fc3  movzx   r9d, [rbp+r15+57h+pbBuffer]
0x140011fc9  lea     eax, [r15+r15]
0x140011fcd  movsxd  rcx, eax
0x140011fd0  lea     r8, a02x; "%02x"
0x140011fd7  lea     rax, [rbp+57h+var_80]
0x140011fdb  mov     edx, 3; unsigned __int64
0x140011fe0  add     rcx, rax; char *
0x140011fe3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140011fe8  mov     ebx, eax
0x140011fea  test    eax, eax
0x140011fec  js      short loc_140012031
0x140011fee  inc     r15d
0x140011ff1  cmp     r15d, r12d
0x140011ff4  jl      short loc_140011FC3
0x140011ff6  lea     rax, [rbp+57h+var_80]
0x140011ffa  mov     r15d, 104h
0x140012000  mov     edx, r15d; unsigned __int64
0x140012003  mov     qword ptr [rsp+100h+dwFlags], rax
0x140012008  mov     r9, r13
0x14001200b  lea     r8, aSS_1; "%s%s"
0x140012012  mov     rcx, rsi; char *
0x140012015  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14001201a  mov     ebx, eax
0x14001201c  test    eax, eax
0x14001201e  jns     short loc_140012042
0x140012020  lea     r8, aFailedToBuildS_3; "Failed to build sandbox full path"
0x140012027  mov     edx, 19Eh
0x14001202c  jmp     loc_140011F97
0x140012031  lea     r8, aFailedToBuildS_1; "Failed to build sandbox directory name"
0x140012038  mov     edx, 196h
0x14001203d  jmp     loc_140011F97
0x140012042  mov     rdx, r14; lpSecurityAttributes
0x140012045  mov     rcx, rsi; lpPathName
0x140012048  call    cs:__imp_CreateDirectoryA
0x14001204e  test    eax, eax
0x140012050  jnz     short loc_140012091
0x140012052  call    cs:__imp_GetLastError
0x140012058  mov     ebx, eax
0x14001205a  test    eax, eax
0x14001205c  jle     short loc_140012067
0x14001205e  movzx   ebx, ax
0x140012061  or      ebx, 80070000h
0x140012067  lea     r8, aFailedToCreate; "Failed to create directory %S, error co"...
0x14001206e  mov     edx, 1A1h
0x140012073  test    ebx, ebx
0x140012075  mov     eax, 80004005h
0x14001207a  mov     r9, rsi
0x14001207d  mov     rcx, rdi
0x140012080  cmovns  ebx, eax
0x140012083  mov     [rsp+100h+dwFlags], ebx
0x140012087  call    WusaLogDebugEventA
0x14001208c  jmp     loc_140012156
0x140012091  mov     rcx, rsi; lpFileName
0x140012094  call    cs:__imp_GetFileAttributesA
0x14001209a  cmp     eax, 0FFFFFFFFh
0x14001209d  jnz     short loc_1400120C2
0x14001209f  call    cs:__imp_GetLastError
0x1400120a5  mov     ebx, eax
0x1400120a7  test    eax, eax
0x1400120a9  jle     short loc_1400120B4
0x1400120ab  movzx   ebx, ax
0x1400120ae  or      ebx, 80070000h
0x1400120b4  lea     r8, aFailedToGetDir; "Failed to get directory attributes for "...
0x1400120bb  mov     edx, 1A4h
0x1400120c0  jmp     short loc_140012073
0x1400120c2  bt      eax, 0Eh
0x1400120c6  jnb     short loc_1400120FD
0x1400120c8  xor     edx, edx; dwReserved
0x1400120ca  mov     rcx, rsi; lpFileName
0x1400120cd  call    cs:__imp_DecryptFileA
0x1400120d3  test    eax, eax
0x1400120d5  jnz     short loc_1400120FD
0x1400120d7  call    cs:__imp_GetLastError
0x1400120dd  mov     ebx, eax
0x1400120df  test    eax, eax
0x1400120e1  jle     short loc_1400120EC
0x1400120e3  movzx   ebx, ax
0x1400120e6  or      ebx, 80070000h
0x1400120ec  lea     r8, aFailedToDecryp; "Failed to decrypt directory %S, error c"...
0x1400120f3  mov     edx, 1A9h
0x1400120f8  jmp     loc_140012073
0x1400120fd  mov     rax, [rbp+57h+lpWideCharStr]
0x140012101  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140012105  mov     [rsp+100h+cchWideChar], r15d; cchWideChar
0x14001210a  mov     r8, rsi; lpMultiByteStr
0x14001210d  xor     edx, edx; dwFlags
0x14001210f  mov     qword ptr [rsp+100h+dwFlags], rax; lpWideCharStr
0x140012114  xor     ecx, ecx; CodePage
0x140012116  call    cs:__imp_MultiByteToWideChar
0x14001211c  test    eax, eax
0x14001211e  jnz     short loc_140012156
0x140012120  call    cs:__imp_GetLastError
0x140012126  mov     ebx, eax
0x140012128  test    eax, eax
0x14001212a  jle     short loc_140012135
0x14001212c  movzx   ebx, ax
0x14001212f  or      ebx, 80070000h
0x140012135  test    ebx, ebx
0x140012137  lea     r8, aFailedToConver; "Failed to convert ANSI to Unicode for %"...
0x14001213e  mov     eax, 80004005h
0x140012143  mov     r9, rsi
0x140012146  mov     edx, 1AFh
0x14001214b  mov     rcx, rdi
0x14001214e  cmovns  ebx, eax
0x140012151  call    WusaLogDebugEventA
0x140012156  mov     r15d, dword ptr [rbp+57h+hMem]
0x14001215a  mov     rcx, rsi; Block
0x14001215d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012162  test    r15d, r15d
0x140012165  jz      short loc_140012173
0x140012167  mov     rcx, [rbp+57h+phProv]; hProv
0x14001216b  xor     edx, edx; dwFlags
0x14001216d  call    cs:__imp_CryptReleaseContext
0x140012173  test    ebx, ebx
0x140012175  jns     short loc_1400121B8
0x140012177  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x14001217b  mov     [rbp+57h+hMem], 0
0x140012183  mov     ecx, ebx; dwMessageId
0x140012185  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14001218a  mov     rsi, [rbp+57h+hMem]
0x14001218e  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140012195  mov     r9d, ebx
0x140012198  mov     qword ptr [rsp+100h+dwFlags], rsi
0x14001219d  mov     edx, 1BAh
0x1400121a2  mov     rcx, rdi
0x1400121a5  call    WusaLogDebugEventA
0x1400121aa  test    rsi, rsi
0x1400121ad  jz      short loc_1400121B8
0x1400121af  mov     rcx, rsi; hMem
0x1400121b2  call    cs:__imp_LocalFree
0x1400121b8  lea     rcx, [rbp+57h+lpSecurityAttributes]; this
0x1400121bc  call    ?Clean@CSecurityAttribute@@AEAAXXZ; CSecurityAttribute::Clean(void)
0x1400121c1  mov     eax, ebx
0x1400121c3  mov     rcx, [rbp+57h+var_38]
0x1400121c7  xor     rcx, rsp; StackCookie
0x1400121ca  call    __security_check_cookie
0x1400121cf  mov     rbx, [rsp+100h+arg_10]
0x1400121d7  add     rsp, 0D0h
0x1400121de  pop     r15
0x1400121e0  pop     r14
0x1400121e2  pop     r13
0x1400121e4  pop     r12
0x1400121e6  pop     rdi
0x1400121e7  pop     rsi
0x1400121e8  pop     rbp
0x1400121e9  retn
```
