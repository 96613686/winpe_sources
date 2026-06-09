# XwpGenerateSecuritySettings(_DOT11_MSM_SECURITY_SETTINGS *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18000e9e0`
- end: `0x18000ec93`
- name: `?XwpGenerateSecuritySettings@@YAKPEAU_DOT11_MSM_SECURITY_SETTINGS@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `691`
- prototype: `unsigned int(struct _DOT11_MSM_SECURITY_SETTINGS *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800450b4`

## callees

- `0x18000e9e0`
- `0x18000ec9c`
- `0x18000ef6c`
- `0x18000f7a8`
- `0x180018388`
- `0x180018a10`
- `0x18004e4a4`
- `0x18004efd0`
- `0x180062010`

## string_xrefs

- `0x18000ea2d`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18000ea82`: `security`
- `0x18000eb3d`: `PMKCacheMode`
- `0x18000eb70`: `PMKCacheTTL`
- `0x18000eb9b`: `PMKCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall XwpGenerateSecuritySettings(
        struct _DOT11_MSM_SECURITY_SETTINGS *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int SingleNode; // esi
  struct IXMLDOMNode *v7; // rbx
  __int64 v8; // rdi
  struct _ONEX_CONNECTION_PROFILE *v9; // rcx
  struct IXMLDOMNode **v11; // [rsp+28h] [rbp-40h]
  struct IXMLDOMNode **v12; // [rsp+38h] [rbp-30h]
  struct IXMLDOMNode *v13; // [rsp+70h] [rbp+8h] BYREF
  struct IXMLDOMNode *v14; // [rsp+88h] [rbp+20h] BYREF

  SingleNode = 0;
  v13 = 0;
  v7 = 0;
  v14 = 0;
  v8 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    SingleNode = XcGetSingleNode(a3, L"WLANProfile:MSM", &v13);
    if ( SingleNode == 1168 )
      SingleNode = XcAddChildElement(
                     a2,
                     a3,
                     (OLECHAR *)L"MSM",
                     (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                     0,
                     &v13);
    if ( !SingleNode )
    {
      SingleNode = XcAddChildElement(
                     a2,
                     v13,
                     (OLECHAR *)L"security",
                     (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                     0,
                     &v14);
      v7 = v14;
      if ( !SingleNode )
      {
        if ( !*(_DWORD *)(v8 + 16) )
          goto LABEL_25;
        if ( *(_QWORD *)(v8 + 24) )
        {
          SingleNode = XwpGenerateAuthEncryptionPair((struct DOT11_MSMSEC_CONNECTION_PROFILE *)v8, a2, v14);
          if ( SingleNode )
            goto LABEL_29;
          SingleNode = XwpGenerateSharedKey((struct DOT11_MSMSEC_CONNECTION_PROFILE *)v8, a2, v7);
          if ( SingleNode )
            goto LABEL_29;
          if ( (*(_BYTE *)v8 & 4) != 0 )
          {
            SingleNode = XcAddChildElementDWORD(
                           a2,
                           v7,
                           (OLECHAR *)L"keyIndex",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 56),
                           v11);
            if ( SingleNode )
              goto LABEL_29;
          }
          if ( (*(_BYTE *)v8 & 0x20) != 0 )
          {
            SingleNode = XcAddChildElementEnum(
                           a2,
                           v7,
                           (OLECHAR *)L"PMKCacheMode",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 112),
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_18006A840,
                           2u,
                           v12);
            if ( SingleNode )
              goto LABEL_29;
          }
          if ( *(char *)v8 < 0 )
          {
            SingleNode = XcAddChildElementDWORD(
                           a2,
                           v7,
                           (OLECHAR *)L"PMKCacheTTL",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 120) / 0x3Cu,
                           v11);
            if ( SingleNode )
              goto LABEL_29;
          }
          if ( (*(_BYTE *)v8 & 0x40) != 0 )
          {
            SingleNode = XcAddChildElementDWORD(
                           a2,
                           v7,
                           (OLECHAR *)L"PMKCacheSize",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 116),
                           v11);
            if ( SingleNode )
              goto LABEL_29;
          }
          if ( (*(_BYTE *)v8 & 8) != 0 )
          {
            SingleNode = XcAddChildElementEnum(
                           a2,
                           v7,
                           (OLECHAR *)L"preAuthMode",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 104),
                           (const struct _XC_STRING_VALUE_MAPPING *)&off_18006A860,
                           2u,
                           v12);
            if ( SingleNode )
              goto LABEL_29;
          }
          if ( (*(_BYTE *)v8 & 0x10) != 0 )
          {
            SingleNode = XcAddChildElementDWORD(
                           a2,
                           v7,
                           (OLECHAR *)L"preAuthThrottle",
                           (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                           *(_DWORD *)(v8 + 108),
                           v11);
            if ( SingleNode )
              goto LABEL_29;
          }
        }
        if ( !*(_DWORD *)(v8 + 16) || !*(_QWORD *)(v8 + 24) || !*(_DWORD *)(v8 + 32) )
        {
LABEL_25:
          if ( !*((_DWORD *)a1 + 3) )
            goto LABEL_29;
        }
        if ( *(_DWORD *)(v8 + 40) )
        {
          v9 = *(struct _ONEX_CONNECTION_PROFILE **)(v8 + 48);
          if ( v9 )
            SingleNode = XoGenerateOnexProfile(v9, a2, v7);
        }
      }
    }
  }
LABEL_29:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  if ( v13 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
  return SingleNode;
}

```

## disassembly

```asm
0x18000e9e0  mov     rax, rsp
0x18000e9e3  mov     [rax+10h], rbx
0x18000e9e7  mov     [rax+18h], rbp
0x18000e9eb  push    rsi
0x18000e9ec  push    rdi
0x18000e9ed  push    r13
0x18000e9ef  push    r14
0x18000e9f1  push    r15
0x18000e9f3  sub     rsp, 40h
0x18000e9f7  mov     r14, r8
0x18000e9fa  mov     rbp, rdx
0x18000e9fd  mov     r15, rcx
0x18000ea00  xor     esi, esi
0x18000ea02  mov     [rax+8], rsi
0x18000ea06  xor     ebx, ebx
0x18000ea08  mov     [rax+20h], rbx
0x18000ea0c  mov     rdi, [rcx]
0x18000ea0f  test    rdi, rdi
0x18000ea12  jz      loc_18000EC4C
0x18000ea18  lea     r8, [rax+8]; struct IXMLDOMNode **
0x18000ea1c  lea     rdx, aWlanprofileMsm_1; "WLANProfile:MSM"
0x18000ea23  mov     rcx, r14; struct IXMLDOMNode *
0x18000ea26  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000ea2b  mov     esi, eax
0x18000ea2d  lea     r13, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18000ea34  cmp     eax, 490h
0x18000ea39  jnz     short loc_18000EA61
0x18000ea3b  lea     rax, [rsp+68h+arg_0]
0x18000ea40  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18000ea45  mov     [rsp+68h+var_48], rbx; OLECHAR *
0x18000ea4a  mov     r9, r13; OLECHAR *
0x18000ea4d  lea     r8, aMsm; "MSM"
0x18000ea54  mov     rdx, r14; struct IXMLDOMNode *
0x18000ea57  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000ea5a  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ea5f  mov     esi, eax
0x18000ea61  test    esi, esi
0x18000ea63  jnz     loc_18000EC4C
0x18000ea69  lea     rax, [rsp+68h+arg_18]
0x18000ea71  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18000ea76  mov     [rsp+68h+var_48], 0; OLECHAR *
0x18000ea7f  mov     r9, r13; OLECHAR *
0x18000ea82  lea     r8, aSecurity_0; "security"
0x18000ea89  mov     rdx, [rsp+68h+arg_0]; struct IXMLDOMNode *
0x18000ea8e  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000ea91  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000ea96  mov     esi, eax
0x18000ea98  mov     rbx, [rsp+68h+arg_18]
0x18000eaa0  test    eax, eax
0x18000eaa2  jnz     loc_18000EC4C
0x18000eaa8  cmp     [rdi+10h], eax
0x18000eaab  jz      loc_18000EC29
0x18000eab1  cmp     qword ptr [rdi+18h], 0
0x18000eab6  jz      loc_18000EC16
0x18000eabc  mov     r8, rbx; struct IXMLDOMNode *
0x18000eabf  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18000eac2  mov     rcx, rdi; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18000eac5  call    ?XwpGenerateAuthEncryptionPair@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateAuthEncryptionPair(DOT11_MSMSEC_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18000eaca  mov     esi, eax
0x18000eacc  test    eax, eax
0x18000eace  jnz     loc_18000EC4C
0x18000ead4  mov     r8, rbx; struct IXMLDOMNode *
0x18000ead7  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18000eada  mov     rcx, rdi; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18000eadd  call    ?XwpGenerateSharedKey@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateSharedKey(DOT11_MSMSEC_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18000eae2  mov     esi, eax
0x18000eae4  test    eax, eax
0x18000eae6  jnz     loc_18000EC4C
0x18000eaec  test    byte ptr [rdi], 4
0x18000eaef  jz      short loc_18000EB17
0x18000eaf1  mov     eax, [rdi+38h]
0x18000eaf4  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18000eaf8  mov     r9, r13; OLECHAR *
0x18000eafb  lea     r8, aKeyindex; "keyIndex"
0x18000eb02  mov     rdx, rbx; struct IXMLDOMNode *
0x18000eb05  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000eb08  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000eb0d  mov     esi, eax
0x18000eb0f  test    eax, eax
0x18000eb11  jnz     loc_18000EC4C
0x18000eb17  mov     r14d, 2
0x18000eb1d  test    byte ptr [rdi], 20h
0x18000eb20  jz      short loc_18000EB59
0x18000eb22  mov     [rsp+68h+var_38], r14d; unsigned int
0x18000eb27  lea     rax, off_18006A840; "disabled"
0x18000eb2e  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18000eb33  mov     eax, [rdi+70h]
0x18000eb36  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18000eb3a  mov     r9, r13; OLECHAR *
0x18000eb3d  lea     r8, aPmkcachemode; "PMKCacheMode"
0x18000eb44  mov     rdx, rbx; struct IXMLDOMNode *
0x18000eb47  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000eb4a  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000eb4f  mov     esi, eax
0x18000eb51  test    eax, eax
0x18000eb53  jnz     loc_18000EC4C
0x18000eb59  test    byte ptr [rdi], 80h
0x18000eb5c  jz      short loc_18000EB8C
0x18000eb5e  mov     eax, 88888889h
0x18000eb63  mul     dword ptr [rdi+78h]
0x18000eb66  shr     edx, 5
0x18000eb69  mov     dword ptr [rsp+68h+var_48], edx; unsigned int
0x18000eb6d  mov     r9, r13; OLECHAR *
0x18000eb70  lea     r8, aPmkcachettl; "PMKCacheTTL"
0x18000eb77  mov     rdx, rbx; struct IXMLDOMNode *
0x18000eb7a  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000eb7d  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000eb82  mov     esi, eax
0x18000eb84  test    eax, eax
0x18000eb86  jnz     loc_18000EC4C
0x18000eb8c  test    byte ptr [rdi], 40h
0x18000eb8f  jz      short loc_18000EBB7
0x18000eb91  mov     eax, [rdi+74h]
0x18000eb94  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18000eb98  mov     r9, r13; OLECHAR *
0x18000eb9b  lea     r8, aPmkcachesize; "PMKCacheSize"
0x18000eba2  mov     rdx, rbx; struct IXMLDOMNode *
0x18000eba5  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000eba8  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000ebad  mov     esi, eax
0x18000ebaf  test    eax, eax
0x18000ebb1  jnz     loc_18000EC4C
0x18000ebb7  test    byte ptr [rdi], 8
0x18000ebba  jz      short loc_18000EBEF
0x18000ebbc  mov     [rsp+68h+var_38], r14d; unsigned int
0x18000ebc1  lea     rax, off_18006A860; "disabled"
0x18000ebc8  mov     [rsp+68h+var_40], rax; struct IXMLDOMNode **
0x18000ebcd  mov     eax, [rdi+68h]
0x18000ebd0  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18000ebd4  mov     r9, r13; OLECHAR *
0x18000ebd7  lea     r8, aPreauthmode; "preAuthMode"
0x18000ebde  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ebe1  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000ebe4  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000ebe9  mov     esi, eax
0x18000ebeb  test    eax, eax
0x18000ebed  jnz     short loc_18000EC4C
0x18000ebef  test    byte ptr [rdi], 10h
0x18000ebf2  jz      short loc_18000EC16
0x18000ebf4  mov     eax, [rdi+6Ch]
0x18000ebf7  mov     dword ptr [rsp+68h+var_48], eax; unsigned int
0x18000ebfb  mov     r9, r13; OLECHAR *
0x18000ebfe  lea     r8, aPreauththrottl; "preAuthThrottle"
0x18000ec05  mov     rdx, rbx; struct IXMLDOMNode *
0x18000ec08  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000ec0b  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18000ec10  mov     esi, eax
0x18000ec12  test    eax, eax
0x18000ec14  jnz     short loc_18000EC4C
0x18000ec16  cmp     dword ptr [rdi+10h], 0
0x18000ec1a  jz      short loc_18000EC29
0x18000ec1c  cmp     qword ptr [rdi+18h], 0
0x18000ec21  jz      short loc_18000EC29
0x18000ec23  cmp     dword ptr [rdi+20h], 0
0x18000ec27  jnz     short loc_18000EC30
0x18000ec29  cmp     dword ptr [r15+0Ch], 0
0x18000ec2e  jz      short loc_18000EC4C
0x18000ec30  cmp     dword ptr [rdi+28h], 0
0x18000ec34  jz      short loc_18000EC4C
0x18000ec36  mov     rcx, [rdi+30h]; struct _ONEX_CONNECTION_PROFILE *
0x18000ec3a  test    rcx, rcx
0x18000ec3d  jz      short loc_18000EC4C
0x18000ec3f  mov     r8, rbx; struct IXMLDOMNode *
0x18000ec42  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18000ec45  call    ?XoGenerateOnexProfile@@YAKPEAU_ONEX_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XoGenerateOnexProfile(_ONEX_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18000ec4a  mov     esi, eax
0x18000ec4c  test    rbx, rbx
0x18000ec4f  jz      short loc_18000EC61
0x18000ec51  mov     rax, [rbx]
0x18000ec54  mov     rcx, rbx
0x18000ec57  mov     rax, [rax+10h]
0x18000ec5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec60  nop
0x18000ec61  mov     rcx, [rsp+68h+arg_0]
0x18000ec66  test    rcx, rcx
0x18000ec69  jz      short loc_18000EC78
0x18000ec6b  mov     rax, [rcx]
0x18000ec6e  mov     rax, [rax+10h]
0x18000ec72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec77  nop
0x18000ec78  mov     eax, esi
0x18000ec7a  lea     r11, [rsp+68h+var_28]
0x18000ec7f  mov     rbx, [r11+38h]
0x18000ec83  mov     rbp, [r11+40h]
0x18000ec87  mov     rsp, r11
0x18000ec8a  pop     r15
0x18000ec8c  pop     r14
0x18000ec8e  pop     r13
0x18000ec90  pop     rdi
0x18000ec91  pop     rsi
0x18000ec92  retn
```
