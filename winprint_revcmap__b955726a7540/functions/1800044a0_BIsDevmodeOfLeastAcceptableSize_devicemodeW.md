# BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)

- ea: `0x1800044a0`
- end: `0x1800044b5`
- name: `?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z`
- size: `21`
- prototype: `__int64 __fastcall(struct _devicemodeW *)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800017d0`
- `0x180002400`
- `0x180003200`
- `0x180006e10`
- `0x180007210`

## callees

- `0x1800044a0`

## pseudocode

```c
_BOOL8 __fastcall BIsDevmodeOfLeastAcceptableSize(struct _devicemodeW *a1)
{
  return a1 && a1->dmSize >= 0x62u;
}

```

## disassembly

```asm
0x1800044a0  test    rcx, rcx
0x1800044a3  jz      short loc_1800044B2
0x1800044a5  cmp     word ptr [rcx+44h], 62h ; 'b'
0x1800044aa  jb      short loc_1800044B2
0x1800044ac  mov     eax, 1
0x1800044b1  retn
0x1800044b2  xor     eax, eax
0x1800044b4  retn
```
