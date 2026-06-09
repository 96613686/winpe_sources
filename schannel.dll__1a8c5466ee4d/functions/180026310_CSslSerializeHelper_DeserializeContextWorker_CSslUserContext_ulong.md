# CSslSerializeHelper::DeserializeContextWorker(CSslUserContext *,ulong)

- ea: `0x180026310`
- end: `0x180026d20`
- name: `?DeserializeContextWorker@CSslSerializeHelper@@AEAAJPEAUCSslUserContext@@K@Z`
- size: `2576`
- prototype: `__int64 __fastcall(CSslSerializeHelper *__hidden this, struct CSslUserContext *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180025ef0`

## callees

- `0x180021da8`
- `0x180021e64`
- `0x180026310`
- `0x180039cf0`
- `0x180039d68`
- `0x180041840`
- `0x180047578`
- `0x18004be74`
- `0x180057c8c`
- `0x18006bc44`
- `0x18006d45c`
- `0x18006d4ac`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026abf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026abf`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800268ba`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800268ba`
- `ntdll!RtlReleaseResource` at `0x1800267f9`
- `ntdll!RtlReleaseResource` at `0x1800268f0`
- `ntdll!RtlReleaseResource` at `0x180026ad1`
- `ntdll!RtlReleaseResource` at `0x1800267f9`
- `ntdll!RtlReleaseResource` at `0x1800268f0`
- `ntdll!RtlReleaseResource` at `0x180026ad1`
- `ntdll!RtlAcquireResourceShared` at `0x1800267e1`
- `ntdll!RtlAcquireResourceShared` at `0x1800267e1`
- `ncrypt!SslIncrementProviderReferenceCount` at `0x18002680b`
- `ncrypt!SslIncrementProviderReferenceCount` at `0x18002680b`
- `ncrypt!SslFreeObject` at `0x180026aa6`
- `ncrypt!SslFreeObject` at `0x180026aa6`
- `ncrypt!SslImportKey` at `0x1800264d4`
- `ncrypt!SslImportKey` at `0x18002655a`
- `ncrypt!SslImportKey` at `0x1800264d4`
- `ncrypt!SslImportKey` at `0x18002655a`

## string_xrefs

- `0x180026587`: `write`

## pseudocode

```c
__int64 __fastcall CSslSerializeHelper::DeserializeContextWorker(CSslSerializeHelper *this, struct CSslUserContext *a2)
{
  unsigned int *v2; // rbx
  unsigned int v4; // r10d
  _OWORD *v5; // rdi
  int i; // r8d
  _OWORD *v7; // r9
  _QWORD *v8; // rcx
  __int64 v9; // rax
  __int128 v10; // xmm0
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // esi
  __int64 v17; // rcx
  __int64 v18; // rdx
  const wchar_t *v19; // r9
  unsigned int v21; // eax
  __int64 v22; // r13
  const unsigned __int16 *v23; // r15
  int v24; // r12d
  HLOCAL SslProvHandleInCache; // r14
  int v26; // eax
  CCipherMill *v27; // rcx
  CCipherMill *v28; // rcx
  unsigned int CachedSslProv; // eax
  int v30; // edx
  int v31; // r8d
  CCipherMill *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rdx
  HLOCAL hMem[11]; // [rsp+30h] [rbp-58h] BYREF
  int v38; // [rsp+A0h] [rbp+18h]

  v2 = (unsigned int *)*((_QWORD *)this + 1);
  if ( *v2 != 1 )
    return 2148074244LL;
  v4 = 1;
  v5 = (_OWORD *)((char *)a2 + 504);
  v38 = 1;
  for ( i = 1; ; i = *v2 )
  {
LABEL_3:
    v7 = v2 + 4;
    switch ( i )
    {
      case 13:
        *((_QWORD *)a2 + 52) = v5;
        goto LABEL_18;
      case 14:
        v11 = *((_QWORD *)a2 + 52);
LABEL_12:
        *(_QWORD *)(v11 + 8) = v5;
        memcpy_0(v5, v2 + 4, v2[2]);
LABEL_13:
        v4 = v38;
        goto LABEL_14;
      case 16:
        v11 = *((_QWORD *)a2 + 53);
        goto LABEL_12;
    }
    if ( i != 15 )
      break;
    *((_QWORD *)a2 + 53) = v5;
LABEL_18:
    *v5 = *v7;
LABEL_14:
    v12 = v2[2] + 7LL;
LABEL_15:
    v5 = (_OWORD *)((char *)v5 + (v12 & 0xFFFFFFFFFFFFFFF8uLL));
LABEL_16:
    v2 = (unsigned int *)((char *)v2 + v2[1] + 16);
  }
  switch ( i )
  {
    case 0:
      return 0;
    case 1:
      v4 = v2[5];
      v38 = v4;
      if ( v4 > 1 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids, v4);
        return (unsigned int)-2146893052;
      }
      v21 = v2[1];
      if ( v21 < 0xC2 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids,
            v4,
            v21,
            194);
        return (unsigned int)-2146893052;
      }
      if ( !a2 )
        goto LABEL_16;
      *((_DWORD *)a2 + 2) = *(_DWORD *)v7;
      *((_DWORD *)a2 + 3) = v2[5];
      *((_QWORD *)a2 + 2) = *((_QWORD *)v2 + 3);
      *((_DWORD *)a2 + 6) = v2[8];
      *((_BYTE *)a2 + 32) = *((_BYTE *)v2 + 60);
      *((_DWORD *)a2 + 7) = v2[11];
      *((_QWORD *)a2 + 12) = *((_QWORD *)v2 + 8);
      *((_QWORD *)a2 + 13) = *((_QWORD *)v2 + 9);
      *((_DWORD *)a2 + 14) = v2[9];
      *((_DWORD *)a2 + 15) = v2[10];
      *((_DWORD *)a2 + 16) = v2[12];
      *((_DWORD *)a2 + 18) = v2[13];
      *((_DWORD *)a2 + 17) = v2[42];
      *((_DWORD *)a2 + 29) = v2[48];
      *((_QWORD *)a2 + 15) = *((_QWORD *)v2 + 22);
      *((_QWORD *)a2 + 16) = *((_QWORD *)v2 + 23);
      *((_WORD *)a2 + 68) = *((_WORD *)v2 + 98);
      *((_WORD *)a2 + 69) = *((_WORD *)v2 + 99);
      *((_DWORD *)a2 + 36) = v2[50];
      *((_DWORD *)a2 + 119) = v2[51];
      *((_BYTE *)a2 + 472) = *((_BYTE *)v2 + 208);
      *((_BYTE *)a2 + 480) = *((_BYTE *)v2 + 209);
      *((_DWORD *)a2 + 57) = v2[14];
      *((_DWORD *)a2 + 99) = v2[41];
      *((_DWORD *)a2 + 98) = v2[40];
      *((_QWORD *)a2 + 35) = *((_QWORD *)v2 + 10);
      *((_DWORD *)a2 + 72) = v2[22];
      *((_QWORD *)a2 + 39) = *((_QWORD *)v2 + 12);
      *((_DWORD *)a2 + 84) = v2[26];
      memcpy_0((char *)a2 + 340, v2 + 27, v2[26]);
      v4 = v38;
      v2 = (unsigned int *)((char *)v2 + v2[1] + 16);
      i = *v2;
      goto LABEL_3;
    case 2:
    case 3:
    case 18:
      if ( !a2 || (v13 = *((_QWORD *)a2 + 11)) == 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v35 = 20;
          goto LABEL_122;
        }
        return (unsigned int)-2146893052;
      }
      if ( i == 2 )
      {
        v14 = 40;
      }
      else
      {
        v14 = 448;
        if ( i == 3 )
          v14 = 48;
      }
      v15 = SslImportKey(v13, (char *)a2 + v14, L"OpaqueKeyBlob", v7, v2[2], 0);
      v16 = v15;
      if ( v15 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v16;
        v33 = 21;
        v34 = v15;
LABEL_79:
        WPP_SF_d(*((_QWORD *)v27 + 2), v33, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids, v34);
        return v16;
      }
LABEL_26:
      v4 = v38;
      v2 = (unsigned int *)((char *)v2 + v2[1] + 16);
      i = *v2;
      goto LABEL_3;
    case 4:
      if ( v4 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)-2146893052;
        v36 = 15;
        goto LABEL_121;
      }
      *((_QWORD *)a2 + 19) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 40) = v2[2];
      goto LABEL_13;
    case 5:
      *((_QWORD *)a2 + 25) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 52) = v2[2];
      goto LABEL_13;
    case 6:
      *((_QWORD *)a2 + 27) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 56) = v2[2];
      goto LABEL_13;
    case 7:
      if ( v4 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)-2146893052;
        v36 = 16;
        goto LABEL_121;
      }
      *((_QWORD *)a2 + 21) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 44) = v2[2];
      goto LABEL_13;
    case 8:
      if ( v4 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)-2146893052;
        v36 = 17;
        goto LABEL_121;
      }
      *((_QWORD *)a2 + 23) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 48) = v2[2];
      break;
    case 9:
      *((_QWORD *)a2 + 10) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      v22 = v2[2];
      v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 10);
      v24 = 0;
      *(_OWORD *)hMem = 0;
      RtlAcquireResourceShared(g_pSslProvCacheRWLock, 1u);
      SslProvHandleInCache = (HLOCAL)FindSslProvHandleInCache(v23);
      RtlReleaseResource(g_pSslProvCacheRWLock);
      if ( SslProvHandleInCache )
        goto LABEL_49;
      CachedSslProv = CreateCachedSslProv((struct CACHED_SSL_PROVIDER *)hMem, v23);
      v16 = CachedSslProv;
      if ( !CachedSslProv )
      {
        RtlAcquireResourceExclusive(g_pSslProvCacheRWLock, 1u);
        SslProvHandleInCache = (HLOCAL)FindSslProvHandleInCache(v23);
        if ( !SslProvHandleInCache )
        {
          SslProvHandleInCache = hMem[0];
          v24 = 1;
          CacheClientSideSslProv((struct CACHED_SSL_PROVIDER *)hMem);
          goto LABEL_63;
        }
        if ( hMem[0] )
        {
          SslFreeObject(hMem[0], 0);
          hMem[0] = 0;
        }
        if ( hMem[1] )
        {
          LocalFree(hMem[1]);
          hMem[1] = 0;
          RtlReleaseResource(g_pSslProvCacheRWLock);
        }
        else
        {
LABEL_63:
          RtlReleaseResource(g_pSslProvCacheRWLock);
        }
LABEL_49:
        v16 = SslIncrementProviderReferenceCount(SslProvHandleInCache);
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              &WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids,
              SslProvHandleInCache,
              v16);
          }
          if ( v24 )
            DestroyCachedSslProv((struct CACHED_SSL_PROVIDER *)hMem);
        }
        else
        {
          *((_QWORD *)a2 + 11) = SslProvHandleInCache;
        }
        goto LABEL_51;
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, (unsigned int)hMem, (__int64)v23, CachedSslProv);
LABEL_51:
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (v26 = *((_DWORD *)WPP_GLOBAL_Control + 7), (v26 & 1) != 0) && v16 || (v26 & 4) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_eb5149e4312e3fc6c7b47b99acf2d5dc_Traceguids, v16, v16);
      }
      if ( v16 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v33 = 19;
          v34 = v16;
          goto LABEL_79;
        }
        return v16;
      }
      v4 = v38;
      v12 = v22 + 7;
      goto LABEL_15;
    case 10:
      *((_QWORD *)a2 + 31) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 64) = v2[2];
      goto LABEL_13;
    case 11:
      *((_QWORD *)a2 + 33) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 68) = v2[2];
      goto LABEL_13;
    case 12:
      *((_QWORD *)a2 + 51) = v5;
      v8 = v5;
      v9 = 2;
      do
      {
        v8 += 16;
        v10 = *v7;
        v7 += 8;
        *((_OWORD *)v8 - 8) = v10;
        *((_OWORD *)v8 - 7) = *(v7 - 7);
        *((_OWORD *)v8 - 6) = *(v7 - 6);
        *((_OWORD *)v8 - 5) = *(v7 - 5);
        *((_OWORD *)v8 - 4) = *(v7 - 4);
        *((_OWORD *)v8 - 3) = *(v7 - 3);
        *((_OWORD *)v8 - 2) = *(v7 - 2);
        *((_OWORD *)v8 - 1) = *(v7 - 1);
        --v9;
      }
      while ( v9 );
      *v8 = *(_QWORD *)v7;
      goto LABEL_14;
    case 17:
      *((_QWORD *)a2 + 55) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 108) = v2[2];
      goto LABEL_13;
    case 19:
    case 20:
      if ( !a2 || (v17 = *((_QWORD *)a2 + 11)) == 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v35 = 22;
LABEL_122:
          WPP_SF_(*((_QWORD *)v28 + 2), v35, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids);
        }
        return (unsigned int)-2146893052;
      }
      v18 = 456;
      if ( i != 19 )
        v18 = 464;
      v16 = SslImportKey(v17, (char *)a2 + v18, L"OpaqueKeyBlob", v7, v2[2], 0);
      if ( !v16 )
        goto LABEL_26;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v16;
      v19 = L"read";
      if ( *v2 != 19 )
        v19 = L"write";
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids,
        (_DWORD)v19,
        v16);
      return v16;
    case 21:
      if ( !v4 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)-2146893052;
        v36 = 18;
LABEL_121:
        WPP_SF_dd(*((_QWORD *)v32 + 2), v36, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids, *v2, v4);
        return (unsigned int)-2146893052;
      }
      *((_QWORD *)a2 + 30) = v5;
      memcpy_0(v5, v2 + 4, v2[2]);
      *((_DWORD *)a2 + 58) = v2[2];
      break;
    default:
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids, *v2);
      return 2148074244LL;
  }
  goto LABEL_13;
}

```

## disassembly

```asm
0x180026310  mov     [rsp+arg_10], r8d
0x180026315  push    rbx
0x180026316  push    rbp
0x180026317  push    rsi
0x180026318  push    rdi
0x180026319  push    r12
0x18002631b  push    r13
0x18002631d  push    r14
0x18002631f  push    r15
0x180026321  sub     rsp, 48h
0x180026325  mov     rbx, [rcx+8]
0x180026329  mov     rbp, rdx
0x18002632c  cmp     dword ptr [rbx], 1
0x18002632f  jnz     loc_180026CBE
0x180026335  mov     r10d, 1
0x18002633b  lea     rdi, [rdx+1F8h]
0x180026342  mov     [rsp+88h+arg_10], r10d
0x18002634a  lea     rdx, __ImageBase
0x180026351  mov     r8d, r10d
0x180026354  lea     r14, WPP_GLOBAL_Control
0x18002635b  mov     esi, 1D0h
0x180026360  mov     r11d, 30h ; '0'
0x180026366  nop     word ptr [rax+rax+00000000h]
0x180026370  lea     r9, [rbx+10h]
0x180026374  cmp     r8d, 0Dh
0x180026378  jz      loc_18002648E
0x18002637e  cmp     r8d, 0Eh
0x180026382  jz      loc_180026427
0x180026388  cmp     r8d, 10h
0x18002638c  jz      loc_180026485
0x180026392  cmp     r8d, 0Fh
0x180026396  jz      loc_180026475
0x18002639c  cmp     r8d, 15h; switch 22 cases
0x1800263a0  ja      def_1800263B3; jumptable 00000001800263B3 default case, cases 13-16
0x1800263a6  movsxd  rax, r8d
0x1800263a9  mov     ecx, ds:(jpt_1800263B3 - 180000000h)[rdx+rax*4]
0x1800263b0  add     rcx, rdx
0x1800263b3  jmp     rcx; switch jump
0x1800263b5  mov     [rbp+198h], rdi; jumptable 00000001800263B3 case 12
0x1800263bc  mov     rcx, rdi
0x1800263bf  mov     eax, 2
0x1800263c4  lea     rcx, [rcx+80h]
0x1800263cb  movups  xmm0, xmmword ptr [r9]
0x1800263cf  lea     r9, [r9+80h]
0x1800263d6  movups  xmmword ptr [rcx-80h], xmm0
0x1800263da  movups  xmm1, xmmword ptr [r9-70h]
0x1800263df  movups  xmmword ptr [rcx-70h], xmm1
0x1800263e3  movups  xmm0, xmmword ptr [r9-60h]
0x1800263e8  movups  xmmword ptr [rcx-60h], xmm0
0x1800263ec  movups  xmm1, xmmword ptr [r9-50h]
0x1800263f1  movups  xmmword ptr [rcx-50h], xmm1
0x1800263f5  movups  xmm0, xmmword ptr [r9-40h]
0x1800263fa  movups  xmmword ptr [rcx-40h], xmm0
0x1800263fe  movups  xmm1, xmmword ptr [r9-30h]
0x180026403  movups  xmmword ptr [rcx-30h], xmm1
0x180026407  movups  xmm0, xmmword ptr [r9-20h]
0x18002640c  movups  xmmword ptr [rcx-20h], xmm0
0x180026410  movups  xmm1, xmmword ptr [r9-10h]
0x180026415  movups  xmmword ptr [rcx-10h], xmm1
0x180026419  sub     rax, 1
0x18002641d  jnz     short loc_1800263C4
0x18002641f  mov     rax, [r9]
0x180026422  mov     [rcx], rax
0x180026425  jmp     short loc_180026456
0x180026427  mov     rax, [rbp+1A0h]
0x18002642e  mov     [rax+8], rdi
0x180026432  mov     rdx, r9; Src
0x180026435  mov     r8d, [rbx+8]; Size
0x180026439  mov     rcx, rdi; void *
0x18002643c  call    memcpy_0
0x180026441  mov     r10d, [rsp+88h+arg_10]
0x180026449  lea     rdx, __ImageBase
0x180026450  mov     r11d, 30h ; '0'
0x180026456  mov     eax, [rbx+8]
0x180026459  add     rax, 7
0x18002645d  and     rax, 0FFFFFFFFFFFFFFF8h
0x180026461  add     rdi, rax
0x180026464  mov     eax, [rbx+4]
0x180026467  add     eax, 10h
0x18002646a  add     rbx, rax
0x18002646d  mov     r8d, [rbx]
0x180026470  jmp     loc_180026370
0x180026475  mov     [rbp+1A8h], rdi
0x18002647c  movups  xmm0, xmmword ptr [r9]
0x180026480  movups  xmmword ptr [rdi], xmm0
0x180026483  jmp     short loc_180026456
0x180026485  mov     rax, [rbp+1A8h]
0x18002648c  jmp     short loc_18002642E
0x18002648e  mov     [rbp+1A0h], rdi
0x180026495  jmp     short loc_18002647C
0x180026497  test    rbp, rbp; jumptable 00000001800263B3 cases 2,3,18
0x18002649a  jz      loc_180026883
0x1800264a0  mov     rcx, [rbp+58h]
0x1800264a4  test    rcx, rcx
0x1800264a7  jz      loc_180026883
0x1800264ad  mov     r10d, [rbx+8]
0x1800264b1  cmp     r8d, 2
0x1800264b5  jnz     short loc_18002650F
0x1800264b7  mov     eax, 28h ; '('
0x1800264bc  lea     rdx, [rax+rbp]
0x1800264c0  mov     [rsp+88h+var_60], 0
0x1800264c8  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x1800264cf  mov     dword ptr [rsp+88h+var_68], r10d
0x1800264d4  call    cs:__imp_SslImportKey
0x1800264da  mov     esi, eax
0x1800264dc  test    eax, eax
0x1800264de  jnz     loc_180026C35
0x1800264e4  mov     eax, [rbx+4]
0x1800264e7  lea     rdx, __ImageBase
0x1800264ee  mov     r10d, [rsp+88h+arg_10]
0x1800264f6  add     eax, 10h
0x1800264f9  add     rbx, rax
0x1800264fc  mov     esi, 1D0h
0x180026501  mov     r11d, 30h ; '0'
0x180026507  mov     r8d, [rbx]
0x18002650a  jmp     loc_180026370
0x18002650f  cmp     r8d, 3
0x180026513  mov     eax, 1C0h
0x180026518  cmovz   rax, r11
0x18002651c  jmp     short loc_1800264BC
0x18002651e  test    rbp, rbp; jumptable 00000001800263B3 cases 19,20
0x180026521  jz      loc_180026C70
0x180026527  mov     rcx, [rbp+58h]
0x18002652b  test    rcx, rcx
0x18002652e  jz      loc_180026C70
0x180026534  mov     eax, [rbx+8]
0x180026537  cmp     r8d, 13h
0x18002653b  mov     edx, 1C8h
0x180026540  mov     [rsp+88h+var_60], 0
0x180026548  cmovnz  rdx, rsi
0x18002654c  mov     dword ptr [rsp+88h+var_68], eax
0x180026550  add     rdx, rbp
0x180026553  lea     r8, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002655a  call    cs:__imp_SslImportKey
0x180026560  mov     esi, eax
0x180026562  test    eax, eax
0x180026564  jz      loc_1800264E4
0x18002656a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026571  cmp     rcx, r14
0x180026574  jz      loc_18002687C
0x18002657a  test    byte ptr [rcx+1Ch], 1
0x18002657e  jz      loc_18002687C
0x180026584  cmp     dword ptr [rbx], 13h
0x180026587  lea     rax, aWrite; "write"
0x18002658e  mov     rcx, [rcx+10h]
0x180026592  lea     r9, aRead; "read"
0x180026599  cmovnz  r9, rax
0x18002659d  mov     dword ptr [rsp+88h+var_68], esi
0x1800265a1  mov     edx, 17h
0x1800265a6  lea     r8, WPP_e0e761b9a60e3e5ad14d955cd0e7eee5_Traceguids
0x1800265ad  call    WPP_SF_Sd
0x1800265b2  mov     eax, esi
0x1800265b4  jmp     loc_1800267A1
0x1800265b9  mov     r10d, [r9+4]; jumptable 00000001800263B3 case 1
0x1800265bd  mov     eax, r10d
0x1800265c0  mov     [rsp+88h+arg_10], r10d
0x1800265c8  test    r10d, r10d
0x1800265cb  jz      short loc_1800265D6
0x1800265cd  cmp     eax, 1
0x1800265d0  jnz     loc_180026B4F
0x1800265d6  mov     eax, [rbx+4]
0x1800265d9  cmp     eax, 0C2h
0x1800265de  jb      loc_180026B86
0x1800265e4  test    rbp, rbp
0x1800265e7  jz      loc_180026464
0x1800265ed  mov     eax, [r9]
0x1800265f0  lea     rdx, [r9+5Ch]; Src
0x1800265f4  mov     [rbp+8], eax
0x1800265f7  lea     rcx, [rbp+154h]; void *
0x1800265fe  mov     eax, [r9+4]
0x180026602  mov     [rbp+0Ch], eax
0x180026605  mov     rax, [r9+8]
0x180026609  mov     [rbp+10h], rax
0x18002660d  mov     eax, [r9+10h]
0x180026611  mov     [rbp+18h], eax
0x180026614  movzx   eax, byte ptr [r9+2Ch]
0x180026619  mov     [rbp+20h], al
0x18002661c  mov     eax, [r9+1Ch]
0x180026620  mov     [rbp+1Ch], eax
0x180026623  mov     rax, [r9+30h]
0x180026627  mov     [rbp+60h], rax
0x18002662b  mov     rax, [r9+38h]
0x18002662f  mov     [rbp+68h], rax
0x180026633  mov     eax, [r9+14h]
0x180026637  mov     [rbp+38h], eax
0x18002663a  mov     eax, [r9+18h]
0x18002663e  mov     [rbp+3Ch], eax
0x180026641  mov     eax, [r9+20h]
0x180026645  mov     [rbp+40h], eax
0x180026648  mov     eax, [r9+24h]
0x18002664c  mov     [rbp+48h], eax
0x18002664f  mov     eax, [r9+98h]
0x180026656  mov     [rbp+44h], eax
0x180026659  mov     eax, [r9+0B0h]
0x180026660  mov     [rbp+74h], eax
0x180026663  mov     rax, [r9+0A0h]
0x18002666a  mov     [rbp+78h], rax
0x18002666e  mov     rax, [r9+0A8h]
0x180026675  mov     [rbp+80h], rax
0x18002667c  movzx   eax, word ptr [r9+0B4h]
0x180026684  mov     [rbp+88h], ax
0x18002668b  movzx   eax, word ptr [r9+0B6h]
0x180026693  mov     [rbp+8Ah], ax
0x18002669a  mov     eax, [r9+0B8h]
0x1800266a1  mov     [rbp+90h], eax
0x1800266a7  mov     eax, [r9+0BCh]
0x1800266ae  mov     [rbp+1DCh], eax
0x1800266b4  movzx   eax, byte ptr [r9+0C0h]
0x1800266bc  mov     [rbp+1D8h], al
0x1800266c2  movzx   eax, byte ptr [r9+0C1h]
0x1800266ca  mov     [rbp+1E0h], al
0x1800266d0  mov     eax, [r9+28h]
0x1800266d4  mov     [rbp+0E4h], eax
0x1800266da  mov     eax, [r9+94h]
0x1800266e1  mov     [rbp+18Ch], eax
0x1800266e7  mov     eax, [r9+90h]
0x1800266ee  mov     [rbp+188h], eax
0x1800266f4  mov     rax, [r9+40h]
0x1800266f8  mov     [rbp+118h], rax
0x1800266ff  mov     eax, [r9+48h]
0x180026703  mov     [rbp+120h], eax
0x180026709  mov     rax, [r9+50h]
0x18002670d  mov     [rbp+138h], rax
0x180026714  mov     eax, [r9+58h]
0x180026718  mov     [rbp+150h], eax
0x18002671e  mov     r8d, [r9+58h]; Size
0x180026722  call    memcpy_0
0x180026727  mov     eax, [rbx+4]
0x18002672a  lea     rdx, __ImageBase
0x180026731  mov     r10d, [rsp+88h+arg_10]
0x180026739  add     eax, 10h
0x18002673c  add     rbx, rax
0x18002673f  mov     r11d, 30h ; '0'
0x180026745  mov     r8d, [rbx]
0x180026748  jmp     loc_180026370
0x18002674d  cmp     r10d, 1; jumptable 00000001800263B3 case 21
0x180026751  jb      loc_180026943
0x180026757  mov     [rbp+0F0h], rdi
0x18002675e  mov     rdx, r9; Src
0x180026761  mov     r8d, [rbx+8]; Size
0x180026765  mov     rcx, rdi; void *
0x180026768  call    memcpy_0
0x18002676d  mov     eax, [rbx+8]
0x180026770  mov     [rbp+0E8h], eax
0x180026776  jmp     loc_180026441
0x18002677b  mov     [rbp+108h], rdi; jumptable 00000001800263B3 case 11
0x180026782  mov     rdx, r9; Src
0x180026785  mov     r8d, [rbx+8]; Size
0x180026789  mov     rcx, rdi; void *
0x18002678c  call    memcpy_0
0x180026791  mov     eax, [rbx+8]
0x180026794  mov     [rbp+110h], eax
0x18002679a  jmp     loc_180026441
0x18002679f  xor     eax, eax; jumptable 00000001800263B3 case 0
0x1800267a1  add     rsp, 48h
0x1800267a5  pop     r15
0x1800267a7  pop     r14
0x1800267a9  pop     r13
0x1800267ab  pop     r12
0x1800267ad  pop     rdi
0x1800267ae  pop     rsi
0x1800267af  pop     rbp
0x1800267b0  pop     rbx
0x1800267b1  retn
0x1800267b2  mov     [rbp+50h], rdi; jumptable 00000001800263B3 case 9
0x1800267b6  mov     rdx, r9; Src
0x1800267b9  mov     r8d, [rbx+8]; Size
0x1800267bd  mov     rcx, rdi; void *
0x1800267c0  call    memcpy_0
0x1800267c5  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_RTL_RESOURCE@@EA; Resource
0x1800267cc  xorps   xmm0, xmm0
0x1800267cf  mov     r13d, [rbx+8]
0x1800267d3  mov     dl, 1; Wait
0x1800267d5  mov     r15, [rbp+50h]
0x1800267d9  xor     r12d, r12d
0x1800267dc  movups  xmmword ptr [rsp+88h+hMem], xmm0
0x1800267e1  call    cs:__imp_RtlAcquireResourceShared
0x1800267e7  mov     rcx, r15; unsigned __int16 *
0x1800267ea  call    ?FindSslProvHandleInCache@@YA_KPEBG@Z; FindSslProvHandleInCache(ushort const *)
0x1800267ef  mov     rcx, cs:?g_pSslProvCacheRWLock@@3PEAU_RTL_RESOURCE@@EA; Resource
0x1800267f6  mov     r14, rax
0x1800267f9  call    cs:__imp_RtlReleaseResource
0x1800267ff  test    r14, r14
0x180026802  jz      loc_18002689A
0x180026808  mov     rcx, r14
0x18002680b  call    cs:__imp_SslIncrementProviderReferenceCount
0x180026811  mov     esi, eax
0x180026813  test    eax, eax
0x180026815  jnz     loc_180026ADC
0x18002681b  mov     [rbp+58h], r14
0x18002681f  lea     r14, WPP_GLOBAL_Control
0x180026826  mov     rcx, cs:WPP_GLOBAL_Control
0x18002682d  cmp     rcx, r14
0x180026830  jz      short loc_180026845
0x180026832  mov     eax, [rcx+1Ch]
0x180026835  test    al, 1
0x180026837  jnz     loc_180026B1F
0x18002683d  test    al, 4
0x18002683f  jnz     loc_180026B27
0x180026845  test    esi, esi
  ... truncated ...
```
