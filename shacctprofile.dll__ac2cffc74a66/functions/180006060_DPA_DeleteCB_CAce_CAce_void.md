# DPA_DeleteCB<CAce>(CAce *,void *)

- ea: `0x180006060`
- end: `0x18000609f`
- name: `??$DPA_DeleteCB@VCAce@@@@YAHPEAVCAce@@PEAX@Z`
- size: `63`
- prototype: `__int64 __fastcall(HLOCAL *p, void *pData)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002600`
- `0x180006060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006072`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000607c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006072`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000607c`

## pseudocode

```c
__int64 __fastcall DPA_DeleteCB<CAce>(HLOCAL *p, void *pData)
{
  if ( p )
  {
    LocalFree(p[1]);
    LocalFree(p[2]);
    *((_DWORD *)p + 7) &= ~0x80000000;
    operator delete(p);
  }
  return 1;
}

```

## disassembly

```asm
0x180006060  push    rbx
0x180006062  sub     rsp, 20h
0x180006066  mov     rbx, rcx
0x180006069  test    rcx, rcx
0x18000606c  jz      short loc_180006094
0x18000606e  mov     rcx, [rcx+8]; hMem
0x180006072  call    cs:__imp_LocalFree
0x180006078  mov     rcx, [rbx+10h]; hMem
0x18000607c  call    cs:__imp_LocalFree
0x180006082  btr     dword ptr [rbx+1Ch], 1Fh
0x180006087  mov     edx, 20h ; ' '
0x18000608c  mov     rcx, rbx; Block
0x18000608f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006094  mov     eax, 1
0x180006099  add     rsp, 20h
0x18000609d  pop     rbx
0x18000609e  retn
```
