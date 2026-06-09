# DoesActionRequireElevation(SecurityAction)

- ea: `0x180006500`
- end: `0x180006515`
- name: `?DoesActionRequireElevation@@YA_NW4SecurityAction@@@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006500`

## pseudocode

```c
bool __fastcall DoesActionRequireElevation(int a1)
{
  int v1; // ecx

  v1 = a1 - 102;
  return !v1 || (unsigned int)(v1 - 15) < 2;
}

```

## disassembly

```asm
0x180006500  sub     ecx, 66h ; 'f'
0x180006503  jz      short loc_180006512
0x180006505  sub     ecx, 0Fh
0x180006508  jz      short loc_180006512
0x18000650a  cmp     ecx, 1
0x18000650d  jz      short loc_180006512
0x18000650f  xor     al, al
0x180006511  retn
0x180006512  mov     al, 1
0x180006514  retn
```
