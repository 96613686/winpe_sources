# CWiaItem::CommonDownload(int,long,IWiaTransferCallback *,IWiaImageFilter *)

- ea: `0x18006d5f0`
- end: `0x18006dd93`
- name: `?CommonDownload@CWiaItem@@UEAAJHJPEAUIWiaTransferCallback@@PEAUIWiaImageFilter@@@Z`
- size: `1955`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int, int, struct IWiaTransferCallback *, struct IWiaImageFilter *)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180011a94`
- `0x18001da54`
- `0x18001db34`
- `0x1800202b8`
- `0x1800284dc`
- `0x180028560`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180033884`
- `0x180033cc0`
- `0x1800586d8`
- `0x18005912c`
- `0x180059534`
- `0x1800598cc`
- `0x18005e2e8`
- `0x180062710`
- `0x1800649a0`
- `0x18006ccf0`
- `0x18006d5f0`
- `0x18006dea4`
- `0x18006e160`
- `0x180070808`
- `0x180070e70`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006db27`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006db27`

## string_xrefs

- `0x18006d907`: `ValidateWiaDrvItemAccess failed`
- `0x18006d92d`: `ValidateWiaDrvItemAccess failed`
- `0x18006d633`: `CWiaItem::CommonDownload`
- `0x18006d7b5`: `CWiaItem::CommonDownload`
- `0x18006d7e3`: `CWiaItem::CommonDownload`
- `0x18006d827`: `CWiaItem::CommonDownload`
- `0x18006d855`: `CWiaItem::CommonDownload`
- `0x18006d8b0`: `CWiaItem::CommonDownload`
- `0x18006d8e0`: `CWiaItem::CommonDownload`
- `0x18006d916`: `CWiaItem::CommonDownload`
- `0x18006d973`: `CWiaItem::CommonDownload`
- `0x18006d9a1`: `CWiaItem::CommonDownload`
- `0x18006db75`: `CWiaItem::CommonDownload`
- `0x18006dba6`: `CWiaItem::CommonDownload`
- `0x18006dc90`: `CWiaItem::CommonDownload`
- `0x18006dd30`: `CWiaItem::CommonDownload`
- `0x18006d8a1`: `update the current item context (0x%X)`
- `0x18006d8c9`: `update the current item context (0x%X)`
- `0x18006d6cb`: `Transfer attempted on root item, this is forbidden.`
- `0x18006d6f1`: `Transfer attempted on root item, this is forbidden.`

## pseudocode

```c
__int64 __fastcall CWiaItem::CommonDownload(
        CWiaItem *this,
        int a2,
        int a3,
        struct IWiaTransferCallback *a4,
        struct IWiaImageFilter *a5)
{
  signed int v5; // edi
  CWiaItem *v6; // r8
  CFilterPropertyStorage *v7; // r12
  int v8; // r15d
  int v9; // r14d
  char *v10; // rbx
  void *v11; // rdx
  void **lpMem; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  CWiaItem *v15; // r13
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  CWiaItem *v21; // rsi
  int v22; // r15d
  int v23; // ebx
  struct IPropertyStorage *v24; // rdx
  CWiaItem *v25; // rcx
  __int64 v26; // r8
  int RelatedDAITItem; // eax
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char *v38; // rbx
  void *v39; // rdx
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  char *v43; // rbx
  void *v44; // rdx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  CFilterPropertyStorage *v50; // rax
  struct IWiaTransferCallback *v51; // r14
  int v52; // eax
  int v53; // ebx
  struct IWiaTransferCallback *v54; // r13
  signed int v55; // eax
  int v56; // eax
  struct IWiaImageFilter *v57; // r15
  HRESULT v58; // eax
  int v59; // ebx
  int v60; // esi
  char *v61; // rbx
  void *v62; // rdx
  void **v63; // rax
  void *v64; // rdx
  __int64 v65; // rcx
  _OWORD *DeviceNameFromItem; // rax
  __int64 v67; // r15
  _OWORD *v68; // rcx
  __int64 v69; // rdx
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int64 v79; // rax
  char *v80; // rbx
  void *v81; // rdx
  _OWORD *v82; // rax
  _OWORD *v83; // rdx
  __int128 v84; // xmm1
  __int128 v85; // xmm0
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  __int128 v91; // xmm0
  __int128 v92; // xmm1
  __int64 v93; // rax
  void **v94; // rax
  void *v95; // rdx
  __int64 v96; // rcx
  int inited; // [rsp+40h] [rbp-C0h] BYREF
  int v99; // [rsp+44h] [rbp-BCh] BYREF
  int IsLegacyDriver; // [rsp+48h] [rbp-B8h]
  int v101; // [rsp+4Ch] [rbp-B4h] BYREF
  int v102; // [rsp+50h] [rbp-B0h]
  struct IWiaTransferCallback *v103; // [rsp+58h] [rbp-A8h]
  CWiaItem *v104; // [rsp+60h] [rbp-A0h] BYREF
  struct IWiaImageFilter *v105; // [rsp+68h] [rbp-98h]
  _QWORD v106[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v107[304]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v108[38]; // [rsp+1B0h] [rbp+B0h] BYREF

  v5 = 0;
  v99 = a3;
  v6 = this;
  v106[0] = this;
  v7 = 0;
  v105 = a5;
  v8 = 0;
  v103 = a4;
  v102 = a2;
  v9 = -2147024809;
  inited = 0;
  IsLegacyDriver = 0;
  v101 = 0;
  if ( !a4 )
  {
    inited = -2147024809;
    v5 = -2147024809;
    v10 = (char *)WiaTrace_TraceLog("NULL callback parameter was specified, callback is a required parameter.");
    WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    lpMem = (void **)WiaTrace_Trace("NULL callback parameter was specified, callback is a required parameter.");
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaItem::CommonDownload", 1, lpMem);
    v6 = (CWiaItem *)v106[0];
    v8 = -2147024809;
  }
  v15 = (CWiaItem *)((char *)v6 - 40);
  if ( *((CWiaItem **)v15 + 26) == v15 )
  {
    v5 = -2147467259;
    inited = -2147467259;
    v16 = (char *)WiaTrace_TraceLog("Transfer attempted on root item, this is forbidden.");
    WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace("Transfer attempted on root item, this is forbidden.");
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaItem::CommonDownload", 1, v18);
    v21 = 0;
LABEL_5:
    v22 = v99;
    goto LABEL_6;
  }
  v21 = 0;
  v104 = 0;
  if ( v8 < 0 )
    goto LABEL_5;
  if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)((char *)v6 - 40))
    || !*(_QWORD *)(*(_QWORD *)(v26 + 168) + 64LL) )
  {
    v21 = v15;
    goto LABEL_20;
  }
  RelatedDAITItem = CWiaItem::FindRelatedDAITItem(v25, &v104, 1);
  v21 = v104;
  v5 = RelatedDAITItem;
  inited = RelatedDAITItem;
  if ( v104 )
  {
    v8 = RelatedDAITItem;
    if ( RelatedDAITItem >= 0 )
      goto LABEL_17;
  }
  else
  {
    v5 = -2147467261;
    inited = -2147467261;
    v8 = -2147467261;
  }
  v28 = (char *)WiaTrace_TraceLog("cannot find related D-AIT item");
  WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v28);
  WiaTrcLib::Free((WiaTrcLib *)v28, v29);
  v30 = (void **)WiaTrace_Trace("cannot find related D-AIT item");
  WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"CWiaItem::CommonDownload", 1, v30);
LABEL_17:
  if ( v8 < 0 )
    goto LABEL_5;
LABEL_20:
  if ( !*((_DWORD *)v21 + 32) )
  {
    inited = CWiaItem::InitLazyProps(v21);
    v5 = inited;
    if ( inited < 0 )
    {
      v33 = (char *)WiaTrace_TraceLog("InitLazyProps failed");
      WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v35 = (void **)WiaTrace_Trace("InitLazyProps failed");
      WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"CWiaItem::CommonDownload", 1, v35);
    }
    v8 = inited;
  }
  *(_DWORD *)(*((_QWORD *)v21 + 26) + 232LL) = 0;
  if ( v8 < 0 )
    goto LABEL_5;
  if ( *(_DWORD *)(*(_QWORD *)(v106[0] + 168LL) + 104LL) == 1 )
  {
    inited = CWiaItem::ApplyCurrentContextSettings(v15);
    v5 = inited;
    if ( inited < 0 )
    {
      v38 = (char *)WiaTrace_TraceLog("update the current item context (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v38);
      WiaTrcLib::Free((WiaTrcLib *)v38, v39);
      v40 = (void **)WiaTrace_Trace("update the current item context (0x%X)", inited);
LABEL_28:
      WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"CWiaItem::CommonDownload", 1, v40);
      goto LABEL_5;
    }
  }
  inited = ValidateWiaDrvItemAccess(*((struct CWiaDrvItem **)v21 + 22));
  v5 = inited;
  if ( inited < 0 )
  {
    v43 = (char *)WiaTrace_TraceLog("ValidateWiaDrvItemAccess failed");
    WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v43);
    WiaTrcLib::Free((WiaTrcLib *)v43, v44);
    v40 = (void **)WiaTrace_Trace("ValidateWiaDrvItemAccess failed");
    goto LABEL_28;
  }
  v22 = v99;
  if ( (v99 & 1) == 0 )
  {
    (*(void (__fastcall **)(CWiaItem *, int *))(*(_QWORD *)v21 + 24LL))(v21, &v101);
    if ( (v101 & 0x2002) == 0 )
    {
      v45 = (char *)WiaTrace_TraceLog("Item is not of File type");
      WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_Trace("Item is not of File type");
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"CWiaItem::CommonDownload", 1, v47);
      return (unsigned int)-2147024809;
    }
  }
  IsLegacyDriver = CWiaItem::IsLegacyDriver(v21);
  if ( !IsLegacyDriver )
  {
    v50 = (CFilterPropertyStorage *)operator new(0x18u);
    if ( v50 )
      v7 = CFilterPropertyStorage::CFilterPropertyStorage(v50);
    v5 = v7 == 0 ? 0x8007000E : 0;
    inited = v5;
  }
LABEL_6:
  if ( v5 < 0 )
    goto LABEL_75;
  v23 = 0;
  if ( (v22 & 1) != 0 )
  {
    v99 = 0;
    v23 = 1;
    v24 = v21 ? (struct IPropertyStorage *)((char *)v21 + 8) : 0LL;
    inited = ReadPropLong(0x1819u, v24, &v99);
    v5 = inited;
    if ( !inited && (v99 & 1) != 0 )
      v23 = 0;
  }
  if ( v5 < 0 )
    goto LABEL_75;
  LOCK_WIA_DEVICE::LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)v106, v21, &inited, *((unsigned __int8 **)v21 + 26));
  v5 = inited;
  if ( inited < 0 )
  {
    DeviceNameFromItem = (_OWORD *)GetDeviceNameFromItem(v108, v21);
    v67 = 2;
    v68 = v107;
    v69 = 2;
    do
    {
      v70 = DeviceNameFromItem[1];
      *v68 = *DeviceNameFromItem;
      v71 = DeviceNameFromItem[2];
      v68[1] = v70;
      v72 = DeviceNameFromItem[3];
      v68[2] = v71;
      v73 = DeviceNameFromItem[4];
      v68[3] = v72;
      v74 = DeviceNameFromItem[5];
      v68[4] = v73;
      v75 = DeviceNameFromItem[6];
      v68[5] = v74;
      v76 = DeviceNameFromItem[7];
      DeviceNameFromItem += 8;
      v68[6] = v75;
      v68[7] = v76;
      v68 += 8;
      --v69;
    }
    while ( v69 );
    v77 = *DeviceNameFromItem;
    v78 = DeviceNameFromItem[1];
    v79 = *((_QWORD *)DeviceNameFromItem + 4);
    *v68 = v77;
    v68[1] = v78;
    *((_QWORD *)v68 + 4) = v79;
    v80 = (char *)WiaTrace_TraceLog("Failed to lock device %ws");
    v108[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v108);
    v108[34] = 0;
    WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v80);
    WiaTrcLib::Free((WiaTrcLib *)v80, v81);
    v82 = (_OWORD *)GetDeviceNameFromItem(v108, v21);
    v83 = v107;
    do
    {
      v84 = v82[1];
      *v83 = *v82;
      v85 = v82[2];
      v83[1] = v84;
      v86 = v82[3];
      v83[2] = v85;
      v87 = v82[4];
      v83[3] = v86;
      v88 = v82[5];
      v83[4] = v87;
      v89 = v82[6];
      v83[5] = v88;
      v90 = v82[7];
      v82 += 8;
      v83[6] = v89;
      v83[7] = v90;
      v83 += 8;
      --v67;
    }
    while ( v67 );
    v91 = *v82;
    v92 = v82[1];
    v93 = *((_QWORD *)v82 + 4);
    *v83 = v91;
    v83[1] = v92;
    *((_QWORD *)v83 + 4) = v93;
    v94 = (void **)WiaTrace_Trace("Failed to lock device %ws", v107);
    WiaTrace_ProcessTrace_Ex(v96, v95, (void *)"CWiaItem::CommonDownload", 1, v94);
    v108[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v108);
    goto LABEL_74;
  }
  IncTransferCount();
  if ( !v23 )
  {
    v53 = IsLegacyDriver;
    v54 = v103;
    if ( IsLegacyDriver )
      v55 = CWiaItem::DoLegacyDownload(v21, v103, (struct IWiaItem *)v21);
    else
      v55 = CWiaItem::DoDownload(v21, v102, v22, v103, (unsigned __int8 *)v21);
    v5 = v55;
    v56 = SendEndOfTransferMessage(v54, 2);
    if ( v5 < 0 || v56 && (v5 = v56, v56 < 0) || (v57 = v105) == 0 || v53 )
    {
LABEL_66:
      if ( v5 == 2162697 )
        v5 = 0;
      goto LABEL_68;
    }
    if ( v21 )
    {
      *((_QWORD *)v7 + 2) = v21;
      v58 = CoImpersonateClient();
      v9 = v58;
      if ( !v58 )
      {
        v59 = 1;
LABEL_60:
        v9 = ((__int64 (__fastcall *)(struct IWiaImageFilter *, CFilterPropertyStorage *))v57->lpVtbl->ApplyProperties)(
               v57,
               v7);
        if ( v59 )
        {
          v60 = SafeCoRevertToSelf();
          if ( v60 < 0 )
          {
            v61 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::CommonDownload", v61);
            WiaTrcLib::Free((WiaTrcLib *)v61, v62);
            v63 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v9);
            WiaTrace_ProcessTrace_Ex(v65, v64, (void *)"CWiaItem::CommonDownload", 1, v63);
            v9 = v60;
          }
        }
        goto LABEL_63;
      }
      v59 = 0;
      if ( v58 >= 0 )
        goto LABEL_60;
    }
LABEL_63:
    if ( v5 >= 0 && v9 < 0 )
      v5 = v9;
    goto LABEL_66;
  }
  v51 = v103;
  v5 = CWiaItem::RecursiveFolderDownload(v15, v21, v102, IsLegacyDriver, v22 & 0xFFFFFFFE, v103, v105, v7);
  v52 = SendEndOfTransferMessage(v51, 2);
  if ( v5 >= 0 && v52 < 0 )
    v5 = v52;
LABEL_68:
  DecTransferCount();
LABEL_74:
  LOCK_WIA_DEVICE::~LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)v106);
LABEL_75:
  if ( v7 )
    (*(void (__fastcall **)(CFilterPropertyStorage *))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006d5f0  push    rbp
0x18006d5f2  push    rbx
0x18006d5f3  push    rsi
0x18006d5f4  push    rdi
0x18006d5f5  push    r12
0x18006d5f7  push    r13
0x18006d5f9  push    r14
0x18006d5fb  push    r15
0x18006d5fd  lea     rbp, [rsp-1F8h]
0x18006d605  sub     rsp, 2F8h
0x18006d60c  mov     rax, cs:__security_cookie
0x18006d613  xor     rax, rsp
0x18006d616  mov     [rbp+230h+var_50], rax
0x18006d61d  xor     edi, edi
0x18006d61f  mov     [rsp+330h+var_2EC], r8d
0x18006d624  mov     r8, rcx
0x18006d627  mov     [rsp+330h+var_2C0], rcx
0x18006d62c  mov     rcx, [rbp+230h+arg_20]
0x18006d633  lea     rsi, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d63a  xor     r12d, r12d
0x18006d63d  mov     [rsp+330h+var_2C8], rcx
0x18006d642  xor     r15d, r15d
0x18006d645  mov     [rsp+330h+var_2D8], r9
0x18006d64a  mov     [rsp+330h+var_2E0], edx
0x18006d64e  mov     r14d, 80070057h
0x18006d654  mov     [rsp+330h+var_2F0], edi
0x18006d658  mov     [rsp+330h+var_2E8], edi
0x18006d65c  mov     [rsp+330h+var_2E4], edi
0x18006d660  test    r9, r9
0x18006d663  jnz     short loc_18006D6B5
0x18006d665  lea     rcx, aNullCallbackPa; "NULL callback parameter was specified, "...
0x18006d66c  mov     [rsp+330h+var_2F0], r14d
0x18006d671  mov     edi, r14d
0x18006d674  call    WiaTrace_TraceLog
0x18006d679  mov     rdx, rax; char *
0x18006d67c  mov     rcx, rsi; char *
0x18006d67f  mov     rbx, rax
0x18006d682  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d687  mov     rcx, rbx; this
0x18006d68a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d68f  lea     rcx, aNullCallbackPa; "NULL callback parameter was specified, "...
0x18006d696  call    WiaTrace_Trace
0x18006d69b  lea     r9d, [r12+1]; int
0x18006d6a0  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d6a5  mov     r8, rsi; int
0x18006d6a8  call    WiaTrace_ProcessTrace_Ex
0x18006d6ad  mov     r8, [rsp+330h+var_2C0]
0x18006d6b2  mov     r15d, r14d
0x18006d6b5  lea     r13, [r8-28h]
0x18006d6b9  cmp     [r13+0D0h], r13
0x18006d6c0  jnz     loc_18006D746
0x18006d6c6  mov     edi, 80004005h
0x18006d6cb  lea     rcx, aTransferAttemp; "Transfer attempted on root item, this i"...
0x18006d6d2  mov     [rsp+330h+var_2F0], edi
0x18006d6d6  call    WiaTrace_TraceLog
0x18006d6db  mov     rdx, rax; char *
0x18006d6de  mov     rcx, rsi; char *
0x18006d6e1  mov     rbx, rax
0x18006d6e4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d6e9  mov     rcx, rbx; this
0x18006d6ec  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d6f1  lea     rcx, aTransferAttemp; "Transfer attempted on root item, this i"...
0x18006d6f8  call    WiaTrace_Trace
0x18006d6fd  mov     r9d, 1; int
0x18006d703  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d708  mov     r8, rsi; int
0x18006d70b  call    WiaTrace_ProcessTrace_Ex
0x18006d710  xor     esi, esi
0x18006d712  mov     r15d, [rsp+330h+var_2EC]
0x18006d717  test    edi, edi
0x18006d719  js      loc_18006DD59
0x18006d71f  xor     ebx, ebx
0x18006d721  test    r15b, 1
0x18006d725  jz      loc_18006DA1C
0x18006d72b  mov     [rsp+330h+var_2EC], ebx
0x18006d72f  mov     ebx, 1
0x18006d734  test    rsi, rsi
0x18006d737  jz      loc_18006D9FA
0x18006d73d  lea     rdx, [rsi+8]
0x18006d741  jmp     loc_18006D9FC
0x18006d746  xor     esi, esi
0x18006d748  mov     [rsp+330h+var_2D0], rsi
0x18006d74d  test    r15d, r15d
0x18006d750  js      short loc_18006D712
0x18006d752  mov     rcx, r13; this
0x18006d755  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18006d75a  test    eax, eax
0x18006d75c  jz      loc_18006D7FA
0x18006d762  mov     rax, [r8+0A8h]
0x18006d769  cmp     [rax+40h], rsi
0x18006d76d  jz      loc_18006D7FA
0x18006d773  lea     r8d, [rsi+1]; int
0x18006d777  lea     rdx, [rsp+330h+var_2D0]; struct CWiaItem **
0x18006d77c  call    ?FindRelatedDAITItem@CWiaItem@@QEAAJPEAPEAV1@H@Z; CWiaItem::FindRelatedDAITItem(CWiaItem * *,int)
0x18006d781  mov     rsi, [rsp+330h+var_2D0]
0x18006d786  mov     edi, eax
0x18006d788  mov     [rsp+330h+var_2F0], eax
0x18006d78c  test    rsi, rsi
0x18006d78f  jnz     short loc_18006D79F
0x18006d791  mov     edi, 80004003h
0x18006d796  mov     [rsp+330h+var_2F0], edi
0x18006d79a  mov     r15d, edi
0x18006d79d  jmp     short loc_18006D7A6
0x18006d79f  mov     r15d, eax
0x18006d7a2  test    eax, eax
0x18006d7a4  jns     short loc_18006D7EF
0x18006d7a6  lea     rcx, aCannotFindRela; "cannot find related D-AIT item"
0x18006d7ad  call    WiaTrace_TraceLog
0x18006d7b2  mov     rdx, rax; char *
0x18006d7b5  lea     rcx, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d7bc  mov     rbx, rax
0x18006d7bf  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d7c4  mov     rcx, rbx; this
0x18006d7c7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d7cc  lea     rcx, aCannotFindRela; "cannot find related D-AIT item"
0x18006d7d3  call    WiaTrace_Trace
0x18006d7d8  mov     r9d, 1; int
0x18006d7de  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d7e3  lea     r8, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d7ea  call    WiaTrace_ProcessTrace_Ex
0x18006d7ef  test    r15d, r15d
0x18006d7f2  js      loc_18006D712
0x18006d7f8  jmp     short loc_18006D7FD
0x18006d7fa  mov     rsi, r13
0x18006d7fd  cmp     [rsi+80h], r12d
0x18006d804  jnz     short loc_18006D864
0x18006d806  mov     rcx, rsi; this
0x18006d809  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x18006d80e  mov     [rsp+330h+var_2F0], eax
0x18006d812  mov     edi, eax
0x18006d814  test    eax, eax
0x18006d816  jns     short loc_18006D861
0x18006d818  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18006d81f  call    WiaTrace_TraceLog
0x18006d824  mov     rdx, rax; char *
0x18006d827  lea     rcx, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d82e  mov     rbx, rax
0x18006d831  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d836  mov     rcx, rbx; this
0x18006d839  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d83e  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18006d845  call    WiaTrace_Trace
0x18006d84a  mov     r9d, 1; int
0x18006d850  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d855  lea     r8, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d85c  call    WiaTrace_ProcessTrace_Ex
0x18006d861  mov     r15d, edi
0x18006d864  mov     rax, [rsi+0D0h]
0x18006d86b  mov     [rax+0E8h], r12d
0x18006d872  test    r15d, r15d
0x18006d875  js      loc_18006D712
0x18006d87b  mov     rax, [rsp+330h+var_2C0]
0x18006d880  mov     rax, [rax+0A8h]
0x18006d887  cmp     dword ptr [rax+68h], 1
0x18006d88b  jnz     short loc_18006D8F1
0x18006d88d  mov     rcx, r13; this
0x18006d890  call    ?ApplyCurrentContextSettings@CWiaItem@@QEAAJXZ; CWiaItem::ApplyCurrentContextSettings(void)
0x18006d895  mov     [rsp+330h+var_2F0], eax
0x18006d899  mov     edi, eax
0x18006d89b  test    eax, eax
0x18006d89d  jns     short loc_18006D8F1
0x18006d89f  mov     edx, eax
0x18006d8a1  lea     rcx, aUpdateTheCurre; "update the current item context (0x%X)"
0x18006d8a8  call    WiaTrace_TraceLog
0x18006d8ad  mov     rdx, rax; char *
0x18006d8b0  lea     rcx, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d8b7  mov     rbx, rax
0x18006d8ba  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d8bf  mov     rcx, rbx; this
0x18006d8c2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d8c7  mov     edx, edi
0x18006d8c9  lea     rcx, aUpdateTheCurre; "update the current item context (0x%X)"
0x18006d8d0  call    WiaTrace_Trace
0x18006d8d5  mov     r9d, 1; int
0x18006d8db  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d8e0  lea     r8, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d8e7  call    WiaTrace_ProcessTrace_Ex
0x18006d8ec  jmp     loc_18006D712
0x18006d8f1  mov     rcx, [rsi+0B0h]; struct CWiaDrvItem *
0x18006d8f8  call    ?ValidateWiaDrvItemAccess@@YAJPEAVCWiaDrvItem@@@Z; ValidateWiaDrvItemAccess(CWiaDrvItem *)
0x18006d8fd  mov     [rsp+330h+var_2F0], eax
0x18006d901  mov     edi, eax
0x18006d903  test    eax, eax
0x18006d905  jns     short loc_18006D93B
0x18006d907  lea     rcx, aValidatewiadrv_0; "ValidateWiaDrvItemAccess failed"
0x18006d90e  call    WiaTrace_TraceLog
0x18006d913  mov     rdx, rax; char *
0x18006d916  lea     rcx, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d91d  mov     rbx, rax
0x18006d920  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d925  mov     rcx, rbx; this
0x18006d928  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d92d  lea     rcx, aValidatewiadrv_0; "ValidateWiaDrvItemAccess failed"
0x18006d934  call    WiaTrace_Trace
0x18006d939  jmp     short loc_18006D8D5
0x18006d93b  mov     r15d, [rsp+330h+var_2EC]
0x18006d940  test    r15b, 1
0x18006d944  jnz     short loc_18006D9B5
0x18006d946  mov     rax, [rsi]
0x18006d949  lea     rdx, [rsp+330h+var_2E4]
0x18006d94e  mov     rcx, rsi
0x18006d951  mov     rax, [rax+18h]
0x18006d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d95a  test    [rsp+330h+var_2E4], 2002h
0x18006d962  jnz     short loc_18006D9B5
0x18006d964  lea     rcx, aItemIsNotOfFil; "Item is not of File type"
0x18006d96b  call    WiaTrace_TraceLog
0x18006d970  mov     rdx, rax; char *
0x18006d973  lea     rcx, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d97a  mov     rbx, rax
0x18006d97d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006d982  mov     rcx, rbx; this
0x18006d985  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006d98a  lea     rcx, aItemIsNotOfFil; "Item is not of File type"
0x18006d991  call    WiaTrace_Trace
0x18006d996  mov     r9d, 1; int
0x18006d99c  mov     [rsp+330h+lpMem], rax; lpMem
0x18006d9a1  lea     r8, aCwiaitemCommon; "CWiaItem::CommonDownload"
0x18006d9a8  call    WiaTrace_ProcessTrace_Ex
0x18006d9ad  mov     edi, r14d
0x18006d9b0  jmp     loc_18006DD6E
0x18006d9b5  mov     rcx, rsi; this
0x18006d9b8  call    ?IsLegacyDriver@CWiaItem@@QEAAHXZ; CWiaItem::IsLegacyDriver(void)
0x18006d9bd  mov     [rsp+330h+var_2E8], eax
0x18006d9c1  test    eax, eax
0x18006d9c3  jnz     loc_18006D717
0x18006d9c9  lea     ecx, [rax+18h]; Size
0x18006d9cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d9d1  test    rax, rax
0x18006d9d4  jz      short loc_18006D9E1
0x18006d9d6  mov     rcx, rax; this
0x18006d9d9  call    ??0CFilterPropertyStorage@@QEAA@XZ; CFilterPropertyStorage::CFilterPropertyStorage(void)
0x18006d9de  mov     r12, rax
0x18006d9e1  mov     rax, r12
0x18006d9e4  neg     rax
0x18006d9e7  sbb     edi, edi
0x18006d9e9  not     edi
0x18006d9eb  and     edi, 8007000Eh
0x18006d9f1  mov     [rsp+330h+var_2F0], edi
0x18006d9f5  jmp     loc_18006D717
0x18006d9fa  xor     edx, edx; struct IPropertyStorage *
0x18006d9fc  lea     r8, [rsp+330h+var_2EC]; int *
0x18006da01  mov     ecx, 1819h; unsigned int
0x18006da06  call    ?ReadPropLong@@YAJKPEAUIPropertyStorage@@PEAJ@Z; ReadPropLong(ulong,IPropertyStorage *,long *)
0x18006da0b  mov     [rsp+330h+var_2F0], eax
0x18006da0f  mov     edi, eax
0x18006da11  test    eax, eax
0x18006da13  jnz     short loc_18006DA1C
0x18006da15  test    byte ptr [rsp+330h+var_2EC], bl
0x18006da19  cmovnz  ebx, eax
0x18006da1c  test    edi, edi
0x18006da1e  js      loc_18006DD59
0x18006da24  mov     r9, [rsi+0D0h]; unsigned __int8 *
0x18006da2b  lea     r8, [rsp+330h+var_2F0]; int *
0x18006da30  mov     rdx, rsi; struct CWiaItem *
0x18006da33  lea     rcx, [rsp+330h+var_2C0]; this
0x18006da38  call    ??0LOCK_WIA_DEVICE@@QEAA@PEAVCWiaItem@@PEAJPEAE@Z; LOCK_WIA_DEVICE::LOCK_WIA_DEVICE(CWiaItem *,long *,uchar *)
0x18006da3d  mov     edi, [rsp+330h+var_2F0]
0x18006da41  test    edi, edi
0x18006da43  js      loc_18006DBD5
0x18006da49  call    ?IncTransferCount@@YAKXZ; IncTransferCount(void)
0x18006da4e  test    ebx, ebx
0x18006da50  jz      short loc_18006DAAF
0x18006da52  mov     rax, [rsp+330h+var_2C8]
0x18006da57  and     r15d, 0FFFFFFFEh
0x18006da5b  mov     r14, [rsp+330h+var_2D8]
0x18006da60  mov     rdx, rsi; struct CWiaItem *
0x18006da63  mov     r9d, [rsp+330h+var_2E8]; int
0x18006da68  mov     rcx, r13; this
0x18006da6b  mov     r8d, [rsp+330h+var_2E0]; int
0x18006da70  mov     [rsp+330h+var_2F8], r12; struct CFilterPropertyStorage *
0x18006da75  mov     [rsp+330h+var_300], rax; struct IWiaImageFilter *
0x18006da7a  mov     [rsp+330h+var_308], r14; struct IWiaTransferCallback *
0x18006da7f  mov     dword ptr [rsp+330h+lpMem], r15d; int
0x18006da84  call    ?RecursiveFolderDownload@CWiaItem@@AEAAJPEAV1@HHJPEAUIWiaTransferCallback@@PEAUIWiaImageFilter@@PEAVCFilterPropertyStorage@@@Z; CWiaItem::RecursiveFolderDownload(CWiaItem *,int,int,long,IWiaTransferCallback *,IWiaImageFilter *,CFilterPropertyStorage *)
0x18006da89  mov     edx, 2; int
0x18006da8e  mov     rcx, r14; struct IWiaTransferCallback *
0x18006da91  mov     edi, eax
0x18006da93  call    ?SendEndOfTransferMessage@@YAJPEAUIWiaTransferCallback@@J@Z; SendEndOfTransferMessage(IWiaTransferCallback *,long)
0x18006da98  test    edi, edi
0x18006da9a  js      loc_18006DBCB
0x18006daa0  test    eax, eax
0x18006daa2  jns     loc_18006DBCB
0x18006daa8  mov     edi, eax
0x18006daaa  jmp     loc_18006DBCB
0x18006daaf  mov     ebx, [rsp+330h+var_2E8]
0x18006dab3  mov     rcx, rsi; this
0x18006dab6  mov     r13, [rsp+330h+var_2D8]
0x18006dabb  test    ebx, ebx
0x18006dabd  jz      short loc_18006DACC
0x18006dabf  mov     r8, rsi; struct CWiaItem *
0x18006dac2  mov     rdx, r13; struct IWiaTransferCallback *
0x18006dac5  call    ?DoLegacyDownload@CWiaItem@@AEAAJPEAUIWiaTransferCallback@@PEAV1@@Z; CWiaItem::DoLegacyDownload(IWiaTransferCallback *,CWiaItem *)
0x18006daca  jmp     short loc_18006DAE0
0x18006dacc  mov     edx, [rsp+330h+var_2E0]; int
0x18006dad0  mov     r9, r13; struct IWiaTransferCallback *
0x18006dad3  mov     r8d, r15d; int
0x18006dad6  mov     [rsp+330h+lpMem], rsi; unsigned __int8 *
0x18006dadb  call    ?DoDownload@CWiaItem@@AEAAJHJPEAUIWiaTransferCallback@@PEAE@Z; CWiaItem::DoDownload(int,long,IWiaTransferCallback *,uchar *)
0x18006dae0  mov     edx, 2; int
  ... truncated ...
```
