# UdfInsertNames

- ea: `0x140057f9c`
- end: `0x14005806a`
- name: `UdfInsertNames`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140038194`
- `0x140050a8c`

## callees

- `0x140009014`
- `0x14000a08c`
- `0x140057f9c`

## import_xrefs

- `ntoskrnl!RtlDelete` at `0x14005afb3`
- `ntoskrnl!RtlDelete` at `0x14005afdc`
- `ntoskrnl!RtlDelete` at `0x14005afb3`
- `ntoskrnl!RtlDelete` at `0x14005afdc`

## pseudocode

```c
__int64 __fastcall UdfInsertNames(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 inserted; // rax
  int v9; // ecx

  v4 = a4;
  inserted = UdfInsertPrefixTreeEntry(a1, a3 + 512, a4, 104);
  if ( inserted == v4 )
  {
    *(_DWORD *)(v4 + 68) |= 0x10u;
    UdfInsertPrefixTreeEntry(a1, a3 + 520, v4, 144);
    *(_DWORD *)(v4 + 68) |= 0x20u;
    v9 = *(_DWORD *)(v4 + 68);
    if ( (*(_DWORD *)(a3 + 212) & 0x800000) != 0 && *(_WORD *)(v4 + 208) )
    {
      UdfInsertPrefixTreeEntry(a1, a3 + 528, v4, 184);
      *(_DWORD *)(v4 + 68) |= 0x40u;
      v9 = *(_DWORD *)(v4 + 68);
    }
    *(_DWORD *)(v4 + 68) = v9 & 0xFFFFFFF7;
  }
  else
  {
    if ( *(_QWORD *)(inserted + 48) != a2 )
      UdfRaiseStatusEx(a1, 3221225859LL, 0);
    return inserted;
  }
  return v4;
}

```

## disassembly

```asm
0x140057f9c  mov     [rsp+arg_0], rbx
0x140057fa1  mov     [rsp+arg_18], r9
0x140057fa6  mov     [rsp+arg_10], r8
0x140057fab  push    rsi
0x140057fac  push    rdi
0x140057fad  push    r14
0x140057faf  sub     rsp, 20h
0x140057fb3  mov     rbx, r9
0x140057fb6  mov     rdi, r8
0x140057fb9  mov     r14, rdx
0x140057fbc  mov     rsi, rcx
0x140057fbf  lea     rdx, [r8+200h]
0x140057fc6  mov     r9d, 68h ; 'h'
0x140057fcc  mov     r8, rbx
0x140057fcf  call    UdfInsertPrefixTreeEntry
0x140057fd4  cmp     rax, rbx
0x140057fd7  jz      short loc_140057FF9
0x140057fd9  cmp     [rax+30h], r14
0x140057fdd  jnz     short loc_140057FE9
0x140057fdf  mov     rbx, rax
0x140057fe2  mov     [rsp+38h+arg_18], rax
0x140057fe7  jmp     short loc_140058058
0x140057fe9  xor     r8d, r8d
0x140057fec  mov     edx, 0C0000183h
0x140057ff1  mov     rcx, rsi
0x140057ff4  call    UdfRaiseStatusEx
0x140057ff9  or      dword ptr [rbx+44h], 10h
0x140057ffd  lea     rdx, [rdi+208h]
0x140058004  mov     r9d, 90h
0x14005800a  mov     r8, rbx
0x14005800d  mov     rcx, rsi
0x140058010  call    UdfInsertPrefixTreeEntry
0x140058015  or      dword ptr [rbx+44h], 20h
0x140058019  mov     ecx, [rbx+44h]
0x14005801c  test    dword ptr [rdi+0D4h], 800000h
0x140058026  jz      short loc_140058052
0x140058028  xor     eax, eax
0x14005802a  cmp     ax, [rbx+0D0h]
0x140058031  jz      short loc_140058052
0x140058033  lea     rdx, [rdi+210h]
0x14005803a  mov     r9d, 0B8h
0x140058040  mov     r8, rbx
0x140058043  mov     rcx, rsi
0x140058046  call    UdfInsertPrefixTreeEntry
0x14005804b  or      dword ptr [rbx+44h], 40h
0x14005804f  mov     ecx, [rbx+44h]
0x140058052  and     ecx, 0FFFFFFF7h
0x140058055  mov     [rbx+44h], ecx
0x140058058  mov     rax, rbx
0x14005805b  mov     rbx, [rsp+38h+arg_0]
0x140058060  add     rsp, 20h
0x140058064  pop     r14
0x140058066  pop     rdi
0x140058067  pop     rsi
0x140058068  retn
0x14005af93  push    rbx
0x14005af95  push    rbp
0x14005af96  sub     rsp, 28h
0x14005af9a  mov     rbp, rdx
0x14005af9d  movzx   eax, cl
0x14005afa0  test    cl, cl
0x14005afa2  jz      short loc_14005AFFC
0x14005afa4  mov     rbx, [rbp+58h]
0x14005afa8  mov     eax, [rbx+44h]
0x14005afab  test    al, 10h
0x14005afad  jz      short loc_14005AFCE
0x14005afaf  lea     rcx, [rbx+68h]; Links
0x14005afb3  call    cs:__imp_RtlDelete
0x14005afba  nop     dword ptr [rax+rax+00h]
0x14005afbf  mov     rcx, [rbp+50h]
0x14005afc3  mov     [rcx+200h], rax
0x14005afca  and     dword ptr [rbx+44h], 0FFFFFFEFh
0x14005afce  mov     eax, [rbx+44h]
0x14005afd1  test    al, 20h
0x14005afd3  jz      short loc_14005AFFC
0x14005afd5  lea     rcx, [rbx+90h]; Links
0x14005afdc  call    cs:__imp_RtlDelete
0x14005afe3  nop     dword ptr [rax+rax+00h]
0x14005afe8  mov     rcx, [rbp+50h]
0x14005afec  mov     [rcx+208h], rax
0x14005aff3  mov     eax, [rbx+44h]
0x14005aff6  and     eax, 0FFFFFFDFh
0x14005aff9  mov     [rbx+44h], eax
0x14005affc  add     rsp, 28h
0x14005b000  pop     rbp
0x14005b001  pop     rbx
0x14005b002  retn
```
