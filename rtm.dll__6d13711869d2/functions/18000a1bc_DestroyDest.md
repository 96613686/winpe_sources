# DestroyDest

- ea: `0x18000a1bc`
- end: `0x18000a227`
- name: `DestroyDest`
- size: `107`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dd0`
- `0x180003730`
- `0x180003a20`
- `0x1800060a0`
- `0x180006990`
- `0x180007220`
- `0x1800072f0`
- `0x180007350`
- `0x180008910`
- `0x18000a230`
- `0x18000a298`
- `0x18000b440`

## callees

- `0x18000a1bc`
- `0x18000b294`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a201`
- `KERNEL32!GetProcessHeap` at `0x18000a201`
- `KERNEL32!HeapFree` at `0x18000a20f`
- `KERNEL32!HeapFree` at `0x18000a20f`

## pseudocode

```c
__int64 __fastcall DestroyDest(LPVOID *lpMem)
{
  __int64 i; // rsi
  HANDLE ProcessHeap; // rax

  for ( i = 0; (unsigned int)i < *((_DWORD *)lpMem[15] + 11); i = (unsigned int)(i + 1) )
  {
    DestroyRouteList(lpMem[3 * i + 16]);
    lpMem[3 * i + 16] = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
  return 0;
}

```

## disassembly

```asm
0x18000a1bc  mov     [rsp+arg_0], rbx
0x18000a1c1  mov     [rsp+arg_8], rsi
0x18000a1c6  push    rdi
0x18000a1c7  sub     rsp, 20h
0x18000a1cb  mov     rax, [rcx+78h]
0x18000a1cf  xor     esi, esi
0x18000a1d1  mov     rdi, rcx
0x18000a1d4  cmp     [rax+2Ch], esi
0x18000a1d7  jbe     short loc_18000A201
0x18000a1d9  lea     rbx, [rsi+rsi*2]
0x18000a1dd  mov     rcx, [rdi+rbx*8+80h]; lpMem
0x18000a1e5  call    DestroyRouteList
0x18000a1ea  mov     qword ptr [rdi+rbx*8+80h], 0
0x18000a1f6  inc     esi
0x18000a1f8  mov     rax, [rdi+78h]
0x18000a1fc  cmp     esi, [rax+2Ch]
0x18000a1ff  jb      short loc_18000A1D9
0x18000a201  call    cs:__imp_GetProcessHeap
0x18000a207  mov     r8, rdi; lpMem
0x18000a20a  xor     edx, edx; dwFlags
0x18000a20c  mov     rcx, rax; hHeap
0x18000a20f  call    cs:__imp_HeapFree
0x18000a215  mov     rbx, [rsp+28h+arg_0]
0x18000a21a  xor     eax, eax
0x18000a21c  mov     rsi, [rsp+28h+arg_8]
0x18000a221  add     rsp, 20h
0x18000a225  pop     rdi
0x18000a226  retn
```
