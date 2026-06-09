# CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::~CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>(void)

- ea: `0x180044fc8`
- end: `0x18004508e`
- name: `??1?$CDlpTransportImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800461f0`
- `0x1800465c0`

## callees

- `0x18001fd60`
- `0x180044d28`
- `0x180044fc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044fe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044fe1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044ff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044ff0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045018`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045035`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045052`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004506f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045018`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045035`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045052`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004506f`

## pseudocode

```c
void __fastcall CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::~CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *(_QWORD *)(a1 + 448);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *(_QWORD *)(a1 + 448) = 0;
  }
  if ( *(_DWORD *)(a1 + 440) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 400));
    *(_DWORD *)(a1 + 440) = 0;
  }
  if ( *(_DWORD *)(a1 + 376) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 336));
    *(_DWORD *)(a1 + 376) = 0;
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 272));
    *(_DWORD *)(a1 + 312) = 0;
  }
  if ( *(_DWORD *)(a1 + 256) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 216));
    *(_DWORD *)(a1 + 256) = 0;
  }
  CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>::~CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>(a1);
}

```

## disassembly

```asm
0x180044fc8  mov     [rsp+arg_0], rbx
0x180044fcd  push    rdi
0x180044fce  sub     rsp, 20h
0x180044fd2  mov     rbx, [rcx+1C0h]
0x180044fd9  mov     rdi, rcx
0x180044fdc  test    rbx, rbx
0x180044fdf  jz      short loc_180045008
0x180044fe1  call    cs:__imp_GetProcessHeap
0x180044fe7  lea     r8, [rbx-4]; lpMem
0x180044feb  xor     edx, edx; dwFlags
0x180044fed  mov     rcx, rax; hHeap
0x180044ff0  call    cs:__imp_HeapFree
0x180044ff6  xor     ecx, ecx
0x180044ff8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180044ffd  mov     qword ptr [rdi+1C0h], 0
0x180045008  lea     rbx, [rdi+190h]
0x18004500f  cmp     dword ptr [rbx+28h], 0
0x180045013  jz      short loc_180045025
0x180045015  mov     rcx, rbx; lpCriticalSection
0x180045018  call    cs:__imp_DeleteCriticalSection
0x18004501e  mov     dword ptr [rbx+28h], 0
0x180045025  lea     rbx, [rdi+150h]
0x18004502c  cmp     dword ptr [rbx+28h], 0
0x180045030  jz      short loc_180045042
0x180045032  mov     rcx, rbx; lpCriticalSection
0x180045035  call    cs:__imp_DeleteCriticalSection
0x18004503b  mov     dword ptr [rbx+28h], 0
0x180045042  lea     rbx, [rdi+110h]
0x180045049  cmp     dword ptr [rbx+28h], 0
0x18004504d  jz      short loc_18004505F
0x18004504f  mov     rcx, rbx; lpCriticalSection
0x180045052  call    cs:__imp_DeleteCriticalSection
0x180045058  mov     dword ptr [rbx+28h], 0
0x18004505f  lea     rbx, [rdi+0D8h]
0x180045066  cmp     dword ptr [rbx+28h], 0
0x18004506a  jz      short loc_18004507C
0x18004506c  mov     rcx, rbx; lpCriticalSection
0x18004506f  call    cs:__imp_DeleteCriticalSection
0x180045075  mov     dword ptr [rbx+28h], 0
0x18004507c  mov     rcx, rdi
0x18004507f  mov     rbx, [rsp+28h+arg_0]
0x180045084  add     rsp, 20h
0x180045088  pop     rdi
0x180045089  jmp     ??1?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@UEAA@XZ; CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>::~CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>(void)
```
