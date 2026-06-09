# SBE2Sink::CSBE2Sink::InternalInitialize(ushort const *)

- ea: `0x18000f058`
- end: `0x18000f32d`
- name: `?InternalInitialize@CSBE2Sink@SBE2Sink@@AEAAJPEBG@Z`
- size: `725`
- prototype: `__int64 __fastcall(SBE2Sink::CSBE2Sink *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e460`
- `0x18000f5d0`
- `0x1800101d0`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x180002b7c`
- `0x180002ed4`
- `0x180006af8`
- `0x180006c44`
- `0x1800089b8`
- `0x18000cb80`
- `0x18000cf8c`
- `0x18000f058`
- `0x18000f334`
- `0x180011498`
- `0x18004774c`
- `0x180048150`
- `0x180058bb8`
- `0x180058bd8`
- `0x18005bedc`
- `0x1800a8c78`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000f0f8`
- `KERNEL32!LeaveCriticalSection` at `0x18000f0f8`
- `KERNEL32!EnterCriticalSection` at `0x18000f0c8`
- `KERNEL32!EnterCriticalSection` at `0x18000f0c8`
- `ole32!StringFromGUID2` at `0x18000f130`
- `ole32!StringFromGUID2` at `0x18000f130`
- `ole32!CoCreateGuid` at `0x18000f10e`
- `ole32!CoCreateGuid` at `0x18000f10e`

## pseudocode

```c
__int64 __fastcall SBE2Sink::CSBE2Sink::InternalInitialize(SBE2Sink::CSBE2Sink *this, unsigned __int16 *a2)
{
  struct IPauseBufferWriter **v2; // r13
  bool v3; // zf
  void (__fastcall ***v6)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION *); // r12
  struct _RTL_CRITICAL_SECTION **v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  HRESULT Instance; // ebx
  SBFThunk::Cv2NodeState *v10; // r12
  __int64 i; // rdi
  __int64 v12; // rax
  __int64 v13; // r15
  unsigned int v14; // r8d
  __int64 v15; // rdi
  struct SBFThunk::Cv2NodeState *v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _AMMediaType v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+A0h] [rbp-60h] BYREF
  GUID pguid; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Buffer[104]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = (struct IPauseBufferWriter **)((char *)this + 232);
  v17[0] = 0;
  v3 = *((_QWORD *)this + 29) == 0;
  v19 = 0;
  if ( !v3 )
  {
    Instance = 0;
    goto LABEL_27;
  }
  v6 = (void (__fastcall ***)(_QWORD, GUID *, struct _RTL_CRITICAL_SECTION *))*((_QWORD *)this + 12);
  v7 = (struct _RTL_CRITICAL_SECTION **)((char *)this + 784);
  if ( v6 )
  {
    v8 = *v7;
    EnterCriticalSection(*v7 + 1);
    SBE2Sink::CSBE2SinkCtx::Uninitialize((SBE2Sink::CSBE2SinkCtx *)v8);
    *(_QWORD *)&v8[2].LockCount = v6;
    (**v6)(v6, &GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770, v8 + 2);
    LeaveCriticalSection(v8 + 1);
  }
  if ( !a2 )
  {
    pguid = 0;
    Instance = CoCreateGuid(&pguid);
    if ( Instance < 0 )
    {
LABEL_9:
      SBE2Sink::CSBE2Sink::InternalUninitialize(this);
      goto LABEL_27;
    }
    a2 = (unsigned __int16 *)((char *)this + 240);
    if ( !StringFromGUID2(&pguid, (LPOLESTR)this + 120, 260) )
    {
      Instance = -2147024809;
      goto LABEL_9;
    }
    Instance = StringCchCatW((unsigned __int16 *)this + 120, 0x104u, L".tmp.stub");
    if ( Instance < 0 )
      goto LABEL_9;
  }
  Instance = SBE2PauseBuffer::CSBE2PauseBufferWriter::CreateInstance(
               *(struct IUnknown **)&(*v7)->LockCount,
               *((struct IFilterGraph **)this + 12),
               *((struct CDVRPolicy **)this + 22),
               a2,
               v2);
  if ( Instance < 0 )
    goto LABEL_9;
  Instance = SBFThunk::Cv2NodeState::CreateInstance(v17);
  if ( Instance < 0 )
    goto LABEL_9;
  v10 = v17[0];
  Instance = (**((__int64 (__fastcall ***)(char *, GUID *, __int64 *))v17[0] + 3))(
               (char *)v17[0] + 24,
               &GUID_00000000_0000_0000_c000_000000000046,
               &v19);
  if ( Instance < 0 )
    goto LABEL_9;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v12 = *((_QWORD *)this + 21);
    if ( (unsigned int)i >= *(_DWORD *)(v12 + 48) )
      break;
    v13 = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 8 * i);
    if ( *(_QWORD *)(v13 + 48) )
    {
      memset_0(&v18, 0, sizeof(v18));
      v18.lSampleSize = 1;
      v18.bFixedSizeSamples = 1;
      Instance = CMediaType::Set(&v18, (const struct _AMMediaType *)(v13 + 456));
      if ( Instance < 0
        || (EncryptedSubtypeHack_IN(&v18), Instance = DShowWMSDKHelpers::MediaTypeSetValidForWMSDK(&v18), Instance < 0)
        || (EncryptedSubtypeHack_OUT(&v18),
            Instance = SBFThunk::Cv2NodeState::AppendPipelineDesc(v10, *(_DWORD *)(v13 + 424), v14, &v18),
            Instance < 0) )
      {
        FreeMediaType(&v18);
        goto LABEL_9;
      }
      FreeMediaType(&v18);
    }
  }
  Instance = (*(__int64 (__fastcall **)(struct IPauseBufferWriter *, __int64))(*(_QWORD *)*v2 + 24LL))(*v2, v19);
  if ( Instance < 0 )
    goto LABEL_9;
  v15 = *((_QWORD *)this + 21);
  memset_0(Buffer, 0, 0xC8u);
  if ( (int)StringCchPrintfW(Buffer, 0x64u, a2) >= 0 )
    SBEPerf::CTeHomeETWEvent<EH_SBE_SOURCE_LOAD>::TraceEvent(v15 + 560, Buffer);
  *((_DWORD *)this + 215) = 0;
  *((_QWORD *)this + 108) = 0;
LABEL_27:
  SBF2::Release<SBF2::CComSBFStateTable *>(v17);
  EhEtw::TPtr<IEhTraceSpan>::Release(&v19);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f058  mov     [rsp-8+arg_10], rbx
0x18000f05d  push    rbp
0x18000f05e  push    rsi
0x18000f05f  push    rdi
0x18000f060  push    r12
0x18000f062  push    r13
0x18000f064  push    r14
0x18000f066  push    r15
0x18000f068  lea     rbp, [rsp-0A0h]
0x18000f070  sub     rsp, 1A0h
0x18000f077  mov     rax, cs:__security_cookie
0x18000f07e  xor     rax, rsp
0x18000f081  mov     [rbp+0D0h+var_40], rax
0x18000f088  lea     r13, [rcx+0E8h]
0x18000f08f  mov     [rsp+1D0h+var_1A0], 0
0x18000f098  cmp     qword ptr [r13+0], 0
0x18000f09d  mov     r14, rdx
0x18000f0a0  mov     rsi, rcx
0x18000f0a3  mov     [rbp+0D0h+var_130], 0
0x18000f0ab  jnz     loc_18000F2EC
0x18000f0b1  mov     r12, [rcx+60h]
0x18000f0b5  lea     r15, [rcx+310h]
0x18000f0bc  test    r12, r12
0x18000f0bf  jz      short loc_18000F0FE
0x18000f0c1  mov     rbx, [r15]
0x18000f0c4  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000f0c8  call    cs:__imp_EnterCriticalSection
0x18000f0ce  mov     rcx, rbx; this
0x18000f0d1  call    ?Uninitialize@CSBE2SinkCtx@SBE2Sink@@QEAAJXZ; SBE2Sink::CSBE2SinkCtx::Uninitialize(void)
0x18000f0d6  mov     [rbx+58h], r12
0x18000f0da  lea     r8, [rbx+50h]
0x18000f0de  mov     rax, [r12]
0x18000f0e2  lea     rdx, _GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770
0x18000f0e9  mov     rcx, r12
0x18000f0ec  mov     rax, [rax]
0x18000f0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f4  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000f0f8  call    cs:__imp_LeaveCriticalSection
0x18000f0fe  test    r14, r14
0x18000f101  jnz     short loc_18000F16E
0x18000f103  xorps   xmm0, xmm0
0x18000f106  lea     rcx, [rbp+0D0h+pguid]; pguid
0x18000f10a  movups  xmmword ptr [rbp+0D0h+pguid.Data1], xmm0
0x18000f10e  call    cs:__imp_CoCreateGuid
0x18000f114  mov     ebx, eax
0x18000f116  test    eax, eax
0x18000f118  js      short loc_18000F159
0x18000f11a  lea     r14, [rsi+0F0h]
0x18000f121  mov     ebx, 104h
0x18000f126  mov     r8d, ebx; cchMax
0x18000f129  lea     rcx, [rbp+0D0h+pguid]; rguid
0x18000f12d  mov     rdx, r14; lpsz
0x18000f130  call    cs:__imp_StringFromGUID2
0x18000f136  test    eax, eax
0x18000f138  jnz     short loc_18000F141
0x18000f13a  mov     ebx, 80070057h
0x18000f13f  jmp     short loc_18000F159
0x18000f141  lea     r8, aTmpStub; ".tmp.stub"
0x18000f148  mov     rdx, rbx; unsigned __int64
0x18000f14b  mov     rcx, r14; unsigned __int16 *
0x18000f14e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f153  mov     ebx, eax
0x18000f155  test    eax, eax
0x18000f157  jns     short loc_18000F16E
0x18000f159  test    ebx, ebx
0x18000f15b  jns     loc_18000F2EE
0x18000f161  mov     rcx, rsi; this
0x18000f164  call    ?InternalUninitialize@CSBE2Sink@SBE2Sink@@AEAAXXZ; SBE2Sink::CSBE2Sink::InternalUninitialize(void)
0x18000f169  jmp     loc_18000F2EE
0x18000f16e  mov     rcx, [r15]
0x18000f171  mov     r9, r14; unsigned __int16 *
0x18000f174  mov     r8, [rsi+0B0h]; struct CDVRPolicy *
0x18000f17b  mov     rdx, [rsi+60h]; struct IFilterGraph *
0x18000f17f  mov     [rsp+1D0h+var_1B0], r13; struct IPauseBufferWriter **
0x18000f184  mov     rcx, [rcx+8]; struct IUnknown *
0x18000f188  call    ?CreateInstance@CSBE2PauseBufferWriter@SBE2PauseBuffer@@SAJPEAUIUnknown@@PEAUIFilterGraph@@PEAVCDVRPolicy@@PEAGPEAPEAUIPauseBufferWriter@@@Z; SBE2PauseBuffer::CSBE2PauseBufferWriter::CreateInstance(IUnknown *,IFilterGraph *,CDVRPolicy *,ushort *,IPauseBufferWriter * *)
0x18000f18d  mov     ebx, eax
0x18000f18f  test    eax, eax
0x18000f191  js      short loc_18000F161
0x18000f193  lea     rcx, [rsp+1D0h+var_1A0]; struct SBFThunk::Cv2NodeState **
0x18000f198  call    ?CreateInstance@Cv2NodeState@SBFThunk@@SAJPEAPEAV12@@Z; SBFThunk::Cv2NodeState::CreateInstance(SBFThunk::Cv2NodeState * *)
0x18000f19d  mov     ebx, eax
0x18000f19f  test    eax, eax
0x18000f1a1  js      short loc_18000F161
0x18000f1a3  mov     r12, [rsp+1D0h+var_1A0]
0x18000f1a8  lea     r8, [rbp+0D0h+var_130]
0x18000f1ac  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000f1b3  lea     rcx, [r12+18h]
0x18000f1b8  mov     rax, [rcx]
0x18000f1bb  mov     rax, [rax]
0x18000f1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1c3  mov     ebx, eax
0x18000f1c5  test    eax, eax
0x18000f1c7  js      short loc_18000F161
0x18000f1c9  xor     edi, edi
0x18000f1cb  mov     rax, [rsi+0A8h]
0x18000f1d2  cmp     edi, [rax+30h]
0x18000f1d5  jnb     loc_18000F27A
0x18000f1db  mov     rax, [rax+28h]
0x18000f1df  mov     r15, [rax+rdi*8]
0x18000f1e3  cmp     qword ptr [r15+30h], 0
0x18000f1e8  jz      short loc_18000F269
0x18000f1ea  xor     edx, edx; Val
0x18000f1ec  lea     rcx, [rsp+1D0h+var_190]; void *
0x18000f1f1  lea     r8d, [rdx+58h]; Size
0x18000f1f5  call    memset_0
0x18000f1fa  lea     rdx, [r15+1C8h]; struct _AMMediaType *
0x18000f201  mov     [rsp+1D0h+var_190.lSampleSize], 1
0x18000f209  lea     rcx, [rsp+1D0h+var_190]; this
0x18000f20e  mov     [rsp+1D0h+var_190.bFixedSizeSamples], 1
0x18000f216  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18000f21b  lea     rcx, [rsp+1D0h+var_190]; struct _AMMediaType *
0x18000f220  mov     ebx, eax
0x18000f222  test    eax, eax
0x18000f224  js      short loc_18000F270
0x18000f226  call    ?EncryptedSubtypeHack_IN@@YAXPEAU_AMMediaType@@@Z; EncryptedSubtypeHack_IN(_AMMediaType *)
0x18000f22b  lea     rcx, [rsp+1D0h+var_190]; struct _AMMediaType *
0x18000f230  call    ?MediaTypeSetValidForWMSDK@DShowWMSDKHelpers@@SAJPEAU_AMMediaType@@@Z; DShowWMSDKHelpers::MediaTypeSetValidForWMSDK(_AMMediaType *)
0x18000f235  lea     rcx, [rsp+1D0h+var_190]; struct _AMMediaType *
0x18000f23a  mov     ebx, eax
0x18000f23c  test    eax, eax
0x18000f23e  js      short loc_18000F270
0x18000f240  call    ?EncryptedSubtypeHack_OUT@@YAXPEAU_AMMediaType@@@Z; EncryptedSubtypeHack_OUT(_AMMediaType *)
0x18000f245  mov     edx, [r15+1A8h]; unsigned int
0x18000f24c  lea     r9, [rsp+1D0h+var_190]; struct _AMMediaType *
0x18000f251  mov     rcx, r12; this
0x18000f254  call    ?AppendPipelineDesc@Cv2NodeState@SBFThunk@@QEAAJKKPEAU_AMMediaType@@@Z; SBFThunk::Cv2NodeState::AppendPipelineDesc(ulong,ulong,_AMMediaType *)
0x18000f259  lea     rcx, [rsp+1D0h+var_190]; struct _AMMediaType *
0x18000f25e  mov     ebx, eax
0x18000f260  test    eax, eax
0x18000f262  js      short loc_18000F270
0x18000f264  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000f269  inc     edi
0x18000f26b  jmp     loc_18000F1CB
0x18000f270  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000f275  jmp     loc_18000F161
0x18000f27a  mov     rcx, [r13+0]
0x18000f27e  mov     rdx, [rbp+0D0h+var_130]
0x18000f282  mov     rax, [rcx]
0x18000f285  mov     rax, [rax+18h]
0x18000f289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f28e  mov     ebx, eax
0x18000f290  test    eax, eax
0x18000f292  js      loc_18000F161
0x18000f298  mov     rdi, [rsi+0A8h]
0x18000f29f  lea     rcx, [rbp+0D0h+Buffer]; void *
0x18000f2a3  xor     edx, edx; Val
0x18000f2a5  mov     r8d, 0C8h; Size
0x18000f2ab  call    memset_0
0x18000f2b0  mov     r8, r14; unsigned __int16 *
0x18000f2b3  lea     rcx, [rbp+0D0h+Buffer]; Buffer
0x18000f2b7  mov     edx, 64h ; 'd'; unsigned __int64
0x18000f2bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f2c1  test    eax, eax
0x18000f2c3  js      short loc_18000F2D5
0x18000f2c5  lea     rcx, [rdi+230h]
0x18000f2cc  lea     rdx, [rbp+0D0h+Buffer]
0x18000f2d0  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_SBE_SOURCE_LOAD@@@SBEPerf@@QEAAXPEAUEH_SBE_SOURCE_LOAD@@@Z; SBEPerf::CTeHomeETWEvent<EH_SBE_SOURCE_LOAD>::TraceEvent(EH_SBE_SOURCE_LOAD *)
0x18000f2d5  mov     dword ptr [rsi+35Ch], 0
0x18000f2df  mov     qword ptr [rsi+360h], 0
0x18000f2ea  jmp     short loc_18000F2EE
0x18000f2ec  xor     ebx, ebx
0x18000f2ee  lea     rcx, [rsp+1D0h+var_1A0]
0x18000f2f3  call    ??$Release@PEAVCComSBFStateTable@SBF2@@@SBF2@@YAXAEAPEAVCComSBFStateTable@0@@Z; SBF2::Release<SBF2::CComSBFStateTable *>(SBF2::CComSBFStateTable * &)
0x18000f2f8  lea     rcx, [rbp+0D0h+var_130]
0x18000f2fc  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x18000f301  mov     eax, ebx
0x18000f303  mov     rcx, [rbp+0D0h+var_40]
0x18000f30a  xor     rcx, rsp; StackCookie
0x18000f30d  call    __security_check_cookie
0x18000f312  mov     rbx, [rsp+1D0h+arg_10]
0x18000f31a  add     rsp, 1A0h
0x18000f321  pop     r15
0x18000f323  pop     r14
0x18000f325  pop     r13
0x18000f327  pop     r12
0x18000f329  pop     rdi
0x18000f32a  pop     rsi
0x18000f32b  pop     rbp
0x18000f32c  retn
```
