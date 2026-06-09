# BuildUserDefinedReasonArray(_REASONDATA *,HKEY__ *,int,int)

- ea: `0x18004f1a8`
- end: `0x18004f574`
- name: `?BuildUserDefinedReasonArray@@YAHPEAU_REASONDATA@@PEAUHKEY__@@HH@Z`
- size: `972`
- prototype: `int(struct _REASONDATA *, HKEY, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18004edc0`

## callees

- `0x18001a2b8`
- `0x18004ed44`
- `0x18004f080`
- `0x18004f1a8`
- `0x18007134c`
- `0x180089d74`
- `0x180096e00`

## import_xrefs

- `ntdll!iswspace` at `0x18004f4b9`
- `ntdll!iswspace` at `0x18004f4b9`
- `ntdll!RtlFreeHeap` at `0x18004f4ff`
- `ntdll!RtlFreeHeap` at `0x18004f520`
- `ntdll!RtlFreeHeap` at `0x18004f4ff`
- `ntdll!RtlFreeHeap` at `0x18004f520`
- `ntdll!RtlAllocateHeap` at `0x18004f43f`
- `ntdll!RtlAllocateHeap` at `0x18004f43f`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18004f20f`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18004f20f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f269`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f35d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f35d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f2e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f2e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f567`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f29c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f29c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f474`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f4a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3d2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f3f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f474`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004f4a1`

## pseudocode

```c
__int64 __fastcall BuildUserDefinedReasonArray(struct _REASONDATA *a1, HKEY a2, int a3, int a4)
{
  unsigned int v8; // r14d
  DWORD i; // esi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  char *Heap; // rax
  unsigned __int16 *v16; // rbx
  const WCHAR *v17; // rdi
  int v18; // eax
  wint_t v19; // ax
  int appended; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp-84h] BYREF
  struct _REASONDATA *v30; // [rsp+80h] [rbp-80h]
  WCHAR v31[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[16]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[32]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[2]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR v35[327]; // [rsp+102h] [rbp+2h] BYREF

  wcscpy(v31, L"UserDefined");
  v30 = a1;
  hKey = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  phkResult = GetSystemDefaultLangID();
  if ( (int)StringCchPrintfW(SubKey, 0x18u, L"%s\\%d", v31, phkResult) < 0 || !a1 || !a2 )
    return 0;
  if ( RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey) && RegCreateKeyExW(a2, v31, 0, 0, 0, 0x20019u, 0, &hKey, 0)
    || RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0) )
  {
LABEL_40:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v8 = 0;
  for ( i = 0; i < cValues && v8 < 0x100; ++i )
  {
    cchValueName = 16;
    Type = 0;
    cbData = 642;
    v27 = 0;
    if ( RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData) || Type != 7 )
      continue;
    v10 = (unsigned __int64)cbData >> 1;
    ValueName[15] = 0;
    if ( v10 + 2 <= 0x141 )
    {
      v11 = 2 * v10;
      if ( v11 >= 0x282 || (*(_WORD *)&Data[v11] = 0, v12 = v11 + 2, v12 >= 0x282) )
        _report_rangecheckfailure();
      *(_WORD *)&Data[v12] = 0;
    }
    if ( !(unsigned int)ParseReasonCode(ValueName, &v27) )
      continue;
    if ( lstrlenW((LPCWSTR)Data) > 63 )
      continue;
    v13 = lstrlenW((LPCWSTR)Data);
    if ( lstrlenW(&v35[v13]) > 255 )
      continue;
    v14 = v27;
    if ( a3 )
    {
      if ( (v27 & 0x4000000) == 0 )
      {
        if ( !a4 )
          continue;
LABEL_24:
        if ( (v27 & 0x8000000) == 0 )
          continue;
      }
    }
    else if ( a4 )
    {
      goto LABEL_24;
    }
    Heap = (char *)RtlAllocateHeap(pUserHeap, 0, 0x284u);
    v16 = (unsigned __int16 *)Heap;
    if ( !Heap )
      goto LABEL_40;
    *(_DWORD *)Heap = v14;
    v17 = (const WCHAR *)(Heap + 4);
    if ( (int)StringCchCopyW((unsigned __int16 *)Heap + 2, 0x40u, (const unsigned __int16 *)Data) < 0 )
      goto LABEL_40;
    v18 = lstrlenW((LPCWSTR)Data);
    if ( (int)StringCchCopyW(v16 + 66, 0x100u, &v35[v18]) < 0 )
      goto LABEL_40;
    if ( !lstrlenW(v17) )
      goto LABEL_36;
    v19 = *v17;
    if ( !*v17 )
      goto LABEL_36;
    do
    {
      if ( !iswspace(v19) )
        break;
      v19 = *++v17;
    }
    while ( *v17 );
    if ( *v17 )
    {
      appended = AppendReason(v30, (struct _REASON *)v16);
      if ( appended == -1 )
      {
        RtlFreeHeap(pUserHeap, 0, v16);
        goto LABEL_40;
      }
      if ( appended == 1 )
        ++v8;
    }
    else
    {
LABEL_36:
      RtlFreeHeap(pUserHeap, 0, v16);
    }
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18004f1a8  mov     [rsp-8+arg_10], rbx
0x18004f1ad  push    rbp
0x18004f1ae  push    rsi
0x18004f1af  push    rdi
0x18004f1b0  push    r12
0x18004f1b2  push    r13
0x18004f1b4  push    r14
0x18004f1b6  push    r15
0x18004f1b8  lea     rbp, [rsp-2A0h]
0x18004f1c0  sub     rsp, 3A0h
0x18004f1c7  mov     rax, cs:__security_cookie
0x18004f1ce  xor     rax, rsp
0x18004f1d1  mov     [rbp+2D0h+var_40], rax
0x18004f1d8  movups  xmm0, xmmword ptr cs:aUserdefined; "UserDefined"
0x18004f1df  xor     edi, edi
0x18004f1e1  mov     r12d, r9d
0x18004f1e4  movsd   xmm1, qword ptr cs:aUserdefined+10h; "ned"
0x18004f1ec  mov     r13d, r8d
0x18004f1ef  movups  xmmword ptr [rbp+2D0h+var_348], xmm0
0x18004f1f3  mov     rbx, rdx
0x18004f1f6  mov     [rbp+2D0h+var_350], rcx
0x18004f1fa  mov     r15, rcx
0x18004f1fd  mov     [rsp+3D0h+hKey], rdi
0x18004f202  mov     [rsp+3D0h+cValues], edi
0x18004f206  mov     [rsp+3D0h+cbMaxValueLen], edi
0x18004f20a  movsd   [rbp+2D0h+var_338], xmm1
0x18004f20f  call    cs:__imp_GetSystemDefaultLangID
0x18004f215  movzx   eax, ax
0x18004f218  lea     r9, [rbp+2D0h+var_348]
0x18004f21c  lea     r8, aSD; "%s\\%d"
0x18004f223  mov     dword ptr [rsp+3D0h+phkResult], eax
0x18004f227  lea     edx, [rdi+18h]; unsigned __int64
0x18004f22a  lea     rcx, [rbp+2D0h+SubKey]; unsigned __int16 *
0x18004f22e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f233  test    eax, eax
0x18004f235  js      loc_18004F536
0x18004f23b  test    r15, r15
0x18004f23e  jz      loc_18004F536
0x18004f244  test    rbx, rbx
0x18004f247  jz      loc_18004F536
0x18004f24d  lea     rax, [rsp+3D0h+hKey]
0x18004f252  mov     esi, 20019h
0x18004f257  mov     r9d, esi; samDesired
0x18004f25a  mov     [rsp+3D0h+phkResult], rax; phkResult
0x18004f25f  xor     r8d, r8d; ulOptions
0x18004f262  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x18004f266  mov     rcx, rbx; hKey
0x18004f269  call    cs:__imp_RegOpenKeyExW
0x18004f26f  test    eax, eax
0x18004f271  jz      short loc_18004F2AA
0x18004f273  mov     [rsp+3D0h+lpdwDisposition], rdi; lpdwDisposition
0x18004f278  lea     rax, [rsp+3D0h+hKey]
0x18004f27d  mov     [rsp+3D0h+var_398], rax; phkResult
0x18004f282  lea     rdx, [rbp+2D0h+var_348]; lpSubKey
0x18004f286  mov     [rsp+3D0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004f28b  xor     r9d, r9d; lpClass
0x18004f28e  mov     [rsp+3D0h+samDesired], esi; samDesired
0x18004f292  xor     r8d, r8d; Reserved
0x18004f295  mov     rcx, rbx; hKey
0x18004f298  mov     dword ptr [rsp+3D0h+phkResult], edi; dwOptions
0x18004f29c  call    cs:__imp_RegCreateKeyExW
0x18004f2a2  test    eax, eax
0x18004f2a4  jnz     loc_18004F526
0x18004f2aa  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18004f2af  lea     rax, [rsp+3D0h+cbMaxValueLen]
0x18004f2b4  mov     [rsp+3D0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18004f2b9  xor     r9d, r9d; lpReserved
0x18004f2bc  mov     [rsp+3D0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18004f2c1  xor     r8d, r8d; lpcchClass
0x18004f2c4  mov     [rsp+3D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18004f2c9  xor     edx, edx; lpClass
0x18004f2cb  mov     [rsp+3D0h+lpdwDisposition], rdi; lpcbMaxValueNameLen
0x18004f2d0  lea     rax, [rsp+3D0h+cValues]
0x18004f2d5  mov     [rsp+3D0h+var_398], rax; lpcValues
0x18004f2da  mov     [rsp+3D0h+lpSecurityAttributes], rdi; lpcbMaxClassLen
0x18004f2df  mov     qword ptr [rsp+3D0h+samDesired], rdi; lpcbMaxSubKeyLen
0x18004f2e4  mov     [rsp+3D0h+phkResult], rdi; lpcSubKeys
0x18004f2e9  call    cs:__imp_RegQueryInfoKeyW
0x18004f2ef  test    eax, eax
0x18004f2f1  jnz     loc_18004F526
0x18004f2f7  mov     r14d, edi
0x18004f2fa  mov     esi, edi
0x18004f2fc  cmp     esi, [rsp+3D0h+cValues]
0x18004f300  jnb     loc_18004F562
0x18004f306  cmp     r14d, 100h
0x18004f30d  jnb     loc_18004F562
0x18004f313  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18004f318  lea     rax, [rsp+3D0h+cbData]
0x18004f31d  mov     [rsp+3D0h+var_398], rax; lpcbData
0x18004f322  lea     r9, [rsp+3D0h+cchValueName]; lpcchValueName
0x18004f327  lea     rax, [rbp+2D0h+Data]
0x18004f32b  mov     [rsp+3D0h+cchValueName], 10h
0x18004f333  mov     [rsp+3D0h+lpSecurityAttributes], rax; lpData
0x18004f338  lea     r8, [rbp+2D0h+ValueName]; lpValueName
0x18004f33c  lea     rax, [rsp+3D0h+Type]
0x18004f341  mov     [rsp+3D0h+Type], edi
0x18004f345  mov     qword ptr [rsp+3D0h+samDesired], rax; lpType
0x18004f34a  mov     edx, esi; dwIndex
0x18004f34c  mov     [rsp+3D0h+phkResult], rdi; lpReserved
0x18004f351  mov     [rsp+3D0h+cbData], 282h
0x18004f359  mov     [rsp+3D0h+var_35C], edi
0x18004f35d  call    cs:__imp_RegEnumValueW
0x18004f363  test    eax, eax
0x18004f365  jnz     loc_18004F507
0x18004f36b  cmp     [rsp+3D0h+Type], 7
0x18004f370  jnz     loc_18004F507
0x18004f376  mov     ecx, [rsp+3D0h+cbData]
0x18004f37a  shr     rcx, 1
0x18004f37d  mov     [rbp+2D0h+var_312], di
0x18004f381  lea     rax, [rcx+2]
0x18004f385  cmp     rax, 141h
0x18004f38b  ja      short loc_18004F3B8
0x18004f38d  add     rcx, rcx
0x18004f390  cmp     rcx, 282h
0x18004f397  jnb     loc_18004F50E
0x18004f39d  mov     word ptr [rbp+rcx+2D0h+Data], di
0x18004f3a2  add     rcx, 2
0x18004f3a6  cmp     rcx, 282h
0x18004f3ad  jnb     loc_18004F50E
0x18004f3b3  mov     word ptr [rbp+rcx+2D0h+Data], di
0x18004f3b8  lea     rdx, [rsp+3D0h+var_35C]; unsigned int *
0x18004f3bd  lea     rcx, [rbp+2D0h+ValueName]; unsigned __int16 *
0x18004f3c1  call    ?ParseReasonCode@@YAHPEAGPEAK@Z; ParseReasonCode(ushort *,ulong *)
0x18004f3c6  test    eax, eax
0x18004f3c8  jz      loc_18004F507
0x18004f3ce  lea     rcx, [rbp+2D0h+Data]; lpString
0x18004f3d2  call    cs:__imp_lstrlenW
0x18004f3d8  cmp     eax, 3Fh ; '?'
0x18004f3db  jg      loc_18004F507
0x18004f3e1  lea     rcx, [rbp+2D0h+Data]; lpString
0x18004f3e5  call    cs:__imp_lstrlenW
0x18004f3eb  movsxd  rcx, eax
0x18004f3ee  lea     rax, [rbp+2D0h+var_2CE]
0x18004f3f2  lea     rcx, [rax+rcx*2]; lpString
0x18004f3f6  call    cs:__imp_lstrlenW
0x18004f3fc  cmp     eax, 0FFh
0x18004f401  jg      loc_18004F507
0x18004f407  mov     edi, [rsp+3D0h+var_35C]
0x18004f40b  test    r13d, r13d
0x18004f40e  jnz     short loc_18004F417
0x18004f410  test    r12d, r12d
0x18004f413  jnz     short loc_18004F426
0x18004f415  jmp     short loc_18004F430
0x18004f417  bt      edi, 1Ah
0x18004f41b  jb      short loc_18004F430
0x18004f41d  test    r12d, r12d
0x18004f420  jz      loc_18004F505
0x18004f426  bt      edi, 1Bh
0x18004f42a  jnb     loc_18004F505
0x18004f430  mov     rcx, cs:pUserHeap; HeapHandle
0x18004f437  xor     edx, edx; Flags
0x18004f439  mov     r8d, 284h; Size
0x18004f43f  call    cs:__imp_RtlAllocateHeap
0x18004f445  mov     rbx, rax
0x18004f448  test    rax, rax
0x18004f44b  jz      loc_18004F526
0x18004f451  mov     [rax], edi
0x18004f453  lea     r8, [rbp+2D0h+Data]; unsigned __int16 *
0x18004f457  lea     rdi, [rax+4]
0x18004f45b  mov     edx, 40h ; '@'; unsigned __int64
0x18004f460  mov     rcx, rdi; unsigned __int16 *
0x18004f463  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f468  test    eax, eax
0x18004f46a  js      loc_18004F526
0x18004f470  lea     rcx, [rbp+2D0h+Data]; lpString
0x18004f474  call    cs:__imp_lstrlenW
0x18004f47a  movsxd  rcx, eax
0x18004f47d  lea     r8, [rbp+2D0h+var_2CE]
0x18004f481  mov     edx, 100h; unsigned __int64
0x18004f486  lea     r8, [r8+rcx*2]; unsigned __int16 *
0x18004f48a  lea     rcx, [rbx+84h]; unsigned __int16 *
0x18004f491  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f496  test    eax, eax
0x18004f498  js      loc_18004F526
0x18004f49e  mov     rcx, rdi; lpString
0x18004f4a1  call    cs:__imp_lstrlenW
0x18004f4a7  test    eax, eax
0x18004f4a9  jz      short loc_18004F4F3
0x18004f4ab  movzx   eax, word ptr [rdi]
0x18004f4ae  test    ax, ax
0x18004f4b1  jz      short loc_18004F4F3
0x18004f4b3  xor     r15d, r15d
0x18004f4b6  movzx   ecx, ax; C
0x18004f4b9  call    cs:__imp_iswspace
0x18004f4bf  test    eax, eax
0x18004f4c1  jz      short loc_18004F4CF
0x18004f4c3  add     rdi, 2
0x18004f4c7  movzx   eax, word ptr [rdi]
0x18004f4ca  test    ax, ax
0x18004f4cd  jnz     short loc_18004F4B6
0x18004f4cf  cmp     [rdi], r15w
0x18004f4d3  mov     r15, [rbp+2D0h+var_350]
0x18004f4d7  jz      short loc_18004F4F3
0x18004f4d9  mov     rdx, rbx; struct _REASON *
0x18004f4dc  mov     rcx, r15; struct _REASONDATA *
0x18004f4df  call    ?AppendReason@@YAHPEAU_REASONDATA@@PEAU_REASON@@@Z; AppendReason(_REASONDATA *,_REASON *)
0x18004f4e4  cmp     eax, 0FFFFFFFFh
0x18004f4e7  jz      short loc_18004F514
0x18004f4e9  cmp     eax, 1
0x18004f4ec  jnz     short loc_18004F505
0x18004f4ee  inc     r14d
0x18004f4f1  jmp     short loc_18004F505
0x18004f4f3  mov     rcx, cs:pUserHeap; HeapHandle
0x18004f4fa  mov     r8, rbx; P
0x18004f4fd  xor     edx, edx; Flags
0x18004f4ff  call    cs:__imp_RtlFreeHeap
0x18004f505  xor     edi, edi
0x18004f507  inc     esi
0x18004f509  jmp     loc_18004F2FC
0x18004f50e  call    __report_rangecheckfailure
0x18004f514  mov     rcx, cs:pUserHeap; HeapHandle
0x18004f51b  mov     r8, rbx; P
0x18004f51e  xor     edx, edx; Flags
0x18004f520  call    cs:__imp_RtlFreeHeap
0x18004f526  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18004f52b  test    rcx, rcx
0x18004f52e  jz      short loc_18004F536
0x18004f530  call    cs:__imp_RegCloseKey
0x18004f536  xor     eax, eax
0x18004f538  mov     rcx, [rbp+2D0h+var_40]
0x18004f53f  xor     rcx, rsp; StackCookie
0x18004f542  call    __security_check_cookie
0x18004f547  mov     rbx, [rsp+3D0h+arg_10]
0x18004f54f  add     rsp, 3A0h
0x18004f556  pop     r15
0x18004f558  pop     r14
0x18004f55a  pop     r13
0x18004f55c  pop     r12
0x18004f55e  pop     rdi
0x18004f55f  pop     rsi
0x18004f560  pop     rbp
0x18004f561  retn
0x18004f562  mov     rcx, [rsp+3D0h+hKey]; hKey
0x18004f567  call    cs:__imp_RegCloseKey
0x18004f56d  mov     eax, 1
0x18004f572  jmp     short loc_18004F538
```
