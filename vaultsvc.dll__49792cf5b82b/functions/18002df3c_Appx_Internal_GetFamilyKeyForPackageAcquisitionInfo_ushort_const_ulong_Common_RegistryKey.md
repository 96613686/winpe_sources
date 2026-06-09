# Appx::Internal::GetFamilyKeyForPackageAcquisitionInfo(ushort const *,ulong,Common::RegistryKey *)

- ea: `0x18002df3c`
- end: `0x18002e0e3`
- name: `?GetFamilyKeyForPackageAcquisitionInfo@Internal@Appx@@YAJPEBGKPEAVRegistryKey@Common@@@Z`
- size: `423`
- prototype: `int(Appx::Internal *__hidden this, const unsigned __int16 *, unsigned int, struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dd0c`

## callees

- `0x18002df3c`
- `0x18002e0ec`
- `0x18002e110`
- `0x18003a580`
- `0x18003af10`
- `0x18003af28`
- `0x18004afcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002dfb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002dfb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e0a7`

## pseudocode

```c
__int64 __fastcall Appx::Internal::GetFamilyKeyForPackageAcquisitionInfo(
        Appx::Internal *this,
        const unsigned __int16 *a2,
        HKEY *a3,
        struct Common::RegistryKey *a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // r8d
  unsigned __int64 *v8; // r9
  unsigned int v9; // ebx
  int FamilyKeyPathForPackageAcquisitionInfo; // eax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  unsigned int v13; // r8d
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v20[4]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[524]; // [rsp+44h] [rbp-BCh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  phkResult = 0;
  *(_DWORD *)SubKey = 0;
  memset_0(v22, 0, 0x204u);
  *(_QWORD *)v20 = 260;
  if ( !this || !a3 )
  {
    v9 = -2147024809;
    goto LABEL_13;
  }
  v6 = RegOpenCurrentUser(0x20019u, &phkResult);
  v9 = v6;
  if ( v6 > 0 )
    v9 = (unsigned __int16)v6 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    v15 = v9;
    v16 = 252;
LABEL_19:
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)v16, v7, (const char *)v15, v17);
    goto LABEL_13;
  }
  FamilyKeyPathForPackageAcquisitionInfo = Appx::Internal::GetFamilyKeyPathForPackageAcquisitionInfo(
                                             this,
                                             SubKey,
                                             v20,
                                             v8);
  v9 = FamilyKeyPathForPackageAcquisitionInfo;
  if ( FamilyKeyPathForPackageAcquisitionInfo < 0 )
  {
    v15 = (unsigned int)FamilyKeyPathForPackageAcquisitionInfo;
    v16 = 253;
    goto LABEL_19;
  }
  if ( (unsigned __int64)*a3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(*a3);
  v11 = phkResult;
  *a3 = 0;
  v12 = RegOpenKeyExW_0(v11, SubKey, 0, 0x20019u, a3);
  v9 = v12;
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  if ( v9 == -2147024894 )
  {
    v9 = -2147024894;
    goto LABEL_13;
  }
  if ( (v9 & 0x80000000) == 0 )
  {
LABEL_13:
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
    return v9;
  }
  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x103, v13, (const char *)v9, v18);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x18002df3c  mov     [rsp-8+arg_8], rbx
0x18002df41  push    rbp
0x18002df42  push    rsi
0x18002df43  push    rdi
0x18002df44  lea     rbp, [rsp-160h]
0x18002df4c  sub     rsp, 260h
0x18002df53  mov     rax, cs:__security_cookie
0x18002df5a  xor     rax, rsp
0x18002df5d  mov     [rbp+170h+var_20], rax
0x18002df64  mov     rdi, r8
0x18002df67  mov     [rsp+270h+phkResult], 0
0x18002df70  mov     rsi, rcx
0x18002df73  mov     dword ptr [rsp+270h+SubKey], 0
0x18002df7b  mov     r8d, 204h; Size
0x18002df81  lea     rcx, [rsp+270h+var_22C]; void *
0x18002df86  xor     edx, edx; Val
0x18002df88  call    memset_0
0x18002df8d  mov     qword ptr [rsp+270h+var_238], 104h
0x18002df96  test    rsi, rsi
0x18002df99  jz      loc_18002E0D9
0x18002df9f  test    rdi, rdi
0x18002dfa2  jz      loc_18002E0D9
0x18002dfa8  lea     rdx, [rsp+270h+phkResult]; phkResult
0x18002dfad  mov     ecx, 20019h; samDesired
0x18002dfb2  call    cs:__imp_RegOpenCurrentUser
0x18002dfb8  mov     ebx, eax
0x18002dfba  test    eax, eax
0x18002dfbc  jg      loc_18002E060
0x18002dfc2  test    ebx, ebx
0x18002dfc4  js      loc_18002E0AF
0x18002dfca  lea     r8, [rsp+270h+var_238]; unsigned __int16 *
0x18002dfcf  mov     rcx, rsi; this
0x18002dfd2  lea     rdx, [rsp+270h+SubKey]; unsigned __int16 *
0x18002dfd7  call    ?GetFamilyKeyPathForPackageAcquisitionInfo@Internal@Appx@@YAJPEBGPEAGPEA_K@Z; Appx::Internal::GetFamilyKeyPathForPackageAcquisitionInfo(ushort const *,ushort *,unsigned __int64 *)
0x18002dfdc  mov     ebx, eax
0x18002dfde  test    eax, eax
0x18002dfe0  js      loc_18002E0B9
0x18002dfe6  mov     rcx, [rdi]; hKey
0x18002dfe9  lea     rax, [rcx-1]
0x18002dfed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002dff1  jbe     loc_18002E079
0x18002dff7  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002dffc  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18002e001  mov     r9d, 20019h; samDesired
0x18002e007  mov     qword ptr [rdi], 0
0x18002e00e  xor     r8d, r8d; ulOptions
0x18002e011  mov     qword ptr [rsp+270h+var_250], rdi; int
0x18002e016  call    RegOpenKeyExW_0
0x18002e01b  mov     ebx, eax
0x18002e01d  test    eax, eax
0x18002e01f  jg      short loc_18002E06E
0x18002e021  mov     eax, 80070002h
0x18002e026  cmp     ebx, eax
0x18002e028  jz      loc_18002E0D2
0x18002e02e  test    ebx, ebx
0x18002e030  js      short loc_18002E084
0x18002e032  lea     rcx, [rsp+270h+phkResult]; this
0x18002e037  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18002e03c  mov     eax, ebx
0x18002e03e  mov     rcx, [rbp+170h+var_20]
0x18002e045  xor     rcx, rsp; StackCookie
0x18002e048  call    __security_check_cookie
0x18002e04d  mov     rbx, [rsp+270h+arg_8]
0x18002e055  add     rsp, 260h
0x18002e05c  pop     rdi
0x18002e05d  pop     rsi
0x18002e05e  pop     rbp
0x18002e05f  retn
0x18002e060  movzx   ebx, ax
0x18002e063  or      ebx, 80070000h
0x18002e069  jmp     loc_18002DFC2
0x18002e06e  movzx   ebx, ax
0x18002e071  or      ebx, 80070000h
0x18002e077  jmp     short loc_18002E021
0x18002e079  call    cs:__imp_RegCloseKey
0x18002e07f  jmp     loc_18002DFF7
0x18002e084  mov     rcx, [rbp+178h]; this
0x18002e08b  mov     r9d, ebx; char *
0x18002e08e  mov     edx, 103h; void *
0x18002e093  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e098  mov     rcx, [rsp+270h+phkResult]; hKey
0x18002e09d  lea     rdx, [rcx-1]
0x18002e0a1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002e0a5  ja      short loc_18002E03C
0x18002e0a7  call    cs:__imp_RegCloseKey
0x18002e0ad  jmp     short loc_18002E03C
0x18002e0af  mov     r9d, ebx
0x18002e0b2  mov     edx, 0FCh
0x18002e0b7  jmp     short loc_18002E0C1
0x18002e0b9  mov     r9d, eax; char *
0x18002e0bc  mov     edx, 0FDh; void *
0x18002e0c1  mov     rcx, [rbp+178h]; this
0x18002e0c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002e0cd  jmp     loc_18002E032
0x18002e0d2  mov     ebx, eax
0x18002e0d4  jmp     loc_18002E032
0x18002e0d9  mov     ebx, 80070057h
0x18002e0de  jmp     loc_18002E032
```
