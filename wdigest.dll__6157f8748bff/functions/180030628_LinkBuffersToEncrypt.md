# LinkBuffersToEncrypt

- ea: `0x180030628`
- end: `0x180030c41`
- name: `LinkBuffersToEncrypt`
- size: `1561`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800301c8`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x180018b18`
- `0x180030628`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030961`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x180030945`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x180030945`

## pseudocode

```c
__int64 LinkBuffersToEncrypt(HCRYPTKEY a1, DWORD a2, __int64 a3, unsigned int *a4, DWORD *a5, void *Src, ...)
{
  unsigned int *v6; // rbp
  __int64 v7; // r15
  HCRYPTKEY v9; // r13
  BYTE *pbData; // r14
  PVOID *v11; // rcx
  unsigned int v12; // r13d
  DWORD v13; // esi
  unsigned int v14; // ebx
  DWORD v15; // r12d
  PVOID *v16; // rcx
  __int64 v17; // rbp
  int v18; // ebp
  DWORD v19; // ebp
  DWORD v20; // r15d
  char *v21; // r14
  char *v22; // rdx
  DWORD v23; // ebx
  DWORD LastError; // eax
  PVOID *v25; // rcx
  DWORD *v26; // r12
  DWORD v27; // esi
  unsigned int v28; // ebp
  DWORD v29; // ebx
  __int64 v30; // rax
  __int64 v31; // r14
  int v32; // r14d
  DWORD v33; // r14d
  DWORD v34; // r12d
  char *v35; // r15
  BYTE *hMem; // [rsp+48h] [rbp-40h]
  __int64 pdwDataLen; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  va_list va1; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va1, Src);
  va_start(va, Src);
  pdwDataLen = va_arg(va1, _QWORD);
  v6 = a4;
  LODWORD(pdwDataLen) = 0;
  v7 = a3;
  v9 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
  hMem = (BYTE *)DigestAllocateMemory(a2);
  pbData = hMem;
  if ( !hMem )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v12 = -2146893056;
    goto LABEL_90;
  }
  v13 = 0;
  v14 = *v6;
  v15 = *a5;
  if ( !a2 )
    goto LABEL_46;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  while ( v14 < *(_DWORD *)(v7 + 4) )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
    {
      WPP_SF_dd(v16[2], 253, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v13, a2);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v17 = *(_QWORD *)(v7 + 8);
    if ( *(_DWORD *)(v17 + 16LL * v14 + 4) == 1 && (v18 = *(_DWORD *)(v17 + 16LL * v14)) != 0 )
    {
      v19 = v18 - v15;
      v20 = a2 - v13;
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
      {
        WPP_SF_dd(v16[2], 255, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v20, v19);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      v21 = *(char **)(*(_QWORD *)(a3 + 8) + 16LL * v14 + 8);
      if ( v19 >= v20 )
      {
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
          WPP_SF_d(v16[2], 257, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v14);
        memcpy_0(&hMem[v13], v21, v20);
        v16 = (PVOID *)WPP_GLOBAL_Control;
        v15 = a2 - v13;
        v7 = a3;
        v13 = a2;
        pbData = hMem;
        goto LABEL_34;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
        WPP_SF_d(v16[2], 256, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v14);
      v22 = &v21[v15];
      pbData = hMem;
      memcpy_0(&hMem[v13], v22, v19);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      v13 += v19;
      v7 = a3;
    }
    else
    {
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
      {
        WPP_SF_d(v16[2], 254, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v14);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      pbData = hMem;
    }
    ++v14;
    v15 = 0;
LABEL_34:
    if ( v13 == a2 )
      goto LABEL_37;
  }
  pbData = hMem;
LABEL_37:
  v9 = a1;
  if ( v13 >= a2 )
  {
    v6 = a4;
  }
  else
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
    {
      WPP_SF_dd(v16[2], 258, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v13, a2);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    v23 = a2 - v13;
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
      WPP_SF_d(v16[2], 259, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v23);
    memcpy_0(&pbData[v13], Src, v23);
    v6 = a4;
  }
LABEL_46:
  LODWORD(pdwDataLen) = a2;
  if ( CryptEncrypt(v9, 0, 0, 0, pbData, (DWORD *)va, a2) )
  {
    v25 = (PVOID *)WPP_GLOBAL_Control;
    v12 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    v26 = a5;
    v27 = 0;
    v28 = *v6;
    v29 = *a5;
    if ( !a2 )
    {
LABEL_88:
      *v26 = v29;
      *a4 = v28;
      goto LABEL_89;
    }
    while ( 1 )
    {
      if ( v28 >= *(_DWORD *)(v7 + 4) )
      {
LABEL_79:
        v12 = 0;
        if ( v27 < a2 )
        {
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
          {
            WPP_SF_dd(v25[2], 267, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v27, a2);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          v29 = a2 - v27;
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
            WPP_SF_d(v25[2], 268, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v29);
          memcpy_0(Src, &pbData[v27], v29);
        }
        v26 = a5;
        goto LABEL_88;
      }
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
      {
        WPP_SF_dd(v25[2], 262, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v27, a2);
        v25 = (PVOID *)WPP_GLOBAL_Control;
      }
      v30 = a3;
      v31 = *(_QWORD *)(a3 + 8);
      if ( *(_DWORD *)(v31 + 16LL * v28 + 4) == 1 && (v32 = *(_DWORD *)(v31 + 16LL * v28)) != 0 )
      {
        v33 = v32 - v29;
        v34 = a2 - v27;
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
        {
          WPP_SF_dd(v25[2], 264, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v34, v33);
          v25 = (PVOID *)WPP_GLOBAL_Control;
          v30 = a3;
        }
        v35 = *(char **)(*(_QWORD *)(v30 + 8) + 16LL * v28 + 8);
        if ( v33 >= v34 )
        {
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
            WPP_SF_d(v25[2], 266, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v28);
          pbData = hMem;
          memcpy_0(v35, &hMem[v27], v34);
          v25 = (PVOID *)WPP_GLOBAL_Control;
          v27 = a2;
          v29 = v34;
          goto LABEL_78;
        }
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 4) != 0 )
          WPP_SF_d(v25[2], 265, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v28);
        memcpy_0(&v35[v29], &hMem[v27], v33);
        v27 += v33;
      }
      else
      {
        if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 4) == 0 )
          goto LABEL_77;
        WPP_SF_d(v25[2], 263, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v28);
      }
      v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_77:
      pbData = hMem;
      ++v28;
      v29 = 0;
LABEL_78:
      v7 = a3;
      if ( v27 == a2 )
        goto LABEL_79;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, LastError);
  }
  v12 = -1073741595;
LABEL_89:
  DigestFreeMemory(pbData);
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_90:
  if ( v11 != &WPP_GLOBAL_Control && *((char *)v11 + 28) < 0 )
    WPP_SF_d(v11[2], 269, &WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180030628  mov     rax, rsp
0x18003062b  mov     [rax+10h], rbx
0x18003062f  mov     [rax+20h], r9
0x180030633  mov     [rax+18h], r8
0x180030637  mov     [rax+8], rcx
0x18003063b  push    rbp
0x18003063c  push    rsi
0x18003063d  push    rdi
0x18003063e  push    r12
0x180030640  push    r13
0x180030642  push    r14
0x180030644  push    r15
0x180030646  sub     rsp, 50h
0x18003064a  mov     rbp, r9
0x18003064d  mov     dword ptr [rax+38h], 0
0x180030654  mov     r15, r8
0x180030657  mov     edi, edx
0x180030659  mov     r13, rcx
0x18003065c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030663  lea     r12, WPP_GLOBAL_Control
0x18003066a  cmp     rcx, r12
0x18003066d  jz      short loc_18003068A
0x18003066f  test    byte ptr [rcx+1Ch], 80h
0x180030673  jz      short loc_18003068A
0x180030675  mov     rcx, [rcx+10h]
0x180030679  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030680  mov     edx, 0FBh
0x180030685  call    WPP_SF_
0x18003068a  mov     ecx, edi; Size
0x18003068c  call    DigestAllocateMemory
0x180030691  mov     [rsp+88h+hMem], rax
0x180030696  mov     r14, rax
0x180030699  test    rax, rax
0x18003069c  jnz     short loc_1800306D7
0x18003069e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306a5  cmp     rcx, r12
0x1800306a8  jz      short loc_1800306CC
0x1800306aa  test    byte ptr [rcx+1Ch], 1
0x1800306ae  jz      short loc_1800306CC
0x1800306b0  mov     rcx, [rcx+10h]
0x1800306b4  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800306bb  mov     edx, 0FCh
0x1800306c0  call    WPP_SF_
0x1800306c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306cc  mov     r13d, 80090300h
0x1800306d2  jmp     loc_180030C03
0x1800306d7  mov     r12, [rsp+88h+arg_20]
0x1800306df  xor     esi, esi
0x1800306e1  mov     ebx, [rbp+0]
0x1800306e4  mov     r12d, [r12]
0x1800306e8  test    edi, edi
0x1800306ea  jz      loc_180030916
0x1800306f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306f7  lea     r13, WPP_GLOBAL_Control
0x1800306fe  cmp     ebx, [r15+4]
0x180030702  jnb     loc_180030882
0x180030708  cmp     rcx, r13
0x18003070b  jz      short loc_180030736
0x18003070d  test    byte ptr [rcx+1Ch], 4
0x180030711  jz      short loc_180030736
0x180030713  mov     rcx, [rcx+10h]
0x180030717  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18003071e  mov     edx, 0FDh
0x180030723  mov     dword ptr [rsp+88h+pbData], edi
0x180030727  mov     r9d, esi
0x18003072a  call    WPP_SF_dd
0x18003072f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030736  mov     rbp, [r15+8]
0x18003073a  mov     r14d, ebx
0x18003073d  add     r14, r14
0x180030740  cmp     dword ptr [rbp+r14*8+4], 1
0x180030746  jnz     loc_180030844
0x18003074c  mov     ebp, [rbp+r14*8+0]
0x180030751  test    ebp, ebp
0x180030753  jz      loc_180030844
0x180030759  sub     ebp, r12d
0x18003075c  mov     r15d, edi
0x18003075f  sub     r15d, esi
0x180030762  cmp     rcx, r13
0x180030765  jz      short loc_180030790
0x180030767  test    byte ptr [rcx+1Ch], 4
0x18003076b  jz      short loc_180030790
0x18003076d  mov     rcx, [rcx+10h]
0x180030771  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030778  mov     edx, 0FFh
0x18003077d  mov     dword ptr [rsp+88h+pbData], ebp
0x180030781  mov     r9d, r15d
0x180030784  call    WPP_SF_dd
0x180030789  mov     rcx, cs:WPP_GLOBAL_Control
0x180030790  mov     rax, [rsp+88h+arg_10]
0x180030798  mov     rax, [rax+8]
0x18003079c  mov     r14, [rax+r14*8+8]
0x1800307a1  cmp     ebp, r15d
0x1800307a4  jnb     short loc_1800307F4
0x1800307a6  cmp     rcx, r13
0x1800307a9  jz      short loc_1800307C9
0x1800307ab  test    byte ptr [rcx+1Ch], 4
0x1800307af  jz      short loc_1800307C9
0x1800307b1  mov     rcx, [rcx+10h]
0x1800307b5  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800307bc  mov     edx, 100h
0x1800307c1  mov     r9d, ebx
0x1800307c4  call    WPP_SF_d
0x1800307c9  mov     edx, r12d
0x1800307cc  add     rdx, r14; Src
0x1800307cf  mov     ecx, esi
0x1800307d1  mov     r14, [rsp+88h+hMem]
0x1800307d6  add     rcx, r14; void *
0x1800307d9  mov     r8d, ebp; Size
0x1800307dc  call    memcpy_0
0x1800307e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307e8  add     esi, ebp
0x1800307ea  mov     r15, [rsp+88h+arg_10]
0x1800307f2  jmp     short loc_180030873
0x1800307f4  cmp     rcx, r13
0x1800307f7  jz      short loc_180030817
0x1800307f9  test    byte ptr [rcx+1Ch], 4
0x1800307fd  jz      short loc_180030817
0x1800307ff  mov     rcx, [rcx+10h]
0x180030803  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18003080a  mov     edx, 101h
0x18003080f  mov     r9d, ebx
0x180030812  call    WPP_SF_d
0x180030817  mov     ecx, esi
0x180030819  mov     rdx, r14; Src
0x18003081c  add     rcx, [rsp+88h+hMem]; void *
0x180030821  mov     r8d, r15d; Size
0x180030824  call    memcpy_0
0x180030829  mov     rcx, cs:WPP_GLOBAL_Control
0x180030830  mov     r12d, r15d
0x180030833  mov     r15, [rsp+88h+arg_10]
0x18003083b  mov     esi, edi
0x18003083d  mov     r14, [rsp+88h+hMem]
0x180030842  jmp     short loc_180030878
0x180030844  cmp     rcx, r13
0x180030847  jz      short loc_18003086E
0x180030849  test    byte ptr [rcx+1Ch], 4
0x18003084d  jz      short loc_18003086E
0x18003084f  mov     rcx, [rcx+10h]
0x180030853  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x18003085a  mov     edx, 0FEh
0x18003085f  mov     r9d, ebx
0x180030862  call    WPP_SF_d
0x180030867  mov     rcx, cs:WPP_GLOBAL_Control
0x18003086e  mov     r14, [rsp+88h+hMem]
0x180030873  inc     ebx
0x180030875  xor     r12d, r12d
0x180030878  cmp     esi, edi
0x18003087a  jnz     loc_1800306FE
0x180030880  jmp     short loc_180030887
0x180030882  mov     r14, [rsp+88h+hMem]
0x180030887  mov     r13, [rsp+88h+hKey]
0x18003088f  cmp     esi, edi
0x180030891  jnb     short loc_18003090E
0x180030893  lea     r12, WPP_GLOBAL_Control
0x18003089a  cmp     rcx, r12
0x18003089d  jz      short loc_1800308C8
0x18003089f  test    byte ptr [rcx+1Ch], 4
0x1800308a3  jz      short loc_1800308C8
0x1800308a5  mov     rcx, [rcx+10h]
0x1800308a9  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800308b0  mov     edx, 102h
0x1800308b5  mov     dword ptr [rsp+88h+pbData], edi
0x1800308b9  mov     r9d, esi
0x1800308bc  call    WPP_SF_dd
0x1800308c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308c8  mov     ebx, edi
0x1800308ca  sub     ebx, esi
0x1800308cc  cmp     rcx, r12
0x1800308cf  jz      short loc_1800308EF
0x1800308d1  test    byte ptr [rcx+1Ch], 4
0x1800308d5  jz      short loc_1800308EF
0x1800308d7  mov     rcx, [rcx+10h]
0x1800308db  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800308e2  mov     edx, 103h
0x1800308e7  mov     r9d, ebx
0x1800308ea  call    WPP_SF_d
0x1800308ef  mov     rdx, [rsp+88h+Src]; Src
0x1800308f7  mov     ecx, esi
0x1800308f9  add     rcx, r14; void *
0x1800308fc  mov     r8d, ebx; Size
0x1800308ff  call    memcpy_0
0x180030904  mov     rbp, [rsp+88h+arg_18]
0x18003090c  jmp     short loc_18003091D
0x18003090e  mov     rbp, [rsp+88h+arg_18]
0x180030916  lea     r12, WPP_GLOBAL_Control
0x18003091d  lea     rax, [rsp+88h+arg_30]
0x180030925  mov     [rsp+88h+dwBufLen], edi; dwBufLen
0x180030929  mov     [rsp+88h+pdwDataLen], rax; pdwDataLen
0x18003092e  xor     r9d, r9d; dwFlags
0x180030931  xor     r8d, r8d; Final
0x180030934  mov     [rsp+88h+pbData], r14; pbData
0x180030939  xor     edx, edx; hHash
0x18003093b  mov     dword ptr [rsp+88h+arg_30], edi
0x180030942  mov     rcx, r13; hKey
0x180030945  call    cs:__imp_CryptEncrypt
0x18003094b  test    eax, eax
0x18003094d  jnz     short loc_180030991
0x18003094f  mov     rax, cs:WPP_GLOBAL_Control
0x180030956  cmp     rax, r12
0x180030959  jz      short loc_180030986
0x18003095b  test    byte ptr [rax+1Ch], 1
0x18003095f  jz      short loc_180030986
0x180030961  call    cs:__imp_GetLastError
0x180030967  mov     rcx, cs:WPP_GLOBAL_Control
0x18003096e  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030975  mov     edx, 104h
0x18003097a  mov     r9d, eax
0x18003097d  mov     rcx, [rcx+10h]
0x180030981  call    WPP_SF_d
0x180030986  mov     r13d, 0C00000E5h
0x18003098c  jmp     loc_180030BF4
0x180030991  mov     rcx, cs:WPP_GLOBAL_Control
0x180030998  xor     r13d, r13d
0x18003099b  mov     [rsp+88h+var_48], r13d
0x1800309a0  cmp     rcx, r12
0x1800309a3  jz      short loc_1800309C7
0x1800309a5  test    byte ptr [rcx+1Ch], 4
0x1800309a9  jz      short loc_1800309C7
0x1800309ab  mov     rcx, [rcx+10h]
0x1800309af  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x1800309b6  mov     edx, 105h
0x1800309bb  call    WPP_SF_
0x1800309c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309c7  mov     r12, [rsp+88h+arg_20]
0x1800309cf  xor     esi, esi
0x1800309d1  mov     ebp, [rbp+0]
0x1800309d4  mov     ebx, [r12]
0x1800309d8  test    edi, edi
0x1800309da  jz      loc_180030BDF
0x1800309e0  lea     r13, WPP_GLOBAL_Control
0x1800309e7  cmp     ebp, [r15+4]
0x1800309eb  jnb     loc_180030B5D
0x1800309f1  cmp     rcx, r13
0x1800309f4  jz      short loc_180030A1F
0x1800309f6  test    byte ptr [rcx+1Ch], 4
0x1800309fa  jz      short loc_180030A1F
0x1800309fc  mov     rcx, [rcx+10h]
0x180030a00  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030a07  mov     edx, 106h
0x180030a0c  mov     dword ptr [rsp+88h+pbData], edi
0x180030a10  mov     r9d, esi
0x180030a13  call    WPP_SF_dd
0x180030a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a1f  mov     rax, [rsp+88h+arg_10]
0x180030a27  mov     r15d, ebp
0x180030a2a  add     r15, r15
0x180030a2d  mov     r14, [rax+8]
0x180030a31  cmp     dword ptr [r14+r15*8+4], 1
0x180030a37  jnz     loc_180030B1A
0x180030a3d  mov     r14d, [r14+r15*8]
0x180030a41  test    r14d, r14d
0x180030a44  jz      loc_180030B1A
0x180030a4a  sub     r14d, ebx
0x180030a4d  mov     r12d, edi
0x180030a50  sub     r12d, esi
0x180030a53  cmp     rcx, r13
0x180030a56  jz      short loc_180030A8A
0x180030a58  test    byte ptr [rcx+1Ch], 4
0x180030a5c  jz      short loc_180030A8A
0x180030a5e  mov     rcx, [rcx+10h]
0x180030a62  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030a69  mov     edx, 108h
0x180030a6e  mov     dword ptr [rsp+88h+pbData], r14d
0x180030a73  mov     r9d, r12d
0x180030a76  call    WPP_SF_dd
0x180030a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a82  mov     rax, [rsp+88h+arg_10]
0x180030a8a  mov     rax, [rax+8]
0x180030a8e  mov     r15, [rax+r15*8+8]
0x180030a93  cmp     r14d, r12d
0x180030a96  jnb     short loc_180030AD4
0x180030a98  cmp     rcx, r13
0x180030a9b  jz      short loc_180030ABB
0x180030a9d  test    byte ptr [rcx+1Ch], 4
0x180030aa1  jz      short loc_180030ABB
0x180030aa3  mov     rcx, [rcx+10h]
0x180030aa7  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030aae  mov     edx, 109h
0x180030ab3  mov     r9d, ebp
0x180030ab6  call    WPP_SF_d
0x180030abb  mov     edx, esi
0x180030abd  add     rdx, [rsp+88h+hMem]; Src
0x180030ac2  mov     ecx, ebx
0x180030ac4  add     rcx, r15; void *
0x180030ac7  mov     r8d, r14d; Size
0x180030aca  call    memcpy_0
0x180030acf  add     esi, r14d
0x180030ad2  jmp     short loc_180030B3D
0x180030ad4  cmp     rcx, r13
0x180030ad7  jz      short loc_180030AF7
0x180030ad9  test    byte ptr [rcx+1Ch], 4
0x180030add  jz      short loc_180030AF7
0x180030adf  mov     rcx, [rcx+10h]
0x180030ae3  lea     r8, WPP_3a9703e229fb3d42fb846768cfaf323c_Traceguids
0x180030aea  mov     edx, 10Ah
0x180030aef  mov     r9d, ebp
0x180030af2  call    WPP_SF_d
0x180030af7  mov     r14, [rsp+88h+hMem]
0x180030afc  mov     rcx, r15; void *
  ... truncated ...
```
