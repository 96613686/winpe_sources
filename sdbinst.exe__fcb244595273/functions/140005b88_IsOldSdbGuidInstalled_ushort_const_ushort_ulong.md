# IsOldSdbGuidInstalled(ushort const *,ushort *,ulong)

- ea: `0x140005b88`
- end: `0x140005ce0`
- name: `?IsOldSdbGuidInstalled@@YAHPEBGPEAGK@Z`
- size: `344`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x140001e68`
- `0x140005b88`
- `0x140007024`
- `0x140007098`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140005c4f`
- `ADVAPI32!RegQueryValueExW` at `0x140005c4f`
- `ADVAPI32!RegOpenKeyExW` at `0x140005c11`
- `ADVAPI32!RegOpenKeyExW` at `0x140005c11`
- `ADVAPI32!RegCloseKey` at `0x140005cb0`
- `ADVAPI32!RegCloseKey` at `0x140005cb0`

## string_xrefs

- `0x140005bd3`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x140005c48`: `DatabasePath`

## pseudocode

```c
_BOOL8 __fastcall IsOldSdbGuidInstalled(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  BOOL v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned __int64 v6; // r8
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v3 = 0;
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB",
              a1) >= 0
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x101u, &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"DatabasePath", 0, &Type, Data, &cbData)
      && Type == 1
      && (cbData & 0xFFFFFFFE) < 0x208
      && *(_WORD *)Data )
    {
      v6 = cbData & 0xFFFFFFFE;
      if ( v6 >= 0x208 )
        _report_rangecheckfailure(v5, v4);
      *(_WORD *)&Data[v6] = 0;
      v3 = (int)StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)Data) >= 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140005b88  mov     [rsp-8+arg_10], rbx
0x140005b8d  push    rbp
0x140005b8e  push    rsi
0x140005b8f  push    rdi
0x140005b90  lea     rbp, [rsp-370h]
0x140005b98  sub     rsp, 470h
0x140005b9f  mov     rax, cs:__security_cookie
0x140005ba6  xor     rax, rsp
0x140005ba9  mov     [rbp+380h+var_20], rax
0x140005bb0  xor     esi, esi
0x140005bb2  mov     [rsp+480h+phkResult], rcx
0x140005bb7  mov     rdi, rdx
0x140005bba  mov     [rsp+480h+hKey], rsi
0x140005bbf  mov     edx, 104h; unsigned __int64
0x140005bc4  mov     [rsp+480h+cbData], esi
0x140005bc8  lea     rcx, [rbp+380h+SubKey]; unsigned __int16 *
0x140005bcf  mov     [rsp+480h+Type], esi
0x140005bd3  lea     r9, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140005bda  mov     ebx, esi
0x140005bdc  lea     r8, aSS_0; "%s\\%s"
0x140005be3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005be8  test    eax, eax
0x140005bea  js      loc_140005CA6
0x140005bf0  lea     rax, [rsp+480h+hKey]
0x140005bf5  mov     r9d, 101h; samDesired
0x140005bfb  xor     r8d, r8d; ulOptions
0x140005bfe  mov     [rsp+480h+phkResult], rax; phkResult
0x140005c03  lea     rdx, [rbp+380h+SubKey]; lpSubKey
0x140005c0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005c11  call    cs:__imp_RegOpenKeyExW
0x140005c17  test    eax, eax
0x140005c19  jnz     loc_140005CA6
0x140005c1f  mov     rcx, [rsp+480h+hKey]; hKey
0x140005c24  lea     rax, [rsp+480h+cbData]
0x140005c29  mov     [rsp+480h+lpcbData], rax; lpcbData
0x140005c2e  lea     r9, [rsp+480h+Type]; lpType
0x140005c33  lea     rax, [rsp+480h+Data]
0x140005c38  mov     [rsp+480h+cbData], 208h
0x140005c40  xor     r8d, r8d; lpReserved
0x140005c43  mov     [rsp+480h+phkResult], rax; lpData
0x140005c48  lea     rdx, aDatabasepath; "DatabasePath"
0x140005c4f  call    cs:__imp_RegQueryValueExW
0x140005c55  test    eax, eax
0x140005c57  jnz     short loc_140005CA6
0x140005c59  cmp     [rsp+480h+Type], 1
0x140005c5e  jnz     short loc_140005CA6
0x140005c60  mov     eax, [rsp+480h+cbData]
0x140005c64  and     eax, 0FFFFFFFEh
0x140005c67  cmp     eax, 208h
0x140005c6c  jnb     short loc_140005CA6
0x140005c6e  cmp     word ptr [rsp+480h+Data], si
0x140005c73  jz      short loc_140005CA6
0x140005c75  mov     r8d, [rsp+480h+cbData]
0x140005c7a  and     r8, 0FFFFFFFFFFFFFFFEh
0x140005c7e  cmp     r8, 208h
0x140005c85  jnb     short loc_140005CDA
0x140005c87  mov     word ptr [rsp+r8+480h+Data], si
0x140005c8d  mov     edx, 104h; unsigned __int64
0x140005c92  lea     r8, [rsp+480h+Data]; unsigned __int16 *
0x140005c97  mov     rcx, rdi; unsigned __int16 *
0x140005c9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140005c9f  test    eax, eax
0x140005ca1  js      short loc_140005CA6
0x140005ca3  lea     ebx, [rsi+1]
0x140005ca6  mov     rcx, [rsp+480h+hKey]; hKey
0x140005cab  test    rcx, rcx
0x140005cae  jz      short loc_140005CB6
0x140005cb0  call    cs:__imp_RegCloseKey
0x140005cb6  mov     eax, ebx
0x140005cb8  mov     rcx, [rbp+380h+var_20]
0x140005cbf  xor     rcx, rsp; StackCookie
0x140005cc2  call    __security_check_cookie
0x140005cc7  mov     rbx, [rsp+480h+arg_10]
0x140005ccf  add     rsp, 470h
0x140005cd6  pop     rdi
0x140005cd7  pop     rsi
0x140005cd8  pop     rbp
0x140005cd9  retn
0x140005cda  call    __report_rangecheckfailure
```
