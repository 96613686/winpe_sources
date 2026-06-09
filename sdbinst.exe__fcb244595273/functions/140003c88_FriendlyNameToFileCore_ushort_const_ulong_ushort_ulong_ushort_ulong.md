# FriendlyNameToFileCore(ushort const *,ulong *,ushort *,ulong,ushort *,ulong)

- ea: `0x140003c88`
- end: `0x140003fee`
- name: `?FriendlyNameToFileCore@@YAHPEBGPEAKPEAGK2K@Z`
- size: `870`
- prototype: `_BOOL8 __fastcall(wchar_t *String2, unsigned int *, unsigned __int16 *, __int64, unsigned __int16 *Str)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x140001e68`
- `0x140003c88`
- `0x140006238`
- `0x140007024`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140003d90`
- `ADVAPI32!RegQueryValueExW` at `0x140003dec`
- `ADVAPI32!RegQueryValueExW` at `0x140003e95`
- `ADVAPI32!RegQueryValueExW` at `0x140003d90`
- `ADVAPI32!RegQueryValueExW` at `0x140003dec`
- `ADVAPI32!RegQueryValueExW` at `0x140003e95`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d10`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d52`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d10`
- `ADVAPI32!RegOpenKeyExW` at `0x140003d52`
- `ADVAPI32!RegEnumKeyExW` at `0x140003f21`
- `ADVAPI32!RegEnumKeyExW` at `0x140003f21`
- `ADVAPI32!RegCloseKey` at `0x140003ee3`
- `ADVAPI32!RegCloseKey` at `0x140003f9a`
- `ADVAPI32!RegCloseKey` at `0x140003faf`
- `ADVAPI32!RegCloseKey` at `0x140003ee3`
- `ADVAPI32!RegCloseKey` at `0x140003f9a`
- `ADVAPI32!RegCloseKey` at `0x140003faf`
- `msvcrt!wcsrchr` at `0x140003f55`
- `msvcrt!wcsrchr` at `0x140003f55`
- `msvcrt!_wcsicmp` at `0x140003e4b`
- `msvcrt!_wcsicmp` at `0x140003e4b`

## string_xrefs

- `0x140003cec`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x140003e8e`: `DatabasePath`

## pseudocode

```c
_BOOL8 __fastcall FriendlyNameToFileCore(
        wchar_t *String2,
        unsigned int *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *Str)
{
  int v8; // edi
  DWORD v9; // r14d
  DWORD i; // edx
  unsigned __int64 v11; // rcx
  LSTATUS v12; // eax
  wchar_t *v13; // rax
  BOOL v14; // ebx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v23[2]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR SubKey[264]; // [rsp+480h] [rbp+380h] BYREF

  hKey = 0;
  phkResult = 0;
  cbData = 0;
  cchName = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  *(_WORD *)v22 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB",
          0,
          0x109u,
          &hKey) )
  {
    v8 = 0;
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      cchName = 260;
      v12 = RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0);
      if ( v12 == 259 )
        break;
      if ( v12 || RegOpenKeyExW(hKey, SubKey, 0, 0x101u, &phkResult) )
        goto LABEL_33;
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"DatabaseRuntimePlatform", 0, &Type, Data, &cbData)
        && Type == 4
        && (!a2 || (*a2 & *(_DWORD *)Data) != 0) )
      {
        cbData = 520;
        if ( !RegQueryValueExW(phkResult, L"DatabaseDescription", 0, &Type, v23, &cbData)
          && Type == 1
          && (cbData & 0xFFFFFFFE) < 0x208
          && *(_WORD *)v23 )
        {
          v11 = cbData & 0xFFFFFFFE;
          if ( v11 >= 0x208 )
            goto LABEL_40;
          *(_WORD *)&v23[v11] = 0;
          if ( !_wcsicmp((const wchar_t *)v23, String2) )
          {
            if ( *(_WORD *)v22 )
            {
              if ( v8 == *(_DWORD *)Data )
                PrintMessage(0x424u);
              else
                PrintMessage(0x41Eu);
              goto LABEL_33;
            }
            cbData = 520;
            if ( !RegQueryValueExW(phkResult, L"DatabasePath", 0, &Type, v22, &cbData)
              && Type == 1
              && (cbData & 0xFFFFFFFE) < 0x208
              && *(_WORD *)v22 )
            {
              v11 = cbData & 0xFFFFFFFE;
              if ( v11 >= 0x208 )
LABEL_40:
                _report_rangecheckfailure(v11, 520);
              v8 = *(_DWORD *)Data;
              *(_WORD *)&v22[v11] = 0;
            }
          }
        }
      }
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      ++v9;
    }
    if ( (int)StringCchCopyW(Str, 0x104u, (const unsigned __int16 *)v22) >= 0 )
    {
      if ( Str )
      {
        v13 = wcsrchr(Str, 0x5Cu);
        if ( v13 )
        {
          if ( v13 != (wchar_t *)-2LL )
          {
            v14 = (int)StringCchCopyW(a3, 0x104u, v13 + 1) >= 0;
            goto LABEL_34;
          }
        }
      }
    }
  }
LABEL_33:
  v14 = 0;
LABEL_34:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v14;
}

```

## disassembly

```asm
0x140003c88  mov     [rsp-8+arg_8], rbx
0x140003c8d  push    rbp
0x140003c8e  push    rsi
0x140003c8f  push    rdi
0x140003c90  push    r12
0x140003c92  push    r13
0x140003c94  push    r14
0x140003c96  push    r15
0x140003c98  lea     rbp, [rsp-5A0h]
0x140003ca0  sub     rsp, 6A0h
0x140003ca7  mov     rax, cs:__security_cookie
0x140003cae  xor     rax, rsp
0x140003cb1  mov     [rbp+5D0h+var_40], rax
0x140003cb8  mov     rbx, [rbp+5D0h+Str]
0x140003cbf  lea     rax, [rsp+6D0h+hKey]
0x140003cc4  xor     r13d, r13d
0x140003cc7  mov     [rsp+6D0h+phkResult], rax; phkResult
0x140003ccc  mov     r15, r8
0x140003ccf  mov     [rsp+6D0h+hKey], r13
0x140003cd4  mov     rsi, rdx
0x140003cd7  mov     [rsp+6D0h+var_680], r13
0x140003cdc  mov     r12, rcx
0x140003cdf  mov     [rsp+6D0h+cbData], r13d
0x140003ce4  xor     r8d, r8d; ulOptions
0x140003ce7  mov     [rsp+6D0h+cchName], r13d
0x140003cec  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003cf3  mov     dword ptr [rsp+6D0h+Data], r13d
0x140003cf8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003cff  mov     [rsp+6D0h+Type], r13d
0x140003d04  mov     r9d, 109h; samDesired
0x140003d0a  mov     word ptr [rsp+6D0h+var_670], r13w
0x140003d10  call    cs:__imp_RegOpenKeyExW
0x140003d16  test    eax, eax
0x140003d18  jnz     loc_140003F8D
0x140003d1e  mov     edi, r13d
0x140003d21  mov     r14d, r13d
0x140003d24  xor     edx, edx
0x140003d26  jmp     loc_140003EF4
0x140003d2b  test    eax, eax
0x140003d2d  jnz     loc_140003F8D
0x140003d33  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140003d38  lea     rax, [rsp+6D0h+var_680]
0x140003d3d  mov     r9d, 101h; samDesired
0x140003d43  mov     [rsp+6D0h+phkResult], rax; phkResult
0x140003d48  xor     r8d, r8d; ulOptions
0x140003d4b  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x140003d52  call    cs:__imp_RegOpenKeyExW
0x140003d58  test    eax, eax
0x140003d5a  jnz     loc_140003F8D
0x140003d60  mov     rcx, [rsp+6D0h+var_680]; hKey
0x140003d65  lea     rax, [rsp+6D0h+cbData]
0x140003d6a  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x140003d6f  lea     r9, [rsp+6D0h+Type]; lpType
0x140003d74  lea     rax, [rsp+6D0h+Data]
0x140003d79  mov     [rsp+6D0h+cbData], 4
0x140003d81  xor     r8d, r8d; lpReserved
0x140003d84  mov     [rsp+6D0h+phkResult], rax; lpData
0x140003d89  lea     rdx, ValueName; "DatabaseRuntimePlatform"
0x140003d90  call    cs:__imp_RegQueryValueExW
0x140003d96  test    eax, eax
0x140003d98  jnz     loc_140003ED9
0x140003d9e  cmp     [rsp+6D0h+Type], 4
0x140003da3  jnz     loc_140003ED9
0x140003da9  test    rsi, rsi
0x140003dac  jz      short loc_140003DBA
0x140003dae  mov     eax, [rsi]
0x140003db0  test    dword ptr [rsp+6D0h+Data], eax
0x140003db4  jz      loc_140003ED9
0x140003dba  mov     rcx, [rsp+6D0h+var_680]; hKey
0x140003dbf  lea     rax, [rsp+6D0h+cbData]
0x140003dc4  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x140003dc9  lea     r9, [rsp+6D0h+Type]; lpType
0x140003dce  lea     rax, [rbp+5D0h+var_460]
0x140003dd5  mov     [rsp+6D0h+cbData], 208h
0x140003ddd  xor     r8d, r8d; lpReserved
0x140003de0  mov     [rsp+6D0h+phkResult], rax; lpData
0x140003de5  lea     rdx, aDatabasedescri; "DatabaseDescription"
0x140003dec  call    cs:__imp_RegQueryValueExW
0x140003df2  test    eax, eax
0x140003df4  jnz     loc_140003ED9
0x140003dfa  cmp     [rsp+6D0h+Type], 1
0x140003dff  jnz     loc_140003ED9
0x140003e05  mov     eax, [rsp+6D0h+cbData]
0x140003e09  mov     edx, 208h
0x140003e0e  and     eax, 0FFFFFFFEh
0x140003e11  cmp     eax, edx
0x140003e13  jnb     loc_140003ED9
0x140003e19  cmp     word ptr [rbp+5D0h+var_460], r13w
0x140003e21  jz      loc_140003ED9
0x140003e27  mov     ecx, [rsp+6D0h+cbData]
0x140003e2b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140003e2f  cmp     rcx, rdx
0x140003e32  jnb     loc_140003FE8
0x140003e38  mov     word ptr [rbp+rcx+5D0h+var_460], r13w
0x140003e41  mov     rdx, r12; String2
0x140003e44  lea     rcx, [rbp+5D0h+var_460]; String1
0x140003e4b  call    cs:__imp__wcsicmp
0x140003e51  test    eax, eax
0x140003e53  jnz     loc_140003ED9
0x140003e59  cmp     word ptr [rsp+6D0h+var_670], r13w
0x140003e5f  jnz     loc_140003F7D
0x140003e65  mov     rcx, [rsp+6D0h+var_680]; hKey
0x140003e6a  lea     rax, [rsp+6D0h+cbData]
0x140003e6f  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x140003e74  lea     r9, [rsp+6D0h+Type]; lpType
0x140003e79  lea     rax, [rsp+6D0h+var_670]
0x140003e7e  mov     [rsp+6D0h+cbData], 208h
0x140003e86  xor     r8d, r8d; lpReserved
0x140003e89  mov     [rsp+6D0h+phkResult], rax; lpData
0x140003e8e  lea     rdx, aDatabasepath; "DatabasePath"
0x140003e95  call    cs:__imp_RegQueryValueExW
0x140003e9b  test    eax, eax
0x140003e9d  jnz     short loc_140003ED9
0x140003e9f  cmp     [rsp+6D0h+Type], 1
0x140003ea4  jnz     short loc_140003ED9
0x140003ea6  mov     eax, [rsp+6D0h+cbData]
0x140003eaa  mov     edx, 208h
0x140003eaf  and     eax, 0FFFFFFFEh
0x140003eb2  cmp     eax, edx
0x140003eb4  jnb     short loc_140003ED9
0x140003eb6  cmp     word ptr [rsp+6D0h+var_670], r13w
0x140003ebc  jz      short loc_140003ED9
0x140003ebe  mov     ecx, [rsp+6D0h+cbData]
0x140003ec2  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140003ec6  cmp     rcx, rdx
0x140003ec9  jnb     loc_140003FE8
0x140003ecf  mov     edi, dword ptr [rsp+6D0h+Data]
0x140003ed3  mov     word ptr [rsp+rcx+6D0h+var_670], r13w
0x140003ed9  mov     rcx, [rsp+6D0h+var_680]; hKey
0x140003ede  test    rcx, rcx
0x140003ee1  jz      short loc_140003EEE
0x140003ee3  call    cs:__imp_RegCloseKey
0x140003ee9  mov     [rsp+6D0h+var_680], r13
0x140003eee  inc     r14d
0x140003ef1  mov     edx, r14d; dwIndex
0x140003ef4  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140003ef9  lea     r9, [rsp+6D0h+cchName]; lpcchName
0x140003efe  mov     [rsp+6D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140003f03  lea     r8, [rbp+5D0h+SubKey]; lpName
0x140003f0a  mov     [rsp+6D0h+lpcchClass], r13; lpcchClass
0x140003f0f  mov     [rsp+6D0h+lpcbData], r13; lpClass
0x140003f14  mov     [rsp+6D0h+phkResult], r13; lpReserved
0x140003f19  mov     [rsp+6D0h+cchName], 104h
0x140003f21  call    cs:__imp_RegEnumKeyExW
0x140003f27  cmp     eax, 103h
0x140003f2c  jnz     loc_140003D2B
0x140003f32  lea     edi, [rax+1]
0x140003f35  mov     rcx, rbx; unsigned __int16 *
0x140003f38  mov     edx, edi; unsigned __int64
0x140003f3a  lea     r8, [rsp+6D0h+var_670]; unsigned __int16 *
0x140003f3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003f44  test    eax, eax
0x140003f46  js      short loc_140003F8D
0x140003f48  test    rbx, rbx
0x140003f4b  jz      short loc_140003F8D
0x140003f4d  mov     edx, 5Ch ; '\'; Ch
0x140003f52  mov     rcx, rbx; Str
0x140003f55  call    cs:__imp_wcsrchr
0x140003f5b  test    rax, rax
0x140003f5e  jz      short loc_140003F8D
0x140003f60  lea     r8, [rax+2]; unsigned __int16 *
0x140003f64  test    r8, r8
0x140003f67  jz      short loc_140003F8D
0x140003f69  mov     edx, edi; unsigned __int64
0x140003f6b  mov     rcx, r15; unsigned __int16 *
0x140003f6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003f73  test    eax, eax
0x140003f75  mov     ebx, r13d
0x140003f78  setns   bl
0x140003f7b  jmp     short loc_140003F90
0x140003f7d  cmp     edi, dword ptr [rsp+6D0h+Data]
0x140003f81  jz      short loc_140003FE1
0x140003f83  mov     ecx, 41Eh; unsigned int
0x140003f88  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140003f8d  mov     ebx, r13d
0x140003f90  mov     rcx, [rsp+6D0h+var_680]; hKey
0x140003f95  test    rcx, rcx
0x140003f98  jz      short loc_140003FA5
0x140003f9a  call    cs:__imp_RegCloseKey
0x140003fa0  mov     [rsp+6D0h+var_680], r13
0x140003fa5  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140003faa  test    rcx, rcx
0x140003fad  jz      short loc_140003FB5
0x140003faf  call    cs:__imp_RegCloseKey
0x140003fb5  mov     eax, ebx
0x140003fb7  mov     rcx, [rbp+5D0h+var_40]
0x140003fbe  xor     rcx, rsp; StackCookie
0x140003fc1  call    __security_check_cookie
0x140003fc6  mov     rbx, [rsp+6D0h+arg_8]
0x140003fce  add     rsp, 6A0h
0x140003fd5  pop     r15
0x140003fd7  pop     r14
0x140003fd9  pop     r13
0x140003fdb  pop     r12
0x140003fdd  pop     rdi
0x140003fde  pop     rsi
0x140003fdf  pop     rbp
0x140003fe0  retn
0x140003fe1  mov     ecx, 424h
0x140003fe6  jmp     short loc_140003F88
0x140003fe8  call    __report_rangecheckfailure
```
