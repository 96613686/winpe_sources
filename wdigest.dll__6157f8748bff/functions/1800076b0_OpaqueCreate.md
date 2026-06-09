# OpaqueCreate

- ea: `0x1800076b0`
- end: `0x180007a93`
- name: `OpaqueCreate`
- size: `995`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ff20`
- `0x1800206d0`

## callees

- `0x1800061a0`
- `0x1800076b0`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007765`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007745`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x180007745`

## pseudocode

```c
__int64 __fastcall OpaqueCreate(__int64 a1)
{
  PVOID *v2; // rcx
  __int64 v3; // rsi
  __int64 Memory; // rax
  unsigned int v5; // ebp
  DWORD LastError; // eax
  __int64 v8; // r9
  unsigned int i; // r10d
  char v10; // cl
  BYTE *v11; // r8
  unsigned int v12; // eax
  char v13; // cl
  char v14; // al
  __int64 v15; // rsi
  unsigned int v16; // ecx
  BYTE *v17; // r8
  __int64 v18; // rsi
  char v19; // al
  unsigned int v20; // ecx
  __int64 v21; // rsi
  char v22; // al
  unsigned int v23; // ecx
  BYTE *v24; // r8
  __int64 v25; // rsi
  char v26; // al
  unsigned int v27; // ecx
  __int64 v28; // rsi
  char v29; // al
  unsigned int v30; // ecx
  BYTE *v31; // r8
  __int64 v32; // rsi
  char v33; // al
  unsigned int v34; // ecx
  __int64 v35; // rsi
  char v36; // al
  unsigned int v37; // ecx
  BYTE *v38; // r8
  __int64 v39; // rsi
  unsigned int v40; // ecx
  char v41; // al
  __int64 v42; // rsi
  char v43; // al
  unsigned int v44; // ecx
  BYTE *v45; // r8
  __int64 v46; // rsi
  char v47; // al
  unsigned int v48; // ecx
  __int64 v49; // rsi
  char v50; // al
  unsigned int v51; // ecx
  BYTE *v52; // r8
  __int64 v53; // rsi
  char v54; // al
  unsigned int v55; // ecx
  __int64 v56; // rsi
  char v57; // al
  unsigned int v58; // ecx
  BYTE *v59; // r8
  __int64 v60; // rsi
  char v61; // al
  unsigned int v62; // ecx
  __int64 v63; // rsi
  char v64; // al
  unsigned int v65; // ecx
  BYTE pbBuffer[16]; // [rsp+20h] [rbp-38h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v5 = 0;
    if ( *(_WORD *)(a1 + 2) < 0x21u )
    {
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
        WPP_SF_(v2[2], 60, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
      v5 = -1073741789;
      goto LABEL_55;
    }
  }
  else
  {
    *(_WORD *)a1 = 0;
    Memory = DigestAllocateMemory(0x21u);
    *(_QWORD *)(a1 + 8) = Memory;
    if ( !Memory )
    {
      *(_WORD *)(a1 + 2) = 0;
      v5 = -2146893056;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, 2148074240LL);
      goto LABEL_55;
    }
    *(_WORD *)(a1 + 2) = 33;
    v5 = 0;
  }
  if ( !CryptGenRandom(g_hCryptProv, 0x10u, pbBuffer) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, LastError);
    }
    return 3221225701LL;
  }
  v8 = *(_QWORD *)(a1 + 8);
  for ( i = 0; i < 0x10; i += 8 )
  {
    v10 = 87;
    v11 = &pbBuffer[i];
    v12 = *v11 >> 4;
    if ( v12 < 0xA )
      v10 = 48;
    v13 = v12 + v10;
    v14 = 87;
    *(_BYTE *)(v3 + v8) = v13;
    v15 = (unsigned int)(v3 + 1);
    v16 = *v11 & 0xF;
    if ( v16 < 0xA )
      v14 = 48;
    *(_BYTE *)(v15 + v8) = v16 + v14;
    v17 = &pbBuffer[i + 1];
    v18 = (unsigned int)(v15 + 1);
    v19 = 87;
    v20 = *v17 >> 4;
    if ( v20 < 0xA )
      v19 = 48;
    *(_BYTE *)(v18 + v8) = v20 + v19;
    v21 = (unsigned int)(v18 + 1);
    v22 = 87;
    v23 = *v17 & 0xF;
    if ( v23 < 0xA )
      v22 = 48;
    *(_BYTE *)(v21 + v8) = v23 + v22;
    v24 = &pbBuffer[i + 2];
    v25 = (unsigned int)(v21 + 1);
    v26 = 87;
    v27 = *v24 >> 4;
    if ( v27 < 0xA )
      v26 = 48;
    *(_BYTE *)(v25 + v8) = v27 + v26;
    v28 = (unsigned int)(v25 + 1);
    v29 = 87;
    v30 = *v24 & 0xF;
    if ( v30 < 0xA )
      v29 = 48;
    *(_BYTE *)(v28 + v8) = v30 + v29;
    v31 = &pbBuffer[i + 3];
    v32 = (unsigned int)(v28 + 1);
    v33 = 87;
    v34 = *v31 >> 4;
    if ( v34 < 0xA )
      v33 = 48;
    *(_BYTE *)(v32 + v8) = v34 + v33;
    v35 = (unsigned int)(v32 + 1);
    v36 = 87;
    v37 = *v31 & 0xF;
    if ( v37 < 0xA )
      v36 = 48;
    v38 = &pbBuffer[i + 4];
    *(_BYTE *)(v35 + v8) = v37 + v36;
    v39 = (unsigned int)(v35 + 1);
    v40 = *v38 >> 4;
    v41 = 87;
    if ( v40 < 0xA )
      v41 = 48;
    *(_BYTE *)(v39 + v8) = v40 + v41;
    v42 = (unsigned int)(v39 + 1);
    v43 = 87;
    v44 = *v38 & 0xF;
    if ( v44 < 0xA )
      v43 = 48;
    *(_BYTE *)(v42 + v8) = v44 + v43;
    v45 = &pbBuffer[i + 5];
    v46 = (unsigned int)(v42 + 1);
    v47 = 87;
    v48 = *v45 >> 4;
    if ( v48 < 0xA )
      v47 = 48;
    *(_BYTE *)(v46 + v8) = v48 + v47;
    v49 = (unsigned int)(v46 + 1);
    v50 = 87;
    v51 = *v45 & 0xF;
    if ( v51 < 0xA )
      v50 = 48;
    *(_BYTE *)(v49 + v8) = v51 + v50;
    v52 = &pbBuffer[i + 6];
    v53 = (unsigned int)(v49 + 1);
    v54 = 87;
    v55 = *v52 >> 4;
    if ( v55 < 0xA )
      v54 = 48;
    *(_BYTE *)(v53 + v8) = v55 + v54;
    v56 = (unsigned int)(v53 + 1);
    v57 = 87;
    v58 = *v52 & 0xF;
    if ( v58 < 0xA )
      v57 = 48;
    *(_BYTE *)(v56 + v8) = v58 + v57;
    v59 = &pbBuffer[i + 7];
    v60 = (unsigned int)(v56 + 1);
    v61 = 87;
    v62 = *v59 >> 4;
    if ( v62 < 0xA )
      v61 = 48;
    *(_BYTE *)(v60 + v8) = v62 + v61;
    v63 = (unsigned int)(v60 + 1);
    v64 = 87;
    v65 = *v59 & 0xF;
    if ( v65 < 0xA )
      v64 = 48;
    *(_BYTE *)(v63 + v8) = v65 + v64;
    v3 = (unsigned int)(v63 + 1);
  }
  *(_BYTE *)(v3 + v8) = 0;
  LOWORD(v3) = 32;
LABEL_55:
  *(_WORD *)a1 = v3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  push    rdi
0x1800076b3  push    r14
0x1800076b5  sub     rsp, 40h
0x1800076b9  mov     rax, cs:__security_cookie
0x1800076c0  xor     rax, rsp
0x1800076c3  mov     [rsp+58h+var_28], rax
0x1800076c8  mov     rbx, rcx
0x1800076cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076d2  lea     r14, WPP_GLOBAL_Control
0x1800076d9  cmp     rcx, r14
0x1800076dc  jz      short loc_180007700
0x1800076de  test    byte ptr [rcx+1Ch], 80h
0x1800076e2  jz      short loc_180007700
0x1800076e4  mov     rcx, [rcx+10h]
0x1800076e8  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x1800076ef  mov     edx, 3Ah ; ':'
0x1800076f4  call    WPP_SF_
0x1800076f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007700  mov     [rsp+58h+arg_8], rbp
0x180007705  mov     [rsp+58h+arg_10], rsi
0x18000770a  xor     esi, esi
0x18000770c  cmp     [rbx+8], rsi
0x180007710  jnz     loc_1800077D7
0x180007716  mov     ebp, 21h ; '!'
0x18000771b  mov     [rbx], si
0x18000771e  mov     ecx, ebp; Size
0x180007720  call    DigestAllocateMemory
0x180007725  mov     [rbx+8], rax
0x180007729  test    rax, rax
0x18000772c  jz      short loc_180007794
0x18000772e  mov     [rbx+2], bp
0x180007732  mov     ebp, esi
0x180007734  mov     rcx, cs:g_hCryptProv; hProv
0x18000773b  lea     r8, [rsp+58h+pbBuffer]; pbBuffer
0x180007740  mov     edx, 10h; dwLen
0x180007745  call    cs:__imp_CryptGenRandom
0x18000774b  test    eax, eax
0x18000774d  jnz     loc_18000780E
0x180007753  mov     rax, cs:WPP_GLOBAL_Control
0x18000775a  cmp     rax, r14
0x18000775d  jz      short loc_18000778A
0x18000775f  test    byte ptr [rax+1Ch], 4
0x180007763  jz      short loc_18000778A
0x180007765  call    cs:__imp_GetLastError
0x18000776b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007772  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x180007779  mov     edx, 3Dh ; '='
0x18000777e  mov     r9d, eax
0x180007781  mov     rcx, [rcx+10h]
0x180007785  call    WPP_SF_d
0x18000778a  mov     eax, 0C00000E5h
0x18000778f  jmp     loc_180007A73
0x180007794  mov     [rbx+2], si
0x180007798  mov     ebp, 80090300h
0x18000779d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a4  cmp     rcx, r14
0x1800077a7  jz      loc_180007A47
0x1800077ad  test    byte ptr [rcx+1Ch], 1
0x1800077b1  jz      loc_180007A47
0x1800077b7  mov     rcx, [rcx+10h]
0x1800077bb  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x1800077c2  mov     edx, 3Bh ; ';'
0x1800077c7  mov     r9d, 80090300h
0x1800077cd  call    WPP_SF_d
0x1800077d2  jmp     loc_180007A47
0x1800077d7  cmp     word ptr [rbx+2], 21h ; '!'
0x1800077dc  mov     ebp, esi
0x1800077de  jnb     loc_180007734
0x1800077e4  cmp     rcx, r14
0x1800077e7  jz      short loc_180007804
0x1800077e9  test    byte ptr [rcx+1Ch], 1
0x1800077ed  jz      short loc_180007804
0x1800077ef  mov     rcx, [rcx+10h]
0x1800077f3  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x1800077fa  mov     edx, 3Ch ; '<'
0x1800077ff  call    WPP_SF_
0x180007804  mov     ebp, 0C0000023h
0x180007809  jmp     loc_180007A47
0x18000780e  mov     r9, [rbx+8]
0x180007812  mov     r10d, esi
0x180007815  mov     r11d, 30h ; '0'
0x18000781b  nop     dword ptr [rax+rax+00h]
0x180007820  mov     ecx, 57h ; 'W'
0x180007825  mov     eax, r10d
0x180007828  lea     r8, [rsp+58h+pbBuffer]
0x18000782d  add     r8, rax
0x180007830  movzx   eax, byte ptr [r8]
0x180007834  shr     eax, 4
0x180007837  cmp     eax, 0Ah
0x18000783a  cmovb   ecx, r11d
0x18000783e  add     cl, al
0x180007840  mov     eax, 57h ; 'W'
0x180007845  mov     [rsi+r9], cl
0x180007849  inc     esi
0x18000784b  movzx   ecx, byte ptr [r8]
0x18000784f  lea     r8, [rsp+58h+pbBuffer]
0x180007854  and     ecx, 0Fh
0x180007857  cmp     ecx, 0Ah
0x18000785a  cmovb   eax, r11d
0x18000785e  add     al, cl
0x180007860  lea     ecx, [r10+1]
0x180007864  mov     [rsi+r9], al
0x180007868  add     r8, rcx
0x18000786b  inc     esi
0x18000786d  mov     eax, 57h ; 'W'
0x180007872  movzx   ecx, byte ptr [r8]
0x180007876  shr     ecx, 4
0x180007879  cmp     ecx, 0Ah
0x18000787c  cmovb   eax, r11d
0x180007880  add     al, cl
0x180007882  mov     [rsi+r9], al
0x180007886  inc     esi
0x180007888  movzx   ecx, byte ptr [r8]
0x18000788c  mov     eax, 57h ; 'W'
0x180007891  and     ecx, 0Fh
0x180007894  lea     r8, [rsp+58h+pbBuffer]
0x180007899  cmp     ecx, 0Ah
0x18000789c  cmovb   eax, r11d
0x1800078a0  add     al, cl
0x1800078a2  lea     ecx, [r10+2]
0x1800078a6  mov     [rsi+r9], al
0x1800078aa  add     r8, rcx
0x1800078ad  inc     esi
0x1800078af  mov     eax, 57h ; 'W'
0x1800078b4  movzx   ecx, byte ptr [r8]
0x1800078b8  shr     ecx, 4
0x1800078bb  cmp     ecx, 0Ah
0x1800078be  cmovb   eax, r11d
0x1800078c2  add     al, cl
0x1800078c4  mov     [rsi+r9], al
0x1800078c8  inc     esi
0x1800078ca  movzx   ecx, byte ptr [r8]
0x1800078ce  mov     eax, 57h ; 'W'
0x1800078d3  and     ecx, 0Fh
0x1800078d6  lea     r8, [rsp+58h+pbBuffer]
0x1800078db  cmp     ecx, 0Ah
0x1800078de  cmovb   eax, r11d
0x1800078e2  add     al, cl
0x1800078e4  lea     ecx, [r10+3]
0x1800078e8  mov     [rsi+r9], al
0x1800078ec  add     r8, rcx
0x1800078ef  inc     esi
0x1800078f1  mov     eax, 57h ; 'W'
0x1800078f6  movzx   ecx, byte ptr [r8]
0x1800078fa  shr     ecx, 4
0x1800078fd  cmp     ecx, 0Ah
0x180007900  cmovb   eax, r11d
0x180007904  add     al, cl
0x180007906  mov     [rsi+r9], al
0x18000790a  inc     esi
0x18000790c  movzx   ecx, byte ptr [r8]
0x180007910  mov     eax, 57h ; 'W'
0x180007915  and     ecx, 0Fh
0x180007918  lea     r8, [rsp+58h+pbBuffer]
0x18000791d  cmp     ecx, 0Ah
0x180007920  cmovb   eax, r11d
0x180007924  add     al, cl
0x180007926  lea     ecx, [r10+4]
0x18000792a  add     r8, rcx
0x18000792d  mov     [rsi+r9], al
0x180007931  inc     esi
0x180007933  movzx   ecx, byte ptr [r8]
0x180007937  shr     ecx, 4
0x18000793a  cmp     ecx, 0Ah
0x18000793d  mov     eax, 57h ; 'W'
0x180007942  cmovb   eax, r11d
0x180007946  add     al, cl
0x180007948  mov     [rsi+r9], al
0x18000794c  inc     esi
0x18000794e  movzx   ecx, byte ptr [r8]
0x180007952  mov     eax, 57h ; 'W'
0x180007957  and     ecx, 0Fh
0x18000795a  lea     r8, [rsp+58h+pbBuffer]
0x18000795f  cmp     ecx, 0Ah
0x180007962  cmovb   eax, r11d
0x180007966  add     al, cl
0x180007968  lea     ecx, [r10+5]
0x18000796c  mov     [rsi+r9], al
0x180007970  add     r8, rcx
0x180007973  inc     esi
0x180007975  mov     eax, 57h ; 'W'
0x18000797a  movzx   ecx, byte ptr [r8]
0x18000797e  shr     ecx, 4
0x180007981  cmp     ecx, 0Ah
0x180007984  cmovb   eax, r11d
0x180007988  add     al, cl
0x18000798a  mov     [rsi+r9], al
0x18000798e  inc     esi
0x180007990  movzx   ecx, byte ptr [r8]
0x180007994  mov     eax, 57h ; 'W'
0x180007999  and     ecx, 0Fh
0x18000799c  lea     r8, [rsp+58h+pbBuffer]
0x1800079a1  cmp     ecx, 0Ah
0x1800079a4  cmovb   eax, r11d
0x1800079a8  add     al, cl
0x1800079aa  lea     ecx, [r10+6]
0x1800079ae  mov     [rsi+r9], al
0x1800079b2  add     r8, rcx
0x1800079b5  inc     esi
0x1800079b7  mov     eax, 57h ; 'W'
0x1800079bc  movzx   ecx, byte ptr [r8]
0x1800079c0  shr     ecx, 4
0x1800079c3  cmp     ecx, 0Ah
0x1800079c6  cmovb   eax, r11d
0x1800079ca  add     al, cl
0x1800079cc  mov     [rsi+r9], al
0x1800079d0  inc     esi
0x1800079d2  movzx   ecx, byte ptr [r8]
0x1800079d6  mov     eax, 57h ; 'W'
0x1800079db  and     ecx, 0Fh
0x1800079de  lea     r8, [rsp+58h+pbBuffer]
0x1800079e3  cmp     ecx, 0Ah
0x1800079e6  cmovb   eax, r11d
0x1800079ea  add     al, cl
0x1800079ec  lea     ecx, [r10+7]
0x1800079f0  mov     [rsi+r9], al
0x1800079f4  add     r8, rcx
0x1800079f7  inc     esi
0x1800079f9  mov     eax, 57h ; 'W'
0x1800079fe  movzx   ecx, byte ptr [r8]
0x180007a02  shr     ecx, 4
0x180007a05  cmp     ecx, 0Ah
0x180007a08  cmovb   eax, r11d
0x180007a0c  add     al, cl
0x180007a0e  mov     [rsi+r9], al
0x180007a12  inc     esi
0x180007a14  movzx   ecx, byte ptr [r8]
0x180007a18  mov     eax, 57h ; 'W'
0x180007a1d  and     ecx, 0Fh
0x180007a20  cmp     ecx, 0Ah
0x180007a23  cmovb   eax, r11d
0x180007a27  add     r10d, 8
0x180007a2b  add     al, cl
0x180007a2d  mov     [rsi+r9], al
0x180007a31  inc     esi
0x180007a33  cmp     r10d, 10h
0x180007a37  jb      loc_180007820
0x180007a3d  mov     byte ptr [rsi+r9], 0
0x180007a42  mov     esi, 20h ; ' '
0x180007a47  mov     [rbx], si
0x180007a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a51  cmp     rcx, r14
0x180007a54  jz      short loc_180007A71
0x180007a56  test    byte ptr [rcx+1Ch], 80h
0x180007a5a  jz      short loc_180007A71
0x180007a5c  mov     rcx, [rcx+10h]
0x180007a60  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x180007a67  mov     edx, 3Eh ; '>'
0x180007a6c  call    WPP_SF_
0x180007a71  mov     eax, ebp
0x180007a73  mov     rsi, [rsp+58h+arg_10]
0x180007a78  mov     rbp, [rsp+58h+arg_8]
0x180007a7d  mov     rcx, [rsp+58h+var_28]
0x180007a82  xor     rcx, rsp; StackCookie
0x180007a85  call    __security_check_cookie
0x180007a8a  add     rsp, 40h
0x180007a8e  pop     r14
0x180007a90  pop     rdi
0x180007a91  pop     rbx
0x180007a92  retn
```
