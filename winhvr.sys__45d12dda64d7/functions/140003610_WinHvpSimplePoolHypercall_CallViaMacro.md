# WinHvpSimplePoolHypercall_CallViaMacro

- ea: `0x140003610`
- end: `0x1400036b5`
- name: `WinHvpSimplePoolHypercall_CallViaMacro`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `86`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f80`
- `0x1400030b0`
- `0x140003240`
- `0x140003370`
- `0x1400034b0`
- `0x1400046b0`
- `0x140004a00`
- `0x140005140`
- `0x140005220`
- `0x1400053c0`
- `0x140005500`
- `0x1400059c0`
- `0x140005f40`
- `0x140006000`
- `0x140006b50`
- `0x140006e60`
- `0x140006f00`
- `0x140007010`
- `0x140007160`
- `0x140007480`
- `0x140007550`
- `0x140007660`
- `0x14000786c`
- `0x1400078dc`
- `0x140007980`
- `0x140007e40`
- `0x1400080c0`
- `0x140008270`
- `0x140008420`
- `0x140008610`
- `0x140008750`
- `0x1400087f0`
- `0x140008970`
- `0x140008a80`
- `0x140008ef0`
- `0x140009350`
- `0x1400094a0`
- `0x1400095e0`
- `0x14001ca20`
- `0x14001cae0`
- `0x14001cbc0`
- `0x14001cc40`
- `0x14001df00`
- `0x14001e070`
- `0x14001f0b0`
- `0x14001f920`
- `0x14001ffd0`
- `0x1400208f0`
- `0x140020990`
- `0x140020a30`

## callees

- `0x140003610`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x14000365c`
- `ntoskrnl!HvlInvokeHypercall` at `0x14000365c`

## pseudocode

```c
__int64 __fastcall WinHvpSimplePoolHypercall_CallViaMacro(__int64 a1, unsigned __int16 a2)
{
  unsigned int v2; // ebx
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned __int16 v6; // ax

  v2 = 0;
  if ( *(_BYTE *)(a1 + 24) )
    return WinHvpSlowHypercallRemote(a2, 0, *(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), 0);
  if ( *(_QWORD *)(a1 + 16) )
    v4 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 40LL);
  else
    v4 = 0;
  if ( *(_QWORD *)(a1 + 8) )
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 24LL);
  else
    v5 = 0;
  if ( WinHvpConnected )
  {
    v6 = HvlInvokeHypercall((WinHvpNested != 0 ? 0x80000000 : 0) | (unsigned __int64)a2, v5, v4);
    if ( v6 )
      return v6 | 0xC0350000;
  }
  else
  {
    return (unsigned int)-1070264320;
  }
  return v2;
}

```

## disassembly

```asm
0x140003610  push    rbx
0x140003612  sub     rsp, 30h
0x140003616  xor     ebx, ebx
0x140003618  mov     r10d, edx
0x14000361b  cmp     [rcx+18h], bl
0x14000361e  jnz     short loc_140003680
0x140003620  cmp     [rcx+10h], rbx
0x140003624  jnz     short loc_140003676
0x140003626  mov     r8d, ebx
0x140003629  cmp     [rcx+8], rbx
0x14000362d  jz      short loc_1400036A9
0x14000362f  mov     rdx, [rcx+28h]
0x140003633  mov     rdx, [rdx+18h]
0x140003637  movzx   eax, cs:WinHvpNested
0x14000363e  neg     al
0x140003640  sbb     r9d, r9d
0x140003643  and     r9d, 80000000h
0x14000364a  cmp     cs:WinHvpConnected, bl
0x140003650  jz      short loc_1400036AE
0x140003652  movzx   ecx, r10w
0x140003656  mov     eax, r9d
0x140003659  or      rcx, rax
0x14000365c  call    cs:__imp_HvlInvokeHypercall
0x140003663  nop     dword ptr [rax+rax+00h]
0x140003668  test    ax, ax
0x14000366b  jnz     short loc_14000369E
0x14000366d  mov     eax, ebx
0x14000366f  add     rsp, 30h
0x140003673  pop     rbx
0x140003674  retn
0x140003676  mov     r8, [rcx+28h]
0x14000367a  mov     r8, [r8+28h]
0x14000367e  jmp     short loc_140003629
0x140003680  mov     r9, [rcx+10h]
0x140003684  xor     edx, edx
0x140003686  mov     r8, [rcx+8]
0x14000368a  mov     ecx, r10d
0x14000368d  mov     [rsp+38h+var_18], rbx
0x140003692  call    WinHvpSlowHypercallRemote
0x140003697  add     rsp, 30h
0x14000369b  pop     rbx
0x14000369c  retn
0x14000369e  movzx   ebx, ax
0x1400036a1  or      ebx, 0C0350000h
0x1400036a7  jmp     short loc_14000366D
0x1400036a9  mov     rdx, rbx
0x1400036ac  jmp     short loc_140003637
0x1400036ae  mov     ebx, 0C0351000h
0x1400036b3  jmp     short loc_14000366D
```
