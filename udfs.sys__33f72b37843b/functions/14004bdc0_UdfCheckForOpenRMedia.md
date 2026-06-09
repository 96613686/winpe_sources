# UdfCheckForOpenRMedia

- ea: `0x14004bdc0`
- end: `0x14004c1ad`
- name: `UdfCheckForOpenRMedia`
- size: `1005`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004b7a4`

## callees

- `0x14000ca10`
- `0x14000cad4`
- `0x14001093c`
- `0x14001bc30`
- `0x14002fe08`
- `0x14004bdc0`
- `0x14004c1b4`

## pseudocode

```c
__int64 __fastcall UdfCheckForOpenRMedia(
        __int64 a1,
        struct _DEVICE_OBJECT *a2,
        _BYTE *a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  int TrackInfo; // r14d
  unsigned __int8 v10; // r13
  char v11; // r14
  char v12; // al
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  _BYTE *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  union _LARGE_INTEGER v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  size_t v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v24; // [rsp+50h] [rbp-B0h]
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v30; // [rsp+82h] [rbp-7Eh]
  unsigned __int8 v31; // [rsp+85h] [rbp-7Bh]
  unsigned __int8 v32; // [rsp+86h] [rbp-7Ah]
  char v33; // [rsp+87h] [rbp-79h]
  char v34; // [rsp+88h] [rbp-78h]
  char v35; // [rsp+89h] [rbp-77h]
  char v36; // [rsp+8Ah] [rbp-76h]
  char v37; // [rsp+8Bh] [rbp-75h]
  char v38; // [rsp+8Ch] [rbp-74h]
  char v39; // [rsp+8Dh] [rbp-73h]
  char v40; // [rsp+8Eh] [rbp-72h]
  char v41; // [rsp+8Fh] [rbp-71h]
  char v42; // [rsp+9Ch] [rbp-64h]
  char v43; // [rsp+9Dh] [rbp-63h]
  char v44; // [rsp+9Eh] [rbp-62h]
  char v45; // [rsp+9Fh] [rbp-61h]

  v28 = a5;
  v26 = 0;
  v27 = a6;
  LOBYTE(v26) = 81;
  *(_WORD *)((char *)&v26 + 7) = 1;
  TrackInfo = UdfSendSptCdb(a2, (unsigned __int8 *)&v26, v29, 0x100u, 1, 0x2Du, v20, v21, v22, v23);
  if ( TrackInfo < 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          115,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return (unsigned int)TrackInfo;
  }
  v10 = v32;
  v24 = v31;
  v11 = v30 & 3;
  if ( (v30 & 3) != 1 || (v12 = (v30 >> 2) & 3, v12 == 3) )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 116, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    return v11 != 0 ? -1073741808 : -1073741489;
  }
  if ( v12 == 2
    && *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 117, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  TrackInfo = UdfReadTrackInfo(a2, v10, v29, 256);
  if ( TrackInfo < 0 )
  {
    v13 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
    {
      return (unsigned int)TrackInfo;
    }
    v14 = v10;
    v15 = 118;
    goto LABEL_16;
  }
  if ( (v32 & 0x40) != 0 )
  {
    if ( v24 == v10 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
      {
        WPP_SF_(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          119,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
      }
      *v27 = 1;
      return 3221225488LL;
    }
    TrackInfo = UdfReadTrackInfo(a2, --v10, v29, 256);
    if ( TrackInfo < 0 )
    {
      v13 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
      {
        return (unsigned int)TrackInfo;
      }
      v14 = v10;
      v15 = 120;
LABEL_16:
      v16 = *(_QWORD *)(v13 + 24);
LABEL_17:
      WPP_SF_dd(v16, v15, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids, v14, TrackInfo);
      return (unsigned int)TrackInfo;
    }
  }
  if ( (v31 & 0x20) != 0 || (v33 & 3) == 0 )
    return 3221225488LL;
  if ( (v33 & 2) != 0 )
  {
    v17 = (_BYTE *)v28;
    *(_BYTE *)a4 = v45;
    *(_BYTE *)(a4 + 1) = v44;
    *(_BYTE *)(a4 + 2) = v43;
    *(_BYTE *)(a4 + 3) = v42;
    *v17 = v41;
    v17[1] = v40;
    v17[2] = v39;
    v17[3] = v38;
    --*(_DWORD *)v17;
    v18 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
    {
      goto LABEL_39;
    }
    v19 = 121;
  }
  else
  {
    *(_BYTE *)a4 = v41;
    *(_BYTE *)(a4 + 1) = v40;
    *(_BYTE *)(a4 + 2) = v39;
    *(_BYTE *)(a4 + 3) = v38;
    --*(_DWORD *)a4;
    v18 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
    {
      goto LABEL_39;
    }
    v19 = 122;
  }
  WPP_SF_d(*(_QWORD *)(v18 + 24), v19, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
LABEL_39:
  if ( v10 != v24 )
  {
    TrackInfo = UdfReadTrackInfo(a2, v24, v29, 256);
    if ( TrackInfo < 0 )
    {
      if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
      {
        return (unsigned int)TrackInfo;
      }
      v16 = *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL);
      v15 = 123;
      v14 = v24;
      goto LABEL_17;
    }
  }
  *a3 = v37;
  a3[1] = v36;
  a3[2] = v35;
  a3[3] = v34;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0xBu) )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      124,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      *(unsigned int *)a3,
      *(_DWORD *)a4);
  }
  return 0;
}

```

## disassembly

```asm
0x14004bdc0  mov     [rsp-8+arg_0], rbx
0x14004bdc5  push    rbp
0x14004bdc6  push    rsi
0x14004bdc7  push    rdi
0x14004bdc8  push    r12
0x14004bdca  push    r13
0x14004bdcc  push    r14
0x14004bdce  push    r15
0x14004bdd0  lea     rbp, [rsp-90h]
0x14004bdd8  sub     rsp, 190h
0x14004bddf  mov     rax, cs:__security_cookie
0x14004bde6  xor     rax, rsp
0x14004bde9  mov     [rbp+0C0h+var_40], rax
0x14004bdf0  mov     rax, [rbp+0C0h+arg_20]
0x14004bdf7  mov     r10, rdx
0x14004bdfa  mov     [rsp+1C0h+var_148], rax
0x14004bdff  xorps   xmm0, xmm0
0x14004be02  mov     rax, [rbp+0C0h+arg_28]
0x14004be09  mov     r15, r9
0x14004be0c  movups  [rsp+1C0h+var_160], xmm0
0x14004be11  mov     r12, r8
0x14004be14  mov     [rsp+1C0h+var_168], rdx
0x14004be19  mov     [rsp+1C0h+var_198], 2Dh ; '-'
0x14004be21  lea     r8, [rbp+0C0h+var_140]
0x14004be25  mov     r9d, 100h
0x14004be2b  mov     [rsp+1C0h+var_150], rax
0x14004be30  lea     rdx, [rsp+1C0h+var_160]
0x14004be35  mov     byte ptr [rsp+1C0h+var_160], 51h ; 'Q'
0x14004be3a  mov     rcx, r10
0x14004be3d  mov     word ptr [rsp+1C0h+var_160+7], 1
0x14004be44  mov     byte ptr [rsp+1C0h+var_1A0], 1
0x14004be49  call    UdfSendSptCdb
0x14004be4e  mov     r14d, eax
0x14004be51  test    eax, eax
0x14004be53  jns     short loc_14004BE90
0x14004be55  mov     r10, cs:WPP_GLOBAL_Control
0x14004be5c  lea     rdi, WPP_GLOBAL_Control
0x14004be63  cmp     r10, rdi
0x14004be66  jz      short loc_14004BE88
0x14004be68  bt      dword ptr [r10+2Ch], 0Bh
0x14004be6e  jnb     short loc_14004BE88
0x14004be70  mov     rcx, [r10+18h]
0x14004be74  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004be7b  mov     edx, 73h ; 's'
0x14004be80  mov     r9d, eax
0x14004be83  call    WPP_SF_d
0x14004be88  mov     eax, r14d
0x14004be8b  jmp     loc_14004C182
0x14004be90  mov     al, [rbp+0C0h+var_13B]
0x14004be93  mov     cl, 3
0x14004be95  mov     r13, [rbp+0C0h+var_13A]
0x14004be99  mov     [rsp+1C0h+var_170], al
0x14004be9d  mov     al, [rbp+0C0h+var_13E]
0x14004bea0  mov     r14b, al
0x14004bea3  and     r14b, cl
0x14004bea6  cmp     r14b, 1
0x14004beaa  jnz     loc_14004C144
0x14004beb0  shr     al, 2
0x14004beb3  and     al, cl
0x14004beb5  cmp     al, cl
0x14004beb7  jz      loc_14004C144
0x14004bebd  lea     rsi, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004bec4  lea     rdi, WPP_GLOBAL_Control
0x14004becb  cmp     al, 2
0x14004becd  jnz     short loc_14004BEF3
0x14004becf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bed6  cmp     rcx, rdi
0x14004bed9  jz      short loc_14004BEF3
0x14004bedb  bt      dword ptr [rcx+2Ch], 0Bh
0x14004bee0  jnb     short loc_14004BEF3
0x14004bee2  mov     rcx, [rcx+18h]
0x14004bee6  mov     edx, 75h ; 'u'
0x14004beeb  mov     r8, rsi
0x14004beee  call    WPP_SF_
0x14004bef3  mov     rcx, [rsp+1C0h+var_168]
0x14004bef8  lea     r8, [rbp+0C0h+var_140]
0x14004befc  movzx   eax, r13b
0x14004bf00  mov     r9d, 100h
0x14004bf06  mov     edx, eax
0x14004bf08  mov     [rsp+1C0h+var_16C], eax
0x14004bf0c  call    UdfReadTrackInfo
0x14004bf11  mov     r14d, eax
0x14004bf14  test    eax, eax
0x14004bf16  jns     short loc_14004BF54
0x14004bf18  mov     r10, cs:WPP_GLOBAL_Control
0x14004bf1f  cmp     r10, rdi
0x14004bf22  jz      loc_14004BE88
0x14004bf28  bt      dword ptr [r10+2Ch], 0Bh
0x14004bf2e  jnb     loc_14004BE88
0x14004bf34  mov     r9d, [rsp+1C0h+var_16C]
0x14004bf39  mov     edx, 76h ; 'v'
0x14004bf3e  mov     rcx, [r10+18h]
0x14004bf42  mov     r8, rsi
0x14004bf45  mov     [rsp+1C0h+var_1A0], r14d
0x14004bf4a  call    WPP_SF_dd
0x14004bf4f  jmp     loc_14004BE88
0x14004bf54  test    byte ptr [rbp+0C0h+var_13A], 40h
0x14004bf58  jz      loc_14004BFF0
0x14004bf5e  cmp     [rsp+1C0h+var_170], r13b
0x14004bf63  jnz     short loc_14004BF9B
0x14004bf65  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf6c  cmp     rcx, rdi
0x14004bf6f  jz      short loc_14004BF89
0x14004bf71  bt      dword ptr [rcx+2Ch], 0Bh
0x14004bf76  jnb     short loc_14004BF89
0x14004bf78  mov     rcx, [rcx+18h]
0x14004bf7c  mov     edx, 77h ; 'w'
0x14004bf81  mov     r8, rsi
0x14004bf84  call    WPP_SF_
0x14004bf89  mov     rax, [rsp+1C0h+var_150]
0x14004bf8e  mov     byte ptr [rax], 1
0x14004bf91  mov     eax, 0C0000010h
0x14004bf96  jmp     loc_14004C182
0x14004bf9b  mov     rcx, [rsp+1C0h+var_168]
0x14004bfa0  lea     r8, [rbp+0C0h+var_140]
0x14004bfa4  add     r13b, 0FFh
0x14004bfa8  mov     r9d, 100h
0x14004bfae  movzx   eax, r13b
0x14004bfb2  mov     edx, eax
0x14004bfb4  mov     [rsp+1C0h+var_16C], eax
0x14004bfb8  call    UdfReadTrackInfo
0x14004bfbd  mov     r14d, eax
0x14004bfc0  test    eax, eax
0x14004bfc2  jns     short loc_14004BFF0
0x14004bfc4  mov     r10, cs:WPP_GLOBAL_Control
0x14004bfcb  cmp     r10, rdi
0x14004bfce  jz      loc_14004BE88
0x14004bfd4  bt      dword ptr [r10+2Ch], 0Bh
0x14004bfda  jnb     loc_14004BE88
0x14004bfe0  movzx   r9d, byte ptr [rsp+1C0h+var_16C]
0x14004bfe6  mov     edx, 78h ; 'x'
0x14004bfeb  jmp     loc_14004BF3E
0x14004bff0  test    [rbp+0C0h+var_13B], 20h
0x14004bff4  jnz     short loc_14004BF91
0x14004bff6  mov     al, byte ptr [rbp+0C0h+var_13A+1]
0x14004bff9  test    al, 3
0x14004bffb  jz      short loc_14004BF91
0x14004bffd  test    al, 2
0x14004bfff  jz      short loc_14004C057
0x14004c001  mov     rcx, [rsp+1C0h+var_148]
0x14004c006  mov     al, [rbp+0C0h+var_121]
0x14004c009  mov     [r15], al
0x14004c00c  mov     al, [rbp+0C0h+var_122]
0x14004c00f  mov     [r15+1], al
0x14004c013  mov     al, [rbp+0C0h+var_123]
0x14004c016  mov     [r15+2], al
0x14004c01a  mov     al, [rbp+0C0h+var_124]
0x14004c01d  mov     [r15+3], al
0x14004c021  mov     al, [rbp+0C0h+var_131]
0x14004c024  mov     [rcx], al
0x14004c026  mov     al, [rbp+0C0h+var_132]
0x14004c029  mov     [rcx+1], al
0x14004c02c  mov     al, byte ptr [rbp+0C0h+var_13A+7]
0x14004c02f  mov     [rcx+2], al
0x14004c032  mov     al, byte ptr [rbp+0C0h+var_13A+6]
0x14004c035  mov     [rcx+3], al
0x14004c038  dec     dword ptr [rcx]
0x14004c03a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c041  cmp     rcx, rdi
0x14004c044  jz      short loc_14004C09C
0x14004c046  bt      dword ptr [rcx+2Ch], 0Bh
0x14004c04b  jnb     short loc_14004C09C
0x14004c04d  mov     r9d, [r15]
0x14004c050  mov     edx, 79h ; 'y'
0x14004c055  jmp     short loc_14004C090
0x14004c057  mov     al, [rbp+0C0h+var_131]
0x14004c05a  mov     [r15], al
0x14004c05d  mov     al, [rbp+0C0h+var_132]
0x14004c060  mov     [r15+1], al
0x14004c064  mov     al, byte ptr [rbp+0C0h+var_13A+7]
0x14004c067  mov     [r15+2], al
0x14004c06b  mov     al, byte ptr [rbp+0C0h+var_13A+6]
0x14004c06e  mov     [r15+3], al
0x14004c072  dec     dword ptr [r15]
0x14004c075  mov     r9d, [r15]
0x14004c078  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c07f  cmp     rcx, rdi
0x14004c082  jz      short loc_14004C09C
0x14004c084  bt      dword ptr [rcx+2Ch], 0Bh
0x14004c089  jnb     short loc_14004C09C
0x14004c08b  mov     edx, 7Ah ; 'z'
0x14004c090  mov     rcx, [rcx+18h]
0x14004c094  mov     r8, rsi
0x14004c097  call    WPP_SF_d
0x14004c09c  movzx   eax, [rsp+1C0h+var_170]
0x14004c0a1  cmp     r13b, al
0x14004c0a4  jz      short loc_14004C0F2
0x14004c0a6  mov     rcx, [rsp+1C0h+var_168]
0x14004c0ab  lea     r8, [rbp+0C0h+var_140]
0x14004c0af  mov     r9d, 100h
0x14004c0b5  mov     edx, eax
0x14004c0b7  mov     r13d, eax
0x14004c0ba  call    UdfReadTrackInfo
0x14004c0bf  mov     r14d, eax
0x14004c0c2  test    eax, eax
0x14004c0c4  jns     short loc_14004C0F2
0x14004c0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c0cd  cmp     rcx, rdi
0x14004c0d0  jz      loc_14004BE88
0x14004c0d6  bt      dword ptr [rcx+2Ch], 0Bh
0x14004c0db  jnb     loc_14004BE88
0x14004c0e1  mov     rcx, [rcx+18h]
0x14004c0e5  mov     edx, 7Bh ; '{'
0x14004c0ea  mov     r9d, r13d
0x14004c0ed  jmp     loc_14004BF42
0x14004c0f2  mov     al, byte ptr [rbp+0C0h+var_13A+5]
0x14004c0f5  mov     [r12], al
0x14004c0f9  mov     al, byte ptr [rbp+0C0h+var_13A+4]
0x14004c0fc  mov     [r12+1], al
0x14004c101  mov     al, byte ptr [rbp+0C0h+var_13A+3]
0x14004c104  mov     [r12+2], al
0x14004c109  mov     al, byte ptr [rbp+0C0h+var_13A+2]
0x14004c10c  mov     [r12+3], al
0x14004c111  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c118  cmp     rcx, rdi
0x14004c11b  jz      short loc_14004C140
0x14004c11d  bt      dword ptr [rcx+2Ch], 0Bh
0x14004c122  jnb     short loc_14004C140
0x14004c124  mov     eax, [r15]
0x14004c127  mov     edx, 7Ch ; '|'
0x14004c12c  mov     r9d, [r12]
0x14004c130  mov     r8, rsi
0x14004c133  mov     rcx, [rcx+18h]
0x14004c137  mov     [rsp+1C0h+var_1A0], eax
0x14004c13b  call    WPP_SF_dd
0x14004c140  xor     eax, eax
0x14004c142  jmp     short loc_14004C182
0x14004c144  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c14b  lea     rdi, WPP_GLOBAL_Control
0x14004c152  cmp     rcx, rdi
0x14004c155  jz      short loc_14004C173
0x14004c157  bt      dword ptr [rcx+2Ch], 0Bh
0x14004c15c  jnb     short loc_14004C173
0x14004c15e  mov     rcx, [rcx+18h]
0x14004c162  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004c169  mov     edx, 74h ; 't'
0x14004c16e  call    WPP_SF_
0x14004c173  neg     r14b
0x14004c176  sbb     eax, eax
0x14004c178  and     eax, 0FFFFFEC1h
0x14004c17d  add     eax, 0C000014Fh
0x14004c182  mov     rcx, [rbp+0C0h+var_40]
0x14004c189  xor     rcx, rsp; StackCookie
0x14004c18c  call    __security_check_cookie
0x14004c191  mov     rbx, [rsp+1C0h+arg_0]
0x14004c199  add     rsp, 190h
0x14004c1a0  pop     r15
0x14004c1a2  pop     r14
0x14004c1a4  pop     r13
0x14004c1a6  pop     r12
0x14004c1a8  pop     rdi
0x14004c1a9  pop     rsi
0x14004c1aa  pop     rbp
0x14004c1ab  retn
```
