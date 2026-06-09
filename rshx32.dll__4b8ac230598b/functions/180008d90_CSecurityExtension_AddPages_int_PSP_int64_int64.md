# CSecurityExtension::AddPages(int (*)(_PSP *,__int64),__int64)

- ea: `0x180008d90`
- end: `0x180008f27`
- name: `?AddPages@CSecurityExtension@@UEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `407`
- prototype: `__int64 __fastcall(struct IDataObject **this, unsigned int (__fastcall *)(HPROPSHEETPAGE, __int64), __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008d90`
- `0x180009f84`
- `0x18000a0e4`
- `0x18000a39c`
- `0x18000a440`
- `0x18000a7a0`
- `0x18000cbfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008e01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008e01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008e3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e50`
- `KERNEL32!GlobalUnlock` at `0x180008ee4`
- `KERNEL32!GlobalUnlock` at `0x180008ee4`
- `ole32!ReleaseStgMedium` at `0x180008eee`
- `ole32!ReleaseStgMedium` at `0x180008eee`

## string_xrefs

- `0x180008e18`: `NoSecurityTab`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::AddPages(
        struct IDataObject **this,
        unsigned int (__fastcall *a2)(HPROPSHEETPAGE, __int64),
        __int64 a3)
{
  int v6; // ebx
  BOOL v7; // ebx
  struct IDataObject **v8; // rdi
  struct _IDA *v9; // rdx
  int v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  struct _IDA *v14; // [rsp+40h] [rbp-20h] BYREF
  STGMEDIUM hMem; // [rsp+48h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+A8h] [rbp+48h] BYREF

  memset(&hMem, 0, sizeof(hMem));
  v14 = 0;
  if ( (unsigned int)IsSimpleUI() )
    return (unsigned int)-2147467259;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer",
          0,
          1u,
          &hKey) )
  {
    cbData = 4;
    v7 = 0;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"NoSecurityTab", 0, 0, (LPBYTE)&Data, &cbData) )
      v7 = Data == 1;
    RegCloseKey(hKey);
    if ( v7 )
      return (unsigned int)-2147467259;
  }
  v8 = this - 1;
  v6 = SHGetItemArrayFromDataObj(this[3], &hMem, &v14);
  if ( v6 >= 0 )
  {
    v9 = v14;
    if ( v14->cidl == 1 )
    {
      if ( *((_DWORD *)this + 5) == 1 )
        *((_DWORD *)this + 9) |= 0x400000u;
      v6 = *((_DWORD *)v8 + 10);
      if ( v6 != -1 )
        goto LABEL_14;
      Data = 0;
      v10 = CSecurityExtension::_ReadDataObject((CSecurityExtension *)(this - 1), v9, &Data);
      *((_DWORD *)v8 + 10) = v10;
      v6 = v10;
      if ( !v10 )
      {
        v6 = CSecurityExtension::_CheckForSecurity((CSecurityExtension *)(this - 1), Data);
        *((_DWORD *)v8 + 10) = v6;
LABEL_14:
        if ( !v6 )
          v6 = CSecurityExtension::_AddSecurityPage((CSecurityExtension *)(this - 1), a2, a3);
      }
    }
    if ( hMem.hBitmap && hMem.tymed == 1 )
      GlobalUnlock(hMem.hBitmap);
    ReleaseStgMedium(&hMem);
    return (unsigned int)v6;
  }
  if ( *((_DWORD *)this + 5) == 1 )
    return (unsigned int)CSecurityExtension::_AddMountedVolumePage(
                           (CSecurityExtension *)(this - 1),
                           (int (*)(struct _PSP *, __int64))a2,
                           a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008d90  mov     [rsp-28h+arg_0], rbx
0x180008d95  mov     [rsp-28h+arg_8], rsi
0x180008d9a  push    rbp
0x180008d9b  push    rdi
0x180008d9c  push    r13
0x180008d9e  push    r14
0x180008da0  push    r15
0x180008da2  mov     rbp, rsp
0x180008da5  sub     rsp, 60h
0x180008da9  xor     eax, eax
0x180008dab  xorps   xmm0, xmm0
0x180008dae  movups  xmmword ptr [rbp+hMem], xmm0
0x180008db2  mov     [rbp+var_8], rax
0x180008db6  mov     r14, r8
0x180008db9  mov     [rbp+var_20], rax
0x180008dbd  mov     r15, rdx
0x180008dc0  mov     rsi, rcx
0x180008dc3  call    ?IsSimpleUI@@YAHXZ; IsSimpleUI(void)
0x180008dc8  test    eax, eax
0x180008dca  jz      short loc_180008DD6
0x180008dcc  mov     ebx, 80004005h
0x180008dd1  jmp     loc_180008F0C
0x180008dd6  lea     rax, [rbp+hKey]
0x180008dda  mov     [rbp+hKey], 0
0x180008de2  mov     r13d, 1
0x180008de8  mov     [rsp+60h+phkResult], rax; phkResult
0x180008ded  mov     r9d, r13d; samDesired
0x180008df0  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008df7  xor     r8d, r8d; ulOptions
0x180008dfa  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180008e01  call    cs:__imp_RegOpenKeyExW
0x180008e07  test    eax, eax
0x180008e09  jnz     short loc_180008E5E
0x180008e0b  mov     rcx, [rbp+hKey]; hKey
0x180008e0f  lea     rax, [rbp+cbData]
0x180008e13  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180008e18  lea     rdx, aNosecuritytab; "NoSecurityTab"
0x180008e1f  lea     rax, [rbp+Data]
0x180008e23  mov     [rbp+cbData], 4
0x180008e2a  xor     ebx, ebx
0x180008e2c  mov     [rsp+60h+phkResult], rax; lpData
0x180008e31  xor     r9d, r9d; lpType
0x180008e34  mov     [rbp+Data], ebx
0x180008e37  xor     r8d, r8d; lpReserved
0x180008e3a  call    cs:__imp_RegQueryValueExW
0x180008e40  test    eax, eax
0x180008e42  jnz     short loc_180008E4C
0x180008e44  cmp     [rbp+Data], r13d
0x180008e48  cmovz   ebx, r13d
0x180008e4c  mov     rcx, [rbp+hKey]; hKey
0x180008e50  call    cs:__imp_RegCloseKey
0x180008e56  test    ebx, ebx
0x180008e58  jnz     loc_180008DCC
0x180008e5e  lea     rdi, [rsi-8]
0x180008e62  mov     rcx, [rdi+20h]; struct IDataObject *
0x180008e66  lea     r8, [rbp+var_20]; struct _IDA **
0x180008e6a  lea     rdx, [rbp+hMem]; struct tagSTGMEDIUM *
0x180008e6e  call    ?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)
0x180008e73  mov     ebx, eax
0x180008e75  test    eax, eax
0x180008e77  js      short loc_180008EF6
0x180008e79  mov     rdx, [rbp+var_20]; struct _IDA *
0x180008e7d  cmp     [rdx], r13d
0x180008e80  jnz     short loc_180008ED5
0x180008e82  cmp     [rsi+14h], r13d
0x180008e86  jnz     short loc_180008E8D
0x180008e88  bts     dword ptr [rsi+24h], 16h
0x180008e8d  mov     ebx, [rdi+28h]
0x180008e90  cmp     ebx, 0FFFFFFFFh
0x180008e93  jnz     short loc_180008EC1
0x180008e95  lea     r8, [rbp+Data]; unsigned int *
0x180008e99  mov     [rbp+Data], 0
0x180008ea0  mov     rcx, rdi; this
0x180008ea3  call    ?_ReadDataObject@CSecurityExtension@@AEAAJPEAU_IDA@@PEAK@Z; CSecurityExtension::_ReadDataObject(_IDA *,ulong *)
0x180008ea8  mov     [rdi+28h], eax
0x180008eab  mov     ebx, eax
0x180008ead  test    eax, eax
0x180008eaf  jnz     short loc_180008ED5
0x180008eb1  mov     edx, [rbp+Data]; unsigned int
0x180008eb4  mov     rcx, rdi; this
0x180008eb7  call    ?_CheckForSecurity@CSecurityExtension@@AEAAJK@Z; CSecurityExtension::_CheckForSecurity(ulong)
0x180008ebc  mov     ebx, eax
0x180008ebe  mov     [rdi+28h], eax
0x180008ec1  test    ebx, ebx
0x180008ec3  jnz     short loc_180008ED5
0x180008ec5  mov     r8, r14; __int64
0x180008ec8  mov     rdx, r15; int (*)(struct _PSP *, __int64)
0x180008ecb  mov     rcx, rdi; this
0x180008ece  call    ?_AddSecurityPage@CSecurityExtension@@AEAAJP6AHPEAU_PSP@@_J@Z1@Z; CSecurityExtension::_AddSecurityPage(int (*)(_PSP *,__int64),__int64)
0x180008ed3  mov     ebx, eax
0x180008ed5  mov     rcx, [rbp+hMem+8]; hMem
0x180008ed9  test    rcx, rcx
0x180008edc  jz      short loc_180008EEA
0x180008ede  cmp     dword ptr [rbp+hMem], r13d
0x180008ee2  jnz     short loc_180008EEA
0x180008ee4  call    cs:__imp_GlobalUnlock
0x180008eea  lea     rcx, [rbp+hMem]; LPSTGMEDIUM
0x180008eee  call    cs:__imp_ReleaseStgMedium
0x180008ef4  jmp     short loc_180008F0C
0x180008ef6  cmp     [rsi+14h], r13d
0x180008efa  jnz     short loc_180008F0C
0x180008efc  mov     r8, r14; __int64
0x180008eff  mov     rdx, r15; int (*)(struct _PSP *, __int64)
0x180008f02  mov     rcx, rdi; this
0x180008f05  call    ?_AddMountedVolumePage@CSecurityExtension@@AEAAJP6AHPEAU_PSP@@_J@Z1@Z; CSecurityExtension::_AddMountedVolumePage(int (*)(_PSP *,__int64),__int64)
0x180008f0a  mov     ebx, eax
0x180008f0c  lea     r11, [rsp+60h+var_s0]
0x180008f11  mov     eax, ebx
0x180008f13  mov     rbx, [r11+30h]
0x180008f17  mov     rsi, [r11+38h]
0x180008f1b  mov     rsp, r11
0x180008f1e  pop     r15
0x180008f20  pop     r14
0x180008f22  pop     r13
0x180008f24  pop     rdi
0x180008f25  pop     rbp
0x180008f26  retn
```
