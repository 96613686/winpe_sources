# VsmmVsmIoctlSetPartitionConfig

- ea: `0x1400ae3c0`
- end: `0x1400aeca5`
- name: `VsmmVsmIoctlSetPartitionConfig`
- size: `2277`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400347a4`
- `0x140034b64`
- `0x1400356c4`
- `0x1400386a0`
- `0x1400ae3c0`
- `0x1400aff24`
- `0x1400b0570`

## string_xrefs

- `0x1400ae42b`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae483`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae533`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae59b`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae5ed`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae67c`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae718`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae756`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae7e6`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae8e7`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae90a`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae92d`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae950`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ae989`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aea1e`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aea41`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aea64`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aea87`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aeb75`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aec94`: `VsmmVsmIoctlSetPartitionConfig`

## pseudocode

```c
__int64 __fastcall VsmmVsmIoctlSetPartitionConfig(__int64 a1, unsigned int a2, unsigned int *a3)
{
  unsigned __int64 v3; // rsi
  __int64 v4; // rbx
  unsigned int v6; // r10d
  int v7; // ebx
  unsigned int v8; // r8d
  bool v9; // zf
  int v10; // r13d
  __int64 v11; // r11
  char *v12; // rdx
  unsigned int *v13; // rax
  __int64 v14; // r11
  int v15; // r14d
  __int64 v16; // r11
  __int64 v17; // r9
  int v18; // r14d
  __int64 v19; // r11
  unsigned __int64 v20; // rdx
  int v21; // eax
  unsigned __int8 i; // r12
  unsigned __int8 v23; // dl
  unsigned __int8 v24; // cl
  int v25; // eax
  unsigned __int8 v26; // al
  unsigned int j; // eax
  unsigned int v28; // eax
  int v29; // eax
  __int64 PartitionVtlInfo; // rax
  int v31; // r8d
  int v32; // r12d
  __int64 v33; // r8
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v37; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v38; // [rsp+38h] [rbp-C8h] BYREF
  char v39; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v42[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v43[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  unsigned int *v47; // [rsp+A0h] [rbp-60h]
  __int64 v48; // [rsp+A8h] [rbp-58h]
  unsigned int *v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  _DWORD *v51; // [rsp+C0h] [rbp-40h]
  __int64 v52; // [rsp+C8h] [rbp-38h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  _DWORD v54[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v55; // [rsp+E0h] [rbp-20h]
  __int64 v56; // [rsp+E8h] [rbp-18h]
  unsigned int *v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]

  v3 = a2;
  v4 = a1;
  v40 = a1;
  v36 = a2;
  v41 = a1 + 3736;
  VidObjectLockAcquireExclusive(a1 + 3736);
  v6 = 0;
  if ( (unsigned int)v3 < 8 )
  {
    v7 = -1073741789;
    VidTraceErrorInternal0("VsmmVsmIoctlSetPartitionConfig", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1395);
    goto LABEL_81;
  }
  v8 = *a3;
  v9 = !_BitScanReverse((unsigned int *)&v10, *a3);
  v38 = 0;
  if ( v9 )
  {
    v7 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
      tlgCreate1Sz_char(v44, v11);
      v36 = 1405;
      v45 = &v36;
      v12 = (char *)qword_14004DFE8;
      v37 = *a3;
      v13 = &v37;
LABEL_7:
      v48 = 4;
LABEL_8:
      v47 = v13;
      v35 = 6;
LABEL_9:
      v46 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v12, 0, 0, v35, v42);
    }
  }
  else if ( (unsigned __int8)v10 < 3u )
  {
    if ( v3 < 16 * (unsigned __int64)(unsigned __int8)v10 + 8 )
    {
      v7 = -1073741789;
      VidTraceErrorInternal0("VsmmVsmIoctlSetPartitionConfig", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1421);
      goto LABEL_81;
    }
    v15 = *(_DWORD *)(v4 + 8776);
    if ( (~v8 & v15) != 0 )
    {
      v7 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
        tlgCreate1Sz_char(v44, v16);
        v37 = 1431;
        v45 = &v37;
        v12 = byte_14004E07D;
        v36 = *a3;
        v13 = &v36;
        goto LABEL_7;
      }
    }
    else
    {
      v17 = a3[1];
      v18 = v8 & ~v15;
      v38 = v17;
      if ( (~v18 & (unsigned int)v17) != 0 )
      {
        v7 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
          tlgCreate1Sz_char(v44, v19);
          v37 = 1444;
          v45 = &v37;
          v12 = byte_14004DED9;
          v36 = a3[1];
          v47 = &v36;
          v38 = *a3;
          v49 = &v38;
          v35 = 7;
          v48 = 4;
          v50 = 4;
          goto LABEL_9;
        }
      }
      else if ( v18 )
      {
        v20 = *(_QWORD *)(v4 + 16);
        if ( (v20 & 8) != 0 )
        {
          v21 = (v20 >> 3) & 2 | 5;
          if ( (v20 & 0x20) == 0 )
            v21 = (v20 >> 3) & 2 | 1;
          if ( (~v21 & v8) != 0 )
          {
            v7 = -1073741811;
            VidTraceErrorInternal0("VsmmVsmIoctlSetPartitionConfig", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1479);
          }
          else
          {
            if ( (_BYTE)v10 )
            {
              for ( i = 1; i <= (unsigned __int8)v10; ++i )
              {
                if ( ((1 << i) & v18) != 0 )
                {
                  v23 = *((_BYTE *)&a3[4 * i - 1] - 3);
                  if ( v23 >= 4u || *((_WORD *)&a3[4 * i - 1] - 1) )
                  {
                    v7 = -1073741811;
                    VidTraceErrorInternal0(
                      "VsmmVsmIoctlSetPartitionConfig",
                      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                      1496);
                    goto LABEL_80;
                  }
                  v24 = a3[4 * i - 2];
                  if ( v24 > 2u )
                  {
                    v7 = -1073741811;
                    VidTraceErrorInternal0(
                      "VsmmVsmIoctlSetPartitionConfig",
                      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                      1503);
                    goto LABEL_80;
                  }
                  if ( v24 == 2 )
                    goto LABEL_43;
                  if ( *(_QWORD *)&a3[4 * i] )
                  {
                    v7 = -1073741811;
                    VidTraceErrorInternal0(
                      "VsmmVsmIoctlSetPartitionConfig",
                      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                      1511);
                    goto LABEL_80;
                  }
                  if ( v24 )
                  {
LABEL_43:
                    if ( (*(_DWORD *)(v4 + 32) & 0x31E0LL) != 0 )
                    {
                      v7 = -1073741811;
                      VidTraceErrorInternal0(
                        "VsmmVsmIoctlSetPartitionConfig",
                        "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                        1532);
                      goto LABEL_80;
                    }
                    if ( v24 == 2 && a3[4 * i - 1] == 15 )
                    {
                      v7 = -1073741811;
                      VidTraceErrorInternal0(
                        "VsmmVsmIoctlSetPartitionConfig",
                        "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                        1540);
                      goto LABEL_80;
                    }
                    if ( (v23 & 1) != 0 && (i != 1 || !*(_BYTE *)(v4 + 8784)) )
                    {
                      v7 = -1073741811;
                      VidTraceErrorInternal0(
                        "VsmmVsmIoctlSetPartitionConfig",
                        "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                        1548);
                      goto LABEL_80;
                    }
                    if ( (v23 & 2) != 0 && (i != 1 || !*(_BYTE *)(v4 + 8785)) )
                    {
                      v7 = -1073741811;
                      VidTraceErrorInternal0(
                        "VsmmVsmIoctlSetPartitionConfig",
                        "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                        1556);
                      goto LABEL_80;
                    }
                    LOBYTE(v20) = i;
                    LOBYTE(v17) = ((1 << i) & (unsigned int)v17) != 0;
                    v25 = VsmmVsmpValidateDefaultVtlProtection(v4, v20, a3[4 * i - 1], v17);
                    v6 = 0;
                    v7 = v25;
                    if ( v25 < 0 )
                    {
                      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
                      {
                        tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
                        tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
                        v38 = 1567;
                        v45 = &v38;
                        v37 = a3[4 * i - 1];
                        v46 = 4;
                        v47 = &v37;
                        v48 = 4;
                        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_14004DD7E, 0, 0, 6, v42);
                      }
                      goto LABEL_80;
                    }
                    v4 = v40;
                    v17 = v38;
                  }
                  else if ( a3[4 * i - 1] != 15 )
                  {
                    v7 = -1073741811;
                    VidTraceErrorInternal0(
                      "VsmmVsmIoctlSetPartitionConfig",
                      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                      1520);
                    goto LABEL_80;
                  }
                }
                else if ( LOBYTE(a3[4 * i - 2])
                       || (v26 = *((_BYTE *)&a3[4 * i - 1] - 3), (v26 & 3) != 0)
                       || v26 >= 4u
                       || *((_WORD *)&a3[4 * i - 1] - 1)
                       || a3[4 * i - 1]
                       || *(_QWORD *)&a3[4 * i] )
                {
                  v7 = -1073741811;
                  VidTraceErrorInternal0(
                    "VsmmVsmIoctlSetPartitionConfig",
                    "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
                    1583);
                  goto LABEL_80;
                }
              }
            }
            for ( j = v18 & 0xFFFFFFFE; ; j = v18 & ~((1 << v32) | ((1 << v32) - 1)) )
            {
              v9 = !_BitScanForward((unsigned int *)&v32, j);
              v38 = v6;
              if ( v9 )
              {
                v7 = v6;
                goto LABEL_80;
              }
              v28 = v6;
              LOBYTE(v20) = v32;
              LOBYTE(v28) = ((1 << v32) & a3[1]) != 0;
              v29 = VsmmVsmpEnablePartitionVtl(
                      v4,
                      v20,
                      v28 | (2 * (*((_BYTE *)&a3[4 * (unsigned __int8)v32 - 1] - 3) & 3)));
              v6 = 0;
              v7 = v29;
              if ( v29 < 0 )
                break;
              v4 = v40;
              if ( LOBYTE(a3[4 * (unsigned __int8)v32 - 2]) )
              {
                LOBYTE(v20) = v32;
                PartitionVtlInfo = VsmmVsmpGetPartitionVtlInfo(v40, v20);
                *(_DWORD *)PartitionVtlInfo = v31;
                *(_DWORD *)(PartitionVtlInfo + 8) = a3[4 * (unsigned __int8)v32 - 1];
                if ( LOBYTE(a3[4 * (unsigned __int8)v32 - 2]) == 2 )
                  *(_QWORD *)(PartitionVtlInfo + 16) = *(_QWORD *)&a3[4 * (unsigned __int8)v32];
              }
            }
            VidTraceErrorInternal0("VsmmVsmIoctlSetPartitionConfig", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1611);
LABEL_80:
            LODWORD(v3) = v36;
          }
        }
        else
        {
          v7 = -1073741637;
          VidTraceErrorInternal0("VsmmVsmIoctlSetPartitionConfig", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1460);
        }
      }
      else
      {
        v7 = 0;
      }
    }
  }
  else
  {
    v7 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
      tlgCreate1Sz_char(v44, v14);
      v37 = 1412;
      v45 = &v37;
      v12 = (char *)&dword_14004E034;
      v13 = (unsigned int *)&v39;
      v39 = v10;
      v48 = 1;
      goto LABEL_8;
    }
  }
LABEL_81:
  VidObjectLockRelease(v41);
  if ( v7 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
    v45 = &v38;
    v38 = 1638;
    v47 = &v37;
    v46 = 4;
    v49 = (unsigned int *)(v40 + 656);
    v51 = v54;
    v53 = *(_QWORD *)(v40 + 128);
    v54[0] = *(unsigned __int16 *)(v40 + 120);
    v41 = *(_QWORD *)(v40 + 648);
    v55 = &v41;
    v57 = &v36;
    v37 = v7;
    v48 = 4;
    v50 = 16;
    v52 = 2;
    v54[1] = v33;
    v56 = 8;
    v36 = v3;
    v58 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_14004DDD9, v33, 0, 11, v42);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400ae3c0  mov     [rsp-8+arg_8], rbx
0x1400ae3c5  mov     [rsp-8+arg_18], rsi
0x1400ae3ca  push    rbp
0x1400ae3cb  push    rdi
0x1400ae3cc  push    r12
0x1400ae3ce  push    r13
0x1400ae3d0  push    r14
0x1400ae3d2  lea     rbp, [rsp-10h]
0x1400ae3d7  sub     rsp, 110h
0x1400ae3de  mov     rax, cs:__security_cookie
0x1400ae3e5  xor     rax, rsp
0x1400ae3e8  mov     [rbp+30h+var_30], rax
0x1400ae3ec  lea     rax, [rcx+0E98h]
0x1400ae3f3  mov     esi, edx
0x1400ae3f5  mov     rbx, rcx
0x1400ae3f8  mov     [rsp+130h+var_F0], rcx
0x1400ae3fd  mov     rcx, rax
0x1400ae400  mov     [rsp+130h+var_100], esi
0x1400ae404  mov     rdi, r8
0x1400ae407  mov     [rsp+130h+var_E8], rax
0x1400ae40c  call    VidObjectLockAcquireExclusive
0x1400ae411  xor     r10d, r10d
0x1400ae414  lea     r11, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae41b  cmp     esi, 8
0x1400ae41e  jnb     short loc_1400AE43F
0x1400ae420  mov     ebx, 0C0000023h
0x1400ae425  mov     r8d, 573h
0x1400ae42b  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae432  mov     rdx, r11
0x1400ae435  call    VidTraceErrorInternal0
0x1400ae43a  jmp     loc_1400AEB38
0x1400ae43f  mov     r8d, [rdi]
0x1400ae442  bsr     r13d, r8d
0x1400ae446  mov     [rsp+130h+var_F8], r10d
0x1400ae44b  setnz   al
0x1400ae44e  test    al, al
0x1400ae450  jnz     loc_1400AE500
0x1400ae456  mov     eax, cs:dword_140065110
0x1400ae45c  mov     ebx, 0C000000Dh
0x1400ae461  cmp     eax, 2
0x1400ae464  jbe     loc_1400AEB38
0x1400ae46a  mov     edx, 100h
0x1400ae46f  lea     rcx, dword_140065110
0x1400ae476  call    _tlgKeywordOn
0x1400ae47b  test    al, al
0x1400ae47d  jz      loc_1400AEB38
0x1400ae483  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae48a  lea     rcx, [rsp+130h+var_C0]
0x1400ae48f  call    _tlgCreate1Sz_char
0x1400ae494  mov     rdx, r11
0x1400ae497  lea     rcx, [rbp+30h+var_B0]
0x1400ae49b  call    _tlgCreate1Sz_char
0x1400ae4a0  lea     rax, [rsp+130h+var_100]
0x1400ae4a5  mov     [rsp+130h+var_100], 57Dh
0x1400ae4ad  mov     [rbp+30h+var_A0], rax
0x1400ae4b1  lea     rdx, qword_14004DFE8
0x1400ae4b8  mov     eax, [rdi]
0x1400ae4ba  mov     [rsp+130h+var_FC], eax
0x1400ae4be  lea     rax, [rsp+130h+var_FC]
0x1400ae4c3  mov     [rbp+30h+var_88], 4
0x1400ae4cb  mov     [rbp+30h+var_90], rax
0x1400ae4cf  lea     rax, [rsp+130h+var_E0]
0x1400ae4d4  mov     [rsp+130h+var_108], rax
0x1400ae4d9  mov     [rsp+130h+var_110], 6
0x1400ae4e1  xor     r9d, r9d
0x1400ae4e4  mov     [rbp+30h+var_98], 4
0x1400ae4ec  xor     r8d, r8d
0x1400ae4ef  lea     rcx, dword_140065110
0x1400ae4f6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ae4fb  jmp     loc_1400AEB38
0x1400ae500  cmp     r13b, 3
0x1400ae504  jb      short loc_1400AE57F
0x1400ae506  mov     eax, cs:dword_140065110
0x1400ae50c  mov     ebx, 0C000000Dh
0x1400ae511  cmp     eax, 2
0x1400ae514  jbe     loc_1400AEB38
0x1400ae51a  mov     edx, 100h
0x1400ae51f  lea     rcx, dword_140065110
0x1400ae526  call    _tlgKeywordOn
0x1400ae52b  test    al, al
0x1400ae52d  jz      loc_1400AEB38
0x1400ae533  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae53a  lea     rcx, [rsp+130h+var_C0]
0x1400ae53f  call    _tlgCreate1Sz_char
0x1400ae544  mov     rdx, r11
0x1400ae547  lea     rcx, [rbp+30h+var_B0]
0x1400ae54b  call    _tlgCreate1Sz_char
0x1400ae550  lea     rax, [rsp+130h+var_FC]
0x1400ae555  mov     [rsp+130h+var_FC], 584h
0x1400ae55d  mov     [rbp+30h+var_A0], rax
0x1400ae561  lea     rdx, dword_14004E034
0x1400ae568  lea     rax, [rsp+130h+var_F4]
0x1400ae56d  mov     [rsp+130h+var_F4], r13b
0x1400ae572  mov     [rbp+30h+var_88], 1
0x1400ae57a  jmp     loc_1400AE4CB
0x1400ae57f  movzx   ecx, r13b
0x1400ae583  shl     rcx, 4
0x1400ae587  add     rcx, 8
0x1400ae58b  cmp     rsi, rcx
0x1400ae58e  jnb     short loc_1400AE5AF
0x1400ae590  mov     ebx, 0C0000023h
0x1400ae595  mov     r8d, 58Dh
0x1400ae59b  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae5a2  mov     rdx, r11
0x1400ae5a5  call    VidTraceErrorInternal0
0x1400ae5aa  jmp     loc_1400AEB38
0x1400ae5af  mov     r14d, [rbx+2248h]
0x1400ae5b6  mov     eax, r8d
0x1400ae5b9  not     eax
0x1400ae5bb  test    r14d, eax
0x1400ae5be  jz      short loc_1400AE632
0x1400ae5c0  mov     eax, cs:dword_140065110
0x1400ae5c6  mov     ebx, 0C000000Dh
0x1400ae5cb  cmp     eax, 2
0x1400ae5ce  jbe     loc_1400AEB38
0x1400ae5d4  mov     edx, 100h
0x1400ae5d9  lea     rcx, dword_140065110
0x1400ae5e0  call    _tlgKeywordOn
0x1400ae5e5  test    al, al
0x1400ae5e7  jz      loc_1400AEB38
0x1400ae5ed  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae5f4  lea     rcx, [rsp+130h+var_C0]
0x1400ae5f9  call    _tlgCreate1Sz_char
0x1400ae5fe  mov     rdx, r11
0x1400ae601  lea     rcx, [rbp+30h+var_B0]
0x1400ae605  call    _tlgCreate1Sz_char
0x1400ae60a  lea     rax, [rsp+130h+var_FC]
0x1400ae60f  mov     [rsp+130h+var_FC], 597h
0x1400ae617  mov     [rbp+30h+var_A0], rax
0x1400ae61b  lea     rdx, byte_14004E07D
0x1400ae622  mov     eax, [rdi]
0x1400ae624  mov     [rsp+130h+var_100], eax
0x1400ae628  lea     rax, [rsp+130h+var_100]
0x1400ae62d  jmp     loc_1400AE4C3
0x1400ae632  mov     r9d, [rdi+4]
0x1400ae636  not     r14d
0x1400ae639  and     r14d, r8d
0x1400ae63c  mov     [rsp+130h+var_F8], r9d
0x1400ae641  mov     eax, r14d
0x1400ae644  not     eax
0x1400ae646  test    r9d, eax
0x1400ae649  jz      loc_1400AE6F7
0x1400ae64f  mov     eax, cs:dword_140065110
0x1400ae655  mov     ebx, 0C000000Dh
0x1400ae65a  cmp     eax, 2
0x1400ae65d  jbe     loc_1400AEB38
0x1400ae663  mov     edx, 100h
0x1400ae668  lea     rcx, dword_140065110
0x1400ae66f  call    _tlgKeywordOn
0x1400ae674  test    al, al
0x1400ae676  jz      loc_1400AEB38
0x1400ae67c  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae683  lea     rcx, [rsp+130h+var_C0]
0x1400ae688  call    _tlgCreate1Sz_char
0x1400ae68d  mov     rdx, r11
0x1400ae690  lea     rcx, [rbp+30h+var_B0]
0x1400ae694  call    _tlgCreate1Sz_char
0x1400ae699  lea     rax, [rsp+130h+var_FC]
0x1400ae69e  mov     [rsp+130h+var_FC], 5A4h
0x1400ae6a6  mov     [rbp+30h+var_A0], rax
0x1400ae6aa  lea     rdx, byte_14004DED9
0x1400ae6b1  mov     eax, [rdi+4]
0x1400ae6b4  mov     [rsp+130h+var_100], eax
0x1400ae6b8  lea     rax, [rsp+130h+var_100]
0x1400ae6bd  mov     [rbp+30h+var_90], rax
0x1400ae6c1  mov     eax, [rdi]
0x1400ae6c3  mov     [rsp+130h+var_F8], eax
0x1400ae6c7  lea     rax, [rsp+130h+var_F8]
0x1400ae6cc  mov     [rbp+30h+var_80], rax
0x1400ae6d0  lea     rax, [rsp+130h+var_E0]
0x1400ae6d5  mov     [rsp+130h+var_108], rax
0x1400ae6da  mov     [rsp+130h+var_110], 7
0x1400ae6e2  mov     [rbp+30h+var_88], 4
0x1400ae6ea  mov     [rbp+30h+var_78], 4
0x1400ae6f2  jmp     loc_1400AE4E1
0x1400ae6f7  test    r14d, r14d
0x1400ae6fa  jnz     short loc_1400AE704
0x1400ae6fc  mov     ebx, r10d
0x1400ae6ff  jmp     loc_1400AEB38
0x1400ae704  mov     rdx, [rbx+10h]
0x1400ae708  test    dl, 8
0x1400ae70b  jnz     short loc_1400AE72C
0x1400ae70d  mov     ebx, 0C00000BBh
0x1400ae712  mov     r8d, 5B4h
0x1400ae718  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae71f  mov     rdx, r11
0x1400ae722  call    VidTraceErrorInternal0
0x1400ae727  jmp     loc_1400AEB38
0x1400ae72c  mov     rcx, rdx
0x1400ae72f  shr     rcx, 3
0x1400ae733  and     ecx, 2
0x1400ae736  or      ecx, 1
0x1400ae739  mov     eax, ecx
0x1400ae73b  or      eax, 4
0x1400ae73e  test    dl, 20h
0x1400ae741  cmovz   eax, ecx
0x1400ae744  not     eax
0x1400ae746  test    r8d, eax
0x1400ae749  jz      short loc_1400AE76A
0x1400ae74b  mov     ebx, 0C000000Dh
0x1400ae750  mov     r8d, 5C7h
0x1400ae756  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae75d  mov     rdx, r11
0x1400ae760  call    VidTraceErrorInternal0
0x1400ae765  jmp     loc_1400AEB38
0x1400ae76a  cmp     r13b, 1
0x1400ae76e  jb      loc_1400AE8CA
0x1400ae774  mov     r12b, 1
0x1400ae777  movzx   esi, r12b
0x1400ae77b  mov     cl, r12b
0x1400ae77e  mov     r8d, 1
0x1400ae784  add     rsi, rsi
0x1400ae787  shl     r8d, cl
0x1400ae78a  test    r14d, r8d
0x1400ae78d  jz      loc_1400AE87E
0x1400ae793  mov     dl, [rdi+rsi*8-7]
0x1400ae797  cmp     dl, 4
0x1400ae79a  jnb     loc_1400AEA52
0x1400ae7a0  cmp     [rdi+rsi*8-6], r10w
0x1400ae7a6  jnz     loc_1400AEA52
0x1400ae7ac  mov     cl, [rdi+rsi*8-8]
0x1400ae7b0  cmp     cl, 2
0x1400ae7b3  ja      loc_1400AEA2F
0x1400ae7b9  jz      short loc_1400AE7F7
0x1400ae7bb  cmp     [rdi+rsi*8], r10
0x1400ae7bf  jnz     loc_1400AE8D5
0x1400ae7c5  test    cl, cl
0x1400ae7c7  jnz     short loc_1400AE7F7
0x1400ae7c9  cmp     dword ptr [rdi+rsi*8-4], 0Fh
0x1400ae7ce  jz      loc_1400AE8BE
0x1400ae7d4  mov     ebx, 0C000000Dh
0x1400ae7d9  mov     r8d, 5F0h
0x1400ae7df  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae7e6  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae7ed  call    VidTraceErrorInternal0
0x1400ae7f2  jmp     loc_1400AEB34
0x1400ae7f7  mov     eax, [rbx+20h]
0x1400ae7fa  test    rax, 31E0h
0x1400ae800  jnz     loc_1400AEA0C
0x1400ae806  cmp     cl, 2
0x1400ae809  jnz     short loc_1400AE816
0x1400ae80b  cmp     dword ptr [rdi+rsi*8-4], 0Fh
0x1400ae810  jz      loc_1400AE8F8
0x1400ae816  test    dl, 1
0x1400ae819  jz      short loc_1400AE832
0x1400ae81b  cmp     r12b, 1
0x1400ae81f  jnz     loc_1400AE91B
0x1400ae825  cmp     [rbx+2250h], r10b
0x1400ae82c  jz      loc_1400AE91B
0x1400ae832  test    dl, 2
0x1400ae835  jz      short loc_1400AE84E
0x1400ae837  cmp     r12b, 1
0x1400ae83b  jnz     loc_1400AE93E
0x1400ae841  cmp     [rbx+2251h], r10b
0x1400ae848  jz      loc_1400AE93E
0x1400ae84e  test    r9d, r8d
0x1400ae851  mov     dl, r12b
0x1400ae854  mov     r8d, [rdi+rsi*8-4]
0x1400ae859  mov     rcx, rbx
0x1400ae85c  setnz   r9b
0x1400ae860  call    VsmmVsmpValidateDefaultVtlProtection
0x1400ae865  xor     r10d, r10d
0x1400ae868  mov     ebx, eax
0x1400ae86a  test    eax, eax
0x1400ae86c  js      loc_1400AE961
0x1400ae872  mov     rbx, [rsp+130h+var_F0]
0x1400ae877  mov     r9d, [rsp+130h+var_F8]
0x1400ae87c  jmp     short loc_1400AE8BE
0x1400ae87e  cmp     [rdi+rsi*8-8], r10b
0x1400ae883  jnz     loc_1400AEA75
0x1400ae889  mov     al, [rdi+rsi*8-7]
0x1400ae88d  test    al, 3
0x1400ae88f  jnz     loc_1400AEA75
0x1400ae895  cmp     al, 4
0x1400ae897  jnb     loc_1400AEA75
0x1400ae89d  cmp     [rdi+rsi*8-6], r10w
0x1400ae8a3  jnz     loc_1400AEA75
0x1400ae8a9  cmp     [rdi+rsi*8-4], r10d
0x1400ae8ae  jnz     loc_1400AEA75
0x1400ae8b4  cmp     [rdi+rsi*8], r10
0x1400ae8b8  jnz     loc_1400AEA75
0x1400ae8be  inc     r12b
0x1400ae8c1  cmp     r12b, r13b
0x1400ae8c4  jbe     loc_1400AE777
0x1400ae8ca  mov     eax, r14d
0x1400ae8cd  and     eax, 0FFFFFFFEh
0x1400ae8d0  jmp     loc_1400AEB1D
0x1400ae8d5  mov     ebx, 0C000000Dh
0x1400ae8da  mov     r8d, 5E7h
0x1400ae8e0  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae8e7  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae8ee  call    VidTraceErrorInternal0
0x1400ae8f3  jmp     loc_1400AEB34
0x1400ae8f8  mov     ebx, 0C000000Dh
0x1400ae8fd  mov     r8d, 604h
0x1400ae903  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae90a  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ae911  call    VidTraceErrorInternal0
0x1400ae916  jmp     loc_1400AEB34
0x1400ae91b  mov     ebx, 0C000000Dh
  ... truncated ...
```
