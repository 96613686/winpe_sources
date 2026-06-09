# UdfQueryStreamsInfo

- ea: `0x14003269c`
- end: `0x140032cc6`
- name: `UdfQueryStreamsInfo`
- size: `1578`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140047a10`

## callees

- `0x140008b0c`
- `0x14000a288`
- `0x14000c3e8`
- `0x14000ca10`
- `0x140012c30`
- `0x14001bc30`
- `0x14001bd80`
- `0x14001c080`
- `0x1400312c0`
- `0x14003269c`
- `0x140041110`
- `0x140041860`
- `0x140041de0`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003285d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003285d`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140032959`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140032959`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400328ce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140032c0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b717`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400328ce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140032c0c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005b717`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003293e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140032c73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b7c8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003293e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140032c73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b7c8`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14003283e`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14003283e`

## pseudocode

```c
__int64 __fastcall UdfQueryStreamsInfo(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v7; // rsi
  __int64 v8; // r14
  unsigned __int64 v10; // r8
  int v11; // r14d
  int v12; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // r12
  unsigned int v15; // r13d
  int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rbx
  int *v20; // r8
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  int v24; // edx
  int v25; // edx
  __int64 v26; // rdx
  signed __int64 v27; // rdx
  char DirEntry; // al
  __int64 v29; // rax
  __int64 v30; // rax
  char v31; // [rsp+30h] [rbp-248h]
  char v32; // [rsp+31h] [rbp-247h]
  char v33; // [rsp+32h] [rbp-246h]
  unsigned int v34; // [rsp+34h] [rbp-244h]
  __int64 v36; // [rsp+48h] [rbp-230h]
  int v37; // [rsp+50h] [rbp-228h]
  __int64 v39; // [rsp+70h] [rbp-208h]
  int v40[100]; // [rsp+A0h] [rbp-1D8h] BYREF

  v7 = *(_QWORD *)(a2 + 136);
  v8 = *(_QWORD *)(v7 + 8);
  v36 = v8;
  memset(v40, 0, 0x188u);
  if ( *(_WORD *)(v8 + 2136) != 10 )
    return 3221225485LL;
  v39 = a3;
  memset((void *)a3, 0, (unsigned int)*a4);
  v10 = (unsigned int)*a4;
  if ( v10 < (unsigned __int64)(unsigned __int16)UdfStreamTypeNames + 26 )
    return 2147483653LL;
  if ( **(_WORD **)(v7 + 16) == 2356 )
  {
    v11 = (unsigned __int16)UdfStreamTypeNames + 26;
    *(_DWORD *)(a3 + 4) = (unsigned __int16)UdfStreamTypeNames + 2;
    *(_WORD *)(a3 + 24) = 58;
    memmove((void *)(a3 + 26), Source1, (unsigned __int16)UdfStreamTypeNames);
    *(_QWORD *)(a3 + 8) = *(_QWORD *)(a2 + 32);
    v12 = *(_DWORD *)(a2 + 212);
    if ( (v12 & 2) != 0 )
    {
      v13 = *(_QWORD *)(a2 + 32);
    }
    else if ( (v12 & 0x2000) != 0 )
    {
      v13 = (unsigned __int64)*(unsigned int *)(a2 + 324) << *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 72LL);
    }
    else
    {
      v13 = *(_QWORD *)(a2 + 24);
    }
    *(_QWORD *)(a3 + 16) = v13;
    *a4 -= v11;
    LODWORD(v10) = *a4;
    v14 = (v11 + 7) & 0xFFFFFFF8;
    v15 = ((v11 + 7) & 0xFFFFFFF8) - v11;
    a3 += v14;
  }
  else
  {
    LODWORD(v14) = 0;
    v15 = 0;
  }
  if ( !*(_DWORD *)(v7 + 56) )
    return 0;
  v16 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v17 = (unsigned __int16)UdfStreamTypeNames + 4LL;
  if ( (unsigned int)v10 < v17 + (unsigned __int64)(v15 + 24) )
    return 2147483653LL;
  if ( !*(_QWORD *)(v7 + 24) )
  {
    if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v7 + 80) + 8LL)) )
    {
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 8LL));
      v18 = *(_QWORD *)(*(_QWORD *)(a2 + 136) + 80LL) + 8LL;
      v19 = a1;
      UdfAcquireResource(a1, v18, 0, 0);
      v33 = 1;
    }
    else
    {
      v19 = a1;
    }
    if ( !*(_QWORD *)(v7 + 24) )
    {
      v16 = UdfOpenStreamDirectory(v19, *(_QWORD *)(v7 + 16), 1);
      if ( v16 < 0 )
        goto LABEL_45;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v36 + 1584));
      *(_QWORD *)(v36 + 1640) = KeGetCurrentThread();
      ++*(_DWORD *)(*(_QWORD *)(v7 + 24) + 204LL);
      ++*(_DWORD *)(*(_QWORD *)(v7 + 24) + 208LL);
      v21 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 136LL) + 8LL);
      ++*(_DWORD *)(v21 + 256);
      v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 136LL) + 8LL);
      ++*(_DWORD *)(v22 + 260);
      v31 = 1;
      *(_QWORD *)(v36 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v36 + 1584));
    }
    if ( v33 )
      ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)(v7 + 80) + 8LL));
  }
  UdfInitializeCompoundDirContext(v17, v40);
  v32 = 1;
  *(_QWORD *)&v40[70] = 1;
  v23 = a1;
  UdfLookupInitialDirEntry(a1, *(_QWORD *)(v7 + 24), v40, 0, 0, 0);
  v34 = 0;
  while ( 1 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)&v40[8] + 18LL) & 4) != 0 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          12,
          WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
      }
      goto LABEL_44;
    }
    UdfUpdateDirNames(v23, (__int64)v40, 0, 1);
    v24 = *(unsigned __int8 *)(*(_QWORD *)&v40[8] + 18LL);
    if ( (v24 & 0x18) != 0
      || LOWORD(v40[16]) >= 8u
      && **(_WORD **)&v40[18] == 42
      && *(_WORD *)(*(_QWORD *)&v40[18] + 2LL) == 85
      && *(_WORD *)(*(_QWORD *)&v40[18] + 4LL) == 68
      && *(_WORD *)(*(_QWORD *)&v40[18] + 6LL) == 70 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
      {
        WPP_SF_Zd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          v24,
          (_DWORD)v20,
          (unsigned int)&v40[16],
          *(_BYTE *)(*(_QWORD *)&v40[8] + 18LL));
      }
      goto LABEL_44;
    }
    v25 = (unsigned __int16)UdfStreamTypeNames + 2 + LOWORD(v40[16]);
    v37 = v25;
    if ( v15 + v25 + 24 > *a4 )
      break;
    *(_DWORD *)(a3 + 4) = v25;
    *(_WORD *)(a3 + 24) = 58;
    memmove((void *)(a3 + 26), *(const void **)&v40[18], LOWORD(v40[16]));
    memmove((void *)(a3 + 26 + LOWORD(v40[16])), Source1, (unsigned __int16)UdfStreamTypeNames);
    v23 = a1;
    UdfLookupFileEntryInEnumeration(a1, *(_QWORD *)(v7 + 24), v40);
    v26 = *(_QWORD *)&v40[42];
    v20 = *(int **)(*(_QWORD *)&v40[42] + 56LL);
    *(_QWORD *)(a3 + 8) = v20;
    v27 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v36 + 68) - 1)
        & ((unsigned int)(*(_DWORD *)(v36 + 68) - 1) + *(_QWORD *)(v26 + 56));
    *(_QWORD *)(a3 + 16) = v27;
    if ( (__int64)v20 < 0 || v27 < 0 )
    {
      v16 = -1073741566;
      goto LABEL_45;
    }
    *(_DWORD *)(v34 + v39) = v14 - v34;
    *a4 -= v37 + 24 + v15;
    v15 = ((v37 + 31) & 0xFFFFFFF8) - (v37 + 24);
    v34 = v14;
    LODWORD(v14) = ((v37 + 31) & 0xFFFFFFF8) + v14;
    a3 = v39 + (unsigned int)v14;
LABEL_44:
    DirEntry = UdfLookupNextDirEntry(v23, *(_QWORD *)(v7 + 24), (int)v40);
    v20 = &WPP_GLOBAL_Control;
    if ( !DirEntry )
      goto LABEL_45;
  }
  v16 = -2147483643;
LABEL_45:
  if ( v31 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v36 + 1584));
    *(_QWORD *)(v36 + 1640) = KeGetCurrentThread();
    --*(_DWORD *)(*(_QWORD *)(v7 + 24) + 204LL);
    --*(_DWORD *)(*(_QWORD *)(v7 + 24) + 208LL);
    v29 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 136LL) + 8LL);
    --*(_DWORD *)(v29 + 256);
    v30 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 136LL) + 8LL);
    --*(_DWORD *)(v30 + 260);
    *(_QWORD *)(v36 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v36 + 1584));
  }
  if ( v32 )
    UdfCleanupCompoundDirContext(a1, v40, v20);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14003269c  push    rbx
0x14003269e  push    rsi
0x14003269f  push    rdi
0x1400326a0  push    r12
0x1400326a2  push    r13
0x1400326a4  push    r14
0x1400326a6  push    r15
0x1400326a8  sub     rsp, 240h
0x1400326af  mov     rax, cs:__security_cookie
0x1400326b6  xor     rax, rsp
0x1400326b9  mov     [rsp+278h+var_48], rax
0x1400326c1  mov     rdi, r9
0x1400326c4  mov     [rsp+278h+var_220], r9
0x1400326c9  mov     r15, r8
0x1400326cc  mov     rbx, rdx
0x1400326cf  mov     qword ptr [rsp+278h+var_238], rcx
0x1400326d4  mov     [rsp+278h+var_1F0], rcx
0x1400326dc  mov     rsi, [rdx+88h]
0x1400326e3  mov     r14, [rsi+8]
0x1400326e7  mov     [rsp+278h+var_230], r14
0x1400326ec  mov     [rsp+278h+var_200], r14
0x1400326f1  xor     edx, edx; Val
0x1400326f3  mov     r8d, 188h; Size
0x1400326f9  lea     rcx, [rsp+278h+var_1D8]; void *
0x140032701  call    memset
0x140032706  mov     eax, 0Ah
0x14003270b  cmp     ax, [r14+858h]
0x140032713  jz      short loc_14003271F
0x140032715  mov     eax, 0C000000Dh
0x14003271a  jmp     loc_140032CA2
0x14003271f  mov     [rsp+278h+var_1F8], rsi
0x140032727  mov     [rsp+278h+var_208], r15
0x14003272c  mov     r8d, [rdi]; Size
0x14003272f  xor     edx, edx; Val
0x140032731  mov     rcx, r15; void *
0x140032734  call    memset
0x140032739  mov     r8d, [rdi]
0x14003273c  movzx   ecx, cs:UdfStreamTypeNames
0x140032743  lea     rax, [rcx+1Ah]
0x140032747  cmp     r8, rax
0x14003274a  jb      loc_140032C9D
0x140032750  mov     rax, [rsi+10h]
0x140032754  mov     edx, 934h
0x140032759  cmp     dx, [rax]
0x14003275c  jnz     loc_1400327E8
0x140032762  lea     eax, [rcx+2]
0x140032765  lea     r14d, [rax+18h]
0x140032769  mov     [r15+4], eax
0x14003276d  mov     word ptr [r15+18h], 3Ah ; ':'
0x140032774  movzx   r8d, cs:UdfStreamTypeNames; Size
0x14003277c  lea     rcx, [r15+1Ah]; void *
0x140032780  mov     rdx, cs:Source1; Src
0x140032787  call    memmove
0x14003278c  mov     rax, [rbx+20h]
0x140032790  mov     [r15+8], rax
0x140032794  mov     eax, [rbx+0D4h]
0x14003279a  test    al, 2
0x14003279c  jz      short loc_1400327A4
0x14003279e  mov     rdx, [rbx+20h]
0x1400327a2  jmp     short loc_1400327C7
0x1400327a4  bt      eax, 0Dh
0x1400327a8  jnb     short loc_1400327C3
0x1400327aa  mov     edx, [rbx+144h]
0x1400327b0  mov     rax, [rbx+88h]
0x1400327b7  mov     rcx, [rax+8]
0x1400327bb  mov     ecx, [rcx+48h]
0x1400327be  shl     rdx, cl
0x1400327c1  jmp     short loc_1400327C7
0x1400327c3  mov     rdx, [rbx+18h]
0x1400327c7  mov     [r15+10h], rdx
0x1400327cb  sub     [rdi], r14d
0x1400327ce  mov     r8d, [rdi]
0x1400327d1  lea     eax, [r14+7]
0x1400327d5  and     eax, 0FFFFFFF8h
0x1400327d8  mov     r12d, eax
0x1400327db  mov     r13d, eax
0x1400327de  sub     r13d, r14d
0x1400327e1  add     r15, r12
0x1400327e4  xor     edi, edi
0x1400327e6  jmp     short loc_1400327F0
0x1400327e8  xor     edi, edi
0x1400327ea  mov     r12d, edi
0x1400327ed  mov     r13d, edi
0x1400327f0  cmp     [rsi+38h], edi
0x1400327f3  jnz     short loc_1400327FC
0x1400327f5  xor     eax, eax
0x1400327f7  jmp     loc_140032CA2
0x1400327fc  mov     r14d, edi
0x1400327ff  mov     [rsp+278h+var_248], dil
0x140032804  mov     [rsp+278h+var_247], dil
0x140032809  mov     [rsp+278h+var_246], dil
0x14003280e  lea     edx, [r13+18h]
0x140032812  movzx   ecx, cs:UdfStreamTypeNames
0x140032819  add     rcx, 4
0x14003281d  add     rdx, rcx
0x140032820  mov     eax, r8d
0x140032823  cmp     rax, rdx
0x140032826  jb      loc_140032C9D
0x14003282c  cmp     [rsi+18h], rdi
0x140032830  jnz     loc_140032965
0x140032836  mov     rcx, [rsi+50h]
0x14003283a  add     rcx, 8; Resource
0x14003283e  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140032845  nop     dword ptr [rax+rax+00h]
0x14003284a  test    eax, eax
0x14003284c  jz      short loc_140032892
0x14003284e  mov     rax, [rbx+88h]
0x140032855  mov     rcx, [rax+50h]
0x140032859  add     rcx, 8; Resource
0x14003285d  call    cs:__imp_ExReleaseResourceLite
0x140032864  nop     dword ptr [rax+rax+00h]
0x140032869  mov     rax, [rbx+88h]
0x140032870  mov     rdx, [rax+50h]
0x140032874  add     rdx, 8
0x140032878  xor     r9d, r9d
0x14003287b  xor     r8d, r8d
0x14003287e  mov     rbx, qword ptr [rsp+278h+var_238]
0x140032883  mov     rcx, rbx
0x140032886  call    UdfAcquireResource
0x14003288b  mov     [rsp+278h+var_246], 1
0x140032890  jmp     short loc_140032897
0x140032892  mov     rbx, qword ptr [rsp+278h+var_238]
0x140032897  cmp     [rsi+18h], rdi
0x14003289b  jnz     loc_14003294A
0x1400328a1  mov     r8d, 1
0x1400328a7  mov     rdx, [rsi+10h]
0x1400328ab  mov     rcx, rbx
0x1400328ae  call    UdfOpenStreamDirectory
0x1400328b3  mov     r14d, eax
0x1400328b6  mov     [rsp+278h+var_240], eax
0x1400328ba  test    eax, eax
0x1400328bc  js      loc_140032BF2
0x1400328c2  mov     rbx, [rsp+278h+var_230]
0x1400328c7  lea     rcx, [rbx+630h]; FastMutex
0x1400328ce  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400328d5  nop     dword ptr [rax+rax+00h]
0x1400328da  mov     rcx, gs:188h
0x1400328e3  mov     r8, rbx
0x1400328e6  mov     [rbx+668h], rcx
0x1400328ed  mov     rcx, [rsi+18h]
0x1400328f1  inc     dword ptr [rcx+0CCh]
0x1400328f7  mov     rdx, [rsi+18h]
0x1400328fb  inc     dword ptr [rdx+0D0h]
0x140032901  mov     rax, [rsi+18h]
0x140032905  mov     rdx, [rax+88h]
0x14003290c  mov     rax, [rdx+8]
0x140032910  inc     dword ptr [rax+100h]
0x140032916  mov     rax, [rsi+18h]
0x14003291a  mov     rdx, [rax+88h]
0x140032921  mov     rax, [rdx+8]
0x140032925  inc     dword ptr [rax+104h]
0x14003292b  mov     [rsp+278h+var_248], 1
0x140032930  mov     [rbx+668h], rdi
0x140032937  lea     rcx, [rbx+630h]; FastMutex
0x14003293e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140032945  nop     dword ptr [rax+rax+00h]
0x14003294a  cmp     [rsp+278h+var_246], dil
0x14003294f  jz      short loc_140032965
0x140032951  mov     rcx, [rsi+50h]
0x140032955  add     rcx, 8; Resource
0x140032959  call    cs:__imp_ExConvertExclusiveToSharedLite
0x140032960  nop     dword ptr [rax+rax+00h]
0x140032965  lea     rdx, [rsp+278h+var_1D8]
0x14003296d  call    UdfInitializeCompoundDirContext
0x140032972  mov     [rsp+278h+var_247], 1
0x140032977  mov     [rsp+278h+var_C0], 1
0x140032983  mov     [rsp+278h+var_250], edi; int
0x140032987  mov     [rsp+278h+var_258], dil; char
0x14003298c  xor     r9d, r9d
0x14003298f  lea     r8, [rsp+278h+var_1D8]; int
0x140032997  mov     rdx, [rsi+18h]; int
0x14003299b  mov     rbx, qword ptr [rsp+278h+var_238]
0x1400329a0  mov     rcx, rbx; int
0x1400329a3  call    UdfLookupInitialDirEntry
0x1400329a8  mov     [rsp+278h+var_244], edi
0x1400329ac  lea     r8, WPP_GLOBAL_Control
0x1400329b3  mov     rax, [rsp+278h+var_1B8]
0x1400329bb  movzx   edx, byte ptr [rax+12h]
0x1400329bf  test    dl, 4
0x1400329c2  jz      short loc_1400329FE
0x1400329c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400329cb  cmp     rcx, r8
0x1400329ce  jz      loc_140032BCF
0x1400329d4  test    dword ptr [rcx+2Ch], 200h
0x1400329db  jz      loc_140032BCF
0x1400329e1  mov     r9d, edx
0x1400329e4  mov     edx, 0Ch
0x1400329e9  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x1400329f0  mov     rcx, [rcx+18h]
0x1400329f4  call    WPP_SF_d
0x1400329f9  jmp     loc_140032BCF
0x1400329fe  mov     r9b, 1
0x140032a01  xor     r8d, r8d
0x140032a04  lea     rdx, [rsp+278h+var_1D8]
0x140032a0c  mov     rcx, rbx
0x140032a0f  call    UdfUpdateDirNames
0x140032a14  mov     rax, [rsp+278h+var_1B8]
0x140032a1c  movzx   edx, byte ptr [rax+12h]
0x140032a20  test    dl, 18h
0x140032a23  jnz     loc_140032B9E
0x140032a29  mov     eax, 8
0x140032a2e  cmp     [rsp+278h+var_198], ax
0x140032a36  jb      short loc_140032A6D
0x140032a38  lea     ecx, [rax+22h]
0x140032a3b  mov     rax, [rsp+278h+Src]
0x140032a43  cmp     cx, [rax]
0x140032a46  jnz     short loc_140032A6D
0x140032a48  mov     ecx, 55h ; 'U'
0x140032a4d  cmp     cx, [rax+2]
0x140032a51  jnz     short loc_140032A6D
0x140032a53  mov     ecx, 44h ; 'D'
0x140032a58  cmp     cx, [rax+4]
0x140032a5c  jnz     short loc_140032A6D
0x140032a5e  mov     ecx, 46h ; 'F'
0x140032a63  cmp     cx, [rax+6]
0x140032a67  jz      loc_140032B9E
0x140032a6d  movzx   edx, [rsp+278h+var_198]
0x140032a75  movzx   eax, cs:UdfStreamTypeNames
0x140032a7c  add     eax, 2
0x140032a7f  add     edx, eax
0x140032a81  mov     [rsp+278h+var_228], edx
0x140032a85  lea     eax, [rdx+18h]
0x140032a88  add     eax, r13d
0x140032a8b  mov     rcx, [rsp+278h+var_220]
0x140032a90  cmp     eax, [rcx]
0x140032a92  ja      loc_140032B96
0x140032a98  mov     [r15+4], edx
0x140032a9c  mov     eax, 3Ah ; ':'
0x140032aa1  mov     [r15+18h], ax
0x140032aa6  lea     rbx, [r15+1Ah]
0x140032aaa  movzx   r8d, [rsp+278h+var_198]; Size
0x140032ab3  mov     rdx, [rsp+278h+Src]; Src
0x140032abb  mov     rcx, rbx; void *
0x140032abe  call    memmove
0x140032ac3  movzx   r8d, cs:UdfStreamTypeNames; Size
0x140032acb  movzx   ecx, [rsp+278h+var_198]
0x140032ad3  add     rcx, rbx; void *
0x140032ad6  mov     rdx, cs:Source1; Src
0x140032add  call    memmove
0x140032ae2  lea     r8, [rsp+278h+var_1D8]
0x140032aea  mov     rdx, [rsi+18h]
0x140032aee  mov     rbx, qword ptr [rsp+278h+var_238]
0x140032af3  mov     rcx, rbx
0x140032af6  call    UdfLookupFileEntryInEnumeration
0x140032afb  mov     rdx, [rsp+278h+var_130]
0x140032b03  mov     r8, [rdx+38h]
0x140032b07  mov     [r15+8], r8
0x140032b0b  mov     rax, [rsp+278h+var_230]
0x140032b10  mov     ecx, [rax+44h]
0x140032b13  dec     ecx
0x140032b15  mov     rax, [rdx+38h]
0x140032b19  lea     rdx, [rcx+rax]
0x140032b1d  not     rcx
0x140032b20  and     rdx, rcx
0x140032b23  mov     [r15+10h], rdx
0x140032b27  test    r8, r8
0x140032b2a  js      short loc_140032B89
0x140032b2c  test    rdx, rdx
0x140032b2f  js      short loc_140032B89
0x140032b31  mov     ecx, r12d
0x140032b34  mov     eax, [rsp+278h+var_244]
0x140032b38  sub     ecx, eax
0x140032b3a  mov     r8, [rsp+278h+var_208]
0x140032b3f  mov     [rax+r8], ecx
0x140032b43  mov     edx, [rsp+278h+var_228]
0x140032b47  add     edx, 18h
0x140032b4a  lea     eax, [rdx+r13]
0x140032b4e  mov     rcx, [rsp+278h+var_220]
0x140032b53  sub     [rcx], eax
0x140032b55  lea     eax, [rdx+7]
0x140032b58  and     eax, 0FFFFFFF8h
0x140032b5b  mov     r13d, eax
0x140032b5e  sub     r13d, edx
0x140032b61  mov     [rsp+278h+var_218], r13d
0x140032b66  mov     ecx, r12d
0x140032b69  mov     [rsp+278h+var_244], ecx
0x140032b6d  mov     [rsp+278h+var_214], ecx
0x140032b71  add     r12d, eax
0x140032b74  mov     [rsp+278h+var_210], r12d
0x140032b79  mov     r15d, r12d
0x140032b7c  add     r15, r8
0x140032b7f  mov     [rsp+278h+var_1E8], r15
0x140032b87  jmp     short loc_140032BCF
0x140032b89  mov     r14d, 0C0000102h
0x140032b8f  mov     [rsp+278h+var_240], r14d
0x140032b94  jmp     short loc_140032BF2
0x140032b96  mov     r14d, 80000005h
0x140032b9c  jmp     short loc_140032B8F
0x140032b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ba5  lea     rax, WPP_GLOBAL_Control
0x140032bac  cmp     rcx, rax
0x140032baf  jz      short loc_140032BCF
0x140032bb1  test    dword ptr [rcx+2Ch], 200h
0x140032bb8  jz      short loc_140032BCF
0x140032bba  mov     dword ptr [rsp+278h+var_258], edx
0x140032bbe  lea     r9, [rsp+278h+var_198]
0x140032bc6  mov     rcx, [rcx+18h]
0x140032bca  call    WPP_SF_Zd
0x140032bcf  lea     r8, [rsp+278h+var_1D8]; int
0x140032bd7  mov     rdx, [rsi+18h]; int
  ... truncated ...
```
