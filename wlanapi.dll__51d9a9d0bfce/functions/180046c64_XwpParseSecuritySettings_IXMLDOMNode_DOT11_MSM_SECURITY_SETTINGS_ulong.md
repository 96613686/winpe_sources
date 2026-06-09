# XwpParseSecuritySettings(IXMLDOMNode *,_DOT11_MSM_SECURITY_SETTINGS *,ulong *)

- ea: `0x180046c64`
- end: `0x180046f6e`
- name: `?XwpParseSecuritySettings@@YAKPEAUIXMLDOMNode@@PEAU_DOT11_MSM_SECURITY_SETTINGS@@PEAK@Z`
- size: `778`
- prototype: `unsigned int(struct IXMLDOMNode *, struct _DOT11_MSM_SECURITY_SETTINGS *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dafc`

## callees

- `0x180009654`
- `0x18000d660`
- `0x18000dea8`
- `0x18000f7a8`
- `0x18000fb68`
- `0x180044de8`
- `0x1800461b0`
- `0x180046c64`
- `0x180046f74`
- `0x18004ea64`
- `0x18004f200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ccc`

## string_xrefs

- `0x180046c95`: `WLANProfile:MSM/WLANProfile:security`
- `0x180046d9c`: `WLANProfile:PMKCacheMode`
- `0x180046e02`: `WLANProfile:PMKCacheTTL`
- `0x180046e4f`: `WLANProfile:PMKCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XwpParseSecuritySettings(
        struct IXMLDOMNode *a1,
        struct _DOT11_MSM_SECURITY_SETTINGS *a2,
        unsigned int *a3)
{
  unsigned int SingleNode; // eax
  DWORD NodeDWORDValue; // edi
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v7; // rax
  unsigned int *v8; // r8
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v9; // rbx
  unsigned int v10; // r14d
  _DWORD *v11; // rax
  int v12; // eax
  unsigned int v13; // eax
  struct _ONEX_CONNECTION_PROFILE *v14; // rcx
  int v16; // [rsp+28h] [rbp-40h]
  int v17; // [rsp+28h] [rbp-40h]
  int v18; // [rsp+28h] [rbp-40h]
  int v19; // [rsp+28h] [rbp-40h]
  unsigned int v20; // [rsp+40h] [rbp-28h] BYREF
  struct IXMLDOMNode *v21; // [rsp+48h] [rbp-20h] BYREF
  struct _ONEX_CONNECTION_PROFILE *v22; // [rsp+50h] [rbp-18h] BYREF
  int v23; // [rsp+C8h] [rbp+60h] BYREF

  v21 = 0;
  v23 = 0;
  v20 = 0;
  v22 = 0;
  SingleNode = XcGetSingleNode(a1, L"WLANProfile:MSM/WLANProfile:security", &v21);
  NodeDWORDValue = SingleNode;
  if ( SingleNode == 1168 )
  {
    NodeDWORDValue = 0;
    goto LABEL_43;
  }
  if ( SingleNode )
    goto LABEL_43;
  v7 = (struct DOT11_MSMSEC_CONNECTION_PROFILE *)Xc_Process_user_allocate(0x98u);
  v9 = v7;
  if ( v7 )
  {
    NodeDWORDValue = XwpParseAuthEncryptionPair(v21, v7, v8);
    if ( !NodeDWORDValue )
    {
      v10 = 0;
      if ( *((_DWORD *)v9 + 4) )
      {
        v11 = (_DWORD *)*((_QWORD *)v9 + 3);
        if ( *v11 == 8 || *v11 == 11 )
          v10 = 0x2000000;
        NodeDWORDValue = XwpParseSharedKey(v21, v9, a3);
        if ( NodeDWORDValue )
          goto LABEL_42;
        NodeDWORDValue = XcGetNodeDWORDValue(v21, L"WLANProfile:keyIndex", &v20, 0, 3u, v16, 0, &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
        {
          *(_DWORD *)v9 |= 4u;
          *((_DWORD *)v9 + 14) = v20;
        }
        NodeDWORDValue = XcGetNodeEnumValue(
                           v21,
                           L"WLANProfile:PMKCacheMode",
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_18006A840,
                           2u,
                           (unsigned int *)v9 + 28,
                           1,
                           2u,
                           &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
        {
          *(_DWORD *)v9 |= 0x20u;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60009473>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60009473>::GetImpl'::`2'::impl) )
          {
            v12 = *(_DWORD *)v9;
            if ( *((_DWORD *)v9 + 28) == 1 )
              v13 = v12 | 0x2000;
            else
              v13 = v12 & 0xFFFFDFFF;
            *(_DWORD *)v9 = v13;
          }
        }
        NodeDWORDValue = XcGetNodeDWORDValue(v21, L"WLANProfile:PMKCacheTTL", &v20, 5u, 0x5A0u, v17, 0, &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
        {
          *(_DWORD *)v9 |= 0x80u;
          *((_DWORD *)v9 + 30) = 60 * v20;
        }
        NodeDWORDValue = XcGetNodeDWORDValue(v21, L"WLANProfile:PMKCacheSize", &v20, 1u, 0xFFu, v18, 0, &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
        {
          *(_DWORD *)v9 |= 0x40u;
          *((_DWORD *)v9 + 29) = v20;
        }
        NodeDWORDValue = XcGetNodeEnumValue(
                           v21,
                           L"WLANProfile:preAuthMode",
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_18006A860,
                           2u,
                           (unsigned int *)v9 + 26,
                           1,
                           1u,
                           &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
          *(_DWORD *)v9 |= 8u;
        NodeDWORDValue = XcGetNodeDWORDValue(v21, L"WLANProfile:preAuthThrottle", &v20, 1u, 0x10u, v19, 0, &v23);
        if ( NodeDWORDValue )
          goto LABEL_42;
        if ( v23 )
        {
          *(_DWORD *)v9 |= 0x10u;
          *((_DWORD *)v9 + 27) = v20;
        }
      }
      if ( !*((_DWORD *)v9 + 8) && *((_DWORD *)v9 + 4) )
        goto LABEL_39;
      NodeDWORDValue = XoParseOnexProfile(v10, v21, &v22, a3);
      if ( !NodeDWORDValue )
      {
        v14 = v22;
        if ( v22 )
        {
          *((_DWORD *)v9 + 10) = *((_DWORD *)v22 + 1);
          *((_QWORD *)v9 + 6) = v14;
        }
LABEL_39:
        *(_QWORD *)a2 = v9;
        goto LABEL_40;
      }
    }
LABEL_42:
    WcFreeDot11MsmSecProfile(v9);
    goto LABEL_43;
  }
  NodeDWORDValue = GetLastError();
LABEL_40:
  if ( NodeDWORDValue && v9 )
    goto LABEL_42;
LABEL_43:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
  return NodeDWORDValue;
}

```

## disassembly

```asm
0x180046c64  push    rbp
0x180046c66  push    rbx
0x180046c67  push    rsi
0x180046c68  push    rdi
0x180046c69  push    r12
0x180046c6b  push    r13
0x180046c6d  push    r14
0x180046c6f  push    r15
0x180046c71  mov     rbp, rsp
0x180046c74  sub     rsp, 68h
0x180046c78  mov     r15, r8
0x180046c7b  mov     r12, rdx
0x180046c7e  xor     r13d, r13d
0x180046c81  mov     [rbp+var_20], r13
0x180046c85  mov     [rbp+arg_18], r13d
0x180046c89  mov     [rbp+var_28], r13d
0x180046c8d  mov     [rbp+var_18], r13
0x180046c91  lea     r8, [rbp+var_20]; struct IXMLDOMNode **
0x180046c95  lea     rdx, aWlanprofileMsm_0; "WLANProfile:MSM/WLANProfile:security"
0x180046c9c  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x180046ca1  mov     edi, eax
0x180046ca3  cmp     eax, 490h
0x180046ca8  jnz     short loc_180046CB2
0x180046caa  mov     edi, r13d
0x180046cad  jmp     loc_180046F52
0x180046cb2  test    eax, eax
0x180046cb4  jnz     loc_180046F52
0x180046cba  mov     ecx, 98h; dwBytes
0x180046cbf  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180046cc4  mov     rbx, rax
0x180046cc7  test    rax, rax
0x180046cca  jnz     short loc_180046CD9
0x180046ccc  call    cs:__imp_GetLastError
0x180046cd2  mov     edi, eax
0x180046cd4  jmp     loc_180046F40
0x180046cd9  mov     rdx, rbx; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180046cdc  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046ce0  call    ?XwpParseAuthEncryptionPair@@YAKPEAUIXMLDOMNode@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAK@Z; XwpParseAuthEncryptionPair(IXMLDOMNode *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong *)
0x180046ce5  mov     edi, eax
0x180046ce7  test    eax, eax
0x180046ce9  jnz     loc_180046F49
0x180046cef  mov     r14d, r13d
0x180046cf2  cmp     [rbx+10h], r13d
0x180046cf6  jz      loc_180046F04
0x180046cfc  mov     rax, [rbx+18h]
0x180046d00  cmp     dword ptr [rax], 8
0x180046d03  jz      short loc_180046D0A
0x180046d05  cmp     dword ptr [rax], 0Bh
0x180046d08  jnz     short loc_180046D10
0x180046d0a  mov     r14d, 2000000h
0x180046d10  mov     r8, r15; unsigned int *
0x180046d13  mov     rdx, rbx; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180046d16  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046d1a  call    ?XwpParseSharedKey@@YAKPEAUIXMLDOMNode@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAK@Z; XwpParseSharedKey(IXMLDOMNode *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong *)
0x180046d1f  mov     edi, eax
0x180046d21  test    eax, eax
0x180046d23  jnz     loc_180046F49
0x180046d29  lea     rax, [rbp+arg_18]
0x180046d2d  mov     [rsp+68h+var_30], rax; int *
0x180046d32  mov     [rsp+68h+var_38], r13d; unsigned int
0x180046d37  mov     dword ptr [rsp+68h+var_48], 3; unsigned int
0x180046d3f  xor     r9d, r9d; unsigned int
0x180046d42  lea     r8, [rbp+var_28]; unsigned int *
0x180046d46  lea     rdx, aWlanprofileKey; "WLANProfile:keyIndex"
0x180046d4d  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046d51  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180046d56  mov     edi, eax
0x180046d58  test    eax, eax
0x180046d5a  jnz     loc_180046F49
0x180046d60  cmp     [rbp+arg_18], r13d
0x180046d64  jz      short loc_180046D6F
0x180046d66  or      dword ptr [rbx], 4
0x180046d69  mov     eax, [rbp+var_28]
0x180046d6c  mov     [rbx+38h], eax
0x180046d6f  lea     rsi, [rbx+70h]
0x180046d73  lea     rax, [rbp+arg_18]
0x180046d77  mov     [rsp+68h+var_30], rax; int *
0x180046d7c  mov     eax, 2
0x180046d81  mov     [rsp+68h+var_38], eax; unsigned int
0x180046d85  mov     [rsp+68h+var_40], 1; int
0x180046d8d  mov     [rsp+68h+var_48], rsi; unsigned int *
0x180046d92  mov     r9d, eax; unsigned int
0x180046d95  lea     r8, off_18006A840; struct _XC_STRING_VALUE_MAPPING *
0x180046d9c  lea     rdx, aWlanprofilePmk; "WLANProfile:PMKCacheMode"
0x180046da3  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046da7  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180046dac  mov     edi, eax
0x180046dae  test    eax, eax
0x180046db0  jnz     loc_180046F49
0x180046db6  cmp     [rbp+arg_18], r13d
0x180046dba  jz      short loc_180046DE2
0x180046dbc  or      dword ptr [rbx], 20h
0x180046dbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60009473@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60009473@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60009473> `wil::Feature<__WilFeatureTraits_Feature_60009473>::GetImpl(void)'::`2'::impl
0x180046dc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60009473@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60009473>::__private_IsEnabled(void)
0x180046dcb  test    al, al
0x180046dcd  jz      short loc_180046DE2
0x180046dcf  mov     eax, [rbx]
0x180046dd1  cmp     dword ptr [rsi], 1
0x180046dd4  jnz     short loc_180046DDC
0x180046dd6  bts     eax, 0Dh
0x180046dda  jmp     short loc_180046DE0
0x180046ddc  btr     eax, 0Dh
0x180046de0  mov     [rbx], eax
0x180046de2  lea     rax, [rbp+arg_18]
0x180046de6  mov     [rsp+68h+var_30], rax; int *
0x180046deb  mov     [rsp+68h+var_38], r13d; unsigned int
0x180046df0  mov     dword ptr [rsp+68h+var_48], 5A0h; unsigned int
0x180046df8  mov     r9d, 5; unsigned int
0x180046dfe  lea     r8, [rbp+var_28]; unsigned int *
0x180046e02  lea     rdx, aWlanprofilePmk_1; "WLANProfile:PMKCacheTTL"
0x180046e09  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046e0d  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180046e12  mov     edi, eax
0x180046e14  test    eax, eax
0x180046e16  jnz     loc_180046F49
0x180046e1c  cmp     [rbp+arg_18], r13d
0x180046e20  jz      short loc_180046E2D
0x180046e22  bts     dword ptr [rbx], 7
0x180046e26  imul    eax, [rbp+var_28], 3Ch ; '<'
0x180046e2a  mov     [rbx+78h], eax
0x180046e2d  lea     rax, [rbp+arg_18]
0x180046e31  mov     [rsp+68h+var_30], rax; int *
0x180046e36  mov     [rsp+68h+var_38], r13d; unsigned int
0x180046e3b  mov     dword ptr [rsp+68h+var_48], 0FFh; unsigned int
0x180046e43  mov     esi, 1
0x180046e48  mov     r9d, esi; unsigned int
0x180046e4b  lea     r8, [rbp+var_28]; unsigned int *
0x180046e4f  lea     rdx, aWlanprofilePmk_0; "WLANProfile:PMKCacheSize"
0x180046e56  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046e5a  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180046e5f  mov     edi, eax
0x180046e61  test    eax, eax
0x180046e63  jnz     loc_180046F49
0x180046e69  cmp     [rbp+arg_18], r13d
0x180046e6d  jz      short loc_180046E78
0x180046e6f  or      dword ptr [rbx], 40h
0x180046e72  mov     eax, [rbp+var_28]
0x180046e75  mov     [rbx+74h], eax
0x180046e78  lea     rax, [rbx+68h]
0x180046e7c  lea     rcx, [rbp+arg_18]
0x180046e80  mov     [rsp+68h+var_30], rcx; int *
0x180046e85  mov     [rsp+68h+var_38], esi; unsigned int
0x180046e89  mov     [rsp+68h+var_40], esi; int
0x180046e8d  mov     [rsp+68h+var_48], rax; unsigned int *
0x180046e92  mov     r9d, 2; unsigned int
0x180046e98  lea     r8, off_18006A860; struct _XC_STRING_VALUE_MAPPING *
0x180046e9f  lea     rdx, aWlanprofilePre_0; "WLANProfile:preAuthMode"
0x180046ea6  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046eaa  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x180046eaf  mov     edi, eax
0x180046eb1  test    eax, eax
0x180046eb3  jnz     loc_180046F49
0x180046eb9  cmp     [rbp+arg_18], r13d
0x180046ebd  jz      short loc_180046EC2
0x180046ebf  or      dword ptr [rbx], 8
0x180046ec2  lea     rax, [rbp+arg_18]
0x180046ec6  mov     [rsp+68h+var_30], rax; int *
0x180046ecb  mov     [rsp+68h+var_38], r13d; unsigned int
0x180046ed0  mov     dword ptr [rsp+68h+var_48], 10h; unsigned int
0x180046ed8  mov     r9d, esi; unsigned int
0x180046edb  lea     r8, [rbp+var_28]; unsigned int *
0x180046edf  lea     rdx, aWlanprofilePre; "WLANProfile:preAuthThrottle"
0x180046ee6  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x180046eea  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180046eef  mov     edi, eax
0x180046ef1  test    eax, eax
0x180046ef3  jnz     short loc_180046F49
0x180046ef5  cmp     [rbp+arg_18], r13d
0x180046ef9  jz      short loc_180046F04
0x180046efb  or      dword ptr [rbx], 10h
0x180046efe  mov     eax, [rbp+var_28]
0x180046f01  mov     [rbx+6Ch], eax
0x180046f04  cmp     [rbx+20h], r13d
0x180046f08  jnz     short loc_180046F10
0x180046f0a  cmp     [rbx+10h], r13d
0x180046f0e  jnz     short loc_180046F3C
0x180046f10  mov     r9, r15; unsigned int *
0x180046f13  lea     r8, [rbp+var_18]; struct _ONEX_CONNECTION_PROFILE **
0x180046f17  mov     rdx, [rbp+var_20]; struct IXMLDOMNode *
0x180046f1b  mov     ecx, r14d; unsigned int
0x180046f1e  call    ?XoParseOnexProfile@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z; XoParseOnexProfile(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)
0x180046f23  mov     edi, eax
0x180046f25  test    eax, eax
0x180046f27  jnz     short loc_180046F49
0x180046f29  mov     rcx, [rbp+var_18]
0x180046f2d  test    rcx, rcx
0x180046f30  jz      short loc_180046F3C
0x180046f32  mov     eax, [rcx+4]
0x180046f35  mov     [rbx+28h], eax
0x180046f38  mov     [rbx+30h], rcx
0x180046f3c  mov     [r12], rbx
0x180046f40  test    edi, edi
0x180046f42  jz      short loc_180046F52
0x180046f44  test    rbx, rbx
0x180046f47  jz      short loc_180046F52
0x180046f49  mov     rcx, rbx; lpMem
0x180046f4c  call    WcFreeDot11MsmSecProfile
0x180046f51  nop
0x180046f52  lea     rcx, [rbp+var_20]
0x180046f56  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180046f5b  mov     eax, edi
0x180046f5d  add     rsp, 68h
0x180046f61  pop     r15
0x180046f63  pop     r14
0x180046f65  pop     r13
0x180046f67  pop     r12
0x180046f69  pop     rdi
0x180046f6a  pop     rsi
0x180046f6b  pop     rbx
0x180046f6c  pop     rbp
0x180046f6d  retn
```
