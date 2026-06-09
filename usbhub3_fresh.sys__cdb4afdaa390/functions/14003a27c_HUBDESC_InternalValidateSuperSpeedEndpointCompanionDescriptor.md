# HUBDESC_InternalValidateSuperSpeedEndpointCompanionDescriptor

- ea: `0x14003a27c`
- end: `0x14003ad10`
- name: `HUBDESC_InternalValidateSuperSpeedEndpointCompanionDescriptor`
- size: `2708`
- prototype: `char __fastcall(char *, __int64, unsigned int *, int *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x14003a27c`
- `0x14003bf54`
- `0x14003f208`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateSuperSpeedEndpointCompanionDescriptor(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5,
        _BYTE *a6)
{
  int *v6; // r14
  __int64 v8; // rbx
  _BYTE *v10; // r13
  unsigned int v11; // eax
  int v12; // r15d
  __int64 v13; // rdx
  unsigned int v14; // edx
  char v15; // r12
  unsigned int v16; // ecx
  int v17; // edx
  int v18; // r8d
  char v19; // r10
  __int64 v20; // r11
  int v21; // edx
  unsigned int v23; // eax
  __int64 v24; // rax
  int v25; // edx
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rdx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  __int64 v32; // rdx
  unsigned int v33; // edx
  int v34; // edx
  int v35; // edx
  int v36; // r8d
  int v37; // edx
  int v38; // edx
  int v39; // edx
  __int64 v40; // [rsp+28h] [rbp-70h]
  int v41; // [rsp+28h] [rbp-70h]
  int v42; // [rsp+A0h] [rbp+8h] BYREF

  v6 = a4;
  v8 = a2;
  v42 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v6 = &v42;
  }
  v10 = a6;
  if ( a6 )
    *a6 = 0;
  v11 = (unsigned __int8)*a1;
  *a3 = v11;
  v12 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  if ( *(_DWORD *)(a2 + 4) != 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v41 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(a5, a2, 5, 74, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v41);
    }
    v13 = 40;
LABEL_11:
    (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), v13);
LABEL_12:
    v15 = 1;
    goto LABEL_13;
  }
  LODWORD(a6) = *(_DWORD *)(a2 + 72) - v12;
  if ( (unsigned __int8)v11 >= 6u )
  {
LABEL_23:
    if ( (unsigned __int8)*a1 > 6u )
    {
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_DDD(a5, v17, v18, 77, v20, *a1, v12, v19);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 42);
    }
    v21 = *(_DWORD *)(v8 + 256);
    if ( (v21 & 4) == 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v40) = v12;
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_d(a5, v21, 5, 78, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v40);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 41);
      *v6 = 2;
      goto LABEL_33;
    }
    v23 = (unsigned int)a6;
    v14 = v21 & 0xFFFFFFDB | 0x20;
    *(_DWORD *)(v8 + 256) = v14;
    if ( *a3 > v23 )
    {
      if ( *(_WORD *)v8 > 0x200u || *(_BYTE *)(v8 + 12) )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v40) = v12;
        LOBYTE(v14) = 2;
        WPP_RECORDER_SF_d(a5, v14, 5, 79, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v40);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 44);
      v15 = 1;
      goto LABEL_13;
    }
    v24 = *(_QWORD *)(v8 + 192);
    switch ( *(_BYTE *)(v24 + 3) & 3 )
    {
      case 0:
        if ( a1[2] )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v38) = 2;
            WPP_RECORDER_SF_dD(a5, v38, 5, 80, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[2]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 38);
        }
        if ( a1[3] )
        {
          if ( *(_BYTE *)(v8 + 15) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_dD(a5, v14, 5, 81, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[3]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 37);
        }
        if ( !*((_WORD *)a1 + 2) )
          goto LABEL_12;
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v39) = 2;
          WPP_RECORDER_SF_dD(
            a5,
            v39,
            5,
            82,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v12,
            *((_WORD *)a1 + 2));
        }
        v13 = 39;
        goto LABEL_11;
      case 1:
        v33 = v14 & 0xFFFFFFBF;
        *(_DWORD *)(v8 + 256) = v33;
        v14 = v33 & 0xFFFFFFF7;
        *(_DWORD *)(v8 + 256) = v14 | ((unsigned __int8)a1[3] >> 4) & 0xFFFFFF8;
        if ( (unsigned __int8)a1[2] > 0xFu )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v34) = 2;
            WPP_RECORDER_SF_dD(a5, v34, 5, 91, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[2]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 50);
        }
        if ( a1[2] && *(_WORD *)(*(_QWORD *)(v8 + 192) + 4LL) != 1024 )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v35) = 2;
            WPP_RECORDER_SF_DDD(
              a5,
              v35,
              v36,
              92,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              v12,
              a1[2],
              *(_WORD *)(*(_QWORD *)(v8 + 192) + 4LL));
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 51);
        }
        if ( (*(_DWORD *)(v8 + 256) & 8) == 0 && (a1[3] & 3) == 3 )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v37) = 2;
            WPP_RECORDER_SF_dD(a5, v37, 5, 93, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[3] & 3);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 52);
        }
        if ( (a1[3] & 0x7C) != 0 )
        {
          if ( *(_BYTE *)(v8 + 15) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_dD(a5, v14, 5, 94, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[3]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 49);
        }
        v15 = 1;
        if ( (*(_DWORD *)(v8 + 256) & 8) == 0 )
        {
          v14 = ((unsigned __int8)a1[2] + 1) * *(unsigned __int16 *)(*(_QWORD *)(v8 + 192) + 4LL) * ((a1[3] & 3) + 1);
          if ( *((unsigned __int16 *)a1 + 2) <= v14 )
            goto LABEL_13;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_Ddd(a5, v14, (_DWORD)a3, 95);
          v28 = 53;
LABEL_70:
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 32))(*(_QWORD *)(v8 + 40), v28);
          goto LABEL_13;
        }
        if ( *((_WORD *)a1 + 2) == 1 )
          goto LABEL_13;
        if ( *(_BYTE *)(v8 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_dD(
            a5,
            v14,
            5,
            96,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v12,
            *((_WORD *)a1 + 2));
        }
        v32 = 204;
        break;
      case 2:
        if ( (unsigned __int8)a1[2] > 0xFu )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = 2;
            WPP_RECORDER_SF_dD(a5, v29, 5, 83, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[2]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 34);
        }
        v15 = 1;
        if ( (a1[3] & 0x1F) != 0 && v10 )
          *v10 = 1;
        if ( (a1[3] & 0x1Fu) > 0x10 )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v30) = 2;
            WPP_RECORDER_SF_dD(
              a5,
              v30,
              5,
              84,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              v12,
              a1[3] & 0x1F);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 35);
        }
        if ( (unsigned __int8)a1[3] >= 0x20u )
        {
          if ( *(_BYTE *)(v8 + 15) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_dD(a5, v14, 5, 85, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[3]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 33);
        }
        if ( !*((_WORD *)a1 + 2) )
          goto LABEL_13;
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v31) = 2;
          WPP_RECORDER_SF_dD(
            a5,
            v31,
            5,
            86,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v12,
            *((_WORD *)a1 + 2));
        }
        v32 = 36;
        break;
      case 3:
        if ( (unsigned __int8)a1[2] > 0xFu )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = 2;
            WPP_RECORDER_SF_dD(a5, v25, 5, 87, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[2]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 45);
        }
        if ( a1[2] && *(_WORD *)(*(_QWORD *)(v8 + 192) + 4LL) != 1024 )
        {
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v26) = 2;
            WPP_RECORDER_SF_DDD(
              a5,
              v26,
              v27,
              88,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              v12,
              a1[2],
              *(_WORD *)(*(_QWORD *)(v8 + 192) + 4LL));
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 46);
        }
        if ( a1[3] )
        {
          if ( *(_BYTE *)(v8 + 15) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_dD(a5, v14, 5, 89, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, a1[3]);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 47);
        }
        v15 = 1;
        v14 = ((unsigned __int8)a1[2] + 1) * *(unsigned __int16 *)(*(_QWORD *)(v8 + 192) + 4LL) * ((a1[3] & 3) + 1);
        if ( *((unsigned __int16 *)a1 + 2) > v14 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_Ddd(a5, v14, (_DWORD)a3, 90);
          v28 = 48;
          goto LABEL_70;
        }
LABEL_13:
        if ( !*v6 )
          return v15;
        goto LABEL_33;
      default:
        goto LABEL_12;
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), v32);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 43);
  if ( (unsigned int)a6 >= 6 )
    *a3 = 6;
  v16 = *a3;
  *v6 = 2;
  if ( v16 >= 6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_DDDD(a5, v14, 5, 76, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v12, 6, v16);
    }
    goto LABEL_23;
  }
  v15 = 1;
  *v6 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_DDD(a5, v14, (_DWORD)a3, 75, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v12, 6);
    goto LABEL_13;
  }
LABEL_33:
  v15 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_(a5, v14, 5, 97, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v15;
}

```

## disassembly

```asm
0x14003a27c  mov     rax, rsp
0x14003a27f  push    rbx
0x14003a280  push    rbp
0x14003a281  push    rsi
0x14003a282  push    rdi
0x14003a283  push    r12
0x14003a285  push    r13
0x14003a287  push    r14
0x14003a289  push    r15
0x14003a28b  sub     rsp, 58h
0x14003a28f  mov     r14, r9
0x14003a292  mov     r12, r8
0x14003a295  xor     r9d, r9d
0x14003a298  mov     rbx, rdx
0x14003a29b  mov     [rax+8], r9d
0x14003a29f  mov     rsi, rcx
0x14003a2a2  test    r14, r14
0x14003a2a5  jnz     short loc_14003A2AD
0x14003a2a7  lea     r14, [rax+8]
0x14003a2ab  jmp     short loc_14003A2B6
0x14003a2ad  cmp     [rdx+30h], r9b
0x14003a2b1  jz      short loc_14003A2B6
0x14003a2b3  mov     [r14], r9d
0x14003a2b6  mov     r13, [rsp+98h+arg_28]
0x14003a2be  test    r13, r13
0x14003a2c1  jz      short loc_14003A2C7
0x14003a2c3  mov     [r13+0], r9b
0x14003a2c7  movzx   eax, byte ptr [rcx]
0x14003a2ca  lea     r11, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a2d1  mov     r15d, esi
0x14003a2d4  mov     [r8], eax
0x14003a2d7  sub     r15d, [rdx+38h]
0x14003a2db  cmp     dword ptr [rdx+4], 3
0x14003a2df  jz      short loc_14003A341
0x14003a2e1  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a2e8  mov     edi, 2
0x14003a2ed  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003a2f4  jz      short loc_14003A318
0x14003a2f6  mov     rcx, [rsp+98h+arg_20]
0x14003a2fe  lea     r9d, [rdi+48h]
0x14003a302  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a307  lea     r8d, [rdi+3]
0x14003a30b  mov     dl, dil
0x14003a30e  mov     [rsp+98h+var_78], r11
0x14003a313  call    WPP_RECORDER_SF_d
0x14003a318  mov     edx, 28h ; '('
0x14003a31d  mov     rax, [rbx+18h]
0x14003a321  mov     rcx, [rbx+28h]
0x14003a325  call    _guard_dispatch_icall
0x14003a32a  mov     r12d, 1
0x14003a330  xor     r13d, r13d
0x14003a333  cmp     [r14], r13d
0x14003a336  jnz     loc_14003A4F0
0x14003a33c  jmp     loc_14003A522
0x14003a341  mov     ecx, [rdx+48h]
0x14003a344  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003a34b  sub     ecx, r15d
0x14003a34e  mov     edi, 2
0x14003a353  mov     dword ptr [rsp+98h+arg_28], ecx
0x14003a35a  lea     r10d, [rdi+4]
0x14003a35e  cmp     al, r10b
0x14003a361  jnb     loc_14003A43A
0x14003a367  mov     rax, [rdx+18h]
0x14003a36b  lea     edx, [rdi+29h]
0x14003a36e  mov     rcx, [rbx+28h]
0x14003a372  call    _guard_dispatch_icall
0x14003a377  lea     r10d, [rdi+4]
0x14003a37b  cmp     dword ptr [rsp+98h+arg_28], r10d
0x14003a383  jb      short loc_14003A389
0x14003a385  mov     [r12], r10d
0x14003a389  mov     ecx, [r12]
0x14003a38d  mov     [r14], edi
0x14003a390  cmp     ecx, r10d
0x14003a393  jnb     short loc_14003A3E9
0x14003a395  mov     r12d, 1
0x14003a39b  mov     [r14], r12d
0x14003a39e  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003a3a5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003a3ac  jz      loc_14003A4ED
0x14003a3b2  movzx   eax, byte ptr [rsi]
0x14003a3b5  lea     r9d, [r12+4Ah]
0x14003a3ba  mov     rcx, [rsp+98h+arg_20]
0x14003a3c2  mov     dl, dil
0x14003a3c5  mov     [rsp+98h+var_60], r10d
0x14003a3ca  mov     [rsp+98h+var_68], r15d
0x14003a3cf  mov     dword ptr [rsp+98h+var_70], eax
0x14003a3d3  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a3da  mov     [rsp+98h+var_78], rax
0x14003a3df  call    WPP_RECORDER_SF_DDD
0x14003a3e4  jmp     loc_14003A330
0x14003a3e9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a3f0  jz      short loc_14003A433
0x14003a3f2  movzx   eax, byte ptr [rsi]
0x14003a3f5  mov     r9d, 4Ch ; 'L'
0x14003a3fb  mov     [rsp+98h+var_58], ecx
0x14003a3ff  mov     dl, dil
0x14003a402  mov     rcx, [rsp+98h+arg_20]
0x14003a40a  mov     [rsp+98h+var_60], r10d
0x14003a40f  mov     [rsp+98h+var_68], r15d
0x14003a414  lea     r8d, [r9-47h]
0x14003a418  mov     dword ptr [rsp+98h+var_70], eax
0x14003a41c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a423  mov     [rsp+98h+var_78], rax
0x14003a428  call    WPP_RECORDER_SF_DDDD
0x14003a42d  mov     r10d, 6
0x14003a433  lea     r11, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a43a  cmp     [rsi], r10b
0x14003a43d  jbe     short loc_14003A495
0x14003a43f  mov     rcx, rbx
0x14003a442  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003a447  test    al, al
0x14003a449  jz      short loc_14003A44E
0x14003a44b  mov     [r14], edi
0x14003a44e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a455  jz      short loc_14003A483
0x14003a457  movzx   eax, byte ptr [rsi]
0x14003a45a  mov     r9d, 4Dh ; 'M'
0x14003a460  mov     rcx, [rsp+98h+arg_20]
0x14003a468  mov     dl, dil
0x14003a46b  mov     [rsp+98h+var_60], r10d
0x14003a470  mov     [rsp+98h+var_68], r15d
0x14003a475  mov     dword ptr [rsp+98h+var_70], eax
0x14003a479  mov     [rsp+98h+var_78], r11
0x14003a47e  call    WPP_RECORDER_SF_DDD
0x14003a483  mov     rax, [rbx+18h]
0x14003a487  mov     edx, 2Ah ; '*'
0x14003a48c  mov     rcx, [rbx+28h]
0x14003a490  call    _guard_dispatch_icall
0x14003a495  mov     edx, [rbx+100h]
0x14003a49b  test    dl, 4
0x14003a49e  jnz     loc_14003A537
0x14003a4a4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a4ab  jz      short loc_14003A4D8
0x14003a4ad  mov     rcx, [rsp+98h+arg_20]
0x14003a4b5  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a4bc  mov     r9d, 4Eh ; 'N'
0x14003a4c2  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a4c7  mov     dl, dil
0x14003a4ca  mov     [rsp+98h+var_78], rax
0x14003a4cf  lea     r8d, [r9-49h]
0x14003a4d3  call    WPP_RECORDER_SF_d
0x14003a4d8  mov     rax, [rbx+18h]
0x14003a4dc  mov     edx, 29h ; ')'
0x14003a4e1  mov     rcx, [rbx+28h]
0x14003a4e5  call    _guard_dispatch_icall
0x14003a4ea  mov     [r14], edi
0x14003a4ed  xor     r13d, r13d
0x14003a4f0  mov     r12b, r13b
0x14003a4f3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a4fa  jz      short loc_14003A522
0x14003a4fc  mov     rcx, [rsp+98h+arg_20]
0x14003a504  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a50b  mov     r9d, 61h ; 'a'
0x14003a511  mov     [rsp+98h+var_78], rax
0x14003a516  mov     dl, dil
0x14003a519  lea     r8d, [r9-5Ch]
0x14003a51d  call    WPP_RECORDER_SF_
0x14003a522  mov     al, r12b
0x14003a525  add     rsp, 58h
0x14003a529  pop     r15
0x14003a52b  pop     r14
0x14003a52d  pop     r13
0x14003a52f  pop     r12
0x14003a531  pop     rdi
0x14003a532  pop     rsi
0x14003a533  pop     rbp
0x14003a534  pop     rbx
0x14003a535  retn
0x14003a537  mov     eax, dword ptr [rsp+98h+arg_28]
0x14003a53e  and     edx, 0FFFFFFFBh
0x14003a541  or      edx, 20h
0x14003a544  mov     [rbx+100h], edx
0x14003a54a  cmp     [r12], eax
0x14003a54e  jbe     short loc_14003A5B7
0x14003a550  mov     eax, 200h
0x14003a555  xor     r13d, r13d
0x14003a558  cmp     [rbx], ax
0x14003a55b  ja      short loc_14003A563
0x14003a55d  cmp     [rbx+0Ch], r13b
0x14003a561  jz      short loc_14003A566
0x14003a563  mov     [r14], edi
0x14003a566  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a56d  jz      short loc_14003A59A
0x14003a56f  mov     rcx, [rsp+98h+arg_20]
0x14003a577  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a57e  mov     r9d, 4Fh ; 'O'
0x14003a584  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a589  mov     dl, dil
0x14003a58c  mov     [rsp+98h+var_78], rax
0x14003a591  lea     r8d, [r9-4Ah]
0x14003a595  call    WPP_RECORDER_SF_d
0x14003a59a  mov     rax, [rbx+18h]
0x14003a59e  mov     edx, 2Ch ; ','
0x14003a5a3  mov     rcx, [rbx+28h]
0x14003a5a7  call    _guard_dispatch_icall
0x14003a5ac  mov     r12d, 1
0x14003a5b2  jmp     loc_14003A333
0x14003a5b7  mov     rax, [rbx+0C0h]
0x14003a5be  xor     r12d, r12d
0x14003a5c1  movzx   ecx, byte ptr [rax+3]
0x14003a5c5  and     ecx, 3
0x14003a5c8  jz      loc_14003ABF0
0x14003a5ce  sub     ecx, 1
0x14003a5d1  jz      loc_14003A94F
0x14003a5d7  sub     ecx, 1
0x14003a5da  jz      loc_14003A79C
0x14003a5e0  cmp     ecx, 1
0x14003a5e3  jnz     loc_14003A32A
0x14003a5e9  cmp     byte ptr [rsi+2], 0Fh
0x14003a5ed  jbe     short loc_14003A64C
0x14003a5ef  mov     rcx, rbx
0x14003a5f2  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003a5f7  test    al, al
0x14003a5f9  jz      short loc_14003A5FE
0x14003a5fb  mov     [r14], edi
0x14003a5fe  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a605  jz      short loc_14003A63A
0x14003a607  movzx   eax, byte ptr [rsi+2]
0x14003a60b  mov     r9d, 57h ; 'W'
0x14003a611  mov     rcx, [rsp+98h+arg_20]
0x14003a619  mov     dl, dil
0x14003a61c  mov     [rsp+98h+var_68], eax
0x14003a620  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a627  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a62c  lea     r8d, [r9-52h]
0x14003a630  mov     [rsp+98h+var_78], rax
0x14003a635  call    WPP_RECORDER_SF_dD
0x14003a63a  mov     rax, [rbx+18h]
0x14003a63e  mov     edx, 2Dh ; '-'
0x14003a643  mov     rcx, [rbx+28h]
0x14003a647  call    _guard_dispatch_icall
0x14003a64c  cmp     [rsi+2], r12b
0x14003a650  jz      short loc_14003A6CC
0x14003a652  mov     rax, [rbx+0C0h]
0x14003a659  mov     ecx, 400h
0x14003a65e  cmp     [rax+4], cx
0x14003a662  jz      short loc_14003A6CC
0x14003a664  mov     rcx, rbx
0x14003a667  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003a66c  test    al, al
0x14003a66e  jz      short loc_14003A673
0x14003a670  mov     [r14], edi
0x14003a673  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a67a  jz      short loc_14003A6BA
0x14003a67c  mov     rax, [rbx+0C0h]
0x14003a683  mov     r9d, 58h ; 'X'
0x14003a689  mov     dl, dil
0x14003a68c  movzx   ecx, word ptr [rax+4]
0x14003a690  movzx   eax, byte ptr [rsi+2]
0x14003a694  mov     [rsp+98h+var_60], ecx
0x14003a698  mov     rcx, [rsp+98h+arg_20]
0x14003a6a0  mov     [rsp+98h+var_68], eax
0x14003a6a4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a6ab  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a6b0  mov     [rsp+98h+var_78], rax
0x14003a6b5  call    WPP_RECORDER_SF_DDD
0x14003a6ba  mov     rax, [rbx+18h]
0x14003a6be  mov     edx, 2Eh ; '.'
0x14003a6c3  mov     rcx, [rbx+28h]
0x14003a6c7  call    _guard_dispatch_icall
0x14003a6cc  cmp     [rsi+3], r12b
0x14003a6d0  jz      short loc_14003A729
0x14003a6d2  cmp     [rbx+0Fh], r12b
0x14003a6d6  jz      short loc_14003A6DB
0x14003a6d8  mov     [r14], edi
0x14003a6db  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a6e2  jz      short loc_14003A717
0x14003a6e4  movzx   eax, byte ptr [rsi+3]
0x14003a6e8  mov     r9d, 59h ; 'Y'
0x14003a6ee  mov     rcx, [rsp+98h+arg_20]
0x14003a6f6  mov     dl, dil
0x14003a6f9  mov     [rsp+98h+var_68], eax
0x14003a6fd  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003a704  mov     dword ptr [rsp+98h+var_70], r15d
0x14003a709  lea     r8d, [r9-54h]
0x14003a70d  mov     [rsp+98h+var_78], rax
0x14003a712  call    WPP_RECORDER_SF_dD
0x14003a717  mov     rax, [rbx+18h]
0x14003a71b  mov     edx, 2Fh ; '/'
0x14003a720  mov     rcx, [rbx+28h]
0x14003a724  call    _guard_dispatch_icall
0x14003a729  mov     rax, [rbx+0C0h]
0x14003a730  mov     r12d, 1
0x14003a736  movzx   edx, byte ptr [rsi+3]
0x14003a73a  and     edx, 3
0x14003a73d  add     edx, r12d
0x14003a740  movzx   ecx, word ptr [rax+4]
0x14003a744  movzx   eax, byte ptr [rsi+2]
0x14003a748  add     eax, r12d
0x14003a74b  imul    edx, ecx
0x14003a74e  imul    edx, eax
0x14003a751  movzx   eax, word ptr [rsi+4]
0x14003a755  cmp     eax, edx
0x14003a757  jbe     loc_14003A330
0x14003a75d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003a764  jz      short loc_14003A785
0x14003a766  mov     rcx, [rsp+98h+arg_20]
0x14003a76e  lea     r9d, [r12+59h]
0x14003a773  mov     [rsp+98h+var_60], edx
0x14003a777  mov     [rsp+98h+var_68], eax
  ... truncated ...
```
