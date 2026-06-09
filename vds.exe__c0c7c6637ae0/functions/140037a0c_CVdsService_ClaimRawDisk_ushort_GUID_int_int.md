# CVdsService::ClaimRawDisk(ushort *,_GUID &,int,int)

- ea: `0x140037a0c`
- end: `0x140037d78`
- name: `?ClaimRawDisk@CVdsService@@SAKPEAGAEAU_GUID@@HH@Z`
- size: `876`
- prototype: `__int64 __fastcall(wchar_t *lpFileName, struct _GUID *, int, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400074c0`
- `0x1400078a0`
- `0x140024360`
- `0x140026c0c`

## callees

- `0x14000d0f0`
- `0x14000f98c`
- `0x140025130`
- `0x140037320`
- `0x14003788c`
- `0x140037a0c`
- `0x140038314`
- `0x140038618`
- `0x14003c514`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037d2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037d2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037a8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037c7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037c7d`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140037c62`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140037c62`
- `vdsutil!OpenDevice` at `0x140037bfe`
- `vdsutil!OpenDevice` at `0x140037bfe`
- `vdsutil!?RegisterHandle@CVdsPnPNotificationBase@@QEAAKPEAXPEAPEAX@Z` at `0x140037c1d`
- `vdsutil!?RegisterHandle@CVdsPnPNotificationBase@@QEAAKPEAXPEAPEAX@Z` at `0x140037c1d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037a4e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037a4e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037d4d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037d4d`
- `vdsutil!VdsTraceW` at `0x140037aa8`
- `vdsutil!VdsTraceW` at `0x140037b5e`
- `vdsutil!VdsTraceW` at `0x140037c94`
- `vdsutil!VdsTraceW` at `0x140037cc1`
- `vdsutil!VdsTraceW` at `0x140037ce5`
- `vdsutil!VdsTraceW` at `0x140037d0c`
- `vdsutil!VdsTraceW` at `0x140037d21`
- `vdsutil!VdsTraceW` at `0x140037aa8`
- `vdsutil!VdsTraceW` at `0x140037b5e`
- `vdsutil!VdsTraceW` at `0x140037c94`
- `vdsutil!VdsTraceW` at `0x140037cc1`
- `vdsutil!VdsTraceW` at `0x140037ce5`
- `vdsutil!VdsTraceW` at `0x140037d0c`
- `vdsutil!VdsTraceW` at `0x140037d21`

## string_xrefs

- `0x140037a3e`: `CVdsService::ClaimRawDisk()`
- `0x140037a9c`: `CVdsService::ClaimRawDisk, 0, name=%s`
- `0x140037b0e`: `CVdsService::ClaimRawDisk, 1, name=%s, error=%ld`
- `0x140037b55`: `CVdsService::ClaimRawDisk, 1.1, name=%s, error=%ld`
- `0x140037b9b`: `CVdsService::ClaimRawDisk, 2, name=%s, error=%ld`
- `0x140037bd0`: `CVdsService::ClaimRawDisk, 3, name=%s, error=%ld`
- `0x140037cf4`: `CVdsService::ClaimRawDisk, 3.5, name=%s, error=%ld`
- `0x140037cfd`: `CVdsService::ClaimRawDisk, 3.7, name=%s, error=%ld`
- `0x140037d12`: `CVdsService::ClaimRawDisk, 4, name=%s, error=%ld`
- `0x140037c8b`: `CVdsService::ClaimRawDisk, 4.3, name=%s, error=%ld`
- `0x140037cdc`: `CVdsService::ClaimRawDisk, 4.4, name=%s, error=%ld`
- `0x140037ceb`: `CVdsService::ClaimRawDisk, 5, name=%s, error=%ld`
- `0x140037cb5`: `CVdsService::ClaimRawDisk, 6, name=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVdsService::ClaimRawDisk(wchar_t *lpFileName, struct _GUID *a2, int a3, int a4)
{
  struct CVdsRawDiskLun *RawDisk; // rax
  struct CVdsRawDiskLun *v9; // rsi
  __int64 v10; // rax
  __int64 LastError; // rbx
  unsigned int v12; // eax
  CVdsRawDiskLun *v13; // rsi
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  CVdsRawDiskLun *v20; // [rsp+20h] [rbp-39h] BYREF
  __int64 v21; // [rsp+28h] [rbp-31h] BYREF
  void *v22; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v23[16]; // [rsp+38h] [rbp-21h] BYREF
  __int128 v24; // [rsp+48h] [rbp-11h] BYREF
  __int128 v25; // [rsp+58h] [rbp-1h]
  __int128 v26; // [rsp+68h] [rbp+Fh] BYREF
  struct _GUID v27; // [rsp+78h] [rbp+1Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsService::ClaimRawDisk()");
  v22 = 0;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  v25 = 0;
  v21 = -1;
  v20 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( lpFileName )
  {
    VdsTraceW(3, L"CVdsService::ClaimRawDisk, 0, name=%s", lpFileName);
    RawDisk = CVdsService::FindRawDisk(lpFileName);
    v9 = RawDisk;
    if ( RawDisk )
    {
      v10 = *(_QWORD *)&a2->Data1 - *((_QWORD *)RawDisk + 15);
      if ( *(_QWORD *)&a2->Data1 == *((_QWORD *)v9 + 15) )
        v10 = *(_QWORD *)a2->Data4 - *((_QWORD *)v9 + 16);
      if ( v10 )
      {
        v27 = *(struct _GUID *)((char *)v9 + 120);
        CVdsService::RemoveUnallocatedDiskFromMap((struct CRtlEntry *)&v26);
        v12 = CVdsRawDiskLun::Initialize(v9, lpFileName, a2, a3);
        LODWORD(LastError) = v12;
        if ( v12 )
        {
          VdsTraceW(0, L"CVdsService::ClaimRawDisk, 1, name=%s, error=%ld", lpFileName, v12, v20);
        }
        else
        {
          v27 = *a2;
          *((_QWORD *)&v24 + 1) = 0;
          *(_QWORD *)&v25 = v9;
          LODWORD(v24) = 13;
          if ( !CVdsService::AddUnallocatedDiskToMap((struct CRtlEntry *)&v26, (struct CRtlEntry *)&v24) )
          {
            LastError = GetLastError();
            VdsTraceW(0, L"CVdsService::ClaimRawDisk, 1.1, name=%s, error=%ld", lpFileName, LastError);
          }
          if ( a4 )
          {
            *((_DWORD *)v9 + 85) = 1;
            *((_DWORD *)v9 + 34) = 0;
          }
        }
      }
      else
      {
        LODWORD(LastError) = 0;
      }
      goto LABEL_33;
    }
  }
  ATL::CComObject<CVdsRawDiskLun>::CreateInstance(&v20);
  v13 = v20;
  if ( !v20 )
  {
    LODWORD(LastError) = 8;
    v14 = L"CVdsService::ClaimRawDisk, 2, name=%s, error=%ld";
LABEL_32:
    VdsTraceW(0, v14, lpFileName, (unsigned int)LastError, v20);
    goto LABEL_33;
  }
  (*(void (__fastcall **)(CVdsRawDiskLun *))(*(_QWORD *)v20 + 8LL))(v20);
  v15 = CVdsRawDiskLun::Initialize(v13, lpFileName, a2, a3);
  LODWORD(LastError) = v15;
  if ( v15 )
  {
    VdsTraceW(0, L"CVdsService::ClaimRawDisk, 3, name=%s, error=%ld", lpFileName, v15, v20);
    goto LABEL_33;
  }
  if ( a4 )
  {
    *((_DWORD *)v13 + 85) = 1;
    *((_DWORD *)v13 + 34) = 0;
  }
  v16 = OpenDevice(lpFileName, 0, &v21);
  LODWORD(LastError) = v16;
  if ( v16 )
  {
    VdsTraceW(0, L"CVdsService::ClaimRawDisk, 3.7, name=%s, error=%ld", lpFileName, v16, v20);
    goto LABEL_31;
  }
  v17 = CVdsPnPNotificationBase::RegisterHandle(
          (CVdsPnPNotificationBase *)&CVdsService::m_PnPNotificationManager,
          (void *)v21,
          &v22);
  LODWORD(LastError) = v17;
  if ( v17 )
  {
    VdsTraceW(0, L"CVdsService::ClaimRawDisk, 3.5, name=%s, error=%ld", lpFileName, v17, v20);
LABEL_31:
    v14 = L"CVdsService::ClaimRawDisk, 4, name=%s, error=%ld";
    goto LABEL_32;
  }
  *((_QWORD *)v13 + 41) = v22;
  v27 = *(struct _GUID *)((char *)v13 + 120);
  *((_QWORD *)&v24 + 1) = 0;
  *(_QWORD *)&v25 = v13;
  LODWORD(v24) = 13;
  if ( CRtlMap::Find((CRtlMap *)CVdsService::m_mapUnallocatedDisks, (struct CRtlEntry *)&v26, 0) )
  {
    LODWORD(LastError) = -2147212259;
    VdsTraceW(0, L"CVdsService::ClaimRawDisk, 4.4, name=%s, error=%ld", lpFileName, 2147755037LL);
LABEL_28:
    v14 = L"CVdsService::ClaimRawDisk, 5, name=%s, error=%ld";
    goto LABEL_32;
  }
  if ( !CVdsService::AddUnallocatedDiskToMap((struct CRtlEntry *)&v26, (struct CRtlEntry *)&v24) )
  {
    LastError = GetLastError();
    VdsTraceW(0, L"CVdsService::ClaimRawDisk, 4.3, name=%s, error=%ld", lpFileName, LastError);
    if ( (_DWORD)LastError )
      goto LABEL_28;
  }
  if ( dword_14009B190 )
  {
    v18 = CVdsService::AddLunIdToMap(lpFileName);
    VdsTraceW(3, L"CVdsService::ClaimRawDisk, 6, name=%s, hr=%lX", lpFileName, v18);
  }
  v20 = 0;
LABEL_33:
  LeaveCriticalSection(&g_GlobalCriticalSection);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v20);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v21);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140037a0c  mov     [rsp-8+arg_18], rbx
0x140037a11  push    rbp
0x140037a12  push    rsi
0x140037a13  push    rdi
0x140037a14  push    r14
0x140037a16  push    r15
0x140037a18  lea     rbp, [rsp-37h]
0x140037a1d  sub     rsp, 90h
0x140037a24  mov     rax, cs:__security_cookie
0x140037a2b  xor     rax, rsp
0x140037a2e  mov     [rbp+57h+var_28], rax
0x140037a32  mov     r15d, r9d
0x140037a35  mov     ebx, r8d
0x140037a38  mov     r14, rdx
0x140037a3b  mov     rdi, rcx
0x140037a3e  lea     r8, aCvdsserviceCla_0; "CVdsService::ClaimRawDisk()"
0x140037a45  mov     edx, 5Eh ; '^'
0x140037a4a  lea     rcx, [rbp+57h+var_78]
0x140037a4e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140037a54  nop
0x140037a55  mov     [rbp+57h+var_80], 0
0x140037a5d  xorps   xmm0, xmm0
0x140037a60  movups  [rbp+57h+var_48], xmm0
0x140037a64  movups  [rbp+57h+var_38], xmm0
0x140037a68  xorps   xmm1, xmm1
0x140037a6b  movups  [rbp+57h+var_68], xmm1
0x140037a6f  movups  [rbp+57h+var_58], xmm1
0x140037a73  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x140037a7b  mov     [rbp+57h+var_90], 0
0x140037a83  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140037a8a  call    cs:__imp_EnterCriticalSection
0x140037a90  test    rdi, rdi
0x140037a93  jz      loc_140037B86
0x140037a99  mov     r8, rdi
0x140037a9c  lea     rdx, aCvdsserviceCla_10; "CVdsService::ClaimRawDisk, 0, name=%s"
0x140037aa3  mov     ecx, 3
0x140037aa8  call    cs:__imp_VdsTraceW
0x140037aae  mov     rcx, rdi; String1
0x140037ab1  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z; CVdsService::FindRawDisk(ushort *)
0x140037ab6  mov     rsi, rax
0x140037ab9  test    rax, rax
0x140037abc  jz      loc_140037B86
0x140037ac2  mov     rax, [r14]
0x140037ac5  sub     rax, [rsi+78h]
0x140037ac9  jnz     short loc_140037AD6
0x140037acb  mov     rax, [r14+8]
0x140037acf  sub     rax, [rsi+80h]
0x140037ad6  test    rax, rax
0x140037ad9  jnz     short loc_140037AE2
0x140037adb  xor     ebx, ebx
0x140037add  jmp     loc_140037D27
0x140037ae2  movups  xmm0, xmmword ptr [rsi+78h]
0x140037ae6  movdqu  [rbp+57h+var_38], xmm0
0x140037aeb  lea     rcx, [rbp+57h+var_48]; struct CRtlEntry *
0x140037aef  call    ?RemoveUnallocatedDiskFromMap@CVdsService@@CAXAEAVCRtlEntry@@@Z; CVdsService::RemoveUnallocatedDiskFromMap(CRtlEntry &)
0x140037af4  mov     r9d, ebx; int
0x140037af7  mov     r8, r14; struct _GUID *
0x140037afa  mov     rdx, rdi; unsigned __int16 *
0x140037afd  mov     rcx, rsi; this
0x140037b00  call    ?Initialize@CVdsRawDiskLun@@QEAAKPEAGAEAU_GUID@@H@Z; CVdsRawDiskLun::Initialize(ushort *,_GUID &,int)
0x140037b05  mov     ebx, eax
0x140037b07  test    eax, eax
0x140037b09  jz      short loc_140037B1A
0x140037b0b  mov     r9d, eax
0x140037b0e  lea     rdx, aCvdsserviceCla_15; "CVdsService::ClaimRawDisk, 1, name=%s, "...
0x140037b15  jmp     loc_140037D1C
0x140037b1a  movups  xmm0, xmmword ptr [r14]
0x140037b1e  movdqu  [rbp+57h+var_38], xmm0
0x140037b23  mov     qword ptr [rbp+57h+var_68+8], 0
0x140037b2b  mov     qword ptr [rbp+57h+var_58], rsi
0x140037b2f  mov     dword ptr [rbp+57h+var_68], 0Dh
0x140037b36  lea     rdx, [rbp+57h+var_68]; struct CRtlEntry *
0x140037b3a  lea     rcx, [rbp+57h+var_48]; struct CRtlEntry *
0x140037b3e  call    ?AddUnallocatedDiskToMap@CVdsService@@CAHAEAVCRtlEntry@@0@Z; CVdsService::AddUnallocatedDiskToMap(CRtlEntry &,CRtlEntry &)
0x140037b43  test    eax, eax
0x140037b45  jnz     short loc_140037B64
0x140037b47  call    cs:__imp_GetLastError
0x140037b4d  mov     ebx, eax
0x140037b4f  mov     r9d, eax
0x140037b52  mov     r8, rdi
0x140037b55  lea     rdx, aCvdsserviceCla_5; "CVdsService::ClaimRawDisk, 1.1, name=%s"...
0x140037b5c  xor     ecx, ecx
0x140037b5e  call    cs:__imp_VdsTraceW
0x140037b64  test    r15d, r15d
0x140037b67  jz      loc_140037D27
0x140037b6d  mov     dword ptr [rsi+154h], 1
0x140037b77  mov     dword ptr [rsi+88h], 0
0x140037b81  jmp     loc_140037D27
0x140037b86  lea     rcx, [rbp+57h+var_90]
0x140037b8a  call    ?CreateInstance@?$CComObject@VCVdsRawDiskLun@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsRawDiskLun>::CreateInstance(ATL::CComObject<CVdsRawDiskLun> * *)
0x140037b8f  mov     rsi, [rbp+57h+var_90]
0x140037b93  test    rsi, rsi
0x140037b96  jnz     short loc_140037BA7
0x140037b98  lea     ebx, [rsi+8]
0x140037b9b  lea     rdx, aCvdsserviceCla_11; "CVdsService::ClaimRawDisk, 2, name=%s, "...
0x140037ba2  jmp     loc_140037D19
0x140037ba7  mov     rax, [rsi]
0x140037baa  mov     rcx, rsi
0x140037bad  mov     rax, [rax+8]
0x140037bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037bb6  mov     r9d, ebx; int
0x140037bb9  mov     r8, r14; struct _GUID *
0x140037bbc  mov     rdx, rdi; unsigned __int16 *
0x140037bbf  mov     rcx, rsi; this
0x140037bc2  call    ?Initialize@CVdsRawDiskLun@@QEAAKPEAGAEAU_GUID@@H@Z; CVdsRawDiskLun::Initialize(ushort *,_GUID &,int)
0x140037bc7  mov     ebx, eax
0x140037bc9  test    eax, eax
0x140037bcb  jz      short loc_140037BDC
0x140037bcd  mov     r9d, eax
0x140037bd0  lea     rdx, aCvdsserviceCla_1; "CVdsService::ClaimRawDisk, 3, name=%s, "...
0x140037bd7  jmp     loc_140037D1C
0x140037bdc  test    r15d, r15d
0x140037bdf  jz      short loc_140037BF5
0x140037be1  mov     dword ptr [rsi+154h], 1
0x140037beb  mov     dword ptr [rsi+88h], 0
0x140037bf5  lea     r8, [rbp+57h+var_88]
0x140037bf9  xor     edx, edx
0x140037bfb  mov     rcx, rdi
0x140037bfe  call    cs:__imp_OpenDevice
0x140037c04  mov     ebx, eax
0x140037c06  test    eax, eax
0x140037c08  jnz     loc_140037CFD
0x140037c0e  lea     r8, [rbp+57h+var_80]
0x140037c12  mov     rdx, [rbp+57h+var_88]
0x140037c16  lea     rcx, ?m_PnPNotificationManager@CVdsService@@2VCVdsPnPNotificationManager@@A; CVdsPnPNotificationManager CVdsService::m_PnPNotificationManager
0x140037c1d  call    cs:__imp_?RegisterHandle@CVdsPnPNotificationBase@@QEAAKPEAXPEAPEAX@Z; CVdsPnPNotificationBase::RegisterHandle(void *,void * *)
0x140037c23  mov     ebx, eax
0x140037c25  test    eax, eax
0x140037c27  jnz     loc_140037CF4
0x140037c2d  mov     rax, [rbp+57h+var_80]
0x140037c31  mov     [rsi+148h], rax
0x140037c38  movups  xmm0, xmmword ptr [rsi+78h]
0x140037c3c  movdqu  [rbp+57h+var_38], xmm0
0x140037c41  mov     qword ptr [rbp+57h+var_68+8], 0
0x140037c49  mov     qword ptr [rbp+57h+var_58], rsi
0x140037c4d  mov     dword ptr [rbp+57h+var_68], 0Dh
0x140037c54  xor     r8d, r8d
0x140037c57  lea     rdx, [rbp+57h+var_48]
0x140037c5b  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x140037c62  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x140037c68  test    eax, eax
0x140037c6a  jnz     short loc_140037CD1
0x140037c6c  lea     rdx, [rbp+57h+var_68]; struct CRtlEntry *
0x140037c70  lea     rcx, [rbp+57h+var_48]; struct CRtlEntry *
0x140037c74  call    ?AddUnallocatedDiskToMap@CVdsService@@CAHAEAVCRtlEntry@@0@Z; CVdsService::AddUnallocatedDiskToMap(CRtlEntry &,CRtlEntry &)
0x140037c79  test    eax, eax
0x140037c7b  jnz     short loc_140037C9E
0x140037c7d  call    cs:__imp_GetLastError
0x140037c83  mov     ebx, eax
0x140037c85  mov     r9d, eax
0x140037c88  mov     r8, rdi
0x140037c8b  lea     rdx, aCvdsserviceCla_6; "CVdsService::ClaimRawDisk, 4.3, name=%s"...
0x140037c92  xor     ecx, ecx
0x140037c94  call    cs:__imp_VdsTraceW
0x140037c9a  test    ebx, ebx
0x140037c9c  jnz     short loc_140037CEB
0x140037c9e  cmp     cs:dword_14009B190, 0
0x140037ca5  jz      short loc_140037CC7
0x140037ca7  mov     rcx, rdi; lpFileName
0x140037caa  call    ?AddLunIdToMap@CVdsService@@CAJPEAG@Z; CVdsService::AddLunIdToMap(ushort *)
0x140037caf  mov     r9d, eax
0x140037cb2  mov     r8, rdi
0x140037cb5  lea     rdx, aCvdsserviceCla_3; "CVdsService::ClaimRawDisk, 6, name=%s, "...
0x140037cbc  mov     ecx, 3
0x140037cc1  call    cs:__imp_VdsTraceW
0x140037cc7  mov     [rbp+57h+var_90], 0
0x140037ccf  jmp     short loc_140037D27
0x140037cd1  mov     ebx, 8004241Dh
0x140037cd6  mov     r9d, ebx
0x140037cd9  mov     r8, rdi
0x140037cdc  lea     rdx, aCvdsserviceCla_7; "CVdsService::ClaimRawDisk, 4.4, name=%s"...
0x140037ce3  xor     ecx, ecx
0x140037ce5  call    cs:__imp_VdsTraceW
0x140037ceb  lea     rdx, aCvdsserviceCla_4; "CVdsService::ClaimRawDisk, 5, name=%s, "...
0x140037cf2  jmp     short loc_140037D19
0x140037cf4  lea     rdx, aCvdsserviceCla_17; "CVdsService::ClaimRawDisk, 3.5, name=%s"...
0x140037cfb  jmp     short loc_140037D04
0x140037cfd  lea     rdx, aCvdsserviceCla_9; "CVdsService::ClaimRawDisk, 3.7, name=%s"...
0x140037d04  mov     r9d, eax
0x140037d07  mov     r8, rdi
0x140037d0a  xor     ecx, ecx
0x140037d0c  call    cs:__imp_VdsTraceW
0x140037d12  lea     rdx, aCvdsserviceCla_8; "CVdsService::ClaimRawDisk, 4, name=%s, "...
0x140037d19  mov     r9d, ebx
0x140037d1c  mov     r8, rdi
0x140037d1f  xor     ecx, ecx
0x140037d21  call    cs:__imp_VdsTraceW
0x140037d27  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140037d2e  call    cs:__imp_LeaveCriticalSection
0x140037d34  nop
0x140037d35  lea     rcx, [rbp+57h+var_90]
0x140037d39  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140037d3e  nop
0x140037d3f  lea     rcx, [rbp+57h+var_88]
0x140037d43  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140037d48  nop
0x140037d49  lea     rcx, [rbp+57h+var_78]
0x140037d4d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140037d53  mov     eax, ebx
0x140037d55  mov     rcx, [rbp+57h+var_28]
0x140037d59  xor     rcx, rsp; StackCookie
0x140037d5c  call    __security_check_cookie
0x140037d61  mov     rbx, [rsp+0B0h+arg_18]
0x140037d69  add     rsp, 90h
0x140037d70  pop     r15
0x140037d72  pop     r14
0x140037d74  pop     rdi
0x140037d75  pop     rsi
0x140037d76  pop     rbp
0x140037d77  retn
```
