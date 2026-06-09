# GetRegProvider

- ea: `0x18000e800`
- end: `0x18000ed75`
- name: `GetRegProvider`
- size: `1397`
- prototype: `__int64 __fastcall(unsigned __int8 *, WCHAR *, BYTE *, CHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e4e0`

## callees

- `0x18000e800`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed41`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ed21`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ed21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eca2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ece4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000eca2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ece4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed6a`

## pseudocode

```c
__int64 __fastcall GetRegProvider(unsigned __int8 *a1, WCHAR *a2, BYTE *a3, CHAR *a4)
{
  unsigned int v7; // ecx
  wchar_t v8; // ax
  unsigned int v9; // ecx
  wchar_t v10; // ax
  unsigned int v11; // ecx
  wchar_t v12; // ax
  unsigned int v13; // ecx
  wchar_t v14; // ax
  unsigned int v15; // ecx
  wchar_t v16; // ax
  unsigned int v17; // ecx
  wchar_t v18; // ax
  unsigned int v19; // ecx
  wchar_t v20; // ax
  unsigned int v21; // ecx
  wchar_t v22; // ax
  unsigned int v23; // ecx
  __int64 v24; // rbx
  wchar_t v25; // ax
  unsigned int v26; // ecx
  wchar_t v27; // ax
  unsigned int v28; // ecx
  wchar_t v29; // ax
  unsigned int v30; // ecx
  wchar_t v31; // ax
  unsigned int v32; // ecx
  wchar_t v33; // ax
  unsigned int v34; // ecx
  wchar_t v35; // ax
  unsigned int v36; // ecx
  wchar_t v37; // ax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // r10
  WCHAR *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r8
  WCHAR *v44; // rcx
  __int64 v45; // rdx
  WCHAR *v46; // rax
  __int64 v47; // rcx
  _WORD *v48; // r8
  const unsigned __int16 *v49; // r9
  _WORD *v50; // rcx
  __int64 v51; // rdx
  WCHAR *v52; // rax
  _WORD *v53; // r8
  _WORD *v54; // rcx
  _WORD *v55; // rcx
  LSTATUS v57; // eax
  HKEY v58; // rcx
  int v60; // eax
  HKEY v61; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v65[37]; // [rsp+50h] [rbp-B0h] BYREF
  int v66; // [rsp+9Ah] [rbp-66h]
  WCHAR SubKey[128]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v68[2]; // [rsp+1A0h] [rbp+A0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !a1 )
    goto LABEL_45;
  if ( !a2 )
    goto LABEL_45;
  if ( !a3 )
    goto LABEL_45;
  if ( !a4 )
    goto LABEL_45;
  *(_WORD *)a3 = 0;
  v65[0] = 123;
  *a4 = 0;
  v7 = a1[3];
  v65[9] = 45;
  v65[14] = 45;
  v65[19] = 45;
  v65[1] = a0123456789abcd_0[(unsigned __int64)v7 >> 4];
  v8 = a0123456789abcd_0[v7 & 0xF];
  v9 = a1[2];
  v65[2] = v8;
  v65[3] = a0123456789abcd_0[(unsigned __int64)v9 >> 4];
  v10 = a0123456789abcd_0[v9 & 0xF];
  v11 = a1[1];
  v65[4] = v10;
  v65[5] = a0123456789abcd_0[(unsigned __int64)v11 >> 4];
  v12 = a0123456789abcd_0[v11 & 0xF];
  v13 = *a1;
  v65[6] = v12;
  v65[7] = a0123456789abcd_0[(unsigned __int64)v13 >> 4];
  v14 = a0123456789abcd_0[v13 & 0xF];
  v15 = a1[5];
  v65[8] = v14;
  v65[10] = a0123456789abcd_0[(unsigned __int64)v15 >> 4];
  v16 = a0123456789abcd_0[v15 & 0xF];
  v17 = a1[4];
  v65[11] = v16;
  v65[12] = a0123456789abcd_0[(unsigned __int64)v17 >> 4];
  v18 = a0123456789abcd_0[v17 & 0xF];
  v19 = a1[7];
  v65[13] = v18;
  v65[15] = a0123456789abcd_0[(unsigned __int64)v19 >> 4];
  v20 = a0123456789abcd_0[v19 & 0xF];
  v21 = a1[6];
  v65[16] = v20;
  v65[17] = a0123456789abcd_0[(unsigned __int64)v21 >> 4];
  v22 = a0123456789abcd_0[v21 & 0xF];
  v23 = a1[8];
  v65[18] = v22;
  v65[20] = a0123456789abcd_0[(unsigned __int64)v23 >> 4];
  v65[21] = a0123456789abcd_0[v23 & 0xF];
  LOBYTE(v23) = a1[9];
  v24 = -1;
  v65[24] = 45;
  v66 = 125;
  v65[22] = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v23 >> 4];
  v25 = a0123456789abcd_0[v23 & 0xF];
  v26 = a1[10];
  v65[23] = v25;
  v65[25] = a0123456789abcd_0[(unsigned __int64)v26 >> 4];
  v27 = a0123456789abcd_0[v26 & 0xF];
  v28 = a1[11];
  v65[26] = v27;
  v65[27] = a0123456789abcd_0[(unsigned __int64)v28 >> 4];
  v29 = a0123456789abcd_0[v28 & 0xF];
  v30 = a1[12];
  v65[28] = v29;
  v65[29] = a0123456789abcd_0[(unsigned __int64)v30 >> 4];
  v31 = a0123456789abcd_0[v30 & 0xF];
  v32 = a1[13];
  v65[30] = v31;
  v65[31] = a0123456789abcd_0[(unsigned __int64)v32 >> 4];
  v33 = a0123456789abcd_0[v32 & 0xF];
  v34 = a1[14];
  v65[32] = v33;
  v65[33] = a0123456789abcd_0[(unsigned __int64)v34 >> 4];
  v35 = a0123456789abcd_0[v34 & 0xF];
  v36 = a1[15];
  v65[34] = v35;
  v65[35] = a0123456789abcd_0[(unsigned __int64)v36 >> 4];
  v37 = a0123456789abcd_0[v36 & 0xF];
  v38 = -1;
  v65[36] = v37;
  do
    ++v38;
  while ( v65[v38] );
  v39 = -1;
  do
    ++v39;
  while ( a2[v39] );
  if ( (unsigned __int64)(v38 + v39 + 2) > 0x80 )
  {
LABEL_45:
    SetLastError(0x57u);
    return 0;
  }
  v40 = 2147483646;
  v41 = SubKey;
  v42 = 2147483646;
  v43 = 128;
  do
  {
    if ( !v42 )
      break;
    if ( !*a2 )
      break;
    *v41++ = *a2++;
    --v42;
    --v43;
  }
  while ( v43 );
  v44 = v41 - 1;
  v45 = 128;
  if ( v43 )
    v44 = v41;
  v46 = SubKey;
  *v44 = 0;
  while ( *v46 )
  {
    ++v46;
    if ( !--v45 )
      goto LABEL_27;
  }
  v47 = 2147483646;
  v48 = (_WORD *)v68 - v45;
  v49 = L"\\";
  do
  {
    if ( !v47 )
      break;
    if ( !*v49 )
      break;
    *v48++ = *v49++;
    --v47;
    --v45;
  }
  while ( v45 );
  v50 = v48 - 1;
  if ( v45 )
    v50 = v48;
  *v50 = 0;
LABEL_27:
  v51 = 128;
  v52 = SubKey;
  while ( *v52 )
  {
    ++v52;
    if ( !--v51 )
      goto LABEL_38;
  }
  v53 = (_WORD *)v68 - v51;
  v54 = v65;
  do
  {
    if ( !v40 )
      break;
    if ( !*v54 )
      break;
    *v53++ = *v54++;
    --v40;
    --v51;
  }
  while ( v51 );
  v55 = v53 - 1;
  if ( v51 )
    v55 = v53;
  *v55 = 0;
LABEL_38:
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    return 0;
  Type = 0;
  cbData = 256;
  v57 = RegQueryValueExW(hKey, L"$DLL", 0, &Type, a3, &cbData);
  v58 = hKey;
  if ( v57 )
  {
    *(_WORD *)a3 = 0;
LABEL_44:
    RegCloseKey(v58);
    return 0;
  }
  Type = 0;
  cbData = 128;
  if ( RegQueryValueExW(hKey, L"$Function", 0, &Type, (LPBYTE)SubKey, &cbData) )
  {
    v61 = hKey;
    *a4 = 0;
    RegCloseKey(v61);
    return 0;
  }
  while ( SubKey[++v24] != 0 )
    ;
  v60 = WideCharToMultiByte(0, 0, SubKey, v24 + 1, a4, 64, 0, 0);
  v58 = hKey;
  if ( v60 < 1 )
    goto LABEL_44;
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18000e800  mov     [rsp-8+arg_0], rbx
0x18000e805  mov     [rsp-8+arg_8], rsi
0x18000e80a  push    rbp
0x18000e80b  push    rdi
0x18000e80c  push    r14
0x18000e80e  lea     rbp, [rsp-0B0h]
0x18000e816  sub     rsp, 1B0h
0x18000e81d  mov     rax, cs:__security_cookie
0x18000e824  xor     rax, rsp
0x18000e827  mov     [rbp+0C0h+var_20], rax
0x18000e82e  xor     r14d, r14d
0x18000e831  mov     rsi, r9
0x18000e834  mov     [rsp+1C0h+hKey], r14
0x18000e839  mov     rdi, r8
0x18000e83c  mov     [rsp+1C0h+Type], r14d
0x18000e841  mov     r10, rcx
0x18000e844  mov     [rsp+1C0h+cbData], r14d
0x18000e849  test    rcx, rcx
0x18000e84c  jz      loc_18000ED3C
0x18000e852  test    rdx, rdx
0x18000e855  jz      loc_18000ED3C
0x18000e85b  test    r8, r8
0x18000e85e  jz      loc_18000ED3C
0x18000e864  test    r9, r9
0x18000e867  jz      loc_18000ED3C
0x18000e86d  mov     [r8], r14w
0x18000e871  mov     eax, 7Bh ; '{'
0x18000e876  mov     [rsp+1C0h+var_170], ax
0x18000e87b  mov     r8d, 2Dh ; '-'
0x18000e881  mov     [r9], r14b
0x18000e884  lea     r9, a0123456789abcd_0; "0123456789ABCDEF"
0x18000e88b  movzx   ecx, byte ptr [rcx+3]
0x18000e88f  mov     eax, ecx
0x18000e891  mov     [rsp+1C0h+var_15E], r8w
0x18000e897  shr     rax, 4
0x18000e89b  and     ecx, 0Fh
0x18000e89e  mov     [rsp+1C0h+var_154], r8w
0x18000e8a4  mov     [rsp+1C0h+var_14A], r8w
0x18000e8aa  movzx   eax, word ptr [r9+rax*2]
0x18000e8af  mov     [rsp+1C0h+var_16E], ax
0x18000e8b4  movzx   eax, word ptr [r9+rcx*2]
0x18000e8b9  movzx   ecx, byte ptr [r10+2]
0x18000e8be  mov     [rsp+1C0h+var_16C], ax
0x18000e8c3  mov     eax, ecx
0x18000e8c5  shr     rax, 4
0x18000e8c9  and     ecx, 0Fh
0x18000e8cc  movzx   eax, word ptr [r9+rax*2]
0x18000e8d1  mov     [rsp+1C0h+var_16A], ax
0x18000e8d6  movzx   eax, word ptr [r9+rcx*2]
0x18000e8db  movzx   ecx, byte ptr [r10+1]
0x18000e8e0  mov     [rsp+1C0h+var_168], ax
0x18000e8e5  mov     eax, ecx
0x18000e8e7  shr     rax, 4
0x18000e8eb  and     ecx, 0Fh
0x18000e8ee  movzx   eax, word ptr [r9+rax*2]
0x18000e8f3  mov     [rsp+1C0h+var_166], ax
0x18000e8f8  movzx   eax, word ptr [r9+rcx*2]
0x18000e8fd  movzx   ecx, byte ptr [r10]
0x18000e901  mov     [rsp+1C0h+var_164], ax
0x18000e906  mov     eax, ecx
0x18000e908  shr     rax, 4
0x18000e90c  and     ecx, 0Fh
0x18000e90f  movzx   eax, word ptr [r9+rax*2]
0x18000e914  mov     [rsp+1C0h+var_162], ax
0x18000e919  movzx   eax, word ptr [r9+rcx*2]
0x18000e91e  movzx   ecx, byte ptr [r10+5]
0x18000e923  mov     [rsp+1C0h+var_160], ax
0x18000e928  mov     eax, ecx
0x18000e92a  shr     rax, 4
0x18000e92e  and     ecx, 0Fh
0x18000e931  movzx   eax, word ptr [r9+rax*2]
0x18000e936  mov     [rsp+1C0h+var_15C], ax
0x18000e93b  movzx   eax, word ptr [r9+rcx*2]
0x18000e940  movzx   ecx, byte ptr [r10+4]
0x18000e945  mov     [rsp+1C0h+var_15A], ax
0x18000e94a  mov     eax, ecx
0x18000e94c  shr     rax, 4
0x18000e950  and     ecx, 0Fh
0x18000e953  movzx   eax, word ptr [r9+rax*2]
0x18000e958  mov     [rsp+1C0h+var_158], ax
0x18000e95d  movzx   eax, word ptr [r9+rcx*2]
0x18000e962  movzx   ecx, byte ptr [r10+7]
0x18000e967  mov     [rsp+1C0h+var_156], ax
0x18000e96c  mov     eax, ecx
0x18000e96e  shr     rax, 4
0x18000e972  and     ecx, 0Fh
0x18000e975  movzx   eax, word ptr [r9+rax*2]
0x18000e97a  mov     [rsp+1C0h+var_152], ax
0x18000e97f  movzx   eax, word ptr [r9+rcx*2]
0x18000e984  movzx   ecx, byte ptr [r10+6]
0x18000e989  mov     [rsp+1C0h+var_150], ax
0x18000e98e  mov     eax, ecx
0x18000e990  shr     rax, 4
0x18000e994  and     ecx, 0Fh
0x18000e997  movzx   eax, word ptr [r9+rax*2]
0x18000e99c  mov     [rsp+1C0h+var_14E], ax
0x18000e9a1  movzx   eax, word ptr [r9+rcx*2]
0x18000e9a6  movzx   ecx, byte ptr [r10+8]
0x18000e9ab  mov     [rsp+1C0h+var_14C], ax
0x18000e9b0  mov     eax, ecx
0x18000e9b2  shr     rax, 4
0x18000e9b6  and     ecx, 0Fh
0x18000e9b9  movzx   eax, word ptr [r9+rax*2]
0x18000e9be  mov     [rsp+1C0h+var_148], ax
0x18000e9c3  movzx   eax, word ptr [r9+rcx*2]
0x18000e9c8  mov     [rsp+1C0h+var_146], ax
0x18000e9cd  movzx   ecx, byte ptr [r10+9]
0x18000e9d2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e9d9  mov     eax, ecx
0x18000e9db  mov     [rbp+0C0h+var_140], r8w
0x18000e9e0  shr     rax, 4
0x18000e9e4  and     ecx, 0Fh
0x18000e9e7  mov     [rbp+0C0h+var_126], 7Dh ; '}'
0x18000e9ee  movzx   eax, word ptr [r9+rax*2]
0x18000e9f3  mov     [rsp+1C0h+var_144], ax
0x18000e9f8  movzx   eax, word ptr [r9+rcx*2]
0x18000e9fd  movzx   ecx, byte ptr [r10+0Ah]
0x18000ea02  mov     [rsp+1C0h+var_142], ax
0x18000ea07  mov     eax, ecx
0x18000ea09  shr     rax, 4
0x18000ea0d  and     ecx, 0Fh
0x18000ea10  movzx   eax, word ptr [r9+rax*2]
0x18000ea15  mov     [rbp+0C0h+var_13E], ax
0x18000ea19  movzx   eax, word ptr [r9+rcx*2]
0x18000ea1e  movzx   ecx, byte ptr [r10+0Bh]
0x18000ea23  mov     [rbp+0C0h+var_13C], ax
0x18000ea27  mov     eax, ecx
0x18000ea29  shr     rax, 4
0x18000ea2d  and     ecx, 0Fh
0x18000ea30  movzx   eax, word ptr [r9+rax*2]
0x18000ea35  mov     [rbp+0C0h+var_13A], ax
0x18000ea39  movzx   eax, word ptr [r9+rcx*2]
0x18000ea3e  movzx   ecx, byte ptr [r10+0Ch]
0x18000ea43  mov     [rbp+0C0h+var_138], ax
0x18000ea47  mov     eax, ecx
0x18000ea49  shr     rax, 4
0x18000ea4d  and     ecx, 0Fh
0x18000ea50  movzx   eax, word ptr [r9+rax*2]
0x18000ea55  mov     [rbp+0C0h+var_136], ax
0x18000ea59  movzx   eax, word ptr [r9+rcx*2]
0x18000ea5e  movzx   ecx, byte ptr [r10+0Dh]
0x18000ea63  mov     [rbp+0C0h+var_134], ax
0x18000ea67  mov     eax, ecx
0x18000ea69  shr     rax, 4
0x18000ea6d  and     ecx, 0Fh
0x18000ea70  movzx   eax, word ptr [r9+rax*2]
0x18000ea75  mov     [rbp+0C0h+var_132], ax
0x18000ea79  movzx   eax, word ptr [r9+rcx*2]
0x18000ea7e  movzx   ecx, byte ptr [r10+0Eh]
0x18000ea83  mov     [rbp+0C0h+var_130], ax
0x18000ea87  mov     eax, ecx
0x18000ea89  shr     rax, 4
0x18000ea8d  and     ecx, 0Fh
0x18000ea90  movzx   eax, word ptr [r9+rax*2]
0x18000ea95  mov     [rbp+0C0h+var_12E], ax
0x18000ea99  movzx   eax, word ptr [r9+rcx*2]
0x18000ea9e  movzx   ecx, byte ptr [r10+0Fh]
0x18000eaa3  mov     [rbp+0C0h+var_12C], ax
0x18000eaa7  mov     eax, ecx
0x18000eaa9  shr     rax, 4
0x18000eaad  and     ecx, 0Fh
0x18000eab0  movzx   eax, word ptr [r9+rax*2]
0x18000eab5  mov     [rbp+0C0h+var_12A], ax
0x18000eab9  movzx   eax, word ptr [r9+rcx*2]
0x18000eabe  mov     rcx, rbx
0x18000eac1  mov     [rbp+0C0h+var_128], ax
0x18000eac5  lea     rax, [rsp+1C0h+var_170]
0x18000eaca  nop     word ptr [rax+rax+00h]
0x18000ead0  inc     rcx
0x18000ead3  cmp     [rax+rcx*2], r14w
0x18000ead8  jnz     short loc_18000EAD0
0x18000eada  mov     rax, rbx
0x18000eadd  nop     dword ptr [rax]
0x18000eae0  inc     rax
0x18000eae3  cmp     [rdx+rax*2], r14w
0x18000eae8  jnz     short loc_18000EAE0
0x18000eaea  add     rax, 2
0x18000eaee  add     rax, rcx
0x18000eaf1  cmp     rax, 80h
0x18000eaf7  ja      loc_18000ED3C
0x18000eafd  mov     r10d, 7FFFFFFEh
0x18000eb03  lea     rax, [rbp+0C0h+SubKey]
0x18000eb07  mov     ecx, r10d
0x18000eb0a  mov     r8d, 80h
0x18000eb10  test    rcx, rcx
0x18000eb13  jz      short loc_18000EB34
0x18000eb15  movzx   r9d, word ptr [rdx]
0x18000eb19  test    r9w, r9w
0x18000eb1d  jz      short loc_18000EB34
0x18000eb1f  mov     [rax], r9w
0x18000eb23  add     rdx, 2
0x18000eb27  add     rax, 2
0x18000eb2b  dec     rcx
0x18000eb2e  sub     r8, 1
0x18000eb32  jnz     short loc_18000EB10
0x18000eb34  lea     rcx, [rax-2]
0x18000eb38  test    r8, r8
0x18000eb3b  mov     edx, 80h
0x18000eb40  cmovnz  rcx, rax
0x18000eb44  lea     rax, [rbp+0C0h+SubKey]
0x18000eb48  mov     [rcx], r14w
0x18000eb4c  nop     dword ptr [rax+00h]
0x18000eb50  cmp     [rax], r14w
0x18000eb54  jz      short loc_18000EB62
0x18000eb56  add     rax, 2
0x18000eb5a  sub     rdx, 1
0x18000eb5e  jnz     short loc_18000EB50
0x18000eb60  jmp     short loc_18000EBB2
0x18000eb62  lea     rax, [rdx+rdx]
0x18000eb66  mov     rcx, r10
0x18000eb69  lea     r8, [rbp+0C0h+var_20]
0x18000eb70  sub     r8, rax
0x18000eb73  lea     r9, asc_1800557E4; "\\"
0x18000eb7a  test    rdx, rdx
0x18000eb7d  jz      short loc_18000EBA3
0x18000eb7f  nop
0x18000eb80  test    rcx, rcx
0x18000eb83  jz      short loc_18000EBA3
0x18000eb85  movzx   eax, word ptr [r9]
0x18000eb89  test    ax, ax
0x18000eb8c  jz      short loc_18000EBA3
0x18000eb8e  mov     [r8], ax
0x18000eb92  add     r9, 2
0x18000eb96  add     r8, 2
0x18000eb9a  dec     rcx
0x18000eb9d  sub     rdx, 1
0x18000eba1  jnz     short loc_18000EB80
0x18000eba3  test    rdx, rdx
0x18000eba6  lea     rcx, [r8-2]
0x18000ebaa  cmovnz  rcx, r8
0x18000ebae  mov     [rcx], r14w
0x18000ebb2  mov     edx, 80h
0x18000ebb7  lea     rax, [rbp+0C0h+SubKey]
0x18000ebbb  nop     dword ptr [rax+rax+00h]
0x18000ebc0  cmp     [rax], r14w
0x18000ebc4  jz      short loc_18000EBD2
0x18000ebc6  add     rax, 2
0x18000ebca  sub     rdx, 1
0x18000ebce  jnz     short loc_18000EBC0
0x18000ebd0  jmp     short loc_18000EC21
0x18000ebd2  lea     rax, [rdx+rdx]
0x18000ebd6  lea     r8, [rbp+0C0h+var_20]
0x18000ebdd  sub     r8, rax
0x18000ebe0  lea     rcx, [rsp+1C0h+var_170]
0x18000ebe5  test    rdx, rdx
0x18000ebe8  jz      short loc_18000EC12
0x18000ebea  nop     word ptr [rax+rax+00h]
0x18000ebf0  test    r10, r10
0x18000ebf3  jz      short loc_18000EC12
0x18000ebf5  movzx   eax, word ptr [rcx]
0x18000ebf8  test    ax, ax
0x18000ebfb  jz      short loc_18000EC12
0x18000ebfd  mov     [r8], ax
0x18000ec01  add     rcx, 2
0x18000ec05  add     r8, 2
0x18000ec09  dec     r10
0x18000ec0c  sub     rdx, 1
0x18000ec10  jnz     short loc_18000EBF0
0x18000ec12  test    rdx, rdx
0x18000ec15  lea     rcx, [r8-2]
0x18000ec19  cmovnz  rcx, r8
0x18000ec1d  mov     [rcx], r14w
0x18000ec21  lea     rax, [rsp+1C0h+hKey]
0x18000ec26  mov     r9d, 20019h; samDesired
0x18000ec2c  xor     r8d, r8d; ulOptions
0x18000ec2f  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18000ec34  lea     rdx, [rbp+0C0h+SubKey]; lpSubKey
0x18000ec38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ec3f  call    cs:__imp_RegOpenKeyExW
0x18000ec45  test    eax, eax
0x18000ec47  jz      short loc_18000EC72
0x18000ec49  xor     eax, eax
0x18000ec4b  mov     rcx, [rbp+0C0h+var_20]
0x18000ec52  xor     rcx, rsp; StackCookie
0x18000ec55  call    __security_check_cookie
0x18000ec5a  lea     r11, [rsp+1C0h+var_10]
0x18000ec62  mov     rbx, [r11+20h]
0x18000ec66  mov     rsi, [r11+28h]
0x18000ec6a  mov     rsp, r11
0x18000ec6d  pop     r14
0x18000ec6f  pop     rdi
0x18000ec70  pop     rbp
0x18000ec71  retn
0x18000ec72  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000ec77  lea     rax, [rsp+1C0h+cbData]
0x18000ec7c  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18000ec81  lea     r9, [rsp+1C0h+Type]; lpType
0x18000ec86  xor     r8d, r8d; lpReserved
0x18000ec89  mov     [rsp+1C0h+phkResult], rdi; lpData
0x18000ec8e  lea     rdx, aDll; "$DLL"
0x18000ec95  mov     [rsp+1C0h+Type], r14d
0x18000ec9a  mov     [rsp+1C0h+cbData], 100h
0x18000eca2  call    cs:__imp_RegQueryValueExW
0x18000eca8  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000ecad  test    eax, eax
0x18000ecaf  jnz     loc_18000ED5C
0x18000ecb5  lea     rax, [rsp+1C0h+cbData]
0x18000ecba  mov     [rsp+1C0h+Type], r14d
0x18000ecbf  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18000ecc4  lea     r9, [rsp+1C0h+Type]; lpType
  ... truncated ...
```
