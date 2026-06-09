# SmpUpdatePagingFileSizes

- ea: `0x14000d8ec`
- end: `0x14000d923`
- name: `SmpUpdatePagingFileSizes`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140010344`

## callees

- `0x14000d8ec`

## pseudocode

```c
bool __fastcall SmpUpdatePagingFileSizes(__int64 *a1, unsigned __int64 *a2)
{
  __int64 v2; // r9
  unsigned __int64 v3; // rax
  bool v4; // r8

  v2 = *a1;
  v3 = *a2;
  if ( (unsigned __int64)*a1 > 0xFFFFFFFF000LL )
    v2 = 0xFFFFFFFF000LL;
  v4 = (unsigned __int64)*a1 > 0xFFFFFFFF000LL;
  if ( v3 > 0xFFFFFFFF000LL )
  {
    v4 = 1;
    v3 = 0xFFFFFFFF000LL;
LABEL_6:
    *a1 = v2;
    *a2 = v3;
    return v4;
  }
  if ( (unsigned __int64)*a1 > 0xFFFFFFFF000LL )
    goto LABEL_6;
  return v4;
}

```

## disassembly

```asm
0x14000d8ec  mov     r9, [rcx]
0x14000d8ef  mov     r10, 0FFFFFFFF000h
0x14000d8f9  mov     rax, [rdx]
0x14000d8fc  cmp     r9, r10
0x14000d8ff  cmova   r9, r10
0x14000d903  setnbe  r8b
0x14000d907  cmp     rax, r10
0x14000d90a  jbe     short loc_14000D914
0x14000d90c  mov     r8b, 1
0x14000d90f  mov     rax, r10
0x14000d912  jmp     short loc_14000D919
0x14000d914  cmp     [rcx], r10
0x14000d917  jbe     short loc_14000D91F
0x14000d919  mov     [rcx], r9
0x14000d91c  mov     [rdx], rax
0x14000d91f  mov     al, r8b
0x14000d922  retn
```
