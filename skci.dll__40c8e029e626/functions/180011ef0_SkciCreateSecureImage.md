# SkciCreateSecureImage

- ea: `0x180011ef0`
- end: `0x180012302`
- name: `SkciCreateSecureImage`
- size: `1042`
- prototype: `__int64 __fastcall(void *Src, unsigned __int64, char, unsigned int, unsigned int, unsigned int **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011ef0`
- `0x180012cb0`
- `0x180012d40`
- `0x18003392c`
- `0x180033950`
- `0x1800461f8`
- `0x180046610`
- `0x1800466f8`
- `0x180046834`
- `0x180046aa0`
- `0x180047110`
- `0x18004b8a0`
- `0x18004bed4`
- `0x18004bf14`

## import_xrefs

- `securekernel!SkeEnterCriticalRegion` at `0x180012020`
- `securekernel!SkeEnterCriticalRegion` at `0x180012020`
- `securekernel!SkAllocatePool` at `0x180011f9f`
- `securekernel!SkAllocatePool` at `0x1800120e9`
- `securekernel!SkAllocatePool` at `0x1800121ec`
- `securekernel!SkAllocatePool` at `0x180011f9f`
- `securekernel!SkAllocatePool` at `0x1800120e9`
- `securekernel!SkAllocatePool` at `0x1800121ec`
- `securekernel!SkInitializePushLock` at `0x180012171`
- `securekernel!SkInitializePushLock` at `0x180012171`
- `securekernel!SkAcquirePushLockShared` at `0x180012033`
- `securekernel!SkAcquirePushLockShared` at `0x180012033`
- `securekernel!SkReleasePushLockShared` at `0x18001204f`
- `securekernel!SkReleasePushLockShared` at `0x18001204f`
- `securekernel!SkeLeaveCriticalRegion` at `0x18001205b`
- `securekernel!SkeLeaveCriticalRegion` at `0x18001205b`

## pseudocode

```c
__int64 __fastcall SkciCreateSecureImage(
        void *Src,
        unsigned __int64 a2,
        char a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int **a6)
{
  unsigned int v7; // r13d
  int NtHeaderChecksumAndTimestamp; // ebx
  unsigned int v10; // r15d
  unsigned __int16 *v11; // r14
  unsigned int *Pool; // rax
  unsigned int *v13; // rdi
  unsigned int v14; // edx
  _DWORD *v15; // r15
  unsigned int v16; // ebx
  unsigned int v17; // ecx
  size_t v18; // rbx
  void *v19; // rax
  char *v21; // rax
  size_t v22; // rbx
  unsigned int *v23; // rax
  unsigned int *v24; // r15
  __int64 v25; // rdx
  unsigned int v26; // esi
  unsigned int **v27; // rax
  int v28; // [rsp+28h] [rbp-48h]
  unsigned int v29; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v30; // [rsp+54h] [rbp-1Ch] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-10h] BYREF
  size_t MaxCount; // [rsp+B8h] [rbp+48h] BYREF
  char v34; // [rsp+C0h] [rbp+50h]

  v34 = a3;
  v31 = 0;
  v30 = 0;
  v7 = a2;
  v29 = 0;
  v32 = 0;
  LODWORD(MaxCount) = 0;
  if ( a2 > 0xFFFFFFFF )
    return (unsigned int)-1073741584;
  v10 = a5;
  if ( (int)HashKGetHashLength(a5, &v30) < 0 )
    return (unsigned int)-1073741581;
  NtHeaderChecksumAndTimestamp = CiValidateImageHeaderMapping(Src, v7, &v32, &MaxCount);
  if ( NtHeaderChecksumAndTimestamp < 0 )
    return (unsigned int)NtHeaderChecksumAndTimestamp;
  v11 = v32;
  NtHeaderChecksumAndTimestamp = SkciCheckNtHeaderForCompliance(v32);
  if ( NtHeaderChecksumAndTimestamp < 0 )
    return (unsigned int)NtHeaderChecksumAndTimestamp;
  Pool = (unsigned int *)SkAllocatePool(1, 392, 1768123219);
  v13 = Pool;
  if ( !Pool )
    return (unsigned int)-1073741801;
  memset_0(Pool, 0, 0x188u);
  v14 = MaxCount;
  v13[1] = v30;
  *v13 = v10;
  v13[20] = a4;
  v13[21] = v14;
  SkciGetResourceFileLocation((_DWORD)v11, v14, 2, (_DWORD)v13 + 280, (__int64)(v13 + 72), (__int64)(v13 + 74));
  v15 = v13 + 62;
  if ( v11[12] == 523 )
    *v15 |= 1u;
  SkeEnterCriticalRegion();
  SkAcquirePushLockShared(&g_CipPolicyLock);
  v16 = (unsigned int)g_CiPolicyState >> 22;
  SkReleasePushLockShared(&g_CipPolicyLock);
  SkeLeaveCriticalRegion();
  if ( (v16 & 1) == 0 )
    goto LABEL_23;
  *v15 |= 4u;
  NtHeaderChecksumAndTimestamp = CiGetNtHeaderChecksumAndTimestamp(v11, v13 + 60, v13 + 61);
  if ( NtHeaderChecksumAndTimestamp < 0 )
    goto LABEL_18;
  SkciGetResourceFileLocation((_DWORD)v11, MaxCount, 10, (_DWORD)v13 + 304, (__int64)(v13 + 78), 0);
  v17 = v13[76];
  if ( !v17 )
    goto LABEL_23;
  if ( (*v15 & 1) == 0 )
  {
    if ( v17 >= 0x98 )
      goto LABEL_16;
LABEL_21:
    v13[76] = 0;
    *((_QWORD *)v13 + 39) = 0;
    goto LABEL_23;
  }
  if ( v17 < 0xF4 )
    goto LABEL_21;
LABEL_16:
  v18 = (unsigned int)MaxCount;
  v19 = (void *)SkAllocatePool(1, (unsigned int)MaxCount, 1768123219);
  *((_QWORD *)v13 + 28) = v19;
  if ( !v19 )
  {
LABEL_17:
    NtHeaderChecksumAndTimestamp = -1073741801;
    goto LABEL_18;
  }
  memcpy_0(v19, Src, v18);
  v21 = (char *)v11 + *((_QWORD *)v13 + 28) - (_QWORD)Src;
  *v15 |= 8u;
  *((_QWORD *)v13 + 29) = v21;
LABEL_23:
  SkInitializePushLock(v13 + 40);
  if ( v34 )
  {
    v22 = 40LL * v11[3] + 33052;
    v23 = (unsigned int *)SkAllocatePool(1, v22, 1768123219);
    v24 = v23;
    if ( !v23 )
      goto LABEL_17;
    memset_0(v23, 0, v22);
    *(_QWORD *)v24 = v22;
    *((_QWORD *)v13 + 21) = v24;
    v24[8262] = v11[3];
    NtHeaderChecksumAndTimestamp = CiCreateVerificationContextForImageGeneratedPageHashes(
                                     (_DWORD)v11,
                                     MaxCount,
                                     (_DWORD)Src,
                                     v7,
                                     a4,
                                     a5,
                                     (__int64)(v24 + 4),
                                     (__int64)(v24 + 66),
                                     (__int64)(v24 + 68));
    if ( NtHeaderChecksumAndTimestamp < 0 )
      goto LABEL_18;
    v25 = v24[8262];
    if ( (_DWORD)v25 )
      CiSortAndCopyImageSectionTable((char *)v11 + v11[10] + 24, v25, v24 + 8263);
    NtHeaderChecksumAndTimestamp = CiGetFileOffsetAfterLastRawSectionData(
                                     (unsigned int)MaxCount,
                                     (char *)v11 + v11[10] + 24,
                                     v24[8262],
                                     &v29);
    if ( NtHeaderChecksumAndTimestamp < 0 )
      goto LABEL_18;
    if ( v29 <= a4 )
    {
      NtHeaderChecksumAndTimestamp = HashKGetCertificateInfo(Src, a4, v7, &v31);
      if ( NtHeaderChecksumAndTimestamp < 0 )
        goto LABEL_18;
      v26 = a4 - v29;
      if ( HIDWORD(v31) <= v26 )
      {
        v27 = a6;
        v24[69] = v26 - HIDWORD(v31);
        *v27 = v13;
        return (unsigned int)NtHeaderChecksumAndTimestamp;
      }
    }
    NtHeaderChecksumAndTimestamp = -1073740760;
LABEL_18:
    SkciFreeImageContext(v13);
    return (unsigned int)NtHeaderChecksumAndTimestamp;
  }
  NtHeaderChecksumAndTimestamp = CiCalculateFirstPageHash(a5, (_DWORD)Src, v13[21], a4, (__int64)(v13 + 4), v28);
  if ( NtHeaderChecksumAndTimestamp >= 0 )
  {
    *a6 = v13;
    v13 = 0;
  }
  if ( v13 )
    goto LABEL_18;
  return (unsigned int)NtHeaderChecksumAndTimestamp;
}

```

## disassembly

```asm
0x180011ef0  mov     [rsp-38h+arg_0], rbx
0x180011ef5  mov     [rsp-38h+arg_10], r8b
0x180011efa  push    rbp
0x180011efb  push    rsi
0x180011efc  push    rdi
0x180011efd  push    r12
0x180011eff  push    r13
0x180011f01  push    r14
0x180011f03  push    r15
0x180011f05  mov     rbp, rsp
0x180011f08  sub     rsp, 70h
0x180011f0c  xor     edi, edi
0x180011f0e  mov     eax, 0FFFFFFFFh
0x180011f13  mov     [rbp+var_18], rdi
0x180011f17  mov     esi, r9d
0x180011f1a  mov     [rbp+var_1C], edi
0x180011f1d  mov     r13, rdx
0x180011f20  mov     [rbp+var_20], edi
0x180011f23  mov     r12, rcx
0x180011f26  mov     [rbp+var_10], rdi
0x180011f2a  mov     dword ptr [rbp+MaxCount], edi
0x180011f2d  cmp     rdx, rax
0x180011f30  jbe     short loc_180011F3C
0x180011f32  mov     ebx, 0C00000F0h
0x180011f37  jmp     loc_18001210E
0x180011f3c  mov     r15d, [rbp+arg_20]
0x180011f40  lea     rdx, [rbp+var_1C]
0x180011f44  mov     ecx, r15d
0x180011f47  call    HashKGetHashLength
0x180011f4c  test    eax, eax
0x180011f4e  jns     short loc_180011F5A
0x180011f50  mov     ebx, 0C00000F3h
0x180011f55  jmp     loc_18001210E
0x180011f5a  lea     r9, [rbp+MaxCount]
0x180011f5e  mov     edx, r13d
0x180011f61  lea     r8, [rbp+var_10]
0x180011f65  mov     rcx, r12
0x180011f68  call    CiValidateImageHeaderMapping
0x180011f6d  mov     ebx, eax
0x180011f6f  test    eax, eax
0x180011f71  js      loc_18001210E
0x180011f77  mov     r14, [rbp+var_10]
0x180011f7b  mov     rcx, r14
0x180011f7e  call    SkciCheckNtHeaderForCompliance
0x180011f83  mov     ebx, eax
0x180011f85  test    eax, eax
0x180011f87  js      loc_18001210E
0x180011f8d  mov     ebx, 188h
0x180011f92  mov     r8d, 69636B53h
0x180011f98  mov     edx, ebx
0x180011f9a  mov     ecx, 1
0x180011f9f  call    cs:__imp_SkAllocatePool
0x180011fa6  nop     dword ptr [rax+rax+00h]
0x180011fab  mov     rdi, rax
0x180011fae  test    rax, rax
0x180011fb1  jnz     short loc_180011FBD
0x180011fb3  mov     ebx, 0C0000017h
0x180011fb8  jmp     loc_18001210E
0x180011fbd  mov     r8, rbx; Size
0x180011fc0  xor     edx, edx; Val
0x180011fc2  mov     rcx, rdi; void *
0x180011fc5  call    memset_0
0x180011fca  mov     eax, [rbp+var_1C]
0x180011fcd  lea     rcx, [rdi+120h]
0x180011fd4  mov     edx, dword ptr [rbp+MaxCount]
0x180011fd7  lea     r9, [rdi+118h]
0x180011fde  mov     [rdi+4], eax
0x180011fe1  mov     r8d, 2
0x180011fe7  lea     rax, [rdi+128h]
0x180011fee  mov     [rdi], r15d
0x180011ff1  mov     [rsp+70h+var_48], rax
0x180011ff6  mov     [rsp+70h+var_50], rcx
0x180011ffb  mov     rcx, r14
0x180011ffe  mov     [rdi+50h], esi
0x180012001  mov     [rdi+54h], edx
0x180012004  call    SkciGetResourceFileLocation
0x180012009  mov     eax, 20Bh
0x18001200e  lea     r15, [rdi+0F8h]
0x180012015  cmp     [r14+18h], ax
0x18001201a  jnz     short loc_180012020
0x18001201c  or      dword ptr [r15], 1
0x180012020  call    cs:__imp_SkeEnterCriticalRegion
0x180012027  nop     dword ptr [rax+rax+00h]
0x18001202c  lea     rcx, g_CipPolicyLock
0x180012033  call    cs:__imp_SkAcquirePushLockShared
0x18001203a  nop     dword ptr [rax+rax+00h]
0x18001203f  mov     ebx, cs:g_CiPolicyState
0x180012045  lea     rcx, g_CipPolicyLock
0x18001204c  shr     ebx, 16h
0x18001204f  call    cs:__imp_SkReleasePushLockShared
0x180012056  nop     dword ptr [rax+rax+00h]
0x18001205b  call    cs:__imp_SkeLeaveCriticalRegion
0x180012062  nop     dword ptr [rax+rax+00h]
0x180012067  test    bl, 1
0x18001206a  jz      loc_18001216A
0x180012070  or      dword ptr [r15], 4
0x180012074  lea     r8, [rdi+0F4h]
0x18001207b  lea     rdx, [rdi+0F0h]
0x180012082  mov     rcx, r14
0x180012085  call    CiGetNtHeaderChecksumAndTimestamp
0x18001208a  mov     ebx, eax
0x18001208c  test    eax, eax
0x18001208e  js      short loc_180012106
0x180012090  mov     edx, dword ptr [rbp+MaxCount]
0x180012093  lea     rax, [rdi+138h]
0x18001209a  lea     rbx, [rdi+130h]
0x1800120a1  mov     [rsp+70h+var_48], 0
0x1800120aa  mov     r9, rbx
0x1800120ad  mov     [rsp+70h+var_50], rax
0x1800120b2  mov     r8d, 0Ah
0x1800120b8  mov     rcx, r14
0x1800120bb  call    SkciGetResourceFileLocation
0x1800120c0  mov     ecx, [rbx]
0x1800120c2  test    ecx, ecx
0x1800120c4  jz      loc_18001216A
0x1800120ca  mov     eax, [r15]
0x1800120cd  test    al, 1
0x1800120cf  jz      short loc_180012129
0x1800120d1  cmp     ecx, 0F4h
0x1800120d7  jb      short loc_180012131
0x1800120d9  mov     ebx, dword ptr [rbp+MaxCount]
0x1800120dc  mov     r8d, 69636B53h
0x1800120e2  mov     edx, ebx
0x1800120e4  mov     ecx, 1
0x1800120e9  call    cs:__imp_SkAllocatePool
0x1800120f0  nop     dword ptr [rax+rax+00h]
0x1800120f5  mov     [rdi+0E0h], rax
0x1800120fc  test    rax, rax
0x1800120ff  jnz     short loc_180012144
0x180012101  mov     ebx, 0C0000017h
0x180012106  mov     rcx, rdi
0x180012109  call    SkciFreeImageContext
0x18001210e  mov     eax, ebx
0x180012110  mov     rbx, [rsp+70h+arg_0]
0x180012118  add     rsp, 70h
0x18001211c  pop     r15
0x18001211e  pop     r14
0x180012120  pop     r13
0x180012122  pop     r12
0x180012124  pop     rdi
0x180012125  pop     rsi
0x180012126  pop     rbp
0x180012127  retn
0x180012129  cmp     ecx, 98h
0x18001212f  jnb     short loc_1800120D9
0x180012131  mov     dword ptr [rbx], 0
0x180012137  mov     qword ptr [rdi+138h], 0
0x180012142  jmp     short loc_18001216A
0x180012144  mov     r8, rbx; MaxCount
0x180012147  mov     rdx, r12; Src
0x18001214a  mov     rcx, rax; void *
0x18001214d  call    memcpy_0
0x180012152  mov     rax, [rdi+0E0h]
0x180012159  sub     rax, r12
0x18001215c  add     rax, r14
0x18001215f  or      dword ptr [r15], 8
0x180012163  mov     [rdi+0E8h], rax
0x18001216a  lea     rcx, [rdi+0A0h]
0x180012171  call    cs:__imp_SkInitializePushLock
0x180012178  nop     dword ptr [rax+rax+00h]
0x18001217d  cmp     [rbp+arg_10], 0
0x180012181  jnz     short loc_1800121CD
0x180012183  mov     ecx, [rbp+arg_20]
0x180012186  lea     r8, [rdi+10h]
0x18001218a  lea     rax, [rdi+58h]
0x18001218e  mov     r9d, esi
0x180012191  mov     [rsp+70h+var_28], rax
0x180012196  lea     rdx, [rdi+60h]
0x18001219a  mov     [rsp+70h+var_30], rdx
0x18001219f  mov     rdx, r12
0x1800121a2  mov     [rsp+70h+var_50], r8
0x1800121a7  mov     r8d, [rdi+54h]
0x1800121ab  call    CiCalculateFirstPageHash
0x1800121b0  mov     ebx, eax
0x1800121b2  test    eax, eax
0x1800121b4  js      short loc_1800121BF
0x1800121b6  mov     rax, [rbp+arg_28]
0x1800121ba  mov     [rax], rdi
0x1800121bd  xor     edi, edi
0x1800121bf  test    rdi, rdi
0x1800121c2  jz      loc_18001210E
0x1800121c8  jmp     loc_180012106
0x1800121cd  movzx   eax, word ptr [r14+6]
0x1800121d2  mov     r8d, 69636B53h
0x1800121d8  mov     ecx, 1
0x1800121dd  lea     rdx, [rax+rax*4]
0x1800121e1  lea     rbx, ds:811Ch[rdx*8]
0x1800121e9  mov     rdx, rbx
0x1800121ec  call    cs:__imp_SkAllocatePool
0x1800121f3  nop     dword ptr [rax+rax+00h]
0x1800121f8  mov     r15, rax
0x1800121fb  test    rax, rax
0x1800121fe  jz      loc_180012101
0x180012204  mov     r8, rbx; Size
0x180012207  xor     edx, edx; Val
0x180012209  mov     rcx, rax; void *
0x18001220c  call    memset_0
0x180012211  mov     [r15], rbx
0x180012214  lea     rdx, [r15+10h]
0x180012218  mov     [rdi+0A8h], r15
0x18001221f  lea     rcx, [r15+108h]
0x180012226  movzx   eax, word ptr [r14+6]
0x18001222b  mov     r9d, r13d
0x18001222e  mov     [r15+8118h], eax
0x180012235  mov     r8, r12
0x180012238  lea     rax, [r15+110h]
0x18001223f  mov     [rsp+70h+var_30], rax
0x180012244  mov     eax, [rbp+arg_20]
0x180012247  mov     [rsp+70h+var_38], rcx
0x18001224c  mov     rcx, r14
0x18001224f  mov     [rsp+70h+var_40], rdx
0x180012254  mov     edx, dword ptr [rbp+MaxCount]
0x180012257  mov     dword ptr [rsp+70h+var_48], eax
0x18001225b  mov     dword ptr [rsp+70h+var_50], esi
0x18001225f  call    CiCreateVerificationContextForImageGeneratedPageHashes
0x180012264  mov     ebx, eax
0x180012266  test    eax, eax
0x180012268  js      loc_180012106
0x18001226e  mov     edx, [r15+8118h]
0x180012275  test    edx, edx
0x180012277  jz      short loc_180012291
0x180012279  movzx   ecx, word ptr [r14+14h]
0x18001227e  lea     r8, [r15+811Ch]
0x180012285  add     rcx, 18h
0x180012289  add     rcx, r14
0x18001228c  call    CiSortAndCopyImageSectionTable
0x180012291  movzx   edx, word ptr [r14+14h]
0x180012296  lea     r9, [rbp+var_20]
0x18001229a  mov     ecx, dword ptr [rbp+MaxCount]
0x18001229d  add     rdx, 18h
0x1800122a1  mov     r8d, [r15+8118h]
0x1800122a8  add     rdx, r14
0x1800122ab  call    CiGetFileOffsetAfterLastRawSectionData
0x1800122b0  mov     ebx, eax
0x1800122b2  test    eax, eax
0x1800122b4  js      loc_180012106
0x1800122ba  cmp     [rbp+var_20], esi
0x1800122bd  jbe     short loc_1800122C9
0x1800122bf  mov     ebx, 0C0000428h
0x1800122c4  jmp     loc_180012106
0x1800122c9  lea     r9, [rbp+var_18]
0x1800122cd  mov     r8d, r13d
0x1800122d0  mov     edx, esi
0x1800122d2  mov     rcx, r12
0x1800122d5  call    HashKGetCertificateInfo
0x1800122da  mov     ebx, eax
0x1800122dc  test    eax, eax
0x1800122de  js      loc_180012106
0x1800122e4  sub     esi, [rbp+var_20]
0x1800122e7  cmp     dword ptr [rbp+var_18+4], esi
0x1800122ea  ja      short loc_1800122BF
0x1800122ec  mov     rax, [rbp+arg_28]
0x1800122f0  sub     esi, dword ptr [rbp+var_18+4]
0x1800122f3  mov     [r15+114h], esi
0x1800122fa  mov     [rax], rdi
0x1800122fd  jmp     loc_18001210E
```
