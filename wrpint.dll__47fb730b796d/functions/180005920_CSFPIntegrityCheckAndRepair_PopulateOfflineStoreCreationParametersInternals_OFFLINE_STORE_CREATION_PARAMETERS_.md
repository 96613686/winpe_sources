# CSFPIntegrityCheckAndRepair::PopulateOfflineStoreCreationParametersInternals(_OFFLINE_STORE_CREATION_PARAMETERS *,ushort const *,ushort const *,IMalloc *)

- ea: `0x180005920`
- end: `0x1800060d0`
- name: `?PopulateOfflineStoreCreationParametersInternals@CSFPIntegrityCheckAndRepair@@EEAAJPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEBG1PEAUIMalloc@@@Z`
- size: `1968`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, struct _OFFLINE_STORE_CREATION_PARAMETERS *, const unsigned __int16 *, const unsigned __int16 *, struct IMalloc *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180001de0`
- `0x180005920`
- `0x180007288`
- `0x180010750`
- `0x180010de4`
- `0x180011364`
- `0x180013b2c`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005df9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005df9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005e40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005e40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e33`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005e6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ea1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ed5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f37`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f61`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f8b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005e6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ea1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005ed5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f37`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f61`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005f8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006012`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180006012`

## string_xrefs

- `0x180005d23`: `system32\ntoskrnl.exe`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::PopulateOfflineStoreCreationParametersInternals(
        CSFPIntegrityCheckAndRepair *this,
        struct _OFFLINE_STORE_CREATION_PARAMETERS *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IMalloc *a5)
{
  LPCWSTR v8; // r15
  int v9; // ebx
  __int64 v10; // rcx
  unsigned __int16 v11; // si
  unsigned int v12; // eax
  int v13; // ecx
  LSTATUS v14; // ebx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v18; // [rsp+40h] [rbp-C0h]
  LPCWSTR v19; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[524]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  lpFileName = 0;
  v16 = 0;
  LOWORD(cbData) = 0;
  v18 = 0;
  v19 = 0;
  v8 = 0;
  v9 = SczPublicAllocFromSz(&v16, a5, a3);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 2) = v16;
  v16 = 0;
  v9 = SczPublicAllocFromSz(&v16, a5, a4);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 3) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 2));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 5) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 5));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 6) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 8));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 7) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 11));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 8) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 17));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 10) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 14));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 9) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 20));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 11) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, L"HKEY_LOCAL_MACHINE\\");
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, *((_QWORD *)this + 23));
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 13) = v16;
  v10 = *((_QWORD *)this + 4);
  v16 = 0;
  v9 = WrpRegQueryStringValue(v10, L"Microsoft\\Windows NT\\CurrentVersion\\", L"SystemRoot", &lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczPublicAllocFromSz(&v16, a5, lpFileName);
  if ( v9 < 0 )
    goto LABEL_73;
  *((_QWORD *)a2 + 4) = v16;
  v16 = 0;
  v9 = SczAllocFromSz(&lpFileName, a4);
  if ( v9 < 0 )
    goto LABEL_73;
  v9 = SczAllocConcatSz(&lpFileName, L"system32\\ntoskrnl.exe");
  if ( v9 < 0 )
    goto LABEL_73;
  if ( (int)FileExecutableArchitecture(lpFileName) < 0
    || (v11 = cbData, (_WORD)cbData != 332)
    && (_WORD)cbData != 512
    && ((v12 = (unsigned __int16)cbData, (unsigned __int16)(cbData - 448) > 4u)
     || (v13 = 21, LOWORD(v12) = cbData - 448, !_bittest(&v13, v12)))
    && (_WORD)cbData != 0x8664
    && (_WORD)cbData != 0xAA64 )
  {
    hKey = 0;
    *(_DWORD *)Data = 0;
    memset_0(v23, 0, 0x206u);
    cbData = 520;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Session Manager\\Environment",
           0,
           0xF003Fu,
           &hKey) )
    {
      goto LABEL_39;
    }
    v14 = RegQueryValueExW(hKey, L"PROCESSOR_ARCHITECTURE", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
    if ( v14 )
      goto LABEL_39;
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"x86", -1) == 2 )
    {
      v11 = 332;
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"amd64", -1) == 2 )
    {
      v11 = -31132;
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"ia64", -1) == 2 )
    {
      v11 = 512;
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"arm", -1) == 2
           || CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"armnt", -1) == 2
           || CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"thumb", -1) == 2 )
    {
      v11 = 448;
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"arm64", -1) != 2 )
        goto LABEL_39;
      v11 = -21916;
    }
  }
  switch ( v11 )
  {
    case 0x14Cu:
      *((_DWORD *)a2 + 24) = 0;
      break;
    case 0x1C0u:
    case 0x1C2u:
    case 0x1C4u:
      *((_DWORD *)a2 + 24) = 5;
      break;
    case 0x200u:
      *((_DWORD *)a2 + 24) = 6;
      break;
    case 0x8664u:
      *((_DWORD *)a2 + 24) = 9;
      break;
    case 0xAA64u:
      *((_DWORD *)a2 + 24) = 12;
      break;
    default:
LABEL_39:
      v9 = -2147024846;
      goto LABEL_73;
  }
  v9 = -2147213311;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( (int)SczAllocFromSz(&v19, Buffer) < 0 || (int)SczAllocConcatSz(&v19, L"\\ntoskrnl.exe") < 0 )
    {
      v8 = v19;
    }
    else
    {
      v8 = v19;
      if ( (int)FileExecutableArchitecture(v19) >= 0 && v18 == v11 )
        v9 = 0;
    }
  }
LABEL_73:
  if ( a5 && v16 )
    ((void (__fastcall *)(struct IMalloc *))a5->lpVtbl->Free)(a5);
  if ( lpFileName )
    operator delete((void *)(lpFileName - 4));
  if ( v8 )
    operator delete((void *)(v8 - 4));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005920  push    rbp
0x180005922  push    rbx
0x180005923  push    rsi
0x180005924  push    rdi
0x180005925  push    r12
0x180005927  push    r13
0x180005929  push    r14
0x18000592b  push    r15
0x18000592d  lea     rbp, [rsp-398h]
0x180005935  sub     rsp, 498h
0x18000593c  mov     rax, cs:__security_cookie
0x180005943  xor     rax, rsp
0x180005946  mov     [rbp+3D0h+var_50], rax
0x18000594d  mov     r14, [rbp+3D0h+arg_20]
0x180005954  xor     r13d, r13d
0x180005957  mov     rdi, rdx
0x18000595a  mov     [rsp+4D0h+lpFileName], r13
0x18000595f  mov     rsi, rcx
0x180005962  mov     [rsp+4D0h+var_4A0], r13
0x180005967  mov     rdx, r14
0x18000596a  mov     word ptr [rsp+4D0h+cbData], r13w
0x180005970  lea     rcx, [rsp+4D0h+var_4A0]
0x180005975  mov     [rsp+4D0h+var_490], r13w
0x18000597b  mov     r12, r9
0x18000597e  mov     [rsp+4D0h+var_488], r13
0x180005983  mov     r15d, r13d
0x180005986  call    SczPublicAllocFromSz
0x18000598b  mov     ebx, eax
0x18000598d  test    eax, eax
0x18000598f  js      loc_18000606C
0x180005995  mov     rax, [rsp+4D0h+var_4A0]
0x18000599a  lea     rcx, [rsp+4D0h+var_4A0]
0x18000599f  mov     r8, r12
0x1800059a2  mov     [rdi+10h], rax
0x1800059a6  mov     rdx, r14
0x1800059a9  mov     [rsp+4D0h+var_4A0], r13
0x1800059ae  call    SczPublicAllocFromSz
0x1800059b3  mov     ebx, eax
0x1800059b5  test    eax, eax
0x1800059b7  js      loc_18000606C
0x1800059bd  mov     rax, [rsp+4D0h+var_4A0]
0x1800059c2  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x1800059c9  lea     rcx, [rsp+4D0h+lpFileName]
0x1800059ce  mov     [rdi+18h], rax
0x1800059d2  mov     [rsp+4D0h+var_4A0], r13
0x1800059d7  call    SczAllocFromSz
0x1800059dc  mov     ebx, eax
0x1800059de  test    eax, eax
0x1800059e0  js      loc_18000606C
0x1800059e6  mov     rdx, [rsi+10h]
0x1800059ea  lea     rcx, [rsp+4D0h+lpFileName]
0x1800059ef  call    SczAllocConcatSz
0x1800059f4  mov     ebx, eax
0x1800059f6  test    eax, eax
0x1800059f8  js      loc_18000606C
0x1800059fe  mov     r8, [rsp+4D0h+lpFileName]
0x180005a03  lea     rcx, [rsp+4D0h+var_4A0]
0x180005a08  mov     rdx, r14
0x180005a0b  call    SczPublicAllocFromSz
0x180005a10  mov     ebx, eax
0x180005a12  test    eax, eax
0x180005a14  js      loc_18000606C
0x180005a1a  mov     rax, [rsp+4D0h+var_4A0]
0x180005a1f  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005a26  lea     rcx, [rsp+4D0h+lpFileName]
0x180005a2b  mov     [rdi+28h], rax
0x180005a2f  mov     [rsp+4D0h+var_4A0], r13
0x180005a34  call    SczAllocFromSz
0x180005a39  mov     ebx, eax
0x180005a3b  test    eax, eax
0x180005a3d  js      loc_18000606C
0x180005a43  mov     rdx, [rsi+28h]
0x180005a47  lea     rcx, [rsp+4D0h+lpFileName]
0x180005a4c  call    SczAllocConcatSz
0x180005a51  mov     ebx, eax
0x180005a53  test    eax, eax
0x180005a55  js      loc_18000606C
0x180005a5b  mov     r8, [rsp+4D0h+lpFileName]
0x180005a60  lea     rcx, [rsp+4D0h+var_4A0]
0x180005a65  mov     rdx, r14
0x180005a68  call    SczPublicAllocFromSz
0x180005a6d  mov     ebx, eax
0x180005a6f  test    eax, eax
0x180005a71  js      loc_18000606C
0x180005a77  mov     rax, [rsp+4D0h+var_4A0]
0x180005a7c  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005a83  lea     rcx, [rsp+4D0h+lpFileName]
0x180005a88  mov     [rdi+30h], rax
0x180005a8c  mov     [rsp+4D0h+var_4A0], r13
0x180005a91  call    SczAllocFromSz
0x180005a96  mov     ebx, eax
0x180005a98  test    eax, eax
0x180005a9a  js      loc_18000606C
0x180005aa0  mov     rdx, [rsi+40h]
0x180005aa4  lea     rcx, [rsp+4D0h+lpFileName]
0x180005aa9  call    SczAllocConcatSz
0x180005aae  mov     ebx, eax
0x180005ab0  test    eax, eax
0x180005ab2  js      loc_18000606C
0x180005ab8  mov     r8, [rsp+4D0h+lpFileName]
0x180005abd  lea     rcx, [rsp+4D0h+var_4A0]
0x180005ac2  mov     rdx, r14
0x180005ac5  call    SczPublicAllocFromSz
0x180005aca  mov     ebx, eax
0x180005acc  test    eax, eax
0x180005ace  js      loc_18000606C
0x180005ad4  mov     rax, [rsp+4D0h+var_4A0]
0x180005ad9  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005ae0  lea     rcx, [rsp+4D0h+lpFileName]
0x180005ae5  mov     [rdi+38h], rax
0x180005ae9  mov     [rsp+4D0h+var_4A0], r13
0x180005aee  call    SczAllocFromSz
0x180005af3  mov     ebx, eax
0x180005af5  test    eax, eax
0x180005af7  js      loc_18000606C
0x180005afd  mov     rdx, [rsi+58h]
0x180005b01  lea     rcx, [rsp+4D0h+lpFileName]
0x180005b06  call    SczAllocConcatSz
0x180005b0b  mov     ebx, eax
0x180005b0d  test    eax, eax
0x180005b0f  js      loc_18000606C
0x180005b15  mov     r8, [rsp+4D0h+lpFileName]
0x180005b1a  lea     rcx, [rsp+4D0h+var_4A0]
0x180005b1f  mov     rdx, r14
0x180005b22  call    SczPublicAllocFromSz
0x180005b27  mov     ebx, eax
0x180005b29  test    eax, eax
0x180005b2b  js      loc_18000606C
0x180005b31  mov     rax, [rsp+4D0h+var_4A0]
0x180005b36  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005b3d  lea     rcx, [rsp+4D0h+lpFileName]
0x180005b42  mov     [rdi+40h], rax
0x180005b46  mov     [rsp+4D0h+var_4A0], r13
0x180005b4b  call    SczAllocFromSz
0x180005b50  mov     ebx, eax
0x180005b52  test    eax, eax
0x180005b54  js      loc_18000606C
0x180005b5a  mov     rdx, [rsi+88h]
0x180005b61  lea     rcx, [rsp+4D0h+lpFileName]
0x180005b66  call    SczAllocConcatSz
0x180005b6b  mov     ebx, eax
0x180005b6d  test    eax, eax
0x180005b6f  js      loc_18000606C
0x180005b75  mov     r8, [rsp+4D0h+lpFileName]
0x180005b7a  lea     rcx, [rsp+4D0h+var_4A0]
0x180005b7f  mov     rdx, r14
0x180005b82  call    SczPublicAllocFromSz
0x180005b87  mov     ebx, eax
0x180005b89  test    eax, eax
0x180005b8b  js      loc_18000606C
0x180005b91  mov     rax, [rsp+4D0h+var_4A0]
0x180005b96  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005b9d  lea     rcx, [rsp+4D0h+lpFileName]
0x180005ba2  mov     [rdi+50h], rax
0x180005ba6  mov     [rsp+4D0h+var_4A0], r13
0x180005bab  call    SczAllocFromSz
0x180005bb0  mov     ebx, eax
0x180005bb2  test    eax, eax
0x180005bb4  js      loc_18000606C
0x180005bba  mov     rdx, [rsi+70h]
0x180005bbe  lea     rcx, [rsp+4D0h+lpFileName]
0x180005bc3  call    SczAllocConcatSz
0x180005bc8  mov     ebx, eax
0x180005bca  test    eax, eax
0x180005bcc  js      loc_18000606C
0x180005bd2  mov     r8, [rsp+4D0h+lpFileName]
0x180005bd7  lea     rcx, [rsp+4D0h+var_4A0]
0x180005bdc  mov     rdx, r14
0x180005bdf  call    SczPublicAllocFromSz
0x180005be4  mov     ebx, eax
0x180005be6  test    eax, eax
0x180005be8  js      loc_18000606C
0x180005bee  mov     rax, [rsp+4D0h+var_4A0]
0x180005bf3  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005bfa  lea     rcx, [rsp+4D0h+lpFileName]
0x180005bff  mov     [rdi+48h], rax
0x180005c03  mov     [rsp+4D0h+var_4A0], r13
0x180005c08  call    SczAllocFromSz
0x180005c0d  mov     ebx, eax
0x180005c0f  test    eax, eax
0x180005c11  js      loc_18000606C
0x180005c17  mov     rdx, [rsi+0A0h]
0x180005c1e  lea     rcx, [rsp+4D0h+lpFileName]
0x180005c23  call    SczAllocConcatSz
0x180005c28  mov     ebx, eax
0x180005c2a  test    eax, eax
0x180005c2c  js      loc_18000606C
0x180005c32  mov     r8, [rsp+4D0h+lpFileName]
0x180005c37  lea     rcx, [rsp+4D0h+var_4A0]
0x180005c3c  mov     rdx, r14
0x180005c3f  call    SczPublicAllocFromSz
0x180005c44  mov     ebx, eax
0x180005c46  test    eax, eax
0x180005c48  js      loc_18000606C
0x180005c4e  mov     rax, [rsp+4D0h+var_4A0]
0x180005c53  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\"
0x180005c5a  lea     rcx, [rsp+4D0h+lpFileName]
0x180005c5f  mov     [rdi+58h], rax
0x180005c63  mov     [rsp+4D0h+var_4A0], r13
0x180005c68  call    SczAllocFromSz
0x180005c6d  mov     ebx, eax
0x180005c6f  test    eax, eax
0x180005c71  js      loc_18000606C
0x180005c77  mov     rdx, [rsi+0B8h]
0x180005c7e  lea     rcx, [rsp+4D0h+lpFileName]
0x180005c83  call    SczAllocConcatSz
0x180005c88  mov     ebx, eax
0x180005c8a  test    eax, eax
0x180005c8c  js      loc_18000606C
0x180005c92  mov     r8, [rsp+4D0h+lpFileName]
0x180005c97  lea     rcx, [rsp+4D0h+var_4A0]
0x180005c9c  mov     rdx, r14
0x180005c9f  call    SczPublicAllocFromSz
0x180005ca4  mov     ebx, eax
0x180005ca6  test    eax, eax
0x180005ca8  js      loc_18000606C
0x180005cae  mov     rax, [rsp+4D0h+var_4A0]
0x180005cb3  lea     r9, [rsp+4D0h+lpFileName]
0x180005cb8  mov     [rdi+68h], rax
0x180005cbc  lea     r8, aSystemroot; "SystemRoot"
0x180005cc3  mov     rcx, [rsi+20h]
0x180005cc7  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows NT\\CurrentVersion\\"
0x180005cce  mov     [rsp+4D0h+var_4A0], r13
0x180005cd3  call    WrpRegQueryStringValue
0x180005cd8  mov     ebx, eax
0x180005cda  test    eax, eax
0x180005cdc  js      loc_18000606C
0x180005ce2  mov     r8, [rsp+4D0h+lpFileName]
0x180005ce7  lea     rcx, [rsp+4D0h+var_4A0]
0x180005cec  mov     rdx, r14
0x180005cef  call    SczPublicAllocFromSz
0x180005cf4  mov     ebx, eax
0x180005cf6  test    eax, eax
0x180005cf8  js      loc_18000606C
0x180005cfe  mov     rax, [rsp+4D0h+var_4A0]
0x180005d03  lea     rcx, [rsp+4D0h+lpFileName]
0x180005d08  mov     rdx, r12
0x180005d0b  mov     [rdi+20h], rax
0x180005d0f  mov     [rsp+4D0h+var_4A0], r13
0x180005d14  call    SczAllocFromSz
0x180005d19  mov     ebx, eax
0x180005d1b  test    eax, eax
0x180005d1d  js      loc_18000606C
0x180005d23  lea     rdx, aSystem32Ntoskr; "system32\\ntoskrnl.exe"
0x180005d2a  lea     rcx, [rsp+4D0h+lpFileName]
0x180005d2f  call    SczAllocConcatSz
0x180005d34  mov     ebx, eax
0x180005d36  test    eax, eax
0x180005d38  js      loc_18000606C
0x180005d3e  mov     rcx, [rsp+4D0h+lpFileName]; lpFileName
0x180005d43  lea     rdx, [rsp+4D0h+cbData]
0x180005d48  call    FileExecutableArchitecture
0x180005d4d  lea     r12d, [r13+2]
0x180005d51  mov     ecx, 14Ch
0x180005d56  mov     edx, 8664h
0x180005d5b  mov     r8d, 200h
0x180005d61  mov     r10d, 0AA64h
0x180005d67  lea     r9d, [rcx+74h]
0x180005d6b  test    eax, eax
0x180005d6d  js      short loc_180005DB4
0x180005d6f  movzx   esi, word ptr [rsp+4D0h+cbData]
0x180005d74  cmp     si, cx
0x180005d77  jz      loc_180005FA6
0x180005d7d  cmp     si, r8w
0x180005d81  jz      loc_180005FA6
0x180005d87  movzx   eax, si
0x180005d8a  sub     ax, r9w
0x180005d8e  cmp     ax, 4
0x180005d92  ja      short loc_180005DA1
0x180005d94  lea     ecx, [r13+15h]
0x180005d98  bt      ecx, eax
0x180005d9b  jb      loc_180005FA6
0x180005da1  cmp     si, dx
0x180005da4  jz      loc_180005FA6
0x180005daa  cmp     si, r10w
0x180005dae  jz      loc_180005FA6
0x180005db4  xor     edx, edx; Val
0x180005db6  mov     [rsp+4D0h+hKey], r13
0x180005dbb  mov     r8d, 206h; Size
0x180005dc1  mov     dword ptr [rsp+4D0h+Data], r13d
0x180005dc6  lea     rcx, [rsp+4D0h+var_46C]; void *
0x180005dcb  call    memset_0
0x180005dd0  lea     rax, [rsp+4D0h+hKey]
0x180005dd5  mov     [rsp+4D0h+cbData], 208h
0x180005ddd  mov     r9d, 0F003Fh; samDesired
0x180005de3  mov     [rsp+4D0h+phkResult], rax; phkResult
0x180005de8  xor     r8d, r8d; ulOptions
0x180005deb  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ses"...
0x180005df2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005df9  call    cs:__imp_RegOpenKeyExW
0x180005dff  test    eax, eax
0x180005e01  jz      short loc_180005E0D
0x180005e03  mov     ebx, 80070032h
0x180005e08  jmp     loc_18000606C
0x180005e0d  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180005e12  lea     rax, [rsp+4D0h+cbData]
0x180005e17  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x180005e1c  lea     rdx, ValueName; "PROCESSOR_ARCHITECTURE"
0x180005e23  lea     rax, [rsp+4D0h+Data]
0x180005e28  xor     r9d, r9d; lpType
  ... truncated ...
```
