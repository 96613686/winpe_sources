# TpmTransport::ShouldCancelCommand(bool)

- ea: `0x1400103f8`
- end: `0x140010419`
- name: `?ShouldCancelCommand@TpmTransport@@IEBA_N_N@Z`
- size: `33`
- prototype: `bool __fastcall(TpmTransport *__hidden this, bool)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001620`
- `0x140001a30`
- `0x1400027e4`
- `0x1400183d0`
- `0x140024f40`
- `0x1400255b0`
- `0x140025d5c`
- `0x140027280`

## callees

- `0x1400103f8`

## pseudocode

```c
char __fastcall TpmTransport::ShouldCancelCommand(TpmTransport *this, char a2)
{
  char v2; // r8

  v2 = 1;
  if ( *((_DWORD *)this + 16) != 2 && (!a2 || *((_DWORD *)this + 16) != 1) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1400103f8  mov     eax, [rcx+40h]
0x1400103fb  mov     r8d, 1
0x140010401  cmp     eax, 2
0x140010404  jz      short loc_140010415
0x140010406  test    dl, dl
0x140010408  jz      short loc_140010412
0x14001040a  mov     eax, [rcx+40h]
0x14001040d  cmp     eax, r8d
0x140010410  jz      short loc_140010415
0x140010412  xor     r8b, r8b
0x140010415  mov     al, r8b
0x140010418  retn
```
