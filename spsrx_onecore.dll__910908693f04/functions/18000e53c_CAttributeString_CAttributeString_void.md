# CAttributeString::~CAttributeString(void)

- ea: `0x18000e53c`
- end: `0x18000e593`
- name: `??1CAttributeString@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CAttributeString *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009138`

## callees

- `0x180001c50`
- `0x18000e53c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e573`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000e573`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e587`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e587`

## pseudocode

```c
void __fastcall CAttributeString::~CAttributeString(CAttributeString *this)
{
  void *v1; // rdx
  void *v3; // rdx

  v1 = (void *)*((_QWORD *)this + 8);
  if ( v1 )
    CWinHeap::Free((CWinHeap *)&g_heap, v1);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    CWinHeap::Free((CWinHeap *)&g_heap, v3);
  free(*((void **)this + 11));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000e53c  push    rbx
0x18000e53e  sub     rsp, 20h
0x18000e542  mov     rdx, [rcx+40h]; void *
0x18000e546  mov     rbx, rcx
0x18000e549  test    rdx, rdx
0x18000e54c  jz      short loc_18000E55A
0x18000e54e  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000e555  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000e55a  mov     rdx, [rbx+48h]; void *
0x18000e55e  test    rdx, rdx
0x18000e561  jz      short loc_18000E56F
0x18000e563  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18000e56a  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18000e56f  mov     rcx, [rbx+58h]; Block
0x18000e573  call    cs:__imp_free
0x18000e579  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000e57d  cmp     byte ptr [rcx+28h], 0
0x18000e581  jz      short loc_18000E58D
0x18000e583  mov     byte ptr [rcx+28h], 0
0x18000e587  call    cs:__imp_DeleteCriticalSection
0x18000e58d  add     rsp, 20h
0x18000e591  pop     rbx
0x18000e592  retn
```
