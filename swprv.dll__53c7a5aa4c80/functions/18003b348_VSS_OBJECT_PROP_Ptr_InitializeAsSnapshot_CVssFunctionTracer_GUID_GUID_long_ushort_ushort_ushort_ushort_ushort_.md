# VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot(CVssFunctionTracer &,_GUID,_GUID,long,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,_GUID,long,__int64,_VSS_SNAPSHOT_STATE)

- ea: `0x18003b348`
- end: `0x18003b5e0`
- name: `?InitializeAsSnapshot@VSS_OBJECT_PROP_Ptr@@QEAAXAEAVCVssFunctionTracer@@U_GUID@@1JPEAG222221J_JW4_VSS_SNAPSHOT_STATE@@@Z`
- size: `664`
- prototype: `void __fastcall(VSS_OBJECT_PROP_Ptr *this, struct CVssFunctionTracer *, struct _GUID *, struct _GUID *, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *pv, unsigned __int16 *, struct _GUID *, LONG, __int64, enum _VSS_SNAPSHOT_STATE)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e900`
- `0x18001c5dc`

## callees

- `0x18000212c`
- `0x180017284`
- `0x18003649c`
- `0x18003abc4`
- `0x18003ade0`
- `0x18003b348`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b3ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b3ba`

## pseudocode

```c
void __fastcall VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot(
        VSS_OBJECT_PROP_Ptr *this,
        struct CVssFunctionTracer *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned __int16 *pv,
        unsigned __int16 *a11,
        struct _GUID *a12,
        LONG a13,
        __int64 a14,
        enum _VSS_SNAPSHOT_STATE a15)
{
  struct CVssFunctionTracer *v17; // rdi
  struct _VSS_OBJECT_PROP *v19; // rax
  struct _VSS_OBJECT_PROP *v20; // rbx
  unsigned int v21; // [rsp+40h] [rbp-158h] BYREF
  const unsigned __int16 *v22; // [rsp+48h] [rbp-150h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-148h]
  const unsigned __int16 *v24; // [rsp+58h] [rbp-140h]
  int v25; // [rsp+60h] [rbp-138h]
  int v26; // [rsp+64h] [rbp-134h]
  int v27; // [rsp+68h] [rbp-130h]
  _BYTE v28[120]; // [rsp+70h] [rbp-128h] BYREF
  int v29; // [rsp+E8h] [rbp-B0h]
  _com_error *v30; // [rsp+F0h] [rbp-A8h] BYREF
  const std::exception *v31; // [rsp+F8h] [rbp-A0h] BYREF
  _OWORD v32[5]; // [rsp+100h] [rbp-98h] BYREF
  int v33; // [rsp+150h] [rbp-48h]
  struct _VSS_OBJECT_PROP *pva; // [rsp+1E8h] [rbp+50h]

  v17 = a2;
  v32[0] = *(_OWORD *)L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot";
  v32[1] = *(_OWORD *)L"CT_PROP_Ptr::InitializeAsSnapshot";
  v32[2] = *(_OWORD *)L"Ptr::InitializeAsSnapshot";
  v32[3] = *(_OWORD *)L"tializeAsSnapshot";
  v32[4] = *(_OWORD *)L"sSnapshot";
  v33 = *(_DWORD *)L"t";
  v19 = (struct _VSS_OBJECT_PROP *)CoTaskMemAlloc(0x88u);
  try
  {
    v20 = v19;
    pva = v19;
    if ( !v19 )
    {
      v22 = L"base\\stor\\vss\\modules\\prop\\pointer.cxx";
      v23 = L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot";
      v24 = L"PRPPNTRC";
      v25 = 96;
      v26 = 11;
      v27 = 255;
      v29 = 0x1000000;
      memset_0(v28, 0, sizeof(v28));
      CVssFunctionTracer::Throw(v17, &v22, 2147942414LL, L"%s: Error on allocating the Properties structure", v32);
    }
    VSS_OBJECT_PROP_Copy::init(v19);
    v20->Type = VSS_OBJECT_SNAPSHOT;
    v20->Obj.Snap.m_SnapshotId = *a3;
    v20->Obj.Snap.m_SnapshotSetId = *a4;
    v20->Obj.Snap.m_lSnapshotsCount = 0;
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszSnapshotDeviceObject, a6);
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszOriginalVolumeName, a7);
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszOriginatingMachine, a8);
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszServiceMachine, a9);
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszExposedName, 0);
    VssSafeDuplicateStr(v17, &v20->Obj.Snap.m_pwszExposedPath, 0);
    v20->Obj.Snap.m_ProviderId = *a12;
    v20->Obj.Snap.m_lSnapshotAttributes = a13;
    v20->Obj.Snap.m_tsCreationTimestamp = 0;
    v20->Obj.Snap.m_eStatus = a15;
    *(_QWORD *)this = v20;
  }
  catch ( long v21 )
  {
    CVssFunctionTracer::HandleHresultException(
      a2,
      v21,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot",
      0x7Eu,
      *((_DWORD *)a2 + 9));
    v17 = a2;
  }
  catch ( _com_error *v30 )
  {
    CVssFunctionTracer::HandleComException(
      a2,
      v30,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot",
      0x7Eu,
      *((_DWORD *)a2 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      a2,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot",
      0x7Eu,
      *((_DWORD *)a2 + 9));
    v17 = a2;
  }
  catch ( const std::exception *v31 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      a2,
      v31,
      L"base\\stor\\vss\\modules\\prop\\pointer.cxx",
      L"PRPPNTRC",
      L"VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot",
      0x7Eu,
      *((_DWORD *)a2 + 9));
  }
  v20 = v19;
}

```

## disassembly

```asm
0x18003b348  mov     rax, rsp
0x18003b34b  mov     [rax+10h], rdx
0x18003b34f  push    rbx
0x18003b350  push    rsi
0x18003b351  push    rdi
0x18003b352  push    r12
0x18003b354  push    r14
0x18003b356  push    r15
0x18003b358  sub     rsp, 168h
0x18003b35f  mov     r14, r9
0x18003b362  mov     r15, r8
0x18003b365  mov     rdi, rdx
0x18003b368  mov     r12, rcx
0x18003b36b  movaps  xmm0, xmmword ptr cs:aVssObjectPropP; "VSS_OBJECT_PROP_Ptr::InitializeAsSnapsh"...
0x18003b372  movaps  xmmword ptr [rax-98h], xmm0
0x18003b379  movaps  xmm1, xmmword ptr cs:aVssObjectPropP+10h; "CT_PROP_Ptr::InitializeAsSnapshot"
0x18003b380  movaps  xmmword ptr [rax-88h], xmm1
0x18003b387  movaps  xmm0, xmmword ptr cs:aVssObjectPropP+20h; "Ptr::InitializeAsSnapshot"
0x18003b38e  movaps  xmmword ptr [rax-78h], xmm0
0x18003b392  movaps  xmm1, xmmword ptr cs:aVssObjectPropP+30h; "tializeAsSnapshot"
0x18003b399  movaps  xmmword ptr [rax-68h], xmm1
0x18003b39d  movaps  xmm0, xmmword ptr cs:aVssObjectPropP+40h; "sSnapshot"
0x18003b3a4  movaps  xmmword ptr [rax-58h], xmm0
0x18003b3a8  mov     eax, dword ptr cs:aVssObjectPropP+50h; "t"
0x18003b3ae  mov     [rsp+198h+var_48], eax
0x18003b3b5  mov     ecx, 88h; cb
0x18003b3ba  call    cs:__imp_CoTaskMemAlloc
0x18003b3c0  mov     rbx, rax
0x18003b3c3  mov     [rsp+198h+pv], rax
0x18003b3cb  xor     esi, esi
0x18003b3cd  test    rax, rax
0x18003b3d0  jnz     short loc_18003B450
0x18003b3d2  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b3d9  mov     [rsp+198h+var_150], rax
0x18003b3de  lea     rax, aVssObjectPropP; "VSS_OBJECT_PROP_Ptr::InitializeAsSnapsh"...
0x18003b3e5  mov     [rsp+198h+var_148], rax
0x18003b3ea  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b3f1  mov     [rsp+198h+var_140], rax
0x18003b3f6  mov     [rsp+198h+var_138], 60h ; '`'
0x18003b3fe  mov     [rsp+198h+var_134], 0Bh
0x18003b406  mov     [rsp+198h+var_130], 0FFh
0x18003b40e  mov     [rsp+198h+var_B0], 1000000h
0x18003b419  xor     edx, edx; Val
0x18003b41b  lea     r8d, [rbx+78h]; Size
0x18003b41f  lea     rcx, [rsp+198h+var_128]; void *
0x18003b424  call    memset_0
0x18003b429  lea     rax, [rsp+198h+var_98]
0x18003b431  mov     [rsp+198h+var_178], rax
0x18003b436  lea     r9, aSErrorOnAlloca; "%s: Error on allocating the Properties "...
0x18003b43d  mov     r8d, 8007000Eh
0x18003b443  lea     rdx, [rsp+198h+var_150]
0x18003b448  mov     rcx, rdi
0x18003b44b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b450  mov     rcx, rbx; struct _VSS_OBJECT_PROP *
0x18003b453  call    ?init@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z; VSS_OBJECT_PROP_Copy::init(_VSS_OBJECT_PROP *)
0x18003b458  mov     dword ptr [rbx], 3
0x18003b45e  movaps  xmm0, xmmword ptr [r15]
0x18003b462  movdqu  xmmword ptr [rbx+8], xmm0
0x18003b467  movaps  xmm1, xmmword ptr [r14]
0x18003b46b  movdqu  xmmword ptr [rbx+18h], xmm1
0x18003b470  mov     [rbx+28h], esi
0x18003b473  lea     rdx, [rbx+30h]; unsigned __int16 **
0x18003b477  mov     r8, [rsp+198h+arg_28]; unsigned __int16 *
0x18003b47f  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b482  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b487  lea     rdx, [rbx+38h]; unsigned __int16 **
0x18003b48b  mov     r8, [rsp+198h+arg_30]; unsigned __int16 *
0x18003b493  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b496  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b49b  lea     rdx, [rbx+40h]; unsigned __int16 **
0x18003b49f  mov     r8, [rsp+198h+arg_38]; unsigned __int16 *
0x18003b4a7  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b4aa  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b4af  lea     rdx, [rbx+48h]; unsigned __int16 **
0x18003b4b3  mov     r8, [rsp+198h+arg_40]; unsigned __int16 *
0x18003b4bb  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b4be  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b4c3  lea     rdx, [rbx+50h]; unsigned __int16 **
0x18003b4c7  xor     r8d, r8d; unsigned __int16 *
0x18003b4ca  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b4cd  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b4d2  lea     rdx, [rbx+58h]; unsigned __int16 **
0x18003b4d6  xor     r8d, r8d; unsigned __int16 *
0x18003b4d9  mov     rcx, rdi; struct CVssFunctionTracer *
0x18003b4dc  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x18003b4e1  mov     rax, [rsp+198h+arg_58]
0x18003b4e9  movaps  xmm0, xmmword ptr [rax]
0x18003b4ec  movdqu  xmmword ptr [rbx+60h], xmm0
0x18003b4f1  mov     eax, [rsp+198h+arg_60]
0x18003b4f8  mov     [rbx+70h], eax
0x18003b4fb  mov     [rbx+78h], rsi
0x18003b4ff  mov     eax, [rsp+198h+arg_70]
0x18003b506  mov     [rbx+80h], eax
0x18003b50c  mov     [r12], rbx
0x18003b510  jmp     short loc_18003B522
0x18003b512  jmp     short loc_18003B518
0x18003b514  jmp     short loc_18003B518
0x18003b516  jmp     short $+2
0x18003b518  mov     rdi, [rsp+198h+arg_8]
0x18003b520  xor     esi, esi
0x18003b522  cmp     [rdi+8], esi
0x18003b525  jge     loc_18003B5CF
0x18003b52b  mov     rbx, [rsp+198h+pv]
0x18003b533  test    rbx, rbx
0x18003b536  jz      short loc_18003B549
0x18003b538  mov     rcx, rbx; struct _VSS_OBJECT_PROP *
0x18003b53b  call    ?destroy@VSS_OBJECT_PROP_Copy@@SAXPEAU_VSS_OBJECT_PROP@@@Z; VSS_OBJECT_PROP_Copy::destroy(_VSS_OBJECT_PROP *)
0x18003b540  mov     rcx, rbx; pv
0x18003b543  call    cs:__imp_CoTaskMemFree
0x18003b549  lea     rax, aBaseStorVssMod_6; "base\\stor\\vss\\modules\\prop\\pointer"...
0x18003b550  mov     [rsp+198h+var_150], rax
0x18003b555  lea     rax, aVssObjectPropP; "VSS_OBJECT_PROP_Ptr::InitializeAsSnapsh"...
0x18003b55c  mov     [rsp+198h+var_148], rax
0x18003b561  lea     rax, aPrppntrc; "PRPPNTRC"
0x18003b568  mov     [rsp+198h+var_140], rax
0x18003b56d  mov     [rsp+198h+var_138], 89h
0x18003b575  mov     [rsp+198h+var_134], 0Bh
0x18003b57d  mov     [rsp+198h+var_130], 0FFh
0x18003b585  mov     [rsp+198h+var_B0], 1000000h
0x18003b590  xor     edx, edx; Val
0x18003b592  lea     r8d, [rdx+78h]; Size
0x18003b596  lea     rcx, [rsp+198h+var_128]; void *
0x18003b59b  call    memset_0
0x18003b5a0  mov     eax, [rdi+8]
0x18003b5a3  mov     [rsp+198h+var_170], eax
0x18003b5a7  lea     rax, [rsp+198h+var_98]
0x18003b5af  mov     [rsp+198h+var_178], rax
0x18003b5b4  lea     r9, aSErrorCatched0; "%s: Error catched 0x%08lx"
0x18003b5bb  mov     r8d, 8007000Eh
0x18003b5c1  lea     rdx, [rsp+198h+var_150]
0x18003b5c6  mov     rcx, rdi
0x18003b5c9  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18003b5cf  add     rsp, 168h
0x18003b5d6  pop     r15
0x18003b5d8  pop     r14
0x18003b5da  pop     r12
0x18003b5dc  pop     rdi
0x18003b5dd  pop     rsi
0x18003b5de  pop     rbx
0x18003b5df  retn
```
