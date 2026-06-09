# CVectorDeleteMe<uchar>::~CVectorDeleteMe<uchar>(void)

- ea: `0x180009da0`
- end: `0x180009dc9`
- name: `??1?$CVectorDeleteMe@E@@QEAA@XZ`
- size: `41`
- prototype: `int __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007100`
- `0x180016090`

## callees

- `0x180009da0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009db8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009db8`

## pseudocode

```c
int __fastcall CVectorDeleteMe<unsigned char>::~CVectorDeleteMe<unsigned char>(void **a1)
{
  void *v1; // rax
  void **v2; // rcx
  void *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *a1;
    goto LABEL_4;
  }
  v2 = (void **)a1[1];
  if ( v2 )
  {
    v3 = *v2;
LABEL_4:
    LODWORD(v1) = CWin32DefaultArena::WbemMemFree(v3);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x180009da0  sub     rsp, 28h
0x180009da4  mov     rax, [rcx]
0x180009da7  test    rax, rax
0x180009daa  jnz     short loc_180009DC4
0x180009dac  mov     rcx, [rcx+8]
0x180009db0  test    rcx, rcx
0x180009db3  jz      short loc_180009DBF
0x180009db5  mov     rcx, [rcx]
0x180009db8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180009dbe  nop
0x180009dbf  add     rsp, 28h
0x180009dc3  retn
0x180009dc4  mov     rcx, rax
0x180009dc7  jmp     short loc_180009DB8
```
