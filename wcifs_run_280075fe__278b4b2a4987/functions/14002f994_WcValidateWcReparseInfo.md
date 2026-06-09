# WcValidateWcReparseInfo

- ea: `0x14002f994`
- end: `0x14002f9f2`
- name: `WcValidateWcReparseInfo`
- size: `94`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14001a62c`
- `0x140029608`
- `0x14002a614`
- `0x140030d54`

## callees

- `0x1400024d4`
- `0x14002f994`

## pseudocode

```c
__int64 __fastcall WcValidateWcReparseInfo(__int64 a1, unsigned int a2)
{
  int v2; // r9d
  USHORT v3; // dx
  USHORT v4; // r9
  USHORT pusResult; // [rsp+38h] [rbp+10h] BYREF

  pusResult = 0;
  if ( a2 < 8 )
    return 3221225730LL;
  v2 = *(unsigned __int16 *)(a1 + 4);
  if ( a2 < v2 + 8 )
    return 3221225730LL;
  if ( (unsigned __int16)v2 < 0x1Au )
    return 3221225730LL;
  if ( *(_DWORD *)(a1 + 8) > 1u )
    return 3221225730LL;
  v3 = *(_WORD *)(a1 + 32);
  if ( (v3 & 1) != 0 || RtlUShortAdd(0x1Au, v3, &pusResult) < 0 || pusResult > v4 )
    return 3221225730LL;
  else
    return 0;
}

```

## disassembly

```asm
0x14002f994  sub     rsp, 28h
0x14002f998  xor     eax, eax
0x14002f99a  mov     [rsp+28h+pusResult], ax
0x14002f99f  cmp     edx, 8
0x14002f9a2  jb      short loc_14002F9E7
0x14002f9a4  movzx   r9d, word ptr [rcx+4]
0x14002f9a9  lea     eax, [r9+8]
0x14002f9ad  cmp     edx, eax
0x14002f9af  jb      short loc_14002F9E7
0x14002f9b1  mov     eax, 1Ah
0x14002f9b6  cmp     r9w, ax
0x14002f9ba  jb      short loc_14002F9E7
0x14002f9bc  cmp     dword ptr [rcx+8], 1
0x14002f9c0  ja      short loc_14002F9E7
0x14002f9c2  movzx   edx, word ptr [rcx+20h]; usAddend
0x14002f9c6  test    dl, 1
0x14002f9c9  jnz     short loc_14002F9E7
0x14002f9cb  mov     ecx, eax; usAugend
0x14002f9cd  lea     r8, [rsp+28h+pusResult]; pusResult
0x14002f9d2  call    RtlUShortAdd
0x14002f9d7  test    eax, eax
0x14002f9d9  js      short loc_14002F9E7
0x14002f9db  cmp     [rsp+28h+pusResult], r9w
0x14002f9e1  ja      short loc_14002F9E7
0x14002f9e3  xor     eax, eax
0x14002f9e5  jmp     short loc_14002F9EC
0x14002f9e7  mov     eax, 0C0000102h
0x14002f9ec  add     rsp, 28h
0x14002f9f0  retn
```
