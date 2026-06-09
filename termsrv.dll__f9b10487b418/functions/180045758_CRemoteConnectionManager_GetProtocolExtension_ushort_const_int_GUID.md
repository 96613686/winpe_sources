# CRemoteConnectionManager::GetProtocolExtension(ushort const *,int *,_GUID *)

- ea: `0x180045758`
- end: `0x1800459dd`
- name: `?GetProtocolExtension@CRemoteConnectionManager@@AEAAJPEBGPEAHPEAU_GUID@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *this, const unsigned __int16 *, int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004aeb0`

## callees

- `0x18000a210`
- `0x1800279a8`
- `0x180027a44`
- `0x180027b44`
- `0x180045758`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045892`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180045892`

## string_xrefs

- `0x180045986`: `CRemoteConnectionManager::GetProtocolExtension`
- `0x18004582d`: `oRegControl.OpenKey(WINSTATION_REG_NAME) failed: 0x%x in %s`
- `0x180045863`: `oRegProtocol.OpenKey(pszProtocolName) failed: 0x%x in %s`
- `0x180045877`: `LoadableProtocol_Object`
- `0x180045947`: `LoadableProtocol_Object`
- `0x1800458a5`: `StringToCLSID(pProtocolGuid) failed: 0x%x in %s`
- `0x1800458b9`: `WdDLL`
- `0x180045902`: `oRegWds.OpenKey(WD_REG_NAME) failed: 0x%x in %s`
- `0x180045936`: `oRegWdDll.OpenKey(pWdDll) failed: 0x%x in %s`
- `0x18004597c`: `oRegWds.OpenKey(WIN_WDDLL) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRemoteConnectionManager::GetProtocolExtension(
        CRemoteConnectionManager *this,
        const unsigned __int16 *a2,
        int *a3,
        struct _GUID *a4)
{
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  const OLECHAR *v10; // rcx
  HRESULT v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  const unsigned __int16 *v16; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v17; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v18; // [rsp+20h] [rbp-89h]
  const unsigned __int16 *v19; // [rsp+20h] [rbp-89h]
  unsigned __int16 *v20; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-69h] BYREF
  int v23; // [rsp+50h] [rbp-59h]
  __int64 v24; // [rsp+58h] [rbp-51h]
  int v25; // [rsp+60h] [rbp-49h]
  int v26; // [rsp+64h] [rbp-45h]
  _QWORD v27[2]; // [rsp+68h] [rbp-41h] BYREF
  int v28; // [rsp+78h] [rbp-31h]
  __int64 v29; // [rsp+80h] [rbp-29h]
  int v30; // [rsp+88h] [rbp-21h]
  int v31; // [rsp+8Ch] [rbp-1Dh]
  _QWORD v32[2]; // [rsp+90h] [rbp-19h] BYREF
  int v33; // [rsp+A0h] [rbp-9h]
  HKEY v34; // [rsp+A8h] [rbp-1h]
  int v35; // [rsp+B0h] [rbp+7h]
  int v36; // [rsp+B4h] [rbp+Bh]
  _QWORD v37[2]; // [rsp+B8h] [rbp+Fh] BYREF
  int v38; // [rsp+C8h] [rbp+1Fh]
  HKEY v39; // [rsp+D0h] [rbp+27h]
  int v40; // [rsp+D8h] [rbp+2Fh]
  int v41; // [rsp+DCh] [rbp+33h]
  unsigned int v42; // [rsp+110h] [rbp+67h] BYREF
  LPCOLESTR lpsz; // [rsp+120h] [rbp+77h] BYREF

  v7 = 0;
  v37[0] = &CRegistry::`vftable';
  v37[1] = 0;
  v38 = 0;
  v39 = 0;
  v40 = -1;
  v41 = -1;
  v22[0] = &CRegistry::`vftable';
  v22[1] = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = -1;
  lpsz = 0;
  v32[0] = &CRegistry::`vftable';
  v32[1] = 0;
  v33 = 0;
  v34 = 0;
  v35 = -1;
  v36 = -1;
  v27[0] = &CRegistry::`vftable';
  v27[1] = 0;
  v28 = 0;
  v29 = 0;
  v30 = -1;
  v31 = -1;
  v20 = 0;
  v21 = 0;
  *a3 = 0;
  v8 = CRegistry::OpenKey(
         (CRegistry *)v37,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0x20019u,
         v16);
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    else
      v7 = v8;
    _DbgPrintMessage(
      8,
      "oRegControl.OpenKey(WINSTATION_REG_NAME) failed: 0x%x in %s",
      v7,
      "CRemoteConnectionManager::GetProtocolExtension");
    goto LABEL_33;
  }
  v9 = CRegistry::OpenKey((CRegistry *)v22, v39, a2, 0x20019u, v17);
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    else
      v7 = v9;
    _DbgPrintMessage(
      8,
      "oRegProtocol.OpenKey(pszProtocolName) failed: 0x%x in %s",
      v7,
      "CRemoteConnectionManager::GetProtocolExtension");
    goto LABEL_33;
  }
  if ( !CRegistry::ReadRegString((CRegistry *)v22, L"LoadableProtocol_Object", (unsigned __int16 **)&lpsz, &v42) )
  {
    v10 = lpsz;
LABEL_13:
    v11 = CLSIDFromString(v10, a4);
    v7 = v11;
    if ( v11 >= 0 )
      *a3 = 1;
    else
      _DbgPrintMessage(
        8,
        "StringToCLSID(pProtocolGuid) failed: 0x%x in %s",
        (unsigned int)v11,
        "CRemoteConnectionManager::GetProtocolExtension");
    goto LABEL_33;
  }
  v12 = CRegistry::ReadRegString((CRegistry *)v22, L"WdDLL", &v20, &v42);
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    else
      v7 = v12;
    _DbgPrintMessage(
      8,
      "oRegWds.OpenKey(WIN_WDDLL) failed: 0x%x in %s",
      v7,
      "CRemoteConnectionManager::GetProtocolExtension");
  }
  else
  {
    v13 = CRegistry::OpenKey(
            (CRegistry *)v32,
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\Wds",
            0x20019u,
            v18);
    if ( v13 )
    {
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      else
        v7 = v13;
      _DbgPrintMessage(
        8,
        "oRegWds.OpenKey(WD_REG_NAME) failed: 0x%x in %s",
        v7,
        "CRemoteConnectionManager::GetProtocolExtension");
    }
    else
    {
      v14 = CRegistry::OpenKey((CRegistry *)v27, v34, v20, 0x20019u, v19);
      if ( !v14 )
      {
        if ( CRegistry::ReadRegString((CRegistry *)v27, L"LoadableProtocol_Object", &v21, &v42) )
          goto LABEL_33;
        v10 = v21;
        goto LABEL_13;
      }
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      else
        v7 = v14;
      _DbgPrintMessage(
        8,
        "oRegWdDll.OpenKey(pWdDll) failed: 0x%x in %s",
        v7,
        "CRemoteConnectionManager::GetProtocolExtension");
    }
  }
LABEL_33:
  CRegistry::~CRegistry((CRegistry *)v27);
  CRegistry::~CRegistry((CRegistry *)v32);
  CRegistry::~CRegistry((CRegistry *)v22);
  CRegistry::~CRegistry((CRegistry *)v37);
  return v7;
}

```

## disassembly

```asm
0x180045758  mov     [rsp-8+arg_8], rbx
0x18004575d  mov     [rsp-8+arg_18], rsi
0x180045762  push    rbp
0x180045763  push    rdi
0x180045764  push    r12
0x180045766  push    r14
0x180045768  push    r15
0x18004576a  lea     rbp, [rsp-37h]
0x18004576f  sub     rsp, 0E0h
0x180045776  mov     rsi, r9
0x180045779  mov     rdi, r8
0x18004577c  mov     r14, rdx
0x18004577f  xor     r15d, r15d
0x180045782  mov     ebx, r15d
0x180045785  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004578c  mov     [rbp+57h+var_48], rax
0x180045790  mov     [rbp+57h+var_40], r15
0x180045794  mov     [rbp+57h+var_38], r15d
0x180045798  mov     [rbp+57h+var_30], r15
0x18004579c  or      ecx, 0FFFFFFFFh
0x18004579f  mov     [rbp+57h+var_28], ecx
0x1800457a2  mov     [rbp+57h+var_24], ecx
0x1800457a5  mov     [rbp+57h+var_C0], rax
0x1800457a9  mov     [rbp+57h+var_B8], r15
0x1800457ad  mov     [rbp+57h+var_B0], r15d
0x1800457b1  mov     [rbp+57h+var_A8], r15
0x1800457b5  mov     [rbp+57h+var_A0], ecx
0x1800457b8  mov     [rbp+57h+var_9C], ecx
0x1800457bb  mov     [rbp+57h+lpsz], r15
0x1800457bf  mov     [rbp+57h+var_70], rax
0x1800457c3  mov     [rbp+57h+var_68], r15
0x1800457c7  mov     [rbp+57h+var_60], r15d
0x1800457cb  mov     [rbp+57h+var_58], r15
0x1800457cf  mov     [rbp+57h+var_50], ecx
0x1800457d2  mov     [rbp+57h+var_4C], ecx
0x1800457d5  mov     [rbp+57h+var_98], rax
0x1800457d9  mov     [rbp+57h+var_90], r15
0x1800457dd  mov     [rbp+57h+var_88], r15d
0x1800457e1  mov     [rbp+57h+var_80], r15
0x1800457e5  mov     [rbp+57h+var_78], ecx
0x1800457e8  mov     [rbp+57h+var_74], ecx
0x1800457eb  mov     [rbp+57h+var_D0], r15
0x1800457ef  mov     [rbp+57h+var_C8], r15
0x1800457f3  mov     [r8], r15d
0x1800457f6  mov     r9d, 20019h; unsigned int
0x1800457fc  lea     r8, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\Ter"...
0x180045803  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18004580a  lea     rcx, [rbp+57h+var_48]; this
0x18004580e  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180045813  mov     r12d, 80070000h
0x180045819  test    eax, eax
0x18004581b  jz      short loc_180045839
0x18004581d  jg      short loc_180045823
0x18004581f  mov     ebx, eax
0x180045821  jmp     short loc_180045829
0x180045823  movzx   ebx, ax
0x180045826  or      ebx, r12d
0x180045829  test    ebx, ebx
0x18004582b  jns     short loc_180045839
0x18004582d  lea     rdx, aOregcontrolOpe; "oRegControl.OpenKey(WINSTATION_REG_NAME"...
0x180045834  jmp     loc_180045983
0x180045839  mov     r9d, 20019h; unsigned int
0x18004583f  mov     r8, r14; unsigned __int16 *
0x180045842  mov     rdx, [rbp+57h+var_30]; HKEY
0x180045846  lea     rcx, [rbp+57h+var_C0]; this
0x18004584a  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004584f  test    eax, eax
0x180045851  jz      short loc_18004586F
0x180045853  jg      short loc_180045859
0x180045855  mov     ebx, eax
0x180045857  jmp     short loc_18004585F
0x180045859  movzx   ebx, ax
0x18004585c  or      ebx, r12d
0x18004585f  test    ebx, ebx
0x180045861  jns     short loc_18004586F
0x180045863  lea     rdx, aOregprotocolOp; "oRegProtocol.OpenKey(pszProtocolName) f"...
0x18004586a  jmp     loc_180045983
0x18004586f  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180045873  lea     r8, [rbp+57h+lpsz]; unsigned __int16 **
0x180045877  lea     rdx, aLoadableprotoc; "LoadableProtocol_Object"
0x18004587e  lea     rcx, [rbp+57h+var_C0]; this
0x180045882  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180045887  test    eax, eax
0x180045889  jnz     short loc_1800458B1
0x18004588b  mov     rcx, [rbp+57h+lpsz]; lpsz
0x18004588f  mov     rdx, rsi; pclsid
0x180045892  call    cs:__imp_CLSIDFromString
0x180045898  test    eax, eax
0x18004589a  mov     ebx, eax
0x18004589c  jns     loc_180045964
0x1800458a2  mov     r8d, eax
0x1800458a5  lea     rdx, aStringtoclsidP_0; "StringToCLSID(pProtocolGuid) failed: 0x"...
0x1800458ac  jmp     loc_180045986
0x1800458b1  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800458b5  lea     r8, [rbp+57h+var_D0]; unsigned __int16 **
0x1800458b9  lea     rdx, aWddll; "WdDLL"
0x1800458c0  lea     rcx, [rbp+57h+var_C0]; this
0x1800458c4  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x1800458c9  test    eax, eax
0x1800458cb  jnz     loc_18004596C
0x1800458d1  mov     r9d, 20019h; unsigned int
0x1800458d7  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Ter"...
0x1800458de  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800458e5  lea     rcx, [rbp+57h+var_70]; this
0x1800458e9  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800458ee  test    eax, eax
0x1800458f0  jz      short loc_18004590B
0x1800458f2  jg      short loc_1800458F8
0x1800458f4  mov     ebx, eax
0x1800458f6  jmp     short loc_1800458FE
0x1800458f8  movzx   ebx, ax
0x1800458fb  or      ebx, r12d
0x1800458fe  test    ebx, ebx
0x180045900  jns     short loc_18004590B
0x180045902  lea     rdx, aOregwdsOpenkey; "oRegWds.OpenKey(WD_REG_NAME) failed: 0x"...
0x180045909  jmp     short loc_180045983
0x18004590b  mov     r9d, 20019h; unsigned int
0x180045911  mov     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x180045915  mov     rdx, [rbp+57h+var_58]; HKEY
0x180045919  lea     rcx, [rbp+57h+var_98]; this
0x18004591d  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180045922  test    eax, eax
0x180045924  jz      short loc_18004593F
0x180045926  jg      short loc_18004592C
0x180045928  mov     ebx, eax
0x18004592a  jmp     short loc_180045932
0x18004592c  movzx   ebx, ax
0x18004592f  or      ebx, r12d
0x180045932  test    ebx, ebx
0x180045934  jns     short loc_18004593F
0x180045936  lea     rdx, aOregwddllOpenk; "oRegWdDll.OpenKey(pWdDll) failed: 0x%x "...
0x18004593d  jmp     short loc_180045983
0x18004593f  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180045943  lea     r8, [rbp+57h+var_C8]; unsigned __int16 **
0x180045947  lea     rdx, aLoadableprotoc; "LoadableProtocol_Object"
0x18004594e  lea     rcx, [rbp+57h+var_98]; this
0x180045952  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180045957  test    eax, eax
0x180045959  jnz     short loc_180045998
0x18004595b  mov     rcx, [rbp+57h+var_C8]
0x18004595f  jmp     loc_18004588F
0x180045964  mov     dword ptr [rdi], 1
0x18004596a  jmp     short loc_180045998
0x18004596c  jg      short loc_180045972
0x18004596e  mov     ebx, eax
0x180045970  jmp     short loc_180045978
0x180045972  movzx   ebx, ax
0x180045975  or      ebx, r12d
0x180045978  test    ebx, ebx
0x18004597a  jns     short loc_180045998
0x18004597c  lea     rdx, aOregwdsOpenkey_0; "oRegWds.OpenKey(WIN_WDDLL) failed: 0x%x"...
0x180045983  mov     r8d, ebx
0x180045986  lea     r9, aCremoteconnect_20; "CRemoteConnectionManager::GetProtocolEx"...
0x18004598d  mov     ecx, 8; int
0x180045992  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180045997  nop
0x180045998  lea     rcx, [rbp+57h+var_98]; this
0x18004599c  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800459a1  nop
0x1800459a2  lea     rcx, [rbp+57h+var_70]; this
0x1800459a6  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800459ab  nop
0x1800459ac  lea     rcx, [rbp+57h+var_C0]; this
0x1800459b0  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800459b5  nop
0x1800459b6  lea     rcx, [rbp+57h+var_48]; this
0x1800459ba  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800459bf  mov     eax, ebx
0x1800459c1  lea     r11, [rsp+100h+var_20]
0x1800459c9  mov     rbx, [r11+38h]
0x1800459cd  mov     rsi, [r11+48h]
0x1800459d1  mov     rsp, r11
0x1800459d4  pop     r15
0x1800459d6  pop     r14
0x1800459d8  pop     r12
0x1800459da  pop     rdi
0x1800459db  pop     rbp
0x1800459dc  retn
```
