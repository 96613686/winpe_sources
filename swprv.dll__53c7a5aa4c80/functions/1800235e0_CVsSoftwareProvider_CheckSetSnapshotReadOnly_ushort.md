# CVsSoftwareProvider::CheckSetSnapshotReadOnly(ushort *)

- ea: `0x1800235e0`
- end: `0x18002382d`
- name: `?CheckSetSnapshotReadOnly@CVsSoftwareProvider@@CAXPEAG@Z`
- size: `589`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180025228`

## callees

- `0x18000212c`
- `0x18000313c`
- `0x1800039d8`
- `0x180003de8`
- `0x180004a38`
- `0x18000610c`
- `0x180018334`
- `0x1800235e0`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`

## string_xrefs

- `0x1800235ff`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x18002360a`: `CVsSoftwareProvider::CheckSetSnapshotReadOnly`
- `0x180023764`: `Changing snapshot %s to read-only`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVsSoftwareProvider::CheckSetSnapshotReadOnly(unsigned __int16 *a1)
{
  __int64 v2; // rbx
  char v3; // [rsp+20h] [rbp-E0h]
  __int64 v4; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v5; // [rsp+58h] [rbp-A8h]
  __int128 v6; // [rsp+68h] [rbp-98h]
  __int16 v7; // [rsp+78h] [rbp-88h]
  __int64 v8; // [rsp+7Ch] [rbp-84h]
  __int64 v9; // [rsp+88h] [rbp-78h]
  __int64 v10; // [rsp+90h] [rbp-70h]
  int v11; // [rsp+98h] [rbp-68h]
  __int64 v12; // [rsp+A0h] [rbp-60h]
  __int16 v13; // [rsp+A8h] [rbp-58h]
  void **v14; // [rsp+B0h] [rbp-50h]
  __int64 v15; // [rsp+B8h] [rbp-48h]
  __int64 v16; // [rsp+C0h] [rbp-40h]
  __int64 v17; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v19; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-20h]
  int v21; // [rsp+E8h] [rbp-18h]
  int v22; // [rsp+ECh] [rbp-14h]
  int v23; // [rsp+F0h] [rbp-10h]
  _BYTE v24[120]; // [rsp+F8h] [rbp-8h] BYREF
  int v25; // [rsp+170h] [rbp+70h]
  LPVOID v26[22]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v27; // [rsp+248h] [rbp+148h] BYREF

  v18 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  v19 = L"CVsSoftwareProvider::CheckSetSnapshotReadOnly";
  v20 = L"SPRDELEC";
  v21 = 754;
  v22 = 2;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v26, (__int64)&v18, 0);
  v4 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v14 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v5 = 0;
  v6 = 0;
  v3 = 1;
  CVssIOCTLChannel::Open(&v4, v26, a1, 0, v3, 2, -1073741824);
  v27 = 0;
  CVssIOCTLChannel::Call(&v4, (__int64)v26, 0x560038u, 1, 2, 0);
  CVssIOCTLChannel::Unpack<__int64>((CVssIOCTLChannel *)&v4, (struct CVssFunctionTracer *)v26, &v27);
  v2 = v27;
  if ( (v27 & 0x1000000000000000LL) == 0 )
  {
    v18 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
    v19 = L"CVsSoftwareProvider::CheckSetSnapshotReadOnly";
    v20 = L"SPRDELEC";
    v21 = 775;
    v22 = 2;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CVssFunctionTracer::Trace(v26, &v18, L"Changing snapshot %s to read-only", a1);
    CVssIOCTLChannel::Call(&v4, (__int64)v26, 0x90020u, 1, 2, 0);
    v17 = 0;
    v16 = v2 | 0x1000000000000000LL;
    CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(
      (CVssIOCTLChannel *)&v4,
      (struct CVssFunctionTracer *)v26);
    CVssIOCTLChannel::Call(&v4, (__int64)v26, 0x560034u, 1, 2, 0);
  }
  CVssIOCTLChannel::Close((CVssIOCTLChannel *)&v4);
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v4);
  CVssFunctionTracer::~CVssFunctionTracer(v26);
}

```

## disassembly

```asm
0x1800235e0  push    rbp
0x1800235e2  push    rbx
0x1800235e3  push    rsi
0x1800235e4  push    rdi
0x1800235e5  push    r12
0x1800235e7  push    r13
0x1800235e9  push    r14
0x1800235eb  push    r15
0x1800235ed  lea     rbp, [rsp-0F8h]
0x1800235f5  sub     rsp, 1F8h
0x1800235fc  mov     rdi, rcx
0x1800235ff  lea     r15, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\softprv\\src"...
0x180023606  mov     [rbp+130h+var_160], r15
0x18002360a  lea     r12, aCvssoftwarepro_14; "CVsSoftwareProvider::CheckSetSnapshotRe"...
0x180023611  mov     [rbp+130h+var_158], r12
0x180023615  lea     r13, aSprdelec; "SPRDELEC"
0x18002361c  mov     [rbp+130h+var_150], r13
0x180023620  mov     [rbp+130h+var_148], 2F2h
0x180023627  mov     r14d, 2
0x18002362d  mov     [rbp+130h+var_144], r14d
0x180023631  mov     [rbp+130h+var_140], 0FFh
0x180023638  xor     esi, esi
0x18002363a  mov     [rbp+130h+var_C0], 1000000h
0x180023641  xor     edx, edx; Val
0x180023643  lea     r8d, [r14+76h]; Size
0x180023647  lea     rcx, [rbp+130h+var_138]; void *
0x18002364b  call    memset_0
0x180023650  xor     r8d, r8d
0x180023653  lea     rdx, [rbp+130h+var_160]
0x180023657  lea     rcx, [rbp+130h+var_B0]
0x18002365e  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180023663  nop
0x180023664  mov     [rsp+230h+var_1E0], rsi
0x180023669  mov     [rsp+230h+var_1B8], si
0x18002366e  mov     [rsp+230h+var_1B4], rsi
0x180023673  mov     [rbp+130h+var_1A8], rsi
0x180023677  mov     [rbp+130h+var_1A0], rsi
0x18002367b  mov     [rbp+130h+var_198], esi
0x18002367e  mov     [rbp+130h+var_190], rsi
0x180023682  mov     [rbp+130h+var_188], si
0x180023686  mov     [rbp+130h+var_178], rsi
0x18002368a  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180023691  mov     [rbp+130h+var_180], rax
0x180023695  xorps   xmm0, xmm0
0x180023698  movups  [rsp+230h+var_1D8], xmm0
0x18002369d  movups  [rsp+230h+var_1C8], xmm0
0x1800236a2  mov     [rsp+230h+var_1F0], 80h
0x1800236aa  mov     dword ptr [rsp+230h+var_200], 0C0000000h
0x1800236b2  mov     [rsp+230h+var_208], r14d
0x1800236b7  mov     [rsp+230h+var_210], 1
0x1800236bc  xor     r9d, r9d
0x1800236bf  mov     r8, rdi
0x1800236c2  lea     rdx, [rbp+130h+var_B0]
0x1800236c9  lea     rcx, [rsp+230h+var_1E0]
0x1800236ce  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x1800236d3  mov     [rbp+130h+arg_8], rsi
0x1800236da  mov     [rsp+230h+var_200], rsi
0x1800236df  mov     byte ptr [rsp+230h+var_208], sil
0x1800236e4  mov     dword ptr [rsp+230h+var_210], r14d
0x1800236e9  mov     r9b, 1
0x1800236ec  mov     r8d, 560038h
0x1800236f2  lea     rdx, [rbp+130h+var_B0]
0x1800236f9  lea     rcx, [rsp+230h+var_1E0]
0x1800236fe  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x180023703  lea     r8, [rbp+130h+arg_8]
0x18002370a  lea     rdx, [rbp+130h+var_B0]
0x180023711  lea     rcx, [rsp+230h+var_1E0]
0x180023716  call    ??$Unpack@_J@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEA_JK_N@Z; CVssIOCTLChannel::Unpack<__int64>(CVssFunctionTracer &,__int64 *,ulong,bool)
0x18002371b  mov     rbx, [rbp+130h+arg_8]
0x180023722  bt      rbx, 3Ch ; '<'
0x180023727  jb      loc_1800237F7
0x18002372d  mov     [rbp+130h+var_160], r15
0x180023731  mov     [rbp+130h+var_158], r12
0x180023735  mov     [rbp+130h+var_150], r13
0x180023739  mov     [rbp+130h+var_148], 307h
0x180023740  mov     [rbp+130h+var_144], r14d
0x180023744  mov     [rbp+130h+var_140], 0FFh
0x18002374b  mov     [rbp+130h+var_C0], 1000000h
0x180023752  xor     edx, edx; Val
0x180023754  lea     r8d, [r14+76h]; Size
0x180023758  lea     rcx, [rbp+130h+var_138]; void *
0x18002375c  call    memset_0
0x180023761  mov     r9, rdi
0x180023764  lea     r8, aChangingSnapsh; "Changing snapshot %s to read-only"
0x18002376b  lea     rdx, [rbp+130h+var_160]
0x18002376f  lea     rcx, [rbp+130h+var_B0]
0x180023776  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002377b  mov     [rsp+230h+var_200], rsi
0x180023780  mov     byte ptr [rsp+230h+var_208], sil
0x180023785  mov     dword ptr [rsp+230h+var_210], r14d
0x18002378a  mov     r9b, 1
0x18002378d  mov     r8d, 90020h
0x180023793  lea     rdx, [rbp+130h+var_B0]
0x18002379a  lea     rcx, [rsp+230h+var_1E0]
0x18002379f  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800237a4  mov     [rbp+130h+var_168], rsi
0x1800237a8  mov     rax, 1000000000000000h
0x1800237b2  or      rbx, rax
0x1800237b5  mov     [rbp+130h+var_170], rbx
0x1800237b9  lea     r8, [rbp+130h+var_170]
0x1800237bd  lea     rdx, [rbp+130h+var_B0]; struct CVssFunctionTracer *
0x1800237c4  lea     rcx, [rsp+230h+var_1E0]; this
0x1800237c9  call    ??$PackArray@U_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@@CVssIOCTLChannel@@QEAAPEAXAEAVCVssFunctionTracer@@PEAU_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION@@K@Z; CVssIOCTLChannel::PackArray<_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION>(CVssFunctionTracer &,_VOLUME_SET_GPT_ATTRIBUTES_INFORMATION *,ulong)
0x1800237ce  mov     [rsp+230h+var_200], rsi
0x1800237d3  mov     byte ptr [rsp+230h+var_208], sil
0x1800237d8  mov     dword ptr [rsp+230h+var_210], r14d
0x1800237dd  mov     r9b, 1
0x1800237e0  mov     r8d, 560034h
0x1800237e6  lea     rdx, [rbp+130h+var_B0]
0x1800237ed  lea     rcx, [rsp+230h+var_1E0]
0x1800237f2  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x1800237f7  lea     rcx, [rsp+230h+var_1E0]; this
0x1800237fc  call    ?Close@CVssIOCTLChannel@@QEAAXXZ; CVssIOCTLChannel::Close(void)
0x180023801  nop
0x180023802  lea     rcx, [rsp+230h+var_1E0]; this
0x180023807  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x18002380c  nop
0x18002380d  lea     rcx, [rbp+130h+var_B0]; this
0x180023814  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180023819  add     rsp, 1F8h
0x180023820  pop     r15
0x180023822  pop     r14
0x180023824  pop     r13
0x180023826  pop     r12
0x180023828  pop     rdi
0x180023829  pop     rsi
0x18002382a  pop     rbx
0x18002382b  pop     rbp
0x18002382c  retn
```
