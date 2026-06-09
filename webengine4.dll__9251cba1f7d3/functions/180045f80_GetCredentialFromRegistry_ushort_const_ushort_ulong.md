# GetCredentialFromRegistry(ushort const *,ushort *,ulong)

- ea: `0x180045f80`
- end: `0x18004626e`
- name: `?GetCredentialFromRegistry@@YAJPEBGPEAGK@Z`
- size: `750`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ffc4`
- `0x180020dcc`

## callees

- `0x180013690`
- `0x180045f80`
- `0x18004d030`
- `0x18004d350`
- `0x1800653b4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180045ff0`
- `KERNEL32!lstrlenW` at `0x1800460f6`
- `KERNEL32!lstrlenW` at `0x180046107`
- `KERNEL32!lstrlenW` at `0x180045ff0`
- `KERNEL32!lstrlenW` at `0x1800460f6`
- `KERNEL32!lstrlenW` at `0x180046107`
- `KERNEL32!FormatMessageW` at `0x180046215`
- `KERNEL32!FormatMessageW` at `0x180046215`
- `KERNEL32!LocalFree` at `0x18004623e`
- `KERNEL32!LocalFree` at `0x18004623e`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800460b3`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800460c7`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800460b3`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800460c7`
- `ADVAPI32!RegCloseKey` at `0x18004622e`
- `ADVAPI32!RegCloseKey` at `0x18004622e`
- `ADVAPI32!RegOpenKeyExW` at `0x180046132`
- `ADVAPI32!RegOpenKeyExW` at `0x180046132`
- `ADVAPI32!RegQueryValueExW` at `0x180046161`
- `ADVAPI32!RegQueryValueExW` at `0x180046161`
- `CRYPT32!CryptUnprotectData` at `0x1800461a8`
- `CRYPT32!CryptUnprotectData` at `0x1800461a8`

## pseudocode

```c
__int64 __fastcall GetCredentialFromRegistry(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  __int64 v6; // rdi
  signed __int64 v7; // rbx
  wchar_t *v8; // rcx
  wchar_t v9; // ax
  wchar_t *v10; // rax
  DWORD LastWin32Error; // ebx
  wchar_t *v12; // rax
  const wchar_t *v13; // rdi
  wchar_t *v14; // rax
  const wchar_t *v15; // rsi
  wchar_t *v16; // rax
  wchar_t *v17; // rdi
  HKEY v18; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataOut; // [rsp+50h] [rbp-B0h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[1024]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Str[1024]; // [rsp+470h] [rbp+370h] BYREF

  v3 = a3;
  if ( !a1 )
    return 2147942487LL;
  if ( !*a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  if ( a3 < 0xA )
    return 2147942487LL;
  v6 = 1024;
  hKey = 0;
  cbData = 1024;
  Type = 0;
  if ( (unsigned __int64)lstrlenW(a1) >= 0x400 )
    return 2147942487LL;
  pDataOut.cbData = 0;
  v7 = (char *)a1 - (char *)Str;
  pDataOut.pbData = 0;
  v8 = Str;
  do
  {
    if ( v6 == -2147482622 )
      break;
    v9 = *(wchar_t *)((char *)v8 + v7);
    if ( !v9 )
      break;
    *v8++ = v9;
    --v6;
  }
  while ( v6 );
  v10 = v8 - 1;
  if ( v6 )
    v10 = v8;
  *v10 = 0;
  LastWin32Error = v6 == 0 ? 0x8007007A : 0;
  if ( !v6 )
    goto LABEL_30;
  v12 = wcschr_0(Str, 0x3Au);
  if ( !v12 )
    goto LABEL_29;
  v13 = v12 + 1;
  v14 = wcschr_0(v12 + 1, 0x5Cu);
  if ( !v14 )
    goto LABEL_29;
  *v14 = 0;
  v15 = v14 + 1;
  if ( _wcsicmp(v13, L"HKLM") )
  {
    if ( _wcsicmp(v13, L"HKEY_LOCAL_MACHINE") )
      goto LABEL_29;
  }
  v16 = wcschr_0(v15, 0x2Cu);
  v17 = v16;
  if ( !v16 )
    goto LABEL_29;
  *v16 = 0;
  if ( !lstrlenW(v16 + 1) || !lstrlenW(v15) )
    goto LABEL_29;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x20019u, &hKey)
    && !RegQueryValueExW(hKey, v17 + 1, 0, &Type, Data, &cbData) )
  {
    if ( Type == 3 )
    {
      pDataIn.cbData = cbData;
      pDataIn.pbData = Data;
      if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      {
        pDataOut.pbData = 0;
        goto LABEL_25;
      }
      cbData = pDataOut.cbData >> 1;
      if ( pDataOut.cbData >> 1 < (unsigned int)v3 )
      {
        StringCchCopyNW(a2, v3, (const unsigned __int16 *)pDataOut.pbData, pDataOut.cbData >> 1);
        a2[cbData] = 0;
        goto LABEL_31;
      }
    }
LABEL_29:
    LastWin32Error = -2147418113;
LABEL_30:
    FormatMessageW(0x1200u, 0, LastWin32Error, 0x800u, a2, v3, 0);
    goto LABEL_31;
  }
LABEL_25:
  LastWin32Error = GetLastWin32Error();
  if ( LastWin32Error )
    goto LABEL_30;
LABEL_31:
  v18 = hKey;
  a2[(unsigned int)(v3 - 1)] = 0;
  if ( v18 )
    RegCloseKey(v18);
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180045f80  push    rbp
0x180045f82  push    rbx
0x180045f83  push    rsi
0x180045f84  push    rdi
0x180045f85  push    r12
0x180045f87  push    r14
0x180045f89  push    r15
0x180045f8b  lea     rbp, [rsp-0B80h]
0x180045f93  sub     rsp, 0C80h
0x180045f9a  mov     rax, cs:__security_cookie
0x180045fa1  xor     rax, rsp
0x180045fa4  mov     [rbp+0BB0h+var_40], rax
0x180045fab  xor     r12d, r12d
0x180045fae  mov     r14d, r8d
0x180045fb1  mov     r15, rdx
0x180045fb4  mov     rbx, rcx
0x180045fb7  test    rcx, rcx
0x180045fba  jz      loc_180046248
0x180045fc0  cmp     [rcx], r12w
0x180045fc4  jz      loc_180046248
0x180045fca  test    rdx, rdx
0x180045fcd  jz      loc_180046248
0x180045fd3  cmp     r14d, 0Ah
0x180045fd7  jb      loc_180046248
0x180045fdd  mov     edi, 400h
0x180045fe2  mov     [rsp+0CB0h+hKey], r12
0x180045fe7  mov     [rsp+0CB0h+cbData], edi
0x180045feb  mov     [rsp+0CB0h+Type], r12d
0x180045ff0  call    cs:__imp_lstrlenW
0x180045ff6  movsxd  rcx, eax
0x180045ff9  cmp     rcx, rdi
0x180045ffc  jnb     loc_180046248
0x180046002  lea     rax, [rbp+0BB0h+Str]
0x180046009  mov     [rsp+0CB0h+var_C60.cbData], r12d
0x18004600e  sub     rbx, rax
0x180046011  mov     [rsp+0CB0h+var_C60.pbData], r12
0x180046016  lea     rcx, [rbp+0BB0h+Str]
0x18004601d  lea     rax, [rdi+7FFFFBFEh]
0x180046024  test    rax, rax
0x180046027  jz      short loc_18004603F
0x180046029  movzx   eax, word ptr [rbx+rcx]
0x18004602d  test    ax, ax
0x180046030  jz      short loc_18004603F
0x180046032  mov     [rcx], ax
0x180046035  add     rcx, 2
0x180046039  sub     rdi, 1
0x18004603d  jnz     short loc_18004601D
0x18004603f  test    rdi, rdi
0x180046042  lea     rax, [rcx-2]
0x180046046  cmovnz  rax, rcx
0x18004604a  mov     [rax], r12w
0x18004604e  mov     rax, rdi
0x180046051  neg     rax
0x180046054  sbb     ebx, ebx
0x180046056  not     ebx
0x180046058  and     ebx, 8007007Ah
0x18004605e  test    rdi, rdi
0x180046061  jz      loc_1800461F6
0x180046067  mov     edx, 3Ah ; ':'; Ch
0x18004606c  lea     rcx, [rbp+0BB0h+Str]; Str
0x180046073  call    wcschr_0
0x180046078  mov     rdi, rax
0x18004607b  test    rax, rax
0x18004607e  jz      loc_1800461F1
0x180046084  add     rdi, 2
0x180046088  mov     edx, 5Ch ; '\'; Ch
0x18004608d  mov     rcx, rdi; Str
0x180046090  call    wcschr_0
0x180046095  mov     rsi, rax
0x180046098  test    rax, rax
0x18004609b  jz      loc_1800461F1
0x1800460a1  lea     rdx, aHklm; "HKLM"
0x1800460a8  mov     [rax], r12w
0x1800460ac  mov     rcx, rdi; String1
0x1800460af  add     rsi, 2
0x1800460b3  call    cs:__imp__wcsicmp
0x1800460b9  test    eax, eax
0x1800460bb  jz      short loc_1800460D5
0x1800460bd  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x1800460c4  mov     rcx, rdi; String1
0x1800460c7  call    cs:__imp__wcsicmp
0x1800460cd  test    eax, eax
0x1800460cf  jnz     loc_1800461F1
0x1800460d5  mov     edx, 2Ch ; ','; Ch
0x1800460da  mov     rcx, rsi; Str
0x1800460dd  call    wcschr_0
0x1800460e2  mov     rdi, rax
0x1800460e5  test    rax, rax
0x1800460e8  jz      loc_1800461F1
0x1800460ee  lea     rcx, [rax+2]; lpString
0x1800460f2  mov     [rax], r12w
0x1800460f6  call    cs:__imp_lstrlenW
0x1800460fc  test    eax, eax
0x1800460fe  jz      loc_1800461F1
0x180046104  mov     rcx, rsi; lpString
0x180046107  call    cs:__imp_lstrlenW
0x18004610d  test    eax, eax
0x18004610f  jz      loc_1800461F1
0x180046115  lea     rax, [rsp+0CB0h+hKey]
0x18004611a  mov     r9d, 20019h; samDesired
0x180046120  xor     r8d, r8d; ulOptions
0x180046123  mov     [rsp+0CB0h+phkResult], rax; phkResult
0x180046128  mov     rdx, rsi; lpSubKey
0x18004612b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046132  call    cs:__imp_RegOpenKeyExW
0x180046138  test    eax, eax
0x18004613a  jnz     short loc_1800461B7
0x18004613c  mov     rcx, [rsp+0CB0h+hKey]; hKey
0x180046141  lea     rax, [rsp+0CB0h+cbData]
0x180046146  mov     [rsp+0CB0h+lpcbData], rax; lpcbData
0x18004614b  lea     r9, [rsp+0CB0h+Type]; lpType
0x180046150  lea     rax, [rsp+0CB0h+Data]
0x180046155  xor     r8d, r8d; lpReserved
0x180046158  lea     rdx, [rdi+2]; lpValueName
0x18004615c  mov     [rsp+0CB0h+phkResult], rax; lpData
0x180046161  call    cs:__imp_RegQueryValueExW
0x180046167  test    eax, eax
0x180046169  jnz     short loc_1800461B7
0x18004616b  cmp     [rsp+0CB0h+Type], 3
0x180046170  jnz     short loc_1800461F1
0x180046172  mov     eax, [rsp+0CB0h+cbData]
0x180046176  lea     rcx, [rsp+0CB0h+pDataIn]; pDataIn
0x18004617b  mov     [rsp+0CB0h+pDataIn.cbData], eax
0x18004617f  xor     r9d, r9d; pvReserved
0x180046182  lea     rax, [rsp+0CB0h+Data]
0x180046187  xor     r8d, r8d; pOptionalEntropy
0x18004618a  mov     [rsp+0CB0h+pDataIn.pbData], rax
0x18004618f  xor     edx, edx; ppszDataDescr
0x180046191  lea     rax, [rsp+0CB0h+var_C60]
0x180046196  mov     [rsp+0CB0h+pDataOut], rax; pDataOut
0x18004619b  mov     dword ptr [rsp+0CB0h+lpcbData], 1; dwFlags
0x1800461a3  mov     [rsp+0CB0h+phkResult], r12; pPromptStruct
0x1800461a8  call    cs:__imp_CryptUnprotectData
0x1800461ae  test    eax, eax
0x1800461b0  jnz     short loc_1800461C4
0x1800461b2  mov     [rsp+0CB0h+var_C60.pbData], r12
0x1800461b7  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800461bc  mov     ebx, eax
0x1800461be  test    eax, eax
0x1800461c0  jz      short loc_18004621B
0x1800461c2  jmp     short loc_1800461F6
0x1800461c4  mov     eax, [rsp+0CB0h+var_C60.cbData]
0x1800461c8  shr     eax, 1
0x1800461ca  mov     [rsp+0CB0h+cbData], eax
0x1800461ce  cmp     eax, r14d
0x1800461d1  jnb     short loc_1800461F1
0x1800461d3  mov     r8, [rsp+0CB0h+var_C60.pbData]; unsigned __int16 *
0x1800461d8  mov     rdx, r14; unsigned __int64
0x1800461db  mov     r9d, eax; unsigned __int64
0x1800461de  mov     rcx, r15; unsigned __int16 *
0x1800461e1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800461e6  mov     eax, [rsp+0CB0h+cbData]
0x1800461ea  mov     [r15+rax*2], r12w
0x1800461ef  jmp     short loc_18004621B
0x1800461f1  mov     ebx, 8000FFFFh
0x1800461f6  mov     [rsp+0CB0h+pDataOut], r12; Arguments
0x1800461fb  mov     r9d, 800h; dwLanguageId
0x180046201  mov     dword ptr [rsp+0CB0h+lpcbData], r14d; nSize
0x180046206  mov     r8d, ebx; dwMessageId
0x180046209  xor     edx, edx; lpSource
0x18004620b  mov     [rsp+0CB0h+phkResult], r15; lpBuffer
0x180046210  mov     ecx, 1200h; dwFlags
0x180046215  call    cs:__imp_FormatMessageW
0x18004621b  mov     rcx, [rsp+0CB0h+hKey]; hKey
0x180046220  lea     eax, [r14-1]
0x180046224  mov     [r15+rax*2], r12w
0x180046229  test    rcx, rcx
0x18004622c  jz      short loc_180046234
0x18004622e  call    cs:__imp_RegCloseKey
0x180046234  mov     rcx, [rsp+0CB0h+var_C60.pbData]; hMem
0x180046239  test    rcx, rcx
0x18004623c  jz      short loc_180046244
0x18004623e  call    cs:__imp_LocalFree
0x180046244  mov     eax, ebx
0x180046246  jmp     short loc_18004624D
0x180046248  mov     eax, 80070057h
0x18004624d  mov     rcx, [rbp+0BB0h+var_40]
0x180046254  xor     rcx, rsp; StackCookie
0x180046257  call    __security_check_cookie
0x18004625c  add     rsp, 0C80h
0x180046263  pop     r15
0x180046265  pop     r14
0x180046267  pop     r12
0x180046269  pop     rdi
0x18004626a  pop     rsi
0x18004626b  pop     rbx
0x18004626c  pop     rbp
0x18004626d  retn
```
