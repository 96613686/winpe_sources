# UdfSeqCacheTransferMcb

- ea: `0x14001acf8`
- end: `0x14001afc7`
- name: `UdfSeqCacheTransferMcb`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000cce0`

## callees

- `0x14000a2e8`
- `0x14001acf8`
- `0x14001afd0`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001ae97`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001af26`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001ae97`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001af26`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ae15`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001af81`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001af90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001afa0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ae15`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001af81`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001af90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001afa0`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001add8`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001ae40`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001add8`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001ae40`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001aec7`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001aec7`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001aee6`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001aee6`
- `ntoskrnl!FsRtlResetLargeMcb` at `0x14001af5e`
- `ntoskrnl!FsRtlResetLargeMcb` at `0x14001af5e`

## pseudocode

```c
char __fastcall UdfSeqCacheTransferMcb(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v7; // r8
  struct _ERESOURCE *v8; // r12
  __int64 v9; // r8
  __int64 v10; // r8
  char v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rdi
  ULONG v14; // edi
  LONGLONG v15; // rdx
  LONGLONG v16; // rcx
  LONGLONG v17; // r8
  __int64 SectorCountFromLbn; // [rsp+40h] [rbp-30h] BYREF
  __int64 Lbn; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 StartingLbn; // [rsp+58h] [rbp-18h] BYREF
  struct _ERESOURCE *v23; // [rsp+60h] [rbp-10h]
  __int64 Vbn; // [rsp+C0h] [rbp+50h] BYREF
  LONGLONG SectorCount; // [rsp+C8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a3 + 752);
  Vbn = 0;
  v4 = a3;
  Lbn = 0;
  SectorCount = 0;
  SectorCountFromLbn = 0;
  StartingLbn = 0;
  v21 = 0;
  if ( v3 )
  {
    LOBYTE(a3) = 1;
    if ( (unsigned __int8)UdfAcquireResource(a1, *(_QWORD *)(v3 + 16), a3, 0) )
    {
      v8 = (struct _ERESOURCE *)(v4 + 344);
      v23 = (struct _ERESOURCE *)(v4 + 344);
      LOBYTE(v7) = 1;
      if ( (unsigned __int8)UdfAcquireResource(a1, v4 + 344, v7, 0) )
      {
        LOBYTE(v9) = 1;
        if ( (unsigned __int8)UdfAcquireResource(a1, v4 + 448, v9, 0) )
        {
          LOBYTE(v10) = 1;
          if ( !(unsigned __int8)UdfAcquireResource(a1, a2 + 136, v10, 0) )
            goto LABEL_25;
          v11 = 1;
          if ( FsRtlGetNextLargeMcbEntry(*(PLARGE_MCB *)(v4 + 728), 0, &Vbn, &Lbn, &SectorCount) )
          {
            LODWORD(v13) = *(_DWORD *)(v4 + 640);
            do
            {
              v13 = ((_BYTE)v13 + 1) & 7;
              UdfSeqCacheTransferMcbBuffer(
                (unsigned int)v13 + 3LL + 4 * v13,
                v4,
                v4 + 8 * ((unsigned int)v13 + 3LL + 4 * v13));
            }
            while ( (_DWORD)v13 != *(_DWORD *)(v4 + 16) );
            ExReleaseResourceLite((PERESOURCE)(v4 + 448));
            v11 = 0;
            v14 = 0;
            while ( FsRtlGetNextLargeMcbEntry(*(PLARGE_MCB *)(v4 + 728), v14, &Vbn, &Lbn, &SectorCount) )
            {
              ++v14;
              if ( Lbn != -1 )
              {
                v15 = Vbn;
                v16 = SectorCount;
                while ( v16 )
                {
                  if ( !FsRtlLookupLargeMcbEntry(
                          (PLARGE_MCB)(v3 + 264),
                          v15,
                          &v21,
                          &SectorCountFromLbn,
                          &StartingLbn,
                          0,
                          0)
                    || v21 == -1 )
                  {
                    FsRtlLookupLargeMcbEntry((PLARGE_MCB)(v3 + 232), Vbn, &v21, &SectorCountFromLbn, &StartingLbn, 0, 0);
                  }
                  else
                  {
                    v17 = SectorCountFromLbn;
                    if ( SectorCountFromLbn >= (unsigned __int64)SectorCount )
                    {
                      v17 = SectorCount;
                      SectorCountFromLbn = SectorCount;
                    }
                    FsRtlRemoveLargeMcbEntry((PLARGE_MCB)(v3 + 264), Vbn, v17);
                    if ( !FsRtlAddLargeMcbEntry((PLARGE_MCB)(v3 + 232), Vbn, Lbn, SectorCountFromLbn) )
                      goto LABEL_23;
                  }
                  v16 = SectorCount - SectorCountFromLbn;
                  v15 = SectorCountFromLbn + Vbn;
                  SectorCount -= SectorCountFromLbn;
                  Lbn += SectorCountFromLbn;
                  Vbn += SectorCountFromLbn;
                }
              }
            }
            FsRtlResetLargeMcb(*(PLARGE_MCB *)(v4 + 728), 0);
LABEL_23:
            v8 = v23;
          }
          UdfReleaseDevice(v12, a2, 0);
          if ( v11 )
LABEL_25:
            ExReleaseResourceLite((PERESOURCE)(v4 + 448));
        }
        ExReleaseResourceLite(v8);
      }
      ExReleaseResourceLite(*(PERESOURCE *)(v3 + 16));
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14001acf8  mov     [rsp-38h+arg_0], rbx
0x14001acfd  push    rbp
0x14001acfe  push    rsi
0x14001acff  push    rdi
0x14001ad00  push    r12
0x14001ad02  push    r13
0x14001ad04  push    r14
0x14001ad06  push    r15
0x14001ad08  mov     rbp, rsp
0x14001ad0b  sub     rsp, 70h
0x14001ad0f  mov     rsi, [r8+2F0h]
0x14001ad16  xor     r15d, r15d
0x14001ad19  mov     [rbp+Vbn], r15
0x14001ad1d  mov     rbx, r8
0x14001ad20  mov     [rbp+Lbn], r15
0x14001ad24  mov     r13, rdx
0x14001ad27  mov     [rbp+arg_18], r15
0x14001ad2b  mov     rdi, rcx
0x14001ad2e  mov     [rbp+SectorCountFromLbn], r15
0x14001ad32  mov     [rbp+StartingLbn], r15
0x14001ad36  mov     [rbp+var_20], r15
0x14001ad3a  test    rsi, rsi
0x14001ad3d  jz      loc_14001AFAC
0x14001ad43  mov     rdx, [rsi+10h]
0x14001ad47  xor     r9d, r9d
0x14001ad4a  mov     r8b, 1
0x14001ad4d  call    UdfAcquireResource
0x14001ad52  test    al, al
0x14001ad54  jz      loc_14001AFAC
0x14001ad5a  lea     r12, [rbx+158h]
0x14001ad61  xor     r9d, r9d
0x14001ad64  mov     rdx, r12
0x14001ad67  mov     [rbp+var_10], r12
0x14001ad6b  mov     r8b, 1
0x14001ad6e  mov     rcx, rdi
0x14001ad71  call    UdfAcquireResource
0x14001ad76  test    al, al
0x14001ad78  jz      loc_14001AF9C
0x14001ad7e  lea     r14, [rbx+1C0h]
0x14001ad85  xor     r9d, r9d
0x14001ad88  mov     rdx, r14
0x14001ad8b  mov     r8b, 1
0x14001ad8e  mov     rcx, rdi
0x14001ad91  call    UdfAcquireResource
0x14001ad96  test    al, al
0x14001ad98  jz      loc_14001AF8D
0x14001ad9e  lea     rdx, [r13+88h]
0x14001ada5  xor     r9d, r9d
0x14001ada8  mov     r8b, 1
0x14001adab  mov     rcx, rdi
0x14001adae  call    UdfAcquireResource
0x14001adb3  test    al, al
0x14001adb5  jz      loc_14001AF7E
0x14001adbb  mov     rcx, [rbx+2D8h]; Mcb
0x14001adc2  lea     rax, [rbp+arg_18]
0x14001adc6  lea     r9, [rbp+Lbn]; Lbn
0x14001adca  mov     [rsp+70h+SectorCount], rax; SectorCount
0x14001adcf  lea     r8, [rbp+Vbn]; Vbn
0x14001add3  xor     edx, edx; RunIndex
0x14001add5  mov     r15b, 1
0x14001add8  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14001addf  nop     dword ptr [rax+rax+00h]
0x14001ade4  test    al, al
0x14001ade6  jz      loc_14001AF6E
0x14001adec  mov     edi, [rbx+280h]
0x14001adf2  inc     edi
0x14001adf4  mov     rdx, rbx
0x14001adf7  and     edi, 7
0x14001adfa  mov     ecx, edi
0x14001adfc  add     rcx, 3
0x14001ae00  lea     rcx, [rcx+rdi*4]
0x14001ae04  lea     r8, [rbx+rcx*8]
0x14001ae08  call    UdfSeqCacheTransferMcbBuffer
0x14001ae0d  cmp     edi, [rbx+10h]
0x14001ae10  jnz     short loc_14001ADF2
0x14001ae12  mov     rcx, r14; Resource
0x14001ae15  call    cs:__imp_ExReleaseResourceLite
0x14001ae1c  nop     dword ptr [rax+rax+00h]
0x14001ae21  xor     r15b, r15b
0x14001ae24  xor     edi, edi
0x14001ae26  mov     rcx, [rbx+2D8h]; Mcb
0x14001ae2d  lea     rax, [rbp+arg_18]
0x14001ae31  lea     r9, [rbp+Lbn]; Lbn
0x14001ae35  mov     [rsp+70h+SectorCount], rax; SectorCount
0x14001ae3a  lea     r8, [rbp+Vbn]; Vbn
0x14001ae3e  mov     edx, edi; RunIndex
0x14001ae40  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14001ae47  nop     dword ptr [rax+rax+00h]
0x14001ae4c  test    al, al
0x14001ae4e  jz      loc_14001AF55
0x14001ae54  inc     edi
0x14001ae56  cmp     [rbp+Lbn], 0FFFFFFFFFFFFFFFFh
0x14001ae5b  jz      short loc_14001AE26
0x14001ae5d  mov     rdx, [rbp+Vbn]; Vbn
0x14001ae61  mov     rcx, [rbp+arg_18]
0x14001ae65  test    rcx, rcx
0x14001ae68  jz      short loc_14001AE26
0x14001ae6a  mov     [rsp+70h+Index], 0; Index
0x14001ae73  lea     rax, [rbp+StartingLbn]
0x14001ae77  lea     r12, [rsi+108h]
0x14001ae7e  mov     [rsp+70h+SectorCountFromStartingLbn], 0; SectorCountFromStartingLbn
0x14001ae87  mov     rcx, r12; Mcb
0x14001ae8a  mov     [rsp+70h+SectorCount], rax; StartingLbn
0x14001ae8f  lea     r9, [rbp+SectorCountFromLbn]; SectorCountFromLbn
0x14001ae93  lea     r8, [rbp+var_20]; Lbn
0x14001ae97  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x14001ae9e  nop     dword ptr [rax+rax+00h]
0x14001aea3  test    al, al
0x14001aea5  jz      short loc_14001AEF8
0x14001aea7  cmp     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x14001aeac  jz      short loc_14001AEF8
0x14001aeae  mov     r8, [rbp+SectorCountFromLbn]
0x14001aeb2  cmp     r8, [rbp+arg_18]
0x14001aeb6  jb      short loc_14001AEC0
0x14001aeb8  mov     r8, [rbp+arg_18]; SectorCount
0x14001aebc  mov     [rbp+SectorCountFromLbn], r8
0x14001aec0  mov     rdx, [rbp+Vbn]; Vbn
0x14001aec4  mov     rcx, r12; Mcb
0x14001aec7  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x14001aece  nop     dword ptr [rax+rax+00h]
0x14001aed3  mov     r9, [rbp+SectorCountFromLbn]; SectorCount
0x14001aed7  lea     rcx, [rsi+0E8h]; Mcb
0x14001aede  mov     r8, [rbp+Lbn]; Lbn
0x14001aee2  mov     rdx, [rbp+Vbn]; Vbn
0x14001aee6  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14001aeed  nop     dword ptr [rax+rax+00h]
0x14001aef2  test    al, al
0x14001aef4  jz      short loc_14001AF6A
0x14001aef6  jmp     short loc_14001AF32
0x14001aef8  mov     rdx, [rbp+Vbn]; Vbn
0x14001aefc  lea     rax, [rbp+StartingLbn]
0x14001af00  mov     [rsp+70h+Index], 0; Index
0x14001af09  lea     rcx, [rsi+0E8h]; Mcb
0x14001af10  mov     [rsp+70h+SectorCountFromStartingLbn], 0; SectorCountFromStartingLbn
0x14001af19  lea     r9, [rbp+SectorCountFromLbn]; SectorCountFromLbn
0x14001af1d  lea     r8, [rbp+var_20]; Lbn
0x14001af21  mov     [rsp+70h+SectorCount], rax; StartingLbn
0x14001af26  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x14001af2d  nop     dword ptr [rax+rax+00h]
0x14001af32  mov     rax, [rbp+SectorCountFromLbn]
0x14001af36  mov     rcx, [rbp+arg_18]
0x14001af3a  mov     rdx, [rbp+Vbn]
0x14001af3e  sub     rcx, rax
0x14001af41  add     rdx, rax
0x14001af44  mov     [rbp+arg_18], rcx
0x14001af48  add     [rbp+Lbn], rax
0x14001af4c  mov     [rbp+Vbn], rdx
0x14001af50  jmp     loc_14001AE65
0x14001af55  mov     rcx, [rbx+2D8h]; Mcb
0x14001af5c  xor     edx, edx; SelfSynchronized
0x14001af5e  call    cs:__imp_FsRtlResetLargeMcb
0x14001af65  nop     dword ptr [rax+rax+00h]
0x14001af6a  mov     r12, [rbp+var_10]
0x14001af6e  xor     r8d, r8d
0x14001af71  mov     rdx, r13
0x14001af74  call    UdfReleaseDevice
0x14001af79  test    r15b, r15b
0x14001af7c  jz      short loc_14001AF8D
0x14001af7e  mov     rcx, r14; Resource
0x14001af81  call    cs:__imp_ExReleaseResourceLite
0x14001af88  nop     dword ptr [rax+rax+00h]
0x14001af8d  mov     rcx, r12; Resource
0x14001af90  call    cs:__imp_ExReleaseResourceLite
0x14001af97  nop     dword ptr [rax+rax+00h]
0x14001af9c  mov     rcx, [rsi+10h]; Resource
0x14001afa0  call    cs:__imp_ExReleaseResourceLite
0x14001afa7  nop     dword ptr [rax+rax+00h]
0x14001afac  mov     rbx, [rsp+70h+arg_0]
0x14001afb4  mov     al, 1
0x14001afb6  add     rsp, 70h
0x14001afba  pop     r15
0x14001afbc  pop     r14
0x14001afbe  pop     r13
0x14001afc0  pop     r12
0x14001afc2  pop     rdi
0x14001afc3  pop     rsi
0x14001afc4  pop     rbp
0x14001afc5  retn
```
