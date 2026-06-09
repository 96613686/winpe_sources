# CDVRReader::CDVRReader(CPVRIOCounters *,ushort const *,ulong,void * *,int,ulong,ulong,void (*)(void *,ulong,__int64,__int64),void *,HKEY__ *,HKEY__ *,int,int,long *)

- ea: `0x180063528`
- end: `0x180063afe`
- name: `??0CDVRReader@@QEAA@PEAVCPVRIOCounters@@PEBGKPEAPEAXHKKP6AXPEAXK_J4@Z3PEAUHKEY__@@6HHPEAJ@Z`
- size: `1494`
- prototype: `CDVRReader *__usercall@<rax>(CDVRReader *__hidden this@<rcx>, struct CPVRIOCounters *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, void **, int, unsigned int, unsigned int, void (*)(void *, unsigned int, __int64, __int64), void *, HKEY, HKEY, int, int, int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180068940`

## callees

- `0x1800017a0`
- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x180029a50`
- `0x180063528`
- `0x180063fbc`
- `0x180064dd8`
- `0x180068244`
- `0x180070c30`
- `0x180071424`
- `0x18007307c`
- `0x1800754a4`
- `0x180075aec`
- `0x180077638`
- `0x18007c3a8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180063872`
- `KERNEL32!CreateEventW` at `0x180063872`
- `KERNEL32!InitializeCriticalSection` at `0x180063715`
- `KERNEL32!InitializeCriticalSection` at `0x180063715`
- `KERNEL32!GetLastError` at `0x180063759`
- `KERNEL32!GetLastError` at `0x180063884`
- `KERNEL32!GetLastError` at `0x180063759`
- `KERNEL32!GetLastError` at `0x180063884`
- `KERNEL32!GetFullPathNameW` at `0x18006374f`
- `KERNEL32!GetFullPathNameW` at `0x1800637b0`
- `KERNEL32!GetFullPathNameW` at `0x18006374f`
- `KERNEL32!GetFullPathNameW` at `0x1800637b0`

## string_xrefs

- `0x180063827`: `CloseReaderFilesAfterConsecutiveReads`

## pseudocode

```c
CDVRReader *__fastcall CDVRReader::CDVRReader(
        CDVRReader *this,
        struct CPVRIOCounters *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void **a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        void (*a9)(void *, unsigned int, __int64, __int64),
        void *a10,
        HKEY a11,
        HKEY a12,
        int a13,
        int a14,
        int *a15)
{
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  DWORD v20; // ebx
  WCHAR *v21; // rax
  WCHAR *v22; // r14
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  int v25; // ebx
  int v26; // eax
  unsigned int RegDWORD; // eax
  signed int Instance; // eax
  HANDLE EventW; // rax
  CAsyncIo *v30; // rax
  CAsyncIo *v31; // rax
  CDVRFileCollection *v32; // rax
  void (*v33)(void *, unsigned int, __int64, __int64); // r8
  CDVRFileCollection *v34; // rax
  CDVRFileCollection *v35; // rcx
  _DWORD *v36; // rax
  int v38; // [rsp+90h] [rbp-58h] BYREF
  unsigned int v39; // [rsp+94h] [rbp-54h] BYREF
  WCHAR Buffer; // [rsp+98h] [rbp-50h] BYREF

  v39 = a4;
  *(_QWORD *)this = &CDVRReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 1) = &CDVRReader::`vftable'{for `IDVRSourceAdviseSink'};
  *((_QWORD *)this + 2) = &CDVRReader::`vftable'{for `IDVRIORecordingAttributes'};
  *((_QWORD *)this + 3) = &CDVRReader::`vftable'{for `IDVRReaderNotify'};
  *((_QWORD *)this + 4) = &CDVRReader::`vftable'{for `IDVRCrossBarNotify'};
  SBECoreUtil::TCDenseVector<unsigned long>::TCDenseVector<unsigned long>((char *)this + 40);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = a11;
  *((_QWORD *)this + 20) = a12;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = a7;
  *((_DWORD *)this + 45) = a8;
  *((_QWORD *)this + 23) = a9;
  *((_QWORD *)this + 24) = a10;
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
  *((_QWORD *)this + 53) = 0;
  *((_DWORD *)this + 108) = 0;
  *((_DWORD *)this + 109) = -1;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 118) = 0;
  *(_QWORD *)((char *)this + 476) = 1;
  *((_QWORD *)this + 61) = 0;
  Buffer = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  *((_QWORD *)this + 38) = (char *)this + 296;
  *((_QWORD *)this + 37) = (char *)this + 296;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 32) + 24LL));
  *((_QWORD *)this + 40) = 100000000;
  FullPathNameW = GetFullPathNameW(a3, 0, &Buffer, 0);
  if ( !FullPathNameW )
    goto LABEL_2;
  v20 = FullPathNameW + 1;
  v21 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
  v22 = v21;
  if ( !v21 )
  {
    *a15 = -2147024882;
    return this;
  }
  if ( !GetFullPathNameW(a3, v20, v21, 0) )
  {
    operator delete(v22, v23);
LABEL_2:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a15 = LastError;
    return this;
  }
  v25 = CDVRFileCollection::ContinueTryingToOpen(v22);
  if ( v25 < 0 )
  {
    operator delete(v22, v24);
    *a15 = v25;
    return this;
  }
  operator delete(v22, v24);
  v26 = CDVRFileCollection::CClientInfo::SetSids((CDVRReader *)((char *)this + 432), v39, a5, 1);
  v38 = v26;
  if ( v26 < 0 )
  {
    v25 = v26;
    goto LABEL_53;
  }
  RegDWORD = GetRegDWORD(*((HKEY *)this + 20), L"CloseReaderFilesAfterConsecutiveReads", 0x19u);
  *((_DWORD *)this + 71) = RegDWORD;
  if ( !RegDWORD )
    *((_DWORD *)this + 71) = 1;
  Instance = COutstandingOps::CreateInstance((struct COutstandingOps **)this + 34);
  if ( !Instance )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)this + 61) = EventW;
    if ( !EventW )
    {
      Instance = GetLastError();
      v25 = Instance;
      if ( Instance <= 0 )
        goto LABEL_53;
LABEL_21:
      v25 = (unsigned __int16)Instance | 0x80070000;
      goto LABEL_53;
    }
    if ( a6 )
    {
      v30 = (CAsyncIo *)operator new(0xC0u);
      if ( v30 )
        v31 = CAsyncIo::CAsyncIo(v30);
      else
        v31 = 0;
      *((_QWORD *)this + 21) = v31;
      if ( !v31 )
      {
        *a15 = -2147024882;
        goto LABEL_53;
      }
      _InterlockedAdd((volatile signed __int32 *)v31 + 46, 1u);
    }
    v39 = 0;
    v32 = (CDVRFileCollection *)operator new(0x1B0u);
    if ( v32 )
      v34 = CDVRFileCollection::CDVRFileCollection(
              v32,
              (CDVRReader *)((char *)this + 432),
              a3,
              *((_DWORD *)this + 70),
              &v39,
              &v38);
    else
      v34 = 0;
    *((_QWORD *)this + 53) = v34;
    if ( !v34 )
    {
LABEL_33:
      v25 = -2147024882;
      goto LABEL_53;
    }
    if ( v38 >= 0 )
    {
      *((_DWORD *)this + 119) = 0;
    }
    else
    {
      *((_DWORD *)this + 119) = 1;
      CDVRFileCollection::Release(v34, (CDVRReader *)((char *)this + 432));
      v35 = (CDVRFileCollection *)operator new(0x1B0u);
      if ( v35 )
        v34 = CDVRFileCollection::CDVRFileCollection(
                v35,
                (CDVRReader *)((char *)this + 432),
                0,
                0,
                1u,
                0,
                1,
                0xFFFFFFFF,
                0,
                0,
                0,
                *((_DWORD *)this + 70),
                &v38);
      else
        v34 = 0;
      *((_QWORD *)this + 53) = v34;
      if ( !v34 )
        goto LABEL_33;
      *((_DWORD *)this + 120) = 1;
      v25 = v38;
      if ( v38 < 0 )
        goto LABEL_53;
    }
    v25 = CDVRFileCollection::RegisterReader(v34, (CDVRReader *)((char *)this + 432), v33, this);
    v38 = v25;
    if ( v25 < 0 )
      goto LABEL_53;
    if ( *((_DWORD *)this + 120) )
    {
      v36 = operator new(0x20u);
      if ( v36 )
      {
        *v36 = 1;
        v36[1] = -1;
        *((_QWORD *)v36 + 1) = 0;
        v36[4] = 0;
        *((_QWORD *)v36 + 3) = 0;
      }
      else
      {
        v36 = 0;
      }
      *((_QWORD *)this + 58) = v36;
      if ( !v36 )
        goto LABEL_33;
      v25 = CDVRFileCollection::CClientInfo::SetSids((CDVRFileCollection::CClientInfo *)v36, 0, 0, 0);
      v38 = v25;
      if ( v25 < 0 )
        goto LABEL_53;
      v25 = CDVRReader::AddAPermanentFile(this, a3, a13);
      v38 = v25;
      if ( v25 < 0 )
        goto LABEL_53;
      *((_DWORD *)this + 72) = -1;
    }
    else
    {
      *((_QWORD *)this + 18) = 10000LL * v39;
    }
    v25 = 0;
    goto LABEL_53;
  }
  if ( Instance > 0 )
    goto LABEL_21;
  v25 = Instance;
LABEL_53:
  if ( a15 )
    *a15 = v25;
  --*((_DWORD *)this + 96);
  return this;
}

```

## disassembly

```asm
0x180063528  push    rbx
0x18006352a  push    rsi
0x18006352b  push    rdi
0x18006352c  push    r12
0x18006352e  push    r13
0x180063530  push    r14
0x180063532  push    r15
0x180063534  sub     rsp, 0B0h
0x18006353b  mov     rax, cs:__security_cookie
0x180063542  xor     rax, rsp
0x180063545  mov     [rsp+0E8h+var_48], rax
0x18006354d  mov     [rsp+0E8h+var_54], r9d
0x180063555  mov     r12, r8
0x180063558  mov     rbx, rdx
0x18006355b  mov     rdi, rcx
0x18006355e  mov     [rsp+0E8h+var_60], rcx
0x180063566  mov     rax, [rsp+0E8h+arg_20]
0x18006356e  mov     [rsp+0E8h+var_70], rax
0x180063573  mov     rsi, [rsp+0E8h+arg_70]
0x18006357b  mov     [rsp+0E8h+var_68], rsi
0x180063583  lea     rax, ??_7CDVRReader@@6BIDVRReader@@@; const CDVRReader::`vftable'{for `IDVRReader'}
0x18006358a  mov     [rcx], rax
0x18006358d  lea     rax, ??_7CDVRReader@@6BIDVRSourceAdviseSink@@@; const CDVRReader::`vftable'{for `IDVRSourceAdviseSink'}
0x180063594  mov     [rcx+8], rax
0x180063598  lea     rax, ??_7CDVRReader@@6BIDVRIORecordingAttributes@@@; const CDVRReader::`vftable'{for `IDVRIORecordingAttributes'}
0x18006359f  mov     [rcx+10h], rax
0x1800635a3  lea     rax, ??_7CDVRReader@@6BIDVRReaderNotify@@@; const CDVRReader::`vftable'{for `IDVRReaderNotify'}
0x1800635aa  mov     [rcx+18h], rax
0x1800635ae  lea     rax, ??_7CDVRReader@@6BIDVRCrossBarNotify@@@; const CDVRReader::`vftable'{for `IDVRCrossBarNotify'}
0x1800635b5  mov     [rcx+20h], rax
0x1800635b9  add     rcx, 28h ; '('
0x1800635bd  call    ??0?$TCDenseVector@K@SBECoreUtil@@QEAA@PEAXKK@Z; SBECoreUtil::TCDenseVector<ulong>::TCDenseVector<ulong>(void *,ulong,ulong)
0x1800635c2  xor     r14d, r14d
0x1800635c5  mov     [rdi+80h], r14
0x1800635cc  mov     [rdi+88h], r14
0x1800635d3  mov     rax, [rsp+0E8h+arg_50]
0x1800635db  mov     [rdi+98h], rax
0x1800635e2  mov     rax, [rsp+0E8h+arg_58]
0x1800635ea  mov     [rdi+0A0h], rax
0x1800635f1  mov     [rdi+0A8h], r14
0x1800635f8  mov     eax, [rsp+0E8h+arg_30]
0x1800635ff  mov     [rdi+0B0h], eax
0x180063605  mov     eax, [rsp+0E8h+arg_38]
0x18006360c  mov     [rdi+0B4h], eax
0x180063612  mov     rax, [rsp+0E8h+arg_40]
0x18006361a  mov     [rdi+0B8h], rax
0x180063621  mov     rax, [rsp+0E8h+arg_48]
0x180063629  mov     [rdi+0C0h], rax
0x180063630  xorps   xmm0, xmm0
0x180063633  movups  xmmword ptr [rdi+0C8h], xmm0
0x18006363a  movups  xmmword ptr [rdi+0D8h], xmm0
0x180063641  movups  xmmword ptr [rdi+0E8h], xmm0
0x180063648  mov     dword ptr [rdi+0C8h], 0FEEFFEEFh
0x180063652  lea     ecx, [r14+1]
0x180063656  mov     [rdi+0F8h], ecx
0x18006365c  mov     [rdi+100h], rbx
0x180063663  mov     [rdi+108h], r14
0x18006366a  lea     r13, [rdi+110h]
0x180063671  mov     [r13+0], r14
0x180063675  mov     eax, [rsp+0E8h+arg_68]
0x18006367c  mov     [rdi+118h], eax
0x180063682  mov     [rdi+120h], r14d
0x180063689  mov     [rdi+138h], r14d
0x180063690  mov     qword ptr [rdi+148h], 0FFFFFFFFFFFFFFFFh
0x18006369b  mov     [rdi+150h], r14
0x1800636a2  mov     [rdi+180h], ecx
0x1800636a8  mov     [rdi+188h], r14
0x1800636af  mov     [rdi+190h], r14
0x1800636b6  mov     [rdi+198h], r14d
0x1800636bd  mov     [rdi+1A0h], r14
0x1800636c4  mov     [rdi+1A8h], r14
0x1800636cb  lea     r15, [rdi+1B0h]
0x1800636d2  mov     [r15], r14d
0x1800636d5  mov     dword ptr [r15+4], 0FFFFFFFFh
0x1800636dd  mov     [r15+8], r14
0x1800636e1  mov     [r15+10h], r14d
0x1800636e5  mov     [r15+18h], r14
0x1800636e9  mov     [rdi+1D0h], r14
0x1800636f0  mov     [rdi+1D8h], r14d
0x1800636f7  mov     [rdi+1DCh], rcx
0x1800636fe  mov     [rdi+1E8h], r14
0x180063705  mov     [rsp+0E8h+Buffer], r14w
0x18006370e  lea     rcx, [rdi+158h]; lpCriticalSection
0x180063715  call    cs:__imp_InitializeCriticalSection
0x18006371b  lea     rax, [rdi+128h]
0x180063722  mov     [rax+8], rax
0x180063726  mov     [rax], rax
0x180063729  mov     rax, [rdi+100h]
0x180063730  lock inc dword ptr [rax+18h]
0x180063734  mov     qword ptr [rdi+140h], 5F5E100h
0x18006373f  xor     r9d, r9d; lpFilePart
0x180063742  lea     r8, [rsp+0E8h+Buffer]; lpBuffer
0x18006374a  xor     edx, edx; nBufferLength
0x18006374c  mov     rcx, r12; lpFileName
0x18006374f  call    cs:__imp_GetFullPathNameW
0x180063755  test    eax, eax
0x180063757  jnz     short loc_180063772
0x180063759  call    cs:__imp_GetLastError
0x18006375f  test    eax, eax
0x180063761  jle     short loc_18006376B
0x180063763  movzx   eax, ax
0x180063766  or      eax, 80070000h
0x18006376b  mov     [rsi], eax
0x18006376d  jmp     loc_180063AD8
0x180063772  lea     ebx, [rax+1]
0x180063775  mov     ecx, ebx
0x180063777  mov     eax, 2
0x18006377c  mul     rcx
0x18006377f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180063786  cmovb   rax, rcx
0x18006378a  mov     rcx, rax; unsigned __int64
0x18006378d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180063792  mov     r14, rax
0x180063795  test    rax, rax
0x180063798  jnz     short loc_1800637A5
0x18006379a  mov     dword ptr [rsi], 8007000Eh
0x1800637a0  jmp     loc_180063AD8
0x1800637a5  xor     r9d, r9d; lpFilePart
0x1800637a8  mov     r8, r14; lpBuffer
0x1800637ab  mov     edx, ebx; nBufferLength
0x1800637ad  mov     rcx, r12; lpFileName
0x1800637b0  call    cs:__imp_GetFullPathNameW
0x1800637b6  mov     rcx, r14; unsigned __int16 *
0x1800637b9  test    eax, eax
0x1800637bb  jnz     short loc_1800637C4
0x1800637bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800637c2  jmp     short loc_180063759
0x1800637c4  call    ?ContinueTryingToOpen@CDVRFileCollection@@SAJPEBG@Z; CDVRFileCollection::ContinueTryingToOpen(ushort const *)
0x1800637c9  mov     ebx, eax
0x1800637cb  mov     [rsp+0E8h+var_78], eax
0x1800637cf  mov     rcx, r14; void *
0x1800637d2  test    eax, eax
0x1800637d4  jns     short loc_1800637E2
0x1800637d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800637db  mov     [rsi], ebx
0x1800637dd  jmp     loc_180063AD8
0x1800637e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800637e7  nop
0x1800637e8  xor     r14d, r14d
0x1800637eb  mov     [rsp+0E8h+var_58], r14d
0x1800637f3  lea     r9d, [r14+1]; int
0x1800637f7  mov     r8, [rsp+0E8h+var_70]; void **
0x1800637fc  mov     edx, [rsp+0E8h+var_54]; unsigned int
0x180063803  mov     rcx, r15; this
0x180063806  call    ?SetSids@CClientInfo@CDVRFileCollection@@QEAAJKPEAPEAXH@Z; CDVRFileCollection::CClientInfo::SetSids(ulong,void * *,int)
0x18006380b  mov     [rsp+0E8h+var_58], eax
0x180063812  test    eax, eax
0x180063814  jns     short loc_180063821
0x180063816  mov     ebx, eax
0x180063818  mov     [rsp+0E8h+var_78], eax
0x18006381c  jmp     loc_180063ACB
0x180063821  mov     r8d, 19h; unsigned int
0x180063827  lea     rdx, aClosereaderfil; "CloseReaderFilesAfterConsecutiveReads"
0x18006382e  mov     rcx, [rdi+0A0h]; hKey
0x180063835  call    ?GetRegDWORD@@YAKPEAUHKEY__@@PEBGK@Z; GetRegDWORD(HKEY__ *,ushort const *,ulong)
0x18006383a  mov     [rdi+11Ch], eax
0x180063840  test    eax, eax
0x180063842  jnz     short loc_18006384E
0x180063844  mov     dword ptr [rdi+11Ch], 1
0x18006384e  mov     rcx, r13; struct COutstandingOps **
0x180063851  call    ?CreateInstance@COutstandingOps@@SAKPEAPEAV1@@Z; COutstandingOps::CreateInstance(COutstandingOps * *)
0x180063856  test    eax, eax
0x180063858  jz      short loc_180063863
0x18006385a  jg      short loc_180063894
0x18006385c  mov     ebx, eax
0x18006385e  jmp     loc_180063AC7
0x180063863  xor     r9d, r9d; lpName
0x180063866  lea     r13d, [r9+1]
0x18006386a  mov     r8d, r13d; bInitialState
0x18006386d  mov     edx, r13d; bManualReset
0x180063870  xor     ecx, ecx; lpEventAttributes
0x180063872  call    cs:__imp_CreateEventW
0x180063878  mov     [rdi+1E8h], rax
0x18006387f  test    rax, rax
0x180063882  jnz     short loc_1800638A2
0x180063884  call    cs:__imp_GetLastError
0x18006388a  mov     ebx, eax
0x18006388c  test    eax, eax
0x18006388e  jle     loc_180063AC7
0x180063894  movzx   ebx, ax
0x180063897  or      ebx, 80070000h
0x18006389d  jmp     loc_180063AC7
0x1800638a2  cmp     [rsp+0E8h+arg_28], r14d
0x1800638aa  jz      short loc_1800638E7
0x1800638ac  mov     ecx, 0C0h; Size
0x1800638b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800638b6  test    rax, rax
0x1800638b9  jz      short loc_1800638C5
0x1800638bb  mov     rcx, rax; this
0x1800638be  call    ??0CAsyncIo@@QEAA@XZ; CAsyncIo::CAsyncIo(void)
0x1800638c3  jmp     short loc_1800638C8
0x1800638c5  mov     rax, r14
0x1800638c8  mov     [rdi+0A8h], rax
0x1800638cf  test    rax, rax
0x1800638d2  jnz     short loc_1800638DF
0x1800638d4  mov     dword ptr [rsi], 8007000Eh
0x1800638da  jmp     loc_180063ACB
0x1800638df  lock add [rax+0B8h], r13d
0x1800638e7  mov     [rsp+0E8h+var_54], r14d
0x1800638ef  mov     ebx, 1B0h
0x1800638f4  mov     ecx, ebx; Size
0x1800638f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800638fb  test    rax, rax
0x1800638fe  jz      short loc_180063931
0x180063900  lea     rcx, [rsp+0E8h+var_58]
0x180063908  mov     [rsp+0E8h+var_C0], rcx; int *
0x18006390d  lea     rcx, [rsp+0E8h+var_54]
0x180063915  mov     [rsp+0E8h+var_C8], rcx; unsigned int *
0x18006391a  mov     r9d, [rdi+118h]; int
0x180063921  mov     r8, r12; unsigned __int16 *
0x180063924  mov     rdx, r15; struct CDVRFileCollection::CClientInfo *
0x180063927  mov     rcx, rax; this
0x18006392a  call    ??0CDVRFileCollection@@QEAA@PEBUCClientInfo@0@PEBGHPEAKPEAJ@Z; CDVRFileCollection::CDVRFileCollection(CDVRFileCollection::CClientInfo const *,ushort const *,int,ulong *,long *)
0x18006392f  jmp     short loc_180063934
0x180063931  mov     rax, r14
0x180063934  mov     [rdi+1A8h], rax
0x18006393b  test    rax, rax
0x18006393e  jnz     short loc_18006394A
0x180063940  mov     ebx, 8007000Eh
0x180063945  jmp     loc_180063AC7
0x18006394a  cmp     [rsp+0E8h+var_58], r14d
0x180063952  jge     loc_1800639F1
0x180063958  mov     [rdi+1DCh], r13d
0x18006395f  mov     rdx, r15; struct CDVRFileCollection::CClientInfo *
0x180063962  mov     rcx, rax; this
0x180063965  call    ?Release@CDVRFileCollection@@QEAAKPEBUCClientInfo@1@@Z; CDVRFileCollection::Release(CDVRFileCollection::CClientInfo const *)
0x18006396a  mov     rcx, rbx; Size
0x18006396d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063972  mov     rcx, rax; this
0x180063975  test    rax, rax
0x180063978  jz      short loc_1800639C7
0x18006397a  lea     rax, [rsp+0E8h+var_58]
0x180063982  mov     [rsp+0E8h+var_88], rax; int *
0x180063987  mov     eax, [rdi+118h]
0x18006398d  mov     [rsp+0E8h+var_90], eax; int
0x180063991  mov     [rsp+0E8h+var_98], r14d; int
0x180063996  mov     [rsp+0E8h+lpFileName], r14; lpFileName
0x18006399b  mov     [rsp+0E8h+var_A8], r14; unsigned __int16 *
0x1800639a0  mov     [rsp+0E8h+var_B0], 0FFFFFFFFh; unsigned int
0x1800639a8  mov     [rsp+0E8h+var_B8], r13d; int
0x1800639ad  mov     dword ptr [rsp+0E8h+var_C0], r14d; unsigned int
0x1800639b2  mov     dword ptr [rsp+0E8h+var_C8], r13d; unsigned int
0x1800639b7  xor     r9d, r9d; unsigned int
0x1800639ba  xor     r8d, r8d; unsigned int
0x1800639bd  mov     rdx, r15; struct CDVRFileCollection::CClientInfo *
0x1800639c0  call    ??0CDVRFileCollection@@QEAA@PEBUCClientInfo@0@KKKKHKPEBG1HHPEAJ@Z; CDVRFileCollection::CDVRFileCollection(CDVRFileCollection::CClientInfo const *,ulong,ulong,ulong,ulong,int,ulong,ushort const *,ushort const *,int,int,long *)
0x1800639c5  jmp     short loc_1800639CA
0x1800639c7  mov     rax, r14
0x1800639ca  mov     [rdi+1A8h], rax
0x1800639d1  test    rax, rax
0x1800639d4  jz      loc_180063940
0x1800639da  mov     [rdi+1E0h], r13d
0x1800639e1  mov     ebx, [rsp+0E8h+var_58]
0x1800639e8  test    ebx, ebx
0x1800639ea  jns     short loc_1800639F8
0x1800639ec  jmp     loc_180063AC7
0x1800639f1  mov     [rdi+1DCh], r14d
0x1800639f8  mov     r9, rdi; void *
0x1800639fb  mov     rdx, r15; struct CDVRFileCollection::CClientInfo *
0x1800639fe  mov     rcx, rax; this
0x180063a01  call    ?RegisterReader@CDVRFileCollection@@QEAAJPEAUCClientInfo@1@P6AXPEAXK_J2@Z1@Z; CDVRFileCollection::RegisterReader(CDVRFileCollection::CClientInfo *,void (*)(void *,ulong,__int64,__int64),void *)
0x180063a06  mov     ebx, eax
0x180063a08  mov     [rsp+0E8h+var_58], eax
0x180063a0f  test    eax, eax
0x180063a11  js      loc_180063818
0x180063a17  cmp     [rdi+1E0h], r14d
0x180063a1e  jz      loc_180063AAF
0x180063a24  mov     ecx, 20h ; ' '; Size
0x180063a29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063a2e  test    rax, rax
0x180063a31  jz      short loc_180063A4B
0x180063a33  mov     [rax], r13d
0x180063a36  mov     dword ptr [rax+4], 0FFFFFFFFh
0x180063a3d  mov     [rax+8], r14
0x180063a41  mov     [rax+10h], r14d
0x180063a45  mov     [rax+18h], r14
0x180063a49  jmp     short loc_180063A4E
0x180063a4b  mov     rax, r14
0x180063a4e  mov     [rdi+1D0h], rax
0x180063a55  test    rax, rax
0x180063a58  jz      loc_180063940
0x180063a5e  xor     r9d, r9d; int
0x180063a61  xor     r8d, r8d; void **
0x180063a64  xor     edx, edx; unsigned int
0x180063a66  mov     rcx, rax; this
0x180063a69  call    ?SetSids@CClientInfo@CDVRFileCollection@@QEAAJKPEAPEAXH@Z; CDVRFileCollection::CClientInfo::SetSids(ulong,void * *,int)
0x180063a6e  mov     ebx, eax
0x180063a70  mov     [rsp+0E8h+var_58], eax
0x180063a77  test    eax, eax
0x180063a79  js      loc_180063818
0x180063a7f  mov     r8d, [rsp+0E8h+arg_60]; int
0x180063a87  mov     rdx, r12; unsigned __int16 *
0x180063a8a  mov     rcx, rdi; this
0x180063a8d  call    ?AddAPermanentFile@CDVRReader@@IEAAJPEBGH@Z; CDVRReader::AddAPermanentFile(ushort const *,int)
0x180063a92  mov     ebx, eax
0x180063a94  mov     [rsp+0E8h+var_58], eax
0x180063a9b  test    eax, eax
0x180063a9d  js      loc_180063818
0x180063aa3  mov     dword ptr [rdi+120h], 0FFFFFFFFh
0x180063aad  jmp     short loc_180063AC4
  ... truncated ...
```
