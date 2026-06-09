# CTokenActivation::~CTokenActivation(void)

- ea: `0x18001a404`
- end: `0x18001a5be`
- name: `??1CTokenActivation@@UEAA@XZ`
- size: `442`
- prototype: `void __fastcall(CTokenActivation *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a930`

## callees

- `0x180004288`
- `0x18001a010`
- `0x18001a134`
- `0x18001a404`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a41d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a45c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a49b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a41d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a45c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a49b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4b0`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a4da`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a4da`
- `SLC!SLClose` at `0x18001a566`
- `SLC!SLClose` at `0x18001a566`
- `sppcext!SLFreeTokenActivationCertificates` at `0x18001a520`
- `sppcext!SLFreeTokenActivationCertificates` at `0x18001a543`
- `sppcext!SLFreeTokenActivationCertificates` at `0x18001a520`
- `sppcext!SLFreeTokenActivationCertificates` at `0x18001a543`
- `sppcext!SLFreeTokenActivationGrants` at `0x18001a4fd`
- `sppcext!SLFreeTokenActivationGrants` at `0x18001a4fd`

## pseudocode

```c
void __fastcall CTokenActivation::~CTokenActivation(CTokenActivation *this)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  const CERT_CONTEXT *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx

  v1 = *((_QWORD *)this + 34);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 34) = 0;
  }
  v4 = *((_QWORD *)this + 33);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, (LPVOID)(v4 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 33) = 0;
  }
  v6 = *((_QWORD *)this + 32);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 32) = 0;
  }
  v8 = (const CERT_CONTEXT *)*((_QWORD *)this + 30);
  if ( v8 )
  {
    CertFreeCertificateContext(v8);
    *((_QWORD *)this + 30) = 0;
  }
  if ( *((_QWORD *)this + 29) )
  {
    SLFreeTokenActivationGrants();
    *((_QWORD *)this + 29) = 0;
  }
  if ( *((_QWORD *)this + 28) )
  {
    SLFreeTokenActivationCertificates();
    *((_QWORD *)this + 28) = 0;
  }
  if ( *((_QWORD *)this + 27) )
  {
    SLFreeTokenActivationCertificates();
    *((_QWORD *)this + 27) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 24);
  if ( v9 )
  {
    SLClose(v9);
    *((_QWORD *)this + 24) = 0;
  }
  SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>((char *)this + 152);
  v10 = *((_QWORD *)this + 18);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 18) = 0;
  }
  CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(this);
}

```

## disassembly

```asm
0x18001a404  mov     [rsp+arg_0], rbx
0x18001a409  push    rdi
0x18001a40a  sub     rsp, 20h
0x18001a40e  mov     rbx, [rcx+110h]
0x18001a415  mov     rdi, rcx
0x18001a418  test    rbx, rbx
0x18001a41b  jz      short loc_18001A450
0x18001a41d  call    cs:__imp_GetProcessHeap
0x18001a424  nop     dword ptr [rax+rax+00h]
0x18001a429  lea     r8, [rbx-4]; lpMem
0x18001a42d  xor     edx, edx; dwFlags
0x18001a42f  mov     rcx, rax; hHeap
0x18001a432  call    cs:__imp_HeapFree
0x18001a439  nop     dword ptr [rax+rax+00h]
0x18001a43e  xor     ecx, ecx
0x18001a440  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a445  mov     qword ptr [rdi+110h], 0
0x18001a450  mov     rbx, [rdi+108h]
0x18001a457  test    rbx, rbx
0x18001a45a  jz      short loc_18001A48F
0x18001a45c  call    cs:__imp_GetProcessHeap
0x18001a463  nop     dword ptr [rax+rax+00h]
0x18001a468  lea     r8, [rbx-4]; lpMem
0x18001a46c  xor     edx, edx; dwFlags
0x18001a46e  mov     rcx, rax; hHeap
0x18001a471  call    cs:__imp_HeapFree
0x18001a478  nop     dword ptr [rax+rax+00h]
0x18001a47d  xor     ecx, ecx
0x18001a47f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a484  mov     qword ptr [rdi+108h], 0
0x18001a48f  mov     rbx, [rdi+100h]
0x18001a496  test    rbx, rbx
0x18001a499  jz      short loc_18001A4CE
0x18001a49b  call    cs:__imp_GetProcessHeap
0x18001a4a2  nop     dword ptr [rax+rax+00h]
0x18001a4a7  lea     r8, [rbx-4]; lpMem
0x18001a4ab  xor     edx, edx; dwFlags
0x18001a4ad  mov     rcx, rax; hHeap
0x18001a4b0  call    cs:__imp_HeapFree
0x18001a4b7  nop     dword ptr [rax+rax+00h]
0x18001a4bc  xor     ecx, ecx
0x18001a4be  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001a4c3  mov     qword ptr [rdi+100h], 0
0x18001a4ce  mov     rcx, [rdi+0F0h]; pCertContext
0x18001a4d5  test    rcx, rcx
0x18001a4d8  jz      short loc_18001A4F1
0x18001a4da  call    cs:__imp_CertFreeCertificateContext
0x18001a4e1  nop     dword ptr [rax+rax+00h]
0x18001a4e6  mov     qword ptr [rdi+0F0h], 0
0x18001a4f1  mov     rcx, [rdi+0E8h]
0x18001a4f8  test    rcx, rcx
0x18001a4fb  jz      short loc_18001A514
0x18001a4fd  call    cs:__imp_SLFreeTokenActivationGrants
0x18001a504  nop     dword ptr [rax+rax+00h]
0x18001a509  mov     qword ptr [rdi+0E8h], 0
0x18001a514  mov     rcx, [rdi+0E0h]
0x18001a51b  test    rcx, rcx
0x18001a51e  jz      short loc_18001A537
0x18001a520  call    cs:__imp_SLFreeTokenActivationCertificates
0x18001a527  nop     dword ptr [rax+rax+00h]
0x18001a52c  mov     qword ptr [rdi+0E0h], 0
0x18001a537  mov     rcx, [rdi+0D8h]
0x18001a53e  test    rcx, rcx
0x18001a541  jz      short loc_18001A55A
0x18001a543  call    cs:__imp_SLFreeTokenActivationCertificates
0x18001a54a  nop     dword ptr [rax+rax+00h]
0x18001a54f  mov     qword ptr [rdi+0D8h], 0
0x18001a55a  mov     rcx, [rdi+0C0h]; hSLC
0x18001a561  test    rcx, rcx
0x18001a564  jz      short loc_18001A57D
0x18001a566  call    cs:__imp_SLClose
0x18001a56d  nop     dword ptr [rax+rax+00h]
0x18001a572  mov     qword ptr [rdi+0C0h], 0
0x18001a57d  lea     rcx, [rdi+98h]
0x18001a584  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x18001a589  mov     rcx, [rdi+90h]
0x18001a590  test    rcx, rcx
0x18001a593  jz      short loc_18001A5AC
0x18001a595  mov     rax, [rcx]
0x18001a598  mov     rax, [rax+10h]
0x18001a59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5a1  mov     qword ptr [rdi+90h], 0
0x18001a5ac  mov     rcx, rdi
0x18001a5af  mov     rbx, [rsp+28h+arg_0]
0x18001a5b4  add     rsp, 20h
0x18001a5b8  pop     rdi
0x18001a5b9  jmp     ??1?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@MEAA@XZ; CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::~CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>(void)
```
