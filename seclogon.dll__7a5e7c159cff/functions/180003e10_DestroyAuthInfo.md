# DestroyAuthInfo

- ea: `0x180003e10`
- end: `0x180003e51`
- name: `DestroyAuthInfo`
- size: `65`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002110`
- `0x180003fec`

## callees

- `0x180003e10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e4a`

## pseudocode

```c
BOOL __fastcall DestroyAuthInfo(__int64 a1, __int64 a2)
{
  _BYTE *v2; // rax
  __int64 v4; // rcx
  HANDLE ProcessHeap; // rax

  v2 = *(_BYTE **)(a2 + 48);
  if ( v2 )
  {
    v4 = *(unsigned __int16 *)(a2 + 40);
    if ( *(_WORD *)(a2 + 40) )
    {
      do
      {
        *v2++ = 0;
        --v4;
      }
      while ( v4 );
    }
  }
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, (LPVOID)a2);
}

```

## disassembly

```asm
0x180003e10  push    rbx
0x180003e12  sub     rsp, 20h
0x180003e16  mov     rax, [rdx+30h]
0x180003e1a  mov     rbx, rdx
0x180003e1d  test    rax, rax
0x180003e20  jz      short loc_180003E37
0x180003e22  movzx   ecx, word ptr [rdx+28h]
0x180003e26  test    rcx, rcx
0x180003e29  jz      short loc_180003E37
0x180003e2b  mov     byte ptr [rax], 0
0x180003e2e  inc     rax
0x180003e31  sub     rcx, 1
0x180003e35  jnz     short loc_180003E2B
0x180003e37  call    cs:__imp_GetProcessHeap
0x180003e3d  mov     r8, rbx
0x180003e40  xor     edx, edx
0x180003e42  mov     rcx, rax
0x180003e45  add     rsp, 20h
0x180003e49  pop     rbx
0x180003e4a  jmp     cs:__imp_HeapFree
```
