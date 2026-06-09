# WcValidateWcReparseInfo

- ea: `0x14002f9e4`
- end: `0x14002fa42`
- name: `WcValidateWcReparseInfo`
- size: `94`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14001a62c`
- `0x140029658`
- `0x14002a664`
- `0x140030da4`

## callees

- `0x1400024d4`
- `0x14002f9e4`

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
0x14002f9e4  sub     rsp, 28h
0x14002f9e8  xor     eax, eax
0x14002f9ea  mov     [rsp+28h+pusResult], ax
0x14002f9ef  cmp     edx, 8
0x14002f9f2  jb      short loc_14002FA37
0x14002f9f4  movzx   r9d, word ptr [rcx+4]
0x14002f9f9  lea     eax, [r9+8]
0x14002f9fd  cmp     edx, eax
0x14002f9ff  jb      short loc_14002FA37
0x14002fa01  mov     eax, 1Ah
0x14002fa06  cmp     r9w, ax
0x14002fa0a  jb      short loc_14002FA37
0x14002fa0c  cmp     dword ptr [rcx+8], 1
0x14002fa10  ja      short loc_14002FA37
0x14002fa12  movzx   edx, word ptr [rcx+20h]; usAddend
0x14002fa16  test    dl, 1
0x14002fa19  jnz     short loc_14002FA37
0x14002fa1b  mov     ecx, eax; usAugend
0x14002fa1d  lea     r8, [rsp+28h+pusResult]; pusResult
0x14002fa22  call    RtlUShortAdd
0x14002fa27  test    eax, eax
0x14002fa29  js      short loc_14002FA37
0x14002fa2b  cmp     [rsp+28h+pusResult], r9w
0x14002fa31  ja      short loc_14002FA37
0x14002fa33  xor     eax, eax
0x14002fa35  jmp     short loc_14002FA3C
0x14002fa37  mov     eax, 0C0000102h
0x14002fa3c  add     rsp, 28h
0x14002fa40  retn
```
