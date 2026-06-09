# CNtSid::~CNtSid(void)

- ea: `0x180022ed0`
- end: `0x180022ef9`
- name: `??1CNtSid@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(CNtSid *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800454f8`
- `0x180045540`
- `0x180045590`
- `0x1800455b0`
- `0x1800457cc`
- `0x1800457de`
- `0x1800457f4`
- `0x18004587a`
- `0x18004588c`
- `0x1800465da`

## callees

- `0x180022ed0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022eed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022eed`

## pseudocode

```c
void __fastcall CNtSid::~CNtSid(LPVOID *this)
{
  if ( hHeap )
  {
    if ( *this )
      HeapFree(hHeap, 0, *this);
  }
}

```

## disassembly

```asm
0x180022ed0  sub     rsp, 28h
0x180022ed4  mov     r8, rcx
0x180022ed7  mov     rcx, cs:hHeap; hHeap
0x180022ede  test    rcx, rcx
0x180022ee1  jz      short loc_180022EF4
0x180022ee3  mov     r8, [r8]; lpMem
0x180022ee6  test    r8, r8
0x180022ee9  jz      short loc_180022EF4
0x180022eeb  xor     edx, edx; dwFlags
0x180022eed  call    cs:__imp_HeapFree
0x180022ef3  nop
0x180022ef4  add     rsp, 28h
0x180022ef8  retn
```
