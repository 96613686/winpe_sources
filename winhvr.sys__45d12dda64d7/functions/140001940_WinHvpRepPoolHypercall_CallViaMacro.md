# WinHvpRepPoolHypercall_CallViaMacro

- ea: `0x140001940`
- end: `0x140001a32`
- name: `WinHvpRepPoolHypercall_CallViaMacro`
- size: `242`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001620`
- `0x140009750`
- `0x14001f990`
- `0x140025ce8`

## callees

- `0x140001940`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x1400019bc`
- `ntoskrnl!HvlInvokeHypercall` at `0x1400019bc`

## pseudocode

```c
__int64 __fastcall WinHvpRepPoolHypercall_CallViaMacro(__int64 a1, unsigned __int16 a2, __int16 a3, int *a4)
{
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax

  if ( *(_BYTE *)(a1 + 24) )
    return WinHvpSlowHypercallRemote(a2, a3, *(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), a4);
  if ( *(_QWORD *)(a1 + 16) )
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 40LL);
  else
    v7 = 0;
  if ( *(_QWORD *)(a1 + 8) )
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL);
  else
    v8 = 0;
  if ( !WinHvpConnected )
    return 3224702976LL;
  v9 = HvlInvokeHypercall((WinHvpNested != 0 ? 0x80000000 : 0) | a2 | ((unsigned __int64)(a3 & 0xFFF) << 32), v8, v7);
  if ( a4 )
    *a4 = WORD2(v9) & 0xFFF;
  if ( (_WORD)v9 )
    return (unsigned __int16)v9 | 0xC0350000;
  else
    return 0;
}

```

## disassembly

```asm
0x140001940  mov     [rsp+arg_0], rbx
0x140001945  push    rdi
0x140001946  sub     rsp, 30h
0x14000194a  cmp     byte ptr [rcx+18h], 0
0x14000194e  mov     rbx, r9
0x140001951  mov     r11d, r8d
0x140001954  mov     edi, edx
0x140001956  jnz     loc_140001A0B
0x14000195c  cmp     qword ptr [rcx+10h], 0
0x140001961  jz      loc_1400019EF
0x140001967  mov     r8, [rcx+28h]
0x14000196b  mov     r8, [r8+28h]
0x14000196f  cmp     qword ptr [rcx+8], 0
0x140001974  jz      loc_140001A24
0x14000197a  mov     rdx, [rcx+28h]
0x14000197e  mov     rdx, [rdx+18h]
0x140001982  movzx   eax, cs:WinHvpNested
0x140001989  neg     al
0x14000198b  sbb     r10d, r10d
0x14000198e  and     r10d, 80000000h
0x140001995  cmp     cs:WinHvpConnected, 0
0x14000199c  jz      loc_140001A2B
0x1400019a2  mov     ecx, r11d
0x1400019a5  movzx   r9d, di
0x1400019a9  and     ecx, 0FFFh
0x1400019af  mov     eax, r10d
0x1400019b2  shl     rcx, 20h
0x1400019b6  or      rcx, r9
0x1400019b9  or      rcx, rax
0x1400019bc  call    cs:__imp_HvlInvokeHypercall
0x1400019c3  nop     dword ptr [rax+rax+00h]
0x1400019c8  test    rbx, rbx
0x1400019cb  jz      short loc_1400019DC
0x1400019cd  mov     rcx, rax
0x1400019d0  shr     rcx, 20h
0x1400019d4  and     ecx, 0FFFh
0x1400019da  mov     [rbx], ecx
0x1400019dc  test    ax, ax
0x1400019df  jnz     short loc_1400019F7
0x1400019e1  xor     eax, eax
0x1400019e3  mov     rbx, [rsp+38h+arg_0]
0x1400019e8  add     rsp, 30h
0x1400019ec  pop     rdi
0x1400019ed  retn
0x1400019ef  xor     r8d, r8d
0x1400019f2  jmp     loc_14000196F
0x1400019f7  mov     rbx, [rsp+38h+arg_0]
0x1400019fc  movzx   eax, ax
0x1400019ff  or      eax, 0C0350000h
0x140001a04  add     rsp, 30h
0x140001a08  pop     rdi
0x140001a09  retn
0x140001a0b  mov     r9, [rcx+10h]
0x140001a0f  mov     edx, r11d
0x140001a12  mov     r8, [rcx+8]
0x140001a16  mov     ecx, edi
0x140001a18  mov     [rsp+38h+var_18], rbx
0x140001a1d  call    WinHvpSlowHypercallRemote
0x140001a22  jmp     short loc_1400019E3
0x140001a24  xor     edx, edx
0x140001a26  jmp     loc_140001982
0x140001a2b  mov     eax, 0C0351000h
0x140001a30  jmp     short loc_1400019E3
```
