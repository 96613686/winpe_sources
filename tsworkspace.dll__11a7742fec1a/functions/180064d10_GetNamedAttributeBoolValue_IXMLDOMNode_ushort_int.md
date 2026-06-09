# GetNamedAttributeBoolValue(IXMLDOMNode *,ushort *,int &)

- ea: `0x180064d10`
- end: `0x1800651a9`
- name: `?GetNamedAttributeBoolValue@@YAJPEAUIXMLDOMNode@@PEAGAEAH@Z`
- size: `1177`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062b0c`

## callees

- `0x1800054c4`
- `0x180005524`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x180020bf0`
- `0x180064d10`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18006501d`
- `OLEAUT32!__imp_SysStringLen` at `0x18006501d`
- `OLEAUT32!__imp_VariantInit` at `0x180064d45`
- `OLEAUT32!__imp_VariantInit` at `0x180064d45`
- `OLEAUT32!__imp_VariantClear` at `0x180065180`
- `OLEAUT32!__imp_VariantClear` at `0x180065180`
- `KERNEL32!CompareStringOrdinal` at `0x180065092`
- `KERNEL32!CompareStringOrdinal` at `0x1800650b9`
- `KERNEL32!CompareStringOrdinal` at `0x1800650e0`
- `KERNEL32!CompareStringOrdinal` at `0x180065107`
- `KERNEL32!CompareStringOrdinal` at `0x180065092`
- `KERNEL32!CompareStringOrdinal` at `0x1800650b9`
- `KERNEL32!CompareStringOrdinal` at `0x1800650e0`
- `KERNEL32!CompareStringOrdinal` at `0x180065107`

## string_xrefs

- `0x180064e2e`: `IXMLDOMNode::get_attributes failed`
- `0x180064f09`: `IXMLDOMNamedNodeMap::getNamedItem failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetNamedAttributeBoolValue(struct IXMLDOMNode *a1, unsigned __int16 *a2, int *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  int v9; // ebx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  UINT v17; // eax
  int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // eax
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+70h] [rbp+20h] BYREF
  __int64 v25; // [rsp+88h] [rbp+38h] BYREF

  v25 = 0;
  v24 = 0;
  VariantInit(&pvarg);
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 17;
    v8 = "pNode";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8);
LABEL_7:
    v9 = -2147467261;
    goto LABEL_64;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 18;
    v8 = "bstrAttributeName";
    goto LABEL_6;
  }
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a1->lpVtbl->get_attributes)(a1, &v25);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 19;
      v12 = "IXMLDOMNode::get_attributes failed";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
        v10,
        (__int64)v12,
        v9,
        -2);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  if ( !v25 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 20;
LABEL_24:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
      v13,
      -2147418113);
LABEL_25:
    v9 = -2147418113;
    goto LABEL_64;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 *))(*(_QWORD *)v25 + 56LL))(v25, a2, &v24);
  if ( v9 >= 0 )
  {
    if ( !v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v15,
          -2147023728);
      }
      v9 = -2147023728;
      goto LABEL_64;
    }
    if ( (*(unsigned int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v24 + 64LL))(v24, &pvarg) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids, v16);
      }
    }
    else
    {
      if ( pvarg.vt != 8 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_25;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 24;
        goto LABEL_24;
      }
      v17 = SysStringLen(pvarg.bstrVal);
      v18 = v17;
      if ( v17 )
      {
        if ( CompareStringOrdinal(pvarg.bstrVal, v17, L"true", -1, 0) == 2
          || CompareStringOrdinal(pvarg.bstrVal, v18, L"1", -1, 0) == 2 )
        {
          v21 = 1;
        }
        else
        {
          if ( CompareStringOrdinal(pvarg.bstrVal, v18, L"false", -1, 0) != 2
            && CompareStringOrdinal(pvarg.bstrVal, v18, L"0", -1, 0) != 2 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                (unsigned int)&WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
                v20,
                pvarg.llVal);
            }
            goto LABEL_42;
          }
          v21 = 0;
        }
        *a3 = v21;
        v9 = 0;
        goto LABEL_64;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids,
          v19,
          -2147220988);
      }
    }
LABEL_42:
    v9 = -2147220988;
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 21;
    v12 = "IXMLDOMNamedNodeMap::getNamedItem failed";
    goto LABEL_18;
  }
LABEL_64:
  VariantClear(&pvarg);
  ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(&v24);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180064d10  push    rbp
0x180064d12  push    rsi
0x180064d13  push    rdi
0x180064d14  mov     rbp, rsp
0x180064d17  sub     rsp, 50h
0x180064d1b  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180064d23  mov     [rsp+50h+arg_8], rbx
0x180064d28  mov     rsi, r8
0x180064d2b  mov     rdi, rdx
0x180064d2e  mov     rbx, rcx
0x180064d31  mov     [rbp+arg_18], 0
0x180064d39  mov     [rbp+arg_0], 0
0x180064d41  lea     rcx, [rbp+pvarg]; pvarg
0x180064d45  call    cs:__imp_VariantInit
0x180064d4b  nop
0x180064d4c  test    rbx, rbx
0x180064d4f  jnz     short loc_180064DA8
0x180064d51  lea     rax, WPP_GLOBAL_Control
0x180064d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180064d5f  cmp     rcx, rax
0x180064d62  jz      short loc_180064D9E
0x180064d64  test    byte ptr [rcx+1Ch], 8
0x180064d68  jz      short loc_180064D9E
0x180064d6a  cmp     byte ptr [rcx+19h], 2
0x180064d6e  jb      short loc_180064D9E
0x180064d70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064d75  lea     edx, [rbx+11h]
0x180064d78  lea     rcx, aPnode; "pNode"
0x180064d7f  mov     qword ptr [rsp+50h+bIgnoreCase], rcx
0x180064d84  mov     r9d, eax
0x180064d87  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180064d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064d95  mov     rcx, [rcx+10h]
0x180064d99  call    WPP_SF_Ds
0x180064d9e  mov     ebx, 80004003h
0x180064da3  jmp     loc_18006517C
0x180064da8  test    rdi, rdi
0x180064dab  jnz     short loc_180064DDD
0x180064dad  lea     rax, WPP_GLOBAL_Control
0x180064db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180064dbb  cmp     rcx, rax
0x180064dbe  jz      short loc_180064D9E
0x180064dc0  test    byte ptr [rcx+1Ch], 8
0x180064dc4  jz      short loc_180064D9E
0x180064dc6  cmp     byte ptr [rcx+19h], 2
0x180064dca  jb      short loc_180064D9E
0x180064dcc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064dd1  lea     edx, [rdi+12h]
0x180064dd4  lea     rcx, aBstrattributen; "bstrAttributeName"
0x180064ddb  jmp     short loc_180064D7F
0x180064ddd  mov     rax, [rbx]
0x180064de0  lea     rdx, [rbp+arg_18]
0x180064de4  mov     rcx, rbx
0x180064de7  mov     rax, [rax+88h]
0x180064dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064df3  mov     ebx, eax
0x180064df5  test    eax, eax
0x180064df7  jns     short loc_180064E5D
0x180064df9  lea     rax, WPP_GLOBAL_Control
0x180064e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e07  cmp     rcx, rax
0x180064e0a  jz      loc_18006517C
0x180064e10  test    byte ptr [rcx+1Ch], 8
0x180064e14  jz      loc_18006517C
0x180064e1a  cmp     byte ptr [rcx+19h], 2
0x180064e1e  jb      loc_18006517C
0x180064e24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064e29  mov     edx, 13h
0x180064e2e  lea     rcx, aIxmldomnodeGet; "IXMLDOMNode::get_attributes failed"
0x180064e35  mov     [rsp+50h+var_28], ebx
0x180064e39  mov     qword ptr [rsp+50h+bIgnoreCase], rcx
0x180064e3e  mov     r9d, eax
0x180064e41  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180064e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e4f  mov     rcx, [rcx+10h]
0x180064e53  call    WPP_SF_DsD
0x180064e58  jmp     loc_18006517C
0x180064e5d  mov     rcx, [rbp+arg_18]
0x180064e61  test    rcx, rcx
0x180064e64  jnz     short loc_180064EBB
0x180064e66  lea     rax, WPP_GLOBAL_Control
0x180064e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064e74  cmp     rcx, rax
0x180064e77  jz      short loc_180064EB1
0x180064e79  test    byte ptr [rcx+1Ch], 8
0x180064e7d  jz      short loc_180064EB1
0x180064e7f  cmp     byte ptr [rcx+19h], 2
0x180064e83  jb      short loc_180064EB1
0x180064e85  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064e8a  mov     edx, 14h
0x180064e8f  mov     [rsp+50h+bIgnoreCase], 8000FFFFh
0x180064e97  mov     r9d, eax
0x180064e9a  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180064ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180064ea8  mov     rcx, [rcx+10h]
0x180064eac  call    WPP_SF_Dd
0x180064eb1  mov     ebx, 8000FFFFh
0x180064eb6  jmp     loc_18006517C
0x180064ebb  mov     rax, [rcx]
0x180064ebe  lea     r8, [rbp+arg_0]
0x180064ec2  mov     rdx, rdi
0x180064ec5  mov     rax, [rax+38h]
0x180064ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ece  mov     ebx, eax
0x180064ed0  test    eax, eax
0x180064ed2  jns     short loc_180064F15
0x180064ed4  lea     rax, WPP_GLOBAL_Control
0x180064edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180064ee2  cmp     rcx, rax
0x180064ee5  jz      loc_18006517C
0x180064eeb  test    byte ptr [rcx+1Ch], 8
0x180064eef  jz      loc_18006517C
0x180064ef5  cmp     byte ptr [rcx+19h], 2
0x180064ef9  jb      loc_18006517C
0x180064eff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064f04  mov     edx, 15h
0x180064f09  lea     rcx, aIxmldomnamedno; "IXMLDOMNamedNodeMap::getNamedItem faile"...
0x180064f10  jmp     loc_180064E35
0x180064f15  mov     rcx, [rbp+arg_0]
0x180064f19  test    rcx, rcx
0x180064f1c  jnz     short loc_180064F73
0x180064f1e  lea     rax, WPP_GLOBAL_Control
0x180064f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180064f2c  cmp     rcx, rax
0x180064f2f  jz      short loc_180064F69
0x180064f31  test    byte ptr [rcx+1Ch], 8
0x180064f35  jz      short loc_180064F69
0x180064f37  cmp     byte ptr [rcx+19h], 2
0x180064f3b  jb      short loc_180064F69
0x180064f3d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064f42  mov     edx, 16h
0x180064f47  mov     [rsp+50h+bIgnoreCase], 80070490h
0x180064f4f  mov     r9d, eax
0x180064f52  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180064f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180064f60  mov     rcx, [rcx+10h]
0x180064f64  call    WPP_SF_Dd
0x180064f69  mov     ebx, 80070490h
0x180064f6e  jmp     loc_18006517C
0x180064f73  mov     rax, [rcx]
0x180064f76  lea     rdx, [rbp+pvarg]
0x180064f7a  mov     rax, [rax+40h]
0x180064f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f83  test    eax, eax
0x180064f85  jz      short loc_180064FD8
0x180064f87  lea     rax, WPP_GLOBAL_Control
0x180064f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064f95  cmp     rcx, rax
0x180064f98  jz      short loc_180064FCE
0x180064f9a  mov     eax, 1
0x180064f9f  test    [rcx+1Ch], al
0x180064fa2  jz      short loc_180064FCE
0x180064fa4  cmp     byte ptr [rcx+19h], 2
0x180064fa8  jb      short loc_180064FCE
0x180064faa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064faf  mov     edx, 17h
0x180064fb4  mov     r9d, eax
0x180064fb7  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180064fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180064fc5  mov     rcx, [rcx+10h]
0x180064fc9  call    WPP_SF_D
0x180064fce  mov     ebx, 80040204h
0x180064fd3  jmp     loc_18006517C
0x180064fd8  cmp     word ptr [rbp+pvarg], 8
0x180064fdd  jz      short loc_180065019
0x180064fdf  lea     rax, WPP_GLOBAL_Control
0x180064fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180064fed  cmp     rcx, rax
0x180064ff0  jz      loc_180064EB1
0x180064ff6  test    byte ptr [rcx+1Ch], 8
0x180064ffa  jz      loc_180064EB1
0x180065000  cmp     byte ptr [rcx+19h], 2
0x180065004  jb      loc_180064EB1
0x18006500a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006500f  mov     edx, 18h
0x180065014  jmp     loc_180064E8F
0x180065019  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x18006501d  call    cs:__imp_SysStringLen
0x180065023  mov     ebx, eax
0x180065025  test    eax, eax
0x180065027  jnz     short loc_180065077
0x180065029  lea     rax, WPP_GLOBAL_Control
0x180065030  mov     rcx, cs:WPP_GLOBAL_Control
0x180065037  cmp     rcx, rax
0x18006503a  jz      short loc_180064FCE
0x18006503c  test    byte ptr [rcx+1Ch], 8
0x180065040  jz      short loc_180064FCE
0x180065042  cmp     byte ptr [rcx+19h], 2
0x180065046  jb      short loc_180064FCE
0x180065048  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006504d  lea     edx, [rbx+19h]
0x180065050  mov     [rsp+50h+bIgnoreCase], 80040204h
0x180065058  mov     r9d, eax
0x18006505b  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x180065062  mov     rcx, cs:WPP_GLOBAL_Control
0x180065069  mov     rcx, [rcx+10h]
0x18006506d  call    WPP_SF_Dd
0x180065072  jmp     loc_180064FCE
0x180065077  mov     [rsp+50h+bIgnoreCase], 0; bIgnoreCase
0x18006507f  or      edi, 0FFFFFFFFh
0x180065082  mov     r9d, edi; cchCount2
0x180065085  lea     r8, aTrue; "true"
0x18006508c  mov     edx, ebx; cchCount1
0x18006508e  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x180065092  call    cs:__imp_CompareStringOrdinal
0x180065098  cmp     eax, 2
0x18006509b  jz      loc_180065173
0x1800650a1  mov     [rsp+50h+bIgnoreCase], 0; bIgnoreCase
0x1800650a9  mov     r9d, edi; cchCount2
0x1800650ac  lea     r8, a1; "1"
0x1800650b3  mov     edx, ebx; cchCount1
0x1800650b5  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x1800650b9  call    cs:__imp_CompareStringOrdinal
0x1800650bf  cmp     eax, 2
0x1800650c2  jz      loc_180065173
0x1800650c8  mov     [rsp+50h+bIgnoreCase], 0; bIgnoreCase
0x1800650d0  mov     r9d, edi; cchCount2
0x1800650d3  lea     r8, aFalse; "false"
0x1800650da  mov     edx, ebx; cchCount1
0x1800650dc  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x1800650e0  call    cs:__imp_CompareStringOrdinal
0x1800650e6  cmp     eax, 2
0x1800650e9  jz      loc_18006516F
0x1800650ef  mov     [rsp+50h+bIgnoreCase], 0; bIgnoreCase
0x1800650f7  mov     r9d, edi; cchCount2
0x1800650fa  lea     r8, a0; "0"
0x180065101  mov     edx, ebx; cchCount1
0x180065103  mov     rcx, qword ptr [rbp+pvarg+8]; lpString1
0x180065107  call    cs:__imp_CompareStringOrdinal
0x18006510d  cmp     eax, 2
0x180065110  jz      short loc_18006516F
0x180065112  lea     rax, WPP_GLOBAL_Control
0x180065119  mov     rcx, cs:WPP_GLOBAL_Control
0x180065120  cmp     rcx, rax
0x180065123  jz      loc_180064FCE
0x180065129  lea     eax, [rdi+2]
0x18006512c  test    [rcx+1Ch], al
0x18006512f  jz      loc_180064FCE
0x180065135  cmp     byte ptr [rcx+19h], 2
0x180065139  jb      loc_180064FCE
0x18006513f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180065144  lea     edx, [rdi+1Bh]
0x180065147  mov     rcx, qword ptr [rbp+pvarg+8]
0x18006514b  mov     qword ptr [rsp+50h+bIgnoreCase], rcx
0x180065150  mov     r9d, eax
0x180065153  lea     r8, WPP_c9dbf043807c3ca10c92d133ddc5d7c2_Traceguids
0x18006515a  mov     rcx, cs:WPP_GLOBAL_Control
0x180065161  mov     rcx, [rcx+10h]
0x180065165  call    WPP_SF_DS
0x18006516a  jmp     loc_180064FCE
0x18006516f  xor     eax, eax
0x180065171  jmp     short loc_180065178
0x180065173  mov     eax, 1
0x180065178  mov     [rsi], eax
0x18006517a  xor     ebx, ebx
0x18006517c  lea     rcx, [rbp+pvarg]; pvarg
0x180065180  call    cs:__imp_VariantClear
0x180065186  nop
0x180065187  lea     rcx, [rbp+arg_0]
0x18006518b  call    ??1?$ComPlainSmartPtr@UIRADCWorkspaceManager@@@@QEAA@XZ; ComPlainSmartPtr<IRADCWorkspaceManager>::~ComPlainSmartPtr<IRADCWorkspaceManager>(void)
0x180065190  nop
0x180065191  lea     rcx, [rbp+arg_18]
0x180065195  call    ??1?$ComPlainSmartPtr@UIXMLDOMNamedNodeMap@@@@QEAA@XZ; ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(void)
0x18006519a  mov     eax, ebx
0x18006519c  mov     rbx, [rsp+50h+arg_8]
0x1800651a1  add     rsp, 50h
0x1800651a5  pop     rdi
0x1800651a6  pop     rsi
0x1800651a7  pop     rbp
0x1800651a8  retn
```
