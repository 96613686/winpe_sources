# InternalGetSetDriveLetter

- ea: `0x180040140`
- end: `0x180040735`
- name: `InternalGetSetDriveLetter`
- size: `1525`
- prototype: `__int64 __usercall@<rax>(struct IVdsService *@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800244d4`
- `0x180026054`

## callees

- `0x180035c20`
- `0x180039394`
- `0x180040140`
- `0x1800417a8`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `msvcrt!iswalpha` at `0x180040564`
- `msvcrt!iswalpha` at `0x180040564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004032b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040611`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004032b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040611`

## pseudocode

```c
__int64 __fastcall InternalGetSetDriveLetter(
        struct IVdsService *a1,
        __int64 *a2,
        __int64 *a3,
        int a4,
        struct IVdsDiskVtbl *a5,
        unsigned __int16 *a6)
{
  __int128 v7; // xmm6
  struct IVdsService *v9; // rdi
  unsigned __int16 v10; // cx
  int v11; // r14d
  signed int Disk; // ebx
  __int64 v13; // rdi
  int i; // ecx
  int v15; // ebx
  int v16; // r8d
  __int64 v17; // rax
  struct IVdsDisk *v18; // rdx
  int v19; // r8d
  __int64 v20; // rax
  signed int v21; // eax
  struct IVdsService v22; // rax
  void *v23; // rcx
  wint_t *v24; // rdx
  __int64 v25; // rax
  unsigned __int16 *v26; // rdx
  __int64 v28; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID v29; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID v30; // [rsp+48h] [rbp-C0h] BYREF
  struct IVdsDisk *v31; // [rsp+50h] [rbp-B8h] BYREF
  struct IVdsService *v32; // [rsp+58h] [rbp-B0h] BYREF
  struct IVdsAdvancedDisk *Buf2; // [rsp+60h] [rbp-A8h] BYREF
  __int128 Buf2_8; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID pv[2]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v36[32]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v37; // [rsp+C8h] [rbp-40h]

  v32 = a1;
  v7 = 0;
  Buf2_8 = 0;
  v9 = a1;
  if ( a1 && a2 && a3 && a4 >= 0 && a5 && a6 )
  {
    v10 = *a6;
    if ( !*a6 )
    {
      v11 = 1;
      goto LABEL_14;
    }
    if ( (unsigned __int16)(v10 - 97) <= 0x19u || (unsigned __int16)(v10 - 65) <= 0x19u )
    {
      v11 = 0;
      if ( (unsigned __int16)(v10 - 97) <= 0x19u )
        v10 -= 32;
      *a6 = v10;
LABEL_14:
      v31 = 0;
      Buf2 = 0;
      Disk = GetDisk(v9, a4, &v31, &Buf2, 0);
      if ( Disk < 0 )
        return (unsigned int)Disk;
      if ( !v31 || !Buf2 )
      {
LABEL_41:
        if ( !memcmp_0(&GUID_NULL, &Buf2_8, 0x10u) )
        {
          v17 = *a2;
          v31 = 0;
          LODWORD(v28) = 0;
          Disk = (*(__int64 (__fastcall **)(__int64 *, struct IVdsDisk **, __int64 *))(v17 + 48))(a2, &v31, &v28);
          if ( Disk >= 0 )
          {
            v18 = v31;
            if ( v31 )
            {
              v19 = 0;
              if ( (int)v28 <= 0 )
                goto LABEL_53;
              do
              {
                if ( a5 == v31[10 * v19 + 3].lpVtbl )
                  break;
                ++v19;
              }
              while ( v19 < (int)v28 );
              if ( v19 >= (int)v28 || (unsigned int)(LODWORD(v31[10 * v19 + 2].lpVtbl) - 3) > 1 )
              {
LABEL_53:
                Disk = -2147467259;
              }
              else
              {
                v20 = *a3;
                if ( v11 == 1 )
                  v21 = (*(__int64 (__fastcall **)(__int64 *, struct IVdsDiskVtbl *, unsigned __int16 *))(v20 + 80))(
                          a3,
                          a5,
                          a6);
                else
                  v21 = (*(__int64 (__fastcall **)(__int64 *, struct IVdsDiskVtbl *, _QWORD))(v20 + 64))(a3, a5, *a6);
                v18 = v31;
                Disk = v21;
              }
              if ( v18 )
                CoTaskMemFree(v18);
            }
            else
            {
              return (unsigned int)-2147467259;
            }
          }
          return (unsigned int)Disk;
        }
        v22.lpVtbl = v9->lpVtbl;
        Buf2_8 = v7;
        v32 = 0;
        Disk = ((__int64 (__fastcall *)(struct IVdsService *, __int128 *, __int64, struct IVdsService **))v22.lpVtbl->GetObjectA)(
                 v9,
                 &Buf2_8,
                 11,
                 &v32);
        if ( Disk >= 0 )
        {
          if ( v32 )
          {
            v29 = 0;
            Disk = ((__int64 (__fastcall *)(struct IVdsService *, GUID *, LPVOID *))v32->lpVtbl->QueryInterface)(
                     v32,
                     &IID_IVdsVolumeMF,
                     &v29);
            if ( Disk >= 0 )
            {
              if ( v29 )
              {
                v30 = 0;
                LODWORD(v28) = 0;
                Disk = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v30, &v28);
                if ( Disk < 0 )
                  goto LABEL_78;
                if ( (_DWORD)v28 )
                {
                  v23 = v30;
                  if ( !v30 )
                    goto LABEL_75;
                  v24 = *(wint_t **)v30;
                  v25 = -1;
                  do
                    ++v25;
                  while ( v24[v25] );
                  if ( v25 != 3 )
                    goto LABEL_75;
                  if ( iswalpha(*v24) )
                  {
                    v23 = v30;
                    v26 = *(unsigned __int16 **)v30;
                    if ( *(_WORD *)(*(_QWORD *)v30 + 2LL) != 58 || v26[2] != 92 || v26[3] )
                      goto LABEL_75;
                    if ( v11 == 1 )
                    {
                      *a6 = *v26;
LABEL_75:
                      if ( v11 )
                      {
LABEL_79:
                        if ( v23 )
                        {
                          CoTaskMemFree(v23);
                          v30 = 0;
                        }
                        if ( v29 )
                        {
                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
                          v29 = 0;
                        }
                        if ( Disk >= 0 && !v11 )
                        {
                          memset_0(v36, 0, 0x90u);
                          Disk = (*(__int64 (__fastcall **)(__int64 *, struct IVdsDiskVtbl *, unsigned __int16 *))(*a3 + 24))(
                                   a3,
                                   a5,
                                   v36);
                          if ( Disk >= 0 && *(_DWORD *)v36 == 2 && v37 < 0 )
                          {
                            LibLog(
                              &g_VdsLibLog,
                              0x4000000,
                              L"AssignDriveLetter: Drive letter assigned; clearing no-drive-letter attribute.");
                            pv[0] = (LPVOID)2;
                            pv[1] = (LPVOID)(v37 & 0x7FFFFFFFFFFFFFFFLL);
                            Disk = (*(__int64 (__fastcall **)(__int64 *, struct IVdsDiskVtbl *, LPVOID *))(*a3 + 56))(
                                     a3,
                                     a5,
                                     pv);
                          }
                        }
                        goto LABEL_90;
                      }
                      memset_0(v36, 0, 0x208u);
                      Disk = StringCchPrintfW(v36, 0x104u, L"%c:\\", *a6);
                      if ( Disk >= 0 )
                        Disk = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v29 + 40LL))(v29, v36);
LABEL_78:
                      v23 = v30;
                      goto LABEL_79;
                    }
                    Disk = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64))(*(_QWORD *)v29 + 64LL))(
                             v29,
                             v26,
                             1);
                    if ( Disk < 0 )
                      goto LABEL_78;
                  }
                }
                v23 = v30;
                goto LABEL_75;
              }
              Disk = -2147024883;
            }
LABEL_90:
            if ( v32 )
              ((void (__fastcall *)(struct IVdsService *))v32->lpVtbl->Release)(v32);
            return (unsigned int)Disk;
          }
          return (unsigned int)-2147024883;
        }
        return (unsigned int)Disk;
      }
      v29 = 0;
      pv[0] = 0;
      LODWORD(v28) = 0;
      LODWORD(v30) = 0;
      Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, LPVOID *, LPVOID *))Buf2->lpVtbl->QueryPartitions)(
               Buf2,
               &v29,
               &v30);
      if ( Disk >= 0 )
      {
        if ( !v29 )
          goto LABEL_36;
        v13 = 0;
        for ( i = 0; i < (int)v30; ++i )
        {
          if ( *((struct IVdsDiskVtbl **)v29 + 18 * i + 2) == a5 )
            v13 = *((_QWORD *)v29 + 18 * i + 3);
        }
        Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, __int64 *))v31->lpVtbl->QueryExtents)(
                 v31,
                 pv,
                 &v28);
        if ( Disk >= 0 && pv[0] )
        {
          v15 = 0;
          v16 = 0;
          if ( (int)v28 > 0 )
          {
            do
            {
              if ( v15 )
                break;
              if ( *((struct IVdsDiskVtbl **)pv[0] + 10 * v16 + 3) == a5 && *((_QWORD *)pv[0] + 10 * v16 + 4) == v13 )
              {
                v7 = *(_OWORD *)((char *)pv[0] + 80 * v16 + 40);
                v15 = 1;
              }
              ++v16;
            }
            while ( v16 < (int)v28 );
            Buf2_8 = v7;
          }
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
          Disk = v15 == 0 ? 0x80004005 : 0;
        }
        v9 = v32;
      }
      if ( v29 )
      {
        CoTaskMemFree(v29);
        v29 = 0;
      }
LABEL_36:
      if ( Buf2 )
      {
        ((void (__fastcall *)(struct IVdsAdvancedDisk *))Buf2->lpVtbl->Release)(Buf2);
        Buf2 = 0;
      }
      if ( v31 )
        ((void (__fastcall *)(struct IVdsDisk *))v31->lpVtbl->Release)(v31);
      if ( Disk < 0 )
        return (unsigned int)Disk;
      goto LABEL_41;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180040140  mov     rax, rsp
0x180040143  push    rbp
0x180040144  push    rbx
0x180040145  push    rsi
0x180040146  push    rdi
0x180040147  push    r12
0x180040149  push    r13
0x18004014b  push    r14
0x18004014d  push    r15
0x18004014f  lea     rbp, [rax-1F8h]
0x180040156  sub     rsp, 2B8h
0x18004015d  movaps  xmmword ptr [rax-58h], xmm6
0x180040161  mov     rax, cs:__security_cookie
0x180040168  xor     rax, rsp
0x18004016b  mov     [rbp+1F0h+var_60], rax
0x180040172  mov     rsi, [rbp+1F0h+arg_28]
0x180040179  mov     r13, rdx
0x18004017c  xor     edx, edx
0x18004017e  mov     [rsp+2F0h+var_2A0], rcx
0x180040183  xorps   xmm6, xmm6
0x180040186  mov     r10d, r9d
0x180040189  movaps  [rsp+2F0h+Buf2+8], xmm6
0x18004018e  mov     r12, r8
0x180040191  mov     rdi, rcx
0x180040194  test    rcx, rcx
0x180040197  jz      loc_180040705
0x18004019d  test    r13, r13
0x1800401a0  jz      loc_180040705
0x1800401a6  test    r8, r8
0x1800401a9  jz      loc_180040705
0x1800401af  test    r9d, r9d
0x1800401b2  js      loc_180040705
0x1800401b8  mov     r15, [rbp+1F0h+arg_20]
0x1800401bf  test    r15, r15
0x1800401c2  jz      loc_180040705
0x1800401c8  test    rsi, rsi
0x1800401cb  jz      loc_180040705
0x1800401d1  movzx   ecx, word ptr [rsi]
0x1800401d4  cmp     dx, cx
0x1800401d7  jz      short loc_180040204
0x1800401d9  lea     eax, [rcx-61h]
0x1800401dc  cmp     ax, 19h
0x1800401e0  jbe     short loc_1800401EF
0x1800401e2  lea     eax, [rcx-41h]
0x1800401e5  cmp     ax, 19h
0x1800401e9  ja      loc_180040705
0x1800401ef  lea     eax, [rcx-61h]
0x1800401f2  mov     r14d, edx
0x1800401f5  cmp     ax, 19h
0x1800401f9  ja      short loc_1800401FF
0x1800401fb  sub     cx, 20h ; ' '
0x1800401ff  mov     [rsi], cx
0x180040202  jmp     short loc_18004020A
0x180040204  mov     r14d, 1
0x18004020a  mov     [rsp+2F0h+var_2A8], rdx
0x18004020f  lea     r9, [rsp+2F0h+Buf2]; struct IVdsAdvancedDisk **
0x180040214  mov     qword ptr [rsp+2F0h+Buf2], rdx
0x180040219  lea     r8, [rsp+2F0h+var_2A8]; struct IVdsDisk **
0x18004021e  mov     [rsp+20h], rdx; struct IVdsAdvancedDisk2 **
0x180040223  mov     rcx, rdi; struct IVdsService *
0x180040226  mov     edx, r10d; int
0x180040229  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18004022e  mov     ebx, eax
0x180040230  test    eax, eax
0x180040232  js      loc_180040701
0x180040238  xor     ebx, ebx
0x18004023a  cmp     [rsp+2F0h+var_2A8], rbx
0x18004023f  jz      loc_1800403A3
0x180040245  mov     rcx, qword ptr [rsp+2F0h+Buf2]
0x18004024a  test    rcx, rcx
0x18004024d  jz      loc_1800403A3
0x180040253  mov     [rsp+2F0h+var_2B8], rbx
0x180040258  lea     r8, [rsp+2F0h+var_2B0]
0x18004025d  mov     [rsp+2F0h+pv], rbx
0x180040262  lea     rdx, [rsp+2F0h+var_2B8]
0x180040267  mov     dword ptr [rsp+2F0h+var_2C0], ebx
0x18004026b  mov     dword ptr [rsp+2F0h+var_2B0], ebx
0x18004026f  mov     rax, [rcx]
0x180040272  mov     rax, [rax+20h]
0x180040276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004027b  mov     ebx, eax
0x18004027d  test    eax, eax
0x18004027f  js      loc_18004034B
0x180040285  mov     r8, [rsp+2F0h+var_2B8]
0x18004028a  test    r8, r8
0x18004028d  jz      loc_180040364
0x180040293  mov     r9d, dword ptr [rsp+2F0h+var_2B0]
0x180040298  xor     edi, edi
0x18004029a  xor     ecx, ecx
0x18004029c  test    r9d, r9d
0x18004029f  jle     short loc_1800402BE
0x1800402a1  movsxd  rax, ecx
0x1800402a4  lea     rdx, [rax+rax*8]
0x1800402a8  add     rdx, rdx
0x1800402ab  cmp     [r8+rdx*8+10h], r15
0x1800402b0  jnz     short loc_1800402B7
0x1800402b2  mov     rdi, [r8+rdx*8+18h]
0x1800402b7  inc     ecx
0x1800402b9  cmp     ecx, r9d
0x1800402bc  jl      short loc_1800402A1
0x1800402be  mov     rcx, [rsp+2F0h+var_2A8]
0x1800402c3  lea     r8, [rsp+2F0h+var_2C0]
0x1800402c8  lea     rdx, [rsp+2F0h+pv]
0x1800402cd  mov     rax, [rcx]
0x1800402d0  mov     rax, [rax+30h]
0x1800402d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402d9  mov     ebx, eax
0x1800402db  test    eax, eax
0x1800402dd  js      short loc_180040346
0x1800402df  mov     rcx, [rsp+2F0h+pv]; pv
0x1800402e4  test    rcx, rcx
0x1800402e7  jz      short loc_180040346
0x1800402e9  mov     r9d, dword ptr [rsp+2F0h+var_2C0]
0x1800402ee  xor     ebx, ebx
0x1800402f0  xor     r8d, r8d
0x1800402f3  test    r9d, r9d
0x1800402f6  jle     short loc_18004032B
0x1800402f8  test    ebx, ebx
0x1800402fa  jnz     short loc_180040326
0x1800402fc  movsxd  rax, r8d
0x1800402ff  lea     rdx, [rax+rax*4]
0x180040303  add     rdx, rdx
0x180040306  cmp     [rcx+rdx*8+18h], r15
0x18004030b  jnz     short loc_18004031E
0x18004030d  cmp     [rcx+rdx*8+20h], rdi
0x180040312  jnz     short loc_18004031E
0x180040314  movups  xmm6, xmmword ptr [rcx+rdx*8+28h]
0x180040319  mov     ebx, 1
0x18004031e  inc     r8d
0x180040321  cmp     r8d, r9d
0x180040324  jl      short loc_1800402F8
0x180040326  movaps  [rsp+2F0h+Buf2+8], xmm6
0x18004032b  call    cs:__imp_CoTaskMemFree
0x180040331  neg     ebx
0x180040333  mov     [rsp+2F0h+pv], 0
0x18004033c  sbb     ebx, ebx
0x18004033e  not     ebx
0x180040340  and     ebx, 80004005h
0x180040346  mov     rdi, [rsp+2F0h+var_2A0]
0x18004034b  mov     rcx, [rsp+2F0h+var_2B8]; pv
0x180040350  test    rcx, rcx
0x180040353  jz      short loc_180040364
0x180040355  call    cs:__imp_CoTaskMemFree
0x18004035b  mov     [rsp+2F0h+var_2B8], 0
0x180040364  mov     rcx, qword ptr [rsp+2F0h+Buf2]
0x180040369  test    rcx, rcx
0x18004036c  jz      short loc_180040383
0x18004036e  mov     rax, [rcx]
0x180040371  mov     rax, [rax+10h]
0x180040375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004037a  mov     qword ptr [rsp+2F0h+Buf2], 0
0x180040383  mov     rcx, [rsp+2F0h+var_2A8]
0x180040388  test    rcx, rcx
0x18004038b  jz      short loc_180040399
0x18004038d  mov     rax, [rcx]
0x180040390  mov     rax, [rax+10h]
0x180040394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040399  test    ebx, ebx
0x18004039b  js      loc_180040701
0x1800403a1  xor     ebx, ebx
0x1800403a3  mov     r8d, 10h; Size
0x1800403a9  lea     rdx, [rsp+2F0h+Buf2+8]; Buf2
0x1800403ae  lea     rcx, GUID_NULL; Buf1
0x1800403b5  call    memcmp_0
0x1800403ba  test    eax, eax
0x1800403bc  jnz     loc_180040498
0x1800403c2  mov     rax, [r13+0]
0x1800403c6  lea     r8, [rsp+2F0h+var_2C0]
0x1800403cb  lea     rdx, [rsp+2F0h+var_2A8]
0x1800403d0  mov     [rsp+2F0h+var_2A8], rbx
0x1800403d5  mov     rcx, r13
0x1800403d8  mov     dword ptr [rsp+2F0h+var_2C0], ebx
0x1800403dc  mov     rax, [rax+30h]
0x1800403e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403e5  mov     ebx, eax
0x1800403e7  test    eax, eax
0x1800403e9  js      loc_180040701
0x1800403ef  mov     rdx, [rsp+2F0h+var_2A8]
0x1800403f4  test    rdx, rdx
0x1800403f7  jz      loc_18004048E
0x1800403fd  mov     r9d, dword ptr [rsp+2F0h+var_2C0]
0x180040402  xor     r8d, r8d
0x180040405  test    r9d, r9d
0x180040408  jle     short loc_180040472
0x18004040a  movsxd  rax, r8d
0x18004040d  lea     rcx, [rax+rax*4]
0x180040411  add     rcx, rcx
0x180040414  cmp     r15, [rdx+rcx*8+18h]
0x180040419  jz      short loc_180040423
0x18004041b  inc     r8d
0x18004041e  cmp     r8d, r9d
0x180040421  jl      short loc_18004040A
0x180040423  cmp     r8d, r9d
0x180040426  jge     short loc_180040472
0x180040428  movsxd  rax, r8d
0x18004042b  lea     rcx, [rax+rax*4]
0x18004042f  add     rcx, rcx
0x180040432  mov     eax, [rdx+rcx*8+10h]
0x180040436  sub     eax, 3
0x180040439  cmp     eax, 1
0x18004043c  ja      short loc_180040472
0x18004043e  mov     rax, [r12]
0x180040442  mov     rdx, r15
0x180040445  mov     rcx, r12
0x180040448  cmp     r14d, 1
0x18004044c  jnz     short loc_18004045C
0x18004044e  mov     rax, [rax+50h]
0x180040452  mov     r8, rsi
0x180040455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004045a  jmp     short loc_180040469
0x18004045c  movzx   r8d, word ptr [rsi]
0x180040460  mov     rax, [rax+40h]
0x180040464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040469  mov     rdx, [rsp+2F0h+var_2A8]
0x18004046e  mov     ebx, eax
0x180040470  jmp     short loc_180040477
0x180040472  mov     ebx, 80004005h
0x180040477  test    rdx, rdx
0x18004047a  jz      loc_180040701
0x180040480  mov     rcx, rdx; pv
0x180040483  call    cs:__imp_CoTaskMemFree
0x180040489  jmp     loc_180040701
0x18004048e  mov     ebx, 80004005h
0x180040493  jmp     loc_180040701
0x180040498  mov     rax, [rdi]
0x18004049b  lea     r9, [rsp+2F0h+var_2A0]
0x1800404a0  xor     r13d, r13d
0x1800404a3  movdqa  [rsp+2F0h+Buf2+8], xmm6
0x1800404a9  lea     rdx, [rsp+2F0h+Buf2+8]
0x1800404ae  mov     [rsp+2F0h+var_2A0], r13
0x1800404b3  mov     rcx, rdi
0x1800404b6  mov     rax, [rax+48h]
0x1800404ba  lea     r8d, [r13+0Bh]
0x1800404be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404c3  mov     ebx, eax
0x1800404c5  test    eax, eax
0x1800404c7  js      loc_180040701
0x1800404cd  mov     rcx, [rsp+2F0h+var_2A0]
0x1800404d2  test    rcx, rcx
0x1800404d5  jz      loc_1800406FC
0x1800404db  mov     [rsp+2F0h+var_2B8], r13
0x1800404e0  lea     r8, [rsp+2F0h+var_2B8]
0x1800404e5  mov     rax, [rcx]
0x1800404e8  lea     rdx, IID_IVdsVolumeMF
0x1800404ef  mov     rax, [rax]
0x1800404f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800404f7  mov     ebx, eax
0x1800404f9  test    eax, eax
0x1800404fb  js      loc_1800406E4
0x180040501  mov     rcx, [rsp+2F0h+var_2B8]
0x180040506  test    rcx, rcx
0x180040509  jz      loc_1800406DF
0x18004050f  mov     [rsp+2F0h+var_2B0], r13
0x180040514  lea     r8, [rsp+2F0h+var_2C0]
0x180040519  mov     dword ptr [rsp+2F0h+var_2C0], r13d
0x18004051e  lea     rdx, [rsp+2F0h+var_2B0]
0x180040523  mov     rax, [rcx]
0x180040526  mov     rax, [rax+30h]
0x18004052a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004052f  mov     ebx, eax
0x180040531  test    eax, eax
0x180040533  js      loc_180040607
0x180040539  cmp     dword ptr [rsp+2F0h+var_2C0], r13d
0x18004053e  jz      short loc_1800405B6
0x180040540  mov     rcx, [rsp+2F0h+var_2B0]
0x180040545  test    rcx, rcx
0x180040548  jz      short loc_1800405BB
0x18004054a  mov     rdx, [rcx]
0x18004054d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040551  inc     rax
0x180040554  cmp     [rdx+rax*2], r13w
0x180040559  jnz     short loc_180040551
0x18004055b  cmp     rax, 3
0x18004055f  jnz     short loc_1800405BB
0x180040561  movzx   ecx, word ptr [rdx]; C
0x180040564  call    cs:__imp_iswalpha
0x18004056a  test    eax, eax
0x18004056c  jz      short loc_1800405B6
0x18004056e  mov     rcx, [rsp+2F0h+var_2B0]
0x180040573  mov     rdx, [rcx]
0x180040576  cmp     word ptr [rdx+2], 3Ah ; ':'
0x18004057b  jnz     short loc_1800405BB
0x18004057d  cmp     word ptr [rdx+4], 5Ch ; '\'
0x180040582  jnz     short loc_1800405BB
0x180040584  cmp     [rdx+6], r13w
0x180040589  jnz     short loc_1800405BB
0x18004058b  cmp     r14d, 1
0x18004058f  jnz     short loc_180040599
0x180040591  movzx   eax, word ptr [rdx]
0x180040594  mov     [rsi], ax
0x180040597  jmp     short loc_1800405BB
0x180040599  mov     rcx, [rsp+2F0h+var_2B8]
0x18004059e  mov     r8d, 1
0x1800405a4  mov     rax, [rcx]
0x1800405a7  mov     rax, [rax+40h]
0x1800405ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405b0  mov     ebx, eax
0x1800405b2  test    eax, eax
0x1800405b4  js      short loc_180040607
0x1800405b6  mov     rcx, [rsp+2F0h+var_2B0]
  ... truncated ...
```
