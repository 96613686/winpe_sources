# RemovePrintDeviceObject

- ea: `0x180013bd0`
- end: `0x180013c12`
- name: `RemovePrintDeviceObject`
- size: `66`
- prototype: `__int64 __fastcall(struct _DEVICEOBJECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001346c`
- `0x180013a04`
- `0x180013bd0`

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
0x180013bd0  push    rbx
0x180013bd2  sub     rsp, 20h
0x180013bd6  mov     rbx, rcx
0x180013bd9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013bdd  jnz     short loc_180013BE6
0x180013bdf  mov     eax, 80070057h
0x180013be4  jmp     short loc_180013C0B
0x180013be6  mov     edx, 1
0x180013beb  call    ?eProtectHandle@@YA?AW4EProtectResult@@PEAXH@Z; eProtectHandle(void *,int)
0x180013bf0  sub     eax, 1
0x180013bf3  jz      short loc_180013C06
0x180013bf5  cmp     eax, 1
0x180013bf8  jz      short loc_180013C02
0x180013bfa  mov     rcx, rbx; struct _DEVICEOBJECT *
0x180013bfd  call    ?FreeDevObjHandle@@YAXPEAU_DEVICEOBJECT@@@Z; FreeDevObjHandle(_DEVICEOBJECT *)
0x180013c02  xor     eax, eax
0x180013c04  jmp     short loc_180013C0B
0x180013c06  mov     eax, 80070006h
0x180013c0b  add     rsp, 20h
0x180013c0f  pop     rbx
0x180013c10  retn
```
