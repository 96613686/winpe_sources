# CVRoots::RemoveVRoot(ushort *)

- ea: `0x180029468`
- end: `0x180029739`
- name: `?RemoveVRoot@CVRoots@@QEAAHPEAG@Z`
- size: `721`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051634`

## callees

- `0x18001197c`
- `0x180018a4c`
- `0x1800200f4`
- `0x180029468`
- `0x180029740`
- `0x180047be4`
- `0x180051c2c`
- `0x1800520d0`
- `0x18005220c`
- `0x180057cb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180029500`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180029500`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002955d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002955d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002954e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002954e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800296e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800296e6`

## string_xrefs

- `0x180029718`: `CVRoots::RemoveVRoot`

## pseudocode

```c
__int64 __fastcall CVRoots::RemoveVRoot(LPCRITICAL_SECTION lpCriticalSection, LPCWCH lpWideCharStr)
{
  char *v4; // rax
  char *v5; // rbp
  __int64 v6; // rsi
  int i; // r14d
  __int64 v8; // rdx
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // r15
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rdx
  char v16; // al
  int j; // edi
  __int64 v18; // rsi
  __int64 v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  int v22; // eax
  int v23; // edi
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v4 = SzFromWsz(lpWideCharStr);
  v5 = v4;
  if ( v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    if ( *(_QWORD *)&lpCriticalSection[1].LockCount )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= SLODWORD(lpCriticalSection[1].DebugInfo) )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids, v5);
          }
          goto LABEL_16;
        }
        v8 = *(_QWORD *)&lpCriticalSection[1].LockCount;
        v9 = 56LL * i;
        v10 = *(_DWORD *)(v8 + v9);
        if ( *(_DWORD *)(v8 + v9 + 40) && v10 != 1 )
          --v10;
        if ( v10 )
        {
          if ( (int)v6 >= v10 )
          {
            v11 = v10;
            if ( !(unsigned int)_o__memicmp(v5, *(_QWORD *)(v8 + v9 + 8), v10) )
            {
              v13 = *(_QWORD *)&lpCriticalSection[1].LockCount;
              if ( !*(_DWORD *)(v13 + v9 + 40) )
                break;
              if ( *(_DWORD *)(v13 + 56LL * i) == 1 )
                break;
              v16 = v5[v11];
              if ( v16 == 47 || !v16 )
                break;
            }
          }
        }
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_ssSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v12,
          (_DWORD)v5,
          *(_QWORD *)(v13 + v9 + 8),
          *(_QWORD *)(v13 + v9 + 24),
          *(_DWORD *)(v13 + v9 + 32));
      }
      v14 = v9 + *(_QWORD *)&lpCriticalSection[1].LockCount;
      if ( v14 )
      {
        for ( j = 0; j < SLODWORD(lpCriticalSection[1].DebugInfo); ++j )
        {
          v18 = 56LL * j;
          v19 = v18 + *(_QWORD *)&lpCriticalSection[1].LockCount;
          if ( v19 == v14 )
          {
            v20 = *(void **)(v19 + 8);
            if ( v20 )
            {
              svsutil_Free(v20);
              *(_QWORD *)(*(_QWORD *)&lpCriticalSection[1].LockCount + v18 + 8) = 0;
            }
            v21 = *(void **)(*(_QWORD *)&lpCriticalSection[1].LockCount + v18 + 24);
            if ( v21 )
            {
              svsutil_Free(v21);
              *(_QWORD *)(*(_QWORD *)&lpCriticalSection[1].LockCount + v18 + 24) = 0;
            }
            CVRoots::FreeExtensionMap(
              (CVRoots *)v21,
              (struct VROOTINFO *)(v18 + *(_QWORD *)&lpCriticalSection[1].LockCount));
            memmove_0(
              (void *)(v18 + *(_QWORD *)&lpCriticalSection[1].LockCount),
              (const void *)(*(_QWORD *)&lpCriticalSection[1].LockCount + 56LL * (j + 1)),
              56LL * (LODWORD(lpCriticalSection[1].DebugInfo) + ~j));
            --LODWORD(lpCriticalSection[1].DebugInfo);
            break;
          }
        }
        hKey = 0;
        v22 = HrCreateOrOpenVRootsKey(&hKey);
        LOBYTE(v23) = v22;
        if ( v22 < 0 || (v23 = HrRegDeleteKey(hKey, lpWideCharStr), RegCloseKey(hKey), v23 < 0) )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids,
              (unsigned int)"CVRoots::RemoveVRoot",
              v23);
        }
      }
    }
  }
LABEL_16:
  LeaveCriticalSection(lpCriticalSection);
  free(v5);
  return 1;
}

```

## disassembly

```asm
0x180029468  mov     [rsp+arg_8], rbx
0x18002946d  mov     [rsp+arg_10], rbp
0x180029472  push    rsi
0x180029473  push    rdi
0x180029474  push    r12
0x180029476  push    r14
0x180029478  push    r15
0x18002947a  sub     rsp, 40h
0x18002947e  mov     r12, rdx
0x180029481  mov     rbx, rcx
0x180029484  call    cs:__imp_EnterCriticalSection
0x18002948b  nop     dword ptr [rax+rax+00h]
0x180029490  mov     rcx, r12; lpWideCharStr
0x180029493  call    ?SzFromWsz@@YAPEADPEBG@Z; SzFromWsz(ushort const *)
0x180029498  mov     rbp, rax
0x18002949b  test    rax, rax
0x18002949e  jz      loc_18002954B
0x1800294a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800294a8  inc     rsi
0x1800294ab  cmp     byte ptr [rsi+rax], 0
0x1800294af  jnz     short loc_1800294A8
0x1800294b1  cmp     qword ptr [rbx+30h], 0
0x1800294b6  jz      loc_18002954B
0x1800294bc  xor     r14d, r14d
0x1800294bf  cmp     r14d, [rbx+28h]
0x1800294c3  jge     loc_1800295A2
0x1800294c9  mov     rdx, [rbx+30h]
0x1800294cd  movsxd  rax, r14d
0x1800294d0  imul    rdi, rax, 38h ; '8'
0x1800294d4  cmp     dword ptr [rdx+rdi+28h], 0
0x1800294d9  mov     eax, [rdx+rdi]
0x1800294dc  jnz     loc_1800295DB
0x1800294e2  test    eax, eax
0x1800294e4  jz      loc_18002959A
0x1800294ea  cmp     esi, eax
0x1800294ec  jl      loc_18002959A
0x1800294f2  mov     rdx, [rdx+rdi+8]
0x1800294f7  mov     rcx, rbp
0x1800294fa  movsxd  r15, eax
0x1800294fd  mov     r8, r15
0x180029500  call    cs:__imp__o__memicmp
0x180029507  nop     dword ptr [rax+rax+00h]
0x18002950c  test    eax, eax
0x18002950e  jnz     loc_18002959A
0x180029514  mov     rcx, [rbx+30h]
0x180029518  cmp     [rcx+rdi+28h], eax
0x18002951c  jnz     short loc_180029588
0x18002951e  mov     rdx, cs:WPP_GLOBAL_Control
0x180029525  lea     r14, WPP_GLOBAL_Control
0x18002952c  cmp     rdx, r14
0x18002952f  jz      short loc_18002953E
0x180029531  test    dword ptr [rdx+1Ch], 1000h
0x180029538  jnz     loc_1800295EB
0x18002953e  mov     rdx, [rbx+30h]
0x180029542  add     rdx, rdi
0x180029545  jnz     loc_180029618
0x18002954b  mov     rcx, rbx; lpCriticalSection
0x18002954e  call    cs:__imp_LeaveCriticalSection
0x180029555  nop     dword ptr [rax+rax+00h]
0x18002955a  mov     rcx, rbp; Block
0x18002955d  call    cs:__imp_free
0x180029564  nop     dword ptr [rax+rax+00h]
0x180029569  lea     r11, [rsp+68h+var_28]
0x18002956e  mov     eax, 1
0x180029573  mov     rbx, [r11+38h]
0x180029577  mov     rbp, [r11+40h]
0x18002957b  mov     rsp, r11
0x18002957e  pop     r15
0x180029580  pop     r14
0x180029582  pop     r12
0x180029584  pop     rdi
0x180029585  pop     rsi
0x180029586  retn
0x180029588  cmp     dword ptr [rcx+rdi], 1
0x18002958c  jz      short loc_18002951E
0x18002958e  mov     al, [r15+rbp]
0x180029592  cmp     al, 2Fh ; '/'
0x180029594  jz      short loc_18002951E
0x180029596  test    al, al
0x180029598  jz      short loc_18002951E
0x18002959a  inc     r14d
0x18002959d  jmp     loc_1800294BF
0x1800295a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295a9  lea     r14, WPP_GLOBAL_Control
0x1800295b0  cmp     rcx, r14
0x1800295b3  jz      short loc_18002954B
0x1800295b5  test    dword ptr [rcx+1Ch], 1000h
0x1800295bc  jz      short loc_18002954B
0x1800295be  mov     rcx, [rcx+10h]
0x1800295c2  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x1800295c9  mov     edx, 0Bh
0x1800295ce  mov     r9, rbp
0x1800295d1  call    WPP_SF_s
0x1800295d6  jmp     loc_18002954B
0x1800295db  cmp     eax, 1
0x1800295de  jz      loc_1800294E2
0x1800295e4  dec     eax
0x1800295e6  jmp     loc_1800294E2
0x1800295eb  mov     eax, [rcx+rdi+20h]
0x1800295ef  mov     r9, rbp
0x1800295f2  mov     [rsp+68h+var_38], eax
0x1800295f6  mov     rax, [rcx+rdi+18h]
0x1800295fb  mov     [rsp+68h+var_40], rax
0x180029600  mov     rax, [rcx+rdi+8]
0x180029605  mov     rcx, [rdx+10h]
0x180029609  mov     [rsp+68h+var_48], rax
0x18002960e  call    WPP_SF_ssSd
0x180029613  jmp     loc_18002953E
0x180029618  xor     edi, edi
0x18002961a  cmp     edi, [rbx+28h]
0x18002961d  jge     loc_1800296B9
0x180029623  mov     rcx, [rbx+30h]
0x180029627  movsxd  rax, edi
0x18002962a  imul    rsi, rax, 38h ; '8'
0x18002962e  add     rcx, rsi
0x180029631  cmp     rcx, rdx
0x180029634  jz      short loc_18002963A
0x180029636  inc     edi
0x180029638  jmp     short loc_18002961A
0x18002963a  mov     rcx, [rcx+8]; Block
0x18002963e  test    rcx, rcx
0x180029641  jz      short loc_18002965C
0x180029643  mov     rdx, cs:g_pvFreeData
0x18002964a  call    svsutil_Free
0x18002964f  mov     rax, [rbx+30h]
0x180029653  mov     qword ptr [rax+rsi+8], 0
0x18002965c  mov     rax, [rbx+30h]
0x180029660  mov     rcx, [rax+rsi+18h]; Block
0x180029665  test    rcx, rcx
0x180029668  jz      short loc_180029683
0x18002966a  mov     rdx, cs:g_pvFreeData
0x180029671  call    svsutil_Free
0x180029676  mov     rax, [rbx+30h]
0x18002967a  mov     qword ptr [rax+rsi+18h], 0
0x180029683  mov     rdx, [rbx+30h]
0x180029687  add     rdx, rsi; struct VROOTINFO *
0x18002968a  call    ?FreeExtensionMap@CVRoots@@AEAAXPEAUVROOTINFO@@@Z; CVRoots::FreeExtensionMap(VROOTINFO *)
0x18002968f  mov     r9, [rbx+30h]
0x180029693  mov     eax, edi
0x180029695  not     eax
0x180029697  add     eax, [rbx+28h]
0x18002969a  cdqe
0x18002969c  imul    r8, rax, 38h ; '8'; Size
0x1800296a0  lea     eax, [rdi+1]
0x1800296a3  movsxd  rcx, eax
0x1800296a6  imul    rdx, rcx, 38h ; '8'
0x1800296aa  lea     rcx, [rsi+r9]; void *
0x1800296ae  add     rdx, r9; Src
0x1800296b1  call    memmove_0
0x1800296b6  dec     dword ptr [rbx+28h]
0x1800296b9  lea     rcx, [rsp+68h+hKey]; HKEY *
0x1800296be  mov     [rsp+68h+hKey], 0
0x1800296c7  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x1800296cc  mov     edi, eax
0x1800296ce  test    eax, eax
0x1800296d0  js      short loc_1800296FA
0x1800296d2  mov     rcx, [rsp+68h+hKey]; HKEY
0x1800296d7  mov     rdx, r12; unsigned __int16 *
0x1800296da  call    ?HrRegDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKey(HKEY__ *,ushort const *)
0x1800296df  mov     rcx, [rsp+68h+hKey]; hKey
0x1800296e4  mov     edi, eax
0x1800296e6  call    cs:__imp_RegCloseKey
0x1800296ed  nop     dword ptr [rax+rax+00h]
0x1800296f2  test    edi, edi
0x1800296f4  jns     loc_18002954B
0x1800296fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180029701  cmp     rcx, r14
0x180029704  jz      loc_18002954B
0x18002970a  test    byte ptr [rcx+1Ch], 1
0x18002970e  jz      loc_18002954B
0x180029714  mov     rcx, [rcx+10h]
0x180029718  lea     r9, aCvrootsRemovev; "CVRoots::RemoveVRoot"
0x18002971f  mov     edx, 10h
0x180029724  mov     dword ptr [rsp+68h+var_48], edi
0x180029728  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x18002972f  call    WPP_SF_sd
0x180029734  jmp     loc_18002954B
```
