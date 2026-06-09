# VsmmVsmIoctlSetPartitionConfig

- ea: `0x1400ac630`
- end: `0x1400acf15`
- name: `VsmmVsmIoctlSetPartitionConfig`
- size: `2277`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140034554`
- `0x140034914`
- `0x140035654`
- `0x140038630`
- `0x1400ac630`
- `0x1400ae1a4`
- `0x1400ae720`

## string_xrefs

- `0x1400ac69b`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac6f3`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac7a3`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac80b`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac85d`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac8ec`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac988`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400ac9c6`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400aca56`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acb57`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acb7a`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acb9d`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acbc0`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acbf9`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acc8e`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400accb1`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400accd4`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400accf7`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acde5`: `VsmmVsmIoctlSetPartitionConfig`
- `0x1400acf04`: `VsmmVsmIoctlSetPartitionConfig`

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
  __int16 *v12; // rdx
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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
      tlgCreate1Sz_char(v44, v11);
      v36 = 1405;
      v45 = &v36;
      v12 = (__int16 *)byte_14004DAED;
      v37 = *a3;
      v13 = &v37;
LABEL_7:
      v48 = 4;
LABEL_8:
      v47 = v13;
      v35 = 6;
LABEL_9:
      v46 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v12, 0, 0, v35, v42);
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
        tlgCreate1Sz_char(v44, v16);
        v37 = 1431;
        v45 = &v37;
        v12 = word_14004DB82;
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
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
          tlgCreate1Sz_char(v44, v19);
          v37 = 1444;
          v45 = &v37;
          v12 = &word_14004D9DE;
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
                      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
                      {
                        tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
                        tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
                        v38 = 1567;
                        v45 = &v38;
                        v37 = a3[4 * i - 1];
                        v46 = 4;
                        v47 = &v37;
                        v48 = 4;
                        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004D883, 0, 0, 6, v42);
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
                      v28 | (2 * (*((_BYTE *)&a3[4 * (unsigned __int8)v32 - 1] - 3) & 3)),
                      v17);
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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v43, "VsmmVsmIoctlSetPartitionConfig");
      tlgCreate1Sz_char(v44, v14);
      v37 = 1412;
      v45 = &v37;
      v12 = (__int16 *)byte_14004DB39;
      v13 = (unsigned int *)&v39;
      v39 = v10;
      v48 = 1;
      goto LABEL_8;
    }
  }
LABEL_81:
  VidObjectLockRelease(v41);
  if ( v7 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14004D8DE, v33, 0, 11, v42);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400ac630  mov     [rsp-8+arg_8], rbx
0x1400ac635  mov     [rsp-8+arg_18], rsi
0x1400ac63a  push    rbp
0x1400ac63b  push    rdi
0x1400ac63c  push    r12
0x1400ac63e  push    r13
0x1400ac640  push    r14
0x1400ac642  lea     rbp, [rsp-10h]
0x1400ac647  sub     rsp, 110h
0x1400ac64e  mov     rax, cs:__security_cookie
0x1400ac655  xor     rax, rsp
0x1400ac658  mov     [rbp+30h+var_30], rax
0x1400ac65c  lea     rax, [rcx+0E98h]
0x1400ac663  mov     esi, edx
0x1400ac665  mov     rbx, rcx
0x1400ac668  mov     [rsp+130h+var_F0], rcx
0x1400ac66d  mov     rcx, rax
0x1400ac670  mov     [rsp+130h+var_100], esi
0x1400ac674  mov     rdi, r8
0x1400ac677  mov     [rsp+130h+var_E8], rax
0x1400ac67c  call    VidObjectLockAcquireExclusive
0x1400ac681  xor     r10d, r10d
0x1400ac684  lea     r11, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac68b  cmp     esi, 8
0x1400ac68e  jnb     short loc_1400AC6AF
0x1400ac690  mov     ebx, 0C0000023h
0x1400ac695  mov     r8d, 573h
0x1400ac69b  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac6a2  mov     rdx, r11
0x1400ac6a5  call    VidTraceErrorInternal0
0x1400ac6aa  jmp     loc_1400ACDA8
0x1400ac6af  mov     r8d, [rdi]
0x1400ac6b2  bsr     r13d, r8d
0x1400ac6b6  mov     [rsp+130h+var_F8], r10d
0x1400ac6bb  setnz   al
0x1400ac6be  test    al, al
0x1400ac6c0  jnz     loc_1400AC770
0x1400ac6c6  mov     eax, cs:dword_140064110
0x1400ac6cc  mov     ebx, 0C000000Dh
0x1400ac6d1  cmp     eax, 2
0x1400ac6d4  jbe     loc_1400ACDA8
0x1400ac6da  mov     edx, 100h
0x1400ac6df  lea     rcx, dword_140064110
0x1400ac6e6  call    _tlgKeywordOn
0x1400ac6eb  test    al, al
0x1400ac6ed  jz      loc_1400ACDA8
0x1400ac6f3  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac6fa  lea     rcx, [rsp+130h+var_C0]
0x1400ac6ff  call    _tlgCreate1Sz_char
0x1400ac704  mov     rdx, r11
0x1400ac707  lea     rcx, [rbp+30h+var_B0]
0x1400ac70b  call    _tlgCreate1Sz_char
0x1400ac710  lea     rax, [rsp+130h+var_100]
0x1400ac715  mov     [rsp+130h+var_100], 57Dh
0x1400ac71d  mov     [rbp+30h+var_A0], rax
0x1400ac721  lea     rdx, byte_14004DAED
0x1400ac728  mov     eax, [rdi]
0x1400ac72a  mov     [rsp+130h+var_FC], eax
0x1400ac72e  lea     rax, [rsp+130h+var_FC]
0x1400ac733  mov     [rbp+30h+var_88], 4
0x1400ac73b  mov     [rbp+30h+var_90], rax
0x1400ac73f  lea     rax, [rsp+130h+var_E0]
0x1400ac744  mov     [rsp+130h+var_108], rax
0x1400ac749  mov     [rsp+130h+var_110], 6
0x1400ac751  xor     r9d, r9d
0x1400ac754  mov     [rbp+30h+var_98], 4
0x1400ac75c  xor     r8d, r8d
0x1400ac75f  lea     rcx, dword_140064110
0x1400ac766  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ac76b  jmp     loc_1400ACDA8
0x1400ac770  cmp     r13b, 3
0x1400ac774  jb      short loc_1400AC7EF
0x1400ac776  mov     eax, cs:dword_140064110
0x1400ac77c  mov     ebx, 0C000000Dh
0x1400ac781  cmp     eax, 2
0x1400ac784  jbe     loc_1400ACDA8
0x1400ac78a  mov     edx, 100h
0x1400ac78f  lea     rcx, dword_140064110
0x1400ac796  call    _tlgKeywordOn
0x1400ac79b  test    al, al
0x1400ac79d  jz      loc_1400ACDA8
0x1400ac7a3  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac7aa  lea     rcx, [rsp+130h+var_C0]
0x1400ac7af  call    _tlgCreate1Sz_char
0x1400ac7b4  mov     rdx, r11
0x1400ac7b7  lea     rcx, [rbp+30h+var_B0]
0x1400ac7bb  call    _tlgCreate1Sz_char
0x1400ac7c0  lea     rax, [rsp+130h+var_FC]
0x1400ac7c5  mov     [rsp+130h+var_FC], 584h
0x1400ac7cd  mov     [rbp+30h+var_A0], rax
0x1400ac7d1  lea     rdx, byte_14004DB39
0x1400ac7d8  lea     rax, [rsp+130h+var_F4]
0x1400ac7dd  mov     [rsp+130h+var_F4], r13b
0x1400ac7e2  mov     [rbp+30h+var_88], 1
0x1400ac7ea  jmp     loc_1400AC73B
0x1400ac7ef  movzx   ecx, r13b
0x1400ac7f3  shl     rcx, 4
0x1400ac7f7  add     rcx, 8
0x1400ac7fb  cmp     rsi, rcx
0x1400ac7fe  jnb     short loc_1400AC81F
0x1400ac800  mov     ebx, 0C0000023h
0x1400ac805  mov     r8d, 58Dh
0x1400ac80b  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac812  mov     rdx, r11
0x1400ac815  call    VidTraceErrorInternal0
0x1400ac81a  jmp     loc_1400ACDA8
0x1400ac81f  mov     r14d, [rbx+2248h]
0x1400ac826  mov     eax, r8d
0x1400ac829  not     eax
0x1400ac82b  test    r14d, eax
0x1400ac82e  jz      short loc_1400AC8A2
0x1400ac830  mov     eax, cs:dword_140064110
0x1400ac836  mov     ebx, 0C000000Dh
0x1400ac83b  cmp     eax, 2
0x1400ac83e  jbe     loc_1400ACDA8
0x1400ac844  mov     edx, 100h
0x1400ac849  lea     rcx, dword_140064110
0x1400ac850  call    _tlgKeywordOn
0x1400ac855  test    al, al
0x1400ac857  jz      loc_1400ACDA8
0x1400ac85d  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac864  lea     rcx, [rsp+130h+var_C0]
0x1400ac869  call    _tlgCreate1Sz_char
0x1400ac86e  mov     rdx, r11
0x1400ac871  lea     rcx, [rbp+30h+var_B0]
0x1400ac875  call    _tlgCreate1Sz_char
0x1400ac87a  lea     rax, [rsp+130h+var_FC]
0x1400ac87f  mov     [rsp+130h+var_FC], 597h
0x1400ac887  mov     [rbp+30h+var_A0], rax
0x1400ac88b  lea     rdx, word_14004DB82
0x1400ac892  mov     eax, [rdi]
0x1400ac894  mov     [rsp+130h+var_100], eax
0x1400ac898  lea     rax, [rsp+130h+var_100]
0x1400ac89d  jmp     loc_1400AC733
0x1400ac8a2  mov     r9d, [rdi+4]
0x1400ac8a6  not     r14d
0x1400ac8a9  and     r14d, r8d
0x1400ac8ac  mov     [rsp+130h+var_F8], r9d
0x1400ac8b1  mov     eax, r14d
0x1400ac8b4  not     eax
0x1400ac8b6  test    r9d, eax
0x1400ac8b9  jz      loc_1400AC967
0x1400ac8bf  mov     eax, cs:dword_140064110
0x1400ac8c5  mov     ebx, 0C000000Dh
0x1400ac8ca  cmp     eax, 2
0x1400ac8cd  jbe     loc_1400ACDA8
0x1400ac8d3  mov     edx, 100h
0x1400ac8d8  lea     rcx, dword_140064110
0x1400ac8df  call    _tlgKeywordOn
0x1400ac8e4  test    al, al
0x1400ac8e6  jz      loc_1400ACDA8
0x1400ac8ec  lea     rdx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac8f3  lea     rcx, [rsp+130h+var_C0]
0x1400ac8f8  call    _tlgCreate1Sz_char
0x1400ac8fd  mov     rdx, r11
0x1400ac900  lea     rcx, [rbp+30h+var_B0]
0x1400ac904  call    _tlgCreate1Sz_char
0x1400ac909  lea     rax, [rsp+130h+var_FC]
0x1400ac90e  mov     [rsp+130h+var_FC], 5A4h
0x1400ac916  mov     [rbp+30h+var_A0], rax
0x1400ac91a  lea     rdx, word_14004D9DE
0x1400ac921  mov     eax, [rdi+4]
0x1400ac924  mov     [rsp+130h+var_100], eax
0x1400ac928  lea     rax, [rsp+130h+var_100]
0x1400ac92d  mov     [rbp+30h+var_90], rax
0x1400ac931  mov     eax, [rdi]
0x1400ac933  mov     [rsp+130h+var_F8], eax
0x1400ac937  lea     rax, [rsp+130h+var_F8]
0x1400ac93c  mov     [rbp+30h+var_80], rax
0x1400ac940  lea     rax, [rsp+130h+var_E0]
0x1400ac945  mov     [rsp+130h+var_108], rax
0x1400ac94a  mov     [rsp+130h+var_110], 7
0x1400ac952  mov     [rbp+30h+var_88], 4
0x1400ac95a  mov     [rbp+30h+var_78], 4
0x1400ac962  jmp     loc_1400AC751
0x1400ac967  test    r14d, r14d
0x1400ac96a  jnz     short loc_1400AC974
0x1400ac96c  mov     ebx, r10d
0x1400ac96f  jmp     loc_1400ACDA8
0x1400ac974  mov     rdx, [rbx+10h]
0x1400ac978  test    dl, 8
0x1400ac97b  jnz     short loc_1400AC99C
0x1400ac97d  mov     ebx, 0C00000BBh
0x1400ac982  mov     r8d, 5B4h
0x1400ac988  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac98f  mov     rdx, r11
0x1400ac992  call    VidTraceErrorInternal0
0x1400ac997  jmp     loc_1400ACDA8
0x1400ac99c  mov     rcx, rdx
0x1400ac99f  shr     rcx, 3
0x1400ac9a3  and     ecx, 2
0x1400ac9a6  or      ecx, 1
0x1400ac9a9  mov     eax, ecx
0x1400ac9ab  or      eax, 4
0x1400ac9ae  test    dl, 20h
0x1400ac9b1  cmovz   eax, ecx
0x1400ac9b4  not     eax
0x1400ac9b6  test    r8d, eax
0x1400ac9b9  jz      short loc_1400AC9DA
0x1400ac9bb  mov     ebx, 0C000000Dh
0x1400ac9c0  mov     r8d, 5C7h
0x1400ac9c6  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400ac9cd  mov     rdx, r11
0x1400ac9d0  call    VidTraceErrorInternal0
0x1400ac9d5  jmp     loc_1400ACDA8
0x1400ac9da  cmp     r13b, 1
0x1400ac9de  jb      loc_1400ACB3A
0x1400ac9e4  mov     r12b, 1
0x1400ac9e7  movzx   esi, r12b
0x1400ac9eb  mov     cl, r12b
0x1400ac9ee  mov     r8d, 1
0x1400ac9f4  add     rsi, rsi
0x1400ac9f7  shl     r8d, cl
0x1400ac9fa  test    r14d, r8d
0x1400ac9fd  jz      loc_1400ACAEE
0x1400aca03  mov     dl, [rdi+rsi*8-7]
0x1400aca07  cmp     dl, 4
0x1400aca0a  jnb     loc_1400ACCC2
0x1400aca10  cmp     [rdi+rsi*8-6], r10w
0x1400aca16  jnz     loc_1400ACCC2
0x1400aca1c  mov     cl, [rdi+rsi*8-8]
0x1400aca20  cmp     cl, 2
0x1400aca23  ja      loc_1400ACC9F
0x1400aca29  jz      short loc_1400ACA67
0x1400aca2b  cmp     [rdi+rsi*8], r10
0x1400aca2f  jnz     loc_1400ACB45
0x1400aca35  test    cl, cl
0x1400aca37  jnz     short loc_1400ACA67
0x1400aca39  cmp     dword ptr [rdi+rsi*8-4], 0Fh
0x1400aca3e  jz      loc_1400ACB2E
0x1400aca44  mov     ebx, 0C000000Dh
0x1400aca49  mov     r8d, 5F0h
0x1400aca4f  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400aca56  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400aca5d  call    VidTraceErrorInternal0
0x1400aca62  jmp     loc_1400ACDA4
0x1400aca67  mov     eax, [rbx+20h]
0x1400aca6a  test    rax, 31E0h
0x1400aca70  jnz     loc_1400ACC7C
0x1400aca76  cmp     cl, 2
0x1400aca79  jnz     short loc_1400ACA86
0x1400aca7b  cmp     dword ptr [rdi+rsi*8-4], 0Fh
0x1400aca80  jz      loc_1400ACB68
0x1400aca86  test    dl, 1
0x1400aca89  jz      short loc_1400ACAA2
0x1400aca8b  cmp     r12b, 1
0x1400aca8f  jnz     loc_1400ACB8B
0x1400aca95  cmp     [rbx+2250h], r10b
0x1400aca9c  jz      loc_1400ACB8B
0x1400acaa2  test    dl, 2
0x1400acaa5  jz      short loc_1400ACABE
0x1400acaa7  cmp     r12b, 1
0x1400acaab  jnz     loc_1400ACBAE
0x1400acab1  cmp     [rbx+2251h], r10b
0x1400acab8  jz      loc_1400ACBAE
0x1400acabe  test    r9d, r8d
0x1400acac1  mov     dl, r12b
0x1400acac4  mov     r8d, [rdi+rsi*8-4]
0x1400acac9  mov     rcx, rbx
0x1400acacc  setnz   r9b
0x1400acad0  call    VsmmVsmpValidateDefaultVtlProtection
0x1400acad5  xor     r10d, r10d
0x1400acad8  mov     ebx, eax
0x1400acada  test    eax, eax
0x1400acadc  js      loc_1400ACBD1
0x1400acae2  mov     rbx, [rsp+130h+var_F0]
0x1400acae7  mov     r9d, [rsp+130h+var_F8]
0x1400acaec  jmp     short loc_1400ACB2E
0x1400acaee  cmp     [rdi+rsi*8-8], r10b
0x1400acaf3  jnz     loc_1400ACCE5
0x1400acaf9  mov     al, [rdi+rsi*8-7]
0x1400acafd  test    al, 3
0x1400acaff  jnz     loc_1400ACCE5
0x1400acb05  cmp     al, 4
0x1400acb07  jnb     loc_1400ACCE5
0x1400acb0d  cmp     [rdi+rsi*8-6], r10w
0x1400acb13  jnz     loc_1400ACCE5
0x1400acb19  cmp     [rdi+rsi*8-4], r10d
0x1400acb1e  jnz     loc_1400ACCE5
0x1400acb24  cmp     [rdi+rsi*8], r10
0x1400acb28  jnz     loc_1400ACCE5
0x1400acb2e  inc     r12b
0x1400acb31  cmp     r12b, r13b
0x1400acb34  jbe     loc_1400AC9E7
0x1400acb3a  mov     eax, r14d
0x1400acb3d  and     eax, 0FFFFFFFEh
0x1400acb40  jmp     loc_1400ACD8D
0x1400acb45  mov     ebx, 0C000000Dh
0x1400acb4a  mov     r8d, 5E7h
0x1400acb50  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400acb57  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400acb5e  call    VidTraceErrorInternal0
0x1400acb63  jmp     loc_1400ACDA4
0x1400acb68  mov     ebx, 0C000000Dh
0x1400acb6d  mov     r8d, 604h
0x1400acb73  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400acb7a  lea     rcx, aVsmmvsmioctlse; "VsmmVsmIoctlSetPartitionConfig"
0x1400acb81  call    VidTraceErrorInternal0
0x1400acb86  jmp     loc_1400ACDA4
0x1400acb8b  mov     ebx, 0C000000Dh
  ... truncated ...
```
