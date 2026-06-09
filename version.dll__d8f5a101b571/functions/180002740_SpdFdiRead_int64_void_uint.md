# SpdFdiRead(__int64,void *,uint)

- ea: `0x180002740`
- end: `0x180002771`
- name: `?SpdFdiRead@@YAI_JPEAXI@Z`
- size: `49`
- prototype: `unsigned int __fastcall(__int64, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000275d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000275d`
- `KERNEL32!_lread` at `0x180002746`
- `KERNEL32!_lread` at `0x180002746`

## pseudocode

```c
__int64 __fastcall SpdFdiRead(HFILE a1, void *a2, UINT a3)
{
  UINT v3; // ebx

  v3 = _lread(a1, a2, a3);
  if ( v3 == -1 )
  {
    v3 = -1;
    *(_DWORD *)TlsGetValue(itlsDiamondContext) = -3;
  }
  return v3;
}

```

## disassembly

```asm
0x180002740  push    rbx
0x180002742  sub     rsp, 20h
0x180002746  call    cs:__imp__lread
0x18000274c  mov     ebx, eax
0x18000274e  or      eax, 0FFFFFFFFh
0x180002751  cmp     ebx, eax
0x180002753  jnz     short loc_180002769
0x180002755  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000275b  mov     ebx, eax
0x18000275d  call    cs:__imp_TlsGetValue
0x180002763  mov     dword ptr [rax], 0FFFFFFFDh
0x180002769  mov     eax, ebx
0x18000276b  add     rsp, 20h
0x18000276f  pop     rbx
0x180002770  retn
```
