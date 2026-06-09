# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::reset(ushort *)

- ea: `0x1800119a8`
- end: `0x1800119d4`
- name: `?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z`
- size: `44`
- prototype: `int __fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fe68`
- `0x180010ae0`

## callees

- `0x1800119a8`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800119c0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800119c0`

## pseudocode

```c
int __fastcall std::unique_ptr<unsigned short [0]>::reset(void **a1, void *a2)
{
  int result; // eax

  if ( a2 != *a1 )
  {
    result = CWin32DefaultArena::WbemMemFree(*a1);
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1800119a8  mov     [rsp+arg_0], rbx
0x1800119ad  push    rdi
0x1800119ae  sub     rsp, 20h
0x1800119b2  mov     rbx, rdx
0x1800119b5  mov     rdi, rcx
0x1800119b8  cmp     rdx, [rcx]
0x1800119bb  jz      short loc_1800119C9
0x1800119bd  mov     rcx, [rcx]
0x1800119c0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800119c6  mov     [rdi], rbx
0x1800119c9  mov     rbx, [rsp+28h+arg_0]
0x1800119ce  add     rsp, 20h
0x1800119d2  pop     rdi
0x1800119d3  retn
```
