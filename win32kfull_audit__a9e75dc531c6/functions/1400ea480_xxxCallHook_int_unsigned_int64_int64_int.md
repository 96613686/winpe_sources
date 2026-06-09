# xxxCallHook(int,unsigned __int64,__int64,int)

- ea: `0x1400ea480`
- end: `0x1400ea7a5`
- name: `?xxxCallHook@@YAHH_K_JH@Z`
- size: `805`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x1400068e4`
- `0x14001cb60`
- `0x140022c54`
- `0x14002427c`
- `0x140026be4`
- `0x140030e20`
- `0x14007fc08`
- `0x1400bcdf8`
- `0x1400bfb28`
- `0x1400c1a1c`
- `0x1400c3a1c`
- `0x1400c6fb4`
- `0x1400e88c0`
- `0x1400e9390`
- `0x1400ea7ac`
- `0x1400ebc3c`
- `0x14012844c`
- `0x14013f4b4`
- `0x1401691b8`
- `0x14016e684`
- `0x1401831b8`
- `0x140183e38`
- `0x14018597c`
- `0x14018f810`
- `0x1401bafd4`
- `0x1401bbe78`
- `0x1401c0f48`
- `0x1401ca020`
- `0x1401f8e1c`
- `0x14021ff40`
- `0x140223680`
- `0x140236884`
- `0x140237460`
- `0x140259040`
- `0x14027d004`
- `0x1402bf9b0`

## callees

- `0x1400ea480`
- `0x1400ea7ac`
- `0x14012a40c`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea50b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea5da`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea68a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea50b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea5da`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400ea68a`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea4f8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea5c7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea677`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea4f8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea5c7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400ea677`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea4c7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea4e1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea559`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea599`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea5b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea649`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea660`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea6ac`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea4c7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea4e1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea559`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea599`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea5b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea649`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea660`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400ea6ac`
- `WIN32K!W32GetUserSessionState` at `0x1400ea49f`
- `WIN32K!W32GetUserSessionState` at `0x1400ea4b2`
- `WIN32K!W32GetUserSessionState` at `0x1400ea571`
- `WIN32K!W32GetUserSessionState` at `0x1400ea584`
- `WIN32K!W32GetUserSessionState` at `0x1400ea621`
- `WIN32K!W32GetUserSessionState` at `0x1400ea634`
- `WIN32K!W32GetUserSessionState` at `0x1400ea49f`
- `WIN32K!W32GetUserSessionState` at `0x1400ea4b2`
- `WIN32K!W32GetUserSessionState` at `0x1400ea571`
- `WIN32K!W32GetUserSessionState` at `0x1400ea584`
- `WIN32K!W32GetUserSessionState` at `0x1400ea621`
- `WIN32K!W32GetUserSessionState` at `0x1400ea634`

## pseudocode

```c
__int64 __fastcall xxxCallHook(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned int v7; // r15d
  struct _ERESOURCE *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdi
  struct _ERESOURCE *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rbx
  struct _ERESOURCE *v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 *v39; // rax

  v4 = (int)a4;
  v7 = a1;
  v8 = *(struct _ERESOURCE **)(W32GetUserSessionState(a1, a2, a3, a4) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v10, v9, v11, v12) + 19592)
    && (*(_DWORD *)(((__int64 (*)(void))PsGetCurrentThreadWin32Thread)() + 24) & 0xC) != 8
    && ((*(_DWORD *)(((__int64 (*)(void))PsGetCurrentThreadWin32Thread)() + 24) & 0xC) == 0
     || ExIsResourceAcquiredExclusiveLite(v8) != 1 && !ExIsResourceAcquiredSharedLite(v8)) )
  {
    __int2c();
  }
  if ( (_DWORD)v4 == 6 )
    goto LABEL_8;
  if ( (_DWORD)v4 != 4 )
  {
    if ( (_DWORD)v4 == 12 )
    {
      v13 = *(unsigned int *)(a3 + 24);
      goto LABEL_9;
    }
    if ( (_DWORD)v4 != 3 && (_DWORD)v4 != -1 )
    {
      v13 = 0;
      v14 = 0;
LABEL_12:
      if ( (_DWORD)v13 == 528 && (_WORD)v14 == 582 )
        return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
      goto LABEL_13;
    }
LABEL_8:
    v13 = *(unsigned int *)(a3 + 8);
LABEL_9:
    v14 = *(_QWORD *)(a3 + 16);
    goto LABEL_10;
  }
  v13 = *(unsigned int *)(a3 + 16);
  v14 = *(_QWORD *)(a3 + 8);
LABEL_10:
  if ( (unsigned int)(v13 - 577) <= 3 )
    return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
  if ( (unsigned int)v13 < 0x245 || (unsigned int)v13 > 0x257 || (_DWORD)v13 == 589 )
    goto LABEL_12;
  if ( (_DWORD)v13 != 595 )
    return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
LABEL_13:
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v13, v14);
  if ( CurrentThreadWin32Thread )
    v20 = *CurrentThreadWin32Thread;
  else
    v20 = 0;
  v21 = *(struct _ERESOURCE **)(W32GetUserSessionState(v17, v16, v18, v19) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v23, v22, v24, v25) + 19592) )
  {
    v27 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v27, v26) + 24);
    LOBYTE(v27) = v27 & 0xC;
    if ( (_BYTE)v27 != 8 )
    {
      v26 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v27, v26) + 24);
      if ( (v26 & 0xC) == 0 || ExIsResourceAcquiredExclusiveLite(v21) != 1 && !ExIsResourceAcquiredSharedLite(v21) )
        __int2c();
    }
  }
  v30 = v4;
  v31 = *(_QWORD *)(v20 + 8 * v4 + 960);
  if ( (v31 || (v31 = *(_QWORD *)(*(_QWORD *)(v20 + 496) + 8 * v30 + 48)) != 0) && (*(_DWORD *)(v31 + 64) & 0x80u) != 0 )
  {
    v32 = *(struct _ERESOURCE **)(W32GetUserSessionState(v27, v26, v28, v29) + 42136);
    if ( !*(_DWORD *)(W32GetUserSessionState(v34, v33, v35, v36) + 19592) )
    {
      v38 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v38, v37) + 24);
      LOBYTE(v38) = v38 & 0xC;
      if ( (_BYTE)v38 != 8 )
      {
        v37 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v38, v37) + 24);
        if ( (v37 & 0xC) == 0 || ExIsResourceAcquiredExclusiveLite(v32) != 1 && !ExIsResourceAcquiredSharedLite(v32) )
          __int2c();
      }
    }
    do
    {
      if ( *(_QWORD *)(v31 + 40) )
      {
        v31 = *(_QWORD *)(v31 + 40);
      }
      else
      {
        if ( (*(_DWORD *)(v31 + 64) & 1) != 0 )
        {
          v31 = 0;
          return xxxCallHook2(v31, v7, a2, a3, 1);
        }
        v39 = (__int64 *)PsGetCurrentThreadWin32Thread(v38, v37);
        if ( v39 )
          v38 = *v39;
        else
          v38 = 0;
        v31 = *(_QWORD *)(*(_QWORD *)(v38 + 496) + 8LL * *(int *)(v31 + 48) + 48);
        if ( !v31 )
          return xxxCallHook2(v31, v7, a2, a3, 1);
      }
    }
    while ( (*(_DWORD *)(v31 + 64) & 0x80u) != 0 );
  }
  return xxxCallHook2(v31, v7, a2, a3, 1);
}

```

## disassembly

```asm
0x1400ea480  mov     [rsp+arg_8], rbx
0x1400ea485  mov     [rsp+arg_10], rbp
0x1400ea48a  push    rdi
0x1400ea48b  push    r14
0x1400ea48d  push    r15
0x1400ea48f  sub     rsp, 30h
0x1400ea493  movsxd  rbx, r9d
0x1400ea496  mov     rbp, r8
0x1400ea499  mov     r14, rdx
0x1400ea49c  mov     r15d, ecx
0x1400ea49f  call    cs:__imp_W32GetUserSessionState
0x1400ea4a6  nop     dword ptr [rax+rax+00h]
0x1400ea4ab  mov     rdi, [rax+0A498h]
0x1400ea4b2  call    cs:__imp_W32GetUserSessionState
0x1400ea4b9  nop     dword ptr [rax+rax+00h]
0x1400ea4be  cmp     dword ptr [rax+4C88h], 0
0x1400ea4c5  jnz     short loc_1400EA51D
0x1400ea4c7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea4ce  nop     dword ptr [rax+rax+00h]
0x1400ea4d3  mov     r9d, [rax+18h]
0x1400ea4d7  and     r9b, 0Ch
0x1400ea4db  cmp     r9b, 8
0x1400ea4df  jz      short loc_1400EA51D
0x1400ea4e1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea4e8  nop     dword ptr [rax+rax+00h]
0x1400ea4ed  mov     edx, [rax+18h]
0x1400ea4f0  test    dl, 0Ch
0x1400ea4f3  jz      short loc_1400EA51B
0x1400ea4f5  mov     rcx, rdi; Resource
0x1400ea4f8  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400ea4ff  nop     dword ptr [rax+rax+00h]
0x1400ea504  cmp     al, 1
0x1400ea506  jz      short loc_1400EA51D
0x1400ea508  mov     rcx, rdi; Resource
0x1400ea50b  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400ea512  nop     dword ptr [rax+rax+00h]
0x1400ea517  test    eax, eax
0x1400ea519  jnz     short loc_1400EA51D
0x1400ea51b  int     2Ch; Windows NT - assertion failure
0x1400ea51d  cmp     ebx, 6
0x1400ea520  jnz     loc_1400EA713
0x1400ea526  mov     ecx, [rbp+8]
0x1400ea529  mov     rdx, [rbp+10h]
0x1400ea52d  lea     eax, [rcx-241h]
0x1400ea533  cmp     eax, 3
0x1400ea536  jbe     loc_1400EA759
0x1400ea53c  cmp     ecx, 245h
0x1400ea542  jnb     loc_1400EA735
0x1400ea548  cmp     ecx, 210h
0x1400ea54e  jz      loc_1400EA787
0x1400ea554  mov     [rsp+48h+arg_0], rsi
0x1400ea559  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea560  nop     dword ptr [rax+rax+00h]
0x1400ea565  test    rax, rax
0x1400ea568  jz      loc_1400EA797
0x1400ea56e  mov     rdi, [rax]
0x1400ea571  call    cs:__imp_W32GetUserSessionState
0x1400ea578  nop     dword ptr [rax+rax+00h]
0x1400ea57d  mov     rsi, [rax+0A498h]
0x1400ea584  call    cs:__imp_W32GetUserSessionState
0x1400ea58b  nop     dword ptr [rax+rax+00h]
0x1400ea590  cmp     dword ptr [rax+4C88h], 0
0x1400ea597  jnz     short loc_1400EA5EC
0x1400ea599  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea5a0  nop     dword ptr [rax+rax+00h]
0x1400ea5a5  mov     ecx, [rax+18h]
0x1400ea5a8  and     cl, 0Ch
0x1400ea5ab  cmp     cl, 8
0x1400ea5ae  jz      short loc_1400EA5EC
0x1400ea5b0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea5b7  nop     dword ptr [rax+rax+00h]
0x1400ea5bc  mov     edx, [rax+18h]
0x1400ea5bf  test    dl, 0Ch
0x1400ea5c2  jz      short loc_1400EA5EA
0x1400ea5c4  mov     rcx, rsi; Resource
0x1400ea5c7  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400ea5ce  nop     dword ptr [rax+rax+00h]
0x1400ea5d3  cmp     al, 1
0x1400ea5d5  jz      short loc_1400EA5EC
0x1400ea5d7  mov     rcx, rsi; Resource
0x1400ea5da  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400ea5e1  nop     dword ptr [rax+rax+00h]
0x1400ea5e6  test    eax, eax
0x1400ea5e8  jnz     short loc_1400EA5EC
0x1400ea5ea  int     2Ch; Windows NT - assertion failure
0x1400ea5ec  mov     rsi, [rsp+48h+arg_0]
0x1400ea5f1  mov     rax, rbx
0x1400ea5f4  mov     rbx, [rdi+rbx*8+3C0h]
0x1400ea5fc  test    rbx, rbx
0x1400ea5ff  jnz     short loc_1400EA616
0x1400ea601  mov     rbx, [rdi+1F0h]
0x1400ea608  mov     rbx, [rbx+rax*8+30h]
0x1400ea60d  test    rbx, rbx
0x1400ea610  jz      loc_1400EA6D9
0x1400ea616  mov     eax, [rbx+40h]
0x1400ea619  test    al, al
0x1400ea61b  jns     loc_1400EA6D9
0x1400ea621  call    cs:__imp_W32GetUserSessionState
0x1400ea628  nop     dword ptr [rax+rax+00h]
0x1400ea62d  mov     rdi, [rax+0A498h]
0x1400ea634  call    cs:__imp_W32GetUserSessionState
0x1400ea63b  nop     dword ptr [rax+rax+00h]
0x1400ea640  cmp     dword ptr [rax+4C88h], 0
0x1400ea647  jnz     short loc_1400EA69C
0x1400ea649  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea650  nop     dword ptr [rax+rax+00h]
0x1400ea655  mov     ecx, [rax+18h]
0x1400ea658  and     cl, 0Ch
0x1400ea65b  cmp     cl, 8
0x1400ea65e  jz      short loc_1400EA69C
0x1400ea660  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea667  nop     dword ptr [rax+rax+00h]
0x1400ea66c  mov     edx, [rax+18h]
0x1400ea66f  test    dl, 0Ch
0x1400ea672  jz      short loc_1400EA69A
0x1400ea674  mov     rcx, rdi; Resource
0x1400ea677  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400ea67e  nop     dword ptr [rax+rax+00h]
0x1400ea683  cmp     al, 1
0x1400ea685  jz      short loc_1400EA69C
0x1400ea687  mov     rcx, rdi; Resource
0x1400ea68a  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400ea691  nop     dword ptr [rax+rax+00h]
0x1400ea696  test    eax, eax
0x1400ea698  jnz     short loc_1400EA69C
0x1400ea69a  int     2Ch; Windows NT - assertion failure
0x1400ea69c  mov     rax, [rbx+28h]
0x1400ea6a0  test    rax, rax
0x1400ea6a3  jnz     short loc_1400EA707
0x1400ea6a5  mov     eax, [rbx+40h]
0x1400ea6a8  test    al, 1
0x1400ea6aa  jnz     short loc_1400EA724
0x1400ea6ac  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400ea6b3  nop     dword ptr [rax+rax+00h]
0x1400ea6b8  test    rax, rax
0x1400ea6bb  jz      loc_1400EA79E
0x1400ea6c1  mov     rcx, [rax]
0x1400ea6c4  movsxd  rax, dword ptr [rbx+30h]
0x1400ea6c8  mov     rbx, [rcx+1F0h]
0x1400ea6cf  mov     rbx, [rbx+rax*8+30h]
0x1400ea6d4  test    rbx, rbx
0x1400ea6d7  jnz     short loc_1400EA70A
0x1400ea6d9  mov     r9, rbp
0x1400ea6dc  mov     [rsp+48h+var_28], 1
0x1400ea6e4  mov     r8, r14
0x1400ea6e7  mov     edx, r15d
0x1400ea6ea  mov     rcx, rbx
0x1400ea6ed  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x1400ea6f2  mov     rbx, [rsp+48h+arg_8]
0x1400ea6f7  mov     rbp, [rsp+48h+arg_10]
0x1400ea6fc  add     rsp, 30h
0x1400ea700  pop     r15
0x1400ea702  pop     r14
0x1400ea704  pop     rdi
0x1400ea705  retn
0x1400ea707  mov     rbx, rax
0x1400ea70a  mov     eax, [rbx+40h]
0x1400ea70d  test    al, al
0x1400ea70f  jns     short loc_1400EA6D9
0x1400ea711  jmp     short loc_1400EA69C
0x1400ea713  cmp     ebx, 4
0x1400ea716  jnz     short loc_1400EA728
0x1400ea718  mov     ecx, [rbp+10h]
0x1400ea71b  mov     rdx, [rbp+8]
0x1400ea71f  jmp     loc_1400EA52D
0x1400ea724  xor     ebx, ebx
0x1400ea726  jmp     short loc_1400EA6D9
0x1400ea728  cmp     ebx, 0Ch
0x1400ea72b  jnz     short loc_1400EA76C
0x1400ea72d  mov     ecx, [rbp+18h]
0x1400ea730  jmp     loc_1400EA529
0x1400ea735  cmp     ecx, 257h
0x1400ea73b  ja      loc_1400EA548
0x1400ea741  cmp     ecx, 24Dh
0x1400ea747  jz      loc_1400EA548
0x1400ea74d  cmp     ecx, 253h
0x1400ea753  jz      loc_1400EA554
0x1400ea759  mov     r9d, ebx
0x1400ea75c  mov     r8, rbp
0x1400ea75f  mov     rdx, r14
0x1400ea762  mov     ecx, r15d
0x1400ea765  call    xxxPointerCallHook
0x1400ea76a  jmp     short loc_1400EA6F2
0x1400ea76c  cmp     ebx, 3
0x1400ea76f  jz      loc_1400EA526
0x1400ea775  cmp     ebx, 0FFFFFFFFh
0x1400ea778  jz      loc_1400EA526
0x1400ea77e  xor     ecx, ecx
0x1400ea780  xor     edx, edx
0x1400ea782  jmp     loc_1400EA548
0x1400ea787  mov     eax, 246h
0x1400ea78c  cmp     dx, ax
0x1400ea78f  jnz     loc_1400EA554
0x1400ea795  jmp     short loc_1400EA759
0x1400ea797  xor     edi, edi
0x1400ea799  jmp     loc_1400EA571
0x1400ea79e  xor     ecx, ecx
0x1400ea7a0  jmp     loc_1400EA6C4
```
