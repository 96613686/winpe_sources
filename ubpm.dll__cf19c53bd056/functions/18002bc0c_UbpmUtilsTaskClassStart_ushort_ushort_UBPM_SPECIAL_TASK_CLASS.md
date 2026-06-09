# UbpmUtilsTaskClassStart(ushort *,ushort *,_UBPM_SPECIAL_TASK_CLASS *)

- ea: `0x18002bc0c`
- end: `0x18002be77`
- name: `?UbpmUtilsTaskClassStart@@YAKPEAG0PEAU_UBPM_SPECIAL_TASK_CLASS@@@Z`
- size: `619`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, struct _UBPM_SPECIAL_TASK_CLASS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002be80`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x18002ab08`
- `0x18002bc0c`
- `0x18003d7d2`
- `0x18003d7ea`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bc71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bc71`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002bd6c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002bd6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be47`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bcc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bcc1`

## pseudocode

```c
__int64 __fastcall UbpmUtilsTaskClassStart(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _UBPM_SPECIAL_TASK_CLASS *a3)
{
  DWORD v3; // r15d
  unsigned int v4; // ebx
  WCHAR *v5; // r12
  BYTE *v6; // rdi
  unsigned __int64 v7; // r13
  char *v8; // r14
  DWORD v9; // esi
  wchar_t *v10; // rcx
  size_t v11; // r8
  DWORD v12; // ebx
  DWORD v13; // edx
  char *v14; // rsi
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-9h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-1h] BYREF
  DWORD Type; // [rsp+74h] [rbp+3h] BYREF
  DWORD v20; // [rsp+78h] [rbp+7h]
  int v21; // [rsp+7Ch] [rbp+Bh]
  HKEY hKey; // [rsp+80h] [rbp+Fh] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+67h] BYREF
  int v24; // [rsp+DCh] [rbp+6Bh]
  wchar_t *String2; // [rsp+E0h] [rbp+6Fh]
  struct _UBPM_SPECIAL_TASK_CLASS *v26; // [rsp+E8h] [rbp+77h]
  DWORD cbMaxValueLen; // [rsp+F0h] [rbp+7Fh] BYREF

  v26 = a3;
  String2 = a2;
  v24 = HIDWORD(a1);
  v3 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  cbMaxValueLen = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Ubpm", 0, 0x20019u, &hKey);
  if ( v4 )
    goto LABEL_25;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v4 )
    goto LABEL_25;
  if ( !cValues )
  {
    v4 = 0;
    goto LABEL_25;
  }
  cbMaxValueLen += 2;
  ++cbMaxValueNameLen;
  v5 = (WCHAR *)UbpmAlloc(2 * cbMaxValueNameLen);
  if ( !v5 )
  {
    v4 = 14;
    goto LABEL_25;
  }
  v6 = (BYTE *)UbpmAlloc(cbMaxValueLen);
  if ( !v6 )
  {
    v4 = 14;
    goto LABEL_23;
  }
  v7 = 0;
  v8 = 0;
  v21 = 0;
  v9 = 0;
  v20 = 0;
  if ( !cValues )
  {
LABEL_22:
    v4 = 0;
    *(_QWORD *)v26 = v8;
    goto LABEL_23;
  }
  while ( 1 )
  {
    cchValueName = cbMaxValueNameLen;
    cbData = cbMaxValueLen;
    if ( RegEnumValueW(hKey, v3, v5, &cchValueName, 0, &Type, v6, &cbData) )
      goto LABEL_21;
    if ( Type != 1 )
      goto LABEL_21;
    v10 = String2;
    v11 = -1;
    *(_WORD *)&v6[2 * (cbData >> 1) - 2] = 0;
    do
      ++v11;
    while ( v10[v11] );
    if ( cchValueName < v11 )
      goto LABEL_21;
    v12 = cbData;
    if ( cbData <= 2 || wcsncmp_0(v5, v10, v11) )
      goto LABEL_21;
    v13 = v9 + v12;
    if ( v7 < (unsigned __int64)(v9 + v12) + 2 )
      break;
LABEL_20:
    memcpy_0(&v8[v7], v6, v12);
    v7 = cbData + v21;
    v21 += cbData;
LABEL_21:
    if ( ++v3 >= cValues )
      goto LABEL_22;
  }
  v14 = v8;
  v8 = (char *)UbpmReAlloc(v8, v13 + 2);
  if ( v8 )
  {
    v12 = cbData;
    v9 = cbData + v20 + 2;
    v20 = v9;
    goto LABEL_20;
  }
  v4 = 14;
  if ( v14 )
    UBPM_MIDL_user_free(v14);
LABEL_23:
  UBPM_MIDL_user_free(v5);
  if ( v6 )
    UBPM_MIDL_user_free(v6);
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18002bc0c  mov     rax, rsp
0x18002bc0f  mov     [rax+18h], r8
0x18002bc13  mov     [rax+10h], rdx
0x18002bc17  mov     [rax+8], rcx
0x18002bc1b  push    rbp
0x18002bc1c  push    rbx
0x18002bc1d  push    rsi
0x18002bc1e  push    rdi
0x18002bc1f  push    r12
0x18002bc21  push    r13
0x18002bc23  push    r14
0x18002bc25  push    r15
0x18002bc27  lea     rbp, [rax-5Fh]
0x18002bc2b  sub     rsp, 88h
0x18002bc32  xor     r15d, r15d
0x18002bc35  lea     rax, [rbp+57h+hKey]
0x18002bc39  mov     r9d, 20019h; samDesired
0x18002bc3f  mov     [rbp+57h+cValues], r15d
0x18002bc43  xor     r8d, r8d; ulOptions
0x18002bc46  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18002bc4a  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ubp"...
0x18002bc51  mov     [rbp+57h+cchValueName], r15d
0x18002bc55  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bc5c  mov     [rbp+57h+cbMaxValueLen], r15d
0x18002bc60  mov     [rbp+57h+cbData], r15d
0x18002bc64  mov     [rbp+57h+Type], r15d
0x18002bc68  mov     [rbp+57h+hKey], r15
0x18002bc6c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002bc71  call    cs:__imp_RegOpenKeyExW
0x18002bc77  mov     ebx, eax
0x18002bc79  test    eax, eax
0x18002bc7b  jnz     loc_18002BE3E
0x18002bc81  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bc85  lea     rax, [rbp+57h+cbMaxValueLen]
0x18002bc89  mov     [rsp+58h], r15; lpftLastWriteTime
0x18002bc8e  xor     r9d, r9d; lpReserved
0x18002bc91  mov     [rsp+0C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002bc96  xor     r8d, r8d; lpcchClass
0x18002bc99  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002bc9e  xor     edx, edx; lpClass
0x18002bca0  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18002bca4  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002bca9  lea     rax, [rbp+57h+cValues]
0x18002bcad  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18002bcb2  mov     [rsp+0C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002bcb7  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18002bcbc  mov     [rsp+0C0h+phkResult], r15; lpcSubKeys
0x18002bcc1  call    cs:__imp_RegQueryInfoKeyW
0x18002bcc7  mov     ebx, eax
0x18002bcc9  test    eax, eax
0x18002bccb  jnz     loc_18002BE3E
0x18002bcd1  cmp     [rbp+57h+cValues], r15d
0x18002bcd5  jnz     short loc_18002BCDF
0x18002bcd7  mov     ebx, r15d
0x18002bcda  jmp     loc_18002BE3E
0x18002bcdf  mov     ecx, [rbp+57h+cbMaxValueNameLen]
0x18002bce2  add     [rbp+57h+cbMaxValueLen], 2
0x18002bce6  inc     ecx
0x18002bce8  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x18002bceb  add     ecx, ecx; Size
0x18002bced  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002bcf2  mov     r12, rax
0x18002bcf5  test    rax, rax
0x18002bcf8  jnz     short loc_18002BD02
0x18002bcfa  lea     ebx, [rax+0Eh]
0x18002bcfd  jmp     loc_18002BE3E
0x18002bd02  mov     ecx, [rbp+57h+cbMaxValueLen]; Size
0x18002bd05  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002bd0a  mov     rdi, rax
0x18002bd0d  test    rax, rax
0x18002bd10  jnz     short loc_18002BD1A
0x18002bd12  lea     ebx, [rax+0Eh]
0x18002bd15  jmp     loc_18002BE29
0x18002bd1a  xor     ebx, ebx
0x18002bd1c  mov     r13d, r15d
0x18002bd1f  mov     r14, r15
0x18002bd22  mov     [rbp+57h+var_4C], r13d
0x18002bd26  mov     esi, r15d
0x18002bd29  mov     [rbp+57h+var_50], r15d
0x18002bd2d  cmp     [rbp+57h+cValues], ebx
0x18002bd30  jbe     loc_18002BE1C
0x18002bd36  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18002bd39  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002bd3d  mov     rcx, [rbp+57h+hKey]; hKey
0x18002bd41  mov     r8, r12; lpValueName
0x18002bd44  mov     [rbp+57h+cchValueName], eax
0x18002bd47  mov     edx, r15d; dwIndex
0x18002bd4a  mov     eax, [rbp+57h+cbMaxValueLen]
0x18002bd4d  mov     [rbp+57h+cbData], eax
0x18002bd50  lea     rax, [rbp+57h+cbData]
0x18002bd54  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x18002bd59  lea     rax, [rbp+57h+Type]
0x18002bd5d  mov     [rsp+0C0h+lpcbMaxClassLen], rdi; lpData
0x18002bd62  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x18002bd67  mov     [rsp+0C0h+phkResult], rbx; lpReserved
0x18002bd6c  call    cs:__imp_RegEnumValueW
0x18002bd72  test    eax, eax
0x18002bd74  jnz     loc_18002BE0F
0x18002bd7a  cmp     [rbp+57h+Type], 1
0x18002bd7e  jnz     loc_18002BE0F
0x18002bd84  mov     eax, [rbp+57h+cbData]
0x18002bd87  mov     rcx, [rbp+57h+String2]
0x18002bd8b  shr     eax, 1
0x18002bd8d  dec     eax
0x18002bd8f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bd93  mov     [rdi+rax*2], bx
0x18002bd97  inc     r8; MaxCount
0x18002bd9a  cmp     [rcx+r8*2], bx
0x18002bd9f  jnz     short loc_18002BD97
0x18002bda1  mov     eax, [rbp+57h+cchValueName]
0x18002bda4  cmp     rax, r8
0x18002bda7  jb      short loc_18002BE0F
0x18002bda9  mov     ebx, [rbp+57h+cbData]
0x18002bdac  cmp     ebx, 2
0x18002bdaf  jbe     short loc_18002BE0D
0x18002bdb1  mov     rdx, rcx; String2
0x18002bdb4  mov     rcx, r12; String1
0x18002bdb7  call    wcsncmp_0
0x18002bdbc  test    eax, eax
0x18002bdbe  jnz     short loc_18002BE0D
0x18002bdc0  lea     edx, [rsi+rbx]
0x18002bdc3  mov     eax, edx
0x18002bdc5  add     rax, 2
0x18002bdc9  cmp     r13, rax
0x18002bdcc  jnb     short loc_18002BDF2
0x18002bdce  add     edx, 2; Size
0x18002bdd1  mov     rcx, r14; Ptr
0x18002bdd4  mov     rsi, r14
0x18002bdd7  call    ?UbpmReAlloc@@YAPEAXPEAXK@Z; UbpmReAlloc(void *,ulong)
0x18002bddc  mov     r14, rax
0x18002bddf  test    rax, rax
0x18002bde2  jz      short loc_18002BE63
0x18002bde4  mov     esi, [rbp+57h+var_50]
0x18002bde7  mov     ebx, [rbp+57h+cbData]
0x18002bdea  add     esi, 2
0x18002bded  add     esi, ebx
0x18002bdef  mov     [rbp+57h+var_50], esi
0x18002bdf2  mov     r8d, ebx; Size
0x18002bdf5  lea     rcx, [r14+r13]; void *
0x18002bdf9  mov     rdx, rdi; Src
0x18002bdfc  call    memcpy_0
0x18002be01  mov     r13d, [rbp+57h+var_4C]
0x18002be05  add     r13d, [rbp+57h+cbData]
0x18002be09  mov     [rbp+57h+var_4C], r13d
0x18002be0d  xor     ebx, ebx
0x18002be0f  inc     r15d
0x18002be12  cmp     r15d, [rbp+57h+cValues]
0x18002be16  jb      loc_18002BD36
0x18002be1c  mov     rax, [rbp+57h+arg_10]
0x18002be20  xor     r15d, r15d
0x18002be23  mov     ebx, r15d
0x18002be26  mov     [rax], r14
0x18002be29  mov     rcx, r12
0x18002be2c  call    UBPM_MIDL_user_free
0x18002be31  test    rdi, rdi
0x18002be34  jz      short loc_18002BE3E
0x18002be36  mov     rcx, rdi
0x18002be39  call    UBPM_MIDL_user_free
0x18002be3e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002be42  test    rcx, rcx
0x18002be45  jz      short loc_18002BE4D
0x18002be47  call    cs:__imp_RegCloseKey
0x18002be4d  mov     eax, ebx
0x18002be4f  add     rsp, 88h
0x18002be56  pop     r15
0x18002be58  pop     r14
0x18002be5a  pop     r13
0x18002be5c  pop     r12
0x18002be5e  pop     rdi
0x18002be5f  pop     rsi
0x18002be60  pop     rbx
0x18002be61  pop     rbp
0x18002be62  retn
0x18002be63  mov     ebx, 0Eh
0x18002be68  test    rsi, rsi
0x18002be6b  jz      short loc_18002BE29
0x18002be6d  mov     rcx, rsi
0x18002be70  call    UBPM_MIDL_user_free
0x18002be75  jmp     short loc_18002BE29
```
