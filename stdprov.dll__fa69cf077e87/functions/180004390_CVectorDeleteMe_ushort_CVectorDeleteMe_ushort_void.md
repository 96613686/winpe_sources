# CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)

- ea: `0x180004390`
- end: `0x1800043b9`
- name: `??1?$CVectorDeleteMe@G@@QEAA@XZ`
- size: `41`
- prototype: `int __fastcall(void **)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800043c0`
- `0x180009774`
- `0x18000999c`
- `0x180013138`
- `0x180015c20`
- `0x180015c40`
- `0x180016374`
- `0x180016386`
- `0x180016cbf`

## callees

- `0x180004390`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000439f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000439f`

## pseudocode

```c
int __fastcall CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(void **a1)
{
  void **v1; // rax
  void *v2; // rcx
  void **v3; // rcx

  v1 = a1;
  v2 = *a1;
  if ( !v2 )
  {
    v3 = (void **)v1[1];
    if ( !v3 )
      return (int)v1;
    v2 = *v3;
  }
  LODWORD(v1) = CWin32DefaultArena::WbemMemFree(v2);
  return (int)v1;
}

```

## disassembly

```asm
0x180004390  sub     rsp, 28h
0x180004394  mov     rax, rcx
0x180004397  mov     rcx, [rcx]
0x18000439a  test    rcx, rcx
0x18000439d  jz      short loc_1800043AB
0x18000439f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800043a5  nop
0x1800043a6  add     rsp, 28h
0x1800043aa  retn
0x1800043ab  mov     rcx, [rax+8]
0x1800043af  test    rcx, rcx
0x1800043b2  jz      short loc_1800043A6
0x1800043b4  mov     rcx, [rcx]
0x1800043b7  jmp     short loc_18000439F
```
