# HrGetExtVCardPropList(IMailUser *,_ExtVCardProp * *)

- ea: `0x18006f348`
- end: `0x18006f6c9`
- name: `?HrGetExtVCardPropList@@YAJPEAUIMailUser@@PEAPEAU_ExtVCardProp@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(struct IMailUser *, struct _ExtVCardProp **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800712f4`
- `0x1800719e8`

## callees

- `0x1800045e4`
- `0x18001dcb8`
- `0x18002fe40`
- `0x18006f304`
- `0x18006f348`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18006f3c0`
- `ADVAPI32!RegOpenKeyExW` at `0x18006f487`
- `ADVAPI32!RegOpenKeyExW` at `0x18006f3c0`
- `ADVAPI32!RegOpenKeyExW` at `0x18006f487`
- `ADVAPI32!RegEnumValueW` at `0x18006f4e0`
- `ADVAPI32!RegEnumValueW` at `0x18006f4e0`
- `ADVAPI32!RegCloseKey` at `0x18006f668`
- `ADVAPI32!RegCloseKey` at `0x18006f686`
- `ADVAPI32!RegCloseKey` at `0x18006f668`
- `ADVAPI32!RegCloseKey` at `0x18006f686`
- `ADVAPI32!RegQueryValueExW` at `0x18006f564`
- `ADVAPI32!RegQueryValueExW` at `0x18006f564`
- `ADVAPI32!RegEnumKeyExW` at `0x18006f409`
- `ADVAPI32!RegEnumKeyExW` at `0x18006f409`
- `KERNEL32!LocalAlloc` at `0x18006f603`
- `KERNEL32!LocalAlloc` at `0x18006f603`
- `KERNEL32!LocalFree` at `0x18006f642`
- `KERNEL32!LocalFree` at `0x18006f642`
- `ole32!CLSIDFromString` at `0x18006f455`
- `ole32!CLSIDFromString` at `0x18006f455`

## pseudocode

```c
__int64 __fastcall HrGetExtVCardPropList(struct IMailUser *a1, struct _ExtVCardProp **a2)
{
  int v4; // ebx
  struct _ExtVCardProp *v5; // rdi
  DWORD i; // r15d
  DWORD v7; // esi
  LSTATUS v8; // eax
  __int64 v9; // rax
  void *v10; // rcx
  struct _ExtVCardProp *v11; // rbx
  char *v12; // rax
  unsigned int v13; // edx
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h]
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchValueName; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int128 *v23; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v25; // [rsp+88h] [rbp-78h]
  GUID pclsid; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _WORD v29[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  OLECHAR sz[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  hKey = 0;
  cchName = 0;
  v4 = -2147467259;
  if ( a2 )
  {
    *a2 = 0;
    v5 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WAB\\WAB4\\NamedVCardProps", 0, 0x20019u, &hKey) )
    {
      for ( i = 0; ; ++i )
      {
        cchName = 260;
        Name[0] = 0;
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        pclsid = 0;
        memset_0(sz, 0, 0x208u);
        StringCchCopyW(sz, 0x104u, Name);
        if ( CLSIDFromString(sz, &pclsid) >= 0 )
        {
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
          {
            Type = 0;
            v7 = 0;
            *(_DWORD *)Data = 0;
            cbData = 4;
LABEL_8:
            ValueName[0] = 0;
            cchValueName = 260;
            while ( !RegEnumValueW(phkResult, v7, ValueName, &cchValueName, 0, &Type, 0, 0) )
            {
              v23 = 0;
              v24 = 0;
              v25 = 0;
              pv = 0;
              v29[0] = 0;
              if ( Type == 4 )
              {
                cbData = 4;
                v8 = RegQueryValueExW(phkResult, ValueName, 0, &Type, Data, &cbData);
              }
              else
              {
                if ( Type != 1 )
                  goto LABEL_15;
                cbData = 260;
                v8 = RegQueryValueExW(phkResult, ValueName, 0, &Type, (LPBYTE)v29, &cbData);
              }
              if ( !v8 )
              {
LABEL_15:
                *(_QWORD *)&v24 = &pclsid;
                v9 = -1;
                do
                  ++v9;
                while ( v29[v9] );
                if ( v9 )
                {
                  DWORD2(v24) = 1;
                  v25 = v29;
                }
                else
                {
                  LODWORD(v25) = *(_DWORD *)Data;
                  DWORD2(v24) = 0;
                }
                v23 = &v24;
                if ( ((int (__fastcall *)(struct IMailUser *, __int64, __int128 **))a1->lpVtbl->GetIDsFromNames)(
                       a1,
                       1,
                       &v23) >= 0 )
                {
                  v10 = pv;
                  if ( *((_DWORD *)pv + 1) && *(_DWORD *)pv )
                  {
                    v11 = (struct _ExtVCardProp *)LocalAlloc(0x40u, 0x18u);
                    if ( v11 )
                    {
                      v12 = ConvertWtoA(ValueName);
                      *((_QWORD *)v11 + 1) = v12;
                      if ( v12 )
                      {
                        v13 = *((_DWORD *)pv + 1) & 0xFFFF001E;
                        *((_QWORD *)v11 + 2) = v5;
                        v5 = v11;
                        *(_DWORD *)v11 = v13 | 0x1E;
                      }
                      else
                      {
                        LocalFree(v11);
                      }
                    }
                    v10 = pv;
                  }
                  if ( v10 )
                    MAPIFreeBuffer(v10);
                }
                ++v7;
                goto LABEL_8;
              }
            }
          }
          if ( phkResult )
            RegCloseKey(phkResult);
        }
      }
      *a2 = v5;
      v4 = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v4 < 0 && v5 )
      FreeExtVCardPropList(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006f348  mov     [rsp-8+arg_10], rbx
0x18006f34d  push    rbp
0x18006f34e  push    rsi
0x18006f34f  push    rdi
0x18006f350  push    r12
0x18006f352  push    r13
0x18006f354  push    r14
0x18006f356  push    r15
0x18006f358  lea     rbp, [rsp-7F0h]
0x18006f360  sub     rsp, 8F0h
0x18006f367  mov     rax, cs:__security_cookie
0x18006f36e  xor     rax, rsp
0x18006f371  mov     [rbp+820h+var_40], rax
0x18006f378  xor     r13d, r13d
0x18006f37b  mov     r14, rdx
0x18006f37e  mov     [rsp+920h+hKey], r13
0x18006f383  mov     r12, rcx
0x18006f386  mov     [rsp+920h+cchName], r13d
0x18006f38b  mov     ebx, 80004005h
0x18006f390  test    rdx, rdx
0x18006f393  jz      loc_18006F69D
0x18006f399  mov     [rdx], r13
0x18006f39c  lea     rax, [rsp+920h+hKey]
0x18006f3a1  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\WAB\\WAB4\\NamedVC"...
0x18006f3a8  mov     [rsp+920h+phkResult], rax; phkResult
0x18006f3ad  mov     r9d, 20019h; samDesired
0x18006f3b3  xor     r8d, r8d; ulOptions
0x18006f3b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f3bd  mov     edi, r13d
0x18006f3c0  call    cs:__imp_RegOpenKeyExW
0x18006f3c6  test    eax, eax
0x18006f3c8  jnz     loc_18006F67C
0x18006f3ce  mov     r15d, r13d
0x18006f3d1  mov     rcx, [rsp+920h+hKey]; hKey
0x18006f3d6  lea     r9, [rsp+920h+cchName]; lpcchName
0x18006f3db  mov     [rsp+920h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18006f3e0  lea     r8, [rbp+820h+Name]; lpName
0x18006f3e7  mov     [rsp+920h+lpcchClass], r13; lpcchClass
0x18006f3ec  mov     edx, r15d; dwIndex
0x18006f3ef  mov     [rsp+920h+lpClass], r13; lpClass
0x18006f3f4  mov     [rsp+920h+phkResult], r13; lpReserved
0x18006f3f9  mov     [rsp+920h+cchName], 104h
0x18006f401  mov     [rbp+820h+Name], r13w
0x18006f409  call    cs:__imp_RegEnumKeyExW
0x18006f40f  test    eax, eax
0x18006f411  jnz     loc_18006F676
0x18006f417  xorps   xmm0, xmm0
0x18006f41a  lea     rcx, [rbp+820h+sz]; void *
0x18006f421  xor     edx, edx; Val
0x18006f423  mov     r8d, 208h; Size
0x18006f429  movups  xmmword ptr [rbp+820h+pclsid.Data1], xmm0
0x18006f42d  call    memset_0
0x18006f432  lea     r8, [rbp+820h+Name]; unsigned __int16 *
0x18006f439  mov     edx, 104h; unsigned __int64
0x18006f43e  lea     rcx, [rbp+820h+sz]; unsigned __int16 *
0x18006f445  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f44a  lea     rdx, [rbp+820h+pclsid]; pclsid
0x18006f44e  lea     rcx, [rbp+820h+sz]; lpsz
0x18006f455  call    cs:__imp_CLSIDFromString
0x18006f45b  test    eax, eax
0x18006f45d  js      loc_18006F66E
0x18006f463  mov     rcx, [rsp+920h+hKey]; hKey
0x18006f468  lea     rax, [rsp+920h+var_8C0]
0x18006f46d  mov     r9d, 20019h; samDesired
0x18006f473  mov     [rsp+920h+phkResult], rax; phkResult
0x18006f478  xor     r8d, r8d; ulOptions
0x18006f47b  mov     [rsp+920h+var_8C0], r13
0x18006f480  lea     rdx, [rbp+820h+Name]; lpSubKey
0x18006f487  call    cs:__imp_RegOpenKeyExW
0x18006f48d  test    eax, eax
0x18006f48f  jnz     loc_18006F65E
0x18006f495  mov     [rsp+920h+Type], r13d
0x18006f49a  mov     esi, r13d
0x18006f49d  mov     dword ptr [rsp+920h+Data], r13d
0x18006f4a2  mov     [rsp+920h+cbData], 4
0x18006f4aa  mov     [rbp+820h+ValueName], r13w
0x18006f4af  mov     [rsp+920h+cchValueName], 104h
0x18006f4b7  mov     rcx, [rsp+920h+var_8C0]; hKey
0x18006f4bc  lea     rax, [rsp+920h+Type]
0x18006f4c1  mov     [rsp+920h+lpftLastWriteTime], r13; lpcbData
0x18006f4c6  lea     r9, [rsp+920h+cchValueName]; lpcchValueName
0x18006f4cb  mov     [rsp+920h+lpcchClass], r13; lpData
0x18006f4d0  lea     r8, [rbp+820h+ValueName]; lpValueName
0x18006f4d4  mov     [rsp+920h+lpClass], rax; lpType
0x18006f4d9  mov     edx, esi; dwIndex
0x18006f4db  mov     [rsp+920h+phkResult], r13; lpReserved
0x18006f4e0  call    cs:__imp_RegEnumValueW
0x18006f4e6  test    eax, eax
0x18006f4e8  jnz     loc_18006F65E
0x18006f4ee  xor     eax, eax
0x18006f4f0  mov     [rsp+920h+var_8B0], r13
0x18006f4f5  cmp     [rsp+920h+Type], 4
0x18006f4fa  xorps   xmm0, xmm0
0x18006f4fd  movups  [rsp+920h+var_8A8], xmm0
0x18006f502  mov     [rbp+820h+var_898], rax
0x18006f506  mov     [rsp+920h+pv], r13
0x18006f50b  mov     [rbp+820h+var_460], r13w
0x18006f513  jnz     short loc_18006F52E
0x18006f515  lea     rax, [rsp+920h+cbData]
0x18006f51a  mov     [rsp+920h+cbData], 4
0x18006f522  mov     [rsp+920h+lpClass], rax
0x18006f527  lea     rax, [rsp+920h+Data]
0x18006f52c  jmp     short loc_18006F54E
0x18006f52e  cmp     [rsp+920h+Type], 1
0x18006f533  jnz     short loc_18006F572
0x18006f535  lea     rax, [rsp+920h+cbData]
0x18006f53a  mov     [rsp+920h+cbData], 104h
0x18006f542  mov     [rsp+920h+lpClass], rax; lpcbData
0x18006f547  lea     rax, [rbp+820h+var_460]
0x18006f54e  mov     rcx, [rsp+920h+var_8C0]; hKey
0x18006f553  lea     r9, [rsp+920h+Type]; lpType
0x18006f558  xor     r8d, r8d; lpReserved
0x18006f55b  mov     [rsp+920h+phkResult], rax; lpData
0x18006f560  lea     rdx, [rbp+820h+ValueName]; lpValueName
0x18006f564  call    cs:__imp_RegQueryValueExW
0x18006f56a  test    eax, eax
0x18006f56c  jnz     loc_18006F4B7
0x18006f572  lea     rax, [rbp+820h+pclsid]
0x18006f576  mov     qword ptr [rsp+920h+var_8A8], rax
0x18006f57b  lea     rcx, [rbp+820h+var_460]
0x18006f582  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006f586  inc     rax
0x18006f589  cmp     [rcx+rax*2], r13w
0x18006f58e  jnz     short loc_18006F586
0x18006f590  test    rax, rax
0x18006f593  jz      short loc_18006F5A9
0x18006f595  lea     rax, [rbp+820h+var_460]
0x18006f59c  mov     dword ptr [rbp+820h+var_8A8+8], 1
0x18006f5a3  mov     [rbp+820h+var_898], rax
0x18006f5a7  jmp     short loc_18006F5B4
0x18006f5a9  mov     eax, dword ptr [rsp+920h+Data]
0x18006f5ad  mov     dword ptr [rbp+820h+var_898], eax
0x18006f5b0  mov     dword ptr [rbp+820h+var_8A8+8], r13d
0x18006f5b4  lea     rax, [rsp+920h+var_8A8]
0x18006f5b9  mov     r9d, 2
0x18006f5bf  mov     [rsp+920h+var_8B0], rax
0x18006f5c4  lea     rcx, [rsp+920h+pv]
0x18006f5c9  mov     rax, [r12]
0x18006f5cd  lea     r8, [rsp+920h+var_8B0]
0x18006f5d2  mov     [rsp+920h+phkResult], rcx
0x18006f5d7  mov     rcx, r12
0x18006f5da  lea     edx, [r9-1]
0x18006f5de  mov     rax, [rax+68h]
0x18006f5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f5e7  test    eax, eax
0x18006f5e9  js      short loc_18006F657
0x18006f5eb  mov     rcx, [rsp+920h+pv]
0x18006f5f0  cmp     [rcx+4], r13d
0x18006f5f4  jz      short loc_18006F64D
0x18006f5f6  cmp     [rcx], r13d
0x18006f5f9  jz      short loc_18006F64D
0x18006f5fb  mov     edx, 18h; uBytes
0x18006f600  lea     ecx, [rdx+28h]; uFlags
0x18006f603  call    cs:__imp_LocalAlloc
0x18006f609  mov     rbx, rax
0x18006f60c  test    rax, rax
0x18006f60f  jz      short loc_18006F648
0x18006f611  lea     rcx, [rbp+820h+ValueName]; lpWideCharStr
0x18006f615  call    ?ConvertWtoA@@YAPEADPEBG@Z; ConvertWtoA(ushort const *)
0x18006f61a  mov     [rbx+8], rax
0x18006f61e  test    rax, rax
0x18006f621  jz      short loc_18006F63F
0x18006f623  mov     rcx, [rsp+920h+pv]
0x18006f628  mov     edx, [rcx+4]
0x18006f62b  and     edx, 0FFFF001Eh
0x18006f631  mov     [rbx+10h], rdi
0x18006f635  or      edx, 1Eh
0x18006f638  mov     rdi, rbx
0x18006f63b  mov     [rbx], edx
0x18006f63d  jmp     short loc_18006F648
0x18006f63f  mov     rcx, rbx; hMem
0x18006f642  call    cs:__imp_LocalFree
0x18006f648  mov     rcx, [rsp+920h+pv]; pv
0x18006f64d  test    rcx, rcx
0x18006f650  jz      short loc_18006F657
0x18006f652  call    MAPIFreeBuffer
0x18006f657  inc     esi
0x18006f659  jmp     loc_18006F4AA
0x18006f65e  mov     rcx, [rsp+920h+var_8C0]; hKey
0x18006f663  test    rcx, rcx
0x18006f666  jz      short loc_18006F66E
0x18006f668  call    cs:__imp_RegCloseKey
0x18006f66e  inc     r15d
0x18006f671  jmp     loc_18006F3D1
0x18006f676  mov     [r14], rdi
0x18006f679  mov     ebx, r13d
0x18006f67c  mov     rcx, [rsp+920h+hKey]; hKey
0x18006f681  test    rcx, rcx
0x18006f684  jz      short loc_18006F68C
0x18006f686  call    cs:__imp_RegCloseKey
0x18006f68c  test    ebx, ebx
0x18006f68e  jns     short loc_18006F69D
0x18006f690  test    rdi, rdi
0x18006f693  jz      short loc_18006F69D
0x18006f695  mov     rcx, rdi; hMem
0x18006f698  call    ?FreeExtVCardPropList@@YAXPEAU_ExtVCardProp@@@Z; FreeExtVCardPropList(_ExtVCardProp *)
0x18006f69d  mov     eax, ebx
0x18006f69f  mov     rcx, [rbp+820h+var_40]
0x18006f6a6  xor     rcx, rsp; StackCookie
0x18006f6a9  call    __security_check_cookie
0x18006f6ae  mov     rbx, [rsp+920h+arg_10]
0x18006f6b6  add     rsp, 8F0h
0x18006f6bd  pop     r15
0x18006f6bf  pop     r14
0x18006f6c1  pop     r13
0x18006f6c3  pop     r12
0x18006f6c5  pop     rdi
0x18006f6c6  pop     rsi
0x18006f6c7  pop     rbp
0x18006f6c8  retn
```
