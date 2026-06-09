# _tag_TOKEN_SCARD_READERSTATE::~_tag_TOKEN_SCARD_READERSTATE(void)

- ea: `0x1800370c0`
- end: `0x180037112`
- name: `??1_tag_TOKEN_SCARD_READERSTATE@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(_tag_TOKEN_SCARD_READERSTATE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036ed8`

## callees

- `0x180004288`
- `0x1800370c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800370d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800370d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800370eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800370eb`

## pseudocode

```c
void __fastcall _tag_TOKEN_SCARD_READERSTATE::~_tag_TOKEN_SCARD_READERSTATE(_tag_TOKEN_SCARD_READERSTATE *this)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *((_QWORD *)this + 8);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800370c0  mov     [rsp+arg_0], rbx
0x1800370c5  push    rdi
0x1800370c6  sub     rsp, 20h
0x1800370ca  mov     rbx, [rcx+40h]
0x1800370ce  mov     rdi, rcx
0x1800370d1  test    rbx, rbx
0x1800370d4  jz      short loc_180037106
0x1800370d6  call    cs:__imp_GetProcessHeap
0x1800370dd  nop     dword ptr [rax+rax+00h]
0x1800370e2  lea     r8, [rbx-4]; lpMem
0x1800370e6  xor     edx, edx; dwFlags
0x1800370e8  mov     rcx, rax; hHeap
0x1800370eb  call    cs:__imp_HeapFree
0x1800370f2  nop     dword ptr [rax+rax+00h]
0x1800370f7  xor     ecx, ecx
0x1800370f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800370fe  mov     qword ptr [rdi+40h], 0
0x180037106  mov     rbx, [rsp+28h+arg_0]
0x18003710b  add     rsp, 20h
0x18003710f  pop     rdi
0x180037110  retn
```
