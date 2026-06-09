# UdfRemovePrefix

- ea: `0x14002cca0`
- end: `0x14002ce00`
- name: `UdfRemovePrefix`
- size: `352`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1400177ac`
- `0x140033548`
- `0x140034450`
- `0x140038194`
- `0x1400537b0`
- `0x140055060`

## callees

- `0x14000c5c8`
- `0x1400148c4`
- `0x14002cca0`

## import_xrefs

- `ntoskrnl!RtlDelete` at `0x14002cd30`
- `ntoskrnl!RtlDelete` at `0x14002cd55`
- `ntoskrnl!RtlDelete` at `0x14002cd7a`
- `ntoskrnl!RtlDelete` at `0x14002cd30`
- `ntoskrnl!RtlDelete` at `0x14002cd55`
- `ntoskrnl!RtlDelete` at `0x14002cd7a`

## pseudocode

```c
__int64 __fastcall UdfRemovePrefix(__int64 a1, __int64 a2, char a3, char a4)
{
  __int64 v6; // rdi
  int v8; // r8d
  bool v9; // cf
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 result; // rax
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // rdx
  __int64 v18; // rdx
  char v19; // [rsp+40h] [rbp-38h]
  __int64 v20; // [rsp+88h] [rbp+10h] BYREF

  v20 = a2;
  v6 = a2;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000) != 0 )
  {
    v8 = a2 + 128;
    v19 = a4 != 0 ? 89 : 78;
    v9 = a3 != 0;
    v10 = *(_QWORD *)(a2 + 48);
    v11 = *(_QWORD *)(a2 + 24);
    LOBYTE(a2) = v9 ? 89 : 78;
    WPP_SF_qZqqcc(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), a2, v8, v11, v6 + 128, v6, v10, a2, v19);
  }
  result = *(unsigned int *)(v6 + 68);
  if ( (result & 8) == 0 )
  {
    if ( (result & 0x10) != 0 )
    {
      v13 = *(_QWORD *)(v6 + 24);
      *(_QWORD *)(v13 + 512) = RtlDelete((PRTL_SPLAY_LINKS)(v6 + 104));
    }
    if ( (*(_DWORD *)(v6 + 68) & 0x20) != 0 )
    {
      v14 = *(_QWORD *)(v6 + 24);
      *(_QWORD *)(v14 + 520) = RtlDelete((PRTL_SPLAY_LINKS)(v6 + 144));
    }
    if ( (*(_DWORD *)(v6 + 68) & 0x40) != 0 )
    {
      v15 = *(_QWORD *)(v6 + 24);
      *(_QWORD *)(v15 + 528) = RtlDelete((PRTL_SPLAY_LINKS)(v6 + 184));
    }
    result = *(_DWORD *)(v6 + 68) & 0xFFFFFF87 | 8;
    *(_DWORD *)(v6 + 68) = result;
  }
  if ( a3 )
  {
    v16 = *(_QWORD *)(v6 + 8);
    if ( *(_QWORD *)(v16 + 8) != v6 + 8
      || (v17 = *(_QWORD **)(v6 + 16), *v17 != v6 + 8)
      || (*v17 = v16, *(_QWORD *)(v16 + 8) = v17, v18 = *(_QWORD *)(v6 + 32), *(_QWORD *)(v18 + 8) != v6 + 32)
      || (result = *(_QWORD *)(v6 + 40), *(_QWORD *)result != v6 + 32) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)result = v18;
    *(_QWORD *)(v18 + 8) = result;
    *(_DWORD *)(v6 + 68) |= 0x100u;
  }
  if ( a4 )
    return UdfFreeLcb(&v20);
  return result;
}

```

## disassembly

```asm
0x14002cca0  mov     r11, rsp
0x14002cca3  mov     [r11+10h], rdx
0x14002cca7  push    rbx
0x14002cca8  push    rbp
0x14002cca9  push    rsi
0x14002ccaa  push    rdi
0x14002ccab  sub     rsp, 58h
0x14002ccaf  mov     bpl, r9b
0x14002ccb2  mov     sil, r8b
0x14002ccb5  mov     rdi, rdx
0x14002ccb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ccbf  lea     rax, WPP_GLOBAL_Control
0x14002ccc6  cmp     rcx, rax
0x14002ccc9  jz      short loc_14002CD1D
0x14002cccb  test    dword ptr [rcx+2Ch], 8000h
0x14002ccd2  jz      short loc_14002CD1D
0x14002ccd4  mov     rcx, [rcx+18h]
0x14002ccd8  mov     al, r9b
0x14002ccdb  neg     al
0x14002ccdd  mov     al, r8b
0x14002cce0  lea     r8, [rdi+80h]
0x14002cce7  sbb     r9b, r9b
0x14002ccea  and     r9b, 0Bh
0x14002ccee  add     r9b, 4Eh ; 'N'
0x14002ccf2  mov     [r11-38h], r9b
0x14002ccf6  neg     al
0x14002ccf8  mov     rax, [rdi+30h]
0x14002ccfc  mov     r9, [rdi+18h]
0x14002cd00  sbb     dl, dl
0x14002cd02  and     dl, 0Bh
0x14002cd05  add     dl, 4Eh ; 'N'
0x14002cd08  mov     [rsp+78h+var_40], dl
0x14002cd0c  mov     [r11-48h], rax
0x14002cd10  mov     [r11-50h], rdi
0x14002cd14  mov     [r11-58h], r8
0x14002cd18  call    WPP_SF_qZqqcc
0x14002cd1d  mov     eax, [rdi+44h]
0x14002cd20  test    al, 8
0x14002cd22  jnz     short loc_14002CD99
0x14002cd24  test    al, 10h
0x14002cd26  jz      short loc_14002CD43
0x14002cd28  mov     rbx, [rdi+18h]
0x14002cd2c  lea     rcx, [rdi+68h]; Links
0x14002cd30  call    cs:__imp_RtlDelete
0x14002cd37  nop     dword ptr [rax+rax+00h]
0x14002cd3c  mov     [rbx+200h], rax
0x14002cd43  mov     eax, [rdi+44h]
0x14002cd46  test    al, 20h
0x14002cd48  jz      short loc_14002CD68
0x14002cd4a  mov     rbx, [rdi+18h]
0x14002cd4e  lea     rcx, [rdi+90h]; Links
0x14002cd55  call    cs:__imp_RtlDelete
0x14002cd5c  nop     dword ptr [rax+rax+00h]
0x14002cd61  mov     [rbx+208h], rax
0x14002cd68  mov     eax, [rdi+44h]
0x14002cd6b  test    al, 40h
0x14002cd6d  jz      short loc_14002CD8D
0x14002cd6f  mov     rbx, [rdi+18h]
0x14002cd73  lea     rcx, [rdi+0B8h]; Links
0x14002cd7a  call    cs:__imp_RtlDelete
0x14002cd81  nop     dword ptr [rax+rax+00h]
0x14002cd86  mov     [rbx+210h], rax
0x14002cd8d  mov     eax, [rdi+44h]
0x14002cd90  and     eax, 0FFFFFF8Fh
0x14002cd93  or      eax, 8
0x14002cd96  mov     [rdi+44h], eax
0x14002cd99  test    sil, sil
0x14002cd9c  jz      short loc_14002CDDD
0x14002cd9e  lea     rax, [rdi+8]
0x14002cda2  mov     rcx, [rax]
0x14002cda5  cmp     [rcx+8], rax
0x14002cda9  jnz     short loc_14002CDF9
0x14002cdab  mov     rdx, [rax+8]
0x14002cdaf  cmp     [rdx], rax
0x14002cdb2  jnz     short loc_14002CDF9
0x14002cdb4  mov     [rdx], rcx
0x14002cdb7  mov     [rcx+8], rdx
0x14002cdbb  lea     rcx, [rdi+20h]
0x14002cdbf  mov     rdx, [rcx]
0x14002cdc2  cmp     [rdx+8], rcx
0x14002cdc6  jnz     short loc_14002CDF9
0x14002cdc8  mov     rax, [rcx+8]
0x14002cdcc  cmp     [rax], rcx
0x14002cdcf  jnz     short loc_14002CDF9
0x14002cdd1  mov     [rax], rdx
0x14002cdd4  mov     [rdx+8], rax
0x14002cdd8  bts     dword ptr [rdi+44h], 8
0x14002cddd  test    bpl, bpl
0x14002cde0  jz      short loc_14002CDEF
0x14002cde2  lea     rcx, [rsp+78h+arg_8]
0x14002cdea  call    UdfFreeLcb
0x14002cdef  add     rsp, 58h
0x14002cdf3  pop     rdi
0x14002cdf4  pop     rsi
0x14002cdf5  pop     rbp
0x14002cdf6  pop     rbx
0x14002cdf7  retn
0x14002cdf9  mov     ecx, 3
0x14002cdfe  int     29h; Win8: RtlFailFast(ecx)
```
