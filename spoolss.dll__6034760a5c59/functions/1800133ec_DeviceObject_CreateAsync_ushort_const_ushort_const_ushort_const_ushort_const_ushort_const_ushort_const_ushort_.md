# DeviceObject::CreateAsync(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,void * *,DeviceObject * *)

- ea: `0x1800133ec`
- end: `0x180013716`
- name: `?CreateAsync@DeviceObject@@CAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5PEAPEAXPEAPEAV1@@Z`
- size: `810`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCOLESTR lpsz, const unsigned __int16 *, const unsigned __int16 *, const struct _SECURITY_DESCRIPTOR *, bool, const struct _DEVPROPERTY *, unsigned int, void (*)(struct DeviceObject *, int, void *), void *, void **, struct DeviceObject **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800132cc`

## callees

- `0x180004ecc`
- `0x180005320`
- `0x180011c98`
- `0x180012344`
- `0x1800130e8`
- `0x180013238`
- `0x1800133ec`
- `0x180013b40`
- `0x180013bd4`
- `0x180013c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800134fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800134fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013508`
- `CFGMGR32!SwDeviceCreate` at `0x18001367f`
- `CFGMGR32!SwDeviceCreate` at `0x18001367f`
- `ole32!IIDFromString` at `0x180013487`
- `ole32!IIDFromString` at `0x180013487`

## pseudocode

```c
__int64 __fastcall DeviceObject::CreateAsync(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCOLESTR lpsz,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const struct _SECURITY_DESCRIPTOR *a8,
        bool a9,
        const struct _DEVPROPERTY *a10,
        unsigned int a11,
        void (*a12)(struct DeviceObject *, int, void *),
        void *a13,
        void **a14,
        struct DeviceObject **a15)
{
  volatile signed __int32 *v15; // rbx
  int v17; // esi
  unsigned __int16 near **v18; // rdi
  int v19; // eax
  HANDLE EventW; // r12
  signed int LastError; // eax
  DeviceObject *v22; // rax
  __int64 *v23; // rax
  __int64 *v24; // r14
  volatile signed __int32 *v25; // rsi
  signed __int32 v26; // eax
  unsigned int v27; // edx
  struct DeviceObject *v28; // rax
  NCoreLibrary::TString *v29; // rcx
  const struct _DEVPROPERTY *v31; // [rsp+20h] [rbp-D1h]
  volatile signed __int32 *v32; // [rsp+40h] [rbp-B1h] BYREF
  unsigned __int16 near **v33; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v34; // [rsp+50h] [rbp-A1h] BYREF
  const struct _SECURITY_DESCRIPTOR *v35; // [rsp+58h] [rbp-99h]
  __int64 v36; // [rsp+60h] [rbp-91h] BYREF
  const struct _DEVPROPERTY *v37; // [rsp+68h] [rbp-89h]
  struct DeviceObject **v38; // [rsp+70h] [rbp-81h]
  _QWORD v39[10]; // [rsp+80h] [rbp-71h] BYREF
  GUID iid; // [rsp+D0h] [rbp-21h] BYREF

  v15 = 0;
  v35 = a8;
  v38 = a15;
  v37 = a10;
  if ( !a2 || !*a2 || !a15 || (v17 = 0, a11) && !a10 )
    v17 = -2147024809;
  iid = 0;
  if ( v17 >= 0 && lpsz && *lpsz )
    v17 = IIDFromString(lpsz, &iid);
  v18 = &NCoreLibrary::TString::gszNullState;
  v33 = &NCoreLibrary::TString::gszNullState;
  if ( v17 >= 0 )
  {
    v19 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v33, L"SWD\\PRINTENUM\\%ws", a2, a4);
    v18 = v33;
    v17 = v19;
  }
  v33 = 0;
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v33);
  v33 = 0;
  v34 = 0;
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v34);
  v34 = 0;
  EventW = 0;
  if ( v17 >= 0 )
  {
    if ( a14 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( !EventW )
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  v32 = 0;
  NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(&v32);
  v32 = 0;
  if ( v17 >= 0 )
  {
    v22 = (DeviceObject *)operator new(0x68u);
    if ( v22 )
      v15 = (volatile signed __int32 *)DeviceObject::DeviceObject(v22);
    NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(&v32);
    v32 = v15;
    if ( !v15 )
      v17 = -2147024882;
  }
  v36 = 0;
  if ( v17 >= 0 )
  {
    v39[1] = a2;
    v39[0] = 72;
    v39[2] = L"PRINTENUM\\PrinterConnection";
    v39[5] = 3;
    v39[3] = L"GenPrinterConnection";
    v39[4] = (unsigned __int64)&iid & -(__int64)(lpsz != 0);
    v39[7] = L"Spooler Internal";
    v39[8] = v35;
    v39[6] = 0;
    v23 = (__int64 *)operator new(0x20u);
    v24 = v23;
    if ( v23 )
    {
      v23[1] = 0;
      v23[2] = 0;
      v23[3] = 0;
      *v23 = 0;
      if ( v15 )
      {
        v25 = v15;
        do
          v26 = *((_DWORD *)v15 + 2);
        while ( v26 != 0x7FFFFFFF && v26 != _InterlockedCompareExchange(v15 + 2, v26 + 1, v26) );
      }
      else
      {
        v25 = 0;
      }
      NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(v24);
      *v24 = (unsigned __int64)v25 & -(__int64)(v25 != 0);
      v31 = v37;
      v24[1] = (__int64)EventW;
      v24[2] = 0;
      v24[3] = 0;
      v17 = SwDeviceCreate(
              L"PRINTENUM",
              L"SWD\\PRINTENUM\\PrintQueues",
              v39,
              a11,
              v31,
              DeviceObject::DeviceCreationCallback,
              v24,
              &v36,
              v32);
      if ( v17 >= 0 )
      {
        if ( a14 )
          *a14 = EventW;
        else
          DeviceObject::OnReady((DeviceObject *)v15, 0);
        v28 = 0;
        if ( v15 )
        {
          v28 = (struct DeviceObject *)v15;
          v32 = 0;
        }
        *v38 = v28;
      }
      else if ( v24 )
      {
        DeviceCreationCallbackContext::`scalar deleting destructor'((DeviceCreationCallbackContext *)v24, v27);
      }
    }
    else
    {
      v17 = -2147024882;
    }
  }
  NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(&v32);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v34);
  NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v33);
  NCoreLibrary::TString::vFree(v29, v18);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800133ec  push    rbp
0x1800133ee  push    rbx
0x1800133ef  push    rsi
0x1800133f0  push    rdi
0x1800133f1  push    r12
0x1800133f3  push    r13
0x1800133f5  push    r14
0x1800133f7  push    r15
0x1800133f9  lea     rbp, [rsp-7]
0x1800133fe  sub     rsp, 0F8h
0x180013405  mov     rax, cs:__security_cookie
0x18001340c  xor     rax, rsp
0x18001340f  mov     [rbp+3Fh+var_50], rax
0x180013413  mov     rax, [rbp+3Fh+arg_38]
0x18001341a  xor     ebx, ebx
0x18001341c  mov     rcx, [rbp+3Fh+arg_48]
0x180013423  mov     r15, rdx
0x180013426  mov     r14, [rbp+3Fh+lpsz]
0x18001342a  mov     r13, [rbp+3Fh+arg_68]
0x180013431  mov     [rsp+130h+var_D8], rax
0x180013436  mov     rax, [rbp+3Fh+arg_70]
0x18001343d  mov     [rsp+130h+var_C0], rax
0x180013442  mov     [rsp+130h+var_C8], rcx
0x180013447  test    rdx, rdx
0x18001344a  jz      short loc_180013465
0x18001344c  cmp     [rdx], bx
0x18001344f  jz      short loc_180013465
0x180013451  test    rax, rax
0x180013454  jz      short loc_180013465
0x180013456  mov     esi, ebx
0x180013458  cmp     [rbp+3Fh+arg_50], ebx
0x18001345e  jz      short loc_18001346A
0x180013460  test    rcx, rcx
0x180013463  jnz     short loc_18001346A
0x180013465  mov     esi, 80070057h
0x18001346a  xorps   xmm0, xmm0
0x18001346d  movups  xmmword ptr [rbp+3Fh+iid.Data1], xmm0
0x180013471  test    esi, esi
0x180013473  js      short loc_18001348F
0x180013475  test    r14, r14
0x180013478  jz      short loc_18001348F
0x18001347a  cmp     [r14], bx
0x18001347e  jz      short loc_18001348F
0x180013480  lea     rdx, [rbp+3Fh+iid]; lpiid
0x180013484  mov     rcx, r14; lpsz
0x180013487  call    cs:__imp_IIDFromString
0x18001348d  mov     esi, eax
0x18001348f  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180013496  mov     [rsp+130h+var_E8], rdi
0x18001349b  test    esi, esi
0x18001349d  js      short loc_1800134BA
0x18001349f  mov     r8, r15
0x1800134a2  lea     rdx, aSwdPrintenumWs; "SWD\\PRINTENUM\\%ws"
0x1800134a9  lea     rcx, [rsp+130h+var_E8]; this
0x1800134ae  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x1800134b3  mov     rdi, [rsp+130h+var_E8]
0x1800134b8  mov     esi, eax
0x1800134ba  lea     rcx, [rsp+130h+var_E8]
0x1800134bf  mov     [rsp+130h+var_E8], rbx
0x1800134c4  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1800134c9  lea     rcx, [rsp+130h+var_E0]
0x1800134ce  mov     [rsp+130h+var_E8], rbx
0x1800134d3  mov     [rsp+130h+var_E0], rbx
0x1800134d8  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1800134dd  mov     [rsp+130h+var_E0], rbx
0x1800134e2  mov     r12, rbx
0x1800134e5  test    esi, esi
0x1800134e7  js      short loc_18001351D
0x1800134e9  test    r13, r13
0x1800134ec  jz      short loc_18001351D
0x1800134ee  xor     r9d, r9d; lpName
0x1800134f1  xor     r8d, r8d; bInitialState
0x1800134f4  xor     ecx, ecx; lpEventAttributes
0x1800134f6  lea     edx, [r9+1]; bManualReset
0x1800134fa  call    cs:__imp_CreateEventW
0x180013500  mov     r12, rax
0x180013503  test    rax, rax
0x180013506  jnz     short loc_18001351D
0x180013508  call    cs:__imp_GetLastError
0x18001350e  mov     esi, eax
0x180013510  test    eax, eax
0x180013512  jle     short loc_18001351D
0x180013514  movzx   esi, ax
0x180013517  or      esi, 80070000h
0x18001351d  lea     rcx, [rsp+130h+var_F0]
0x180013522  mov     [rsp+130h+var_F0], rbx
0x180013527  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x18001352c  mov     [rsp+130h+var_F0], rbx
0x180013531  test    esi, esi
0x180013533  js      short loc_180013569
0x180013535  mov     ecx, 68h ; 'h'; Size
0x18001353a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001353f  test    rax, rax
0x180013542  jz      short loc_18001354F
0x180013544  mov     rcx, rax; this
0x180013547  call    ??0DeviceObject@@QEAA@XZ; DeviceObject::DeviceObject(void)
0x18001354c  mov     rbx, rax
0x18001354f  lea     rcx, [rsp+130h+var_F0]
0x180013554  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180013559  test    rbx, rbx
0x18001355c  mov     [rsp+130h+var_F0], rbx
0x180013561  mov     eax, 8007000Eh
0x180013566  cmovz   esi, eax
0x180013569  mov     [rsp+130h+var_D0], 0
0x180013572  test    esi, esi
0x180013574  js      loc_1800136CE
0x18001357a  lea     rcx, [rbp+3Fh+iid]
0x18001357e  mov     [rbp+3Fh+var_A8], r15
0x180013582  lea     rax, aPrintenumPrint; "PRINTENUM\\PrinterConnection"
0x180013589  mov     [rbp+3Fh+var_B0], 48h ; 'H'
0x180013591  mov     [rbp+3Fh+var_A0], rax
0x180013595  neg     r14
0x180013598  lea     rax, aGenprinterconn; "GenPrinterConnection"
0x18001359f  mov     [rbp+3Fh+var_88], 3
0x1800135a7  mov     [rbp+3Fh+var_98], rax
0x1800135ab  sbb     rax, rax
0x1800135ae  and     rax, rcx
0x1800135b1  xor     r15d, r15d
0x1800135b4  mov     [rbp+3Fh+var_90], rax
0x1800135b8  lea     rax, aSpoolerInterna; "Spooler Internal"
0x1800135bf  mov     [rbp+3Fh+var_78], rax
0x1800135c3  mov     rax, [rsp+130h+var_D8]
0x1800135c8  lea     ecx, [r15+20h]; Size
0x1800135cc  mov     [rbp+3Fh+var_70], rax
0x1800135d0  mov     [rbp+3Fh+var_80], r15
0x1800135d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800135d9  mov     r14, rax
0x1800135dc  test    rax, rax
0x1800135df  jz      loc_1800136C9
0x1800135e5  mov     [rax+8], r15
0x1800135e9  mov     [rax+10h], r15
0x1800135ed  mov     [rax+18h], r15
0x1800135f1  mov     [rax], r15
0x1800135f4  test    rbx, rbx
0x1800135f7  jnz     short loc_1800135FE
0x1800135f9  mov     esi, r15d
0x1800135fc  jmp     short loc_18001361C
0x1800135fe  mov     rsi, rbx
0x180013601  test    rbx, rbx
0x180013604  jz      short loc_18001361C
0x180013606  mov     edx, 7FFFFFFFh
0x18001360b  mov     eax, [rbx+8]
0x18001360e  cmp     eax, edx
0x180013610  jz      short loc_18001361C
0x180013612  lea     ecx, [rax+1]
0x180013615  lock cmpxchg [rbx+8], ecx
0x18001361a  jnz     short loc_18001360B
0x18001361c  mov     rcx, r14
0x18001361f  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180013624  mov     r9d, [rbp+3Fh+arg_50]
0x18001362b  lea     r8, [rbp+3Fh+var_B0]
0x18001362f  test    rsi, rsi
0x180013632  lea     rdx, aSwdPrintenumPr; "SWD\\PRINTENUM\\PrintQueues"
0x180013639  setnz   al
0x18001363c  neg     al
0x18001363e  lea     rax, [rsp+130h+var_D0]
0x180013643  mov     [rsp+130h+var_F8], rax
0x180013648  sbb     rcx, rcx
0x18001364b  and     rcx, rsi
0x18001364e  mov     [rsp+130h+var_100], r14
0x180013653  mov     [r14], rcx
0x180013656  lea     rax, ?DeviceCreationCallback@DeviceObject@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; DeviceObject::DeviceCreationCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18001365d  mov     [rsp+130h+var_108], rax
0x180013662  lea     rcx, aPrintenum; "PRINTENUM"
0x180013669  mov     rax, [rsp+130h+var_C8]
0x18001366e  mov     [rsp+130h+var_110], rax
0x180013673  mov     [r14+8], r12
0x180013677  mov     [r14+10h], r15
0x18001367b  mov     [r14+18h], r15
0x18001367f  call    cs:__imp_SwDeviceCreate
0x180013685  mov     esi, eax
0x180013687  test    eax, eax
0x180013689  jns     short loc_18001369A
0x18001368b  test    r14, r14
0x18001368e  jz      short loc_1800136CE
0x180013690  mov     rcx, r14; this
0x180013693  call    ??_GDeviceCreationCallbackContext@@QEAAPEAXI@Z; DeviceCreationCallbackContext::`scalar deleting destructor'(uint)
0x180013698  jmp     short loc_1800136CE
0x18001369a  test    r13, r13
0x18001369d  jz      short loc_1800136A5
0x18001369f  mov     [r13+0], r12
0x1800136a3  jmp     short loc_1800136AF
0x1800136a5  xor     edx, edx; int
0x1800136a7  mov     rcx, rbx; this
0x1800136aa  call    ?OnReady@DeviceObject@@AEAAXJ@Z; DeviceObject::OnReady(long)
0x1800136af  mov     rax, r15
0x1800136b2  test    rbx, rbx
0x1800136b5  jz      short loc_1800136BF
0x1800136b7  mov     rax, rbx
0x1800136ba  mov     [rsp+130h+var_F0], r15
0x1800136bf  mov     rcx, [rsp+130h+var_C0]
0x1800136c4  mov     [rcx], rax
0x1800136c7  jmp     short loc_1800136CE
0x1800136c9  mov     esi, 8007000Eh
0x1800136ce  lea     rcx, [rsp+130h+var_F0]
0x1800136d3  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x1800136d8  lea     rcx, [rsp+130h+var_E0]
0x1800136dd  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1800136e2  lea     rcx, [rsp+130h+var_E8]
0x1800136e7  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1800136ec  mov     rdx, rdi; void *
0x1800136ef  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1800136f4  mov     eax, esi
0x1800136f6  mov     rcx, [rbp+3Fh+var_50]
0x1800136fa  xor     rcx, rsp; StackCookie
0x1800136fd  call    __security_check_cookie
0x180013702  add     rsp, 0F8h
0x180013709  pop     r15
0x18001370b  pop     r14
0x18001370d  pop     r13
0x18001370f  pop     r12
0x180013711  pop     rdi
0x180013712  pop     rsi
0x180013713  pop     rbx
0x180013714  pop     rbp
0x180013715  retn
```
