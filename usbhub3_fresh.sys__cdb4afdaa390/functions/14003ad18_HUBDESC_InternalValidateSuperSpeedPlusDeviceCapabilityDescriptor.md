# HUBDESC_InternalValidateSuperSpeedPlusDeviceCapabilityDescriptor

- ea: `0x14003ad18`
- end: `0x14003b5f3`
- name: `HUBDESC_InternalValidateSuperSpeedPlusDeviceCapabilityDescriptor`
- size: `2267`
- prototype: `__int64 __fastcall(unsigned __int8 *, __int64, unsigned int *, int *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14003676c`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x14003ad18`
- `0x14003f420`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDESC_InternalValidateSuperSpeedPlusDeviceCapabilityDescriptor(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int *v6; // rsi
  int v9; // r14d
  unsigned int v10; // r12d
  __int64 result; // rax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rax
  unsigned int v15; // edx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // r14d
  __int64 v19; // r8
  unsigned int v20; // ecx
  int v21; // edx
  unsigned int v22; // eax
  __int64 v23; // r9
  int v24; // ecx
  int v25; // r10d
  int v26; // eax
  int v27; // r9d
  int v28; // [rsp+20h] [rbp-A8h]
  __int64 v29; // [rsp+28h] [rbp-A0h]
  char v30; // [rsp+30h] [rbp-98h]
  char v31; // [rsp+38h] [rbp-90h]
  int v32; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v33; // [rsp+74h] [rbp-54h]
  unsigned int v34; // [rsp+78h] [rbp-50h]
  unsigned int v35; // [rsp+7Ch] [rbp-4Ch]
  __int64 v36; // [rsp+80h] [rbp-48h]
  char v37; // [rsp+D0h] [rbp+8h]
  unsigned int v38; // [rsp+D8h] [rbp+10h]
  unsigned int v39; // [rsp+E8h] [rbp+20h]

  v6 = a4;
  v32 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v6 = &v32;
  }
  v9 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v10 = *(_DWORD *)(a2 + 72) - v9;
  if ( *a1 >= 0x10u )
  {
LABEL_9:
    v14 = *a1;
    v34 = *((_DWORD *)a1 + 1) & 0x1F;
    v15 = v34;
    if ( v14 != 4LL * v34 + 16 )
    {
      if ( *(_BYTE *)(a2 + 12) || *(_WORD *)a2 == 784 )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v31 = 4 * v15 + 16;
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_DDD(a5, v15, 0, 187, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v9, *a1, v31);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 213);
    }
    if ( *a3 <= v10 )
    {
      if ( *((_DWORD *)a1 + 1) >= 0x200u )
      {
        if ( *(_BYTE *)(a2 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_d(a5, v15, 5, 189, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 215);
      }
      if ( (a1[8] & 0xF0) != 0 )
      {
        if ( *(_BYTE *)(a2 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_d(a5, v15, 5, 190, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 216);
      }
      if ( a1[3] )
      {
        if ( *(_BYTE *)(a2 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_d(a5, v15, 5, 191, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 218);
      }
      if ( *((_WORD *)a1 + 5) )
      {
        if ( *(_BYTE *)(a2 + 15) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_d(a5, v15, 5, 192, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 219);
      }
      v17 = 0;
      v38 = 0;
      v37 = 0;
      v18 = 0;
      v19 = 0;
      v39 = 0;
      while ( 1 )
      {
        v35 = v18 + 1;
        v36 = v18 + 1;
        if ( (unsigned __int64)&a1[4 * v36 + 12] > *(_QWORD *)(a2 + 64) )
          break;
        v15 = *(_DWORD *)&a1[4 * v18 + 12];
        if ( (v15 & 0x80u) != 0 )
        {
          if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v29) = v18;
            LOBYTE(v15) = 2;
            WPP_RECORDER_SF_d(a5, v15, 5, 194, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29);
          }
          v16 = 220;
          goto LABEL_104;
        }
        if ( (((unsigned __int8)v15 ^ (unsigned __int8)*((_WORD *)a1 + 4)) & 0xF) == 0 )
        {
          v37 = 1;
          if ( (v15 & 0x40) == 0 && (*((_WORD *)a1 + 4) & 0xF00) != ((*((_WORD *)a1 + 4) >> 4) & 0xF00) )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
              *v6 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v20 = *((unsigned __int16 *)a1 + 4);
              v21 = (v20 >> 8) & 0xF;
              LOBYTE(v21) = 2;
              WPP_RECORDER_SF_DDD(
                a5,
                v21,
                v19,
                195,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                a1[4 * v18 + 12] & 0xF,
                BYTE1(v20) & 0xF,
                v20 >> 12);
            }
            (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 225, v19, v17);
            v19 = v39;
            v17 = v38;
          }
        }
        v22 = *(_DWORD *)&a1[4 * v18 + 12] & 0xF;
        if ( _bittest((const int *)&v19, v22) )
        {
          if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 2;
            WPP_RECORDER_SF_dD(
              a5,
              v15,
              5,
              196,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              v18,
              a1[4 * v18 + 12] & 0xF);
          }
          (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 226, v19, v17);
        }
        else
        {
          LODWORD(v19) = v19 | (1 << v22);
          v17 = (unsigned int)(v17 + 1);
          v39 = v19;
          v38 = v17;
        }
        v33 = v18 + 2;
        if ( (unsigned __int64)&a1[4 * v18 + 20] > *(_QWORD *)(a2 + 64) )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_90;
          v27 = 197;
          goto LABEL_117;
        }
        v23 = v36;
        v24 = *(_DWORD *)&a1[4 * v36 + 12];
        if ( (v24 & 0x80u) == 0 )
        {
          if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v29) = v35;
            LOBYTE(v15) = 2;
            WPP_RECORDER_SF_d(a5, v15, 5, 198, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29);
          }
          v16 = 221;
          goto LABEL_104;
        }
        v25 = *(_DWORD *)&a1[4 * v18 + 12];
        if ( (((unsigned __int8)v25 ^ (unsigned __int8)v24) & 0xF) != 0
          || (((unsigned __int8)v25 ^ (unsigned __int8)v24) & 0x40) != 0
          || (((unsigned __int16)v25 ^ (unsigned __int16)v24) & 0xC000) != 0 )
        {
          if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
          {
            *v6 = 2;
            v25 = *(_DWORD *)&a1[4 * v18 + 12];
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dDDDdDDD(
              a5,
              (*(_DWORD *)&a1[4 * v23 + 12] >> 6) & 1,
              v25 & 0xF,
              199,
              v28,
              v18,
              v25 & 0xF,
              (v25 & 0x40) != 0,
              (unsigned __int16)v25 >> 14,
              v18 + 1,
              v25 & 0xF,
              (*(_DWORD *)&a1[4 * v23 + 12] & 0x40) != 0,
              (unsigned __int8)HIBYTE(*(_WORD *)&a1[4 * v23 + 12]) >> 6);
          (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 223);
          v23 = v36;
        }
        v26 = *(_DWORD *)&a1[4 * v18 + 12];
        if ( (v26 & 0x40) == 0
          && (((a1[4 * v23 + 12] ^ (unsigned __int8)v26) & 0x30) != 0
           || *(_WORD *)&a1[4 * v18 + 14] != *(_WORD *)&a1[4 * v23 + 14]) )
        {
          if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
            *v6 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v30 = a1[4 * v18 + 12] & 0xF;
            WPP_RECORDER_SF_dDDDdDDD(
              a5,
              (*(_DWORD *)&a1[4 * v23 + 12] >> 4) & 3,
              (*(_DWORD *)&a1[4 * v18 + 12] >> 4) & 3,
              200,
              v28,
              v18,
              v30,
              *(_WORD *)&a1[4 * v18 + 14],
              (*(_DWORD *)&a1[4 * v18 + 12] >> 4) & 3,
              v18 + 1,
              v30,
              *(_WORD *)&a1[4 * v23 + 14],
              (*(_DWORD *)&a1[4 * v23 + 12] >> 4) & 3);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 224);
        }
        v18 = v33;
        v19 = v39;
        v17 = v38;
        if ( v33 > v34 )
          goto LABEL_90;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = 193;
LABEL_117:
        LODWORD(v29) = v18;
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(a5, v15, 5, v27, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29);
      }
LABEL_90:
      result = ((*((_DWORD *)a1 + 1) >> 5) & 0xFu) + 1;
      if ( (_DWORD)result != v38 )
      {
        if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_dD(
            a5,
            v15,
            5,
            201,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v38,
            ((*((_DWORD *)a1 + 1) >> 5) & 0xF) + 1);
        }
        result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(a2 + 24))(
                   *(_QWORD *)(a2 + 40),
                   227,
                   v19,
                   v17);
      }
      if ( !v37 )
      {
        if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
          *v6 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          LODWORD(v29) = *(_DWORD *)&a1[4 * v18 + 12] & 0xF;
          WPP_RECORDER_SF_d(a5, v15, 5, 202, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29);
        }
        v16 = 228;
        goto LABEL_104;
      }
    }
    else
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v6 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v29) = v9;
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(a5, v15, 5, 188, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29);
      }
      v16 = 217;
LABEL_104:
      result = (*(__int64 (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v16);
    }
    goto LABEL_105;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 214);
  if ( v10 >= 0x10 )
  {
    *v6 = 2;
    *a3 = 16;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DDDD(a5, v12, 5, 185, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v9, *a1, 16, 16);
    }
    goto LABEL_9;
  }
  *v6 = 1;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return result;
  LOBYTE(v12) = 2;
  result = WPP_RECORDER_SF_DDD(a5, v12, v13, 186, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v9, *a1, 16);
LABEL_105:
  if ( *v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      return WPP_RECORDER_SF_(a5, v15, 5, 203, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003ad18  mov     [rsp+arg_10], rbx
0x14003ad1d  push    rbp
0x14003ad1e  push    rsi
0x14003ad1f  push    rdi
0x14003ad20  push    r12
0x14003ad22  push    r13
0x14003ad24  push    r14
0x14003ad26  push    r15
0x14003ad28  sub     rsp, 90h
0x14003ad2f  mov     r13, r8
0x14003ad32  mov     rsi, r9
0x14003ad35  xor     r8d, r8d
0x14003ad38  mov     rbx, rdx
0x14003ad3b  mov     [rsp+0C8h+var_58], r8d
0x14003ad40  mov     rdi, rcx
0x14003ad43  test    r9, r9
0x14003ad46  jnz     short loc_14003AD4F
0x14003ad48  lea     rsi, [rsp+0C8h+var_58]
0x14003ad4d  jmp     short loc_14003AD58
0x14003ad4f  cmp     [rdx+30h], r8b
0x14003ad53  jz      short loc_14003AD58
0x14003ad55  mov     [r9], r8d
0x14003ad58  mov     r12d, [rdx+48h]
0x14003ad5c  lea     r10, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ad63  mov     r15, [rsp+0C8h+arg_20]
0x14003ad6b  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003ad72  mov     r14d, edi
0x14003ad75  sub     r14d, [rdx+38h]
0x14003ad79  sub     r12d, r14d
0x14003ad7c  cmp     byte ptr [rcx], 10h
0x14003ad7f  jnb     short loc_14003ADF2
0x14003ad81  mov     rax, [rdx+18h]
0x14003ad85  mov     edx, 0D6h
0x14003ad8a  mov     rcx, [rbx+28h]
0x14003ad8e  call    _guard_dispatch_icall
0x14003ad93  mov     ecx, 10h
0x14003ad98  cmp     r12d, ecx
0x14003ad9b  jb      loc_14003AEC5
0x14003ada1  mov     dword ptr [rsi], 2
0x14003ada7  mov     [r13+0], ecx
0x14003adab  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003adb2  jz      short loc_14003ADE8
0x14003adb4  movzx   eax, byte ptr [rdi]
0x14003adb7  lea     r8d, [rcx-0Bh]
0x14003adbb  mov     [rsp+0C8h+var_88], ecx
0x14003adbf  mov     r9d, 0B9h
0x14003adc5  mov     dword ptr [rsp+0C8h+var_90], ecx
0x14003adc9  mov     dl, 2
0x14003adcb  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003adcf  mov     rcx, r15
0x14003add2  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003add9  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x14003adde  mov     [rsp+0C8h+var_A8], rax
0x14003ade3  call    WPP_RECORDER_SF_DDDD
0x14003ade8  lea     r10, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003adef  xor     r8d, r8d
0x14003adf2  mov     edx, [rdi+4]
0x14003adf5  movzx   eax, byte ptr [rdi]
0x14003adf8  and     edx, 1Fh
0x14003adfb  mov     [rsp+0C8h+var_50], edx
0x14003adff  lea     rcx, ds:10h[rdx*4]
0x14003ae07  cmp     rax, rcx
0x14003ae0a  jz      short loc_14003AE69
0x14003ae0c  cmp     [rbx+0Ch], r8b
0x14003ae10  jnz     short loc_14003AE1C
0x14003ae12  mov     ecx, 310h
0x14003ae17  cmp     [rbx], cx
0x14003ae1a  jnz     short loc_14003AE22
0x14003ae1c  mov     dword ptr [rsi], 2
0x14003ae22  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003ae29  jz      short loc_14003AE57
0x14003ae2b  movzx   ecx, byte ptr [rdi]
0x14003ae2e  lea     eax, ds:10h[rdx*4]
0x14003ae35  mov     dword ptr [rsp+0C8h+var_90], eax
0x14003ae39  mov     r9d, 0BBh
0x14003ae3f  mov     dword ptr [rsp+0C8h+var_98], ecx
0x14003ae43  mov     dl, 2
0x14003ae45  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x14003ae4a  mov     rcx, r15
0x14003ae4d  mov     [rsp+0C8h+var_A8], r10
0x14003ae52  call    WPP_RECORDER_SF_DDD
0x14003ae57  mov     rax, [rbx+18h]
0x14003ae5b  mov     edx, 0D5h
0x14003ae60  mov     rcx, [rbx+28h]
0x14003ae64  call    _guard_dispatch_icall
0x14003ae69  cmp     [r13+0], r12d
0x14003ae6d  mov     r12d, 200h
0x14003ae73  jbe     loc_14003AF10
0x14003ae79  cmp     [rbx], r12w
0x14003ae7d  ja      short loc_14003AE85
0x14003ae7f  cmp     byte ptr [rbx+0Ch], 0
0x14003ae83  jz      short loc_14003AE8B
0x14003ae85  mov     dword ptr [rsi], 2
0x14003ae8b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003ae92  jz      short loc_14003AEBB
0x14003ae94  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ae9b  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x14003aea0  mov     r9d, 0BCh
0x14003aea6  mov     [rsp+0C8h+var_A8], rax
0x14003aeab  mov     r8d, 5
0x14003aeb1  mov     dl, 2
0x14003aeb3  mov     rcx, r15
0x14003aeb6  call    WPP_RECORDER_SF_d
0x14003aebb  mov     edx, 0D9h
0x14003aec0  jmp     loc_14003B4A8
0x14003aec5  mov     dword ptr [rsi], 1
0x14003aecb  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003aed2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003aed9  jz      loc_14003B4E5
0x14003aedf  movzx   eax, byte ptr [rdi]
0x14003aee2  lea     r13, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003aee9  mov     dword ptr [rsp+0C8h+var_90], ecx
0x14003aeed  mov     r9d, 0BAh
0x14003aef3  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003aef7  mov     dl, 2
0x14003aef9  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x14003aefe  mov     rcx, r15
0x14003af01  mov     [rsp+0C8h+var_A8], r13
0x14003af06  call    WPP_RECORDER_SF_DDD
0x14003af0b  jmp     loc_14003B4B5
0x14003af10  cmp     [rdi+4], r12d
0x14003af14  jb      short loc_14003AF66
0x14003af16  cmp     byte ptr [rbx+0Fh], 0
0x14003af1a  jz      short loc_14003AF22
0x14003af1c  mov     dword ptr [rsi], 2
0x14003af22  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003af29  jz      short loc_14003AF54
0x14003af2b  mov     eax, [rdi+4]
0x14003af2e  mov     r9d, 0BDh
0x14003af34  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003af38  mov     r8d, 5
0x14003af3e  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003af45  mov     dl, 2
0x14003af47  mov     rcx, r15
0x14003af4a  mov     [rsp+0C8h+var_A8], rax
0x14003af4f  call    WPP_RECORDER_SF_d
0x14003af54  mov     rax, [rbx+18h]
0x14003af58  mov     edx, 0D7h
0x14003af5d  mov     rcx, [rbx+28h]
0x14003af61  call    _guard_dispatch_icall
0x14003af66  test    byte ptr [rdi+8], 0F0h
0x14003af6a  jz      short loc_14003AFBD
0x14003af6c  cmp     byte ptr [rbx+0Fh], 0
0x14003af70  jz      short loc_14003AF78
0x14003af72  mov     dword ptr [rsi], 2
0x14003af78  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003af7f  jz      short loc_14003AFAB
0x14003af81  movzx   eax, word ptr [rdi+8]
0x14003af85  mov     r9d, 0BEh
0x14003af8b  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003af8f  mov     r8d, 5
0x14003af95  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003af9c  mov     dl, 2
0x14003af9e  mov     rcx, r15
0x14003afa1  mov     [rsp+0C8h+var_A8], rax
0x14003afa6  call    WPP_RECORDER_SF_d
0x14003afab  mov     rax, [rbx+18h]
0x14003afaf  mov     edx, 0D8h
0x14003afb4  mov     rcx, [rbx+28h]
0x14003afb8  call    _guard_dispatch_icall
0x14003afbd  xor     r10d, r10d
0x14003afc0  cmp     [rdi+3], r10b
0x14003afc4  jz      short loc_14003B01A
0x14003afc6  cmp     [rbx+0Fh], r10b
0x14003afca  jz      short loc_14003AFD2
0x14003afcc  mov     dword ptr [rsi], 2
0x14003afd2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003afd9  jz      short loc_14003B005
0x14003afdb  movzx   eax, byte ptr [rdi+3]
0x14003afdf  mov     r9d, 0BFh
0x14003afe5  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003afe9  mov     r8d, 5
0x14003afef  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003aff6  mov     dl, 2
0x14003aff8  mov     rcx, r15
0x14003affb  mov     [rsp+0C8h+var_A8], rax
0x14003b000  call    WPP_RECORDER_SF_d
0x14003b005  mov     rax, [rbx+18h]
0x14003b009  mov     edx, 0DAh
0x14003b00e  mov     rcx, [rbx+28h]
0x14003b012  call    _guard_dispatch_icall
0x14003b017  xor     r10d, r10d
0x14003b01a  cmp     [rdi+0Ah], r10w
0x14003b01f  jz      short loc_14003B075
0x14003b021  cmp     [rbx+0Fh], r10b
0x14003b025  jz      short loc_14003B02D
0x14003b027  mov     dword ptr [rsi], 2
0x14003b02d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b034  jz      short loc_14003B060
0x14003b036  movzx   eax, word ptr [rdi+0Ah]
0x14003b03a  mov     r9d, 0C0h
0x14003b040  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003b044  mov     r8d, 5
0x14003b04a  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b051  mov     dl, 2
0x14003b053  mov     rcx, r15
0x14003b056  mov     [rsp+0C8h+var_A8], rax
0x14003b05b  call    WPP_RECORDER_SF_d
0x14003b060  mov     rax, [rbx+18h]
0x14003b064  mov     edx, 0DBh
0x14003b069  mov     rcx, [rbx+28h]
0x14003b06d  call    _guard_dispatch_icall
0x14003b072  xor     r10d, r10d
0x14003b075  mov     r9d, r10d
0x14003b078  mov     [rsp+0C8h+arg_8], r10d
0x14003b080  mov     [rsp+0C8h+arg_0], r10b
0x14003b088  mov     r14d, r10d
0x14003b08b  mov     r8d, r10d
0x14003b08e  mov     [rsp+0C8h+arg_18], r10d
0x14003b096  mov     r11d, 0F00h
0x14003b09c  lea     eax, [r14+1]
0x14003b0a0  mov     [rsp+0C8h+var_4C], eax
0x14003b0a4  mov     [rsp+0C8h+var_48], rax
0x14003b0ac  add     rax, 3
0x14003b0b0  lea     rax, [rdi+rax*4]
0x14003b0b4  cmp     rax, [rbx+40h]
0x14003b0b8  ja      loc_14003B5D4
0x14003b0be  mov     r13d, r14d
0x14003b0c1  mov     edx, [rdi+r13*4+0Ch]
0x14003b0c6  test    dl, dl
0x14003b0c8  js      loc_14003B588
0x14003b0ce  movzx   ecx, word ptr [rdi+8]
0x14003b0d2  mov     eax, ecx
0x14003b0d4  xor     eax, edx
0x14003b0d6  test    al, 0Fh
0x14003b0d8  jnz     loc_14003B182
0x14003b0de  mov     [rsp+0C8h+arg_0], 1
0x14003b0e6  test    dl, 40h
0x14003b0e9  jnz     loc_14003B182
0x14003b0ef  movzx   eax, cx
0x14003b0f2  and     cx, r11w
0x14003b0f6  shr     ax, 4
0x14003b0fa  and     ax, r11w
0x14003b0fe  cmp     cx, ax
0x14003b101  jz      short loc_14003B182
0x14003b103  cmp     [rbx], r12w
0x14003b107  ja      short loc_14003B10F
0x14003b109  cmp     [rbx+0Ch], r10b
0x14003b10d  jz      short loc_14003B115
0x14003b10f  mov     dword ptr [rsi], 2
0x14003b115  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b11c  jz      short loc_14003B15D
0x14003b11e  movzx   edx, word ptr [rdi+8]
0x14003b122  mov     r9d, 0C3h
0x14003b128  mov     eax, [rdi+r13*4+0Ch]
0x14003b12d  mov     ecx, edx
0x14003b12f  shr     edx, 8
0x14003b132  and     eax, 0Fh
0x14003b135  shr     ecx, 0Ch
0x14003b138  and     edx, 0Fh
0x14003b13b  mov     dword ptr [rsp+0C8h+var_90], ecx
0x14003b13f  mov     rcx, r15
0x14003b142  mov     dword ptr [rsp+0C8h+var_98], edx
0x14003b146  mov     dl, 2
0x14003b148  mov     dword ptr [rsp+0C8h+var_A0], eax
0x14003b14c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b153  mov     [rsp+0C8h+var_A8], rax
0x14003b158  call    WPP_RECORDER_SF_DDD
0x14003b15d  mov     rax, [rbx+18h]
0x14003b161  mov     edx, 0E1h
0x14003b166  mov     rcx, [rbx+28h]
0x14003b16a  call    _guard_dispatch_icall
0x14003b16f  mov     r8d, [rsp+0C8h+arg_18]
0x14003b177  xor     r10d, r10d
0x14003b17a  mov     r9d, [rsp+0C8h+arg_8]
0x14003b182  mov     eax, [rdi+r13*4+0Ch]
0x14003b187  and     eax, 0Fh
0x14003b18a  bt      r8d, eax
0x14003b18e  jnb     short loc_14003B1F2
0x14003b190  cmp     [rbx], r12w
0x14003b194  ja      short loc_14003B19C
0x14003b196  cmp     [rbx+0Ch], r10b
0x14003b19a  jz      short loc_14003B1A2
0x14003b19c  mov     dword ptr [rsi], 2
0x14003b1a2  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b1a9  jz      short loc_14003B1DE
0x14003b1ab  mov     eax, [rdi+r13*4+0Ch]
0x14003b1b0  mov     r9d, 0C4h
0x14003b1b6  and     eax, 0Fh
0x14003b1b9  mov     r8d, 5
0x14003b1bf  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003b1c3  mov     dl, 2
0x14003b1c5  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b1cc  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x14003b1d1  mov     rcx, r15
0x14003b1d4  mov     [rsp+0C8h+var_A8], rax
0x14003b1d9  call    WPP_RECORDER_SF_dD
0x14003b1de  mov     rax, [rbx+18h]
0x14003b1e2  mov     edx, 0E2h
0x14003b1e7  mov     rcx, [rbx+28h]
0x14003b1eb  call    _guard_dispatch_icall
0x14003b1f0  jmp     short loc_14003B209
0x14003b1f2  bts     r8d, eax
0x14003b1f6  inc     r9d
0x14003b1f9  mov     [rsp+0C8h+arg_18], r8d
0x14003b201  mov     [rsp+0C8h+arg_8], r9d
0x14003b209  lea     eax, [r14+2]
0x14003b20d  mov     ecx, eax
0x14003b20f  add     rcx, 3
0x14003b213  mov     [rsp+0C8h+var_54], eax
  ... truncated ...
```
