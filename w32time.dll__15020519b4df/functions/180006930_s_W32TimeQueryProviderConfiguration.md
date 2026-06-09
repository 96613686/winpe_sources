# s_W32TimeQueryProviderConfiguration

- ea: `0x180006930`
- end: `0x180007032`
- name: `s_W32TimeQueryProviderConfiguration`
- size: `1794`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x180006930`
- `0x18000f5f0`
- `0x180010b74`
- `0x180018138`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006a17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006e45`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006a17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180006e45`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006988`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006df0`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006988`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180006df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007008`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007017`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007008`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007017`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006aef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800069ba`
- `ntdll!RtlReleaseResource` at `0x180006ef0`
- `ntdll!RtlReleaseResource` at `0x180006ef0`
- `ntdll!RtlAcquireResourceShared` at `0x180006eb7`
- `ntdll!RtlAcquireResourceShared` at `0x180006eb7`

## string_xrefs

- `0x180006f04`: `RPC Call - Query Provider Configuration\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall s_W32TimeQueryProviderConfiguration(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v5; // r15
  char v6; // bl
  int v7; // edi
  __int64 j; // r14
  char v9; // bl
  _OWORD *v10; // rax
  __int64 v11; // r13
  __int64 v12; // rax
  SIZE_T v13; // rbx
  SIZE_T v14; // r14
  _WORD *v15; // rax
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rax
  _WORD *v21; // rax
  _WORD *v22; // rcx
  unsigned __int64 v23; // rbx
  __int64 v24; // r8
  __int16 v25; // dx
  unsigned __int64 v26; // r14
  __int64 v27; // r8
  __int64 v28; // r9
  __int16 v29; // dx
  __int64 i; // rdx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  __int64 v34; // [rsp+38h] [rbp-E0h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-D8h]
  _WORD *v36; // [rsp+48h] [rbp-D0h]
  __int64 k; // [rsp+50h] [rbp-C8h]
  _WORD *v38; // [rsp+58h] [rbp-C0h]
  __int64 m; // [rsp+60h] [rbp-B8h]
  _WORD *v40; // [rsp+68h] [rbp-B0h]
  unsigned __int64 v41; // [rsp+70h] [rbp-A8h]
  __int64 v42; // [rsp+78h] [rbp-A0h]
  _WORD *v43; // [rsp+80h] [rbp-98h]
  unsigned __int64 v44; // [rsp+88h] [rbp-90h]
  __int64 v45; // [rsp+90h] [rbp-88h]
  __int64 v46; // [rsp+98h] [rbp-80h]
  __int64 v47; // [rsp+A0h] [rbp-78h]
  __int64 v48; // [rsp+A8h] [rbp-70h]
  __int64 v49; // [rsp+130h] [rbp+18h]

  v34 = 0;
  if ( !a3 || !a4 )
    return 2147942487LL;
  v5 = 0;
  hMem = 0;
  v46 = _set_se_translator(SeTransFunc);
  v6 = 0;
  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0) )
  {
    if ( _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x45u; i = *(_QWORD *)(i + 8) )
      {
        if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x45 )
        {
          v6 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    }
    if ( v6 )
      FileLogAdd(L"RPC Call - Query Provider Configuration\n");
  }
  EnterCriticalSection(&CriticalSection);
  v7 = 0;
  for ( j = *(_QWORD *)qword_1800A42F0; ; j = *(_QWORD *)(j + 24) )
  {
    v49 = j;
    if ( !j )
    {
      for ( j = *((_QWORD *)qword_1800A42F0 + 1); ; j = *(_QWORD *)(j + 24) )
      {
        v49 = j;
        if ( !j )
          break;
        if ( !(unsigned int)_o__wcsnicmp(a3, *(_QWORD *)(j + 8), 1024) )
        {
          v9 = 0;
          goto LABEL_10;
        }
      }
      v7 = -2147023728;
      goto LABEL_23;
    }
    if ( !(unsigned int)_o__wcsnicmp(a3, *(_QWORD *)(j + 8), 1024) )
      break;
  }
  v9 = 1;
  if ( !*(_BYTE *)(j + 18) )
  {
    v7 = -2147023834;
    goto LABEL_23;
  }
  LODWORD(v34) = 1;
  v7 = SendNotificationToProvider((struct TimeProvider *)j, TPC_Query, &v34);
  if ( *(_BYTE *)(j + 68) != 1
    || *(_DWORD *)(j + 72)
    || (int)RemoveProviderFromList((struct TimeProvider *)j, 1, 0) >= 0 )
  {
LABEL_10:
    v10 = LocalAlloc(0x40u, 0x38u);
    v5 = v10;
    if ( !v10 )
    {
      v7 = -2147024882;
      goto LABEL_23;
    }
    *v10 = 0;
    v10[1] = 0;
    v10[2] = 0;
    *((_QWORD *)v10 + 6) = 0;
    *(_DWORD *)v10 = 56;
    *((_DWORD *)v10 + 2) = v9 != 0;
    *((_DWORD *)v10 + 11) = *(_DWORD *)(j + 92);
    *((_DWORD *)v10 + 1) = *(_BYTE *)(j + 16) != 0;
    *((_DWORD *)v10 + 10) = *(_DWORD *)(j + 84);
    v11 = -1;
    if ( *(_QWORD *)j )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(*(_QWORD *)j + 2 * v12) );
      v47 = 0;
      v13 = 2;
      v14 = 2 * (v12 + 1);
      if ( !is_mul_ok(2u, v12 + 1) )
      {
        v7 = -2147024362;
        goto LABEL_23;
      }
      v7 = 0;
    }
    else
    {
      v13 = 2;
      v14 = 2;
    }
    v15 = LocalAlloc(0x40u, v14);
    v5[2] = v15;
    if ( !v15 )
    {
      v7 = -2147024882;
      goto LABEL_23;
    }
    v16 = v49;
    v17 = *(_WORD **)v49;
    if ( *(_QWORD *)v49 )
    {
      v26 = v14 >> 1;
      if ( !v26 || (v7 = 0, v26 > 0x7FFFFFFF) )
        v7 = -2147024809;
      v18 = 2147483646;
      if ( v7 < 0 )
      {
        if ( v26 )
          *v15 = 0;
      }
      else
      {
        v27 = 2147483646;
        v42 = 2147483646;
        v40 = v17;
        v41 = v26;
        v36 = v15;
        v28 = 0;
        for ( k = 0; v26; k = v28 )
        {
          if ( !v27 )
            break;
          v29 = *v17;
          if ( !*v17 )
            break;
          v40 = ++v17;
          *v15++ = v29;
          v36 = v15;
          v41 = --v26;
          v42 = --v27;
          ++v28;
        }
        v7 = 0;
        if ( !v26 )
        {
          v36 = --v15;
          k = v28 - 1;
          v7 = -2147024774;
        }
        *v15 = 0;
        v16 = v49;
      }
      if ( v7 < 0 )
        goto LABEL_23;
    }
    else
    {
      *v15 = 0;
      v18 = 2147483646;
    }
    *((_DWORD *)v5 + 8) = *(_DWORD *)(v16 + 76);
    v19 = *(_QWORD *)(v16 + 8);
    if ( v19 )
    {
      do
        ++v11;
      while ( *(_WORD *)(v19 + 2 * v11) );
      v48 = 0;
      v13 = 2 * (v11 + 1);
      if ( !is_mul_ok(2u, v11 + 1) )
      {
        v7 = -2147024362;
        goto LABEL_23;
      }
      v7 = 0;
    }
    v21 = LocalAlloc(0x40u, v13);
    v5[3] = v21;
    if ( !v21 )
    {
      v7 = -2147024882;
      goto LABEL_23;
    }
    v22 = *(_WORD **)(v49 + 8);
    if ( v22 )
    {
      v23 = v13 >> 1;
      if ( !v23 || (v7 = 0, v23 > 0x7FFFFFFF) )
        v7 = -2147024809;
      if ( v7 < 0 )
      {
        if ( v23 )
          *v21 = 0;
      }
      else
      {
        v45 = 2147483646;
        v43 = v22;
        v44 = v23;
        v38 = v21;
        v24 = 0;
        for ( m = 0; v23; m = v24 )
        {
          if ( !v18 )
            break;
          v25 = *v22;
          if ( !*v22 )
            break;
          v43 = ++v22;
          *v21++ = v25;
          v38 = v21;
          v44 = --v23;
          v45 = --v18;
          ++v24;
        }
        v7 = 0;
        if ( !v23 )
        {
          v38 = --v21;
          m = v24 - 1;
          v7 = -2147024774;
        }
        *v21 = 0;
      }
      if ( v7 < 0 )
        goto LABEL_23;
    }
    else
    {
      *v21 = 0;
    }
    *((_DWORD *)v5 + 9) = *(_DWORD *)(v49 + 80);
    if ( hMem )
    {
      v5[6] = hMem;
      hMem = 0;
    }
    else
    {
      v5[6] = 0;
    }
    *a4 = v5;
    v5 = 0;
    _set_se_translator(v46);
    if ( v7 >= 0 )
      v7 = 0;
  }
LABEL_23:
  LeaveCriticalSection(&CriticalSection);
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
  {
    v31 = (void *)v5[2];
    if ( v31 )
      LocalFree(v31);
    v32 = (void *)v5[3];
    if ( v32 )
      LocalFree(v32);
    v33 = (void *)v5[6];
    if ( v33 )
      LocalFree(v33);
    LocalFree(v5);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006930  mov     [rsp+arg_0], rbx
0x180006935  mov     [rsp+arg_8], rsi
0x18000693a  mov     [rsp+arg_18], r9
0x18000693f  push    rdi
0x180006940  push    r12
0x180006942  push    r13
0x180006944  push    r14
0x180006946  push    r15
0x180006948  sub     rsp, 0F0h
0x18000694f  mov     rax, r9
0x180006952  mov     rsi, r8
0x180006955  xor     r12d, r12d
0x180006958  mov     [rsp+118h+var_E0], r12
0x18000695d  test    r8, r8
0x180006960  jz      loc_180007028
0x180006966  test    rax, rax
0x180006969  jz      loc_180007028
0x18000696f  mov     [rsp+118h+var_F4], r12b
0x180006974  mov     r15d, r12d
0x180006977  mov     [rsp+118h+var_E8], r12
0x18000697c  mov     [rsp+118h+hMem], r12
0x180006981  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x180006988  call    cs:__imp__set_se_translator
0x18000698f  nop     dword ptr [rax+rax+00h]
0x180006994  mov     [rsp+118h+var_80], rax
0x18000699c  xor     bl, bl
0x18000699e  mov     [rsp+118h+var_F3], bl
0x1800069a2  xor     eax, eax
0x1800069a4  lock cmpxchg cs:?_lLoggingEnabled@@3JC, r12d; long volatile _lLoggingEnabled
0x1800069ad  jnz     loc_180006E9D
0x1800069b3  lea     rcx, CriticalSection; lpCriticalSection
0x1800069ba  call    cs:__imp_EnterCriticalSection
0x1800069c1  nop     dword ptr [rax+rax+00h]
0x1800069c6  mov     edi, r12d
0x1800069c9  mov     [rsp+118h+var_F8], r12d
0x1800069ce  mov     [rsp+118h+var_F4], 1
0x1800069d3  mov     rax, cs:qword_1800A42F0
0x1800069da  mov     r14, [rax]
0x1800069dd  mov     [rsp+118h+arg_10], r14
0x1800069e5  test    r14, r14
0x1800069e8  jnz     loc_180006E38
0x1800069ee  mov     rax, cs:qword_1800A42F0
0x1800069f5  mov     r14, [rax+8]
0x1800069f9  mov     [rsp+118h+arg_10], r14
0x180006a01  test    r14, r14
0x180006a04  jz      loc_180006DA8
0x180006a0a  mov     r8d, 400h
0x180006a10  mov     rdx, [r14+8]
0x180006a14  mov     rcx, rsi
0x180006a17  call    cs:__imp__o__wcsnicmp
0x180006a1e  nop     dword ptr [rax+rax+00h]
0x180006a23  test    eax, eax
0x180006a25  jnz     loc_180006FA6
0x180006a2b  xor     bl, bl
0x180006a2d  mov     [rsp+118h+var_F2], bl
0x180006a31  mov     edx, 38h ; '8'; uBytes
0x180006a36  mov     ecx, 40h ; '@'; uFlags
0x180006a3b  call    cs:__imp_LocalAlloc
0x180006a42  nop     dword ptr [rax+rax+00h]
0x180006a47  mov     r15, rax
0x180006a4a  mov     [rsp+118h+var_E8], rax
0x180006a4f  test    rax, rax
0x180006a52  jz      loc_180006F4F
0x180006a58  xorps   xmm0, xmm0
0x180006a5b  xor     eax, eax
0x180006a5d  movups  xmmword ptr [r15], xmm0
0x180006a61  movups  xmmword ptr [r15+10h], xmm0
0x180006a66  movups  xmmword ptr [r15+20h], xmm0
0x180006a6b  mov     [r15+30h], rax
0x180006a6f  mov     dword ptr [r15], 38h ; '8'
0x180006a76  mov     eax, r12d
0x180006a79  test    bl, bl
0x180006a7b  setnz   al
0x180006a7e  mov     [r15+8], eax
0x180006a82  mov     eax, [r14+5Ch]
0x180006a86  mov     [r15+2Ch], eax
0x180006a8a  mov     eax, r12d
0x180006a8d  cmp     [r14+10h], al
0x180006a91  setnz   al
0x180006a94  mov     [r15+4], eax
0x180006a98  mov     eax, [r14+54h]
0x180006a9c  mov     [r15+28h], eax
0x180006aa0  mov     rcx, [r14]
0x180006aa3  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180006aaa  test    rcx, rcx
0x180006aad  jz      loc_180006F5D
0x180006ab3  mov     rax, r13
0x180006ab6  inc     rax
0x180006ab9  cmp     word ptr [rcx+rax*2], 0
0x180006abe  jnz     short loc_180006AB6
0x180006ac0  inc     rax
0x180006ac3  mov     [rsp+118h+var_78], r12
0x180006acb  mov     ebx, 2
0x180006ad0  mul     rbx
0x180006ad3  mov     r14, rax
0x180006ad6  test    rdx, rdx
0x180006ad9  jnz     loc_180006BAE
0x180006adf  mov     edi, r12d
0x180006ae2  mov     [rsp+118h+var_F8], r12d
0x180006ae7  mov     rdx, r14; uBytes
0x180006aea  mov     ecx, 40h ; '@'; uFlags
0x180006aef  call    cs:__imp_LocalAlloc
0x180006af6  nop     dword ptr [rax+rax+00h]
0x180006afb  mov     [r15+10h], rax
0x180006aff  test    rax, rax
0x180006b02  jz      loc_180006F6A
0x180006b08  mov     rdx, [rsp+118h+arg_10]
0x180006b10  mov     rcx, [rdx]
0x180006b13  test    rcx, rcx
0x180006b16  jnz     loc_180006CB5
0x180006b1c  mov     [rax], r12w
0x180006b20  mov     esi, 7FFFFFFEh
0x180006b25  mov     eax, [rdx+4Ch]
0x180006b28  mov     [r15+20h], eax
0x180006b2c  mov     rax, [rdx+8]
0x180006b30  test    rax, rax
0x180006b33  jz      loc_180006BC1
0x180006b39  nop     dword ptr [rax+00000000h]
0x180006b40  lea     r13, [r13+1]
0x180006b44  cmp     word ptr [rax+r13*2], 0
0x180006b4a  jnz     short loc_180006B40
0x180006b4c  lea     rax, [r13+1]
0x180006b50  mov     [rsp+118h+var_70], r12
0x180006b58  mul     rbx
0x180006b5b  mov     rbx, rax
0x180006b5e  test    rdx, rdx
0x180006b61  jz      short loc_180006BB9
0x180006b63  mov     edi, 80070216h
0x180006b68  mov     [rsp+118h+var_F8], edi
0x180006b6c  cmp     [rsp+118h+var_F4], 0
0x180006b71  jnz     loc_180006E0C
0x180006b77  mov     rcx, [rsp+118h+hMem]; hMem
0x180006b7c  test    rcx, rcx
0x180006b7f  jnz     loc_180006FC4
0x180006b85  test    r15, r15
0x180006b88  jnz     loc_180006FD5
0x180006b8e  mov     eax, edi
0x180006b90  lea     r11, [rsp+118h+var_28]
0x180006b98  mov     rbx, [r11+30h]
0x180006b9c  mov     rsi, [r11+38h]
0x180006ba0  mov     rsp, r11
0x180006ba3  pop     r15
0x180006ba5  pop     r14
0x180006ba7  pop     r13
0x180006ba9  pop     r12
0x180006bab  pop     rdi
0x180006bac  retn
0x180006bae  mov     edi, 80070216h
0x180006bb3  mov     [rsp+118h+var_F8], edi
0x180006bb7  jmp     short loc_180006B6C
0x180006bb9  mov     edi, r12d
0x180006bbc  mov     [rsp+118h+var_F8], r12d
0x180006bc1  mov     rdx, rbx; uBytes
0x180006bc4  mov     ecx, 40h ; '@'; uFlags
0x180006bc9  call    cs:__imp_LocalAlloc
0x180006bd0  nop     dword ptr [rax+rax+00h]
0x180006bd5  mov     [r15+18h], rax
0x180006bd9  test    rax, rax
0x180006bdc  jz      loc_180006E2A
0x180006be2  mov     r9, [rsp+118h+arg_10]
0x180006bea  mov     rcx, [r9+8]
0x180006bee  test    rcx, rcx
0x180006bf1  jz      loc_180006DB6
0x180006bf7  mov     [rsp+118h+var_EC], r12d
0x180006bfc  shr     rbx, 1
0x180006bff  jz      loc_180006D83
0x180006c05  mov     edi, r12d
0x180006c08  cmp     rbx, 7FFFFFFFh
0x180006c0f  ja      loc_180006D83
0x180006c15  mov     [rsp+118h+var_EC], edi
0x180006c19  test    edi, edi
0x180006c1b  js      loc_180006F94
0x180006c21  mov     [rsp+118h+var_88], rsi
0x180006c29  mov     [rsp+118h+var_98], rcx
0x180006c31  mov     [rsp+118h+var_90], rbx
0x180006c39  mov     [rsp+118h+var_C0], rax
0x180006c3e  mov     r8, r12
0x180006c41  mov     [rsp+118h+var_B8], r12
0x180006c46  test    rbx, rbx
0x180006c49  jz      short loc_180006C90
0x180006c4b  test    rsi, rsi
0x180006c4e  jz      short loc_180006C90
0x180006c50  movzx   edx, word ptr [rcx]
0x180006c53  test    dx, dx
0x180006c56  jz      short loc_180006C90
0x180006c58  add     rcx, 2
0x180006c5c  mov     [rsp+118h+var_98], rcx
0x180006c64  mov     [rax], dx
0x180006c67  add     rax, 2
0x180006c6b  mov     [rsp+118h+var_C0], rax
0x180006c70  dec     rbx
0x180006c73  mov     [rsp+118h+var_90], rbx
0x180006c7b  dec     rsi
0x180006c7e  mov     [rsp+118h+var_88], rsi
0x180006c86  inc     r8
0x180006c89  mov     [rsp+118h+var_B8], r8
0x180006c8e  jmp     short loc_180006C46
0x180006c90  mov     edi, r12d
0x180006c93  test    rbx, rbx
0x180006c96  jz      loc_180006D8D
0x180006c9c  mov     [rax], r12w
0x180006ca0  mov     [rsp+118h+var_EC], edi
0x180006ca4  mov     [rsp+118h+var_F8], edi
0x180006ca8  test    edi, edi
0x180006caa  jns     loc_180006DBA
0x180006cb0  jmp     loc_180006B6C
0x180006cb5  mov     [rsp+118h+var_F0], r12d
0x180006cba  shr     r14, 1
0x180006cbd  jz      loc_180006F78
0x180006cc3  mov     edi, r12d
0x180006cc6  cmp     r14, 7FFFFFFFh
0x180006ccd  ja      loc_180006F78
0x180006cd3  mov     [rsp+118h+var_F0], edi
0x180006cd7  mov     esi, 7FFFFFFEh
0x180006cdc  test    edi, edi
0x180006cde  js      loc_180006F82
0x180006ce4  mov     r8d, esi
0x180006ce7  mov     [rsp+118h+var_A0], rsi
0x180006cec  mov     [rsp+118h+var_B0], rcx
0x180006cf1  mov     [rsp+118h+var_A8], r14
0x180006cf6  mov     [rsp+118h+var_D0], rax
0x180006cfb  mov     r9, r12
0x180006cfe  mov     [rsp+118h+var_C8], r12
0x180006d03  test    r14, r14
0x180006d06  jz      short loc_180006D44
0x180006d08  test    r8, r8
0x180006d0b  jz      short loc_180006D44
0x180006d0d  movzx   edx, word ptr [rcx]
0x180006d10  test    dx, dx
0x180006d13  jz      short loc_180006D44
0x180006d15  add     rcx, 2
0x180006d19  mov     [rsp+118h+var_B0], rcx
0x180006d1e  mov     [rax], dx
0x180006d21  add     rax, 2
0x180006d25  mov     [rsp+118h+var_D0], rax
0x180006d2a  dec     r14
0x180006d2d  mov     [rsp+118h+var_A8], r14
0x180006d32  dec     r8
0x180006d35  mov     [rsp+118h+var_A0], r8
0x180006d3a  inc     r9
0x180006d3d  mov     [rsp+118h+var_C8], r9
0x180006d42  jmp     short loc_180006D03
0x180006d44  mov     edi, r12d
0x180006d47  test    r14, r14
0x180006d4a  jnz     short loc_180006D62
0x180006d4c  sub     rax, 2
0x180006d50  mov     [rsp+118h+var_D0], rax
0x180006d55  dec     r9
0x180006d58  mov     [rsp+118h+var_C8], r9
0x180006d5d  mov     edi, 8007007Ah
0x180006d62  mov     [rax], r12w
0x180006d66  mov     [rsp+118h+var_F0], edi
0x180006d6a  mov     rdx, [rsp+118h+arg_10]
0x180006d72  mov     [rsp+118h+var_F8], edi
0x180006d76  test    edi, edi
0x180006d78  jns     loc_180006B25
0x180006d7e  jmp     loc_180006B6C
0x180006d83  mov     edi, 80070057h
0x180006d88  jmp     loc_180006C15
0x180006d8d  sub     rax, 2
0x180006d91  mov     [rsp+118h+var_C0], rax
0x180006d96  dec     r8
0x180006d99  mov     [rsp+118h+var_B8], r8
0x180006d9e  mov     edi, 8007007Ah
0x180006da3  jmp     loc_180006C9C
0x180006da8  mov     edi, 80070490h
0x180006dad  mov     [rsp+118h+var_F8], edi
0x180006db1  jmp     loc_180006B6C
0x180006db6  mov     [rax], r12w
0x180006dba  mov     eax, [r9+50h]
0x180006dbe  mov     [r15+24h], eax
0x180006dc2  mov     rax, [rsp+118h+hMem]
0x180006dc7  test    rax, rax
0x180006dca  jz      short loc_180006E24
0x180006dcc  mov     [r15+30h], rax
0x180006dd0  mov     [rsp+118h+hMem], r12
0x180006dd5  mov     rax, [rsp+118h+arg_18]
0x180006ddd  mov     [rax], r15
0x180006de0  mov     r15, r12
0x180006de3  mov     [rsp+118h+var_E8], r12
0x180006de8  mov     rcx, [rsp+118h+var_80]
0x180006df0  call    cs:__imp__set_se_translator
0x180006df7  nop     dword ptr [rax+rax+00h]
0x180006dfc  test    edi, edi
0x180006dfe  js      loc_180006B6C
0x180006e04  mov     edi, r12d
0x180006e07  jmp     loc_180006B6C
0x180006e0c  lea     rcx, CriticalSection; lpCriticalSection
0x180006e13  call    cs:__imp_LeaveCriticalSection
0x180006e1a  nop     dword ptr [rax+rax+00h]
0x180006e1f  jmp     loc_180006B77
0x180006e24  mov     [r15+30h], r12
0x180006e28  jmp     short loc_180006DD5
0x180006e2a  mov     edi, 8007000Eh
0x180006e2f  mov     [rsp+118h+var_F8], edi
0x180006e33  jmp     loc_180006B6C
0x180006e38  mov     r8d, 400h
0x180006e3e  mov     rdx, [r14+8]
0x180006e42  mov     rcx, rsi
0x180006e45  call    cs:__imp__o__wcsnicmp
  ... truncated ...
```
