# CMDEContentServer::GetLocalPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *,_SpecialPathRequest,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,IStream * *)

- ea: `0x14002ba58`
- end: `0x14002c138`
- name: `?GetLocalPath@CMDEContentServer@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBGW4_SpecialPathRequest@@HAEAV23@PEAPEAUIStream@@@Z`
- size: `1760`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002ac5c`

## callees

- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000c9cc`
- `0x140021194`
- `0x140027660`
- `0x14002ba58`
- `0x14002c17c`
- `0x14002eb14`
- `0x14003a168`
- `0x14003f17c`
- `0x14004a834`
- `0x140054490`
- `0x14005480c`
- `0x14005e01c`
- `0x1400637b0`
- `0x14006789c`
- `0x1400908e0`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002bde0`
- `KERNEL32!CompareStringW` at `0x14002bde0`
- `OLEAUT32!__imp_VariantInit` at `0x14002bb77`
- `OLEAUT32!__imp_VariantInit` at `0x14002bb77`
- `OLEAUT32!__imp_VariantClear` at `0x14002bd71`
- `OLEAUT32!__imp_VariantClear` at `0x14002bf1d`
- `OLEAUT32!__imp_VariantClear` at `0x14002bf29`
- `OLEAUT32!__imp_VariantClear` at `0x14002c08a`
- `OLEAUT32!__imp_VariantClear` at `0x14002bd71`
- `OLEAUT32!__imp_VariantClear` at `0x14002bf1d`
- `OLEAUT32!__imp_VariantClear` at `0x14002bf29`
- `OLEAUT32!__imp_VariantClear` at `0x14002c08a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMDEContentServer::GetLocalPath(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 *a6,
        _QWORD *a7)
{
  int ObjectW; // eax
  unsigned int v12; // edx
  unsigned int v13; // ecx
  int v14; // r8d
  int v15; // ebx
  PVOID *v16; // r10
  int v17; // eax
  PVOID *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  VARIANTARG *p_pvarg; // rcx
  struct IWMCUPnPObject *v22; // rdi
  __int64 (__fastcall *v23)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, VARIANTARG *, int, __int64); // rbx
  __int64 BufferSetLength; // rax
  PVOID *v25; // rcx
  struct IWMCUPnPObject *v26; // rdi
  __int64 (__fastcall *v27)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, __int64, __int64); // rbx
  __int64 v28; // rax
  _QWORD *v29; // rax
  int v30; // r9d
  struct IWMCUPnPObject *v32; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v33; // [rsp+48h] [rbp-99h] BYREF
  VARIANTARG v34; // [rsp+50h] [rbp-91h] BYREF
  PCNZWCH lpString2; // [rsp+70h] [rbp-71h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-69h] BYREF
  VARIANTARG v37; // [rsp+90h] [rbp-51h] BYREF
  VARIANTARG v38; // [rsp+B0h] [rbp-31h] BYREF
  VARIANTARG v39; // [rsp+D0h] [rbp-11h] BYREF

  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0ttq_EventWriteTransfer(a1, (unsigned int)MDE_Callback_Get_Local_Path_Start, a4 != 0, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, 0);
  }
  v32 = 0;
  ObjectW = CMDEContentServer::GetObjectW(a1, a2, a3, &v32);
  v15 = ObjectW;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = ((ObjectW >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v12 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        214,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)ObjectW);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v15 >= 0 )
  {
    if ( a4 != 1 )
    {
      if ( a4 == 2 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v33);
        CdsItemInfo::CdsItemInfo((CdsItemInfo *)&pvarg, v32);
        CdsItemInfoBase::GetMIMETypeAndProfileIDs(&pvarg, &lpString2, &v33);
        if ( CompareStringW(0x7Fu, 1u, L"video/mpeg", -1, lpString2, -1) == 2 )
        {
          v34.vt = 19;
          v34.lVal = 3;
          v37.vt = 19;
          v37.lVal = 26;
          v22 = v32;
          v23 = *(__int64 (__fastcall **)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, VARIANTARG *, int, __int64))(*(_QWORD *)v32 + 64LL);
          BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a6, 1025);
          v39 = v37;
          v38 = v34;
          v15 = v23(v22, &v38, 0, &v39, 1024, BufferSetLength);
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a6, ((v15 >> 31) & 1u) - 1);
          v25 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v15 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              220,
              (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              v15,
              *a6);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v15 >= 0 && !*(_DWORD *)(*a6 - 16) )
          {
            v15 = -2147024894;
            if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 2) != 0 && *((_BYTE *)v25 + 25) >= 2u )
              WPP_SF_d(v25[2], 221, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, 2147942402LL);
          }
          VariantClear(&v37);
          VariantClear(&v34);
        }
        else
        {
          v15 = -2147024894;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              222,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              2147942402LL);
          }
        }
        CdsItemInfo::~CdsItemInfo((CdsItemInfo *)&pvarg);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v33);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString2);
        goto LABEL_67;
      }
      v34.vt = 19;
      v34.lVal = 47;
      v26 = v32;
      v27 = *(__int64 (__fastcall **)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, __int64, __int64))(*(_QWORD *)v32 + 56LL);
      v28 = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a6, 1025);
      v38 = v34;
      v15 = v27(v26, &v38, 0, 1024, v28);
      ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a6, ((v15 >> 31) & 1u) - 1);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v15 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          223,
          (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          v15,
          *a6);
      }
      if ( v15 >= 0 && !*(_DWORD *)(*a6 - 16) )
        v15 = -2147024894;
      v29 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                        a6,
                        &v33,
                        5);
      ATL::CSimpleStringT<unsigned short,0>::operator=(a6, v29);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v33);
      p_pvarg = &v34;
LABEL_66:
      VariantClear(p_pvarg);
LABEL_67:
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_68;
    }
    VariantInit(&pvarg);
    v37.vt = 19;
    v37.lVal = 29;
    v34 = v37;
    v17 = (*(__int64 (__fastcall **)(struct IWMCUPnPObject *, VARIANTARG *, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v32 + 72LL))(
            v32,
            &v34,
            0,
            1024,
            &pvarg);
    v15 = v17;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v17 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v17);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 >= 0 )
    {
      if ( pvarg.vt == 8 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a6, pvarg.llVal);
        if ( *(_DWORD *)(*a6 - 16) )
          goto LABEL_39;
        v15 = -2147024894;
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v19 = 216;
        goto LABEL_24;
      }
      if ( pvarg.vt != 13 )
      {
        v15 = -2147024894;
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 2u )
          WPP_SF_Dd(v18[2], 219, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, pvarg.vt);
        goto LABEL_39;
      }
      if ( pvarg.llVal )
      {
        v20 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, _QWORD *))pvarg.llVal)(
                pvarg.llVal,
                &GUID_0000000c_0000_0000_c000_000000000046,
                a7);
        v15 = v20;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v20 >> 31) & 0xFFFFFFFD) + 5 )
        {
          WPP_SF_dq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            218,
            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
            (unsigned int)v20,
            *a7);
        }
        goto LABEL_39;
      }
      v15 = -2147024894;
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 2u )
      {
        v19 = 217;
LABEL_24:
        WPP_SF_d(v18[2], v19, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, 2147942402LL);
      }
    }
LABEL_39:
    VariantClear(&v37);
    p_pvarg = &pvarg;
    goto LABEL_66;
  }
LABEL_68:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
  {
    v13 = ((v15 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)v16 + 25) >= v13 )
      WPP_SF_dSq((unsigned int)v16[2], v12, v14, v15, *a6, *a7);
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    v30 = 0;
    if ( a7 )
      LOBYTE(v30) = *a7 != 0;
    McTemplateU0ttq_EventWriteTransfer(v13, (unsigned int)MDE_Callback_Get_Local_Path_Stop, a4 != 0, v30, v15);
  }
  if ( v32 )
    (*(void (__fastcall **)(struct IWMCUPnPObject *))(*(_QWORD *)v32 + 16LL))(v32);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14002ba58  push    rbp
0x14002ba5a  push    rbx
0x14002ba5b  push    rsi
0x14002ba5c  push    rdi
0x14002ba5d  push    r13
0x14002ba5f  push    r14
0x14002ba61  push    r15
0x14002ba63  lea     rbp, [rsp-0Fh]
0x14002ba68  sub     rsp, 0F0h
0x14002ba6f  mov     r15d, r9d
0x14002ba72  mov     rbx, r8
0x14002ba75  mov     rdi, rdx
0x14002ba78  mov     rsi, rcx
0x14002ba7b  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14002ba82  jz      short loc_14002BAA5
0x14002ba84  xor     r8d, r8d
0x14002ba87  test    r9d, r9d
0x14002ba8a  setnz   r8b
0x14002ba8e  mov     dword ptr [rsp+120h+lpString2], 0
0x14002ba96  xor     r9d, r9d
0x14002ba99  lea     rdx, MDE_Callback_Get_Local_Path_Start
0x14002baa0  call    McTemplateU0ttq_EventWriteTransfer
0x14002baa5  lea     rax, WPP_GLOBAL_Control
0x14002baac  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bab3  cmp     rcx, rax
0x14002bab6  jz      short loc_14002BAE9
0x14002bab8  test    byte ptr [rcx+1Ch], 1
0x14002babc  jz      short loc_14002BAE9
0x14002babe  cmp     byte ptr [rcx+19h], 5
0x14002bac2  jb      short loc_14002BAE9
0x14002bac4  mov     edx, 0D5h
0x14002bac9  mov     [rsp+120h+cchCount2], 0; char
0x14002bad1  mov     [rsp+120h+lpString2], rbx; __int64
0x14002bad6  mov     r9, [rdi]
0x14002bad9  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bae0  mov     rcx, [rcx+10h]; LoggerHandle
0x14002bae4  call    WPP_SF_SSd
0x14002bae9  mov     [rsp+120h+var_E0], 0
0x14002baf2  lea     r9, [rsp+120h+var_E0]
0x14002baf7  mov     r8, rbx
0x14002bafa  mov     rdx, rdi
0x14002bafd  mov     rcx, rsi
0x14002bb00  call    ?GetObjectW@CMDEContentServer@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAUIWMCUPnPObject@@_N@Z; CMDEContentServer::GetObjectW(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *,IWMCUPnPObject * *,bool)
0x14002bb05  mov     ebx, eax
0x14002bb07  mov     r13d, 2
0x14002bb0d  mov     r10, cs:WPP_GLOBAL_Control
0x14002bb14  lea     rdi, WPP_GLOBAL_Control
0x14002bb1b  cmp     r10, rdi
0x14002bb1e  jz      short loc_14002BB59
0x14002bb20  test    [r10+1Ch], r13b
0x14002bb24  jz      short loc_14002BB59
0x14002bb26  mov     edx, eax
0x14002bb28  sar     edx, 1Fh
0x14002bb2b  and     edx, 0FFFFFFFDh
0x14002bb2e  add     edx, 5
0x14002bb31  movzx   eax, byte ptr [r10+19h]
0x14002bb36  cmp     eax, edx
0x14002bb38  jb      short loc_14002BB59
0x14002bb3a  mov     edx, 0D6h
0x14002bb3f  mov     r9d, ebx
0x14002bb42  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bb49  mov     rcx, [r10+10h]
0x14002bb4d  call    WPP_SF_d
0x14002bb52  mov     r10, cs:WPP_GLOBAL_Control
0x14002bb59  mov     r14, [rbp+3Fh+arg_30]
0x14002bb5d  mov     rsi, [rbp+3Fh+arg_28]
0x14002bb61  test    ebx, ebx
0x14002bb63  js      loc_14002C097
0x14002bb69  cmp     r15d, 1
0x14002bb6d  jnz     loc_14002BD81
0x14002bb73  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x14002bb77  call    cs:__imp_VariantInit
0x14002bb7d  nop
0x14002bb7e  lea     eax, [r15+12h]
0x14002bb82  mov     word ptr [rbp+3Fh+var_90], ax
0x14002bb86  mov     dword ptr [rbp+3Fh+var_90+8], 1Dh
0x14002bb8d  mov     rcx, [rsp+120h+var_E0]
0x14002bb92  movups  xmm0, xmmword ptr [rbp+3Fh+var_90]
0x14002bb96  movaps  xmmword ptr [rsp+120h+var_D0], xmm0
0x14002bb9b  movsd   xmm1, qword ptr [rbp+3Fh+var_90+10h]
0x14002bba0  movsd   qword ptr [rsp+120h+var_D0+10h], xmm1
0x14002bba6  mov     rax, [rcx]
0x14002bba9  lea     rdx, [rbp+3Fh+pvarg]
0x14002bbad  mov     [rsp+120h+lpString2], rdx
0x14002bbb2  mov     r9d, 400h
0x14002bbb8  xor     r8d, r8d
0x14002bbbb  lea     rdx, [rsp+120h+var_D0]
0x14002bbc0  mov     rax, [rax+48h]
0x14002bbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bbc9  mov     ebx, eax
0x14002bbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbd2  cmp     rcx, rdi
0x14002bbd5  jz      short loc_14002BC17
0x14002bbd7  test    [rcx+1Ch], r13b
0x14002bbdb  jz      short loc_14002BC17
0x14002bbdd  mov     edx, eax
0x14002bbdf  sar     edx, 1Fh
0x14002bbe2  and     edx, 0FFFFFFFDh
0x14002bbe5  add     edx, 5
0x14002bbe8  movzx   eax, byte ptr [rcx+19h]
0x14002bbec  cmp     eax, edx
0x14002bbee  jb      short loc_14002BC17
0x14002bbf0  movzx   eax, word ptr [rbp+3Fh+pvarg]
0x14002bbf4  mov     edx, 0D7h
0x14002bbf9  mov     dword ptr [rsp+120h+lpString2], eax
0x14002bbfd  mov     r9d, ebx
0x14002bc00  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bc07  mov     rcx, [rcx+10h]
0x14002bc0b  call    WPP_SF_Dd
0x14002bc10  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc17  test    ebx, ebx
0x14002bc19  js      loc_14002BD6D
0x14002bc1f  mov     edx, 8
0x14002bc24  movzx   eax, word ptr [rbp+3Fh+pvarg]
0x14002bc28  cmp     dx, ax
0x14002bc2b  jnz     short loc_14002BC90
0x14002bc2d  mov     rdx, qword ptr [rbp+3Fh+pvarg+8]
0x14002bc31  mov     rcx, rsi
0x14002bc34  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14002bc39  mov     rax, [rsi]
0x14002bc3c  cmp     dword ptr [rax-10h], 0
0x14002bc40  jnz     loc_14002BD6D
0x14002bc46  mov     r10d, 80070002h
0x14002bc4c  mov     ebx, r10d
0x14002bc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc56  cmp     rcx, rdi
0x14002bc59  jz      loc_14002BD6D
0x14002bc5f  test    [rcx+1Ch], r13b
0x14002bc63  jz      loc_14002BD6D
0x14002bc69  cmp     [rcx+19h], r13b
0x14002bc6d  jb      loc_14002BD6D
0x14002bc73  mov     edx, 0D8h
0x14002bc78  mov     r9d, r10d
0x14002bc7b  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bc82  mov     rcx, [rcx+10h]
0x14002bc86  call    WPP_SF_d
0x14002bc8b  jmp     loc_14002BD6D
0x14002bc90  mov     edx, 0Dh
0x14002bc95  cmp     dx, ax
0x14002bc98  jnz     loc_14002BD35
0x14002bc9e  mov     r9, qword ptr [rbp+3Fh+pvarg+8]
0x14002bca2  test    r9, r9
0x14002bca5  jnz     short loc_14002BCD4
0x14002bca7  mov     r10d, 80070002h
0x14002bcad  mov     ebx, r10d
0x14002bcb0  cmp     rcx, rdi
0x14002bcb3  jz      loc_14002BD6D
0x14002bcb9  test    [rcx+1Ch], r13b
0x14002bcbd  jz      loc_14002BD6D
0x14002bcc3  cmp     [rcx+19h], r13b
0x14002bcc7  jb      loc_14002BD6D
0x14002bccd  mov     edx, 0D9h
0x14002bcd2  jmp     short loc_14002BC78
0x14002bcd4  mov     rax, [r9]
0x14002bcd7  mov     r8, r14
0x14002bcda  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x14002bce1  mov     rcx, r9
0x14002bce4  mov     rax, [rax]
0x14002bce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcec  mov     ebx, eax
0x14002bcee  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bcf5  cmp     rcx, rdi
0x14002bcf8  jz      short loc_14002BD6D
0x14002bcfa  test    [rcx+1Ch], r13b
0x14002bcfe  jz      short loc_14002BD6D
0x14002bd00  mov     edx, eax
0x14002bd02  sar     edx, 1Fh
0x14002bd05  and     edx, 0FFFFFFFDh
0x14002bd08  add     edx, 5
0x14002bd0b  movzx   eax, byte ptr [rcx+19h]
0x14002bd0f  cmp     eax, edx
0x14002bd11  jb      short loc_14002BD6D
0x14002bd13  mov     edx, 0DAh
0x14002bd18  mov     rax, [r14]
0x14002bd1b  mov     [rsp+120h+lpString2], rax
0x14002bd20  mov     r9d, ebx
0x14002bd23  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bd2a  mov     rcx, [rcx+10h]
0x14002bd2e  call    WPP_SF_dq
0x14002bd33  jmp     short loc_14002BD6D
0x14002bd35  mov     r10d, 80070002h
0x14002bd3b  mov     ebx, r10d
0x14002bd3e  cmp     rcx, rdi
0x14002bd41  jz      short loc_14002BD6D
0x14002bd43  test    [rcx+1Ch], r13b
0x14002bd47  jz      short loc_14002BD6D
0x14002bd49  cmp     [rcx+19h], r13b
0x14002bd4d  jb      short loc_14002BD6D
0x14002bd4f  mov     r9d, eax
0x14002bd52  mov     edx, 0DBh
0x14002bd57  mov     dword ptr [rsp+120h+lpString2], r10d
0x14002bd5c  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bd63  mov     rcx, [rcx+10h]
0x14002bd67  call    WPP_SF_Dd
0x14002bd6c  nop
0x14002bd6d  lea     rcx, [rbp+3Fh+var_90]; pvarg
0x14002bd71  call    cs:__imp_VariantClear
0x14002bd77  nop
0x14002bd78  lea     rcx, [rbp+3Fh+pvarg]
0x14002bd7c  jmp     loc_14002C08A
0x14002bd81  cmp     r15d, r13d
0x14002bd84  jnz     loc_14002BF8E
0x14002bd8a  lea     rcx, [rbp+3Fh+var_B0]
0x14002bd8e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14002bd93  nop
0x14002bd94  lea     rcx, [rsp+120h+var_D8]
0x14002bd99  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x14002bd9e  nop
0x14002bd9f  mov     rdx, [rsp+120h+var_E0]; struct IWMCUPnPObject *
0x14002bda4  lea     rcx, [rbp+3Fh+pvarg]; this
0x14002bda8  call    ??0CdsItemInfo@@QEAA@PEAUIWMCUPnPObject@@@Z; CdsItemInfo::CdsItemInfo(IWMCUPnPObject *)
0x14002bdad  nop
0x14002bdae  lea     r8, [rsp+120h+var_D8]
0x14002bdb3  lea     rdx, [rbp+3Fh+var_B0]
0x14002bdb7  lea     rcx, [rbp+3Fh+pvarg]
0x14002bdbb  call    ?GetMIMETypeAndProfileIDs@CdsItemInfoBase@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@0@Z; CdsItemInfoBase::GetMIMETypeAndProfileIDs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14002bdc0  or      r9d, 0FFFFFFFFh; cchCount1
0x14002bdc4  mov     [rsp+120h+cchCount2], r9d; cchCount2
0x14002bdc9  mov     rax, [rbp+3Fh+var_B0]
0x14002bdcd  mov     [rsp+120h+lpString2], rax; lpString2
0x14002bdd2  lea     r8, aVideoMpeg; "video/mpeg"
0x14002bdd9  lea     edx, [r9+2]; dwCmpFlags
0x14002bddd  lea     ecx, [rdx+7Eh]; Locale
0x14002bde0  call    cs:__imp_CompareStringW
0x14002bde6  cmp     eax, r13d
0x14002bde9  jnz     loc_14002BF31
0x14002bdef  mov     eax, 13h
0x14002bdf4  mov     word ptr [rsp+120h+var_D0], ax
0x14002bdf9  mov     dword ptr [rsp+120h+var_D0+8], 3
0x14002be01  mov     word ptr [rbp+3Fh+var_90], ax
0x14002be05  mov     dword ptr [rbp+3Fh+var_90+8], 1Ah
0x14002be0c  mov     rdi, [rsp+120h+var_E0]
0x14002be11  mov     rax, [rdi]
0x14002be14  mov     rbx, [rax+40h]
0x14002be18  mov     edx, 401h
0x14002be1d  mov     rcx, rsi
0x14002be20  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x14002be25  movups  xmm0, xmmword ptr [rbp+3Fh+var_90]
0x14002be29  movaps  [rbp+3Fh+var_50], xmm0
0x14002be2d  movsd   xmm1, qword ptr [rbp+3Fh+var_90+10h]
0x14002be32  movsd   [rbp+3Fh+var_40], xmm1
0x14002be37  movups  xmm0, xmmword ptr [rsp+120h+var_D0]
0x14002be3c  movaps  [rbp+3Fh+var_70], xmm0
0x14002be40  movsd   xmm1, qword ptr [rsp+120h+var_D0+10h]
0x14002be46  movsd   [rbp+3Fh+var_60], xmm1
0x14002be4b  mov     qword ptr [rsp+120h+cchCount2], rax
0x14002be50  mov     dword ptr [rsp+120h+lpString2], 400h
0x14002be58  lea     r9, [rbp+3Fh+var_50]
0x14002be5c  xor     r8d, r8d
0x14002be5f  lea     rdx, [rbp+3Fh+var_70]
0x14002be63  mov     rcx, rdi
0x14002be66  mov     rax, rbx
0x14002be69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002be6e  mov     ebx, eax
0x14002be70  mov     edi, eax
0x14002be72  sar     edi, 1Fh
0x14002be75  mov     edx, edi
0x14002be77  and     edx, 1
0x14002be7a  dec     edx
0x14002be7c  mov     rcx, rsi
0x14002be7f  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x14002be84  mov     rcx, cs:WPP_GLOBAL_Control
0x14002be8b  lea     rdx, WPP_GLOBAL_Control
0x14002be92  cmp     rcx, rdx
0x14002be95  jz      short loc_14002BED9
0x14002be97  test    [rcx+1Ch], r13b
0x14002be9b  jz      short loc_14002BED9
0x14002be9d  and     edi, 0FFFFFFFDh
0x14002bea0  add     edi, 5
0x14002bea3  movzx   eax, byte ptr [rcx+19h]
0x14002bea7  cmp     eax, edi
0x14002bea9  jb      short loc_14002BED9
0x14002beab  mov     edx, 0DCh
0x14002beb0  mov     rax, [rsi]
0x14002beb3  mov     [rsp+120h+lpString2], rax
0x14002beb8  mov     r9d, ebx
0x14002bebb  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bec2  mov     rcx, [rcx+10h]
0x14002bec6  call    WPP_SF_dS
0x14002becb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bed2  lea     rdx, WPP_GLOBAL_Control
0x14002bed9  test    ebx, ebx
0x14002bedb  js      short loc_14002BF19
0x14002bedd  mov     rax, [rsi]
0x14002bee0  cmp     dword ptr [rax-10h], 0
0x14002bee4  jnz     short loc_14002BF19
0x14002bee6  mov     r10d, 80070002h
0x14002beec  mov     ebx, r10d
0x14002beef  cmp     rcx, rdx
0x14002bef2  jz      short loc_14002BF19
0x14002bef4  test    [rcx+1Ch], r13b
0x14002bef8  jz      short loc_14002BF19
0x14002befa  cmp     [rcx+19h], r13b
0x14002befe  jb      short loc_14002BF19
0x14002bf00  mov     edx, 0DDh
0x14002bf05  mov     r9d, r10d
0x14002bf08  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14002bf0f  mov     rcx, [rcx+10h]
0x14002bf13  call    WPP_SF_d
0x14002bf18  nop
  ... truncated ...
```
