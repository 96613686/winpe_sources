# CVRoots::RemoveVRoot(ushort *)

- ea: `0x18002824c`
- end: `0x1800284f7`
- name: `?RemoveVRoot@CVRoots@@QEAAHPEAG@Z`
- size: `683`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e16c`

## callees

- `0x1800062a8`
- `0x18000db4c`
- `0x18001ca98`
- `0x18002824c`
- `0x180028500`
- `0x18004503c`
- `0x18004e704`
- `0x18004eb70`
- `0x18004ec9c`
- `0x180054318`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x1800282de`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x1800282de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002832b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002832b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028322`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028322`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800284aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800284aa`

## string_xrefs

- `0x1800284d6`: `CVRoots::RemoveVRoot`

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
0x18002824c  mov     [rsp+arg_8], rbx
0x180028251  mov     [rsp+arg_10], rbp
0x180028256  push    rsi
0x180028257  push    rdi
0x180028258  push    r12
0x18002825a  push    r14
0x18002825c  push    r15
0x18002825e  sub     rsp, 40h
0x180028262  mov     r12, rdx
0x180028265  mov     rbx, rcx
0x180028268  call    cs:__imp_EnterCriticalSection
0x18002826e  mov     rcx, r12; lpWideCharStr
0x180028271  call    ?SzFromWsz@@YAPEADPEBG@Z; SzFromWsz(ushort const *)
0x180028276  mov     rbp, rax
0x180028279  test    rax, rax
0x18002827c  jz      loc_18002831F
0x180028282  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028286  inc     rsi
0x180028289  cmp     byte ptr [rsi+rax], 0
0x18002828d  jnz     short loc_180028286
0x18002828f  cmp     qword ptr [rbx+30h], 0
0x180028294  jz      loc_18002831F
0x18002829a  xor     r14d, r14d
0x18002829d  cmp     r14d, [rbx+28h]
0x1800282a1  jge     loc_180028369
0x1800282a7  mov     rdx, [rbx+30h]
0x1800282ab  movsxd  rax, r14d
0x1800282ae  imul    rdi, rax, 38h ; '8'
0x1800282b2  cmp     dword ptr [rdx+rdi+28h], 0
0x1800282b7  mov     eax, [rdx+rdi]
0x1800282ba  jnz     loc_18002839F
0x1800282c0  test    eax, eax
0x1800282c2  jz      loc_180028361
0x1800282c8  cmp     esi, eax
0x1800282ca  jl      loc_180028361
0x1800282d0  mov     rdx, [rdx+rdi+8]
0x1800282d5  mov     rcx, rbp
0x1800282d8  movsxd  r15, eax
0x1800282db  mov     r8, r15
0x1800282de  call    cs:__imp__o__memicmp
0x1800282e4  test    eax, eax
0x1800282e6  jnz     short loc_180028361
0x1800282e8  mov     rcx, [rbx+30h]
0x1800282ec  cmp     [rcx+rdi+28h], eax
0x1800282f0  jnz     short loc_18002834F
0x1800282f2  mov     rdx, cs:WPP_GLOBAL_Control
0x1800282f9  lea     r14, WPP_GLOBAL_Control
0x180028300  cmp     rdx, r14
0x180028303  jz      short loc_180028312
0x180028305  test    dword ptr [rdx+1Ch], 1000h
0x18002830c  jnz     loc_1800283AF
0x180028312  mov     rdx, [rbx+30h]
0x180028316  add     rdx, rdi
0x180028319  jnz     loc_1800283DC
0x18002831f  mov     rcx, rbx; lpCriticalSection
0x180028322  call    cs:__imp_LeaveCriticalSection
0x180028328  mov     rcx, rbp; Block
0x18002832b  call    cs:__imp_free
0x180028331  lea     r11, [rsp+68h+var_28]
0x180028336  mov     eax, 1
0x18002833b  mov     rbx, [r11+38h]
0x18002833f  mov     rbp, [r11+40h]
0x180028343  mov     rsp, r11
0x180028346  pop     r15
0x180028348  pop     r14
0x18002834a  pop     r12
0x18002834c  pop     rdi
0x18002834d  pop     rsi
0x18002834e  retn
0x18002834f  cmp     dword ptr [rcx+rdi], 1
0x180028353  jz      short loc_1800282F2
0x180028355  mov     al, [r15+rbp]
0x180028359  cmp     al, 2Fh ; '/'
0x18002835b  jz      short loc_1800282F2
0x18002835d  test    al, al
0x18002835f  jz      short loc_1800282F2
0x180028361  inc     r14d
0x180028364  jmp     loc_18002829D
0x180028369  mov     rcx, cs:WPP_GLOBAL_Control
0x180028370  lea     r14, WPP_GLOBAL_Control
0x180028377  cmp     rcx, r14
0x18002837a  jz      short loc_18002831F
0x18002837c  test    dword ptr [rcx+1Ch], 1000h
0x180028383  jz      short loc_18002831F
0x180028385  mov     rcx, [rcx+10h]
0x180028389  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x180028390  mov     edx, 0Bh
0x180028395  mov     r9, rbp
0x180028398  call    WPP_SF_s
0x18002839d  jmp     short loc_18002831F
0x18002839f  cmp     eax, 1
0x1800283a2  jz      loc_1800282C0
0x1800283a8  dec     eax
0x1800283aa  jmp     loc_1800282C0
0x1800283af  mov     eax, [rcx+rdi+20h]
0x1800283b3  mov     r9, rbp
0x1800283b6  mov     [rsp+68h+var_38], eax
0x1800283ba  mov     rax, [rcx+rdi+18h]
0x1800283bf  mov     [rsp+68h+var_40], rax
0x1800283c4  mov     rax, [rcx+rdi+8]
0x1800283c9  mov     rcx, [rdx+10h]
0x1800283cd  mov     [rsp+68h+var_48], rax
0x1800283d2  call    WPP_SF_ssSd
0x1800283d7  jmp     loc_180028312
0x1800283dc  xor     edi, edi
0x1800283de  cmp     edi, [rbx+28h]
0x1800283e1  jge     loc_18002847D
0x1800283e7  mov     rcx, [rbx+30h]
0x1800283eb  movsxd  rax, edi
0x1800283ee  imul    rsi, rax, 38h ; '8'
0x1800283f2  add     rcx, rsi
0x1800283f5  cmp     rcx, rdx
0x1800283f8  jz      short loc_1800283FE
0x1800283fa  inc     edi
0x1800283fc  jmp     short loc_1800283DE
0x1800283fe  mov     rcx, [rcx+8]; Block
0x180028402  test    rcx, rcx
0x180028405  jz      short loc_180028420
0x180028407  mov     rdx, cs:g_pvFreeData
0x18002840e  call    svsutil_Free
0x180028413  mov     rax, [rbx+30h]
0x180028417  mov     qword ptr [rax+rsi+8], 0
0x180028420  mov     rax, [rbx+30h]
0x180028424  mov     rcx, [rax+rsi+18h]; Block
0x180028429  test    rcx, rcx
0x18002842c  jz      short loc_180028447
0x18002842e  mov     rdx, cs:g_pvFreeData
0x180028435  call    svsutil_Free
0x18002843a  mov     rax, [rbx+30h]
0x18002843e  mov     qword ptr [rax+rsi+18h], 0
0x180028447  mov     rdx, [rbx+30h]
0x18002844b  add     rdx, rsi; struct VROOTINFO *
0x18002844e  call    ?FreeExtensionMap@CVRoots@@AEAAXPEAUVROOTINFO@@@Z; CVRoots::FreeExtensionMap(VROOTINFO *)
0x180028453  mov     r9, [rbx+30h]
0x180028457  mov     eax, edi
0x180028459  not     eax
0x18002845b  add     eax, [rbx+28h]
0x18002845e  cdqe
0x180028460  imul    r8, rax, 38h ; '8'; Size
0x180028464  lea     eax, [rdi+1]
0x180028467  movsxd  rcx, eax
0x18002846a  imul    rdx, rcx, 38h ; '8'
0x18002846e  lea     rcx, [rsi+r9]; void *
0x180028472  add     rdx, r9; Src
0x180028475  call    memmove_0
0x18002847a  dec     dword ptr [rbx+28h]
0x18002847d  lea     rcx, [rsp+68h+hKey]; HKEY *
0x180028482  mov     [rsp+68h+hKey], 0
0x18002848b  call    ?HrCreateOrOpenVRootsKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenVRootsKey(HKEY__ * *)
0x180028490  mov     edi, eax
0x180028492  test    eax, eax
0x180028494  js      short loc_1800284B8
0x180028496  mov     rcx, [rsp+68h+hKey]; HKEY
0x18002849b  mov     rdx, r12; unsigned __int16 *
0x18002849e  call    ?HrRegDeleteKey@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKey(HKEY__ *,ushort const *)
0x1800284a3  mov     rcx, [rsp+68h+hKey]; hKey
0x1800284a8  mov     edi, eax
0x1800284aa  call    cs:__imp_RegCloseKey
0x1800284b0  test    edi, edi
0x1800284b2  jns     loc_18002831F
0x1800284b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284bf  cmp     rcx, r14
0x1800284c2  jz      loc_18002831F
0x1800284c8  test    byte ptr [rcx+1Ch], 1
0x1800284cc  jz      loc_18002831F
0x1800284d2  mov     rcx, [rcx+10h]
0x1800284d6  lea     r9, aCvrootsRemovev; "CVRoots::RemoveVRoot"
0x1800284dd  mov     edx, 10h
0x1800284e2  mov     dword ptr [rsp+68h+var_48], edi
0x1800284e6  lea     r8, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids
0x1800284ed  call    WPP_SF_sd
0x1800284f2  jmp     loc_18002831F
```
