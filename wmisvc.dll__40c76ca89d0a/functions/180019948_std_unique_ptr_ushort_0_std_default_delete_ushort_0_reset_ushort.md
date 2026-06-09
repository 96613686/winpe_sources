# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::reset(ushort *)

- ea: `0x180019948`
- end: `0x180019974`
- name: `?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAXPEAG@Z`
- size: `44`
- prototype: `int __fastcall(void **, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001855c`
- `0x180018fb4`

## callees

- `0x180019948`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019960`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180019960`

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
0x180019948  mov     [rsp+arg_0], rbx
0x18001994d  push    rdi
0x18001994e  sub     rsp, 20h
0x180019952  mov     rbx, rdx
0x180019955  mov     rdi, rcx
0x180019958  cmp     rdx, [rcx]
0x18001995b  jz      short loc_180019969
0x18001995d  mov     rcx, [rcx]
0x180019960  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180019966  mov     [rdi], rbx
0x180019969  mov     rbx, [rsp+28h+arg_0]
0x18001996e  add     rsp, 20h
0x180019972  pop     rdi
0x180019973  retn
```
