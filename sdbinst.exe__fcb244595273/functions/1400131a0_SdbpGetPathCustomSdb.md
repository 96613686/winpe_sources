# SdbpGetPathCustomSdb

- ea: `0x1400131a0`
- end: `0x140013279`
- name: `SdbpGetPathCustomSdb`
- size: `217`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x14001008c`
- `0x1400100c4`
- `0x140012db0`
- `0x1400131a0`
- `0x14002e420`

## string_xrefs

- `0x140013223`: `AslPathCombine failed [%x]`
- `0x140013234`: `SdbpGetPathCustomSdb`

## pseudocode

```c
__int64 __fastcall SdbpGetPathCustomSdb(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  _OWORD v9[2]; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int16 v10[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  v9[0] = *(_OWORD *)L"\\CustomSDB";
  *(_QWORD *)((char *)v9 + 14) = *(_QWORD *)L"SDB";
  if ( a2 < 0xB )
    return 3221225507LL;
  *a1 = 0;
  v10[0] = 0;
  if ( !a3 )
    v3 = (unsigned __int16 *)&Format;
  v7 = AslPathCombine(v9, v3, v10, 260);
  v8 = v7;
  if ( v7 >= 0 )
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, v10);
  else
    AslLogCallPrintf(1, "SdbpGetPathCustomSdb", 1190, "AslPathCombine failed [%x]", v7);
  return v8;
}

```

## disassembly

```asm
0x1400131a0  push    rbx
0x1400131a2  push    rsi
0x1400131a3  push    rdi
0x1400131a4  sub     rsp, 270h
0x1400131ab  mov     rax, cs:__security_cookie
0x1400131b2  xor     rax, rsp
0x1400131b5  mov     [rsp+288h+var_28], rax
0x1400131bd  movsd   xmm1, qword ptr cs:aCustomsdb+0Eh; "SDB"
0x1400131c5  mov     r10, r8
0x1400131c8  mov     rsi, rdx
0x1400131cb  mov     rdi, rcx
0x1400131ce  movups  xmm0, xmmword ptr cs:aCustomsdb; "\\CustomSDB"
0x1400131d5  movups  xmmword ptr [rsp+288h+var_258], xmm0
0x1400131da  movsd   qword ptr [rsp+288h+var_258+0Eh], xmm1
0x1400131e0  cmp     rdx, 0Bh
0x1400131e4  jnb     short loc_1400131ED
0x1400131e6  mov     eax, 0C0000023h
0x1400131eb  jmp     short loc_14001325E
0x1400131ed  xor     eax, eax
0x1400131ef  lea     r8, [rsp+288h+var_238]
0x1400131f4  mov     [rcx], ax
0x1400131f7  test    r10, r10
0x1400131fa  mov     [rsp+288h+var_238], ax
0x1400131ff  lea     rcx, [rsp+288h+var_258]
0x140013204  lea     rax, Format
0x14001320b  mov     r9d, 104h
0x140013211  cmovz   r10, rax
0x140013215  mov     rdx, r10
0x140013218  call    AslPathCombine
0x14001321d  mov     ebx, eax
0x14001321f  test    eax, eax
0x140013221  jns     short loc_140013247
0x140013223  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14001322a  mov     [rsp+288h+var_268], eax
0x14001322e  mov     r8d, 4A6h
0x140013234  lea     rdx, aSdbpgetpathcus; "SdbpGetPathCustomSdb"
0x14001323b  mov     ecx, 1
0x140013240  call    AslLogCallPrintf
0x140013245  jmp     short loc_14001325C
0x140013247  xor     r9d, r9d
0x14001324a  lea     r8, [rsp+288h+var_238]
0x14001324f  mov     rdx, rsi; unsigned __int64
0x140013252  mov     rcx, rdi; unsigned __int16 *
0x140013255  call    SdbpGetPathAppPatch
0x14001325a  mov     ebx, eax
0x14001325c  mov     eax, ebx
0x14001325e  mov     rcx, [rsp+288h+var_28]
0x140013266  xor     rcx, rsp; StackCookie
0x140013269  call    __security_check_cookie
0x14001326e  add     rsp, 270h
0x140013275  pop     rdi
0x140013276  pop     rsi
0x140013277  pop     rbx
0x140013278  retn
```
