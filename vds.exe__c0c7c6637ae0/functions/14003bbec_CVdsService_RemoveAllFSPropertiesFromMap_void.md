# CVdsService::RemoveAllFSPropertiesFromMap(void)

- ea: `0x14003bbec`
- end: `0x14003bca2`
- name: `?RemoveAllFSPropertiesFromMap@CVdsService@@QEAAXXZ`
- size: `182`
- prototype: `void __fastcall(CVdsService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140036f88`

## callees

- `0x14003bbec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003bc5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003bc5b`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003bc85`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003bc85`
- `vdsutil!VdsHeapFree` at `0x14003bc69`
- `vdsutil!VdsHeapFree` at `0x14003bc69`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bc0a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bc0a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bc91`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003bc91`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003bc74`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003bc74`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003bc2c`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003bc2c`

## string_xrefs

- `0x14003bbf9`: `RemoveAllFSPropertiesFromMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsService::RemoveAllFSPropertiesFromMap(CVdsService *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE v5[16]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v6; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-28h]
  _BYTE v8[32]; // [rsp+48h] [rbp-20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v5, 0x5Eu, "RemoveAllFSPropertiesFromMap");
  v6 = 0;
  v7 = 0;
  v2 = CRtlMap::Begin((char *)this + 304, v8);
  v6 = *(_OWORD *)v2;
  v7 = *(_QWORD *)(v2 + 16);
  while ( (_QWORD)v6 && *((_QWORD *)&v6 + 1) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)&v6 + 1) + 48LL);
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v3);
    CRtlMapIter::Next((CRtlMapIter *)&v6);
  }
  CRtlMap::RemoveAll((CVdsService *)((char *)this + 304), 0);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v5);
}

```

## disassembly

```asm
0x14003bbec  mov     [rsp+arg_0], rbx
0x14003bbf1  push    rdi
0x14003bbf2  sub     rsp, 60h
0x14003bbf6  mov     rdi, rcx
0x14003bbf9  lea     r8, aRemoveallfspro; "RemoveAllFSPropertiesFromMap"
0x14003bc00  mov     edx, 5Eh ; '^'
0x14003bc05  lea     rcx, [rsp+68h+var_48]
0x14003bc0a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003bc10  nop
0x14003bc11  xorps   xmm0, xmm0
0x14003bc14  xor     eax, eax
0x14003bc16  movups  [rsp+68h+var_38], xmm0
0x14003bc1b  mov     [rsp+68h+var_28], rax
0x14003bc20  lea     rdx, [rsp+68h+var_20]
0x14003bc25  lea     rcx, [rdi+130h]
0x14003bc2c  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003bc32  movups  xmm0, xmmword ptr [rax]
0x14003bc35  movups  [rsp+68h+var_38], xmm0
0x14003bc3a  movsd   xmm1, qword ptr [rax+10h]
0x14003bc3f  movsd   [rsp+68h+var_28], xmm1
0x14003bc45  cmp     qword ptr [rsp+68h+var_38], 0
0x14003bc4b  jz      short loc_14003BC7C
0x14003bc4d  mov     rbx, qword ptr [rsp+68h+var_38+8]
0x14003bc52  test    rbx, rbx
0x14003bc55  jz      short loc_14003BC7C
0x14003bc57  mov     rbx, [rbx+30h]
0x14003bc5b  call    cs:__imp_GetProcessHeap
0x14003bc61  mov     rcx, rax
0x14003bc64  mov     r8, rbx
0x14003bc67  xor     edx, edx
0x14003bc69  call    cs:__imp_VdsHeapFree
0x14003bc6f  lea     rcx, [rsp+68h+var_38]
0x14003bc74  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003bc7a  jmp     short loc_14003BC45
0x14003bc7c  xor     edx, edx
0x14003bc7e  lea     rcx, [rdi+130h]
0x14003bc85  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x14003bc8b  nop
0x14003bc8c  lea     rcx, [rsp+68h+var_48]
0x14003bc91  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003bc97  mov     rbx, [rsp+68h+arg_0]
0x14003bc9c  add     rsp, 60h
0x14003bca0  pop     rdi
0x14003bca1  retn
```
