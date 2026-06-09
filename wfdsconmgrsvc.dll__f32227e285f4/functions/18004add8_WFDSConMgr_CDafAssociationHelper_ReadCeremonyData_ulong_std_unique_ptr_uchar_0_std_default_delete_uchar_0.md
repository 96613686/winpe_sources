# WFDSConMgr::CDafAssociationHelper::ReadCeremonyData(ulong *,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &)

- ea: `0x18004add8`
- end: `0x18004b027`
- name: `?ReadCeremonyData@CDafAssociationHelper@WFDSConMgr@@QEAAXPEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005b210`

## callees

- `0x180002ffc`
- `0x180004260`
- `0x18000444e`
- `0x180006740`
- `0x180009c80`
- `0x180009e5c`
- `0x180009ff4`
- `0x18004add8`
- `0x18005c888`
- `0x18005df7c`
- `0x18006d010`

## string_xrefs

- `0x18004ae36`: `Must create association before calling Read Ceremony Data`
- `0x18004ae4f`: `WFDSConMgr::CDafAssociationHelper::ReadCeremonyData`
- `0x18004ae84`: `WFDSConMgr::CDafAssociationHelper::ReadCeremonyData`
- `0x18004aed1`: `WFDSConMgr::CDafAssociationHelper::ReadCeremonyData`
- `0x18004af1a`: `WFDSConMgr::CDafAssociationHelper::ReadCeremonyData`
- `0x18004af54`: `WFDSConMgr::CDafAssociationHelper::ReadCeremonyData`
- `0x18004ae6b`: `Bad parameters to ReadCeremonyData`
- `0x18004aeb8`: `Failure in DafStartReadCeremonyData, bailing out`
- `0x18004af01`: `StartReadCeremonyData operation canceled`
- `0x18004af3b`: `Failure in DafStartReadCeremonyData callback, bailing out`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CDafAssociationHelper::ReadCeremonyData(int *a1, _DWORD *a2, __int64 *a3)
{
  __int64 v6; // rdx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // eax
  void *v10; // rbp
  const void *v11; // rdi
  unsigned int v12; // ebx
  void *v13; // rax
  void *v14; // [rsp+60h] [rbp+8h] BYREF
  void *v15; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids, a1);
  }
  v6 = *((_QWORD *)a1 + 2);
  if ( !v6 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CDafAssociationHelper::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      98,
      L"Must create association before calling Read Ceremony Data",
      a1);
  if ( !a2 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CDafAssociationHelper::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      104,
      L"Bad parameters to ReadCeremonyData",
      a1);
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**(_QWORD **)a1 + 40LL))(
         *(_QWORD *)a1,
         v6,
         WFDSConMgr::CDafAssociationHelper::ReadCeremonyDataCallback,
         a1);
  if ( v7 < 0 )
    WFDSConMgr::CException::Throw(
      v7,
      "WFDSConMgr::CDafAssociationHelper::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      109,
      L"Failure in DafStartReadCeremonyData, bailing out",
      a1);
  WFDSConMgr::WaitMultipleEvents(&v14, 0xFFFFFFFFLL, a1 + 8, a1 + 18);
  if ( HIDWORD(v14) == 1 )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CDafAssociationHelper::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      118,
      L"StartReadCeremonyData operation canceled",
      a1);
  v8 = a1[32];
  if ( v8 < 0 )
    WFDSConMgr::CException::Throw(
      v8,
      "WFDSConMgr::CDafAssociationHelper::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      123,
      L"Failure in DafStartReadCeremonyData callback, bailing out",
      a1);
  *a2 = a1[33];
  v9 = a1[33];
  v10 = 0;
  v14 = 0;
  if ( v9 )
  {
    v11 = (const void *)*((_QWORD *)a1 + 17);
    v12 = v9;
    v13 = operator new[](v9);
    std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(&v14, v13);
    v10 = v14;
    memset_0(v14, 0, v12);
    memcpy_0(v10, v11, v12);
  }
  v14 = 0;
  v15 = v10;
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(&v14);
  std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(a3, (__int64 *)&v15);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(&v15);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids, a1);
  }
}

```

## disassembly

```asm
0x18004add8  mov     [rsp+arg_8], rbx
0x18004addd  push    rbp
0x18004adde  push    rsi
0x18004addf  push    rdi
0x18004ade0  push    r14
0x18004ade2  push    r15
0x18004ade4  sub     rsp, 30h
0x18004ade8  mov     r14, r8
0x18004adeb  mov     rbx, rdx
0x18004adee  mov     rsi, rcx
0x18004adf1  lea     r15, WPP_GLOBAL_Control
0x18004adf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004adff  cmp     rcx, r15
0x18004ae02  jz      short loc_18004AE28
0x18004ae04  cmp     byte ptr [rcx+19h], 4
0x18004ae08  jb      short loc_18004AE28
0x18004ae0a  test    byte ptr [rcx+1Ch], 1
0x18004ae0e  jz      short loc_18004AE28
0x18004ae10  mov     edx, 16h
0x18004ae15  mov     r9, rsi
0x18004ae18  lea     r8, WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids
0x18004ae1f  mov     rcx, [rcx+10h]
0x18004ae23  call    WPP_SF_q
0x18004ae28  mov     rdx, [rsi+10h]
0x18004ae2c  test    rdx, rdx
0x18004ae2f  jnz     short loc_18004AE61
0x18004ae31  mov     [rsp+58h+var_30], rsi; void *
0x18004ae36  lea     rax, aMustCreateAsso; "Must create association before calling "...
0x18004ae3d  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004ae42  mov     r9d, 162h; char
0x18004ae48  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ae4f  lea     rdx, aWfdsconmgrCdaf_5; "WFDSConMgr::CDafAssociationHelper::Read"...
0x18004ae56  mov     ecx, 8007139Fh; char
0x18004ae5b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ae61  test    rbx, rbx
0x18004ae64  jnz     short loc_18004AE96
0x18004ae66  mov     [rsp+58h+var_30], rsi; void *
0x18004ae6b  lea     rax, aBadParametersT_0; "Bad parameters to ReadCeremonyData"
0x18004ae72  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004ae77  mov     r9d, 168h; char
0x18004ae7d  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ae84  lea     rdx, aWfdsconmgrCdaf_5; "WFDSConMgr::CDafAssociationHelper::Read"...
0x18004ae8b  mov     ecx, 80070057h; char
0x18004ae90  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ae96  mov     rcx, [rsi]
0x18004ae99  mov     rax, [rcx]
0x18004ae9c  mov     r9, rsi
0x18004ae9f  lea     r8, ?ReadCeremonyDataCallback@CDafAssociationHelper@WFDSConMgr@@KAXKQEAEPEAXJ@Z; WFDSConMgr::CDafAssociationHelper::ReadCeremonyDataCallback(ulong,uchar * const,void *,long)
0x18004aea6  mov     rax, [rax+28h]
0x18004aeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aeaf  test    eax, eax
0x18004aeb1  jns     short loc_18004AEE0
0x18004aeb3  mov     [rsp+58h+var_30], rsi; void *
0x18004aeb8  lea     rcx, aFailureInDafst_6; "Failure in DafStartReadCeremonyData, ba"...
0x18004aebf  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x18004aec4  mov     r9d, 16Dh; char
0x18004aeca  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004aed1  lea     rdx, aWfdsconmgrCdaf_5; "WFDSConMgr::CDafAssociationHelper::Read"...
0x18004aed8  mov     ecx, eax; char
0x18004aeda  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004aee0  lea     r9, [rsi+48h]
0x18004aee4  lea     r8, [rsi+20h]
0x18004aee8  or      edx, 0FFFFFFFFh
0x18004aeeb  lea     rcx, [rsp+58h+arg_0]
0x18004aef0  call    ?WaitMultipleEvents@WFDSConMgr@@YA?AVCWaitResult@1@KAEBVCEventWrapper@1@0@Z; WFDSConMgr::WaitMultipleEvents(ulong,WFDSConMgr::CEventWrapper const &,WFDSConMgr::CEventWrapper const &)
0x18004aef5  cmp     dword ptr [rsp+58h+arg_0+4], 1
0x18004aefa  jnz     short loc_18004AF2C
0x18004aefc  mov     [rsp+58h+var_30], rsi; void *
0x18004af01  lea     rax, aStartreadcerem; "StartReadCeremonyData operation cancele"...
0x18004af08  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004af0d  mov     r9d, 176h; char
0x18004af13  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004af1a  lea     rdx, aWfdsconmgrCdaf_5; "WFDSConMgr::CDafAssociationHelper::Read"...
0x18004af21  mov     ecx, 800704C7h; char
0x18004af26  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004af2c  mov     ecx, [rsi+80h]; char
0x18004af32  test    ecx, ecx
0x18004af34  jns     short loc_18004AF61
0x18004af36  mov     [rsp+58h+var_30], rsi; void *
0x18004af3b  lea     rax, aFailureInDafst_1; "Failure in DafStartReadCeremonyData cal"...
0x18004af42  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18004af47  mov     r9d, 17Bh; char
0x18004af4d  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004af54  lea     rdx, aWfdsconmgrCdaf_5; "WFDSConMgr::CDafAssociationHelper::Read"...
0x18004af5b  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004af61  mov     eax, [rsi+84h]
0x18004af67  mov     [rbx], eax
0x18004af69  mov     eax, [rsi+84h]
0x18004af6f  xor     ebp, ebp
0x18004af71  mov     [rsp+58h+arg_0], rbp
0x18004af76  test    eax, eax
0x18004af78  jz      short loc_18004AFB7
0x18004af7a  mov     rdi, [rsi+88h]
0x18004af81  mov     ebx, eax
0x18004af83  mov     ecx, eax; unsigned __int64
0x18004af85  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004af8a  mov     rdx, rax
0x18004af8d  lea     rcx, [rsp+58h+arg_0]
0x18004af92  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x18004af97  mov     r8d, ebx; Size
0x18004af9a  xor     edx, edx; Val
0x18004af9c  mov     rbp, [rsp+58h+arg_0]
0x18004afa1  mov     rcx, rbp; void *
0x18004afa4  call    memset_0
0x18004afa9  mov     r8d, ebx; Size
0x18004afac  mov     rdx, rdi; Src
0x18004afaf  mov     rcx, rbp; void *
0x18004afb2  call    memcpy_0
0x18004afb7  mov     [rsp+58h+arg_0], 0
0x18004afc0  mov     [rsp+58h+arg_18], rbp
0x18004afc5  lea     rcx, [rsp+58h+arg_0]
0x18004afca  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x18004afcf  lea     rdx, [rsp+58h+arg_18]
0x18004afd4  mov     rcx, r14
0x18004afd7  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x18004afdc  lea     rcx, [rsp+58h+arg_18]
0x18004afe1  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x18004afe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004afed  cmp     rcx, r15
0x18004aff0  jz      short loc_18004B016
0x18004aff2  cmp     byte ptr [rcx+19h], 4
0x18004aff6  jb      short loc_18004B016
0x18004aff8  test    byte ptr [rcx+1Ch], 1
0x18004affc  jz      short loc_18004B016
0x18004affe  mov     edx, 17h
0x18004b003  mov     r9, rsi
0x18004b006  lea     r8, WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids
0x18004b00d  mov     rcx, [rcx+10h]
0x18004b011  call    WPP_SF_q
0x18004b016  mov     rbx, [rsp+58h+arg_8]
0x18004b01b  add     rsp, 30h
0x18004b01f  pop     r15
0x18004b021  pop     r14
0x18004b023  pop     rdi
0x18004b024  pop     rsi
0x18004b025  pop     rbp
0x18004b026  retn
```
