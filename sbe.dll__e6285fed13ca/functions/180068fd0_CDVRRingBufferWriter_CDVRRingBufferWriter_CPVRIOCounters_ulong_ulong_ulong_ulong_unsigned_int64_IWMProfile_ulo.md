# CDVRRingBufferWriter::CDVRRingBufferWriter(CPVRIOCounters *,ulong,ulong,ulong,ulong,unsigned __int64,IWMProfile *,ulong,ulong,int,ulong,ulong,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,ushort const *,ushort const *,ulong,void * *,ulong,CPVRStreamProf &,int,long *)

- ea: `0x180068fd0`
- end: `0x1800696f5`
- name: `??0CDVRRingBufferWriter@@QEAA@PEAVCPVRIOCounters@@KKKK_KPEAUIWMProfile@@KKHKKKKP6AXPEAXK_J4@Z3PEAUHKEY__@@6PEBG7KPEAPEAXKAEAVCPVRStreamProf@@HPEAJ@Z`
- size: `1829`
- prototype: `CDVRRingBufferWriter *__usercall@<rax>(CDVRRingBufferWriter *__hidden this@<rcx>, struct CPVRIOCounters *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned __int64, struct IWMProfile *, unsigned int, unsigned int, int, unsigned int, unsigned int, unsigned int, unsigned int, void (*)(void *, unsigned int, __int64, __int64), void *, HKEY, HKEY, const unsigned __int16 *, LPCWSTR lpFileName, unsigned int, void **, size_t Size, struct CPVRStreamProf *, int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180070734`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x180068244`
- `0x180068fd0`
- `0x1800696fc`
- `0x180069bb8`
- `0x180070c30`
- `0x180077638`
- `0x18007c47c`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180069606`
- `KERNEL32!WaitForSingleObject` at `0x180069606`
- `KERNEL32!InitializeCriticalSection` at `0x1800691b0`
- `KERNEL32!InitializeCriticalSection` at `0x1800691b0`
- `KERNEL32!GetLastError` at `0x180069329`
- `KERNEL32!GetLastError` at `0x180069468`
- `KERNEL32!GetLastError` at `0x180069329`
- `KERNEL32!GetLastError` at `0x180069468`
- `KERNEL32!GetTempPath2W` at `0x18006931f`
- `KERNEL32!GetTempPath2W` at `0x180069365`
- `KERNEL32!GetTempPath2W` at `0x18006931f`
- `KERNEL32!GetTempPath2W` at `0x180069365`
- `KERNEL32!DeleteFileW` at `0x1800694f0`
- `KERNEL32!DeleteFileW` at `0x1800694f0`
- `KERNEL32!GetFullPathNameW` at `0x18006945b`
- `KERNEL32!GetFullPathNameW` at `0x1800694b8`
- `KERNEL32!GetFullPathNameW` at `0x18006945b`
- `KERNEL32!GetFullPathNameW` at `0x1800694b8`

## string_xrefs

- `0x180069250`: `DVRDirectory`
- `0x1800692d2`: `DVRDirectory`

## pseudocode

```c
CDVRRingBufferWriter *__fastcall CDVRRingBufferWriter::CDVRRingBufferWriter(
        CDVRRingBufferWriter *this,
        struct CPVRIOCounters *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        struct IWMProfile *a8,
        unsigned int a9,
        unsigned int a10,
        int a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        unsigned int a15,
        void (*a16)(void *, unsigned int, __int64, __int64),
        void *a17,
        HKEY a18,
        HKEY a19,
        const unsigned __int16 *a20,
        WCHAR *lpFileName,
        unsigned int a22,
        void **a23,
        size_t Size,
        struct CPVRStreamProf *a25,
        int a26,
        int *a27)
{
  WCHAR *v28; // rdi
  int *v29; // r14
  int v30; // r15d
  const struct CDVRFileCollection::CClientInfo *v31; // r12
  char *v32; // r13
  int RegString; // ecx
  BYTE *v34; // rax
  int TempPath2W; // eax
  unsigned int v36; // r15d
  unsigned __int64 v37; // kr00_8
  void *v38; // rax
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  BYTE *v43; // rax
  DWORD FullPathNameW; // eax
  DWORD v45; // r13d
  signed int LastError; // eax
  DWORD v47; // r12d
  WCHAR *v48; // rax
  DWORD v49; // eax
  CDVRFileCollection *v50; // r10
  CDVRFileCollection *v51; // rax
  CAsyncIo *v52; // rax
  CAsyncIo *v53; // rax
  __int64 v54; // rdi
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rcx
  void *v57; // rax
  int v58; // eax
  DWORD cbData; // [rsp+90h] [rbp-48h] BYREF
  DWORD v61; // [rsp+94h] [rbp-44h] BYREF
  int v62; // [rsp+98h] [rbp-40h] BYREF
  __int16 v63; // [rsp+9Ch] [rbp-3Ch] BYREF
  WCHAR Buffer; // [rsp+A0h] [rbp-38h] BYREF

  v28 = lpFileName;
  v29 = a27;
  *(_QWORD *)this = &CDVRRingBufferWriter::`vftable'{for `IDVRRingBufferWriter'};
  *((_QWORD *)this + 1) = &CDVRRingBufferWriter::`vftable'{for `IWMStatusCallback'};
  *((_QWORD *)this + 2) = a7;
  *((_QWORD *)this + 3) = a8;
  v30 = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = a3;
  *((_DWORD *)this + 13) = a4;
  *((_DWORD *)this + 14) = a5;
  *((_DWORD *)this + 15) = a9;
  *((_DWORD *)this + 16) = a10;
  *((_QWORD *)this + 9) = a18;
  *((_QWORD *)this + 10) = a19;
  *((_QWORD *)this + 11) = &CPVRStreamProf::`vftable';
  *((_DWORD *)this + 24) = *((_DWORD *)a25 + 2);
  *((_DWORD *)this + 25) = *((_DWORD *)a25 + 3);
  *((_DWORD *)this + 26) = *((_DWORD *)a25 + 4);
  *((_QWORD *)this + 14) = CDVREventSink::DVRIOCallback;
  *((_QWORD *)this + 15) = a17;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = a12;
  *((_DWORD *)this + 35) = a13;
  *((_DWORD *)this + 36) = a14;
  *((_DWORD *)this + 37) = a15;
  *((_DWORD *)this + 38) = a26;
  *((_QWORD *)this + 20) = a2;
  CIndexSampleGenerator::CIndexSampleGenerator((CDVRRingBufferWriter *)((char *)this + 168), (struct IUnknown *)this);
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 122) = -2;
  *((_DWORD *)this + 123) = 0;
  *((_DWORD *)this + 134) = 0;
  *((_QWORD *)this + 72) = 0;
  v31 = (CDVRRingBufferWriter *)((char *)this + 584);
  *((_DWORD *)this + 146) = 1;
  *((_DWORD *)this + 147) = -1;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 150) = 0;
  *((_QWORD *)this + 76) = 0;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 20) + 24LL));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  v32 = (char *)this + 440;
  *((_QWORD *)this + 56) = (char *)this + 440;
  *((_QWORD *)this + 55) = (char *)this + 440;
  *((_QWORD *)this + 58) = (char *)this + 456;
  *((_QWORD *)this + 57) = (char *)this + 456;
  *((_QWORD *)this + 69) = (char *)this + 544;
  *((_QWORD *)this + 68) = (char *)this + 544;
  *((_QWORD *)this + 71) = (char *)this + 560;
  *((_QWORD *)this + 70) = (char *)this + 560;
  RegString = CDVRFileCollection::CClientInfo::SetSids((CDVRRingBufferWriter *)((char *)this + 584), a22, a23, 1);
  v62 = RegString;
  if ( RegString >= 0 )
  {
    if ( *((_QWORD *)this + 4) )
      goto LABEL_11;
    cbData = 0;
    RegString = GetRegString(*((HKEY *)this + 10), L"DVRDirectory", 0, &cbData);
    v62 = RegString;
    if ( (int)(RegString + 0x80000000) < 0 || RegString == -2147024894 )
    {
      if ( RegString >= 0 && cbData > 2 )
      {
        v34 = (BYTE *)operator new[](saturated_mul(((unsigned __int64)cbData >> 1) + 1, 2u));
        *((_QWORD *)this + 4) = v34;
        if ( !v34 )
        {
LABEL_8:
          RegString = -2147024882;
LABEL_58:
          v29 = a27;
          goto LABEL_59;
        }
        RegString = GetRegString(*((HKEY *)this + 10), L"DVRDirectory", v34, &cbData);
        v62 = RegString;
        if ( RegString < 0 )
        {
LABEL_10:
          v29 = a27;
          goto LABEL_59;
        }
      }
LABEL_11:
      if ( !*((_QWORD *)this + 4) )
      {
        v63 = 0;
        TempPath2W = GetTempPath2W(0, &v63);
        if ( !TempPath2W )
          goto LABEL_13;
        v36 = TempPath2W + 1;
        v37 = (unsigned int)(TempPath2W + 1);
        v38 = operator new[](saturated_mul(v37, 2u));
        *((_QWORD *)this + 4) = v38;
        if ( !v38 )
          goto LABEL_8;
        v39 = GetTempPath2W(v36, v38);
        v30 = 0;
        if ( !v39 )
        {
LABEL_13:
          GetLastError();
          RegString = -2147024894;
          goto LABEL_58;
        }
        v40 = (unsigned int)(v39 - 1);
        v41 = *((_QWORD *)this + 4);
        if ( *(_WORD *)(v41 + 2 * v40) == 92 )
          *(_WORD *)(v41 + 2 * v40) = 0;
      }
      if ( lpFileName )
        goto LABEL_26;
      v61 = 0;
      v62 = GetRegString(*((HKEY *)this + 10), L"RingBufferFileName", 0, &v61);
      if ( v62 >= 0 && v61 > 2 )
      {
        v43 = (BYTE *)operator new[](saturated_mul(((unsigned __int64)v61 >> 1) + 1, 2u));
        v28 = (WCHAR *)v43;
        if ( !v43 )
          goto LABEL_8;
        v62 = GetRegString(*((HKEY *)this + 10), L"RingBufferFileName", v43, &v61);
        if ( v62 < 0 )
        {
          operator delete(v28, v42);
          v28 = 0;
        }
        v30 = 1;
      }
      if ( v28 )
      {
LABEL_26:
        Buffer = 0;
        FullPathNameW = GetFullPathNameW(v28, 0, &Buffer, 0);
        v45 = FullPathNameW;
        if ( !FullPathNameW )
          goto LABEL_27;
        v47 = FullPathNameW + 1;
        v48 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
        *((_QWORD *)this + 5) = v48;
        if ( !v48 )
          goto LABEL_8;
        v49 = GetFullPathNameW(v28, v47, v48, 0);
        if ( !v49 )
          goto LABEL_27;
        if ( v49 > v45 )
        {
LABEL_32:
          RegString = -2147467259;
          goto LABEL_58;
        }
        v31 = (CDVRRingBufferWriter *)((char *)this + 584);
        v32 = (char *)this + 440;
      }
      if ( v30 )
      {
        operator delete(v28, v42);
        DeleteFileW(*((LPCWSTR *)this + 5));
      }
      v50 = (CDVRFileCollection *)operator new(0x1B0u);
      if ( v50 )
        v51 = CDVRFileCollection::CDVRFileCollection(
                v50,
                v31,
                *((_DWORD *)this + 12) + 1,
                *((_DWORD *)this + 13) + 1,
                *((_DWORD *)this + 14) + 1,
                a6,
                0,
                *((_DWORD *)this + 16),
                *((const unsigned __int16 **)this + 4),
                *((LPCWSTR *)this + 5),
                0,
                *((_DWORD *)this + 38),
                &v62);
      else
        v51 = 0;
      *((_QWORD *)this + 72) = v51;
      if ( !v51 )
        goto LABEL_8;
      RegString = v62;
      if ( v62 < 0 )
        goto LABEL_58;
      if ( a11 )
      {
        v52 = (CAsyncIo *)operator new(0xC0u);
        if ( v52 )
          v53 = CAsyncIo::CAsyncIo(v52);
        else
          v53 = 0;
        *((_QWORD *)this + 16) = v53;
        if ( !v53 )
          goto LABEL_8;
        _InterlockedIncrement((volatile signed __int32 *)v53 + 46);
      }
      RegString = CDVRRingBufferWriter::AddATemporaryFile(this, 0, *((_QWORD *)this + 2));
      v62 = RegString;
      if ( RegString < 0 )
        goto LABEL_10;
      *((_DWORD *)this + 123) |= 0x20u;
      v54 = *(_QWORD *)v32;
      if ( WaitForSingleObject(*(HANDLE *)(*(_QWORD *)v32 + 72LL), 0xFFFFFFFF) != -1 )
      {
        if ( *(_QWORD *)(v54 + 16) )
        {
          RegString = *(_DWORD *)(v54 + 88);
          if ( RegString >= 0 )
          {
            if ( (_DWORD)Size )
            {
              *((_WORD *)this + 88) = a9;
              v56 = 10000LL * a10;
              *((_QWORD *)this + 23) = v56;
              *((_QWORD *)this + 24) = v56 >> 1;
              operator delete(*((void **)this + 53), v55);
              v57 = operator new[]((unsigned int)Size);
              *((_QWORD *)this + 53) = v57;
              if ( v57 )
              {
                *((_DWORD *)this + 108) = Size;
                memset_0(v57, 0, (unsigned int)Size);
                v58 = 0;
              }
              else
              {
                v58 = -2147024882;
              }
              v62 = v58;
              RegString = 0;
              if ( v58 < 0 )
                RegString = v58;
            }
            else
            {
              RegString = -2147024809;
            }
          }
          goto LABEL_58;
        }
        goto LABEL_32;
      }
LABEL_27:
      LastError = GetLastError();
      RegString = LastError;
      if ( LastError > 0 )
        RegString = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_58;
    }
  }
LABEL_59:
  if ( v29 )
    *v29 = RegString;
  return this;
}

```

## disassembly

```asm
0x180068fd0  mov     [rsp+arg_8], rbx
0x180068fd5  mov     [rsp+arg_10], rsi
0x180068fda  push    rdi
0x180068fdb  push    r12
0x180068fdd  push    r13
0x180068fdf  push    r14
0x180068fe1  push    r15
0x180068fe3  sub     rsp, 0B0h
0x180068fea  mov     rax, cs:__security_cookie
0x180068ff1  xor     rax, rsp
0x180068ff4  mov     [rsp+0D8h+var_30], rax
0x180068ffc  mov     rbx, rcx
0x180068fff  mov     eax, [rsp+0D8h+arg_28]
0x180069006  mov     [rsp+0D8h+var_54], eax
0x18006900d  mov     rdi, [rsp+0D8h+lpFileName]
0x180069015  mov     rsi, [rsp+0D8h+arg_B0]
0x18006901d  mov     r14, [rsp+0D8h+arg_D0]
0x180069025  mov     [rsp+0D8h+var_60], r14
0x18006902a  mov     [rsp+0D8h+var_50], r14
0x180069032  lea     rax, ??_7CDVRRingBufferWriter@@6BIDVRRingBufferWriter@@@; const CDVRRingBufferWriter::`vftable'{for `IDVRRingBufferWriter'}
0x180069039  mov     [rcx], rax
0x18006903c  lea     rax, ??_7CDVRRingBufferWriter@@6BIWMStatusCallback@@@; const CDVRRingBufferWriter::`vftable'{for `IWMStatusCallback'}
0x180069043  mov     [rcx+8], rax
0x180069047  mov     rax, [rsp+0D8h+arg_30]
0x18006904f  mov     [rcx+10h], rax
0x180069053  mov     rax, [rsp+0D8h+arg_38]
0x18006905b  mov     [rcx+18h], rax
0x18006905f  xor     r15d, r15d
0x180069062  mov     [rcx+20h], r15
0x180069066  mov     [rcx+28h], r15
0x18006906a  mov     [rcx+30h], r8d
0x18006906e  mov     [rcx+34h], r9d
0x180069072  mov     eax, [rsp+0D8h+arg_20]
0x180069079  mov     [rcx+38h], eax
0x18006907c  mov     eax, [rsp+0D8h+arg_40]
0x180069083  mov     [rcx+3Ch], eax
0x180069086  mov     eax, [rsp+0D8h+arg_48]
0x18006908d  mov     [rcx+40h], eax
0x180069090  mov     rax, [rsp+0D8h+arg_88]
0x180069098  mov     [rcx+48h], rax
0x18006909c  mov     rax, [rsp+0D8h+arg_90]
0x1800690a4  mov     [rcx+50h], rax
0x1800690a8  lea     rax, ??_7CPVRStreamProf@@6B@; const CPVRStreamProf::`vftable'
0x1800690af  mov     [rcx+58h], rax
0x1800690b3  mov     rcx, [rsp+0D8h+arg_C0]
0x1800690bb  mov     eax, [rcx+8]
0x1800690be  mov     [rbx+60h], eax
0x1800690c1  mov     eax, [rcx+0Ch]
0x1800690c4  mov     [rbx+64h], eax
0x1800690c7  mov     eax, [rcx+10h]
0x1800690ca  mov     [rbx+68h], eax
0x1800690cd  lea     rax, ?DVRIOCallback@CDVREventSink@@SAXPEAXK_J1@Z; CDVREventSink::DVRIOCallback(void *,ulong,__int64,__int64)
0x1800690d4  mov     [rbx+70h], rax
0x1800690d8  mov     rax, [rsp+0D8h+arg_80]
0x1800690e0  mov     [rbx+78h], rax
0x1800690e4  mov     [rbx+80h], r15
0x1800690eb  mov     eax, [rsp+0D8h+arg_58]
0x1800690f2  mov     [rbx+88h], eax
0x1800690f8  mov     eax, [rsp+0D8h+arg_60]
0x1800690ff  mov     [rbx+8Ch], eax
0x180069105  mov     eax, [rsp+0D8h+arg_68]
0x18006910c  mov     [rbx+90h], eax
0x180069112  mov     eax, [rsp+0D8h+arg_70]
0x180069119  mov     [rbx+94h], eax
0x18006911f  mov     eax, [rsp+0D8h+arg_C8]
0x180069126  mov     [rbx+98h], eax
0x18006912c  mov     [rbx+0A0h], rdx
0x180069133  lea     rcx, [rbx+0A8h]; this
0x18006913a  mov     rdx, rbx; struct IUnknown *
0x18006913d  call    ??0CIndexSampleGenerator@@QEAA@PEAUIUnknown@@@Z; CIndexSampleGenerator::CIndexSampleGenerator(IUnknown *)
0x180069142  mov     [rbx+1D8h], r15
0x180069149  mov     [rbx+1E0h], r15
0x180069150  mov     dword ptr [rbx+1E8h], 0FFFFFFFEh
0x18006915a  mov     [rbx+1ECh], r15d
0x180069161  mov     [rbx+218h], r15d
0x180069168  mov     [rbx+240h], r15
0x18006916f  lea     r12, [rbx+248h]
0x180069176  mov     dword ptr [r12], 1
0x18006917e  mov     dword ptr [r12+4], 0FFFFFFFFh
0x180069187  mov     [r12+8], r15
0x18006918c  mov     [r12+10h], r15d
0x180069191  mov     [r12+18h], r15
0x180069196  mov     [rsp+0D8h+var_68], 80004005h
0x18006919e  mov     rax, [rbx+0A0h]
0x1800691a5  lock inc dword ptr [rax+18h]
0x1800691a9  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x1800691b0  call    cs:__imp_InitializeCriticalSection
0x1800691b6  mov     rcx, [rbx+18h]
0x1800691ba  mov     rax, [rcx]
0x1800691bd  mov     rax, [rax+8]
0x1800691c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800691c6  lea     r13, [rbx+1B8h]
0x1800691cd  mov     [r13+8], r13
0x1800691d1  mov     [r13+0], r13
0x1800691d5  lea     rax, [rbx+1C8h]
0x1800691dc  mov     [rax+8], rax
0x1800691e0  mov     [rax], rax
0x1800691e3  lea     rax, [rbx+220h]
0x1800691ea  mov     [rax+8], rax
0x1800691ee  mov     [rax], rax
0x1800691f1  lea     rax, [rbx+230h]
0x1800691f8  mov     [rax+8], rax
0x1800691fc  mov     [rax], rax
0x1800691ff  mov     [rsp+0D8h+var_40], r15d
0x180069207  lea     r9d, [r15+1]; int
0x18006920b  mov     r8, rsi; void **
0x18006920e  mov     edx, [rsp+0D8h+arg_A8]; unsigned int
0x180069215  mov     rcx, r12; this
0x180069218  call    ?SetSids@CClientInfo@CDVRFileCollection@@QEAAJKPEAPEAXH@Z; CDVRFileCollection::CClientInfo::SetSids(ulong,void * *,int)
0x18006921d  mov     ecx, eax
0x18006921f  mov     [rsp+0D8h+var_40], eax
0x180069226  test    eax, eax
0x180069228  jns     short loc_180069233
0x18006922a  mov     [rsp+0D8h+var_68], eax
0x18006922e  jmp     loc_1800696BD
0x180069233  cmp     [rbx+20h], r15
0x180069237  jnz     loc_1800692FD
0x18006923d  mov     [rsp+0D8h+cbData], r15d
0x180069245  lea     r9, [rsp+0D8h+cbData]; lpcbData
0x18006924d  xor     r8d, r8d; lpData
0x180069250  lea     rdx, aDvrdirectory; "DVRDirectory"
0x180069257  mov     rcx, [rbx+50h]; hKey
0x18006925b  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAGPEAK@Z; GetRegString(HKEY__ *,ushort const *,ushort *,ulong *)
0x180069260  mov     ecx, eax
0x180069262  mov     [rsp+0D8h+var_40], eax
0x180069269  mov     edx, 80000000h
0x18006926e  add     eax, edx
0x180069270  test    edx, eax
0x180069272  jnz     short loc_180069280
0x180069274  cmp     ecx, 80070002h
0x18006927a  jnz     loc_1800696B9
0x180069280  mov     esi, 2
0x180069285  test    ecx, ecx
0x180069287  js      short loc_180069302
0x180069289  cmp     [rsp+0D8h+cbData], esi
0x180069290  jbe     short loc_180069302
0x180069292  mov     ecx, [rsp+0D8h+cbData]
0x180069299  shr     rcx, 1
0x18006929c  inc     rcx
0x18006929f  mov     eax, esi
0x1800692a1  mul     rcx
0x1800692a4  lea     r14, [rsi-3]
0x1800692a8  cmovb   rax, r14
0x1800692ac  mov     rcx, rax; unsigned __int64
0x1800692af  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800692b4  mov     [rbx+20h], rax
0x1800692b8  test    rax, rax
0x1800692bb  jnz     short loc_1800692C7
0x1800692bd  mov     ecx, 8007000Eh
0x1800692c2  jmp     loc_1800696B4
0x1800692c7  lea     r9, [rsp+0D8h+cbData]; lpcbData
0x1800692cf  mov     r8, rax; lpData
0x1800692d2  lea     rdx, aDvrdirectory; "DVRDirectory"
0x1800692d9  mov     rcx, [rbx+50h]; hKey
0x1800692dd  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAGPEAK@Z; GetRegString(HKEY__ *,ushort const *,ushort *,ulong *)
0x1800692e2  mov     ecx, eax
0x1800692e4  mov     [rsp+0D8h+var_40], eax
0x1800692eb  test    eax, eax
0x1800692ed  jns     short loc_180069306
0x1800692ef  mov     [rsp+0D8h+var_68], eax
0x1800692f3  mov     r14, [rsp+0D8h+var_60]
0x1800692f8  jmp     loc_1800696BD
0x1800692fd  mov     esi, 2
0x180069302  or      r14, 0FFFFFFFFFFFFFFFFh
0x180069306  cmp     [rbx+20h], r15
0x18006930a  jnz     short loc_180069384
0x18006930c  mov     [rsp+0D8h+var_3C], r15w
0x180069315  lea     rdx, [rsp+0D8h+var_3C]
0x18006931d  xor     ecx, ecx
0x18006931f  call    cs:__imp_GetTempPath2W
0x180069325  test    eax, eax
0x180069327  jnz     short loc_180069339
0x180069329  call    cs:__imp_GetLastError
0x18006932f  mov     ecx, 80070002h
0x180069334  jmp     loc_1800696B4
0x180069339  lea     r15d, [rax+1]
0x18006933d  mov     ecx, r15d
0x180069340  mov     rax, rsi
0x180069343  mul     rcx
0x180069346  cmovb   rax, r14
0x18006934a  mov     rcx, rax; unsigned __int64
0x18006934d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180069352  mov     [rbx+20h], rax
0x180069356  test    rax, rax
0x180069359  jz      loc_1800692BD
0x18006935f  mov     rdx, rax
0x180069362  mov     ecx, r15d
0x180069365  call    cs:__imp_GetTempPath2W
0x18006936b  xor     r15d, r15d
0x18006936e  test    eax, eax
0x180069370  jz      short loc_180069329
0x180069372  dec     eax
0x180069374  mov     rdx, [rbx+20h]
0x180069378  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x18006937d  jnz     short loc_180069384
0x18006937f  mov     [rdx+rax*2], r15w
0x180069384  mov     [rsp+0D8h+var_58], r15d
0x18006938c  test    rdi, rdi
0x18006938f  jnz     loc_180069441
0x180069395  mov     [rsp+0D8h+var_44], edi
0x18006939c  lea     r9, [rsp+0D8h+var_44]; lpcbData
0x1800693a4  xor     r8d, r8d; lpData
0x1800693a7  lea     rdx, aRingbufferfile; "RingBufferFileName"
0x1800693ae  mov     rcx, [rbx+50h]; hKey
0x1800693b2  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAGPEAK@Z; GetRegString(HKEY__ *,ushort const *,ushort *,ulong *)
0x1800693b7  mov     [rsp+0D8h+var_40], eax
0x1800693be  test    eax, eax
0x1800693c0  js      short loc_180069438
0x1800693c2  cmp     [rsp+0D8h+var_44], esi
0x1800693c9  jbe     short loc_180069438
0x1800693cb  mov     ecx, [rsp+0D8h+var_44]
0x1800693d2  shr     rcx, 1
0x1800693d5  inc     rcx
0x1800693d8  mov     rax, rsi
0x1800693db  mul     rcx
0x1800693de  cmovb   rax, r14
0x1800693e2  mov     rcx, rax; unsigned __int64
0x1800693e5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800693ea  mov     rdi, rax
0x1800693ed  xor     r15d, r15d
0x1800693f0  test    rax, rax
0x1800693f3  jz      loc_1800692BD
0x1800693f9  lea     r9, [rsp+0D8h+var_44]; lpcbData
0x180069401  mov     r8, rax; lpData
0x180069404  lea     rdx, aRingbufferfile; "RingBufferFileName"
0x18006940b  mov     rcx, [rbx+50h]; hKey
0x18006940f  call    ?GetRegString@@YAJPEAUHKEY__@@PEBGPEAGPEAK@Z; GetRegString(HKEY__ *,ushort const *,ushort *,ulong *)
0x180069414  mov     [rsp+0D8h+var_40], eax
0x18006941b  test    eax, eax
0x18006941d  jns     short loc_18006942A
0x18006941f  mov     rcx, rdi; void *
0x180069422  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069427  mov     edi, r15d
0x18006942a  mov     r15d, 1
0x180069430  mov     [rsp+0D8h+var_58], r15d
0x180069438  test    rdi, rdi
0x18006943b  jz      loc_1800694DF
0x180069441  xor     eax, eax
0x180069443  mov     [rsp+0D8h+Buffer], ax
0x18006944b  xor     r9d, r9d; lpFilePart
0x18006944e  lea     r8, [rsp+0D8h+Buffer]; lpBuffer
0x180069456  xor     edx, edx; nBufferLength
0x180069458  mov     rcx, rdi; lpFileName
0x18006945b  call    cs:__imp_GetFullPathNameW
0x180069461  mov     r13d, eax
0x180069464  test    eax, eax
0x180069466  jnz     short loc_180069486
0x180069468  call    cs:__imp_GetLastError
0x18006946e  mov     ecx, eax
0x180069470  test    eax, eax
0x180069472  jle     loc_1800696B4
0x180069478  movzx   ecx, ax
0x18006947b  or      ecx, 80070000h
0x180069481  jmp     loc_1800696B4
0x180069486  lea     r12d, [rax+1]
0x18006948a  mov     ecx, r12d
0x18006948d  mov     rax, rsi
0x180069490  mul     rcx
0x180069493  cmovb   rax, r14
0x180069497  mov     rcx, rax; unsigned __int64
0x18006949a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006949f  mov     [rbx+28h], rax
0x1800694a3  test    rax, rax
0x1800694a6  jz      loc_1800692BD
0x1800694ac  xor     r9d, r9d; lpFilePart
0x1800694af  mov     r8, rax; lpBuffer
0x1800694b2  mov     edx, r12d; nBufferLength
0x1800694b5  mov     rcx, rdi; lpFileName
0x1800694b8  call    cs:__imp_GetFullPathNameW
0x1800694be  test    eax, eax
0x1800694c0  jz      short loc_180069468
0x1800694c2  cmp     eax, r13d
0x1800694c5  jbe     short loc_1800694D1
0x1800694c7  mov     ecx, 80004005h
0x1800694cc  jmp     loc_1800696B4
0x1800694d1  lea     r12, [rbx+248h]
0x1800694d8  lea     r13, [rbx+1B8h]
0x1800694df  test    r15d, r15d
0x1800694e2  jz      short loc_1800694F6
0x1800694e4  mov     rcx, rdi; void *
0x1800694e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800694ec  mov     rcx, [rbx+28h]; lpFileName
0x1800694f0  call    cs:__imp_DeleteFileW
0x1800694f6  mov     ecx, 1B0h; Size
0x1800694fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069500  mov     r10, rax
0x180069503  xor     r15d, r15d
0x180069506  test    rax, rax
0x180069509  jz      short loc_180069574
0x18006950b  mov     ecx, [rbx+38h]
0x18006950e  inc     ecx
0x180069510  mov     r9d, [rbx+34h]
0x180069514  inc     r9d; unsigned int
0x180069517  mov     r8d, [rbx+30h]
0x18006951b  inc     r8d; unsigned int
0x18006951e  lea     rax, [rsp+0D8h+var_40]
0x180069526  mov     [rsp+0D8h+var_78], rax; int *
0x18006952b  mov     eax, [rbx+98h]
0x180069531  mov     [rsp+0D8h+var_80], eax; int
0x180069535  mov     [rsp+0D8h+var_88], r15d; int
  ... truncated ...
```
