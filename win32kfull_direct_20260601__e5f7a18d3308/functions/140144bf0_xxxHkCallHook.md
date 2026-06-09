# xxxHkCallHook

- ea: `0x140144bf0`
- end: `0x140145419`
- name: `xxxHkCallHook`
- size: `2089`
- prototype: ``
- caller_count: `1`
- callee_count: `81`
- tags: `loader_planting`

## callers

- `0x1400ea7ac`

## callees

- `0x1400b99b4`
- `0x1400ba260`
- `0x1400ba780`
- `0x1400ba7e0`
- `0x1400ba960`
- `0x1400bae20`
- `0x1400bbc70`
- `0x1400bbda0`
- `0x1400c1d20`
- `0x1400ddc08`
- `0x1400de0b0`
- `0x1400de310`
- `0x1400de560`
- `0x1400decc0`
- `0x1400df0d4`
- `0x1400df330`
- `0x1400df5b0`
- `0x1400df8a0`
- `0x1400dfc60`
- `0x1400e0460`
- `0x1400e1d60`
- `0x1400e2de0`
- `0x1400e3d30`
- `0x1400e4250`
- `0x140144bf0`
- `0x14018bdb0`
- `0x14018f510`
- `0x1401a21c0`
- `0x1401a24a0`
- `0x1401a27a0`
- `0x1401a2c00`
- `0x1401a2f00`
- `0x1401acf9c`
- `0x1401cf410`
- `0x1401d8654`
- `0x1401ddfd0`
- `0x1401de390`
- `0x1401e2cb0`
- `0x1401e5620`
- `0x1401ea7e0`
- `0x1401f3320`
- `0x1401fece0`
- `0x1402021a0`
- `0x140202f20`
- `0x1402053d0`
- `0x140207bb0`
- `0x14020a350`
- `0x14020d6f0`
- `0x14020e420`
- `0x140211b80`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140144ca2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140144ca2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140144c8f`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140144c8f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140144d3a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140144d3a`
- `ntoskrnl!KeBugCheckEx` at `0x1401450d4`
- `ntoskrnl!KeBugCheckEx` at `0x1401450d4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c61`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c78`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144cc7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144cfc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140145168`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c61`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144c78`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144cc7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140144cfc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140145168`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140144d5c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1401453e2`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x140144d5c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x1401453e2`
- `win32kbase!_HMObjectFromHandle` at `0x140145240`
- `win32kbase!_HMObjectFromHandle` at `0x1401452a7`
- `win32kbase!_HMObjectFromHandle` at `0x1401452ec`
- `win32kbase!_HMObjectFromHandle` at `0x140145351`
- `win32kbase!_HMObjectFromHandle` at `0x140145240`
- `win32kbase!_HMObjectFromHandle` at `0x1401452a7`
- `win32kbase!_HMObjectFromHandle` at `0x1401452ec`
- `win32kbase!_HMObjectFromHandle` at `0x140145351`
- `WIN32K!W32GetUserSessionState` at `0x140144c39`
- `WIN32K!W32GetUserSessionState` at `0x140144c4c`
- `WIN32K!W32GetUserSessionState` at `0x140144d76`
- `WIN32K!W32GetUserSessionState` at `0x140144da5`
- `WIN32K!W32GetUserSessionState` at `0x140144c39`
- `WIN32K!W32GetUserSessionState` at `0x140144c4c`
- `WIN32K!W32GetUserSessionState` at `0x140144d76`
- `WIN32K!W32GetUserSessionState` at `0x140144da5`

## pseudocode

```c
__int64 __fastcall xxxHkCallHook(unsigned __int64 a1, __int64 a2, unsigned __int64 a3, __int128 *a4)
{
  int v6; // r12d
  struct _ERESOURCE *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // rax
  _QWORD *CurrentProcessWin32Process; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int *v23; // rbx
  __int64 v24; // rcx
  unsigned __int64 *v25; // rax
  __int64 *v26; // r15
  __int64 v27; // rcx
  unsigned int v28; // edi
  __int64 v29; // rax
  int v30; // ecx
  unsigned int v31; // ebx
  __int64 v32; // rsi
  __int64 v33; // rbx
  unsigned __int128 v34; // rax
  unsigned __int64 v35; // rdx
  __int128 *v36; // r12
  __int128 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rsi
  _QWORD *v40; // rax
  unsigned __int64 v41; // rdx
  unsigned int v42; // r15d
  int v43; // r13d
  int v44; // ebx
  int v45; // r13d
  unsigned int v46; // r12d
  __int64 v47; // rbx
  __int64 v48; // rdi
  __int64 *v49; // rax
  unsigned __int64 v50; // rax
  __int64 (__fastcall *v51)(int, int, int, int, __int64, __int64); // rsi
  __int64 v52; // rax
  unsigned __int64 *v53; // rcx
  __int64 v54; // rbx
  __int64 v55; // rdi
  __int64 *v56; // rax
  __int64 (__fastcall *v57)(int, int, int, int, __int64, __int64); // rsi
  __int64 v58; // rax
  __int64 v60; // [rsp+28h] [rbp-110h]
  __int64 v61; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int64 v62; // [rsp+58h] [rbp-E0h]
  unsigned __int64 *v63; // [rsp+60h] [rbp-D8h]
  unsigned __int64 *v64; // [rsp+68h] [rbp-D0h]
  __int64 v65; // [rsp+70h] [rbp-C8h]
  unsigned int v66; // [rsp+78h] [rbp-C0h]
  __int64 v67; // [rsp+80h] [rbp-B8h]
  unsigned __int64 *v68; // [rsp+88h] [rbp-B0h]
  __int128 *v69; // [rsp+90h] [rbp-A8h]
  _BYTE v70[56]; // [rsp+B8h] [rbp-80h] BYREF

  v6 = a2;
  v62 = a1;
  v68 = 0;
  v67 = 0;
  v8 = *(struct _ERESOURCE **)(W32GetUserSessionState(a1, a2) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v10, v9) + 19592) )
  {
    v11 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v11) + 24);
    LOBYTE(v11) = v11 & 0xC;
    if ( (_BYTE)v11 != 8
      && ((*(_DWORD *)(PsGetCurrentThreadWin32Thread(v11) + 24) & 0xC) == 0
       || ExIsResourceAcquiredExclusiveLite(v8) != 1 && !ExIsResourceAcquiredSharedLite(v8)) )
    {
      __int2c();
    }
  }
  v12 = *(_QWORD *)(a1 + 56);
  if ( !v12 )
    return 0;
  if ( *(_DWORD *)(a1 + 68) != -1 )
  {
    CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v11);
    v15 = CurrentThreadWin32Thread ? *CurrentThreadWin32Thread : 0LL;
    v16 = *(int *)(a1 + 68);
    v12 = *(_QWORD *)(a1 + 56) + *(_QWORD *)(*(_QWORD *)(v15 + 456) + 8 * v16 + 400);
    if ( (_DWORD)v16 != -1 )
    {
      v17 = (__int64 *)PsGetCurrentThreadWin32Thread(v14);
      if ( v17 )
        v18 = *v17;
      else
        v18 = 0;
      v65 = *(_QWORD *)(v18 + 512);
      *(_QWORD *)(v65 + 224) |= 0x200uLL;
    }
  }
  CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process();
  v20 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
    v20 = 0;
  v66 = W32SetCurrentThreadDpiAwarenessContext(*((unsigned int *)v20 + 67));
  v23 = (int *)(a1 + 64);
  if ( (*(_DWORD *)(a1 + 64) & 2) != 0 )
  {
    v24 = *(_QWORD *)(W32GetUserSessionState(v22, v21) + 19704);
    v63 = (unsigned __int64 *)(v24 + 536);
    v25 = (unsigned __int64 *)(v24 + 528);
    v26 = (__int64 *)(v24 + 544);
  }
  else
  {
    v27 = *(_QWORD *)(W32GetUserSessionState(v22, v21) + 19704);
    v63 = (unsigned __int64 *)(v27 + 728);
    v25 = (unsigned __int64 *)(v27 + 720);
    v26 = (__int64 *)(v27 + 736);
  }
  v64 = v25;
  v28 = *(_DWORD *)(a1 + 48);
  if ( v28 == 12 )
  {
LABEL_47:
    v36 = 0;
    if ( v28 != 4 )
      v36 = a4;
    v37 = a4;
    if ( v28 != 4 )
      v37 = 0;
    v69 = v37;
    v38 = 32;
    if ( v28 != 4 )
      v38 = 40;
    v39 = *(_QWORD *)((char *)a4 + v38);
    v65 = v39;
    if ( v39 && (*(_DWORD *)(v39 + 84) & 5) != 0 )
    {
      v32 = 0;
    }
    else
    {
      v40 = (_QWORD *)PsGetCurrentThreadWin32Thread(40);
      if ( v40 )
        v40 = (_QWORD *)*v40;
      v61 = v40[64];
      v41 = v62;
      if ( *(_DWORD *)(v62 + 48) == 4 )
      {
        v62 = *v64;
      }
      else
      {
        v62 = *v63;
        *(_QWORD *)(v61 + 104) = *(_QWORD *)v36;
      }
      v42 = *(_DWORD *)v61 & 0x10;
      v67 = v42;
      v64 = *(unsigned __int64 **)(v61 + 104);
      v68 = v64;
      if ( a3 )
        *(_QWORD *)v61 |= 0x10uLL;
      else
        *(_QWORD *)v61 &= ~0x10uLL;
      v43 = *v23;
      v44 = *(_DWORD *)(v41 + 48);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v70);
      v45 = v43 & 2;
      if ( v44 == 4 )
      {
        v46 = *((_DWORD *)v69 + 4);
        v47 = *(_QWORD *)v69;
        v48 = *((_QWORD *)v69 + 1);
        if ( (v46 & 0x1FFFF) < 0x400 )
        {
          v51 = gapfnScSendMessage[(unsigned __int8)MessageTable[(unsigned __int16)v46]];
          v52 = _HMObjectFromHandle(*((_QWORD *)v69 + 3));
          v50 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, unsigned __int64, unsigned __int64, unsigned int, __int64))v51)(
                  v52,
                  v46,
                  v48,
                  v47,
                  v12,
                  v62,
                  (unsigned int)(v45 != 0) + 2,
                  v65);
        }
        else
        {
          v49 = (__int64 *)_HMObjectFromHandle(*((_QWORD *)v69 + 3));
          v50 = SfnDWORD(v49, v46, v48, v47, v12, v62);
        }
      }
      else
      {
        v53 = (unsigned __int64 *)*((unsigned int *)v36 + 6);
        v63 = v53;
        v54 = *((_QWORD *)v36 + 1);
        v55 = *((_QWORD *)v36 + 2);
        if ( ((unsigned int)v53 & 0x1FFFF) < 0x400 )
        {
          v57 = gapfnScSendMessage[(unsigned __int8)MessageTable[(unsigned __int16)v53]];
          v58 = _HMObjectFromHandle(*((_QWORD *)v36 + 4));
          v50 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, unsigned __int64, unsigned __int64, unsigned int, __int64))v57)(
                  v58,
                  (unsigned int)v63,
                  v55,
                  v54,
                  v12,
                  v62,
                  (unsigned int)(v45 != 0) + 2,
                  v65);
        }
        else
        {
          v56 = (__int64 *)_HMObjectFromHandle(*((_QWORD *)v36 + 4));
          v50 = SfnDWORD(v56, (unsigned int)v63, v55, v54, v12, v62);
        }
      }
      v32 = v50;
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v70);
      *(_QWORD *)v61 ^= (*(_DWORD *)v61 ^ v42) & 0x10;
      *(_QWORD *)(v61 + 104) = v64;
    }
  }
  else
  {
    if ( v28 == 3 )
    {
      LODWORD(v61) = *v23;
      LODWORD(v60) = ((unsigned int)v61 >> 1) & 1;
      v29 = fnHkINLPMSG((unsigned __int16)v6 | 0x30000u, a3, a4, v12, *v26, v60, &v61);
    }
    else if ( v28 == 11 )
    {
LABEL_31:
      v29 = fnHkINDWORD((unsigned __int16)v6 | ((unsigned __int16)v28 << 16), a3, (__int64)a4, v12, *v26, v23);
    }
    else
    {
      switch ( v28 )
      {
        case 0xFFFFFFFF:
        case 6u:
          v31 = *v23;
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v70);
          LODWORD(v61) = v31;
          LODWORD(v60) = (v31 >> 1) & 1;
          v32 = fnHkINLPMSG((unsigned __int16)v6 | ((unsigned __int16)v28 << 16), a3, a4, v12, *v26, v60, &v61);
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v70);
          goto LABEL_73;
        case 2u:
          goto LABEL_31;
        case 4u:
          goto LABEL_47;
        case 5u:
          if ( v6 == 3 )
          {
            v29 = fnHkINLPCBTCREATESTRUCT(
                    ((unsigned __int16)v28 << 16) | 3u,
                    a3,
                    a4,
                    v12,
                    ((unsigned int)*v23 >> 1) & 1);
          }
          else if ( v6 )
          {
            if ( v6 == 5 )
            {
              v29 = fnHkINLPCBTACTIVATESTRUCT(((unsigned __int16)v28 << 16) | 5u, a3, a4, v12, *v26);
            }
            else
            {
              if ( v6 != 6 )
                goto LABEL_31;
LABEL_44:
              v29 = (__int64)fnHkINLPMOUSEHOOKSTRUCTEX(
                               (unsigned __int16)v6 | ((unsigned __int16)v28 << 16),
                               a3,
                               a4,
                               v12,
                               *v26,
                               v23);
            }
          }
          else
          {
            v30 = (unsigned __int16)v28 << 16;
LABEL_37:
            v29 = fnHkINLPRECT(v30, a3, a4, v12, *v26);
          }
          break;
        case 7u:
          goto LABEL_44;
        case 9u:
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v70);
          v32 = (__int64)fnHkINLPDEBUGHOOKSTRUCT(
                           (unsigned __int16)v6 | ((unsigned __int16)v28 << 16),
                           a3,
                           (__int64 *)a4,
                           v12,
                           *v26);
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v70);
          goto LABEL_73;
        case 0xAu:
          if ( v6 != 5 )
            goto LABEL_31;
          v30 = ((unsigned __int16)v28 << 16) | 5;
          goto LABEL_37;
        case 0xDu:
          v33 = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          v32 = (__int64)fnHkINLPKBDLLHOOKSTRUCT(
                           (unsigned __int16)v6 | (*(unsigned __int16 *)(v62 + 48) << 16),
                           a3,
                           a4,
                           v12,
                           *v26);
          v34 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
          goto LABEL_41;
        case 0xEu:
          v33 = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          v32 = fnHkINLPMSLLHOOKSTRUCT(
                  (unsigned __int16)v6 | (*(unsigned __int16 *)(v62 + 48) << 16),
                  a3,
                  a4,
                  v12,
                  *v26);
          v34 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
LABEL_41:
          v35 = *((_QWORD *)&v34 + 1) - v33;
          if ( v35 > 0x14 )
            TraceLoggingSlowLowLevelHook(v28, v35, v12);
          goto LABEL_73;
        default:
          KeBugCheckEx(0x164u, 0xFFFFFFFFC00000E5uLL, 0, 0, 0);
      }
    }
    v32 = v29;
  }
LABEL_73:
  W32SetCurrentThreadDpiAwarenessContext(v66);
  return v32;
}

```

## disassembly

```asm
0x140144bf0  push    rbx
0x140144bf2  push    rsi
0x140144bf3  push    rdi
0x140144bf4  push    r12
0x140144bf6  push    r13
0x140144bf8  push    r14
0x140144bfa  push    r15
0x140144bfc  sub     rsp, 100h
0x140144c03  mov     rax, cs:__security_cookie
0x140144c0a  xor     rax, rsp
0x140144c0d  mov     [rsp+138h+var_48], rax
0x140144c15  mov     rsi, r9
0x140144c18  mov     r13, r8
0x140144c1b  mov     r12d, edx
0x140144c1e  mov     rdi, rcx
0x140144c21  mov     [rsp+138h+var_E0], rcx
0x140144c26  xor     r15d, r15d
0x140144c29  mov     [rsp+138h+var_B0], r15
0x140144c31  mov     [rsp+138h+var_B8], r15
0x140144c39  call    cs:__imp_W32GetUserSessionState
0x140144c40  nop     dword ptr [rax+rax+00h]
0x140144c45  mov     rbx, [rax+0A498h]
0x140144c4c  call    cs:__imp_W32GetUserSessionState
0x140144c53  nop     dword ptr [rax+rax+00h]
0x140144c58  cmp     [rax+4C88h], r15d
0x140144c5f  jnz     short loc_140144CB4
0x140144c61  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144c68  nop     dword ptr [rax+rax+00h]
0x140144c6d  mov     ecx, [rax+18h]
0x140144c70  and     cl, 0Ch
0x140144c73  cmp     cl, 8
0x140144c76  jz      short loc_140144CB4
0x140144c78  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144c7f  nop     dword ptr [rax+rax+00h]
0x140144c84  mov     edx, [rax+18h]
0x140144c87  test    dl, 0Ch
0x140144c8a  jz      short loc_140144CB2
0x140144c8c  mov     rcx, rbx; Resource
0x140144c8f  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140144c96  nop     dword ptr [rax+rax+00h]
0x140144c9b  cmp     al, 1
0x140144c9d  jz      short loc_140144CB4
0x140144c9f  mov     rcx, rbx; Resource
0x140144ca2  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140144ca9  nop     dword ptr [rax+rax+00h]
0x140144cae  test    eax, eax
0x140144cb0  jnz     short loc_140144CB4
0x140144cb2  int     2Ch; Windows NT - assertion failure
0x140144cb4  mov     r14, [rdi+38h]
0x140144cb8  test    r14, r14
0x140144cbb  jz      loc_1401453F3
0x140144cc1  cmp     dword ptr [rdi+44h], 0FFFFFFFFh
0x140144cc5  jz      short loc_140144D3A
0x140144cc7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144cce  nop     dword ptr [rax+rax+00h]
0x140144cd3  test    rax, rax
0x140144cd6  jz      short loc_140144CDD
0x140144cd8  mov     rax, [rax]
0x140144cdb  jmp     short loc_140144CE0
0x140144cdd  mov     rax, r15
0x140144ce0  movsxd  rdx, dword ptr [rdi+44h]
0x140144ce4  mov     rax, [rax+1C8h]
0x140144ceb  mov     r14, [rax+rdx*8+190h]
0x140144cf3  add     r14, [rdi+38h]
0x140144cf7  cmp     edx, 0FFFFFFFFh
0x140144cfa  jz      short loc_140144D3A
0x140144cfc  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140144d03  nop     dword ptr [rax+rax+00h]
0x140144d08  test    rax, rax
0x140144d0b  jz      short loc_140144D12
0x140144d0d  mov     rax, [rax]
0x140144d10  jmp     short loc_140144D15
0x140144d12  mov     rax, r15
0x140144d15  mov     rax, [rax+200h]
0x140144d1c  mov     [rsp+138h+var_C8], rax
0x140144d21  mov     rax, [rsp+138h+var_C8]
0x140144d26  or      qword ptr [rax+0E0h], 200h
0x140144d31  jmp     short loc_140144D3A
0x140144d33  xor     eax, eax
0x140144d35  jmp     loc_1401453F5
0x140144d3a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140144d41  nop     dword ptr [rax+rax+00h]
0x140144d46  mov     rcx, rax
0x140144d49  test    rax, rax
0x140144d4c  jz      short loc_140144D56
0x140144d4e  cmp     qword ptr [rax], 0
0x140144d52  cmovz   rcx, r15
0x140144d56  mov     ecx, [rcx+10Ch]
0x140144d5c  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x140144d63  nop     dword ptr [rax+rax+00h]
0x140144d68  mov     [rsp+138h+var_C0], eax
0x140144d6c  lea     rbx, [rdi+40h]
0x140144d70  mov     eax, [rbx]
0x140144d72  test    al, 2
0x140144d74  jz      short loc_140144DA5
0x140144d76  call    cs:__imp_W32GetUserSessionState
0x140144d7d  nop     dword ptr [rax+rax+00h]
0x140144d82  mov     rcx, [rax+4CF8h]
0x140144d89  lea     rdx, [rcx+218h]
0x140144d90  mov     [rsp+138h+var_D8], rdx
0x140144d95  lea     rax, [rcx+210h]
0x140144d9c  lea     r15, [rcx+220h]
0x140144da3  jmp     short loc_140144DD2
0x140144da5  call    cs:__imp_W32GetUserSessionState
0x140144dac  nop     dword ptr [rax+rax+00h]
0x140144db1  mov     rcx, [rax+4CF8h]
0x140144db8  lea     rax, [rcx+2D8h]
0x140144dbf  mov     [rsp+138h+var_D8], rax
0x140144dc4  lea     rax, [rcx+2D0h]
0x140144dcb  lea     r15, [rcx+2E0h]
0x140144dd2  mov     [rsp+138h+var_D0], rax
0x140144dd7  mov     edi, [rdi+30h]
0x140144dda  cmp     edi, 0Ch
0x140144ddd  jz      loc_140145121; jumptable 0000000140144E10 case 4
0x140144de3  cmp     edi, 3
0x140144de6  jz      loc_1401450E1
0x140144dec  cmp     edi, 0Bh
0x140144def  jz      short loc_140144E32; jumptable 0000000140144E10 case 2
0x140144df1  lea     eax, [rdi+1]; switch 16 cases
0x140144df4  cmp     eax, 0Fh
0x140144df7  ja      def_140144E10; jumptable 0000000140144E10 default case, cases 0,1,3,8,11,12
0x140144dfd  cdqe
0x140144dff  lea     rdx, cs:140000000h
0x140144e06  mov     eax, ds:(jpt_140144E10 - 140000000h)[rdx+rax*4]
0x140144e0d  add     rax, rdx
0x140144e10  jmp     rax; switch jump
0x140144e16  cmp     r12d, 3; jumptable 0000000140144E10 case 5
0x140144e1a  jz      short loc_140144E8A
0x140144e1c  mov     ecx, r12d
0x140144e1f  test    r12d, r12d
0x140144e22  jz      short loc_140144E82
0x140144e24  sub     ecx, 5
0x140144e27  jz      short loc_140144E5E
0x140144e29  cmp     ecx, 1
0x140144e2c  jz      loc_14014508D; jumptable 0000000140144E10 case 7
0x140144e32  movzx   ecx, di; jumptable 0000000140144E10 case 2
0x140144e35  shl     ecx, 10h
0x140144e38  movzx   eax, r12w
0x140144e3c  or      ecx, eax
0x140144e3e  mov     [rsp+138h+var_110], rbx
0x140144e43  mov     rax, [r15]
0x140144e46  mov     [rsp+138h+BugCheckParameter4], rax
0x140144e4b  mov     r9, r14
0x140144e4e  mov     r8, rsi
0x140144e51  mov     rdx, r13
0x140144e54  call    fnHkINDWORD
0x140144e59  jmp     loc_1401453DB
0x140144e5e  movzx   ecx, di
0x140144e61  shl     ecx, 10h
0x140144e64  or      ecx, 5
0x140144e67  mov     rax, [r15]
0x140144e6a  mov     [rsp+138h+BugCheckParameter4], rax
0x140144e6f  mov     r9, r14
0x140144e72  mov     r8, rsi
0x140144e75  mov     rdx, r13
0x140144e78  call    fnHkINLPCBTACTIVATESTRUCT
0x140144e7d  jmp     loc_1401453DB
0x140144e82  movzx   ecx, di
0x140144e85  shl     ecx, 10h
0x140144e88  jmp     short loc_140144EC4
0x140144e8a  mov     eax, [rbx]
0x140144e8c  shr     eax, 1
0x140144e8e  and     eax, 1
0x140144e91  movzx   ecx, di
0x140144e94  shl     ecx, 10h
0x140144e97  or      ecx, 3
0x140144e9a  mov     dword ptr [rsp+138h+BugCheckParameter4], eax
0x140144e9e  mov     r9, r14
0x140144ea1  mov     r8, rsi
0x140144ea4  mov     rdx, r13
0x140144ea7  call    fnHkINLPCBTCREATESTRUCT
0x140144eac  jmp     loc_1401453DB
0x140144eb1  cmp     r12d, 5; jumptable 0000000140144E10 case 10
0x140144eb5  jnz     loc_140144E32; jumptable 0000000140144E10 case 2
0x140144ebb  movzx   ecx, di
0x140144ebe  shl     ecx, 10h
0x140144ec1  or      ecx, r12d
0x140144ec4  mov     rax, [r15]
0x140144ec7  mov     [rsp+138h+BugCheckParameter4], rax
0x140144ecc  mov     r9, r14
0x140144ecf  mov     r8, rsi
0x140144ed2  mov     rdx, r13
0x140144ed5  call    fnHkINLPRECT
0x140144eda  jmp     loc_1401453DB
0x140144edf  mov     ebx, [rbx]; jumptable 0000000140144E10 cases -1,6
0x140144ee1  lea     rcx, [rsp+138h+var_80]
0x140144ee9  call    ??0?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(void)
0x140144eee  mov     dword ptr [rsp+138h+var_E8], ebx
0x140144ef2  shr     ebx, 1
0x140144ef4  and     ebx, 1
0x140144ef7  movzx   ecx, di
0x140144efa  shl     ecx, 10h
0x140144efd  movzx   eax, r12w
0x140144f01  or      ecx, eax
0x140144f03  lea     rax, [rsp+138h+var_E8]
0x140144f08  mov     [rsp+138h+var_108], rax
0x140144f0d  mov     dword ptr [rsp+138h+var_110], ebx
0x140144f11  mov     rax, [r15]
0x140144f14  mov     [rsp+138h+BugCheckParameter4], rax
0x140144f19  mov     r9, r14
0x140144f1c  mov     r8, rsi
0x140144f1f  mov     rdx, r13
0x140144f22  call    fnHkINLPMSG
0x140144f27  mov     rsi, rax
0x140144f2a  lea     rcx, [rsp+138h+var_80]
0x140144f32  call    ??1?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(void)
0x140144f37  jmp     loc_1401453DE
0x140144f3c  lea     rcx, [rsp+138h+var_80]; jumptable 0000000140144E10 case 9
0x140144f44  call    ??0?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(void)
0x140144f49  movzx   ecx, di
0x140144f4c  shl     ecx, 10h
0x140144f4f  movzx   eax, r12w
0x140144f53  or      ecx, eax
0x140144f55  mov     rax, [r15]
0x140144f58  mov     [rsp+138h+BugCheckParameter4], rax
0x140144f5d  mov     r9, r14
0x140144f60  mov     r8, rsi
0x140144f63  mov     rdx, r13
0x140144f66  call    fnHkINLPDEBUGHOOKSTRUCT
0x140144f6b  mov     rsi, rax
0x140144f6e  lea     rcx, [rsp+138h+var_80]
0x140144f76  call    ??1?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(void)
0x140144f7b  jmp     loc_1401453DE
0x140144f80  mov     rax, 0FFFFF78000000004h; jumptable 0000000140144E10 case 13
0x140144f8a  mov     ecx, [rax]
0x140144f8c  mov     rax, 0FFFFF78000000320h
0x140144f96  mov     rax, [rax]
0x140144f99  shl     rax, 8
0x140144f9d  shl     rcx, 20h
0x140144fa1  mul     rcx
0x140144fa4  mov     rbx, rdx
0x140144fa7  mov     rdx, [rsp+138h+var_E0]
0x140144fac  movzx   ecx, word ptr [rdx+30h]
0x140144fb0  shl     ecx, 10h
0x140144fb3  movzx   eax, r12w
0x140144fb7  or      ecx, eax
0x140144fb9  mov     rax, [r15]
0x140144fbc  mov     [rsp+138h+BugCheckParameter4], rax
0x140144fc1  mov     r9, r14
0x140144fc4  mov     r8, rsi
0x140144fc7  mov     rdx, r13
0x140144fca  call    fnHkINLPKBDLLHOOKSTRUCT
0x140144fcf  mov     rsi, rax
0x140144fd2  mov     rax, 0FFFFF78000000004h
0x140144fdc  mov     edx, [rax]
0x140144fde  mov     rax, 0FFFFF78000000320h
0x140144fe8  mov     rax, [rax]
0x140144feb  shl     rax, 8
0x140144fef  shl     rdx, 20h
0x140144ff3  mul     rdx
0x140144ff6  sub     rdx, rbx; unsigned __int64
0x140144ff9  cmp     rdx, 14h
0x140144ffd  jbe     loc_1401453DE
0x140145003  mov     r8, r14; unsigned __int64
0x140145006  mov     ecx, edi; unsigned int
0x140145008  call    ?TraceLoggingSlowLowLevelHook@@YAXI_K0@Z; TraceLoggingSlowLowLevelHook(uint,unsigned __int64,unsigned __int64)
0x14014500d  jmp     loc_1401453DE
0x140145012  mov     rax, 0FFFFF78000000004h; jumptable 0000000140144E10 case 14
0x14014501c  mov     ecx, [rax]
0x14014501e  mov     rax, 0FFFFF78000000320h
0x140145028  mov     rax, [rax]
0x14014502b  shl     rax, 8
0x14014502f  shl     rcx, 20h
0x140145033  mul     rcx
0x140145036  mov     rbx, rdx
0x140145039  mov     rdx, [rsp+138h+var_E0]
0x14014503e  movzx   ecx, word ptr [rdx+30h]
0x140145042  shl     ecx, 10h
0x140145045  movzx   eax, r12w
0x140145049  or      ecx, eax
0x14014504b  mov     rax, [r15]
0x14014504e  mov     [rsp+138h+BugCheckParameter4], rax
0x140145053  mov     r9, r14
0x140145056  mov     r8, rsi
0x140145059  mov     rdx, r13
0x14014505c  call    fnHkINLPMSLLHOOKSTRUCT
0x140145061  mov     rsi, rax
0x140145064  mov     rax, 0FFFFF78000000004h
0x14014506e  mov     ecx, [rax]
0x140145070  mov     rax, 0FFFFF78000000320h
0x14014507a  mov     rax, [rax]
0x14014507d  shl     rax, 8
0x140145081  shl     rcx, 20h
0x140145085  mul     rcx
0x140145088  jmp     loc_140144FF6
0x14014508d  movzx   ecx, di; jumptable 0000000140144E10 case 7
0x140145090  shl     ecx, 10h
0x140145093  movzx   eax, r12w
0x140145097  or      ecx, eax
0x140145099  mov     [rsp+138h+var_110], rbx
0x14014509e  mov     rax, [r15]
0x1401450a1  mov     [rsp+138h+BugCheckParameter4], rax
0x1401450a6  mov     r9, r14
0x1401450a9  mov     r8, rsi
0x1401450ac  mov     rdx, r13
0x1401450af  call    fnHkINLPMOUSEHOOKSTRUCTEX
0x1401450b4  jmp     loc_1401453DB
0x1401450b9  mov     [rsp+138h+BugCheckParameter4], 0; jumptable 0000000140144E10 default case, cases 0,1,3,8,11,12
0x1401450c2  xor     r9d, r9d; BugCheckParameter3
0x1401450c5  xor     r8d, r8d; BugCheckParameter2
  ... truncated ...
```
