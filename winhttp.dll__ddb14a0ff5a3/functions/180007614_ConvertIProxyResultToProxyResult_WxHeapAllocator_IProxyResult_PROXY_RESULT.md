# ConvertIProxyResultToProxyResult<WxHeapAllocator>(IProxyResult *,_PROXY_RESULT *)

- ea: `0x180007614`
- end: `0x180007a77`
- name: `??$ConvertIProxyResultToProxyResult@VWxHeapAllocator@@@@YAJPEAUIProxyResult@@PEAU_PROXY_RESULT@@@Z`
- size: `1123`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005770`
- `0x1800be2f0`

## callees

- `0x180007614`
- `0x1800081a0`
- `0x18001b480`
- `0x180069488`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c7cac`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007936`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007834`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800077fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007834`

## pseudocode

```c
__int64 __fastcall ConvertIProxyResultToProxyResult<WxHeapAllocator>(__int64 a1, _OWORD *a2)
{
  __int64 v2; // rbx
  __int128 v3; // xmm6
  __int64 v5; // r15
  _BYTE *v6; // rax
  unsigned int v7; // r12d
  char *Heap; // rax
  char *v9; // rsi
  unsigned int v10; // r14d
  int v11; // edi
  void *v12; // rcx
  int v13; // eax
  int v14; // edi
  int v15; // eax
  int v16; // ecx
  void *v17; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int i; // r15d
  char *v22; // r13
  int v23; // eax
  char *v24; // rax
  __int64 v25; // [rsp+40h] [rbp-51h] BYREF
  __int128 v26; // [rsp+48h] [rbp-49h]
  HANDLE hObject[2]; // [rsp+58h] [rbp-39h]
  __int16 v28[2]; // [rsp+68h] [rbp-29h] BYREF
  int v29; // [rsp+6Ch] [rbp-25h] BYREF
  int v30; // [rsp+70h] [rbp-21h] BYREF
  int v31; // [rsp+74h] [rbp-1Dh] BYREF
  LPVOID pv; // [rsp+78h] [rbp-19h] BYREF
  int v33; // [rsp+80h] [rbp-11h] BYREF
  __int64 v34; // [rsp+88h] [rbp-9h] BYREF
  int v35; // [rsp+90h] [rbp-1h] BYREF

  v2 = 0;
  v29 = 0;
  v30 = 0;
  v3 = 0;
  v35 = 0;
  v31 = 0;
  v5 = a1;
  v28[0] = 0;
  pv = 0;
  v25 = 0;
  v34 = 0;
  v33 = 0;
  v26 = 0;
  *(_OWORD *)hObject = 0;
  if ( a2 )
  {
    a1 = 32;
    v6 = a2;
    do
    {
      *v6++ = 0;
      --a1;
    }
    while ( a1 );
  }
  if ( !v5 || !a2 )
  {
    v14 = -2147024809;
    goto LABEL_36;
  }
  v7 = 320;
  Heap = (char *)WxAllocateHeapEx(a1, 320);
  v9 = Heap;
  if ( !Heap )
  {
    v14 = -2147024882;
LABEL_36:
    v9 = (char *)*((_QWORD *)&v26 + 1);
    v10 = v26;
    goto LABEL_20;
  }
  memset_0(Heap, 0, 0x140u);
  *((_QWORD *)&v26 + 1) = v9;
  v10 = v26;
  v11 = 0;
  while ( 1 )
  {
    v12 = pv;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v28[0] = 0;
    if ( pv )
    {
      pv = 0;
      CoTaskMemFree(v12);
    }
    if ( v10 == v7 >> 5 )
    {
      v7 += 320;
      v24 = (char *)WxHeapAllocator::ReAllocEx((unsigned int)v12, v7, v9);
      if ( !v24 )
      {
        v14 = -2147024882;
        goto LABEL_20;
      }
      v9 = v24;
      *((_QWORD *)&v26 + 1) = v24;
    }
    if ( v11 )
      break;
LABEL_31:
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 24LL))(v5, &v29);
    if ( v14 < 0 )
      goto LABEL_20;
    v19 = *(_QWORD *)v5;
    if ( v29 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *, __int16 *))(v19 + 48))(v5, &v31, &pv, v28);
      if ( v14 < 0 )
        goto LABEL_20;
      v23 = WxNewStringW<WxHeapAllocator>(pv, &v25);
      v2 = v25;
      v14 = v23;
      if ( v23 < 0 )
        goto LABEL_20;
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(__int64, int *, int *))(v19 + 32))(v5, &v35, &v30);
      if ( v14 < 0 )
        goto LABEL_20;
    }
    v11 = 1;
    v20 = 32LL * v10;
    *(_DWORD *)&v9[v20] = v29;
    *(_DWORD *)&v9[v20 + 4] = v30;
    *(_DWORD *)&v9[v20 + 8] = v31;
    *(_WORD *)&v9[v20 + 24] = v28[0];
    *(_QWORD *)&v9[v20 + 16] = v2;
    v2 = 0;
    ++v10;
    v25 = 0;
    LODWORD(v26) = v10;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 40LL))(v5);
  v14 = v13;
  if ( v13 != -2147023728 )
  {
    if ( v13 < 0 )
      goto LABEL_20;
    goto LABEL_31;
  }
  v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &IID_ICmProxyResult, &v34);
  if ( v14 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 96LL))(v34, &v33);
    if ( v14 < 0 )
      goto LABEL_20;
    LODWORD(hObject[1]) = v33;
    v3 = *(_OWORD *)hObject;
  }
  v15 = 0;
  v16 = v14;
  if ( v14 == -2147467262 )
    v14 = 0;
  if ( v16 != -2147467262 )
    v15 = v16;
  if ( v15 >= 0 )
  {
    *a2 = v26;
    v10 = _mm_cvtsi128_si32((__m128i)0LL);
    v9 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    a2[1] = v3;
    *(_OWORD *)hObject = 0;
  }
LABEL_20:
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( v9 )
  {
    for ( i = 0; i < v10; ++i )
    {
      v22 = &v9[32 * i];
      if ( v22 )
      {
        WxFreeHeapEx(v22 + 16);
        *(_OWORD *)v22 = 0;
        *((_OWORD *)v22 + 1) = 0;
      }
    }
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v9);
    else
      HeapFree(g_hWxProcessHeap, 0, v9);
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v2 )
    WxFreeHeapEx(&v25);
  v17 = pv;
  if ( pv )
  {
    pv = 0;
    CoTaskMemFree(v17);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180007614  mov     rax, rsp
0x180007617  mov     [rax+18h], rbx
0x18000761b  push    rbp
0x18000761c  push    rsi
0x18000761d  push    rdi
0x18000761e  push    r12
0x180007620  push    r13
0x180007622  push    r14
0x180007624  push    r15
0x180007626  lea     rbp, [rax-5Fh]
0x18000762a  sub     rsp, 0B0h
0x180007631  movaps  xmmword ptr [rax-48h], xmm6
0x180007635  mov     rax, cs:__security_cookie
0x18000763c  xor     rax, rsp
0x18000763f  mov     [rbp+57h+var_50], rax
0x180007643  xor     eax, eax
0x180007645  mov     [rbp+57h+var_AC], 0
0x18000764c  xor     ebx, ebx
0x18000764e  mov     [rbp+57h+var_7C], 0
0x180007655  mov     [rbp+57h+var_78], 0
0x18000765c  xorps   xmm6, xmm6
0x18000765f  mov     [rbp+57h+var_58], 0
0x180007666  mov     r13, rdx
0x180007669  mov     [rbp+57h+var_74], 0
0x180007670  mov     r15, rcx
0x180007673  mov     [rbp+57h+var_80], ax
0x180007677  mov     [rbp+57h+pv], rax
0x18000767b  mov     [rbp+57h+var_A8], rbx
0x18000767f  mov     [rbp+57h+var_60], rax
0x180007683  mov     [rbp+57h+var_68], eax
0x180007686  movups  [rbp+57h+var_A0], xmm6
0x18000768a  movups  xmmword ptr [rbp+57h+hObject], xmm6
0x18000768e  test    rdx, rdx
0x180007691  jz      short loc_1800076A4
0x180007693  lea     ecx, [rax+20h]
0x180007696  mov     rax, rdx
0x180007699  mov     [rax], bl
0x18000769b  inc     rax
0x18000769e  sub     rcx, 1
0x1800076a2  jnz     short loc_180007699
0x1800076a4  test    r15, r15
0x1800076a7  jz      loc_180007997
0x1800076ad  test    r13, r13
0x1800076b0  jz      loc_18000797A
0x1800076b6  mov     r12d, 140h
0x1800076bc  mov     [rbp+57h+var_AC], ebx
0x1800076bf  mov     edx, r12d
0x1800076c2  call    WxAllocateHeapEx
0x1800076c7  mov     rsi, rax
0x1800076ca  test    rax, rax
0x1800076cd  jz      loc_1800078CF
0x1800076d3  mov     r8d, r12d; Size
0x1800076d6  xor     edx, edx; Val
0x1800076d8  mov     rcx, rax; void *
0x1800076db  call    memset_0
0x1800076e0  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x1800076e4  mov     r14d, dword ptr [rbp+57h+var_A0]
0x1800076e8  xor     edi, edi
0x1800076ea  mov     rcx, [rbp+57h+pv]; unsigned int
0x1800076ee  xor     eax, eax
0x1800076f0  mov     [rbp+57h+var_7C], 0
0x1800076f7  mov     [rbp+57h+var_78], 0
0x1800076fe  mov     [rbp+57h+var_74], 0
0x180007705  mov     [rbp+57h+var_80], ax
0x180007709  test    rcx, rcx
0x18000770c  jnz     loc_180007830
0x180007712  mov     eax, r12d
0x180007715  shr     eax, 5
0x180007718  cmp     r14d, eax
0x18000771b  jz      loc_180007A06
0x180007721  test    edi, edi
0x180007723  jz      loc_180007847
0x180007729  mov     rax, [r15]
0x18000772c  mov     rcx, r15
0x18000772f  mov     rax, [rax+28h]
0x180007733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007738  mov     edi, eax
0x18000773a  cmp     eax, 80070490h
0x18000773f  jnz     loc_18000783F
0x180007745  mov     rax, [r15]
0x180007748  lea     r8, [rbp+57h+var_60]
0x18000774c  lea     rdx, IID_ICmProxyResult
0x180007753  mov     rcx, r15
0x180007756  mov     rax, [rax]
0x180007759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775e  mov     edi, eax
0x180007760  test    eax, eax
0x180007762  jns     loc_18000794D
0x180007768  xor     eax, eax
0x18000776a  mov     ecx, edi
0x18000776c  mov     edx, 80004002h
0x180007771  cmp     edi, edx
0x180007773  cmovz   edi, eax
0x180007776  cmp     ecx, edx
0x180007778  cmovnz  eax, ecx
0x18000777b  test    eax, eax
0x18000777d  js      loc_180007A54
0x180007783  movups  xmm0, [rbp+57h+var_A0]
0x180007787  xorps   xmm1, xmm1
0x18000778a  movups  xmmword ptr [r13+0], xmm0
0x18000778f  xorps   xmm0, xmm0
0x180007792  movd    r14d, xmm1
0x180007797  psrldq  xmm0, 8
0x18000779c  movq    rsi, xmm0
0x1800077a1  movups  xmmword ptr [r13+10h], xmm6
0x1800077a6  movups  xmmword ptr [rbp+57h+hObject], xmm1
0x1800077aa  mov     rcx, [rbp+57h+hObject]; hObject
0x1800077ae  test    rcx, rcx
0x1800077b1  jnz     loc_180007A6C
0x1800077b7  test    rsi, rsi
0x1800077ba  jnz     loc_1800078EF
0x1800077c0  mov     rcx, [rbp+57h+var_60]
0x1800077c4  test    rcx, rcx
0x1800077c7  jz      short loc_1800077DD
0x1800077c9  mov     rax, [rcx]
0x1800077cc  mov     rax, [rax+10h]
0x1800077d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d5  mov     [rbp+57h+var_60], 0
0x1800077dd  test    rbx, rbx
0x1800077e0  jz      short loc_1800077EB
0x1800077e2  lea     rcx, [rbp+57h+var_A8]
0x1800077e6  call    WxFreeHeapEx
0x1800077eb  mov     rcx, [rbp+57h+pv]; pv
0x1800077ef  test    rcx, rcx
0x1800077f2  jz      short loc_180007802
0x1800077f4  mov     [rbp+57h+pv], 0
0x1800077fc  call    cs:__imp_CoTaskMemFree
0x180007802  mov     eax, edi
0x180007804  mov     rcx, [rbp+57h+var_50]
0x180007808  xor     rcx, rsp; StackCookie
0x18000780b  call    __security_check_cookie
0x180007810  lea     r11, [rsp+0E0h+var_30]
0x180007818  mov     rbx, [r11+50h]
0x18000781c  movaps  xmm6, xmmword ptr [r11-10h]
0x180007821  mov     rsp, r11
0x180007824  pop     r15
0x180007826  pop     r14
0x180007828  pop     r13
0x18000782a  pop     r12
0x18000782c  pop     rdi
0x18000782d  pop     rsi
0x18000782e  pop     rbp
0x18000782f  retn
0x180007830  mov     [rbp+57h+pv], rax
0x180007834  call    cs:__imp_CoTaskMemFree
0x18000783a  jmp     loc_180007712
0x18000783f  test    eax, eax
0x180007841  js      loc_180007A48
0x180007847  mov     rax, [r15]
0x18000784a  lea     rdx, [rbp+57h+var_7C]
0x18000784e  mov     rcx, r15
0x180007851  mov     rax, [rax+18h]
0x180007855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785a  mov     edi, eax
0x18000785c  test    eax, eax
0x18000785e  js      loc_180007941
0x180007864  cmp     [rbp+57h+var_7C], 0
0x180007868  mov     rcx, r15
0x18000786b  mov     rax, [r15]
0x18000786e  jnz     loc_1800079B4
0x180007874  mov     rax, [rax+20h]
0x180007878  lea     r8, [rbp+57h+var_78]
0x18000787c  lea     rdx, [rbp+57h+var_58]
0x180007880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007885  mov     edi, eax
0x180007887  test    eax, eax
0x180007889  js      loc_18000798B
0x18000788f  mov     eax, [rbp+57h+var_7C]
0x180007892  mov     edi, 1
0x180007897  mov     ecx, r14d
0x18000789a  shl     rcx, 5
0x18000789e  mov     [rcx+rsi], eax
0x1800078a1  mov     eax, [rbp+57h+var_78]
0x1800078a4  mov     [rcx+rsi+4], eax
0x1800078a8  mov     eax, [rbp+57h+var_74]
0x1800078ab  mov     [rcx+rsi+8], eax
0x1800078af  movzx   eax, [rbp+57h+var_80]
0x1800078b3  mov     [rcx+rsi+18h], ax
0x1800078b8  mov     [rcx+rsi+10h], rbx
0x1800078bd  xor     ebx, ebx
0x1800078bf  inc     r14d
0x1800078c2  mov     [rbp+57h+var_A8], rbx
0x1800078c6  mov     dword ptr [rbp+57h+var_A0], r14d
0x1800078ca  jmp     loc_1800076EA
0x1800078cf  mov     [rbp+57h+var_AC], 4Ch ; 'L'
0x1800078d6  mov     edi, 8007000Eh
0x1800078db  mov     [rbp+57h+var_AC], 362h
0x1800078e2  mov     rsi, qword ptr [rbp+57h+var_A0+8]
0x1800078e6  mov     r14d, dword ptr [rbp+57h+var_A0]
0x1800078ea  jmp     loc_1800077AA
0x1800078ef  xor     r15d, r15d
0x1800078f2  test    r14d, r14d
0x1800078f5  jz      short loc_180007921
0x1800078f7  mov     r13d, r15d
0x1800078fa  shl     r13, 5
0x1800078fe  add     r13, rsi
0x180007901  jz      short loc_180007919
0x180007903  lea     rcx, [r13+10h]
0x180007907  call    WxFreeHeapEx
0x18000790c  xorps   xmm0, xmm0
0x18000790f  movups  xmmword ptr [r13+0], xmm0
0x180007914  movups  xmmword ptr [r13+10h], xmm0
0x180007919  inc     r15d
0x18000791c  cmp     r15d, r14d
0x18000791f  jb      short loc_1800078F7
0x180007921  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180007928  jnz     short loc_1800079A0
0x18000792a  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180007931  mov     r8, rsi; lpMem
0x180007934  xor     edx, edx; dwFlags
0x180007936  call    cs:__imp_HeapFree
0x18000793c  jmp     loc_1800077C0
0x180007941  mov     [rbp+57h+var_AC], 383h
0x180007948  jmp     loc_1800077AA
0x18000794d  mov     rcx, [rbp+57h+var_60]
0x180007951  lea     rdx, [rbp+57h+var_68]
0x180007955  mov     rax, [rcx]
0x180007958  mov     rax, [rax+60h]
0x18000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007961  mov     edi, eax
0x180007963  test    eax, eax
0x180007965  js      loc_1800079FA
0x18000796b  mov     eax, [rbp+57h+var_68]
0x18000796e  mov     dword ptr [rbp+57h+hObject+8], eax
0x180007971  movups  xmm6, xmmword ptr [rbp+57h+hObject]
0x180007975  jmp     loc_180007768
0x18000797a  mov     [rbp+57h+var_AC], 35Eh
0x180007981  mov     edi, 80070057h
0x180007986  jmp     loc_1800078E2
0x18000798b  mov     [rbp+57h+var_AC], 391h
0x180007992  jmp     loc_1800077AA
0x180007997  mov     [rbp+57h+var_AC], 35Dh
0x18000799e  jmp     short loc_180007981
0x1800079a0  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x1800079a7  mov     rcx, rsi
0x1800079aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079af  jmp     loc_1800077C0
0x1800079b4  mov     rax, [rax+30h]
0x1800079b8  lea     r9, [rbp+57h+var_80]
0x1800079bc  lea     r8, [rbp+57h+pv]
0x1800079c0  lea     rdx, [rbp+57h+var_74]
0x1800079c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c9  mov     edi, eax
0x1800079cb  test    eax, eax
0x1800079cd  js      loc_180007A60
0x1800079d3  mov     rcx, [rbp+57h+pv]
0x1800079d7  lea     rdx, [rbp+57h+var_A8]
0x1800079db  call    ??$WxNewStringW@VWxHeapAllocator@@@@YAJPEBGPEAPEAG@Z; WxNewStringW<WxHeapAllocator>(ushort const *,ushort * *)
0x1800079e0  mov     rbx, [rbp+57h+var_A8]
0x1800079e4  mov     edi, eax
0x1800079e6  test    eax, eax
0x1800079e8  jns     loc_18000788F
0x1800079ee  mov     [rbp+57h+var_AC], 38Bh
0x1800079f5  jmp     loc_1800077AA
0x1800079fa  mov     [rbp+57h+var_AC], 3A2h
0x180007a01  jmp     loc_1800077AA
0x180007a06  add     r12d, 140h
0x180007a0d  mov     [rbp+57h+var_AC], 0
0x180007a14  mov     edx, r12d; unsigned int
0x180007a17  mov     r8, rsi; void *
0x180007a1a  call    ?ReAllocEx@WxHeapAllocator@@SAPEAXKKPEAX@Z; WxHeapAllocator::ReAllocEx(ulong,ulong,void *)
0x180007a1f  test    rax, rax
0x180007a22  jz      short loc_180007A30
0x180007a24  mov     rsi, rax
0x180007a27  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180007a2b  jmp     loc_180007721
0x180007a30  mov     [rbp+57h+var_AC], 7Eh ; '~'
0x180007a37  mov     edi, 8007000Eh
0x180007a3c  mov     [rbp+57h+var_AC], 371h
0x180007a43  jmp     loc_1800077AA
0x180007a48  mov     [rbp+57h+var_AC], 37Eh
0x180007a4f  jmp     loc_1800077AA
0x180007a54  mov     [rbp+57h+var_AC], 3AAh
0x180007a5b  jmp     loc_1800077AA
0x180007a60  mov     [rbp+57h+var_AC], 389h
0x180007a67  jmp     loc_1800077AA
0x180007a6c  call    cs:__imp_CloseHandle
0x180007a72  jmp     loc_1800077B7
```
