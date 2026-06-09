# RemovePrintDeviceObject

- ea: `0x1800124b0`
- end: `0x1800124f1`
- name: `RemovePrintDeviceObject`
- size: `65`
- prototype: `__int64 __fastcall(struct _DEVICEOBJECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011d48`
- `0x180012288`
- `0x1800124b0`

## pseudocode

```c
__int64 __fastcall RemovePrintDeviceObject(struct _DEVICEOBJECT *a1)
{
  int v3; // eax

  if ( a1 == (struct _DEVICEOBJECT *)-1LL )
    return 2147942487LL;
  v3 = eProtectHandle(a1, 1) - 1;
  if ( !v3 )
    return 2147942406LL;
  if ( v3 != 1 )
    FreeDevObjHandle(a1);
  return 0;
}

```

## disassembly

```asm
0x1800124b0  push    rbx
0x1800124b2  sub     rsp, 20h
0x1800124b6  mov     rbx, rcx
0x1800124b9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800124bd  jnz     short loc_1800124C6
0x1800124bf  mov     eax, 80070057h
0x1800124c4  jmp     short loc_1800124EB
0x1800124c6  mov     edx, 1
0x1800124cb  call    ?eProtectHandle@@YA?AW4EProtectResult@@PEAXH@Z; eProtectHandle(void *,int)
0x1800124d0  sub     eax, 1
0x1800124d3  jz      short loc_1800124E6
0x1800124d5  cmp     eax, 1
0x1800124d8  jz      short loc_1800124E2
0x1800124da  mov     rcx, rbx; struct _DEVICEOBJECT *
0x1800124dd  call    ?FreeDevObjHandle@@YAXPEAU_DEVICEOBJECT@@@Z; FreeDevObjHandle(_DEVICEOBJECT *)
0x1800124e2  xor     eax, eax
0x1800124e4  jmp     short loc_1800124EB
0x1800124e6  mov     eax, 80070006h
0x1800124eb  add     rsp, 20h
0x1800124ef  pop     rbx
0x1800124f0  retn
```
