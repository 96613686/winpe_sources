# CWdsTransportCollection::~CWdsTransportCollection(void)

- ea: `0x1800069e8`
- end: `0x180006a72`
- name: `??1CWdsTransportCollection@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(CWdsTransportCollection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006938`

## callees

- `0x180002bc4`
- `0x1800069e8`
- `0x180020010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a31`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006a31`
- `KERNEL32!DeleteCriticalSection` at `0x180006a4e`
- `KERNEL32!DeleteCriticalSection` at `0x180006a4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWdsTransportCollection::~CWdsTransportCollection(CWdsTransportCollection *this)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  void *v5; // rcx

  if ( *((_DWORD *)this + 29) )
  {
    v2 = 0;
    v3 = *((unsigned int *)this + 29);
    do
    {
      v4 = *(_QWORD *)(v2 + *((_QWORD *)this + 13));
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      v2 += 8;
      --v3;
    }
    while ( v3 );
  }
  v5 = (void *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    operator delete[](v5);
    *((_QWORD *)this + 13) = 0;
    *((_DWORD *)this + 29) = 0;
    *((_DWORD *)this + 28) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CWdsTransportCollection *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800069e8  mov     [rsp+arg_0], rbx
0x1800069ed  mov     [rsp+arg_8], rsi
0x1800069f2  push    rdi
0x1800069f3  sub     rsp, 20h
0x1800069f7  mov     rbx, rcx
0x1800069fa  cmp     dword ptr [rcx+74h], 0
0x1800069fe  jbe     short loc_180006A28
0x180006a00  xor     edi, edi
0x180006a02  mov     esi, [rcx+74h]
0x180006a05  mov     rax, [rbx+68h]
0x180006a09  mov     rcx, [rdi+rax]
0x180006a0d  test    rcx, rcx
0x180006a10  jz      short loc_180006A1E
0x180006a12  mov     rax, [rcx]
0x180006a15  mov     rax, [rax+10h]
0x180006a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1e  add     rdi, 8
0x180006a22  sub     rsi, 1
0x180006a26  jnz     short loc_180006A05
0x180006a28  mov     rcx, [rbx+68h]
0x180006a2c  test    rcx, rcx
0x180006a2f  jz      short loc_180006A4A
0x180006a31  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006a38  nop     dword ptr [rax+rax+00h]
0x180006a3d  and     qword ptr [rbx+68h], 0
0x180006a42  and     dword ptr [rbx+74h], 0
0x180006a46  and     dword ptr [rbx+70h], 0
0x180006a4a  lea     rcx, [rbx+40h]; lpCriticalSection
0x180006a4e  call    cs:__imp_DeleteCriticalSection
0x180006a55  nop     dword ptr [rax+rax+00h]
0x180006a5a  lea     rcx, [rbx+10h]; this
0x180006a5e  mov     rbx, [rsp+28h+arg_0]
0x180006a63  mov     rsi, [rsp+28h+arg_8]
0x180006a68  add     rsp, 20h
0x180006a6c  pop     rdi
0x180006a6d  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
