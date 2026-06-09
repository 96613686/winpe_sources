# UmpoInternalWriteToUserPowerKeyEx

- ea: `0x18000b9b8`
- end: `0x18000bdce`
- name: `UmpoInternalWriteToUserPowerKeyEx`
- size: `1046`
- prototype: `__int64 __fastcall(UUID *, UUID *Uuid1, UUID *Uuid2, unsigned int, DWORD dwType, BYTE *, DWORD cbData)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000b7b0`

## callees

- `0x180003370`
- `0x180003560`
- `0x180005480`
- `0x1800058c4`
- `0x18000681c`
- `0x180007f70`
- `0x18000ab60`
- `0x18000b9b8`
- `0x18000cb4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bcbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdb2`
- `RPCRT4!UuidEqual` at `0x18000bac1`
- `RPCRT4!UuidEqual` at `0x18000bb4f`
- `RPCRT4!UuidEqual` at `0x18000bac1`
- `RPCRT4!UuidEqual` at `0x18000bb4f`

## pseudocode

```c
__int64 __fastcall UmpoInternalWriteToUserPowerKeyEx(
        UUID *a1,
        UUID *Uuid1,
        UUID *Uuid2,
        unsigned int a4,
        DWORD dwType,
        BYTE *a6,
        DWORD cbData)
{
  DWORD v11; // r15d
  unsigned int v13; // ebx
  HKEY v14; // rcx
  HKEY v15; // r15
  HKEY v16; // rbx
  const BYTE *lpData; // r12
  unsigned int v18; // ebx
  int v19; // eax
  const WCHAR *v20; // rax
  LSTATUS v21; // eax
  HKEY v22; // rbx
  const WCHAR *v23; // rdx
  HKEY hKey; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v25; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v26; // [rsp+6Ch] [rbp-35h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-31h] BYREF
  HKEY v28; // [rsp+78h] [rbp-29h] BYREF
  DWORD v29; // [rsp+80h] [rbp-21h] BYREF
  HKEY v30; // [rsp+88h] [rbp-19h] BYREF
  HKEY v31; // [rsp+90h] [rbp-11h] BYREF
  HKEY v32; // [rsp+98h] [rbp-9h] BYREF
  RPC_STATUS Status; // [rsp+108h] [rbp+67h] BYREF

  v29 = 4;
  v28 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v26 = 0;
  v25 = 0;
  Status = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v31 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( a4 > 1 )
  {
    v11 = cbData;
  }
  else
  {
    if ( !a1 )
      return 87;
    if ( !Uuid2 )
      return 87;
    v11 = cbData;
    if ( cbData != 4 )
      return 87;
  }
  v13 = UmpoInternalOpenUserPowerKey(&v31, 131097, 1);
  if ( v13 )
    goto LABEL_48;
  v14 = v31;
  if ( a4 - 2 <= 1 || a4 == 13 )
  {
    if ( a1 )
    {
      if ( !Uuid2 && !Uuid1 )
      {
        v13 = UmpoInternalOpenGUIDSubKey(v31, a1, &hKey, 0x20006u, 1, 0);
        if ( v13 )
          goto LABEL_48;
        v22 = hKey;
        v23 = (const WCHAR *)UmpoInternalDataAccessorToString(a4);
        if ( !v23 )
          goto LABEL_42;
        v21 = RegSetValueExW(v22, v23, 0, dwType, a6, v11);
LABEL_47:
        v13 = v21;
        goto LABEL_48;
      }
    }
    else if ( !Uuid2 && !Uuid1 )
    {
      goto LABEL_42;
    }
    v21 = UmpoWriteToSystemPowerKey(0, Uuid1, 0, Uuid2, a4, dwType, 0, a6, v11);
    goto LABEL_47;
  }
  if ( a4 > 1 )
    goto LABEL_42;
  if ( UmpoStateSeparationEnabled )
    v14 = UmpoUserPowerStateSepRootKey;
  v13 = UmpoInternalOpenGUIDSubKey(v14, a1, &hKey, 0x20006u, 1, 0);
  if ( v13 )
    goto LABEL_48;
  v15 = hKey;
  if ( Uuid1 && !UuidEqual(Uuid1, (UUID *)&NO_SUBGROUP_GUID, &Status) )
  {
    v13 = UmpoInternalOpenGUIDSubKey(v15, Uuid1, &phkResult, 0x20006u, 0, 0);
    if ( v13 )
      goto LABEL_48;
    v15 = phkResult;
  }
  if ( !Uuid2 )
  {
LABEL_27:
    lpData = a6;
    v18 = *(_DWORD *)a6;
    v19 = UmpoReadFromSystemPowerKey((__int64)a1, Uuid1, 0, 4, 0, *(_DWORD *)a6, 0, &v29, 0);
    if ( v19 != 234 && v19 )
    {
      v13 = 13;
      goto LABEL_48;
    }
    if ( !(unsigned int)UmpoInternalReadValueRange(Uuid1, (__int64)Uuid2, &v25, &v26) && (v18 < v25 || v18 > v26) )
    {
      v13 = 5;
      goto LABEL_48;
    }
    v20 = (const WCHAR *)UmpoInternalDataAccessorToString(a4);
    if ( v20 )
    {
      v21 = RegSetValueExW(v15, v20, 0, dwType, lpData, cbData);
      goto LABEL_47;
    }
LABEL_42:
    v13 = 87;
    goto LABEL_48;
  }
  if ( !(unsigned int)UmpoInternalOpenGUIDSubKey(v15, Uuid2, &v28, 0x20006u, 1, 0) )
  {
LABEL_26:
    v15 = v28;
    goto LABEL_27;
  }
  v16 = UmpoSystemPowerRootKey;
  v32 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v30 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( !Uuid1 || UuidEqual(Uuid1, (UUID *)&NO_SUBGROUP_GUID, &Status) )
  {
LABEL_24:
    v13 = UmpoInternalOpenGUIDSubKey(v16, Uuid2, &v32, 0x20019u, 1, (int *)&UmpoPowerSettingCache);
    UmpoInternalRegCloseKey((__int64)&UmpoPowerSubGroupCache, v30);
    UmpoInternalRegCloseKey((__int64)&UmpoPowerSettingCache, v32);
    if ( v13 )
      goto LABEL_48;
    v13 = UmpoInternalOpenGUIDSubKey(v15, Uuid2, &v28, 0x20006u, 0, 0);
    if ( v13 )
      goto LABEL_48;
    goto LABEL_26;
  }
  v13 = UmpoInternalOpenGUIDSubKey(v16, Uuid1, &v30, 0x20019u, 1, (int *)&UmpoPowerSubGroupCache);
  if ( !v13 )
  {
    v16 = v30;
    goto LABEL_24;
  }
LABEL_48:
  UmpoInternalCloseUserPowerKey(v31);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( (unsigned __int64)v28 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v28);
  return v13;
}

```

## disassembly

```asm
0x18000b9b8  push    rbp
0x18000b9ba  push    rbx
0x18000b9bb  push    rsi
0x18000b9bc  push    rdi
0x18000b9bd  push    r12
0x18000b9bf  push    r13
0x18000b9c1  push    r14
0x18000b9c3  push    r15
0x18000b9c5  lea     rbp, [rsp-7]
0x18000b9ca  sub     rsp, 0A8h
0x18000b9d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b9d5  mov     [rbp+3Fh+var_60], 4
0x18000b9dc  xor     r12d, r12d
0x18000b9df  mov     [rbp+3Fh+var_68], rax
0x18000b9e3  mov     [rbp+3Fh+var_74], r12d
0x18000b9e7  mov     r14d, r9d
0x18000b9ea  mov     [rbp+3Fh+var_78], r12d
0x18000b9ee  mov     rsi, r8
0x18000b9f1  mov     [rbp+3Fh+Status], r12d
0x18000b9f5  mov     rdi, rdx
0x18000b9f8  mov     [rbp+3Fh+hKey], rax
0x18000b9fc  mov     r13, rcx
0x18000b9ff  mov     [rbp+3Fh+phkResult], rax
0x18000ba03  mov     [rbp+3Fh+var_50], rax
0x18000ba07  cmp     r9d, 1
0x18000ba0b  ja      short loc_18000BA2B
0x18000ba0d  test    rcx, rcx
0x18000ba10  jz      short loc_18000BA21
0x18000ba12  test    r8, r8
0x18000ba15  jz      short loc_18000BA21
0x18000ba17  mov     r15d, [rbp+3Fh+arg_30]
0x18000ba1b  cmp     r15d, 4
0x18000ba1f  jz      short loc_18000BA2F
0x18000ba21  mov     eax, 57h ; 'W'
0x18000ba26  jmp     loc_18000BDBA
0x18000ba2b  mov     r15d, [rbp+3Fh+arg_30]
0x18000ba2f  mov     edx, 20019h; samDesired
0x18000ba34  lea     rcx, [rbp+3Fh+var_50]; phkResult
0x18000ba38  mov     r8d, 1
0x18000ba3e  call    UmpoInternalOpenUserPowerKey
0x18000ba43  mov     ebx, eax
0x18000ba45  test    eax, eax
0x18000ba47  jnz     loc_18000BD63
0x18000ba4d  mov     rcx, [rbp+3Fh+var_50]; hKey
0x18000ba51  lea     eax, [r14-2]
0x18000ba55  cmp     eax, 1
0x18000ba58  jbe     loc_18000BCC9
0x18000ba5e  cmp     r14d, 0Dh
0x18000ba62  jz      loc_18000BCC9
0x18000ba68  cmp     r14d, 1
0x18000ba6c  ja      loc_18000BD0E
0x18000ba72  cmp     cs:UmpoStateSeparationEnabled, r12b
0x18000ba79  lea     r8, [rbp+3Fh+hKey]; phkResult
0x18000ba7d  mov     qword ptr [rsp+0E0h+cbData], r12; __int64
0x18000ba82  mov     rdx, r13; Uuid2
0x18000ba85  cmovnz  rcx, cs:UmpoUserPowerStateSepRootKey; hKey
0x18000ba8d  mov     r12d, 20006h
0x18000ba93  mov     r9d, r12d; samDesired
0x18000ba96  mov     byte ptr [rsp+0E0h+lpData], 1; char
0x18000ba9b  call    UmpoInternalOpenGUIDSubKey
0x18000baa0  mov     ebx, eax
0x18000baa2  test    eax, eax
0x18000baa4  jnz     loc_18000BD63
0x18000baaa  mov     r15, [rbp+3Fh+hKey]
0x18000baae  test    rdi, rdi
0x18000bab1  jz      short loc_18000BAF8
0x18000bab3  lea     r8, [rbp+3Fh+Status]; Status
0x18000bab7  mov     rcx, rdi; Uuid1
0x18000baba  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x18000bac1  call    cs:__imp_UuidEqual
0x18000bac7  test    eax, eax
0x18000bac9  jnz     short loc_18000BAF8
0x18000bacb  mov     qword ptr [rsp+0E0h+cbData], 0; __int64
0x18000bad4  lea     r8, [rbp+3Fh+phkResult]; phkResult
0x18000bad8  mov     r9d, r12d; samDesired
0x18000badb  mov     byte ptr [rsp+0E0h+lpData], al; char
0x18000badf  mov     rdx, rdi; Uuid2
0x18000bae2  mov     rcx, r15; hKey
0x18000bae5  call    UmpoInternalOpenGUIDSubKey
0x18000baea  mov     ebx, eax
0x18000baec  test    eax, eax
0x18000baee  jnz     loc_18000BD63
0x18000baf4  mov     r15, [rbp+3Fh+phkResult]
0x18000baf8  test    rsi, rsi
0x18000bafb  jz      loc_18000BC0A
0x18000bb01  mov     qword ptr [rsp+0E0h+cbData], 0; __int64
0x18000bb0a  lea     r8, [rbp+3Fh+var_68]; phkResult
0x18000bb0e  mov     r9d, r12d; samDesired
0x18000bb11  mov     byte ptr [rsp+0E0h+lpData], 1; char
0x18000bb16  mov     rdx, rsi; Uuid2
0x18000bb19  mov     rcx, r15; hKey
0x18000bb1c  call    UmpoInternalOpenGUIDSubKey
0x18000bb21  test    eax, eax
0x18000bb23  jz      loc_18000BC06
0x18000bb29  mov     rbx, cs:UmpoSystemPowerRootKey
0x18000bb30  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb34  mov     [rbp+3Fh+var_48], rax
0x18000bb38  mov     [rbp+3Fh+var_58], rax
0x18000bb3c  test    rdi, rdi
0x18000bb3f  jz      short loc_18000BB8D
0x18000bb41  lea     r8, [rbp+3Fh+Status]; Status
0x18000bb45  mov     rcx, rdi; Uuid1
0x18000bb48  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x18000bb4f  call    cs:__imp_UuidEqual
0x18000bb55  test    eax, eax
0x18000bb57  jnz     short loc_18000BB8D
0x18000bb59  lea     rax, UmpoPowerSubGroupCache
0x18000bb60  mov     r9d, 20019h; samDesired
0x18000bb66  mov     qword ptr [rsp+0E0h+cbData], rax; __int64
0x18000bb6b  lea     r8, [rbp+3Fh+var_58]; phkResult
0x18000bb6f  mov     rdx, rdi; Uuid2
0x18000bb72  mov     byte ptr [rsp+0E0h+lpData], 1; char
0x18000bb77  mov     rcx, rbx; hKey
0x18000bb7a  call    UmpoInternalOpenGUIDSubKey
0x18000bb7f  mov     ebx, eax
0x18000bb81  test    eax, eax
0x18000bb83  jnz     loc_18000BD63
0x18000bb89  mov     rbx, [rbp+3Fh+var_58]
0x18000bb8d  lea     rax, UmpoPowerSettingCache
0x18000bb94  mov     r9d, 20019h; samDesired
0x18000bb9a  mov     qword ptr [rsp+0E0h+cbData], rax; __int64
0x18000bb9f  lea     r8, [rbp+3Fh+var_48]; phkResult
0x18000bba3  mov     rdx, rsi; Uuid2
0x18000bba6  mov     byte ptr [rsp+0E0h+lpData], 1; char
0x18000bbab  mov     rcx, rbx; hKey
0x18000bbae  call    UmpoInternalOpenGUIDSubKey
0x18000bbb3  mov     rdx, [rbp+3Fh+var_58]
0x18000bbb7  lea     rcx, UmpoPowerSubGroupCache
0x18000bbbe  mov     ebx, eax
0x18000bbc0  call    UmpoInternalRegCloseKey
0x18000bbc5  mov     rdx, [rbp+3Fh+var_48]
0x18000bbc9  lea     rcx, UmpoPowerSettingCache
0x18000bbd0  call    UmpoInternalRegCloseKey
0x18000bbd5  test    ebx, ebx
0x18000bbd7  jnz     loc_18000BD63
0x18000bbdd  mov     qword ptr [rsp+0E0h+cbData], 0; __int64
0x18000bbe6  lea     r8, [rbp+3Fh+var_68]; phkResult
0x18000bbea  mov     r9d, r12d; samDesired
0x18000bbed  mov     byte ptr [rsp+0E0h+lpData], bl; char
0x18000bbf1  mov     rdx, rsi; Uuid2
0x18000bbf4  mov     rcx, r15; hKey
0x18000bbf7  call    UmpoInternalOpenGUIDSubKey
0x18000bbfc  mov     ebx, eax
0x18000bbfe  test    eax, eax
0x18000bc00  jnz     loc_18000BD63
0x18000bc06  mov     r15, [rbp+3Fh+var_68]
0x18000bc0a  mov     r12, [rbp+3Fh+arg_28]
0x18000bc0e  lea     rax, [rbp+3Fh+var_60]
0x18000bc12  mov     [rsp+0E0h+var_90], 0; __int64
0x18000bc1b  mov     r9, rsi
0x18000bc1e  mov     [rsp+0E0h+var_98], rax; LPDWORD
0x18000bc23  xor     r8d, r8d
0x18000bc26  mov     [rsp+0E0h+var_A0], 0; __int64
0x18000bc2f  mov     rdx, rdi; Uuid1
0x18000bc32  mov     ebx, [r12]
0x18000bc36  mov     rcx, r13; __int64
0x18000bc39  mov     [rsp+0E0h+var_A8], ebx; int
0x18000bc3d  mov     [rsp+0E0h+var_B0], 0; __int64
0x18000bc46  mov     [rsp+0E0h+cbData], 4; int
0x18000bc4e  mov     byte ptr [rsp+0E0h+lpData], 0; char
0x18000bc53  call    UmpoReadFromSystemPowerKey
0x18000bc58  cmp     eax, 0EAh
0x18000bc5d  jz      short loc_18000BC6D
0x18000bc5f  test    eax, eax
0x18000bc61  jz      short loc_18000BC6D
0x18000bc63  mov     ebx, 0Dh
0x18000bc68  jmp     loc_18000BD63
0x18000bc6d  lea     r9, [rbp+3Fh+var_74]
0x18000bc71  mov     rdx, rsi
0x18000bc74  lea     r8, [rbp+3Fh+var_78]
0x18000bc78  mov     rcx, rdi
0x18000bc7b  call    UmpoInternalReadValueRange
0x18000bc80  test    eax, eax
0x18000bc82  jnz     short loc_18000BC98
0x18000bc84  cmp     ebx, [rbp+3Fh+var_78]
0x18000bc87  jb      short loc_18000BC8E
0x18000bc89  cmp     ebx, [rbp+3Fh+var_74]
0x18000bc8c  jbe     short loc_18000BC98
0x18000bc8e  mov     ebx, 5
0x18000bc93  jmp     loc_18000BD63
0x18000bc98  mov     ecx, r14d
0x18000bc9b  call    UmpoInternalDataAccessorToString
0x18000bca0  test    rax, rax
0x18000bca3  jz      short loc_18000BD0E
0x18000bca5  mov     ecx, [rbp+3Fh+arg_30]
0x18000bca8  mov     rdx, rax; lpValueName
0x18000bcab  mov     [rsp+0E0h+cbData], ecx; cbData
0x18000bcaf  mov     rcx, r15; hKey
0x18000bcb2  mov     [rsp+0E0h+lpData], r12; lpData
0x18000bcb7  mov     r9d, [rbp+3Fh+dwType]; dwType
0x18000bcbb  xor     r8d, r8d; Reserved
0x18000bcbe  call    cs:__imp_RegSetValueExW
0x18000bcc4  jmp     loc_18000BD61
0x18000bcc9  test    r13, r13
0x18000bccc  jz      short loc_18000BD28
0x18000bcce  test    rsi, rsi
0x18000bcd1  jnz     short loc_18000BD32
0x18000bcd3  test    rdi, rdi
0x18000bcd6  jnz     short loc_18000BD32
0x18000bcd8  mov     qword ptr [rsp+0E0h+cbData], r12; __int64
0x18000bcdd  lea     r8, [rbp+3Fh+hKey]; phkResult
0x18000bce1  mov     r9d, 20006h; samDesired
0x18000bce7  mov     byte ptr [rsp+0E0h+lpData], 1; char
0x18000bcec  mov     rdx, r13; Uuid2
0x18000bcef  call    UmpoInternalOpenGUIDSubKey
0x18000bcf4  mov     ebx, eax
0x18000bcf6  test    eax, eax
0x18000bcf8  jnz     short loc_18000BD63
0x18000bcfa  mov     rbx, [rbp+3Fh+hKey]
0x18000bcfe  mov     ecx, r14d
0x18000bd01  call    UmpoInternalDataAccessorToString
0x18000bd06  mov     rdx, rax
0x18000bd09  test    rax, rax
0x18000bd0c  jnz     short loc_18000BD15
0x18000bd0e  mov     ebx, 57h ; 'W'
0x18000bd13  jmp     short loc_18000BD63
0x18000bd15  mov     rax, [rbp+3Fh+arg_28]
0x18000bd19  mov     rcx, rbx
0x18000bd1c  mov     [rsp+0E0h+cbData], r15d
0x18000bd21  mov     [rsp+0E0h+lpData], rax
0x18000bd26  jmp     short loc_18000BCB7
0x18000bd28  test    rsi, rsi
0x18000bd2b  jnz     short loc_18000BD32
0x18000bd2d  test    rdi, rdi
0x18000bd30  jz      short loc_18000BD0E
0x18000bd32  mov     rax, [rbp+3Fh+arg_28]
0x18000bd36  mov     r9, rsi
0x18000bd39  mov     dword ptr [rsp+0E0h+var_A0], r15d
0x18000bd3e  xor     r8d, r8d
0x18000bd41  mov     qword ptr [rsp+0E0h+var_A8], rax
0x18000bd46  mov     rdx, rdi
0x18000bd49  mov     eax, [rbp+3Fh+dwType]
0x18000bd4c  xor     ecx, ecx
0x18000bd4e  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x18000bd53  mov     [rsp+0E0h+cbData], eax
0x18000bd57  mov     dword ptr [rsp+0E0h+lpData], r14d
0x18000bd5c  call    UmpoWriteToSystemPowerKey
0x18000bd61  mov     ebx, eax
0x18000bd63  mov     rcx, [rbp+3Fh+var_50]
0x18000bd67  call    UmpoInternalCloseUserPowerKey
0x18000bd6c  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18000bd70  lea     rax, [rcx-1]
0x18000bd74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bd78  ja      short loc_18000BD88
0x18000bd7a  call    cs:__imp_RegCloseKey
0x18000bd80  mov     [rbp+3Fh+hKey], 0FFFFFFFFFFFFFFFFh
0x18000bd88  mov     rcx, [rbp+3Fh+phkResult]; hKey
0x18000bd8c  lea     rax, [rcx-1]
0x18000bd90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bd94  ja      short loc_18000BDA4
0x18000bd96  call    cs:__imp_RegCloseKey
0x18000bd9c  mov     [rbp+3Fh+phkResult], 0FFFFFFFFFFFFFFFFh
0x18000bda4  mov     rcx, [rbp+3Fh+var_68]; hKey
0x18000bda8  lea     rax, [rcx-1]
0x18000bdac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bdb0  ja      short loc_18000BDB8
0x18000bdb2  call    cs:__imp_RegCloseKey
0x18000bdb8  mov     eax, ebx
0x18000bdba  add     rsp, 0A8h
0x18000bdc1  pop     r15
0x18000bdc3  pop     r14
0x18000bdc5  pop     r13
0x18000bdc7  pop     r12
0x18000bdc9  pop     rdi
0x18000bdca  pop     rsi
0x18000bdcb  pop     rbx
0x18000bdcc  pop     rbp
0x18000bdcd  retn
```
