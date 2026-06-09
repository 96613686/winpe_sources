# CWSHRemote::EnumConnections(IEnumConnections * *)

- ea: `0x140002530`
- end: `0x140002569`
- name: `?EnumConnections@CWSHRemote@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, struct IEnumConnections **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002530`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000254c`
- `KERNEL32!GetCurrentThreadId` at `0x14000254c`

## pseudocode

```c
__int64 __fastcall CWSHRemote::EnumConnections(CWSHRemote *this, struct IEnumConnections **a2)
{
  int v3; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v5; // ecx

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v3 = *((_DWORD *)this + 4);
  CurrentThreadId = GetCurrentThreadId();
  v5 = -2147467263;
  if ( CurrentThreadId != v3 )
    return (unsigned int)-2147418113;
  return v5;
}

```

## disassembly

```asm
0x140002530  push    rbx
0x140002532  sub     rsp, 20h
0x140002536  test    rdx, rdx
0x140002539  jnz     short loc_140002542
0x14000253b  mov     eax, 80004003h
0x140002540  jmp     short loc_140002563
0x140002542  mov     qword ptr [rdx], 0
0x140002549  mov     ebx, [rcx+10h]
0x14000254c  call    cs:__imp_GetCurrentThreadId
0x140002552  mov     ecx, 80004001h
0x140002557  mov     edx, 8000FFFFh
0x14000255c  cmp     eax, ebx
0x14000255e  cmovnz  ecx, edx
0x140002561  mov     eax, ecx
0x140002563  add     rsp, 20h
0x140002567  pop     rbx
0x140002568  retn
```
