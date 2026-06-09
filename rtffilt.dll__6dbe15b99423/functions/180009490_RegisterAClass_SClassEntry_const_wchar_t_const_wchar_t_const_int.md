# RegisterAClass(SClassEntry const &,wchar_t const *,wchar_t const *,int)

- ea: `0x180009490`
- end: `0x18000988d`
- name: `?RegisterAClass@@YAJAEBUSClassEntry@@PEB_W1H@Z`
- size: `1021`
- prototype: `__int64 __fastcall(const struct SClassEntry *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009894`
- `0x18000cff4`

## callees

- `0x180001e40`
- `0x18000920c`
- `0x180009490`
- `0x18000b288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009640`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009640`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000981f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000985a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000981f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000985a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800095ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000975d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800095ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000975d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009798`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009798`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000971c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000971c`

## string_xrefs

- `0x1800096e9`: `\CLSID`

## pseudocode

```c
__int64 __fastcall RegisterAClass(const struct SClassEntry *a1, const wchar_t *a2, const wchar_t *a3, int a4)
{
  WCHAR *v4; // rax
  int v5; // ebx
  __int64 v6; // rsi
  const wchar_t *v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // r8
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  __int64 result; // rax
  LSTATUS v15; // eax
  unsigned int v16; // ebx
  const BYTE *v17; // rcx
  __int64 v18; // rax
  LSTATUS v19; // eax
  WCHAR *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  WCHAR *v23; // rax
  WCHAR *v24; // rcx
  __int64 v25; // rax
  LSTATUS v26; // eax
  const wchar_t *v27; // rdx
  int v28; // edi
  const BYTE *v29; // rcx
  __int64 v30; // rax
  LSTATUS v31; // eax
  WCHAR *v32; // r8
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+5Ch] [rbp-A4h]
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type[3]; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = SubKey;
  v5 = a4;
  v36 = a4;
  v6 = 2147483646;
  v8 = a3;
  v9 = 2147483646;
  v10 = 260;
  if ( a3 )
  {
    do
    {
      if ( !v9 )
        break;
      if ( !*a3 )
        break;
      *v4++ = *a3++;
      --v9;
      --v10;
    }
    while ( v10 );
  }
  else
  {
    v11 = (WCHAR *)*((_QWORD *)a1 + 1);
    do
    {
      if ( !v9 )
        break;
      if ( !*v11 )
        break;
      *v4++ = *v11++;
      --v9;
      --v10;
    }
    while ( v10 );
  }
  v12 = v4 - 1;
  if ( v10 )
    v12 = v4;
  v13 = -v10;
  result = v13 == 0 ? 0x8007007A : 0;
  *v12 = 0;
  if ( v13 )
  {
    dwDisposition = 0;
    Type[0] = 0;
    cbData = 0;
    if ( a4 )
    {
      v15 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
      if ( v15 )
        goto LABEL_15;
      dwDisposition = 2;
    }
    else
    {
      v16 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      if ( v16 )
        goto LABEL_60;
      if ( dwDisposition == 1 && !v8 )
      {
        v17 = (const BYTE *)*((_QWORD *)a1 + 2);
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v17[2 * v18] );
        v19 = RegSetValueExW(hKey, 0, 0, 1u, v17, 2 * v18 + 2);
        v20 = (WCHAR *)*((_QWORD *)a1 + 1);
        v16 = v19;
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        if ( (unsigned __int64)(v21 + 7) > 0x104 )
        {
          v16 = -2147024809;
          goto LABEL_60;
        }
        v22 = 260;
        v23 = SubKey;
        do
        {
          if ( !v6 )
            break;
          if ( !*v20 )
            break;
          *v23++ = *v20++;
          --v6;
          --v22;
        }
        while ( v22 );
        v24 = v23 - 1;
        if ( v22 )
          v24 = v23;
        *v24 = 0;
        if ( v16 )
          goto LABEL_60;
      }
      v5 = v36;
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(hKey);
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    v25 = -1;
    do
      ++v25;
    while ( SubKey[v25] );
    StringCchCatW(SubKey, 260 - v25, L"\\CLSID");
    if ( v5 )
    {
      v15 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
      if ( v15 )
      {
LABEL_15:
        v16 = 0;
        if ( v15 != 2 )
          v16 = v15;
        goto LABEL_60;
      }
      dwDisposition = 2;
    }
    else
    {
      v16 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      if ( v16 )
        goto LABEL_60;
    }
    cbData = 520;
    v26 = RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)SubKey, &cbData);
    v16 = v26;
    if ( !v26 )
    {
      v28 = v36;
      if ( Type[0] != 1 )
        v16 = -2147467259;
      goto LABEL_54;
    }
    if ( v26 == 2 )
    {
      v28 = v36;
      if ( v36 )
      {
        v16 = 0;
        goto LABEL_60;
      }
      v29 = (const BYTE *)*((_QWORD *)a1 + 3);
      v30 = -1;
      do
        ++v30;
      while ( *(_WORD *)&v29[2 * v30] );
      v31 = RegSetValueExW(hKey, 0, 0, 1u, v29, 2 * v30 + 2);
      SubKey[0] = 0;
      v16 = v31;
      if ( !v31 )
      {
LABEL_54:
        if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          RegCloseKey(hKey);
          hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        }
        if ( !v16 )
        {
          v32 = SubKey;
          if ( !SubKey[0] )
            v32 = 0;
          v16 = RegisterACLSID(a1, v27, v32, v28, phkResult);
        }
      }
    }
LABEL_60:
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x180009490  mov     [rsp-8+arg_8], rbx
0x180009495  mov     [rsp-8+arg_10], rsi
0x18000949a  push    rbp
0x18000949b  push    rdi
0x18000949c  push    r12
0x18000949e  push    r13
0x1800094a0  push    r14
0x1800094a2  lea     rbp, [rsp-190h]
0x1800094aa  sub     rsp, 290h
0x1800094b1  mov     rax, cs:__security_cookie
0x1800094b8  xor     rax, rsp
0x1800094bb  mov     [rbp+1B0h+var_30], rax
0x1800094c2  xor     r10d, r10d
0x1800094c5  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800094ce  lea     rax, [rsp+2B0h+SubKey]
0x1800094d3  mov     ebx, r9d
0x1800094d6  mov     [rsp+2B0h+var_254], ebx
0x1800094da  mov     esi, 7FFFFFFEh
0x1800094df  mov     edi, 104h
0x1800094e4  mov     r13, rcx
0x1800094e7  mov     r14, r8
0x1800094ea  mov     ecx, esi
0x1800094ec  mov     edx, edi
0x1800094ee  test    r8, r8
0x1800094f1  jnz     short loc_18000951D
0x1800094f3  mov     r8, [r13+8]
0x1800094f7  test    rcx, rcx
0x1800094fa  jz      short loc_180009541
0x1800094fc  movzx   r9d, word ptr [r8]
0x180009500  test    r9w, r9w
0x180009504  jz      short loc_180009541
0x180009506  mov     [rax], r9w
0x18000950a  add     r8, 2
0x18000950e  add     rax, 2
0x180009512  dec     rcx
0x180009515  sub     rdx, 1
0x180009519  jnz     short loc_1800094F7
0x18000951b  jmp     short loc_180009541
0x18000951d  test    rcx, rcx
0x180009520  jz      short loc_180009541
0x180009522  movzx   r9d, word ptr [r8]
0x180009526  test    r9w, r9w
0x18000952a  jz      short loc_180009541
0x18000952c  mov     [rax], r9w
0x180009530  add     r8, 2
0x180009534  add     rax, 2
0x180009538  dec     rcx
0x18000953b  sub     rdx, 1
0x18000953f  jnz     short loc_18000951D
0x180009541  lea     rcx, [rax-2]
0x180009545  test    rdx, rdx
0x180009548  cmovnz  rcx, rax
0x18000954c  neg     rdx
0x18000954f  sbb     eax, eax
0x180009551  not     eax
0x180009553  and     eax, 8007007Ah
0x180009558  mov     [rcx], r10w
0x18000955c  test    eax, eax
0x18000955e  js      loc_180009862
0x180009564  xor     r8d, r8d; Reserved
0x180009567  mov     [rsp+2B0h+dwDisposition], r10d
0x18000956c  mov     [rsp+2B0h+Type], r10d
0x180009571  mov     r12, 0FFFFFFFF80000000h
0x180009578  mov     [rsp+2B0h+cbData], r10d
0x18000957d  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180009582  mov     rcx, r12; hKey
0x180009585  test    ebx, ebx
0x180009587  jz      short loc_1800095C1
0x180009589  lea     rax, [rsp+2B0h+hKey]
0x18000958e  mov     r9d, 2001Fh; samDesired
0x180009594  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180009599  call    cs:__imp_RegOpenKeyExW
0x18000959f  xor     r14d, r14d
0x1800095a2  test    eax, eax
0x1800095a4  jz      short loc_1800095B4
0x1800095a6  cmp     eax, 2
0x1800095a9  mov     ebx, r14d
0x1800095ac  cmovnz  ebx, eax
0x1800095af  jmp     loc_18000984F
0x1800095b4  mov     [rsp+2B0h+dwDisposition], 2
0x1800095bc  jmp     loc_1800096B9
0x1800095c1  lea     rax, [rsp+2B0h+dwDisposition]
0x1800095c6  xor     r9d, r9d; lpClass
0x1800095c9  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x1800095ce  lea     rax, [rsp+2B0h+hKey]
0x1800095d3  mov     [rsp+2B0h+var_278], rax; phkResult
0x1800095d8  mov     [rsp+2B0h+lpSecurityAttributes], r10; lpSecurityAttributes
0x1800095dd  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x1800095e5  mov     dword ptr [rsp+2B0h+phkResult], r10d; dwOptions
0x1800095ea  call    cs:__imp_RegCreateKeyExW
0x1800095f0  mov     ebx, eax
0x1800095f2  test    eax, eax
0x1800095f4  jnz     loc_18000984F
0x1800095fa  cmp     [rsp+2B0h+dwDisposition], 1
0x1800095ff  jnz     loc_1800096B2
0x180009605  test    r14, r14
0x180009608  jnz     loc_1800096B2
0x18000960e  mov     rcx, [r13+10h]
0x180009612  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009616  inc     rax
0x180009619  cmp     [rcx+rax*2], r14w
0x18000961e  jnz     short loc_180009616
0x180009620  lea     eax, ds:2[rax*2]
0x180009627  mov     r9d, 1; dwType
0x18000962d  mov     [rsp+2B0h+samDesired], eax; cbData
0x180009631  xor     r8d, r8d; Reserved
0x180009634  mov     [rsp+2B0h+phkResult], rcx; lpData
0x180009639  xor     edx, edx; lpValueName
0x18000963b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180009640  call    cs:__imp_RegSetValueExW
0x180009646  mov     rcx, [r13+8]
0x18000964a  mov     ebx, eax
0x18000964c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009650  inc     rax
0x180009653  cmp     [rcx+rax*2], r14w
0x180009658  jnz     short loc_180009650
0x18000965a  add     rax, 7
0x18000965e  cmp     rax, rdi
0x180009661  jbe     short loc_18000966D
0x180009663  mov     ebx, 80070057h
0x180009668  jmp     loc_18000984F
0x18000966d  mov     rdx, rdi
0x180009670  lea     rax, [rsp+2B0h+SubKey]
0x180009675  test    rsi, rsi
0x180009678  jz      short loc_180009699
0x18000967a  movzx   r8d, word ptr [rcx]
0x18000967e  test    r8w, r8w
0x180009682  jz      short loc_180009699
0x180009684  mov     [rax], r8w
0x180009688  add     rcx, 2
0x18000968c  add     rax, 2
0x180009690  dec     rsi
0x180009693  sub     rdx, 1
0x180009697  jnz     short loc_180009675
0x180009699  test    rdx, rdx
0x18000969c  lea     rcx, [rax-2]
0x1800096a0  cmovnz  rcx, rax
0x1800096a4  mov     [rcx], r14w
0x1800096a8  test    ebx, ebx
0x1800096aa  jnz     loc_18000984F
0x1800096b0  jmp     short loc_1800096B5
0x1800096b2  xor     r14d, r14d
0x1800096b5  mov     ebx, [rsp+2B0h+var_254]
0x1800096b9  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800096be  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800096c2  jz      short loc_1800096D3
0x1800096c4  call    cs:__imp_RegCloseKey
0x1800096ca  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x1800096d3  lea     rcx, [rsp+2B0h+SubKey]
0x1800096d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096dc  inc     rax
0x1800096df  cmp     [rcx+rax*2], r14w
0x1800096e4  jnz     short loc_1800096DC
0x1800096e6  sub     rdi, rax
0x1800096e9  lea     r8, aClsid_0; "\\CLSID"
0x1800096f0  mov     rdx, rdi; unsigned __int64
0x1800096f3  lea     rcx, [rsp+2B0h+SubKey]; wchar_t *
0x1800096f8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800096fd  xor     r8d, r8d; Reserved
0x180009700  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x180009705  mov     rcx, r12; hKey
0x180009708  test    ebx, ebx
0x18000970a  jz      short loc_180009734
0x18000970c  lea     rax, [rsp+2B0h+hKey]
0x180009711  mov     r9d, 2001Fh; samDesired
0x180009717  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000971c  call    cs:__imp_RegOpenKeyExW
0x180009722  test    eax, eax
0x180009724  jnz     loc_1800095A6
0x18000972a  mov     [rsp+2B0h+dwDisposition], 2
0x180009732  jmp     short loc_18000976D
0x180009734  lea     rax, [rsp+2B0h+dwDisposition]
0x180009739  xor     r9d, r9d; lpClass
0x18000973c  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x180009741  lea     rax, [rsp+2B0h+hKey]
0x180009746  mov     [rsp+2B0h+var_278], rax; phkResult
0x18000974b  mov     [rsp+2B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180009750  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x180009758  mov     dword ptr [rsp+2B0h+phkResult], r14d; dwOptions
0x18000975d  call    cs:__imp_RegCreateKeyExW
0x180009763  mov     ebx, eax
0x180009765  test    eax, eax
0x180009767  jnz     loc_18000984F
0x18000976d  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180009772  lea     rax, [rsp+2B0h+cbData]
0x180009777  mov     qword ptr [rsp+2B0h+samDesired], rax; lpcbData
0x18000977c  lea     r9, [rsp+2B0h+Type]; lpType
0x180009781  lea     rax, [rsp+2B0h+SubKey]
0x180009786  mov     [rsp+2B0h+cbData], 208h
0x18000978e  xor     r8d, r8d; lpReserved
0x180009791  mov     [rsp+2B0h+phkResult], rax; int
0x180009796  xor     edx, edx; lpValueName
0x180009798  call    cs:__imp_RegQueryValueExW
0x18000979e  mov     ebx, eax
0x1800097a0  test    eax, eax
0x1800097a2  jz      short loc_180009803
0x1800097a4  cmp     eax, 2
0x1800097a7  jnz     loc_18000984F
0x1800097ad  mov     edi, [rsp+2B0h+var_254]
0x1800097b1  test    edi, edi
0x1800097b3  jz      short loc_1800097BD
0x1800097b5  mov     ebx, r14d
0x1800097b8  jmp     loc_18000984F
0x1800097bd  mov     rcx, [r13+18h]
0x1800097c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800097c5  inc     rax
0x1800097c8  cmp     [rcx+rax*2], r14w
0x1800097cd  jnz     short loc_1800097C5
0x1800097cf  lea     eax, ds:2[rax*2]
0x1800097d6  mov     r9d, 1; dwType
0x1800097dc  mov     [rsp+2B0h+samDesired], eax; cbData
0x1800097e0  xor     r8d, r8d; Reserved
0x1800097e3  mov     [rsp+2B0h+phkResult], rcx; lpData
0x1800097e8  xor     edx, edx; lpValueName
0x1800097ea  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800097ef  call    cs:__imp_RegSetValueExW
0x1800097f5  mov     [rsp+2B0h+SubKey], r14w
0x1800097fb  mov     ebx, eax
0x1800097fd  test    eax, eax
0x1800097ff  jnz     short loc_18000984F
0x180009801  jmp     short loc_180009814
0x180009803  cmp     [rsp+2B0h+Type], 1
0x180009808  mov     eax, 80004005h
0x18000980d  mov     edi, [rsp+2B0h+var_254]
0x180009811  cmovnz  ebx, eax
0x180009814  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180009819  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000981d  jz      short loc_18000982E
0x18000981f  call    cs:__imp_RegCloseKey
0x180009825  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18000982e  test    ebx, ebx
0x180009830  jnz     short loc_18000984F
0x180009832  xor     ecx, ecx
0x180009834  lea     r8, [rsp+2B0h+SubKey]
0x180009839  cmp     cx, [rsp+2B0h+SubKey]
0x18000983e  mov     r9d, edi; int
0x180009841  mov     rcx, r13; struct SClassEntry *
0x180009844  cmovz   r8, r14; wchar_t *
0x180009848  call    ?RegisterACLSID@@YAJAEBUSClassEntry@@PEB_W1HH@Z; RegisterACLSID(SClassEntry const &,wchar_t const *,wchar_t const *,int,int)
0x18000984d  mov     ebx, eax
0x18000984f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180009854  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009858  jz      short loc_180009860
0x18000985a  call    cs:__imp_RegCloseKey
0x180009860  mov     eax, ebx
0x180009862  mov     rcx, [rbp+1B0h+var_30]
0x180009869  xor     rcx, rsp; StackCookie
0x18000986c  call    __security_check_cookie
0x180009871  lea     r11, [rsp+2B0h+var_20]
0x180009879  mov     rbx, [r11+38h]
0x18000987d  mov     rsi, [r11+40h]
0x180009881  mov     rsp, r11
0x180009884  pop     r14
0x180009886  pop     r13
0x180009888  pop     r12
0x18000988a  pop     rdi
0x18000988b  pop     rbp
0x18000988c  retn
```
