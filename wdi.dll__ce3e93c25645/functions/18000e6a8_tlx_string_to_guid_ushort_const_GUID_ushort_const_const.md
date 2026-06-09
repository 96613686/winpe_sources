# tlx::string_to_guid<ushort const *>(_GUID *,ushort const * const &)

- ea: `0x18000e6a8`
- end: `0x18000e9b3`
- name: `??$string_to_guid@PEBG@tlx@@YAPEBGPEAU_GUID@@AEBQEBG@Z`
- size: `779`
- prototype: `__int64 __fastcall(_BYTE *, _WORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cf0`

## callees

- `0x18000e6a8`
- `0x18000e9bc`

## pseudocode

```c
__int64 __fastcall tlx::string_to_guid<unsigned short const *>(_BYTE *a1, _WORD **a2)
{
  _WORD *v2; // r9
  unsigned __int64 v4; // rdx
  unsigned __int8 v5; // al
  __int64 v6; // rbx
  unsigned __int16 *v7; // r9
  unsigned int v8; // edx
  char v9; // al
  char v10; // r8
  __int64 v11; // r9
  unsigned int v12; // edx
  unsigned int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // edx
  __int64 v18; // r9
  unsigned int v19; // eax
  __int64 v20; // r9
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // edx
  __int64 v24; // r9
  unsigned int v25; // eax
  __int64 v26; // r9
  unsigned int v27; // eax
  int v28; // edx
  unsigned int v29; // edx
  __int64 v30; // r9
  unsigned int v31; // eax
  __int64 v32; // r9
  unsigned int v33; // eax
  __int64 v34; // r9
  int v35; // edx
  unsigned int v36; // edx
  unsigned int v37; // eax
  unsigned __int16 *v38; // r8
  unsigned int v39; // eax
  int v40; // edx
  unsigned int v41; // edx
  __int64 v42; // r8
  unsigned int v43; // eax
  __int64 v44; // r8
  unsigned int v45; // eax
  __int64 v46; // r8
  int v47; // edx
  unsigned int v48; // edx
  unsigned int v49; // eax
  __int64 v50; // r9
  unsigned int v51; // eax
  int v52; // edx
  unsigned int v53; // edx
  __int64 v54; // r9
  unsigned int v55; // eax
  __int64 v56; // r9
  unsigned int v57; // eax
  int v58; // edx
  unsigned int v59; // edx
  __int64 v60; // r9
  unsigned int v61; // eax
  unsigned __int16 *v62; // r8
  unsigned int v63; // eax
  int v64; // edx
  unsigned int v65; // edx
  __int64 v66; // r8
  unsigned int v67; // eax
  __int64 v68; // r8
  unsigned int v69; // eax
  __int64 v70; // r8
  int v71; // edx
  unsigned int v72; // edx
  unsigned int v73; // eax
  __int64 v74; // r9
  unsigned int v75; // eax
  int v76; // edx
  unsigned int v77; // edx
  __int64 v78; // r9
  unsigned int v79; // eax
  __int64 v80; // r9
  unsigned int v81; // eax
  int v82; // edx
  unsigned int v83; // edx
  __int64 v84; // r9
  unsigned int v85; // eax
  __int64 v86; // r9
  unsigned int v87; // eax
  int v88; // edx
  unsigned int v89; // edx
  __int64 v90; // r9
  unsigned int v91; // eax
  __int64 v92; // r9
  unsigned int v93; // eax
  int v94; // edx
  unsigned int v95; // edx
  __int64 v96; // r9
  unsigned int v97; // eax
  __int64 v98; // r9
  unsigned int v99; // eax
  unsigned int v100; // r8d
  unsigned __int8 v101; // r11
  __int64 v102; // r9
  unsigned __int64 v103; // r9
  int v104; // edx
  int v105; // edx

  v2 = *a2;
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  v5 = 32;
  if ( v4 <= 0x20 )
  {
    v6 = 0;
  }
  else
  {
    if ( *v2 == 123 || *v2 == 40 )
    {
      ++v2;
      v5 = 34;
    }
    v6 = 0;
    if ( v2[8] == 45 )
    {
      if ( v2[13] != 45 || v2[18] != 45 || v2[23] != 45 )
        return 0;
      v5 += 4;
      v6 = 1;
    }
  }
  if ( v4 >= v5 )
  {
    tlx::hex_to_u4((tlx *)(unsigned __int16)v2[1], v4);
    v9 = tlx::hex_to_u4((tlx *)*v7, v8);
    a1[3] = (16 * v9) | v10;
    v13 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v11 + 6), v12);
    v15 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v14 + 4), v13);
    v17 = (16 * v15) | v16;
    a1[2] = v17;
    v19 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v18 + 10), v17);
    v21 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v20 + 8), v19);
    v23 = (16 * v21) | v22;
    a1[1] = v23;
    v25 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v24 + 14), v23);
    v27 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v26 + 12), v25);
    v29 = (16 * v27) | v28;
    *a1 = v29;
    v31 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v30 + 2 * v6 + 18), v29);
    v33 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v32 + 2 * v6 + 16), v31);
    v36 = (16 * v33) | v35;
    a1[5] = v36;
    v37 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v34 + 20 + 2 * v6 + 2), v36);
    v39 = tlx::hex_to_u4((tlx *)*v38, v37);
    v41 = (16 * v39) | v40;
    a1[4] = v41;
    v43 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v42 + 2 * v6 + 6), v41);
    v45 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v44 + 2 * v6 + 4), v43);
    v48 = (16 * v45) | v47;
    a1[7] = v48;
    v49 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v46 + 2 * v6 + 10), v48);
    v51 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v50 + 8), v49);
    v53 = (16 * v51) | v52;
    a1[6] = v53;
    v55 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v54 + 2 * v6 + 14), v53);
    v57 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v56 + 2 * v6 + 12), v55);
    v59 = (16 * v57) | v58;
    a1[8] = v59;
    v61 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v60 + 16 + 2 * v6 + 2), v59);
    v63 = tlx::hex_to_u4((tlx *)*v62, v61);
    v65 = (16 * v63) | v64;
    a1[9] = v65;
    v67 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v66 + 2 * v6 + 6), v65);
    v69 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v68 + 2 * v6 + 4), v67);
    v72 = (16 * v69) | v71;
    a1[10] = v72;
    v73 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v70 + 2 * v6 + 10), v72);
    v75 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v74 + 8), v73);
    v77 = (16 * v75) | v76;
    a1[11] = v77;
    v79 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v78 + 14), v77);
    v81 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v80 + 12), v79);
    v83 = (16 * v81) | v82;
    a1[12] = v83;
    v85 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v84 + 18), v83);
    v87 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v86 + 16), v85);
    v89 = (16 * v87) | v88;
    a1[13] = v89;
    v91 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v90 + 22), v89);
    v93 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v92 + 20), v91);
    v95 = (16 * v93) | v94;
    a1[14] = v95;
    v97 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v96 + 26), v95);
    v99 = tlx::hex_to_u4((tlx *)*(unsigned __int16 *)(v98 + 24), v97);
    v103 = v102 + 28;
    v105 = (16 * v99) | v104;
    a1[15] = v105;
    if ( !v101 )
      return v103 & -(__int64)((v105 | v100) < 0x100);
    if ( *(_WORD *)v103 == v101 )
    {
      v103 += 2LL;
      return v103 & -(__int64)((v105 | v100) < 0x100);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e6a8  mov     [rsp+arg_0], rbx
0x18000e6ad  mov     [rsp+arg_8], rsi
0x18000e6b2  push    rdi
0x18000e6b3  sub     rsp, 20h
0x18000e6b7  mov     r9, [rdx]
0x18000e6ba  mov     rdi, rcx
0x18000e6bd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000e6c1  xor     esi, esi
0x18000e6c3  inc     rdx; unsigned int
0x18000e6c6  cmp     [r9+rdx*2], si
0x18000e6cb  jnz     short loc_18000E6C3
0x18000e6cd  mov     eax, 20h ; ' '
0x18000e6d2  mov     r11b, sil
0x18000e6d5  cmp     rdx, rax
0x18000e6d8  jbe     short loc_18000E73A
0x18000e6da  movzx   ecx, word ptr [r9]
0x18000e6de  cmp     cx, 7Bh ; '{'
0x18000e6e2  jz      short loc_18000E6EA
0x18000e6e4  cmp     cx, 28h ; '('
0x18000e6e8  jnz     short loc_18000E702
0x18000e6ea  mov     r11d, 7Dh ; '}'
0x18000e6f0  add     r9, 2
0x18000e6f4  cmp     cx, 7Bh ; '{'
0x18000e6f8  mov     al, 22h ; '"'
0x18000e6fa  lea     r8d, [r11-54h]
0x18000e6fe  cmovnz  r11d, r8d
0x18000e702  mov     cx, 2Dh ; '-'
0x18000e706  mov     rbx, rsi
0x18000e709  cmp     [r9+10h], cx
0x18000e70e  jnz     short loc_18000E73D
0x18000e710  cmp     [r9+1Ah], cx
0x18000e715  jnz     loc_18000E9A1
0x18000e71b  cmp     [r9+24h], cx
0x18000e720  jnz     loc_18000E9A1
0x18000e726  cmp     [r9+2Eh], cx
0x18000e72b  jnz     loc_18000E9A1
0x18000e731  add     al, 4
0x18000e733  mov     ebx, 1
0x18000e738  jmp     short loc_18000E73D
0x18000e73a  mov     rbx, rsi
0x18000e73d  movzx   eax, al
0x18000e740  cmp     rdx, rax
0x18000e743  jb      loc_18000E9A1
0x18000e749  movzx   ecx, word ptr [r9+2]; this
0x18000e74e  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e753  movzx   ecx, word ptr [r9]; this
0x18000e757  mov     r8d, eax
0x18000e75a  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e75f  shl     eax, 4
0x18000e762  or      r8d, eax
0x18000e765  mov     [rdi+3], r8b
0x18000e769  movzx   ecx, word ptr [r9+6]; this
0x18000e76e  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e773  movzx   ecx, word ptr [r9+4]; this
0x18000e778  mov     edx, eax; unsigned int
0x18000e77a  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e77f  shl     eax, 4
0x18000e782  or      edx, eax; unsigned int
0x18000e784  mov     r10d, edx
0x18000e787  mov     [rdi+2], dl
0x18000e78a  movzx   ecx, word ptr [r9+0Ah]; this
0x18000e78f  or      r10d, r8d
0x18000e792  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e797  movzx   ecx, word ptr [r9+8]; this
0x18000e79c  mov     edx, eax; unsigned int
0x18000e79e  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e7a3  shl     eax, 4
0x18000e7a6  or      edx, eax; unsigned int
0x18000e7a8  mov     [rdi+1], dl
0x18000e7ab  or      r10d, edx
0x18000e7ae  movzx   ecx, word ptr [r9+0Eh]; this
0x18000e7b3  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e7b8  movzx   ecx, word ptr [r9+0Ch]; this
0x18000e7bd  mov     edx, eax; unsigned int
0x18000e7bf  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e7c4  shl     eax, 4
0x18000e7c7  or      edx, eax; unsigned int
0x18000e7c9  mov     [rdi], dl
0x18000e7cb  or      r10d, edx
0x18000e7ce  movzx   ecx, word ptr [r9+rbx*2+12h]; this
0x18000e7d4  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e7d9  movzx   ecx, word ptr [r9+rbx*2+10h]; this
0x18000e7df  mov     edx, eax; unsigned int
0x18000e7e1  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e7e6  shl     eax, 4
0x18000e7e9  lea     r8, [r9+14h]
0x18000e7ed  or      edx, eax; unsigned int
0x18000e7ef  lea     r8, [r8+rbx*2]
0x18000e7f3  mov     [rdi+5], dl
0x18000e7f6  or      r10d, edx
0x18000e7f9  movzx   ecx, word ptr [r8+2]; this
0x18000e7fe  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e803  movzx   ecx, word ptr [r8]; this
0x18000e807  mov     edx, eax; unsigned int
0x18000e809  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e80e  shl     eax, 4
0x18000e811  or      edx, eax; unsigned int
0x18000e813  mov     [rdi+4], dl
0x18000e816  or      r10d, edx
0x18000e819  movzx   ecx, word ptr [r8+rbx*2+6]; this
0x18000e81f  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e824  movzx   ecx, word ptr [r8+rbx*2+4]; this
0x18000e82a  mov     edx, eax; unsigned int
0x18000e82c  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e831  shl     eax, 4
0x18000e834  lea     r9, [r8+rbx*2]
0x18000e838  or      edx, eax; unsigned int
0x18000e83a  mov     [rdi+7], dl
0x18000e83d  or      r10d, edx
0x18000e840  movzx   ecx, word ptr [r9+0Ah]; this
0x18000e845  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e84a  movzx   ecx, word ptr [r9+8]; this
0x18000e84f  mov     edx, eax; unsigned int
0x18000e851  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e856  shl     eax, 4
0x18000e859  or      edx, eax; unsigned int
0x18000e85b  mov     [rdi+6], dl
0x18000e85e  or      r10d, edx
0x18000e861  movzx   ecx, word ptr [r9+rbx*2+0Eh]; this
0x18000e867  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e86c  movzx   ecx, word ptr [r9+rbx*2+0Ch]; this
0x18000e872  mov     edx, eax; unsigned int
0x18000e874  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e879  shl     eax, 4
0x18000e87c  or      edx, eax; unsigned int
0x18000e87e  lea     r8, [r9+10h]
0x18000e882  lea     r8, [r8+rbx*2]
0x18000e886  mov     [rdi+8], dl
0x18000e889  movzx   ecx, word ptr [r8+2]; this
0x18000e88e  or      r10d, edx
0x18000e891  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e896  movzx   ecx, word ptr [r8]; this
0x18000e89a  mov     edx, eax; unsigned int
0x18000e89c  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8a1  shl     eax, 4
0x18000e8a4  or      edx, eax; unsigned int
0x18000e8a6  mov     [rdi+9], dl
0x18000e8a9  or      r10d, edx
0x18000e8ac  movzx   ecx, word ptr [r8+rbx*2+6]; this
0x18000e8b2  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8b7  movzx   ecx, word ptr [r8+rbx*2+4]; this
0x18000e8bd  mov     edx, eax; unsigned int
0x18000e8bf  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8c4  shl     eax, 4
0x18000e8c7  lea     r9, [r8+rbx*2]
0x18000e8cb  or      edx, eax; unsigned int
0x18000e8cd  mov     [rdi+0Ah], dl
0x18000e8d0  or      r10d, edx
0x18000e8d3  movzx   ecx, word ptr [r9+0Ah]; this
0x18000e8d8  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8dd  movzx   ecx, word ptr [r9+8]; this
0x18000e8e2  mov     edx, eax; unsigned int
0x18000e8e4  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8e9  shl     eax, 4
0x18000e8ec  or      edx, eax; unsigned int
0x18000e8ee  mov     [rdi+0Bh], dl
0x18000e8f1  or      r10d, edx
0x18000e8f4  movzx   ecx, word ptr [r9+0Eh]; this
0x18000e8f9  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e8fe  movzx   ecx, word ptr [r9+0Ch]; this
0x18000e903  mov     edx, eax; unsigned int
0x18000e905  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e90a  shl     eax, 4
0x18000e90d  or      edx, eax; unsigned int
0x18000e90f  mov     [rdi+0Ch], dl
0x18000e912  or      r10d, edx
0x18000e915  movzx   ecx, word ptr [r9+12h]; this
0x18000e91a  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e91f  movzx   ecx, word ptr [r9+10h]; this
0x18000e924  mov     edx, eax; unsigned int
0x18000e926  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e92b  shl     eax, 4
0x18000e92e  or      edx, eax; unsigned int
0x18000e930  mov     [rdi+0Dh], dl
0x18000e933  or      r10d, edx
0x18000e936  movzx   ecx, word ptr [r9+16h]; this
0x18000e93b  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e940  movzx   ecx, word ptr [r9+14h]; this
0x18000e945  mov     edx, eax; unsigned int
0x18000e947  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e94c  shl     eax, 4
0x18000e94f  or      edx, eax; unsigned int
0x18000e951  mov     r8d, edx
0x18000e954  mov     [rdi+0Eh], dl
0x18000e957  movzx   ecx, word ptr [r9+1Ah]; this
0x18000e95c  or      r8d, r10d
0x18000e95f  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e964  movzx   ecx, word ptr [r9+18h]; this
0x18000e969  mov     edx, eax; unsigned int
0x18000e96b  call    ?hex_to_u4@tlx@@YAII@Z; tlx::hex_to_u4(uint)
0x18000e970  shl     eax, 4
0x18000e973  add     r9, 1Ch
0x18000e977  or      edx, eax
0x18000e979  mov     [rdi+0Fh], dl
0x18000e97c  test    r11b, r11b
0x18000e97f  jz      short loc_18000E98F
0x18000e981  movzx   ecx, r11b
0x18000e985  cmp     [r9], cx
0x18000e989  jnz     short loc_18000E9A1
0x18000e98b  add     r9, 2
0x18000e98f  or      r8d, edx
0x18000e992  cmp     r8d, 100h
0x18000e999  sbb     rax, rax
0x18000e99c  and     rax, r9
0x18000e99f  jmp     short loc_18000E9A3
0x18000e9a1  xor     eax, eax
0x18000e9a3  mov     rbx, [rsp+28h+arg_0]
0x18000e9a8  mov     rsi, [rsp+28h+arg_8]
0x18000e9ad  add     rsp, 20h
0x18000e9b1  pop     rdi
0x18000e9b2  retn
```
