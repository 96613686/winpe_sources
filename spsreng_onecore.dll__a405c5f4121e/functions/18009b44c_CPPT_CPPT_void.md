# CPPT::~CPPT(void)

- ea: `0x18009b44c`
- end: `0x18009b688`
- name: `??1CPPT@@QEAA@XZ`
- size: `572`
- prototype: `void __fastcall(CPPT *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005b974`

## callees

- `0x180002aac`
- `0x180006abc`
- `0x18009b44c`
- `0x18009b69c`
- `0x18009b6c4`
- `0x1800a1fb4`
- `0x1800a23e0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b46a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b503`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b503`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009b497`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009b497`

## pseudocode

```c
void __fastcall CPPT::~CPPT(CPPT *this)
{
  void *v2; // rdx
  CWinHeap *v3; // rcx
  void *v4; // rdx
  CWinHeap *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax
  void *v8; // rdx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  unsigned int v10; // edx
  CUgtreeHeap *v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // r8
  CSsidStore *v15; // rcx

  *(_QWORD *)this = &CPPT::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 295));
  CWinHeap::Free(*((CWinHeap **)this + 1), *((void **)this + 298));
  CWinHeap::Free(*((CWinHeap **)this + 1), *((void **)this + 299));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  CWinHeap::Free(*((CWinHeap **)this + 1), *((void **)this + 75));
  v2 = (void *)*((_QWORD *)this + 94);
  v3 = (CWinHeap *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 75) = 0;
  CWinHeap::Free(v3, v2);
  v4 = (void *)*((_QWORD *)this + 93);
  v5 = (CWinHeap *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 94) = 0;
  CWinHeap::Free(v5, v4);
  *((_QWORD *)this + 93) = 0;
  CPronDict::DestroyBuffers((CPPT *)((char *)this + 80));
  v6 = (void *)*((_QWORD *)this + 99);
  if ( v6 )
    CloseHandle(v6);
  CWinHeap::Free((CWinHeap *)&g_heap, *((void **)this + 9));
  v7 = *((_QWORD *)this + 80);
  if ( !v7 || !*(_QWORD *)(v7 + 8) )
  {
    v8 = (void *)*((_QWORD *)this + 8);
    if ( v8 )
    {
      CWinHeap::Free(*((CWinHeap **)this + 1), v8);
      *((_QWORD *)this + 8) = 0;
    }
  }
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v9 )
    (**v9)(v9, 1);
  CWinHeap::Free(*((CWinHeap **)this + 1), *((void **)this + 67));
  v11 = (CUgtreeHeap *)*((_QWORD *)this + 88);
  if ( v11 )
    CUgtreeHeap::`scalar deleting destructor'(v11, v10);
  v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 81);
  if ( v12 )
    (**v12)(v12, 1);
  v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 80);
  v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 77);
  if ( v14 != v13 )
  {
    if ( v14 )
    {
      (**v14)(*((_QWORD *)this + 77), 1);
      v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 80);
    }
    *((_QWORD *)this + 77) = 0;
  }
  if ( v13 )
    (**v13)(v13, 1);
  v15 = (CSsidStore *)*((_QWORD *)this + 307);
  *((_QWORD *)this + 80) = 0;
  if ( v15 )
    CSsidStore::`scalar deleting destructor'(v15, v10);
  *((_QWORD *)this + 307) = 0;
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 2424));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 2400));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 576));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 488));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 456));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 408));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 368));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPPT *)((char *)this + 328));
  CPronDict::~CPronDict((CPPT *)((char *)this + 80));
}

```

## disassembly

```asm
0x18009b44c  mov     [rsp+arg_0], rbx
0x18009b451  push    rdi
0x18009b452  sub     rsp, 20h
0x18009b456  lea     rax, ??_7CPPT@@6B@; const CPPT::`vftable'
0x18009b45d  mov     rbx, rcx
0x18009b460  mov     [rcx], rax
0x18009b463  mov     rcx, [rcx+938h]; pv
0x18009b46a  call    cs:__imp_CoTaskMemFree
0x18009b470  mov     rdx, [rbx+950h]; void *
0x18009b477  mov     rcx, [rbx+8]; this
0x18009b47b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b480  mov     rdx, [rbx+958h]; void *
0x18009b487  mov     rcx, [rbx+8]; this
0x18009b48b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b490  lea     rcx, [rbx+298h]; lpCriticalSection
0x18009b497  call    cs:__imp_DeleteCriticalSection
0x18009b49d  mov     rdx, [rbx+258h]; void *
0x18009b4a4  mov     rcx, [rbx+8]; this
0x18009b4a8  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b4ad  mov     rdx, [rbx+2F0h]; void *
0x18009b4b4  mov     rcx, [rbx+8]; this
0x18009b4b8  mov     qword ptr [rbx+258h], 0
0x18009b4c3  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b4c8  mov     rdx, [rbx+2E8h]; void *
0x18009b4cf  mov     rcx, [rbx+8]; this
0x18009b4d3  mov     qword ptr [rbx+2F0h], 0
0x18009b4de  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b4e3  lea     rcx, [rbx+50h]; this
0x18009b4e7  mov     qword ptr [rbx+2E8h], 0
0x18009b4f2  call    ?DestroyBuffers@CPronDict@@QEAAJXZ; CPronDict::DestroyBuffers(void)
0x18009b4f7  mov     rcx, [rbx+318h]; hObject
0x18009b4fe  test    rcx, rcx
0x18009b501  jz      short loc_18009B509
0x18009b503  call    cs:__imp_CloseHandle
0x18009b509  mov     rdx, [rbx+48h]; void *
0x18009b50d  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18009b514  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b519  mov     rax, [rbx+280h]
0x18009b520  test    rax, rax
0x18009b523  jz      short loc_18009B52C
0x18009b525  cmp     qword ptr [rax+8], 0
0x18009b52a  jnz     short loc_18009B546
0x18009b52c  mov     rdx, [rbx+40h]; void *
0x18009b530  test    rdx, rdx
0x18009b533  jz      short loc_18009B546
0x18009b535  mov     rcx, [rbx+8]; this
0x18009b539  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b53e  mov     qword ptr [rbx+40h], 0
0x18009b546  mov     rcx, [rbx+10h]
0x18009b54a  test    rcx, rcx
0x18009b54d  jz      short loc_18009B55F
0x18009b54f  mov     rax, [rcx]
0x18009b552  mov     edx, 1
0x18009b557  mov     rax, [rax]
0x18009b55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b55f  mov     rdx, [rbx+218h]; void *
0x18009b566  mov     rcx, [rbx+8]; this
0x18009b56a  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18009b56f  mov     rcx, [rbx+2C0h]; this
0x18009b576  test    rcx, rcx
0x18009b579  jz      short loc_18009B580
0x18009b57b  call    ??_GCUgtreeHeap@@QEAAPEAXI@Z; CUgtreeHeap::`scalar deleting destructor'(uint)
0x18009b580  mov     rcx, [rbx+288h]
0x18009b587  test    rcx, rcx
0x18009b58a  jz      short loc_18009B59C
0x18009b58c  mov     rax, [rcx]
0x18009b58f  mov     edx, 1
0x18009b594  mov     rax, [rax]
0x18009b597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b59c  mov     rcx, [rbx+280h]
0x18009b5a3  mov     r8, [rbx+268h]
0x18009b5aa  cmp     r8, rcx
0x18009b5ad  jz      short loc_18009B5D9
0x18009b5af  test    r8, r8
0x18009b5b2  jz      short loc_18009B5CE
0x18009b5b4  mov     rax, [r8]
0x18009b5b7  mov     edx, 1
0x18009b5bc  mov     rcx, r8
0x18009b5bf  mov     rax, [rax]
0x18009b5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b5c7  mov     rcx, [rbx+280h]
0x18009b5ce  mov     qword ptr [rbx+268h], 0
0x18009b5d9  test    rcx, rcx
0x18009b5dc  jz      short loc_18009B5EE
0x18009b5de  mov     rax, [rcx]
0x18009b5e1  mov     edx, 1
0x18009b5e6  mov     rax, [rax]
0x18009b5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b5ee  mov     rcx, [rbx+998h]; this
0x18009b5f5  mov     qword ptr [rbx+280h], 0
0x18009b600  test    rcx, rcx
0x18009b603  jz      short loc_18009B60A
0x18009b605  call    ??_GCSsidStore@@QEAAPEAXI@Z; CSsidStore::`scalar deleting destructor'(uint)
0x18009b60a  lea     rcx, [rbx+978h]; this
0x18009b611  mov     qword ptr [rbx+998h], 0
0x18009b61c  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b621  lea     rcx, [rbx+960h]; this
0x18009b628  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b62d  lea     rcx, [rbx+240h]; this
0x18009b634  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b639  lea     rcx, [rbx+1E8h]; this
0x18009b640  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b645  lea     rcx, [rbx+1C8h]; this
0x18009b64c  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b651  lea     rcx, [rbx+198h]; this
0x18009b658  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b65d  lea     rcx, [rbx+170h]; this
0x18009b664  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b669  lea     rcx, [rbx+148h]; this
0x18009b670  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18009b675  lea     rcx, [rbx+50h]; this
0x18009b679  mov     rbx, [rsp+28h+arg_0]
0x18009b67e  add     rsp, 20h
0x18009b682  pop     rdi
0x18009b683  jmp     ??1CPronDict@@QEAA@XZ; CPronDict::~CPronDict(void)
```
