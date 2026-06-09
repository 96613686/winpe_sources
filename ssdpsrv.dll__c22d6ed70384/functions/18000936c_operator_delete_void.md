# operator delete(void *)

- ea: `0x18000936c`
- end: `0x180009380`
- name: `??3@YAXPEAX@Z`
- size: `20`
- prototype: `void __fastcall(void *)`
- caller_count: `58`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800092cc`
- `0x1800092f4`
- `0x1800095d8`
- `0x18000a3f0`
- `0x18000a620`
- `0x18000a730`
- `0x18000a768`
- `0x18000b2a0`
- `0x18000be44`
- `0x18000c340`
- `0x18000c8ac`
- `0x18000cd44`
- `0x18000d09c`
- `0x18000d108`
- `0x18000d4e8`
- `0x18000d990`
- `0x18000e500`
- `0x18000e780`
- `0x18000ec50`
- `0x180010890`
- `0x180011c90`
- `0x180014868`
- `0x18001c3a0`
- `0x18001c974`
- `0x1800213d4`
- `0x180023740`
- `0x1800238dc`
- `0x180023fd4`
- `0x1800246e4`
- `0x180024d5c`
- `0x180025300`
- `0x180025404`
- `0x180027a8c`
- `0x180028c10`
- `0x18002d870`
- `0x18002ddf0`
- `0x18002de30`
- `0x18002de68`
- `0x18002f190`
- `0x18002f1d0`
- `0x18002f510`
- `0x18002f550`
- `0x18002fa40`
- `0x18002fa80`
- `0x18002fac0`
- `0x18002faf8`
- `0x18002fe8c`
- `0x180030010`
- `0x180032bbc`
- `0x180032f2c`

## callees

- `0x18000936c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009375`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009375`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    free(a1);
}

```

## disassembly

```asm
0x18000936c  sub     rsp, 28h
0x180009370  test    rcx, rcx
0x180009373  jz      short loc_18000937B
0x180009375  call    cs:__imp_free
0x18000937b  add     rsp, 28h
0x18000937f  retn
```
