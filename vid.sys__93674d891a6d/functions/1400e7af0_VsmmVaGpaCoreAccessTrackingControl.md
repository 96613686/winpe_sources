# VsmmVaGpaCoreAccessTrackingControl

- ea: `0x1400e7af0`
- end: `0x1400e814c`
- name: `VsmmVaGpaCoreAccessTrackingControl`
- size: `1628`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400d5414`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400386a0`
- `0x140079dfc`
- `0x1400e7af0`
- `0x1400ee950`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1400e7cf1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1400e7cf1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400e7eb8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400e7eb8`
- `winhvr!WinHvGetGpaPagesAccessState` at `0x1400e7d5e`
- `winhvr!WinHvGetGpaPagesAccessState` at `0x1400e7d5e`

## string_xrefs

- `0x1400e7b85`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e7c29`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e7d9d`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e7f07`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e7f66`: `VsmmVaGpaCoreAccessTrackingControl`
- `0x1400e7fa8`: `VsmmVaGpaCoreAccessTrackingControl`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaCoreAccessTrackingControl(char *a1, char *a2, unsigned __int64 a3, void *a4, int a5)
{
  unsigned __int64 v5; // r14
  char v8; // di
  int GpaPagesAccessState; // r14d
  __int64 Range; // rax
  __int64 v11; // rdi
  char *v12; // rdx
  char *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 i; // r8
  size_t v17; // r8
  char *v18; // r14
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-2A8h]
  unsigned __int64 v22; // [rsp+38h] [rbp-290h] BYREF
  void *v23; // [rsp+40h] [rbp-288h] BYREF
  char *v24; // [rsp+48h] [rbp-280h] BYREF
  char *v25; // [rsp+50h] [rbp-278h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-270h] BYREF
  char *v27; // [rsp+60h] [rbp-268h] BYREF
  __int128 v28; // [rsp+68h] [rbp-260h] BYREF
  _QWORD v29[3]; // [rsp+78h] [rbp-250h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-238h] BYREF
  _BYTE v31[16]; // [rsp+B0h] [rbp-218h] BYREF
  _BYTE v32[16]; // [rsp+C0h] [rbp-208h] BYREF
  char **v33; // [rsp+D0h] [rbp-1F8h]
  __int64 v34; // [rsp+D8h] [rbp-1F0h]
  void **v35; // [rsp+E0h] [rbp-1E8h]
  __int64 v36; // [rsp+E8h] [rbp-1E0h]
  __int128 *v37; // [rsp+F0h] [rbp-1D8h]
  __int64 v38; // [rsp+F8h] [rbp-1D0h]
  char **v39; // [rsp+100h] [rbp-1C8h]
  __int64 v40; // [rsp+108h] [rbp-1C0h]
  __int64 v41; // [rsp+110h] [rbp-1B8h]
  _DWORD v42[2]; // [rsp+118h] [rbp-1B0h] BYREF
  _QWORD *v43; // [rsp+120h] [rbp-1A8h]
  __int64 v44; // [rsp+128h] [rbp-1A0h]
  char **v45; // [rsp+130h] [rbp-198h]
  __int64 v46; // [rsp+138h] [rbp-190h]
  __int128 *v47; // [rsp+140h] [rbp-188h]
  __int64 v48; // [rsp+148h] [rbp-180h]
  unsigned __int64 *v49; // [rsp+150h] [rbp-178h]
  __int64 v50; // [rsp+158h] [rbp-170h]
  _OWORD Src[2]; // [rsp+160h] [rbp-168h] BYREF
  _BYTE v52[256]; // [rsp+180h] [rbp-148h] BYREF

  v23 = a4;
  v5 = a3;
  v22 = a3;
  v27 = a1;
  v25 = a2;
  v29[0] = a3;
  v26 = 0;
  v24 = 0;
  v28 = 0;
  v8 = 0;
  if ( !a5 || (a5 & 0xC) == 0xC )
  {
    GpaPagesAccessState = -1073741811;
    VidTraceErrorInternal0("VsmmVaGpaCoreAccessTrackingControl", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c", 4957);
  }
  else if ( (a5 & 1) != 0 )
  {
    VidObjectLockAcquireShared(a1 + 10784);
    v24 = a2;
    if ( (unsigned __int64)a2 > v5 )
    {
LABEL_9:
      if ( (a5 & 4) != 0 )
      {
        v11 = 4;
      }
      else
      {
        v11 = 0;
        if ( (a5 & 8) != 0 )
          v11 = 8;
      }
      v24 = a2;
      v13 = a2;
      while ( 1 )
      {
        if ( (unsigned __int64)v13 > v5 )
        {
          GpaPagesAccessState = 0;
          goto LABEL_15;
        }
        if ( PsIsThreadTerminating(KeGetCurrentThread()) )
        {
          GpaPagesAccessState = -1073741749;
          v8 = 1;
          goto LABEL_41;
        }
        v14 = 256;
        if ( v5 - (unsigned __int64)v24 + 1 < 0x100 )
          v14 = v5 - (_QWORD)v24 + 1;
        *(_QWORD *)&v28 = v14;
        v26 = 0;
        GpaPagesAccessState = WinHvGetGpaPagesAccessState(*((_QWORD *)a1 + 81), v11, v24, v14, v52, &v26);
        if ( GpaPagesAccessState < 0 )
          break;
        if ( (a5 & 2) != 0 )
        {
          memset(Src, 0, sizeof(Src));
          v15 = 0;
          for ( i = v26; v15 < i; ++v15 )
          {
            if ( (v52[v15] & 2) != 0 )
              _bittestandset64((signed __int64 *)Src, v15);
          }
          v17 = 8 * ((i + 63) >> 6);
          v18 = (char *)v23;
          if ( v17 && ((unsigned __int8)v23 & 7) != 0 )
            ExRaiseDatatypeMisalignment();
          RtlCopyToUser(v23, Src, v17);
          v23 = (char *)v23 + 8 * ((v26 + 63) >> 6);
          v29[1] = &v18[8 * ((v26 + 63) >> 6)];
        }
        v13 = &v24[v26];
        v24 += v26;
        v5 = v22;
      }
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
        tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
        LODWORD(v25) = 5029;
        v33 = &v25;
        v23 = v24;
        v35 = &v23;
        v37 = &v28;
        v38 = 8;
        v27 = (char *)v26;
        v39 = &v27;
        v40 = 8;
        v21 = 8;
        v12 = byte_14005BC89;
        goto LABEL_14;
      }
    }
    else
    {
      while ( 1 )
      {
        Range = VsmmVaGpaCorepFindRange(a1, &v24, &v28);
        if ( !Range || (*(_DWORD *)(Range + 96) & 4) == 0 )
          break;
        v24 = (char *)(*(_QWORD *)(Range + 64) + 1LL);
        if ( (unsigned __int64)v24 > v5 )
          goto LABEL_9;
      }
      GpaPagesAccessState = -1073741436;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
        tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
        LODWORD(v25) = 4983;
        v33 = &v25;
        v23 = v24;
        v35 = &v23;
        v21 = 6;
        v12 = byte_14005BBB3;
LABEL_14:
        v36 = 8;
        v34 = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v12, 0, 0, v21, v30);
      }
    }
LABEL_15:
    v8 = 1;
  }
  else
  {
    GpaPagesAccessState = -1073741822;
    VidTraceErrorStatusInternal0(
      "VsmmVaGpaCoreAccessTrackingControl",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c",
      4964,
      3221225474LL);
  }
  if ( GpaPagesAccessState < 0 )
  {
LABEL_41:
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v31, "VsmmVaGpaCoreAccessTrackingControl");
      tlgCreate1Sz_char(v32, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpacore.c");
      LODWORD(v25) = 5083;
      v33 = &v25;
      v34 = 4;
      LODWORD(v23) = GpaPagesAccessState;
      v35 = &v23;
      v36 = 4;
      v37 = (__int128 *)(a1 + 656);
      v38 = 16;
      v39 = (char **)v42;
      v40 = 2;
      v41 = *((_QWORD *)a1 + 16);
      v42[0] = *((unsigned __int16 *)a1 + 60);
      v42[1] = 0;
      v29[0] = *((_QWORD *)a1 + 81);
      v43 = v29;
      v44 = 8;
      v27 = a2;
      v45 = &v27;
      v46 = 8;
      *(_QWORD *)&v28 = v19;
      v47 = &v28;
      v48 = 8;
      LODWORD(v22) = a5;
      v49 = &v22;
      v50 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_14005BBF9, 0, 0, 13, v30);
    }
  }
  if ( v8 )
    VidObjectLockRelease(a1 + 10784);
  return (unsigned int)GpaPagesAccessState;
}

```

## disassembly

```asm
0x1400e7af0  push    rbx
0x1400e7af2  push    rsi
0x1400e7af3  push    rdi
0x1400e7af4  push    r12
0x1400e7af6  push    r13
0x1400e7af8  push    r14
0x1400e7afa  push    r15
0x1400e7afc  sub     rsp, 290h
0x1400e7b03  mov     rax, cs:__security_cookie
0x1400e7b0a  xor     rax, rsp
0x1400e7b0d  mov     [rsp+2C8h+var_48], rax
0x1400e7b15  mov     [rsp+2C8h+var_288], r9
0x1400e7b1a  mov     r14, r8
0x1400e7b1d  mov     [rsp+2C8h+var_290], r8
0x1400e7b22  mov     r12, rdx
0x1400e7b25  mov     r13, rcx
0x1400e7b28  mov     [rsp+2C8h+var_268], rcx
0x1400e7b2d  mov     [rsp+2C8h+var_278], rdx
0x1400e7b32  mov     [rsp+2C8h+var_250], r8
0x1400e7b37  xor     esi, esi
0x1400e7b39  mov     [rsp+2C8h+var_270], rsi
0x1400e7b3e  mov     [rsp+2C8h+var_280], rsi
0x1400e7b43  xorps   xmm0, xmm0
0x1400e7b46  movups  [rsp+2C8h+var_260], xmm0
0x1400e7b4b  mov     dil, sil
0x1400e7b4e  mov     ebx, [rsp+2C8h+arg_20]
0x1400e7b55  test    ebx, ebx
0x1400e7b57  jz      loc_1400E7F53
0x1400e7b5d  mov     eax, ebx
0x1400e7b5f  and     eax, 0Ch
0x1400e7b62  cmp     al, 0Ch
0x1400e7b64  jz      loc_1400E7F53
0x1400e7b6a  test    bl, 1
0x1400e7b6d  jnz     short loc_1400E7B96
0x1400e7b6f  mov     r14d, 0C0000002h
0x1400e7b75  mov     r9d, r14d
0x1400e7b78  mov     r8d, 1364h
0x1400e7b7e  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7b85  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7b8c  call    VidTraceErrorStatusInternal0
0x1400e7b91  jmp     loc_1400E7F72
0x1400e7b96  mov     [rsp+2C8h+var_298], 1
0x1400e7b9b  add     rcx, 2A20h
0x1400e7ba2  call    VidObjectLockAcquireShared
0x1400e7ba7  mov     [rsp+2C8h+var_280], r12
0x1400e7bac  cmp     r12, r14
0x1400e7baf  ja      short loc_1400E7BE3
0x1400e7bb1  lea     r8, [rsp+2C8h+var_260]
0x1400e7bb6  lea     rdx, [rsp+2C8h+var_280]
0x1400e7bbb  mov     rcx, r13
0x1400e7bbe  call    VsmmVaGpaCorepFindRange
0x1400e7bc3  mov     rcx, rax
0x1400e7bc6  test    rax, rax
0x1400e7bc9  jz      short loc_1400E7BFB
0x1400e7bcb  mov     eax, [rax+60h]
0x1400e7bce  test    al, 4
0x1400e7bd0  jz      short loc_1400E7BFB
0x1400e7bd2  mov     rax, [rcx+40h]
0x1400e7bd6  inc     rax
0x1400e7bd9  mov     [rsp+2C8h+var_280], rax
0x1400e7bde  cmp     rax, r14
0x1400e7be1  jbe     short loc_1400E7BB1
0x1400e7be3  mov     r15d, 8
0x1400e7be9  test    bl, 4
0x1400e7bec  jz      loc_1400E7CCD
0x1400e7bf2  lea     edi, [r15-4]
0x1400e7bf6  jmp     loc_1400E7CD7
0x1400e7bfb  mov     r14d, 0C0000184h
0x1400e7c01  mov     eax, cs:dword_140065110
0x1400e7c07  cmp     eax, 2
0x1400e7c0a  jbe     loc_1400E7CC3
0x1400e7c10  mov     edx, 100h
0x1400e7c15  lea     rcx, dword_140065110
0x1400e7c1c  call    _tlgKeywordOn
0x1400e7c21  test    al, al
0x1400e7c23  jz      loc_1400E7CC3
0x1400e7c29  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7c30  lea     rcx, [rsp+2C8h+var_218]
0x1400e7c38  call    _tlgCreate1Sz_char
0x1400e7c3d  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7c44  lea     rcx, [rsp+2C8h+var_208]
0x1400e7c4c  call    _tlgCreate1Sz_char
0x1400e7c51  mov     dword ptr [rsp+2C8h+var_278], 1377h
0x1400e7c59  lea     rax, [rsp+2C8h+var_278]
0x1400e7c5e  mov     [rsp+2C8h+var_1F8], rax
0x1400e7c66  mov     rax, [rsp+2C8h+var_280]
0x1400e7c6b  mov     [rsp+2C8h+var_288], rax
0x1400e7c70  lea     rax, [rsp+2C8h+var_288]
0x1400e7c75  mov     [rsp+2C8h+var_1E8], rax
0x1400e7c7d  lea     rax, [rsp+2C8h+var_238]
0x1400e7c85  mov     [rsp+2C8h+var_2A0], rax
0x1400e7c8a  mov     dword ptr [rsp+2C8h+var_2A8], 6
0x1400e7c92  lea     rdx, byte_14005BBB3
0x1400e7c99  xor     r9d, r9d
0x1400e7c9c  xor     r8d, r8d
0x1400e7c9f  mov     [rsp+2C8h+var_1E0], 8
0x1400e7cab  mov     [rsp+2C8h+var_1F0], 4
0x1400e7cb7  lea     rcx, dword_140065110
0x1400e7cbe  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e7cc3  mov     dil, [rsp+2C8h+var_298]
0x1400e7cc8  jmp     loc_1400E7F72
0x1400e7ccd  mov     rdi, rsi
0x1400e7cd0  test    r15b, bl
0x1400e7cd3  cmovnz  rdi, r15
0x1400e7cd7  mov     [rsp+2C8h+var_280], r12
0x1400e7cdc  mov     rax, r12
0x1400e7cdf  cmp     rax, r14
0x1400e7ce2  ja      loc_1400E7F4B
0x1400e7ce8  mov     rcx, gs:188h; Thread
0x1400e7cf1  call    cs:__imp_PsIsThreadTerminating
0x1400e7cf8  nop     dword ptr [rax+rax+00h]
0x1400e7cfd  test    al, al
0x1400e7cff  jz      short loc_1400E7D16
0x1400e7d01  mov     r14d, 0C000004Bh
0x1400e7d07  mov     r8, [rsp+2C8h+var_290]
0x1400e7d0c  mov     dil, [rsp+2C8h+var_298]
0x1400e7d11  jmp     loc_1400E7F80
0x1400e7d16  mov     rax, r14
0x1400e7d19  mov     r8, [rsp+2C8h+var_280]
0x1400e7d1e  sub     rax, r8
0x1400e7d21  inc     rax
0x1400e7d24  mov     ecx, 100h
0x1400e7d29  cmp     rax, rcx
0x1400e7d2c  cmovb   rcx, rax
0x1400e7d30  mov     qword ptr [rsp+2C8h+var_260], rcx
0x1400e7d35  mov     [rsp+2C8h+var_270], rsi
0x1400e7d3a  lea     rax, [rsp+2C8h+var_270]
0x1400e7d3f  mov     [rsp+2C8h+var_2A0], rax
0x1400e7d44  lea     rax, [rsp+2C8h+var_148]
0x1400e7d4c  mov     [rsp+2C8h+var_2A8], rax
0x1400e7d51  mov     r9, rcx
0x1400e7d54  mov     rdx, rdi
0x1400e7d57  mov     rcx, [r13+288h]
0x1400e7d5e  call    cs:__imp_WinHvGetGpaPagesAccessState
0x1400e7d65  nop     dword ptr [rax+rax+00h]
0x1400e7d6a  mov     r14d, eax
0x1400e7d6d  test    eax, eax
0x1400e7d6f  jns     loc_1400E7E55
0x1400e7d75  mov     ecx, cs:dword_140065110
0x1400e7d7b  cmp     ecx, 2
0x1400e7d7e  jbe     loc_1400E7CC3
0x1400e7d84  mov     edx, 100h
0x1400e7d89  lea     rcx, dword_140065110
0x1400e7d90  call    _tlgKeywordOn
0x1400e7d95  test    al, al
0x1400e7d97  jz      loc_1400E7CC3
0x1400e7d9d  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7da4  lea     rcx, [rsp+2C8h+var_218]
0x1400e7dac  call    _tlgCreate1Sz_char
0x1400e7db1  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7db8  lea     rcx, [rsp+2C8h+var_208]
0x1400e7dc0  call    _tlgCreate1Sz_char
0x1400e7dc5  mov     dword ptr [rsp+2C8h+var_278], 13A5h
0x1400e7dcd  lea     rax, [rsp+2C8h+var_278]
0x1400e7dd2  mov     [rsp+2C8h+var_1F8], rax
0x1400e7dda  mov     rax, [rsp+2C8h+var_280]
0x1400e7ddf  mov     [rsp+2C8h+var_288], rax
0x1400e7de4  lea     rax, [rsp+2C8h+var_288]
0x1400e7de9  mov     [rsp+2C8h+var_1E8], rax
0x1400e7df1  mov     rax, qword ptr [rsp+2C8h+var_260]
0x1400e7df6  mov     qword ptr [rsp+2C8h+var_260], rax
0x1400e7dfb  lea     rax, [rsp+2C8h+var_260]
0x1400e7e00  mov     [rsp+2C8h+var_1D8], rax
0x1400e7e08  mov     [rsp+2C8h+var_1D0], 8
0x1400e7e14  mov     rax, [rsp+2C8h+var_270]
0x1400e7e19  mov     [rsp+2C8h+var_268], rax
0x1400e7e1e  lea     rax, [rsp+2C8h+var_268]
0x1400e7e23  mov     [rsp+2C8h+var_1C8], rax
0x1400e7e2b  mov     [rsp+2C8h+var_1C0], 8
0x1400e7e37  lea     rax, [rsp+2C8h+var_238]
0x1400e7e3f  mov     [rsp+2C8h+var_2A0], rax
0x1400e7e44  mov     dword ptr [rsp+2C8h+var_2A8], r15d
0x1400e7e49  lea     rdx, byte_14005BC89
0x1400e7e50  jmp     loc_1400E7C99
0x1400e7e55  test    bl, 2
0x1400e7e58  jz      loc_1400E7F32
0x1400e7e5e  xorps   xmm0, xmm0
0x1400e7e61  movups  [rsp+2C8h+Src], xmm0
0x1400e7e69  movups  [rsp+2C8h+var_158], xmm0
0x1400e7e71  mov     rcx, rsi
0x1400e7e74  mov     r8, [rsp+2C8h+var_270]
0x1400e7e79  test    r8, r8
0x1400e7e7c  jz      short loc_1400E7E9C
0x1400e7e7e  test    [rsp+rcx+2C8h+var_148], 2
0x1400e7e86  jz      short loc_1400E7E94
0x1400e7e88  lea     rax, [rsp+2C8h+Src]
0x1400e7e90  bts     [rax], rcx
0x1400e7e94  inc     rcx
0x1400e7e97  cmp     rcx, r8
0x1400e7e9a  jb      short loc_1400E7E7E
0x1400e7e9c  add     r8, 3Fh ; '?'
0x1400e7ea0  shr     r8, 6
0x1400e7ea4  shl     r8, 3
0x1400e7ea8  mov     r14, [rsp+2C8h+var_288]
0x1400e7ead  test    r8, r8
0x1400e7eb0  jz      short loc_1400E7EC4
0x1400e7eb2  test    r14b, 7
0x1400e7eb6  jz      short loc_1400E7EC4
0x1400e7eb8  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400e7ebf  nop     dword ptr [rax+rax+00h]
0x1400e7ec4  lea     rdx, [rsp+2C8h+Src]; Src
0x1400e7ecc  mov     rcx, r14; void *
0x1400e7ecf  call    RtlCopyToUser
0x1400e7ed4  mov     rax, [rsp+2C8h+var_270]
0x1400e7ed9  add     rax, 3Fh ; '?'
0x1400e7edd  shr     rax, 6
0x1400e7ee1  lea     r14, [r14+rax*8]
0x1400e7ee5  mov     [rsp+2C8h+var_288], r14
0x1400e7eea  mov     [rsp+2C8h+var_248], r14
0x1400e7ef2  jmp     short loc_1400E7F32
0x1400e7ef4  mov     r14d, eax
0x1400e7ef7  mov     r9d, eax
0x1400e7efa  mov     r8d, 13CAh
0x1400e7f00  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7f07  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7f0e  call    VidTraceErrorStatusInternal0
0x1400e7f13  xor     esi, esi
0x1400e7f15  mov     ebx, [rsp+2C8h+arg_20]
0x1400e7f1c  mov     dil, [rsp+2C8h+var_298]
0x1400e7f21  mov     r13, [rsp+2C8h+var_268]
0x1400e7f26  mov     r12, [rsp+2C8h+var_278]
0x1400e7f2b  mov     r8, [rsp+2C8h+var_250]
0x1400e7f30  jmp     short loc_1400E7F77
0x1400e7f32  mov     rax, [rsp+2C8h+var_280]
0x1400e7f37  add     rax, [rsp+2C8h+var_270]
0x1400e7f3c  mov     [rsp+2C8h+var_280], rax
0x1400e7f41  mov     r14, [rsp+2C8h+var_290]
0x1400e7f46  jmp     loc_1400E7CDF
0x1400e7f4b  mov     r14d, esi
0x1400e7f4e  jmp     loc_1400E7CC3
0x1400e7f53  mov     r14d, 0C000000Dh
0x1400e7f59  mov     r8d, 135Dh
0x1400e7f5f  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7f66  lea     rcx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7f6d  call    VidTraceErrorInternal0
0x1400e7f72  mov     r8, [rsp+2C8h+var_290]
0x1400e7f77  test    r14d, r14d
0x1400e7f7a  jns     loc_1400E8114
0x1400e7f80  mov     eax, cs:dword_140065110
0x1400e7f86  cmp     eax, 2
0x1400e7f89  jbe     loc_1400E8114
0x1400e7f8f  mov     edx, 100h
0x1400e7f94  lea     rcx, dword_140065110
0x1400e7f9b  call    _tlgKeywordOn
0x1400e7fa0  test    al, al
0x1400e7fa2  jz      loc_1400E8114
0x1400e7fa8  lea     rdx, aVsmmvagpacorea; "VsmmVaGpaCoreAccessTrackingControl"
0x1400e7faf  lea     rcx, [rsp+2C8h+var_218]
0x1400e7fb7  call    _tlgCreate1Sz_char
0x1400e7fbc  lea     rdx, aOnecoreVmVidSy_60; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpac"...
0x1400e7fc3  lea     rcx, [rsp+2C8h+var_208]
0x1400e7fcb  call    _tlgCreate1Sz_char
0x1400e7fd0  mov     dword ptr [rsp+2C8h+var_278], 13DBh
0x1400e7fd8  lea     rax, [rsp+2C8h+var_278]
0x1400e7fdd  mov     [rsp+2C8h+var_1F8], rax
0x1400e7fe5  mov     [rsp+2C8h+var_1F0], 4
0x1400e7ff1  mov     dword ptr [rsp+2C8h+var_288], r14d
0x1400e7ff6  lea     rax, [rsp+2C8h+var_288]
0x1400e7ffb  mov     [rsp+2C8h+var_1E8], rax
0x1400e8003  mov     [rsp+2C8h+var_1E0], 4
0x1400e800f  lea     rax, [r13+290h]
0x1400e8016  mov     [rsp+2C8h+var_1D8], rax
0x1400e801e  mov     [rsp+2C8h+var_1D0], 10h
0x1400e802a  lea     rax, [rsp+2C8h+var_1B0]
0x1400e8032  mov     [rsp+2C8h+var_1C8], rax
0x1400e803a  mov     [rsp+2C8h+var_1C0], 2
0x1400e8046  mov     rax, [r13+80h]
0x1400e804d  mov     [rsp+2C8h+var_1B8], rax
0x1400e8055  movzx   eax, word ptr [r13+78h]
0x1400e805a  mov     [rsp+2C8h+var_1B0], eax
0x1400e8061  mov     [rsp+2C8h+var_1AC], esi
0x1400e8068  mov     rax, [r13+288h]
0x1400e806f  mov     [rsp+2C8h+var_250], rax
0x1400e8074  lea     rax, [rsp+2C8h+var_250]
0x1400e8079  mov     [rsp+2C8h+var_1A8], rax
0x1400e8081  mov     [rsp+2C8h+var_1A0], 8
0x1400e808d  mov     [rsp+2C8h+var_268], r12
0x1400e8092  lea     rax, [rsp+2C8h+var_268]
0x1400e8097  mov     [rsp+2C8h+var_198], rax
0x1400e809f  mov     [rsp+2C8h+var_190], 8
0x1400e80ab  mov     qword ptr [rsp+2C8h+var_260], r8
0x1400e80b0  lea     rax, [rsp+2C8h+var_260]
0x1400e80b5  mov     [rsp+2C8h+var_188], rax
0x1400e80bd  mov     [rsp+2C8h+var_180], 8
0x1400e80c9  mov     dword ptr [rsp+2C8h+var_290], ebx
0x1400e80cd  lea     rax, [rsp+2C8h+var_290]
0x1400e80d2  mov     [rsp+2C8h+var_178], rax
0x1400e80da  mov     [rsp+2C8h+var_170], 4
0x1400e80e6  lea     rax, [rsp+2C8h+var_238]
0x1400e80ee  mov     [rsp+2C8h+var_2A0], rax
0x1400e80f3  mov     dword ptr [rsp+2C8h+var_2A8], 0Dh
0x1400e80fb  xor     r9d, r9d
0x1400e80fe  xor     r8d, r8d
0x1400e8101  lea     rdx, byte_14005BBF9
0x1400e8108  lea     rcx, dword_140065110
0x1400e810f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e8114  test    dil, dil
0x1400e8117  jz      short loc_1400E8125
0x1400e8119  lea     rcx, [r13+2A20h]
0x1400e8120  call    VidObjectLockRelease
  ... truncated ...
```
