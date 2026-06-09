# ExtendPartition(IVdsService *,int,unsigned __int64,unsigned __int64)

- ea: `0x18003f2f0`
- end: `0x18003f9f2`
- name: `?ExtendPartition@@YAJPEAUIVdsService@@H_K1@Z`
- size: `1794`
- prototype: `__int64 __fastcall(struct IVdsService *, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026054`

## callees

- `0x18003f2f0`
- `0x1800417a8`
- `0x18004248c`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f96f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f775`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f96f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f982`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ExtendPartition(struct IVdsService *a1, int a2, __int64 a3)
{
  signed int Disk; // ebx
  struct IVdsDisk *v7; // rsi
  __int128 v8; // xmm6
  __int64 v9; // rdi
  int j; // ecx
  int v11; // ebx
  int v12; // r8d
  struct IVdsServiceVtbl *lpVtbl; // rax
  struct IVdsAdvancedDiskVtbl *v14; // rax
  int v15; // edi
  void *v16; // rcx
  unsigned __int64 v17; // rsi
  __int64 v18; // r15
  __int64 v19; // rdx
  __int64 i; // r8
  __int64 v21; // r9
  int v22; // r12d
  char v23; // al
  unsigned __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // r9
  int v27; // eax
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  struct IVdsAdvancedDisk *v31; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v32; // [rsp+40h] [rbp-C0h] BYREF
  struct IVdsDisk *v33; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct IVdsDisk *v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  struct IVdsAdvancedDisk *v37; // [rsp+70h] [rbp-90h] BYREF
  _OWORD Buf2[2]; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A4h] [rbp-5Ch]
  int v41; // [rsp+ACh] [rbp-54h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  __int128 v43; // [rsp+B8h] [rbp-48h]
  __int64 v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+D4h] [rbp-2Ch] BYREF
  int v47; // [rsp+DCh] [rbp-24h]
  LPVOID v48; // [rsp+128h] [rbp+28h]
  LPVOID v49; // [rsp+130h] [rbp+30h]
  LPVOID v50; // [rsp+138h] [rbp+38h]
  LPVOID v51; // [rsp+140h] [rbp+40h]
  LPVOID v52; // [rsp+148h] [rbp+48h]

  v35 = 0;
  v37 = 0;
  if ( a1 && a2 >= 0 && a3 )
  {
    Disk = GetDisk(a1, a2, &v35, &v37, 0);
    if ( Disk < 0 )
      return (unsigned int)Disk;
    v7 = v35;
    if ( !v35 || !v37 )
      return (unsigned int)Disk;
    v45 = 0;
    memset_0(&v46, 0, 0x7Cu);
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v7->lpVtbl->GetProperties)(v7, &v45);
    if ( Disk < 0 )
    {
LABEL_111:
      if ( v37 )
      {
        ((void (__fastcall *)(struct IVdsAdvancedDisk *))v37->lpVtbl->Release)(v37);
        v37 = 0;
      }
      if ( v35 )
        ((void (__fastcall *)(struct IVdsDisk *))v35->lpVtbl->Release)(v35);
      return (unsigned int)Disk;
    }
    v8 = 0;
    v36 = 0;
    Buf2[0] = 0;
    v33 = 0;
    v31 = 0;
    Disk = GetDisk(a1, a2, &v33, &v31, 0);
    if ( Disk < 0 || !v33 || !v31 )
    {
LABEL_33:
      if ( Disk < 0
        || !memcmp_0(&GUID_NULL, Buf2, 0x10u)
        || (lpVtbl = a1->lpVtbl,
            *(_OWORD *)pv = v8,
            Disk = ((__int64 (__fastcall *)(struct IVdsService *, LPVOID *, __int64, __int64 *))lpVtbl->GetObjectA)(
                     a1,
                     pv,
                     11,
                     &v36),
            Disk < 0)
        || !v36 )
      {
LABEL_101:
        if ( v48 )
        {
          CoTaskMemFree(v48);
          v48 = 0;
        }
        if ( v49 )
        {
          CoTaskMemFree(v49);
          v49 = 0;
        }
        if ( v50 )
        {
          CoTaskMemFree(v50);
          v50 = 0;
        }
        if ( v51 )
        {
          CoTaskMemFree(v51);
          v51 = 0;
        }
        if ( v52 )
        {
          CoTaskMemFree(v52);
          v52 = 0;
        }
        goto LABEL_111;
      }
      v31 = 0;
      Disk = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsAdvancedDisk **))v36)(v36, &IID_IVdsVolume, &v31);
      if ( Disk < 0 || !v31 )
      {
LABEL_99:
        if ( v36 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          v36 = 0;
        }
        goto LABEL_101;
      }
      v14 = v31->lpVtbl;
      v29 = 0;
      pv[0] = 0;
      Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, LPVOID *))v14->QueryPartitions)(v31, pv);
      if ( Disk >= 0 )
      {
        if ( pv[0] )
        {
          Disk = IsPackDynamic((struct IVdsPack *)pv[0], &v29);
          if ( pv[0] )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
        }
      }
      if ( Disk >= 0 )
      {
        if ( !v29 )
        {
          v30 = 0;
          v32 = 0;
          Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))v35->lpVtbl->QueryExtents)(
                   v35,
                   &v32,
                   &v30);
          if ( Disk < 0 )
          {
LABEL_92:
            v16 = v32;
            goto LABEL_93;
          }
          v15 = 0;
          v16 = v32;
          if ( v30 <= 0 )
          {
LABEL_76:
            Disk = -2147212274;
            goto LABEL_93;
          }
          while ( *(_OWORD *)((char *)v32 + 80 * v15 + 40) != Buf2[0] )
          {
            if ( ++v15 >= v30 )
              goto LABEL_76;
          }
          v33 = 0;
          if ( !v35 )
          {
            Disk = -2147024809;
LABEL_93:
            if ( v16 )
              CoTaskMemFree(v16);
            goto LABEL_97;
          }
          v17 = 0;
          v18 = 0;
          Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, GUID *, struct IVdsDisk **))v35->lpVtbl->QueryInterface)(
                   v35,
                   &IID_IVdsAdvancedDisk,
                   &v33);
          if ( Disk >= 0 )
          {
            if ( v33 )
            {
              v29 = 0;
              pv[0] = 0;
              v22 = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))v33->lpVtbl->GetPack)(v33, pv, &v29);
              if ( v22 >= 0 )
              {
                v21 = 0;
                for ( i = 0; (int)i < v29; i = (unsigned int)(i + 1) )
                {
                  if ( (_DWORD)v21 )
                    break;
                  v19 = 18LL * (int)i;
                  if ( *((_DWORD *)pv[0] + 36 * (int)i) == 1 )
                  {
                    v23 = *((_BYTE *)pv[0] + 144 * (int)i + 32);
                    if ( v23 == 5 || v23 == 15 )
                    {
                      v17 = *((_QWORD *)pv[0] + 18 * (int)i + 2);
                      v21 = 1;
                      v18 = *((_QWORD *)pv[0] + 18 * (int)i + 3);
                    }
                  }
                }
              }
              if ( pv[0] )
              {
                CoTaskMemFree(pv[0]);
                pv[0] = 0;
              }
              if ( v33 )
                ((void (__fastcall *)(struct IVdsDisk *, __int64, __int64, __int64))v33->lpVtbl->Release)(
                  v33,
                  v19,
                  i,
                  v21);
              Disk = 0;
              if ( v22 != 1 )
                Disk = v22;
            }
            else
            {
              Disk = -2147024883;
            }
          }
          v16 = v32;
          if ( Disk < 0 )
            goto LABEL_93;
          v24 = v18 + v17;
          if ( *((_QWORD *)v32 + 10 * v15 + 3) < v17 || (v25 = 1, *((_QWORD *)v32 + 10 * v15 + 3) >= v24) )
            v25 = 0;
          if ( v15 + 1 >= v30 )
          {
            v26 = 0;
          }
          else
          {
            if ( *((_DWORD *)v32 + 20 * v15 + 24) != 1 && *((_DWORD *)v32 + 20 * v15 + 24) != 0x7FFF )
              goto LABEL_76;
            v26 = *((_QWORD *)v32 + 10 * v15 + 14);
            if ( *((_QWORD *)v32 + 10 * v15 + 13) < v17 || (v27 = 1, *((_QWORD *)v32 + 10 * v15 + 13) >= v24) )
              v27 = 0;
            if ( v25 )
            {
              if ( v27 )
                goto LABEL_87;
            }
            else if ( !v27 )
            {
LABEL_87:
              if ( Disk < 0 )
                goto LABEL_93;
              v39 = v45;
              v43 = 0;
              v41 = v47;
              v42 = v26;
              v40 = v46;
              v44 = 0;
              pv[0] = 0;
              Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, int *, __int64, LPVOID *))v31->lpVtbl->DeletePartition)(
                       v31,
                       &v39,
                       1,
                       pv);
              if ( Disk >= 0 )
              {
                if ( pv[0] )
                {
                  v29 = 0;
                  memset(Buf2, 0, sizeof(Buf2));
                  Disk = (*(__int64 (__fastcall **)(LPVOID, int *, _OWORD *))(*(_QWORD *)pv[0] + 32LL))(
                           pv[0],
                           &v29,
                           Buf2);
                  if ( pv[0] )
                    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
                }
              }
              goto LABEL_92;
            }
          }
          Disk = -2147212274;
          goto LABEL_87;
        }
        Disk = -2147212267;
      }
LABEL_97:
      if ( v31 )
      {
        ((void (__fastcall *)(struct IVdsAdvancedDisk *))v31->lpVtbl->Release)(v31);
        v31 = 0;
      }
      goto LABEL_99;
    }
    v32 = 0;
    pv[0] = 0;
    v29 = 0;
    v30 = 0;
    Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, LPVOID *, int *))v31->lpVtbl->QueryPartitions)(
             v31,
             &v32,
             &v30);
    if ( Disk >= 0 )
    {
      if ( !v32 )
      {
LABEL_29:
        if ( v31 )
        {
          ((void (__fastcall *)(struct IVdsAdvancedDisk *))v31->lpVtbl->Release)(v31);
          v31 = 0;
        }
        if ( v33 )
          ((void (__fastcall *)(struct IVdsDisk *))v33->lpVtbl->Release)(v33);
        goto LABEL_33;
      }
      v9 = 0;
      for ( j = 0; j < v30; ++j )
      {
        if ( *((_QWORD *)v32 + 18 * j + 2) == a3 )
          v9 = *((_QWORD *)v32 + 18 * j + 3);
      }
      Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))v33->lpVtbl->QueryExtents)(v33, pv, &v29);
      if ( Disk >= 0 && pv[0] )
      {
        v11 = 0;
        v12 = 0;
        if ( v29 > 0 )
        {
          do
          {
            if ( v11 )
              break;
            if ( *((_QWORD *)pv[0] + 10 * v12 + 3) == a3 && *((_QWORD *)pv[0] + 10 * v12 + 4) == v9 )
            {
              v8 = *(_OWORD *)((char *)pv[0] + 80 * v12 + 40);
              v11 = 1;
            }
            ++v12;
          }
          while ( v12 < v29 );
          Buf2[0] = v8;
        }
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
        Disk = v11 == 0 ? 0x80004005 : 0;
      }
    }
    if ( v32 )
    {
      CoTaskMemFree(v32);
      v32 = 0;
    }
    goto LABEL_29;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003f2f0  mov     rax, rsp
0x18003f2f3  mov     [rax+18h], rbx
0x18003f2f7  push    rbp
0x18003f2f8  push    rsi
0x18003f2f9  push    rdi
0x18003f2fa  push    r12
0x18003f2fc  push    r13
0x18003f2fe  push    r14
0x18003f300  push    r15
0x18003f302  lea     rbp, [rsp-70h]
0x18003f307  sub     rsp, 170h
0x18003f30e  movaps  xmmword ptr [rax-48h], xmm6
0x18003f312  mov     rax, cs:__security_cookie
0x18003f319  xor     rax, rsp
0x18003f31c  mov     [rbp+0A0h+var_50], rax
0x18003f320  xor     r12d, r12d
0x18003f323  mov     r15, r8
0x18003f326  mov     [rsp+1A0h+var_140], r12
0x18003f32b  mov     edi, edx
0x18003f32d  mov     [rsp+1A0h+var_130], r12
0x18003f332  mov     r14, rcx
0x18003f335  test    rcx, rcx
0x18003f338  jz      loc_18003F9C1
0x18003f33e  test    edx, edx
0x18003f340  js      loc_18003F9C1
0x18003f346  test    r8, r8
0x18003f349  jz      loc_18003F9C1
0x18003f34f  lea     r9, [rsp+1A0h+var_130]; struct IVdsAdvancedDisk **
0x18003f354  mov     [rsp+1A0h+var_180], r12; struct IVdsAdvancedDisk2 **
0x18003f359  lea     r8, [rsp+1A0h+var_140]; struct IVdsDisk **
0x18003f35e  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18003f363  mov     ebx, eax
0x18003f365  test    eax, eax
0x18003f367  js      loc_18003F9BD
0x18003f36d  mov     rsi, [rsp+1A0h+var_140]
0x18003f372  test    rsi, rsi
0x18003f375  jz      loc_18003F9BD
0x18003f37b  cmp     [rsp+1A0h+var_130], r12
0x18003f380  jz      loc_18003F9BD
0x18003f386  xor     edx, edx; Val
0x18003f388  mov     [rbp+0A0h+var_D0], r12d
0x18003f38c  lea     r8d, [r12+7Ch]; Size
0x18003f391  lea     rcx, [rbp+0A0h+var_CC]; void *
0x18003f395  call    memset_0
0x18003f39a  mov     rax, [rsi]
0x18003f39d  lea     rdx, [rbp+0A0h+var_D0]
0x18003f3a1  mov     rcx, rsi
0x18003f3a4  mov     rax, [rax+18h]
0x18003f3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ad  mov     ebx, eax
0x18003f3af  test    eax, eax
0x18003f3b1  js      loc_18003F98C
0x18003f3b7  xorps   xmm6, xmm6
0x18003f3ba  mov     [rsp+1A0h+var_138], r12
0x18003f3bf  lea     r9, [rsp+1A0h+var_168]; struct IVdsAdvancedDisk **
0x18003f3c4  movaps  [rbp+0A0h+Buf2], xmm6
0x18003f3c8  lea     r8, [rsp+1A0h+var_158]; struct IVdsDisk **
0x18003f3cd  mov     [rsp+1A0h+var_158], r12
0x18003f3d2  mov     edx, edi; int
0x18003f3d4  mov     [rsp+1A0h+var_168], r12
0x18003f3d9  mov     rcx, r14; struct IVdsService *
0x18003f3dc  mov     [rsp+1A0h+var_180], r12; struct IVdsAdvancedDisk2 **
0x18003f3e1  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18003f3e6  lea     esi, [r12+1]
0x18003f3eb  mov     ebx, eax
0x18003f3ed  test    eax, eax
0x18003f3ef  js      loc_18003F544
0x18003f3f5  cmp     [rsp+1A0h+var_158], r12
0x18003f3fa  jz      loc_18003F544
0x18003f400  mov     rcx, [rsp+1A0h+var_168]
0x18003f405  test    rcx, rcx
0x18003f408  jz      loc_18003F544
0x18003f40e  mov     [rsp+1A0h+var_160], r12
0x18003f413  lea     r8, [rsp+1A0h+var_16C]
0x18003f418  mov     [rsp+1A0h+pv], r12
0x18003f41d  lea     rdx, [rsp+1A0h+var_160]
0x18003f422  mov     [rsp+1A0h+var_170], r12d
0x18003f427  mov     [rsp+1A0h+var_16C], r12d
0x18003f42c  mov     rax, [rcx]
0x18003f42f  mov     rax, [rax+20h]
0x18003f433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f438  mov     ebx, eax
0x18003f43a  test    eax, eax
0x18003f43c  js      loc_18003F4FE
0x18003f442  mov     r8, [rsp+1A0h+var_160]
0x18003f447  test    r8, r8
0x18003f44a  jz      loc_18003F513
0x18003f450  mov     r9d, [rsp+1A0h+var_16C]
0x18003f455  mov     edi, r12d
0x18003f458  mov     ecx, r12d
0x18003f45b  test    r9d, r9d
0x18003f45e  jle     short loc_18003F47D
0x18003f460  movsxd  rax, ecx
0x18003f463  lea     rdx, [rax+rax*8]
0x18003f467  add     rdx, rdx
0x18003f46a  cmp     [r8+rdx*8+10h], r15
0x18003f46f  jnz     short loc_18003F476
0x18003f471  mov     rdi, [r8+rdx*8+18h]
0x18003f476  add     ecx, esi
0x18003f478  cmp     ecx, r9d
0x18003f47b  jl      short loc_18003F460
0x18003f47d  mov     rcx, [rsp+1A0h+var_158]
0x18003f482  lea     r8, [rsp+1A0h+var_170]
0x18003f487  lea     rdx, [rsp+1A0h+pv]
0x18003f48c  mov     rax, [rcx]
0x18003f48f  mov     rax, [rax+30h]
0x18003f493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f498  mov     ebx, eax
0x18003f49a  test    eax, eax
0x18003f49c  js      short loc_18003F4FE
0x18003f49e  mov     rcx, [rsp+1A0h+pv]; pv
0x18003f4a3  test    rcx, rcx
0x18003f4a6  jz      short loc_18003F4FE
0x18003f4a8  mov     r9d, [rsp+1A0h+var_170]
0x18003f4ad  mov     ebx, r12d
0x18003f4b0  mov     r8d, r12d
0x18003f4b3  test    r9d, r9d
0x18003f4b6  jle     short loc_18003F4E7
0x18003f4b8  test    ebx, ebx
0x18003f4ba  jnz     short loc_18003F4E3
0x18003f4bc  movsxd  rax, r8d
0x18003f4bf  lea     rdx, [rax+rax*4]
0x18003f4c3  add     rdx, rdx
0x18003f4c6  cmp     [rcx+rdx*8+18h], r15
0x18003f4cb  jnz     short loc_18003F4DB
0x18003f4cd  cmp     [rcx+rdx*8+20h], rdi
0x18003f4d2  jnz     short loc_18003F4DB
0x18003f4d4  movups  xmm6, xmmword ptr [rcx+rdx*8+28h]
0x18003f4d9  mov     ebx, esi
0x18003f4db  add     r8d, esi
0x18003f4de  cmp     r8d, r9d
0x18003f4e1  jl      short loc_18003F4B8
0x18003f4e3  movaps  [rbp+0A0h+Buf2], xmm6
0x18003f4e7  call    cs:__imp_CoTaskMemFree
0x18003f4ed  neg     ebx
0x18003f4ef  mov     [rsp+1A0h+pv], r12
0x18003f4f4  sbb     ebx, ebx
0x18003f4f6  not     ebx
0x18003f4f8  and     ebx, 80004005h
0x18003f4fe  mov     rcx, [rsp+1A0h+var_160]; pv
0x18003f503  test    rcx, rcx
0x18003f506  jz      short loc_18003F513
0x18003f508  call    cs:__imp_CoTaskMemFree
0x18003f50e  mov     [rsp+1A0h+var_160], r12
0x18003f513  mov     rcx, [rsp+1A0h+var_168]
0x18003f518  test    rcx, rcx
0x18003f51b  jz      short loc_18003F52E
0x18003f51d  mov     rax, [rcx]
0x18003f520  mov     rax, [rax+10h]
0x18003f524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f529  mov     [rsp+1A0h+var_168], r12
0x18003f52e  mov     rcx, [rsp+1A0h+var_158]
0x18003f533  test    rcx, rcx
0x18003f536  jz      short loc_18003F544
0x18003f538  mov     rax, [rcx]
0x18003f53b  mov     rax, [rax+10h]
0x18003f53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f544  test    ebx, ebx
0x18003f546  js      loc_18003F92D
0x18003f54c  mov     r8d, 10h; Size
0x18003f552  lea     rdx, [rbp+0A0h+Buf2]; Buf2
0x18003f556  lea     rcx, GUID_NULL; Buf1
0x18003f55d  call    memcmp_0
0x18003f562  test    eax, eax
0x18003f564  jz      loc_18003F92D
0x18003f56a  mov     rax, [r14]
0x18003f56d  lea     r9, [rsp+1A0h+var_138]
0x18003f572  mov     r8d, 0Bh
0x18003f578  movdqa  xmmword ptr [rsp+1A0h+pv], xmm6
0x18003f57e  lea     rdx, [rsp+1A0h+pv]
0x18003f583  mov     rcx, r14
0x18003f586  mov     rax, [rax+48h]
0x18003f58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f58f  mov     ebx, eax
0x18003f591  test    eax, eax
0x18003f593  js      loc_18003F92D
0x18003f599  mov     rcx, [rsp+1A0h+var_138]
0x18003f59e  test    rcx, rcx
0x18003f5a1  jz      loc_18003F92D
0x18003f5a7  mov     [rsp+1A0h+var_168], r12
0x18003f5ac  lea     r8, [rsp+1A0h+var_168]
0x18003f5b1  mov     rax, [rcx]
0x18003f5b4  lea     rdx, IID_IVdsVolume
0x18003f5bb  mov     rax, [rax]
0x18003f5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5c3  mov     ebx, eax
0x18003f5c5  test    eax, eax
0x18003f5c7  js      loc_18003F912
0x18003f5cd  mov     rcx, [rsp+1A0h+var_168]
0x18003f5d2  test    rcx, rcx
0x18003f5d5  jz      loc_18003F912
0x18003f5db  mov     rax, [rcx]
0x18003f5de  lea     rdx, [rsp+1A0h+pv]
0x18003f5e3  mov     [rsp+1A0h+var_170], r12d
0x18003f5e8  mov     [rsp+1A0h+pv], r12
0x18003f5ed  mov     rax, [rax+20h]
0x18003f5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5f6  mov     ebx, eax
0x18003f5f8  test    eax, eax
0x18003f5fa  js      short loc_18003F628
0x18003f5fc  mov     rcx, [rsp+1A0h+pv]; struct IVdsPack *
0x18003f601  test    rcx, rcx
0x18003f604  jz      short loc_18003F628
0x18003f606  lea     rdx, [rsp+1A0h+var_170]; int *
0x18003f60b  call    ?IsPackDynamic@@YAJPEAUIVdsPack@@PEAH@Z; IsPackDynamic(IVdsPack *,int *)
0x18003f610  mov     rcx, [rsp+1A0h+pv]
0x18003f615  mov     ebx, eax
0x18003f617  test    rcx, rcx
0x18003f61a  jz      short loc_18003F628
0x18003f61c  mov     rax, [rcx]
0x18003f61f  mov     rax, [rax+10h]
0x18003f623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f628  test    ebx, ebx
0x18003f62a  js      loc_18003F8F7
0x18003f630  cmp     [rsp+1A0h+var_170], r12d
0x18003f635  jnz     loc_18003F8F2
0x18003f63b  mov     rcx, [rsp+1A0h+var_140]
0x18003f640  lea     r8, [rsp+1A0h+var_16C]
0x18003f645  mov     [rsp+1A0h+var_16C], r12d
0x18003f64a  lea     rdx, [rsp+1A0h+var_160]
0x18003f64f  mov     [rsp+1A0h+var_160], r12
0x18003f654  mov     rax, [rcx]
0x18003f657  mov     rax, [rax+30h]
0x18003f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f660  mov     ebx, eax
0x18003f662  test    eax, eax
0x18003f664  js      loc_18003F8D9
0x18003f66a  mov     eax, [rsp+1A0h+var_16C]
0x18003f66e  mov     edi, r12d
0x18003f671  mov     rcx, [rsp+1A0h+var_160]
0x18003f676  test    eax, eax
0x18003f678  jle     loc_18003F7FB
0x18003f67e  mov     rdx, qword ptr [rbp+0A0h+Buf2+8]
0x18003f682  mov     r8, qword ptr [rbp+0A0h+Buf2]
0x18003f686  movsxd  r13, edi
0x18003f689  lea     r14, ds:0[r13*4]
0x18003f691  add     r14, r13
0x18003f694  add     r14, r14
0x18003f697  cmp     [rcx+r14*8+28h], r8
0x18003f69c  jnz     short loc_18003F6A5
0x18003f69e  cmp     [rcx+r14*8+30h], rdx
0x18003f6a3  jz      short loc_18003F6B0
0x18003f6a5  add     edi, esi
0x18003f6a7  cmp     edi, eax
0x18003f6a9  jl      short loc_18003F686
0x18003f6ab  jmp     loc_18003F7FB
0x18003f6b0  mov     r9, [rsp+1A0h+var_140]
0x18003f6b5  mov     [rsp+1A0h+var_158], r12
0x18003f6ba  test    r9, r9
0x18003f6bd  jz      loc_18003F8EB
0x18003f6c3  mov     rax, [r9]
0x18003f6c6  lea     r8, [rsp+1A0h+var_158]
0x18003f6cb  lea     rdx, IID_IVdsAdvancedDisk
0x18003f6d2  mov     rcx, r9
0x18003f6d5  mov     rsi, r12
0x18003f6d8  mov     r15, r12
0x18003f6db  mov     rax, [rax]
0x18003f6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6e3  mov     ebx, eax
0x18003f6e5  test    eax, eax
0x18003f6e7  js      loc_18003F7AE
0x18003f6ed  mov     rcx, [rsp+1A0h+var_158]
0x18003f6f2  test    rcx, rcx
0x18003f6f5  jz      loc_18003F7A9
0x18003f6fb  mov     [rsp+1A0h+var_170], r12d
0x18003f700  lea     r8, [rsp+1A0h+var_170]
0x18003f705  mov     [rsp+1A0h+pv], r12
0x18003f70a  lea     rdx, [rsp+1A0h+pv]
0x18003f70f  mov     rax, [rcx]
0x18003f712  mov     rax, [rax+20h]
0x18003f716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f71b  mov     rcx, [rsp+1A0h+pv]; pv
0x18003f720  mov     r12d, eax
0x18003f723  test    eax, eax
0x18003f725  js      short loc_18003F770
0x18003f727  mov     r10d, [rsp+1A0h+var_170]
0x18003f72c  xor     r9d, r9d
0x18003f72f  xor     r8d, r8d
0x18003f732  test    r10d, r10d
0x18003f735  jle     short loc_18003F770
0x18003f737  test    r9d, r9d
0x18003f73a  jnz     short loc_18003F770
0x18003f73c  movsxd  rax, r8d
0x18003f73f  lea     rdx, [rax+rax*8]
0x18003f743  add     rdx, rdx
0x18003f746  cmp     dword ptr [rcx+rdx*8], 1
0x18003f74a  jnz     short loc_18003F768
0x18003f74c  mov     al, [rcx+rdx*8+20h]
0x18003f750  cmp     al, 5
0x18003f752  jz      short loc_18003F758
0x18003f754  cmp     al, 0Fh
0x18003f756  jnz     short loc_18003F768
0x18003f758  mov     rsi, [rcx+rdx*8+10h]
0x18003f75d  mov     r9d, 1
0x18003f763  mov     r15, [rcx+rdx*8+18h]
0x18003f768  inc     r8d
0x18003f76b  cmp     r8d, r10d
0x18003f76e  jl      short loc_18003F737
0x18003f770  test    rcx, rcx
0x18003f773  jz      short loc_18003F784
  ... truncated ...
```
