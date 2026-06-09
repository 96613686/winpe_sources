# CTextNormMultiResult::~CTextNormMultiResult(void)

- ea: `0x180009218`
- end: `0x1800092c8`
- name: `??1CTextNormMultiResult@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(CTextNormMultiResult *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004cbc`

## callees

- `0x180001c50`
- `0x180004f5c`
- `0x180009218`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800092bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800092bc`

## pseudocode

```c
void __fastcall CTextNormMultiResult::~CTextNormMultiResult(CTextNormMultiResult *this)
{
  void *v1; // rdx
  void *v3; // rdx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  CSPPlex *v5; // rcx

  v1 = (void *)*((_QWORD *)this + 13);
  if ( v1 )
    CWinHeap::Free((CWinHeap *)&g_heap, v1);
  v3 = (void *)*((_QWORD *)this + 22);
  if ( v3 )
    CWinHeap::Free((CWinHeap *)&g_heap, v3);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 11);
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (CSPPlex *)*((_QWORD *)this + 20);
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( v5 )
  {
    CSPPlex::FreeDataChain(v5);
    *((_QWORD *)this + 20) = 0;
  }
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180009218  push    rbx
0x18000921a  sub     rsp, 20h
0x18000921e  mov     rdx, [rcx+68h]; void *
0x180009222  mov     rbx, rcx
0x180009225  test    rdx, rdx
0x180009228  jz      short loc_180009236
0x18000922a  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180009231  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180009236  mov     rdx, [rbx+0B0h]; void *
0x18000923d  test    rdx, rdx
0x180009240  jz      short loc_18000924E
0x180009242  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180009249  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000924e  mov     rcx, [rbx+58h]
0x180009252  test    rcx, rcx
0x180009255  jz      short loc_180009267
0x180009257  mov     rax, [rcx]
0x18000925a  mov     edx, 1
0x18000925f  mov     rax, [rax]
0x180009262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009267  mov     rcx, [rbx+0A0h]; this
0x18000926e  mov     dword ptr [rbx+90h], 0
0x180009278  mov     qword ptr [rbx+98h], 0
0x180009283  mov     qword ptr [rbx+88h], 0
0x18000928e  mov     qword ptr [rbx+80h], 0
0x180009299  test    rcx, rcx
0x18000929c  jz      short loc_1800092AE
0x18000929e  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x1800092a3  mov     qword ptr [rbx+0A0h], 0
0x1800092ae  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800092b2  cmp     byte ptr [rcx+28h], 0
0x1800092b6  jz      short loc_1800092C2
0x1800092b8  mov     byte ptr [rcx+28h], 0
0x1800092bc  call    cs:__imp_DeleteCriticalSection
0x1800092c2  add     rsp, 20h
0x1800092c6  pop     rbx
0x1800092c7  retn
```
