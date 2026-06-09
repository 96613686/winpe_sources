# HUBDESC_InternalValidateIADescriptor

- ea: `0x140038450`
- end: `0x14003888d`
- name: `HUBDESC_InternalValidateIADescriptor`
- size: `1085`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x140038450`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateIADescriptor(char *a1, __int64 a2, unsigned int *a3, int *a4, __int64 a5)
{
  int *v5; // rdi
  __int64 v9; // rax
  int v10; // r15d
  int v11; // r12d
  int v12; // edx
  int v13; // r13d
  unsigned int v14; // r15d
  __int64 *v15; // r8
  int v16; // r8d
  __int64 v17; // rdx
  char v18; // bl
  __int64 v19; // r14
  int v21; // [rsp+90h] [rbp+8h] BYREF
  __int64 v22; // [rsp+98h] [rbp+10h]

  v21 = 0;
  v5 = a4;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v21;
  }
  v9 = *(_QWORD *)(a2 + 56);
  v10 = *(_DWORD *)(a2 + 72);
  v11 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v12 = 512;
  v13 = a5;
  v14 = v10 - v11;
  v22 = v9;
  LODWORD(v9) = (unsigned __int8)*a1;
  *a3 = v9;
  v15 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  if ( (unsigned __int8)v9 >= 8u )
  {
LABEL_14:
    if ( (unsigned __int8)*a1 > 8u )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_DDD(
          v13,
          v12,
          (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          128,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          v11,
          *a1,
          8);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 92, v15);
    }
    if ( *a3 <= v14 )
    {
      if ( 256 - (unsigned __int8)a1[2] < (unsigned __int8)a1[3] )
      {
        if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_DDD(
            v13,
            v12,
            (_DWORD)v15,
            130,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v11,
            a1[2],
            a1[3]);
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 97, v15);
      }
      v19 = v22;
      if ( (unsigned __int8)a1[3] > *(_BYTE *)(v22 + 4) )
      {
        if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_DDD(
            v13,
            v12,
            (_DWORD)v15,
            131,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v11,
            a1[3],
            *(_BYTE *)(v19 + 4));
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 95, v15);
      }
      if ( *(unsigned __int16 *)(a2 + 202) + (unsigned int)(unsigned __int8)a1[3] > *(unsigned __int8 *)(v19 + 4) )
      {
        if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_DDDD(
            v13,
            v12,
            5,
            132,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v11,
            a1[3],
            *(_WORD *)(a2 + 202),
            *(_BYTE *)(v19 + 4));
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 95, v15);
      }
      if ( a1[3] )
        goto LABEL_64;
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(v13, v12, 5, 133, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11);
      }
      v17 = 96;
    }
    else
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(v13, v12, 5, 129, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11);
      }
      v17 = 94;
    }
    (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), v17, v15);
LABEL_64:
    v18 = 1;
LABEL_65:
    if ( !*v5 )
      return v18;
    goto LABEL_66;
  }
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(
    *(_QWORD *)(a2 + 40),
    93,
    WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  v12 = 512;
  if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
    *v5 = 2;
  if ( v14 >= 8 )
  {
    *a3 = 8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DDDD(v13, v12, 5, 126, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11, *a1, 8, 8);
      v12 = 512;
    }
    v15 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
    goto LABEL_14;
  }
  v18 = 1;
  *v5 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_DDD(v13, v12, v16, 127, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11, *a1, 8);
    goto LABEL_65;
  }
LABEL_66:
  v18 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(v13, v12, 5, 134, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v18;
}

```

## disassembly

```asm
0x140038450  mov     rax, rsp
0x140038453  mov     [rax+18h], rbx
0x140038457  push    rbp
0x140038458  push    rsi
0x140038459  push    rdi
0x14003845a  push    r12
0x14003845c  push    r13
0x14003845e  push    r14
0x140038460  push    r15
0x140038462  sub     rsp, 50h
0x140038466  mov     dword ptr [rax+8], 0
0x14003846d  mov     rdi, r9
0x140038470  mov     r14, r8
0x140038473  mov     rbx, rdx
0x140038476  mov     rsi, rcx
0x140038479  test    r9, r9
0x14003847c  jnz     short loc_140038484
0x14003847e  lea     rdi, [rax+8]
0x140038482  jmp     short loc_140038491
0x140038484  cmp     byte ptr [rdx+30h], 0
0x140038488  jz      short loc_140038491
0x14003848a  mov     dword ptr [r9], 0
0x140038491  mov     rax, [rdx+38h]
0x140038495  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003849c  mov     r15d, [rdx+48h]
0x1400384a0  mov     r12d, esi
0x1400384a3  sub     r12d, [rdx+38h]
0x1400384a7  mov     edx, 200h
0x1400384ac  mov     r13, [rsp+88h+arg_20]
0x1400384b4  sub     r15d, r12d
0x1400384b7  mov     [rsp+88h+arg_8], rax
0x1400384bf  movzx   eax, byte ptr [rcx]
0x1400384c2  mov     ecx, 8
0x1400384c7  mov     [r8], eax
0x1400384ca  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400384d1  cmp     al, cl
0x1400384d3  jnb     loc_140038562
0x1400384d9  mov     rax, [rbx+18h]
0x1400384dd  lea     edx, [rcx+55h]
0x1400384e0  mov     rcx, [rbx+28h]
0x1400384e4  call    _guard_dispatch_icall
0x1400384e9  mov     edx, 200h
0x1400384ee  cmp     [rbx], dx
0x1400384f1  ja      short loc_1400384FF
0x1400384f3  cmp     byte ptr [rbx+0Ch], 0
0x1400384f7  jnz     short loc_1400384FF
0x1400384f9  cmp     byte ptr [rbx+0Dh], 0
0x1400384fd  jz      short loc_140038505
0x1400384ff  mov     dword ptr [rdi], 2
0x140038505  mov     ecx, 8
0x14003850a  cmp     r15d, ecx
0x14003850d  jb      loc_14003861A
0x140038513  mov     [r14], ecx
0x140038516  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003851d  jz      short loc_14003855B
0x14003851f  movzx   eax, byte ptr [rsi]
0x140038522  lea     r9d, [rcx+76h]
0x140038526  mov     [rsp+88h+var_48], ecx
0x14003852a  lea     r8d, [rcx-3]
0x14003852e  mov     [rsp+88h+var_50], ecx
0x140038532  mov     dl, 2
0x140038534  mov     [rsp+88h+var_58], eax
0x140038538  mov     rcx, r13
0x14003853b  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038542  mov     [rsp+88h+var_60], r12d
0x140038547  mov     [rsp+88h+var_68], rax
0x14003854c  call    WPP_RECORDER_SF_DDDD
0x140038551  mov     ecx, 8
0x140038556  mov     edx, 200h
0x14003855b  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038562  cmp     [rsi], cl
0x140038564  jbe     short loc_1400385BD
0x140038566  cmp     [rbx], dx
0x140038569  ja      short loc_140038577
0x14003856b  cmp     byte ptr [rbx+0Ch], 0
0x14003856f  jnz     short loc_140038577
0x140038571  cmp     byte ptr [rbx+0Dh], 0
0x140038575  jz      short loc_14003857D
0x140038577  mov     dword ptr [rdi], 2
0x14003857d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140038584  jz      short loc_1400385AB
0x140038586  movzx   eax, byte ptr [rsi]
0x140038589  mov     r9d, 80h
0x14003858f  mov     [rsp+88h+var_50], ecx
0x140038593  mov     dl, 2
0x140038595  mov     [rsp+88h+var_58], eax
0x140038599  mov     rcx, r13
0x14003859c  mov     [rsp+88h+var_60], r12d
0x1400385a1  mov     [rsp+88h+var_68], r8
0x1400385a6  call    WPP_RECORDER_SF_DDD
0x1400385ab  mov     rax, [rbx+18h]
0x1400385af  mov     edx, 5Ch ; '\'
0x1400385b4  mov     rcx, [rbx+28h]
0x1400385b8  call    _guard_dispatch_icall
0x1400385bd  cmp     [r14], r15d
0x1400385c0  jbe     loc_140038664
0x1400385c6  mov     eax, 200h
0x1400385cb  cmp     [rbx], ax
0x1400385ce  ja      short loc_1400385DC
0x1400385d0  cmp     byte ptr [rbx+0Ch], 0
0x1400385d4  jnz     short loc_1400385DC
0x1400385d6  cmp     byte ptr [rbx+0Dh], 0
0x1400385da  jz      short loc_1400385E2
0x1400385dc  mov     dword ptr [rdi], 2
0x1400385e2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400385e9  jz      short loc_140038610
0x1400385eb  mov     r9d, 81h
0x1400385f1  mov     [rsp+88h+var_60], r12d
0x1400385f6  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400385fd  mov     dl, 2
0x1400385ff  mov     rcx, r13
0x140038602  mov     [rsp+88h+var_68], rax
0x140038607  lea     r8d, [r9-7Ch]
0x14003860b  call    WPP_RECORDER_SF_d
0x140038610  mov     edx, 5Eh ; '^'
0x140038615  jmp     loc_14003882E
0x14003861a  mov     ebx, 1
0x14003861f  mov     [rdi], ebx
0x140038621  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140038628  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003862f  jz      loc_140038845
0x140038635  movzx   eax, byte ptr [rsi]
0x140038638  lea     r9d, [rbx+7Eh]
0x14003863c  mov     [rsp+88h+var_50], ecx
0x140038640  mov     dl, 2
0x140038642  mov     [rsp+88h+var_58], eax
0x140038646  mov     rcx, r13
0x140038649  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038650  mov     [rsp+88h+var_60], r12d
0x140038655  mov     [rsp+88h+var_68], rax
0x14003865a  call    WPP_RECORDER_SF_DDD
0x14003865f  jmp     loc_140038840
0x140038664  movzx   eax, byte ptr [rsi+2]
0x140038668  mov     ecx, 100h
0x14003866d  sub     ecx, eax
0x14003866f  mov     r15d, 200h
0x140038675  movzx   eax, byte ptr [rsi+3]
0x140038679  cmp     ecx, eax
0x14003867b  jge     short loc_1400386E1
0x14003867d  cmp     [rbx], r15w
0x140038681  ja      short loc_14003868F
0x140038683  cmp     byte ptr [rbx+0Ch], 0
0x140038687  jnz     short loc_14003868F
0x140038689  cmp     byte ptr [rbx+0Dh], 0
0x14003868d  jz      short loc_140038695
0x14003868f  mov     dword ptr [rdi], 2
0x140038695  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003869c  jz      short loc_1400386CF
0x14003869e  movzx   eax, byte ptr [rsi+3]
0x1400386a2  mov     r9d, 82h
0x1400386a8  movzx   ecx, byte ptr [rsi+2]
0x1400386ac  mov     dl, 2
0x1400386ae  mov     [rsp+88h+var_50], eax
0x1400386b2  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400386b9  mov     [rsp+88h+var_58], ecx
0x1400386bd  mov     rcx, r13
0x1400386c0  mov     [rsp+88h+var_60], r12d
0x1400386c5  mov     [rsp+88h+var_68], rax
0x1400386ca  call    WPP_RECORDER_SF_DDD
0x1400386cf  mov     rax, [rbx+18h]
0x1400386d3  mov     edx, 61h ; 'a'
0x1400386d8  mov     rcx, [rbx+28h]
0x1400386dc  call    _guard_dispatch_icall
0x1400386e1  mov     r14, [rsp+88h+arg_8]
0x1400386e9  mov     al, [r14+4]
0x1400386ed  cmp     [rsi+3], al
0x1400386f0  jbe     short loc_140038757
0x1400386f2  cmp     [rbx], r15w
0x1400386f6  ja      short loc_140038704
0x1400386f8  cmp     byte ptr [rbx+0Ch], 0
0x1400386fc  jnz     short loc_140038704
0x1400386fe  cmp     byte ptr [rbx+0Dh], 0
0x140038702  jz      short loc_14003870A
0x140038704  mov     dword ptr [rdi], 2
0x14003870a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140038711  jz      short loc_140038745
0x140038713  movzx   eax, byte ptr [r14+4]
0x140038718  mov     r9d, 83h
0x14003871e  movzx   ecx, byte ptr [rsi+3]
0x140038722  mov     dl, 2
0x140038724  mov     [rsp+88h+var_50], eax
0x140038728  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003872f  mov     [rsp+88h+var_58], ecx
0x140038733  mov     rcx, r13
0x140038736  mov     [rsp+88h+var_60], r12d
0x14003873b  mov     [rsp+88h+var_68], rax
0x140038740  call    WPP_RECORDER_SF_DDD
0x140038745  mov     rax, [rbx+18h]
0x140038749  mov     edx, 5Fh ; '_'
0x14003874e  mov     rcx, [rbx+28h]
0x140038752  call    _guard_dispatch_icall
0x140038757  movzx   eax, word ptr [rbx+0CAh]
0x14003875e  movzx   ecx, byte ptr [rsi+3]
0x140038762  add     ecx, eax
0x140038764  movzx   eax, byte ptr [r14+4]
0x140038769  cmp     ecx, eax
0x14003876b  jbe     short loc_1400387DD
0x14003876d  cmp     [rbx], r15w
0x140038771  ja      short loc_140038779
0x140038773  cmp     byte ptr [rbx+0Ch], 0
0x140038777  jz      short loc_14003877F
0x140038779  mov     dword ptr [rdi], 2
0x14003877f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140038786  jz      short loc_1400387CB
0x140038788  movzx   eax, byte ptr [r14+4]
0x14003878d  mov     r9d, 84h
0x140038793  movzx   ecx, word ptr [rbx+0CAh]
0x14003879a  mov     dl, 2
0x14003879c  movzx   r8d, byte ptr [rsi+3]
0x1400387a1  mov     [rsp+88h+var_48], eax
0x1400387a5  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400387ac  mov     [rsp+88h+var_50], ecx
0x1400387b0  mov     rcx, r13
0x1400387b3  mov     [rsp+88h+var_58], r8d
0x1400387b8  lea     r8d, [r9-7Fh]
0x1400387bc  mov     [rsp+88h+var_60], r12d
0x1400387c1  mov     [rsp+88h+var_68], rax
0x1400387c6  call    WPP_RECORDER_SF_DDDD
0x1400387cb  mov     rax, [rbx+18h]
0x1400387cf  mov     edx, 5Fh ; '_'
0x1400387d4  mov     rcx, [rbx+28h]
0x1400387d8  call    _guard_dispatch_icall
0x1400387dd  cmp     byte ptr [rsi+3], 0
0x1400387e1  jnz     short loc_14003883B
0x1400387e3  cmp     [rbx], r15w
0x1400387e7  ja      short loc_1400387F5
0x1400387e9  cmp     byte ptr [rbx+0Ch], 0
0x1400387ed  jnz     short loc_1400387F5
0x1400387ef  cmp     byte ptr [rbx+0Dh], 0
0x1400387f3  jz      short loc_1400387FB
0x1400387f5  mov     dword ptr [rdi], 2
0x1400387fb  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140038802  jz      short loc_140038829
0x140038804  mov     r9d, 85h
0x14003880a  mov     [rsp+88h+var_60], r12d
0x14003880f  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038816  mov     dl, 2
0x140038818  mov     rcx, r13
0x14003881b  mov     [rsp+88h+var_68], rax
0x140038820  lea     r8d, [r9-80h]
0x140038824  call    WPP_RECORDER_SF_d
0x140038829  mov     edx, 60h ; '`'
0x14003882e  mov     rcx, [rbx+28h]
0x140038832  mov     rax, [rbx+18h]
0x140038836  call    _guard_dispatch_icall
0x14003883b  mov     ebx, 1
0x140038840  cmp     dword ptr [rdi], 0
0x140038843  jz      short loc_140038872
0x140038845  xor     bl, bl
0x140038847  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003884e  jz      short loc_140038872
0x140038850  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038857  mov     r9d, 86h
0x14003885d  mov     r8d, 5
0x140038863  mov     [rsp+88h+var_68], rax
0x140038868  mov     dl, 2
0x14003886a  mov     rcx, r13
0x14003886d  call    WPP_RECORDER_SF_
0x140038872  mov     al, bl
0x140038874  mov     rbx, [rsp+88h+arg_10]
0x14003887c  add     rsp, 50h
0x140038880  pop     r15
0x140038882  pop     r14
0x140038884  pop     r13
0x140038886  pop     r12
0x140038888  pop     rdi
0x140038889  pop     rsi
0x14003888a  pop     rbp
0x14003888b  retn
```
