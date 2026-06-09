# Srv2UpdateNetnameTable

- ea: `0x140012e00`
- end: `0x1400135d7`
- name: `Srv2UpdateNetnameTable`
- size: `2007`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x140010af8`
- `0x140012e00`
- `0x1400135e0`
- `0x140013620`
- `0x140025054`
- `0x140038490`
- `0x1400384d0`
- `0x140038560`
- `0x140038680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012e2f`
- `ntoskrnl!ExAllocatePool2` at `0x140012e2f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013376`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013376`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012eca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012eca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001304b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013194`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013363`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001304b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013194`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013363`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133e8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140012fae`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001341e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140012fae`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001341e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400134aa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400134aa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001351b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013531`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001351b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013531`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013505`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140013505`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012e8c`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140012e8c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400131e5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400131e5`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400134d2`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400134ee`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400134d2`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400134ee`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140013546`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140013546`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001311a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400132ce`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001311a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400132ce`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013170`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013170`

## pseudocode

```c
__int64 __fastcall Srv2UpdateNetnameTable(void *Src, size_t Size)
{
  unsigned int v2; // ebx
  __int64 Pool2; // rax
  __int64 v5; // rdi
  UNICODE_STRING *v6; // r15
  __int64 v7; // rax
  NTSTATUS v8; // r12d
  int v9; // ebx
  int v10; // edx
  _DWORD *v11; // rsi
  __int64 v12; // r13
  unsigned int Length; // ebp
  unsigned int v14; // eax
  __int64 v15; // r8
  __m128i v16; // xmm3
  __m128i v17; // xmm2
  __m128i v18; // xmm1
  __int64 v19; // rax
  __m128i v20; // xmm2
  __m128i v21; // xmm2
  int v22; // edx
  __int64 v23; // r15
  _QWORD *v24; // r14
  _QWORD *i; // rax
  volatile signed __int32 *v26; // rbx
  void (__fastcall *v27)(volatile signed __int32 *); // rax
  unsigned int v28; // eax
  unsigned int v29; // r9d
  volatile signed __int32 *v30; // rbp
  unsigned int v31; // eax
  __int64 v32; // r10
  __int64 v33; // r8
  __m128i v34; // xmm3
  __m128i v35; // xmm2
  __m128i v36; // xmm1
  __int64 v37; // rax
  __m128i v38; // xmm2
  __m128i v39; // xmm2
  int v40; // edx
  __int64 v41; // rsi
  KIRQL v42; // r14
  volatile signed __int32 *v43; // rax
  volatile signed __int32 **v44; // rcx
  int v45; // r13d
  _QWORD *v46; // rbp
  volatile signed __int32 *v47; // rsi
  __int64 v48; // r10
  unsigned int v49; // r9d
  unsigned int v50; // eax
  __int64 v51; // r8
  __m128i v52; // xmm3
  __m128i v53; // xmm2
  __m128i v54; // xmm1
  __int64 v55; // rax
  __m128i v56; // xmm2
  __m128i v57; // xmm2
  int v58; // edx
  __int64 v59; // rbx
  KIRQL v60; // bp
  unsigned int v61; // eax
  _QWORD *v62; // rcx
  __int64 v63; // r8
  _QWORD *v64; // rdx
  char v65; // bl
  KIRQL v67; // r12
  unsigned int j; // esi
  __int64 v69; // rbx
  _QWORD *k; // r9
  __int64 v71; // rax
  unsigned int *v72; // r8
  unsigned int *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rcx
  unsigned int *v76; // rsi
  __int64 v77; // rax
  int v78; // [rsp+50h] [rbp-68h]
  KIRQL v79; // [rsp+60h] [rbp-58h]
  __int128 v80; // [rsp+68h] [rbp-50h] BYREF

  v2 = Size;
  Pool2 = ExAllocatePool2(66, (unsigned int)(Size + 24), 1852724044);
  v5 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = Pool2;
    *(_QWORD *)Pool2 = Pool2;
    v6 = (UNICODE_STRING *)(Pool2 + 24);
    *(_DWORD *)(Pool2 + 16) = 1;
    memmove((void *)(Pool2 + 24), Src, v2);
    v7 = *(_QWORD *)(v5 + 32);
    if ( v7 )
      *(_QWORD *)(v5 + 32) = v5 + v7 + 24;
    v8 = RtlUpcaseUnicodeString(v6, v6, 0);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          (unsigned int)WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
          (_DWORD)v6,
          v8);
      }
      ExFreePoolWithTag((PVOID)v5, 0);
      return (unsigned int)v8;
    }
    v9 = 0;
    ExAcquireResourceExclusiveLite(&Smb2NameLock, 1u);
    v11 = Smb2NetnameTable;
    if ( Smb2NetnameTable )
    {
      if ( *((_QWORD *)Smb2NetnameTable + 4) )
      {
        v12 = *(_QWORD *)(v5 + 32);
        if ( v12 )
        {
          Length = v6->Length;
          v14 = 0;
          if ( v6->Length )
          {
            v15 = 0;
            if ( Length < 8 )
              goto LABEL_120;
            v16 = 0;
            v17 = 0;
            do
            {
              v18 = _mm_cvtsi32_si128(*(_DWORD *)(v15 + v12));
              v19 = (unsigned int)(v15 + 4);
              v15 = (unsigned int)(v15 + 8);
              v16 = _mm_add_epi32(v16, _mm_unpacklo_epi16(_mm_unpacklo_epi8(v18, (__m128i)0LL), (__m128i)0LL));
              v17 = _mm_add_epi32(
                      v17,
                      _mm_unpacklo_epi16(
                        _mm_unpacklo_epi8(_mm_cvtsi32_si128(*(_DWORD *)(v19 + v12)), (__m128i)0LL),
                        (__m128i)0LL));
            }
            while ( (unsigned int)v15 < (Length & 0xFFFFFFF8) );
            v20 = _mm_add_epi32(v17, v16);
            v21 = _mm_add_epi32(v20, _mm_srli_si128(v20, 8));
            v14 = _mm_cvtsi128_si32(_mm_add_epi32(v21, _mm_srli_si128(v21, 4)));
            if ( (unsigned int)v15 < Length )
            {
LABEL_120:
              do
              {
                v22 = *(unsigned __int8 *)(v15 + v12);
                v15 = (unsigned int)(v15 + 1);
                v14 += v22;
              }
              while ( (unsigned int)v15 < Length );
            }
          }
          v23 = *((_QWORD *)Smb2NetnameTable + 7) + 32LL * (v14 % *(_DWORD *)Smb2NetnameTable);
          if ( (*(_DWORD *)(v23 + 12) & 1) != 0 )
          {
            v79 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v23);
          }
          else
          {
            v79 = 0;
            ExAcquirePushLockSharedEx(v23, 0);
          }
          v24 = *(_QWORD **)(v23 + 16);
          for ( i = (_QWORD *)(v23 + 16); ; i = (_QWORD *)(v23 + 16) )
          {
            if ( v24 == i )
            {
              v26 = 0;
              goto LABEL_21;
            }
            v26 = (volatile signed __int32 *)((char *)v24 - v11[1]);
            if ( (*((unsigned __int8 (__fastcall **)(volatile signed __int32 *, __int64, _QWORD))v11 + 4))(
                   v26,
                   v12,
                   Length) )
            {
              break;
            }
            v24 = (_QWORD *)*v24;
          }
          v27 = (void (__fastcall *)(volatile signed __int32 *))*((_QWORD *)v11 + 3);
          if ( v27 )
            v27(v26);
LABEL_21:
          RfsHashBucketReleaseLockShared(v23, v79);
          if ( v26 )
          {
            v28 = *(_DWORD *)(v5 + 44);
            if ( v28 == *((_DWORD *)v26 + 11) && !memcmp((const void *)(v5 + 48), (const void *)(v26 + 12), v28) )
            {
              if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) == 1 )
                ExFreePoolWithTag((PVOID)v26, 0);
              v8 = 0;
              goto LABEL_68;
            }
            v29 = *(unsigned __int16 *)(v5 + 24);
            v6 = (UNICODE_STRING *)(v5 + 24);
            v30 = (volatile signed __int32 *)Smb2NetnameTable;
            v31 = 0;
            if ( *(_WORD *)(v5 + 24) )
            {
              v32 = *(_QWORD *)(v5 + 32);
              v33 = 0;
              if ( v29 < 8 )
                goto LABEL_121;
              v34 = 0;
              v35 = 0;
              do
              {
                v36 = _mm_cvtsi32_si128(*(_DWORD *)(v33 + v32));
                v37 = (unsigned int)(v33 + 4);
                v33 = (unsigned int)(v33 + 8);
                v34 = _mm_add_epi32(v34, _mm_unpacklo_epi16(_mm_unpacklo_epi8(v36, (__m128i)0LL), (__m128i)0LL));
                v35 = _mm_add_epi32(
                        v35,
                        _mm_unpacklo_epi16(
                          _mm_unpacklo_epi8(_mm_cvtsi32_si128(*(_DWORD *)(v37 + v32)), (__m128i)0LL),
                          (__m128i)0LL));
              }
              while ( (unsigned int)v33 < (v29 & 0xFFFFFFF8) );
              v38 = _mm_add_epi32(v35, v34);
              v39 = _mm_add_epi32(v38, _mm_srli_si128(v38, 8));
              v31 = _mm_cvtsi128_si32(_mm_add_epi32(v39, _mm_srli_si128(v39, 4)));
              if ( (unsigned int)v33 < v29 )
              {
LABEL_121:
                do
                {
                  v40 = *(unsigned __int8 *)(v33 + v32);
                  v33 = (unsigned int)(v33 + 1);
                  v31 += v40;
                }
                while ( (unsigned int)v33 < v29 );
              }
            }
            v41 = *((_QWORD *)Smb2NetnameTable + 7) + 32LL * (v31 % *(_DWORD *)Smb2NetnameTable);
            if ( (*(_DWORD *)(v41 + 12) & 1) != 0 )
            {
              v42 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v41);
            }
            else
            {
              v42 = 0;
              ExAcquirePushLockExclusiveEx(v41, 0);
            }
            v43 = *(volatile signed __int32 **)v26;
            if ( *(volatile signed __int32 **)v26 != v26 )
            {
              if ( *((volatile signed __int32 **)v43 + 1) != v26 )
                goto LABEL_110;
              v44 = (volatile signed __int32 **)*((_QWORD *)v26 + 1);
              if ( *v44 != v26 )
                goto LABEL_110;
              *v44 = v43;
              *((_QWORD *)v43 + 1) = v44;
              *((_QWORD *)v26 + 1) = v26;
              *(_QWORD *)v26 = v26;
              _InterlockedDecrement(v30 + 2);
              --*(_DWORD *)(v41 + 8);
            }
            if ( (*(_DWORD *)(v41 + 12) & 1) != 0 )
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v41, v42);
            else
              ExReleasePushLockExclusiveEx(v41, 0);
            if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) == 1 )
              ExFreePoolWithTag((PVOID)v26, 0);
            if ( _InterlockedExchangeAdd(v26 + 4, 0xFFFFFFFF) == 1 )
              ExFreePoolWithTag((PVOID)v26, 0);
            v9 = 1;
          }
          else
          {
            v9 = 0;
            v6 = (UNICODE_STRING *)(v5 + 24);
          }
        }
      }
    }
    if ( (*(_DWORD *)(v5 + 40) & 1) == 0 )
    {
      v45 = 2;
      v65 = 1;
      goto LABEL_66;
    }
    v45 = v9 == 1;
    if ( RtlEqualUnicodeString(&Smb2DefaultServerName, v6, 0) )
    {
      if ( *(_DWORD *)(v5 + 44) )
      {
        v46 = Smb2NetnameTable;
        if ( Smb2NetnameTable )
        {
          v67 = 0;
          for ( j = 0; j < *(_DWORD *)v46; ++j )
          {
            v69 = v46[7] + 32LL * j;
            if ( (*(_DWORD *)(v69 + 12) & 1) != 0 )
              v67 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v69);
            else
              ExAcquirePushLockSharedEx(v69, 0);
            for ( k = *(_QWORD **)(v69 + 16); k != (_QWORD *)(v69 + 16); k = (_QWORD *)*k )
            {
              v71 = -*((_DWORD *)v46 + 1);
              if ( *(_DWORD *)((char *)k + v71 + 44) )
              {
                v72 = (unsigned int *)((char *)k + v71 + 48);
                do
                {
                  v73 = (unsigned int *)(v5 + 48);
                  if ( v5 != -48 )
                  {
                    while ( v72[1] != v73[1] )
                    {
                      v75 = *v73;
                      if ( (_DWORD)v75 )
                      {
                        v73 = (unsigned int *)((char *)v73 + v75);
                        if ( v73 )
                          continue;
                      }
                      goto LABEL_84;
                    }
                    v72[2] = v73[2];
                    v72[3] = v73[3];
                    *((_QWORD *)v72 + 2) = *((_QWORD *)v73 + 2);
                  }
LABEL_84:
                  v74 = *v72;
                  if ( !(_DWORD)v74 )
                    break;
                  v72 = (unsigned int *)((char *)v72 + v74);
                }
                while ( v72 );
              }
            }
            if ( (*(_DWORD *)(v69 + 12) & 1) != 0 )
              ExReleaseSpinLockShared((PEX_SPIN_LOCK)v69, v67);
            else
              ExReleasePushLockSharedEx(v69, 0);
          }
        }
      }
    }
    v47 = (volatile signed __int32 *)Smb2NetnameTable;
    if ( !Smb2NetnameTable || (v48 = *(_QWORD *)(v5 + 32)) == 0 )
    {
      v8 = -1073741811;
      goto LABEL_68;
    }
    v49 = v6->Length;
    v50 = 0;
    if ( v6->Length )
    {
      v51 = 0;
      if ( v49 < 8 )
        goto LABEL_122;
      v52 = 0;
      v53 = 0;
      do
      {
        v54 = _mm_cvtsi32_si128(*(_DWORD *)(v51 + v48));
        v55 = (unsigned int)(v51 + 4);
        v51 = (unsigned int)(v51 + 8);
        v52 = _mm_add_epi32(v52, _mm_unpacklo_epi16(_mm_unpacklo_epi8(v54, (__m128i)0LL), (__m128i)0LL));
        v53 = _mm_add_epi32(
                v53,
                _mm_unpacklo_epi16(
                  _mm_unpacklo_epi8(_mm_cvtsi32_si128(*(_DWORD *)(v55 + v48)), (__m128i)0LL),
                  (__m128i)0LL));
      }
      while ( (unsigned int)v51 < (v49 & 0xFFFFFFF8) );
      v56 = _mm_add_epi32(v53, v52);
      v57 = _mm_add_epi32(v56, _mm_srli_si128(v56, 8));
      v50 = _mm_cvtsi128_si32(_mm_add_epi32(v57, _mm_srli_si128(v57, 4)));
      if ( (unsigned int)v51 < v49 )
      {
LABEL_122:
        do
        {
          v58 = *(unsigned __int8 *)(v51 + v48);
          v51 = (unsigned int)(v51 + 1);
          v50 += v58;
        }
        while ( (unsigned int)v51 < v49 );
      }
    }
    v59 = *((_QWORD *)Smb2NetnameTable + 7) + 32LL * (v50 % *(_DWORD *)Smb2NetnameTable);
    if ( (*(_DWORD *)(v59 + 12) & 1) != 0 )
    {
      v60 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v59);
    }
    else
    {
      v60 = 0;
      ExAcquirePushLockExclusiveEx(v59, 0);
    }
    v61 = *((_DWORD *)v47 + 4);
    if ( _InterlockedIncrement(v47 + 2) > v61 )
    {
      _InterlockedDecrement(v47 + 2);
      v8 = -1073741670;
LABEL_63:
      RfsHashBucketReleaseLockExclusive(v59, v60);
      if ( v8 >= 0 )
      {
        v65 = 0;
LABEL_66:
        v80 = 0;
        if ( v45 != 1 )
        {
          if ( *(_DWORD *)(v5 + 44) )
          {
            v76 = (unsigned int *)(v5 + 48);
            if ( v5 != -48 )
            {
              do
              {
                if ( (byte_14004C339 & 0x10) != 0 )
                  McTemplateK0qhzr1dqdxhbr7_EtwWriteTransfer(
                    v6->Length >> 1,
                    v10,
                    (unsigned int)&v80,
                    v45,
                    v6->Length >> 1,
                    *(_QWORD *)(v5 + 32),
                    *(_DWORD *)(v5 + 40),
                    v76[1],
                    v76[2],
                    *((_QWORD *)v76 + 2),
                    v78,
                    (__int64)(v76 + 6));
                v77 = *v76;
                if ( !(_DWORD)v77 )
                  break;
                v76 = (unsigned int *)((char *)v76 + v77);
              }
              while ( v76 );
            }
          }
        }
        if ( !v65 )
          goto LABEL_70;
      }
LABEL_68:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag((PVOID)v5, 0);
LABEL_70:
      ExReleaseResourceLite(&Smb2NameLock);
      return (unsigned int)v8;
    }
    ++*(_DWORD *)(v59 + 8);
    v62 = (_QWORD *)(v59 + 16);
    v63 = *(_QWORD *)(v59 + 16);
    if ( *(_QWORD *)(v63 + 8) == v59 + 16 )
    {
      v8 = 0;
      v64 = (_QWORD *)(v5 + *((unsigned int *)v47 + 1));
      *v64 = v63;
      v64[1] = v62;
      *(_QWORD *)(v63 + 8) = v64;
      *v62 = v64;
      goto LABEL_63;
    }
LABEL_110:
    __fastfail(3u);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140012e00  push    rbx
0x140012e02  push    rsi
0x140012e03  push    rdi
0x140012e04  push    r12
0x140012e06  sub     rsp, 98h
0x140012e0d  mov     rax, cs:__security_cookie
0x140012e14  xor     rax, rsp
0x140012e17  mov     [rsp+0B8h+var_40], rax
0x140012e1c  mov     ebx, edx
0x140012e1e  mov     rsi, rcx
0x140012e21  mov     ecx, 42h ; 'B'
0x140012e26  mov     r8d, 6E6E534Ch
0x140012e2c  lea     edx, [rbx+18h]
0x140012e2f  call    cs:__imp_ExAllocatePool2
0x140012e36  nop     dword ptr [rax+rax+00h]
0x140012e3b  mov     rdi, rax
0x140012e3e  test    rax, rax
0x140012e41  jz      loc_1400134BD
0x140012e47  mov     [rax+8], rax
0x140012e4b  mov     r8d, ebx; Size
0x140012e4e  mov     [rax], rax
0x140012e51  mov     rdx, rsi; Src
0x140012e54  mov     [rsp+0B8h+var_38], r15
0x140012e5c  lea     r15, [rax+18h]
0x140012e60  mov     rcx, r15; void *
0x140012e63  mov     dword ptr [rax+10h], 1
0x140012e6a  call    memmove
0x140012e6f  mov     rax, [rdi+20h]
0x140012e73  test    rax, rax
0x140012e76  jz      short loc_140012E83
0x140012e78  add     rax, 18h
0x140012e7c  add     rax, rdi
0x140012e7f  mov     [rdi+20h], rax
0x140012e83  xor     r8d, r8d; AllocateDestinationString
0x140012e86  mov     rdx, r15; SourceString
0x140012e89  mov     rcx, r15; DestinationString
0x140012e8c  call    cs:__imp_RtlUpcaseUnicodeString
0x140012e93  nop     dword ptr [rax+rax+00h]
0x140012e98  mov     r12d, eax
0x140012e9b  test    eax, eax
0x140012e9d  js      loc_1400133CC
0x140012ea3  mov     [rsp+0B8h+arg_10], rbp
0x140012eab  lea     rcx, Smb2NameLock; Resource
0x140012eb2  xor     ebx, ebx
0x140012eb4  mov     [rsp+0B8h+var_28], r13
0x140012ebc  mov     dl, 1; Wait
0x140012ebe  mov     [rsp+0B8h+var_30], r14
0x140012ec6  mov     [rsp+0B8h+var_54], ebx
0x140012eca  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012ed1  nop     dword ptr [rax+rax+00h]
0x140012ed6  mov     rsi, cs:Smb2NetnameTable
0x140012edd  mov     r14d, 0FFFFFFFFh
0x140012ee3  test    rsi, rsi
0x140012ee6  jz      loc_1400131C3
0x140012eec  cmp     [rsi+20h], rbx
0x140012ef0  jz      loc_1400131C3
0x140012ef6  mov     r13, [rdi+20h]
0x140012efa  test    r13, r13
0x140012efd  jz      loc_1400131C3
0x140012f03  movzx   ebp, word ptr [r15]
0x140012f07  xor     eax, eax
0x140012f09  test    ebp, ebp
0x140012f0b  jz      short loc_140012F8A
0x140012f0d  xor     r8d, r8d
0x140012f10  cmp     ebp, 8
0x140012f13  jb      short loc_140012F7B
0x140012f15  mov     edx, ebp
0x140012f17  xorps   xmm3, xmm3
0x140012f1a  and     edx, 0FFFFFFF8h
0x140012f1d  xorps   xmm2, xmm2
0x140012f20  movd    xmm1, dword ptr [r8+r13]
0x140012f26  lea     eax, [r8+4]
0x140012f2a  xorps   xmm0, xmm0
0x140012f2d  add     r8d, 8
0x140012f31  punpcklbw xmm1, xmm0
0x140012f35  punpcklwd xmm1, xmm0
0x140012f39  paddd   xmm3, xmm1
0x140012f3d  movd    xmm1, dword ptr [rax+r13]
0x140012f43  punpcklbw xmm1, xmm0
0x140012f47  punpcklwd xmm1, xmm0
0x140012f4b  paddd   xmm2, xmm1
0x140012f4f  cmp     r8d, edx
0x140012f52  jb      short loc_140012F20
0x140012f54  paddd   xmm2, xmm3
0x140012f58  movdqa  xmm0, xmm2
0x140012f5c  psrldq  xmm0, 8
0x140012f61  paddd   xmm2, xmm0
0x140012f65  movdqa  xmm0, xmm2
0x140012f69  psrldq  xmm0, 4
0x140012f6e  paddd   xmm2, xmm0
0x140012f72  movd    eax, xmm2
0x140012f76  cmp     r8d, ebp
0x140012f79  jnb     short loc_140012F8A
0x140012f7b  movzx   edx, byte ptr [r8+r13]
0x140012f80  inc     r8d
0x140012f83  add     eax, edx
0x140012f85  cmp     r8d, ebp
0x140012f88  jb      short loc_140012F7B
0x140012f8a  xor     edx, edx
0x140012f8c  div     dword ptr [rsi]
0x140012f8e  mov     r15d, edx
0x140012f91  shl     r15, 5
0x140012f95  add     r15, [rsi+38h]
0x140012f99  mov     rcx, r15; SpinLock
0x140012f9c  mov     eax, [r15+0Ch]
0x140012fa0  test    al, 1
0x140012fa2  jnz     loc_1400134D2
0x140012fa8  xor     edx, edx
0x140012faa  mov     [rsp+0B8h+var_58], bl
0x140012fae  call    cs:__imp_ExAcquirePushLockSharedEx
0x140012fb5  nop     dword ptr [rax+rax+00h]
0x140012fba  mov     r14, [r15+10h]
0x140012fbe  lea     rax, [r15+10h]
0x140012fc2  cmp     r14, rax
0x140012fc5  jz      loc_1400134E7
0x140012fcb  mov     eax, [rsi+4]
0x140012fce  mov     r8d, ebp
0x140012fd1  neg     eax
0x140012fd3  mov     rdx, r13
0x140012fd6  movsxd  rbx, eax
0x140012fd9  mov     rax, [rsi+20h]
0x140012fdd  add     rbx, r14
0x140012fe0  mov     rcx, rbx
0x140012fe3  call    _guard_dispatch_icall
0x140012fe8  test    al, al
0x140012fea  jz      loc_1400133C0
0x140012ff0  mov     rax, [rsi+18h]
0x140012ff4  test    rax, rax
0x140012ff7  jz      short loc_140013001
0x140012ff9  mov     rcx, rbx
0x140012ffc  call    _guard_dispatch_icall
0x140013001  movzx   edx, [rsp+0B8h+var_58]
0x140013006  mov     rcx, r15
0x140013009  call    RfsHashBucketReleaseLockShared
0x14001300e  test    rbx, rbx
0x140013011  jz      loc_140013592
0x140013017  mov     eax, [rdi+2Ch]
0x14001301a  cmp     eax, [rbx+2Ch]
0x14001301d  jnz     short loc_14001305F
0x14001301f  mov     r8d, eax; Size
0x140013022  lea     rdx, [rbx+30h]; Buf2
0x140013026  lea     rcx, [rdi+30h]; Buf1
0x14001302a  call    memcmp
0x14001302f  test    eax, eax
0x140013031  jnz     short loc_14001305F
0x140013033  mov     r14d, 0FFFFFFFFh
0x140013039  mov     eax, r14d
0x14001303c  lock xadd [rbx+10h], eax
0x140013041  cmp     eax, 1
0x140013044  jnz     short loc_140013057
0x140013046  xor     edx, edx; Tag
0x140013048  mov     rcx, rbx; P
0x14001304b  call    cs:__imp_ExFreePoolWithTag
0x140013052  nop     dword ptr [rax+rax+00h]
0x140013057  xor     r12d, r12d
0x14001305a  jmp     loc_140013352
0x14001305f  movzx   r9d, word ptr [rdi+18h]
0x140013064  lea     r15, [rdi+18h]
0x140013068  mov     rbp, cs:Smb2NetnameTable
0x14001306f  xor     eax, eax
0x140013071  test    r9d, r9d
0x140013074  jz      loc_1400130FD
0x14001307a  mov     r10, [rdi+20h]
0x14001307e  xor     r8d, r8d
0x140013081  cmp     r9d, 8
0x140013085  jb      short loc_1400130EE
0x140013087  mov     edx, r9d
0x14001308a  xorps   xmm3, xmm3
0x14001308d  and     edx, 0FFFFFFF8h
0x140013090  xorps   xmm2, xmm2
0x140013093  movd    xmm1, dword ptr [r8+r10]
0x140013099  lea     eax, [r8+4]
0x14001309d  xorps   xmm0, xmm0
0x1400130a0  add     r8d, 8
0x1400130a4  punpcklbw xmm1, xmm0
0x1400130a8  punpcklwd xmm1, xmm0
0x1400130ac  paddd   xmm3, xmm1
0x1400130b0  movd    xmm1, dword ptr [rax+r10]
0x1400130b6  punpcklbw xmm1, xmm0
0x1400130ba  punpcklwd xmm1, xmm0
0x1400130be  paddd   xmm2, xmm1
0x1400130c2  cmp     r8d, edx
0x1400130c5  jb      short loc_140013093
0x1400130c7  paddd   xmm2, xmm3
0x1400130cb  movdqa  xmm0, xmm2
0x1400130cf  psrldq  xmm0, 8
0x1400130d4  paddd   xmm2, xmm0
0x1400130d8  movdqa  xmm0, xmm2
0x1400130dc  psrldq  xmm0, 4
0x1400130e1  paddd   xmm2, xmm0
0x1400130e5  movd    eax, xmm2
0x1400130e9  cmp     r8d, r9d
0x1400130ec  jnb     short loc_1400130FD
0x1400130ee  movzx   edx, byte ptr [r8+r10]
0x1400130f3  inc     r8d
0x1400130f6  add     eax, edx
0x1400130f8  cmp     r8d, r9d
0x1400130fb  jb      short loc_1400130EE
0x1400130fd  xor     edx, edx
0x1400130ff  div     dword ptr [rbp+0]
0x140013102  mov     esi, edx
0x140013104  shl     rsi, 5
0x140013108  add     rsi, [rbp+38h]
0x14001310c  mov     rcx, rsi; SpinLock
0x14001310f  mov     eax, [rsi+0Ch]
0x140013112  test    al, 1
0x140013114  jz      loc_140013516
0x14001311a  call    cs:__imp_ExAcquireSpinLockExclusive
0x140013121  nop     dword ptr [rax+rax+00h]
0x140013126  movzx   r14d, al
0x14001312a  mov     rax, [rbx]
0x14001312d  cmp     rax, rbx
0x140013130  jz      short loc_14001315E
0x140013132  cmp     [rax+8], rbx
0x140013136  jnz     loc_1400135B4
0x14001313c  mov     rcx, [rbx+8]
0x140013140  cmp     [rcx], rbx
0x140013143  jnz     loc_1400135B4
0x140013149  mov     [rcx], rax
0x14001314c  mov     [rax+8], rcx
0x140013150  mov     [rbx+8], rbx
0x140013154  mov     [rbx], rbx
0x140013157  lock dec dword ptr [rbp+8]
0x14001315b  dec     dword ptr [rsi+8]
0x14001315e  mov     eax, [rsi+0Ch]
0x140013161  mov     rcx, rsi; SpinLock
0x140013164  test    al, 1
0x140013166  jz      loc_140013503
0x14001316c  movzx   edx, r14b; OldIrql
0x140013170  call    cs:__imp_ExReleaseSpinLockExclusive
0x140013177  nop     dword ptr [rax+rax+00h]
0x14001317c  mov     r14d, 0FFFFFFFFh
0x140013182  mov     eax, r14d
0x140013185  lock xadd [rbx+10h], eax
0x14001318a  cmp     eax, 1
0x14001318d  jnz     short loc_1400131A0
0x14001318f  xor     edx, edx; Tag
0x140013191  mov     rcx, rbx; P
0x140013194  call    cs:__imp_ExFreePoolWithTag
0x14001319b  nop     dword ptr [rax+rax+00h]
0x1400131a0  mov     eax, r14d
0x1400131a3  lock xadd [rbx+10h], eax
0x1400131a8  cmp     eax, 1
0x1400131ab  jnz     short loc_1400131BE
0x1400131ad  xor     edx, edx; Tag
0x1400131af  mov     rcx, rbx; P
0x1400131b2  call    cs:__imp_ExFreePoolWithTag
0x1400131b9  nop     dword ptr [rax+rax+00h]
0x1400131be  mov     ebx, 1
0x1400131c3  mov     eax, [rdi+28h]
0x1400131c6  test    al, 1
0x1400131c8  jz      loc_140013334
0x1400131ce  xor     r13d, r13d
0x1400131d1  lea     rcx, Smb2DefaultServerName; String1
0x1400131d8  cmp     ebx, 1
0x1400131db  mov     rdx, r15; String2
0x1400131de  cmovz   r13d, ebx
0x1400131e2  xor     r8d, r8d; CaseInSensitive
0x1400131e5  call    cs:__imp_RtlEqualUnicodeString
0x1400131ec  nop     dword ptr [rax+rax+00h]
0x1400131f1  test    al, al
0x1400131f3  jz      short loc_14001320B
0x1400131f5  cmp     dword ptr [rdi+2Ch], 0
0x1400131f9  jbe     short loc_14001320B
0x1400131fb  mov     rbp, cs:Smb2NetnameTable
0x140013202  test    rbp, rbp
0x140013205  jnz     loc_1400133F6
0x14001320b  mov     rsi, cs:Smb2NetnameTable
0x140013212  test    rsi, rsi
0x140013215  jz      loc_1400134C7
0x14001321b  mov     r10, [rdi+20h]
0x14001321f  test    r10, r10
0x140013222  jz      loc_1400134C7
0x140013228  movzx   r9d, word ptr [r15]
0x14001322c  xor     eax, eax
0x14001322e  test    r9d, r9d
0x140013231  jz      short loc_1400132B2
0x140013233  xor     r8d, r8d
0x140013236  cmp     r9d, 8
0x14001323a  jb      short loc_1400132A3
0x14001323c  mov     edx, r9d
0x14001323f  xorps   xmm3, xmm3
0x140013242  and     edx, 0FFFFFFF8h
0x140013245  xorps   xmm2, xmm2
0x140013248  movd    xmm1, dword ptr [r8+r10]
0x14001324e  lea     eax, [r8+4]
0x140013252  xorps   xmm0, xmm0
0x140013255  add     r8d, 8
0x140013259  punpcklbw xmm1, xmm0
0x14001325d  punpcklwd xmm1, xmm0
0x140013261  paddd   xmm3, xmm1
0x140013265  movd    xmm1, dword ptr [rax+r10]
0x14001326b  punpcklbw xmm1, xmm0
0x14001326f  punpcklwd xmm1, xmm0
0x140013273  paddd   xmm2, xmm1
0x140013277  cmp     r8d, edx
0x14001327a  jb      short loc_140013248
0x14001327c  paddd   xmm2, xmm3
0x140013280  movdqa  xmm0, xmm2
0x140013284  psrldq  xmm0, 8
  ... truncated ...
```
