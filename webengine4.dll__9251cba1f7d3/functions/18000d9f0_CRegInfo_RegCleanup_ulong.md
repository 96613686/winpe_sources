# CRegInfo::RegCleanup(ulong)

- ea: `0x18000d9f0`
- end: `0x18000dbde`
- name: `?RegCleanup@CRegInfo@@SAJK@Z`
- size: `494`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b2c8`
- `0x18003ef38`

## callees

- `0x18000d43c`
- `0x18000d9f0`
- `0x18000dbe0`
- `0x18000dd04`
- `0x18003aba8`
- `0x18004a28c`
- `0x18004a2dc`
- `0x18004d030`
- `0x18004d754`
- `0x18004e638`
- `0x18004f048`
- `0x18004f1c4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000db97`
- `ADVAPI32!RegCloseKey` at `0x18000db97`
- `ADVAPI32!RegEnumKeyExW` at `0x18000db24`
- `ADVAPI32!RegEnumKeyExW` at `0x18000db24`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da73`
- `ADVAPI32!RegOpenKeyExW` at `0x18000da73`

## string_xrefs

- `0x18000da2e`: `Cleaning up registry`
- `0x18000db75`: `Cleaning up registry`
- `0x18000da38`: `CleanupRegistry`
- `0x18000db7f`: `CleanupRegistry`

## pseudocode

```c
__int64 __fastcall CRegInfo::RegCleanup(char a1)
{
  unsigned int v2; // ebx
  int v3; // edi
  LSTATUS v4; // eax
  DWORD i; // edx
  signed int v6; // edi
  __int64 v7; // rbx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v13[24]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  ASPNETVER::ASPNETVER((ASPNETVER *)v13);
  hKey = 0;
  v12 = 0;
  v3 = a1 & 1;
  CSetupLogging::Log(1, "CleanupRegistry", 0, "Cleaning up registry");
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 0x20019u, &hKey);
  if ( v4 != 2 )
  {
    if ( v4 )
    {
LABEL_3:
      v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        v2 = v4;
    }
    else
    {
      for ( i = 0; ; i = v2 )
      {
        cchName = 259;
        v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v4 == 259 )
          break;
        if ( v4 )
          goto LABEL_3;
        if ( ASPNETVER::Init((ASPNETVER *)v13, Name)
          && v3
          && !(unsigned int)CRegInfo::IsSamePathKey((struct ASPNETVER *)v13, &v11)
          && v11 )
        {
          AppendCStrAry((CImplPtrAry *)&v12, Name);
        }
        ++v2;
      }
      v6 = 0;
      if ( (v12 & 0xFFFFFFFC) != 0 )
      {
        v7 = 0;
        do
        {
          CRegInfo::RemoveKeyFromRegistry(L"Software\\Microsoft\\ASP.NET", *(LPCWSTR *)(v7 + *((_QWORD *)&v12 + 1)));
          CRegInfo::RemoveRelatedKeys(*(unsigned __int16 **)(v7 + *((_QWORD *)&v12 + 1)));
          v7 += 8;
          ++v6;
        }
        while ( v6 < (int)((unsigned int)v12 >> 2) );
      }
      v2 = 0;
    }
  }
  CSetupLogging::Log(v2, "CleanupRegistry", 0, "Cleaning up registry");
  if ( hKey )
    RegCloseKey(hKey);
  MemFree(0);
  CleanupCStrAry((CImplAry *)&v12);
  CImplAry::~CImplAry((CImplAry *)&v12);
  return v2;
}

```

## disassembly

```asm
0x18000d9f0  mov     [rsp-8+arg_0], rbx
0x18000d9f5  mov     [rsp-8+arg_8], rdi
0x18000d9fa  push    rbp
0x18000d9fb  lea     rbp, [rsp-1A0h]
0x18000da03  sub     rsp, 2A0h
0x18000da0a  mov     rax, cs:__security_cookie
0x18000da11  xor     rax, rsp
0x18000da14  mov     [rbp+1A0h+var_10], rax
0x18000da1b  mov     edi, ecx
0x18000da1d  xor     ebx, ebx
0x18000da1f  lea     rcx, [rsp+2A0h+var_238]; this
0x18000da24  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x18000da29  and     [rsp+2A0h+hKey], rbx
0x18000da2e  lea     r9, aCleaningUpRegi; "Cleaning up registry"
0x18000da35  xorps   xmm0, xmm0
0x18000da38  lea     rdx, aCleanupregistr; "CleanupRegistry"
0x18000da3f  xor     r8d, r8d; unsigned int
0x18000da42  lea     ecx, [rbx+1]; int
0x18000da45  movups  [rsp+2A0h+var_248], xmm0
0x18000da4a  and     edi, 1
0x18000da4d  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18000da52  lea     rax, [rsp+2A0h+hKey]
0x18000da57  mov     r9d, 20019h; samDesired
0x18000da5d  xor     r8d, r8d; ulOptions
0x18000da60  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18000da65  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18000da6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000da73  call    cs:__imp_RegOpenKeyExW
0x18000da79  cmp     eax, 2
0x18000da7c  jz      loc_18000DB75
0x18000da82  test    eax, eax
0x18000da84  jz      short loc_18000DA99
0x18000da86  movzx   ebx, ax
0x18000da89  or      ebx, 80070000h
0x18000da8f  test    eax, eax
0x18000da91  cmovle  ebx, eax
0x18000da94  jmp     loc_18000DB75
0x18000da99  and     [rsp+2A0h+var_268], rbx
0x18000da9e  and     [rsp+2A0h+var_270], rbx
0x18000daa3  and     [rsp+2A0h+var_278], rbx
0x18000daa8  and     [rsp+2A0h+phkResult], rbx
0x18000daad  xor     edx, edx
0x18000daaf  jmp     short loc_18000DB0E
0x18000dab1  test    eax, eax
0x18000dab3  jnz     short loc_18000DA86
0x18000dab5  lea     rdx, [rbp+1A0h+Name]; unsigned __int16 *
0x18000dab9  lea     rcx, [rsp+2A0h+var_238]; this
0x18000dabe  call    ?Init@ASPNETVER@@QEAAHPEBG@Z; ASPNETVER::Init(ushort const *)
0x18000dac3  test    eax, eax
0x18000dac5  jz      short loc_18000DAF2
0x18000dac7  test    edi, edi
0x18000dac9  jz      short loc_18000DAF2
0x18000dacb  lea     rdx, [rsp+2A0h+var_250]; int *
0x18000dad0  lea     rcx, [rsp+2A0h+var_238]; struct ASPNETVER *
0x18000dad5  call    ?IsSamePathKey@CRegInfo@@CAJPEAVASPNETVER@@PEAH@Z; CRegInfo::IsSamePathKey(ASPNETVER *,int *)
0x18000dada  test    eax, eax
0x18000dadc  jnz     short loc_18000DAF2
0x18000dade  cmp     [rsp+2A0h+var_250], eax
0x18000dae2  jz      short loc_18000DAF2
0x18000dae4  lea     rdx, [rbp+1A0h+Name]; Src
0x18000dae8  lea     rcx, [rsp+2A0h+var_248]; this
0x18000daed  call    ?AppendCStrAry@@YAJPEAV?$CPtrAry@PEAG@@PEAG@Z; AppendCStrAry(CPtrAry<ushort *> *,ushort *)
0x18000daf2  and     [rsp+2A0h+var_268], 0
0x18000daf8  inc     ebx
0x18000dafa  and     [rsp+2A0h+var_270], 0
0x18000db00  mov     edx, ebx; dwIndex
0x18000db02  and     [rsp+2A0h+var_278], 0
0x18000db08  and     [rsp+2A0h+phkResult], 0
0x18000db0e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000db13  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000db18  lea     r8, [rbp+1A0h+Name]; lpName
0x18000db1c  mov     [rsp+2A0h+cchName], 103h
0x18000db24  call    cs:__imp_RegEnumKeyExW
0x18000db2a  cmp     eax, 103h
0x18000db2f  jnz     short loc_18000DAB1
0x18000db31  xor     edi, edi
0x18000db33  test    dword ptr [rsp+2A0h+var_248], 0FFFFFFFCh
0x18000db3b  jbe     short loc_18000DB73
0x18000db3d  xor     ebx, ebx
0x18000db3f  mov     rdx, qword ptr [rsp+2A0h+var_248+8]
0x18000db44  lea     rcx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18000db4b  mov     rdx, [rbx+rdx]; pszSubKey
0x18000db4f  call    ?RemoveKeyFromRegistry@CRegInfo@@SAJPEAG0@Z; CRegInfo::RemoveKeyFromRegistry(ushort *,ushort *)
0x18000db54  mov     rcx, qword ptr [rsp+2A0h+var_248+8]
0x18000db59  mov     rcx, [rbx+rcx]; unsigned __int16 *
0x18000db5d  call    ?RemoveRelatedKeys@CRegInfo@@SAJPEAG@Z; CRegInfo::RemoveRelatedKeys(ushort *)
0x18000db62  mov     eax, dword ptr [rsp+2A0h+var_248]
0x18000db66  lea     rbx, [rbx+8]
0x18000db6a  shr     eax, 2
0x18000db6d  inc     edi
0x18000db6f  cmp     edi, eax
0x18000db71  jl      short loc_18000DB3F
0x18000db73  xor     ebx, ebx
0x18000db75  lea     r9, aCleaningUpRegi; "Cleaning up registry"
0x18000db7c  xor     r8d, r8d; unsigned int
0x18000db7f  lea     rdx, aCleanupregistr; "CleanupRegistry"
0x18000db86  mov     ecx, ebx; int
0x18000db88  call    ?Log@CSetupLogging@@SAXJPEBDI0@Z; CSetupLogging::Log(long,char const *,uint,char const *)
0x18000db8d  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000db92  test    rcx, rcx
0x18000db95  jz      short loc_18000DB9D
0x18000db97  call    cs:__imp_RegCloseKey
0x18000db9d  xor     ecx, ecx; lpMem
0x18000db9f  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000dba4  lea     rcx, [rsp+2A0h+var_248]; this
0x18000dba9  call    ?CleanupCStrAry@@YAXPEAV?$CPtrAry@PEAG@@@Z; CleanupCStrAry(CPtrAry<ushort *> *)
0x18000dbae  lea     rcx, [rsp+2A0h+var_248]; this
0x18000dbb3  call    ??1CImplAry@@QEAA@XZ; CImplAry::~CImplAry(void)
0x18000dbb8  mov     eax, ebx
0x18000dbba  mov     rcx, [rbp+1A0h+var_10]
0x18000dbc1  xor     rcx, rsp; StackCookie
0x18000dbc4  call    __security_check_cookie
0x18000dbc9  lea     r11, [rsp+2A0h+var_s0]
0x18000dbd1  mov     rbx, [r11+10h]
0x18000dbd5  mov     rdi, [r11+18h]
0x18000dbd9  mov     rsp, r11
0x18000dbdc  pop     rbp
0x18000dbdd  retn
```
