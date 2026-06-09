# SAL2::CSALFileSize::~CSALFileSize(void)

- ea: `0x180098614`
- end: `0x1800986f5`
- name: `??1CSALFileSize@SAL2@@MEAA@XZ`
- size: `225`
- prototype: `void __fastcall(SAL2::CSALFileSize *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180098750`

## callees

- `0x1800089b8`
- `0x18002573c`
- `0x1800621ec`
- `0x18008530c`
- `0x180098300`
- `0x180098614`
- `0x180099094`
- `0x1800993e8`
- `0x18009a560`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800986c4`
- `KERNEL32!DeleteCriticalSection` at `0x1800986c4`
- `KERNEL32!LeaveCriticalSection` at `0x180098670`
- `KERNEL32!LeaveCriticalSection` at `0x180098670`
- `KERNEL32!EnterCriticalSection` at `0x18009864f`
- `KERNEL32!EnterCriticalSection` at `0x18009864f`

## pseudocode

```c
void __fastcall SAL2::CSALFileSize::~CSALFileSize(SAL2::CSALFileSize *this)
{
  char *v2; // rbx
  bool v3; // zf
  void *v4; // r8

  *(_QWORD *)this = &SAL2::CSALFileSize::`vftable'{for `SAL2::CRefCounted'};
  v2 = (char *)this + 296;
  v3 = *((_QWORD *)this + 37) == 0;
  *((_QWORD *)this + 2) = &SAL2::CSALFileSize::`vftable'{for `SBEBasicTracers'};
  if ( !v3 )
  {
    EnterCriticalSection(&SAL2::CSALFileSize::g_globalWorkerLock);
    if ( !--SAL2::CSALFileSize::g_globalWorkerRef )
      SAL2::CSALFileSize::g_globalWorker = 0;
    LeaveCriticalSection(&SAL2::CSALFileSize::g_globalWorkerLock);
    SAL2::Release<SAL2::CSALFileSize::Worker *>(v2);
  }
  GrowFile::Uninitialize((SAL2::CSALFileSize *)((char *)this + 376));
  SAL2::CSALFileSize::SetFinalFileSize(this);
  SAL2::CloseHandle((SAL2::CSALFileSize *)((char *)this + 312), (void **)0xFFFFFFFFFFFFFFFFLL, v4);
  EhEtw::TPtr<IEhTraceSpan>::Release((char *)this + 288);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 280);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1872));
  GrowFile::~GrowFile((SAL2::CSALFileSize *)((char *)this + 376));
  SBEBasicTracers::~SBEBasicTracers((SAL2::CSALFileSize *)((char *)this + 16));
  *(_QWORD *)this = &SBFThunk::CStreamCtx::`vftable';
}

```

## disassembly

```asm
0x180098614  mov     [rsp+arg_8], rbx
0x180098619  mov     [rsp+arg_10], rsi
0x18009861e  push    rdi
0x18009861f  sub     rsp, 20h
0x180098623  lea     rax, ??_7CSALFileSize@SAL2@@6BCRefCounted@1@@; const SAL2::CSALFileSize::`vftable'{for `SAL2::CRefCounted'}
0x18009862a  mov     rdi, rcx
0x18009862d  mov     [rcx], rax
0x180098630  lea     rbx, [rcx+128h]
0x180098637  cmp     qword ptr [rbx], 0
0x18009863b  lea     rax, ??_7CSALFileSize@SAL2@@6BSBEBasicTracers@@@; const SAL2::CSALFileSize::`vftable'{for `SBEBasicTracers'}
0x180098642  mov     [rcx+10h], rax
0x180098646  jz      short loc_18009867E
0x180098648  lea     rcx, ?g_globalWorkerLock@CSALFileSize@SAL2@@0VCCritSec@@A; lpCriticalSection
0x18009864f  call    cs:__imp_EnterCriticalSection
0x180098655  add     cs:?g_globalWorkerRef@CSALFileSize@SAL2@@0KA, 0FFFFFFFFh; ulong SAL2::CSALFileSize::g_globalWorkerRef
0x18009865c  jnz     short loc_180098669
0x18009865e  mov     cs:?g_globalWorker@CSALFileSize@SAL2@@0PEAVWorker@12@EA, 0; SAL2::CSALFileSize::Worker * SAL2::CSALFileSize::g_globalWorker
0x180098669  lea     rcx, ?g_globalWorkerLock@CSALFileSize@SAL2@@0VCCritSec@@A; lpCriticalSection
0x180098670  call    cs:__imp_LeaveCriticalSection
0x180098676  mov     rcx, rbx
0x180098679  call    ??$Release@PEAVWorker@CSALFileSize@SAL2@@@SAL2@@YAXAEAPEAVWorker@CSALFileSize@0@@Z; SAL2::Release<SAL2::CSALFileSize::Worker *>(SAL2::CSALFileSize::Worker * &)
0x18009867e  lea     rbx, [rdi+178h]
0x180098685  mov     rcx, rbx; this
0x180098688  call    ?Uninitialize@GrowFile@@QEAAXXZ; GrowFile::Uninitialize(void)
0x18009868d  mov     rcx, rdi; this
0x180098690  call    ?SetFinalFileSize@CSALFileSize@SAL2@@QEAAJXZ; SAL2::CSALFileSize::SetFinalFileSize(void)
0x180098695  lea     rcx, [rdi+138h]; this
0x18009869c  or      rdx, 0FFFFFFFFFFFFFFFFh; void **
0x1800986a0  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x1800986a5  lea     rcx, [rdi+120h]
0x1800986ac  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800986b1  lea     rcx, [rdi+118h]
0x1800986b8  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800986bd  lea     rcx, [rdi+750h]; lpCriticalSection
0x1800986c4  call    cs:__imp_DeleteCriticalSection
0x1800986ca  mov     rcx, rbx; this
0x1800986cd  call    ??1GrowFile@@UEAA@XZ; GrowFile::~GrowFile(void)
0x1800986d2  lea     rcx, [rdi+10h]; this
0x1800986d6  call    ??1SBEBasicTracers@@UEAA@XZ; SBEBasicTracers::~SBEBasicTracers(void)
0x1800986db  mov     rbx, [rsp+28h+arg_8]
0x1800986e0  lea     rax, ??_7CStreamCtx@SBFThunk@@6B@; const SBFThunk::CStreamCtx::`vftable'
0x1800986e7  mov     rsi, [rsp+28h+arg_10]
0x1800986ec  mov     [rdi], rax
0x1800986ef  add     rsp, 20h
0x1800986f3  pop     rdi
0x1800986f4  retn
```
