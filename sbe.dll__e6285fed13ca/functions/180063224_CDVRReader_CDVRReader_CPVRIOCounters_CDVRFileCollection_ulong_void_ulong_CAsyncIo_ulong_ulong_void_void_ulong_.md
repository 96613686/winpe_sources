# CDVRReader::CDVRReader(CPVRIOCounters *,CDVRFileCollection *,ulong,void * *,ulong,CAsyncIo *,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,int,long *)

- ea: `0x180063224`
- end: `0x180063522`
- name: `??0CDVRReader@@QEAA@PEAVCPVRIOCounters@@PEAVCDVRFileCollection@@KPEAPEAXKPEAVCAsyncIo@@KKP6AXPEAXK_J5@Z4PEAUHKEY__@@7HPEAJ@Z`
- size: `766`
- prototype: `CDVRReader *__usercall@<rax>(CDVRReader *__hidden this@<rcx>, struct CPVRIOCounters *@<rdx>, struct CDVRFileCollection *@<r8>, unsigned int@<r9d>, void **, unsigned int, struct CAsyncIo *, unsigned int, unsigned int, void (*)(void *, unsigned int, __int64, __int64), void *, HKEY, HKEY, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18006ad70`

## callees

- `0x180029a50`
- `0x180063224`
- `0x180064dd8`
- `0x180068244`
- `0x1800754a4`
- `0x18007c3a8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18006349d`
- `KERNEL32!CreateEventW` at `0x18006349d`
- `KERNEL32!InitializeCriticalSection` at `0x180063413`
- `KERNEL32!InitializeCriticalSection` at `0x180063413`
- `KERNEL32!GetLastError` at `0x1800634af`
- `KERNEL32!GetLastError` at `0x1800634af`

## string_xrefs

- `0x180063441`: `CloseReaderFilesAfterConsecutiveReads`

## pseudocode

```c
CDVRReader *__fastcall CDVRReader::CDVRReader(
        CDVRReader *this,
        struct CPVRIOCounters *a2,
        struct CDVRFileCollection *a3,
        unsigned int a4,
        void **a5,
        unsigned int a6,
        struct CAsyncIo *a7,
        unsigned int a8,
        unsigned int a9,
        void (*a10)(void *, unsigned int, __int64, __int64),
        void *a11,
        HKEY a12,
        HKEY a13,
        int a14,
        int *a15)
{
  __int64 v19; // rax
  unsigned int RegDWORD; // eax
  signed int v21; // ecx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v24; // cc
  void (*v25)(void *, unsigned int, __int64, __int64); // r8
  int v26; // eax

  *(_QWORD *)this = &CDVRReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 1) = &CDVRReader::`vftable'{for `IDVRSourceAdviseSink'};
  *((_QWORD *)this + 2) = &CDVRReader::`vftable'{for `IDVRIORecordingAttributes'};
  *((_QWORD *)this + 3) = &CDVRReader::`vftable'{for `IDVRReaderNotify'};
  *((_QWORD *)this + 4) = &CDVRReader::`vftable'{for `IDVRCrossBarNotify'};
  SBECoreUtil::TCDenseVector<unsigned long>::TCDenseVector<unsigned long>((char *)this + 40);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 10000LL * a6;
  *((_QWORD *)this + 19) = a12;
  *((_QWORD *)this + 20) = a13;
  *((_QWORD *)this + 21) = a7;
  *((_DWORD *)this + 44) = a8;
  *((_DWORD *)this + 45) = a9;
  *((_QWORD *)this + 23) = a10;
  *((_QWORD *)this + 24) = a11;
  *(_OWORD *)((char *)this + 200) = 0;
  *(_OWORD *)((char *)this + 216) = 0;
  *(_OWORD *)((char *)this + 232) = 0;
  *((_DWORD *)this + 50) = -17826065;
  *((_DWORD *)this + 62) = 1;
  *((_QWORD *)this + 32) = a2;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_DWORD *)this + 70) = a14;
  *((_DWORD *)this + 72) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 41) = -1;
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 96) = 1;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_DWORD *)this + 102) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = a3;
  *((_DWORD *)this + 108) = 0;
  *((_DWORD *)this + 109) = -1;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_DWORD *)this + 120) = 0;
  *((_QWORD *)this + 61) = 0;
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 32) + 24LL), 1u);
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 53) + 144LL), 1u);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  *((_QWORD *)this + 38) = (char *)this + 296;
  *((_QWORD *)this + 37) = (char *)this + 296;
  v19 = *((_QWORD *)this + 21);
  if ( v19 )
    _InterlockedAdd((volatile signed __int32 *)(v19 + 184), 1u);
  RegDWORD = GetRegDWORD(*((HKEY *)this + 20), L"CloseReaderFilesAfterConsecutiveReads", 0x19u);
  *((_DWORD *)this + 71) = RegDWORD;
  if ( !RegDWORD )
    *((_DWORD *)this + 71) = 1;
  *((_QWORD *)this + 40) = 100000000;
  v21 = CDVRFileCollection::CClientInfo::SetSids((CDVRReader *)((char *)this + 432), a4, a5, 1);
  if ( v21 >= 0 )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 61) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v21 = LastError;
      v24 = LastError <= 0;
      goto LABEL_8;
    }
    LastError = COutstandingOps::CreateInstance((struct COutstandingOps **)this + 34);
    v21 = LastError;
    v24 = LastError <= 0;
    if ( LastError )
    {
LABEL_8:
      if ( !v24 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_13;
    }
    v26 = CDVRFileCollection::RegisterReader(
            *((CDVRFileCollection **)this + 53),
            (CDVRReader *)((char *)this + 432),
            v25,
            this);
    v21 = 0;
    if ( v26 < 0 )
      v21 = v26;
  }
LABEL_13:
  if ( a15 )
    *a15 = v21;
  --*((_DWORD *)this + 96);
  return this;
}

```

## disassembly

```asm
0x180063224  mov     [rsp+arg_8], rbx
0x180063229  mov     [rsp+arg_10], rsi
0x18006322e  mov     [rsp+arg_0], rcx
0x180063233  push    rdi
0x180063234  push    r12
0x180063236  push    r13
0x180063238  push    r14
0x18006323a  push    r15
0x18006323c  sub     rsp, 30h
0x180063240  mov     r15d, r9d
0x180063243  mov     rdi, r8
0x180063246  mov     rbx, rdx
0x180063249  mov     rsi, rcx
0x18006324c  lea     rax, ??_7CDVRReader@@6BIDVRReader@@@; const CDVRReader::`vftable'{for `IDVRReader'}
0x180063253  mov     [rcx], rax
0x180063256  lea     rax, ??_7CDVRReader@@6BIDVRSourceAdviseSink@@@; const CDVRReader::`vftable'{for `IDVRSourceAdviseSink'}
0x18006325d  mov     [rcx+8], rax
0x180063261  lea     rax, ??_7CDVRReader@@6BIDVRIORecordingAttributes@@@; const CDVRReader::`vftable'{for `IDVRIORecordingAttributes'}
0x180063268  mov     [rcx+10h], rax
0x18006326c  lea     rax, ??_7CDVRReader@@6BIDVRReaderNotify@@@; const CDVRReader::`vftable'{for `IDVRReaderNotify'}
0x180063273  mov     [rcx+18h], rax
0x180063277  lea     rax, ??_7CDVRReader@@6BIDVRCrossBarNotify@@@; const CDVRReader::`vftable'{for `IDVRCrossBarNotify'}
0x18006327e  mov     [rcx+20h], rax
0x180063282  add     rcx, 28h ; '('
0x180063286  call    ??0?$TCDenseVector@K@SBECoreUtil@@QEAA@PEAXKK@Z; SBECoreUtil::TCDenseVector<ulong>::TCDenseVector<ulong>(void *,ulong,ulong)
0x18006328b  xor     r12d, r12d
0x18006328e  mov     [rsi+80h], r12
0x180063295  mov     [rsi+88h], r12
0x18006329c  mov     eax, [rsp+58h+arg_28]
0x1800632a3  imul    rcx, rax, 2710h
0x1800632aa  mov     [rsi+90h], rcx
0x1800632b1  mov     rax, [rsp+58h+arg_58]
0x1800632b9  mov     [rsi+98h], rax
0x1800632c0  mov     rax, [rsp+58h+arg_60]
0x1800632c8  mov     [rsi+0A0h], rax
0x1800632cf  mov     rax, [rsp+58h+arg_30]
0x1800632d7  mov     [rsi+0A8h], rax
0x1800632de  mov     eax, [rsp+58h+arg_38]
0x1800632e5  mov     [rsi+0B0h], eax
0x1800632eb  mov     eax, [rsp+58h+arg_40]
0x1800632f2  mov     [rsi+0B4h], eax
0x1800632f8  mov     rax, [rsp+58h+arg_48]
0x180063300  mov     [rsi+0B8h], rax
0x180063307  mov     rax, [rsp+58h+arg_50]
0x18006330f  mov     [rsi+0C0h], rax
0x180063316  xorps   xmm0, xmm0
0x180063319  movups  xmmword ptr [rsi+0C8h], xmm0
0x180063320  movups  xmmword ptr [rsi+0D8h], xmm0
0x180063327  movups  xmmword ptr [rsi+0E8h], xmm0
0x18006332e  mov     dword ptr [rsi+0C8h], 0FEEFFEEFh
0x180063338  lea     r13d, [r12+1]
0x18006333d  mov     [rsi+0F8h], r13d
0x180063344  mov     [rsi+100h], rbx
0x18006334b  mov     [rsi+108h], r12
0x180063352  lea     r14, [rsi+110h]
0x180063359  mov     [r14], r12
0x18006335c  mov     eax, [rsp+58h+arg_68]
0x180063363  mov     [rsi+118h], eax
0x180063369  mov     [rsi+120h], r12d
0x180063370  mov     [rsi+138h], r12d
0x180063377  mov     qword ptr [rsi+148h], 0FFFFFFFFFFFFFFFFh
0x180063382  mov     [rsi+150h], r12
0x180063389  mov     [rsi+180h], r13d
0x180063390  mov     [rsi+188h], r12
0x180063397  mov     [rsi+190h], r12
0x18006339e  mov     [rsi+198h], r12d
0x1800633a5  mov     [rsi+1A0h], r12
0x1800633ac  mov     [rsi+1A8h], rdi
0x1800633b3  lea     rbx, [rsi+1B0h]
0x1800633ba  mov     [rbx], r12d
0x1800633bd  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x1800633c4  mov     [rbx+8], r12
0x1800633c8  mov     [rbx+10h], r12d
0x1800633cc  mov     [rbx+18h], r12
0x1800633d0  mov     [rsi+1D0h], r12
0x1800633d7  mov     [rsi+1D8h], r12
0x1800633de  mov     [rsi+1E0h], r12d
0x1800633e5  mov     [rsi+1E8h], r12
0x1800633ec  mov     [rsp+58h+var_38], r12d
0x1800633f1  mov     rax, [rsi+100h]
0x1800633f8  lock add [rax+18h], r13d
0x1800633fd  mov     rax, [rsi+1A8h]
0x180063404  lock add [rax+90h], r13d
0x18006340c  lea     rcx, [rsi+158h]; lpCriticalSection
0x180063413  call    cs:__imp_InitializeCriticalSection
0x180063419  lea     rax, [rsi+128h]
0x180063420  mov     [rax+8], rax
0x180063424  mov     [rax], rax
0x180063427  mov     rax, [rsi+0A8h]
0x18006342e  test    rax, rax
0x180063431  jz      short loc_18006343B
0x180063433  lock add [rax+0B8h], r13d
0x18006343b  mov     r8d, 19h; unsigned int
0x180063441  lea     rdx, aClosereaderfil; "CloseReaderFilesAfterConsecutiveReads"
0x180063448  mov     rcx, [rsi+0A0h]; hKey
0x18006344f  call    ?GetRegDWORD@@YAKPEAUHKEY__@@PEBGK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong)
0x180063454  mov     [rsi+11Ch], eax
0x18006345a  test    eax, eax
0x18006345c  jnz     short loc_180063465
0x18006345e  mov     [rsi+11Ch], r13d
0x180063465  mov     qword ptr [rsi+140h], 5F5E100h
0x180063470  mov     r9d, r13d; int
0x180063473  mov     r8, [rsp+58h+arg_20]; void **
0x18006347b  mov     edx, r15d; unsigned int
0x18006347e  mov     rcx, rbx; this
0x180063481  call    ?SetSids@CClientInfo@CDVRFileCollection@@QEAAJKPEAPEAXH@Z; CDVRFileCollection::CClientInfo::SetSids(ulong,void * *,int)
0x180063486  mov     ecx, eax
0x180063488  test    eax, eax
0x18006348a  jns     short loc_180063492
0x18006348c  mov     [rsp+58h+var_38], eax
0x180063490  jmp     short loc_1800634F2
0x180063492  xor     r9d, r9d; lpName
0x180063495  mov     r8d, r13d; bInitialState
0x180063498  mov     edx, r13d; bManualReset
0x18006349b  xor     ecx, ecx; lpEventAttributes
0x18006349d  call    cs:__imp_CreateEventW
0x1800634a3  mov     [rsi+1E8h], rax
0x1800634aa  test    rax, rax
0x1800634ad  jnz     short loc_1800634C6
0x1800634af  call    cs:__imp_GetLastError
0x1800634b5  mov     ecx, eax
0x1800634b7  test    eax, eax
0x1800634b9  jle     short loc_1800634EE
0x1800634bb  movzx   ecx, ax
0x1800634be  or      ecx, 80070000h
0x1800634c4  jmp     short loc_1800634EE
0x1800634c6  mov     rcx, r14; struct COutstandingOps **
0x1800634c9  call    ?CreateInstance@COutstandingOps@@SAKPEAPEAV1@@Z; COutstandingOps::CreateInstance(COutstandingOps * *)
0x1800634ce  mov     ecx, eax
0x1800634d0  test    eax, eax
0x1800634d2  jnz     short loc_1800634B9
0x1800634d4  mov     r9, rsi; void *
0x1800634d7  mov     rdx, rbx; struct CDVRFileCollection::CClientInfo *
0x1800634da  mov     rcx, [rsi+1A8h]; this
0x1800634e1  call    ?RegisterReader@CDVRFileCollection@@QEAAJPEAUCClientInfo@1@P6AXPEAXK_J2@Z1@Z; CDVRFileCollection::RegisterReader(CDVRFileCollection::CClientInfo *,void (*)(void *,ulong,__int64,__int64),void *)
0x1800634e6  mov     ecx, r12d
0x1800634e9  test    eax, eax
0x1800634eb  cmovs   ecx, eax
0x1800634ee  mov     [rsp+58h+var_38], ecx
0x1800634f2  mov     rax, [rsp+58h+arg_70]
0x1800634fa  test    rax, rax
0x1800634fd  jz      short loc_180063501
0x1800634ff  mov     [rax], ecx
0x180063501  dec     dword ptr [rsi+180h]
0x180063507  mov     rax, rsi
0x18006350a  mov     rbx, [rsp+58h+arg_8]
0x18006350f  mov     rsi, [rsp+58h+arg_10]
0x180063514  add     rsp, 30h
0x180063518  pop     r15
0x18006351a  pop     r14
0x18006351c  pop     r13
0x18006351e  pop     r12
0x180063520  pop     rdi
0x180063521  retn
0x1800b35e4  push    rbp
0x1800b35e6  sub     rsp, 20h
0x1800b35ea  mov     rbp, rdx
0x1800b35ed  mov     rcx, [rbp+0D0h]
0x1800b35f4  test    rcx, rcx
0x1800b35f7  jz      short loc_1800B35FE
0x1800b35f9  mov     eax, [rbp+20h]
0x1800b35fc  mov     [rcx], eax
0x1800b35fe  mov     rcx, [rbp+60h]
0x1800b3602  mov     eax, [rcx+180h]
0x1800b3608  dec     eax
0x1800b360a  mov     [rcx+180h], eax
0x1800b3610  add     rsp, 20h
0x1800b3614  pop     rbp
0x1800b3615  retn
```
