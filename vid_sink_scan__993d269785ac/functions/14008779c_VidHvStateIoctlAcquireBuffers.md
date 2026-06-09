# VidHvStateIoctlAcquireBuffers

- ea: `0x14008779c`
- end: `0x140087d0c`
- name: `VidHvStateIoctlAcquireBuffers`
- size: `1392`
- prototype: `__int64 __fastcall(__int64, volatile void *, unsigned int *, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140031fa4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140024c78`
- `0x1400303c0`
- `0x140030760`
- `0x140030790`
- `0x1400307d0`
- `0x14008779c`
- `0x140089380`
- `0x140089990`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140087a6b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140087a6b`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400879ca`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400879ca`
- `ntoskrnl!ProbeForWrite` at `0x140087814`
- `ntoskrnl!ProbeForWrite` at `0x140087814`

## pseudocode

```c
__int64 __fastcall VidHvStateIoctlAcquireBuffers(
        __int64 a1,
        volatile void *a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        _DWORD *a6)
{
  __int64 v9; // r13
  char v10; // r15
  int v11; // r14d
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // r12d
  __int64 **v15; // r10
  __int64 **v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // r9
  __int64 *v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // r8
  unsigned __int64 v22; // r14
  __int64 *v23; // rax
  unsigned __int64 v24; // rax
  __int64 *v25; // rdx
  unsigned int v26; // ecx
  __int64 v27; // r8
  __int64 *v29; // [rsp+48h] [rbp-140h] BYREF
  __int64 v30; // [rsp+50h] [rbp-138h] BYREF
  __int64 v31; // [rsp+58h] [rbp-130h] BYREF
  _QWORD v32[2]; // [rsp+60h] [rbp-128h] BYREF
  unsigned int *v33; // [rsp+70h] [rbp-118h] BYREF
  _DWORD *v34; // [rsp+78h] [rbp-110h]
  char v35[32]; // [rsp+80h] [rbp-108h] BYREF
  char v36[16]; // [rsp+A0h] [rbp-E8h] BYREF
  char v37[16]; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 *v38; // [rsp+C0h] [rbp-C8h]
  __int64 v39; // [rsp+C8h] [rbp-C0h]
  __int64 *v40; // [rsp+D0h] [rbp-B8h]
  __int64 v41; // [rsp+D8h] [rbp-B0h]
  __int64 v42; // [rsp+E0h] [rbp-A8h]
  __int64 v43; // [rsp+E8h] [rbp-A0h]
  _DWORD *v44; // [rsp+F0h] [rbp-98h]
  __int64 v45; // [rsp+F8h] [rbp-90h]
  __int64 v46; // [rsp+100h] [rbp-88h]
  _DWORD v47[2]; // [rsp+108h] [rbp-80h] BYREF
  unsigned int **v48; // [rsp+110h] [rbp-78h]
  __int64 v49; // [rsp+118h] [rbp-70h]
  _QWORD *v50; // [rsp+120h] [rbp-68h]
  __int64 v51; // [rsp+128h] [rbp-60h]
  __int64 *v52; // [rsp+130h] [rbp-58h]
  __int64 v53; // [rsp+138h] [rbp-50h]

  v32[1] = a4;
  v33 = a3;
  v32[0] = a2;
  v34 = a6;
  v29 = (__int64 *)a1;
  v30 = a4;
  v9 = *(_QWORD *)(a1 + 12720);
  v31 = v9;
  v10 = 0;
  *a6 = 0;
  ProbeForWrite(a2, 8LL * *a3, 8u);
  if ( VidOpCtrlStart((volatile signed __int32 *)(a1 + 12624)) )
  {
    VidLockAcquireExclusive(v9);
    v10 = 1;
    v12 = a5;
    v13 = VidHvStatepAcquireBuffers(a1, a4, a5, a6);
    v11 = v13;
    if ( v13 >= 0 )
    {
      v14 = *a3;
      if ( v14 >= *(_DWORD *)(v9 + 56) )
        v14 = *(_DWORD *)(v9 + 56);
      v15 = (__int64 **)(v9 + 40);
      v16 = *(__int64 ***)(v9 + 40);
      v17 = 0;
      v18 = v32[0];
      while ( v16 != v15 && v17 < v14 )
      {
        *(_QWORD *)(v18 + 8LL * v17) = v16[3];
        v16 = (__int64 **)*v16;
        ++v17;
      }
      LODWORD(v31) = 0;
      if ( v14 )
      {
        do
        {
          v19 = *v15;
          if ( (__int64 **)(*v15)[1] != v15 || (v20 = (__int64 *)*v19, *(__int64 **)(*v19 + 8) != v19) )
            __fastfail(3u);
          *v15 = v20;
          v20[1] = (__int64)v15;
          --*(_DWORD *)(v9 + 56);
          v29 = v19 - 3;
          RtlRbRemoveNode(v9 + 16, v19 - 3);
          v22 = *(_QWORD *)(v9 + 64);
          if ( (*(_BYTE *)(v9 + 72) & 1) != 0 )
          {
            if ( v22 )
              v22 ^= v9 + 64;
            else
              v22 = 0;
          }
          LODWORD(v30) = *(_BYTE *)(v9 + 72) & 1;
          LOBYTE(v21) = 0;
          if ( v22 )
          {
            v23 = v29 + 6;
            for ( v32[0] = v29 + 6; ; v23 = (__int64 *)v32[0] )
            {
              if ( (int)VidHvStatepCompareBuffersByMappedAddress(v23, v22, v21) < 0 )
              {
                v24 = *(_QWORD *)v22;
                if ( (_DWORD)v30 )
                {
                  if ( !v24 )
                    goto LABEL_32;
                  v24 ^= v22;
                }
                if ( !v24 )
                {
LABEL_32:
                  LOBYTE(v21) = 0;
                  break;
                }
              }
              else
              {
                v24 = *(_QWORD *)(v22 + 8);
                if ( (_DWORD)v30 )
                {
                  if ( !v24 )
                    goto LABEL_26;
                  v24 ^= v22;
                }
                if ( !v24 )
                {
LABEL_26:
                  LOBYTE(v21) = 1;
                  break;
                }
              }
              v22 = v24;
            }
          }
          RtlRbInsertNodeEx(v9 + 64, v22, v21, v29);
          v25 = v29;
          *((_DWORD *)v29 + 32) = v29[16] & 0xFFFFFFFC | 2;
          v26 = a5 & 1;
          if ( (a5 & 1) != 0 && (*v34 & 2) == 0 && *(__int64 **)(v9 + 80) == v25 )
            *(_QWORD *)(v9 + 80) = 0;
          LODWORD(v31) = v31 + 1;
          v15 = (__int64 **)(v9 + 40);
        }
        while ( (unsigned int)v31 < v14 );
      }
      else
      {
        v26 = a5 & 1;
      }
      v11 = 0;
      if ( v26 && *(_QWORD *)(v9 + 80) )
        *v34 |= 2u;
      *v33 = v14;
    }
    else
    {
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidHvStateIoctlAcquireBuffers",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
        352,
        a1 + 656,
        a1 + 120,
        *(_QWORD *)(a1 + 648),
        v13);
    }
  }
  else
  {
    v11 = -1073741436;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlAcquireBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      341,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      -1073741436);
    v12 = a5;
  }
  if ( v11 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v36, "VidHvStateIoctlAcquireBuffers");
    tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
    LODWORD(v31) = 433;
    v38 = &v31;
    v39 = 4;
    LODWORD(v30) = v11;
    v40 = &v30;
    v41 = 4;
    v42 = a1 + 656;
    v43 = 16;
    v44 = v47;
    v45 = 2;
    v46 = *(_QWORD *)(a1 + 128);
    v47[0] = *(unsigned __int16 *)(a1 + 120);
    v47[1] = 0;
    v33 = *(unsigned int **)(a1 + 648);
    v48 = &v33;
    v49 = 8;
    v32[0] = v27;
    v50 = v32;
    v51 = 8;
    LODWORD(v29) = v12;
    v52 = (__int64 *)&v29;
    v53 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004707D, 0, 0, 12, v35);
  }
  if ( v10 )
  {
    VidLockRelease(v9);
    VidOpCtrlFinish(a1 + 12624);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14008779c  push    rbx
0x14008779e  push    rsi
0x14008779f  push    rdi
0x1400877a0  push    r12
0x1400877a2  push    r13
0x1400877a4  push    r14
0x1400877a6  push    r15
0x1400877a8  sub     rsp, 150h
0x1400877af  mov     rax, cs:__security_cookie
0x1400877b6  xor     rax, rsp
0x1400877b9  mov     [rsp+188h+var_48], rax
0x1400877c1  mov     r14, r9
0x1400877c4  mov     [rsp+188h+var_120], r9
0x1400877c9  mov     r12, r8
0x1400877cc  mov     [rsp+188h+var_118], r8
0x1400877d1  mov     rax, rdx
0x1400877d4  mov     [rsp+188h+var_128], rdx
0x1400877d9  mov     rsi, rcx
0x1400877dc  mov     rbx, [rsp+188h+arg_28]
0x1400877e4  mov     [rsp+188h+var_110], rbx
0x1400877e9  mov     [rsp+188h+var_140], rcx
0x1400877ee  mov     [rsp+188h+var_138], r9
0x1400877f3  mov     r13, [rcx+31B0h]
0x1400877fa  mov     [rsp+188h+var_130], r13
0x1400877ff  xor     edi, edi
0x140087801  mov     r15b, dil
0x140087804  mov     [rbx], edi
0x140087806  mov     edx, [r8]
0x140087809  shl     rdx, 3; Length
0x14008780d  lea     r8d, [rdi+8]; Alignment
0x140087811  mov     rcx, rax; Address
0x140087814  call    cs:__imp_ProbeForWrite
0x14008781b  nop     dword ptr [rax+rax+00h]
0x140087820  nop
0x140087821  lea     rcx, [rsi+3150h]
0x140087828  call    VidOpCtrlStart
0x14008782d  test    al, al
0x14008782f  jnz     short loc_140087882
0x140087831  mov     r14d, 0C0000184h
0x140087837  lea     rcx, [rsi+78h]
0x14008783b  lea     r9, [rsi+290h]
0x140087842  mov     [rsp+188h+var_158], r14d
0x140087847  mov     rax, [rsi+288h]
0x14008784e  mov     [rsp+188h+var_160], rax
0x140087853  mov     [rsp+188h+var_168], rcx
0x140087858  mov     r8d, 155h
0x14008785e  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140087865  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x14008786c  call    VidTracePartitionErrorInternal0
0x140087871  mov     ebx, [rsp+188h+arg_20]
0x140087878  mov     r8, [rsp+188h+var_120]
0x14008787d  jmp     loc_140087B49
0x140087882  mov     rcx, r13
0x140087885  call    VidLockAcquireExclusive
0x14008788a  mov     r15d, 1
0x140087890  mov     [rsp+188h+var_148], r15b
0x140087895  mov     r9, rbx
0x140087898  mov     ebx, [rsp+188h+arg_20]
0x14008789f  mov     r8d, ebx
0x1400878a2  mov     rdx, r14
0x1400878a5  mov     rcx, rsi
0x1400878a8  call    VidHvStatepAcquireBuffers
0x1400878ad  mov     r14d, eax
0x1400878b0  test    eax, eax
0x1400878b2  jns     short loc_1400878EF
0x1400878b4  lea     rdx, [rsi+78h]
0x1400878b8  lea     r9, [rsi+290h]
0x1400878bf  mov     [rsp+188h+var_158], eax
0x1400878c3  mov     rcx, [rsi+288h]
0x1400878ca  mov     [rsp+188h+var_160], rcx
0x1400878cf  mov     [rsp+188h+var_168], rdx
0x1400878d4  mov     r8d, 160h
0x1400878da  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x1400878e1  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x1400878e8  call    VidTracePartitionErrorInternal0
0x1400878ed  jmp     short loc_140087878
0x1400878ef  mov     eax, [r13+38h]
0x1400878f3  mov     r12d, [r12]
0x1400878f7  cmp     r12d, eax
0x1400878fa  cmovnb  r12d, eax
0x1400878fe  lea     r10, [r13+28h]
0x140087902  mov     rdx, [r10]
0x140087905  mov     r8d, edi
0x140087908  mov     r9, [rsp+188h+var_128]
0x14008790d  cmp     rdx, r10
0x140087910  jz      short loc_140087988
0x140087912  cmp     r8d, r12d
0x140087915  jnb     short loc_140087988
0x140087917  mov     ecx, r8d
0x14008791a  mov     rax, [rdx+18h]
0x14008791e  mov     [r9+rcx*8], rax
0x140087922  mov     rdx, [rdx]
0x140087925  add     r8d, r15d
0x140087928  jmp     short loc_14008790D
0x14008792a  mov     r14d, eax
0x14008792d  mov     rsi, [rsp+188h+var_140]
0x140087932  lea     rcx, [rsi+78h]
0x140087936  lea     r9, [rsi+290h]
0x14008793d  mov     [rsp+188h+var_158], eax
0x140087941  mov     rax, [rsi+288h]
0x140087948  mov     [rsp+188h+var_160], rax
0x14008794d  mov     [rsp+188h+var_168], rcx
0x140087952  mov     r8d, 17Ah
0x140087958  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x14008795f  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140087966  call    VidTracePartitionErrorInternal0
0x14008796b  xor     edi, edi
0x14008796d  mov     ebx, [rsp+188h+arg_20]
0x140087974  mov     r13, [rsp+188h+var_130]
0x140087979  mov     r15b, [rsp+188h+var_148]
0x14008797e  mov     r8, [rsp+188h+var_138]
0x140087983  jmp     loc_140087B49
0x140087988  mov     dword ptr [rsp+188h+var_130], edi
0x14008798c  test    r12d, r12d
0x14008798f  jz      loc_140087ACB
0x140087995  mov     rax, [r10]
0x140087998  cmp     [rax+8], r10
0x14008799c  jnz     loc_140087AC4
0x1400879a2  mov     rcx, [rax]
0x1400879a5  cmp     [rcx+8], rax
0x1400879a9  jnz     loc_140087AC4
0x1400879af  mov     [r10], rcx
0x1400879b2  mov     [rcx+8], r10
0x1400879b6  dec     dword ptr [r13+38h]
0x1400879ba  add     rax, 0FFFFFFFFFFFFFFE8h
0x1400879be  mov     [rsp+188h+var_140], rax
0x1400879c3  lea     rcx, [r13+10h]
0x1400879c7  mov     rdx, rax
0x1400879ca  call    cs:__imp_RtlRbRemoveNode
0x1400879d1  nop     dword ptr [rax+rax+00h]
0x1400879d6  lea     rdx, [r13+40h]
0x1400879da  mov     r14, [rdx]
0x1400879dd  test    [r13+48h], r15b
0x1400879e1  jz      short loc_1400879F0
0x1400879e3  test    r14, r14
0x1400879e6  jz      short loc_1400879ED
0x1400879e8  xor     r14, rdx
0x1400879eb  jmp     short loc_1400879F0
0x1400879ed  mov     r14, rdi
0x1400879f0  movzx   eax, byte ptr [rdx+8]
0x1400879f4  and     eax, r15d
0x1400879f7  mov     dword ptr [rsp+188h+var_138], eax
0x1400879fb  mov     r8b, dil
0x1400879fe  test    r14, r14
0x140087a01  jz      short loc_140087A5F
0x140087a03  mov     rax, [rsp+188h+var_140]
0x140087a08  add     rax, 30h ; '0'
0x140087a0c  mov     [rsp+188h+var_128], rax
0x140087a11  mov     rdx, r14
0x140087a14  mov     rcx, rax
0x140087a17  call    VidHvStatepCompareBuffersByMappedAddress
0x140087a1c  test    eax, eax
0x140087a1e  js      short loc_140087A3C
0x140087a20  mov     rax, [r14+8]
0x140087a24  cmp     dword ptr [rsp+188h+var_138], edi
0x140087a28  jz      short loc_140087A32
0x140087a2a  test    rax, rax
0x140087a2d  jz      short loc_140087A37
0x140087a2f  xor     rax, r14
0x140087a32  test    rax, rax
0x140087a35  jnz     short loc_140087A52
0x140087a37  mov     r8b, r15b
0x140087a3a  jmp     short loc_140087A5F
0x140087a3c  mov     rax, [r14]
0x140087a3f  cmp     dword ptr [rsp+188h+var_138], edi
0x140087a43  jz      short loc_140087A4D
0x140087a45  test    rax, rax
0x140087a48  jz      short loc_140087A5C
0x140087a4a  xor     rax, r14
0x140087a4d  test    rax, rax
0x140087a50  jz      short loc_140087A5C
0x140087a52  mov     r14, rax
0x140087a55  mov     rax, [rsp+188h+var_128]
0x140087a5a  jmp     short loc_140087A11
0x140087a5c  mov     r8b, dil
0x140087a5f  mov     r9, [rsp+188h+var_140]
0x140087a64  mov     rdx, r14
0x140087a67  lea     rcx, [r13+40h]
0x140087a6b  call    cs:__imp_RtlRbInsertNodeEx
0x140087a72  nop     dword ptr [rax+rax+00h]
0x140087a77  mov     rdx, [rsp+188h+var_140]
0x140087a7c  mov     eax, [rdx+80h]
0x140087a82  and     eax, 0FFFFFFFEh
0x140087a85  or      eax, 2
0x140087a88  mov     [rdx+80h], eax
0x140087a8e  mov     ecx, ebx
0x140087a90  and     ecx, r15d
0x140087a93  jz      short loc_140087AAA
0x140087a95  mov     rax, [rsp+188h+var_110]
0x140087a9a  mov     eax, [rax]
0x140087a9c  test    al, 2
0x140087a9e  jnz     short loc_140087AAA
0x140087aa0  cmp     [r13+50h], rdx
0x140087aa4  jnz     short loc_140087AAA
0x140087aa6  mov     [r13+50h], rdi
0x140087aaa  mov     edx, dword ptr [rsp+188h+var_130]
0x140087aae  add     edx, r15d
0x140087ab1  mov     dword ptr [rsp+188h+var_130], edx
0x140087ab5  cmp     edx, r12d
0x140087ab8  lea     r10, [r13+28h]
0x140087abc  jb      loc_140087995
0x140087ac2  jmp     short loc_140087AD0
0x140087ac4  mov     ecx, 3
0x140087ac9  int     29h; Win8: RtlFailFast(ecx)
0x140087acb  mov     ecx, ebx
0x140087acd  and     ecx, r15d
0x140087ad0  mov     r14d, edi
0x140087ad3  test    ecx, ecx
0x140087ad5  jz      short loc_140087AE5
0x140087ad7  cmp     [r13+50h], rdi
0x140087adb  jz      short loc_140087AE5
0x140087add  mov     rax, [rsp+188h+var_110]
0x140087ae2  or      dword ptr [rax], 2
0x140087ae5  mov     rax, [rsp+188h+var_118]
0x140087aea  mov     [rax], r12d
0x140087aed  jmp     loc_140087878
0x140087af2  mov     r14d, eax
0x140087af5  mov     rsi, [rsp+188h+var_140]
0x140087afa  lea     rcx, [rsi+78h]
0x140087afe  lea     r9, [rsi+290h]
0x140087b05  mov     [rsp+188h+var_158], eax
0x140087b09  mov     rax, [rsi+288h]
0x140087b10  mov     [rsp+188h+var_160], rax
0x140087b15  mov     [rsp+188h+var_168], rcx
0x140087b1a  mov     r8d, 14Eh
0x140087b20  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140087b27  lea     rcx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140087b2e  call    VidTracePartitionErrorInternal0
0x140087b33  xor     edi, edi
0x140087b35  mov     ebx, [rsp+188h+arg_20]
0x140087b3c  mov     r13, [rsp+188h+var_130]
0x140087b41  mov     r15b, dil
0x140087b44  mov     r8, [rsp+188h+var_138]
0x140087b49  test    r14d, r14d
0x140087b4c  jns     loc_140087CC7
0x140087b52  mov     eax, cs:dword_140064110
0x140087b58  cmp     eax, 2
0x140087b5b  jbe     loc_140087CC7
0x140087b61  mov     edx, 100h
0x140087b66  lea     rcx, dword_140064110
0x140087b6d  call    _tlgKeywordOn
0x140087b72  test    al, al
0x140087b74  jz      loc_140087CC7
0x140087b7a  lea     rdx, aVidhvstateioct_0; "VidHvStateIoctlAcquireBuffers"
0x140087b81  lea     rcx, [rsp+188h+var_E8]
0x140087b89  call    _tlgCreate1Sz_char
0x140087b8e  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140087b95  lea     rcx, [rsp+188h+var_D8]
0x140087b9d  call    _tlgCreate1Sz_char
0x140087ba2  mov     dword ptr [rsp+188h+var_130], 1B1h
0x140087baa  lea     rax, [rsp+188h+var_130]
0x140087baf  mov     [rsp+188h+var_C8], rax
0x140087bb7  mov     [rsp+188h+var_C0], 4
0x140087bc3  mov     dword ptr [rsp+188h+var_138], r14d
0x140087bc8  lea     rax, [rsp+188h+var_138]
0x140087bcd  mov     [rsp+188h+var_B8], rax
0x140087bd5  mov     [rsp+188h+var_B0], 4
0x140087be1  lea     rax, [rsi+290h]
0x140087be8  mov     [rsp+188h+var_A8], rax
0x140087bf0  mov     [rsp+188h+var_A0], 10h
0x140087bfc  lea     rax, [rsp+188h+var_80]
0x140087c04  mov     [rsp+188h+var_98], rax
0x140087c0c  mov     [rsp+188h+var_90], 2
0x140087c18  mov     rax, [rsi+80h]
0x140087c1f  mov     [rsp+188h+var_88], rax
0x140087c27  movzx   eax, word ptr [rsi+78h]
0x140087c2b  mov     [rsp+188h+var_80], eax
0x140087c32  mov     [rsp+188h+var_7C], edi
0x140087c39  mov     rax, [rsi+288h]
0x140087c40  mov     [rsp+188h+var_118], rax
0x140087c45  lea     rax, [rsp+188h+var_118]
0x140087c4a  mov     [rsp+188h+var_78], rax
0x140087c52  mov     [rsp+188h+var_70], 8
0x140087c5e  mov     [rsp+188h+var_128], r8
0x140087c63  lea     rax, [rsp+188h+var_128]
0x140087c68  mov     [rsp+188h+var_68], rax
0x140087c70  mov     [rsp+188h+var_60], 8
0x140087c7c  mov     dword ptr [rsp+188h+var_140], ebx
0x140087c80  lea     rax, [rsp+188h+var_140]
0x140087c85  mov     [rsp+188h+var_58], rax
0x140087c8d  mov     [rsp+188h+var_50], 4
0x140087c99  lea     rax, [rsp+188h+var_108]
0x140087ca1  mov     [rsp+188h+var_160], rax
0x140087ca6  mov     dword ptr [rsp+188h+var_168], 0Ch
0x140087cae  xor     r9d, r9d
0x140087cb1  xor     r8d, r8d
0x140087cb4  lea     rdx, byte_14004707D
0x140087cbb  lea     rcx, dword_140064110
0x140087cc2  call    _tlgWriteTransfer_EtwWriteTransfer
0x140087cc7  test    r15b, r15b
0x140087cca  jz      short loc_140087CE5
0x140087ccc  mov     rcx, r13
0x140087ccf  call    VidLockRelease
0x140087cd4  test    r15b, r15b
0x140087cd7  jz      short loc_140087CE5
0x140087cd9  lea     rcx, [rsi+3150h]
0x140087ce0  call    VidOpCtrlFinish
0x140087ce5  mov     eax, r14d
0x140087ce8  mov     rcx, [rsp+188h+var_48]
0x140087cf0  xor     rcx, rsp; StackCookie
  ... truncated ...
```
