# XwParseWlanProfile(IXMLDOMNode *,_PM_PROFILE *,ulong *)

- ea: `0x18000dafc`
- end: `0x18000dea1`
- name: `?XwParseWlanProfile@@YAKPEAUIXMLDOMNode@@PEAU_PM_PROFILE@@PEAK@Z`
- size: `933`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _PM_PROFILE *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000da08`

## callees

- `0x18000dafc`
- `0x18000dea8`
- `0x18000df08`
- `0x18000e3d0`
- `0x18000e470`
- `0x18000f7a8`
- `0x18000fb68`
- `0x180044d40`
- `0x180046490`
- `0x180046614`
- `0x1800468c8`
- `0x180046c64`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000dc62`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000dd50`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000dc62`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000dd50`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbae`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc9b`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbae`
- `OLEAUT32!__imp_VariantInit` at `0x18000dc9b`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc89`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd7f`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc89`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XwParseWlanProfile(struct IXMLDOMNode *a1, struct _PM_PROFILE *a2, unsigned int *a3)
{
  int v5; // r13d
  unsigned int NodeStringValue; // edi
  _DWORD *v7; // rax
  int *v8; // r9
  _DWORD *v9; // rsi
  int v10; // ebx
  unsigned int v11; // eax
  int SingleNode; // ebx
  int v13; // eax
  unsigned int i; // r15d
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r15d
  struct _DOT11_MSM_CONNECTIVITY_SETTINGS *v18; // rax
  int v20; // [rsp+20h] [rbp-50h]
  const unsigned __int16 *v21; // [rsp+28h] [rbp-48h]
  int *v22; // [rsp+30h] [rbp-40h]
  unsigned int v23; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMNode *v24; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v5 = 0;
  v28 = 0;
  if ( a3 )
    *a3 = 0;
  NodeStringValue = XcGetNodeStringValue(a1, L"WLANProfile:name", (unsigned __int16 *)a2 + 12, 0x100u, v20, v21, v22);
  if ( !NodeStringValue )
  {
    v7 = Xc_Process_user_allocate(0x48u);
    v9 = v7;
    if ( v7 )
    {
      *v7 = 1;
      v7[6] = 5;
      v7[5] = 4;
      v10 = XwpParseSSIDConfig(a1, (struct _DOT11_AC_PROFILE *)v7, a3, v8);
      v11 = XwpParseHotspot2Config(a1, (struct _DOT11_AC_PROFILE *)v9);
      NodeStringValue = v11;
      if ( v10 && v11 )
      {
LABEL_52:
        if ( !NodeStringValue || !v9 )
          return NodeStringValue;
LABEL_61:
        WcFreeDot11ACProfile(v9);
        return NodeStringValue;
      }
      VariantInit(&pvarg);
      v24 = 0;
      SingleNode = XcGetSingleNode(a1, L"WLANProfile:connectionType", &v24);
      if ( !SingleNode )
      {
        v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v24->lpVtbl->get_nodeTypedValue)(v24, &pvarg);
        if ( v13 < 0 )
        {
          SingleNode = (unsigned __int16)v13;
          if ( (v13 & 0x1FFF0000) != 0x70000 )
            SingleNode = v13;
        }
        else if ( pvarg.vt != 8 || !pvarg.llVal )
        {
          SingleNode = 1168;
        }
      }
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      NodeStringValue = 1206;
      if ( SingleNode == 1168 )
      {
        SingleNode = 1206;
      }
      else if ( !SingleNode )
      {
        SingleNode = 1206;
        for ( i = 0; i < 2; ++i )
        {
          if ( !lstrcmpW((&off_18006AA50)[2 * i], pvarg.bstrVal) )
          {
            v9[4] = dword_18006AA58[4 * i];
            SingleNode = 0;
            break;
          }
        }
      }
      VariantClear(&pvarg);
      if ( SingleNode )
      {
        NodeStringValue = SingleNode;
        goto LABEL_61;
      }
      VariantInit(&pvarg);
      v24 = 0;
      v15 = XcGetSingleNode(a1, L"WLANProfile:connectionMode", &v24);
      if ( !v15 )
      {
        v16 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v24->lpVtbl->get_nodeTypedValue)(v24, &pvarg);
        if ( v16 < 0 )
        {
          v15 = (unsigned __int16)v16;
          if ( (v16 & 0x1FFF0000) != 0x70000 )
            v15 = v16;
        }
        else if ( pvarg.vt != 8 || !pvarg.llVal )
        {
          v15 = 1168;
        }
      }
      if ( v24 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v24->lpVtbl->Release)(v24);
      if ( v15 == 1168 )
      {
        NodeStringValue = 0;
        v17 = 1;
      }
      else
      {
        v17 = 0;
        if ( v15 )
        {
          NodeStringValue = v15;
        }
        else
        {
          while ( v15 < 2 )
          {
            if ( !lstrcmpW((&off_18006AA30)[2 * v15], pvarg.bstrVal) )
            {
              v17 = dword_18006AA38[4 * v15];
              NodeStringValue = 0;
              v5 = 1;
              v28 = 1;
              break;
            }
            ++v15;
          }
        }
      }
      VariantClear(&pvarg);
      if ( NodeStringValue )
        goto LABEL_61;
      if ( v5 )
      {
        v9[1] |= 1u;
        if ( !v17 )
          v9[6] &= ~1u;
      }
      NodeStringValue = XcGetNodeEnumValue(
                          a1,
                          L"WLANProfile:autoSwitch",
                          (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                          4u,
                          &v23,
                          1,
                          1u,
                          &v28);
      if ( NodeStringValue )
        goto LABEL_61;
      if ( v28 )
      {
        v9[1] |= 2u;
        if ( !v23 )
          v9[6] &= ~4u;
      }
      v18 = (struct _DOT11_MSM_CONNECTIVITY_SETTINGS *)Xc_Process_user_allocate(0x1C8u);
      *((_QWORD *)v9 + 4) = v18;
      if ( v18 )
      {
        NodeStringValue = XwpParseConnectivitySettings(a1, v18);
        if ( !NodeStringValue )
        {
          NodeStringValue = XwpParseSecuritySettings(
                              a1,
                              (struct _DOT11_MSM_SECURITY_SETTINGS *)(*((_QWORD *)v9 + 4) + 424LL),
                              a3);
          if ( !NodeStringValue )
          {
            NodeStringValue = XwpParseIHVSettings(a1, *((struct _DOT11_MSM_PROFILE **)v9 + 4));
            if ( !NodeStringValue )
            {
              NodeStringValue = XwpParseRandomMACConfig(a1, (struct _DOT11_AC_PROFILE *)v9);
              if ( !NodeStringValue )
              {
                *((_QWORD *)a2 + 69) = v9;
                return NodeStringValue;
              }
            }
          }
        }
        goto LABEL_61;
      }
    }
    NodeStringValue = GetLastError();
    goto LABEL_52;
  }
  return NodeStringValue;
}

```

## disassembly

```asm
0x18000dafc  mov     [rsp-38h+arg_0], rbx
0x18000db01  mov     [rsp-38h+arg_10], r8
0x18000db06  mov     [rsp-38h+arg_8], rdx
0x18000db0b  push    rbp
0x18000db0c  push    rsi
0x18000db0d  push    rdi
0x18000db0e  push    r12
0x18000db10  push    r13
0x18000db12  push    r14
0x18000db14  push    r15
0x18000db16  mov     rbp, rsp
0x18000db19  sub     rsp, 70h
0x18000db1d  mov     rbx, r8
0x18000db20  mov     r14, rcx
0x18000db23  mov     [rbp+var_30], 0
0x18000db2a  xor     r13d, r13d
0x18000db2d  mov     [rbp+arg_18], r13d
0x18000db31  test    r8, r8
0x18000db34  jz      short loc_18000DB39
0x18000db36  mov     [r8], r13d
0x18000db39  lea     r8, [rdx+18h]; unsigned __int16 *
0x18000db3d  mov     r9d, 100h; unsigned __int64
0x18000db43  lea     rdx, aWlanprofileNam; "WLANProfile:name"
0x18000db4a  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000db4f  mov     edi, eax
0x18000db51  test    eax, eax
0x18000db53  jnz     loc_18000DE87
0x18000db59  lea     ecx, [rax+48h]; dwBytes
0x18000db5c  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000db61  mov     rsi, rax
0x18000db64  test    rax, rax
0x18000db67  jz      loc_18000DE0C
0x18000db6d  mov     dword ptr [rax], 1
0x18000db73  mov     dword ptr [rax+18h], 5
0x18000db7a  mov     dword ptr [rax+14h], 4
0x18000db81  mov     r8, rbx; unsigned int *
0x18000db84  mov     rdx, rax; struct _DOT11_AC_PROFILE *
0x18000db87  mov     rcx, r14; struct IXMLDOMNode *
0x18000db8a  call    ?XwpParseSSIDConfig@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@PEAKPEAH@Z; XwpParseSSIDConfig(IXMLDOMNode *,_DOT11_AC_PROFILE *,ulong *,int *)
0x18000db8f  mov     ebx, eax
0x18000db91  mov     rdx, rsi; struct _DOT11_AC_PROFILE *
0x18000db94  mov     rcx, r14; struct IXMLDOMNode *
0x18000db97  call    ?XwpParseHotspot2Config@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@@Z; XwpParseHotspot2Config(IXMLDOMNode *,_DOT11_AC_PROFILE *)
0x18000db9c  mov     edi, eax
0x18000db9e  test    ebx, ebx
0x18000dba0  jz      short loc_18000DBAA
0x18000dba2  test    eax, eax
0x18000dba4  jnz     loc_18000DE14
0x18000dbaa  lea     rcx, [rbp+pvarg]; pvarg
0x18000dbae  call    cs:__imp_VariantInit
0x18000dbb4  mov     [rbp+var_28], r13
0x18000dbb8  lea     r8, [rbp+var_28]; struct IXMLDOMNode **
0x18000dbbc  lea     rdx, aWlanprofileCon_1; "WLANProfile:connectionType"
0x18000dbc3  mov     rcx, r14; struct IXMLDOMNode *
0x18000dbc6  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000dbcb  mov     ebx, eax
0x18000dbcd  test    eax, eax
0x18000dbcf  jnz     short loc_18000DC13
0x18000dbd1  mov     rcx, [rbp+var_28]
0x18000dbd5  mov     rdx, [rcx]
0x18000dbd8  mov     rax, [rdx+0F0h]
0x18000dbdf  lea     rdx, [rbp+pvarg]
0x18000dbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe8  mov     ecx, eax
0x18000dbea  test    eax, eax
0x18000dbec  js      short loc_18000DC02
0x18000dbee  cmp     word ptr [rbp+pvarg], 8
0x18000dbf3  jnz     short loc_18000DBFB
0x18000dbf5  cmp     qword ptr [rbp+pvarg+8], r13
0x18000dbf9  jnz     short loc_18000DC13
0x18000dbfb  mov     ebx, 490h
0x18000dc00  jmp     short loc_18000DC13
0x18000dc02  and     eax, 1FFF0000h
0x18000dc07  cmp     eax, 70000h
0x18000dc0c  movzx   ebx, cx
0x18000dc0f  jz      short loc_18000DC13
0x18000dc11  mov     ebx, ecx
0x18000dc13  mov     rcx, [rbp+var_28]
0x18000dc17  test    rcx, rcx
0x18000dc1a  jz      short loc_18000DC29
0x18000dc1c  mov     rax, [rcx]
0x18000dc1f  mov     rax, [rax+10h]
0x18000dc23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc28  nop
0x18000dc29  lea     rax, __ImageBase
0x18000dc30  mov     edi, 4B6h
0x18000dc35  cmp     ebx, 490h
0x18000dc3b  jnz     short loc_18000DC41
0x18000dc3d  mov     ebx, edi
0x18000dc3f  jmp     short loc_18000DC85
0x18000dc41  test    ebx, ebx
0x18000dc43  jnz     short loc_18000DC85
0x18000dc45  mov     ebx, edi
0x18000dc47  xor     r15d, r15d
0x18000dc4a  cmp     r15d, 2
0x18000dc4e  jnb     short loc_18000DC85
0x18000dc50  mov     r12d, r15d
0x18000dc53  add     r12, r12
0x18000dc56  mov     rdx, qword ptr [rbp+pvarg+8]; lpString2
0x18000dc5a  mov     rcx, ds:rva off_18006AA50[rax+r12*8]; lpString1
0x18000dc62  call    cs:__imp_lstrcmpW
0x18000dc68  test    eax, eax
0x18000dc6a  lea     rax, __ImageBase
0x18000dc71  jz      short loc_18000DC78
0x18000dc73  inc     r15d
0x18000dc76  jmp     short loc_18000DC4A
0x18000dc78  mov     eax, ds:rva dword_18006AA58[rax+r12*8]
0x18000dc80  mov     [rsi+10h], eax
0x18000dc83  xor     ebx, ebx
0x18000dc85  lea     rcx, [rbp+pvarg]; pvarg
0x18000dc89  call    cs:__imp_VariantClear
0x18000dc8f  test    ebx, ebx
0x18000dc91  jnz     loc_18000DE7D
0x18000dc97  lea     rcx, [rbp+pvarg]; pvarg
0x18000dc9b  call    cs:__imp_VariantInit
0x18000dca1  mov     [rbp+var_28], 0
0x18000dca9  lea     r8, [rbp+var_28]; struct IXMLDOMNode **
0x18000dcad  lea     rdx, aWlanprofileCon_0; "WLANProfile:connectionMode"
0x18000dcb4  mov     rcx, r14; struct IXMLDOMNode *
0x18000dcb7  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000dcbc  mov     ebx, eax
0x18000dcbe  test    eax, eax
0x18000dcc0  jnz     short loc_18000DD05
0x18000dcc2  mov     rcx, [rbp+var_28]
0x18000dcc6  mov     rdx, [rcx]
0x18000dcc9  mov     rax, [rdx+0F0h]
0x18000dcd0  lea     rdx, [rbp+pvarg]
0x18000dcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd9  mov     ecx, eax
0x18000dcdb  test    eax, eax
0x18000dcdd  js      short loc_18000DCF4
0x18000dcdf  cmp     word ptr [rbp+pvarg], 8
0x18000dce4  jnz     short loc_18000DCED
0x18000dce6  cmp     qword ptr [rbp+pvarg+8], 0
0x18000dceb  jnz     short loc_18000DD05
0x18000dced  mov     ebx, 490h
0x18000dcf2  jmp     short loc_18000DD05
0x18000dcf4  and     eax, 1FFF0000h
0x18000dcf9  cmp     eax, 70000h
0x18000dcfe  movzx   ebx, cx
0x18000dd01  jz      short loc_18000DD05
0x18000dd03  mov     ebx, ecx
0x18000dd05  mov     rcx, [rbp+var_28]
0x18000dd09  test    rcx, rcx
0x18000dd0c  jz      short loc_18000DD1B
0x18000dd0e  mov     rax, [rcx]
0x18000dd11  mov     rax, [rax+10h]
0x18000dd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd1a  nop
0x18000dd1b  cmp     ebx, 490h
0x18000dd21  jnz     short loc_18000DD2B
0x18000dd23  xor     edi, edi
0x18000dd25  lea     r15d, [rdi+1]
0x18000dd29  jmp     short loc_18000DD7B
0x18000dd2b  xor     r15d, r15d
0x18000dd2e  test    ebx, ebx
0x18000dd30  jnz     short loc_18000DD79
0x18000dd32  cmp     ebx, 2
0x18000dd35  jnb     short loc_18000DD7B
0x18000dd37  mov     r12d, ebx
0x18000dd3a  add     r12, r12
0x18000dd3d  mov     rdx, qword ptr [rbp+pvarg+8]; lpString2
0x18000dd41  lea     rax, __ImageBase
0x18000dd48  mov     rcx, ds:rva off_18006AA30[rax+r12*8]; lpString1
0x18000dd50  call    cs:__imp_lstrcmpW
0x18000dd56  test    eax, eax
0x18000dd58  jz      short loc_18000DD5E
0x18000dd5a  inc     ebx
0x18000dd5c  jmp     short loc_18000DD32
0x18000dd5e  lea     rax, __ImageBase
0x18000dd65  mov     r15d, ds:rva dword_18006AA38[rax+r12*8]
0x18000dd6d  xor     edi, edi
0x18000dd6f  lea     r13d, [rdi+1]
0x18000dd73  mov     [rbp+arg_18], r13d
0x18000dd77  jmp     short loc_18000DD7B
0x18000dd79  mov     edi, ebx
0x18000dd7b  lea     rcx, [rbp+pvarg]; pvarg
0x18000dd7f  call    cs:__imp_VariantClear
0x18000dd85  test    edi, edi
0x18000dd87  jnz     loc_18000DE7F
0x18000dd8d  test    r13d, r13d
0x18000dd90  jz      short loc_18000DD9F
0x18000dd92  or      dword ptr [rsi+4], 1
0x18000dd96  test    r15d, r15d
0x18000dd99  jnz     short loc_18000DD9F
0x18000dd9b  and     dword ptr [rsi+18h], 0FFFFFFFEh
0x18000dd9f  lea     rax, [rbp+arg_18]
0x18000dda3  mov     [rsp+70h+var_38], rax; int *
0x18000dda8  mov     dword ptr [rsp+70h+var_40], 1; unsigned int
0x18000ddb0  mov     dword ptr [rsp+70h+var_48], 1; int
0x18000ddb8  lea     rax, [rbp+var_30]
0x18000ddbc  mov     [rsp+70h+var_50], rax; unsigned int *
0x18000ddc1  mov     r9d, 4; unsigned int
0x18000ddc7  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x18000ddce  lea     rdx, aWlanprofileAut_0; "WLANProfile:autoSwitch"
0x18000ddd5  mov     rcx, r14; struct IXMLDOMNode *
0x18000ddd8  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000dddd  mov     edi, eax
0x18000dddf  test    eax, eax
0x18000dde1  jnz     loc_18000DE7F
0x18000dde7  cmp     [rbp+arg_18], eax
0x18000ddea  jz      short loc_18000DDF9
0x18000ddec  or      dword ptr [rsi+4], 2
0x18000ddf0  cmp     [rbp+var_30], eax
0x18000ddf3  jnz     short loc_18000DDF9
0x18000ddf5  and     dword ptr [rsi+18h], 0FFFFFFFBh
0x18000ddf9  mov     ecx, 1C8h; dwBytes
0x18000ddfe  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000de03  mov     [rsi+20h], rax
0x18000de07  test    rax, rax
0x18000de0a  jnz     short loc_18000DE1F
0x18000de0c  call    cs:__imp_GetLastError
0x18000de12  mov     edi, eax
0x18000de14  test    edi, edi
0x18000de16  jz      short loc_18000DE87
0x18000de18  test    rsi, rsi
0x18000de1b  jnz     short loc_18000DE7F
0x18000de1d  jmp     short loc_18000DE87
0x18000de1f  mov     rdx, rax; struct _DOT11_MSM_CONNECTIVITY_SETTINGS *
0x18000de22  mov     rcx, r14; struct IXMLDOMNode *
0x18000de25  call    ?XwpParseConnectivitySettings@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_MSM_CONNECTIVITY_SETTINGS@@@Z; XwpParseConnectivitySettings(IXMLDOMNode *,_DOT11_MSM_CONNECTIVITY_SETTINGS *)
0x18000de2a  mov     edi, eax
0x18000de2c  test    eax, eax
0x18000de2e  jnz     short loc_18000DE7F
0x18000de30  mov     rdx, [rsi+20h]
0x18000de34  add     rdx, 1A8h; struct _DOT11_MSM_SECURITY_SETTINGS *
0x18000de3b  mov     r8, [rbp+arg_10]; unsigned int *
0x18000de3f  mov     rcx, r14; struct IXMLDOMNode *
0x18000de42  call    ?XwpParseSecuritySettings@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_MSM_SECURITY_SETTINGS@@PEAK@Z; XwpParseSecuritySettings(IXMLDOMNode *,_DOT11_MSM_SECURITY_SETTINGS *,ulong *)
0x18000de47  mov     edi, eax
0x18000de49  test    eax, eax
0x18000de4b  jnz     short loc_18000DE7F
0x18000de4d  mov     rdx, [rsi+20h]; struct _DOT11_MSM_PROFILE *
0x18000de51  mov     rcx, r14; struct IXMLDOMNode *
0x18000de54  call    ?XwpParseIHVSettings@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_MSM_PROFILE@@@Z; XwpParseIHVSettings(IXMLDOMNode *,_DOT11_MSM_PROFILE *)
0x18000de59  mov     edi, eax
0x18000de5b  test    eax, eax
0x18000de5d  jnz     short loc_18000DE7F
0x18000de5f  mov     rdx, rsi; struct _DOT11_AC_PROFILE *
0x18000de62  mov     rcx, r14; struct IXMLDOMNode *
0x18000de65  call    ?XwpParseRandomMACConfig@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_AC_PROFILE@@@Z; XwpParseRandomMACConfig(IXMLDOMNode *,_DOT11_AC_PROFILE *)
0x18000de6a  mov     edi, eax
0x18000de6c  test    eax, eax
0x18000de6e  jnz     short loc_18000DE7F
0x18000de70  mov     rax, [rbp+arg_8]
0x18000de74  mov     [rax+228h], rsi
0x18000de7b  jmp     short loc_18000DE87
0x18000de7d  mov     edi, ebx
0x18000de7f  mov     rcx, rsi; lpMem
0x18000de82  call    WcFreeDot11ACProfile
0x18000de87  mov     eax, edi
0x18000de89  mov     rbx, [rsp+70h+arg_0]
0x18000de91  add     rsp, 70h
0x18000de95  pop     r15
0x18000de97  pop     r14
0x18000de99  pop     r13
0x18000de9b  pop     r12
0x18000de9d  pop     rdi
0x18000de9e  pop     rsi
0x18000de9f  pop     rbp
0x18000dea0  retn
```
