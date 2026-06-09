# ATL::CRegKey::RecurseDeleteKey(char const *)

- ea: `0x180011538`
- end: `0x180011676`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z`
- size: `318`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011538`
- `0x180011b0c`

## callees

- `0x180010e78`
- `0x180011538`
- `0x180014270`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180011593`
- `ADVAPI32!RegOpenKeyExA` at `0x180011593`
- `ADVAPI32!RegEnumKeyExA` at `0x180011614`
- `ADVAPI32!RegEnumKeyExA` at `0x180011614`
- `ADVAPI32!RegCloseKey` at `0x1800115b0`
- `ADVAPI32!RegCloseKey` at `0x180011628`
- `ADVAPI32!RegCloseKey` at `0x18001164a`
- `ADVAPI32!RegCloseKey` at `0x1800115b0`
- `ADVAPI32!RegCloseKey` at `0x180011628`
- `ADVAPI32!RegCloseKey` at `0x18001164a`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const char *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  CHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExA(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExA(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x180011538  mov     [rsp-8+arg_10], rbx
0x18001153d  mov     [rsp-8+arg_18], rsi
0x180011542  push    rbp
0x180011543  push    rdi
0x180011544  push    r14
0x180011546  lea     rbp, [rsp-80h]
0x18001154b  sub     rsp, 180h
0x180011552  mov     rax, cs:__security_cookie
0x180011559  xor     rax, rsp
0x18001155c  mov     [rbp+90h+var_20], rax
0x180011560  xor     r14d, r14d
0x180011563  lea     rax, [rsp+190h+var_130]
0x180011568  mov     rdi, rcx
0x18001156b  mov     [rsp+190h+hKey], r14
0x180011570  mov     rcx, [rcx]; hKey
0x180011573  mov     r9d, 2001Fh; samDesired
0x180011579  xor     r8d, r8d; ulOptions
0x18001157c  mov     [rsp+190h+var_140], r14
0x180011581  mov     [rsp+190h+var_138], r14
0x180011586  mov     rsi, rdx
0x180011589  mov     [rsp+190h+var_130], r14
0x18001158e  mov     [rsp+190h+phkResult], rax; phkResult
0x180011593  call    cs:__imp_RegOpenKeyExA
0x180011599  mov     rcx, [rsp+190h+hKey]; hKey
0x18001159e  mov     ebx, eax
0x1800115a0  test    eax, eax
0x1800115a2  jnz     loc_180011645
0x1800115a8  mov     ebx, r14d
0x1800115ab  test    rcx, rcx
0x1800115ae  jz      short loc_1800115B8
0x1800115b0  call    cs:__imp_RegCloseKey
0x1800115b6  mov     ebx, eax
0x1800115b8  mov     rcx, [rsp+190h+var_130]
0x1800115bd  mov     [rsp+190h+hKey], rcx
0x1800115c2  test    ebx, ebx
0x1800115c4  jnz     short loc_180011645
0x1800115c6  mov     qword ptr [rsp+190h+ftLastWriteTime.dwLowDateTime], r14
0x1800115cb  jmp     short loc_1800115E7
0x1800115cd  lea     rdx, [rsp+190h+Name]; char *
0x1800115d2  lea     rcx, [rsp+190h+hKey]; this
0x1800115d7  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::RecurseDeleteKey(char const *)
0x1800115dc  mov     rcx, [rsp+190h+hKey]; hKey
0x1800115e1  mov     ebx, eax
0x1800115e3  test    eax, eax
0x1800115e5  jnz     short loc_180011645
0x1800115e7  lea     rax, [rsp+190h+ftLastWriteTime]
0x1800115ec  mov     [rsp+190h+cchName], 100h
0x1800115f4  mov     [rsp+190h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800115f9  lea     r9, [rsp+190h+cchName]; lpcchName
0x1800115fe  mov     [rsp+190h+lpcchClass], r14; lpcchClass
0x180011603  lea     r8, [rsp+190h+Name]; lpName
0x180011608  mov     [rsp+190h+lpClass], r14; lpClass
0x18001160d  xor     edx, edx; dwIndex
0x18001160f  mov     [rsp+190h+phkResult], r14; lpReserved
0x180011614  call    cs:__imp_RegEnumKeyExA
0x18001161a  test    eax, eax
0x18001161c  jz      short loc_1800115CD
0x18001161e  mov     rcx, [rsp+190h+hKey]; hKey
0x180011623  test    rcx, rcx
0x180011626  jz      short loc_180011633
0x180011628  call    cs:__imp_RegCloseKey
0x18001162e  mov     [rsp+190h+hKey], r14
0x180011633  mov     rdx, rsi; char *
0x180011636  mov     rcx, rdi; this
0x180011639  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z; ATL::CRegKey::DeleteSubKey(char const *)
0x18001163e  mov     rcx, [rsp+190h+hKey]; hKey
0x180011643  mov     ebx, eax
0x180011645  test    rcx, rcx
0x180011648  jz      short loc_180011650
0x18001164a  call    cs:__imp_RegCloseKey
0x180011650  mov     eax, ebx
0x180011652  mov     rcx, [rbp+90h+var_20]
0x180011656  xor     rcx, rsp; StackCookie
0x180011659  call    __security_check_cookie
0x18001165e  lea     r11, [rsp+190h+var_10]
0x180011666  mov     rbx, [r11+30h]
0x18001166a  mov     rsi, [r11+38h]
0x18001166e  mov     rsp, r11
0x180011671  pop     r14
0x180011673  pop     rdi
0x180011674  pop     rbp
0x180011675  retn
```
