# TSPackBuffers(_SecBufferDesc *,uchar *,ulong,uchar *,ulong,_SecBuffer *,long,uchar *,ulong)

- ea: `0x180004f20`
- end: `0x1800052ea`
- name: `?TSPackBuffers@@YAJPEAU_SecBufferDesc@@PEAEK1KPEAU_SecBuffer@@J1K@Z`
- size: `970`
- prototype: `__int64 __fastcall(struct _SecBufferDesc *, unsigned __int8 *, int, unsigned __int8 *, unsigned int, struct _SecBuffer *, int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006650`

## callees

- `0x180004f20`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `MSASN1!ASN1_CloseEncoder` at `0x1800050e9`
- `MSASN1!ASN1_CloseEncoder` at `0x1800050e9`
- `MSASN1!ASN1_CreateEncoder` at `0x180004ff8`
- `MSASN1!ASN1_CreateEncoder` at `0x180004ff8`
- `MSASN1!ASN1_CreateModule` at `0x1800052c3`
- `MSASN1!ASN1_CreateModule` at `0x1800052c3`
- `MSASN1!ASN1_Encode` at `0x180005024`
- `MSASN1!ASN1_Encode` at `0x180005024`
- `MSASN1!ASN1_FreeEncoded` at `0x18000507a`
- `MSASN1!ASN1_FreeEncoded` at `0x18000507a`

## pseudocode

```c
__int64 __fastcall TSPackBuffers(
        struct _SecBufferDesc *a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct _SecBuffer *a6,
        int a7,
        unsigned __int8 *a8,
        unsigned int a9)
{
  int v9; // esi
  int v12; // eax
  struct _SecBuffer *v14; // rdi
  unsigned int v15; // r12d
  __int16 v16; // dx
  __int64 Module; // rax
  void *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdi
  __int64 v24; // r8
  __int128 v25; // [rsp+50h] [rbp-51h] BYREF
  __int128 v26; // [rsp+60h] [rbp-41h]
  __int128 v27; // [rsp+70h] [rbp-31h]
  __int128 v28; // [rsp+80h] [rbp-21h]
  unsigned __int8 *v29; // [rsp+90h] [rbp-11h]
  __int64 v30; // [rsp+E0h] [rbp+3Fh] BYREF
  int v31; // [rsp+F0h] [rbp+4Fh]

  v31 = a3;
  v9 = a7;
  v12 = a3;
  v29 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( __PAIR128__((unsigned __int64)a1, (unsigned __int64)a2) == 0 && !a4 && a7 >= 0 )
    return 3221225485LL;
  v14 = a6;
  if ( !a6 )
    return 3221225485LL;
  v15 = 0;
  if ( a1 )
  {
    while ( 1 )
    {
      if ( v15 >= a1->cBuffers )
      {
        v12 = v31;
        break;
      }
      if ( a1->pBuffers[v15].cbBuffer )
      {
        LOWORD(v25) = v25 | 0x80;
        if ( TSGlobalState == 1 )
        {
          v24 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(24);
          if ( !v24 )
            goto LABEL_42;
        }
        else
        {
          v24 = ((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(24);
          if ( !v24 )
          {
LABEL_42:
            v19 = -1073741670;
            goto LABEL_23;
          }
          *(_OWORD *)v24 = 0;
          *(_QWORD *)(v24 + 16) = 0;
        }
        *(_QWORD *)(v24 + 16) = a1->pBuffers[v15].pvBuffer;
        *(_DWORD *)(v24 + 8) = a1->pBuffers[v15].cbBuffer;
        if ( *((_QWORD *)&v25 + 1) )
          *(_QWORD *)v24 = *((_QWORD *)&v25 + 1);
        *((_QWORD *)&v25 + 1) = v24;
      }
      ++v15;
    }
  }
  v16 = v25;
  if ( a2 )
  {
    v16 = v25 | 0x40;
    LODWORD(v26) = v12;
    LOWORD(v25) = v25 | 0x40;
    *((_QWORD *)&v26 + 1) = a2;
  }
  if ( a4 )
  {
    v16 |= 0x20u;
    LOWORD(v25) = v16;
    LODWORD(v27) = a5;
    *((_QWORD *)&v27 + 1) = a4;
  }
  if ( v9 < 0 )
  {
    v16 |= 0x10u;
    LODWORD(v28) = v9;
    LOWORD(v25) = v16;
  }
  if ( a8 )
  {
    v16 |= 8u;
    LOWORD(v25) = v16;
    DWORD2(v28) = a9;
    v29 = a8;
  }
  if ( v16 )
  {
    DWORD1(v25) = 6;
    v30 = 0;
    if ( fTSSSPModuleStarted )
    {
      Module = TSSSP_Module;
    }
    else
    {
      fTSSSPModuleStarted = 1;
      Module = ASN1_CreateModule(
                 0x10000,
                 1024,
                 4096,
                 6,
                 off_18001E1E0,
                 off_18001E1B0,
                 off_18001E180,
                 qword_18001F2E8,
                 1936946036);
      TSSSP_Module = Module;
    }
    if ( (unsigned int)ASN1_CreateEncoder(Module, &v30, 0, 0, 0) )
    {
      v19 = -1073741823;
    }
    else if ( (int)ASN1_Encode(v30, &v25, 3, 16, 0, 0) < 0 )
    {
      v19 = -1073741823;
    }
    else
    {
      v18 = (void *)((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocateLsaHeap)(*(unsigned int *)(v30 + 28));
      v14->pvBuffer = v18;
      if ( v18 )
      {
        v19 = 0;
        memcpy_0(v18, *(const void **)(v30 + 16), *(unsigned int *)(v30 + 28));
        v20 = v30;
        v14->cbBuffer = *(_DWORD *)(v30 + 28);
      }
      else
      {
        v20 = v30;
        v19 = -1073741823;
      }
      ASN1_FreeEncoded(v20, *(_QWORD *)(v20 + 16));
    }
    if ( v30 )
      ASN1_CloseEncoder();
  }
  else
  {
    v19 = 0;
    v14->cbBuffer = 0;
  }
  v14->BufferType = 2;
LABEL_23:
  v21 = (_QWORD *)*((_QWORD *)&v25 + 1);
  if ( *((_QWORD *)&v25 + 1) )
  {
    do
    {
      v22 = (_QWORD *)*v21;
      if ( TSGlobalState == 1 )
        ((void (__fastcall *)(_QWORD *))TSGlobalLsaFunctions->FreePrivateHeap)(v21);
      else
        ((void (__fastcall *)(_QWORD *))TSGlobalDllFunctions->FreeHeap)(v21);
      v21 = v22;
    }
    while ( v22 );
  }
  return v19;
}

```

## disassembly

```asm
0x180004f20  mov     [rsp-8+arg_10], r8d
0x180004f25  push    rbp
0x180004f26  push    rbx
0x180004f27  push    rsi
0x180004f28  push    rdi
0x180004f29  push    r14
0x180004f2b  push    r15
0x180004f2d  lea     rbp, [rsp-7]
0x180004f32  sub     rsp, 0A8h
0x180004f39  mov     esi, [rbp+2Fh+arg_30]
0x180004f3c  xorps   xmm0, xmm0
0x180004f3f  mov     rbx, rcx
0x180004f42  mov     r15, r9
0x180004f45  xor     ecx, ecx
0x180004f47  mov     eax, r8d
0x180004f4a  mov     [rbp+2Fh+var_40], rcx
0x180004f4e  mov     r14, rdx
0x180004f51  movups  [rbp+2Fh+var_80], xmm0
0x180004f55  movups  [rbp+2Fh+var_70], xmm0
0x180004f59  movups  [rbp+2Fh+var_60], xmm0
0x180004f5d  movups  [rbp+2Fh+var_50], xmm0
0x180004f61  test    rbx, rbx
0x180004f64  jz      loc_1800051E4
0x180004f6a  mov     rdi, [rbp+2Fh+arg_28]
0x180004f6e  test    rdi, rdi
0x180004f71  jz      loc_180005181
0x180004f77  mov     [rsp+0D0h+arg_8], r12
0x180004f7f  xor     r12d, r12d
0x180004f82  mov     [rsp+0D0h+var_30], r13
0x180004f8a  test    rbx, rbx
0x180004f8d  jnz     loc_1800050F1
0x180004f93  movzx   edx, word ptr [rbp+2Fh+var_80]
0x180004f97  test    r14, r14
0x180004f9a  jnz     loc_180005219
0x180004fa0  test    r15, r15
0x180004fa3  jnz     loc_18000522D
0x180004fa9  test    esi, esi
0x180004fab  js      loc_180005244
0x180004fb1  mov     rcx, [rbp+2Fh+arg_38]
0x180004fb5  test    rcx, rcx
0x180004fb8  jnz     loc_180005254
0x180004fbe  test    dx, dx
0x180004fc1  jz      loc_1800052DF
0x180004fc7  cmp     cs:?fTSSSPModuleStarted@@3HA, 0; int fTSSSPModuleStarted
0x180004fce  mov     dword ptr [rbp+2Fh+var_80+4], 6
0x180004fd5  mov     [rbp+2Fh+arg_0], r12
0x180004fd9  jz      loc_18000526B
0x180004fdf  mov     rax, cs:TSSSP_Module
0x180004fe6  xor     r9d, r9d
0x180004fe9  mov     [rsp+0D0h+var_B0], r12
0x180004fee  xor     r8d, r8d
0x180004ff1  lea     rdx, [rbp+2Fh+arg_0]
0x180004ff5  mov     rcx, rax
0x180004ff8  call    cs:__imp_ASN1_CreateEncoder
0x180004ffe  test    eax, eax
0x180005000  jnz     loc_1800052D5
0x180005006  mov     rcx, [rbp+2Fh+arg_0]
0x18000500a  lea     rdx, [rbp+2Fh+var_80]
0x18000500e  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x180005013  mov     r9d, 10h
0x180005019  mov     r8d, 3
0x18000501f  mov     [rsp+0D0h+var_B0], r12
0x180005024  call    cs:__imp_ASN1_Encode
0x18000502a  test    eax, eax
0x18000502c  js      loc_180005196
0x180005032  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180005039  mov     rcx, [rbp+2Fh+arg_0]
0x18000503d  mov     rax, [rax+28h]
0x180005041  mov     ecx, [rcx+1Ch]
0x180005044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005049  mov     [rdi+8], rax
0x18000504d  test    rax, rax
0x180005050  jz      loc_1800051A0
0x180005056  mov     rdx, [rbp+2Fh+arg_0]
0x18000505a  mov     rcx, rax; void *
0x18000505d  mov     ebx, r12d
0x180005060  mov     r8d, [rdx+1Ch]; Size
0x180005064  mov     rdx, [rdx+10h]; Src
0x180005068  call    memcpy_0
0x18000506d  mov     rcx, [rbp+2Fh+arg_0]
0x180005071  mov     eax, [rcx+1Ch]
0x180005074  mov     [rdi], eax
0x180005076  mov     rdx, [rcx+10h]
0x18000507a  call    cs:__imp_ASN1_FreeEncoded
0x180005080  mov     rcx, [rbp+2Fh+arg_0]
0x180005084  test    rcx, rcx
0x180005087  jnz     short loc_1800050E9
0x180005089  mov     dword ptr [rdi+4], 2
0x180005090  mov     rdx, qword ptr [rbp+2Fh+var_80+8]
0x180005094  mov     r13, [rsp+0D0h+var_30]
0x18000509c  mov     r12, [rsp+0D0h+arg_8]
0x1800050a4  test    rdx, rdx
0x1800050a7  jz      short loc_1800050D7
0x1800050a9  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800050b0  mov     rdi, [rdx]
0x1800050b3  jnz     loc_1800051AE
0x1800050b9  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800050c0  mov     rax, [rax+188h]
0x1800050c7  mov     rcx, rdx
0x1800050ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050cf  mov     rdx, rdi
0x1800050d2  test    rdi, rdi
0x1800050d5  jnz     short loc_1800050A9
0x1800050d7  mov     eax, ebx
0x1800050d9  add     rsp, 0A8h
0x1800050e0  pop     r15
0x1800050e2  pop     r14
0x1800050e4  pop     rdi
0x1800050e5  pop     rsi
0x1800050e6  pop     rbx
0x1800050e7  pop     rbp
0x1800050e8  retn
0x1800050e9  call    cs:__imp_ASN1_CloseEncoder
0x1800050ef  jmp     short loc_180005089
0x1800050f1  mov     ecx, 80h
0x1800050f6  cmp     r12d, [rbx+4]
0x1800050fa  jnb     short loc_180005176
0x1800050fc  mov     rax, [rbx+8]
0x180005100  mov     r13d, r12d
0x180005103  add     r13, r13
0x180005106  cmp     dword ptr [rax+r13*8], 0
0x18000510b  jz      short loc_180005171
0x18000510d  or      word ptr [rbp+2Fh+var_80], cx
0x180005111  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180005118  jnz     loc_1800051BE
0x18000511e  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180005125  mov     ecx, 18h
0x18000512a  mov     rax, [rax+180h]
0x180005131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005136  mov     r8, rax
0x180005139  test    rax, rax
0x18000513c  jz      loc_1800051DA
0x180005142  mov     rcx, [rbx+8]
0x180005146  mov     rdx, [rcx+r13*8+8]
0x18000514b  mov     [r8+10h], rdx
0x18000514f  mov     rcx, [rbx+8]
0x180005153  mov     eax, [rcx+r13*8]
0x180005157  mov     ecx, 80h
0x18000515c  mov     [r8+8], eax
0x180005160  mov     rax, qword ptr [rbp+2Fh+var_80+8]
0x180005164  test    rax, rax
0x180005167  jnz     loc_180005211
0x18000516d  mov     qword ptr [rbp+2Fh+var_80+8], r8
0x180005171  inc     r12d
0x180005174  jmp     short loc_1800050F6
0x180005176  mov     eax, [rbp+2Fh+arg_10]
0x180005179  xor     r12d, r12d
0x18000517c  jmp     loc_180004F93
0x180005181  mov     eax, 0C000000Dh
0x180005186  add     rsp, 0A8h
0x18000518d  pop     r15
0x18000518f  pop     r14
0x180005191  pop     rdi
0x180005192  pop     rsi
0x180005193  pop     rbx
0x180005194  pop     rbp
0x180005195  retn
0x180005196  mov     ebx, 0C0000001h
0x18000519b  jmp     loc_180005080
0x1800051a0  mov     rcx, [rbp+2Fh+arg_0]
0x1800051a4  mov     ebx, 0C0000001h
0x1800051a9  jmp     loc_180005076
0x1800051ae  mov     rcx, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800051b5  mov     rax, [rcx+8]
0x1800051b9  jmp     loc_1800050C7
0x1800051be  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800051c5  mov     ecx, 18h
0x1800051ca  mov     rax, [rax]
0x1800051cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d2  mov     r8, rax
0x1800051d5  test    rax, rax
0x1800051d8  jnz     short loc_1800051FF
0x1800051da  mov     ebx, 0C000009Ah
0x1800051df  jmp     loc_180005090
0x1800051e4  test    r14, r14
0x1800051e7  jnz     loc_180004F6A
0x1800051ed  test    r15, r15
0x1800051f0  jnz     loc_180004F6A
0x1800051f6  test    esi, esi
0x1800051f8  jns     short loc_180005181
0x1800051fa  jmp     loc_180004F6A
0x1800051ff  xorps   xmm0, xmm0
0x180005202  xor     eax, eax
0x180005204  movups  xmmword ptr [r8], xmm0
0x180005208  mov     [r8+10h], rax
0x18000520c  jmp     loc_180005142
0x180005211  mov     [r8], rax
0x180005214  jmp     loc_18000516D
0x180005219  or      dx, 40h
0x18000521d  mov     dword ptr [rbp+2Fh+var_70], eax
0x180005220  mov     word ptr [rbp+2Fh+var_80], dx
0x180005224  mov     qword ptr [rbp+2Fh+var_70+8], r14
0x180005228  jmp     loc_180004FA0
0x18000522d  mov     eax, [rbp+2Fh+arg_20]
0x180005230  or      dx, 20h
0x180005234  mov     word ptr [rbp+2Fh+var_80], dx
0x180005238  mov     dword ptr [rbp+2Fh+var_60], eax
0x18000523b  mov     qword ptr [rbp+2Fh+var_60+8], r15
0x18000523f  jmp     loc_180004FA9
0x180005244  or      dx, 10h
0x180005248  mov     dword ptr [rbp+2Fh+var_50], esi
0x18000524b  mov     word ptr [rbp+2Fh+var_80], dx
0x18000524f  jmp     loc_180004FB1
0x180005254  mov     eax, [rbp+2Fh+arg_40]
0x180005257  or      dx, 8
0x18000525b  mov     word ptr [rbp+2Fh+var_80], dx
0x18000525f  mov     dword ptr [rbp+2Fh+var_50+8], eax
0x180005262  mov     [rbp+2Fh+var_40], rcx
0x180005266  jmp     loc_180004FBE
0x18000526b  mov     [rsp+0D0h+var_90], 73737374h
0x180005273  lea     rax, qword_18001F2E8
0x18000527a  mov     [rsp+0D0h+var_98], rax
0x18000527f  mov     edx, 400h
0x180005284  lea     rax, off_18001E180
0x18000528b  mov     cs:?fTSSSPModuleStarted@@3HA, 1; int fTSSSPModuleStarted
0x180005295  mov     [rsp+0D0h+var_A0], rax
0x18000529a  mov     ecx, 10000h
0x18000529f  lea     rax, off_18001E1B0
0x1800052a6  mov     r9d, 6
0x1800052ac  mov     [rsp+0D0h+var_A8], rax
0x1800052b1  mov     r8d, 1000h
0x1800052b7  lea     rax, off_18001E1E0
0x1800052be  mov     [rsp+0D0h+var_B0], rax
0x1800052c3  call    cs:__imp_ASN1_CreateModule
0x1800052c9  mov     cs:TSSSP_Module, rax
0x1800052d0  jmp     loc_180004FE6
0x1800052d5  mov     ebx, 0C0000001h
0x1800052da  jmp     loc_180005080
0x1800052df  mov     ebx, r12d
0x1800052e2  mov     [rdi], r12d
0x1800052e5  jmp     loc_180005089
```
