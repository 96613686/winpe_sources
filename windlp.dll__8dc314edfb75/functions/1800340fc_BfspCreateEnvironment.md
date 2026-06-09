# BfspCreateEnvironment

- ea: `0x1800340fc`
- end: `0x1800345df`
- name: `BfspCreateEnvironment`
- size: `1251`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032518`

## callees

- `0x1800315c4`
- `0x1800318b0`
- `0x1800321ec`
- `0x1800324a4`
- `0x1800340fc`
- `0x1800347c4`
- `0x180034834`
- `0x1800366b8`
- `0x180037058`
- `0x1800371c4`
- `0x180037220`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180034325`
- `ntdll!RtlImageNtHeader` at `0x180034325`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800344de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003456b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003459d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800344de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003456b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003459d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003414a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800343fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800344ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003414a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800343fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800344ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034560`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800345ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034547`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034560`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034579`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800345ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800345bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800345bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003452f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800344ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003452f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18003418f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180034201`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180034464`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18003418f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180034201`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180034464`

## pseudocode

```c
__int64 __fastcall BfspCreateEnvironment(STRSAFE_LPCWSTR pszSrc, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  void *v5; // r12
  HANDLE ProcessHeap; // rax
  unsigned int v9; // edi
  const wchar_t *LastError; // rbx
  void *v11; // r14
  _WORD *v12; // r13
  WCHAR *v13; // r15
  __int64 v14; // rcx
  WCHAR *SystemPartition; // rax
  __int64 v16; // rcx
  int FirmwareType; // ebp
  const wchar_t *v18; // r8
  __int64 v19; // r12
  DWORD v20; // eax
  unsigned int v21; // eax
  const WCHAR *v22; // rax
  void *v23; // rax
  PIMAGE_NT_HEADERS v24; // rax
  int v25; // ebx
  int v26; // ebx
  const wchar_t *v27; // r8
  HANDLE v28; // rax
  char *v29; // rax
  __int64 v30; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  wchar_t *lpMem; // [rsp+20h] [rbp-58h]
  __int128 v39; // [rsp+28h] [rbp-50h] BYREF
  __int64 v40; // [rsp+38h] [rbp-40h]
  SIZE_T dwBytes; // [rsp+98h] [rbp+20h]

  v3 = -1;
  a3[1] = a3;
  v4 = -1;
  *a3 = a3;
  v5 = 0;
  do
    ++v4;
  while ( pszSrc[v4] );
  ProcessHeap = GetProcessHeap();
  lpMem = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 2 * v4 + 2);
  if ( !lpMem )
  {
    v9 = 0;
    LODWORD(LastError) = 8;
LABEL_66:
    BfspEnvDestory(a3);
    SetLastError((DWORD)LastError);
    return v9;
  }
  v11 = 0;
  v12 = 0;
  v13 = 0;
  do
    ++v3;
  while ( pszSrc[v3] );
  StringCchCopyW(lpMem, v3 + 1, pszSrc);
  PathRemoveBackslashW(lpMem);
  v9 = BfspEnvAddVariable(a3, L"SOURCE", lpMem);
  if ( !v9 )
    goto LABEL_55;
  v9 = BfspEnvAddVariable(a3, L"SYSROOT", lpMem);
  if ( !v9 )
    goto LABEL_55;
  SystemPartition = (WCHAR *)BfspGetSystemPartition(v14);
  v13 = SystemPartition;
  if ( !SystemPartition )
  {
    v9 = 0;
    LastError = (const wchar_t *)GetLastError();
    BfspLogMessage(4, L"Failed to get system partition! Last Error = %#x", LastError);
    goto LABEL_57;
  }
  PathRemoveBackslashW(SystemPartition);
  v9 = BfspEnvAddVariable(a3, L"SYSPART", v13);
  if ( !v9 )
    goto LABEL_55;
  FirmwareType = BfspGetFirmwareType(v16);
  if ( FirmwareType == 1 )
  {
    v18 = L"PCAT";
    dwBytes = 10;
    LastError = L"bootmgr";
    v19 = 8;
  }
  else
  {
    if ( FirmwareType != 2 )
    {
      v9 = 0;
      LODWORD(LastError) = 31;
      goto LABEL_57;
    }
    v9 = BfspEnvAddVariable(a3, L"BOOTMGBINEX", L"bootmgfw_EX.efi");
    if ( !v9 )
      goto LABEL_55;
    v18 = L"EFI";
    dwBytes = 38;
    LastError = L"bootmgfw.efi";
    v19 = 36;
  }
  v9 = BfspEnvAddVariable(a3, L"FWTYPE", v18);
  if ( !v9 || (v21 = BfspEnvAddVariable(a3, L"BOOTMGBIN", LastError), LODWORD(LastError) = 0, (v9 = v21) == 0) )
  {
LABEL_19:
    v20 = GetLastError();
    v5 = 0;
LABEL_56:
    LODWORD(LastError) = v20;
    goto LABEL_57;
  }
  if ( FirmwareType == 2 )
  {
    v22 = (const WCHAR *)BfspEnvExpandString(a3, L"|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|");
    v40 = 0;
    v39 = 0;
    v23 = (void *)BfspMapFileForRead(v22);
    if ( v23 )
    {
      v24 = RtlImageNtHeader(v23);
      if ( v24 )
        LODWORD(LastError) = v24->FileHeader.Machine;
      BfspUnmapFile(&v39);
      if ( (_DWORD)LastError )
      {
        v25 = (_DWORD)LastError - 332;
        if ( !v25 )
        {
          v27 = L"bootia32.efi";
          goto LABEL_32;
        }
        v26 = v25 - 118;
        if ( !v26 )
        {
          v27 = L"bootarm.efi";
          goto LABEL_32;
        }
        if ( v26 == 43170 )
        {
          v27 = L"bootaa64.efi";
LABEL_32:
          LODWORD(LastError) = 0;
          goto LABEL_35;
        }
      }
      LODWORD(LastError) = 0;
    }
    v27 = L"bootx64.efi";
LABEL_35:
    if ( !(unsigned int)BfspEnvAddVariable(a3, L"DEFAULTAPP", v27) )
    {
      v20 = GetLastError();
      v9 = 0;
      v5 = 0;
      goto LABEL_56;
    }
  }
  v9 = BfspEnvAddVariable(a3, L"FONTS", L"Fonts");
  if ( !v9 )
    goto LABEL_19;
  v9 = BfspEnvAddVariable(a3, L"RESOURCES", L"Resources");
  if ( !v9 )
    goto LABEL_19;
  v28 = GetProcessHeap();
  v29 = (char *)HeapAlloc(v28, 8u, dwBytes);
  v11 = v29;
  if ( !v29 )
  {
    v9 = 0;
    LODWORD(LastError) = 8;
    v5 = 0;
    goto LABEL_57;
  }
  *(_WORD *)&v29[v19] = 0;
  if ( FirmwareType == 1 )
  {
    *(_QWORD *)v29 = 0x74006F006F0042LL;
  }
  else
  {
    *(_OWORD *)v29 = *(_OWORD *)L"EFI\\Microsoft\\Boot";
    *((_OWORD *)v29 + 1) = *(_OWORD *)L"osoft\\Boot";
    *((_DWORD *)v29 + 8) = *(_DWORD *)L"ot";
  }
  PathRemoveBackslashW((LPWSTR)v29);
  v9 = BfspEnvAddVariable(a3, L"DEST", v11);
  if ( !v9 )
    goto LABEL_19;
  v30 = BfspEnvExpandString(a3, L"|SYSPART|\\");
  v5 = (void *)v30;
  if ( !v30 )
  {
LABEL_46:
    v9 = 0;
LABEL_55:
    v20 = GetLastError();
    goto LABEL_56;
  }
  if ( (unsigned int)BfspIsSecuritySupported(v30) )
  {
    v9 = BfspEnvAddVariable(a3, L"ACLS", L"Yes");
    if ( !v9 )
      goto LABEL_55;
  }
  else if ( GetLastError() != 50 )
  {
    goto LABEL_46;
  }
  if ( FirmwareType != 2 )
    goto LABEL_57;
  v31 = GetProcessHeap();
  v12 = HeapAlloc(v31, 8u, 0x12u);
  if ( !v12 )
  {
    v9 = 0;
    LODWORD(LastError) = 8;
    goto LABEL_57;
  }
  v12[8] = 0;
  *(_OWORD *)v12 = *(_OWORD *)L"EFI\\Boot";
  v9 = BfspEnvAddVariable(a3, L"EFIDEFAULTDIR", v12);
  if ( !v9 )
    goto LABEL_55;
LABEL_57:
  v32 = GetProcessHeap();
  HeapFree(v32, 0, lpMem);
  if ( v13 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v13);
  }
  if ( v5 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v5);
  }
  if ( v11 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v11);
  }
  if ( v12 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v12);
  }
  if ( !v9 )
    goto LABEL_66;
  return v9;
}

```

## disassembly

```asm
0x1800340fc  mov     [rsp+arg_0], rbx
0x180034101  push    rbp
0x180034102  push    rsi
0x180034103  push    rdi
0x180034104  push    r12
0x180034106  push    r13
0x180034108  push    r14
0x18003410a  push    r15
0x18003410c  sub     rsp, 40h
0x180034110  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034114  mov     [r8+8], r8
0x180034118  mov     rbx, rdi
0x18003411b  mov     [r8], r8
0x18003411e  xor     r12d, r12d
0x180034121  mov     rsi, r8
0x180034124  mov     rbp, rcx
0x180034127  inc     rbx
0x18003412a  cmp     [rcx+rbx*2], r12w
0x18003412f  jnz     short loc_180034127
0x180034131  lea     rbx, ds:2[rbx*2]
0x180034139  call    cs:__imp_GetProcessHeap
0x18003413f  mov     r8, rbx; dwBytes
0x180034142  mov     edx, 8; dwFlags
0x180034147  mov     rcx, rax; hHeap
0x18003414a  call    cs:__imp_HeapAlloc
0x180034150  mov     [rsp+78h+lpMem], rax
0x180034155  mov     rbx, rax
0x180034158  test    rax, rax
0x18003415b  jnz     short loc_180034168
0x18003415d  mov     edi, r12d
0x180034160  lea     ebx, [rax+8]
0x180034163  jmp     loc_1800345B5
0x180034168  mov     r14, r12
0x18003416b  mov     r13, r12
0x18003416e  mov     r15, r12
0x180034171  xor     eax, eax
0x180034173  inc     rdi
0x180034176  cmp     [rbp+rdi*2+0], ax
0x18003417b  jnz     short loc_180034173
0x18003417d  lea     rdx, [rdi+1]; cchDest
0x180034181  mov     r8, rbp; pszSrc
0x180034184  mov     rcx, rbx; pszDest
0x180034187  call    StringCchCopyW
0x18003418c  mov     rcx, rbx; pszPath
0x18003418f  call    cs:__imp_PathRemoveBackslashW
0x180034195  mov     r8, rbx
0x180034198  lea     rdx, aSource; "SOURCE"
0x18003419f  mov     rcx, rsi
0x1800341a2  call    BfspEnvAddVariable
0x1800341a7  mov     edi, eax
0x1800341a9  test    eax, eax
0x1800341ab  jz      loc_18003452F
0x1800341b1  mov     r8, rbx
0x1800341b4  lea     rdx, aSysroot_0; "SYSROOT"
0x1800341bb  mov     rcx, rsi
0x1800341be  call    BfspEnvAddVariable
0x1800341c3  xor     ebx, ebx
0x1800341c5  mov     edi, eax
0x1800341c7  test    eax, eax
0x1800341c9  jz      loc_18003452F
0x1800341cf  call    BfspGetSystemPartition
0x1800341d4  mov     r15, rax
0x1800341d7  test    rax, rax
0x1800341da  jnz     short loc_1800341FE
0x1800341dc  mov     edi, ebx
0x1800341de  call    cs:__imp_GetLastError
0x1800341e4  mov     r8d, eax
0x1800341e7  lea     rdx, aFailedToGetSys; "Failed to get system partition! Last Er"...
0x1800341ee  lea     ecx, [r15+4]
0x1800341f2  mov     ebx, eax
0x1800341f4  call    BfspLogMessage
0x1800341f9  jmp     loc_180034537
0x1800341fe  mov     rcx, r15; pszPath
0x180034201  call    cs:__imp_PathRemoveBackslashW
0x180034207  mov     r8, r15
0x18003420a  lea     rdx, aSyspart_1; "SYSPART"
0x180034211  mov     rcx, rsi
0x180034214  call    BfspEnvAddVariable
0x180034219  mov     edi, eax
0x18003421b  test    eax, eax
0x18003421d  jz      loc_18003452F
0x180034223  call    BfspGetFirmwareType
0x180034228  mov     edx, eax
0x18003422a  mov     ebp, eax
0x18003422c  sub     edx, 1
0x18003422f  jz      short loc_180034284
0x180034231  cmp     edx, 1
0x180034234  jz      short loc_180034242
0x180034236  mov     edi, ebx
0x180034238  mov     ebx, 1Fh
0x18003423d  jmp     loc_180034537
0x180034242  lea     r8, aBootmgfwExEfi; "bootmgfw_EX.efi"
0x180034249  mov     rcx, rsi
0x18003424c  lea     rdx, aBootmgbinex; "BOOTMGBINEX"
0x180034253  call    BfspEnvAddVariable
0x180034258  mov     edi, eax
0x18003425a  test    eax, eax
0x18003425c  jz      loc_18003452F
0x180034262  lea     r8, aEfi; "EFI"
0x180034269  mov     [rsp+78h+dwBytes], 26h ; '&'
0x180034275  lea     rbx, aBootmgfwEfi; "bootmgfw.efi"
0x18003427c  mov     r12d, 24h ; '$'
0x180034282  jmp     short loc_1800342A4
0x180034284  lea     r8, aPcat; "PCAT"
0x18003428b  mov     [rsp+78h+dwBytes], 0Ah
0x180034297  lea     rbx, aBootmgr; "bootmgr"
0x18003429e  mov     r12d, 8
0x1800342a4  lea     rdx, aFwtype; "FWTYPE"
0x1800342ab  mov     rcx, rsi
0x1800342ae  call    BfspEnvAddVariable
0x1800342b3  mov     edi, eax
0x1800342b5  test    eax, eax
0x1800342b7  jnz     short loc_1800342C7
0x1800342b9  call    cs:__imp_GetLastError
0x1800342bf  mov     r12, r13
0x1800342c2  jmp     loc_180034535
0x1800342c7  mov     r8, rbx
0x1800342ca  lea     rdx, aBootmgbin; "BOOTMGBIN"
0x1800342d1  mov     rcx, rsi
0x1800342d4  call    BfspEnvAddVariable
0x1800342d9  xor     ebx, ebx
0x1800342db  mov     edi, eax
0x1800342dd  test    eax, eax
0x1800342df  jz      short loc_1800342B9
0x1800342e1  cmp     ebp, 2
0x1800342e4  jnz     loc_1800343A8
0x1800342ea  lea     rdx, aSourceFwtypeBo; "|SOURCE|\\|FWTYPE|\\|BOOTMGBIN|"
0x1800342f1  mov     rcx, rsi
0x1800342f4  call    BfspEnvExpandString
0x1800342f9  xor     ecx, ecx
0x1800342fb  lea     r8, [rsp+78h+var_50]
0x180034300  mov     [rsp+78h+var_40], rcx
0x180034305  lea     rdx, [rsp+78h+arg_8]
0x18003430d  xorps   xmm0, xmm0
0x180034310  mov     rcx, rax; lpFileName
0x180034313  movups  [rsp+78h+var_50], xmm0
0x180034318  call    BfspMapFileForRead
0x18003431d  test    rax, rax
0x180034320  jz      short loc_18003437E
0x180034322  mov     rcx, rax; BaseAddress
0x180034325  call    cs:__imp_RtlImageNtHeader
0x18003432b  test    rax, rax
0x18003432e  jz      short loc_180034334
0x180034330  movzx   ebx, word ptr [rax+4]
0x180034334  lea     rcx, [rsp+78h+var_50]
0x180034339  call    BfspUnmapFile
0x18003433e  test    ebx, ebx
0x180034340  jz      short loc_18003437C
0x180034342  sub     ebx, 14Ch
0x180034348  jz      short loc_180034371
0x18003434a  sub     ebx, 76h ; 'v'
0x18003434d  jz      short loc_180034368
0x18003434f  sub     ebx, 84A2h
0x180034355  jz      short loc_18003437C
0x180034357  cmp     ebx, 2400h
0x18003435d  jnz     short loc_18003437C
0x18003435f  lea     r8, aBootaa64Efi; "bootaa64.efi"
0x180034366  jmp     short loc_180034378
0x180034368  lea     r8, aBootarmEfi; "bootarm.efi"
0x18003436f  jmp     short loc_180034378
0x180034371  lea     r8, aBootia32Efi; "bootia32.efi"
0x180034378  xor     ebx, ebx
0x18003437a  jmp     short loc_180034385
0x18003437c  xor     ebx, ebx
0x18003437e  lea     r8, aBootx64Efi; "bootx64.efi"
0x180034385  lea     rdx, aDefaultapp; "DEFAULTAPP"
0x18003438c  mov     rcx, rsi
0x18003438f  call    BfspEnvAddVariable
0x180034394  test    eax, eax
0x180034396  jnz     short loc_1800343A8
0x180034398  call    cs:__imp_GetLastError
0x18003439e  xor     edi, edi
0x1800343a0  mov     r12d, edi
0x1800343a3  jmp     loc_180034535
0x1800343a8  lea     r8, aFonts_0; "Fonts"
0x1800343af  mov     rcx, rsi
0x1800343b2  lea     rdx, aFonts; "FONTS"
0x1800343b9  call    BfspEnvAddVariable
0x1800343be  mov     edi, eax
0x1800343c0  test    eax, eax
0x1800343c2  jz      loc_1800342B9
0x1800343c8  lea     r8, aResources_0; "Resources"
0x1800343cf  mov     rcx, rsi
0x1800343d2  lea     rdx, aResources; "RESOURCES"
0x1800343d9  call    BfspEnvAddVariable
0x1800343de  mov     edi, eax
0x1800343e0  test    eax, eax
0x1800343e2  jz      loc_1800342B9
0x1800343e8  call    cs:__imp_GetProcessHeap
0x1800343ee  mov     r8, [rsp+78h+dwBytes]; dwBytes
0x1800343f6  mov     edx, 8; dwFlags
0x1800343fb  mov     rcx, rax; hHeap
0x1800343fe  call    cs:__imp_HeapAlloc
0x180034404  mov     r14, rax
0x180034407  test    rax, rax
0x18003440a  jnz     short loc_180034419
0x18003440c  mov     edi, ebx
0x18003440e  lea     ebx, [rax+8]
0x180034411  mov     r12, r13
0x180034414  jmp     loc_180034537
0x180034419  mov     ecx, ebp
0x18003441b  mov     [r12+rax], bx
0x180034420  sub     ecx, 1
0x180034423  jz      short loc_180034454
0x180034425  cmp     ecx, 1
0x180034428  jz      short loc_180034433
0x18003442a  mov     edi, ebx
0x18003442c  mov     ebx, 1Fh
0x180034431  jmp     short loc_180034411
0x180034433  movups  xmm0, xmmword ptr cs:aEfiMicrosoftBo; "EFI\\Microsoft\\Boot"
0x18003443a  movups  xmmword ptr [rax], xmm0
0x18003443d  movups  xmm1, xmmword ptr cs:aEfiMicrosoftBo+10h; "osoft\\Boot"
0x180034444  movups  xmmword ptr [rax+10h], xmm1
0x180034448  mov     eax, dword ptr cs:aEfiMicrosoftBo+20h; "ot"
0x18003444e  mov     [r14+20h], eax
0x180034452  jmp     short loc_180034461
0x180034454  mov     rax, 74006F006F0042h
0x18003445e  mov     [r14], rax
0x180034461  mov     rcx, r14; pszPath
0x180034464  call    cs:__imp_PathRemoveBackslashW
0x18003446a  mov     r8, r14
0x18003446d  lea     rdx, aDest; "DEST"
0x180034474  mov     rcx, rsi
0x180034477  call    BfspEnvAddVariable
0x18003447c  mov     edi, eax
0x18003447e  test    eax, eax
0x180034480  jz      loc_1800342B9
0x180034486  lea     rdx, aSyspart_0; "|SYSPART|\\"
0x18003448d  mov     rcx, rsi
0x180034490  call    BfspEnvExpandString
0x180034495  mov     r12, rax
0x180034498  test    rax, rax
0x18003449b  jnz     short loc_1800344A4
0x18003449d  mov     edi, ebx
0x18003449f  jmp     loc_18003452F
0x1800344a4  mov     rcx, rax
0x1800344a7  call    BfspIsSecuritySupported
0x1800344ac  test    eax, eax
0x1800344ae  jz      short loc_1800344CE
0x1800344b0  lea     r8, aYes; "Yes"
0x1800344b7  mov     rcx, rsi
0x1800344ba  lea     rdx, aAcls; "ACLS"
0x1800344c1  call    BfspEnvAddVariable
0x1800344c6  mov     edi, eax
0x1800344c8  test    eax, eax
0x1800344ca  jnz     short loc_1800344D9
0x1800344cc  jmp     short loc_18003452F
0x1800344ce  call    cs:__imp_GetLastError
0x1800344d4  cmp     eax, 32h ; '2'
0x1800344d7  jnz     short loc_18003449D
0x1800344d9  cmp     ebp, 2
0x1800344dc  jnz     short loc_180034537
0x1800344de  call    cs:__imp_GetProcessHeap
0x1800344e4  mov     rcx, rax; hHeap
0x1800344e7  lea     edx, [rbp+6]; dwFlags
0x1800344ea  lea     r8d, [rbp+10h]; dwBytes
0x1800344ee  call    cs:__imp_HeapAlloc
0x1800344f4  mov     r13, rax
0x1800344f7  xor     eax, eax
0x1800344f9  test    r13, r13
0x1800344fc  jnz     short loc_180034505
0x1800344fe  mov     edi, eax
0x180034500  lea     ebx, [rbp+6]
0x180034503  jmp     short loc_180034537
0x180034505  mov     [r13+10h], ax
0x18003450a  lea     rdx, aEfidefaultdir; "EFIDEFAULTDIR"
0x180034511  movups  xmm0, xmmword ptr cs:aEfiBoot; "EFI\\Boot"
0x180034518  mov     r8, r13
0x18003451b  mov     rcx, rsi
0x18003451e  movdqu  xmmword ptr [r13+0], xmm0
0x180034524  call    BfspEnvAddVariable
0x180034529  mov     edi, eax
0x18003452b  test    eax, eax
0x18003452d  jnz     short loc_180034537
0x18003452f  call    cs:__imp_GetLastError
0x180034535  mov     ebx, eax
0x180034537  call    cs:__imp_GetProcessHeap
0x18003453d  mov     r8, [rsp+78h+lpMem]; lpMem
0x180034542  xor     edx, edx; dwFlags
0x180034544  mov     rcx, rax; hHeap
0x180034547  call    cs:__imp_HeapFree
0x18003454d  test    r15, r15
0x180034550  jz      short loc_180034566
0x180034552  call    cs:__imp_GetProcessHeap
0x180034558  mov     r8, r15; lpMem
0x18003455b  xor     edx, edx; dwFlags
0x18003455d  mov     rcx, rax; hHeap
0x180034560  call    cs:__imp_HeapFree
0x180034566  test    r12, r12
0x180034569  jz      short loc_18003457F
0x18003456b  call    cs:__imp_GetProcessHeap
0x180034571  mov     r8, r12; lpMem
0x180034574  xor     edx, edx; dwFlags
0x180034576  mov     rcx, rax; hHeap
0x180034579  call    cs:__imp_HeapFree
0x18003457f  test    r14, r14
0x180034582  jz      short loc_180034598
0x180034584  call    cs:__imp_GetProcessHeap
0x18003458a  mov     r8, r14; lpMem
0x18003458d  xor     edx, edx; dwFlags
  ... truncated ...
```
