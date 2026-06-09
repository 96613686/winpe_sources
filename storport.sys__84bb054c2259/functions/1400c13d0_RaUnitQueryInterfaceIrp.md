# RaUnitQueryInterfaceIrp

- ea: `0x1400c13d0`
- end: `0x1400c1a2c`
- name: `RaUnitQueryInterfaceIrp`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004018c`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400c13d0`
- `0x14014b400`
- `0x140191a4c`
- `0x1401b81a8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c1494`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c16a2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c17ca`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c1494`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c16a2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400c17ca`
- `ntoskrnl!IofCompleteRequest` at `0x1400c19fc`
- `ntoskrnl!IofCompleteRequest` at `0x1400c19fc`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1420`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1448`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1420`
- `ntoskrnl!RtlCompareMemory` at `0x1400c1448`

## pseudocode

```c
__int64 __fastcall RaUnitQueryInterfaceIrp(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  GUID *v5; // rcx
  GUID *v6; // rcx
  __int64 v7; // rcx
  int v9; // ebx
  bool v10; // zf
  unsigned __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax
  int *v14; // rax
  __int64 *v15; // rdx
  __int64 v16; // rdx
  char v17; // si
  int v18; // eax
  unsigned int v19; // r12d
  unsigned __int8 v20; // r10
  char *v21; // r11
  char v22; // r13
  _BYTE *v23; // r9
  unsigned int v24; // r15d
  unsigned __int64 v25; // r14
  __int64 v26; // r8
  int v27; // ecx
  char v28; // r8
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // r8
  unsigned int InterfacePdoInfo; // eax
  unsigned int v33; // r12d
  unsigned int v34; // r15d
  unsigned __int64 v35; // r14
  int v36; // ecx
  unsigned int v37; // r12d
  unsigned int v38; // r15d
  unsigned __int64 v39; // r14
  int v40; // ecx
  char v41; // cl
  char v42; // r14
  char v43; // r11
  _BYTE *v44; // rax
  char *v45; // r8
  unsigned int v46; // eax
  char v47; // [rsp+60h] [rbp-9h]
  char v48; // [rsp+60h] [rbp-9h]
  char v49; // [rsp+60h] [rbp-9h]
  unsigned int v50; // [rsp+64h] [rbp-5h]
  __int128 v51; // [rsp+68h] [rbp-1h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v5 = *(GUID **)(v2 + 8);
  if ( v5 == &GUID_STORAGE_QUERY_PDO_INFO || RtlCompareMemory(v5, &GUID_STORAGE_QUERY_PDO_INFO, 0x10u) == 16 )
  {
    v29 = *(_QWORD *)(a1 + 24);
    LOBYTE(v9) = 0;
    v17 = 1;
    if ( v29 && (v30 = *(_DWORD *)(a1 + 56)) != 0 && (unsigned int)(v30 - 5) > 1 )
    {
      if ( *(_DWORD *)v29 == 1094997074 || *(_DWORD *)v29 == 1314275652 )
        v31 = *(_QWORD *)(v29 + 8);
      else
        LODWORD(v31) = 0;
      InterfacePdoInfo = PortQueryInterfacePdoInfo(
                           (unsigned int)*(_QWORD *)(a1 + 112) + 16,
                           a2,
                           v31,
                           (unsigned int)*(_QWORD *)(a1 + 112) + 8,
                           *(_QWORD *)(a1 + 112) + 16LL,
                           **(_BYTE **)(a1 + 112) & 0x1F,
                           *(_DWORD *)(a1 + 3432));
      v10 = StorEtwLoggingEnabled == 0;
      v50 = InterfacePdoInfo;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = InterfacePdoInfo;
      if ( v10 )
        goto LABEL_122;
      v51 = 0;
      IoGetActivityIdIrp(a2, &v51);
      v12 = *(unsigned __int8 **)(a2 + 184);
      if ( *v12 != 14 )
      {
        v13 = *v12 - 15;
        if ( *v12 != 15 )
          goto LABEL_9;
        if ( byte_140177431 >= 0 )
          goto LABEL_122;
        v16 = *((_QWORD *)v12 + 1);
        v18 = *(unsigned __int8 *)(v16 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( !*(_DWORD *)(v16 + 20) )
          {
            v33 = *(_DWORD *)(v16 + 56);
            if ( v33 )
            {
              v20 = 0;
              v48 = 0;
              v21 = 0;
              v22 = 0;
              v23 = 0;
              v34 = 0;
              while ( 1 )
              {
                v11 = *(unsigned int *)(v16 + 4LL * v34 + 120);
                if ( (unsigned int)v11 >= 0x80 )
                {
                  v35 = *(unsigned int *)(v16 + 16);
                  if ( (unsigned int)v11 < (unsigned int)v35 )
                  {
                    v26 = (unsigned int)v11;
                    v36 = *(_DWORD *)(v11 + v16) - 64;
                    if ( v36 )
                    {
                      LODWORD(v11) = v36 - 1;
                      if ( (_DWORD)v11 )
                      {
                        if ( (_DWORD)v11 == 1 )
                        {
                          LODWORD(v11) = v26 + 40;
                          if ( v26 + 40 <= v35 )
                            goto LABEL_29;
                        }
                      }
                      else
                      {
                        LODWORD(v11) = v26 + 56;
                        if ( v26 + 56 <= v35 )
                        {
                          v48 = 1;
                          if ( *(_BYTE *)(v26 + v16 + 10) )
                            v21 = (char *)(v26 + v16 + 24);
                          v22 = *(_BYTE *)(v26 + v16 + 8);
                          v23 = *(_BYTE **)(v26 + v16 + 16);
                          v20 = *(_BYTE *)(v26 + v16 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v11) = v26 + 40;
                      if ( v26 + 40 <= v35 )
                        goto LABEL_94;
                    }
                    if ( v48 )
                      goto LABEL_98;
                  }
                }
                if ( ++v34 >= v33 )
                  goto LABEL_98;
              }
            }
          }
          goto LABEL_122;
        }
        goto LABEL_100;
      }
    }
    else
    {
      v10 = StorEtwLoggingEnabled == 0;
      v50 = -1073741810;
      *(_DWORD *)(a2 + 48) = -1073741810;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v10 )
        goto LABEL_122;
      v51 = 0;
      IoGetActivityIdIrp(a2, &v51);
      v12 = *(unsigned __int8 **)(a2 + 184);
      if ( *v12 != 14 )
      {
        v13 = *v12 - 15;
        if ( *v12 != 15 )
          goto LABEL_9;
        if ( byte_140177431 >= 0 )
          goto LABEL_122;
        v16 = *((_QWORD *)v12 + 1);
        v18 = *(unsigned __int8 *)(v16 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( *(_DWORD *)(v16 + 20) )
            goto LABEL_122;
          v37 = *(_DWORD *)(v16 + 56);
          if ( !v37 )
            goto LABEL_122;
          v20 = 0;
          v49 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v38 = 0;
          while ( 1 )
          {
            v11 = *(unsigned int *)(v16 + 4LL * v38 + 120);
            if ( (unsigned int)v11 >= 0x80 )
            {
              v39 = *(unsigned int *)(v16 + 16);
              if ( (unsigned int)v11 < (unsigned int)v39 )
              {
                v26 = (unsigned int)v11;
                v40 = *(_DWORD *)(v11 + v16) - 64;
                if ( v40 )
                {
                  LODWORD(v11) = v40 - 1;
                  if ( (_DWORD)v11 )
                  {
                    if ( (_DWORD)v11 == 1 )
                    {
                      LODWORD(v11) = v26 + 40;
                      if ( v26 + 40 <= v39 )
                      {
LABEL_29:
                        if ( *(_DWORD *)(v26 + v16 + 12) )
                          v21 = (char *)(v26 + v16 + 32);
                        v23 = *(_BYTE **)(v26 + v16 + 24);
                        goto LABEL_97;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v11) = v26 + 56;
                    if ( v26 + 56 <= v39 )
                    {
                      v49 = 1;
                      if ( *(_BYTE *)(v26 + v16 + 10) )
                        v21 = (char *)(v26 + v16 + 24);
                      v22 = *(_BYTE *)(v26 + v16 + 8);
                      v23 = *(_BYTE **)(v26 + v16 + 16);
                      v20 = *(_BYTE *)(v26 + v16 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v11) = v26 + 40;
                  if ( v26 + 40 <= v39 )
                  {
LABEL_94:
                    if ( *(_BYTE *)(v26 + v16 + 10) )
                      v21 = (char *)(v26 + v16 + 24);
                    v23 = *(_BYTE **)(v26 + v16 + 16);
LABEL_97:
                    v20 = *(_BYTE *)(v26 + v16 + 9);
                    v22 = *(_BYTE *)(v26 + v16 + 8);
LABEL_98:
                    if ( v21 )
                    {
                      v41 = *v21;
                      goto LABEL_101;
                    }
                    goto LABEL_122;
                  }
                }
                if ( v49 )
                  goto LABEL_98;
              }
            }
            if ( ++v38 >= v37 )
              goto LABEL_98;
          }
        }
        goto LABEL_100;
      }
    }
LABEL_119:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_122;
    v15 = EventNonReadWriteRequestComplete;
    goto LABEL_121;
  }
  v6 = *(GUID **)(v2 + 8);
  if ( v6 != &GUID_THERMAL_COOLING_INTERFACE && RtlCompareMemory(v6, &GUID_THERMAL_COOLING_INTERFACE, 0x10u) != 16 )
    return RaUnitIgnorePnpIrp(v7, a2);
  *(_BYTE *)(a2 + 141) = -84;
  LOBYTE(v9) = 0;
  v50 = -1073741637;
  v10 = StorEtwLoggingEnabled == 0;
  *(_DWORD *)(a2 + 48) = -1073741637;
  if ( v10 )
    goto LABEL_122;
  v51 = 0;
  IoGetActivityIdIrp(a2, &v51);
  v12 = *(unsigned __int8 **)(a2 + 184);
  if ( *v12 == 14 )
    goto LABEL_119;
  v13 = *v12 - 15;
  if ( *v12 != 15 )
  {
LABEL_9:
    if ( v13 != 12 )
      goto LABEL_122;
    if ( v12[1] == 7 && !*((_DWORD *)v12 + 2) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v14 = *(int **)(a2 + 56);
        if ( v14 )
          v9 = *v14;
        McTemplateK0pqd_EtwWriteTransfer(v11, (_DWORD)v12, (unsigned int)&v51, a2, v9, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_122;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_122;
    v15 = EventPnpRequestComplete;
LABEL_121:
    McTemplateK0pd_EtwWriteTransfer(v11, v15, &v51, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_122;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_122;
  v16 = *((_QWORD *)v12 + 1);
  v17 = 1;
  v18 = *(unsigned __int8 *)(v16 + 2);
  if ( (_BYTE)v18 == 40 )
  {
    if ( !*(_DWORD *)(v16 + 20) )
    {
      v19 = *(_DWORD *)(v16 + 56);
      if ( v19 )
      {
        v20 = 0;
        v47 = 0;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v24 = 0;
        while ( 1 )
        {
          v11 = *(unsigned int *)(v16 + 4LL * v24 + 120);
          if ( (unsigned int)v11 >= 0x80 )
          {
            v25 = *(unsigned int *)(v16 + 16);
            if ( (unsigned int)v11 < (unsigned int)v25 )
            {
              v26 = (unsigned int)v11;
              v27 = *(_DWORD *)(v11 + v16) - 64;
              if ( v27 )
              {
                LODWORD(v11) = v27 - 1;
                if ( (_DWORD)v11 )
                {
                  if ( (_DWORD)v11 == 1 )
                  {
                    LODWORD(v11) = v26 + 40;
                    if ( v26 + 40 <= v25 )
                      goto LABEL_29;
                  }
                }
                else
                {
                  LODWORD(v11) = v26 + 56;
                  if ( v26 + 56 <= v25 )
                  {
                    v47 = 1;
                    if ( *(_BYTE *)(v26 + v16 + 10) )
                      v21 = (char *)(v26 + v16 + 24);
                    v22 = *(_BYTE *)(v26 + v16 + 8);
                    v23 = *(_BYTE **)(v26 + v16 + 16);
                    v20 = *(_BYTE *)(v26 + v16 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v11) = v26 + 40;
                if ( v26 + 40 <= v25 )
                  goto LABEL_94;
              }
              if ( v47 )
                goto LABEL_98;
            }
          }
          if ( ++v24 >= v19 )
            goto LABEL_98;
        }
      }
    }
    goto LABEL_122;
  }
LABEL_100:
  v41 = *(_BYTE *)(v16 + 72);
  v23 = *(_BYTE **)(v16 + 32);
  v20 = *(_BYTE *)(v16 + 11);
  v22 = *(_BYTE *)(v16 + 4);
  if ( v18 )
    goto LABEL_122;
LABEL_101:
  LOBYTE(v11) = v41 - 8;
  if ( (v11 & 0x5D) == 0 )
  {
    v42 = *(_BYTE *)(v16 + 3);
    if ( v42 == 1 || !v23 || !v20 )
      goto LABEL_117;
    LOBYTE(v16) = 0;
    v11 = (unsigned __int64)&v23[v20];
    v43 = 0;
    v44 = v23 + 8;
    v28 = 0;
    if ( (unsigned __int8)((*v23 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v44 <= v11 )
      {
        v43 = v23[2];
        LOBYTE(v16) = v23[1] & 0xF;
        v28 = v23[3];
        goto LABEL_116;
      }
    }
    else if ( (unsigned __int64)v44 <= v11 )
    {
      v45 = v23 + 13;
      LOBYTE(v16) = v23[2] & 0xF;
      v46 = v20;
      if ( (unsigned int)(unsigned __int8)v23[7] + 8 <= v20 )
        v46 = (unsigned __int8)v23[7] + 8;
      v11 = (unsigned __int64)&v23[v46];
      if ( (unsigned __int64)v45 <= v11 )
        v43 = v23[12];
      if ( (unsigned __int64)(v23 + 14) > v11 )
        v28 = 0;
      else
        v28 = *v45;
LABEL_116:
      if ( v17 )
      {
LABEL_118:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v11,
          v16,
          (unsigned int)&v51,
          a2,
          *(_DWORD *)(a2 + 48),
          v42,
          v22,
          v16,
          v43,
          v28,
          a2);
        goto LABEL_122;
      }
LABEL_117:
      LOBYTE(v16) = 0;
      v43 = 0;
      v28 = 0;
      goto LABEL_118;
    }
    v17 = 0;
    goto LABEL_116;
  }
LABEL_122:
  IofCompleteRequest((PIRP)a2, 0);
  return v50;
}

```

## disassembly

```asm
0x1400c13d0  push    rbp
0x1400c13d2  push    rbx
0x1400c13d3  push    rsi
0x1400c13d4  push    rdi
0x1400c13d5  push    r12
0x1400c13d7  push    r13
0x1400c13d9  push    r14
0x1400c13db  push    r15
0x1400c13dd  lea     rbp, [rsp-1Fh]
0x1400c13e2  sub     rsp, 88h
0x1400c13e9  mov     rax, cs:__security_cookie
0x1400c13f0  xor     rax, rsp
0x1400c13f3  mov     [rbp+57h+var_48], rax
0x1400c13f7  mov     rbx, [rdx+0B8h]
0x1400c13fe  mov     rdi, rdx
0x1400c1401  mov     r14, rcx
0x1400c1404  lea     rdx, GUID_STORAGE_QUERY_PDO_INFO; Source2
0x1400c140b  mov     rcx, [rbx+8]; Source1
0x1400c140f  cmp     rcx, rdx
0x1400c1412  jz      loc_1400C1609
0x1400c1418  mov     esi, 10h
0x1400c141d  mov     r8d, esi; Length
0x1400c1420  call    cs:__imp_RtlCompareMemory
0x1400c1427  nop     dword ptr [rax+rax+00h]
0x1400c142c  cmp     rax, rsi
0x1400c142f  jz      loc_1400C1609
0x1400c1435  mov     rcx, [rbx+8]; Source1
0x1400c1439  lea     rdx, GUID_THERMAL_COOLING_INTERFACE; Source2
0x1400c1440  cmp     rcx, rdx
0x1400c1443  jz      short loc_1400C1466
0x1400c1445  mov     r8d, esi; Length
0x1400c1448  call    cs:__imp_RtlCompareMemory
0x1400c144f  nop     dword ptr [rax+rax+00h]
0x1400c1454  cmp     rax, rsi
0x1400c1457  jz      short loc_1400C1466
0x1400c1459  mov     rdx, rdi
0x1400c145c  call    RaUnitIgnorePnpIrp
0x1400c1461  jmp     loc_1400C1A0B
0x1400c1466  mov     eax, 0C00000BBh
0x1400c146b  mov     byte ptr [rdi+8Dh], 0ACh
0x1400c1472  xor     ebx, ebx
0x1400c1474  mov     [rbp+57h+var_5C], eax
0x1400c1477  cmp     cs:StorEtwLoggingEnabled, bl
0x1400c147d  mov     [rdi+30h], eax
0x1400c1480  jz      loc_1400C19F7
0x1400c1486  xorps   xmm0, xmm0
0x1400c1489  lea     rdx, [rbp+57h+var_58]
0x1400c148d  mov     rcx, rdi
0x1400c1490  movups  [rbp+57h+var_58], xmm0
0x1400c1494  call    cs:__imp_IoGetActivityIdIrp
0x1400c149b  nop     dword ptr [rax+rax+00h]
0x1400c14a0  mov     rdx, [rdi+0B8h]
0x1400c14a7  movzx   eax, byte ptr [rdx]
0x1400c14aa  sub     eax, 0Eh
0x1400c14ad  jz      loc_1400C19D4
0x1400c14b3  sub     eax, 1
0x1400c14b6  jz      short loc_1400C1519
0x1400c14b8  cmp     eax, 0Ch
0x1400c14bb  jnz     loc_1400C19F7
0x1400c14c1  cmp     byte ptr [rdx+1], 7
0x1400c14c5  jnz     short loc_1400C1500
0x1400c14c7  cmp     [rdx+8], ebx
0x1400c14ca  jnz     short loc_1400C1500
0x1400c14cc  test    cs:byte_140177432, 40h
0x1400c14d3  jz      loc_1400C19F7
0x1400c14d9  mov     rax, [rdi+38h]
0x1400c14dd  test    rax, rax
0x1400c14e0  jz      short loc_1400C14E4
0x1400c14e2  mov     ebx, [rax]
0x1400c14e4  mov     eax, [rdi+30h]
0x1400c14e7  lea     r8, [rbp+57h+var_58]
0x1400c14eb  mov     [rsp+0C0h+var_98], eax
0x1400c14ef  mov     r9, rdi
0x1400c14f2  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1400c14f6  call    McTemplateK0pqd_EtwWriteTransfer
0x1400c14fb  jmp     loc_1400C19F7
0x1400c1500  test    cs:byte_140177432, 20h
0x1400c1507  jz      loc_1400C19F7
0x1400c150d  lea     rdx, EventPnpRequestComplete
0x1400c1514  jmp     loc_1400C19E4
0x1400c1519  cmp     cs:byte_140177431, bl
0x1400c151f  jge     loc_1400C19F7
0x1400c1525  mov     rdx, [rdx+8]
0x1400c1529  mov     esi, 1
0x1400c152e  movzx   eax, byte ptr [rdx+2]
0x1400c1532  cmp     al, 28h ; '('
0x1400c1534  jnz     loc_1400C18DE
0x1400c153a  cmp     [rdx+14h], ebx
0x1400c153d  jnz     loc_1400C19F7
0x1400c1543  mov     r12d, [rdx+38h]
0x1400c1547  test    r12d, r12d
0x1400c154a  jz      loc_1400C19F7
0x1400c1550  mov     r10b, bl
0x1400c1553  mov     [rbp+57h+var_60], bl
0x1400c1556  mov     r11, rbx
0x1400c1559  mov     r13b, bl
0x1400c155c  mov     r9, rbx
0x1400c155f  mov     r15d, ebx
0x1400c1562  mov     eax, r15d
0x1400c1565  mov     ecx, [rdx+rax*4+78h]
0x1400c1569  cmp     ecx, 80h
0x1400c156f  jb      short loc_1400C15F0
0x1400c1571  mov     r14d, [rdx+10h]
0x1400c1575  cmp     ecx, r14d
0x1400c1578  jnb     short loc_1400C15F0
0x1400c157a  mov     r8d, ecx
0x1400c157d  mov     ecx, [rcx+rdx]
0x1400c1580  sub     ecx, 40h ; '@'
0x1400c1583  jz      short loc_1400C15DA
0x1400c1585  sub     ecx, esi
0x1400c1587  jz      short loc_1400C15AE
0x1400c1589  cmp     ecx, esi
0x1400c158b  jnz     short loc_1400C15E7
0x1400c158d  lea     rcx, [r8+28h]
0x1400c1591  cmp     rcx, r14
0x1400c1594  ja      short loc_1400C15E7
0x1400c1596  cmp     [r8+rdx+0Ch], ebx
0x1400c159b  jbe     short loc_1400C15A4
0x1400c159d  lea     r11, [rdx+20h]
0x1400c15a1  add     r11, r8
0x1400c15a4  mov     r9, [r8+rdx+18h]
0x1400c15a9  jmp     loc_1400C18C6
0x1400c15ae  lea     rcx, [r8+38h]
0x1400c15b2  cmp     rcx, r14
0x1400c15b5  ja      short loc_1400C15E7
0x1400c15b7  mov     [rbp+57h+var_60], sil
0x1400c15bb  cmp     [r8+rdx+0Ah], bl
0x1400c15c0  jbe     short loc_1400C15C9
0x1400c15c2  lea     r11, [rdx+18h]
0x1400c15c6  add     r11, r8
0x1400c15c9  mov     r13b, [r8+rdx+8]
0x1400c15ce  mov     r9, [r8+rdx+10h]
0x1400c15d3  mov     r10b, [r8+rdx+9]
0x1400c15d8  jmp     short loc_1400C15E7
0x1400c15da  lea     rcx, [r8+28h]
0x1400c15de  cmp     rcx, r14
0x1400c15e1  jbe     loc_1400C18B3
0x1400c15e7  cmp     [rbp+57h+var_60], bl
0x1400c15ea  jnz     loc_1400C18D0
0x1400c15f0  add     r15d, esi
0x1400c15f3  cmp     r15d, r12d
0x1400c15f6  jb      loc_1400C1562
0x1400c15fc  jmp     loc_1400C18D0
0x1400c1601  mov     r8b, bl
0x1400c1604  jmp     loc_1400C1995
0x1400c1609  mov     rcx, [r14+18h]
0x1400c160d  xor     ebx, ebx
0x1400c160f  mov     esi, 1
0x1400c1614  test    rcx, rcx
0x1400c1617  jz      loc_1400C179A
0x1400c161d  mov     eax, [r14+38h]
0x1400c1621  test    eax, eax
0x1400c1623  jz      loc_1400C179A
0x1400c1629  add     eax, 0FFFFFFFBh
0x1400c162c  cmp     eax, esi
0x1400c162e  jbe     loc_1400C179A
0x1400c1634  mov     eax, [rcx]
0x1400c1636  mov     r9, [r14+70h]
0x1400c163a  cmp     eax, 41445452h
0x1400c163f  jnz     short loc_1400C1647
0x1400c1641  mov     r8, [rcx+8]
0x1400c1645  jmp     short loc_1400C1651
0x1400c1647  cmp     eax, 4E564144h
0x1400c164c  jz      short loc_1400C1641
0x1400c164e  mov     r8, rbx
0x1400c1651  mov     dl, [r9]
0x1400c1654  lea     rcx, [r9+10h]
0x1400c1658  mov     eax, [r14+0D68h]
0x1400c165f  and     dl, 1Fh
0x1400c1662  mov     [rsp+0C0h+var_90], eax
0x1400c1666  add     r9, 8
0x1400c166a  mov     byte ptr [rsp+0C0h+var_98], dl
0x1400c166e  mov     rdx, rdi
0x1400c1671  mov     [rsp+0C0h+var_A0], rcx
0x1400c1676  call    PortQueryInterfacePdoInfo
0x1400c167b  cmp     cs:StorEtwLoggingEnabled, bl
0x1400c1681  mov     [rbp+57h+var_5C], eax
0x1400c1684  mov     byte ptr [rdi+8Dh], 0ACh
0x1400c168b  mov     [rdi+30h], eax
0x1400c168e  jz      loc_1400C19F7
0x1400c1694  xorps   xmm0, xmm0
0x1400c1697  lea     rdx, [rbp+57h+var_58]
0x1400c169b  mov     rcx, rdi
0x1400c169e  movups  [rbp+57h+var_58], xmm0
0x1400c16a2  call    cs:__imp_IoGetActivityIdIrp
0x1400c16a9  nop     dword ptr [rax+rax+00h]
0x1400c16ae  mov     rdx, [rdi+0B8h]
0x1400c16b5  movzx   eax, byte ptr [rdx]
0x1400c16b8  sub     eax, 0Eh
0x1400c16bb  jz      loc_1400C19D4
0x1400c16c1  sub     eax, esi
0x1400c16c3  jnz     loc_1400C14B8
0x1400c16c9  cmp     cs:byte_140177431, bl
0x1400c16cf  jge     loc_1400C19F7
0x1400c16d5  mov     rdx, [rdx+8]
0x1400c16d9  movzx   eax, byte ptr [rdx+2]
0x1400c16dd  cmp     al, 28h ; '('
0x1400c16df  jnz     loc_1400C18DE
0x1400c16e5  cmp     [rdx+14h], ebx
0x1400c16e8  jnz     loc_1400C19F7
0x1400c16ee  mov     r12d, [rdx+38h]
0x1400c16f2  test    r12d, r12d
0x1400c16f5  jz      loc_1400C19F7
0x1400c16fb  mov     r10b, bl
0x1400c16fe  mov     [rbp+57h+var_60], bl
0x1400c1701  mov     r11, rbx
0x1400c1704  mov     r13b, bl
0x1400c1707  mov     r9, rbx
0x1400c170a  mov     r15d, ebx
0x1400c170d  mov     eax, r15d
0x1400c1710  mov     ecx, [rdx+rax*4+78h]
0x1400c1714  cmp     ecx, 80h
0x1400c171a  jb      short loc_1400C1789
0x1400c171c  mov     r14d, [rdx+10h]
0x1400c1720  cmp     ecx, r14d
0x1400c1723  jnb     short loc_1400C1789
0x1400c1725  mov     r8d, ecx
0x1400c1728  mov     ecx, [rcx+rdx]
0x1400c172b  sub     ecx, 40h ; '@'
0x1400c172e  jz      short loc_1400C1773
0x1400c1730  sub     ecx, esi
0x1400c1732  jz      short loc_1400C1747
0x1400c1734  cmp     ecx, esi
0x1400c1736  jnz     short loc_1400C1780
0x1400c1738  lea     rcx, [r8+28h]
0x1400c173c  cmp     rcx, r14
0x1400c173f  jbe     loc_1400C1596
0x1400c1745  jmp     short loc_1400C1780
0x1400c1747  lea     rcx, [r8+38h]
0x1400c174b  cmp     rcx, r14
0x1400c174e  ja      short loc_1400C1780
0x1400c1750  mov     [rbp+57h+var_60], sil
0x1400c1754  cmp     [r8+rdx+0Ah], bl
0x1400c1759  jbe     short loc_1400C1762
0x1400c175b  lea     r11, [rdx+18h]
0x1400c175f  add     r11, r8
0x1400c1762  mov     r13b, [r8+rdx+8]
0x1400c1767  mov     r9, [r8+rdx+10h]
0x1400c176c  mov     r10b, [r8+rdx+9]
0x1400c1771  jmp     short loc_1400C1780
0x1400c1773  lea     rcx, [r8+28h]
0x1400c1777  cmp     rcx, r14
0x1400c177a  jbe     loc_1400C18B3
0x1400c1780  cmp     [rbp+57h+var_60], bl
0x1400c1783  jnz     loc_1400C18D0
0x1400c1789  add     r15d, esi
0x1400c178c  cmp     r15d, r12d
0x1400c178f  jb      loc_1400C170D
0x1400c1795  jmp     loc_1400C18D0
0x1400c179a  cmp     cs:StorEtwLoggingEnabled, bl
0x1400c17a0  mov     eax, 0C000000Eh
0x1400c17a5  mov     [rbp+57h+var_5C], eax
0x1400c17a8  mov     [rdi+30h], eax
0x1400c17ab  mov     [rdi+38h], rbx
0x1400c17af  mov     byte ptr [rdi+8Dh], 0ACh
0x1400c17b6  jz      loc_1400C19F7
0x1400c17bc  xorps   xmm0, xmm0
0x1400c17bf  lea     rdx, [rbp+57h+var_58]
0x1400c17c3  mov     rcx, rdi
0x1400c17c6  movups  [rbp+57h+var_58], xmm0
0x1400c17ca  call    cs:__imp_IoGetActivityIdIrp
0x1400c17d1  nop     dword ptr [rax+rax+00h]
0x1400c17d6  mov     rdx, [rdi+0B8h]
0x1400c17dd  movzx   eax, byte ptr [rdx]
0x1400c17e0  sub     eax, 0Eh
0x1400c17e3  jz      loc_1400C19D4
0x1400c17e9  sub     eax, esi
0x1400c17eb  jnz     loc_1400C14B8
0x1400c17f1  cmp     cs:byte_140177431, bl
0x1400c17f7  jge     loc_1400C19F7
0x1400c17fd  mov     rdx, [rdx+8]
0x1400c1801  movzx   eax, byte ptr [rdx+2]
0x1400c1805  cmp     al, 28h ; '('
0x1400c1807  jnz     loc_1400C18DE
0x1400c180d  cmp     [rdx+14h], ebx
0x1400c1810  jnz     loc_1400C19F7
0x1400c1816  mov     r12d, [rdx+38h]
0x1400c181a  test    r12d, r12d
0x1400c181d  jz      loc_1400C19F7
0x1400c1823  mov     r10b, bl
0x1400c1826  mov     [rbp+57h+var_60], bl
0x1400c1829  mov     r11, rbx
0x1400c182c  mov     r13b, bl
0x1400c182f  mov     r9, rbx
0x1400c1832  mov     r15d, ebx
0x1400c1835  mov     eax, r15d
0x1400c1838  mov     ecx, [rdx+rax*4+78h]
0x1400c183c  cmp     ecx, 80h
0x1400c1842  jb      short loc_1400C18A9
0x1400c1844  mov     r14d, [rdx+10h]
0x1400c1848  cmp     ecx, r14d
0x1400c184b  jnb     short loc_1400C18A9
0x1400c184d  mov     r8d, ecx
0x1400c1850  mov     ecx, [rcx+rdx]
0x1400c1853  sub     ecx, 40h ; '@'
0x1400c1856  jz      short loc_1400C189B
0x1400c1858  sub     ecx, esi
0x1400c185a  jz      short loc_1400C186F
0x1400c185c  cmp     ecx, esi
0x1400c185e  jnz     short loc_1400C18A4
  ... truncated ...
```
