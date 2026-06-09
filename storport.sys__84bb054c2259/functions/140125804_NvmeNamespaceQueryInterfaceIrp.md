# NvmeNamespaceQueryInterfaceIrp

- ea: `0x140125804`
- end: `0x140125e60`
- name: `NvmeNamespaceQueryInterfaceIrp`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140040b64`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x140125804`
- `0x14014b400`
- `0x140191a4c`
- `0x1401b81a8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1401258d0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140125ada`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140125c00`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401258d0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140125ada`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140125c00`
- `ntoskrnl!IofCompleteRequest` at `0x140125e30`
- `ntoskrnl!IofCompleteRequest` at `0x140125e30`
- `ntoskrnl!RtlCompareMemory` at `0x14012585d`
- `ntoskrnl!RtlCompareMemory` at `0x140125885`
- `ntoskrnl!RtlCompareMemory` at `0x14012585d`
- `ntoskrnl!RtlCompareMemory` at `0x140125885`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceQueryInterfaceIrp(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  GUID *v5; // rcx
  GUID *v6; // rcx
  __int64 v7; // rcx
  bool v9; // zf
  unsigned __int64 v10; // rcx
  unsigned __int8 *v11; // rdx
  int v12; // eax
  int *v13; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  __int64 v16; // rdx
  char v17; // di
  int v18; // eax
  unsigned int v19; // r15d
  unsigned __int8 v20; // r10
  char *v21; // r11
  char v22; // r12
  _BYTE *v23; // r9
  __int64 v24; // r14
  char v25; // r13
  unsigned __int64 v26; // rsi
  __int64 v27; // r8
  int v28; // ecx
  char v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int InterfacePdoInfo; // eax
  unsigned int v33; // r15d
  __int64 v34; // r14
  char v35; // r13
  unsigned __int64 v36; // rsi
  int v37; // ecx
  unsigned int v38; // r15d
  __int64 v39; // r14
  char v40; // r13
  unsigned __int64 v41; // rsi
  int v42; // ecx
  char v43; // cl
  char v44; // si
  char v45; // r11
  _BYTE *v46; // rax
  char *v47; // r8
  unsigned int v48; // eax
  __int64 v49; // [rsp+60h] [rbp-9h] BYREF
  __int128 v50; // [rsp+68h] [rbp-1h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v49 = 0;
  v5 = *(GUID **)(v2 + 8);
  if ( v5 == &GUID_STORAGE_QUERY_PDO_INFO || RtlCompareMemory(v5, &GUID_STORAGE_QUERY_PDO_INFO, 0x10u) == 16 )
  {
    v30 = *(_DWORD *)(a1 + 96);
    v17 = 1;
    if ( v30 && (unsigned int)(v30 - 5) > 1 )
    {
      v31 = *(_QWORD *)(a1 + 16);
      LODWORD(v49) = 1699567182;
      InterfacePdoInfo = PortQueryInterfacePdoInfo(
                           (*(_BYTE *)(v31 + 136) & 2) != 0 ? 20 : 17,
                           a2,
                           *(_QWORD *)(*(_QWORD *)(v31 + 128) + 8LL),
                           (unsigned int)&v49,
                           *(_QWORD *)(v31 + 592) + 24LL,
                           0,
                           (*(_BYTE *)(v31 + 136) & 2) != 0 ? 20 : 17);
      v9 = StorEtwLoggingEnabled == 0;
      LODWORD(v49) = InterfacePdoInfo;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = InterfacePdoInfo;
      if ( v9 )
        goto LABEL_118;
      v50 = 0;
      IoGetActivityIdIrp(a2, &v50);
      v11 = *(unsigned __int8 **)(a2 + 184);
      if ( *v11 != 14 )
      {
        v12 = *v11 - 15;
        if ( *v11 != 15 )
          goto LABEL_9;
        if ( byte_140177431 >= 0 )
          goto LABEL_118;
        v16 = *((_QWORD *)v11 + 1);
        v18 = *(unsigned __int8 *)(v16 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( !*(_DWORD *)(v16 + 20) )
          {
            v33 = *(_DWORD *)(v16 + 56);
            if ( v33 )
            {
              v20 = 0;
              v21 = 0;
              v22 = 0;
              v23 = 0;
              v34 = 0;
              v35 = 0;
              while ( 1 )
              {
                v10 = *(unsigned int *)(v16 + 4 * v34 + 120);
                if ( (unsigned int)v10 >= 0x80 )
                {
                  v36 = *(unsigned int *)(v16 + 16);
                  if ( (unsigned int)v10 < (unsigned int)v36 )
                  {
                    v27 = (unsigned int)v10;
                    v37 = *(_DWORD *)(v10 + v16) - 64;
                    if ( v37 )
                    {
                      LODWORD(v10) = v37 - 1;
                      if ( (_DWORD)v10 )
                      {
                        if ( (_DWORD)v10 == 1 )
                        {
                          LODWORD(v10) = v27 + 40;
                          if ( v27 + 40 <= v36 )
                            goto LABEL_30;
                        }
                      }
                      else
                      {
                        LODWORD(v10) = v27 + 56;
                        if ( v27 + 56 <= v36 )
                        {
                          v35 = 1;
                          if ( *(_BYTE *)(v27 + v16 + 10) )
                            v21 = (char *)(v27 + v16 + 24);
                          v22 = *(_BYTE *)(v27 + v16 + 8);
                          v23 = *(_BYTE **)(v27 + v16 + 16);
                          v20 = *(_BYTE *)(v27 + v16 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v10) = v27 + 40;
                      if ( v27 + 40 <= v36 )
                        goto LABEL_90;
                    }
                    if ( v35 )
                      goto LABEL_94;
                  }
                }
                v34 = (unsigned int)(v34 + 1);
                if ( (unsigned int)v34 >= v33 )
                  goto LABEL_94;
              }
            }
          }
          goto LABEL_118;
        }
        goto LABEL_96;
      }
    }
    else
    {
      v9 = StorEtwLoggingEnabled == 0;
      LODWORD(v49) = -1073741810;
      *(_DWORD *)(a2 + 48) = -1073741810;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v9 )
        goto LABEL_118;
      v50 = 0;
      IoGetActivityIdIrp(a2, &v50);
      v11 = *(unsigned __int8 **)(a2 + 184);
      if ( *v11 != 14 )
      {
        v12 = *v11 - 15;
        if ( *v11 != 15 )
          goto LABEL_9;
        if ( byte_140177431 >= 0 )
          goto LABEL_118;
        v16 = *((_QWORD *)v11 + 1);
        v18 = *(unsigned __int8 *)(v16 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( *(_DWORD *)(v16 + 20) )
            goto LABEL_118;
          v38 = *(_DWORD *)(v16 + 56);
          if ( !v38 )
            goto LABEL_118;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v39 = 0;
          v40 = 0;
          while ( 1 )
          {
            v10 = *(unsigned int *)(v16 + 4 * v39 + 120);
            if ( (unsigned int)v10 >= 0x80 )
            {
              v41 = *(unsigned int *)(v16 + 16);
              if ( (unsigned int)v10 < (unsigned int)v41 )
              {
                v27 = (unsigned int)v10;
                v42 = *(_DWORD *)(v10 + v16) - 64;
                if ( v42 )
                {
                  LODWORD(v10) = v42 - 1;
                  if ( (_DWORD)v10 )
                  {
                    if ( (_DWORD)v10 == 1 )
                    {
                      LODWORD(v10) = v27 + 40;
                      if ( v27 + 40 <= v41 )
                      {
LABEL_30:
                        if ( *(_DWORD *)(v27 + v16 + 12) )
                          v21 = (char *)(v27 + v16 + 32);
                        v23 = *(_BYTE **)(v27 + v16 + 24);
                        goto LABEL_93;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v10) = v27 + 56;
                    if ( v27 + 56 <= v41 )
                    {
                      v40 = 1;
                      if ( *(_BYTE *)(v27 + v16 + 10) )
                        v21 = (char *)(v27 + v16 + 24);
                      v22 = *(_BYTE *)(v27 + v16 + 8);
                      v23 = *(_BYTE **)(v27 + v16 + 16);
                      v20 = *(_BYTE *)(v27 + v16 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v10) = v27 + 40;
                  if ( v27 + 40 <= v41 )
                  {
LABEL_90:
                    if ( *(_BYTE *)(v27 + v16 + 10) )
                      v21 = (char *)(v27 + v16 + 24);
                    v23 = *(_BYTE **)(v27 + v16 + 16);
LABEL_93:
                    v20 = *(_BYTE *)(v27 + v16 + 9);
                    v22 = *(_BYTE *)(v27 + v16 + 8);
LABEL_94:
                    if ( v21 )
                    {
                      v43 = *v21;
                      goto LABEL_97;
                    }
                    goto LABEL_118;
                  }
                }
                if ( v40 )
                  goto LABEL_94;
              }
            }
            v39 = (unsigned int)(v39 + 1);
            if ( (unsigned int)v39 >= v38 )
              goto LABEL_94;
          }
        }
        goto LABEL_96;
      }
    }
LABEL_115:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_118;
    v15 = EventNonReadWriteRequestComplete;
    goto LABEL_117;
  }
  v6 = *(GUID **)(v2 + 8);
  if ( v6 != &GUID_THERMAL_COOLING_INTERFACE && RtlCompareMemory(v6, &GUID_THERMAL_COOLING_INTERFACE, 0x10u) != 16 )
    return RaUnitIgnorePnpIrp(v7, a2);
  v9 = StorEtwLoggingEnabled == 0;
  LODWORD(v49) = -1073741637;
  *(_DWORD *)(a2 + 48) = -1073741637;
  *(_BYTE *)(a2 + 141) = -84;
  if ( v9 )
    goto LABEL_118;
  v50 = 0;
  IoGetActivityIdIrp(a2, &v50);
  v11 = *(unsigned __int8 **)(a2 + 184);
  if ( *v11 == 14 )
    goto LABEL_115;
  v12 = *v11 - 15;
  if ( *v11 != 15 )
  {
LABEL_9:
    if ( v12 != 12 )
      goto LABEL_118;
    if ( v11[1] == 7 && !*((_DWORD *)v11 + 2) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v13 = *(int **)(a2 + 56);
        if ( v13 )
          v14 = *v13;
        else
          v14 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v14, (_DWORD)v11, (unsigned int)&v50, a2, v14, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_118;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_118;
    v15 = EventPnpRequestComplete;
LABEL_117:
    McTemplateK0pd_EtwWriteTransfer(v10, v15, &v50, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_118;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_118;
  v16 = *((_QWORD *)v11 + 1);
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
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v24 = 0;
        v25 = 0;
        while ( 1 )
        {
          v10 = *(unsigned int *)(v16 + 4 * v24 + 120);
          if ( (unsigned int)v10 >= 0x80 )
          {
            v26 = *(unsigned int *)(v16 + 16);
            if ( (unsigned int)v10 < (unsigned int)v26 )
            {
              v27 = (unsigned int)v10;
              v28 = *(_DWORD *)(v10 + v16) - 64;
              if ( v28 )
              {
                LODWORD(v10) = v28 - 1;
                if ( (_DWORD)v10 )
                {
                  if ( (_DWORD)v10 == 1 )
                  {
                    LODWORD(v10) = v27 + 40;
                    if ( v27 + 40 <= v26 )
                      goto LABEL_30;
                  }
                }
                else
                {
                  LODWORD(v10) = v27 + 56;
                  if ( v27 + 56 <= v26 )
                  {
                    v25 = 1;
                    if ( *(_BYTE *)(v27 + v16 + 10) )
                      v21 = (char *)(v27 + v16 + 24);
                    v22 = *(_BYTE *)(v27 + v16 + 8);
                    v23 = *(_BYTE **)(v27 + v16 + 16);
                    v20 = *(_BYTE *)(v27 + v16 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v10) = v27 + 40;
                if ( v27 + 40 <= v26 )
                  goto LABEL_90;
              }
              if ( v25 )
                goto LABEL_94;
            }
          }
          v24 = (unsigned int)(v24 + 1);
          if ( (unsigned int)v24 >= v19 )
            goto LABEL_94;
        }
      }
    }
    goto LABEL_118;
  }
LABEL_96:
  v43 = *(_BYTE *)(v16 + 72);
  v23 = *(_BYTE **)(v16 + 32);
  v20 = *(_BYTE *)(v16 + 11);
  v22 = *(_BYTE *)(v16 + 4);
  if ( v18 )
    goto LABEL_118;
LABEL_97:
  LOBYTE(v10) = v43 - 8;
  if ( (v10 & 0x5D) == 0 )
  {
    v44 = *(_BYTE *)(v16 + 3);
    if ( v44 == 1 || !v23 || !v20 )
      goto LABEL_113;
    LOBYTE(v16) = 0;
    v45 = 0;
    v29 = 0;
    v10 = (unsigned __int64)&v23[v20];
    v46 = v23 + 8;
    if ( (unsigned __int8)((*v23 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v46 <= v10 )
      {
        v45 = v23[2];
        LOBYTE(v16) = v23[1] & 0xF;
        v29 = v23[3];
        goto LABEL_112;
      }
    }
    else if ( (unsigned __int64)v46 <= v10 )
    {
      v47 = v23 + 13;
      LOBYTE(v16) = v23[2] & 0xF;
      v48 = v20;
      if ( (unsigned int)(unsigned __int8)v23[7] + 8 <= v20 )
        v48 = (unsigned __int8)v23[7] + 8;
      v10 = (unsigned __int64)&v23[v48];
      if ( (unsigned __int64)v47 <= v10 )
        v45 = v23[12];
      if ( (unsigned __int64)(v23 + 14) > v10 )
        v29 = 0;
      else
        v29 = *v47;
LABEL_112:
      if ( v17 )
      {
LABEL_114:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v10,
          v16,
          (unsigned int)&v50,
          a2,
          *(_DWORD *)(a2 + 48),
          v44,
          v22,
          v16,
          v45,
          v29,
          a2);
        goto LABEL_118;
      }
LABEL_113:
      LOBYTE(v16) = 0;
      v45 = 0;
      v29 = 0;
      goto LABEL_114;
    }
    v17 = 0;
    goto LABEL_112;
  }
LABEL_118:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)v49;
}

```

## disassembly

```asm
0x140125804  push    rbp
0x140125806  push    rbx
0x140125807  push    rsi
0x140125808  push    rdi
0x140125809  push    r12
0x14012580b  push    r13
0x14012580d  push    r14
0x14012580f  push    r15
0x140125811  lea     rbp, [rsp-1Fh]
0x140125816  sub     rsp, 88h
0x14012581d  mov     rax, cs:__security_cookie
0x140125824  xor     rax, rsp
0x140125827  mov     [rbp+57h+var_48], rax
0x14012582b  mov     rdi, [rdx+0B8h]
0x140125832  mov     rbx, rdx
0x140125835  mov     rsi, rcx
0x140125838  mov     [rbp+57h+var_60], 0
0x140125840  lea     rdx, GUID_STORAGE_QUERY_PDO_INFO; Source2
0x140125847  mov     rcx, [rdi+8]; Source1
0x14012584b  cmp     rcx, rdx
0x14012584e  jz      loc_140125A49
0x140125854  mov     r14d, 10h
0x14012585a  mov     r8d, r14d; Length
0x14012585d  call    cs:__imp_RtlCompareMemory
0x140125864  nop     dword ptr [rax+rax+00h]
0x140125869  cmp     rax, r14
0x14012586c  jz      loc_140125A49
0x140125872  mov     rcx, [rdi+8]; Source1
0x140125876  lea     rdx, GUID_THERMAL_COOLING_INTERFACE; Source2
0x14012587d  cmp     rcx, rdx
0x140125880  jz      short loc_1401258A3
0x140125882  mov     r8d, r14d; Length
0x140125885  call    cs:__imp_RtlCompareMemory
0x14012588c  nop     dword ptr [rax+rax+00h]
0x140125891  cmp     rax, r14
0x140125894  jz      short loc_1401258A3
0x140125896  mov     rdx, rbx
0x140125899  call    RaUnitIgnorePnpIrp
0x14012589e  jmp     loc_140125E3F
0x1401258a3  cmp     cs:StorEtwLoggingEnabled, 0
0x1401258aa  mov     eax, 0C00000BBh
0x1401258af  mov     dword ptr [rbp+57h+var_60], eax
0x1401258b2  mov     [rbx+30h], eax
0x1401258b5  mov     byte ptr [rbx+8Dh], 0ACh
0x1401258bc  jz      loc_140125E2B
0x1401258c2  xorps   xmm0, xmm0
0x1401258c5  lea     rdx, [rbp+57h+var_58]
0x1401258c9  mov     rcx, rbx
0x1401258cc  movups  [rbp+57h+var_58], xmm0
0x1401258d0  call    cs:__imp_IoGetActivityIdIrp
0x1401258d7  nop     dword ptr [rax+rax+00h]
0x1401258dc  mov     rdx, [rbx+0B8h]
0x1401258e3  movzx   eax, byte ptr [rdx]
0x1401258e6  sub     eax, 0Eh
0x1401258e9  jz      loc_140125E08
0x1401258ef  sub     eax, 1
0x1401258f2  jz      short loc_14012595A
0x1401258f4  cmp     eax, 0Ch
0x1401258f7  jnz     loc_140125E2B
0x1401258fd  cmp     byte ptr [rdx+1], 7
0x140125901  jnz     short loc_140125941
0x140125903  cmp     dword ptr [rdx+8], 0
0x140125907  jnz     short loc_140125941
0x140125909  test    cs:byte_140177432, 40h
0x140125910  jz      loc_140125E2B
0x140125916  mov     rax, [rbx+38h]
0x14012591a  test    rax, rax
0x14012591d  jz      short loc_140125923
0x14012591f  mov     ecx, [rax]
0x140125921  jmp     short loc_140125925
0x140125923  xor     ecx, ecx
0x140125925  mov     eax, [rbx+30h]
0x140125928  lea     r8, [rbp+57h+var_58]
0x14012592c  mov     [rsp+0C0h+var_98], eax
0x140125930  mov     r9, rbx
0x140125933  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x140125937  call    McTemplateK0pqd_EtwWriteTransfer
0x14012593c  jmp     loc_140125E2B
0x140125941  test    cs:byte_140177432, 20h
0x140125948  jz      loc_140125E2B
0x14012594e  lea     rdx, EventPnpRequestComplete
0x140125955  jmp     loc_140125E18
0x14012595a  cmp     cs:byte_140177431, 0
0x140125961  jge     loc_140125E2B
0x140125967  mov     rdx, [rdx+8]
0x14012596b  mov     edi, 1
0x140125970  movzx   eax, byte ptr [rdx+2]
0x140125974  cmp     al, 28h ; '('
0x140125976  jnz     loc_140125D12
0x14012597c  cmp     dword ptr [rdx+14h], 0
0x140125980  jnz     loc_140125E2B
0x140125986  mov     r15d, [rdx+38h]
0x14012598a  test    r15d, r15d
0x14012598d  jz      loc_140125E2B
0x140125993  xor     r10b, r10b
0x140125996  xor     r11d, r11d
0x140125999  xor     r12b, r12b
0x14012599c  xor     r9d, r9d
0x14012599f  xor     r14d, r14d
0x1401259a2  xor     r13b, r13b
0x1401259a5  mov     ecx, [rdx+r14*4+78h]
0x1401259aa  cmp     ecx, 80h
0x1401259b0  jb      short loc_140125A30
0x1401259b2  mov     esi, [rdx+10h]
0x1401259b5  cmp     ecx, esi
0x1401259b7  jnb     short loc_140125A30
0x1401259b9  mov     r8d, ecx
0x1401259bc  mov     ecx, [rcx+rdx]
0x1401259bf  sub     ecx, 40h ; '@'
0x1401259c2  jz      short loc_140125A1A
0x1401259c4  sub     ecx, edi
0x1401259c6  jz      short loc_1401259EE
0x1401259c8  cmp     ecx, edi
0x1401259ca  jnz     short loc_140125A27
0x1401259cc  lea     rcx, [r8+28h]
0x1401259d0  cmp     rcx, rsi
0x1401259d3  ja      short loc_140125A27
0x1401259d5  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401259db  jbe     short loc_1401259E4
0x1401259dd  lea     r11, [rdx+20h]
0x1401259e1  add     r11, r8
0x1401259e4  mov     r9, [r8+rdx+18h]
0x1401259e9  jmp     loc_140125CFA
0x1401259ee  lea     rcx, [r8+38h]
0x1401259f2  cmp     rcx, rsi
0x1401259f5  ja      short loc_140125A27
0x1401259f7  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401259fd  mov     r13b, dil
0x140125a00  jbe     short loc_140125A09
0x140125a02  lea     r11, [rdx+18h]
0x140125a06  add     r11, r8
0x140125a09  mov     r12b, [r8+rdx+8]
0x140125a0e  mov     r9, [r8+rdx+10h]
0x140125a13  mov     r10b, [r8+rdx+9]
0x140125a18  jmp     short loc_140125A27
0x140125a1a  lea     rcx, [r8+28h]
0x140125a1e  cmp     rcx, rsi
0x140125a21  jbe     loc_140125CE6
0x140125a27  test    r13b, r13b
0x140125a2a  jnz     loc_140125D04
0x140125a30  add     r14d, edi
0x140125a33  cmp     r14d, r15d
0x140125a36  jb      loc_1401259A5
0x140125a3c  jmp     loc_140125D04
0x140125a41  xor     r8b, r8b
0x140125a44  jmp     loc_140125DC9
0x140125a49  mov     eax, [rsi+60h]
0x140125a4c  mov     edi, 1
0x140125a51  test    eax, eax
0x140125a53  jz      loc_140125BCB
0x140125a59  add     eax, 0FFFFFFFBh
0x140125a5c  cmp     eax, edi
0x140125a5e  jbe     loc_140125BCB
0x140125a64  mov     r8, [rsi+10h]
0x140125a68  lea     r9, [rbp+57h+var_60]
0x140125a6c  mov     rdx, rbx
0x140125a6f  mov     dword ptr [rbp+57h+var_60], 654D564Eh
0x140125a76  mov     al, [r8+88h]
0x140125a7d  and     al, 2
0x140125a7f  neg     al
0x140125a81  mov     rax, [r8+250h]
0x140125a88  mov     r8, [r8+80h]
0x140125a8f  sbb     ecx, ecx
0x140125a91  and     ecx, 3
0x140125a94  add     rax, 18h
0x140125a98  add     ecx, 11h
0x140125a9b  mov     [rsp+0C0h+var_90], ecx
0x140125a9f  mov     r8, [r8+8]
0x140125aa3  mov     byte ptr [rsp+0C0h+var_98], 0
0x140125aa8  mov     [rsp+0C0h+var_A0], rax
0x140125aad  call    PortQueryInterfacePdoInfo
0x140125ab2  cmp     cs:StorEtwLoggingEnabled, 0
0x140125ab9  mov     dword ptr [rbp+57h+var_60], eax
0x140125abc  mov     byte ptr [rbx+8Dh], 0ACh
0x140125ac3  mov     [rbx+30h], eax
0x140125ac6  jz      loc_140125E2B
0x140125acc  xorps   xmm0, xmm0
0x140125acf  lea     rdx, [rbp+57h+var_58]
0x140125ad3  mov     rcx, rbx
0x140125ad6  movups  [rbp+57h+var_58], xmm0
0x140125ada  call    cs:__imp_IoGetActivityIdIrp
0x140125ae1  nop     dword ptr [rax+rax+00h]
0x140125ae6  mov     rdx, [rbx+0B8h]
0x140125aed  movzx   eax, byte ptr [rdx]
0x140125af0  sub     eax, 0Eh
0x140125af3  jz      loc_140125E08
0x140125af9  sub     eax, edi
0x140125afb  jnz     loc_1401258F4
0x140125b01  cmp     cs:byte_140177431, al
0x140125b07  jge     loc_140125E2B
0x140125b0d  mov     rdx, [rdx+8]
0x140125b11  movzx   eax, byte ptr [rdx+2]
0x140125b15  cmp     al, 28h ; '('
0x140125b17  jnz     loc_140125D12
0x140125b1d  cmp     dword ptr [rdx+14h], 0
0x140125b21  jnz     loc_140125E2B
0x140125b27  mov     r15d, [rdx+38h]
0x140125b2b  test    r15d, r15d
0x140125b2e  jz      loc_140125E2B
0x140125b34  xor     r10b, r10b
0x140125b37  xor     r11d, r11d
0x140125b3a  xor     r12b, r12b
0x140125b3d  xor     r9d, r9d
0x140125b40  xor     r14d, r14d
0x140125b43  xor     r13b, r13b
0x140125b46  mov     ecx, [rdx+r14*4+78h]
0x140125b4b  cmp     ecx, 80h
0x140125b51  jb      short loc_140125BBE
0x140125b53  mov     esi, [rdx+10h]
0x140125b56  cmp     ecx, esi
0x140125b58  jnb     short loc_140125BBE
0x140125b5a  mov     r8d, ecx
0x140125b5d  mov     ecx, [rcx+rdx]
0x140125b60  sub     ecx, 40h ; '@'
0x140125b63  jz      short loc_140125BA8
0x140125b65  sub     ecx, edi
0x140125b67  jz      short loc_140125B7C
0x140125b69  cmp     ecx, edi
0x140125b6b  jnz     short loc_140125BB5
0x140125b6d  lea     rcx, [r8+28h]
0x140125b71  cmp     rcx, rsi
0x140125b74  jbe     loc_1401259D5
0x140125b7a  jmp     short loc_140125BB5
0x140125b7c  lea     rcx, [r8+38h]
0x140125b80  cmp     rcx, rsi
0x140125b83  ja      short loc_140125BB5
0x140125b85  cmp     byte ptr [r8+rdx+0Ah], 0
0x140125b8b  mov     r13b, dil
0x140125b8e  jbe     short loc_140125B97
0x140125b90  lea     r11, [rdx+18h]
0x140125b94  add     r11, r8
0x140125b97  mov     r12b, [r8+rdx+8]
0x140125b9c  mov     r9, [r8+rdx+10h]
0x140125ba1  mov     r10b, [r8+rdx+9]
0x140125ba6  jmp     short loc_140125BB5
0x140125ba8  lea     rcx, [r8+28h]
0x140125bac  cmp     rcx, rsi
0x140125baf  jbe     loc_140125CE6
0x140125bb5  test    r13b, r13b
0x140125bb8  jnz     loc_140125D04
0x140125bbe  add     r14d, edi
0x140125bc1  cmp     r14d, r15d
0x140125bc4  jb      short loc_140125B46
0x140125bc6  jmp     loc_140125D04
0x140125bcb  cmp     cs:StorEtwLoggingEnabled, 0
0x140125bd2  mov     eax, 0C000000Eh
0x140125bd7  mov     dword ptr [rbp+57h+var_60], eax
0x140125bda  mov     [rbx+30h], eax
0x140125bdd  mov     qword ptr [rbx+38h], 0
0x140125be5  mov     byte ptr [rbx+8Dh], 0ACh
0x140125bec  jz      loc_140125E2B
0x140125bf2  xorps   xmm0, xmm0
0x140125bf5  lea     rdx, [rbp+57h+var_58]
0x140125bf9  mov     rcx, rbx
0x140125bfc  movups  [rbp+57h+var_58], xmm0
0x140125c00  call    cs:__imp_IoGetActivityIdIrp
0x140125c07  nop     dword ptr [rax+rax+00h]
0x140125c0c  mov     rdx, [rbx+0B8h]
0x140125c13  movzx   eax, byte ptr [rdx]
0x140125c16  sub     eax, 0Eh
0x140125c19  jz      loc_140125E08
0x140125c1f  sub     eax, edi
0x140125c21  jnz     loc_1401258F4
0x140125c27  cmp     cs:byte_140177431, al
0x140125c2d  jge     loc_140125E2B
0x140125c33  mov     rdx, [rdx+8]
0x140125c37  movzx   eax, byte ptr [rdx+2]
0x140125c3b  cmp     al, 28h ; '('
0x140125c3d  jnz     loc_140125D12
0x140125c43  cmp     dword ptr [rdx+14h], 0
0x140125c47  jnz     loc_140125E2B
0x140125c4d  mov     r15d, [rdx+38h]
0x140125c51  test    r15d, r15d
0x140125c54  jz      loc_140125E2B
0x140125c5a  xor     r10b, r10b
0x140125c5d  xor     r11d, r11d
0x140125c60  xor     r12b, r12b
0x140125c63  xor     r9d, r9d
0x140125c66  xor     r14d, r14d
0x140125c69  xor     r13b, r13b
0x140125c6c  mov     ecx, [rdx+r14*4+78h]
0x140125c71  cmp     ecx, 80h
0x140125c77  jb      short loc_140125CDC
0x140125c79  mov     esi, [rdx+10h]
0x140125c7c  cmp     ecx, esi
0x140125c7e  jnb     short loc_140125CDC
0x140125c80  mov     r8d, ecx
0x140125c83  mov     ecx, [rcx+rdx]
0x140125c86  sub     ecx, 40h ; '@'
0x140125c89  jz      short loc_140125CCE
0x140125c8b  sub     ecx, edi
0x140125c8d  jz      short loc_140125CA2
0x140125c8f  cmp     ecx, edi
0x140125c91  jnz     short loc_140125CD7
0x140125c93  lea     rcx, [r8+28h]
0x140125c97  cmp     rcx, rsi
0x140125c9a  jbe     loc_1401259D5
0x140125ca0  jmp     short loc_140125CD7
0x140125ca2  lea     rcx, [r8+38h]
0x140125ca6  cmp     rcx, rsi
  ... truncated ...
```
