# RaUnitFlushQueueSrb

- ea: `0x1400bf1c8`
- end: `0x1400bf981`
- name: `RaUnitFlushQueueSrb`
- size: `1977`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140015200`
- `0x140017e80`

## callees

- `0x1400121e4`
- `0x140065b70`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400bf1c8`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400bf383`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400bf6a0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400bf383`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400bf6a0`
- `ntoskrnl!KeSetEvent` at `0x1400bf301`
- `ntoskrnl!KeSetEvent` at `0x1400bf301`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf34c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf34c`
- `ntoskrnl!IofCompleteRequest` at `0x1400bf633`
- `ntoskrnl!IofCompleteRequest` at `0x1400bf94b`
- `ntoskrnl!IofCompleteRequest` at `0x1400bf633`
- `ntoskrnl!IofCompleteRequest` at `0x1400bf94b`

## pseudocode

```c
__int64 __fastcall RaUnitFlushQueueSrb(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rsi
  __int64 **v5; // rcx
  __int64 ***v6; // rax
  __int64 v7; // rax
  char v8; // r13
  __int64 *v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // r14
  __int64 v12; // rdi
  unsigned __int64 v13; // r8
  signed __int32 v14; // eax
  signed __int32 v15; // ett
  _QWORD *v16; // rcx
  bool v17; // zf
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  int *v20; // rax
  int v21; // ecx
  __int64 *v22; // rdx
  _BYTE *v23; // rdx
  unsigned int v24; // r15d
  unsigned __int8 v25; // r11
  char *v26; // rdi
  _BYTE *v27; // r9
  __int64 v28; // rsi
  char v29; // r12
  unsigned __int64 v30; // r10
  __int64 v31; // r8
  int v32; // ecx
  char v33; // si
  char v34; // cl
  char v35; // di
  char v36; // r8
  char v37; // r10
  _BYTE *v38; // rax
  unsigned int v39; // eax
  char v40; // al
  unsigned __int64 v41; // rcx
  __int64 v42; // rdx
  int *v43; // rax
  int v44; // ecx
  __int64 *v45; // rdx
  __int64 v46; // rdx
  unsigned int v47; // r15d
  unsigned __int8 v48; // r10
  char *v49; // r11
  char v50; // di
  _BYTE *v51; // r8
  __int64 v52; // r14
  char v53; // r12
  unsigned __int64 v54; // rsi
  __int64 v55; // r9
  int v56; // ecx
  char v57; // cl
  char v58; // si
  char v59; // r11
  char v60; // r9
  _BYTE *v61; // rax
  char *v62; // r9
  unsigned int v63; // eax
  char v65; // [rsp+60h] [rbp-19h]
  __int64 *v66; // [rsp+68h] [rbp-11h] BYREF
  __int64 **v67; // [rsp+70h] [rbp-9h]
  __int64 v68; // [rsp+78h] [rbp-1h]
  __int128 v69; // [rsp+88h] [rbp+Fh] BYREF

  v68 = a1;
  v67 = &v66;
  v2 = a1 + 704;
  v66 = (__int64 *)&v66;
  v4 = a1;
  while ( 1 )
  {
    v7 = RaidRemoveIoQueue(v2);
    if ( !v7 )
      break;
    v5 = v67;
    if ( *v67 != (__int64 *)&v66 )
LABEL_87:
      __fastfail(3u);
    v6 = (__int64 ***)(v7 + 168);
    *v6 = &v66;
    v6[1] = v5;
    *v5 = (__int64 *)v6;
    v67 = (__int64 **)v6;
  }
  *(_BYTE *)(v4 + 756) = 0;
  RaUnitUnlockForwardIo(v4, 3);
  v8 = 1;
  while ( 1 )
  {
    v9 = v66;
    if ( v66 == (__int64 *)&v66 )
      break;
    if ( (__int64 **)v66[1] != &v66 )
      goto LABEL_87;
    v10 = (__int64 *)*v66;
    if ( *(__int64 **)(*v66 + 8) != v66 )
      goto LABEL_87;
    v66 = (__int64 *)*v66;
    v11 = v9 - 21;
    v10[1] = (__int64)&v66;
    v12 = *(_QWORD *)(v9[2] + 8);
    *(_BYTE *)(v12 + 3) = 22;
    *(v9 - 14) = 0;
    v13 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v14 = *(_DWORD *)(v13 + *(_QWORD *)(v4 + 40));
    while ( (v14 & 1) == 0 )
    {
      v15 = v14;
      v14 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + *(_QWORD *)(v4 + 40)), v14 - 2, v14);
      if ( v15 == v14 )
        goto LABEL_15;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v4 + 520), 0, 0);
LABEL_15:
    if ( (*((_BYTE *)v11 + 142) & 0x20) != 0 )
    {
      if ( *(_BYTE *)(v12 + 2) == 40 )
      {
        v16 = *(_QWORD **)(v12 + 96);
        *(_QWORD *)(v12 + 96) = v16[2];
      }
      else
      {
        v16 = *(_QWORD **)(v12 + 48);
        *(_QWORD *)(v12 + 48) = v16[2];
        *(_QWORD *)(v12 + 56) = 0;
        *(_QWORD *)(v12 + 40) = 0;
      }
      ExFreePoolWithTag(v16, 0x54436152u);
    }
    v17 = StorEtwLoggingEnabled == 0;
    *((_BYTE *)v11 + 141) = -84;
    *((_DWORD *)v11 + 12) = -1073741823;
    if ( !v17 )
    {
      v69 = 0;
      IoGetActivityIdIrp(v11, &v69);
      v19 = v11[23];
      switch ( *(_BYTE *)v19 )
      {
        case 0xE:
          if ( (byte_140177432 & 8) != 0 )
          {
            v22 = EventNonReadWriteRequestComplete;
LABEL_33:
            McTemplateK0pd_EtwWriteTransfer(v18, v22, &v69, v11, *((_DWORD *)v11 + 12));
          }
          break;
        case 0xF:
          if ( byte_140177431 >= 0 )
            break;
          v23 = *(_BYTE **)(v19 + 8);
          if ( v23[2] != 40 )
          {
            v34 = v23[72];
            v27 = (_BYTE *)*((_QWORD *)v23 + 4);
            v25 = v23[11];
            v33 = v23[4];
            if ( v23[2] )
              goto LABEL_83;
LABEL_63:
            LOBYTE(v18) = v34 - 8;
            if ( (v18 & 0x5D) != 0 )
              goto LABEL_83;
            v35 = v23[3];
            if ( v35 == 1 || !v27 || !v25 )
              goto LABEL_81;
            v36 = 0;
            v37 = 0;
            LOBYTE(v23) = 0;
            v18 = (unsigned __int64)&v27[v25];
            v38 = v27 + 8;
            if ( (unsigned __int8)((*v27 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v38 <= v18 )
              {
                v37 = v27[2];
                v36 = v27[1] & 0xF;
                LOBYTE(v23) = v27[3];
                goto LABEL_78;
              }
            }
            else if ( (unsigned __int64)v38 <= v18 )
            {
              v23 = v27 + 13;
              v36 = v27[2] & 0xF;
              v39 = v25;
              if ( (unsigned int)(unsigned __int8)v27[7] + 8 <= v25 )
                v39 = (unsigned __int8)v27[7] + 8;
              v18 = (unsigned __int64)&v27[v39];
              if ( (unsigned __int64)v23 <= v18 )
                v37 = v27[12];
              if ( (unsigned __int64)(v27 + 14) > v18 )
                LOBYTE(v23) = 0;
              else
                LOBYTE(v23) = *v23;
LABEL_78:
              v40 = 1;
LABEL_80:
              if ( !v40 )
              {
LABEL_81:
                v36 = 0;
                v37 = 0;
                LOBYTE(v23) = 0;
              }
              McTemplateK0pduuuuup_EtwWriteTransfer(
                v18,
                (_DWORD)v23,
                (unsigned int)&v69,
                (_DWORD)v11,
                *((_DWORD *)v11 + 12),
                v35,
                v33,
                v36,
                v37,
                (char)v23,
                (char)v11);
LABEL_83:
              v4 = v68;
              break;
            }
            v40 = 0;
            goto LABEL_80;
          }
          if ( !*((_DWORD *)v23 + 5) )
          {
            v24 = *((_DWORD *)v23 + 14);
            if ( v24 )
            {
              v25 = 0;
              v26 = 0;
              v65 = 0;
              v27 = 0;
              v28 = 0;
              v29 = 0;
              do
              {
                v18 = *(unsigned int *)&v23[4 * v28 + 120];
                if ( (unsigned int)v18 >= 0x80 )
                {
                  v30 = *((unsigned int *)v23 + 4);
                  if ( (unsigned int)v18 < (unsigned int)v30 )
                  {
                    v31 = (unsigned int)v18;
                    v32 = *(_DWORD *)&v23[v18] - 64;
                    if ( v32 )
                    {
                      LODWORD(v18) = v32 - 1;
                      if ( (_DWORD)v18 )
                      {
                        if ( (_DWORD)v18 == 1 )
                        {
                          LODWORD(v18) = v31 + 40;
                          if ( v31 + 40 <= v30 )
                          {
                            if ( *(_DWORD *)&v23[v31 + 12] )
                              v26 = &v23[v31 + 32];
                            v27 = *(_BYTE **)&v23[v31 + 24];
LABEL_48:
                            v33 = v23[v31 + 8];
                            v25 = v23[v31 + 9];
                            goto LABEL_57;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v18) = v31 + 56;
                        if ( v31 + 56 <= v30 )
                        {
                          v29 = 1;
                          if ( v23[v31 + 10] )
                            v26 = &v23[v31 + 24];
                          v27 = *(_BYTE **)&v23[v31 + 16];
                          v25 = v23[v31 + 9];
                          v65 = v23[v31 + 8];
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v18) = v31 + 40;
                      if ( v31 + 40 <= v30 )
                      {
                        if ( v23[v31 + 10] )
                          v26 = &v23[v31 + 24];
                        v27 = *(_BYTE **)&v23[v31 + 16];
                        goto LABEL_48;
                      }
                    }
                    if ( v29 )
                      break;
                  }
                }
                v28 = (unsigned int)(v28 + 1);
              }
              while ( (unsigned int)v28 < v24 );
              v33 = v65;
LABEL_57:
              if ( v26 )
              {
                v34 = *v26;
                goto LABEL_63;
              }
              goto LABEL_83;
            }
          }
          break;
        case 0x1B:
          if ( *(_BYTE *)(v19 + 1) != 7 || *(_DWORD *)(v19 + 8) )
          {
            if ( (byte_140177432 & 0x20) == 0 )
              break;
            v22 = EventPnpRequestComplete;
            goto LABEL_33;
          }
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v20 = (int *)v11[7];
            if ( v20 )
              v21 = *v20;
            else
              v21 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v21, v19, (unsigned int)&v69, (_DWORD)v11, v21, *((_DWORD *)v11 + 12));
          }
          break;
        default:
          break;
      }
    }
    IofCompleteRequest((PIRP)v11, 0);
  }
  v17 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL) + 3LL) = 1;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = 0;
  if ( v17 )
    goto LABEL_152;
  v69 = 0;
  IoGetActivityIdIrp(a2, &v69);
  v42 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v42 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_152;
    v45 = EventNonReadWriteRequestComplete;
    goto LABEL_151;
  }
  if ( *(_BYTE *)v42 != 15 )
  {
    if ( *(_BYTE *)v42 != 27 )
      goto LABEL_152;
    if ( *(_BYTE *)(v42 + 1) == 7 && !*(_DWORD *)(v42 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v43 = *(int **)(a2 + 56);
        if ( v43 )
          v44 = *v43;
        else
          v44 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v44, v42, (unsigned int)&v69, a2, v44, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_152;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_152;
    v45 = EventPnpRequestComplete;
LABEL_151:
    McTemplateK0pd_EtwWriteTransfer(v41, v45, &v69, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_152;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_152;
  v46 = *(_QWORD *)(v42 + 8);
  if ( *(_BYTE *)(v46 + 2) != 40 )
  {
    v57 = *(_BYTE *)(v46 + 72);
    v51 = *(_BYTE **)(v46 + 32);
    v48 = *(_BYTE *)(v46 + 11);
    v50 = *(_BYTE *)(v46 + 4);
    if ( *(_BYTE *)(v46 + 2) )
      goto LABEL_152;
LABEL_130:
    LOBYTE(v41) = v57 - 8;
    if ( (v41 & 0x5D) != 0 )
      goto LABEL_152;
    v58 = *(_BYTE *)(v46 + 3);
    if ( v58 == 1 || !v51 || !v48 )
      goto LABEL_147;
    LOBYTE(v46) = 0;
    v59 = 0;
    v60 = 0;
    v41 = (unsigned __int64)&v51[v48];
    v61 = v51 + 8;
    if ( (unsigned __int8)((*v51 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v61 <= v41 )
      {
        v59 = v51[2];
        LOBYTE(v46) = v51[1] & 0xF;
        v60 = v51[3];
        goto LABEL_146;
      }
    }
    else if ( (unsigned __int64)v61 <= v41 )
    {
      v62 = v51 + 13;
      LOBYTE(v46) = v51[2] & 0xF;
      v63 = v48;
      if ( (unsigned int)(unsigned __int8)v51[7] + 8 <= v48 )
        v63 = (unsigned __int8)v51[7] + 8;
      v41 = (unsigned __int64)&v51[v63];
      if ( (unsigned __int64)v62 <= v41 )
        v59 = v51[12];
      if ( (unsigned __int64)(v51 + 14) > v41 )
        v60 = 0;
      else
        v60 = *v62;
LABEL_146:
      if ( v8 )
      {
LABEL_148:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v41,
          v46,
          (unsigned int)&v69,
          a2,
          *(_DWORD *)(a2 + 48),
          v58,
          v50,
          v46,
          v59,
          v60,
          a2);
        goto LABEL_152;
      }
LABEL_147:
      LOBYTE(v46) = 0;
      v59 = 0;
      v60 = 0;
      goto LABEL_148;
    }
    v8 = 0;
    goto LABEL_146;
  }
  if ( *(_DWORD *)(v46 + 20) )
    goto LABEL_152;
  v47 = *(_DWORD *)(v46 + 56);
  if ( !v47 )
    goto LABEL_152;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  while ( 2 )
  {
    v41 = *(unsigned int *)(v46 + 4 * v52 + 120);
    if ( (unsigned int)v41 < 0x80 )
      goto LABEL_121;
    v54 = *(unsigned int *)(v46 + 16);
    if ( (unsigned int)v41 >= (unsigned int)v54 )
      goto LABEL_121;
    v55 = (unsigned int)v41;
    v56 = *(_DWORD *)(v46 + v41) - 64;
    if ( v56 )
    {
      LODWORD(v41) = v56 - 1;
      if ( (_DWORD)v41 )
      {
        if ( (_DWORD)v41 == 1 )
        {
          LODWORD(v41) = v55 + 40;
          if ( v55 + 40 <= v54 )
          {
            if ( *(_DWORD *)(v46 + v55 + 12) )
              v49 = (char *)(v55 + v46 + 32);
            v51 = *(_BYTE **)(v46 + v55 + 24);
            goto LABEL_126;
          }
        }
      }
      else
      {
        LODWORD(v41) = v55 + 56;
        if ( v55 + 56 <= v54 )
        {
          v53 = 1;
          if ( *(_BYTE *)(v46 + v55 + 10) )
            v49 = (char *)(v55 + v46 + 24);
          v50 = *(_BYTE *)(v46 + v55 + 8);
          v51 = *(_BYTE **)(v46 + v55 + 16);
          v48 = *(_BYTE *)(v46 + v55 + 9);
        }
      }
LABEL_120:
      if ( v53 )
        goto LABEL_127;
LABEL_121:
      v52 = (unsigned int)(v52 + 1);
      if ( (unsigned int)v52 >= v47 )
        goto LABEL_127;
      continue;
    }
    break;
  }
  LODWORD(v41) = v55 + 40;
  if ( v55 + 40 > v54 )
    goto LABEL_120;
  if ( *(_BYTE *)(v46 + v55 + 10) )
    v49 = (char *)(v55 + v46 + 24);
  v51 = *(_BYTE **)(v46 + v55 + 16);
LABEL_126:
  v48 = *(_BYTE *)(v46 + v55 + 9);
  v50 = *(_BYTE *)(v46 + v55 + 8);
LABEL_127:
  if ( v49 )
  {
    v57 = *v49;
    goto LABEL_130;
  }
LABEL_152:
  IofCompleteRequest((PIRP)a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1400bf1c8  mov     [rsp-8+arg_10], rbx
0x1400bf1cd  push    rbp
0x1400bf1ce  push    rsi
0x1400bf1cf  push    rdi
0x1400bf1d0  push    r12
0x1400bf1d2  push    r13
0x1400bf1d4  push    r14
0x1400bf1d6  push    r15
0x1400bf1d8  lea     rbp, [rsp-27h]
0x1400bf1dd  sub     rsp, 0A0h
0x1400bf1e4  mov     rax, cs:__security_cookie
0x1400bf1eb  xor     rax, rsp
0x1400bf1ee  mov     [rbp+57h+var_38], rax
0x1400bf1f2  lea     rax, [rbp+57h+var_68]
0x1400bf1f6  mov     [rbp+57h+var_58], rcx
0x1400bf1fa  mov     [rbp+57h+var_60], rax
0x1400bf1fe  lea     rdi, [rcx+2C0h]
0x1400bf205  lea     rax, [rbp+57h+var_68]
0x1400bf209  mov     rbx, rdx
0x1400bf20c  mov     [rbp+57h+var_68], rax
0x1400bf210  mov     rsi, rcx
0x1400bf213  jmp     short loc_1400BF23E
0x1400bf215  mov     rcx, [rbp+57h+var_60]
0x1400bf219  lea     rdx, [rbp+57h+var_68]
0x1400bf21d  cmp     [rcx], rdx
0x1400bf220  jnz     loc_1400BF659
0x1400bf226  add     rax, 0A8h
0x1400bf22c  lea     rdx, [rbp+57h+var_68]
0x1400bf230  mov     [rax], rdx
0x1400bf233  mov     [rax+8], rcx
0x1400bf237  mov     [rcx], rax
0x1400bf23a  mov     [rbp+57h+var_60], rax
0x1400bf23e  mov     rcx, rdi
0x1400bf241  call    RaidRemoveIoQueue
0x1400bf246  test    rax, rax
0x1400bf249  jnz     short loc_1400BF215
0x1400bf24b  lea     edx, [rax+3]
0x1400bf24e  mov     [rsi+2F4h], al
0x1400bf254  mov     rcx, rsi
0x1400bf257  call    RaUnitUnlockForwardIo
0x1400bf25c  mov     r13d, 1
0x1400bf262  mov     rax, [rbp+57h+var_68]
0x1400bf266  lea     rcx, [rbp+57h+var_68]
0x1400bf26a  cmp     rax, rcx
0x1400bf26d  jz      loc_1400BF660
0x1400bf273  lea     rcx, [rbp+57h+var_68]
0x1400bf277  cmp     [rax+8], rcx
0x1400bf27b  jnz     loc_1400BF659
0x1400bf281  mov     rcx, [rax]
0x1400bf284  cmp     [rcx+8], rax
0x1400bf288  jnz     loc_1400BF659
0x1400bf28e  mov     [rbp+57h+var_68], rcx
0x1400bf292  lea     r14, [rax-0A8h]
0x1400bf299  lea     rdx, [rbp+57h+var_68]
0x1400bf29d  mov     [rcx+8], rdx
0x1400bf2a1  mov     rax, [r14+0B8h]
0x1400bf2a8  mov     rdi, [rax+8]
0x1400bf2ac  mov     byte ptr [rdi+3], 16h
0x1400bf2b0  mov     qword ptr [r14+38h], 0
0x1400bf2b8  mov     eax, gs:1A4h
0x1400bf2c0  mov     r8d, eax
0x1400bf2c3  mov     rax, [rsi+28h]
0x1400bf2c7  shl     r8, 6
0x1400bf2cb  mov     eax, [r8+rax]
0x1400bf2cf  test    r13b, al
0x1400bf2d2  jnz     short loc_1400BF2E5
0x1400bf2d4  mov     rcx, [rsi+28h]
0x1400bf2d8  lea     edx, [rax-2]
0x1400bf2db  lock cmpxchg [r8+rcx], edx
0x1400bf2e1  jnz     short loc_1400BF2CF
0x1400bf2e3  jmp     short loc_1400BF30D
0x1400bf2e5  or      eax, 0FFFFFFFFh
0x1400bf2e8  lock xadd [rsi+408h], eax
0x1400bf2f0  cmp     eax, r13d
0x1400bf2f3  jnz     short loc_1400BF30D
0x1400bf2f5  lea     rcx, [rsi+208h]; Event
0x1400bf2fc  xor     r8d, r8d; Wait
0x1400bf2ff  xor     edx, edx; Increment
0x1400bf301  call    cs:__imp_KeSetEvent
0x1400bf308  nop     dword ptr [rax+rax+00h]
0x1400bf30d  test    byte ptr [r14+8Eh], 20h
0x1400bf315  jz      short loc_1400BF358
0x1400bf317  cmp     byte ptr [rdi+2], 28h ; '('
0x1400bf31b  jnz     short loc_1400BF32B
0x1400bf31d  mov     rcx, [rdi+60h]
0x1400bf321  mov     rax, [rcx+10h]
0x1400bf325  mov     [rdi+60h], rax
0x1400bf329  jmp     short loc_1400BF347
0x1400bf32b  mov     rcx, [rdi+30h]; P
0x1400bf32f  mov     rax, [rcx+10h]
0x1400bf333  mov     [rdi+30h], rax
0x1400bf337  mov     qword ptr [rdi+38h], 0
0x1400bf33f  mov     qword ptr [rdi+28h], 0
0x1400bf347  mov     edx, 54436152h; Tag
0x1400bf34c  call    cs:__imp_ExFreePoolWithTag
0x1400bf353  nop     dword ptr [rax+rax+00h]
0x1400bf358  cmp     cs:StorEtwLoggingEnabled, 0
0x1400bf35f  mov     byte ptr [r14+8Dh], 0ACh
0x1400bf367  mov     dword ptr [r14+30h], 0C0000001h
0x1400bf36f  jz      loc_1400BF62E
0x1400bf375  xorps   xmm0, xmm0
0x1400bf378  lea     rdx, [rbp+57h+var_48]
0x1400bf37c  mov     rcx, r14
0x1400bf37f  movups  [rbp+57h+var_48], xmm0
0x1400bf383  call    cs:__imp_IoGetActivityIdIrp
0x1400bf38a  nop     dword ptr [rax+rax+00h]
0x1400bf38f  mov     rdx, [r14+0B8h]
0x1400bf396  movzx   eax, byte ptr [rdx]
0x1400bf399  sub     eax, 0Eh
0x1400bf39c  jz      loc_1400BF644
0x1400bf3a2  sub     eax, r13d
0x1400bf3a5  jz      short loc_1400BF422
0x1400bf3a7  cmp     eax, 0Ch
0x1400bf3aa  jnz     loc_1400BF62E
0x1400bf3b0  cmp     byte ptr [rdx+1], 7
0x1400bf3b4  jnz     short loc_1400BF3F5
0x1400bf3b6  cmp     dword ptr [rdx+8], 0
0x1400bf3ba  jnz     short loc_1400BF3F5
0x1400bf3bc  test    cs:byte_140177432, 40h
0x1400bf3c3  jz      loc_1400BF62E
0x1400bf3c9  mov     rax, [r14+38h]
0x1400bf3cd  test    rax, rax
0x1400bf3d0  jz      short loc_1400BF3D6
0x1400bf3d2  mov     ecx, [rax]
0x1400bf3d4  jmp     short loc_1400BF3D8
0x1400bf3d6  xor     ecx, ecx
0x1400bf3d8  mov     eax, [r14+30h]
0x1400bf3dc  lea     r8, [rbp+57h+var_48]
0x1400bf3e0  mov     [rsp+0D0h+var_A8], eax
0x1400bf3e4  mov     r9, r14
0x1400bf3e7  mov     [rsp+0D0h+var_B0], ecx
0x1400bf3eb  call    McTemplateK0pqd_EtwWriteTransfer
0x1400bf3f0  jmp     loc_1400BF62E
0x1400bf3f5  test    cs:byte_140177432, 20h
0x1400bf3fc  jz      loc_1400BF62E
0x1400bf402  lea     rdx, EventPnpRequestComplete
0x1400bf409  mov     eax, [r14+30h]
0x1400bf40d  lea     r8, [rbp+57h+var_48]
0x1400bf411  mov     r9, r14
0x1400bf414  mov     [rsp+0D0h+var_B0], eax
0x1400bf418  call    McTemplateK0pd_EtwWriteTransfer
0x1400bf41d  jmp     loc_1400BF62E
0x1400bf422  cmp     cs:byte_140177431, 0
0x1400bf429  jge     loc_1400BF62E
0x1400bf42f  mov     rdx, [rdx+8]
0x1400bf433  movzx   eax, byte ptr [rdx+2]
0x1400bf437  cmp     al, 28h ; '('
0x1400bf439  jnz     loc_1400BF52F
0x1400bf43f  cmp     dword ptr [rdx+14h], 0
0x1400bf443  jnz     loc_1400BF62E
0x1400bf449  mov     r15d, [rdx+38h]
0x1400bf44d  test    r15d, r15d
0x1400bf450  jz      loc_1400BF62E
0x1400bf456  xor     al, al
0x1400bf458  xor     r11b, r11b
0x1400bf45b  xor     edi, edi
0x1400bf45d  mov     [rbp+57h+var_70], al
0x1400bf460  xor     r9d, r9d
0x1400bf463  xor     esi, esi
0x1400bf465  xor     r12b, r12b
0x1400bf468  mov     ecx, [rdx+rsi*4+78h]
0x1400bf46c  cmp     ecx, 80h
0x1400bf472  jb      loc_1400BF4FC
0x1400bf478  mov     r10d, [rdx+10h]
0x1400bf47c  cmp     ecx, r10d
0x1400bf47f  jnb     short loc_1400BF4FC
0x1400bf481  mov     r8d, ecx
0x1400bf484  mov     ecx, [rcx+rdx]
0x1400bf487  sub     ecx, 40h ; '@'
0x1400bf48a  jz      short loc_1400BF4EE
0x1400bf48c  sub     ecx, r13d
0x1400bf48f  jz      short loc_1400BF4BF
0x1400bf491  cmp     ecx, r13d
0x1400bf494  jnz     short loc_1400BF4F7
0x1400bf496  lea     rcx, [r8+28h]
0x1400bf49a  cmp     rcx, r10
0x1400bf49d  ja      short loc_1400BF4F7
0x1400bf49f  cmp     dword ptr [r8+rdx+0Ch], 0
0x1400bf4a5  jbe     short loc_1400BF4AE
0x1400bf4a7  lea     rdi, [rdx+20h]
0x1400bf4ab  add     rdi, r8
0x1400bf4ae  mov     r9, [r8+rdx+18h]
0x1400bf4b3  mov     sil, [r8+rdx+8]
0x1400bf4b8  mov     r11b, [r8+rdx+9]
0x1400bf4bd  jmp     short loc_1400BF50C
0x1400bf4bf  lea     rcx, [r8+38h]
0x1400bf4c3  cmp     rcx, r10
0x1400bf4c6  ja      short loc_1400BF4F7
0x1400bf4c8  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400bf4ce  mov     r12b, r13b
0x1400bf4d1  jbe     short loc_1400BF4DA
0x1400bf4d3  lea     rdi, [rdx+18h]
0x1400bf4d7  add     rdi, r8
0x1400bf4da  mov     al, [r8+rdx+8]
0x1400bf4df  mov     r9, [r8+rdx+10h]
0x1400bf4e4  mov     r11b, [r8+rdx+9]
0x1400bf4e9  mov     [rbp+57h+var_70], al
0x1400bf4ec  jmp     short loc_1400BF4F7
0x1400bf4ee  lea     rcx, [r8+28h]
0x1400bf4f2  cmp     rcx, r10
0x1400bf4f5  jbe     short loc_1400BF519
0x1400bf4f7  test    r12b, r12b
0x1400bf4fa  jnz     short loc_1400BF508
0x1400bf4fc  add     esi, r13d
0x1400bf4ff  cmp     esi, r15d
0x1400bf502  jb      loc_1400BF468
0x1400bf508  mov     sil, [rbp+57h+var_70]
0x1400bf50c  test    rdi, rdi
0x1400bf50f  jz      loc_1400BF62A
0x1400bf515  mov     cl, [rdi]
0x1400bf517  jmp     short loc_1400BF546
0x1400bf519  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400bf51f  jbe     short loc_1400BF528
0x1400bf521  lea     rdi, [rdx+18h]
0x1400bf525  add     rdi, r8
0x1400bf528  mov     r9, [r8+rdx+10h]
0x1400bf52d  jmp     short loc_1400BF4B3
0x1400bf52f  mov     cl, [rdx+48h]
0x1400bf532  mov     r9, [rdx+20h]
0x1400bf536  mov     r11b, [rdx+0Bh]
0x1400bf53a  mov     sil, [rdx+4]
0x1400bf53e  test    eax, eax
0x1400bf540  jnz     loc_1400BF62A
0x1400bf546  sub     cl, 8
0x1400bf549  test    cl, 5Dh
0x1400bf54c  jnz     loc_1400BF62A
0x1400bf552  mov     dil, [rdx+3]
0x1400bf556  cmp     dil, r13b
0x1400bf559  jz      loc_1400BF5F1
0x1400bf55f  test    r9, r9
0x1400bf562  jz      loc_1400BF5F1
0x1400bf568  test    r11b, r11b
0x1400bf56b  jz      loc_1400BF5F1
0x1400bf571  mov     al, [r9]
0x1400bf574  xor     r8b, r8b
0x1400bf577  and     al, 7Fh
0x1400bf579  movzx   ecx, r11b
0x1400bf57d  sub     al, 72h ; 'r'
0x1400bf57f  xor     r10b, r10b
0x1400bf582  xor     dl, dl
0x1400bf584  add     rcx, r9
0x1400bf587  cmp     al, r13b
0x1400bf58a  lea     rax, [r9+8]
0x1400bf58e  jbe     short loc_1400BF5D1
0x1400bf590  cmp     rax, rcx
0x1400bf593  ja      short loc_1400BF5EB
0x1400bf595  movzx   ecx, byte ptr [r9+7]
0x1400bf59a  lea     rdx, [r9+0Dh]
0x1400bf59e  mov     r8b, [r9+2]
0x1400bf5a2  add     ecx, 8
0x1400bf5a5  and     r8b, 0Fh
0x1400bf5a9  movzx   eax, r11b
0x1400bf5ad  cmp     ecx, eax
0x1400bf5af  cmovbe  eax, ecx
0x1400bf5b2  mov     ecx, eax
0x1400bf5b4  add     rcx, r9
0x1400bf5b7  cmp     rdx, rcx
0x1400bf5ba  ja      short loc_1400BF5C0
0x1400bf5bc  mov     r10b, [r9+0Ch]
0x1400bf5c0  lea     rax, [r9+0Eh]
0x1400bf5c4  cmp     rax, rcx
0x1400bf5c7  ja      short loc_1400BF5CD
0x1400bf5c9  mov     dl, [rdx]
0x1400bf5cb  jmp     short loc_1400BF5E6
0x1400bf5cd  xor     dl, dl
0x1400bf5cf  jmp     short loc_1400BF5E6
0x1400bf5d1  cmp     rax, rcx
0x1400bf5d4  ja      short loc_1400BF5EB
0x1400bf5d6  mov     r8b, [r9+1]
0x1400bf5da  mov     r10b, [r9+2]
0x1400bf5de  and     r8b, 0Fh
0x1400bf5e2  mov     dl, [r9+3]
0x1400bf5e6  mov     al, r13b
0x1400bf5e9  jmp     short loc_1400BF5ED
0x1400bf5eb  xor     al, al
0x1400bf5ed  test    al, al
0x1400bf5ef  jnz     short loc_1400BF5F9
0x1400bf5f1  xor     r8b, r8b
0x1400bf5f4  xor     r10b, r10b
0x1400bf5f7  xor     dl, dl
0x1400bf5f9  mov     eax, [r14+30h]
0x1400bf5fd  mov     r9, r14
0x1400bf600  mov     [rsp+0D0h+var_80], r14
0x1400bf605  mov     [rsp+0D0h+var_88], dl
0x1400bf609  mov     [rsp+0D0h+var_90], r10b
0x1400bf60e  mov     [rsp+0D0h+var_98], r8b
0x1400bf613  lea     r8, [rbp+57h+var_48]
0x1400bf617  mov     [rsp+0D0h+var_A0], sil
0x1400bf61c  mov     byte ptr [rsp+0D0h+var_A8], dil
0x1400bf621  mov     [rsp+0D0h+var_B0], eax
0x1400bf625  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1400bf62a  mov     rsi, [rbp+57h+var_58]
0x1400bf62e  xor     edx, edx; PriorityBoost
0x1400bf630  mov     rcx, r14; Irp
0x1400bf633  call    cs:__imp_IofCompleteRequest
0x1400bf63a  nop     dword ptr [rax+rax+00h]
0x1400bf63f  jmp     loc_1400BF262
0x1400bf644  test    cs:byte_140177432, 8
0x1400bf64b  jz      short loc_1400BF62E
0x1400bf64d  lea     rdx, EventNonReadWriteRequestComplete
  ... truncated ...
```
