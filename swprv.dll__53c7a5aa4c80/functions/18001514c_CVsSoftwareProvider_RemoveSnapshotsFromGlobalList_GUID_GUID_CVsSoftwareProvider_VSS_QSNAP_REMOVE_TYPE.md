# CVsSoftwareProvider::RemoveSnapshotsFromGlobalList(_GUID,_GUID,CVsSoftwareProvider::_VSS_QSNAP_REMOVE_TYPE)

- ea: `0x18001514c`
- end: `0x18001585d`
- name: `?RemoveSnapshotsFromGlobalList@CVsSoftwareProvider@@CAXU_GUID@@0W4_VSS_QSNAP_REMOVE_TYPE@1@@Z`
- size: `1809`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000dc7c`
- `0x18000e900`
- `0x180012e50`

## callees

- `0x18000212c`
- `0x1800036c4`
- `0x180008e34`
- `0x18001514c`
- `0x1800190d0`
- `0x1800192bc`
- `0x1800192e0`
- `0x1800193a4`
- `0x180019458`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800419fc`

## string_xrefs

- `0x180015188`: `CVsSoftwareProvider::RemoveSnapshotsFromGlobalList`
- `0x180015418`: `CVsSoftwareProvider::RemoveSnapshotsFromGlobalList`
- `0x18001568b`: `CVsSoftwareProvider::RemoveSnapshotsFromGlobalList`
- `0x18001530a`: `FilterId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}CurrentSSID = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}eRemoveType = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVsSoftwareProvider::RemoveSnapshotsFromGlobalList(unsigned __int8 *a1, __int64 a2, int a3)
{
  void *v5; // rdi
  struct _GUID *v6; // rbx
  unsigned int v7; // esi
  struct IUnknown *v8; // rax
  struct IUnknown *v9; // rbx
  struct IUnknown *v10; // rdx
  struct CVssQueuedSnapshot *NextByProviderInstance; // rax
  int v12; // r13d
  int v13; // r12d
  int v14; // r15d
  int v15; // r14d
  int v16; // esi
  struct _GUID *ProviderInstanceId; // rdi
  __int64 v18; // [rsp+20h] [rbp-1B0h]
  __int64 v19; // [rsp+28h] [rbp-1A8h]
  __int64 v20; // [rsp+30h] [rbp-1A0h]
  __int64 v21; // [rsp+38h] [rbp-198h]
  __int64 v22; // [rsp+40h] [rbp-190h]
  __int64 v23; // [rsp+48h] [rbp-188h]
  __int64 v24; // [rsp+50h] [rbp-180h]
  __int64 v25; // [rsp+58h] [rbp-178h]
  __int64 v26; // [rsp+60h] [rbp-170h]
  __int64 v27; // [rsp+68h] [rbp-168h]
  __int64 v28; // [rsp+70h] [rbp-160h]
  __int64 v29; // [rsp+78h] [rbp-158h]
  __int64 v30; // [rsp+80h] [rbp-150h]
  __int64 v31; // [rsp+88h] [rbp-148h]
  __int64 v32; // [rsp+90h] [rbp-140h]
  __int64 v33; // [rsp+98h] [rbp-138h]
  __int64 v34; // [rsp+A0h] [rbp-130h]
  __int64 v35; // [rsp+A8h] [rbp-128h]
  __int64 v36; // [rsp+B0h] [rbp-120h]
  __int64 v37; // [rsp+B8h] [rbp-118h]
  __int64 v38; // [rsp+C0h] [rbp-110h]
  __int64 v39; // [rsp+C8h] [rbp-108h]
  __int64 v40; // [rsp+D0h] [rbp-100h]
  __int64 v41; // [rsp+D8h] [rbp-F8h]
  __int64 v42; // [rsp+E0h] [rbp-F0h]
  __int64 v43; // [rsp+E8h] [rbp-E8h]
  __int64 v44; // [rsp+F0h] [rbp-E0h]
  __int64 v45; // [rsp+F8h] [rbp-D8h]
  __int64 v46; // [rsp+100h] [rbp-D0h]
  __int64 v47; // [rsp+108h] [rbp-C8h]
  __int64 v48; // [rsp+110h] [rbp-C0h]
  __int64 v49; // [rsp+118h] [rbp-B8h]
  __int64 v50; // [rsp+120h] [rbp-B0h]
  __int64 v51; // [rsp+138h] [rbp-98h]
  __int64 v52; // [rsp+140h] [rbp-90h]
  struct IUnknown *v53; // [rsp+150h] [rbp-80h] BYREF
  int v54; // [rsp+158h] [rbp-78h]
  VSS_SNAPSHOT_STATE m_eStatus; // [rsp+15Ch] [rbp-74h]
  int v56; // [rsp+160h] [rbp-70h]
  struct _GUID *v57; // [rsp+168h] [rbp-68h]
  struct IUnknown *v58; // [rsp+170h] [rbp-60h] BYREF
  int v59; // [rsp+178h] [rbp-58h]
  int v60; // [rsp+17Ch] [rbp-54h]
  int v61; // [rsp+180h] [rbp-50h]
  int v62; // [rsp+184h] [rbp-4Ch]
  int v63; // [rsp+188h] [rbp-48h]
  int v64; // [rsp+18Ch] [rbp-44h]
  int v65; // [rsp+190h] [rbp-40h]
  int Data3; // [rsp+194h] [rbp-3Ch]
  int Data2; // [rsp+198h] [rbp-38h]
  unsigned int Data1; // [rsp+19Ch] [rbp-34h]
  int v69; // [rsp+1A0h] [rbp-30h]
  int v70; // [rsp+1A4h] [rbp-2Ch]
  int v71; // [rsp+1A8h] [rbp-28h]
  int v72; // [rsp+1ACh] [rbp-24h]
  int v73; // [rsp+1B0h] [rbp-20h]
  int v74; // [rsp+1B4h] [rbp-1Ch]
  int v75; // [rsp+1B8h] [rbp-18h]
  int v76; // [rsp+1BCh] [rbp-14h]
  int v77; // [rsp+1C0h] [rbp-10h]
  unsigned int v78; // [rsp+1C4h] [rbp-Ch]
  int v79; // [rsp+1C8h] [rbp-8h]
  int v80; // [rsp+1CCh] [rbp-4h]
  int v81; // [rsp+1D0h] [rbp+0h]
  int v82; // [rsp+1D4h] [rbp+4h]
  LONG m_lSnapshotAttributes; // [rsp+1D8h] [rbp+8h]
  int v84; // [rsp+1DCh] [rbp+Ch]
  int v85; // [rsp+1E0h] [rbp+10h]
  struct _VSS_SNAPSHOT_PROP *SnapshotProperties; // [rsp+1E8h] [rbp+18h]
  VSS_ID Buf2; // [rsp+1F0h] [rbp+20h] BYREF
  void *Buf1; // [rsp+200h] [rbp+30h]
  _QWORD v89[2]; // [rsp+208h] [rbp+38h] BYREF
  const unsigned __int16 *v90; // [rsp+218h] [rbp+48h] BYREF
  const wchar_t *v91; // [rsp+220h] [rbp+50h]
  const unsigned __int16 *v92; // [rsp+228h] [rbp+58h]
  int v93; // [rsp+230h] [rbp+60h]
  int v94; // [rsp+234h] [rbp+64h]
  int v95; // [rsp+238h] [rbp+68h]
  _BYTE v96[120]; // [rsp+240h] [rbp+70h] BYREF
  int v97; // [rsp+2B8h] [rbp+E8h]
  VSS_PWSZ m_pwszOriginalVolumeName; // [rsp+2C0h] [rbp+F0h]
  VSS_TIMESTAMP m_tsCreationTimestamp; // [rsp+2C8h] [rbp+F8h]
  struct _GUID v100; // [rsp+2D0h] [rbp+100h] BYREF
  struct _GUID v101; // [rsp+2E0h] [rbp+110h] BYREF
  struct _GUID v102; // [rsp+2F0h] [rbp+120h] BYREF
  struct _GUID v103; // [rsp+300h] [rbp+130h] BYREF
  struct _GUID v104; // [rsp+310h] [rbp+140h] BYREF
  struct _GUID v105; // [rsp+320h] [rbp+150h] BYREF
  struct _GUID v106; // [rsp+330h] [rbp+160h] BYREF
  struct _GUID v107; // [rsp+340h] [rbp+170h] BYREF
  struct _GUID v108; // [rsp+350h] [rbp+180h] BYREF
  struct _GUID v109; // [rsp+360h] [rbp+190h] BYREF
  struct _GUID v110; // [rsp+370h] [rbp+1A0h] BYREF
  LPVOID v111[20]; // [rsp+380h] [rbp+1B0h] BYREF

  v56 = a3;
  Buf1 = (void *)a2;
  v57 = (struct _GUID *)a1;
  v90 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v91 = L"CVsSoftwareProvider::RemoveSnapshotsFromGlobalList";
  v92 = L"SPRPROVC";
  v93 = 1861;
  v94 = 2;
  v95 = 255;
  v97 = 0x1000000;
  memset_0(v96, 0, sizeof(v96));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v111, (__int64)&v90, 0);
  v90 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v91 = L"CVsSoftwareProvider::RemoveSnapshotsFromGlobalList";
  v92 = L"SPRPROVC";
  v93 = 1863;
  v94 = 2;
  v95 = 255;
  v97 = 0x1000000;
  memset_0(v96, 0, sizeof(v96));
  v5 = Buf1;
  v6 = v57;
  CVssFunctionTracer::Trace(
    v111,
    &v90,
    L"FilterId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}CurrentSSID = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x"
     "%.2x%.2x}eRemoveType = %d",
    v57->Data1,
    v57->Data2,
    v57->Data3,
    v57->Data4[0],
    v57->Data4[1],
    v57->Data4[2],
    v57->Data4[3],
    a1[12],
    a1[13],
    a1[14],
    a1[15],
    *(_DWORD *)Buf1,
    *(unsigned __int16 *)(a2 + 4),
    *(unsigned __int16 *)(a2 + 6),
    *(unsigned __int8 *)(a2 + 8),
    *(unsigned __int8 *)(a2 + 9),
    *(unsigned __int8 *)(a2 + 10),
    *(unsigned __int8 *)(a2 + 11),
    *(unsigned __int8 *)(a2 + 12),
    *(unsigned __int8 *)(a2 + 13),
    *(unsigned __int8 *)(a2 + 14),
    *(unsigned __int8 *)(a2 + 15),
    v56);
  v7 = 0;
  v54 = 0;
  v89[0] = &CVssQueuedSnapshot::m_list;
  v89[1] = CVssQueuedSnapshot::m_list;
  while ( 1 )
  {
    v53 = 0;
    if ( v56 == 1 )
    {
      Buf2 = *v6;
      NextByProviderInstance = CVssSnapIterator::GetNextByProviderInstance((CVssSnapIterator *)v89, &Buf2);
      if ( !NextByProviderInstance )
        goto LABEL_13;
      v10 = (struct IUnknown *)NextByProviderInstance;
      goto LABEL_16;
    }
    if ( v56 == 2 )
      break;
    if ( v56 != 3 )
      goto LABEL_13;
    Buf2 = *v6;
    v8 = (struct IUnknown *)CVssSnapIterator::GetNextByProviderInstance((CVssSnapIterator *)v89, &Buf2);
    if ( !v8 )
      goto LABEL_13;
    ATL::AtlComPtrAssign(&v53, v8);
    v9 = v53;
    if ( !v53 )
      goto LABEL_13;
    Buf2 = CVssQueuedSnapshot::GetSnapshotProperties((CVssQueuedSnapshot *)v53)->m_SnapshotSetId;
    if ( memcmp_0(v5, &Buf2, 0x10u) && ((__int64)v9[35].lpVtbl & 8) != 0 )
    {
LABEL_17:
      if ( !v9 )
        goto LABEL_13;
      SnapshotProperties = CVssQueuedSnapshot::GetSnapshotProperties((CVssQueuedSnapshot *)v9);
      m_eStatus = SnapshotProperties->m_eStatus;
      m_lSnapshotAttributes = SnapshotProperties->m_lSnapshotAttributes;
      m_tsCreationTimestamp = SnapshotProperties->m_tsCreationTimestamp;
      m_pwszOriginalVolumeName = SnapshotProperties->m_pwszOriginalVolumeName;
      v84 = SnapshotProperties->m_SnapshotId.Data4[7];
      v59 = SnapshotProperties->m_SnapshotId.Data4[6];
      v60 = SnapshotProperties->m_SnapshotId.Data4[5];
      v61 = SnapshotProperties->m_SnapshotId.Data4[4];
      v62 = SnapshotProperties->m_SnapshotId.Data4[3];
      v63 = SnapshotProperties->m_SnapshotId.Data4[2];
      v64 = SnapshotProperties->m_SnapshotId.Data4[1];
      v65 = SnapshotProperties->m_SnapshotId.Data4[0];
      Data3 = SnapshotProperties->m_SnapshotId.Data3;
      Data2 = SnapshotProperties->m_SnapshotId.Data2;
      Data1 = SnapshotProperties->m_SnapshotId.Data1;
      v69 = SnapshotProperties->m_SnapshotSetId.Data4[7];
      v70 = SnapshotProperties->m_SnapshotSetId.Data4[6];
      v71 = SnapshotProperties->m_SnapshotSetId.Data4[5];
      v72 = SnapshotProperties->m_SnapshotSetId.Data4[4];
      v73 = SnapshotProperties->m_SnapshotSetId.Data4[3];
      v79 = SnapshotProperties->m_SnapshotSetId.Data4[2];
      v74 = SnapshotProperties->m_SnapshotSetId.Data4[1];
      v75 = SnapshotProperties->m_SnapshotSetId.Data4[0];
      v76 = SnapshotProperties->m_SnapshotSetId.Data3;
      v77 = SnapshotProperties->m_SnapshotSetId.Data2;
      v78 = SnapshotProperties->m_SnapshotSetId.Data1;
      v85 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v105)->Data4[7];
      v80 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v100)->Data4[6];
      v81 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v101)->Data4[5];
      v82 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v102)->Data4[4];
      LODWORD(v58) = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v103)->Data4[3];
      v12 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v104)->Data4[2];
      v13 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v110)->Data4[1];
      v14 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v106)->Data4[0];
      v15 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v107)->Data3;
      v16 = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v108)->Data2;
      ProviderInstanceId = CVssQueuedSnapshot::GetProviderInstanceId((CVssQueuedSnapshot *)v9, &v109);
      v90 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v91 = L"CVsSoftwareProvider::RemoveSnapshotsFromGlobalList";
      v92 = L"SPRPROVC";
      v93 = 1915;
      v94 = 2;
      v95 = 255;
      v97 = 0x1000000;
      memset_0(v96, 0, sizeof(v96));
      LODWORD(v52) = m_eStatus;
      LODWORD(v51) = m_lSnapshotAttributes;
      LODWORD(v50) = v84;
      LODWORD(v49) = v59;
      LODWORD(v48) = v60;
      LODWORD(v47) = v61;
      LODWORD(v46) = v62;
      LODWORD(v45) = v63;
      LODWORD(v44) = v64;
      LODWORD(v43) = v65;
      LODWORD(v42) = Data3;
      LODWORD(v41) = Data2;
      LODWORD(v40) = Data1;
      LODWORD(v39) = v69;
      LODWORD(v38) = v70;
      LODWORD(v37) = v71;
      LODWORD(v36) = v72;
      LODWORD(v35) = v73;
      LODWORD(v34) = v79;
      LODWORD(v33) = v74;
      LODWORD(v32) = v75;
      LODWORD(v31) = v76;
      LODWORD(v30) = v77;
      LODWORD(v29) = v78;
      LODWORD(v28) = v85;
      LODWORD(v27) = v80;
      LODWORD(v26) = v81;
      LODWORD(v25) = v82;
      LODWORD(v24) = (_DWORD)v58;
      LODWORD(v23) = v12;
      LODWORD(v22) = v13;
      LODWORD(v21) = v14;
      LODWORD(v20) = v15;
      LODWORD(v19) = v16;
      LODWORD(v18) = ProviderInstanceId->Data1;
      CVssFunctionTracer::Trace(
        v111,
        &v90,
        L"Field values for %p: \n"
         " *ProvInstanceId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  SnapshotId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
         "  VolumeName = %s\n"
         "  Creation timestamp = 0x%016I64x\n"
         "  lAttributes = 0x%08lx\n"
         "  status = %d\n",
        SnapshotProperties,
        v18,
        v19,
        v20,
        v21,
        v22,
        v23,
        v24,
        v25,
        v26,
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        v33,
        v34,
        v35,
        v36,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48,
        v49,
        v50,
        m_pwszOriginalVolumeName,
        m_tsCreationTimestamp,
        v51,
        v52);
      CVssQueuedSnapshot::DetachFromGlobalList((CVssQueuedSnapshot *)v9);
      v7 = ++v54;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
      v6 = v57;
      v5 = Buf1;
    }
    else
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
      v6 = v57;
    }
  }
  v58 = 0;
  if ( CVssDLListIterator<CVssQueuedSnapshot *>::GetNext((__int64)v89, &v58) )
  {
    v10 = v58;
    if ( v58 )
    {
LABEL_16:
      ATL::AtlComPtrAssign(&v53, v10);
      v9 = v53;
      goto LABEL_17;
    }
  }
LABEL_13:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v53);
  v90 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v91 = L"CVsSoftwareProvider::RemoveSnapshotsFromGlobalList";
  v92 = L"SPRPROVC";
  v93 = 1937;
  v94 = 2;
  v95 = 255;
  v97 = 0x1000000;
  memset_0(v96, 0, sizeof(v96));
  CVssFunctionTracer::Trace(v111, &v90, L" %ld snapshots were detached", v7);
  CVssFunctionTracer::~CVssFunctionTracer(v111);
}

```

## disassembly

```asm
0x18001514c  mov     [rsp-8+arg_18], rbx
0x180015151  push    rbp
0x180015152  push    rsi
0x180015153  push    rdi
0x180015154  push    r12
0x180015156  push    r13
0x180015158  push    r14
0x18001515a  push    r15
0x18001515c  lea     rbp, [rsp-220h]
0x180015164  sub     rsp, 3F0h
0x18001516b  mov     [rbp+250h+var_2C0], r8d
0x18001516f  mov     rsi, rdx
0x180015172  mov     [rbp+250h+Buf1], rdx
0x180015176  mov     r13, rcx
0x180015179  mov     [rbp+250h+var_2B8], rcx
0x18001517d  lea     rbx, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180015184  mov     [rbp+250h+var_208], rbx
0x180015188  lea     rdi, aCvssoftwarepro; "CVsSoftwareProvider::RemoveSnapshotsFro"...
0x18001518f  mov     [rbp+250h+var_200], rdi
0x180015193  lea     r14, aSprprovc; "SPRPROVC"
0x18001519a  mov     [rbp+250h+var_1F8], r14
0x18001519e  mov     [rbp+250h+var_1F0], 745h
0x1800151a5  mov     r15d, 2
0x1800151ab  mov     [rbp+250h+var_1EC], r15d
0x1800151af  mov     r12d, 0FFh
0x1800151b5  mov     [rbp+250h+var_1E8], r12d
0x1800151b9  mov     [rbp+250h+var_168], 1000000h
0x1800151c3  xor     edx, edx; Val
0x1800151c5  lea     r8d, [r15+76h]; Size
0x1800151c9  lea     rcx, [rbp+250h+var_1E0]; void *
0x1800151cd  call    memset_0
0x1800151d2  xor     r8d, r8d
0x1800151d5  lea     rdx, [rbp+250h+var_208]
0x1800151d9  lea     rcx, [rbp+250h+var_A0]
0x1800151e0  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800151e5  nop
0x1800151e6  mov     [rbp+250h+var_208], rbx
0x1800151ea  mov     [rbp+250h+var_200], rdi
0x1800151ee  mov     [rbp+250h+var_1F8], r14
0x1800151f2  mov     [rbp+250h+var_1F0], 747h
0x1800151f9  mov     [rbp+250h+var_1EC], r15d
0x1800151fd  mov     [rbp+250h+var_1E8], r12d
0x180015201  mov     [rbp+250h+var_168], 1000000h
0x18001520b  xor     edx, edx; Val
0x18001520d  lea     r8d, [r15+76h]; Size
0x180015211  lea     rcx, [rbp+250h+var_1E0]; void *
0x180015215  call    memset_0
0x18001521a  movzx   eax, byte ptr [rsi+0Fh]
0x18001521e  movzx   ecx, byte ptr [rsi+0Eh]
0x180015222  movzx   edx, byte ptr [rsi+0Dh]
0x180015226  movzx   r8d, byte ptr [rsi+0Ch]
0x18001522b  movzx   r9d, byte ptr [rsi+0Bh]
0x180015230  movzx   r10d, byte ptr [rsi+0Ah]
0x180015235  movzx   r11d, byte ptr [rsi+9]
0x18001523a  movzx   ebx, byte ptr [rsi+8]
0x18001523e  movzx   edi, word ptr [rsi+6]
0x180015242  movzx   esi, word ptr [rsi+4]
0x180015246  movzx   r14d, byte ptr [r13+0Fh]
0x18001524b  mov     [rbp+250h+var_2C8], r14d
0x18001524f  movzx   r15d, byte ptr [r13+0Eh]
0x180015254  movzx   r12d, byte ptr [r13+0Dh]
0x180015259  movzx   r13d, byte ptr [r13+0Ch]
0x18001525e  mov     r14d, [rbp+250h+var_2C0]
0x180015262  mov     dword ptr [rsp+420h+var_358], r14d
0x18001526a  mov     dword ptr [rsp+420h+var_360], eax
0x180015271  mov     dword ptr [rsp+420h+var_368], ecx
0x180015278  mov     dword ptr [rsp+420h+var_370], edx
0x18001527f  mov     dword ptr [rsp+420h+var_378], r8d
0x180015287  mov     dword ptr [rsp+420h+var_380], r9d
0x18001528f  mov     dword ptr [rsp+420h+var_388], r10d
0x180015297  mov     dword ptr [rsp+420h+var_390], r11d
0x18001529f  mov     dword ptr [rsp+420h+var_398], ebx
0x1800152a6  mov     dword ptr [rsp+420h+var_3A0], edi
0x1800152ad  mov     dword ptr [rsp+420h+var_3A8], esi
0x1800152b1  mov     rdi, [rbp+250h+Buf1]
0x1800152b5  mov     eax, [rdi]
0x1800152b7  mov     dword ptr [rsp+420h+var_3B0], eax
0x1800152bb  mov     r14d, [rbp+250h+var_2C8]
0x1800152bf  mov     dword ptr [rsp+420h+var_3B8], r14d
0x1800152c4  mov     dword ptr [rsp+420h+var_3C0], r15d
0x1800152c9  mov     dword ptr [rsp+420h+var_3C8], r12d
0x1800152ce  mov     dword ptr [rsp+420h+var_3D0], r13d
0x1800152d3  mov     rbx, [rbp+250h+var_2B8]
0x1800152d7  movzx   eax, byte ptr [rbx+0Bh]
0x1800152db  mov     dword ptr [rsp+420h+var_3D8], eax
0x1800152df  movzx   eax, byte ptr [rbx+0Ah]
0x1800152e3  mov     dword ptr [rsp+420h+var_3E0], eax
0x1800152e7  movzx   eax, byte ptr [rbx+9]
0x1800152eb  mov     dword ptr [rsp+420h+var_3E8], eax
0x1800152ef  movzx   eax, byte ptr [rbx+8]
0x1800152f3  mov     dword ptr [rsp+420h+var_3F0], eax
0x1800152f7  movzx   eax, word ptr [rbx+6]
0x1800152fb  mov     dword ptr [rsp+420h+var_3F8], eax
0x1800152ff  movzx   eax, word ptr [rbx+4]
0x180015303  mov     dword ptr [rsp+420h+var_400], eax
0x180015307  mov     r9d, [rbx]
0x18001530a  lea     r8, aFilterid8x4x4x; "FilterId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2"...
0x180015311  lea     rdx, [rbp+250h+var_208]
0x180015315  lea     rcx, [rbp+250h+var_A0]
0x18001531c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180015321  xor     esi, esi
0x180015323  mov     [rbp+250h+var_2C8], esi
0x180015326  lea     rax, ?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x18001532d  mov     [rbp+250h+var_218], rax
0x180015331  mov     rax, cs:?m_list@CVssQueuedSnapshot@@0V?$CVssDLList@PEAVCVssQueuedSnapshot@@@@A; CVssDLList<CVssQueuedSnapshot *> CVssQueuedSnapshot::m_list
0x180015338  mov     [rbp+250h+var_210], rax
0x18001533c  mov     [rbp+250h+var_2D0], 0
0x180015344  mov     ecx, [rbp+250h+var_2C0]
0x180015347  sub     ecx, 1
0x18001534a  jz      loc_18001549E
0x180015350  sub     ecx, 1
0x180015353  jz      loc_1800153DE
0x180015359  cmp     ecx, 1
0x18001535c  jnz     loc_180015404
0x180015362  movaps  xmm0, xmmword ptr [rbx]
0x180015365  movdqa  [rbp+250h+Buf2], xmm0
0x18001536a  lea     rdx, [rbp+250h+Buf2]; struct _GUID
0x18001536e  lea     rcx, [rbp+250h+var_218]; this
0x180015372  call    ?GetNextByProviderInstance@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextByProviderInstance(_GUID)
0x180015377  test    rax, rax
0x18001537a  jz      loc_180015404
0x180015380  mov     rdx, rax; struct IUnknown *
0x180015383  lea     rcx, [rbp+250h+var_2D0]; struct IUnknown **
0x180015387  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001538c  mov     rbx, [rbp+250h+var_2D0]
0x180015390  test    rbx, rbx
0x180015393  jz      short loc_180015404
0x180015395  mov     rcx, rbx; this
0x180015398  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x18001539d  movups  xmm0, xmmword ptr [rax+10h]
0x1800153a1  movdqu  [rbp+250h+Buf2], xmm0
0x1800153a6  mov     r8d, 10h; Size
0x1800153ac  lea     rdx, [rbp+250h+Buf2]; Buf2
0x1800153b0  mov     rcx, rdi; Buf1
0x1800153b3  call    memcmp_0
0x1800153b8  test    eax, eax
0x1800153ba  jnz     short loc_1800153CE
0x1800153bc  lea     rcx, [rbp+250h+var_2D0]
0x1800153c0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800153c5  mov     rbx, [rbp+250h+var_2B8]
0x1800153c9  jmp     loc_18001533C
0x1800153ce  mov     eax, [rbx+118h]
0x1800153d4  test    al, 8
0x1800153d6  jnz     loc_1800154CC
0x1800153dc  jmp     short loc_1800153BC
0x1800153de  mov     [rbp+250h+var_2B0], 0
0x1800153e6  lea     rdx, [rbp+250h+var_2B0]
0x1800153ea  lea     rcx, [rbp+250h+var_218]
0x1800153ee  call    ?GetNext@?$CVssDLListIterator@PEAVCVssQueuedSnapshot@@@@QEAA_NAEAPEAVCVssQueuedSnapshot@@@Z; CVssDLListIterator<CVssQueuedSnapshot *>::GetNext(CVssQueuedSnapshot * &)
0x1800153f3  test    al, al
0x1800153f5  jz      short loc_180015404
0x1800153f7  mov     rdx, [rbp+250h+var_2B0]
0x1800153fb  test    rdx, rdx
0x1800153fe  jnz     loc_1800154BF
0x180015404  lea     rcx, [rbp+250h+var_2D0]
0x180015408  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001540d  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x180015414  mov     [rbp+250h+var_208], rax
0x180015418  lea     rax, aCvssoftwarepro; "CVsSoftwareProvider::RemoveSnapshotsFro"...
0x18001541f  mov     [rbp+250h+var_200], rax
0x180015423  lea     rax, aSprprovc; "SPRPROVC"
0x18001542a  mov     [rbp+250h+var_1F8], rax
0x18001542e  mov     [rbp+250h+var_1F0], 791h
0x180015435  mov     [rbp+250h+var_1EC], 2
0x18001543c  mov     [rbp+250h+var_1E8], 0FFh
0x180015443  mov     [rbp+250h+var_168], 1000000h
0x18001544d  xor     edx, edx; Val
0x18001544f  lea     r8d, [rdx+78h]; Size
0x180015453  lea     rcx, [rbp+250h+var_1E0]; void *
0x180015457  call    memset_0
0x18001545c  mov     r9d, esi
0x18001545f  lea     r8, aLdSnapshotsWer; " %ld snapshots were detached"
0x180015466  lea     rdx, [rbp+250h+var_208]
0x18001546a  lea     rcx, [rbp+250h+var_A0]
0x180015471  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180015476  nop
0x180015477  lea     rcx, [rbp+250h+var_A0]; this
0x18001547e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180015483  mov     rbx, [rsp+420h+arg_18]
0x18001548b  add     rsp, 3F0h
0x180015492  pop     r15
0x180015494  pop     r14
0x180015496  pop     r13
0x180015498  pop     r12
0x18001549a  pop     rdi
0x18001549b  pop     rsi
0x18001549c  pop     rbp
0x18001549d  retn
0x18001549e  movaps  xmm0, xmmword ptr [rbx]
0x1800154a1  movdqa  [rbp+250h+Buf2], xmm0
0x1800154a6  lea     rdx, [rbp+250h+Buf2]; struct _GUID
0x1800154aa  lea     rcx, [rbp+250h+var_218]; this
0x1800154ae  call    ?GetNextByProviderInstance@CVssSnapIterator@@QEAAPEAVCVssQueuedSnapshot@@U_GUID@@@Z; CVssSnapIterator::GetNextByProviderInstance(_GUID)
0x1800154b3  test    rax, rax
0x1800154b6  jz      loc_180015404
0x1800154bc  mov     rdx, rax; struct IUnknown *
0x1800154bf  lea     rcx, [rbp+250h+var_2D0]; struct IUnknown **
0x1800154c3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800154c8  mov     rbx, [rbp+250h+var_2D0]
0x1800154cc  test    rbx, rbx
0x1800154cf  jz      loc_180015404
0x1800154d5  mov     rcx, rbx; this
0x1800154d8  call    ?GetSnapshotProperties@CVssQueuedSnapshot@@QEAAPEAU_VSS_SNAPSHOT_PROP@@XZ; CVssQueuedSnapshot::GetSnapshotProperties(void)
0x1800154dd  mov     rcx, rax
0x1800154e0  mov     [rbp+250h+var_238], rax
0x1800154e4  mov     eax, [rax+78h]
0x1800154e7  mov     [rbp+250h+var_2C4], eax
0x1800154ea  mov     eax, [rcx+68h]
0x1800154ed  mov     [rbp+250h+var_248], eax
0x1800154f0  mov     rax, [rcx+70h]
0x1800154f4  mov     [rbp+250h+var_158], rax
0x1800154fb  mov     rax, [rcx+30h]
0x1800154ff  mov     [rbp+250h+var_160], rax
0x180015506  movzx   eax, byte ptr [rcx+0Fh]
0x18001550a  mov     [rbp+250h+var_244], eax
0x18001550d  movzx   eax, byte ptr [rcx+0Eh]
0x180015511  mov     [rbp+250h+var_2A8], eax
0x180015514  movzx   eax, byte ptr [rcx+0Dh]
0x180015518  mov     [rbp+250h+var_2A4], eax
0x18001551b  movzx   eax, byte ptr [rcx+0Ch]
0x18001551f  mov     [rbp+250h+var_2A0], eax
0x180015522  movzx   eax, byte ptr [rcx+0Bh]
0x180015526  mov     [rbp+250h+var_29C], eax
0x180015529  movzx   eax, byte ptr [rcx+0Ah]
0x18001552d  mov     [rbp+250h+var_298], eax
0x180015530  movzx   eax, byte ptr [rcx+9]
0x180015534  mov     [rbp+250h+var_294], eax
0x180015537  movzx   eax, byte ptr [rcx+8]
0x18001553b  mov     [rbp+250h+var_290], eax
0x18001553e  movzx   eax, word ptr [rcx+6]
0x180015542  mov     [rbp+250h+var_28C], eax
0x180015545  movzx   eax, word ptr [rcx+4]
0x180015549  mov     [rbp+250h+var_288], eax
0x18001554c  mov     eax, [rcx]
0x18001554e  mov     [rbp+250h+var_284], eax
0x180015551  movzx   eax, byte ptr [rcx+1Fh]
0x180015555  mov     [rbp+250h+var_280], eax
0x180015558  movzx   eax, byte ptr [rcx+1Eh]
0x18001555c  mov     [rbp+250h+var_27C], eax
0x18001555f  movzx   eax, byte ptr [rcx+1Dh]
0x180015563  mov     [rbp+250h+var_278], eax
0x180015566  movzx   eax, byte ptr [rcx+1Ch]
0x18001556a  mov     [rbp+250h+var_274], eax
0x18001556d  movzx   eax, byte ptr [rcx+1Bh]
0x180015571  mov     [rbp+250h+var_270], eax
0x180015574  movzx   eax, byte ptr [rcx+1Ah]
0x180015578  mov     [rbp+250h+var_258], eax
0x18001557b  movzx   eax, byte ptr [rcx+19h]
0x18001557f  mov     [rbp+250h+var_26C], eax
0x180015582  movzx   eax, byte ptr [rcx+18h]
0x180015586  mov     [rbp+250h+var_268], eax
0x180015589  movzx   eax, word ptr [rcx+16h]
0x18001558d  mov     [rbp+250h+var_264], eax
0x180015590  movzx   eax, word ptr [rcx+14h]
0x180015594  mov     [rbp+250h+var_260], eax
0x180015597  mov     eax, [rcx+10h]
0x18001559a  mov     [rbp+250h+var_25C], eax
0x18001559d  lea     rdx, [rbp+250h+var_100]; retstr
0x1800155a4  mov     rcx, rbx; this
0x1800155a7  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x1800155ac  movzx   eax, byte ptr [rax+0Fh]
0x1800155b0  mov     [rbp+250h+var_240], eax
0x1800155b3  lea     rdx, [rbp+250h+var_150]; retstr
0x1800155ba  mov     rcx, rbx; this
0x1800155bd  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x1800155c2  movzx   eax, byte ptr [rax+0Eh]
0x1800155c6  mov     [rbp+250h+var_254], eax
0x1800155c9  lea     rdx, [rbp+250h+var_140]; retstr
0x1800155d0  mov     rcx, rbx; this
0x1800155d3  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x1800155d8  movzx   eax, byte ptr [rax+0Dh]
0x1800155dc  mov     [rbp+250h+var_250], eax
0x1800155df  lea     rdx, [rbp+250h+var_130]; retstr
0x1800155e6  mov     rcx, rbx; this
0x1800155e9  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x1800155ee  movzx   eax, byte ptr [rax+0Ch]
0x1800155f2  mov     [rbp+250h+var_24C], eax
0x1800155f5  lea     rdx, [rbp+250h+var_120]; retstr
0x1800155fc  mov     rcx, rbx; this
0x1800155ff  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x180015604  movzx   eax, byte ptr [rax+0Bh]
0x180015608  mov     dword ptr [rbp+250h+var_2B0], eax
0x18001560b  lea     rdx, [rbp+250h+var_110]; retstr
0x180015612  mov     rcx, rbx; this
0x180015615  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x18001561a  movzx   r13d, byte ptr [rax+0Ah]
0x18001561f  lea     rdx, [rbp+250h+var_B0]; retstr
0x180015626  mov     rcx, rbx; this
0x180015629  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x18001562e  movzx   r12d, byte ptr [rax+9]
0x180015633  lea     rdx, [rbp+250h+var_F0]; retstr
0x18001563a  mov     rcx, rbx; this
0x18001563d  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x180015642  movzx   r15d, byte ptr [rax+8]
0x180015647  lea     rdx, [rbp+250h+var_E0]; retstr
0x18001564e  mov     rcx, rbx; this
0x180015651  call    ?GetProviderInstanceId@CVssQueuedSnapshot@@QEAA?AU_GUID@@XZ; CVssQueuedSnapshot::GetProviderInstanceId(void)
0x180015656  movzx   r14d, word ptr [rax+6]
0x18001565b  lea     rdx, [rbp+250h+var_D0]; retstr
0x180015662  mov     rcx, rbx; this
  ... truncated ...
```
