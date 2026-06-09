# DeviceObject::CreateAsync(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SECURITY_DESCRIPTOR const *,bool,_DEVPROPERTY const *,ulong,void (*)(DeviceObject *,long,void *),void *,void * *,DeviceObject * *)

- ea: `0x180014b7c`
- end: `0x180014ebf`
- name: `?CreateAsync@DeviceObject@@CAJPEBG000000PEBU_SECURITY_DESCRIPTOR@@_NPEBU_DEVPROPERTY@@KP6AXPEAV1@JPEAX@Z5PEAPEAXPEAPEAV1@@Z`
- size: `835`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCOLESTR lpsz, const unsigned __int16 *, const unsigned __int16 *, const struct _SECURITY_DESCRIPTOR *, bool, const struct _DEVPROPERTY *, unsigned int, void (*)(struct DeviceObject *, int, void *), void *, void **, struct DeviceObject **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180014a50`

## callees

- `0x18000522c`
- `0x180005680`
- `0x1800133bc`
- `0x180013acc`
- `0x180014848`
- `0x1800149ac`
- `0x180014b7c`
- `0x1800152e8`
- `0x180015398`
- `0x1800153f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014c90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ca4`
- `CFGMGR32!SwDeviceCreate` at `0x180014e21`
- `CFGMGR32!SwDeviceCreate` at `0x180014e21`
- `ole32!IIDFromString` at `0x180014c17`
- `ole32!IIDFromString` at `0x180014c17`

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
0x180014b7c  push    rbp
0x180014b7e  push    rbx
0x180014b7f  push    rsi
0x180014b80  push    rdi
0x180014b81  push    r12
0x180014b83  push    r13
0x180014b85  push    r14
0x180014b87  push    r15
0x180014b89  lea     rbp, [rsp-7]
0x180014b8e  sub     rsp, 0F8h
0x180014b95  mov     rax, cs:__security_cookie
0x180014b9c  xor     rax, rsp
0x180014b9f  mov     [rbp+3Fh+var_50], rax
0x180014ba3  mov     rax, [rbp+3Fh+arg_38]
0x180014baa  xor     ebx, ebx
0x180014bac  mov     rcx, [rbp+3Fh+arg_48]
0x180014bb3  mov     r15, rdx
0x180014bb6  mov     r14, [rbp+3Fh+lpsz]
0x180014bba  mov     r13, [rbp+3Fh+arg_68]
0x180014bc1  mov     [rsp+130h+var_D8], rax
0x180014bc6  mov     rax, [rbp+3Fh+arg_70]
0x180014bcd  mov     [rsp+130h+var_C0], rax
0x180014bd2  mov     [rsp+130h+var_C8], rcx
0x180014bd7  test    rdx, rdx
0x180014bda  jz      short loc_180014BF5
0x180014bdc  cmp     [rdx], bx
0x180014bdf  jz      short loc_180014BF5
0x180014be1  test    rax, rax
0x180014be4  jz      short loc_180014BF5
0x180014be6  mov     esi, ebx
0x180014be8  cmp     [rbp+3Fh+arg_50], ebx
0x180014bee  jz      short loc_180014BFA
0x180014bf0  test    rcx, rcx
0x180014bf3  jnz     short loc_180014BFA
0x180014bf5  mov     esi, 80070057h
0x180014bfa  xorps   xmm0, xmm0
0x180014bfd  movups  xmmword ptr [rbp+3Fh+iid.Data1], xmm0
0x180014c01  test    esi, esi
0x180014c03  js      short loc_180014C25
0x180014c05  test    r14, r14
0x180014c08  jz      short loc_180014C25
0x180014c0a  cmp     [r14], bx
0x180014c0e  jz      short loc_180014C25
0x180014c10  lea     rdx, [rbp+3Fh+iid]; lpiid
0x180014c14  mov     rcx, r14; lpsz
0x180014c17  call    cs:__imp_IIDFromString
0x180014c1e  nop     dword ptr [rax+rax+00h]
0x180014c23  mov     esi, eax
0x180014c25  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180014c2c  mov     [rsp+130h+var_E8], rdi
0x180014c31  test    esi, esi
0x180014c33  js      short loc_180014C50
0x180014c35  mov     r8, r15
0x180014c38  lea     rdx, aSwdPrintenumWs; "SWD\\PRINTENUM\\%ws"
0x180014c3f  lea     rcx, [rsp+130h+var_E8]; this
0x180014c44  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180014c49  mov     rdi, [rsp+130h+var_E8]
0x180014c4e  mov     esi, eax
0x180014c50  lea     rcx, [rsp+130h+var_E8]
0x180014c55  mov     [rsp+130h+var_E8], rbx
0x180014c5a  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014c5f  lea     rcx, [rsp+130h+var_E0]
0x180014c64  mov     [rsp+130h+var_E8], rbx
0x180014c69  mov     [rsp+130h+var_E0], rbx
0x180014c6e  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014c73  mov     [rsp+130h+var_E0], rbx
0x180014c78  mov     r12, rbx
0x180014c7b  test    esi, esi
0x180014c7d  js      short loc_180014CBF
0x180014c7f  test    r13, r13
0x180014c82  jz      short loc_180014CBF
0x180014c84  xor     r9d, r9d; lpName
0x180014c87  xor     r8d, r8d; bInitialState
0x180014c8a  xor     ecx, ecx; lpEventAttributes
0x180014c8c  lea     edx, [r9+1]; bManualReset
0x180014c90  call    cs:__imp_CreateEventW
0x180014c97  nop     dword ptr [rax+rax+00h]
0x180014c9c  mov     r12, rax
0x180014c9f  test    rax, rax
0x180014ca2  jnz     short loc_180014CBF
0x180014ca4  call    cs:__imp_GetLastError
0x180014cab  nop     dword ptr [rax+rax+00h]
0x180014cb0  mov     esi, eax
0x180014cb2  test    eax, eax
0x180014cb4  jle     short loc_180014CBF
0x180014cb6  movzx   esi, ax
0x180014cb9  or      esi, 80070000h
0x180014cbf  lea     rcx, [rsp+130h+var_F0]
0x180014cc4  mov     [rsp+130h+var_F0], rbx
0x180014cc9  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180014cce  mov     [rsp+130h+var_F0], rbx
0x180014cd3  test    esi, esi
0x180014cd5  js      short loc_180014D0B
0x180014cd7  mov     ecx, 68h ; 'h'; Size
0x180014cdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014ce1  test    rax, rax
0x180014ce4  jz      short loc_180014CF1
0x180014ce6  mov     rcx, rax; this
0x180014ce9  call    ??0DeviceObject@@QEAA@XZ; DeviceObject::DeviceObject(void)
0x180014cee  mov     rbx, rax
0x180014cf1  lea     rcx, [rsp+130h+var_F0]
0x180014cf6  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180014cfb  test    rbx, rbx
0x180014cfe  mov     [rsp+130h+var_F0], rbx
0x180014d03  mov     eax, 8007000Eh
0x180014d08  cmovz   esi, eax
0x180014d0b  mov     [rsp+130h+var_D0], 0
0x180014d14  test    esi, esi
0x180014d16  js      loc_180014E76
0x180014d1c  lea     rcx, [rbp+3Fh+iid]
0x180014d20  mov     [rbp+3Fh+var_A8], r15
0x180014d24  lea     rax, aPrintenumPrint; "PRINTENUM\\PrinterConnection"
0x180014d2b  mov     [rbp+3Fh+var_B0], 48h ; 'H'
0x180014d33  mov     [rbp+3Fh+var_A0], rax
0x180014d37  neg     r14
0x180014d3a  lea     rax, aGenprinterconn; "GenPrinterConnection"
0x180014d41  mov     [rbp+3Fh+var_88], 3
0x180014d49  mov     [rbp+3Fh+var_98], rax
0x180014d4d  sbb     rax, rax
0x180014d50  and     rax, rcx
0x180014d53  xor     r15d, r15d
0x180014d56  mov     [rbp+3Fh+var_90], rax
0x180014d5a  lea     rax, aSpoolerInterna; "Spooler Internal"
0x180014d61  mov     [rbp+3Fh+var_78], rax
0x180014d65  mov     rax, [rsp+130h+var_D8]
0x180014d6a  lea     ecx, [r15+20h]; Size
0x180014d6e  mov     [rbp+3Fh+var_70], rax
0x180014d72  mov     [rbp+3Fh+var_80], r15
0x180014d76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d7b  mov     r14, rax
0x180014d7e  test    rax, rax
0x180014d81  jz      loc_180014E71
0x180014d87  mov     [rax+8], r15
0x180014d8b  mov     [rax+10h], r15
0x180014d8f  mov     [rax+18h], r15
0x180014d93  mov     [rax], r15
0x180014d96  test    rbx, rbx
0x180014d99  jnz     short loc_180014DA0
0x180014d9b  mov     esi, r15d
0x180014d9e  jmp     short loc_180014DBE
0x180014da0  mov     rsi, rbx
0x180014da3  test    rbx, rbx
0x180014da6  jz      short loc_180014DBE
0x180014da8  mov     edx, 7FFFFFFFh
0x180014dad  mov     eax, [rbx+8]
0x180014db0  cmp     eax, edx
0x180014db2  jz      short loc_180014DBE
0x180014db4  lea     ecx, [rax+1]
0x180014db7  lock cmpxchg [rbx+8], ecx
0x180014dbc  jnz     short loc_180014DAD
0x180014dbe  mov     rcx, r14
0x180014dc1  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180014dc6  mov     r9d, [rbp+3Fh+arg_50]
0x180014dcd  lea     r8, [rbp+3Fh+var_B0]
0x180014dd1  test    rsi, rsi
0x180014dd4  lea     rdx, aSwdPrintenumPr; "SWD\\PRINTENUM\\PrintQueues"
0x180014ddb  setnz   al
0x180014dde  neg     al
0x180014de0  lea     rax, [rsp+130h+var_D0]
0x180014de5  mov     [rsp+130h+var_F8], rax
0x180014dea  sbb     rcx, rcx
0x180014ded  and     rcx, rsi
0x180014df0  mov     [rsp+130h+var_100], r14
0x180014df5  mov     [r14], rcx
0x180014df8  lea     rax, ?DeviceCreationCallback@DeviceObject@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; DeviceObject::DeviceCreationCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x180014dff  mov     [rsp+130h+var_108], rax
0x180014e04  lea     rcx, aPrintenum; "PRINTENUM"
0x180014e0b  mov     rax, [rsp+130h+var_C8]
0x180014e10  mov     [rsp+130h+var_110], rax
0x180014e15  mov     [r14+8], r12
0x180014e19  mov     [r14+10h], r15
0x180014e1d  mov     [r14+18h], r15
0x180014e21  call    cs:__imp_SwDeviceCreate
0x180014e28  nop     dword ptr [rax+rax+00h]
0x180014e2d  mov     esi, eax
0x180014e2f  test    eax, eax
0x180014e31  jns     short loc_180014E42
0x180014e33  test    r14, r14
0x180014e36  jz      short loc_180014E76
0x180014e38  mov     rcx, r14; this
0x180014e3b  call    ??_GDeviceCreationCallbackContext@@QEAAPEAXI@Z; DeviceCreationCallbackContext::`scalar deleting destructor'(uint)
0x180014e40  jmp     short loc_180014E76
0x180014e42  test    r13, r13
0x180014e45  jz      short loc_180014E4D
0x180014e47  mov     [r13+0], r12
0x180014e4b  jmp     short loc_180014E57
0x180014e4d  xor     edx, edx; int
0x180014e4f  mov     rcx, rbx; this
0x180014e52  call    ?OnReady@DeviceObject@@AEAAXJ@Z; DeviceObject::OnReady(long)
0x180014e57  mov     rax, r15
0x180014e5a  test    rbx, rbx
0x180014e5d  jz      short loc_180014E67
0x180014e5f  mov     rax, rbx
0x180014e62  mov     [rsp+130h+var_F0], r15
0x180014e67  mov     rcx, [rsp+130h+var_C0]
0x180014e6c  mov     [rcx], rax
0x180014e6f  jmp     short loc_180014E76
0x180014e71  mov     esi, 8007000Eh
0x180014e76  lea     rcx, [rsp+130h+var_F0]
0x180014e7b  call    ?Reset@?$TGenericSP@VDeviceObject@@V?$TAutoPtrCOM@VDeviceObject@@@NCoreLibrary@@PEAV1@$0A@PEBV1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<DeviceObject,NCoreLibrary::TAutoPtrCOM<DeviceObject>,DeviceObject *,0,DeviceObject const *>::Reset(void)
0x180014e80  lea     rcx, [rsp+130h+var_E0]
0x180014e85  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014e8a  lea     rcx, [rsp+130h+var_E8]
0x180014e8f  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x180014e94  mov     rdx, rdi; void *
0x180014e97  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180014e9c  mov     eax, esi
0x180014e9e  mov     rcx, [rbp+3Fh+var_50]
0x180014ea2  xor     rcx, rsp; StackCookie
0x180014ea5  call    __security_check_cookie
0x180014eaa  add     rsp, 0F8h
0x180014eb1  pop     r15
0x180014eb3  pop     r14
0x180014eb5  pop     r13
0x180014eb7  pop     r12
0x180014eb9  pop     rdi
0x180014eba  pop     rsi
0x180014ebb  pop     rbx
0x180014ebc  pop     rbp
0x180014ebd  retn
```
