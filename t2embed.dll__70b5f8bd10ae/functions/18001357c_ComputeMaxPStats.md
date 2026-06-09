# ComputeMaxPStats

- ea: `0x18001357c`
- end: `0x180013b3e`
- name: `ComputeMaxPStats`
- size: `1474`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180028dfc`

## callees

- `0x18000faf0`
- `0x18000ffc4`
- `0x180010018`
- `0x180013230`
- `0x1800134b4`
- `0x18001357c`
- `0x180013b44`
- `0x180015190`
- `0x180016438`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall ComputeMaxPStats(
        __int64 a1,
        __int16 *a2,
        unsigned __int16 *a3,
        __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        __int64 a9,
        __int16 a10)
{
  unsigned __int16 *v10; // r15
  __int16 *v11; // r13
  unsigned __int16 v13; // r14
  int v14; // edi
  int v15; // esi
  __int16 v16; // r12
  int i; // ecx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 result; // rax
  int v22; // r14d
  int v23; // edi
  unsigned __int16 v24; // si
  unsigned __int16 v25; // cx
  unsigned __int16 GenericSize; // ax
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // edx
  unsigned __int16 v31; // r8
  __int16 v32; // ax
  __int16 v33; // r12
  unsigned __int16 v34; // r13
  unsigned __int16 v35; // r14
  unsigned __int16 v36; // dx
  unsigned __int16 j; // r15
  unsigned __int16 v38; // cx
  unsigned __int16 *v39; // r14
  __int16 v40; // ax
  unsigned __int16 v41; // ax
  unsigned __int16 *v42; // rax
  unsigned __int16 v43; // ax
  unsigned __int16 v44; // di
  unsigned __int16 v45; // ax
  unsigned __int16 v46; // dx
  unsigned int v47; // ecx
  unsigned __int16 v48; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v49[2]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v51; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+64h] [rbp-9Ch]
  int v54; // [rsp+68h] [rbp-98h]
  unsigned __int16 NumGlyphs; // [rsp+6Ch] [rbp-94h]
  int v56; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v59; // [rsp+80h] [rbp-80h]
  __int16 *v60; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v61; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v62; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v64; // [rsp+A8h] [rbp-58h]
  __int16 *v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v67; // [rsp+C0h] [rbp-40h]
  _OWORD v68[3]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v69; // [rsp+F8h] [rbp-8h]

  v10 = a6;
  v11 = a2;
  v65 = a2;
  *a2 = 0;
  *a3 = 0;
  *a6 = 0;
  *a4 = 0;
  *a5 = 0;
  v58 = a9;
  v61 = a5;
  *a7 = 0;
  *a8 = 0;
  v60 = a4;
  v59 = a3;
  v62 = a6;
  v63 = a7;
  v64 = a8;
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  v51 = 0;
  NumGlyphs = GetNumGlyphs(a1);
  v13 = NumGlyphs;
  if ( !NumGlyphs )
    return 1009;
  v53 = TTTableOffset(a1, "loca");
  v14 = v53;
  if ( !v53 )
    return 1035;
  v54 = TTTableOffset(a1, "glyf");
  v15 = v54;
  if ( !v54 )
    return 1031;
  if ( !(unsigned int)GetGeneric(a1, v68, 0) )
    return 1032;
  v16 = WORD1(v69);
  for ( i = 0; ; LOWORD(i) = v56 + 1 )
  {
    v56 = i;
    if ( (unsigned __int16)i >= v13 )
      break;
    v18 = *(_QWORD *)a1;
    v66 = 0;
    v67 = 0;
    v49[0] = 0;
    if ( v16 )
    {
      if ( !v18 )
        return 1001;
      v29 = v14 + 4 * (unsigned int)(unsigned __int16)i;
      if ( (int)v29 + 4 < (unsigned int)v29
        || (unsigned int)(v29 + 4) > *(_DWORD *)(a1 + 8)
        || (int)v29 + 8 < (unsigned int)(v29 + 4)
        || (unsigned int)(v29 + 8) > *(_DWORD *)(a1 + 8) )
      {
        return 1001;
      }
      v30 = *(unsigned __int8 *)((unsigned int)v29 + v18 + 3)
          | ((*(unsigned __int8 *)((unsigned int)v29 + v18 + 2)
            | (((*(unsigned __int8 *)(v29 + v18) << 8) | *(unsigned __int8 *)(v29 + v18 + 1)) << 8)) << 8);
      v31 = _byteswap_ushort(*(_WORD *)((unsigned int)(v29 + 4) + v18 + 2));
    }
    else
    {
      if ( !v18 )
        return 1001;
      v19 = v14 + 2 * (unsigned int)(unsigned __int16)i;
      v20 = (unsigned int)(v19 + 2);
      if ( (unsigned int)v20 < (unsigned int)v19 || (unsigned int)v20 > *(_DWORD *)(a1 + 8) )
        return 1001;
      if ( (int)v19 + 4 < (unsigned int)(v19 + 2) || (unsigned int)(v19 + 4) > *(_DWORD *)(a1 + 8) )
        return 1001;
      v30 = 2 * ((*(unsigned __int8 *)(v19 + v18) << 8) | *(unsigned __int8 *)(v19 + v18 + 1));
      v31 = 2 * _byteswap_ushort(*(_WORD *)(v20 + v18));
    }
    if ( v31 != (_WORD)v30 )
    {
      v22 = v30 + v15;
      result = ReadGeneric((__int64 *)a1, (__int64)&v66, 0xAu, (unsigned __int8 *)&GLYF_HEADER_CONTROL, v30 + v15, v49);
      if ( (_WORD)result )
        return result;
      v23 = (__int16)v66;
      v24 = 0;
      v25 = 0;
      if ( (__int16)v66 > 0 )
      {
        GenericSize = GetGenericSize(&GLYF_HEADER_CONTROL);
        v27 = *(_QWORD *)a1;
        if ( !*(_QWORD *)a1 )
          return 1001;
        v28 = v22 + (unsigned int)GenericSize + 2 * v23;
        if ( (unsigned int)v28 < 2
          || (unsigned int)v28 > *(_DWORD *)(a1 + 8)
          || (int)v28 + 2 < (unsigned int)v28
          || (unsigned int)(v28 + 2) > *(_DWORD *)(a1 + 8) )
        {
          return 1001;
        }
        v24 = _byteswap_ushort(*(_WORD *)((unsigned int)(v28 - 2) + v27)) + 1;
        v25 = _byteswap_ushort(*(_WORD *)(v28 + v27));
LABEL_30:
        v32 = *v11;
        if ( (unsigned __int16)*v11 <= (unsigned __int16)v23 )
          v32 = v23;
        v14 = v53;
        *v11 = v32;
        if ( *v59 > v24 )
          v24 = *v59;
        *v59 = v24;
        v15 = v54;
        if ( *v10 > v25 )
          v25 = *v10;
        *v10 = v25;
        goto LABEL_15;
      }
      if ( (v66 & 0x8000u) == 0LL )
        goto LABEL_30;
      if ( (_WORD)v66 != 0xFFFF )
        return 1061;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v51 = 0;
      v52 = 0;
      v49[0] = 0;
      v50[0] = 0;
      v48 = 0;
      v57 = 0;
      GetComponentGlyphList(
        a1,
        (unsigned __int16)v56,
        (unsigned int)&v48,
        v58,
        a10,
        (__int64)&v51,
        0,
        SWORD1(v69),
        v53,
        v54);
      v36 = v48;
      for ( j = 0; ; ++j )
      {
        if ( j >= v36 )
        {
          LOWORD(v23) = v33;
          v24 = v34;
          v38 = v35;
          goto LABEL_47;
        }
        if ( (unsigned __int16)GetGlyphStats(
                                 a1,
                                 *(unsigned __int16 *)(v58 + 2LL * j),
                                 (unsigned int)&v52,
                                 (unsigned int)v49,
                                 (__int64)v50,
                                 SWORD1(v69),
                                 v53,
                                 v54,
                                 (__int64)&v57) )
          break;
        if ( v57 == 1 && v52 > 0 )
        {
          v34 += v49[0];
          v33 += v52;
          if ( v35 <= v50[0] )
            v35 = v50[0];
        }
        v36 = v48;
      }
      v36 = v48;
      v38 = 0;
LABEL_47:
      v10 = v62;
      v39 = v64;
      v40 = *v60;
      if ( (unsigned __int16)*v60 <= (unsigned __int16)v23 )
        v40 = v23;
      *v60 = v40;
      v41 = *v61;
      if ( *v61 <= v24 )
        v41 = v24;
      *v61 = v41;
      v42 = v63;
      if ( *v10 > v38 )
        v38 = *v10;
      *v10 = v38;
      if ( *v42 > v36 )
        v36 = *v42;
      *v42 = v36;
      v43 = v51;
      if ( *v39 > v51 )
        v43 = *v39;
      v14 = v53;
      v15 = v54;
      v16 = WORD1(v69);
      v11 = v65;
      *v39 = v43;
    }
LABEL_15:
    HIWORD(i) = HIWORD(v56);
    v13 = NumGlyphs;
  }
  v44 = TTTableLength(a1, "prep");
  v45 = TTTableLength(a1, "fpgm");
  v46 = v44;
  v47 = v44;
  if ( v44 <= v45 )
    v47 = v45;
  if ( v47 <= *v10 )
  {
    v46 = *v10;
  }
  else if ( v44 <= v45 )
  {
    v46 = v45;
  }
  *v10 = v46;
  return 0;
}

```

## disassembly

```asm
0x18001357c  push    rbp
0x18001357e  push    rbx
0x18001357f  push    rsi
0x180013580  push    rdi
0x180013581  push    r12
0x180013583  push    r13
0x180013585  push    r14
0x180013587  push    r15
0x180013589  lea     rbp, [rsp-18h]
0x18001358e  sub     rsp, 118h
0x180013595  mov     rax, cs:__security_cookie
0x18001359c  xor     rax, rsp
0x18001359f  mov     [rbp+50h+var_50], rax
0x1800135a3  mov     r15, [rbp+50h+arg_28]
0x1800135aa  xor     r12d, r12d
0x1800135ad  mov     r14, [rbp+50h+arg_38]
0x1800135b4  xorps   xmm0, xmm0
0x1800135b7  mov     rax, [rbp+50h+arg_40]
0x1800135be  mov     r13, rdx
0x1800135c1  mov     rbx, rcx
0x1800135c4  mov     [rbp+50h+var_A0], rdx
0x1800135c8  mov     rcx, [rbp+50h+arg_20]
0x1800135cf  mov     rdx, [rbp+50h+arg_30]
0x1800135d6  mov     [r13+0], r12w
0x1800135db  mov     [r8], r12w
0x1800135df  mov     [r15], r12w
0x1800135e3  mov     [r9], r12w
0x1800135e7  mov     [rcx], r12w
0x1800135eb  mov     [rsp+150h+var_D8], rax
0x1800135f0  xor     eax, eax
0x1800135f2  mov     [rbp+50h+var_C0], rcx
0x1800135f6  mov     rcx, rbx
0x1800135f9  mov     [rdx], r12w
0x1800135fd  mov     [r14], r12w
0x180013601  mov     [rbp+50h+var_C8], r9
0x180013605  mov     [rbp+50h+var_D0], r8
0x180013609  mov     [rbp+50h+var_B8], r15
0x18001360d  mov     [rbp+50h+var_B0], rdx
0x180013611  mov     [rbp+50h+var_A8], r14
0x180013615  movups  [rbp+50h+var_88], xmm0
0x180013619  mov     [rbp+50h+var_58], rax
0x18001361d  movups  [rbp+50h+var_78], xmm0
0x180013621  mov     [rsp+150h+var_F4], r12w
0x180013627  movups  [rbp+50h+var_68], xmm0
0x18001362b  call    GetNumGlyphs
0x180013630  mov     [rsp+150h+var_E4], ax
0x180013635  movzx   r14d, ax
0x180013639  test    ax, ax
0x18001363c  jz      loc_180013A74
0x180013642  lea     rdx, aLoca; "loca"
0x180013649  mov     rcx, rbx
0x18001364c  call    TTTableOffset
0x180013651  mov     [rsp+150h+var_EC], eax
0x180013655  mov     edi, eax
0x180013657  test    eax, eax
0x180013659  jz      loc_180013A7E
0x18001365f  lea     rdx, aGlyf; "glyf"
0x180013666  mov     rcx, rbx
0x180013669  call    TTTableOffset
0x18001366e  mov     [rsp+150h+var_E8], eax
0x180013672  mov     esi, eax
0x180013674  test    eax, eax
0x180013676  jz      loc_180013A88
0x18001367c  xor     r8d, r8d
0x18001367f  lea     rdx, [rbp+50h+var_88]
0x180013683  mov     rcx, rbx
0x180013686  call    GetGeneric
0x18001368b  xor     r10d, r10d
0x18001368e  test    eax, eax
0x180013690  jz      loc_180013A92
0x180013696  movzx   r12d, word ptr [rbp+50h+var_58+2]
0x18001369b  mov     ecx, r10d
0x18001369e  mov     [rsp+150h+var_E0], ecx
0x1800136a2  mov     r11d, 3E9h
0x1800136a8  cmp     cx, r14w
0x1800136ac  jnb     loc_180013AEA
0x1800136b2  mov     r9, [rbx]
0x1800136b5  xor     eax, eax
0x1800136b7  mov     [rbp+50h+var_98], rax
0x1800136bb  mov     [rbp+50h+var_90], ax
0x1800136bf  movzx   eax, cx
0x1800136c2  mov     [rsp+150h+var_FC], r10w
0x1800136c8  test    r12w, r12w
0x1800136cc  jnz     loc_1800137BC
0x1800136d2  test    r9, r9
0x1800136d5  jz      short loc_1800136EA
0x1800136d7  lea     eax, [rdi+rax*2]
0x1800136da  lea     ecx, [rax+2]
0x1800136dd  cmp     ecx, eax
0x1800136df  jb      short loc_1800136EA
0x1800136e1  cmp     ecx, [rbx+8]
0x1800136e4  jbe     loc_180013A20
0x1800136ea  mov     eax, r11d
0x1800136ed  jmp     short loc_1800136FC
0x1800136ef  cmp     edx, [rbx+8]
0x1800136f2  jbe     loc_180013A9C
0x1800136f8  movzx   eax, r11w
0x1800136fc  test    ax, ax
0x1800136ff  jnz     loc_18001379C
0x180013705  jmp     short loc_18001370D
0x180013707  cmp     r8w, dx
0x18001370b  jnz     short loc_18001371C
0x18001370d  mov     ecx, [rsp+150h+var_E0]
0x180013711  movzx   r14d, [rsp+150h+var_E4]
0x180013717  inc     cx
0x18001371a  jmp     short loc_18001369E
0x18001371c  lea     r14d, [rdx+rsi]
0x180013720  mov     r8d, 0Ah
0x180013726  lea     rax, [rsp+150h+var_FC]
0x18001372b  mov     rcx, rbx
0x18001372e  mov     [rsp+150h+var_128], rax
0x180013733  lea     r9, GLYF_HEADER_CONTROL
0x18001373a  lea     rdx, [rbp+50h+var_98]
0x18001373e  mov     dword ptr [rsp+150h+var_130], r14d
0x180013743  call    ReadGeneric
0x180013748  xor     r10d, r10d
0x18001374b  test    ax, ax
0x18001374e  jnz     short loc_18001379C
0x180013750  movsx   edi, word ptr [rbp+50h+var_98]
0x180013754  mov     esi, r10d
0x180013757  mov     ecx, r10d
0x18001375a  test    di, di
0x18001375d  jle     loc_18001383A
0x180013763  lea     rcx, GLYF_HEADER_CONTROL
0x18001376a  call    GetGenericSize
0x18001376f  mov     r9, [rbx]
0x180013772  xor     r10d, r10d
0x180013775  test    r9, r9
0x180013778  jz      short loc_180013797
0x18001377a  movzx   ecx, ax
0x18001377d  add     ecx, r14d
0x180013780  lea     r8d, [rcx+rdi*2]
0x180013784  lea     ecx, [r8-2]
0x180013788  cmp     r8d, ecx
0x18001378b  jb      short loc_180013797
0x18001378d  cmp     r8d, [rbx+8]
0x180013791  jbe     loc_180013A65
0x180013797  mov     eax, 3E9h
0x18001379c  mov     rcx, [rbp+50h+var_50]
0x1800137a0  xor     rcx, rsp; StackCookie
0x1800137a3  call    __security_check_cookie
0x1800137a8  add     rsp, 118h
0x1800137af  pop     r15
0x1800137b1  pop     r14
0x1800137b3  pop     r13
0x1800137b5  pop     r12
0x1800137b7  pop     rdi
0x1800137b8  pop     rsi
0x1800137b9  pop     rbx
0x1800137ba  pop     rbp
0x1800137bb  retn
0x1800137bc  test    r9, r9
0x1800137bf  jz      loc_1800136F8
0x1800137c5  lea     eax, [rdi+rax*4]
0x1800137c8  lea     r8d, [rax+4]
0x1800137cc  cmp     r8d, eax
0x1800137cf  jb      loc_1800136F8
0x1800137d5  cmp     r8d, [rbx+8]
0x1800137d9  ja      loc_1800136F8
0x1800137df  lea     ecx, [r8+4]
0x1800137e3  cmp     ecx, r8d
0x1800137e6  jb      loc_1800136F8
0x1800137ec  cmp     ecx, [rbx+8]
0x1800137ef  ja      loc_1800136F8
0x1800137f5  movzx   edx, byte ptr [rax+r9+1]
0x1800137fb  mov     ecx, eax
0x1800137fd  movzx   eax, byte ptr [rax+r9]
0x180013802  shl     eax, 8
0x180013805  or      edx, eax
0x180013807  movzx   eax, byte ptr [rcx+r9+2]
0x18001380d  shl     edx, 8
0x180013810  or      edx, eax
0x180013812  movzx   eax, byte ptr [rcx+r9+3]
0x180013818  shl     edx, 8
0x18001381b  or      edx, eax
0x18001381d  mov     eax, r8d
0x180013820  movzx   r8d, byte ptr [r8+r9+2]
0x180013826  shl     r8w, 8
0x18001382b  movzx   eax, byte ptr [rax+r9+3]
0x180013831  or      r8w, ax
0x180013835  jmp     loc_180013707
0x18001383a  js      short loc_180013875
0x18001383c  movzx   eax, word ptr [r13+0]
0x180013841  cmp     ax, di
0x180013844  cmovbe  ax, di
0x180013848  mov     edi, [rsp+150h+var_EC]
0x18001384c  mov     [r13+0], ax
0x180013851  mov     rax, [rbp+50h+var_D0]
0x180013855  cmp     [rax], si
0x180013858  cmova   si, [rax]
0x18001385c  mov     [rax], si
0x18001385f  cmp     [r15], cx
0x180013863  mov     esi, [rsp+150h+var_E8]
0x180013867  cmova   cx, [r15]
0x18001386c  mov     [r15], cx
0x180013870  jmp     loc_18001370D
0x180013875  cmp     di, 0FFFFh
0x180013879  jnz     loc_180013AE0
0x18001387f  mov     ecx, [rsp+150h+var_E8]
0x180013883  lea     rax, [rsp+150h+var_F4]
0x180013888  mov     r9, [rsp+150h+var_D8]
0x18001388d  lea     r8, [rsp+150h+var_100]
0x180013892  movzx   edx, word ptr [rsp+150h+var_E0]
0x180013897  mov     r12d, r10d
0x18001389a  mov     [rsp+150h+var_108], ecx
0x18001389e  mov     r13d, r10d
0x1800138a1  mov     ecx, [rsp+150h+var_EC]
0x1800138a5  mov     r14d, r10d
0x1800138a8  mov     dword ptr [rsp+150h+var_110], ecx
0x1800138ac  movzx   ecx, word ptr [rbp+50h+var_58+2]
0x1800138b0  mov     word ptr [rsp+150h+var_118], cx
0x1800138b5  mov     rcx, rbx
0x1800138b8  mov     word ptr [rsp+150h+var_120], r10w
0x1800138be  mov     [rsp+150h+var_128], rax
0x1800138c3  movzx   eax, [rbp+50h+arg_48]
0x1800138ca  mov     word ptr [rsp+150h+var_130], ax
0x1800138cf  mov     [rsp+150h+var_F4], r10w
0x1800138d5  mov     [rsp+150h+var_F0], r10w
0x1800138db  mov     [rsp+150h+var_FC], r10w
0x1800138e1  mov     [rsp+150h+var_F8], r10w
0x1800138e7  mov     [rsp+150h+var_100], r10w
0x1800138ed  mov     [rsp+150h+var_DC], r10d
0x1800138f2  call    GetComponentGlyphList
0x1800138f7  movzx   edx, [rsp+150h+var_100]
0x1800138fc  xor     r10d, r10d
0x1800138ff  mov     [rsp+150h+var_100], dx
0x180013904  mov     r15d, r10d
0x180013907  cmp     r15w, dx
0x18001390b  jnb     loc_1800139A2
0x180013911  lea     rax, [rsp+150h+var_DC]
0x180013916  movzx   edx, r15w
0x18001391a  mov     [rsp+150h+var_110], rax
0x18001391f  lea     r9, [rsp+150h+var_FC]
0x180013924  mov     eax, [rsp+150h+var_E8]
0x180013928  lea     r8, [rsp+150h+var_F0]
0x18001392d  mov     [rsp+150h+var_118], eax
0x180013931  mov     rcx, rbx
0x180013934  mov     eax, [rsp+150h+var_EC]
0x180013938  mov     [rsp+150h+var_120], eax
0x18001393c  movzx   eax, word ptr [rbp+50h+var_58+2]
0x180013940  mov     word ptr [rsp+150h+var_128], ax
0x180013945  lea     rax, [rsp+150h+var_F8]
0x18001394a  mov     [rsp+150h+var_130], rax
0x18001394f  mov     rax, [rsp+150h+var_D8]
0x180013954  movzx   edx, word ptr [rax+rdx*2]
0x180013958  call    GetGlyphStats
0x18001395d  xor     r10d, r10d
0x180013960  test    ax, ax
0x180013963  jnz     loc_180013ACA
0x180013969  lea     ecx, [r10+1]
0x18001396d  cmp     [rsp+150h+var_DC], ecx
0x180013971  jnz     short loc_180013994
0x180013973  movzx   eax, [rsp+150h+var_F0]
0x180013978  test    ax, ax
0x18001397b  jle     short loc_180013994
0x18001397d  add     r13w, [rsp+150h+var_FC]
0x180013983  add     r12w, ax
0x180013987  cmp     r14w, [rsp+150h+var_F8]
0x18001398d  cmovbe  r14w, [rsp+150h+var_F8]
0x180013994  movzx   edx, [rsp+150h+var_100]
0x180013999  add     r15w, cx
0x18001399d  jmp     loc_180013907
0x1800139a2  movzx   edi, r12w
0x1800139a6  movzx   esi, r13w
0x1800139aa  movzx   ecx, r14w
0x1800139ae  mov     r8, [rbp+50h+var_C8]
0x1800139b2  mov     r15, [rbp+50h+var_B8]
0x1800139b6  mov     r14, [rbp+50h+var_A8]
0x1800139ba  movzx   eax, word ptr [r8]
0x1800139be  cmp     ax, di
0x1800139c1  cmovbe  ax, di
0x1800139c5  mov     [r8], ax
0x1800139c9  mov     r8, [rbp+50h+var_C0]
0x1800139cd  movzx   eax, word ptr [r8]
0x1800139d1  cmp     ax, si
0x1800139d4  cmovbe  ax, si
0x1800139d8  mov     [r8], ax
0x1800139dc  cmp     [r15], cx
0x1800139e0  mov     rax, [rbp+50h+var_B0]
0x1800139e4  cmova   cx, [r15]
0x1800139e9  mov     [r15], cx
0x1800139ed  cmp     [rax], dx
0x1800139f0  cmova   dx, [rax]
0x1800139f4  mov     [rax], dx
0x1800139f7  movzx   eax, [rsp+150h+var_F4]
0x1800139fc  cmp     [r14], ax
0x180013a00  ja      loc_180013AD7
0x180013a06  mov     edi, [rsp+150h+var_EC]
0x180013a0a  mov     esi, [rsp+150h+var_E8]
0x180013a0e  movzx   r12d, word ptr [rbp+50h+var_58+2]
0x180013a13  mov     r13, [rbp+50h+var_A0]
0x180013a17  mov     [r14], ax
0x180013a1b  jmp     loc_18001370D
0x180013a20  lea     edx, [rcx+2]
0x180013a23  cmp     edx, ecx
0x180013a25  jb      loc_1800136F8
0x180013a2b  jmp     loc_1800136EF
0x180013a30  cmp     eax, [rbx+8]
0x180013a33  ja      loc_180013797
0x180013a39  movzx   eax, byte ptr [rcx+r9+1]
  ... truncated ...
```
