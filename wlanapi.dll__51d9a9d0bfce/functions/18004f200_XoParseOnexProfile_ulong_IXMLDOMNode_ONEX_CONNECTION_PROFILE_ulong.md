# XoParseOnexProfile(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)

- ea: `0x18004f200`
- end: `0x18004f584`
- name: `?XoParseOnexProfile@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z`
- size: `900`
- prototype: `unsigned int __fastcall(unsigned int, struct IXMLDOMNode *, struct _ONEX_CONNECTION_PROFILE **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046c64`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000f7a8`
- `0x18000fb68`
- `0x180019370`
- `0x180043748`
- `0x18004ea64`
- `0x18004f200`
- `0x18004f954`
- `0x18004fc68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f278`

## string_xrefs

- `0x18004f2c0`: `OneX:cacheUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XoParseOnexProfile(
        int a1,
        struct IXMLDOMNode *a2,
        struct _ONEX_CONNECTION_PROFILE **a3,
        unsigned int *a4)
{
  unsigned int SingleNode; // eax
  unsigned int NodeEnumValue; // edi
  struct _ONEX_CONNECTION_PROFILE *v9; // rax
  struct _ONEX_CONNECTION_PROFILE *v10; // rbx
  unsigned int *v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  int v15; // [rsp+28h] [rbp-38h]
  int v16; // [rsp+28h] [rbp-38h]
  int v17; // [rsp+28h] [rbp-38h]
  int v18; // [rsp+28h] [rbp-38h]
  int v19; // [rsp+28h] [rbp-38h]
  int v20; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-1Ch] BYREF
  struct IXMLDOMNode *v22; // [rsp+48h] [rbp-18h] BYREF
  struct _ONEX_CONNECTION_PROFILE *v23; // [rsp+50h] [rbp-10h] BYREF

  v22 = 0;
  v21 = 0;
  v20 = 0;
  SingleNode = XcGetSingleNode(a2, L"OneX:OneX", &v22);
  NodeEnumValue = SingleNode;
  if ( SingleNode == 1168 )
  {
    NodeEnumValue = 0;
    *a3 = 0;
  }
  else if ( !SingleNode )
  {
    v9 = (struct _ONEX_CONNECTION_PROFILE *)Xc_Process_user_allocate(0x68u);
    v10 = v9;
    v23 = v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = 1;
      *((_DWORD *)v9 + 1) = 104;
      NodeEnumValue = XcGetNodeEnumValue(
                        v22,
                        L"OneX:cacheUserData",
                        (const struct _XC_STRING_VALUE_MAPPING *)&off_1800631E0,
                        4u,
                        &v21,
                        1,
                        1u,
                        &v20);
      if ( !NodeEnumValue )
      {
        if ( v20 )
        {
          *((_DWORD *)v10 + 2) |= 1u;
          if ( !v21 )
            *((_DWORD *)v10 + 3) |= 2u;
        }
        NodeEnumValue = XcGetNodeDWORDValue(
                          v22,
                          L"OneX:heldPeriod",
                          (unsigned int *)v10 + 6,
                          1u,
                          0xE10u,
                          v15,
                          0xFFFFFFFF,
                          &v20);
        if ( !NodeEnumValue )
        {
          *((_DWORD *)v10 + 2) &= ~8u;
          *((_DWORD *)v10 + 2) |= 8 * (v20 & 1);
          NodeEnumValue = XcGetNodeDWORDValue(
                            v22,
                            L"OneX:authPeriod",
                            (unsigned int *)v10 + 7,
                            1u,
                            0xE10u,
                            v16,
                            0xFFFFFFFF,
                            &v20);
          if ( !NodeEnumValue )
          {
            *((_DWORD *)v10 + 2) &= ~0x10u;
            *((_DWORD *)v10 + 2) |= 16 * (v20 & 1);
            NodeEnumValue = XcGetNodeDWORDValue(
                              v22,
                              L"OneX:startPeriod",
                              (unsigned int *)v10 + 8,
                              1u,
                              0xE10u,
                              v17,
                              0xFFFFFFFF,
                              &v20);
            if ( !NodeEnumValue )
            {
              *((_DWORD *)v10 + 2) &= ~0x20u;
              *((_DWORD *)v10 + 2) |= 32 * (v20 & 1);
              NodeEnumValue = XcGetNodeDWORDValue(
                                v22,
                                L"OneX:maxStart",
                                (unsigned int *)v10 + 9,
                                1u,
                                0x64u,
                                v18,
                                0xFFFFFFFF,
                                &v20);
              if ( !NodeEnumValue )
              {
                *((_DWORD *)v10 + 2) &= ~0x40u;
                *((_DWORD *)v10 + 2) |= (v20 & 1) << 6;
                NodeEnumValue = XcGetNodeDWORDValue(
                                  v22,
                                  L"OneX:maxAuthFailures",
                                  (unsigned int *)v10 + 10,
                                  1u,
                                  0x64u,
                                  v19,
                                  0xFFFFFFFF,
                                  &v20);
                if ( !NodeEnumValue )
                {
                  *((_DWORD *)v10 + 2) &= ~0x80u;
                  *((_DWORD *)v10 + 2) |= (v20 & 1) << 7;
                  NodeEnumValue = XcGetNodeEnumValue(
                                    v22,
                                    L"OneX:supplicantMode",
                                    (const struct _XC_STRING_VALUE_MAPPING *)&off_18006AD30,
                                    3u,
                                    (unsigned int *)v10 + 4,
                                    1,
                                    3u,
                                    &v20);
                  if ( !NodeEnumValue )
                  {
                    *((_DWORD *)v10 + 2) &= ~2u;
                    *((_DWORD *)v10 + 2) |= 2 * (v20 & 1);
                    NodeEnumValue = XcGetNodeEnumValue(
                                      v22,
                                      L"OneX:authMode",
                                      (const struct _XC_STRING_VALUE_MAPPING *)&off_18006ACF0,
                                      4u,
                                      (unsigned int *)v10 + 5,
                                      1,
                                      5u,
                                      &v20);
                    if ( !NodeEnumValue )
                    {
                      *((_DWORD *)v10 + 2) &= ~4u;
                      *((_DWORD *)v10 + 2) |= 4 * (v20 & 1);
                      NodeEnumValue = XopParseSingleSignOn(v22, v10, v11);
                      if ( !NodeEnumValue )
                      {
                        NodeEnumValue = GetAlignedSize(32, (char *)v10 + 60, v12);
                        if ( !NodeEnumValue )
                        {
                          NodeEnumValue = GetAlignedSize(68, (char *)v10 + 64, v13);
                          if ( !NodeEnumValue )
                          {
                            NodeEnumValue = XopParseEapConfig(a1, v22, &v23, a4);
                            if ( !NodeEnumValue )
                            {
                              *a3 = v23;
                              goto LABEL_26;
                            }
                            v10 = v23;
                          }
                        }
                      }
                    }
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
      NodeEnumValue = GetLastError();
      if ( !NodeEnumValue )
        goto LABEL_26;
    }
    if ( v10 )
      Xc_Process_user_free(v10);
  }
LABEL_26:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v22);
  return NodeEnumValue;
}

```

## disassembly

```asm
0x18004f200  push    rbp
0x18004f202  push    rbx
0x18004f203  push    rsi
0x18004f204  push    rdi
0x18004f205  push    r13
0x18004f207  push    r14
0x18004f209  push    r15
0x18004f20b  mov     rbp, rsp
0x18004f20e  sub     rsp, 60h
0x18004f212  mov     r14, r9
0x18004f215  mov     rsi, r8
0x18004f218  mov     rax, rdx
0x18004f21b  mov     r15d, ecx
0x18004f21e  mov     [rbp+var_18], 0
0x18004f226  mov     [rbp+var_1C], 0
0x18004f22d  mov     [rbp+var_20], 0
0x18004f234  lea     r8, [rbp+var_18]; struct IXMLDOMNode **
0x18004f238  lea     rdx, aOnexOnex; "OneX:OneX"
0x18004f23f  mov     rcx, rax; struct IXMLDOMNode *
0x18004f242  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18004f247  mov     edi, eax
0x18004f249  cmp     eax, 490h
0x18004f24e  jnz     short loc_18004F25A
0x18004f250  xor     edi, edi
0x18004f252  mov     [rsi], rdi
0x18004f255  jmp     loc_18004F569
0x18004f25a  test    eax, eax
0x18004f25c  jnz     loc_18004F569
0x18004f262  lea     edi, [rax+68h]
0x18004f265  mov     ecx, edi; dwBytes
0x18004f267  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18004f26c  mov     rbx, rax
0x18004f26f  mov     [rbp+var_10], rax
0x18004f273  test    rax, rax
0x18004f276  jnz     short loc_18004F28D
0x18004f278  call    cs:__imp_GetLastError
0x18004f27e  mov     edi, eax
0x18004f280  test    eax, eax
0x18004f282  jz      loc_18004F569
0x18004f288  jmp     loc_18004F55B
0x18004f28d  mov     r13d, 1
0x18004f293  mov     [rax], r13d
0x18004f296  mov     [rax+4], edi
0x18004f299  lea     rax, [rbp+var_20]
0x18004f29d  mov     [rsp+60h+var_28], rax; int *
0x18004f2a2  mov     [rsp+60h+var_30], r13d; unsigned int
0x18004f2a7  mov     [rsp+60h+var_38], r13d; int
0x18004f2ac  lea     rax, [rbp+var_1C]
0x18004f2b0  mov     [rsp+60h+var_40], rax; unsigned int *
0x18004f2b5  lea     r9d, [r13+3]; unsigned int
0x18004f2b9  lea     r8, off_1800631E0; struct _XC_STRING_VALUE_MAPPING *
0x18004f2c0  lea     rdx, aOnexCacheuserd; "OneX:cacheUserData"
0x18004f2c7  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f2cb  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18004f2d0  mov     edi, eax
0x18004f2d2  test    eax, eax
0x18004f2d4  jnz     loc_18004F55B
0x18004f2da  cmp     [rbp+var_20], eax
0x18004f2dd  jz      short loc_18004F2EC
0x18004f2df  or      [rbx+8], r13d
0x18004f2e3  cmp     [rbp+var_1C], eax
0x18004f2e6  jnz     short loc_18004F2EC
0x18004f2e8  or      dword ptr [rbx+0Ch], 2
0x18004f2ec  lea     r8, [rbx+18h]; unsigned int *
0x18004f2f0  lea     rax, [rbp+var_20]
0x18004f2f4  mov     [rsp+60h+var_28], rax; int *
0x18004f2f9  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x18004f301  mov     dword ptr [rsp+60h+var_40], 0E10h; unsigned int
0x18004f309  mov     r9d, r13d; unsigned int
0x18004f30c  lea     rdx, aOnexHeldperiod; "OneX:heldPeriod"
0x18004f313  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f317  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18004f31c  mov     edi, eax
0x18004f31e  test    eax, eax
0x18004f320  jnz     loc_18004F55B
0x18004f326  and     dword ptr [rbx+8], 0FFFFFFF7h
0x18004f32a  mov     eax, [rbp+var_20]
0x18004f32d  and     eax, r13d
0x18004f330  shl     eax, 3
0x18004f333  or      [rbx+8], eax
0x18004f336  lea     r8, [rbx+1Ch]; unsigned int *
0x18004f33a  lea     rax, [rbp+var_20]
0x18004f33e  mov     [rsp+60h+var_28], rax; int *
0x18004f343  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x18004f34b  mov     dword ptr [rsp+60h+var_40], 0E10h; unsigned int
0x18004f353  mov     r9d, r13d; unsigned int
0x18004f356  lea     rdx, aOnexAuthperiod; "OneX:authPeriod"
0x18004f35d  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f361  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18004f366  mov     edi, eax
0x18004f368  test    eax, eax
0x18004f36a  jnz     loc_18004F55B
0x18004f370  and     dword ptr [rbx+8], 0FFFFFFEFh
0x18004f374  mov     eax, [rbp+var_20]
0x18004f377  and     eax, r13d
0x18004f37a  shl     eax, 4
0x18004f37d  or      [rbx+8], eax
0x18004f380  lea     r8, [rbx+20h]; unsigned int *
0x18004f384  lea     rax, [rbp+var_20]
0x18004f388  mov     [rsp+60h+var_28], rax; int *
0x18004f38d  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x18004f395  mov     dword ptr [rsp+60h+var_40], 0E10h; unsigned int
0x18004f39d  mov     r9d, r13d; unsigned int
0x18004f3a0  lea     rdx, aOnexStartperio; "OneX:startPeriod"
0x18004f3a7  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f3ab  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18004f3b0  mov     edi, eax
0x18004f3b2  test    eax, eax
0x18004f3b4  jnz     loc_18004F55B
0x18004f3ba  and     dword ptr [rbx+8], 0FFFFFFDFh
0x18004f3be  mov     eax, [rbp+var_20]
0x18004f3c1  and     eax, r13d
0x18004f3c4  shl     eax, 5
0x18004f3c7  or      [rbx+8], eax
0x18004f3ca  lea     r8, [rbx+24h]; unsigned int *
0x18004f3ce  lea     rax, [rbp+var_20]
0x18004f3d2  mov     [rsp+60h+var_28], rax; int *
0x18004f3d7  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x18004f3df  mov     dword ptr [rsp+60h+var_40], 64h ; 'd'; unsigned int
0x18004f3e7  mov     r9d, r13d; unsigned int
0x18004f3ea  lea     rdx, aOnexMaxstart; "OneX:maxStart"
0x18004f3f1  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f3f5  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18004f3fa  mov     edi, eax
0x18004f3fc  test    eax, eax
0x18004f3fe  jnz     loc_18004F55B
0x18004f404  and     dword ptr [rbx+8], 0FFFFFFBFh
0x18004f408  mov     eax, [rbp+var_20]
0x18004f40b  and     eax, r13d
0x18004f40e  shl     eax, 6
0x18004f411  or      [rbx+8], eax
0x18004f414  lea     r8, [rbx+28h]; unsigned int *
0x18004f418  lea     rax, [rbp+var_20]
0x18004f41c  mov     [rsp+60h+var_28], rax; int *
0x18004f421  mov     [rsp+60h+var_30], 0FFFFFFFFh; unsigned int
0x18004f429  mov     dword ptr [rsp+60h+var_40], 64h ; 'd'; unsigned int
0x18004f431  mov     r9d, r13d; unsigned int
0x18004f434  lea     rdx, aOnexMaxauthfai; "OneX:maxAuthFailures"
0x18004f43b  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f43f  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18004f444  mov     edi, eax
0x18004f446  test    eax, eax
0x18004f448  jnz     loc_18004F55B
0x18004f44e  btr     dword ptr [rbx+8], 7
0x18004f453  mov     eax, [rbp+var_20]
0x18004f456  and     eax, r13d
0x18004f459  shl     eax, 7
0x18004f45c  or      [rbx+8], eax
0x18004f45f  lea     rax, [rbx+10h]
0x18004f463  lea     rcx, [rbp+var_20]
0x18004f467  mov     [rsp+60h+var_28], rcx; int *
0x18004f46c  lea     r9d, [rdi+3]; unsigned int
0x18004f470  mov     [rsp+60h+var_30], r9d; unsigned int
0x18004f475  mov     [rsp+60h+var_38], r13d; int
0x18004f47a  mov     [rsp+60h+var_40], rax; unsigned int *
0x18004f47f  lea     r8, off_18006AD30; struct _XC_STRING_VALUE_MAPPING *
0x18004f486  lea     rdx, aOnexSupplicant; "OneX:supplicantMode"
0x18004f48d  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f491  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18004f496  mov     edi, eax
0x18004f498  test    eax, eax
0x18004f49a  jnz     loc_18004F55B
0x18004f4a0  and     dword ptr [rbx+8], 0FFFFFFFDh
0x18004f4a4  mov     eax, [rbp+var_20]
0x18004f4a7  and     eax, r13d
0x18004f4aa  add     eax, eax
0x18004f4ac  or      [rbx+8], eax
0x18004f4af  lea     rax, [rbx+14h]
0x18004f4b3  lea     rcx, [rbp+var_20]
0x18004f4b7  mov     [rsp+60h+var_28], rcx; int *
0x18004f4bc  mov     [rsp+60h+var_30], 5; unsigned int
0x18004f4c4  mov     [rsp+60h+var_38], r13d; int
0x18004f4c9  mov     [rsp+60h+var_40], rax; unsigned int *
0x18004f4ce  lea     r9d, [rdi+4]; unsigned int
0x18004f4d2  lea     r8, off_18006ACF0; struct _XC_STRING_VALUE_MAPPING *
0x18004f4d9  lea     rdx, aOnexAuthmode; "OneX:authMode"
0x18004f4e0  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f4e4  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18004f4e9  mov     edi, eax
0x18004f4eb  test    eax, eax
0x18004f4ed  jnz     short loc_18004F55B
0x18004f4ef  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18004f4f3  mov     eax, [rbp+var_20]
0x18004f4f6  and     eax, r13d
0x18004f4f9  shl     eax, 2
0x18004f4fc  or      [rbx+8], eax
0x18004f4ff  mov     rdx, rbx; struct _ONEX_CONNECTION_PROFILE *
0x18004f502  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f506  call    ?XopParseSingleSignOn@@YAKPEAUIXMLDOMNode@@PEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z; XopParseSingleSignOn(IXMLDOMNode *,_ONEX_CONNECTION_PROFILE *,ulong *)
0x18004f50b  mov     edi, eax
0x18004f50d  test    eax, eax
0x18004f50f  jnz     short loc_18004F55B
0x18004f511  lea     rdx, [rbx+3Ch]
0x18004f515  lea     ecx, [rax+20h]
0x18004f518  call    GetAlignedSize
0x18004f51d  mov     edi, eax
0x18004f51f  test    eax, eax
0x18004f521  jnz     short loc_18004F55B
0x18004f523  lea     rdx, [rbx+40h]
0x18004f527  lea     ecx, [rax+44h]
0x18004f52a  call    GetAlignedSize
0x18004f52f  mov     edi, eax
0x18004f531  test    eax, eax
0x18004f533  jnz     short loc_18004F55B
0x18004f535  mov     r9, r14; unsigned int *
0x18004f538  lea     r8, [rbp+var_10]; struct _ONEX_CONNECTION_PROFILE **
0x18004f53c  mov     rdx, [rbp+var_18]; struct IXMLDOMNode *
0x18004f540  mov     ecx, r15d; unsigned int
0x18004f543  call    ?XopParseEapConfig@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z; XopParseEapConfig(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)
0x18004f548  mov     edi, eax
0x18004f54a  test    eax, eax
0x18004f54c  jnz     short loc_18004F557
0x18004f54e  mov     rax, [rbp+var_10]
0x18004f552  mov     [rsi], rax
0x18004f555  jmp     short loc_18004F569
0x18004f557  mov     rbx, [rbp+var_10]
0x18004f55b  test    rbx, rbx
0x18004f55e  jz      short loc_18004F569
0x18004f560  mov     rcx, rbx; lpMem
0x18004f563  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18004f568  nop
0x18004f569  lea     rcx, [rbp+var_18]
0x18004f56d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004f572  nop
0x18004f573  mov     eax, edi
0x18004f575  add     rsp, 60h
0x18004f579  pop     r15
0x18004f57b  pop     r14
0x18004f57d  pop     r13
0x18004f57f  pop     rdi
0x18004f580  pop     rsi
0x18004f581  pop     rbx
0x18004f582  pop     rbp
0x18004f583  retn
```
