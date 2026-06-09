# CVssMachineInformation::GetMinDiffAreaOnVolume(ushort const *)

- ea: `0x180039394`
- end: `0x180039710`
- name: `?GetMinDiffAreaOnVolume@CVssMachineInformation@@SA_JPEBG@Z`
- size: `892`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011178`
- `0x180018eec`
- `0x18001f7f8`
- `0x18001f898`
- `0x1800200c0`
- `0x180021bc4`
- `0x180027ca0`
- `0x180028aa0`
- `0x180038fa8`

## callees

- `0x180001580`
- `0x18000212c`
- `0x18000313c`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x180012254`
- `0x18002a774`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x180039394`

## string_xrefs

- `0x1800393c1`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039650`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssMachineInformation::GetMinDiffAreaOnVolume(const unsigned __int16 *a1)
{
  bool v2; // al
  __int64 v3; // r9
  const unsigned __int16 *v4; // r8
  __int64 v5; // rsi
  __int64 result; // rax
  int v7; // ebx
  char v8; // [rsp+20h] [rbp-2D8h]
  __int64 v9; // [rsp+20h] [rbp-2D8h]
  __int64 v10; // [rsp+50h] [rbp-2A8h] BYREF
  int v11; // [rsp+58h] [rbp-2A0h] BYREF
  const unsigned __int16 *v12; // [rsp+60h] [rbp-298h]
  const unsigned __int16 *v13; // [rsp+68h] [rbp-290h] BYREF
  const unsigned __int16 *v14; // [rsp+70h] [rbp-288h]
  const unsigned __int16 *v15; // [rsp+78h] [rbp-280h]
  int v16; // [rsp+80h] [rbp-278h]
  int v17; // [rsp+84h] [rbp-274h]
  int v18; // [rsp+88h] [rbp-270h]
  _BYTE v19[120]; // [rsp+90h] [rbp-268h] BYREF
  int v20; // [rsp+108h] [rbp-1F0h]
  const unsigned __int16 *v21; // [rsp+110h] [rbp-1E8h] BYREF
  __int128 v22; // [rsp+118h] [rbp-1E0h]
  __int128 v23; // [rsp+128h] [rbp-1D0h]
  _WORD v24[2]; // [rsp+138h] [rbp-1C0h] BYREF
  __int64 v25; // [rsp+13Ch] [rbp-1BCh]
  __int64 v26; // [rsp+148h] [rbp-1B0h]
  __int64 v27; // [rsp+150h] [rbp-1A8h]
  int v28; // [rsp+158h] [rbp-1A0h]
  __int64 v29; // [rsp+160h] [rbp-198h]
  __int16 v30; // [rsp+168h] [rbp-190h]
  void **v31; // [rsp+170h] [rbp-188h]
  __int64 v32; // [rsp+178h] [rbp-180h]
  int v33; // [rsp+1B0h] [rbp-148h]
  LPVOID v34; // [rsp+1C0h] [rbp-138h] BYREF
  int v35; // [rsp+1C8h] [rbp-130h]
  unsigned int v36; // [rsp+1E4h] [rbp-114h]
  _com_error *v37; // [rsp+230h] [rbp-C8h] BYREF
  const std::exception *v38; // [rsp+238h] [rbp-C0h] BYREF
  _BYTE v39[112]; // [rsp+240h] [rbp-B8h] BYREF

  v12 = a1;
  v21 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  *(_QWORD *)&v22 = L"CVssMachineInformation::GetMinDiffAreaOnVolume";
  *((_QWORD *)&v22 + 1) = L"REGREGSC";
  *(_QWORD *)&v23 = 0xB00000698LL;
  DWORD2(v23) = 255;
  v33 = 0x1000000;
  memset_0(v24, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v34, (__int64)&v21, 0);
  v2 = IsVolMgmtVolumeName(a1);
  try
  {
    if ( v2 )
    {
      v4 = a1;
    }
    else
    {
      v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v14 = L"CVssMachineInformation::GetMinDiffAreaOnVolume";
      v15 = L"REGREGSC";
      v16 = 1700;
      v17 = 11;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      GetVolumeNameWithCheck(&v13, 2147942487LL, a1, v39);
      v4 = (const unsigned __int16 *)v39;
    }
    v21 = 0;
    v24[0] = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v32 = 0;
    v31 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v22 = 0;
    v23 = 0;
    v8 = 1;
    LOBYTE(v3) = 1;
    CVssIOCTLChannel::Open(&v21, &v34, v4, v3, v8, 2, 0x80000000);
    CVssIOCTLChannel::Call(&v21, (__int64)&v34, 0x534058u, 1, 0, 0);
    v10 = 0;
    CVssIOCTLChannel::Unpack<__int64>((CVssIOCTLChannel *)&v21, (struct CVssFunctionTracer *)&v34, &v10);
    v5 = v10;
    v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v14 = L"CVssMachineInformation::GetMinDiffAreaOnVolume";
    v15 = L"REGREGSC";
    v16 = 1721;
    v17 = 11;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    CVssFunctionTracer::Trace(&v34, &v13, L"Minimum diff area size for volume %s: %I64d", a1, v5);
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v21);
    CVssFunctionTracer::~CVssFunctionTracer(&v34);
    result = v5;
  }
  catch ( long v11 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v34,
      v11,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaOnVolume",
      0x6BEu,
      v36);
    goto LABEL_6;
  }
  catch ( _com_error *v37 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v34,
      v37,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaOnVolume",
      0x6BEu,
      v36);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v34,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaOnVolume",
      0x6BEu,
      v36);
LABEL_6:
    v7 = v35;
    v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v14 = L"CVssMachineInformation::GetMinDiffAreaOnVolume";
    v15 = L"REGREGSC";
    v16 = 1728;
    v17 = 11;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    LODWORD(v9) = v7;
    CVssFunctionTracer::Trace(
      &v34,
      &v13,
      L"Cannot retrieve minimum diff area for volume %s [0x%08lx]. Using the default value %I64d",
      v12,
      v9,
      335544320);
    CVssFunctionTracer::~CVssFunctionTracer(&v34);
    return 335544320;
  }
  catch ( const std::exception *v38 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v34,
      v38,
      L"base\\stor\\vss\\modules\\registry\\registry.cxx",
      L"REGREGSC",
      L"CVssMachineInformation::GetMinDiffAreaOnVolume",
      0x6BEu,
      v36);
  }
  if ( v2 )
  {
    v4 = a1;
  }
  else
  {
    v13 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v14 = L"CVssMachineInformation::GetMinDiffAreaOnVolume";
    v15 = L"REGREGSC";
    v16 = 1700;
    v17 = 11;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    GetVolumeNameWithCheck(&v13, 2147942487LL, a1, v39);
    v4 = (const unsigned __int16 *)v39;
  }
}

```

## disassembly

```asm
0x180039394  mov     r11, rsp
0x180039397  push    rbx
0x180039398  push    rsi
0x180039399  push    rdi
0x18003939a  push    r12
0x18003939c  push    r14
0x18003939e  push    r15
0x1800393a0  sub     rsp, 2C8h
0x1800393a7  mov     rax, cs:__security_cookie
0x1800393ae  xor     rax, rsp
0x1800393b1  mov     [rsp+2F8h+var_48], rax
0x1800393b9  mov     rbx, rcx
0x1800393bc  mov     [rsp+2F8h+var_298], rcx
0x1800393c1  lea     r14, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x1800393c8  mov     [r11-1E8h], r14
0x1800393cf  lea     r15, aCvssmachineinf; "CVssMachineInformation::GetMinDiffAreaO"...
0x1800393d6  mov     [r11-1E0h], r15
0x1800393dd  lea     r12, aRegregsc; "REGREGSC"
0x1800393e4  mov     [r11-1D8h], r12
0x1800393eb  mov     dword ptr [rsp+2F8h+var_1D0], 698h
0x1800393f6  mov     dword ptr [rsp+2F8h+var_1D0+4], 0Bh
0x180039401  mov     esi, 0FFh
0x180039406  mov     dword ptr [rsp+2F8h+var_1D0+8], esi
0x18003940d  xor     edi, edi
0x18003940f  mov     [rsp+2F8h+var_148], 1000000h
0x18003941a  xor     edx, edx; Val
0x18003941c  lea     r8d, [rdi+78h]; Size
0x180039420  lea     rcx, [r11-1C0h]; void *
0x180039427  call    memset_0
0x18003942c  xor     r8d, r8d
0x18003942f  lea     rdx, [rsp+2F8h+var_1E8]
0x180039437  lea     rcx, [rsp+2F8h+var_138]
0x18003943f  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180039444  nop
0x180039445  mov     rcx, rbx; unsigned __int16 *
0x180039448  call    ?IsVolMgmtVolumeName@@YA_NPEBG@Z; IsVolMgmtVolumeName(ushort const *)
0x18003944d  test    al, al
0x18003944f  jnz     short loc_1800394BF
0x180039451  mov     [rsp+2F8h+var_290], r14
0x180039456  mov     [rsp+2F8h+var_288], r15
0x18003945b  mov     [rsp+2F8h+var_280], r12
0x180039460  mov     [rsp+2F8h+var_278], 6A4h
0x18003946b  mov     [rsp+2F8h+var_274], 0Bh
0x180039476  mov     [rsp+2F8h+var_270], esi
0x18003947d  mov     [rsp+2F8h+var_1F0], 1000000h
0x180039488  xor     edx, edx; Val
0x18003948a  lea     r8d, [rdi+78h]; Size
0x18003948e  lea     rcx, [rsp+2F8h+var_268]; void *
0x180039496  call    memset_0
0x18003949b  lea     r9, [rsp+2F8h+var_B8]
0x1800394a3  mov     r8, rbx
0x1800394a6  mov     edx, 80070057h
0x1800394ab  lea     rcx, [rsp+2F8h+var_290]
0x1800394b0  call    ?GetVolumeNameWithCheck@@YAXUCVssDebugInfo@@JPEBGPEAGK@Z; GetVolumeNameWithCheck(CVssDebugInfo,long,ushort const *,ushort *,ulong)
0x1800394b5  lea     r8, [rsp+2F8h+var_B8]
0x1800394bd  jmp     short loc_1800394C2
0x1800394bf  mov     r8, rbx
0x1800394c2  mov     [rsp+2F8h+var_1E8], rdi
0x1800394ca  mov     [rsp+2F8h+var_1C0], di
0x1800394d2  mov     [rsp+2F8h+var_1BC], rdi
0x1800394da  mov     [rsp+2F8h+var_1B0], rdi
0x1800394e2  mov     [rsp+2F8h+var_1A8], rdi
0x1800394ea  mov     [rsp+2F8h+var_1A0], edi
0x1800394f1  mov     [rsp+2F8h+var_198], rdi
0x1800394f9  mov     [rsp+2F8h+var_190], di
0x180039501  mov     [rsp+2F8h+var_180], rdi
0x180039509  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180039510  mov     [rsp+2F8h+var_188], rax
0x180039518  xorps   xmm0, xmm0
0x18003951b  movups  [rsp+2F8h+var_1E0], xmm0
0x180039523  movups  [rsp+2F8h+var_1D0], xmm0
0x18003952b  mov     [rsp+2F8h+var_2B8], 80h
0x180039533  mov     dword ptr [rsp+2F8h+var_2C8], 80000000h
0x18003953b  mov     dword ptr [rsp+2F8h+var_2D0], 2
0x180039543  mov     byte ptr [rsp+2F8h+var_2D8], 1
0x180039548  mov     r9b, 1
0x18003954b  lea     rdx, [rsp+2F8h+var_138]
0x180039553  lea     rcx, [rsp+2F8h+var_1E8]
0x18003955b  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z; CVssIOCTLChannel::Open(CVssFunctionTracer &,ushort const *,bool,bool,_VSS_ICHANNEL_LOGGING,ulong,ulong,ulong)
0x180039560  mov     [rsp+2F8h+var_2C8], rdi
0x180039565  mov     byte ptr [rsp+2F8h+var_2D0], dil
0x18003956a  mov     dword ptr [rsp+2F8h+var_2D8], edi
0x18003956e  mov     r9b, 1
0x180039571  mov     r8d, 534058h
0x180039577  lea     rdx, [rsp+2F8h+var_138]
0x18003957f  lea     rcx, [rsp+2F8h+var_1E8]
0x180039587  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z; CVssIOCTLChannel::Call(CVssFunctionTracer &,ulong,bool,_VSS_ICHANNEL_LOGGING,bool,void *)
0x18003958c  mov     [rsp+2F8h+var_2A8], rdi
0x180039591  lea     r8, [rsp+2F8h+var_2A8]
0x180039596  lea     rdx, [rsp+2F8h+var_138]
0x18003959e  lea     rcx, [rsp+2F8h+var_1E8]
0x1800395a6  call    ??$Unpack@_J@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEA_JK_N@Z; CVssIOCTLChannel::Unpack<__int64>(CVssFunctionTracer &,__int64 *,ulong,bool)
0x1800395ab  mov     rsi, [rsp+2F8h+var_2A8]
0x1800395b0  mov     [rsp+2F8h+var_290], r14
0x1800395b5  mov     [rsp+2F8h+var_288], r15
0x1800395ba  mov     [rsp+2F8h+var_280], r12
0x1800395bf  mov     [rsp+2F8h+var_278], 6B9h
0x1800395ca  mov     [rsp+2F8h+var_274], 0Bh
0x1800395d5  mov     [rsp+2F8h+var_270], 0FFh
0x1800395e0  mov     [rsp+2F8h+var_1F0], 1000000h
0x1800395eb  xor     edx, edx; Val
0x1800395ed  lea     r8d, [rdx+78h]; Size
0x1800395f1  lea     rcx, [rsp+2F8h+var_268]; void *
0x1800395f9  call    memset_0
0x1800395fe  mov     [rsp+2F8h+var_2D8], rsi
0x180039603  mov     r9, rbx
0x180039606  lea     r8, aMinimumDiffAre; "Minimum diff area size for volume %s: %"...
0x18003960d  lea     rdx, [rsp+2F8h+var_290]
0x180039612  lea     rcx, [rsp+2F8h+var_138]
0x18003961a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003961f  nop
0x180039620  lea     rcx, [rsp+2F8h+var_1E8]; this
0x180039628  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x18003962d  nop
0x18003962e  lea     rcx, [rsp+2F8h+var_138]; this
0x180039636  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003963b  mov     rax, rsi
0x18003963e  jmp     loc_1800396EF
0x180039643  jmp     short loc_180039649
0x180039645  jmp     short loc_180039649
0x180039647  jmp     short $+2
0x180039649  mov     ebx, [rsp+2F8h+var_130]
0x180039650  lea     r14, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039657  mov     [rsp+2F8h+var_290], r14
0x18003965c  lea     r15, aCvssmachineinf; "CVssMachineInformation::GetMinDiffAreaO"...
0x180039663  mov     [rsp+2F8h+var_288], r15
0x180039668  lea     r12, aRegregsc; "REGREGSC"
0x18003966f  mov     [rsp+2F8h+var_280], r12
0x180039674  mov     [rsp+2F8h+var_278], 6C0h
0x18003967f  mov     [rsp+2F8h+var_274], 0Bh
0x18003968a  mov     [rsp+2F8h+var_270], 0FFh
0x180039695  mov     [rsp+2F8h+var_1F0], 1000000h
0x1800396a0  xor     edx, edx; Val
0x1800396a2  lea     r8d, [rdx+78h]; Size
0x1800396a6  lea     rcx, [rsp+2F8h+var_268]; void *
0x1800396ae  call    memset_0
0x1800396b3  mov     edi, 14000000h
0x1800396b8  mov     [rsp+2F8h+var_2D0], rdi
0x1800396bd  mov     dword ptr [rsp+2F8h+var_2D8], ebx
0x1800396c1  mov     r9, [rsp+2F8h+var_298]
0x1800396c6  lea     r8, aCannotRetrieve_0; "Cannot retrieve minimum diff area for v"...
0x1800396cd  lea     rdx, [rsp+2F8h+var_290]
0x1800396d2  lea     rcx, [rsp+2F8h+var_138]
0x1800396da  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800396df  nop
0x1800396e0  lea     rcx, [rsp+2F8h+var_138]; this
0x1800396e8  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800396ed  mov     eax, edi
0x1800396ef  mov     rcx, [rsp+2F8h+var_48]
0x1800396f7  xor     rcx, rsp; StackCookie
0x1800396fa  call    __security_check_cookie
0x1800396ff  add     rsp, 2C8h
0x180039706  pop     r15
0x180039708  pop     r14
0x18003970a  pop     r12
0x18003970c  pop     rdi
0x18003970d  pop     rsi
0x18003970e  pop     rbx
0x18003970f  retn
```
