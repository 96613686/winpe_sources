# CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)

- ea: `0x18007120c`
- end: `0x1800716e4`
- name: `?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z`
- size: `1240`
- prototype: `void __fastcall(CSrmFunctionTracerBase *__hidden this, struct CSrmAutoPWSZ *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180071efc`
- `0x180072598`
- `0x180073080`
- `0x180073a80`
- `0x180073d04`

## callees

- `0x180001350`
- `0x180001948`
- `0x180002018`
- `0x18000af40`
- `0x18000e9ec`
- `0x18000ead4`
- `0x18000ebd4`
- `0x180010b24`
- `0x18001bc58`
- `0x180070bd8`
- `0x18007120c`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_snwscanf_s` at `0x18007139c`
- `msvcrt!_snwscanf_s` at `0x18007139c`
- `ole32!CoTaskMemFree` at `0x180071692`
- `ole32!CoTaskMemFree` at `0x1800716a7`
- `ole32!CoTaskMemFree` at `0x180071692`
- `ole32!CoTaskMemFree` at `0x1800716a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CSrmFunctionTracerBase::GetCurrentContexts(CSrmFunctionTracerBase *this, LPVOID *a2)
{
  CSrmFunctionTracerBase *v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // r8
  __int64 v5; // r13
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r15
  _QWORD *v8; // r12
  __int64 v9; // r14
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  size_t v12; // rdx
  void *StringW; // rax
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // esi
  void **v17; // rcx
  int v18; // edi
  int i; // ebx
  UINT v20; // edx
  __int64 v21; // rax
  const unsigned __int16 *v22; // rdx
  LPVOID *v23; // r14
  LPVOID v24; // rax
  LPVOID v25; // [rsp+30h] [rbp-198h] BYREF
  UINT uID; // [rsp+38h] [rbp-190h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-18Ch]
  int v28; // [rsp+40h] [rbp-188h]
  int v29; // [rsp+44h] [rbp-184h]
  int v30; // [rsp+48h] [rbp-180h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-178h]
  unsigned __int64 v32; // [rsp+58h] [rbp-170h]
  CSrmFunctionTracerBase *v33; // [rsp+60h] [rbp-168h]
  LPVOID *v34; // [rsp+68h] [rbp-160h]
  void *Src[2]; // [rsp+70h] [rbp-158h] BYREF
  __int64 v36; // [rsp+80h] [rbp-148h]
  unsigned __int64 v37; // [rsp+88h] [rbp-140h]
  void *v38[2]; // [rsp+98h] [rbp-130h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-120h]
  unsigned __int64 v40; // [rsp+B0h] [rbp-118h]
  void *Block[3]; // [rsp+C0h] [rbp-108h] BYREF
  unsigned __int64 v42; // [rsp+D8h] [rbp-F0h]
  void *v43[3]; // [rsp+E8h] [rbp-E0h] BYREF
  unsigned __int64 v44; // [rsp+100h] [rbp-C8h]
  _QWORD v45[16]; // [rsp+110h] [rbp-B8h] BYREF

  v34 = a2;
  v2 = this;
  v33 = this;
  v3 = 0;
  v27 = 0;
  v25 = 0;
  CSrmAutoPWSZ::CopyFrom(&v25, &dword_1800DC394);
  try
  {
    `eh vector constructor iterator'(v45, 0x28u, 3u, std::wstring::wstring, (void (*)(void *))std::wstring::~wstring);
    v18 = 0;
    v28 = 0;
    while ( v18 < 3 )
    {
      while ( v2 )
      {
        v4 = v18;
        v5 = 32LL * v18;
        v6 = (*(_QWORD *)((char *)v2 + v5 + 80) - *(_QWORD *)((char *)v2 + v5 + 72)) / 80LL;
        v32 = v6;
        v7 = 0;
        v31 = 0;
        while ( v7 < v6 )
        {
          v8 = &v45[5 * v4];
          std::wstring::append(v8, L"\n   ");
          v9 = 80 * v7;
          v10 = (_QWORD *)(80 * v7 + *((_QWORD *)v2 + 4 * v18 + 9));
          if ( *(_QWORD *)(80 * v7 + *(_QWORD *)((char *)v2 + v5 + 72) + 16) )
          {
            if ( v10[3] >= 8u )
              v10 = (_QWORD *)*v10;
            if ( *(_WORD *)v10 == 31 )
            {
              uID = 0;
              v40 = 7;
              v39 = 0;
              LOWORD(v38[0]) = 0;
              v11 = v9 + *(_QWORD *)((char *)v2 + v5 + 72);
              v12 = *(_QWORD *)(v11 + 16);
              if ( *(_QWORD *)(v11 + 24) >= 8u )
                v11 = *(_QWORD *)v11;
              if ( _snwscanf_s((const wchar_t *const)v11, v12, &word_1800EDA38, &uID) )
              {
                StringW = (void *)CSrmResource::LoadStringW(Block, uID);
                std::wstring::assign(v38, StringW);
                if ( v42 >= 8 )
                  operator delete(Block[0]);
                v42 = 7;
                Block[2] = 0;
                LOWORD(Block[0]) = 0;
              }
              std::wstring::append(v8, v38, 0, -1);
              if ( v40 >= 8 )
                operator delete(v38[0]);
              v40 = 7;
              v39 = 0;
              LOWORD(v38[0]) = 0;
            }
            else
            {
              std::wstring::append(v8, 80 * v7 + *(_QWORD *)((char *)v2 + v5 + 72), 0, -1);
            }
            v15 = *(_QWORD *)((char *)v2 + v5 + 72) + v9;
            v37 = 7;
            v36 = 0;
            LOWORD(Src[0]) = 0;
            v16 = v3 | 1;
            v27 = v16;
            if ( *(_QWORD *)(v15 + 56) != 5 )
            {
              LOBYTE(v14) = 1;
              if ( (unsigned __int8)std::wstring::_Grow(Src, *(_QWORD *)(v15 + 56) + 2LL, v14) )
              {
                v17 = Src;
                if ( v37 >= 8 )
                  v17 = (void **)Src[0];
                v36 = 0;
                *(_WORD *)v17 = 0;
              }
            }
            std::wstring::append(Src, L": ");
            std::wstring::append(Src, v15 + 40, 0, -1);
            std::wstring::append(v8, Src, 0, -1);
            v3 = v16 & 0xFFFFFFFE;
            v27 = v3;
            if ( v37 >= 8 )
              operator delete(Src[0]);
            v37 = 7;
            v36 = 0;
            LOWORD(Src[0]) = 0;
          }
          else
          {
            std::wstring::append(v8, v10 + 5, 0, -1);
          }
          v31 = ++v7;
          v6 = v32;
          v4 = v18;
        }
        v2 = (CSrmFunctionTracerBase *)*((_QWORD *)v2 + 21);
      }
      v28 = ++v18;
      v2 = v33;
    }
    for ( i = 0; ; ++i )
    {
      v29 = i;
      if ( i >= 3 )
        break;
      if ( v45[5 * i + 2] )
      {
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v25, L"\n\n");
        if ( i )
        {
          if ( i == 1 )
            v20 = 1003;
          else
            v20 = 1004;
        }
        else
        {
          v20 = 1002;
        }
        v21 = CSrmResource::LoadStringW(v43, v20);
        if ( *(_QWORD *)(v21 + 24) >= 8u )
          v21 = *(_QWORD *)v21;
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v25, (const unsigned __int16 *)v21);
        if ( v44 >= 8 )
          operator delete(v43[0]);
        v44 = 7;
        v43[2] = 0;
        LOWORD(v43[0]) = 0;
        v22 = (const unsigned __int16 *)&v45[5 * i];
        if ( *((_QWORD *)v22 + 3) >= 8u )
          v22 = *(const unsigned __int16 **)v22;
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v25, v22);
      }
    }
  }
  catch ( std::bad_alloc )
  {
    v30 = -2147024882;
    throw (long *)&v30;
  }
  `eh vector destructor iterator'(v45, 0x28u, 3u, (void (*)(void *))std::wstring::~wstring);
  v23 = v34;
  CoTaskMemFree(*v34);
  v24 = v25;
  v25 = 0;
  *v23 = v24;
  CoTaskMemFree(0);
  v25 = 0;
}

```

## disassembly

```asm
0x18007120c  mov     [rsp+arg_10], rbx
0x180071211  mov     [rsp+arg_18], rsi
0x180071216  push    rdi
0x180071217  push    r12
0x180071219  push    r13
0x18007121b  push    r14
0x18007121d  push    r15
0x18007121f  sub     rsp, 1A0h
0x180071226  mov     rax, cs:__security_cookie
0x18007122d  xor     rax, rsp
0x180071230  mov     [rsp+1C8h+var_38], rax
0x180071238  mov     [rsp+1C8h+var_160], rdx
0x18007123d  mov     rbx, rcx
0x180071240  mov     [rsp+1C8h+var_168], rcx
0x180071245  xor     r12d, r12d
0x180071248  mov     esi, r12d
0x18007124b  mov     [rsp+1C8h+var_18C], r12d
0x180071250  mov     [rsp+1C8h+var_198], r12
0x180071255  lea     rdx, dword_1800DC394; unsigned __int16 *
0x18007125c  lea     rcx, [rsp+1C8h+var_198]; this
0x180071261  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x180071266  nop
0x180071267  lea     r14, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007126e  mov     [rsp+1C8h+var_1A8], r14; void (*)(void *)
0x180071273  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18007127a  lea     edx, [r12+28h]; unsigned __int64
0x18007127f  lea     r8d, [r12+3]; unsigned __int64
0x180071284  lea     rcx, [rsp+1C8h+var_B8]; void *
0x18007128c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180071291  nop
0x180071292  mov     edi, r12d
0x180071295  mov     [rsp+1C8h+var_188], r12d
0x18007129a  cmp     edi, 3
0x18007129d  jge     loc_180071594
0x1800712a3  test    rbx, rbx
0x1800712a6  jz      loc_180071584
0x1800712ac  movsxd  r8, edi
0x1800712af  mov     r13, r8
0x1800712b2  shl     r13, 5
0x1800712b6  mov     rcx, [rbx+r13+50h]
0x1800712bb  sub     rcx, [rbx+r13+48h]
0x1800712c0  mov     rax, 6666666666666667h
0x1800712ca  imul    rcx
0x1800712cd  mov     rcx, rdx
0x1800712d0  sar     rcx, 5
0x1800712d4  mov     rax, rcx
0x1800712d7  shr     rax, 3Fh
0x1800712db  add     rcx, rax
0x1800712de  mov     [rsp+1C8h+var_170], rcx
0x1800712e3  mov     r15, r12
0x1800712e6  mov     [rsp+1C8h+var_178], r12
0x1800712eb  cmp     r15, rcx
0x1800712ee  jnb     loc_180071578
0x1800712f4  lea     rax, [r8+r8*4]
0x1800712f8  lea     r12, [rsp+1C8h+var_B8]
0x180071300  lea     r12, [r12+rax*8]
0x180071304  lea     rdx, asc_1800ECE30; "\n   "
0x18007130b  mov     rcx, r12; Src
0x18007130e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180071313  lea     r14, [r15+r15*4]
0x180071317  shl     r14, 4
0x18007131b  mov     r10, [rbx+r13+48h]
0x180071320  add     r10, r14
0x180071323  lea     rcx, [r15+r15*4]
0x180071327  shl     rcx, 4
0x18007132b  movsxd  rax, edi
0x18007132e  shl     rax, 5
0x180071332  mov     rdx, [rax+rbx+48h]
0x180071337  add     rdx, rcx
0x18007133a  xor     eax, eax
0x18007133c  cmp     [r10+10h], rax
0x180071340  jbe     loc_18007154D
0x180071346  cmp     qword ptr [rdx+18h], 8
0x18007134b  jb      short loc_180071350
0x18007134d  mov     rdx, [rdx]
0x180071350  cmp     word ptr [rdx], 1Fh
0x180071354  jnz     loc_180071457
0x18007135a  mov     [rsp+1C8h+uID], eax
0x18007135e  mov     [rsp+1C8h+var_118], 7
0x18007136a  mov     [rsp+1C8h+var_120], rax
0x180071372  mov     word ptr [rsp+1C8h+var_130], ax
0x18007137a  mov     rcx, [rbx+r13+48h]
0x18007137f  add     rcx, r14
0x180071382  mov     rdx, [rcx+10h]; BufferCount
0x180071386  cmp     qword ptr [rcx+18h], 8
0x18007138b  jb      short loc_180071390
0x18007138d  mov     rcx, [rcx]; Buffer
0x180071390  lea     r9, [rsp+1C8h+uID]
0x180071395  lea     r8, word_1800EDA38; Format
0x18007139c  call    cs:__imp__snwscanf_s
0x1800713a2  test    eax, eax
0x1800713a4  jz      short loc_180071403
0x1800713a6  mov     edx, [rsp+1C8h+uID]; uID
0x1800713aa  lea     rcx, [rsp+1C8h+Block]; void *
0x1800713b2  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x1800713b7  nop
0x1800713b8  mov     rdx, rax; Src
0x1800713bb  lea     rcx, [rsp+1C8h+var_130]; void *
0x1800713c3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x1800713c8  nop
0x1800713c9  cmp     [rsp+1C8h+var_F0], 8
0x1800713d2  jb      short loc_1800713E1
0x1800713d4  mov     rcx, [rsp+1C8h+Block]; Block
0x1800713dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800713e1  mov     [rsp+1C8h+var_F0], 7
0x1800713ed  mov     [rsp+1C8h+var_F8], 0
0x1800713f9  xor     eax, eax
0x1800713fb  mov     word ptr [rsp+1C8h+Block], ax
0x180071403  or      r9, 0FFFFFFFFFFFFFFFFh
0x180071407  xor     r8d, r8d
0x18007140a  lea     rdx, [rsp+1C8h+var_130]
0x180071412  mov     rcx, r12
0x180071415  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18007141a  nop
0x18007141b  cmp     [rsp+1C8h+var_118], 8
0x180071424  jb      short loc_180071433
0x180071426  mov     rcx, [rsp+1C8h+var_130]; Block
0x18007142e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180071433  mov     [rsp+1C8h+var_118], 7
0x18007143f  mov     [rsp+1C8h+var_120], 0
0x18007144b  xor     eax, eax
0x18007144d  mov     word ptr [rsp+1C8h+var_130], ax
0x180071455  jmp     short loc_180071469
0x180071457  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007145b  xor     r8d, r8d
0x18007145e  mov     rdx, r10
0x180071461  mov     rcx, r12
0x180071464  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180071469  add     r14, [rbx+r13+48h]
0x18007146e  mov     [rsp+1C8h+var_140], 7
0x18007147a  mov     [rsp+1C8h+var_148], 0
0x180071486  xor     eax, eax
0x180071488  mov     word ptr [rsp+1C8h+Src], ax
0x18007148d  or      esi, 1
0x180071490  mov     [rsp+1C8h+var_18C], esi
0x180071494  mov     rdx, [r14+38h]
0x180071498  add     rdx, 2
0x18007149c  cmp     rdx, 7
0x1800714a0  jz      short loc_1800714D8
0x1800714a2  mov     r8b, 1
0x1800714a5  lea     rcx, [rsp+1C8h+Src]
0x1800714aa  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800714af  test    al, al
0x1800714b1  jz      short loc_1800714D8
0x1800714b3  lea     rcx, [rsp+1C8h+Src]
0x1800714b8  cmp     [rsp+1C8h+var_140], 8
0x1800714c1  cmovnb  rcx, [rsp+1C8h+Src]
0x1800714c7  mov     [rsp+1C8h+var_148], 0
0x1800714d3  xor     eax, eax
0x1800714d5  mov     [rcx], ax
0x1800714d8  lea     rdx, asc_1800ECE58; ": "
0x1800714df  lea     rcx, [rsp+1C8h+Src]; Src
0x1800714e4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800714e9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800714ed  xor     r8d, r8d
0x1800714f0  lea     rdx, [r14+28h]
0x1800714f4  lea     rcx, [rsp+1C8h+Src]
0x1800714f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800714fe  or      r9, 0FFFFFFFFFFFFFFFFh
0x180071502  xor     r8d, r8d
0x180071505  lea     rdx, [rsp+1C8h+Src]
0x18007150a  mov     rcx, r12
0x18007150d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180071512  and     esi, 0FFFFFFFEh
0x180071515  mov     [rsp+1C8h+var_18C], esi
0x180071519  cmp     [rsp+1C8h+var_140], 8
0x180071522  jb      short loc_18007152E
0x180071524  mov     rcx, [rsp+1C8h+Src]; Block
0x180071529  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007152e  mov     [rsp+1C8h+var_140], 7
0x18007153a  xor     r12d, r12d
0x18007153d  mov     [rsp+1C8h+var_148], r12
0x180071545  mov     word ptr [rsp+1C8h+Src], r12w
0x18007154b  jmp     short loc_180071563
0x18007154d  add     rdx, 28h ; '('
0x180071551  or      r9, 0FFFFFFFFFFFFFFFFh
0x180071555  xor     r8d, r8d
0x180071558  mov     rcx, r12
0x18007155b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180071560  xor     r12d, r12d
0x180071563  inc     r15
0x180071566  mov     [rsp+1C8h+var_178], r15
0x18007156b  mov     rcx, [rsp+1C8h+var_170]
0x180071570  movsxd  r8, edi
0x180071573  jmp     loc_1800712EB
0x180071578  mov     rbx, [rbx+0A8h]
0x18007157f  jmp     loc_1800712A3
0x180071584  inc     edi
0x180071586  mov     [rsp+1C8h+var_188], edi
0x18007158a  mov     rbx, [rsp+1C8h+var_168]
0x18007158f  jmp     loc_18007129A
0x180071594  mov     ebx, r12d
0x180071597  mov     esi, 3ECh
0x18007159c  mov     [rsp+1C8h+var_184], ebx
0x1800715a0  cmp     ebx, 3
0x1800715a3  jge     loc_18007166C
0x1800715a9  movsxd  rax, ebx
0x1800715ac  lea     rdi, [rax+rax*4]
0x1800715b0  cmp     [rsp+rdi*8+1C8h+var_A8], r12
0x1800715b8  jbe     loc_180071665
0x1800715be  lea     rdx, asc_1800ECE50; "\n\n"
0x1800715c5  lea     rcx, [rsp+1C8h+var_198]; this
0x1800715ca  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x1800715cf  mov     ecx, ebx
0x1800715d1  test    ebx, ebx
0x1800715d3  jz      short loc_1800715E5
0x1800715d5  sub     ecx, 1
0x1800715d8  jz      short loc_1800715DE
0x1800715da  mov     edx, esi
0x1800715dc  jmp     short loc_1800715EA
0x1800715de  mov     edx, 3EBh
0x1800715e3  jmp     short loc_1800715EA
0x1800715e5  mov     edx, 3EAh; uID
0x1800715ea  lea     rcx, [rsp+1C8h+var_E0]; void *
0x1800715f2  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x1800715f7  nop
0x1800715f8  cmp     qword ptr [rax+18h], 8
0x1800715fd  jb      short loc_180071602
0x1800715ff  mov     rax, [rax]
0x180071602  mov     rdx, rax; unsigned __int16 *
0x180071605  lea     rcx, [rsp+1C8h+var_198]; this
0x18007160a  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x18007160f  nop
0x180071610  cmp     [rsp+1C8h+var_C8], 8
0x180071619  jb      short loc_180071628
0x18007161b  mov     rcx, [rsp+1C8h+var_E0]; Block
0x180071623  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180071628  mov     [rsp+1C8h+var_C8], 7
0x180071634  mov     [rsp+1C8h+var_D0], r12
0x18007163c  mov     word ptr [rsp+1C8h+var_E0], r12w
0x180071645  lea     rdx, [rsp+1C8h+var_B8]
0x18007164d  lea     rdx, [rdx+rdi*8]
0x180071651  cmp     qword ptr [rdx+18h], 8
0x180071656  jb      short loc_18007165B
0x180071658  mov     rdx, [rdx]; unsigned __int16 *
0x18007165b  lea     rcx, [rsp+1C8h+var_198]; this
0x180071660  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x180071665  inc     ebx
0x180071667  jmp     loc_18007159C
0x18007166c  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180071673  mov     edx, 28h ; '('; unsigned __int64
0x180071678  lea     r8d, [rdx-25h]; unsigned __int64
0x18007167c  lea     rcx, [rsp+1C8h+var_B8]; void *
0x180071684  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180071689  nop
0x18007168a  mov     r14, [rsp+1C8h+var_160]
0x18007168f  mov     rcx, [r14]; pv
0x180071692  call    cs:__imp_CoTaskMemFree
0x180071698  mov     rax, [rsp+1C8h+var_198]
0x18007169d  mov     [rsp+1C8h+var_198], r12
0x1800716a2  mov     [r14], rax
0x1800716a5  xor     ecx, ecx; pv
0x1800716a7  call    cs:__imp_CoTaskMemFree
0x1800716ad  mov     [rsp+1C8h+var_198], r12
0x1800716b2  mov     [rsp+1C8h+var_198], r12
0x1800716b7  mov     rcx, [rsp+1C8h+var_38]
0x1800716bf  xor     rcx, rsp; StackCookie
0x1800716c2  call    __security_check_cookie
0x1800716c7  lea     r11, [rsp+1C8h+var_28]
0x1800716cf  mov     rbx, [r11+40h]
0x1800716d3  mov     rsi, [r11+48h]
0x1800716d7  mov     rsp, r11
0x1800716da  pop     r15
0x1800716dc  pop     r14
0x1800716de  pop     r13
0x1800716e0  pop     r12
0x1800716e2  pop     rdi
0x1800716e3  retn
```
