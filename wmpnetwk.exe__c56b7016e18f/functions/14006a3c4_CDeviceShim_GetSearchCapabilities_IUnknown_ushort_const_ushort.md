# CDeviceShim::GetSearchCapabilities(IUnknown *,ushort const *,ushort * *)

- ea: `0x14006a3c4`
- end: `0x14006a6ba`
- name: `?GetSearchCapabilities@CDeviceShim@@SAJPEAUIUnknown@@PEBGPEAPEAG@Z`
- size: `758`
- prototype: `__int64 __fastcall(struct IUnknown *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14005c458`

## callees

- `0x140006d70`
- `0x14000b3b0`
- `0x14000c920`
- `0x14000e848`
- `0x14003d6ec`
- `0x140047798`
- `0x140054490`
- `0x140058900`
- `0x14006a3c4`
- `0x14006a964`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14006a4a0`
- `KERNEL32!CompareStringW` at `0x14006a4cc`
- `KERNEL32!CompareStringW` at `0x14006a4f4`
- `KERNEL32!CompareStringW` at `0x14006a51c`
- `KERNEL32!CompareStringW` at `0x14006a544`
- `KERNEL32!CompareStringW` at `0x14006a4a0`
- `KERNEL32!CompareStringW` at `0x14006a4cc`
- `KERNEL32!CompareStringW` at `0x14006a4f4`
- `KERNEL32!CompareStringW` at `0x14006a51c`
- `KERNEL32!CompareStringW` at `0x14006a544`
- `OLEAUT32!__imp_SysAllocString` at `0x14006a5d0`
- `OLEAUT32!__imp_SysAllocString` at `0x14006a5d0`
- `OLEAUT32!__imp_SysFreeString` at `0x14006a5bf`
- `OLEAUT32!__imp_SysFreeString` at `0x14006a5bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDeviceShim::GetSearchCapabilities(
        struct IUnknown *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v4; // ebx
  int v5; // esi
  int DeviceInfo; // ebx
  int v7; // eax
  unsigned __int16 *v8; // r8
  OLECHAR *psz; // [rsp+30h] [rbp-20h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+48h] [rbp-8h] BYREF
  PCNZWCH v14; // [rsp+98h] [rbp+48h] BYREF

  v4 = (int)a2;
  v5 = (int)a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)*a3);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v14);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v12);
  DeviceInfo = CDeviceShim::GetDeviceInfo(
                 v5,
                 v4,
                 (unsigned int)&lpString1,
                 (unsigned int)&v13,
                 (__int64)&v14,
                 (__int64)&v12);
  if ( DeviceInfo >= 0
    && CompareStringW(0x7Fu, 1u, lpString1, -1, L"Roku", -1) == 2
    && (CompareStringW(0x7Fu, 1u, v14, -1, L"M500", -1) == 2
     || CompareStringW(0x7Fu, 1u, v14, -1, L"M1000", -1) == 2
     || CompareStringW(0x7Fu, 1u, v14, -1, L"M2000", -1) == 2
     || CompareStringW(0x7Fu, 1u, v14, -1, L"R1000", -1) == 2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)&psz,
      (char *)*a3);
    ATL::CSimpleStringT<unsigned short,0>::Truncate(&psz, 255);
    v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::ReverseFind(
           &psz,
           44);
    if ( v7 > 0 )
      ATL::CSimpleStringT<unsigned short,0>::Truncate(&psz, (unsigned int)v7);
    if ( *a3 )
    {
      SysFreeString(*a3);
      *a3 = 0;
    }
    v8 = SysAllocString(psz);
    *a3 = v8;
    if ( !v8 )
      DeviceInfo = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((DeviceInfo >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids,
        DeviceInfo,
        (__int64)v8);
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&psz);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((DeviceInfo >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids,
      DeviceInfo,
      (__int64)*a3);
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v12);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v14);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v13);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
  return (unsigned int)DeviceInfo;
}

```

## disassembly

```asm
0x14006a3c4  mov     r11, rsp
0x14006a3c7  mov     [r11+8], rbx
0x14006a3cb  mov     [r11+10h], rsi
0x14006a3cf  push    rbp
0x14006a3d0  push    rdi
0x14006a3d1  push    r12
0x14006a3d3  push    r13
0x14006a3d5  push    r14
0x14006a3d7  mov     rbp, rsp
0x14006a3da  sub     rsp, 50h
0x14006a3de  mov     rdi, r8
0x14006a3e1  mov     rbx, rdx
0x14006a3e4  mov     rsi, rcx
0x14006a3e7  lea     r13, WPP_GLOBAL_Control
0x14006a3ee  mov     r14d, 1
0x14006a3f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a3fb  cmp     rcx, r13
0x14006a3fe  jz      short loc_14006A423
0x14006a400  test    [rcx+1Ch], r14b
0x14006a404  jz      short loc_14006A423
0x14006a406  cmp     byte ptr [rcx+19h], 5
0x14006a40a  jb      short loc_14006A423
0x14006a40c  mov     rax, [r8]
0x14006a40f  mov     [r11-50h], rax
0x14006a413  mov     [r11-58h], rdx
0x14006a417  mov     r9, rsi
0x14006a41a  mov     rcx, [rcx+10h]; LoggerHandle
0x14006a41e  call    WPP_SF_qSS
0x14006a423  lea     rcx, [rbp+lpString1]
0x14006a427  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14006a42c  nop
0x14006a42d  lea     rcx, [rbp+var_8]
0x14006a431  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14006a436  nop
0x14006a437  lea     rcx, [rbp+arg_18]
0x14006a43b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14006a440  nop
0x14006a441  lea     rcx, [rbp+var_10]
0x14006a445  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14006a44a  nop
0x14006a44b  lea     rax, [rbp+var_10]
0x14006a44f  mov     qword ptr [rsp+50h+cchCount2], rax
0x14006a454  lea     rax, [rbp+arg_18]
0x14006a458  mov     [rsp+50h+lpString2], rax
0x14006a45d  lea     r9, [rbp+var_8]
0x14006a461  lea     r8, [rbp+lpString1]
0x14006a465  mov     rdx, rbx
0x14006a468  mov     rcx, rsi
0x14006a46b  call    ?GetDeviceInfo@CDeviceShim@@CAJPEAUIUnknown@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@222@Z; CDeviceShim::GetDeviceInfo(IUnknown *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14006a470  mov     ebx, eax
0x14006a472  test    eax, eax
0x14006a474  js      loc_14006A632
0x14006a47a  or      esi, 0FFFFFFFFh
0x14006a47d  mov     [rsp+50h+cchCount2], esi; cchCount2
0x14006a481  lea     rax, aRoku; "Roku"
0x14006a488  mov     [rsp+50h+lpString2], rax; lpString2
0x14006a48d  mov     r9d, esi; cchCount1
0x14006a490  mov     r8, [rbp+lpString1]; lpString1
0x14006a494  mov     edx, r14d; dwCmpFlags
0x14006a497  mov     r12d, 7Fh
0x14006a49d  mov     ecx, r12d; Locale
0x14006a4a0  call    cs:__imp_CompareStringW
0x14006a4a6  cmp     eax, 2
0x14006a4a9  jnz     loc_14006A632
0x14006a4af  mov     [rsp+50h+cchCount2], esi; cchCount2
0x14006a4b3  lea     rax, aM500; "M500"
0x14006a4ba  mov     [rsp+50h+lpString2], rax; lpString2
0x14006a4bf  mov     r9d, esi; cchCount1
0x14006a4c2  mov     r8, [rbp+arg_18]; lpString1
0x14006a4c6  mov     edx, r14d; dwCmpFlags
0x14006a4c9  mov     ecx, r12d; Locale
0x14006a4cc  call    cs:__imp_CompareStringW
0x14006a4d2  cmp     eax, 2
0x14006a4d5  jz      short loc_14006A553
0x14006a4d7  mov     [rsp+50h+cchCount2], esi; cchCount2
0x14006a4db  lea     rax, aM1000; "M1000"
0x14006a4e2  mov     [rsp+50h+lpString2], rax; lpString2
0x14006a4e7  mov     r9d, esi; cchCount1
0x14006a4ea  mov     r8, [rbp+arg_18]; lpString1
0x14006a4ee  mov     edx, r14d; dwCmpFlags
0x14006a4f1  mov     ecx, r12d; Locale
0x14006a4f4  call    cs:__imp_CompareStringW
0x14006a4fa  cmp     eax, 2
0x14006a4fd  jz      short loc_14006A553
0x14006a4ff  mov     [rsp+50h+cchCount2], esi; cchCount2
0x14006a503  lea     rax, aM2000; "M2000"
0x14006a50a  mov     [rsp+50h+lpString2], rax; lpString2
0x14006a50f  mov     r9d, esi; cchCount1
0x14006a512  mov     r8, [rbp+arg_18]; lpString1
0x14006a516  mov     edx, r14d; dwCmpFlags
0x14006a519  mov     ecx, r12d; Locale
0x14006a51c  call    cs:__imp_CompareStringW
0x14006a522  cmp     eax, 2
0x14006a525  jz      short loc_14006A553
0x14006a527  mov     [rsp+50h+cchCount2], esi; cchCount2
0x14006a52b  lea     rax, aR1000; "R1000"
0x14006a532  mov     [rsp+50h+lpString2], rax; lpString2
0x14006a537  mov     r9d, esi; cchCount1
0x14006a53a  mov     r8, [rbp+arg_18]; lpString1
0x14006a53e  mov     edx, r14d; dwCmpFlags
0x14006a541  mov     ecx, r12d; Locale
0x14006a544  call    cs:__imp_CompareStringW
0x14006a54a  cmp     eax, 2
0x14006a54d  jnz     loc_14006A632
0x14006a553  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a55a  cmp     rcx, r13
0x14006a55d  jz      short loc_14006A580
0x14006a55f  test    byte ptr [rcx+1Ch], 2
0x14006a563  jz      short loc_14006A580
0x14006a565  cmp     byte ptr [rcx+19h], 4
0x14006a569  jb      short loc_14006A580
0x14006a56b  mov     edx, 0Bh
0x14006a570  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14006a577  mov     rcx, [rcx+10h]
0x14006a57b  call    WPP_SF_
0x14006a580  mov     rdx, [rdi]
0x14006a583  lea     rcx, [rbp+psz]
0x14006a587  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14006a58c  mov     edx, 0FFh
0x14006a591  lea     rcx, [rbp+psz]
0x14006a595  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x14006a59a  mov     edx, 2Ch ; ','
0x14006a59f  lea     rcx, [rbp+psz]
0x14006a5a3  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::ReverseFind(ushort)
0x14006a5a8  test    eax, eax
0x14006a5aa  jle     short loc_14006A5B7
0x14006a5ac  mov     edx, eax
0x14006a5ae  lea     rcx, [rbp+psz]
0x14006a5b2  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x14006a5b7  mov     rcx, [rdi]; bstrString
0x14006a5ba  test    rcx, rcx
0x14006a5bd  jz      short loc_14006A5CC
0x14006a5bf  call    cs:__imp_SysFreeString
0x14006a5c5  mov     qword ptr [rdi], 0
0x14006a5cc  mov     rcx, [rbp+psz]; psz
0x14006a5d0  call    cs:__imp_SysAllocString
0x14006a5d6  mov     r8, rax
0x14006a5d9  mov     [rdi], rax
0x14006a5dc  mov     eax, 8007000Eh
0x14006a5e1  test    r8, r8
0x14006a5e4  cmovz   ebx, eax
0x14006a5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a5ee  cmp     rcx, r13
0x14006a5f1  jz      short loc_14006A629
0x14006a5f3  test    byte ptr [rcx+1Ch], 2
0x14006a5f7  jz      short loc_14006A629
0x14006a5f9  mov     edx, ebx
0x14006a5fb  sar     edx, 1Fh
0x14006a5fe  and     edx, 0FFFFFFFDh
0x14006a601  add     edx, 5
0x14006a604  movzx   eax, byte ptr [rcx+19h]
0x14006a608  cmp     eax, edx
0x14006a60a  jb      short loc_14006A629
0x14006a60c  mov     edx, 0Ch
0x14006a611  mov     [rsp+50h+lpString2], r8
0x14006a616  mov     r9d, ebx
0x14006a619  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14006a620  mov     rcx, [rcx+10h]
0x14006a624  call    WPP_SF_dS
0x14006a629  lea     rcx, [rbp+psz]
0x14006a62d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006a632  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a639  cmp     rcx, r13
0x14006a63c  jz      short loc_14006A678
0x14006a63e  test    [rcx+1Ch], r14b
0x14006a642  jz      short loc_14006A678
0x14006a644  mov     edx, ebx
0x14006a646  sar     edx, 1Fh
0x14006a649  and     edx, 0FFFFFFFDh
0x14006a64c  add     edx, 5
0x14006a64f  movzx   eax, byte ptr [rcx+19h]
0x14006a653  cmp     eax, edx
0x14006a655  jb      short loc_14006A678
0x14006a657  mov     edx, 0Dh
0x14006a65c  mov     rax, [rdi]
0x14006a65f  mov     [rsp+50h+lpString2], rax
0x14006a664  mov     r9d, ebx
0x14006a667  lea     r8, WPP_08036f9138b83ef0e1e5ceefe9679dff_Traceguids
0x14006a66e  mov     rcx, [rcx+10h]
0x14006a672  call    WPP_SF_dS
0x14006a677  nop
0x14006a678  lea     rcx, [rbp+var_10]
0x14006a67c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006a681  nop
0x14006a682  lea     rcx, [rbp+arg_18]
0x14006a686  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006a68b  nop
0x14006a68c  lea     rcx, [rbp+var_8]
0x14006a690  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006a695  nop
0x14006a696  lea     rcx, [rbp+lpString1]
0x14006a69a  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14006a69f  mov     eax, ebx
0x14006a6a1  lea     r11, [rsp+50h+var_s0]
0x14006a6a6  mov     rbx, [r11+30h]
0x14006a6aa  mov     rsi, [r11+38h]
0x14006a6ae  mov     rsp, r11
0x14006a6b1  pop     r14
0x14006a6b3  pop     r13
0x14006a6b5  pop     r12
0x14006a6b7  pop     rdi
0x14006a6b8  pop     rbp
0x14006a6b9  retn
```
