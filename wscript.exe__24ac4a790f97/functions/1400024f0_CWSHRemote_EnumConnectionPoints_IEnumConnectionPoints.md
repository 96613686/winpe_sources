# CWSHRemote::EnumConnectionPoints(IEnumConnectionPoints * *)

- ea: `0x1400024f0`
- end: `0x140002529`
- name: `?EnumConnectionPoints@CWSHRemote@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct IEnumConnectionPoints **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400024f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000250c`
- `KERNEL32!GetCurrentThreadId` at `0x14000250c`

## pseudocode

```c
__int64 __fastcall CWSHRemote::EnumConnectionPoints(CWSHRemote *this, struct IEnumConnectionPoints **a2)
{
  int v3; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v5; // ecx

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v3 = *((_DWORD *)this + 6);
  CurrentThreadId = GetCurrentThreadId();
  v5 = -2147467263;
  if ( CurrentThreadId != v3 )
    return (unsigned int)-2147418113;
  return v5;
}

```

## disassembly

```asm
0x1400024f0  push    rbx
0x1400024f2  sub     rsp, 20h
0x1400024f6  test    rdx, rdx
0x1400024f9  jnz     short loc_140002502
0x1400024fb  mov     eax, 80004003h
0x140002500  jmp     short loc_140002523
0x140002502  mov     qword ptr [rdx], 0
0x140002509  mov     ebx, [rcx+18h]
0x14000250c  call    cs:__imp_GetCurrentThreadId
0x140002512  mov     ecx, 80004001h
0x140002517  mov     edx, 8000FFFFh
0x14000251c  cmp     eax, ebx
0x14000251e  cmovnz  ecx, edx
0x140002521  mov     eax, ecx
0x140002523  add     rsp, 20h
0x140002527  pop     rbx
0x140002528  retn
```
