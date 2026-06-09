# OncRpcBufMgrStartup

- ea: `0x140001520`
- end: `0x1400015e3`
- name: `OncRpcBufMgrStartup`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140024b80`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000154e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001584`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400015ba`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000154e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140001584`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400015ba`

## pseudocode

```c
__int64 OncRpcBufMgrStartup()
{
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0xA0u, 0x43426458u, 0);
  ExInitializeNPagedLookasideList(&stru_14001A580, 0, 0, 0x200u, 0x8B0u, 0x44426458u, 0);
  ExInitializeNPagedLookasideList(&stru_14001A600, 0, 0, 0x200u, 0x68u, 0x44426458u, 0);
  qword_14001A4C8 = (__int64)&OncRpcGlobals;
  OncRpcGlobals = (__int64)&OncRpcGlobals;
  return 0;
}

```

## disassembly

```asm
0x140001520  sub     rsp, 48h
0x140001524  xor     eax, eax
0x140001526  lea     rcx, Lookaside; Lookaside
0x14000152d  mov     [rsp+48h+Depth], ax; Depth
0x140001532  mov     r9d, 200h; Flags
0x140001538  mov     [rsp+48h+Tag], 43426458h; Tag
0x140001540  xor     r8d, r8d; Free
0x140001543  xor     edx, edx; Allocate
0x140001545  mov     [rsp+48h+Size], 0A0h; Size
0x14000154e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140001555  nop     dword ptr [rax+rax+00h]
0x14000155a  xor     eax, eax
0x14000155c  lea     rcx, stru_14001A580; Lookaside
0x140001563  mov     [rsp+48h+Depth], ax; Depth
0x140001568  mov     r9d, 200h; Flags
0x14000156e  mov     [rsp+48h+Tag], 44426458h; Tag
0x140001576  xor     r8d, r8d; Free
0x140001579  xor     edx, edx; Allocate
0x14000157b  mov     [rsp+48h+Size], 8B0h; Size
0x140001584  call    cs:__imp_ExInitializeNPagedLookasideList
0x14000158b  nop     dword ptr [rax+rax+00h]
0x140001590  xor     eax, eax
0x140001592  lea     rcx, stru_14001A600; Lookaside
0x140001599  mov     [rsp+48h+Depth], ax; Depth
0x14000159e  mov     r9d, 200h; Flags
0x1400015a4  mov     [rsp+48h+Tag], 44426458h; Tag
0x1400015ac  xor     r8d, r8d; Free
0x1400015af  xor     edx, edx; Allocate
0x1400015b1  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x1400015ba  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400015c1  nop     dword ptr [rax+rax+00h]
0x1400015c6  lea     rax, OncRpcGlobals
0x1400015cd  mov     cs:qword_14001A4C8, rax
0x1400015d4  mov     cs:OncRpcGlobals, rax
0x1400015db  xor     eax, eax
0x1400015dd  add     rsp, 48h
0x1400015e1  retn
```
