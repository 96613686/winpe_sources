# CDUIResourceManager::InitThread(uint,DUI_RESOURCE_MANAGER_INIT_FLAGS)

- ea: `0x1800434a0`
- end: `0x180043615`
- name: `?InitThread@CDUIResourceManager@@QEAAJIW4DUI_RESOURCE_MANAGER_INIT_FLAGS@@@Z`
- size: `373`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180043158`
- `0x18005cde4`
- `0x18005f3e4`
- `0x1800748b0`
- `0x1800764e8`
- `0x180085718`

## callees

- `0x1800434a0`
- `0x1800d84c0`
- `0x1800d8634`
- `0x1800d8750`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800435fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800435fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800434b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800434b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180043549`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180043549`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800435be`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800435be`
- `DUI70!UnInitProcessPriv` at `0x180043574`
- `DUI70!UnInitProcessPriv` at `0x1800435e3`
- `DUI70!UnInitProcessPriv` at `0x180043574`
- `DUI70!UnInitProcessPriv` at `0x1800435e3`
- `DUI70!UnInitThread` at `0x1800435a9`
- `DUI70!UnInitThread` at `0x1800435a9`
- `DUI70!InitThread` at `0x180043584`
- `DUI70!InitThread` at `0x180043584`
- `DUI70!InitProcessPriv` at `0x1800434e7`
- `DUI70!InitProcessPriv` at `0x1800434e7`

## pseudocode

```c
__int64 __fastcall CDUIResourceManager::InitThread(__int64 a1, unsigned int a2)
{
  __int64 v4; // r8
  __int64 v5; // rcx
  int inited; // edi
  __int64 v7; // rsi
  int v8; // eax
  unsigned int i; // esi
  unsigned int v10; // edx
  DWORD v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // edx

  AcquireSRWLockExclusive((PSRWLOCK)a1);
  if ( !*(_DWORD *)(a1 + 12) )
  {
    LOBYTE(v4) = 1;
    inited = InitProcessPriv(14, &_ImageBase, v4);
    if ( inited < 0 )
      goto LABEL_24;
    v7 = 0;
    while ( (unsigned int)v7 < *(_DWORD *)(a1 + 40) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 32) + 8 * v7))(v5);
      v7 = (unsigned int)(v7 + 1);
      inited = v8;
      if ( v8 < 0 )
        goto LABEL_16;
    }
    if ( *(_QWORD *)(a1 + 56) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 64); ++i )
      {
        inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 56) + 16LL * i))(2LL * i);
        if ( inited < 0 )
        {
          v10 = i;
          goto LABEL_15;
        }
      }
    }
    v11 = TlsAlloc();
    *(_DWORD *)(a1 + 16) = v11;
    if ( v11 == -1 )
    {
      v10 = *(_DWORD *)(a1 + 64);
      inited = -2147467259;
LABEL_15:
      CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)a1, v10);
LABEL_16:
      UnInitProcessPriv(&_ImageBase);
      goto LABEL_24;
    }
  }
  inited = InitThread(a2);
  if ( inited >= 0 )
  {
    inited = CDUIResourceManager::_InitParserForThread((CDUIResourceManager *)a1);
    if ( inited >= 0 )
    {
      ++*(_DWORD *)(a1 + 12);
      SHKeepDUIInitializedForThread(a2);
      goto LABEL_24;
    }
    UnInitThread(v12);
  }
  if ( !*(_DWORD *)(a1 + 12) )
  {
    TlsFree(*(_DWORD *)(a1 + 16));
    v13 = *(_DWORD *)(a1 + 64);
    *(_DWORD *)(a1 + 16) = -1;
    CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)a1, v13);
    UnInitProcessPriv(&_ImageBase);
  }
LABEL_24:
  ReleaseSRWLockExclusive((PSRWLOCK)a1);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800434a0  push    rbx
0x1800434a2  push    rbp
0x1800434a3  push    rsi
0x1800434a4  push    rdi
0x1800434a5  sub     rsp, 38h
0x1800434a9  mov     edi, r8d
0x1800434ac  mov     ebp, edx
0x1800434ae  mov     rbx, rcx
0x1800434b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800434b8  nop     dword ptr [rax+rax+00h]
0x1800434bd  cmp     dword ptr [rbx+0Ch], 0
0x1800434c1  jnz     loc_180043582
0x1800434c7  shr     edi, 1
0x1800434c9  lea     rdx, __ImageBase
0x1800434d0  mov     r9b, 1
0x1800434d3  not     dil
0x1800434d6  and     dil, 1
0x1800434da  mov     r8b, r9b
0x1800434dd  mov     ecx, 0Eh
0x1800434e2  mov     [rsp+58h+var_38], dil
0x1800434e7  call    cs:__imp_InitProcessPriv
0x1800434ee  nop     dword ptr [rax+rax+00h]
0x1800434f3  mov     edi, eax
0x1800434f5  test    eax, eax
0x1800434f7  js      loc_1800435FA
0x1800434fd  xor     esi, esi
0x1800434ff  cmp     esi, [rbx+28h]
0x180043502  jnb     short loc_18004351B
0x180043504  mov     rax, [rbx+20h]
0x180043508  mov     rax, [rax+rsi*8]
0x18004350c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043511  inc     esi
0x180043513  mov     edi, eax
0x180043515  test    eax, eax
0x180043517  jns     short loc_1800434FF
0x180043519  jmp     short loc_18004356D
0x18004351b  cmp     qword ptr [rbx+38h], 0
0x180043520  jz      short loc_180043549
0x180043522  xor     esi, esi
0x180043524  cmp     esi, [rbx+40h]
0x180043527  jnb     short loc_180043549
0x180043529  mov     rax, [rbx+38h]
0x18004352d  mov     ecx, esi
0x18004352f  add     rcx, rcx
0x180043532  mov     rax, [rax+rcx*8]
0x180043536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004353b  mov     edi, eax
0x18004353d  test    eax, eax
0x18004353f  js      short loc_180043545
0x180043541  inc     esi
0x180043543  jmp     short loc_180043524
0x180043545  mov     edx, esi
0x180043547  jmp     short loc_180043565
0x180043549  call    cs:__imp_TlsAlloc
0x180043550  nop     dword ptr [rax+rax+00h]
0x180043555  mov     [rbx+10h], eax
0x180043558  cmp     eax, 0FFFFFFFFh
0x18004355b  jnz     short loc_180043582
0x18004355d  mov     edx, [rbx+40h]; unsigned int
0x180043560  mov     edi, 80004005h
0x180043565  mov     rcx, rbx; this
0x180043568  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x18004356d  lea     rcx, __ImageBase
0x180043574  call    cs:__imp_UnInitProcessPriv
0x18004357b  nop     dword ptr [rax+rax+00h]
0x180043580  jmp     short loc_1800435FA
0x180043582  mov     ecx, ebp
0x180043584  call    cs:__imp_InitThread
0x18004358b  nop     dword ptr [rax+rax+00h]
0x180043590  mov     edi, eax
0x180043592  test    eax, eax
0x180043594  js      short loc_1800435B5
0x180043596  mov     rcx, rbx; this
0x180043599  call    ?_InitParserForThread@CDUIResourceManager@@AEAAJXZ; CDUIResourceManager::_InitParserForThread(void)
0x18004359e  mov     edi, eax
0x1800435a0  test    eax, eax
0x1800435a2  js      short loc_1800435A9
0x1800435a4  inc     dword ptr [rbx+0Ch]
0x1800435a7  jmp     short loc_1800435F3
0x1800435a9  call    cs:__imp_UnInitThread
0x1800435b0  nop     dword ptr [rax+rax+00h]
0x1800435b5  cmp     dword ptr [rbx+0Ch], 0
0x1800435b9  jnz     short loc_1800435FA
0x1800435bb  mov     ecx, [rbx+10h]; dwTlsIndex
0x1800435be  call    cs:__imp_TlsFree
0x1800435c5  nop     dword ptr [rax+rax+00h]
0x1800435ca  mov     edx, [rbx+40h]; unsigned int
0x1800435cd  mov     rcx, rbx; this
0x1800435d0  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800435d7  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x1800435dc  lea     rcx, __ImageBase
0x1800435e3  call    cs:__imp_UnInitProcessPriv
0x1800435ea  nop     dword ptr [rax+rax+00h]
0x1800435ef  test    edi, edi
0x1800435f1  js      short loc_1800435FA
0x1800435f3  mov     ecx, ebp; unsigned int
0x1800435f5  call    ?SHKeepDUIInitializedForThread@@YAJI@Z; SHKeepDUIInitializedForThread(uint)
0x1800435fa  mov     rcx, rbx; SRWLock
0x1800435fd  call    cs:__imp_ReleaseSRWLockExclusive
0x180043604  nop     dword ptr [rax+rax+00h]
0x180043609  mov     eax, edi
0x18004360b  add     rsp, 38h
0x18004360f  pop     rdi
0x180043610  pop     rsi
0x180043611  pop     rbp
0x180043612  pop     rbx
0x180043613  retn
```
