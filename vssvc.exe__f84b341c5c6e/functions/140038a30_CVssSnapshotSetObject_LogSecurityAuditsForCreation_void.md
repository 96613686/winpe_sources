# CVssSnapshotSetObject::LogSecurityAuditsForCreation(void)

- ea: `0x140038a30`
- end: `0x14003939b`
- name: `?LogSecurityAuditsForCreation@CVssSnapshotSetObject@@AEAAXXZ`
- size: `2411`
- prototype: `void __fastcall(CVssSnapshotSetObject *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400462e0`

## callees

- `0x140006020`
- `0x1400088fc`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140025b00`
- `0x1400326c0`
- `0x1400328ac`
- `0x140038a30`
- `0x1400393a4`
- `0x14003a8f0`
- `0x14003fb9c`
- `0x14005eaf8`
- `0x140070084`
- `0x140070da0`
- `0x140089a68`
- `0x140091560`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140039149`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140039149`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140038b00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140038b00`
- `VssTrace!__imp_VssTraceMessage` at `0x140038bc4`
- `VssTrace!__imp_VssTraceMessage` at `0x140038bc4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140038b43`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140038b43`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140038b35`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140038b35`

## string_xrefs

- `0x140038a6e`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140038be5`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140038c9b`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140038e42`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140038f40`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140039176`: `CVssSnapshotSetObject::LogSecurityAuditsForCreation`
- `0x140038cea`: `Fail to find details of the COM client process.`
- `0x140038ed7`: `The provider did not return the properties for ({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}). Fail to log security audit.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVssSnapshotSetObject::LogSecurityAuditsForCreation(PSID **this)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v5; // rdx
  int ComClientDetails; // eax
  unsigned int v7; // r13d
  unsigned int v8; // r12d
  char *v9; // r9
  PSID *v10; // rax
  int v11; // r14d
  int v12; // esi
  int v13; // edi
  int v14; // ebx
  DWORD v15; // ecx
  struct CVssDebugInfo *v16; // rax
  struct CVssDebugInfo *v17; // rax
  struct CVssDebugInfo *v18; // rax
  struct CVssDebugInfo *v19; // rax
  struct CVssDebugInfo *v20; // rax
  struct CVssDebugInfo *v21; // rax
  struct CVssDebugInfo *v22; // rax
  struct CVssDebugInfo *v23; // rax
  struct CVssDebugInfo *v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // rcx
  struct CVssDebugInfo *v27; // rax
  struct CVssDebugInfo *v28; // rax
  struct CVssDebugInfo *v29; // rax
  struct CVssDebugInfo *v30; // rax
  struct CVssDebugInfo *v31; // rax
  struct CVssDebugInfo *v32; // rax
  struct CVssDebugInfo *v33; // rax
  struct CVssDebugInfo *v34; // rax
  struct CVssDebugInfo *v35; // rax
  unsigned __int16 *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // [rsp+20h] [rbp-E0h]
  __int64 v39; // [rsp+28h] [rbp-D8h]
  __int64 v40; // [rsp+30h] [rbp-D0h]
  __int64 v41; // [rsp+38h] [rbp-C8h]
  __int64 v42; // [rsp+40h] [rbp-C0h]
  __int64 v43; // [rsp+48h] [rbp-B8h]
  __int64 v44; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h]
  __int64 v47; // [rsp+68h] [rbp-98h]
  unsigned __int8 v48; // [rsp+70h] [rbp-90h]
  unsigned __int8 v49; // [rsp+71h] [rbp-8Fh]
  unsigned __int8 v50; // [rsp+72h] [rbp-8Eh]
  unsigned __int8 v51; // [rsp+73h] [rbp-8Dh]
  unsigned __int8 v52; // [rsp+74h] [rbp-8Ch]
  unsigned __int8 v53; // [rsp+75h] [rbp-8Bh]
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  __int128 v55; // [rsp+80h] [rbp-80h] BYREF
  __int128 v56; // [rsp+90h] [rbp-70h]
  void **v57; // [rsp+A0h] [rbp-60h] BYREF
  _WORD *v58; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v59; // [rsp+B0h] [rbp-50h] BYREF
  int v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v62; // [rsp+C8h] [rbp-38h]
  unsigned int v63; // [rsp+D0h] [rbp-30h]
  int v64; // [rsp+D4h] [rbp-2Ch]
  const wchar_t *v65; // [rsp+D8h] [rbp-28h]
  unsigned int v66; // [rsp+E0h] [rbp-20h]
  DWORD TickCount; // [rsp+E4h] [rbp-1Ch]
  int v68; // [rsp+E8h] [rbp-18h]
  __int128 v69; // [rsp+F0h] [rbp-10h]
  __int128 v70; // [rsp+100h] [rbp+0h]
  __int64 v71; // [rsp+110h] [rbp+10h]
  __int128 v72; // [rsp+120h] [rbp+20h]
  __int128 v73; // [rsp+130h] [rbp+30h]
  const unsigned __int16 *v74; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v75; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v76; // [rsp+150h] [rbp+50h]
  int v77; // [rsp+158h] [rbp+58h]
  int v78; // [rsp+15Ch] [rbp+5Ch]
  int v79; // [rsp+160h] [rbp+60h]
  _BYTE v80[120]; // [rsp+168h] [rbp+68h] BYREF
  int v81; // [rsp+1E0h] [rbp+E0h]
  _QWORD v82[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v83[168]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v84[168]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v85[168]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v86[168]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v87[168]; // [rsp+498h] [rbp+398h] BYREF
  _BYTE v88[168]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v89[168]; // [rsp+5E8h] [rbp+4E8h] BYREF
  _BYTE v90[168]; // [rsp+690h] [rbp+590h] BYREF
  _BYTE v91[168]; // [rsp+738h] [rbp+638h] BYREF
  _BYTE v92[176]; // [rsp+7E0h] [rbp+6E0h] BYREF
  __int128 v93; // [rsp+890h] [rbp+790h] BYREF
  __int128 v94; // [rsp+8A0h] [rbp+7A0h]
  int v95; // [rsp+8B0h] [rbp+7B0h]
  _WORD *v96; // [rsp+8B8h] [rbp+7B8h] BYREF
  _WORD *v97; // [rsp+8C0h] [rbp+7C0h]
  _WORD *v98; // [rsp+8C8h] [rbp+7C8h]
  __int128 v99; // [rsp+8E8h] [rbp+7E8h]
  int v100; // [rsp+930h] [rbp+830h]
  unsigned __int16 v101[4]; // [rsp+940h] [rbp+840h] BYREF
  const wchar_t *v102; // [rsp+948h] [rbp+848h]
  const unsigned __int16 *v103; // [rsp+950h] [rbp+850h]
  int v104; // [rsp+958h] [rbp+858h]
  int v105; // [rsp+95Ch] [rbp+85Ch]
  int v106; // [rsp+960h] [rbp+860h]
  _BYTE v107[120]; // [rsp+968h] [rbp+868h] BYREF
  int v108; // [rsp+9E0h] [rbp+8E0h]
  unsigned __int16 v109[80]; // [rsp+9F0h] [rbp+8F0h] BYREF
  WCHAR Buffer[264]; // [rsp+A90h] [rbp+990h] BYREF

  *(_QWORD *)v101 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v102 = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
  v103 = L"CORSNPSC";
  v104 = 2282;
  v105 = 1;
  v106 = 255;
  v108 = 0x1000000;
  memset_0(v107, 0, sizeof(v107));
  v60 = 0;
  v65 = v102;
  v61 = *(_QWORD *)v101;
  v62 = v103;
  v63 = v104;
  v64 = v105;
  TickCount = GetTickCount();
  v68 = v106;
  v59 = 0xFFFFFFFF00000000uLL;
  v71 = 0;
  v69 = 0;
  v70 = 0;
  v54 = 0;
  if ( (int)VssGetTracingContextPerThread(&v54) < 0 )
  {
    v3 = v71;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v59);
    v3 = v71;
    if ( v2 >= 0 )
      v3 = v54;
    v71 = v3;
  }
  if ( v3 )
    v66 = *(_DWORD *)(v3 + 48) + 1;
  else
    v66 = 0;
  v4 = 160;
  if ( v68 != 255 )
    v4 = v68;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v59) )
    VssTraceMessage(v61, v62, v63, v66, v64, v65, L"ENTER", v4, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v101);
  if ( ((_BYTE)this[8] & 0x20) != 0 )
  {
    *(_QWORD *)v101 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
    v102 = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
    v103 = L"CORSNPSC";
    v104 = 2286;
    v105 = 1;
    v106 = 255;
    v108 = 0x1000000;
    memset_0(v107, 0, sizeof(v107));
    CVssFunctionTracer::Trace(&v59, v101, L"Transportable snapshot. Don't log on creation until import.");
  }
  else
  {
    memset_0(v109, 0, sizeof(v109));
    memset_0(v101, 0, 0xA0u);
    ComClientDetails = CVssSnapshotSetObject::GetComClientDetails(this, v5, v109, v101);
    if ( ComClientDetails < 0 || ComClientDetails == 1 )
    {
      *(_QWORD *)&v93 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
      *((_QWORD *)&v93 + 1) = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
      *(_QWORD *)&v94 = L"CORSNPSC";
      *((_QWORD *)&v94 + 1) = 0x1000008F9LL;
      v95 = 255;
      v100 = 0x1000000;
      memset_0(&v96, 0, 0x78u);
      CVssFunctionTracer::Trace(&v59, &v93, L"Fail to find details of the COM client process.");
      memset_0(v109, 0, sizeof(v109));
      memset_0(v101, 0, 0xA0u);
      *((_DWORD *)this + 634) = 0;
    }
    v7 = *((_DWORD *)this + 32);
    v8 = 0;
    if ( v7 )
    {
      v9 = (char *)(this + 11);
      do
      {
        v10 = this[14];
        LODWORD(v56) = v10[2 * (int)v8];
        v11 = WORD2(v10[2 * (int)v8]);
        WORD2(v56) = WORD2(v10[2 * (int)v8]);
        v12 = HIWORD(v10[2 * (int)v8]);
        WORD3(v56) = HIWORD(v10[2 * (int)v8]);
        v13 = LOBYTE(v10[2 * (int)v8 + 1]);
        BYTE8(v56) = v10[2 * (int)v8 + 1];
        v14 = BYTE1(v10[2 * (int)v8 + 1]);
        BYTE9(v56) = BYTE1(v10[2 * (int)v8 + 1]);
        v53 = BYTE2(v10[2 * (int)v8 + 1]);
        BYTE10(v56) = v53;
        v52 = BYTE3(v10[2 * (int)v8 + 1]);
        BYTE11(v56) = v52;
        v51 = BYTE4(v10[2 * (int)v8 + 1]);
        BYTE12(v56) = v51;
        v50 = BYTE5(v10[2 * (int)v8 + 1]);
        BYTE13(v56) = v50;
        v49 = BYTE6(v10[2 * (int)v8 + 1]);
        BYTE14(v56) = v49;
        v48 = HIBYTE(v10[2 * (int)v8 + 1]);
        HIBYTE(v56) = v48;
        v55 = *(_OWORD *)this[15][v8];
        CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::Lookup(v9, &v54, &v55);
        LODWORD(v93) = 0;
        memset_0((char *)&v93 + 4, 0, 0x7Cu);
        v55 = v56;
        if ( (*(int (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v54 + 40LL))(v54, &v55, &v93) >= 0 )
        {
          v82[0] = &CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable';
          v82[1] = &v93;
          v15 = *((_DWORD *)this + 634);
          if ( v15 )
          {
            v58 = 0;
            v57 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
            GetProcessName(v15);
            v74 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
            v75 = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
            v76 = L"CORSNPSC";
            v77 = 2325;
            v78 = 1;
            v79 = 255;
            v81 = 0x1000000;
            memset_0(v80, 0, sizeof(v80));
            v16 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v74, (CVssDebugInfo *)v92, v109);
            v17 = CVssDebugInfo::operator<<(v16, (CVssDebugInfo *)v91, v101);
            v18 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v17, (CVssDebugInfo *)v90);
            v19 = CVssDebugInfo::operator<<(v18, (CVssDebugInfo *)v89, v58);
            v55 = v94;
            v20 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v19, (CVssDebugInfo *)v88);
            v72 = v93;
            v21 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v20, (CVssDebugInfo *)v87);
            v55 = v99;
            v22 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v21, (CVssDebugInfo *)v86);
            v23 = CVssDebugInfo::operator<<(v22, (CVssDebugInfo *)v85, v98);
            v24 = CVssDebugInfo::operator<<(v23, (CVssDebugInfo *)v84, v97);
            v25 = (unsigned __int16 *)CVssDebugInfo::operator<<(v24, (CVssDebugInfo *)v83, v96);
            CVssFunctionTracer::LogSecurityAudit(v26, 0x201Eu, v25);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v84);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v85);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v86);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v87);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v88);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v89);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v90);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v91);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v92);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v74);
            CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v57);
          }
          else
          {
            memset_0(Buffer, 0, 0x208u);
            if ( !LoadStringW(hInstance, 0x12Cu, Buffer, 259) )
              StringCchCopyW(Buffer, 0x104u, L"Unknown");
            v74 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
            v75 = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
            v76 = L"CORSNPSC";
            v77 = 2338;
            v78 = 1;
            v79 = 255;
            v81 = 0x1000000;
            memset_0(v80, 0, sizeof(v80));
            v27 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v74, (CVssDebugInfo *)v83, Buffer);
            v28 = CVssDebugInfo::operator<<(v27, (CVssDebugInfo *)v84, Buffer);
            v29 = CVssDebugInfo::operator<<(v28, (CVssDebugInfo *)v85, Buffer);
            v30 = CVssDebugInfo::operator<<(v29, (CVssDebugInfo *)v86, Buffer);
            v55 = v94;
            v31 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v30, (CVssDebugInfo *)v87);
            v73 = v93;
            v32 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v31, (CVssDebugInfo *)v88);
            v55 = v99;
            v33 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v32, (CVssDebugInfo *)v89);
            v34 = CVssDebugInfo::operator<<(v33, (CVssDebugInfo *)v90, v98);
            v35 = CVssDebugInfo::operator<<(v34, (CVssDebugInfo *)v91, v97);
            v36 = (unsigned __int16 *)CVssDebugInfo::operator<<(v35, (CVssDebugInfo *)v92, v96);
            CVssFunctionTracer::LogSecurityAudit(v37, 0x201Eu, v36);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v91);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v90);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v89);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v88);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v87);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v86);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v85);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v84);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v83);
            CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v74);
          }
          CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::~CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&void VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&public: static _VSS_SNAPSHOT_PROP * & DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>(v82);
        }
        else
        {
          v74 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
          v75 = L"CVssSnapshotSetObject::LogSecurityAuditsForCreation";
          v76 = L"CORSNPSC";
          v77 = 2315;
          v78 = 1;
          v79 = 255;
          v81 = 0x1000000;
          memset_0(v80, 0, sizeof(v80));
          LODWORD(v47) = v48;
          LODWORD(v46) = v49;
          LODWORD(v45) = v50;
          LODWORD(v44) = v51;
          LODWORD(v43) = v52;
          LODWORD(v42) = v53;
          LODWORD(v41) = v14;
          LODWORD(v40) = v13;
          LODWORD(v39) = v12;
          LODWORD(v38) = v11;
          CVssFunctionTracer::Trace(
            &v59,
            &v74,
            L"The provider did not return the properties for ({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}). Fail to"
             " log security audit.",
            (unsigned int)v56,
            v38,
            v39,
            v40,
            v41,
            v42,
            v43,
            v44,
            v45,
            v46,
            v47);
        }
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v54);
        ++v8;
        v9 = (char *)(this + 11);
      }
      while ( v8 < v7 );
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v59);
}

```

## disassembly

```asm
0x140038a30  push    rbp
0x140038a32  push    rbx
0x140038a33  push    rsi
0x140038a34  push    rdi
0x140038a35  push    r12
0x140038a37  push    r13
0x140038a39  push    r14
0x140038a3b  push    r15
0x140038a3d  lea     rbp, [rsp-0BB8h]
0x140038a45  sub     rsp, 0CB8h
0x140038a4c  mov     rax, cs:__security_cookie
0x140038a53  xor     rax, rsp
0x140038a56  mov     [rbp+0BF0h+var_50], rax
0x140038a5d  mov     r15, rcx
0x140038a60  lea     r13, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140038a67  mov     qword ptr [rbp+0BF0h+var_3B0], r13
0x140038a6e  lea     rax, aCvsssnapshotse_41; "CVssSnapshotSetObject::LogSecurityAudit"...
0x140038a75  mov     [rbp+0BF0h+var_3A8], rax
0x140038a7c  lea     rax, aCorsnpsc; "CORSNPSC"
0x140038a83  mov     [rbp+0BF0h+var_3A0], rax
0x140038a8a  mov     [rbp+0BF0h+var_398], 8EAh
0x140038a94  mov     esi, 1
0x140038a99  mov     [rbp+0BF0h+var_394], esi
0x140038a9f  mov     r12d, 0FFh
0x140038aa5  mov     [rbp+0BF0h+var_390], r12d
0x140038aac  xor     edi, edi
0x140038aae  mov     [rbp+0BF0h+var_310], 1000000h
0x140038ab8  xor     edx, edx; Val
0x140038aba  lea     r8d, [rsi+77h]; Size
0x140038abe  lea     rcx, [rbp+0BF0h+var_388]; void *
0x140038ac5  call    memset_0
0x140038aca  mov     [rbp+0BF0h+var_C38], edi
0x140038acd  mov     rax, [rbp+0BF0h+var_3A8]
0x140038ad4  mov     [rbp+0BF0h+var_C18], rax
0x140038ad8  mov     rax, qword ptr [rbp+0BF0h+var_3B0]
0x140038adf  mov     [rbp+0BF0h+var_C30], rax
0x140038ae3  mov     rax, [rbp+0BF0h+var_3A0]
0x140038aea  mov     [rbp+0BF0h+var_C28], rax
0x140038aee  mov     eax, [rbp+0BF0h+var_398]
0x140038af4  mov     [rbp+0BF0h+var_C20], eax
0x140038af7  mov     eax, [rbp+0BF0h+var_394]
0x140038afd  mov     [rbp+0BF0h+var_C1C], eax
0x140038b00  call    cs:__imp_GetTickCount
0x140038b06  mov     [rbp+0BF0h+var_C0C], eax
0x140038b09  mov     [rbp+0BF0h+var_C3C], 0FFFFFFFFh
0x140038b10  mov     eax, [rbp+0BF0h+var_390]
0x140038b16  mov     [rbp+0BF0h+var_C08], eax
0x140038b19  mov     [rbp+0BF0h+var_C40], edi
0x140038b1c  mov     [rbp+0BF0h+var_BE0], rdi
0x140038b20  xorps   xmm0, xmm0
0x140038b23  movups  [rbp+0BF0h+var_C00], xmm0
0x140038b27  movups  [rbp+0BF0h+var_BF0], xmm0
0x140038b2b  mov     [rsp+0CF0h+var_C78], rdi
0x140038b30  lea     rcx, [rsp+0CF0h+var_C78]
0x140038b35  call    cs:__imp_VssGetTracingContextPerThread
0x140038b3b  test    eax, eax
0x140038b3d  js      short loc_140038B5B
0x140038b3f  lea     rcx, [rbp+0BF0h+var_C40]
0x140038b43  call    cs:__imp_VssSetTracingContextPerThread
0x140038b49  mov     rcx, [rbp+0BF0h+var_BE0]
0x140038b4d  test    eax, eax
0x140038b4f  cmovns  rcx, [rsp+0CF0h+var_C78]
0x140038b55  mov     [rbp+0BF0h+var_BE0], rcx
0x140038b59  jmp     short loc_140038B5F
0x140038b5b  mov     rcx, [rbp+0BF0h+var_BE0]
0x140038b5f  test    rcx, rcx
0x140038b62  jz      short loc_140038B6E
0x140038b64  mov     eax, [rcx+30h]
0x140038b67  add     eax, esi
0x140038b69  mov     [rbp+0BF0h+var_C10], eax
0x140038b6c  jmp     short loc_140038B71
0x140038b6e  mov     [rbp+0BF0h+var_C10], edi
0x140038b71  mov     r14d, 0A0h
0x140038b77  mov     ebx, r14d
0x140038b7a  cmp     [rbp+0BF0h+var_C08], r12d
0x140038b7e  cmovnz  ebx, [rbp+0BF0h+var_C08]
0x140038b82  lea     rcx, [rbp+0BF0h+var_C40]; this
0x140038b86  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140038b8b  test    eax, eax
0x140038b8d  jz      short loc_140038BCA
0x140038b8f  mov     [rsp+0CF0h+var_CB0], rdi
0x140038b94  mov     dword ptr [rsp+0CF0h+var_CB8], ebx
0x140038b98  lea     rax, aEnter; "ENTER"
0x140038b9f  mov     [rsp+0CF0h+var_CC0], rax
0x140038ba4  mov     rax, [rbp+0BF0h+var_C18]
0x140038ba8  mov     [rsp+0CF0h+var_CC8], rax
0x140038bad  mov     eax, [rbp+0BF0h+var_C1C]
0x140038bb0  mov     dword ptr [rsp+0CF0h+var_CD0], eax
0x140038bb4  mov     r9d, [rbp+0BF0h+var_C10]
0x140038bb8  mov     r8d, [rbp+0BF0h+var_C20]
0x140038bbc  mov     rdx, [rbp+0BF0h+var_C28]
0x140038bc0  mov     rcx, [rbp+0BF0h+var_C30]
0x140038bc4  call    cs:__imp_VssTraceMessage
0x140038bca  lea     rcx, [rbp+0BF0h+var_3B0]; this
0x140038bd1  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140038bd6  nop
0x140038bd7  test    byte ptr [r15+40h], 20h
0x140038bdc  jz      short loc_140038C50
0x140038bde  mov     qword ptr [rbp+0BF0h+var_3B0], r13
0x140038be5  lea     rax, aCvsssnapshotse_41; "CVssSnapshotSetObject::LogSecurityAudit"...
0x140038bec  mov     [rbp+0BF0h+var_3A8], rax
0x140038bf3  lea     rax, aCorsnpsc; "CORSNPSC"
0x140038bfa  mov     [rbp+0BF0h+var_3A0], rax
0x140038c01  mov     [rbp+0BF0h+var_398], 8EEh
0x140038c0b  mov     [rbp+0BF0h+var_394], esi
0x140038c11  mov     [rbp+0BF0h+var_390], r12d
0x140038c18  mov     [rbp+0BF0h+var_310], 1000000h
0x140038c22  xor     edx, edx; Val
0x140038c24  lea     r8d, [rdx+78h]; Size
0x140038c28  lea     rcx, [rbp+0BF0h+var_388]; void *
0x140038c2f  call    memset_0
0x140038c34  lea     r8, aTransportableS; "Transportable snapshot. Don't log on cr"...
0x140038c3b  lea     rdx, [rbp+0BF0h+var_3B0]
0x140038c42  lea     rcx, [rbp+0BF0h+var_C40]
0x140038c46  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140038c4b  jmp     loc_14003936F
0x140038c50  mov     r8, r14; Size
0x140038c53  xor     edx, edx; Val
0x140038c55  lea     rcx, [rbp+0BF0h+var_300]; void *
0x140038c5c  call    memset_0
0x140038c61  mov     r8, r14; Size
0x140038c64  xor     edx, edx; Val
0x140038c66  lea     rcx, [rbp+0BF0h+var_3B0]; void *
0x140038c6d  call    memset_0
0x140038c72  lea     r9, [rbp+0BF0h+var_3B0]; unsigned __int16 *
0x140038c79  lea     r8, [rbp+0BF0h+var_300]; unsigned __int16 *
0x140038c80  mov     rcx, r15; this
0x140038c83  call    ?GetComClientDetails@CVssSnapshotSetObject@@AEAAJKPEAG0@Z; CVssSnapshotSetObject::GetComClientDetails(ulong,ushort *,ushort *)
0x140038c88  test    eax, eax
0x140038c8a  js      short loc_140038C94
0x140038c8c  cmp     eax, esi
0x140038c8e  jnz     loc_140038D2A
0x140038c94  mov     [rbp+0BF0h+var_460], r13
0x140038c9b  lea     rax, aCvsssnapshotse_41; "CVssSnapshotSetObject::LogSecurityAudit"...
0x140038ca2  mov     [rbp+0BF0h+var_458], rax
0x140038ca9  lea     rax, aCorsnpsc; "CORSNPSC"
0x140038cb0  mov     qword ptr [rbp+0BF0h+var_450], rax
0x140038cb7  mov     dword ptr [rbp+0BF0h+var_450+8], 8F9h
0x140038cc1  mov     dword ptr [rbp+0BF0h+var_450+0Ch], esi
0x140038cc7  mov     [rbp+0BF0h+var_440], r12d
0x140038cce  mov     [rbp+0BF0h+var_3C0], 1000000h
0x140038cd8  xor     edx, edx; Val
0x140038cda  lea     r8d, [rdx+78h]; Size
0x140038cde  lea     rcx, [rbp+0BF0h+var_438]; void *
0x140038ce5  call    memset_0
0x140038cea  lea     r8, aFailToFindDeta_0; "Fail to find details of the COM client "...
0x140038cf1  lea     rdx, [rbp+0BF0h+var_460]
0x140038cf8  lea     rcx, [rbp+0BF0h+var_C40]
0x140038cfc  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140038d01  mov     r8, r14; Size
0x140038d04  xor     edx, edx; Val
0x140038d06  lea     rcx, [rbp+0BF0h+var_300]; void *
0x140038d0d  call    memset_0
0x140038d12  mov     r8, r14; Size
0x140038d15  xor     edx, edx; Val
0x140038d17  lea     rcx, [rbp+0BF0h+var_3B0]; void *
0x140038d1e  call    memset_0
0x140038d23  mov     [r15+9E8h], edi
0x140038d2a  mov     r13d, [r15+80h]
0x140038d31  mov     r12d, edi
0x140038d34  test    r13d, r13d
0x140038d37  jz      loc_14003936F
0x140038d3d  lea     r9, [r15+58h]
0x140038d41  movsxd  rdx, r12d
0x140038d44  mov     rcx, rdx
0x140038d47  add     rcx, rcx
0x140038d4a  mov     rax, [r15+70h]
0x140038d4e  mov     r8d, [rax+rcx*8]
0x140038d52  mov     dword ptr [rbp+0BF0h+var_C60], r8d
0x140038d56  movzx   r14d, word ptr [rax+rcx*8+4]
0x140038d5c  mov     word ptr [rbp+0BF0h+var_C60+4], r14w
0x140038d61  movzx   esi, word ptr [rax+rcx*8+6]
0x140038d66  mov     word ptr [rbp+0BF0h+var_C60+6], si
0x140038d6a  movzx   edi, byte ptr [rax+rcx*8+8]
0x140038d6f  mov     byte ptr [rbp+0BF0h+var_C60+8], dil
0x140038d73  movzx   ebx, byte ptr [rax+rcx*8+9]
0x140038d78  mov     byte ptr [rbp+0BF0h+var_C60+9], bl
0x140038d7b  mov     r8b, [rax+rcx*8+0Ah]
0x140038d80  mov     [rsp+0CF0h+var_C7B], r8b
0x140038d85  mov     byte ptr [rbp+0BF0h+var_C60+0Ah], r8b
0x140038d89  mov     r8b, [rax+rcx*8+0Bh]
0x140038d8e  mov     [rsp+0CF0h+var_C7C], r8b
0x140038d93  mov     byte ptr [rbp+0BF0h+var_C60+0Bh], r8b
0x140038d97  mov     r8b, [rax+rcx*8+0Ch]
0x140038d9c  mov     [rsp+0CF0h+var_C7D], r8b
0x140038da1  mov     byte ptr [rbp+0BF0h+var_C60+0Ch], r8b
0x140038da5  mov     r8b, [rax+rcx*8+0Dh]
0x140038daa  mov     [rsp+0CF0h+var_C7E], r8b
0x140038daf  mov     byte ptr [rbp+0BF0h+var_C60+0Dh], r8b
0x140038db3  mov     r8b, [rax+rcx*8+0Eh]
0x140038db8  mov     [rsp+0CF0h+var_C7F], r8b
0x140038dbd  mov     byte ptr [rbp+0BF0h+var_C60+0Eh], r8b
0x140038dc1  mov     al, [rax+rcx*8+0Fh]
0x140038dc5  mov     [rsp+0CF0h+var_C80], al
0x140038dc9  mov     byte ptr [rbp+0BF0h+var_C60+0Fh], al
0x140038dcc  mov     rax, [r15+78h]
0x140038dd0  mov     rcx, [rax+rdx*8]
0x140038dd4  movups  xmm0, xmmword ptr [rcx]
0x140038dd7  movdqu  [rbp+0BF0h+var_C70], xmm0
0x140038ddc  lea     r8, [rbp+0BF0h+var_C70]
0x140038de0  lea     rdx, [rsp+0CF0h+var_C78]
0x140038de5  mov     rcx, r9
0x140038de8  call    ?Lookup@?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@QEBA?AV?$CComPtr@UIVssSnapshotProvider@@@ATL@@U_GUID@@@Z; CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::Lookup(_GUID)
0x140038ded  nop
0x140038dee  mov     dword ptr [rbp+0BF0h+var_460], 0
0x140038df8  xor     edx, edx; Val
0x140038dfa  lea     r8d, [rdx+7Ch]; Size
0x140038dfe  lea     rcx, [rbp+0BF0h+var_460+4]; void *
0x140038e05  call    memset_0
0x140038e0a  mov     rcx, [rsp+0CF0h+var_C78]
0x140038e0f  movaps  xmm0, [rbp+0BF0h+var_C60]
0x140038e13  movdqa  [rbp+0BF0h+var_C70], xmm0
0x140038e18  mov     rax, [rcx]
0x140038e1b  lea     r8, [rbp+0BF0h+var_460]
0x140038e22  lea     rdx, [rbp+0BF0h+var_C70]
0x140038e26  mov     rax, [rax+28h]
0x140038e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038e2f  test    eax, eax
0x140038e31  jns     loc_140038EF0
0x140038e37  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140038e3e  mov     [rbp+0BF0h+var_BB0], rax
0x140038e42  lea     rax, aCvsssnapshotse_41; "CVssSnapshotSetObject::LogSecurityAudit"...
0x140038e49  mov     [rbp+0BF0h+var_BA8], rax
0x140038e4d  lea     rax, aCorsnpsc; "CORSNPSC"
0x140038e54  mov     [rbp+0BF0h+var_BA0], rax
0x140038e58  mov     [rbp+0BF0h+var_B98], 90Bh
0x140038e5f  mov     [rbp+0BF0h+var_B94], 1
0x140038e66  mov     [rbp+0BF0h+var_B90], 0FFh
0x140038e6d  mov     [rbp+0BF0h+var_B10], 1000000h
0x140038e77  xor     edx, edx; Val
0x140038e79  lea     r8d, [rdx+78h]; Size
0x140038e7d  lea     rcx, [rbp+0BF0h+var_B88]; void *
0x140038e81  call    memset_0
0x140038e86  movzx   eax, [rsp+0CF0h+var_C80]
0x140038e8b  movzx   ecx, [rsp+0CF0h+var_C7F]
0x140038e90  movzx   edx, [rsp+0CF0h+var_C7E]
0x140038e95  movzx   r8d, [rsp+0CF0h+var_C7D]
0x140038e9b  movzx   r10d, [rsp+0CF0h+var_C7C]
0x140038ea1  movzx   r11d, [rsp+0CF0h+var_C7B]
0x140038ea7  mov     dword ptr [rsp+0CF0h+var_C88], eax
0x140038eab  mov     dword ptr [rsp+0CF0h+var_C90], ecx
0x140038eaf  mov     dword ptr [rsp+0CF0h+var_C98], edx
0x140038eb3  mov     dword ptr [rsp+0CF0h+var_CA0], r8d
0x140038eb8  mov     dword ptr [rsp+0CF0h+var_CA8], r10d
0x140038ebd  mov     dword ptr [rsp+0CF0h+var_CB0], r11d
0x140038ec2  mov     dword ptr [rsp+0CF0h+var_CB8], ebx
0x140038ec6  mov     dword ptr [rsp+0CF0h+var_CC0], edi
0x140038eca  mov     dword ptr [rsp+0CF0h+var_CC8], esi
0x140038ece  mov     dword ptr [rsp+0CF0h+var_CD0], r14d
0x140038ed3  mov     r9d, dword ptr [rbp+0BF0h+var_C60]
0x140038ed7  lea     r8, aTheProviderDid; "The provider did not return the propert"...
0x140038ede  lea     rdx, [rbp+0BF0h+var_BB0]
0x140038ee2  lea     rcx, [rbp+0BF0h+var_C40]
0x140038ee6  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140038eeb  jmp     loc_140039355
0x140038ef0  lea     rax, ??_7?$CVssAuto@PEAU_VSS_SNAPSHOT_PROP@@V?$CVssAutoGenericValue_Storage@PEAU_VSS_SNAPSHOT_PROP@@$0A@P6AXPEAU1@@Z$1?VssFreeSnapshotProperties@@YAX0@ZP6AAEAPEAU1@AEAPEAU1@@Z$1?Identity@?$DTyper@PEAU_VSS_SNAPSHOT_PROP@@@@SAAEAPEAU1@1@Z@@@@6B@; const CVssAuto<_VSS_SNAPSHOT_PROP *,CVssAutoGenericValue_Storage<_VSS_SNAPSHOT_PROP *,0,void (*)(_VSS_SNAPSHOT_PROP *),&VssFreeSnapshotProperties(_VSS_SNAPSHOT_PROP *),_VSS_SNAPSHOT_PROP * & (*)(_VSS_SNAPSHOT_PROP * &),&DTyper<_VSS_SNAPSHOT_PROP *>::Identity(_VSS_SNAPSHOT_PROP * &)>>::`vftable'
0x140038ef7  mov     [rbp+0BF0h+var_B08], rax
0x140038efe  lea     rax, [rbp+0BF0h+var_460]
0x140038f05  mov     [rbp+0BF0h+var_B00], rax
0x140038f0c  mov     ecx, [r15+9E8h]; dwProcessId
0x140038f13  xor     ebx, ebx
0x140038f15  test    ecx, ecx
0x140038f17  jz      loc_14003911D
0x140038f1d  mov     [rbp+0BF0h+var_C48], rbx
0x140038f21  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140038f28  mov     [rbp+0BF0h+var_C50], rax
0x140038f2c  lea     rdx, [rbp+0BF0h+var_C50]
0x140038f30  call    ?GetProcessName@@YAXKAEAV?$CVssAutoString@V?$CVssAutoLocalPtr@PEAG@@@@@Z; GetProcessName(ulong,CVssAutoString<CVssAutoLocalPtr<ushort *>> &)
0x140038f35  lea     rax, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x140038f3c  mov     [rbp+0BF0h+var_BB0], rax
0x140038f40  lea     rax, aCvsssnapshotse_41; "CVssSnapshotSetObject::LogSecurityAudit"...
0x140038f47  mov     [rbp+0BF0h+var_BA8], rax
0x140038f4b  lea     rax, aCorsnpsc; "CORSNPSC"
0x140038f52  mov     [rbp+0BF0h+var_BA0], rax
0x140038f56  mov     [rbp+0BF0h+var_B98], 915h
0x140038f5d  mov     [rbp+0BF0h+var_B94], 1
0x140038f64  mov     [rbp+0BF0h+var_B90], 0FFh
0x140038f6b  mov     [rbp+0BF0h+var_B10], 1000000h
0x140038f75  xor     edx, edx; Val
0x140038f77  lea     r8d, [rbx+78h]; Size
0x140038f7b  lea     rcx, [rbp+0BF0h+var_B88]; void *
0x140038f7f  call    memset_0
0x140038f84  lea     r8, [rbp+0BF0h+var_300]
0x140038f8b  lea     rdx, [rbp+0BF0h+var_510]; this
0x140038f92  lea     rcx, [rbp+0BF0h+var_BB0]; struct CVssDebugInfo *
0x140038f96  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x140038f9b  lea     r8, [rbp+0BF0h+var_3B0]
0x140038fa2  lea     rdx, [rbp+0BF0h+var_5B8]; this
0x140038fa9  mov     rcx, rax; struct CVssDebugInfo *
0x140038fac  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x140038fb1  mov     r8d, [r15+9E8h]
0x140038fb8  lea     rdx, [rbp+0BF0h+var_660]; this
0x140038fbf  mov     rcx, rax; struct CVssDebugInfo *
0x140038fc2  call    ??6CVssDebugInfo@@QEAA?AU0@_J@Z; CVssDebugInfo::operator<<(__int64)
0x140038fc7  mov     r8, [rbp+0BF0h+var_C48]
0x140038fcb  lea     rdx, [rbp+0BF0h+var_708]; this
0x140038fd2  mov     rcx, rax; struct CVssDebugInfo *
0x140038fd5  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x140038fda  movaps  xmm0, [rbp+0BF0h+var_450]
0x140038fe1  movdqu  [rbp+0BF0h+var_C70], xmm0
  ... truncated ...
```
