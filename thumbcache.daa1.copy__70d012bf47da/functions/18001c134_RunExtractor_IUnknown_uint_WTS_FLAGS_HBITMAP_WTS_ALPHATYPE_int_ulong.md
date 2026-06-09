# RunExtractor(IUnknown *,uint,WTS_FLAGS,HBITMAP__ * *,WTS_ALPHATYPE *,int *,ulong *)

- ea: `0x18001c134`
- end: `0x18001c41e`
- name: `?RunExtractor@@YAJPEAUIUnknown@@IW4WTS_FLAGS@@PEAPEAUHBITMAP__@@PEAW4WTS_ALPHATYPE@@PEAHPEAK@Z`
- size: `746`
- prototype: `__int64 __fastcall(IUnknown *punk, unsigned int, unsigned int, HBITMAP *, enum WTS_ALPHATYPE *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x18001c134`
- `0x18001c424`
- `0x18001c460`
- `0x18001c6f0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c1de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c249`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c1de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c249`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18001c2ab`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18001c2ab`
- `GDI32!DeleteObject` at `0x18001c3bd`
- `GDI32!DeleteObject` at `0x18001c403`
- `GDI32!DeleteObject` at `0x18001c3bd`
- `GDI32!DeleteObject` at `0x18001c403`

## pseudocode

```c
__int64 __fastcall RunExtractor(
        IUnknown *punk,
        unsigned int a2,
        unsigned int a3,
        HBITMAP *a4,
        enum WTS_ALPHATYPE *a5,
        int *a6,
        unsigned int *a7)
{
  int v10; // ebx
  DWORD v11; // r12d
  DWORD TickCount; // r12d
  bool v13; // cl
  __int64 v14; // rdx
  __int64 v15; // r8
  HBITMAP v17; // rbx
  _OWORD v19[2]; // [rsp+38h] [rbp-49h]
  int v20; // [rsp+58h] [rbp-29h]
  int v21; // [rsp+5Ch] [rbp-25h]
  HGDIOBJ ho; // [rsp+60h] [rbp-21h] BYREF
  __int64 v23; // [rsp+68h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp-11h] BYREF
  __int64 v25; // [rsp+78h] [rbp-9h] BYREF

  *a4 = 0;
  *a5 = WTSAT_UNKNOWN;
  if ( a7 )
    *a7 = 0;
  v10 = 0;
  v25 = 0;
  if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk->lpVtbl->QueryInterface)(
         punk,
         &GUID_f4376f00_bef5_4d45_80f3_1e023bbf1209,
         &v25) >= 0 )
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 24LL))(
            v25,
            ((a3 & 0x80004000) != 0 ? 4 : 0)
          | a3 & 0x40000000
          | (4 * (a3 & 2))
          | ((a3 & 0x200 | (a3 >> 5) & 0x100) >> 8));
  ho = 0;
  if ( v10 >= 0 )
  {
    v24 = 0;
    if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk->lpVtbl->QueryInterface)(
           punk,
           &GUID_e357fccd_a995_4576_b01f_234630154e96,
           &v24) < 0 )
    {
      v23 = 0;
      v10 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk->lpVtbl->QueryInterface)(
              punk,
              &GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1,
              &v23);
      if ( v10 >= 0 )
      {
        TickCount = GetTickCount();
        v10 = (*(__int64 (__fastcall **)(__int64, HGDIOBJ *))(*(_QWORD *)v23 + 32LL))(v23, &ho);
        if ( a7 )
          *a7 = ComputeElapsedTime(TickCount);
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    else
    {
      v11 = GetTickCount();
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, HGDIOBJ *, enum WTS_ALPHATYPE *))(*(_QWORD *)v24 + 24LL))(
              v24,
              a2,
              &ho,
              a5);
      if ( v10 == 307712 )
      {
        *a6 = 0;
        v10 = 0;
      }
      if ( a7 )
        *a7 = ComputeElapsedTime(v11);
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  IUnknown_SetSite(punk, 0);
  if ( v10 >= 0 )
  {
    v17 = ConvertDDB2DIB((HBITMAP)ho, a5);
    v15 = (__int64)ho;
    if ( v17 != ho )
    {
      DeleteObject(ho);
      v15 = (__int64)v17;
      ho = v17;
    }
    if ( v15 )
    {
      v10 = AdjustImage(a2, v14, v15, a4);
      v15 = 1;
      if ( v10 == 1 )
      {
        *a4 = (HBITMAP)ho;
        v10 = 0;
      }
      else
      {
        DeleteObject(ho);
      }
    }
    else
    {
      v10 = -2147467259;
    }
  }
  else
  {
    v19[0] = _mm_load_si128((const __m128i *)&_xmm);
    v19[1] = _mm_load_si128((const __m128i *)&_xmm);
    v20 = -2147175931;
    v21 = -2147175929;
    v13 = 0;
    v14 = 0;
    v15 = 1;
    while ( !v13 )
    {
      v13 = v10 == *((_DWORD *)v19 + (int)v14);
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= 0xA )
      {
        if ( !v13 )
          v10 = -2147175936;
        break;
      }
    }
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v25 + 16LL))(v25, v14, v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c134  mov     [rsp-8+arg_10], rbx
0x18001c139  push    rbp
0x18001c13a  push    rsi
0x18001c13b  push    rdi
0x18001c13c  push    r12
0x18001c13e  push    r13
0x18001c140  push    r14
0x18001c142  push    r15
0x18001c144  lea     rbp, [rsp-0Fh]
0x18001c149  sub     rsp, 90h
0x18001c150  mov     rax, cs:__security_cookie
0x18001c157  xor     rax, rsp
0x18001c15a  mov     [rbp+3Fh+var_40], rax
0x18001c15e  mov     r14, r9
0x18001c161  mov     r12d, r8d
0x18001c164  mov     [rbp+3Fh+var_90], edx
0x18001c167  mov     rsi, rcx
0x18001c16a  mov     r15, [rbp+3Fh+arg_20]
0x18001c16e  mov     r13, [rbp+3Fh+arg_28]
0x18001c172  mov     rdi, [rbp+3Fh+arg_30]
0x18001c176  xor     eax, eax
0x18001c178  mov     [r9], rax
0x18001c17b  mov     [r15], eax
0x18001c17e  test    rdi, rdi
0x18001c181  jz      short loc_18001C185
0x18001c183  mov     [rdi], eax
0x18001c185  mov     ebx, eax
0x18001c187  mov     [rbp+3Fh+var_48], rax
0x18001c18b  mov     rax, [rcx]
0x18001c18e  lea     r8, [rbp+3Fh+var_48]
0x18001c192  lea     rdx, _GUID_f4376f00_bef5_4d45_80f3_1e023bbf1209
0x18001c199  mov     rax, [rax]
0x18001c19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1a1  test    eax, eax
0x18001c1a3  jns     loc_18001C34C
0x18001c1a9  mov     [rbp+3Fh+ho], 0
0x18001c1b1  test    ebx, ebx
0x18001c1b3  js      loc_18001C2A6
0x18001c1b9  mov     [rbp+3Fh+var_50], 0
0x18001c1c1  mov     rax, [rsi]
0x18001c1c4  lea     r8, [rbp+3Fh+var_50]
0x18001c1c8  lea     rdx, _GUID_e357fccd_a995_4576_b01f_234630154e96
0x18001c1cf  mov     rcx, rsi
0x18001c1d2  mov     rax, [rax]
0x18001c1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1da  test    eax, eax
0x18001c1dc  js      short loc_18001C222
0x18001c1de  call    cs:__imp_GetTickCount
0x18001c1e4  mov     r12d, eax
0x18001c1e7  mov     r10, [rbp+3Fh+var_50]
0x18001c1eb  mov     rcx, [r10]
0x18001c1ee  mov     rax, [rcx+18h]
0x18001c1f2  mov     r9, r15
0x18001c1f5  lea     r8, [rbp+3Fh+ho]
0x18001c1f9  mov     edx, [rbp+3Fh+var_90]
0x18001c1fc  mov     rcx, r10
0x18001c1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c204  mov     ebx, eax
0x18001c206  cmp     eax, 4B200h
0x18001c20b  jz      loc_18001C40E
0x18001c211  test    rdi, rdi
0x18001c214  jz      short loc_18001C290
0x18001c216  mov     ecx, r12d; unsigned int
0x18001c219  call    ?ComputeElapsedTime@@YAKK@Z; ComputeElapsedTime(ulong)
0x18001c21e  mov     [rdi], eax
0x18001c220  jmp     short loc_18001C290
0x18001c222  mov     [rbp+3Fh+var_58], 0
0x18001c22a  mov     rax, [rsi]
0x18001c22d  lea     r8, [rbp+3Fh+var_58]
0x18001c231  lea     rdx, _GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1
0x18001c238  mov     rcx, rsi
0x18001c23b  mov     rax, [rax]
0x18001c23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c243  mov     ebx, eax
0x18001c245  test    eax, eax
0x18001c247  js      short loc_18001C27A
0x18001c249  call    cs:__imp_GetTickCount
0x18001c24f  mov     r12d, eax
0x18001c252  mov     r8, [rbp+3Fh+var_58]
0x18001c256  mov     rcx, [r8]
0x18001c259  mov     rax, [rcx+20h]
0x18001c25d  lea     rdx, [rbp+3Fh+ho]
0x18001c261  mov     rcx, r8
0x18001c264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c269  mov     ebx, eax
0x18001c26b  test    rdi, rdi
0x18001c26e  jz      short loc_18001C27A
0x18001c270  mov     ecx, r12d; unsigned int
0x18001c273  call    ?ComputeElapsedTime@@YAKK@Z; ComputeElapsedTime(ulong)
0x18001c278  mov     [rdi], eax
0x18001c27a  mov     rcx, [rbp+3Fh+var_58]
0x18001c27e  test    rcx, rcx
0x18001c281  jz      short loc_18001C290
0x18001c283  mov     rax, [rcx]
0x18001c286  mov     rax, [rax+10h]
0x18001c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c28f  nop
0x18001c290  mov     rcx, [rbp+3Fh+var_50]
0x18001c294  test    rcx, rcx
0x18001c297  jz      short loc_18001C2A6
0x18001c299  mov     rax, [rcx]
0x18001c29c  mov     rax, [rax+10h]
0x18001c2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2a5  nop
0x18001c2a6  xor     edx, edx; punkSite
0x18001c2a8  mov     rcx, rsi; punk
0x18001c2ab  call    cs:__imp_IUnknown_SetSite
0x18001c2b1  test    ebx, ebx
0x18001c2b3  jns     loc_18001C3A2
0x18001c2b9  movdqa  xmm0, cs:__xmm@800700208000000a800700058007000e
0x18001c2c1  movdqu  [rbp+3Fh+var_88], xmm0
0x18001c2c6  movdqa  xmm1, cs:__xmm@8004b2048004b2038004b2028004b201
0x18001c2ce  movdqu  [rbp+3Fh+var_78], xmm1
0x18001c2d3  mov     [rbp+3Fh+var_68], 8004B205h
0x18001c2da  mov     [rbp+3Fh+var_64], 8004B207h
0x18001c2e1  xor     cl, cl
0x18001c2e3  xor     edx, edx
0x18001c2e5  lea     r8d, [rdx+1]
0x18001c2e9  test    cl, cl
0x18001c2eb  jnz     short loc_18001C30D
0x18001c2ed  movsxd  rax, edx
0x18001c2f0  movzx   ecx, cl
0x18001c2f3  cmp     ebx, dword ptr [rbp+rax*4+3Fh+var_88]
0x18001c2f7  cmovz   ecx, r8d
0x18001c2fb  add     edx, r8d
0x18001c2fe  cmp     edx, 0Ah
0x18001c301  jb      short loc_18001C2E9
0x18001c303  mov     eax, 8004B200h
0x18001c308  test    cl, cl
0x18001c30a  cmovz   ebx, eax
0x18001c30d  mov     rcx, [rbp+3Fh+var_48]
0x18001c311  test    rcx, rcx
0x18001c314  jz      short loc_18001C323
0x18001c316  mov     rax, [rcx]
0x18001c319  mov     rax, [rax+10h]
0x18001c31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c322  nop
0x18001c323  mov     eax, ebx
0x18001c325  mov     rcx, [rbp+3Fh+var_40]
0x18001c329  xor     rcx, rsp; StackCookie
0x18001c32c  call    __security_check_cookie
0x18001c331  mov     rbx, [rsp+0C0h+arg_10]
0x18001c339  add     rsp, 90h
0x18001c340  pop     r15
0x18001c342  pop     r14
0x18001c344  pop     r13
0x18001c346  pop     r12
0x18001c348  pop     rdi
0x18001c349  pop     rsi
0x18001c34a  pop     rbp
0x18001c34b  retn
0x18001c34c  mov     rcx, [rbp+3Fh+var_48]
0x18001c350  mov     r8, [rcx]
0x18001c353  mov     edx, r12d
0x18001c356  shr     edx, 5
0x18001c359  and     edx, 100h
0x18001c35f  mov     eax, r12d
0x18001c362  and     eax, 200h
0x18001c367  or      edx, eax
0x18001c369  shr     edx, 8
0x18001c36c  mov     eax, r12d
0x18001c36f  and     eax, 2
0x18001c372  shl     eax, 2
0x18001c375  or      edx, eax
0x18001c377  mov     eax, r12d
0x18001c37a  and     eax, 40000000h
0x18001c37f  or      edx, eax
0x18001c381  and     r12d, 80004000h
0x18001c388  neg     r12d
0x18001c38b  sbb     eax, eax
0x18001c38d  and     eax, 4
0x18001c390  or      edx, eax
0x18001c392  mov     rax, [r8+18h]
0x18001c396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39b  mov     ebx, eax
0x18001c39d  jmp     loc_18001C1A9
0x18001c3a2  mov     rdx, r15; enum WTS_ALPHATYPE *
0x18001c3a5  mov     rcx, [rbp+3Fh+ho]; h
0x18001c3a9  call    ?ConvertDDB2DIB@@YAPEAUHBITMAP__@@PEAU1@PEAW4WTS_ALPHATYPE@@@Z; ConvertDDB2DIB(HBITMAP__ *,WTS_ALPHATYPE *)
0x18001c3ae  mov     rbx, rax
0x18001c3b1  mov     r8, [rbp+3Fh+ho]
0x18001c3b5  cmp     rax, r8
0x18001c3b8  jz      short loc_18001C3CA
0x18001c3ba  mov     rcx, r8; ho
0x18001c3bd  call    cs:__imp_DeleteObject
0x18001c3c3  mov     r8, rbx
0x18001c3c6  mov     [rbp+3Fh+ho], rbx
0x18001c3ca  test    r8, r8
0x18001c3cd  jz      short loc_18001C3F5
0x18001c3cf  mov     r9, r14
0x18001c3d2  mov     ecx, [rbp+3Fh+var_90]
0x18001c3d5  call    ?AdjustImage@@YAJIW4AI_FLAGS@@PEAUHBITMAP__@@PEAPEAU2@@Z; AdjustImage(uint,AI_FLAGS,HBITMAP__ *,HBITMAP__ * *)
0x18001c3da  mov     ebx, eax
0x18001c3dc  mov     r8d, 1
0x18001c3e2  cmp     eax, r8d
0x18001c3e5  jnz     short loc_18001C3FF
0x18001c3e7  mov     rax, [rbp+3Fh+ho]
0x18001c3eb  mov     [r14], rax
0x18001c3ee  xor     ebx, ebx
0x18001c3f0  jmp     loc_18001C30D
0x18001c3f5  mov     ebx, 80004005h
0x18001c3fa  jmp     loc_18001C30D
0x18001c3ff  mov     rcx, [rbp+3Fh+ho]; ho
0x18001c403  call    cs:__imp_DeleteObject
0x18001c409  jmp     loc_18001C30D
0x18001c40e  mov     dword ptr [r13+0], 0
0x18001c416  xor     ebx, ebx
0x18001c418  jmp     loc_18001C211
```
