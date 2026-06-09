# ExtractProductOwner(ulong)

- ea: `0x180008170`
- end: `0x1800081be`
- name: `?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ed0`
- `0x180009824`
- `0x1800098c4`
- `0x18000a3e8`

## callees

- `0x180008058`
- `0x180008170`

## pseudocode

```c
__int64 __fastcall ExtractProductOwner(__int16 a1)
{
  unsigned int v1; // ecx

  v1 = a1 & 0xF00;
  if ( (v1 & 0xFFFFFEFF) == 0 )
    return v1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xBu, (__int64)&WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids, v1);
  return 0;
}

```

## disassembly

```asm
0x180008170  sub     rsp, 28h
0x180008174  and     ecx, 0F00h
0x18000817a  test    ecx, 0FFFFFEFFh
0x180008180  jz      short loc_1800081B7
0x180008182  mov     rax, cs:WPP_GLOBAL_Control
0x180008189  lea     rdx, WPP_GLOBAL_Control
0x180008190  cmp     rax, rdx
0x180008193  jz      short loc_1800081B3
0x180008195  test    byte ptr [rax+1Ch], 1
0x180008199  jz      short loc_1800081B3
0x18000819b  mov     r9d, ecx
0x18000819e  lea     r8, WPP_d8f56309d88e3febb8d819a47bcf5371_Traceguids
0x1800081a5  mov     rcx, [rax+10h]
0x1800081a9  mov     edx, 0Bh
0x1800081ae  call    WPP_SF_d
0x1800081b3  xor     eax, eax
0x1800081b5  jmp     short loc_1800081B9
0x1800081b7  mov     eax, ecx
0x1800081b9  add     rsp, 28h
0x1800081bd  retn
```
