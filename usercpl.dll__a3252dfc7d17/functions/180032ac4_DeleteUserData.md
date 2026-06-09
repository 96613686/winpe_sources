# _DeleteUserData

- ea: `0x180032ac4`
- end: `0x180032c5b`
- name: `_DeleteUserData`
- size: `407`
- prototype: `int __fastcall(__int64, __int64, const unsigned __int16 *, _WORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800343b0`

## callees

- `0x180006df4`
- `0x18002fc14`
- `0x1800307cc`
- `0x180032918`
- `0x180032ac4`
- `0x18007728a`
- `0x1800772c0`

## import_xrefs

- `SHELL32!__imp_SHSetUserPicturePath` at `0x180032b01`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x180032b01`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032bc8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180032bc8`
- `USERENV!DeleteProfileW` at `0x180032c36`
- `USERENV!DeleteProfileW` at `0x180032c36`

## string_xrefs

- `0x180032bb7`: `ProfileImagePath`

## pseudocode

```c
int __fastcall DeleteUserData(__int64 a1, __int64 a2, const unsigned __int16 *a3, _WORD *a4)
{
  int result; // eax
  bool v9; // sf
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[58]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[412]; // [rsp+C4h] [rbp-3Ch] BYREF
  WCHAR pObjectName[264]; // [rsp+260h] [rbp+160h] BYREF

  SHSetUserPicturePath(a2, 0, 0);
  wcscpy(SubKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\");
  memset_0(v12, 0, 0x194u);
  result = StringCchCatW(SubKey, 0x104u, a3);
  if ( result >= 0 )
  {
    pcbData[0] = 520;
    result = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ProfileImagePath", 2u, 0, pObjectName, pcbData);
    v9 = result < 0;
    if ( result )
    {
      pObjectName[0] = 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v9 = result < 0;
      }
    }
    if ( !v9 )
    {
      EnsureAdminFileAccess(pObjectName);
      if ( a4 && *a4 )
      {
        result = BuildBackupUserDataPath(a1, a2, a4, SubKey);
        if ( result >= 0 )
          BackupUserData(a3, pObjectName, SubKey);
      }
      else
      {
        return DeleteProfileW(a3, 0, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180032ac4  push    rbp
0x180032ac6  push    rbx
0x180032ac7  push    rsi
0x180032ac8  push    rdi
0x180032ac9  push    r14
0x180032acb  push    r15
0x180032acd  lea     rbp, [rsp-388h]
0x180032ad5  sub     rsp, 488h
0x180032adc  mov     rax, cs:__security_cookie
0x180032ae3  xor     rax, rsp
0x180032ae6  mov     [rbp+3B0h+var_40], rax
0x180032aed  mov     rsi, rdx
0x180032af0  mov     rdi, r8
0x180032af3  mov     r14, rcx
0x180032af6  xor     r8d, r8d
0x180032af9  mov     rcx, rsi
0x180032afc  xor     edx, edx
0x180032afe  mov     rbx, r9
0x180032b01  call    cs:__imp_SHSetUserPicturePath
0x180032b07  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x180032b0e  lea     rcx, [rbp+3B0h+var_3EC]; void *
0x180032b12  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x180032b19  xor     edx, edx; Val
0x180032b1b  mov     eax, dword ptr cs:aSoftwareMicros_4+70h; "\\"
0x180032b21  mov     r8d, 194h; Size
0x180032b27  movaps  xmmword ptr [rsp+4B0h+SubKey], xmm0
0x180032b2c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+20h; "ft\\Windows NT\\CurrentVersion\\Profile"...
0x180032b33  movaps  [rsp+4B0h+var_440], xmm0
0x180032b38  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+40h; "rrentVersion\\ProfileList\\"
0x180032b3f  movaps  [rsp+4B0h+var_450], xmm1
0x180032b44  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+30h; "ws NT\\CurrentVersion\\ProfileList\\"
0x180032b4b  movaps  [rbp+3B0h+var_420], xmm0
0x180032b4f  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_4+60h; "fileList\\"
0x180032b56  movaps  [rbp+3B0h+var_430], xmm1
0x180032b5a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_4+50h; "sion\\ProfileList\\"
0x180032b61  movaps  [rbp+3B0h+var_400], xmm0
0x180032b65  movaps  [rbp+3B0h+var_410], xmm1
0x180032b69  mov     [rbp+3B0h+var_3F0], eax
0x180032b6c  call    memset_0
0x180032b71  mov     r8, rdi; unsigned __int16 *
0x180032b74  lea     rcx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180032b79  mov     edx, 104h; unsigned __int64
0x180032b7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032b83  xor     r15d, r15d
0x180032b86  test    eax, eax
0x180032b88  js      loc_180032C3C
0x180032b8e  lea     rax, [rsp+4B0h+var_470]
0x180032b93  mov     [rsp+4B0h+var_470], 208h
0x180032b9b  mov     [rsp+4B0h+pcbData], rax; pcbData
0x180032ba0  lea     r9d, [r15+2]; dwFlags
0x180032ba4  lea     rax, [rbp+3B0h+pObjectName]
0x180032bab  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180032bb2  mov     [rsp+4B0h+pvData], rax; pvData
0x180032bb7  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180032bbe  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x180032bc3  mov     [rsp+4B0h+pdwType], r15; pdwType
0x180032bc8  call    cs:__imp_RegGetValueW
0x180032bce  test    eax, eax
0x180032bd0  jz      short loc_180032BE6
0x180032bd2  mov     [rbp+3B0h+pObjectName], r15w
0x180032bda  jle     short loc_180032BE6
0x180032bdc  movzx   eax, ax
0x180032bdf  or      eax, 80070000h
0x180032be4  test    eax, eax
0x180032be6  js      short loc_180032C3C
0x180032be8  lea     rcx, [rbp+3B0h+pObjectName]; pObjectName
0x180032bef  call    ?EnsureAdminFileAccess@@YAKPEAG@Z; EnsureAdminFileAccess(ushort *)
0x180032bf4  test    rbx, rbx
0x180032bf7  jz      short loc_180032C2E
0x180032bf9  cmp     [rbx], r15w
0x180032bfd  jz      short loc_180032C2E
0x180032bff  lea     r9, [rsp+4B0h+SubKey]
0x180032c04  mov     r8, rbx
0x180032c07  mov     rdx, rsi
0x180032c0a  mov     rcx, r14
0x180032c0d  call    _BuildBackupUserDataPath
0x180032c12  test    eax, eax
0x180032c14  js      short loc_180032C3C
0x180032c16  lea     r8, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180032c1b  mov     rcx, rdi; lpSubKey
0x180032c1e  lea     rdx, [rbp+3B0h+pObjectName]; lpString1
0x180032c25  call    ?BackupUserData@@YAJPEBGPEAG0@Z; AFR coverage: BackupUserData copies selected user's shell folders during admin-gated delete-user backup; source from HKLM ProfileList/loaded ntuser.dat, not low-priv arbitrary file.
0x180032c2a  test    eax, eax
0x180032c2c  js      short loc_180032C3C
0x180032c2e  xor     r8d, r8d; lpComputerName
0x180032c31  xor     edx, edx; lpProfilePath
0x180032c33  mov     rcx, rdi; lpSidString
0x180032c36  call    cs:__imp_DeleteProfileW
0x180032c3c  mov     rcx, [rbp+3B0h+var_40]
0x180032c43  xor     rcx, rsp; StackCookie
0x180032c46  call    __security_check_cookie
0x180032c4b  add     rsp, 488h
0x180032c52  pop     r15
0x180032c54  pop     r14
0x180032c56  pop     rdi
0x180032c57  pop     rsi
0x180032c58  pop     rbx
0x180032c59  pop     rbp
0x180032c5a  retn
```
