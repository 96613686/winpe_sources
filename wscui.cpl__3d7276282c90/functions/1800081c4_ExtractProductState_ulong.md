# ExtractProductState(ulong)

- ea: `0x1800081c4`
- end: `0x18000823e`
- name: `?ExtractProductState@@YA?AW4ProductState@@K@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006fec`
- `0x180008ed0`
- `0x1800098c4`
- `0x180009d60`
- `0x18000a3e8`

## callees

- `0x180008058`
- `0x1800081c4`

## pseudocode

```c
__int64 __fastcall ExtractProductState(__int16 a1)
{
  unsigned int v1; // ecx

  v1 = a1 & 0xF000;
  if ( v1 == 4096 || v1 == 0x2000 || !v1 || v1 == 20480 || v1 == 12288 || v1 == 0x4000 || v1 == 0x8000 )
    return v1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v1);
  return 0;
}

```

## disassembly

```asm
0x1800081c4  sub     rsp, 28h
0x1800081c8  and     ecx, 0F000h
0x1800081ce  cmp     ecx, 1000h
0x1800081d4  jz      short loc_180008237
0x1800081d6  cmp     ecx, 2000h
0x1800081dc  jz      short loc_180008237
0x1800081de  test    ecx, ecx
0x1800081e0  jz      short loc_180008237
0x1800081e2  cmp     ecx, 5000h
0x1800081e8  jz      short loc_180008237
0x1800081ea  cmp     ecx, 3000h
0x1800081f0  jz      short loc_180008237
0x1800081f2  cmp     ecx, 4000h
0x1800081f8  jz      short loc_180008237
0x1800081fa  cmp     ecx, 8000h
0x180008200  jz      short loc_180008237
0x180008202  mov     rax, cs:WPP_GLOBAL_Control
0x180008209  lea     rdx, WPP_GLOBAL_Control
0x180008210  cmp     rax, rdx
0x180008213  jz      short loc_180008233
0x180008215  test    byte ptr [rax+1Ch], 1
0x180008219  jz      short loc_180008233
0x18000821b  mov     r9d, ecx
0x18000821e  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x180008225  mov     rcx, [rax+10h]
0x180008229  mov     edx, 0Ch
0x18000822e  call    WPP_SF_d
0x180008233  xor     eax, eax
0x180008235  jmp     short loc_180008239
0x180008237  mov     eax, ecx
0x180008239  add     rsp, 28h
0x18000823d  retn
```
