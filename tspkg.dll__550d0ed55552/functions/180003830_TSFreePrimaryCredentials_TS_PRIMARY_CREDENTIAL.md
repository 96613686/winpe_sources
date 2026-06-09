# TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)

- ea: `0x180003830`
- end: `0x180003d26`
- name: `?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(struct _TS_PRIMARY_CREDENTIAL *)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001160`
- `0x1800029b0`
- `0x1800034b0`
- `0x180004170`
- `0x180006650`
- `0x180012af0`
- `0x180013f70`
- `0x180014100`
- `0x18001449c`
- `0x180014720`
- `0x1800147b0`
- `0x180014a84`
- `0x180019958`

## callees

- `0x180003830`
- `0x18001d010`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180003943`
- `CRYPT32!CertFreeCertificateContext` at `0x180003943`

## pseudocode

```c
__int64 __fastcall TSFreePrimaryCredentials(struct _TS_PRIMARY_CREDENTIAL *a1)
{
  _OWORD *v2; // rbx
  void (*FreePrivateHeap)(void); // rax
  void (*FreeHeap)(void); // rax
  _BYTE *v5; // rax
  __int64 v6; // rcx
  void (*v7)(void); // rax
  const CERT_CONTEXT *v8; // rcx
  void (*v9)(void); // rax
  void (*v10)(void); // rax
  void (*v11)(void); // rax
  void (*v12)(void); // rax
  void (*v13)(void); // rax
  _BYTE *v14; // rax
  __int64 v15; // rcx
  void (*v16)(void); // rax
  _BYTE *v17; // rax
  __int64 v18; // rcx
  void (*v19)(void); // rax
  void (*v20)(void); // rax
  _BYTE *v21; // rax
  __int64 v22; // rcx
  void (*v23)(void); // rax
  unsigned int i; // esi
  __int64 v25; // rbx
  void (*v26)(void); // rax
  _BYTE *v27; // rax
  __int64 v28; // rcx
  void (*v29)(void); // rax
  void (*v30)(void); // rax

  if ( a1 )
  {
    v2 = (_OWORD *)((char *)a1 + 24);
    if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-24LL && *((_QWORD *)a1 + 4) )
    {
      if ( TSGlobalState == 1 )
        FreePrivateHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        FreePrivateHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      FreePrivateHeap();
      *v2 = 0;
    }
    if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-8LL && *((_QWORD *)a1 + 2) )
    {
      if ( TSGlobalState == 1 )
        FreeHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        FreeHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      FreeHeap();
      *(_OWORD *)((char *)a1 + 8) = 0;
    }
    v5 = (_BYTE *)*((_QWORD *)a1 + 6);
    if ( v5 )
    {
      v6 = *((unsigned __int16 *)a1 + 20);
      if ( *((_WORD *)a1 + 20) )
      {
        do
        {
          *v5++ = 0;
          --v6;
        }
        while ( v6 );
      }
      if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-40LL && *((_QWORD *)a1 + 6) )
      {
        if ( TSGlobalState == 1 )
          v7 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v7 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v7();
        *(_OWORD *)((char *)a1 + 40) = 0;
      }
    }
    v8 = (const CERT_CONTEXT *)*((_QWORD *)a1 + 7);
    if ( v8 )
      CertFreeCertificateContext(v8);
    if ( *((_QWORD *)a1 + 8) )
    {
      if ( TSGlobalState == 1 )
        v9 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        v9 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      v9();
    }
    if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-80LL )
    {
      if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-88LL && *((_QWORD *)a1 + 12) )
      {
        if ( TSGlobalState == 1 )
          v10 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v10 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v10();
        *(_OWORD *)((char *)a1 + 88) = 0;
      }
      if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-120LL && *((_QWORD *)a1 + 16) )
      {
        if ( TSGlobalState == 1 )
          v11 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v11 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v11();
        *(_OWORD *)((char *)a1 + 120) = 0;
      }
      if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-136LL && *((_QWORD *)a1 + 18) )
      {
        if ( TSGlobalState == 1 )
          v12 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v12 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v12();
        *(_OWORD *)((char *)a1 + 136) = 0;
      }
      if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-104LL && *((_QWORD *)a1 + 14) )
      {
        if ( TSGlobalState == 1 )
          v13 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v13 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v13();
        *(_OWORD *)((char *)a1 + 104) = 0;
      }
    }
    v14 = (_BYTE *)*((_QWORD *)a1 + 19);
    if ( v14 )
    {
      v15 = *((unsigned int *)a1 + 40);
      if ( (_DWORD)v15 )
      {
        do
        {
          *v14++ = 0;
          --v15;
        }
        while ( v15 );
        if ( *((_QWORD *)a1 + 19) )
        {
          if ( TSGlobalState == 1 )
            v16 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
          else
            v16 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
          v16();
        }
      }
    }
    v17 = (_BYTE *)*((_QWORD *)a1 + 21);
    if ( v17 )
    {
      v18 = *((unsigned int *)a1 + 44);
      if ( *((_DWORD *)a1 + 44) )
      {
        do
        {
          *v17++ = 0;
          --v18;
        }
        while ( v18 );
      }
      if ( *((_QWORD *)a1 + 21) )
      {
        if ( TSGlobalState == 1 )
          v19 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v19 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v19();
      }
    }
    if ( a1 != (struct _TS_PRIMARY_CREDENTIAL *)-184LL && *((_QWORD *)a1 + 24) )
    {
      if ( TSGlobalState == 1 )
        v20 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        v20 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      v20();
      *(_OWORD *)((char *)a1 + 184) = 0;
    }
    v21 = (_BYTE *)*((_QWORD *)a1 + 26);
    if ( v21 )
    {
      v22 = *((unsigned int *)a1 + 50);
      if ( *((_DWORD *)a1 + 50) )
      {
        do
        {
          *v21++ = 0;
          --v22;
        }
        while ( v22 );
      }
      if ( *((_QWORD *)a1 + 26) )
      {
        if ( TSGlobalState == 1 )
          v23 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v23 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v23();
      }
    }
    for ( i = 0; i < *((_DWORD *)a1 + 54); ++i )
    {
      v25 = *((_QWORD *)a1 + 28) + 32LL * i;
      if ( v25 && *(_QWORD *)(v25 + 8) )
      {
        if ( TSGlobalState == 1 )
          v26 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
        else
          v26 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
        v26();
        *(_OWORD *)v25 = 0;
      }
      v27 = *(_BYTE **)(v25 + 24);
      if ( v27 )
      {
        v28 = *(unsigned int *)(v25 + 16);
        if ( *(_DWORD *)(v25 + 16) )
        {
          do
          {
            *v27++ = 0;
            --v28;
          }
          while ( v28 );
        }
        if ( *(_QWORD *)(v25 + 24) )
        {
          if ( TSGlobalState == 1 )
            v29 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
          else
            v29 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
          v29();
        }
      }
    }
    if ( *((_QWORD *)a1 + 28) )
    {
      if ( TSGlobalState == 1 )
        v30 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        v30 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      v30();
      *((_QWORD *)a1 + 28) = 0;
    }
    if ( TSGlobalState == 1 )
    {
      ((void (__fastcall *)(struct _TS_PRIMARY_CREDENTIAL *))TSGlobalLsaFunctions->FreePrivateHeap)(a1);
      return 0;
    }
    ((void (__fastcall *)(struct _TS_PRIMARY_CREDENTIAL *))TSGlobalDllFunctions->FreeHeap)(a1);
  }
  return 0;
}

```

## disassembly

```asm
0x180003830  push    rdi
0x180003832  sub     rsp, 20h
0x180003836  mov     rdi, rcx
0x180003839  test    rcx, rcx
0x18000383c  jz      loc_180003D1E
0x180003842  mov     [rsp+28h+arg_0], rbx
0x180003847  lea     rbx, [rcx+18h]
0x18000384b  mov     [rsp+28h+arg_8], rsi
0x180003850  test    rbx, rbx
0x180003853  jz      short loc_18000388D
0x180003855  mov     rcx, [rbx+8]
0x180003859  test    rcx, rcx
0x18000385c  jz      short loc_18000388D
0x18000385e  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003865  jnz     short loc_180003877
0x180003867  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000386e  mov     rax, [rax+188h]
0x180003875  jmp     short loc_180003882
0x180003877  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000387e  mov     rax, [rax+8]
0x180003882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003887  xorps   xmm0, xmm0
0x18000388a  movups  xmmword ptr [rbx], xmm0
0x18000388d  lea     rbx, [rdi+8]
0x180003891  test    rbx, rbx
0x180003894  jz      short loc_1800038CE
0x180003896  mov     rcx, [rbx+8]
0x18000389a  test    rcx, rcx
0x18000389d  jz      short loc_1800038CE
0x18000389f  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800038a6  jnz     short loc_1800038B8
0x1800038a8  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800038af  mov     rax, [rax+188h]
0x1800038b6  jmp     short loc_1800038C3
0x1800038b8  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800038bf  mov     rax, [rax+8]
0x1800038c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c8  xorps   xmm0, xmm0
0x1800038cb  movups  xmmword ptr [rbx], xmm0
0x1800038ce  mov     rax, [rdi+30h]
0x1800038d2  test    rax, rax
0x1800038d5  jz      short loc_18000393A
0x1800038d7  movzx   ecx, word ptr [rdi+28h]
0x1800038db  lea     rbx, [rdi+28h]
0x1800038df  test    rcx, rcx
0x1800038e2  jz      short loc_1800038FD
0x1800038e4  nop     dword ptr [rax+00h]
0x1800038e8  nop     dword ptr [rax+rax+00000000h]
0x1800038f0  mov     byte ptr [rax], 0
0x1800038f3  lea     rax, [rax+1]
0x1800038f7  sub     rcx, 1
0x1800038fb  jnz     short loc_1800038F0
0x1800038fd  test    rbx, rbx
0x180003900  jz      short loc_18000393A
0x180003902  mov     rcx, [rbx+8]
0x180003906  test    rcx, rcx
0x180003909  jz      short loc_18000393A
0x18000390b  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003912  jnz     short loc_180003924
0x180003914  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000391b  mov     rax, [rax+188h]
0x180003922  jmp     short loc_18000392F
0x180003924  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000392b  mov     rax, [rax+8]
0x18000392f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003934  xorps   xmm0, xmm0
0x180003937  movups  xmmword ptr [rbx], xmm0
0x18000393a  mov     rcx, [rdi+38h]; pCertContext
0x18000393e  test    rcx, rcx
0x180003941  jz      short loc_180003949
0x180003943  call    cs:__imp_CertFreeCertificateContext
0x180003949  mov     rcx, [rdi+40h]
0x18000394d  test    rcx, rcx
0x180003950  jz      short loc_18000397B
0x180003952  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003959  jnz     short loc_18000396B
0x18000395b  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003962  mov     rax, [rax+188h]
0x180003969  jmp     short loc_180003976
0x18000396b  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003972  mov     rax, [rax+8]
0x180003976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397b  lea     rbx, [rdi+50h]
0x18000397f  test    rbx, rbx
0x180003982  jz      loc_180003A89
0x180003988  lea     rsi, [rbx+8]
0x18000398c  test    rsi, rsi
0x18000398f  jz      short loc_1800039C9
0x180003991  mov     rcx, [rsi+8]
0x180003995  test    rcx, rcx
0x180003998  jz      short loc_1800039C9
0x18000399a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800039a1  jnz     short loc_1800039B3
0x1800039a3  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800039aa  mov     rax, [rax+188h]
0x1800039b1  jmp     short loc_1800039BE
0x1800039b3  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800039ba  mov     rax, [rax+8]
0x1800039be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c3  xorps   xmm0, xmm0
0x1800039c6  movups  xmmword ptr [rsi], xmm0
0x1800039c9  lea     rsi, [rbx+28h]
0x1800039cd  test    rsi, rsi
0x1800039d0  jz      short loc_180003A0A
0x1800039d2  mov     rcx, [rsi+8]
0x1800039d6  test    rcx, rcx
0x1800039d9  jz      short loc_180003A0A
0x1800039db  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800039e2  jnz     short loc_1800039F4
0x1800039e4  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800039eb  mov     rax, [rax+188h]
0x1800039f2  jmp     short loc_1800039FF
0x1800039f4  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800039fb  mov     rax, [rax+8]
0x1800039ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a04  xorps   xmm0, xmm0
0x180003a07  movups  xmmword ptr [rsi], xmm0
0x180003a0a  lea     rsi, [rbx+38h]
0x180003a0e  test    rsi, rsi
0x180003a11  jz      short loc_180003A4B
0x180003a13  mov     rcx, [rsi+8]
0x180003a17  test    rcx, rcx
0x180003a1a  jz      short loc_180003A4B
0x180003a1c  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003a23  jnz     short loc_180003A35
0x180003a25  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003a2c  mov     rax, [rax+188h]
0x180003a33  jmp     short loc_180003A40
0x180003a35  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003a3c  mov     rax, [rax+8]
0x180003a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a45  xorps   xmm0, xmm0
0x180003a48  movups  xmmword ptr [rsi], xmm0
0x180003a4b  add     rbx, 18h
0x180003a4f  jz      short loc_180003A89
0x180003a51  mov     rcx, [rbx+8]
0x180003a55  test    rcx, rcx
0x180003a58  jz      short loc_180003A89
0x180003a5a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003a61  jnz     short loc_180003A73
0x180003a63  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003a6a  mov     rax, [rax+188h]
0x180003a71  jmp     short loc_180003A7E
0x180003a73  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003a7a  mov     rax, [rax+8]
0x180003a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a83  xorps   xmm0, xmm0
0x180003a86  movups  xmmword ptr [rbx], xmm0
0x180003a89  mov     rax, [rdi+98h]
0x180003a90  test    rax, rax
0x180003a93  jz      short loc_180003AE2
0x180003a95  mov     ecx, [rdi+0A0h]
0x180003a9b  test    ecx, ecx
0x180003a9d  jz      short loc_180003AE2
0x180003a9f  nop
0x180003aa0  mov     byte ptr [rax], 0
0x180003aa3  lea     rax, [rax+1]
0x180003aa7  sub     rcx, 1
0x180003aab  jnz     short loc_180003AA0
0x180003aad  mov     rcx, [rdi+98h]
0x180003ab4  test    rcx, rcx
0x180003ab7  jz      short loc_180003AE2
0x180003ab9  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003ac0  jnz     short loc_180003AD2
0x180003ac2  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003ac9  mov     rax, [rax+188h]
0x180003ad0  jmp     short loc_180003ADD
0x180003ad2  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003ad9  mov     rax, [rax+8]
0x180003add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae2  mov     rax, [rdi+0A8h]
0x180003ae9  test    rax, rax
0x180003aec  jz      short loc_180003B42
0x180003aee  mov     ecx, [rdi+0B0h]
0x180003af4  test    rcx, rcx
0x180003af7  jz      short loc_180003B0D
0x180003af9  nop     dword ptr [rax+00000000h]
0x180003b00  mov     byte ptr [rax], 0
0x180003b03  lea     rax, [rax+1]
0x180003b07  sub     rcx, 1
0x180003b0b  jnz     short loc_180003B00
0x180003b0d  mov     rcx, [rdi+0A8h]
0x180003b14  test    rcx, rcx
0x180003b17  jz      short loc_180003B42
0x180003b19  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003b20  jnz     short loc_180003B32
0x180003b22  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003b29  mov     rax, [rax+188h]
0x180003b30  jmp     short loc_180003B3D
0x180003b32  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003b39  mov     rax, [rax+8]
0x180003b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b42  lea     rbx, [rdi+0B8h]
0x180003b49  test    rbx, rbx
0x180003b4c  jz      short loc_180003B86
0x180003b4e  mov     rcx, [rbx+8]
0x180003b52  test    rcx, rcx
0x180003b55  jz      short loc_180003B86
0x180003b57  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003b5e  jnz     short loc_180003B70
0x180003b60  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003b67  mov     rax, [rax+188h]
0x180003b6e  jmp     short loc_180003B7B
0x180003b70  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003b77  mov     rax, [rax+8]
0x180003b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b80  xorps   xmm0, xmm0
0x180003b83  movups  xmmword ptr [rbx], xmm0
0x180003b86  mov     rax, [rbx+18h]
0x180003b8a  test    rax, rax
0x180003b8d  jz      short loc_180003BDF
0x180003b8f  mov     ecx, [rbx+10h]
0x180003b92  test    rcx, rcx
0x180003b95  jz      short loc_180003BAD
0x180003b97  nop     word ptr [rax+rax+00000000h]
0x180003ba0  mov     byte ptr [rax], 0
0x180003ba3  lea     rax, [rax+1]
0x180003ba7  sub     rcx, 1
0x180003bab  jnz     short loc_180003BA0
0x180003bad  mov     rcx, [rbx+18h]
0x180003bb1  test    rcx, rcx
0x180003bb4  jz      short loc_180003BDF
0x180003bb6  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003bbd  jnz     short loc_180003BCF
0x180003bbf  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003bc6  mov     rax, [rax+188h]
0x180003bcd  jmp     short loc_180003BDA
0x180003bcf  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003bd6  mov     rax, [rax+8]
0x180003bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bdf  xor     esi, esi
0x180003be1  cmp     [rdi+0D8h], esi
0x180003be7  jbe     loc_180003C9D
0x180003bed  nop     dword ptr [rax]
0x180003bf0  mov     ebx, esi
0x180003bf2  shl     rbx, 5
0x180003bf6  add     rbx, [rdi+0E0h]
0x180003bfd  jz      short loc_180003C37
0x180003bff  mov     rcx, [rbx+8]
0x180003c03  test    rcx, rcx
0x180003c06  jz      short loc_180003C37
0x180003c08  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003c0f  jnz     short loc_180003C21
0x180003c11  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003c18  mov     rax, [rax+188h]
0x180003c1f  jmp     short loc_180003C2C
0x180003c21  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003c28  mov     rax, [rax+8]
0x180003c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c31  xorps   xmm0, xmm0
0x180003c34  movups  xmmword ptr [rbx], xmm0
0x180003c37  mov     rax, [rbx+18h]
0x180003c3b  test    rax, rax
0x180003c3e  jz      short loc_180003C8F
0x180003c40  mov     ecx, [rbx+10h]
0x180003c43  test    rcx, rcx
0x180003c46  jz      short loc_180003C5D
0x180003c48  nop     dword ptr [rax+rax+00000000h]
0x180003c50  mov     byte ptr [rax], 0
0x180003c53  lea     rax, [rax+1]
0x180003c57  sub     rcx, 1
0x180003c5b  jnz     short loc_180003C50
0x180003c5d  mov     rcx, [rbx+18h]
0x180003c61  test    rcx, rcx
0x180003c64  jz      short loc_180003C8F
0x180003c66  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003c6d  jnz     short loc_180003C7F
0x180003c6f  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003c76  mov     rax, [rax+188h]
0x180003c7d  jmp     short loc_180003C8A
0x180003c7f  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003c86  mov     rax, [rax+8]
0x180003c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8f  inc     esi
0x180003c91  cmp     esi, [rdi+0D8h]
0x180003c97  jb      loc_180003BF0
0x180003c9d  mov     rcx, [rdi+0E0h]
0x180003ca4  mov     rsi, [rsp+28h+arg_8]
0x180003ca9  mov     rbx, [rsp+28h+arg_0]
0x180003cae  test    rcx, rcx
0x180003cb1  jz      short loc_180003CE7
0x180003cb3  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003cba  jnz     short loc_180003CCC
0x180003cbc  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003cc3  mov     rax, [rax+188h]
0x180003cca  jmp     short loc_180003CD7
0x180003ccc  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180003cd3  mov     rax, [rax+8]
0x180003cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cdc  mov     qword ptr [rdi+0E0h], 0
0x180003ce7  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180003cee  mov     rcx, rdi
0x180003cf1  jnz     short loc_180003D0E
0x180003cf3  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180003cfa  mov     rax, [rax+188h]
0x180003d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d06  xor     eax, eax
0x180003d08  add     rsp, 20h
0x180003d0c  pop     rdi
0x180003d0d  retn
  ... truncated ...
```
