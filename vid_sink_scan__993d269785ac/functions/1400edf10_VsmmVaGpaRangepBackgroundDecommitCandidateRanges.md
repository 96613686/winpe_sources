# VsmmVaGpaRangepBackgroundDecommitCandidateRanges

- ea: `0x1400edf10`
- end: `0x1400ee44e`
- name: `VsmmVaGpaRangepBackgroundDecommitCandidateRanges`
- size: `1342`
- prototype: `int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400edde0`

## callees

- `0x1400087ec`
- `0x140021650`
- `0x140021800`
- `0x1400234f0`
- `0x140035670`
- `0x140037610`
- `0x1400edf10`
- `0x1400ee454`
- `0x1400ee634`
- `0x1400f2f50`

## import_xrefs

- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400ee2bb`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400ee2bb`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee2ef`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400ee2ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ee2c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ee2c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ee30e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ee30e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400ee302`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400ee302`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ee2da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ee2da`
- `ntoskrnl!KeSetEvent` at `0x1400ee341`
- `ntoskrnl!KeSetEvent` at `0x1400ee341`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ee42a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ee42a`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400ee258`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400ee280`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400ee258`
- `ntoskrnl!RtlInterlockedClearBitRunEx` at `0x1400ee280`
- `ntoskrnl!RtlExtractBitMapEx` at `0x1400ee106`
- `ntoskrnl!RtlExtractBitMapEx` at `0x1400ee106`
- `ntoskrnl!RtlSetBitsEx` at `0x1400ee0bc`
- `ntoskrnl!RtlSetBitsEx` at `0x1400ee0bc`
- `ntoskrnl!RtlClearBitEx` at `0x1400ee1c5`
- `ntoskrnl!RtlClearBitEx` at `0x1400ee1c5`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400ee31e`
- `ntoskrnl!ExpInterlockedFlushSList` at `0x1400ee31e`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400edf9a`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400ee0d9`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400edf9a`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x1400ee0d9`
- `ntoskrnl!RtlClearAllBitsEx` at `0x1400ee40b`
- `ntoskrnl!RtlClearAllBitsEx` at `0x1400ee40b`
- `ntoskrnl!RtlClearBitsEx` at `0x1400ee299`
- `ntoskrnl!RtlClearBitsEx` at `0x1400ee299`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400edfed`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400ee148`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400ee214`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400edfed`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400ee148`
- `ntoskrnl!RtlFindNextForwardRunSetEx` at `0x1400ee214`

## pseudocode

```c
int __fastcall VsmmVaGpaRangepBackgroundDecommitCandidateRanges(_QWORD *a1)
{
  _QWORD *v1; // rbx
  unsigned __int64 v2; // r14
  __int64 v3; // rcx
  __int64 v4; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int64 NextForwardRunSet; // rax
  unsigned __int64 v7; // r13
  unsigned __int64 v8; // r13
  __int64 v9; // rsi
  ULONGLONG v10; // r15
  __int64 v11; // rax
  __int64 v12; // r12
  unsigned __int64 v13; // rbx
  ULONGLONG v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rax
  bool v20; // cl
  bool v21; // zf
  bool v22; // al
  unsigned __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  struct _KPROCESS *CurrentProcess; // rax
  signed __int32 v30[8]; // [rsp+0h] [rbp-100h] BYREF
  unsigned __int64 v31; // [rsp+20h] [rbp-E0h] BYREF
  ULONGLONG v32; // [rsp+28h] [rbp-D8h]
  __int128 v33; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v34; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h]
  __int64 v36; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v37; // [rsp+58h] [rbp-A8h]
  _QWORD *v38; // [rsp+60h] [rbp-A0h]
  _QWORD *v39; // [rsp+68h] [rbp-98h]
  unsigned __int64 v40; // [rsp+70h] [rbp-90h]
  __int128 v41; // [rsp+78h] [rbp-88h] BYREF
  union _SLIST_HEADER v42[5]; // [rsp+90h] [rbp-70h] BYREF
  char v43[64]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = a1;
  v34 = a1;
  v41 = 0;
  v33 = 0;
  memset(v42, 0, sizeof(v42));
  v2 = v1[49];
  v3 = v1[34] - v1[32];
  v4 = v1[48];
  v31 = 0;
  v5 = v3 + v2 + 1;
  v40 = v5;
  RtlInitializeBitMapEx(&v41, *(_QWORD *)(v4 + 480), v5);
  NextForwardRunSet = v1[30];
  v35 = NextForwardRunSet;
  if ( v2 < v5 )
  {
    while ( 1 )
    {
      NextForwardRunSet = RtlFindNextForwardRunSetEx(&v41, v2, &v31);
      if ( !NextForwardRunSet )
        return NextForwardRunSet;
      v2 = v31;
      if ( NextForwardRunSet <= 0x200 )
        NextForwardRunSet = 512;
      v7 = v5 - v31;
      if ( NextForwardRunSet < v5 - v31 )
        v7 = NextForwardRunSet;
      v8 = v31 + v7;
      v37 = v8;
      if ( v31 < v8 )
        break;
LABEL_51:
      if ( v2 >= v5 )
        return NextForwardRunSet;
    }
    v38 = v1 + 67;
    v9 = v4 + 928;
    v39 = v1 + 65;
    while ( 1 )
    {
      v10 = v8 - v2;
      v32 = v8 - v2;
      if ( (v2 & 0x1FF) != 0 )
        break;
      if ( v10 > 0x200 )
      {
        v10 = 512;
LABEL_12:
        v32 = v10;
      }
LABEL_13:
      v11 = VsmmNtSlatAbPreAcquire(v9, 0);
      v36 = v11;
      v12 = v11;
      if ( v11 )
        VsmmNtSlatAbPostAcquire(v11);
      VsmmVaGpaRangeBeginHoldingNtVmRange(v42, (__int64)v1, v1[32] + v2 - v1[49], v10);
      RtlSetBitsEx(v4 + 488, v2, v10);
      _InterlockedOr(v30, 0);
      RtlInitializeBitMapEx(&v33, v43, v10);
      v13 = v35;
      if ( (*(_BYTE *)(v35 + 24) & 0x10) != 0 )
        RtlExtractBitMapEx(v4 + 504, &v33, v2, v10);
      else
        RtlClearAllBitsEx(&v33);
      if ( (*(_BYTE *)(v13 + 24) & 8) != 0 )
      {
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
        VsmmQueryKnownZeroVaPages(CurrentProcess);
      }
      v14 = 0;
      if ( v10 )
      {
        do
        {
          v15 = RtlFindNextForwardRunSetEx(&v33, v14, &v31);
          v16 = v15;
          if ( !v15 )
            break;
          v14 = v31;
          if ( v31 < v15 + v31 )
          {
            do
            {
              v17 = v2 + v14;
              v18 = *(_QWORD *)(v4 + 256);
              if ( (*(_DWORD *)(v4 + 20) & 8) != 0 )
                v19 = (_QWORD *)(v18 + 8 * v17);
              else
                v19 = (_QWORD *)(16 * v17 + v18 + 8);
              v20 = 0;
              v21 = (*v19 & 0x3FF000000000000LL) == 0;
              v22 = (*v19 & 0xFFFE00000000LL) == 0 && (*v19 & 0x1FFFFE000LL) == 0;
              if ( v21 )
                v20 = v22;
              if ( !v20 )
                RtlClearBitEx(&v33, v14);
              ++v14;
            }
            while ( v14 < v16 + v31 );
            v10 = v32;
          }
        }
        while ( v14 < v10 );
        v12 = v36;
        v9 = v4 + 928;
        v8 = v37;
      }
      v23 = 0;
      if ( v10 )
      {
        do
        {
          v24 = RtlFindNextForwardRunSetEx(&v33, v23, &v31);
          v25 = v24;
          if ( !v24 )
            break;
          VsmmMemoryBlockDecommitPrimaryRamRange(v4, v2 + v31, v24, 0);
          v23 = v25 + v31;
        }
        while ( v25 + v31 < v10 );
      }
      RtlInterlockedClearBitRunEx(v4 + 472, v2, v10);
      if ( (*(_BYTE *)(*(_QWORD *)(v4 + 8) + 24LL) & 0x10) != 0 )
      {
        _InterlockedOr(v30, 0);
        RtlInterlockedClearBitRunEx(v4 + 504, v2, v10);
      }
      RtlClearBitsEx(v4 + 488, v2, v10);
      ++*(_QWORD *)(v4 + 920);
      ExUnblockOnAddressPushLockEx(v9, 0);
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v38, 0);
      RtlRbRemoveNode(v39, v42);
      ExReleasePushLockEx(v38, 0);
      KeLeaveCriticalRegion();
      NextForwardRunSet = (unsigned __int64)ExpInterlockedFlushSList(&v42[3]);
      v26 = (_QWORD *)NextForwardRunSet;
      while ( v26 )
      {
        v27 = v26;
        v26 = (_QWORD *)*v26;
        LODWORD(NextForwardRunSet) = KeSetEvent((PRKEVENT)(v27 + 2), 0, 0);
      }
      if ( v42[4].Alignment )
      {
        if ( v42[4].Region )
          VsmmNtSlatAbPostReleaseEx(v42[4].Alignment, v42[4].Region);
        LODWORD(NextForwardRunSet) = VsmmAutoBoostLockDereference();
      }
      if ( v12 )
        LODWORD(NextForwardRunSet) = VsmmNtSlatAbPostReleaseEx(v9, v12);
      v1 = v34;
      v2 += v10;
      if ( v2 >= v8 )
      {
        v5 = v40;
        goto LABEL_51;
      }
    }
    if ( v10 <= 0x200 )
      goto LABEL_13;
    v10 = ((v2 + 511) & 0xFFFFFFFFFFFFFE00uLL) - v2;
    goto LABEL_12;
  }
  return NextForwardRunSet;
}

```

## disassembly

```asm
0x1400edf10  push    rbp
0x1400edf12  push    rbx
0x1400edf13  push    rsi
0x1400edf14  push    rdi
0x1400edf15  push    r14
0x1400edf17  lea     rbp, [rsp-30h]
0x1400edf1c  sub     rsp, 130h
0x1400edf23  mov     rax, cs:__security_cookie
0x1400edf2a  xor     rax, rsp
0x1400edf2d  mov     [rbp+50h+var_30], rax
0x1400edf31  mov     rbx, rcx
0x1400edf34  mov     [rsp+150h+var_110], rcx
0x1400edf39  xorps   xmm0, xmm0
0x1400edf3c  lea     rcx, [rbp+50h+var_C0]; void *
0x1400edf40  xorps   xmm1, xmm1
0x1400edf43  xor     edx, edx; Val
0x1400edf45  mov     r8d, 50h ; 'P'; Size
0x1400edf4b  movups  [rsp+150h+var_D8], xmm0
0x1400edf50  movups  [rsp+150h+var_120], xmm1
0x1400edf55  call    memset
0x1400edf5a  mov     r14, [rbx+188h]
0x1400edf61  mov     rcx, [rbx+110h]
0x1400edf68  sub     rcx, [rbx+100h]
0x1400edf6f  mov     rdi, [rbx+180h]
0x1400edf76  mov     [rsp+150h+var_130], 0
0x1400edf7f  lea     rsi, [r14+1]
0x1400edf83  add     rsi, rcx
0x1400edf86  lea     rcx, [rsp+150h+var_D8]
0x1400edf8b  mov     r8, rsi
0x1400edf8e  mov     [rsp+150h+var_E0], rsi
0x1400edf93  mov     rdx, [rdi+1E0h]
0x1400edf9a  call    cs:__imp_RtlInitializeBitMapEx
0x1400edfa1  nop     dword ptr [rax+rax+00h]
0x1400edfa6  mov     rax, [rbx+0F0h]
0x1400edfad  mov     [rsp+150h+var_108], rax
0x1400edfb2  cmp     r14, rsi
0x1400edfb5  jnb     loc_1400EE3EB
0x1400edfbb  mov     [rsp+150h+arg_8], r12
0x1400edfc3  mov     r12d, 200h
0x1400edfc9  mov     [rsp+150h+arg_10], r13
0x1400edfd1  mov     [rsp+150h+arg_18], r15
0x1400edfd9  nop     dword ptr [rax+00000000h]
0x1400edfe0  lea     r8, [rsp+150h+var_130]
0x1400edfe5  mov     rdx, r14
0x1400edfe8  lea     rcx, [rsp+150h+var_D8]
0x1400edfed  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400edff4  nop     dword ptr [rax+rax+00h]
0x1400edff9  test    rax, rax
0x1400edffc  jz      loc_1400EE3D3
0x1400ee002  mov     r14, [rsp+150h+var_130]
0x1400ee007  cmp     rax, r12
0x1400ee00a  mov     r13, rsi
0x1400ee00d  cmovbe  rax, r12
0x1400ee011  sub     r13, r14
0x1400ee014  cmp     rax, r13
0x1400ee017  cmovb   r13, rax
0x1400ee01b  add     r13, r14
0x1400ee01e  mov     [rsp+150h+var_F8], r13
0x1400ee023  cmp     r14, r13
0x1400ee026  jnb     loc_1400EE3CA
0x1400ee02c  lea     rax, [rbx+218h]
0x1400ee033  mov     [rsp+150h+var_F0], rax
0x1400ee038  lea     rsi, [rdi+3A0h]
0x1400ee03f  lea     rax, [rbx+208h]
0x1400ee046  mov     [rsp+150h+var_E8], rax
0x1400ee04b  mov     r15, r13
0x1400ee04e  sub     r15, r14
0x1400ee051  mov     [rsp+150h+var_128], r15
0x1400ee056  test    r14, 1FFh
0x1400ee05d  jnz     loc_1400EE35F
0x1400ee063  cmp     r15, r12
0x1400ee066  jbe     short loc_1400EE070
0x1400ee068  mov     r15, r12
0x1400ee06b  mov     [rsp+150h+var_128], r15
0x1400ee070  xor     edx, edx
0x1400ee072  mov     rcx, rsi
0x1400ee075  call    VsmmNtSlatAbPreAcquire
0x1400ee07a  mov     [rsp+150h+var_100], rax
0x1400ee07f  mov     r12, rax
0x1400ee082  test    rax, rax
0x1400ee085  jz      short loc_1400EE08F
0x1400ee087  mov     rcx, rax
0x1400ee08a  call    VsmmNtSlatAbPostAcquire
0x1400ee08f  mov     r8, r14
0x1400ee092  lea     rcx, [rbp+50h+var_C0]
0x1400ee096  sub     r8, [rbx+188h]
0x1400ee09d  mov     r9, r15
0x1400ee0a0  add     r8, [rbx+100h]
0x1400ee0a7  mov     rdx, rbx
0x1400ee0aa  call    VsmmVaGpaRangeBeginHoldingNtVmRange
0x1400ee0af  mov     r8, r15
0x1400ee0b2  lea     rcx, [rdi+1E8h]
0x1400ee0b9  mov     rdx, r14
0x1400ee0bc  call    cs:__imp_RtlSetBitsEx
0x1400ee0c3  nop     dword ptr [rax+rax+00h]
0x1400ee0c8  lock or [rsp+150h+var_150], 0
0x1400ee0cd  mov     r8, r15
0x1400ee0d0  lea     rdx, [rbp+50h+var_70]
0x1400ee0d4  lea     rcx, [rsp+150h+var_120]
0x1400ee0d9  call    cs:__imp_RtlInitializeBitMapEx
0x1400ee0e0  nop     dword ptr [rax+rax+00h]
0x1400ee0e5  mov     rbx, [rsp+150h+var_108]
0x1400ee0ea  test    byte ptr [rbx+18h], 10h
0x1400ee0ee  jz      loc_1400EE406
0x1400ee0f4  lea     rcx, [rdi+1F8h]
0x1400ee0fb  mov     r9, r15
0x1400ee0fe  mov     r8, r14
0x1400ee101  lea     rdx, [rsp+150h+var_120]
0x1400ee106  call    cs:__imp_RtlExtractBitMapEx
0x1400ee10d  nop     dword ptr [rax+rax+00h]
0x1400ee112  test    byte ptr [rbx+18h], 8
0x1400ee116  jnz     loc_1400EE41C
0x1400ee11c  xor     ebx, ebx
0x1400ee11e  test    r15, r15
0x1400ee121  jz      loc_1400EE200
0x1400ee127  mov     r13, 3FF000000000000h
0x1400ee131  mov     r12, 1FFFFE000h
0x1400ee13b  lea     r8, [rsp+150h+var_130]
0x1400ee140  mov     rdx, rbx
0x1400ee143  lea     rcx, [rsp+150h+var_120]
0x1400ee148  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400ee14f  nop     dword ptr [rax+rax+00h]
0x1400ee154  mov     rsi, rax
0x1400ee157  test    rax, rax
0x1400ee15a  jz      loc_1400EE1EF
0x1400ee160  mov     rbx, [rsp+150h+var_130]
0x1400ee165  lea     rcx, [rax+rbx]
0x1400ee169  cmp     rbx, rcx
0x1400ee16c  jnb     short loc_1400EE1E6
0x1400ee16e  mov     r15, 0FFFE00000000h
0x1400ee178  nop     dword ptr [rax+rax+00000000h]
0x1400ee180  mov     eax, [rdi+14h]
0x1400ee183  lea     rcx, [r14+rbx]
0x1400ee187  mov     rdx, [rdi+100h]
0x1400ee18e  test    al, 8
0x1400ee190  jz      loc_1400EE34F
0x1400ee196  lea     rax, [rdx+rcx*8]
0x1400ee19a  mov     rax, [rax]
0x1400ee19d  test    r12, rax
0x1400ee1a0  mov     r8, rax
0x1400ee1a3  setz    dl
0x1400ee1a6  test    r15, rax
0x1400ee1a9  setz    al
0x1400ee1ac  xor     ecx, ecx
0x1400ee1ae  and     dl, al
0x1400ee1b0  test    r13, r8
0x1400ee1b3  movzx   eax, dl
0x1400ee1b6  cmovz   ecx, eax
0x1400ee1b9  test    cl, cl
0x1400ee1bb  jnz     short loc_1400EE1D1
0x1400ee1bd  mov     rdx, rbx
0x1400ee1c0  lea     rcx, [rsp+150h+var_120]
0x1400ee1c5  call    cs:__imp_RtlClearBitEx
0x1400ee1cc  nop     dword ptr [rax+rax+00h]
0x1400ee1d1  mov     rcx, [rsp+150h+var_130]
0x1400ee1d6  inc     rbx
0x1400ee1d9  add     rcx, rsi
0x1400ee1dc  cmp     rbx, rcx
0x1400ee1df  jb      short loc_1400EE180
0x1400ee1e1  mov     r15, [rsp+150h+var_128]
0x1400ee1e6  cmp     rbx, r15
0x1400ee1e9  jb      loc_1400EE13B
0x1400ee1ef  mov     r12, [rsp+150h+var_100]
0x1400ee1f4  lea     rsi, [rdi+3A0h]
0x1400ee1fb  mov     r13, [rsp+150h+var_F8]
0x1400ee200  xor     eax, eax
0x1400ee202  test    r15, r15
0x1400ee205  jz      short loc_1400EE24B
0x1400ee207  lea     r8, [rsp+150h+var_130]
0x1400ee20c  mov     rdx, rax
0x1400ee20f  lea     rcx, [rsp+150h+var_120]
0x1400ee214  call    cs:__imp_RtlFindNextForwardRunSetEx
0x1400ee21b  nop     dword ptr [rax+rax+00h]
0x1400ee220  mov     rbx, rax
0x1400ee223  test    rax, rax
0x1400ee226  jz      short loc_1400EE24B
0x1400ee228  mov     rdx, [rsp+150h+var_130]
0x1400ee22d  xor     r9d, r9d
0x1400ee230  add     rdx, r14
0x1400ee233  mov     r8, rax
0x1400ee236  mov     rcx, rdi
0x1400ee239  call    VsmmMemoryBlockDecommitPrimaryRamRange
0x1400ee23e  mov     rax, [rsp+150h+var_130]
0x1400ee243  add     rax, rbx
0x1400ee246  cmp     rax, r15
0x1400ee249  jb      short loc_1400EE207
0x1400ee24b  mov     r8, r15
0x1400ee24e  lea     rcx, [rdi+1D8h]
0x1400ee255  mov     rdx, r14
0x1400ee258  call    cs:__imp_RtlInterlockedClearBitRunEx
0x1400ee25f  nop     dword ptr [rax+rax+00h]
0x1400ee264  mov     rax, [rdi+8]
0x1400ee268  test    byte ptr [rax+18h], 10h
0x1400ee26c  jz      short loc_1400EE28C
0x1400ee26e  lock or [rsp+150h+var_150], 0
0x1400ee273  lea     rcx, [rdi+1F8h]
0x1400ee27a  mov     r8, r15
0x1400ee27d  mov     rdx, r14
0x1400ee280  call    cs:__imp_RtlInterlockedClearBitRunEx
0x1400ee287  nop     dword ptr [rax+rax+00h]
0x1400ee28c  mov     r8, r15
0x1400ee28f  lea     rcx, [rdi+1E8h]
0x1400ee296  mov     rdx, r14
0x1400ee299  call    cs:__imp_RtlClearBitsEx
0x1400ee2a0  nop     dword ptr [rax+rax+00h]
0x1400ee2a5  mov     rax, [rdi+398h]
0x1400ee2ac  xor     edx, edx
0x1400ee2ae  inc     rax
0x1400ee2b1  mov     rcx, rsi
0x1400ee2b4  mov     [rdi+398h], rax
0x1400ee2bb  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400ee2c2  nop     dword ptr [rax+rax+00h]
0x1400ee2c7  call    cs:__imp_KeEnterCriticalRegion
0x1400ee2ce  nop     dword ptr [rax+rax+00h]
0x1400ee2d3  mov     rcx, [rsp+150h+var_F0]
0x1400ee2d8  xor     edx, edx
0x1400ee2da  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400ee2e1  nop     dword ptr [rax+rax+00h]
0x1400ee2e6  mov     rcx, [rsp+150h+var_E8]
0x1400ee2eb  lea     rdx, [rbp+50h+var_C0]
0x1400ee2ef  call    cs:__imp_RtlRbRemoveNode
0x1400ee2f6  nop     dword ptr [rax+rax+00h]
0x1400ee2fb  mov     rcx, [rsp+150h+var_F0]
0x1400ee300  xor     edx, edx
0x1400ee302  call    cs:__imp_ExReleasePushLockEx
0x1400ee309  nop     dword ptr [rax+rax+00h]
0x1400ee30e  call    cs:__imp_KeLeaveCriticalRegion
0x1400ee315  nop     dword ptr [rax+rax+00h]
0x1400ee31a  lea     rcx, [rbp+50h+ListHead]; ListHead
0x1400ee31e  call    cs:__imp_ExpInterlockedFlushSList
0x1400ee325  nop     dword ptr [rax+rax+00h]
0x1400ee32a  mov     rbx, rax
0x1400ee32d  test    rbx, rbx
0x1400ee330  jz      short loc_1400EE37E
0x1400ee332  mov     rcx, rbx
0x1400ee335  xor     r8d, r8d; Wait
0x1400ee338  mov     rbx, [rbx]
0x1400ee33b  add     rcx, 10h; Event
0x1400ee33f  xor     edx, edx; Increment
0x1400ee341  call    cs:__imp_KeSetEvent
0x1400ee348  nop     dword ptr [rax+rax+00h]
0x1400ee34d  jmp     short loc_1400EE32D
0x1400ee34f  shl     rcx, 4
0x1400ee353  lea     rax, [rdx+8]
0x1400ee357  add     rax, rcx
0x1400ee35a  jmp     loc_1400EE19A
0x1400ee35f  cmp     r15, r12
0x1400ee362  jbe     loc_1400EE070
0x1400ee368  lea     r15, [r14+1FFh]
0x1400ee36f  and     r15, 0FFFFFFFFFFFFFE00h
0x1400ee376  sub     r15, r14
0x1400ee379  jmp     loc_1400EE06B
0x1400ee37e  mov     rcx, [rbp+50h+var_80]
0x1400ee382  test    rcx, rcx
0x1400ee385  jz      short loc_1400EE39E
0x1400ee387  mov     rdx, [rbp+50h+var_78]
0x1400ee38b  test    rdx, rdx
0x1400ee38e  jz      short loc_1400EE399
0x1400ee390  call    VsmmNtSlatAbPostReleaseEx
0x1400ee395  mov     rcx, [rbp+50h+var_80]
0x1400ee399  call    VsmmAutoBoostLockDereference
0x1400ee39e  test    r12, r12
0x1400ee3a1  jz      short loc_1400EE3AE
0x1400ee3a3  mov     rdx, r12
0x1400ee3a6  mov     rcx, rsi
0x1400ee3a9  call    VsmmNtSlatAbPostReleaseEx
0x1400ee3ae  mov     rbx, [rsp+150h+var_110]
0x1400ee3b3  add     r14, r15
0x1400ee3b6  mov     r12d, 200h
0x1400ee3bc  cmp     r14, r13
0x1400ee3bf  jb      loc_1400EE04B
0x1400ee3c5  mov     rsi, [rsp+150h+var_E0]
0x1400ee3ca  cmp     r14, rsi
0x1400ee3cd  jb      loc_1400EDFE0
0x1400ee3d3  mov     r13, [rsp+150h+arg_10]
0x1400ee3db  mov     r12, [rsp+150h+arg_8]
0x1400ee3e3  mov     r15, [rsp+150h+arg_18]
0x1400ee3eb  mov     rcx, [rbp+50h+var_30]
0x1400ee3ef  xor     rcx, rsp; StackCookie
0x1400ee3f2  call    __security_check_cookie
0x1400ee3f7  add     rsp, 130h
0x1400ee3fe  pop     r14
0x1400ee400  pop     rdi
0x1400ee401  pop     rsi
0x1400ee402  pop     rbx
0x1400ee403  pop     rbp
0x1400ee404  retn
0x1400ee406  lea     rcx, [rsp+150h+var_120]
0x1400ee40b  call    cs:__imp_RtlClearAllBitsEx
0x1400ee412  nop     dword ptr [rax+rax+00h]
0x1400ee417  jmp     loc_1400EE112
0x1400ee41c  mov     rbx, r14
0x1400ee41f  shl     rbx, 0Ch
0x1400ee423  add     rbx, [rdi+370h]
0x1400ee42a  call    cs:__imp_PsGetCurrentProcess
0x1400ee431  nop     dword ptr [rax+rax+00h]
0x1400ee436  lea     r9, [rsp+150h+var_120]
0x1400ee43b  mov     r8, r15
0x1400ee43e  mov     rcx, rax; PROCESS
0x1400ee441  mov     rdx, rbx
  ... truncated ...
```
