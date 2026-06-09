# xxxHkCallHook

- ea: `0x14014ec30`
- end: `0x14014f459`
- name: `xxxHkCallHook`
- size: `2089`
- prototype: ``
- caller_count: `1`
- callee_count: `81`
- tags: `loader_planting`

## callers

- `0x1400c459c`

## callees

- `0x140010a10`
- `0x1400b7978`
- `0x1400b7e20`
- `0x1400b8080`
- `0x1400b82d0`
- `0x1400b8a30`
- `0x1400b8e44`
- `0x1400b90a0`
- `0x1400b9320`
- `0x1400b9610`
- `0x1400b99d0`
- `0x1400ba1d0`
- `0x1400bbb50`
- `0x1400bcbd0`
- `0x1400bdb20`
- `0x1400be040`
- `0x1400d2028`
- `0x1400d28d0`
- `0x1400d2df0`
- `0x1400d2e50`
- `0x1400d2fd0`
- `0x1400d3490`
- `0x1400d42e0`
- `0x1400d43a0`
- `0x14014ec30`
- `0x14017e910`
- `0x140183a90`
- `0x1401a0cb0`
- `0x1401a0f90`
- `0x1401a1290`
- `0x1401a16f0`
- `0x1401a19f0`
- `0x1401b1f2c`
- `0x1401d2fc0`
- `0x1401da8a8`
- `0x1401e06b0`
- `0x1401e0c60`
- `0x1401e5f30`
- `0x1401e89d0`
- `0x1401ea280`
- `0x1401eed70`
- `0x1401fe1f0`
- `0x140201580`
- `0x1402025b0`
- `0x140204290`
- `0x140207110`
- `0x140209bf0`
- `0x14020c350`
- `0x14020d270`
- `0x140211320`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14014ece2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14014ece2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14014eccf`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14014eccf`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014ed7a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14014ed7a`
- `ntoskrnl!KeBugCheckEx` at `0x14014f114`
- `ntoskrnl!KeBugCheckEx` at `0x14014f114`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014eca1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ecb8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ed07`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ed3c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014f1a8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014eca1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ecb8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ed07`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014ed3c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014f1a8`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x14014ed9c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x14014f422`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x14014ed9c`
- `win32kbase!W32SetCurrentThreadDpiAwarenessContext` at `0x14014f422`
- `win32kbase!_HMObjectFromHandle` at `0x14014f280`
- `win32kbase!_HMObjectFromHandle` at `0x14014f2e7`
- `win32kbase!_HMObjectFromHandle` at `0x14014f32c`
- `win32kbase!_HMObjectFromHandle` at `0x14014f391`
- `win32kbase!_HMObjectFromHandle` at `0x14014f280`
- `win32kbase!_HMObjectFromHandle` at `0x14014f2e7`
- `win32kbase!_HMObjectFromHandle` at `0x14014f32c`
- `win32kbase!_HMObjectFromHandle` at `0x14014f391`
- `WIN32K!W32GetUserSessionState` at `0x14014ec79`
- `WIN32K!W32GetUserSessionState` at `0x14014ec8c`
- `WIN32K!W32GetUserSessionState` at `0x14014edb6`
- `WIN32K!W32GetUserSessionState` at `0x14014ede5`
- `WIN32K!W32GetUserSessionState` at `0x14014ec79`
- `WIN32K!W32GetUserSessionState` at `0x14014ec8c`
- `WIN32K!W32GetUserSessionState` at `0x14014edb6`
- `WIN32K!W32GetUserSessionState` at `0x14014ede5`

## pseudocode

```c
__int64 __fastcall xxxHkCallHook(__int64 a1, int a2, __int64 a3, __int128 *a4)
{
  struct _ERESOURCE *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int64 v11; // r14
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rax
  __int64 v17; // rax
  _QWORD *CurrentProcessWin32Process; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  unsigned int *v21; // rbx
  __int64 *v22; // rcx
  __int64 *v23; // rax
  __int64 *v24; // r15
  __int64 *v25; // rcx
  unsigned int v26; // edi
  __int64 v27; // rax
  int v28; // ecx
  unsigned int v29; // ebx
  __int64 v30; // rsi
  __int64 v31; // rbx
  unsigned __int128 v32; // rax
  unsigned __int64 v33; // rdx
  __int128 *v34; // r12
  __int128 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rsi
  _QWORD *v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // r15d
  unsigned int v41; // r13d
  int v42; // ebx
  int v43; // r13d
  unsigned int v44; // r12d
  __int64 v45; // rbx
  __int64 v46; // rdi
  int v47; // eax
  __int64 v48; // rax
  __int64 (__fastcall *v49)(int, int, int, int, __int64, __int64); // rsi
  __int64 v50; // rax
  __int64 *v51; // rcx
  __int64 v52; // rbx
  __int64 v53; // rdi
  int v54; // eax
  __int64 (__fastcall *v55)(int, int, int, int, __int64, __int64); // rsi
  __int64 v56; // rax
  __int64 v58; // [rsp+28h] [rbp-110h]
  __int64 v59; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v60; // [rsp+58h] [rbp-E0h]
  __int64 *v61; // [rsp+60h] [rbp-D8h]
  __int64 *v62; // [rsp+68h] [rbp-D0h]
  __int64 v63; // [rsp+70h] [rbp-C8h]
  unsigned int v64; // [rsp+78h] [rbp-C0h]
  __int64 v65; // [rsp+80h] [rbp-B8h]
  __int64 *v66; // [rsp+88h] [rbp-B0h]
  __int128 *v67; // [rsp+90h] [rbp-A8h]
  _BYTE v68[56]; // [rsp+B8h] [rbp-80h] BYREF

  v60 = a1;
  v66 = 0;
  v65 = 0;
  v8 = *(struct _ERESOURCE **)(W32GetUserSessionState(a1) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v9) + 19592) )
  {
    v10 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v10) + 24);
    LOBYTE(v10) = v10 & 0xC;
    if ( (_BYTE)v10 != 8
      && ((*(_DWORD *)(PsGetCurrentThreadWin32Thread(v10) + 24) & 0xC) == 0
       || ExIsResourceAcquiredExclusiveLite(v8) != 1 && !ExIsResourceAcquiredSharedLite(v8)) )
    {
      __int2c();
    }
  }
  v11 = *(_QWORD *)(a1 + 56);
  if ( !v11 )
    return 0;
  if ( *(_DWORD *)(a1 + 68) != -1 )
  {
    CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread(v10);
    v14 = CurrentThreadWin32Thread ? *CurrentThreadWin32Thread : 0LL;
    v15 = *(int *)(a1 + 68);
    v11 = *(_QWORD *)(a1 + 56) + *(_QWORD *)(*(_QWORD *)(v14 + 456) + 8 * v15 + 400);
    if ( (_DWORD)v15 != -1 )
    {
      v16 = (__int64 *)PsGetCurrentThreadWin32Thread(v13);
      if ( v16 )
        v17 = *v16;
      else
        v17 = 0;
      v63 = *(_QWORD *)(v17 + 512);
      *(_QWORD *)(v63 + 224) |= 0x200uLL;
    }
  }
  CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process();
  v19 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
    v19 = 0;
  v64 = W32SetCurrentThreadDpiAwarenessContext(*((unsigned int *)v19 + 67));
  v21 = (unsigned int *)(a1 + 64);
  if ( (*(_DWORD *)(a1 + 64) & 2) != 0 )
  {
    v22 = *(__int64 **)(W32GetUserSessionState(v20) + 19704);
    v61 = v22 + 67;
    v23 = v22 + 66;
    v24 = v22 + 68;
  }
  else
  {
    v25 = *(__int64 **)(W32GetUserSessionState(v20) + 19704);
    v61 = v25 + 91;
    v23 = v25 + 90;
    v24 = v25 + 92;
  }
  v62 = v23;
  v26 = *(_DWORD *)(a1 + 48);
  if ( v26 == 12 )
  {
LABEL_47:
    v34 = 0;
    if ( v26 != 4 )
      v34 = a4;
    v35 = a4;
    if ( v26 != 4 )
      v35 = 0;
    v67 = v35;
    v36 = 32;
    if ( v26 != 4 )
      v36 = 40;
    v37 = *(_QWORD *)((char *)a4 + v36);
    v63 = v37;
    if ( v37 && (*(_DWORD *)(v37 + 84) & 5) != 0 )
    {
      v30 = 0;
    }
    else
    {
      v38 = (_QWORD *)PsGetCurrentThreadWin32Thread(40);
      if ( v38 )
        v38 = (_QWORD *)*v38;
      v59 = v38[64];
      v39 = v60;
      if ( *(_DWORD *)(v60 + 48) == 4 )
      {
        v60 = *v62;
      }
      else
      {
        v60 = *v61;
        *(_QWORD *)(v59 + 104) = *(_QWORD *)v34;
      }
      v40 = *(_DWORD *)v59 & 0x10;
      v65 = v40;
      v62 = *(__int64 **)(v59 + 104);
      v66 = v62;
      if ( a3 )
        *(_QWORD *)v59 |= 0x10uLL;
      else
        *(_QWORD *)v59 &= ~0x10uLL;
      v41 = *v21;
      v42 = *(_DWORD *)(v39 + 48);
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v68);
      v43 = v41 & 2;
      if ( v42 == 4 )
      {
        v44 = *((_DWORD *)v67 + 4);
        v45 = *(_QWORD *)v67;
        v46 = *((_QWORD *)v67 + 1);
        if ( (v44 & 0x1FFFF) < 0x400 )
        {
          v49 = gapfnScSendMessage[(unsigned __int8)MessageTable[(unsigned __int16)v44]];
          v50 = _HMObjectFromHandle(*((_QWORD *)v67 + 3));
          v48 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, unsigned __int64, __int64, unsigned int, __int64))v49)(
                  v50,
                  v44,
                  v46,
                  v45,
                  v11,
                  v60,
                  (unsigned int)(v43 != 0) + 2,
                  v63);
        }
        else
        {
          v47 = _HMObjectFromHandle(*((_QWORD *)v67 + 3));
          v48 = SfnDWORD(v47, v44, v46, v45, v11, v60);
        }
      }
      else
      {
        v51 = (__int64 *)*((unsigned int *)v34 + 6);
        v61 = v51;
        v52 = *((_QWORD *)v34 + 1);
        v53 = *((_QWORD *)v34 + 2);
        if ( ((unsigned int)v51 & 0x1FFFF) < 0x400 )
        {
          v55 = gapfnScSendMessage[(unsigned __int8)MessageTable[(unsigned __int16)v51]];
          v56 = _HMObjectFromHandle(*((_QWORD *)v34 + 4));
          v48 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, unsigned __int64, __int64, unsigned int, __int64))v55)(
                  v56,
                  (unsigned int)v61,
                  v53,
                  v52,
                  v11,
                  v60,
                  (unsigned int)(v43 != 0) + 2,
                  v63);
        }
        else
        {
          v54 = _HMObjectFromHandle(*((_QWORD *)v34 + 4));
          v48 = SfnDWORD(v54, (_DWORD)v61, v53, v52, v11, v60);
        }
      }
      v30 = v48;
      SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v68);
      *(_QWORD *)v59 ^= (*(_DWORD *)v59 ^ v40) & 0x10;
      *(_QWORD *)(v59 + 104) = v62;
    }
  }
  else
  {
    if ( v26 == 3 )
    {
      LODWORD(v59) = *v21;
      LODWORD(v58) = ((unsigned int)v59 >> 1) & 1;
      v27 = fnHkINLPMSG((unsigned __int16)a2 | 0x30000u, a3, a4, v11, *v24, v58, &v59);
    }
    else if ( v26 == 11 )
    {
LABEL_31:
      v27 = fnHkINDWORD((unsigned __int16)a2 | ((unsigned __int16)v26 << 16), a3, (_DWORD)a4, v11, *v24, (__int64)v21);
    }
    else
    {
      switch ( v26 )
      {
        case 0xFFFFFFFF:
        case 6u:
          v29 = *v21;
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v68);
          LODWORD(v59) = v29;
          LODWORD(v58) = (v29 >> 1) & 1;
          v30 = fnHkINLPMSG((unsigned __int16)a2 | ((unsigned __int16)v26 << 16), a3, a4, v11, *v24, v58, &v59);
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v68);
          goto LABEL_73;
        case 2u:
          goto LABEL_31;
        case 4u:
          goto LABEL_47;
        case 5u:
          if ( a2 == 3 )
          {
            v27 = fnHkINLPCBTCREATESTRUCT(((unsigned __int16)v26 << 16) | 3u, a3, (_DWORD)a4, v11, (*v21 >> 1) & 1);
          }
          else if ( a2 )
          {
            if ( a2 == 5 )
            {
              v27 = fnHkINLPCBTACTIVATESTRUCT(((unsigned __int16)v26 << 16) | 5u, a3, (_DWORD)a4, v11, *v24);
            }
            else
            {
              if ( a2 != 6 )
                goto LABEL_31;
LABEL_44:
              v27 = fnHkINLPMOUSEHOOKSTRUCTEX(
                      (unsigned __int16)a2 | ((unsigned __int16)v26 << 16),
                      a3,
                      (_DWORD)a4,
                      v11,
                      *v24,
                      (__int64)v21);
            }
          }
          else
          {
            v28 = (unsigned __int16)v26 << 16;
LABEL_37:
            v27 = fnHkINLPRECT(v28, a3, (_DWORD)a4, v11, *v24);
          }
          break;
        case 7u:
          goto LABEL_44;
        case 9u:
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(v68);
          v30 = fnHkINLPDEBUGHOOKSTRUCT((unsigned __int16)a2 | ((unsigned __int16)v26 << 16), a3, a4, v11, *v24);
          SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(v68);
          goto LABEL_73;
        case 0xAu:
          if ( a2 != 5 )
            goto LABEL_31;
          v28 = ((unsigned __int16)v26 << 16) | 5;
          goto LABEL_37;
        case 0xDu:
          v31 = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          v30 = fnHkINLPKBDLLHOOKSTRUCT(
                  (unsigned __int16)a2 | (*(unsigned __int16 *)(v60 + 48) << 16),
                  a3,
                  (_DWORD)a4,
                  v11,
                  *v24);
          v32 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
          goto LABEL_41;
        case 0xEu:
          v31 = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          v30 = fnHkINLPMSLLHOOKSTRUCT(
                  (unsigned __int16)a2 | (*(unsigned __int16 *)(v60 + 48) << 16),
                  a3,
                  (_DWORD)a4,
                  v11,
                  *v24);
          v32 = ((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
              * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8);
LABEL_41:
          v33 = *((_QWORD *)&v32 + 1) - v31;
          if ( v33 > 0x14 )
            TraceLoggingSlowLowLevelHook(v26, v33, v11);
          goto LABEL_73;
        default:
          KeBugCheckEx(0x164u, 0xFFFFFFFFC00000E5uLL, 0, 0, 0);
      }
    }
    v30 = v27;
  }
LABEL_73:
  W32SetCurrentThreadDpiAwarenessContext(v64);
  return v30;
}

```

## disassembly

```asm
0x14014ec30  push    rbx
0x14014ec32  push    rsi
0x14014ec33  push    rdi
0x14014ec34  push    r12
0x14014ec36  push    r13
0x14014ec38  push    r14
0x14014ec3a  push    r15
0x14014ec3c  sub     rsp, 100h
0x14014ec43  mov     rax, cs:__security_cookie
0x14014ec4a  xor     rax, rsp
0x14014ec4d  mov     [rsp+138h+var_48], rax
0x14014ec55  mov     rsi, r9
0x14014ec58  mov     r13, r8
0x14014ec5b  mov     r12d, edx
0x14014ec5e  mov     rdi, rcx
0x14014ec61  mov     [rsp+138h+var_E0], rcx
0x14014ec66  xor     r15d, r15d
0x14014ec69  mov     [rsp+138h+var_B0], r15
0x14014ec71  mov     [rsp+138h+var_B8], r15
0x14014ec79  call    cs:__imp_W32GetUserSessionState
0x14014ec80  nop     dword ptr [rax+rax+00h]
0x14014ec85  mov     rbx, [rax+0A498h]
0x14014ec8c  call    cs:__imp_W32GetUserSessionState
0x14014ec93  nop     dword ptr [rax+rax+00h]
0x14014ec98  cmp     [rax+4C88h], r15d
0x14014ec9f  jnz     short loc_14014ECF4
0x14014eca1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014eca8  nop     dword ptr [rax+rax+00h]
0x14014ecad  mov     ecx, [rax+18h]
0x14014ecb0  and     cl, 0Ch
0x14014ecb3  cmp     cl, 8
0x14014ecb6  jz      short loc_14014ECF4
0x14014ecb8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014ecbf  nop     dword ptr [rax+rax+00h]
0x14014ecc4  mov     edx, [rax+18h]
0x14014ecc7  test    dl, 0Ch
0x14014ecca  jz      short loc_14014ECF2
0x14014eccc  mov     rcx, rbx; Resource
0x14014eccf  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14014ecd6  nop     dword ptr [rax+rax+00h]
0x14014ecdb  cmp     al, 1
0x14014ecdd  jz      short loc_14014ECF4
0x14014ecdf  mov     rcx, rbx; Resource
0x14014ece2  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14014ece9  nop     dword ptr [rax+rax+00h]
0x14014ecee  test    eax, eax
0x14014ecf0  jnz     short loc_14014ECF4
0x14014ecf2  int     2Ch; Windows NT - assertion failure
0x14014ecf4  mov     r14, [rdi+38h]
0x14014ecf8  test    r14, r14
0x14014ecfb  jz      loc_14014F433
0x14014ed01  cmp     dword ptr [rdi+44h], 0FFFFFFFFh
0x14014ed05  jz      short loc_14014ED7A
0x14014ed07  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014ed0e  nop     dword ptr [rax+rax+00h]
0x14014ed13  test    rax, rax
0x14014ed16  jz      short loc_14014ED1D
0x14014ed18  mov     rax, [rax]
0x14014ed1b  jmp     short loc_14014ED20
0x14014ed1d  mov     rax, r15
0x14014ed20  movsxd  rdx, dword ptr [rdi+44h]
0x14014ed24  mov     rax, [rax+1C8h]
0x14014ed2b  mov     r14, [rax+rdx*8+190h]
0x14014ed33  add     r14, [rdi+38h]
0x14014ed37  cmp     edx, 0FFFFFFFFh
0x14014ed3a  jz      short loc_14014ED7A
0x14014ed3c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014ed43  nop     dword ptr [rax+rax+00h]
0x14014ed48  test    rax, rax
0x14014ed4b  jz      short loc_14014ED52
0x14014ed4d  mov     rax, [rax]
0x14014ed50  jmp     short loc_14014ED55
0x14014ed52  mov     rax, r15
0x14014ed55  mov     rax, [rax+200h]
0x14014ed5c  mov     [rsp+138h+var_C8], rax
0x14014ed61  mov     rax, [rsp+138h+var_C8]
0x14014ed66  or      qword ptr [rax+0E0h], 200h
0x14014ed71  jmp     short loc_14014ED7A
0x14014ed73  xor     eax, eax
0x14014ed75  jmp     loc_14014F435
0x14014ed7a  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14014ed81  nop     dword ptr [rax+rax+00h]
0x14014ed86  mov     rcx, rax
0x14014ed89  test    rax, rax
0x14014ed8c  jz      short loc_14014ED96
0x14014ed8e  cmp     qword ptr [rax], 0
0x14014ed92  cmovz   rcx, r15
0x14014ed96  mov     ecx, [rcx+10Ch]
0x14014ed9c  call    cs:__imp_W32SetCurrentThreadDpiAwarenessContext
0x14014eda3  nop     dword ptr [rax+rax+00h]
0x14014eda8  mov     [rsp+138h+var_C0], eax
0x14014edac  lea     rbx, [rdi+40h]
0x14014edb0  mov     eax, [rbx]
0x14014edb2  test    al, 2
0x14014edb4  jz      short loc_14014EDE5
0x14014edb6  call    cs:__imp_W32GetUserSessionState
0x14014edbd  nop     dword ptr [rax+rax+00h]
0x14014edc2  mov     rcx, [rax+4CF8h]
0x14014edc9  lea     rdx, [rcx+218h]
0x14014edd0  mov     [rsp+138h+var_D8], rdx
0x14014edd5  lea     rax, [rcx+210h]
0x14014eddc  lea     r15, [rcx+220h]
0x14014ede3  jmp     short loc_14014EE12
0x14014ede5  call    cs:__imp_W32GetUserSessionState
0x14014edec  nop     dword ptr [rax+rax+00h]
0x14014edf1  mov     rcx, [rax+4CF8h]
0x14014edf8  lea     rax, [rcx+2D8h]
0x14014edff  mov     [rsp+138h+var_D8], rax
0x14014ee04  lea     rax, [rcx+2D0h]
0x14014ee0b  lea     r15, [rcx+2E0h]
0x14014ee12  mov     [rsp+138h+var_D0], rax
0x14014ee17  mov     edi, [rdi+30h]
0x14014ee1a  cmp     edi, 0Ch
0x14014ee1d  jz      loc_14014F161; jumptable 000000014014EE50 case 4
0x14014ee23  cmp     edi, 3
0x14014ee26  jz      loc_14014F121
0x14014ee2c  cmp     edi, 0Bh
0x14014ee2f  jz      short loc_14014EE72; jumptable 000000014014EE50 case 2
0x14014ee31  lea     eax, [rdi+1]; switch 16 cases
0x14014ee34  cmp     eax, 0Fh
0x14014ee37  ja      def_14014EE50; jumptable 000000014014EE50 default case, cases 0,1,3,8,11,12
0x14014ee3d  cdqe
0x14014ee3f  lea     rdx, cs:140000000h
0x14014ee46  mov     eax, ds:(jpt_14014EE50 - 140000000h)[rdx+rax*4]
0x14014ee4d  add     rax, rdx
0x14014ee50  jmp     rax; switch jump
0x14014ee56  cmp     r12d, 3; jumptable 000000014014EE50 case 5
0x14014ee5a  jz      short loc_14014EECA
0x14014ee5c  mov     ecx, r12d
0x14014ee5f  test    r12d, r12d
0x14014ee62  jz      short loc_14014EEC2
0x14014ee64  sub     ecx, 5
0x14014ee67  jz      short loc_14014EE9E
0x14014ee69  cmp     ecx, 1
0x14014ee6c  jz      loc_14014F0CD; jumptable 000000014014EE50 case 7
0x14014ee72  movzx   ecx, di; jumptable 000000014014EE50 case 2
0x14014ee75  shl     ecx, 10h
0x14014ee78  movzx   eax, r12w
0x14014ee7c  or      ecx, eax
0x14014ee7e  mov     [rsp+138h+var_110], rbx
0x14014ee83  mov     rax, [r15]
0x14014ee86  mov     [rsp+138h+BugCheckParameter4], rax
0x14014ee8b  mov     r9, r14
0x14014ee8e  mov     r8, rsi
0x14014ee91  mov     rdx, r13
0x14014ee94  call    fnHkINDWORD
0x14014ee99  jmp     loc_14014F41B
0x14014ee9e  movzx   ecx, di
0x14014eea1  shl     ecx, 10h
0x14014eea4  or      ecx, 5
0x14014eea7  mov     rax, [r15]
0x14014eeaa  mov     [rsp+138h+BugCheckParameter4], rax
0x14014eeaf  mov     r9, r14
0x14014eeb2  mov     r8, rsi
0x14014eeb5  mov     rdx, r13
0x14014eeb8  call    fnHkINLPCBTACTIVATESTRUCT
0x14014eebd  jmp     loc_14014F41B
0x14014eec2  movzx   ecx, di
0x14014eec5  shl     ecx, 10h
0x14014eec8  jmp     short loc_14014EF04
0x14014eeca  mov     eax, [rbx]
0x14014eecc  shr     eax, 1
0x14014eece  and     eax, 1
0x14014eed1  movzx   ecx, di
0x14014eed4  shl     ecx, 10h
0x14014eed7  or      ecx, 3
0x14014eeda  mov     dword ptr [rsp+138h+BugCheckParameter4], eax
0x14014eede  mov     r9, r14
0x14014eee1  mov     r8, rsi
0x14014eee4  mov     rdx, r13
0x14014eee7  call    fnHkINLPCBTCREATESTRUCT
0x14014eeec  jmp     loc_14014F41B
0x14014eef1  cmp     r12d, 5; jumptable 000000014014EE50 case 10
0x14014eef5  jnz     loc_14014EE72; jumptable 000000014014EE50 case 2
0x14014eefb  movzx   ecx, di
0x14014eefe  shl     ecx, 10h
0x14014ef01  or      ecx, r12d
0x14014ef04  mov     rax, [r15]
0x14014ef07  mov     [rsp+138h+BugCheckParameter4], rax
0x14014ef0c  mov     r9, r14
0x14014ef0f  mov     r8, rsi
0x14014ef12  mov     rdx, r13
0x14014ef15  call    fnHkINLPRECT
0x14014ef1a  jmp     loc_14014F41B
0x14014ef1f  mov     ebx, [rbx]; jumptable 000000014014EE50 cases -1,6
0x14014ef21  lea     rcx, [rsp+138h+var_80]
0x14014ef29  call    ??0?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(void)
0x14014ef2e  mov     dword ptr [rsp+138h+var_E8], ebx
0x14014ef32  shr     ebx, 1
0x14014ef34  and     ebx, 1
0x14014ef37  movzx   ecx, di
0x14014ef3a  shl     ecx, 10h
0x14014ef3d  movzx   eax, r12w
0x14014ef41  or      ecx, eax
0x14014ef43  lea     rax, [rsp+138h+var_E8]
0x14014ef48  mov     [rsp+138h+var_108], rax
0x14014ef4d  mov     dword ptr [rsp+138h+var_110], ebx
0x14014ef51  mov     rax, [r15]
0x14014ef54  mov     [rsp+138h+BugCheckParameter4], rax
0x14014ef59  mov     r9, r14
0x14014ef5c  mov     r8, rsi
0x14014ef5f  mov     rdx, r13
0x14014ef62  call    fnHkINLPMSG
0x14014ef67  mov     rsi, rax
0x14014ef6a  lea     rcx, [rsp+138h+var_80]
0x14014ef72  call    ??1?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(void)
0x14014ef77  jmp     loc_14014F41E
0x14014ef7c  lea     rcx, [rsp+138h+var_80]; jumptable 000000014014EE50 case 9
0x14014ef84  call    ??0?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::UnlockObjectLock<>(void)
0x14014ef89  movzx   ecx, di
0x14014ef8c  shl     ecx, 10h
0x14014ef8f  movzx   eax, r12w
0x14014ef93  or      ecx, eax
0x14014ef95  mov     rax, [r15]
0x14014ef98  mov     [rsp+138h+BugCheckParameter4], rax
0x14014ef9d  mov     r9, r14
0x14014efa0  mov     r8, rsi
0x14014efa3  mov     rdx, r13
0x14014efa6  call    fnHkINLPDEBUGHOOKSTRUCT
0x14014efab  mov     rsi, rax
0x14014efae  lea     rcx, [rsp+138h+var_80]
0x14014efb6  call    ??1?$UnlockObjectLock@$$V@?$UnlockDomainExclusive@$$V@?$UnlockDomainShared@VDLT_HOOK@@@SharedUserCritOnly@@QEAA@XZ; SharedUserCritOnly::UnlockDomainShared<DLT_HOOK>::UnlockDomainExclusive<>::UnlockObjectLock<>::~UnlockObjectLock<>(void)
0x14014efbb  jmp     loc_14014F41E
0x14014efc0  mov     rax, 0FFFFF78000000004h; jumptable 000000014014EE50 case 13
0x14014efca  mov     ecx, [rax]
0x14014efcc  mov     rax, 0FFFFF78000000320h
0x14014efd6  mov     rax, [rax]
0x14014efd9  shl     rax, 8
0x14014efdd  shl     rcx, 20h
0x14014efe1  mul     rcx
0x14014efe4  mov     rbx, rdx
0x14014efe7  mov     rdx, [rsp+138h+var_E0]
0x14014efec  movzx   ecx, word ptr [rdx+30h]
0x14014eff0  shl     ecx, 10h
0x14014eff3  movzx   eax, r12w
0x14014eff7  or      ecx, eax
0x14014eff9  mov     rax, [r15]
0x14014effc  mov     [rsp+138h+BugCheckParameter4], rax
0x14014f001  mov     r9, r14
0x14014f004  mov     r8, rsi
0x14014f007  mov     rdx, r13
0x14014f00a  call    fnHkINLPKBDLLHOOKSTRUCT
0x14014f00f  mov     rsi, rax
0x14014f012  mov     rax, 0FFFFF78000000004h
0x14014f01c  mov     edx, [rax]
0x14014f01e  mov     rax, 0FFFFF78000000320h
0x14014f028  mov     rax, [rax]
0x14014f02b  shl     rax, 8
0x14014f02f  shl     rdx, 20h
0x14014f033  mul     rdx
0x14014f036  sub     rdx, rbx; unsigned __int64
0x14014f039  cmp     rdx, 14h
0x14014f03d  jbe     loc_14014F41E
0x14014f043  mov     r8, r14; unsigned __int64
0x14014f046  mov     ecx, edi; unsigned int
0x14014f048  call    ?TraceLoggingSlowLowLevelHook@@YAXI_K0@Z; TraceLoggingSlowLowLevelHook(uint,unsigned __int64,unsigned __int64)
0x14014f04d  jmp     loc_14014F41E
0x14014f052  mov     rax, 0FFFFF78000000004h; jumptable 000000014014EE50 case 14
0x14014f05c  mov     ecx, [rax]
0x14014f05e  mov     rax, 0FFFFF78000000320h
0x14014f068  mov     rax, [rax]
0x14014f06b  shl     rax, 8
0x14014f06f  shl     rcx, 20h
0x14014f073  mul     rcx
0x14014f076  mov     rbx, rdx
0x14014f079  mov     rdx, [rsp+138h+var_E0]
0x14014f07e  movzx   ecx, word ptr [rdx+30h]
0x14014f082  shl     ecx, 10h
0x14014f085  movzx   eax, r12w
0x14014f089  or      ecx, eax
0x14014f08b  mov     rax, [r15]
0x14014f08e  mov     [rsp+138h+BugCheckParameter4], rax
0x14014f093  mov     r9, r14
0x14014f096  mov     r8, rsi
0x14014f099  mov     rdx, r13
0x14014f09c  call    fnHkINLPMSLLHOOKSTRUCT
0x14014f0a1  mov     rsi, rax
0x14014f0a4  mov     rax, 0FFFFF78000000004h
0x14014f0ae  mov     ecx, [rax]
0x14014f0b0  mov     rax, 0FFFFF78000000320h
0x14014f0ba  mov     rax, [rax]
0x14014f0bd  shl     rax, 8
0x14014f0c1  shl     rcx, 20h
0x14014f0c5  mul     rcx
0x14014f0c8  jmp     loc_14014F036
0x14014f0cd  movzx   ecx, di; jumptable 000000014014EE50 case 7
0x14014f0d0  shl     ecx, 10h
0x14014f0d3  movzx   eax, r12w
0x14014f0d7  or      ecx, eax
0x14014f0d9  mov     [rsp+138h+var_110], rbx
0x14014f0de  mov     rax, [r15]
0x14014f0e1  mov     [rsp+138h+BugCheckParameter4], rax
0x14014f0e6  mov     r9, r14
0x14014f0e9  mov     r8, rsi
0x14014f0ec  mov     rdx, r13
0x14014f0ef  call    fnHkINLPMOUSEHOOKSTRUCTEX
0x14014f0f4  jmp     loc_14014F41B
0x14014f0f9  mov     [rsp+138h+BugCheckParameter4], 0; jumptable 000000014014EE50 default case, cases 0,1,3,8,11,12
0x14014f102  xor     r9d, r9d; BugCheckParameter3
0x14014f105  xor     r8d, r8d; BugCheckParameter2
  ... truncated ...
```
