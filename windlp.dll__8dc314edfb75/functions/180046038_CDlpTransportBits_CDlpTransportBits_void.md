# CDlpTransportBits::~CDlpTransportBits(void)

- ea: `0x180046038`
- end: `0x18004612c`
- name: `??1CDlpTransportBits@@UEAA@XZ`
- size: `244`
- prototype: `void __fastcall(CDlpTransportBits *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046b40`

## callees

- `0x180044f28`
- `0x180046038`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046074`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004608c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046074`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004608c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460a4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800460ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046058`

## pseudocode

```c
void __fastcall CDlpTransportBits::~CDlpTransportBits(CDlpTransportBits *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 73);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 73) = 0;
  }
  if ( *((_DWORD *)this + 144) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
    *((_DWORD *)this + 144) = 0;
  }
  if ( *((_DWORD *)this + 128) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
    *((_DWORD *)this + 128) = 0;
  }
  if ( *((_DWORD *)this + 112) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 408));
    *((_DWORD *)this + 112) = 0;
  }
  if ( *((_DWORD *)this + 96) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
    *((_DWORD *)this + 96) = 0;
  }
  if ( *((_DWORD *)this + 82) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
    *((_DWORD *)this + 82) = 0;
  }
  if ( *((_DWORD *)this + 68) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    *((_DWORD *)this + 68) = 0;
  }
  v3 = *((_QWORD *)this + 26);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 26) = 0;
  }
  CDlpErrorImpl<CUnknownRefChainImpl<IDlpTransport>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpTransport>>((__int64)this);
}

```

## disassembly

```asm
0x180046038  mov     [rsp+arg_0], rbx
0x18004603d  mov     [rsp+arg_8], rsi
0x180046042  push    rdi
0x180046043  sub     rsp, 20h
0x180046047  mov     rbx, rcx
0x18004604a  mov     rcx, [rcx+248h]; hObject
0x180046051  xor     esi, esi
0x180046053  test    rcx, rcx
0x180046056  jz      short loc_180046065
0x180046058  call    cs:__imp_CloseHandle
0x18004605e  mov     [rbx+248h], rsi
0x180046065  lea     rdi, [rbx+218h]
0x18004606c  cmp     [rdi+28h], esi
0x18004606f  jz      short loc_18004607D
0x180046071  mov     rcx, rdi; lpCriticalSection
0x180046074  call    cs:__imp_DeleteCriticalSection
0x18004607a  mov     [rdi+28h], esi
0x18004607d  lea     rdi, [rbx+1D8h]
0x180046084  cmp     [rdi+28h], esi
0x180046087  jz      short loc_180046095
0x180046089  mov     rcx, rdi; lpCriticalSection
0x18004608c  call    cs:__imp_DeleteCriticalSection
0x180046092  mov     [rdi+28h], esi
0x180046095  lea     rdi, [rbx+198h]
0x18004609c  cmp     [rdi+28h], esi
0x18004609f  jz      short loc_1800460AD
0x1800460a1  mov     rcx, rdi; lpCriticalSection
0x1800460a4  call    cs:__imp_DeleteCriticalSection
0x1800460aa  mov     [rdi+28h], esi
0x1800460ad  lea     rdi, [rbx+158h]
0x1800460b4  cmp     [rdi+28h], esi
0x1800460b7  jz      short loc_1800460C5
0x1800460b9  mov     rcx, rdi; lpCriticalSection
0x1800460bc  call    cs:__imp_DeleteCriticalSection
0x1800460c2  mov     [rdi+28h], esi
0x1800460c5  lea     rdi, [rbx+120h]
0x1800460cc  cmp     [rdi+28h], esi
0x1800460cf  jz      short loc_1800460DD
0x1800460d1  mov     rcx, rdi; lpCriticalSection
0x1800460d4  call    cs:__imp_DeleteCriticalSection
0x1800460da  mov     [rdi+28h], esi
0x1800460dd  lea     rdi, [rbx+0E8h]
0x1800460e4  cmp     [rdi+28h], esi
0x1800460e7  jz      short loc_1800460F5
0x1800460e9  mov     rcx, rdi; lpCriticalSection
0x1800460ec  call    cs:__imp_DeleteCriticalSection
0x1800460f2  mov     [rdi+28h], esi
0x1800460f5  mov     rcx, [rbx+0D0h]
0x1800460fc  test    rcx, rcx
0x1800460ff  jz      short loc_180046115
0x180046101  mov     rax, [rcx]
0x180046104  mov     rax, [rax+10h]
0x180046108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004610d  nop
0x18004610e  mov     [rbx+0D0h], rsi
0x180046115  mov     rcx, rbx
0x180046118  mov     rbx, [rsp+28h+arg_0]
0x18004611d  mov     rsi, [rsp+28h+arg_8]
0x180046122  add     rsp, 20h
0x180046126  pop     rdi
0x180046127  jmp     ??1?$CDlpErrorImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@UEAA@XZ; CDlpErrorImpl<CUnknownRefChainImpl<IDlpTransport>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpTransport>>(void)
```
