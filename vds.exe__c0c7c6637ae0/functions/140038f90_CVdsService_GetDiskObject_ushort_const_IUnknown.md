# CVdsService::GetDiskObject(ushort const *,IUnknown * *)

- ea: `0x140038f90`
- end: `0x14003929a`
- name: `?GetDiskObject@CVdsService@@UEAAJPEBGPEAPEAUIUnknown@@@Z`
- size: `778`
- prototype: `int(CVdsService *__hidden this, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140001980`
- `0x140003710`
- `0x140004360`
- `0x140038f90`
- `0x140039dec`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14003915b`
- `vdsutil!VdsTraceEx` at `0x140039192`
- `vdsutil!VdsTraceEx` at `0x1400391c7`
- `vdsutil!VdsTraceEx` at `0x1400391e8`
- `vdsutil!VdsTraceEx` at `0x140039250`
- `vdsutil!VdsTraceEx` at `0x14003915b`
- `vdsutil!VdsTraceEx` at `0x140039192`
- `vdsutil!VdsTraceEx` at `0x1400391c7`
- `vdsutil!VdsTraceEx` at `0x1400391e8`
- `vdsutil!VdsTraceEx` at `0x140039250`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039090`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039090`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x1400390a9`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x1400390a9`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x1400390d6`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x1400390d6`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140039165`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x140039165`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038fcc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039076`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140038fcc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039076`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400391ab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039280`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400391ab`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039280`

## string_xrefs

- `0x14003914f`: `CVdsService::GetObjectFromProviders, 4, %lX`
- `0x140038fb8`: `CVdsService::GetDiskObject()`
- `0x1400391b8`: `CVdsService::GetDiskObject, 1, hr=%lX`
- `0x1400391de`: `CVdsService::GetDiskObject, 2, hr=%lX`
- `0x140039244`: `CVdsService::GetDiskObject, 3`
- `0x140039068`: `CVdsService::GetDiskFromSwProviders()`
- `0x1400390ff`: `CVdsService::GetDiskFromSwProviders, 2, %lX`
- `0x140039186`: `CVdsService::GetDiskFromSwProviders, 3, %lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsService::GetDiskObject(CVdsService *this, const unsigned __int16 *a2, struct IUnknown **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  signed int RawDiskByDeviceID; // ebx
  CVdsService *v8; // rcx
  __int64 (__fastcall ***EntryPointer)(void *, GUID *, __int64 *); // rax
  int v10; // eax
  struct IUnknown *v11; // rax
  struct IUnknown *Wrapper; // rbx
  struct IUnknown *v13; // rcx
  struct IUnknown *v15; // [rsp+20h] [rbp-59h] BYREF
  __int64 v16; // [rsp+28h] [rbp-51h] BYREF
  int v17; // [rsp+30h] [rbp-49h]
  __int64 v18; // [rsp+38h] [rbp-41h] BYREF
  struct IUnknown *v19; // [rsp+40h] [rbp-39h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-31h] BYREF
  __int128 Buf2; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v22[16]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v23[16]; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v24[64]; // [rsp+90h] [rbp+17h] BYREF

  v15 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsService::GetDiskObject()");
  if ( !a2 || !a3 )
  {
    RawDiskByDeviceID = -2147024809;
    goto LABEL_36;
  }
  *a3 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  RawDiskByDeviceID = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 7) + 32LL))((char *)this - 56);
  if ( RawDiskByDeviceID >= 0 )
  {
    v16 = 0;
    v17 = 0;
    RawDiskByDeviceID = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v16);
    if ( RawDiskByDeviceID < 0 )
      goto LABEL_5;
    RawDiskByDeviceID = CVdsService::GetRawDiskByDeviceID(v8, a2, &v15);
    if ( RawDiskByDeviceID >= 0 )
      goto LABEL_26;
    v18 = 0;
    v19 = 0;
    Buf1 = 0;
    CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsService::GetDiskFromSwProviders()");
    v15 = 0;
    for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstSoftwareProviders, &Buf2);
          ;
          CRtlListIter::Next((CRtlListIter *)&Buf1) )
    {
      Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstSoftwareProviders, v24);
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        RawDiskByDeviceID = 0;
        v11 = v15;
        goto LABEL_22;
      }
      EntryPointer = (__int64 (__fastcall ***)(void *, GUID *, __int64 *))CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
      v10 = (**EntryPointer)(EntryPointer, &IID_IVdsSwProviderPrivateGetDisk, &v18);
      if ( v10 >= 0 )
      {
        if ( !v18 )
        {
          RawDiskByDeviceID = -2147212216;
          VdsTraceEx(94, 0, "CVdsService::GetDiskFromSwProviders, 3, %lX", -2147212216);
          goto LABEL_24;
        }
        RawDiskByDeviceID = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IUnknown **))(*(_QWORD *)v18 + 24LL))(
                              v18,
                              a2,
                              &v19);
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v18 = 0;
        }
        if ( RawDiskByDeviceID != -2147212283 )
        {
          if ( RawDiskByDeviceID >= 0 )
          {
            v11 = v19;
            v15 = v19;
            if ( RawDiskByDeviceID )
              goto LABEL_24;
LABEL_22:
            if ( !v11 )
              RawDiskByDeviceID = -2147212283;
LABEL_24:
            CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
            if ( RawDiskByDeviceID < 0 )
            {
              VdsTraceEx(94, 1, "CVdsService::GetDiskObject, 1, hr=%lX", RawDiskByDeviceID);
LABEL_5:
              CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
              break;
            }
LABEL_26:
            if ( v15 )
            {
              Wrapper = CVdsService::FindOrCreateWrapper(v6, v15, VDS_OT_DISK, 0);
              v13 = v15;
              if ( v15 )
              {
                ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
                v13 = 0;
                v15 = 0;
              }
              if ( Wrapper )
              {
                *a3 = Wrapper;
                CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
                RawDiskByDeviceID = 0;
              }
              else
              {
                if ( v13 )
                {
                  ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
                  v15 = 0;
                }
                VdsTraceEx(94, 0, "CVdsService::GetDiskObject, 3");
                CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
                RawDiskByDeviceID = -2147024882;
              }
            }
            else
            {
              VdsTraceEx(94, 0, "CVdsService::GetDiskObject, 2, hr=%lX", RawDiskByDeviceID);
              CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
              RawDiskByDeviceID = -2147212283;
            }
            break;
          }
          VdsTraceEx(94, 0, "CVdsService::GetObjectFromProviders, 4, %lX", (unsigned int)RawDiskByDeviceID);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsService::GetDiskFromSwProviders, 2, %lX", (unsigned int)v10);
      }
    }
  }
LABEL_36:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  return (unsigned int)RawDiskByDeviceID;
}

```

## disassembly

```asm
0x140038f90  push    rbp
0x140038f92  push    rbx
0x140038f93  push    rsi
0x140038f94  push    rdi
0x140038f95  push    r12
0x140038f97  push    r13
0x140038f99  push    r14
0x140038f9b  lea     rbp, [rsp-27h]
0x140038fa0  sub     rsp, 0A0h
0x140038fa7  mov     rdi, r8
0x140038faa  mov     rsi, rdx
0x140038fad  mov     rbx, rcx
0x140038fb0  mov     [rbp+57h+var_B0], 0
0x140038fb8  lea     r8, aCvdsserviceGet_2; "CVdsService::GetDiskObject()"
0x140038fbf  mov     r12d, 5Eh ; '^'
0x140038fc5  mov     edx, r12d
0x140038fc8  lea     rcx, [rbp+57h+var_50]
0x140038fcc  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140038fd2  nop
0x140038fd3  test    rsi, rsi
0x140038fd6  jz      loc_140039277
0x140038fdc  test    rdi, rdi
0x140038fdf  jz      loc_140039277
0x140038fe5  mov     qword ptr [rdi], 0
0x140038fec  lea     r14, [rbx-38h]
0x140038ff0  mov     rax, [r14]
0x140038ff3  mov     rcx, r14
0x140038ff6  mov     rax, [rax+20h]
0x140038ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038fff  mov     ebx, eax
0x140039001  test    eax, eax
0x140039003  js      loc_14003927C
0x140039009  mov     [rbp+57h+var_A8], 0
0x140039011  mov     [rbp+57h+var_A0], 0
0x140039018  lea     rcx, [rbp+57h+var_A8]; this
0x14003901c  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140039021  mov     ebx, eax
0x140039023  test    eax, eax
0x140039025  jns     short loc_140039035
0x140039027  lea     rcx, [rbp+57h+var_A8]; this
0x14003902b  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140039030  jmp     loc_14003927C
0x140039035  lea     r8, [rbp+57h+var_B0]; struct IUnknown **
0x140039039  mov     rdx, rsi; unsigned __int16 *
0x14003903c  call    ?GetRawDiskByDeviceID@CVdsService@@AEAAJPEBGPEAPEAUIUnknown@@@Z; CVdsService::GetRawDiskByDeviceID(ushort const *,IUnknown * *)
0x140039041  mov     ebx, eax
0x140039043  mov     r13d, 80042405h
0x140039049  test    eax, eax
0x14003904b  jns     loc_1400391D2
0x140039051  mov     [rbp+57h+var_98], 0
0x140039059  mov     [rbp+57h+var_90], 0
0x140039061  xorps   xmm0, xmm0
0x140039064  movups  [rbp+57h+Buf1], xmm0
0x140039068  lea     r8, aCvdsserviceGet_0; "CVdsService::GetDiskFromSwProviders()"
0x14003906f  mov     edx, r12d
0x140039072  lea     rcx, [rbp+57h+var_60]
0x140039076  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003907c  nop
0x14003907d  mov     [rbp+57h+var_B0], 0
0x140039085  lea     rdx, [rbp+57h+Buf2]
0x140039089  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x140039090  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x140039096  movups  xmm0, xmmword ptr [rax]
0x140039099  movdqu  [rbp+57h+Buf1], xmm0
0x14003909e  lea     rdx, [rbp+57h+var_40]
0x1400390a2  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; CRtlList CVdsService::m_lstSoftwareProviders
0x1400390a9  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x1400390af  movups  xmm0, xmmword ptr [rax]
0x1400390b2  movdqu  [rbp+57h+Buf2], xmm0
0x1400390b7  mov     r8d, 10h; Size
0x1400390bd  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1400390c1  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1400390c5  call    memcmp_0
0x1400390ca  test    eax, eax
0x1400390cc  jz      loc_14003919A
0x1400390d2  lea     rcx, [rbp+57h+Buf1]
0x1400390d6  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x1400390dc  mov     r9, rax
0x1400390df  mov     rcx, [rax]
0x1400390e2  mov     rax, [rcx]
0x1400390e5  lea     r8, [rbp+57h+var_98]
0x1400390e9  lea     rdx, IID_IVdsSwProviderPrivateGetDisk
0x1400390f0  mov     rcx, r9
0x1400390f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400390f8  test    eax, eax
0x1400390fa  jns     short loc_140039108
0x1400390fc  mov     r9d, eax
0x1400390ff  lea     r8, aCvdsserviceGet_115; "CVdsService::GetDiskFromSwProviders, 2,"...
0x140039106  jmp     short loc_140039156
0x140039108  mov     rcx, [rbp+57h+var_98]
0x14003910c  test    rcx, rcx
0x14003910f  jz      short loc_14003917E
0x140039111  mov     rax, [rcx]
0x140039114  lea     r8, [rbp+57h+var_90]
0x140039118  mov     rdx, rsi
0x14003911b  mov     rax, [rax+18h]
0x14003911f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039124  mov     ebx, eax
0x140039126  mov     rcx, [rbp+57h+var_98]
0x14003912a  test    rcx, rcx
0x14003912d  jz      short loc_140039143
0x14003912f  mov     rax, [rcx]
0x140039132  mov     rax, [rax+10h]
0x140039136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003913b  mov     [rbp+57h+var_98], 0
0x140039143  cmp     ebx, r13d
0x140039146  jz      short loc_140039161
0x140039148  test    ebx, ebx
0x14003914a  jns     short loc_140039170
0x14003914c  mov     r9d, ebx
0x14003914f  lea     r8, aCvdsserviceGet_26; "CVdsService::GetObjectFromProviders, 4,"...
0x140039156  xor     edx, edx
0x140039158  mov     ecx, r12d
0x14003915b  call    cs:__imp_VdsTraceEx
0x140039161  lea     rcx, [rbp+57h+Buf1]
0x140039165  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003916b  jmp     loc_14003909E
0x140039170  mov     rax, [rbp+57h+var_90]
0x140039174  mov     [rbp+57h+var_B0], rax
0x140039178  test    ebx, ebx
0x14003917a  jnz     short loc_1400391A7
0x14003917c  jmp     short loc_1400391A0
0x14003917e  mov     ebx, 80042448h
0x140039183  mov     r9d, ebx
0x140039186  lea     r8, aCvdsserviceGet_30; "CVdsService::GetDiskFromSwProviders, 3,"...
0x14003918d  xor     edx, edx
0x14003918f  mov     ecx, r12d
0x140039192  call    cs:__imp_VdsTraceEx
0x140039198  jmp     short loc_1400391A7
0x14003919a  xor     ebx, ebx
0x14003919c  mov     rax, [rbp+57h+var_B0]
0x1400391a0  test    rax, rax
0x1400391a3  cmovz   ebx, r13d
0x1400391a7  lea     rcx, [rbp+57h+var_60]
0x1400391ab  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400391b1  test    ebx, ebx
0x1400391b3  jns     short loc_1400391D2
0x1400391b5  mov     r9d, ebx
0x1400391b8  lea     r8, aCvdsserviceGet_138; "CVdsService::GetDiskObject, 1, hr=%lX"
0x1400391bf  mov     edx, 1
0x1400391c4  mov     ecx, r12d
0x1400391c7  call    cs:__imp_VdsTraceEx
0x1400391cd  jmp     loc_140039027
0x1400391d2  mov     rdx, [rbp+57h+var_B0]; struct IUnknown *
0x1400391d6  test    rdx, rdx
0x1400391d9  jnz     short loc_1400391FD
0x1400391db  mov     r9d, ebx
0x1400391de  lea     r8, aCvdsserviceGet_89; "CVdsService::GetDiskObject, 2, hr=%lX"
0x1400391e5  mov     ecx, r12d
0x1400391e8  call    cs:__imp_VdsTraceEx
0x1400391ee  nop
0x1400391ef  lea     rcx, [rbp+57h+var_A8]; this
0x1400391f3  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400391f8  mov     ebx, r13d
0x1400391fb  jmp     short loc_14003927C
0x1400391fd  xor     r9d, r9d; unsigned int **
0x140039200  lea     r8d, [r9+0Dh]; enum _VDS_OBJECT_TYPE
0x140039204  mov     rcx, r14; this
0x140039207  call    ?FindOrCreateWrapper@CVdsService@@QEAAPEAUIUnknown@@PEAU2@W4_VDS_OBJECT_TYPE@@PEAPEAK@Z; CVdsService::FindOrCreateWrapper(IUnknown *,_VDS_OBJECT_TYPE,ulong * *)
0x14003920c  mov     rbx, rax
0x14003920f  mov     rcx, [rbp+57h+var_B0]
0x140039213  test    rcx, rcx
0x140039216  jz      short loc_14003922A
0x140039218  mov     rdx, [rcx]
0x14003921b  mov     rax, [rdx+10h]
0x14003921f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039224  xor     ecx, ecx
0x140039226  mov     [rbp+57h+var_B0], rcx
0x14003922a  test    rbx, rbx
0x14003922d  jnz     short loc_140039267
0x14003922f  test    rcx, rcx
0x140039232  jz      short loc_140039244
0x140039234  mov     rax, [rcx]
0x140039237  mov     rax, [rax+10h]
0x14003923b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039240  mov     [rbp+57h+var_B0], rbx
0x140039244  lea     r8, aCvdsserviceGet_82; "CVdsService::GetDiskObject, 3"
0x14003924b  xor     edx, edx
0x14003924d  mov     ecx, r12d
0x140039250  call    cs:__imp_VdsTraceEx
0x140039256  nop
0x140039257  lea     rcx, [rbp+57h+var_A8]; this
0x14003925b  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140039260  mov     ebx, 8007000Eh
0x140039265  jmp     short loc_14003927C
0x140039267  mov     [rdi], rbx
0x14003926a  lea     rcx, [rbp+57h+var_A8]; this
0x14003926e  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140039273  xor     ebx, ebx
0x140039275  jmp     short loc_14003927C
0x140039277  mov     ebx, 80070057h
0x14003927c  lea     rcx, [rbp+57h+var_50]
0x140039280  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140039286  mov     eax, ebx
0x140039288  add     rsp, 0A0h
0x14003928f  pop     r14
0x140039291  pop     r13
0x140039293  pop     r12
0x140039295  pop     rdi
0x140039296  pop     rsi
0x140039297  pop     rbx
0x140039298  pop     rbp
0x140039299  retn
```
