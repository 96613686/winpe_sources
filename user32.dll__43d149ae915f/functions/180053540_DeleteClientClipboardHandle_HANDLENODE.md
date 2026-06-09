# DeleteClientClipboardHandle(_HANDLENODE *)

- ea: `0x180053540`
- end: `0x1800535ce`
- name: `?DeleteClientClipboardHandle@@YAHPEAU_HANDLENODE@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct _HANDLENODE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a5f0`
- `0x1800534c8`

## callees

- `0x180053540`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180053579`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800535ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180053579`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800535ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180053597`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180053597`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800535b0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800535b0`
- `GDI32!DeleteEnhMetaFile` at `0x1800535c6`
- `GDI32!DeleteEnhMetaFile` at `0x1800535c6`
- `GDI32!DeleteMetaFile` at `0x1800535a6`
- `GDI32!DeleteMetaFile` at `0x1800535a6`

## pseudocode

```c
_BOOL8 __fastcall DeleteClientClipboardHandle(HENHMETAFILE *a1)
{
  HMETAFILE *v3; // rax

  switch ( *((_DWORD *)a1 + 2) )
  {
    case 2:
      return 1;
    case 3:
      goto LABEL_12;
    case 9:
      return 1;
    case 0xE:
LABEL_14:
      DeleteEnhMetaFile(a1[3]);
      return 1;
    case 0x82:
      return 1;
    case 0x83:
LABEL_12:
      v3 = (HMETAFILE *)GlobalLock(a1[3]);
      if ( !v3 )
        return 0;
      DeleteMetaFile(v3[2]);
      GlobalUnlock(a1[3]);
      GlobalFree(a1[3]);
      return 1;
    case 0x8E:
      goto LABEL_14;
  }
  return !*((_DWORD *)a1 + 8) || !GlobalFree(a1[3]);
}

```

## disassembly

```asm
0x180053540  push    rbx
0x180053542  sub     rsp, 20h
0x180053546  mov     edx, [rcx+8]
0x180053549  mov     rbx, rcx
0x18005354c  sub     edx, 2
0x18005354f  jz      short loc_180053584
0x180053551  sub     edx, 1
0x180053554  jz      short loc_180053593
0x180053556  sub     edx, 6
0x180053559  jz      short loc_180053584
0x18005355b  sub     edx, 5
0x18005355e  jz      short loc_1800535C2
0x180053560  sub     edx, 74h ; 't'
0x180053563  jz      short loc_180053584
0x180053565  sub     edx, 1
0x180053568  jz      short loc_180053593
0x18005356a  cmp     edx, 0Bh
0x18005356d  jz      short loc_1800535C2
0x18005356f  cmp     dword ptr [rcx+20h], 0
0x180053573  jz      short loc_180053584
0x180053575  mov     rcx, [rcx+18h]; hMem
0x180053579  call    cs:__imp_GlobalFree
0x18005357f  test    rax, rax
0x180053582  jnz     short loc_18005358F
0x180053584  mov     eax, 1
0x180053589  add     rsp, 20h
0x18005358d  pop     rbx
0x18005358e  retn
0x18005358f  xor     eax, eax
0x180053591  jmp     short loc_180053589
0x180053593  mov     rcx, [rcx+18h]; hMem
0x180053597  call    cs:__imp_GlobalLock
0x18005359d  test    rax, rax
0x1800535a0  jz      short loc_18005358F
0x1800535a2  mov     rcx, [rax+10h]; hmf
0x1800535a6  call    cs:__imp_DeleteMetaFile
0x1800535ac  mov     rcx, [rbx+18h]; hMem
0x1800535b0  call    cs:__imp_GlobalUnlock
0x1800535b6  mov     rcx, [rbx+18h]; hMem
0x1800535ba  call    cs:__imp_GlobalFree
0x1800535c0  jmp     short loc_180053584
0x1800535c2  mov     rcx, [rcx+18h]; hmf
0x1800535c6  call    cs:__imp_DeleteEnhMetaFile
0x1800535cc  jmp     short loc_180053584
```
