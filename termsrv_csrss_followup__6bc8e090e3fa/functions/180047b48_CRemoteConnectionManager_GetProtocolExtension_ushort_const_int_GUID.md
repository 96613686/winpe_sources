# CRemoteConnectionManager::GetProtocolExtension(ushort const *,int *,_GUID *)

- ea: `0x180047b48`
- end: `0x180047dd4`
- name: `?GetProtocolExtension@CRemoteConnectionManager@@AEAAJPEBGPEAHPEAU_GUID@@@Z`
- size: `652`
- prototype: `int(CRemoteConnectionManager *__hidden this, const unsigned __int16 *, int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d4d0`

## callees

- `0x180009940`
- `0x180028dd8`
- `0x180028e88`
- `0x180028f88`
- `0x180047b48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047c82`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047c82`

## string_xrefs

- `0x180047d7c`: `CRemoteConnectionManager::GetProtocolExtension`
- `0x180047c1d`: `oRegControl.OpenKey(WINSTATION_REG_NAME) failed: 0x%x in %s`
- `0x180047c53`: `oRegProtocol.OpenKey(pszProtocolName) failed: 0x%x in %s`
- `0x180047c67`: `LoadableProtocol_Object`
- `0x180047d3d`: `LoadableProtocol_Object`
- `0x180047c9b`: `StringToCLSID(pProtocolGuid) failed: 0x%x in %s`
- `0x180047caf`: `WdDLL`
- `0x180047cf8`: `oRegWds.OpenKey(WD_REG_NAME) failed: 0x%x in %s`
- `0x180047d2c`: `oRegWdDll.OpenKey(pWdDll) failed: 0x%x in %s`
- `0x180047d72`: `oRegWds.OpenKey(WIN_WDDLL) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180047b48  mov     [rsp-8+arg_8], rbx
0x180047b4d  mov     [rsp-8+arg_18], rsi
0x180047b52  push    rbp
0x180047b53  push    rdi
0x180047b54  push    r12
0x180047b56  push    r14
0x180047b58  push    r15
0x180047b5a  lea     rbp, [rsp-37h]
0x180047b5f  sub     rsp, 0E0h
0x180047b66  mov     rsi, r9
0x180047b69  mov     rdi, r8
0x180047b6c  mov     r14, rdx
0x180047b6f  xor     r15d, r15d
0x180047b72  mov     ebx, r15d
0x180047b75  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180047b7c  mov     [rbp+57h+var_48], rax
0x180047b80  mov     [rbp+57h+var_40], r15
0x180047b84  mov     [rbp+57h+var_38], r15d
0x180047b88  mov     [rbp+57h+var_30], r15
0x180047b8c  or      ecx, 0FFFFFFFFh
0x180047b8f  mov     [rbp+57h+var_28], ecx
0x180047b92  mov     [rbp+57h+var_24], ecx
0x180047b95  mov     [rbp+57h+var_C0], rax
0x180047b99  mov     [rbp+57h+var_B8], r15
0x180047b9d  mov     [rbp+57h+var_B0], r15d
0x180047ba1  mov     [rbp+57h+var_A8], r15
0x180047ba5  mov     [rbp+57h+var_A0], ecx
0x180047ba8  mov     [rbp+57h+var_9C], ecx
0x180047bab  mov     [rbp+57h+lpsz], r15
0x180047baf  mov     [rbp+57h+var_70], rax
0x180047bb3  mov     [rbp+57h+var_68], r15
0x180047bb7  mov     [rbp+57h+var_60], r15d
0x180047bbb  mov     [rbp+57h+var_58], r15
0x180047bbf  mov     [rbp+57h+var_50], ecx
0x180047bc2  mov     [rbp+57h+var_4C], ecx
0x180047bc5  mov     [rbp+57h+var_98], rax
0x180047bc9  mov     [rbp+57h+var_90], r15
0x180047bcd  mov     [rbp+57h+var_88], r15d
0x180047bd1  mov     [rbp+57h+var_80], r15
0x180047bd5  mov     [rbp+57h+var_78], ecx
0x180047bd8  mov     [rbp+57h+var_74], ecx
0x180047bdb  mov     [rbp+57h+var_D0], r15
0x180047bdf  mov     [rbp+57h+var_C8], r15
0x180047be3  mov     [r8], r15d
0x180047be6  mov     r9d, 20019h; unsigned int
0x180047bec  lea     r8, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180047bf3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180047bfa  lea     rcx, [rbp+57h+var_48]; this
0x180047bfe  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180047c03  mov     r12d, 80070000h
0x180047c09  test    eax, eax
0x180047c0b  jz      short loc_180047C29
0x180047c0d  jg      short loc_180047C13
0x180047c0f  mov     ebx, eax
0x180047c11  jmp     short loc_180047C19
0x180047c13  movzx   ebx, ax
0x180047c16  or      ebx, r12d
0x180047c19  test    ebx, ebx
0x180047c1b  jns     short loc_180047C29
0x180047c1d  lea     rdx, aOregcontrolOpe; "oRegControl.OpenKey(WINSTATION_REG_NAME"...
0x180047c24  jmp     loc_180047D79
0x180047c29  mov     r9d, 20019h; unsigned int
0x180047c2f  mov     r8, r14; unsigned __int16 *
0x180047c32  mov     rdx, [rbp+57h+var_30]; HKEY
0x180047c36  lea     rcx, [rbp+57h+var_C0]; this
0x180047c3a  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180047c3f  test    eax, eax
0x180047c41  jz      short loc_180047C5F
0x180047c43  jg      short loc_180047C49
0x180047c45  mov     ebx, eax
0x180047c47  jmp     short loc_180047C4F
0x180047c49  movzx   ebx, ax
0x180047c4c  or      ebx, r12d
0x180047c4f  test    ebx, ebx
0x180047c51  jns     short loc_180047C5F
0x180047c53  lea     rdx, aOregprotocolOp; "oRegProtocol.OpenKey(pszProtocolName) f"...
0x180047c5a  jmp     loc_180047D79
0x180047c5f  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180047c63  lea     r8, [rbp+57h+lpsz]; unsigned __int16 **
0x180047c67  lea     rdx, aLoadableprotoc; "LoadableProtocol_Object"
0x180047c6e  lea     rcx, [rbp+57h+var_C0]; this
0x180047c72  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180047c77  test    eax, eax
0x180047c79  jnz     short loc_180047CA7
0x180047c7b  mov     rcx, [rbp+57h+lpsz]; lpsz
0x180047c7f  mov     rdx, rsi; pclsid
0x180047c82  call    cs:__imp_CLSIDFromString
0x180047c89  nop     dword ptr [rax+rax+00h]
0x180047c8e  test    eax, eax
0x180047c90  mov     ebx, eax
0x180047c92  jns     loc_180047D5A
0x180047c98  mov     r8d, eax
0x180047c9b  lea     rdx, aStringtoclsidP_0; "StringToCLSID(pProtocolGuid) failed: 0x"...
0x180047ca2  jmp     loc_180047D7C
0x180047ca7  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180047cab  lea     r8, [rbp+57h+var_D0]; unsigned __int16 **
0x180047caf  lea     rdx, aWddll; "WdDLL"
0x180047cb6  lea     rcx, [rbp+57h+var_C0]; this
0x180047cba  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180047cbf  test    eax, eax
0x180047cc1  jnz     loc_180047D62
0x180047cc7  mov     r9d, 20019h; unsigned int
0x180047ccd  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Ter"...
0x180047cd4  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180047cdb  lea     rcx, [rbp+57h+var_70]; this
0x180047cdf  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180047ce4  test    eax, eax
0x180047ce6  jz      short loc_180047D01
0x180047ce8  jg      short loc_180047CEE
0x180047cea  mov     ebx, eax
0x180047cec  jmp     short loc_180047CF4
0x180047cee  movzx   ebx, ax
0x180047cf1  or      ebx, r12d
0x180047cf4  test    ebx, ebx
0x180047cf6  jns     short loc_180047D01
0x180047cf8  lea     rdx, aOregwdsOpenkey; "oRegWds.OpenKey(WD_REG_NAME) failed: 0x"...
0x180047cff  jmp     short loc_180047D79
0x180047d01  mov     r9d, 20019h; unsigned int
0x180047d07  mov     r8, [rbp+57h+var_D0]; unsigned __int16 *
0x180047d0b  mov     rdx, [rbp+57h+var_58]; HKEY
0x180047d0f  lea     rcx, [rbp+57h+var_98]; this
0x180047d13  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180047d18  test    eax, eax
0x180047d1a  jz      short loc_180047D35
0x180047d1c  jg      short loc_180047D22
0x180047d1e  mov     ebx, eax
0x180047d20  jmp     short loc_180047D28
0x180047d22  movzx   ebx, ax
0x180047d25  or      ebx, r12d
0x180047d28  test    ebx, ebx
0x180047d2a  jns     short loc_180047D35
0x180047d2c  lea     rdx, aOregwddllOpenk; "oRegWdDll.OpenKey(pWdDll) failed: 0x%x "...
0x180047d33  jmp     short loc_180047D79
0x180047d35  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180047d39  lea     r8, [rbp+57h+var_C8]; unsigned __int16 **
0x180047d3d  lea     rdx, aLoadableprotoc; "LoadableProtocol_Object"
0x180047d44  lea     rcx, [rbp+57h+var_98]; this
0x180047d48  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180047d4d  test    eax, eax
0x180047d4f  jnz     short loc_180047D8E
0x180047d51  mov     rcx, [rbp+57h+var_C8]
0x180047d55  jmp     loc_180047C7F
0x180047d5a  mov     dword ptr [rdi], 1
0x180047d60  jmp     short loc_180047D8E
0x180047d62  jg      short loc_180047D68
0x180047d64  mov     ebx, eax
0x180047d66  jmp     short loc_180047D6E
0x180047d68  movzx   ebx, ax
0x180047d6b  or      ebx, r12d
0x180047d6e  test    ebx, ebx
0x180047d70  jns     short loc_180047D8E
0x180047d72  lea     rdx, aOregwdsOpenkey_0; "oRegWds.OpenKey(WIN_WDDLL) failed: 0x%x"...
0x180047d79  mov     r8d, ebx
0x180047d7c  lea     r9, aCremoteconnect_20; "CRemoteConnectionManager::GetProtocolEx"...
0x180047d83  mov     ecx, 8; int
0x180047d88  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180047d8d  nop
0x180047d8e  lea     rcx, [rbp+57h+var_98]; this
0x180047d92  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180047d97  nop
0x180047d98  lea     rcx, [rbp+57h+var_70]; this
0x180047d9c  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180047da1  nop
0x180047da2  lea     rcx, [rbp+57h+var_C0]; this
0x180047da6  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180047dab  nop
0x180047dac  lea     rcx, [rbp+57h+var_48]; this
0x180047db0  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180047db5  mov     eax, ebx
0x180047db7  lea     r11, [rsp+100h+var_20]
0x180047dbf  mov     rbx, [r11+38h]
0x180047dc3  mov     rsi, [r11+48h]
0x180047dc7  mov     rsp, r11
0x180047dca  pop     r15
0x180047dcc  pop     r14
0x180047dce  pop     r12
0x180047dd0  pop     rdi
0x180047dd1  pop     rbp
0x180047dd2  retn
```
