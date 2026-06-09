# CVsSoftwareProvider::GetTimewarpSnapshotsCount(CVssIOCTLChannel &)

- ea: `0x18002432c`
- end: `0x180024708`
- name: `?GetTimewarpSnapshotsCount@CVsSoftwareProvider@@CAKAEAVCVssIOCTLChannel@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(struct CVssIOCTLChannel *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task`

## callers

- `0x180025228`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180002f1c`
- `0x180003718`
- `0x1800039d8`
- `0x180003de8`
- `0x18000610c`
- `0x180015864`
- `0x180016ff0`
- `0x18001ae14`
- `0x18001d648`
- `0x18002432c`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800419fc`

## string_xrefs

- `0x18002435c`: `base\stor\vss\modules\softprv\src\delete.cxx`
- `0x180024506`: `Warning: snapshot %s cannot be opened`

## pseudocode

```c
__int64 __fastcall CVsSoftwareProvider::GetTimewarpSnapshotsCount(struct CVssIOCTLChannel *this)
{
  unsigned int v2; // edi
  int v3; // ebx
  bool v4; // cl
  unsigned int v5; // eax
  unsigned __int16 **Ref; // rax
  unsigned __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v10; // [rsp+20h] [rbp-E0h]
  void **v11; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v12; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+68h] [rbp-98h]
  __int128 v15; // [rsp+78h] [rbp-88h]
  _WORD v16[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v17; // [rsp+8Ch] [rbp-74h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+A8h] [rbp-58h]
  __int64 v21; // [rsp+B0h] [rbp-50h]
  __int16 v22; // [rsp+B8h] [rbp-48h]
  void **v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  int v25; // [rsp+100h] [rbp+0h]
  LPVOID v26; // [rsp+110h] [rbp+10h] BYREF
  int v27; // [rsp+118h] [rbp+18h]
  _QWORD v28[3]; // [rsp+180h] [rbp+80h] BYREF
  int v29; // [rsp+198h] [rbp+98h]
  int v30; // [rsp+19Ch] [rbp+9Ch]
  int v31; // [rsp+1A0h] [rbp+A0h]
  _BYTE v32[120]; // [rsp+1A8h] [rbp+A8h] BYREF
  int v33; // [rsp+220h] [rbp+120h]
  _QWORD v34[3]; // [rsp+228h] [rbp+128h] BYREF
  int v35; // [rsp+240h] [rbp+140h]
  int v36; // [rsp+244h] [rbp+144h]
  int v37; // [rsp+248h] [rbp+148h]
  _BYTE v38[120]; // [rsp+250h] [rbp+150h] BYREF
  int v39; // [rsp+2C8h] [rbp+1C8h]
  _QWORD v40[3]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v41; // [rsp+2E8h] [rbp+1E8h]
  int v42; // [rsp+2ECh] [rbp+1ECh]
  int v43; // [rsp+2F0h] [rbp+1F0h]
  _BYTE v44[120]; // [rsp+2F8h] [rbp+1F8h] BYREF
  int v45; // [rsp+370h] [rbp+270h]
  __int128 Buf1; // [rsp+378h] [rbp+278h] BYREF
  unsigned __int16 v47[264]; // [rsp+390h] [rbp+290h] BYREF

  v13 = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
  *(_QWORD *)&v14 = L"CVsSoftwareProvider::GetTimewarpSnapshotsCount";
  *((_QWORD *)&v14 + 1) = L"SPRDELEC";
  *(_QWORD *)&v15 = 0x2000002AELL;
  DWORD2(v15) = 255;
  v25 = 0x1000000;
  memset_0(v16, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v26, (__int64)&v13, 0);
  v2 = 0;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 16) = 0;
  CVssIOCTLChannel::Call(this, (__int64)&v26, 0x530018u, 1, 2, 0);
  LODWORD(Buf1) = 0;
  CVssIOCTLChannel::Unpack<unsigned long>(this, (struct CVssFunctionTracer *)&v26, &Buf1);
  v12 = 0;
  v11 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  while ( 1 )
  {
    Ref = (unsigned __int16 **)CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(&v11);
    if ( !CVssIOCTLChannel::UnpackZeroString(this, (struct CVssFunctionTracer *)&v26, Ref) )
      break;
    VssConcatenate((struct CVssFunctionTracer *)&v26, v47, v7, L"\\\\?\\GLOBALROOT", v12);
    v13 = 0;
    v16[0] = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v24 = 0;
    v23 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v14 = 0;
    v15 = 0;
    LOBYTE(v9) = 1;
    v27 = CVssIOCTLChannel::Open(&v13, &v26, v47, 0, v9, 2, 0);
    if ( v27 >= 0 )
    {
      v27 = CVssIOCTLChannel::Call(&v13, (__int64)&v26, 0x53019Cu, 0, 0, 0);
      if ( v27 >= 0 )
      {
        LODWORD(Buf1) = 0;
        CVssIOCTLChannel::Unpack<unsigned long>((CVssIOCTLChannel *)&v13, (struct CVssFunctionTracer *)&v26, &Buf1);
        v3 = Buf1;
        if ( (unsigned int)Buf1 >= 0x10 )
        {
          Buf1 = 0;
          CVssIOCTLChannel::Unpack<_GUID>((__int64)&v13, (struct CVssFunctionTracer *)&v26, &Buf1);
          v4 = memcmp_0(&Buf1, &VOLSNAP_APPINFO_GUID_CLIENT_ACCESSIBLE, 0x10u) == 0;
          v5 = v2 + 1;
          if ( !v4 )
            v5 = v2;
          v2 = v5;
        }
        else
        {
          v40[0] = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
          v40[1] = L"CVsSoftwareProvider::GetTimewarpSnapshotsCount";
          v40[2] = L"SPRDELEC";
          v41 = 731;
          v42 = 2;
          v43 = 255;
          v45 = 0x1000000;
          memset_0(v44, 0, sizeof(v44));
          LODWORD(v10) = v3;
          CVssFunctionTracer::Trace(&v26, v40, L"Warning: small size snapshot detected: %s %ld", v24, v10);
          v27 = 0;
        }
      }
      else
      {
        v34[0] = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
        v34[1] = L"CVsSoftwareProvider::GetTimewarpSnapshotsCount";
        v34[2] = L"SPRDELEC";
        v35 = 720;
        v36 = 2;
        v37 = 255;
        v39 = 0x1000000;
        memset_0(v38, 0, sizeof(v38));
        CVssFunctionTracer::Trace(&v26, v34, L"Warning: snapshot %s cannot be queried for properties", v47);
      }
    }
    else
    {
      v28[0] = L"base\\stor\\vss\\modules\\softprv\\src\\delete.cxx";
      v28[1] = L"CVsSoftwareProvider::GetTimewarpSnapshotsCount";
      v28[2] = L"SPRDELEC";
      v29 = 712;
      v30 = 2;
      v31 = 255;
      v33 = 0x1000000;
      memset_0(v32, 0, sizeof(v32));
      CVssFunctionTracer::Trace(&v26, v28, L"Warning: snapshot %s cannot be opened", v47);
    }
    CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v13);
  }
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v11);
  CVssFunctionTracer::~CVssFunctionTracer(&v26);
  return v2;
}

```

## disassembly

```asm
0x18002432c  push    rbp
0x18002432e  push    rbx
0x18002432f  push    rsi
0x180024330  push    rdi
0x180024331  push    r12
0x180024333  push    r13
0x180024335  push    r14
0x180024337  push    r15
0x180024339  lea     rbp, [rsp-4B8h]
0x180024341  sub     rsp, 5B8h
0x180024348  mov     rax, cs:__security_cookie
0x18002434f  xor     rax, rsp
0x180024352  mov     [rbp+4F0h+var_50], rax
0x180024359  mov     rsi, rcx
0x18002435c  lea     r12, aBaseStorVssMod_5
0x180024363  mov     [rsp+5F0h+var_590], r12
0x180024368  lea     r13, aCvssoftwarepro_27
0x18002436f  mov     qword ptr [rsp+5F0h+var_588], r13
0x180024374  lea     rbx, aSprdelec
0x18002437b  mov     qword ptr [rsp+5F0h+var_588+8], rbx
0x180024380  mov     dword ptr [rsp+5F0h+var_578], 2AEh
0x180024388  mov     r15d, 2
0x18002438e  mov     dword ptr [rsp+5F0h+var_578+4], r15d
0x180024393  mov     dword ptr [rbp+4F0h+var_578+8], 0FFh
0x18002439a  xor     r14d, r14d
0x18002439d  mov     [rbp+4F0h+var_4F0], 1000000h
0x1800243a4  xor     edx, edx; Val
0x1800243a6  lea     r8d, [r15+76h]; Size
0x1800243aa  lea     rcx, [rbp+4F0h+var_568]; void *
0x1800243ae  call    memset_0
0x1800243b3  xor     r8d, r8d
0x1800243b6  lea     rdx, [rsp+5F0h+var_590]
0x1800243bb  lea     rcx, [rbp+4F0h+var_4E0]
0x1800243bf  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z
0x1800243c4  nop
0x1800243c5  mov     edi, r14d
0x1800243c8  mov     [rsi+2Ch], r14d
0x1800243cc  mov     [rsi+40h], r14d
0x1800243d0  mov     [rsp+5F0h+var_5C0], r14
0x1800243d5  mov     byte ptr [rsp+5F0h+var_5C8], r14b
0x1800243da  mov     dword ptr [rsp+5F0h+var_5D0], r15d
0x1800243df  mov     r9b, 1
0x1800243e2  mov     r8d, 530018h
0x1800243e8  lea     rdx, [rbp+4F0h+var_4E0]
0x1800243ec  mov     rcx, rsi
0x1800243ef  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z
0x1800243f4  mov     dword ptr [rbp+4F0h+Buf1], r14d
0x1800243fb  lea     r8, [rbp+4F0h+Buf1]
0x180024402  lea     rdx, [rbp+4F0h+var_4E0]
0x180024406  mov     rcx, rsi
0x180024409  call    ??$Unpack@K@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAKK_N@Z
0x18002440e  mov     [rsp+5F0h+var_598], r14
0x180024413  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@
0x18002441a  mov     [rsp+5F0h+var_5A0], rax
0x18002441f  jmp     loc_1800246AD
0x180024424  mov     rax, [rsp+5F0h+var_598]
0x180024429  mov     [rsp+5F0h+var_5D0], rax; unsigned __int16 *
0x18002442e  lea     r9, aGlobalroot_3
0x180024435  lea     rdx, [rbp+4F0h+var_260]; unsigned __int16 *
0x18002443c  lea     rcx, [rbp+4F0h+var_4E0]; struct CVssFunctionTracer *
0x180024440  call    ?VssConcatenate@@YAXAEAVCVssFunctionTracer@@PEAG_KPEBG3@Z
0x180024445  mov     [rsp+5F0h+var_590], r14
0x18002444a  mov     [rbp+4F0h+var_568], r14w
0x18002444f  mov     [rbp+4F0h+var_564], r14
0x180024453  mov     [rbp+4F0h+var_558], r14
0x180024457  mov     [rbp+4F0h+var_550], r14
0x18002445b  mov     [rbp+4F0h+var_548], r14d
0x18002445f  mov     [rbp+4F0h+var_540], r14
0x180024463  mov     [rbp+4F0h+var_538], r14w
0x180024468  mov     [rbp+4F0h+var_528], r14
0x18002446c  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@
0x180024473  mov     [rbp+4F0h+var_530], rax
0x180024477  xorps   xmm0, xmm0
0x18002447a  movups  [rsp+5F0h+var_588], xmm0
0x18002447f  movups  [rsp+5F0h+var_578], xmm0
0x180024484  mov     [rsp+5F0h+var_5B0], 80h
0x18002448c  mov     dword ptr [rsp+5F0h+var_5C0], r14d
0x180024491  mov     [rsp+5F0h+var_5C8], r15d
0x180024496  mov     byte ptr [rsp+5F0h+var_5D0], 1
0x18002449b  xor     r9d, r9d
0x18002449e  lea     r8, [rbp+4F0h+var_260]
0x1800244a5  lea     rdx, [rbp+4F0h+var_4E0]
0x1800244a9  lea     rcx, [rsp+5F0h+var_590]
0x1800244ae  call    ?Open@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@PEBG_N2W4_VSS_ICHANNEL_LOGGING@@KKK@Z
0x1800244b3  mov     [rbp+4F0h+var_4D8], eax
0x1800244b6  test    eax, eax
0x1800244b8  jns     short loc_18002452A
0x1800244ba  mov     [rbp+4F0h+var_470], r12
0x1800244c1  mov     [rbp+4F0h+var_468], r13
0x1800244c8  mov     [rbp+4F0h+var_460], rbx
0x1800244cf  mov     [rbp+4F0h+var_458], 2C8h
0x1800244d9  mov     [rbp+4F0h+var_454], r15d
0x1800244e0  mov     [rbp+4F0h+var_450], 0FFh
0x1800244ea  mov     [rbp+4F0h+var_3D0], 1000000h
0x1800244f4  xor     edx, edx; Val
0x1800244f6  lea     r8d, [rdx+78h]; Size
0x1800244fa  lea     rcx, [rbp+4F0h+var_448]; void *
0x180024501  call    memset_0
0x180024506  lea     r8, aWarningSnapsho_0
0x18002450d  lea     rdx, [rbp+4F0h+var_470]
0x180024514  lea     r9, [rbp+4F0h+var_260]
0x18002451b  lea     rcx, [rbp+4F0h+var_4E0]
0x18002451f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ
0x180024524  nop
0x180024525  jmp     loc_1800246A3
0x18002452a  mov     [rsp+5F0h+var_5C0], r14
0x18002452f  mov     byte ptr [rsp+5F0h+var_5C8], r14b
0x180024534  mov     dword ptr [rsp+5F0h+var_5D0], r14d
0x180024539  xor     r9d, r9d
0x18002453c  mov     r8d, 53019Ch
0x180024542  lea     rdx, [rbp+4F0h+var_4E0]
0x180024546  lea     rcx, [rsp+5F0h+var_590]
0x18002454b  call    ?Call@CVssIOCTLChannel@@QEAAJAEAVCVssFunctionTracer@@K_NW4_VSS_ICHANNEL_LOGGING@@1PEAX@Z
0x180024550  mov     [rbp+4F0h+var_4D8], eax
0x180024553  test    eax, eax
0x180024555  jns     short loc_1800245B6
0x180024557  mov     [rbp+4F0h+var_3C8], r12
0x18002455e  mov     [rbp+4F0h+var_3C0], r13
0x180024565  mov     [rbp+4F0h+var_3B8], rbx
0x18002456c  mov     [rbp+4F0h+var_3B0], 2D0h
0x180024576  mov     [rbp+4F0h+var_3AC], r15d
0x18002457d  mov     [rbp+4F0h+var_3A8], 0FFh
0x180024587  mov     [rbp+4F0h+var_328], 1000000h
0x180024591  xor     edx, edx; Val
0x180024593  lea     r8d, [rdx+78h]; Size
0x180024597  lea     rcx, [rbp+4F0h+var_3A0]; void *
0x18002459e  call    memset_0
0x1800245a3  lea     r8, aWarningSnapsho
0x1800245aa  lea     rdx, [rbp+4F0h+var_3C8]
0x1800245b1  jmp     loc_180024514
0x1800245b6  mov     dword ptr [rbp+4F0h+Buf1], r14d
0x1800245bd  lea     r8, [rbp+4F0h+Buf1]
0x1800245c4  lea     rdx, [rbp+4F0h+var_4E0]
0x1800245c8  lea     rcx, [rsp+5F0h+var_590]
0x1800245cd  call    ??$Unpack@K@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAKK_N@Z
0x1800245d2  mov     ebx, dword ptr [rbp+4F0h+Buf1]
0x1800245d8  cmp     ebx, 10h
0x1800245db  jnb     short loc_180024655
0x1800245dd  mov     [rbp+4F0h+var_320], r12
0x1800245e4  mov     [rbp+4F0h+var_318], r13
0x1800245eb  lea     rax, aSprdelec
0x1800245f2  mov     [rbp+4F0h+var_310], rax
0x1800245f9  mov     [rbp+4F0h+var_308], 2DBh
0x180024603  mov     [rbp+4F0h+var_304], r15d
0x18002460a  mov     [rbp+4F0h+var_300], 0FFh
0x180024614  mov     [rbp+4F0h+var_280], 1000000h
0x18002461e  xor     edx, edx; Val
0x180024620  lea     r8d, [rdx+78h]; Size
0x180024624  lea     rcx, [rbp+4F0h+var_2F8]; void *
0x18002462b  call    memset_0
0x180024630  mov     dword ptr [rsp+5F0h+var_5D0], ebx
0x180024634  mov     r9, [rbp+4F0h+var_528]
0x180024638  lea     r8, aWarningSmallSi
0x18002463f  lea     rdx, [rbp+4F0h+var_320]
0x180024646  lea     rcx, [rbp+4F0h+var_4E0]
0x18002464a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ
0x18002464f  mov     [rbp+4F0h+var_4D8], r14d
0x180024653  jmp     short loc_18002469C
0x180024655  xorps   xmm0, xmm0
0x180024658  movups  [rbp+4F0h+Buf1], xmm0
0x18002465f  lea     r8, [rbp+4F0h+Buf1]
0x180024666  lea     rdx, [rbp+4F0h+var_4E0]
0x18002466a  lea     rcx, [rsp+5F0h+var_590]
0x18002466f  call    ??$Unpack@U_GUID@@@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAU_GUID@@K_N@Z
0x180024674  mov     r8d, 10h; Size
0x18002467a  lea     rdx, VOLSNAP_APPINFO_GUID_CLIENT_ACCESSIBLE; Buf2
0x180024681  lea     rcx, [rbp+4F0h+Buf1]; Buf1
0x180024688  call    memcmp_0
0x18002468d  test    eax, eax
0x18002468f  setz    cl
0x180024692  lea     eax, [rdi+1]
0x180024695  test    cl, cl
0x180024697  cmovz   eax, edi
0x18002469a  mov     edi, eax
0x18002469c  lea     rbx, aSprdelec
0x1800246a3  lea     rcx, [rsp+5F0h+var_590]; this
0x1800246a8  call    ??1CVssIOCTLChannel@@QEAA@XZ
0x1800246ad  lea     rcx, [rsp+5F0h+var_5A0]
0x1800246b2  call    ?ResetAndGetRef@?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@QEAAAEAPEAGXZ
0x1800246b7  mov     r8, rax; unsigned __int16 **
0x1800246ba  lea     rdx, [rbp+4F0h+var_4E0]; struct CVssFunctionTracer *
0x1800246be  mov     rcx, rsi; this
0x1800246c1  call    ?UnpackZeroString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG@Z
0x1800246c6  test    rax, rax
0x1800246c9  jnz     loc_180024424
0x1800246cf  lea     rcx, [rsp+5F0h+var_5A0]
0x1800246d4  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ
0x1800246d9  nop
0x1800246da  lea     rcx, [rbp+4F0h+var_4E0]; this
0x1800246de  call    ??1CVssFunctionTracer@@QEAA@XZ
0x1800246e3  mov     eax, edi
0x1800246e5  mov     rcx, [rbp+4F0h+var_50]
0x1800246ec  xor     rcx, rsp; StackCookie
0x1800246ef  call    __security_check_cookie
0x1800246f4  add     rsp, 5B8h
0x1800246fb  pop     r15
0x1800246fd  pop     r14
0x1800246ff  pop     r13
0x180024701  pop     r12
0x180024703  pop     rdi
0x180024704  pop     rsi
0x180024705  pop     rbx
0x180024706  pop     rbp
0x180024707  retn
```
