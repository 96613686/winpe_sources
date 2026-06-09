# VMX_RAW_CONFIG::UnformatRecords(uchar * *,unsigned __int64,unsigned __int64)

- ea: `0x14005e110`
- end: `0x14005e91e`
- name: `?UnformatRecords@VMX_RAW_CONFIG@@AEAAJPEAPEAE_K1@Z`
- size: `2062`
- prototype: `__int64 __fastcall(VMX_RAW_CONFIG *__hidden this, unsigned __int8 **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059780`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001a52c`
- `0x140058f88`
- `0x14005a2f8`
- `0x14005a37c`
- `0x14005e110`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005e55b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e55b`
- `ntoskrnl!RtlCompareMemory` at `0x14005e1fd`
- `ntoskrnl!RtlCompareMemory` at `0x14005e1fd`

## pseudocode

```c
__int64 __fastcall VMX_RAW_CONFIG::UnformatRecords(
        VMX_RAW_CONFIG *this,
        unsigned __int8 **a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  __int64 v5; // r11
  VMX_NOTIFICATION_QUEUE *v7; // rcx
  __int64 v8; // rdx
  unsigned __int8 *v9; // r13
  unsigned int v10; // r14d
  unsigned __int64 v11; // rdx
  __int64 i; // rsi
  int v13; // r8d
  __int16 v14; // r9
  int v15; // ecx
  unsigned int v16; // ebp
  unsigned __int16 v17; // r12
  struct VMX_RAW_RECORD *RawRecordByReference; // rax
  unsigned __int16 v19; // r8
  struct VMX_RAW_RECORD *v20; // rdi
  _OWORD *v21; // rax
  unsigned int v22; // r8d
  _OWORD *v23; // rdi
  unsigned int v24; // edx
  int v25; // r14d
  unsigned int v26; // edx
  unsigned int v27; // eax
  VMX_RAW_CONFIG **v28; // rcx
  __int16 v29; // dx
  __int64 result; // rax
  int v31; // r8d
  unsigned int v32; // r14d
  unsigned int v33; // r8d
  _OWORD *v34; // rax
  VMX_RAW_CONFIG **v35; // rdx
  __int64 v36; // rax
  unsigned int v37; // r11d
  __int16 v38; // dx
  __int64 v39; // r10
  unsigned int *j; // r9
  unsigned int v41; // r10d
  void *v42; // rcx
  unsigned int v43; // ecx
  VMX_NOTIFICATION_QUEUE *v44; // rcx
  __int64 v45; // rdx
  unsigned __int8 *v46; // [rsp+30h] [rbp-58h] BYREF
  __int64 v47; // [rsp+38h] [rbp-50h]
  unsigned int v48; // [rsp+90h] [rbp+8h]
  unsigned __int64 v51; // [rsp+A8h] [rbp+20h]

  v4 = *((unsigned int *)this + 20);
  v5 = a3;
  if ( a4 % v4 || a3 % v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3224895490LL;
    }
    v8 = 49;
    goto LABEL_115;
  }
  if ( (unsigned int)v4 <= 0x18 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v8 = 50;
      goto LABEL_115;
    }
    return 3224895490LL;
  }
  v9 = *a2;
  v10 = v4 - 16;
  v48 = v4 - 16;
  v11 = a4 / v4;
  v51 = a4 / v4;
  for ( i = *((_QWORD *)this + 17) + 24LL * (unsigned int)(a4 / v4); ; i += 24 )
  {
    v47 = v5;
    if ( !v5 )
    {
      *a2 += a3;
      return 0;
    }
    if ( (unsigned int)v11 >= *((_DWORD *)this + 19) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3224895490LL;
      }
      v8 = 63;
      goto LABEL_115;
    }
    *(_DWORD *)(i + 8) = -1;
    if ( RtlCompareMemory(v9, "VBLK", 4u) != 4 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3224895490LL;
      }
      v8 = 51;
      goto LABEL_115;
    }
    v13 = v9[8];
    v14 = v9[14];
    v15 = v9[7] | ((v9[6] | ((v9[5] | (v9[4] << 8)) << 8)) << 8);
    v46 = v9 + 16;
    if ( v15 != (_DWORD)v51 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3224895490LL;
      }
      v8 = 52;
      goto LABEL_115;
    }
    v16 = v9[11] | ((v9[10] | ((v9[9] | (v13 << 8)) << 8)) << 8);
    if ( !v16 )
      goto LABEL_38;
    v17 = (v14 << 8) | v9[15];
    RawRecordByReference = VMX_RAW_CONFIG::FindRawRecordByReference(this, v16);
    v20 = RawRecordByReference;
    if ( !v19 )
      break;
    v31 = v10 * v19;
    v32 = v10 - 16;
    *(_DWORD *)(i + 16) = v32;
    v33 = v31 - 8;
    *(_DWORD *)(i + 12) = v33;
    if ( RawRecordByReference )
    {
      v37 = *((_DWORD *)RawRecordByReference + 7);
      if ( (v37 + v48 + 7) / v48 == v17 )
      {
        v38 = *((_WORD *)RawRecordByReference + 12);
        if ( (v38 & 2) == 0 )
        {
          if ( (v38 & 5) == 0 )
          {
            v39 = *((_QWORD *)this + 17);
            for ( j = (unsigned int *)(v39 + 24LL * *((unsigned int *)RawRecordByReference + 8));
                  j[2] != -1;
                  j = (unsigned int *)(v39 + 24LL * j[2]) )
            {
              ;
            }
            v41 = j[3] + j[4];
            if ( v41 > v33 )
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
              {
                v8 = 61;
                goto LABEL_115;
              }
              return 3224895490LL;
            }
            if ( v41 >= v33 )
            {
              if ( v33 >= v37 )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
                {
                  v8 = 62;
                  goto LABEL_115;
                }
                return 3224895490LL;
              }
              *(_QWORD *)i = RawRecordByReference;
              v43 = *((_DWORD *)RawRecordByReference + 7);
              if ( v33 + v32 >= v43 )
              {
                *(_DWORD *)(i + 16) = v43 - v33;
                *((_WORD *)RawRecordByReference + 12) |= 2u;
              }
              j[2] = v51;
              result = VMX_RAW_RECORD::UnformatRecordFragment(
                         RawRecordByReference,
                         &v46,
                         *(_DWORD *)(i + 16),
                         *(_DWORD *)(i + 12),
                         *(struct VMX_CONFIG **)this);
              if ( (int)result < 0 )
                return result;
              goto LABEL_52;
            }
            v42 = (void *)*((_QWORD *)RawRecordByReference + 6);
            *((_DWORD *)RawRecordByReference + 8) = -1;
            *((_WORD *)RawRecordByReference + 12) = v38 | 1;
            if ( v42 )
            {
              ExFreePoolWithTag(v42, 0);
              *((_QWORD *)v20 + 6) = 0;
            }
          }
          *(_QWORD *)i = v20;
LABEL_52:
          v10 = v48;
          goto LABEL_38;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3224895490LL;
        }
        v8 = 60;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3224895490LL;
        }
        v8 = 59;
      }
LABEL_115:
      WPP_SF_d(*((_QWORD *)v7 + 3), v8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3224895490LL);
      return 3224895490LL;
    }
    v34 = VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x72526D56u);
    if ( !v34 )
    {
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v45 = 58;
LABEL_80:
        WPP_SF_d(*((_QWORD *)v44 + 3), v45, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3221225626LL);
      }
      return 3221225626LL;
    }
    *v34 = 0;
    v34[1] = 0;
    v34[2] = 0;
    *((_QWORD *)v34 + 6) = 0;
    *((_WORD *)v34 + 12) |= 1u;
    *((_DWORD *)v34 + 4) = v16;
    *((_DWORD *)v34 + 8) = -1;
    *(_QWORD *)i = v34;
    v35 = (VMX_RAW_CONFIG **)*((_QWORD *)this + 15);
    if ( *v35 != (VMX_RAW_CONFIG *)((char *)this + 112) )
      goto LABEL_75;
    v10 = v48;
    *(_QWORD *)v34 = (char *)this + 112;
    *((_QWORD *)v34 + 1) = v35;
    *v35 = (VMX_RAW_CONFIG *)v34;
    *((_QWORD *)this + 15) = v34;
LABEL_38:
    v36 = *((unsigned int *)this + 20);
    v9 += v36;
    LODWORD(v11) = v51 + 1;
    v5 = v47 - v36;
    LODWORD(v51) = v51 + 1;
  }
  *(_DWORD *)(i + 12) = 0;
  *(_DWORD *)(i + 16) = v10 - 8;
  if ( RawRecordByReference )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v8 = 53;
      goto LABEL_115;
    }
    return 3224895490LL;
  }
  v21 = VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x72526D56u);
  v23 = v21;
  if ( !v21 )
  {
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v45 = 54;
      goto LABEL_80;
    }
    return 3221225626LL;
  }
  *v21 = 0;
  v21[1] = 0;
  v21[2] = 0;
  *((_QWORD *)v21 + 6) = 0;
  *((_DWORD *)v21 + 8) = -1;
  v25 = VMX_RAW_RECORD::UnformatHeader((VMX_RAW_RECORD *)v21, &v46, v22);
  if ( v25 >= 0 )
  {
    v10 = v48;
    v26 = (v48 + *((_DWORD *)v23 + 7) + 7) % v48;
    if ( (v48 + *((_DWORD *)v23 + 7) + 7) / v48 != v17 )
    {
      VMX_RAW_RECORD::`scalar deleting destructor'((VMX_RAW_RECORD *)v23, v26);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v8 = 56;
        goto LABEL_115;
      }
      return 3224895490LL;
    }
    if ( (*((_BYTE *)v23 + 22) & 3) == 3 )
    {
      VMX_RAW_RECORD::`scalar deleting destructor'((VMX_RAW_RECORD *)v23, v26);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v8 = 57;
        goto LABEL_115;
      }
      return 3224895490LL;
    }
    *((_DWORD *)v23 + 8) = v51;
    *((_DWORD *)v23 + 4) = v16;
    *(_QWORD *)i = v23;
    v27 = *((_DWORD *)v23 + 7);
    if ( *(_DWORD *)(i + 16) >= v27 )
    {
      *(_DWORD *)(i + 16) = v27;
      *((_WORD *)v23 + 12) |= 2u;
    }
    v28 = (VMX_RAW_CONFIG **)*((_QWORD *)this + 15);
    if ( *v28 != (VMX_RAW_CONFIG *)((char *)this + 112) )
LABEL_75:
      __fastfail(3u);
    *(_QWORD *)v23 = (char *)this + 112;
    *((_QWORD *)v23 + 1) = v28;
    *v28 = (VMX_RAW_CONFIG *)v23;
    *((_QWORD *)this + 15) = v23;
    v29 = *((_WORD *)v23 + 11);
    if ( (v29 & 2) != 0 && (*((_WORD *)this + 36) == 1 || *((_WORD *)this + 36) == 2 || *((_WORD *)this + 36) == 4) )
      *((_WORD *)v23 + 12) |= 4u;
    if ( (v29 & 1) != 0 && *((_WORD *)this + 36) == 3 )
      *((_WORD *)v23 + 12) |= 4u;
    if ( (*((_BYTE *)v23 + 24) & 4) == 0 )
    {
      result = VMX_RAW_RECORD::UnformatRecordFragment(
                 (VMX_RAW_RECORD *)v23,
                 &v46,
                 *(_DWORD *)(i + 16),
                 *(_DWORD *)(i + 12),
                 *(struct VMX_CONFIG **)this);
      if ( (int)result < 0 )
        return result;
    }
    goto LABEL_38;
  }
  VMX_RAW_RECORD::`scalar deleting destructor'((VMX_RAW_RECORD *)v23, v24);
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      55,
      WPP_36c7d132267136af2220cbe73d2245a2_Traceguids,
      (unsigned int)v25);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14005e110  mov     [rsp+arg_10], r8
0x14005e115  mov     [rsp+arg_8], rdx
0x14005e11a  push    rbx
0x14005e11b  push    rbp
0x14005e11c  push    rsi
0x14005e11d  push    rdi
0x14005e11e  push    r12
0x14005e120  push    r13
0x14005e122  push    r14
0x14005e124  push    r15
0x14005e126  sub     rsp, 48h
0x14005e12a  mov     r10d, [rcx+50h]
0x14005e12e  mov     r11, r8
0x14005e131  mov     r8, rdx
0x14005e134  mov     rax, r9
0x14005e137  xor     edx, edx
0x14005e139  xor     ebp, ebp
0x14005e13b  div     r10
0x14005e13e  mov     r15, rcx
0x14005e141  test    rdx, rdx
0x14005e144  jnz     loc_14005E8CA
0x14005e14a  mov     rax, r11
0x14005e14d  div     r10
0x14005e150  test    rdx, rdx
0x14005e153  jnz     loc_14005E8CA
0x14005e159  cmp     r10d, 18h
0x14005e15d  ja      short loc_14005E195
0x14005e15f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e166  lea     rax, WPP_GLOBAL_Control
0x14005e16d  cmp     rcx, rax
0x14005e170  jz      loc_14005E907
0x14005e176  mov     eax, [rcx+2Ch]
0x14005e179  test    al, 40h
0x14005e17b  jz      loc_14005E907
0x14005e181  lea     ebx, [rbp+2]
0x14005e184  cmp     [rcx+29h], bl
0x14005e187  jb      loc_14005E907
0x14005e18d  lea     edx, [rbp+32h]
0x14005e190  jmp     loc_14005E8F1
0x14005e195  mov     r13, [r8]
0x14005e198  lea     r14d, [r10-10h]
0x14005e19c  xor     edx, edx
0x14005e19e  mov     [rsp+88h+arg_0], r14d
0x14005e1a6  mov     rax, r9
0x14005e1a9  mov     ebx, 2
0x14005e1ae  div     r10
0x14005e1b1  lea     r12d, [rbx+2]
0x14005e1b5  mov     rdx, rax
0x14005e1b8  mov     [rsp+88h+arg_18], rax
0x14005e1c0  mov     eax, eax
0x14005e1c2  lea     rcx, [rax+rax*2]
0x14005e1c6  mov     rax, [r15+88h]
0x14005e1cd  lea     rsi, [rax+rcx*8]
0x14005e1d1  mov     [rsp+88h+var_50], r11
0x14005e1d6  test    r11, r11
0x14005e1d9  jz      loc_14005E8B3
0x14005e1df  cmp     edx, [r15+4Ch]
0x14005e1e3  jnb     loc_14005E88D
0x14005e1e9  mov     r8, r12; Length
0x14005e1ec  mov     dword ptr [rsi+8], 0FFFFFFFFh
0x14005e1f3  lea     rdx, aVblk; "VBLK"
0x14005e1fa  mov     rcx, r13; Source1
0x14005e1fd  call    cs:__imp_RtlCompareMemory
0x14005e204  nop     dword ptr [rax+rax+00h]
0x14005e209  cmp     rax, r12
0x14005e20c  jnz     loc_14005E85B
0x14005e212  movzx   eax, byte ptr [r13+5]
0x14005e217  movzx   ecx, byte ptr [r13+4]
0x14005e21c  movzx   r8d, byte ptr [r13+8]
0x14005e221  movzx   edx, byte ptr [r13+0Ch]
0x14005e226  movzx   r9d, byte ptr [r13+0Eh]
0x14005e22b  shl     ecx, 8
0x14005e22e  or      ecx, eax
0x14005e230  movzx   eax, byte ptr [r13+6]
0x14005e235  shl     ecx, 8
0x14005e238  or      ecx, eax
0x14005e23a  movzx   eax, byte ptr [r13+7]
0x14005e23f  shl     ecx, 8
0x14005e242  or      ecx, eax
0x14005e244  lea     rax, [r13+10h]
0x14005e248  mov     [rsp+88h+var_58], rax
0x14005e24d  cmp     ecx, dword ptr [rsp+88h+arg_18]
0x14005e254  jnz     loc_14005E826
0x14005e25a  movzx   eax, byte ptr [r13+9]
0x14005e25f  mov     ebp, r8d
0x14005e262  shl     ebp, 8
0x14005e265  or      ebp, eax
0x14005e267  movzx   eax, byte ptr [r13+0Ah]
0x14005e26c  shl     ebp, 8
0x14005e26f  or      ebp, eax
0x14005e271  movzx   eax, byte ptr [r13+0Bh]
0x14005e276  shl     ebp, 8
0x14005e279  or      ebp, eax
0x14005e27b  jz      loc_14005E49E
0x14005e281  movzx   r8d, byte ptr [r13+0Dh]
0x14005e286  movzx   eax, r9w
0x14005e28a  movzx   r12d, byte ptr [r13+0Fh]
0x14005e28f  mov     rcx, r15; this
0x14005e292  shl     dx, 8
0x14005e296  shl     ax, 8
0x14005e29a  or      r8w, dx
0x14005e29e  mov     edx, ebp; unsigned int
0x14005e2a0  or      r12w, ax
0x14005e2a4  call    ?FindRawRecordByReference@VMX_RAW_CONFIG@@AEAAPEAVVMX_RAW_RECORD@@K@Z; VMX_RAW_CONFIG::FindRawRecordByReference(ulong)
0x14005e2a9  xor     ecx, ecx
0x14005e2ab  mov     rdi, rax
0x14005e2ae  test    r8w, r8w
0x14005e2b2  jnz     loc_14005E40E
0x14005e2b8  mov     [rsi+0Ch], ecx
0x14005e2bb  lea     eax, [r14-8]
0x14005e2bf  mov     [rsi+10h], eax
0x14005e2c2  test    rdi, rdi
0x14005e2c5  jnz     loc_14005E6CE
0x14005e2cb  mov     edx, 102h; unsigned __int64
0x14005e2d0  lea     ecx, [rdi+38h]; unsigned __int64
0x14005e2d3  mov     r8d, 72526D56h; unsigned int
0x14005e2d9  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14005e2de  mov     rdi, rax
0x14005e2e1  test    rax, rax
0x14005e2e4  jz      loc_14005E69C
0x14005e2ea  xorps   xmm0, xmm0
0x14005e2ed  lea     rdx, [rsp+88h+var_58]; unsigned __int8 **
0x14005e2f2  movups  xmmword ptr [rdi], xmm0
0x14005e2f5  xor     eax, eax
0x14005e2f7  mov     rcx, rdi; this
0x14005e2fa  movups  xmmword ptr [rdi+10h], xmm0
0x14005e2fe  movups  xmmword ptr [rdi+20h], xmm0
0x14005e302  mov     [rdi+30h], rax
0x14005e306  mov     dword ptr [rdi+20h], 0FFFFFFFFh
0x14005e30d  call    ?UnformatHeader@VMX_RAW_RECORD@@QEAAJPEAPEAEK@Z; VMX_RAW_RECORD::UnformatHeader(uchar * *,ulong)
0x14005e312  mov     r14d, eax
0x14005e315  test    eax, eax
0x14005e317  js      loc_14005E655
0x14005e31d  mov     r14d, [rsp+88h+arg_0]
0x14005e325  xor     edx, edx; unsigned int
0x14005e327  mov     eax, [rdi+1Ch]
0x14005e32a  add     eax, 7
0x14005e32d  add     eax, r14d
0x14005e330  div     r14d
0x14005e333  mov     ecx, eax
0x14005e335  movzx   eax, r12w
0x14005e339  cmp     ecx, eax
0x14005e33b  jnz     loc_14005E618
0x14005e341  mov     al, [rdi+16h]
0x14005e344  mov     r8d, 3
0x14005e34a  and     al, r8b
0x14005e34d  cmp     al, r8b
0x14005e350  jz      loc_14005E5DB
0x14005e356  mov     rax, [rsp+88h+arg_18]
0x14005e35e  mov     [rdi+20h], eax
0x14005e361  mov     [rdi+10h], ebp
0x14005e364  mov     [rsi], rdi
0x14005e367  mov     eax, [rdi+1Ch]
0x14005e36a  cmp     [rsi+10h], eax
0x14005e36d  jb      short loc_14005E376
0x14005e36f  mov     [rsi+10h], eax
0x14005e372  or      [rdi+18h], bx
0x14005e376  lea     rax, [r15+70h]
0x14005e37a  mov     rcx, [rax+8]
0x14005e37e  cmp     [rcx], rax
0x14005e381  jnz     loc_14005E709
0x14005e387  mov     [rdi], rax
0x14005e38a  mov     [rdi+8], rcx
0x14005e38e  mov     [rcx], rdi
0x14005e391  mov     [rax+8], rdi
0x14005e395  movzx   edx, word ptr [rdi+16h]
0x14005e399  test    bl, dl
0x14005e39b  jz      short loc_14005E3BD
0x14005e39d  movzx   ecx, word ptr [r15+48h]
0x14005e3a2  sub     ecx, 1
0x14005e3a5  jz      short loc_14005E3B0
0x14005e3a7  sub     ecx, 1
0x14005e3aa  jz      short loc_14005E3B0
0x14005e3ac  cmp     ecx, ebx
0x14005e3ae  jnz     short loc_14005E3BD
0x14005e3b0  mov     r12d, 4
0x14005e3b6  or      [rdi+18h], r12w
0x14005e3bb  jmp     short loc_14005E3C3
0x14005e3bd  mov     r12d, 4
0x14005e3c3  mov     ecx, 1
0x14005e3c8  test    cl, dl
0x14005e3ca  jz      short loc_14005E3D8
0x14005e3cc  cmp     [r15+48h], r8w
0x14005e3d1  jnz     short loc_14005E3D8
0x14005e3d3  or      [rdi+18h], r12w
0x14005e3d8  test    [rdi+18h], r12b
0x14005e3dc  jnz     loc_14005E49E
0x14005e3e2  mov     rax, [r15]
0x14005e3e5  lea     rdx, [rsp+88h+var_58]; unsigned __int8 **
0x14005e3ea  mov     r9d, [rsi+0Ch]; unsigned int
0x14005e3ee  mov     rcx, rdi; this
0x14005e3f1  mov     r8d, [rsi+10h]; unsigned int
0x14005e3f5  mov     [rsp+88h+var_68], rax; struct VMX_CONFIG *
0x14005e3fa  call    ?UnformatRecordFragment@VMX_RAW_RECORD@@QEAAJPEAPEAEKKPEAVVMX_CONFIG@@@Z; VMX_RAW_RECORD::UnformatRecordFragment(uchar * *,ulong,ulong,VMX_CONFIG *)
0x14005e3ff  xor     ebp, ebp
0x14005e401  test    eax, eax
0x14005e403  jns     loc_14005E4A0
0x14005e409  jmp     loc_14005E90C
0x14005e40e  movzx   r8d, r8w
0x14005e412  imul    r8d, r14d
0x14005e416  add     r14d, 0FFFFFFF0h
0x14005e41a  mov     [rsi+10h], r14d
0x14005e41e  add     r8d, 0FFFFFFF8h
0x14005e422  mov     [rsi+0Ch], r8d
0x14005e426  test    rdi, rdi
0x14005e429  jnz     loc_14005E4CA
0x14005e42f  mov     edx, 102h; unsigned __int64
0x14005e434  lea     ecx, [rdi+38h]; unsigned __int64
0x14005e437  mov     r8d, 72526D56h; unsigned int
0x14005e43d  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14005e442  test    rax, rax
0x14005e445  jz      loc_14005E70E
0x14005e44b  xor     ecx, ecx
0x14005e44d  xorps   xmm0, xmm0
0x14005e450  movups  xmmword ptr [rax], xmm0
0x14005e453  movups  xmmword ptr [rax+10h], xmm0
0x14005e457  movups  xmmword ptr [rax+20h], xmm0
0x14005e45b  mov     [rax+30h], rcx
0x14005e45f  lea     ecx, [rdi+1]
0x14005e462  or      [rax+18h], cx
0x14005e466  lea     rcx, [r15+70h]
0x14005e46a  mov     [rax+10h], ebp
0x14005e46d  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x14005e474  mov     [rsi], rax
0x14005e477  mov     rdx, [rcx+8]
0x14005e47b  cmp     [rdx], rcx
0x14005e47e  jnz     loc_14005E703
0x14005e484  mov     r14d, [rsp+88h+arg_0]
0x14005e48c  lea     r12d, [rdi+4]
0x14005e490  mov     [rax], rcx
0x14005e493  mov     [rax+8], rdx
0x14005e497  mov     [rdx], rax
0x14005e49a  mov     [rcx+8], rax
0x14005e49e  xor     ebp, ebp
0x14005e4a0  mov     eax, [r15+50h]
0x14005e4a4  mov     rdx, [rsp+88h+arg_18]
0x14005e4ac  add     r13, rax
0x14005e4af  mov     r11, [rsp+88h+var_50]
0x14005e4b4  inc     edx
0x14005e4b6  sub     r11, rax
0x14005e4b9  mov     [rsp+88h+arg_18], rdx
0x14005e4c1  add     rsi, 18h
0x14005e4c5  jmp     loc_14005E1D1
0x14005e4ca  mov     r11d, [rax+1Ch]
0x14005e4ce  xor     edx, edx
0x14005e4d0  mov     ecx, [rsp+88h+arg_0]
0x14005e4d7  lea     eax, [rcx+7]
0x14005e4da  add     eax, r11d
0x14005e4dd  div     ecx
0x14005e4df  mov     ecx, eax
0x14005e4e1  movzx   eax, r12w
0x14005e4e5  cmp     ecx, eax
0x14005e4e7  jnz     loc_14005E7F1
0x14005e4ed  movzx   edx, word ptr [rdi+18h]
0x14005e4f1  test    bl, dl
0x14005e4f3  jnz     loc_14005E7BC
0x14005e4f9  test    dl, 5
0x14005e4fc  jnz     loc_14005E5D4
0x14005e502  mov     eax, [rdi+20h]
0x14005e505  or      ebp, 0FFFFFFFFh
0x14005e508  mov     r10, [r15+88h]
0x14005e50f  lea     rcx, [rax+rax*2]
0x14005e513  lea     r9, [r10+rcx*8]
0x14005e517  cmp     [r9+8], ebp
0x14005e51b  jz      short loc_14005E530
0x14005e51d  mov     eax, [r9+8]
0x14005e521  lea     rcx, [rax+rax*2]
0x14005e525  lea     r9, [r10+rcx*8]
0x14005e529  cmp     [r10+rcx*8+8], ebp
0x14005e52e  jnz     short loc_14005E51D
0x14005e530  mov     r10d, [r9+10h]
0x14005e534  add     r10d, [r9+0Ch]
0x14005e538  cmp     r10d, r8d
0x14005e53b  ja      loc_14005E787
0x14005e541  jnb     short loc_14005E56D
0x14005e543  mov     rcx, [rdi+30h]; P
0x14005e547  or      dx, 1
0x14005e54b  mov     [rdi+20h], ebp
0x14005e54e  xor     ebp, ebp
0x14005e550  mov     [rdi+18h], dx
0x14005e554  test    rcx, rcx
0x14005e557  jz      short loc_14005E5D6
0x14005e559  xor     edx, edx; Tag
0x14005e55b  call    cs:__imp_ExFreePoolWithTag
0x14005e562  nop     dword ptr [rax+rax+00h]
0x14005e567  mov     [rdi+30h], rbp
0x14005e56b  jmp     short loc_14005E5D6
0x14005e56d  cmp     r8d, r11d
0x14005e570  jnb     loc_14005E752
0x14005e576  mov     [rsi], rdi
0x14005e579  lea     eax, [r8+r14]
0x14005e57d  mov     ecx, [rdi+1Ch]
0x14005e580  cmp     eax, ecx
0x14005e582  jb      short loc_14005E58E
0x14005e584  sub     ecx, r8d
0x14005e587  mov     [rsi+10h], ecx
0x14005e58a  or      [rdi+18h], bx
0x14005e58e  mov     rax, [rsp+88h+arg_18]
0x14005e596  lea     rdx, [rsp+88h+var_58]; unsigned __int8 **
0x14005e59b  mov     [r9+8], eax
  ... truncated ...
```
