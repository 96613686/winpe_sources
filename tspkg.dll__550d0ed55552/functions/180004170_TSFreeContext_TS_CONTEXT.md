# TSFreeContext(_TS_CONTEXT *)

- ea: `0x180004170`
- end: `0x180004437`
- name: `?TSFreeContext@@YAXPEAU_TS_CONTEXT@@@Z`
- size: `711`
- prototype: `void __fastcall(struct _TS_CONTEXT *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001160`
- `0x180003e00`
- `0x180003e30`
- `0x180003ea0`

## callees

- `0x180003830`
- `0x180004170`
- `0x180004440`
- `0x180005ed0`
- `0x18000b920`
- `0x180012904`
- `0x180014100`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004407`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004407`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004412`
- `SspiCli!DeleteSecurityContext` at `0x18000437d`
- `SspiCli!DeleteSecurityContext` at `0x18000437d`
- `ntdll!RtlEnterCriticalSection` at `0x18000418d`
- `ntdll!RtlEnterCriticalSection` at `0x18000418d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800041c2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800041c2`
- `ntdll!RtlAvlRemoveNode` at `0x1800042ee`
- `ntdll!RtlAvlRemoveNode` at `0x1800043d3`
- `ntdll!RtlAvlRemoveNode` at `0x1800042ee`
- `ntdll!RtlAvlRemoveNode` at `0x1800043d3`
- `ntdll!RtlDeleteCriticalSection` at `0x180004255`
- `ntdll!RtlDeleteCriticalSection` at `0x180004255`

## pseudocode

```c
void __fastcall TSFreeContext(struct _TS_CONTEXT *a1)
{
  _QWORD *v2; // rbx
  int v3; // eax
  unsigned int v4; // edx
  struct _TS_CREDENTIAL *v5; // rcx
  struct _TS_PRIMARY_CREDENTIAL *v6; // rcx
  struct _TS_PRIMARY_CREDENTIAL *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  RedirectedCredContextTable *v12; // rcx
  void *v13; // rcx
  void (*FreeHeap)(void); // rax
  void (*v15)(void); // rax
  void (*FreePrivateHeap)(void); // rax

  if ( !a1 )
    return;
  RtlEnterCriticalSection(&CriticalSection);
  v2 = qword_1800258C8;
  if ( !qword_1800258C8 )
    goto LABEL_6;
  while ( 1 )
  {
    v3 = TSContextCompareCallback(a1, v2);
    if ( v3 >= 0 )
      break;
    v2 = (_QWORD *)*v2;
LABEL_5:
    if ( !v2 )
      goto LABEL_6;
  }
  if ( v3 > 0 )
  {
    v2 = (_QWORD *)v2[1];
    goto LABEL_5;
  }
  if ( v2 )
  {
    RtlAvlRemoveNode(&qword_1800258C8, v2);
    if ( *((_DWORD *)v2 + 13) || *((_DWORD *)v2 + 12) )
      RtlAvlRemoveNode(&qword_1800258D0, v2 + 3);
    operator delete(v2, 0x40u);
  }
LABEL_6:
  RtlLeaveCriticalSection(&CriticalSection);
  v5 = (struct _TS_CREDENTIAL *)*((_QWORD *)a1 + 2);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) <= 1 )
      TSFreeCredential(v5);
    *((_QWORD *)a1 + 2) = 0;
  }
  if ( *((_QWORD *)a1 + 3) || *((_QWORD *)a1 + 4) )
    DeleteSecurityContext((PCtxtHandle)((char *)a1 + 24));
  v6 = (struct _TS_PRIMARY_CREDENTIAL *)*((_QWORD *)a1 + 12);
  if ( v6 )
    TSFreePrimaryCredentials(v6);
  v7 = (struct _TS_PRIMARY_CREDENTIAL *)*((_QWORD *)a1 + 19);
  if ( v7 )
    TSFreePrimaryCredentials(v7);
  v8 = (void *)*((_QWORD *)a1 + 5);
  if ( v8 )
    CloseHandle(v8);
  v9 = (void *)*((_QWORD *)a1 + 6);
  if ( v9 )
    CloseHandle(v9);
  v10 = (void *)*((_QWORD *)a1 + 7);
  if ( v10 )
    CloseHandle(v10);
  v11 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 22);
  if ( v11 )
  {
    RtlDeleteCriticalSection(v11);
    if ( *((_QWORD *)a1 + 22) )
    {
      if ( TSGlobalState == 1 )
        FreePrivateHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
      else
        FreePrivateHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
      FreePrivateHeap();
    }
  }
  v12 = (RedirectedCredContextTable *)*((_QWORD *)a1 + 20);
  if ( v12 )
    RedirectedCredContextTable::`scalar deleting destructor'(v12, v4);
  if ( a1 != (struct _TS_CONTEXT *)-64LL )
  {
    v13 = (void *)*((_QWORD *)a1 + 9);
    if ( v13 )
    {
      TSFree(v13);
      *((_OWORD *)a1 + 4) = 0;
    }
  }
  if ( *((_QWORD *)a1 + 10) )
  {
    if ( TSGlobalState == 1 )
      FreeHeap = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      FreeHeap = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    FreeHeap();
  }
  if ( *((_QWORD *)a1 + 13) )
  {
    if ( TSGlobalState == 1 )
      v15 = (void (*)(void))TSGlobalLsaFunctions->FreePrivateHeap;
    else
      v15 = (void (*)(void))TSGlobalDllFunctions->FreeHeap;
    v15();
  }
  if ( TSGlobalState == 1 )
    ((void (__fastcall *)(struct _TS_CONTEXT *))TSGlobalLsaFunctions->FreePrivateHeap)(a1);
  else
    ((void (__fastcall *)(struct _TS_CONTEXT *))TSGlobalDllFunctions->FreeHeap)(a1);
}

```

## disassembly

```asm
0x180004170  test    rcx, rcx
0x180004173  jz      locret_1800042D4
0x180004179  push    rdi
0x18000417a  sub     rsp, 20h
0x18000417e  mov     rdi, rcx
0x180004181  mov     [rsp+28h+arg_0], rbx
0x180004186  lea     rcx, CriticalSection; CriticalSection
0x18000418d  call    cs:__imp_RtlEnterCriticalSection
0x180004193  mov     rbx, cs:qword_1800258C8
0x18000419a  test    rbx, rbx
0x18000419d  jz      short loc_1800041BB
0x18000419f  nop
0x1800041a0  mov     rdx, rbx
0x1800041a3  mov     rcx, rdi
0x1800041a6  call    TSContextCompareCallback
0x1800041ab  test    eax, eax
0x1800041ad  jns     loc_1800042D5
0x1800041b3  mov     rbx, [rbx]
0x1800041b6  test    rbx, rbx
0x1800041b9  jnz     short loc_1800041A0
0x1800041bb  lea     rcx, CriticalSection; CriticalSection
0x1800041c2  call    cs:__imp_RtlLeaveCriticalSection
0x1800041c8  mov     rcx, [rdi+10h]; struct _TS_CREDENTIAL *
0x1800041cc  test    rcx, rcx
0x1800041cf  jz      short loc_1800041EB
0x1800041d1  mov     eax, 0FFFFFFFFh
0x1800041d6  lock xadd [rcx], eax
0x1800041da  sub     eax, 1
0x1800041dd  jle     loc_1800043DE
0x1800041e3  mov     qword ptr [rdi+10h], 0
0x1800041eb  cmp     qword ptr [rdi+18h], 0
0x1800041f0  lea     rcx, [rdi+18h]; phContext
0x1800041f4  jnz     loc_18000437D
0x1800041fa  cmp     qword ptr [rdi+20h], 0
0x1800041ff  jnz     loc_18000437D
0x180004205  mov     rcx, [rdi+60h]; struct _TS_PRIMARY_CREDENTIAL *
0x180004209  test    rcx, rcx
0x18000420c  jnz     loc_1800043E8
0x180004212  mov     rcx, [rdi+98h]; struct _TS_PRIMARY_CREDENTIAL *
0x180004219  test    rcx, rcx
0x18000421c  jnz     loc_1800043F2
0x180004222  mov     rcx, [rdi+28h]; hObject
0x180004226  test    rcx, rcx
0x180004229  jnz     loc_1800043FC
0x18000422f  mov     rcx, [rdi+30h]; hObject
0x180004233  test    rcx, rcx
0x180004236  jnz     loc_180004407
0x18000423c  mov     rcx, [rdi+38h]; hObject
0x180004240  test    rcx, rcx
0x180004243  jnz     loc_180004412
0x180004249  mov     rcx, [rdi+0B0h]; CriticalSection
0x180004250  test    rcx, rcx
0x180004253  jz      short loc_18000426B
0x180004255  call    cs:__imp_RtlDeleteCriticalSection
0x18000425b  mov     rcx, [rdi+0B0h]
0x180004262  test    rcx, rcx
0x180004265  jnz     loc_18000435C
0x18000426b  mov     rcx, [rdi+0A0h]; this
0x180004272  test    rcx, rcx
0x180004275  jnz     loc_18000441D
0x18000427b  lea     rbx, [rdi+40h]
0x18000427f  test    rbx, rbx
0x180004282  jz      short loc_180004291
0x180004284  mov     rcx, [rbx+8]; void *
0x180004288  test    rcx, rcx
0x18000428b  jnz     loc_180004427
0x180004291  mov     rcx, [rdi+50h]
0x180004295  mov     rbx, [rsp+28h+arg_0]
0x18000429a  test    rcx, rcx
0x18000429d  jnz     short loc_18000431A
0x18000429f  mov     rcx, [rdi+68h]
0x1800042a3  test    rcx, rcx
0x1800042a6  jnz     loc_18000433B
0x1800042ac  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800042b3  mov     rcx, rdi
0x1800042b6  jnz     loc_1800043A2
0x1800042bc  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800042c3  mov     rax, [rax+188h]
0x1800042ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042cf  add     rsp, 20h
0x1800042d3  pop     rdi
0x1800042d4  retn
0x1800042d5  jg      loc_1800043BF
0x1800042db  test    rbx, rbx
0x1800042de  jz      loc_1800041BB
0x1800042e4  mov     rdx, rbx
0x1800042e7  lea     rcx, qword_1800258C8
0x1800042ee  call    cs:__imp_RtlAvlRemoveNode
0x1800042f4  cmp     dword ptr [rbx+34h], 0
0x1800042f8  jnz     loc_1800043C8
0x1800042fe  cmp     dword ptr [rbx+30h], 0
0x180004302  jnz     loc_1800043C8
0x180004308  mov     edx, 40h ; '@'; unsigned __int64
0x18000430d  mov     rcx, rbx; void *
0x180004310  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004315  jmp     loc_1800041BB
0x18000431a  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180004321  jnz     short loc_180004388
0x180004323  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000432a  mov     rax, [rax+188h]
0x180004331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004336  jmp     loc_18000429F
0x18000433b  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180004342  jnz     short loc_180004395
0x180004344  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000434b  mov     rax, [rax+188h]
0x180004352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004357  jmp     loc_1800042AC
0x18000435c  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x180004363  jnz     short loc_1800043B2
0x180004365  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000436c  mov     rax, [rax+188h]
0x180004373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004378  jmp     loc_18000426B
0x18000437d  call    cs:__imp_DeleteSecurityContext
0x180004383  jmp     loc_180004205
0x180004388  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000438f  mov     rax, [rax+8]
0x180004393  jmp     short loc_180004331
0x180004395  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x18000439c  mov     rax, [rax+8]
0x1800043a0  jmp     short loc_180004352
0x1800043a2  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800043a9  mov     rax, [rax+8]
0x1800043ad  jmp     loc_1800042CA
0x1800043b2  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x1800043b9  mov     rax, [rax+8]
0x1800043bd  jmp     short loc_180004373
0x1800043bf  mov     rbx, [rbx+8]
0x1800043c3  jmp     loc_1800041B6
0x1800043c8  lea     rdx, [rbx+18h]
0x1800043cc  lea     rcx, qword_1800258D0
0x1800043d3  call    cs:__imp_RtlAvlRemoveNode
0x1800043d9  jmp     loc_180004308
0x1800043de  call    ?TSFreeCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSFreeCredential(_TS_CREDENTIAL *)
0x1800043e3  jmp     loc_1800041E3
0x1800043e8  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x1800043ed  jmp     loc_180004212
0x1800043f2  call    ?TSFreePrimaryCredentials@@YAJPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSFreePrimaryCredentials(_TS_PRIMARY_CREDENTIAL *)
0x1800043f7  jmp     loc_180004222
0x1800043fc  call    cs:__imp_CloseHandle
0x180004402  jmp     loc_18000422F
0x180004407  call    cs:__imp_CloseHandle
0x18000440d  jmp     loc_18000423C
0x180004412  call    cs:__imp_CloseHandle
0x180004418  jmp     loc_180004249
0x18000441d  call    ??_GRedirectedCredContextTable@@QEAAPEAXI@Z; RedirectedCredContextTable::`scalar deleting destructor'(uint)
0x180004422  jmp     loc_18000427B
0x180004427  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x18000442c  xorps   xmm0, xmm0
0x18000442f  movups  xmmword ptr [rbx], xmm0
0x180004432  jmp     loc_180004291
```
