# GetInterfaceTextName

- ea: `0x14003d9b4`
- end: `0x14003dbac`
- name: `GetInterfaceTextName`
- size: `504`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003f2f0`

## callees

- `0x140001abc`
- `0x140001ac8`
- `0x14000acf4`
- `0x14000e674`
- `0x14003d9b4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14003da7d`
- `ADVAPI32!RegQueryValueExW` at `0x14003db34`
- `ADVAPI32!RegQueryValueExW` at `0x14003da7d`
- `ADVAPI32!RegQueryValueExW` at `0x14003db34`
- `msvcrt!wcscat_s` at `0x14003da98`
- `msvcrt!wcscat_s` at `0x14003da98`
- `ole32!CoTaskMemFree` at `0x14003db6c`
- `ole32!CoTaskMemFree` at `0x14003db6c`
- `ole32!StringFromCLSID` at `0x14003d9ff`
- `ole32!StringFromCLSID` at `0x14003d9ff`

## string_xrefs

- `0x14003daba`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_WORD *__fastcall GetInterfaceTextName(IID *rclsid)
{
  HRESULT v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rax
  _WORD *lpData; // rbx
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    memset(hKey, 0, 24);
    Type = 0;
    cbData = 0;
    lpData = operator new[](0x800u);
    lpsz = 0;
    v2 = StringFromCLSID(rclsid, &lpsz);
  }
  catch ( std::bad_alloc )
  {
    goto LABEL_22;
  }
  if ( v2 < 0 )
  {
    operator delete(lpData);
LABEL_22:
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return 0;
  }
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"Interface", 0x20019u)
    || (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], lpsz, 0x20019u)
    || (cbData = 2048, RegQueryValueExW(hKey[0], 0, 0, &Type, (LPBYTE)lpData, &cbData))
    || wcscat_s(lpData, 0x400u, L", ") )
  {
    *lpData = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID", 0x20019u)
    || (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], lpsz, 0x20019u) )
  {
    v3 = -1;
    do
LABEL_16:
      ++v3;
    while ( lpData[v3] );
    cbData = v3;
    if ( (unsigned int)v3 >= 2 )
    {
      lpData[(unsigned int)(v3 - 2)] = 0;
      cbData -= 2;
    }
    goto LABEL_19;
  }
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( lpData[v4] );
  cbData = 2 * (1024 - v4);
  if ( RegQueryValueExW(hKey[0], 0, 0, &Type, (LPBYTE)&lpData[(unsigned int)v4], &cbData) )
    goto LABEL_16;
LABEL_19:
  CoTaskMemFree(lpsz);
  if ( !*lpData )
  {
    operator delete(lpData);
    lpData = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return lpData;
}

```

## disassembly

```asm
0x14003d9b4  mov     rax, rsp
0x14003d9b7  mov     [rax+8], rbx
0x14003d9bb  push    rsi
0x14003d9bc  push    rdi
0x14003d9bd  push    r14
0x14003d9bf  sub     rsp, 50h
0x14003d9c3  mov     rdi, rcx
0x14003d9c6  xor     r14d, r14d
0x14003d9c9  mov     [rax-38h], r14
0x14003d9cd  mov     [rax-30h], r14
0x14003d9d1  mov     [rax-28h], r14
0x14003d9d5  mov     [rax+18h], r14d
0x14003d9d9  mov     [rax+10h], r14d
0x14003d9dd  mov     esi, 800h
0x14003d9e2  mov     ecx, esi; unsigned __int64
0x14003d9e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14003d9e9  mov     rbx, rax
0x14003d9ec  mov     [rsp+68h+lpsz], r14
0x14003d9f4  lea     rdx, [rsp+68h+lpsz]; lplpsz
0x14003d9fc  mov     rcx, rdi; rclsid
0x14003d9ff  call    cs:__imp_StringFromCLSID
0x14003da05  test    eax, eax
0x14003da07  jns     short loc_14003DA16
0x14003da09  mov     rcx, rbx; Block
0x14003da0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003da11  jmp     loc_14003DB92
0x14003da16  mov     edi, 20019h
0x14003da1b  mov     r9d, edi; unsigned int
0x14003da1e  lea     r8, aInterface; "Interface"
0x14003da25  mov     rdx, 0FFFFFFFF80000000h; hKey
0x14003da2c  lea     rcx, [rsp+68h+hKey]; this
0x14003da31  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14003da36  test    eax, eax
0x14003da38  jnz     short loc_14003DAA4
0x14003da3a  mov     r9d, edi; unsigned int
0x14003da3d  mov     r8, [rsp+68h+lpsz]; lpSubKey
0x14003da45  mov     rdx, [rsp+68h+hKey]; hKey
0x14003da4a  lea     rcx, [rsp+68h+hKey]; this
0x14003da4f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14003da54  test    eax, eax
0x14003da56  jnz     short loc_14003DAA4
0x14003da58  mov     [rsp+68h+cbData], esi
0x14003da5c  lea     rax, [rsp+68h+cbData]
0x14003da61  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14003da66  mov     [rsp+68h+lpData], rbx; lpData
0x14003da6b  lea     r9, [rsp+68h+Type]; lpType
0x14003da73  xor     r8d, r8d; lpReserved
0x14003da76  xor     edx, edx; lpValueName
0x14003da78  mov     rcx, [rsp+68h+hKey]; hKey
0x14003da7d  call    cs:__imp_RegQueryValueExW
0x14003da83  test    eax, eax
0x14003da85  jnz     short loc_14003DAA4
0x14003da87  lea     r8, Source; ", "
0x14003da8e  mov     esi, 400h
0x14003da93  mov     edx, esi; SizeInWords
0x14003da95  mov     rcx, rbx; Destination
0x14003da98  call    cs:__imp_wcscat_s
0x14003da9e  test    eax, eax
0x14003daa0  jz      short loc_14003DAAD
0x14003daa2  jmp     short loc_14003DAA9
0x14003daa4  mov     esi, 400h
0x14003daa9  mov     [rbx], r14w
0x14003daad  lea     rcx, [rsp+68h+hKey]; this
0x14003dab2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14003dab7  mov     r9d, edi; unsigned int
0x14003daba  lea     r8, aClsid; "CLSID"
0x14003dac1  mov     rdx, 0FFFFFFFF80000000h; hKey
0x14003dac8  lea     rcx, [rsp+68h+hKey]; this
0x14003dacd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14003dad2  test    eax, eax
0x14003dad4  jnz     short loc_14003DB40
0x14003dad6  mov     r9d, edi; unsigned int
0x14003dad9  mov     r8, [rsp+68h+lpsz]; lpSubKey
0x14003dae1  mov     rdx, [rsp+68h+hKey]; hKey
0x14003dae6  lea     rcx, [rsp+68h+hKey]; this
0x14003daeb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14003daf0  test    eax, eax
0x14003daf2  jnz     short loc_14003DB40
0x14003daf4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003daf8  mov     rax, rdi
0x14003dafb  inc     rax
0x14003dafe  cmp     [rbx+rax*2], r14w
0x14003db03  jnz     short loc_14003DAFB
0x14003db05  mov     eax, eax
0x14003db07  sub     esi, eax
0x14003db09  add     esi, esi
0x14003db0b  mov     [rsp+68h+cbData], esi
0x14003db0f  lea     rax, [rbx+rax*2]
0x14003db13  lea     rcx, [rsp+68h+cbData]
0x14003db18  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x14003db1d  mov     [rsp+68h+lpData], rax; lpData
0x14003db22  lea     r9, [rsp+68h+Type]; lpType
0x14003db2a  xor     r8d, r8d; lpReserved
0x14003db2d  xor     edx, edx; lpValueName
0x14003db2f  mov     rcx, [rsp+68h+hKey]; hKey
0x14003db34  call    cs:__imp_RegQueryValueExW
0x14003db3a  test    eax, eax
0x14003db3c  jz      short loc_14003DB64
0x14003db3e  jmp     short loc_14003DB44
0x14003db40  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003db44  inc     rdi
0x14003db47  cmp     [rbx+rdi*2], r14w
0x14003db4c  jnz     short loc_14003DB44
0x14003db4e  mov     [rsp+68h+cbData], edi
0x14003db52  cmp     edi, 2
0x14003db55  jb      short loc_14003DB64
0x14003db57  lea     eax, [rdi-2]
0x14003db5a  mov     [rbx+rax*2], r14w
0x14003db5f  add     [rsp+68h+cbData], 0FFFFFFFEh
0x14003db64  mov     rcx, [rsp+68h+lpsz]; pv
0x14003db6c  call    cs:__imp_CoTaskMemFree
0x14003db72  cmp     [rbx], r14w
0x14003db76  jnz     short loc_14003DB83
0x14003db78  mov     rcx, rbx; Block
0x14003db7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003db80  mov     rbx, r14
0x14003db83  lea     rcx, [rsp+68h+hKey]; this
0x14003db88  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14003db8d  mov     rax, rbx
0x14003db90  jmp     short loc_14003DB9E
0x14003db92  lea     rcx, [rsp+68h+hKey]; this
0x14003db97  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14003db9c  xor     eax, eax
0x14003db9e  mov     rbx, [rsp+68h+arg_0]
0x14003dba3  add     rsp, 50h
0x14003dba7  pop     r14
0x14003dba9  pop     rdi
0x14003dbaa  pop     rsi
0x14003dbab  retn
```
