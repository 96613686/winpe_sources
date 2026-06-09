# CRegInfo::EnumRegistry(ulong,ASPNETVER *,CASPNET_VER_LIST *,ASPNETVER *,ulong,int)

- ea: `0x18000c978`
- end: `0x18000cfc1`
- name: `?EnumRegistry@CRegInfo@@AEAAJKPEAVASPNETVER@@PEAVCASPNET_VER_LIST@@0KH@Z`
- size: `1609`
- prototype: `__int64 __usercall@<rax>(CRegInfo *__hidden this@<rcx>, unsigned int@<edx>, struct ASPNETVER *@<r8>, struct CASPNET_VER_LIST *@<r9>, struct ASPNETVER *, unsigned int, int)`
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cfcc`
- `0x18000d158`
- `0x18000d180`
- `0x18000d1a8`
- `0x18000d1d4`

## callees

- `0x180002584`
- `0x180007824`
- `0x18000b1f8`
- `0x18000c5c0`
- `0x18000c66c`
- `0x18000c6c4`
- `0x18000c978`
- `0x18000d6c4`
- `0x18000d794`
- `0x18000d850`
- `0x18001c550`
- `0x18004d030`
- `0x18004d690`
- `0x18004d754`
- `0x18004e168`
- `0x18004e650`
- `0x18004f048`
- `0x18004f058`
- `0x18004f078`
- `0x18004f0d0`
- `0x18004f130`
- `0x18004f1c4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000ce70`
- `KERNEL32!lstrlenW` at `0x18000ce7f`
- `KERNEL32!lstrlenW` at `0x18000ce70`
- `KERNEL32!lstrlenW` at `0x18000ce7f`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000cbfa`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000cbfa`
- `ADVAPI32!RegCloseKey` at `0x18000ccd9`
- `ADVAPI32!RegCloseKey` at `0x18000cf20`
- `ADVAPI32!RegCloseKey` at `0x18000cf30`
- `ADVAPI32!RegCloseKey` at `0x18000ccd9`
- `ADVAPI32!RegCloseKey` at `0x18000cf20`
- `ADVAPI32!RegCloseKey` at `0x18000cf30`
- `ADVAPI32!RegEnumKeyExW` at `0x18000ca9e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000cd25`
- `ADVAPI32!RegEnumKeyExW` at `0x18000ca9e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000cd25`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ca48`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ca48`

## string_xrefs

- `0x18000cbc9`: `DllFullPath`
- `0x18000ce09`: `DllFullPath`
- `0x18000ce76`: `aspnet_filter.dll`
- `0x18000cee5`: `aspnet_filter.dll`
- `0x18000cf69`: `.wsdl,text/xml,.disco,text/xml,.xsd,text/xml,.wbmp,image/vnd.wap.wbmp,.png,image/png,.pnz,image/png,.smd,audio/x-smd,.smz,audio/x-smd,.smx,audio/x-smd,.mmf,application/x-smaf,.application,application/x-ms-application,.manifest,application/x-ms-manifest,.deploy,application/octet-stream,`

## pseudocode

```c
__int64 __fastcall CRegInfo::EnumRegistry(
        CRegInfo *this,
        unsigned int a2,
        struct ASPNETVER *a3,
        struct CASPNET_VER_LIST *a4,
        struct ASPNETVER *a5,
        unsigned int lpReserved,
        int a7)
{
  int v8; // r15d
  unsigned int RegValue; // ebx
  int v11; // r12d
  wchar_t *v12; // r13
  unsigned __int16 *v13; // rsi
  unsigned int v14; // r14d
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int v17; // esi
  int v18; // r14d
  int v19; // eax
  unsigned int v20; // eax
  unsigned __int16 *v21; // rax
  unsigned int v22; // esi
  unsigned int v23; // eax
  void *v24; // r14
  HKEY v25; // rcx
  HKEY v26; // rcx
  const WCHAR *v27; // rcx
  int v28; // ebx
  unsigned __int64 v29; // r14
  unsigned __int16 *v30; // rax
  int v32; // [rsp+40h] [rbp-C0h]
  HKEY v33; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v36; // [rsp+60h] [rbp-A0h]
  wchar_t *String1; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v40; // [rsp+7Ch] [rbp-84h]
  _DWORD v41[6]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v42[24]; // [rsp+98h] [rbp-68h] BYREF
  struct ASPNETVER *v43; // [rsp+B0h] [rbp-50h]
  ASPNETVER *v44; // [rsp+B8h] [rbp-48h]
  CASPNET_VER_LIST *v45; // [rsp+C0h] [rbp-40h]
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v47[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v48[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v8 = 0;
  v44 = a5;
  v45 = a4;
  RegValue = 0;
  v43 = a3;
  v40 = a2;
  ASPNETVER::ASPNETVER((ASPNETVER *)v42);
  ASPNETVER::ASPNETVER((ASPNETVER *)v41);
  hKey = 0;
  v33 = 0;
  v11 = a2 & 1;
  String1 = 0;
  lpMem = 0;
  v12 = 0;
  v32 = (a2 >> 2) & 1;
  v13 = 0;
  if ( (a2 & 8) != 0 || (a2 & 1) != 0 )
    v8 = 1;
  v14 = lpReserved;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, lpReserved | 0x20019, &hKey);
  if ( v15 == 3 )
    goto LABEL_68;
  if ( v15 )
  {
    RegValue = (unsigned __int16)v15 | 0x80070000;
    if ( v15 <= 0 )
      RegValue = v15;
    goto LABEL_68;
  }
  v36 = 0;
  cchName = 259;
  v16 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
  if ( v16 == 259 )
  {
LABEL_50:
    if ( !v8 || (ASPNETVER::Init((CRegInfo *)((char *)this + 136), (struct ASPNETVER *)v42), *((_DWORD *)this + 38)) )
    {
      if ( v11 )
      {
        RegValue = CRegInfo::OpenVersionKey((struct ASPNETVER *)v42, v47, 0x104u, &v33, 0);
        if ( !RegValue )
        {
          v13 = 0;
          RegValue = CRegInfo::ReadRegValue(v33, v47, L"DefaultDoc", (unsigned __int16 **)this + 8, 0);
          if ( !RegValue )
          {
            RegValue = CRegInfo::ReadRegValue(v33, v47, L"Mimemap", (unsigned __int16 **)this + 9, 0);
            if ( !RegValue )
            {
              v25 = v33;
              *((_QWORD *)this + 1) = *((_QWORD *)this + 8);
              *((_QWORD *)this + 2) = *((_QWORD *)this + 9);
              RegValue = CRegInfo::ReadRegValue(v25, v47, L"DllFullPath", (unsigned __int16 **)this + 10, 0);
              if ( !RegValue )
              {
                v26 = v33;
                *((_QWORD *)this + 3) = *((_QWORD *)this + 10);
                RegValue = CRegInfo::ReadRegValue(v26, v47, L"Path", (unsigned __int16 **)this + 12, 0);
                if ( !RegValue )
                {
                  v27 = (const WCHAR *)*((_QWORD *)this + 12);
                  *((_QWORD *)this + 5) = v27;
                  v28 = lstrlenW(v27);
                  v29 = v28 + lstrlenW(L"aspnet_filter.dll") + 2;
                  v30 = (unsigned __int16 *)MemAlloc(saturated_mul(v29, 2u));
                  *((_QWORD *)this + 11) = v30;
                  if ( v30 )
                  {
                    RegValue = StringCchCopyW(v30, v29, *((const unsigned __int16 **)this + 5));
                    if ( !RegValue )
                    {
                      RegValue = StringCchCatW(*((unsigned __int16 **)this + 11), v29, L"\\");
                      if ( !RegValue )
                      {
                        RegValue = StringCchCatW(*((unsigned __int16 **)this + 11), v29, L"aspnet_filter.dll");
                        if ( !RegValue )
                        {
                          *((_QWORD *)this + 4) = *((_QWORD *)this + 11);
                          *((_QWORD *)this + 7) = *((_QWORD *)this + 5);
                          CRegInfo::ReadHighestVersionInstallPath32(this, (struct ASPNETVER *)v42);
                        }
                      }
                    }
                  }
                  else
                  {
LABEL_63:
                    RegValue = -2147024882;
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      RegValue = -2147023728;
    }
    goto LABEL_68;
  }
  v17 = v32;
  while ( !v16 )
  {
    if ( ASPNETVER::Init((ASPNETVER *)v41, Name) )
    {
      RegValue = CRegInfo::DetectMissingDll((struct ASPNETVER *)v41, &v39, v14);
      if ( !RegValue )
      {
        v18 = v39;
        if ( ((v40 & 2) == 0 || !v39) && (!v43 || !(unsigned int)ASPNETVER::operator==(v41, v43)) )
        {
          if ( !(unsigned int)IsVista() )
            goto LABEL_22;
          v19 = v41[0];
          if ( v41[0] == 2 )
          {
            if ( !(unsigned int)CRegInfo::CheckIIS7ASPNETKey(this, lpReserved) )
            {
LABEL_22:
              v19 = v41[0];
              goto LABEL_23;
            }
          }
          else
          {
LABEL_23:
            if ( !a7 || v19 != 2 )
            {
              if ( v8 && (unsigned int)ASPNETVER::operator>(v41, v42) )
                ASPNETVER::Init((ASPNETVER *)v42, (struct ASPNETVER *)v41);
              if ( !v11 && !v17 )
                goto LABEL_42;
              RegValue = CRegInfo::OpenVersionKey((struct ASPNETVER *)v41, v48, 0x104u, &v33, lpReserved);
              if ( RegValue )
                goto LABEL_55;
              v20 = CRegInfo::ReadRegValue(v33, v48, L"DllFullPath", &String1, 0);
              v12 = String1;
              RegValue = v20;
              if ( !v20 )
              {
                if ( v11 && _wcsicmp(String1, &Names::s_wszIsapiFullPath) )
                {
                  v21 = DupStr(v12);
                  v13 = v21;
                  if ( !v21 )
                    goto LABEL_63;
                  RegValue = CImplPtrAry::Append((CRegInfo *)((char *)this + 120), v21);
                  if ( RegValue )
                    goto LABEL_68;
                }
                if ( v32 )
                {
                  v22 = v18 != 0 ? 4 : 2;
                  if ( v44 && (unsigned int)ASPNETVER::Equal(v44, Name) )
                    v22 |= 1u;
                  v23 = CRegInfo::ReadRegValue(v33, Name, L"Path", (unsigned __int16 **)&lpMem, 0);
                  v24 = lpMem;
                  RegValue = v23;
                  if ( !v23 )
                    RegValue = CASPNET_VER_LIST::Add(v45, Name, v22, v12, (const unsigned __int16 *)lpMem);
                }
                else
                {
                  v24 = lpMem;
                }
                v17 = v32;
              }
              else
              {
LABEL_42:
                v24 = lpMem;
              }
              MemFree(v12);
              v12 = 0;
              String1 = 0;
              MemFree(v24);
              lpMem = 0;
              if ( v33 )
              {
                RegCloseKey(v33);
                v33 = 0;
              }
            }
          }
        }
        v14 = lpReserved;
        goto LABEL_48;
      }
      RegValue = 0;
    }
LABEL_48:
    ++v36;
    cchName = 259;
    v16 = RegEnumKeyExW(hKey, v36, Name, &cchName, 0, 0, 0, 0);
    if ( v16 == 259 )
    {
      v13 = 0;
      goto LABEL_50;
    }
  }
  RegValue = (unsigned __int16)v16 | 0x80070000;
  if ( v16 <= 0 )
    RegValue = v16;
LABEL_55:
  v13 = 0;
LABEL_68:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v33 )
    RegCloseKey(v33);
  MemFree(v12);
  MemFree(v13);
  MemFree(0);
  if ( RegValue && v11 )
  {
    CRegInfo::CleanupHighestVersionInfo(this);
    *((_QWORD *)this + 1) = L"Default.aspx";
    *((_QWORD *)this + 2) = L".wsdl,text/xml,.disco,text/xml,.xsd,text/xml,.wbmp,image/vnd.wap.wbmp,.png,image/png,.pnz,im"
                             "age/png,.smd,audio/x-smd,.smz,audio/x-smd,.smx,audio/x-smd,.mmf,application/x-smaf,.applica"
                             "tion,application/x-ms-application,.manifest,application/x-ms-manifest,.deploy,application/octet-stream,";
    *((_QWORD *)this + 3) = &Names::s_wszIsapiFullPath;
    *((_QWORD *)this + 4) = &Names::s_wszFilterFullPath;
    *((_QWORD *)this + 5) = &Names::s_wszInstallDirectory;
  }
  return RegValue;
}

```

## disassembly

```asm
0x18000c978  mov     [rsp-8+arg_8], rbx
0x18000c97d  push    rbp
0x18000c97e  push    rsi
0x18000c97f  push    rdi
0x18000c980  push    r12
0x18000c982  push    r13
0x18000c984  push    r14
0x18000c986  push    r15
0x18000c988  lea     rbp, [rsp-610h]
0x18000c990  sub     rsp, 710h
0x18000c997  mov     rax, cs:__security_cookie
0x18000c99e  xor     rax, rsp
0x18000c9a1  mov     [rbp+640h+var_40], rax
0x18000c9a8  mov     rax, [rbp+640h+arg_20]
0x18000c9af  mov     rdi, rcx
0x18000c9b2  xor     r15d, r15d
0x18000c9b5  mov     [rbp+640h+var_688], rax
0x18000c9b9  lea     rcx, [rbp+640h+var_6A8]; this
0x18000c9bd  mov     [rbp+640h+var_680], r9
0x18000c9c1  mov     ebx, r15d
0x18000c9c4  mov     [rbp+640h+var_690], r8
0x18000c9c8  mov     r14d, edx
0x18000c9cb  mov     [rsp+740h+var_6C4], edx
0x18000c9cf  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x18000c9d4  lea     rcx, [rbp+640h+var_6C0]; this
0x18000c9d8  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x18000c9dd  mov     eax, r14d
0x18000c9e0  mov     [rsp+740h+hKey], r15
0x18000c9e5  shr     eax, 2
0x18000c9e8  mov     r12d, r14d
0x18000c9eb  and     eax, 1
0x18000c9ee  mov     [rsp+740h+var_6F8], r15
0x18000c9f3  and     r12d, 1
0x18000c9f7  mov     [rsp+740h+String1], r15
0x18000c9fc  mov     [rsp+740h+lpMem], r15
0x18000ca01  mov     r13d, r15d
0x18000ca04  mov     [rsp+740h+var_700], eax
0x18000ca08  mov     esi, r15d
0x18000ca0b  test    r14b, 8
0x18000ca0f  jnz     short loc_18000CA16
0x18000ca11  test    r12d, r12d
0x18000ca14  jz      short loc_18000CA1C
0x18000ca16  mov     r15d, 1
0x18000ca1c  mov     r14d, dword ptr [rbp+640h+lpReserved]
0x18000ca23  lea     rax, [rsp+740h+hKey]
0x18000ca28  mov     r9d, r14d
0x18000ca2b  mov     [rsp+740h+phkResult], rax; phkResult
0x18000ca30  or      r9d, 20019h; samDesired
0x18000ca37  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18000ca3e  xor     r8d, r8d; ulOptions
0x18000ca41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ca48  call    cs:__imp_RegOpenKeyExW
0x18000ca4e  cmp     eax, 3
0x18000ca51  jz      loc_18000CF16
0x18000ca57  test    eax, eax
0x18000ca59  jz      short loc_18000CA6E
0x18000ca5b  movzx   ebx, ax
0x18000ca5e  or      ebx, 80070000h
0x18000ca64  test    eax, eax
0x18000ca66  cmovle  ebx, eax
0x18000ca69  jmp     loc_18000CF16
0x18000ca6e  mov     rcx, [rsp+740h+hKey]; hKey
0x18000ca73  lea     r9, [rsp+740h+cchName]; lpcchName
0x18000ca78  mov     [rsp+740h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18000ca7d  lea     r8, [rbp+640h+Name]; lpName
0x18000ca81  mov     [rsp+740h+lpcchClass], rsi; lpcchClass
0x18000ca86  xor     edx, edx; dwIndex
0x18000ca88  mov     [rsp+740h+lpClass], rsi; lpClass
0x18000ca8d  mov     [rsp+740h+phkResult], rsi; lpReserved
0x18000ca92  mov     [rsp+740h+var_6E0], esi
0x18000ca96  mov     [rsp+740h+cchName], 103h
0x18000ca9e  call    cs:__imp_RegEnumKeyExW
0x18000caa4  cmp     eax, 103h
0x18000caa9  jz      loc_18000CD38
0x18000caaf  mov     esi, [rsp+740h+var_700]
0x18000cab3  test    eax, eax
0x18000cab5  jnz     loc_18000CD5F
0x18000cabb  lea     rdx, [rbp+640h+Name]; unsigned __int16 *
0x18000cabf  lea     rcx, [rbp+640h+var_6C0]; this
0x18000cac3  call    ?Init@ASPNETVER@@QEAAHPEBG@Z; ASPNETVER::Init(ushort const *)
0x18000cac8  test    eax, eax
0x18000caca  jz      loc_18000CCEB
0x18000cad0  mov     r8d, r14d; unsigned int
0x18000cad3  lea     rdx, [rsp+740h+var_6C8]; int *
0x18000cad8  lea     rcx, [rbp+640h+var_6C0]; this
0x18000cadc  call    ?DetectMissingDll@CRegInfo@@CAJPEAVASPNETVER@@PEAHK@Z; CRegInfo::DetectMissingDll(ASPNETVER *,int *,ulong)
0x18000cae1  mov     ebx, eax
0x18000cae3  test    eax, eax
0x18000cae5  jz      short loc_18000CAEE
0x18000cae7  xor     ebx, ebx
0x18000cae9  jmp     loc_18000CCEB
0x18000caee  test    byte ptr [rsp+740h+var_6C4], 2
0x18000caf3  mov     r14d, [rsp+740h+var_6C8]
0x18000caf8  jz      short loc_18000CB03
0x18000cafa  test    r14d, r14d
0x18000cafd  jnz     loc_18000CCE4
0x18000cb03  mov     rax, [rbp+640h+var_690]
0x18000cb07  test    rax, rax
0x18000cb0a  jz      short loc_18000CB20
0x18000cb0c  mov     rdx, rax
0x18000cb0f  lea     rcx, [rbp+640h+var_6C0]
0x18000cb13  call    ??8ASPNETVER@@QEAAHAEAV0@@Z; ASPNETVER::operator==(ASPNETVER &)
0x18000cb18  test    eax, eax
0x18000cb1a  jnz     loc_18000CCE4
0x18000cb20  call    ?IsVista@@YAHXZ; IsVista(void)
0x18000cb25  test    eax, eax
0x18000cb27  jz      short loc_18000CB47
0x18000cb29  mov     eax, [rbp+640h+var_6C0]
0x18000cb2c  cmp     eax, 2
0x18000cb2f  jnz     short loc_18000CB4A
0x18000cb31  mov     edx, dword ptr [rbp+640h+lpReserved]; unsigned int
0x18000cb37  mov     rcx, rdi; this
0x18000cb3a  call    ?CheckIIS7ASPNETKey@CRegInfo@@AEAAJK@Z; CRegInfo::CheckIIS7ASPNETKey(ulong)
0x18000cb3f  test    eax, eax
0x18000cb41  jnz     loc_18000CCE4
0x18000cb47  mov     eax, [rbp+640h+var_6C0]
0x18000cb4a  cmp     [rbp+640h+arg_30], 0
0x18000cb51  jz      short loc_18000CB5C
0x18000cb53  cmp     eax, 2
0x18000cb56  jz      loc_18000CCE4
0x18000cb5c  test    r15d, r15d
0x18000cb5f  jz      short loc_18000CB7F
0x18000cb61  lea     rdx, [rbp+640h+var_6A8]
0x18000cb65  lea     rcx, [rbp+640h+var_6C0]
0x18000cb69  call    ??OASPNETVER@@QEAAHAEAV0@@Z; ASPNETVER::operator>(ASPNETVER &)
0x18000cb6e  test    eax, eax
0x18000cb70  jz      short loc_18000CB7F
0x18000cb72  lea     rdx, [rbp+640h+var_6C0]; struct ASPNETVER *
0x18000cb76  lea     rcx, [rbp+640h+var_6A8]; this
0x18000cb7a  call    ?Init@ASPNETVER@@QEAAHPEAV1@@Z; ASPNETVER::Init(ASPNETVER *)
0x18000cb7f  test    r12d, r12d
0x18000cb82  jnz     short loc_18000CB8C
0x18000cb84  test    esi, esi
0x18000cb86  jz      loc_18000CCA2
0x18000cb8c  mov     eax, dword ptr [rbp+640h+lpReserved]
0x18000cb92  lea     r9, [rsp+740h+var_6F8]; HKEY *
0x18000cb97  mov     r8d, 104h; unsigned __int64
0x18000cb9d  mov     dword ptr [rsp+740h+phkResult], eax; int
0x18000cba1  lea     rdx, [rbp+640h+var_250]; unsigned __int16 *
0x18000cba8  lea     rcx, [rbp+640h+var_6C0]; struct ASPNETVER *
0x18000cbac  call    ?OpenVersionKey@CRegInfo@@SAJPEAVASPNETVER@@QEAG_KPEAPEAUHKEY__@@K@Z; CRegInfo::OpenVersionKey(ASPNETVER *,ushort * const,unsigned __int64,HKEY__ * *,ulong)
0x18000cbb1  mov     ebx, eax
0x18000cbb3  test    eax, eax
0x18000cbb5  jnz     loc_18000CD6D
0x18000cbbb  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000cbc0  lea     r9, [rsp+740h+String1]; unsigned __int16 **
0x18000cbc5  and     dword ptr [rsp+740h+phkResult], eax
0x18000cbc9  lea     r8, aDllfullpath; "DllFullPath"
0x18000cbd0  lea     rdx, [rbp+640h+var_250]; unsigned __int16 *
0x18000cbd7  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000cbdc  mov     r13, [rsp+740h+String1]
0x18000cbe1  mov     ebx, eax
0x18000cbe3  test    eax, eax
0x18000cbe5  jnz     loc_18000CCA2
0x18000cbeb  test    r12d, r12d
0x18000cbee  jz      short loc_18000CC2E
0x18000cbf0  lea     rdx, ?s_wszIsapiFullPath@Names@@0PAGA; String2
0x18000cbf7  mov     rcx, r13; String1
0x18000cbfa  call    cs:__imp__wcsicmp
0x18000cc00  test    eax, eax
0x18000cc02  jz      short loc_18000CC2E
0x18000cc04  mov     rcx, r13; Src
0x18000cc07  call    ?DupStr@@YAPEAGPEBG@Z; DupStr(ushort const *)
0x18000cc0c  mov     rsi, rax
0x18000cc0f  test    rax, rax
0x18000cc12  jz      loc_18000CEAC
0x18000cc18  lea     rcx, [rdi+78h]; this
0x18000cc1c  mov     rdx, rax; void *
0x18000cc1f  call    ?Append@CImplPtrAry@@IEAAJPEAX@Z; CImplPtrAry::Append(void *)
0x18000cc24  mov     ebx, eax
0x18000cc26  test    eax, eax
0x18000cc28  jnz     loc_18000CF16
0x18000cc2e  cmp     [rsp+740h+var_700], 0
0x18000cc33  jz      short loc_18000CCA9
0x18000cc35  mov     rax, [rbp+640h+var_688]
0x18000cc39  neg     r14d
0x18000cc3c  sbb     esi, esi
0x18000cc3e  and     esi, 2
0x18000cc41  add     esi, 2
0x18000cc44  test    rax, rax
0x18000cc47  jz      short loc_18000CC5C
0x18000cc49  lea     rdx, [rbp+640h+Name]; unsigned __int16 *
0x18000cc4d  mov     rcx, rax; this
0x18000cc50  call    ?Equal@ASPNETVER@@QEAAHPEBG@Z; ASPNETVER::Equal(ushort const *)
0x18000cc55  test    eax, eax
0x18000cc57  jz      short loc_18000CC5C
0x18000cc59  or      esi, 1
0x18000cc5c  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000cc61  lea     r9, [rsp+740h+lpMem]; unsigned __int16 **
0x18000cc66  and     dword ptr [rsp+740h+phkResult], 0
0x18000cc6b  lea     r8, aPath; "Path"
0x18000cc72  lea     rdx, [rbp+640h+Name]; unsigned __int16 *
0x18000cc76  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000cc7b  mov     r14, [rsp+740h+lpMem]
0x18000cc80  mov     ebx, eax
0x18000cc82  test    eax, eax
0x18000cc84  jnz     short loc_18000CCAE
0x18000cc86  mov     rcx, [rbp+640h+var_680]; this
0x18000cc8a  lea     rdx, [rbp+640h+Name]; unsigned __int16 *
0x18000cc8e  mov     r9, r13; unsigned __int16 *
0x18000cc91  mov     [rsp+740h+phkResult], r14; unsigned __int16 *
0x18000cc96  mov     r8d, esi; unsigned int
0x18000cc99  call    ?Add@CASPNET_VER_LIST@@QEAAJPEBGK00@Z; CASPNET_VER_LIST::Add(ushort const *,ulong,ushort const *,ushort const *)
0x18000cc9e  mov     ebx, eax
0x18000cca0  jmp     short loc_18000CCAE
0x18000cca2  mov     r14, [rsp+740h+lpMem]
0x18000cca7  jmp     short loc_18000CCB2
0x18000cca9  mov     r14, [rsp+740h+lpMem]
0x18000ccae  mov     esi, [rsp+740h+var_700]
0x18000ccb2  mov     rcx, r13; lpMem
0x18000ccb5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000ccba  xor     r13d, r13d
0x18000ccbd  mov     rcx, r14; lpMem
0x18000ccc0  mov     [rsp+740h+String1], r13
0x18000ccc5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000ccca  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000cccf  and     [rsp+740h+lpMem], r13
0x18000ccd4  test    rcx, rcx
0x18000ccd7  jz      short loc_18000CCE4
0x18000ccd9  call    cs:__imp_RegCloseKey
0x18000ccdf  and     [rsp+740h+var_6F8], r13
0x18000cce4  mov     r14d, dword ptr [rbp+640h+lpReserved]
0x18000cceb  mov     eax, [rsp+740h+var_6E0]
0x18000ccef  lea     r9, [rsp+740h+cchName]; lpcchName
0x18000ccf4  and     [rsp+740h+lpftLastWriteTime], 0
0x18000ccfa  lea     r8, [rbp+640h+Name]; lpName
0x18000ccfe  and     [rsp+740h+lpcchClass], 0
0x18000cd04  inc     eax
0x18000cd06  and     [rsp+740h+lpClass], 0
0x18000cd0c  mov     edx, eax; dwIndex
0x18000cd0e  mov     rcx, [rsp+740h+hKey]; hKey
0x18000cd13  and     [rsp+740h+phkResult], 0
0x18000cd19  mov     [rsp+740h+var_6E0], eax
0x18000cd1d  mov     [rsp+740h+cchName], 103h
0x18000cd25  call    cs:__imp_RegEnumKeyExW
0x18000cd2b  cmp     eax, 103h
0x18000cd30  jnz     loc_18000CAB3
0x18000cd36  xor     esi, esi
0x18000cd38  test    r15d, r15d
0x18000cd3b  jz      short loc_18000CD74
0x18000cd3d  lea     rcx, [rdi+88h]; this
0x18000cd44  lea     rdx, [rbp+640h+var_6A8]; struct ASPNETVER *
0x18000cd48  call    ?Init@ASPNETVER@@QEAAHPEAV1@@Z; ASPNETVER::Init(ASPNETVER *)
0x18000cd4d  cmp     [rdi+98h], esi
0x18000cd53  jnz     short loc_18000CD74
0x18000cd55  mov     ebx, 80070490h
0x18000cd5a  jmp     loc_18000CF16
0x18000cd5f  movzx   ebx, ax
0x18000cd62  or      ebx, 80070000h
0x18000cd68  test    eax, eax
0x18000cd6a  cmovle  ebx, eax
0x18000cd6d  xor     esi, esi
0x18000cd6f  jmp     loc_18000CF16
0x18000cd74  test    r12d, r12d
0x18000cd77  jz      loc_18000CF16
0x18000cd7d  lea     r9, [rsp+740h+var_6F8]; HKEY *
0x18000cd82  mov     dword ptr [rsp+740h+phkResult], esi; int
0x18000cd86  mov     r8d, 104h; unsigned __int64
0x18000cd8c  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x18000cd93  lea     rcx, [rbp+640h+var_6A8]; struct ASPNETVER *
0x18000cd97  call    ?OpenVersionKey@CRegInfo@@SAJPEAVASPNETVER@@QEAG_KPEAPEAUHKEY__@@K@Z; CRegInfo::OpenVersionKey(ASPNETVER *,ushort * const,unsigned __int64,HKEY__ * *,ulong)
0x18000cd9c  mov     ebx, eax
0x18000cd9e  test    eax, eax
0x18000cda0  jnz     loc_18000CF16
0x18000cda6  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000cdab  lea     r9, [rdi+40h]; unsigned __int16 **
0x18000cdaf  and     dword ptr [rsp+740h+phkResult], eax
0x18000cdb3  lea     r8, aDefaultdoc; "DefaultDoc"
0x18000cdba  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x18000cdc1  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000cdc6  xor     esi, esi
0x18000cdc8  mov     ebx, eax
0x18000cdca  test    eax, eax
0x18000cdcc  jnz     loc_18000CF16
0x18000cdd2  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000cdd7  lea     r9, [rdi+48h]; unsigned __int16 **
0x18000cddb  and     dword ptr [rsp+740h+phkResult], esi
0x18000cddf  lea     r8, aMimemap; "Mimemap"
0x18000cde6  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x18000cded  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000cdf2  mov     ebx, eax
0x18000cdf4  test    eax, eax
0x18000cdf6  jnz     loc_18000CF16
0x18000cdfc  mov     rax, [rdi+40h]
0x18000ce00  lea     r9, [rdi+50h]; unsigned __int16 **
0x18000ce04  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000ce09  lea     r8, aDllfullpath; "DllFullPath"
0x18000ce10  and     dword ptr [rsp+740h+phkResult], esi
0x18000ce14  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x18000ce1b  mov     [rdi+8], rax
0x18000ce1f  mov     rax, [rdi+48h]
0x18000ce23  mov     [rdi+10h], rax
0x18000ce27  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000ce2c  mov     ebx, eax
0x18000ce2e  test    eax, eax
0x18000ce30  jnz     loc_18000CF16
0x18000ce36  mov     rax, [rdi+50h]
0x18000ce3a  lea     r9, [rdi+60h]; unsigned __int16 **
0x18000ce3e  mov     rcx, [rsp+740h+var_6F8]; hKey
0x18000ce43  lea     r8, aPath; "Path"
  ... truncated ...
```
