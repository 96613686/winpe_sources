# _GetMouseMovePointsEx

- ea: `0x14021119c`
- end: `0x14021179c`
- name: `_GetMouseMovePointsEx`
- size: `1536`
- prototype: `__int64 __fastcall(__int16 *, __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140211080`

## callees

- `0x1400e5410`
- `0x1400e559c`
- `0x1400e8c20`
- `0x14021119c`

## import_xrefs

- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140211516`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1402116f9`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140211516`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1402116f9`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402111e3`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14021134a`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402114fa`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402116dd`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402111e3`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x14021134a`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402114fa`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402116dd`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402111ff`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402111ff`
- `win32kbase!EngMulDiv` at `0x1402114af`
- `win32kbase!EngMulDiv` at `0x1402114ea`
- `win32kbase!EngMulDiv` at `0x140211568`
- `win32kbase!EngMulDiv` at `0x140211593`
- `win32kbase!EngMulDiv` at `0x14021165a`
- `win32kbase!EngMulDiv` at `0x140211678`
- `win32kbase!EngMulDiv` at `0x14021175c`
- `win32kbase!EngMulDiv` at `0x140211783`
- `win32kbase!EngMulDiv` at `0x1402114af`
- `win32kbase!EngMulDiv` at `0x1402114ea`
- `win32kbase!EngMulDiv` at `0x140211568`
- `win32kbase!EngMulDiv` at `0x140211593`
- `win32kbase!EngMulDiv` at `0x14021165a`
- `win32kbase!EngMulDiv` at `0x140211678`
- `win32kbase!EngMulDiv` at `0x14021175c`
- `win32kbase!EngMulDiv` at `0x140211783`
- `WIN32K!W32GetUserSessionState` at `0x14021120b`
- `WIN32K!W32GetUserSessionState` at `0x140211224`
- `WIN32K!W32GetUserSessionState` at `0x14021123d`
- `WIN32K!W32GetUserSessionState` at `0x140211277`
- `WIN32K!W32GetUserSessionState` at `0x140211297`
- `WIN32K!W32GetUserSessionState` at `0x1402112b7`
- `WIN32K!W32GetUserSessionState` at `0x1402112d5`
- `WIN32K!W32GetUserSessionState` at `0x1402112f8`
- `WIN32K!W32GetUserSessionState` at `0x140211320`
- `WIN32K!W32GetUserSessionState` at `0x140211392`
- `WIN32K!W32GetUserSessionState` at `0x1402113fb`
- `WIN32K!W32GetUserSessionState` at `0x14021140f`
- `WIN32K!W32GetUserSessionState` at `0x140211423`
- `WIN32K!W32GetUserSessionState` at `0x140211444`
- `WIN32K!W32GetUserSessionState` at `0x140211490`
- `WIN32K!W32GetUserSessionState` at `0x1402114c7`
- `WIN32K!W32GetUserSessionState` at `0x1402115b3`
- `WIN32K!W32GetUserSessionState` at `0x1402115cb`
- `WIN32K!W32GetUserSessionState` at `0x14021163b`
- `WIN32K!W32GetUserSessionState` at `0x14021120b`
- `WIN32K!W32GetUserSessionState` at `0x140211224`
- `WIN32K!W32GetUserSessionState` at `0x14021123d`
- `WIN32K!W32GetUserSessionState` at `0x140211277`
- `WIN32K!W32GetUserSessionState` at `0x140211297`
- `WIN32K!W32GetUserSessionState` at `0x1402112b7`
- `WIN32K!W32GetUserSessionState` at `0x1402112d5`
- `WIN32K!W32GetUserSessionState` at `0x1402112f8`
- `WIN32K!W32GetUserSessionState` at `0x140211320`
- `WIN32K!W32GetUserSessionState` at `0x140211392`
- `WIN32K!W32GetUserSessionState` at `0x1402113fb`
- `WIN32K!W32GetUserSessionState` at `0x14021140f`
- `WIN32K!W32GetUserSessionState` at `0x140211423`
- `WIN32K!W32GetUserSessionState` at `0x140211444`
- `WIN32K!W32GetUserSessionState` at `0x140211490`
- `WIN32K!W32GetUserSessionState` at `0x1402114c7`
- `WIN32K!W32GetUserSessionState` at `0x1402115b3`
- `WIN32K!W32GetUserSessionState` at `0x1402115cb`
- `WIN32K!W32GetUserSessionState` at `0x14021163b`

## pseudocode

```c
__int64 __fastcall GetMouseMovePointsEx(__int16 *a1, __int64 a2, unsigned int a3, int a4)
{
  unsigned int CurrentThreadDpiAwarenessContext; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  unsigned int v14; // esi
  _DWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // r14d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  INT v24; // r13d
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned __int64 v28; // rcx
  INT v29; // r12d
  INT v30; // r14d
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 UserSessionState; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  unsigned int v39; // r13d
  INT v40; // r14d
  __int64 v41; // rax
  unsigned int v42; // r12d
  BOOL v43; // r14d
  int v44; // eax
  __int64 v45; // rcx
  unsigned int v46; // r14d
  __int64 v47; // rdi
  int v48; // ebx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  int v53; // r12d
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdx
  unsigned __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rcx
  INT v66; // r12d
  INT v67; // ebx
  __int64 v68; // rax
  INT v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  INT v74; // ebx
  __int64 v75; // rax
  INT v76; // eax
  __int64 v77; // rcx
  unsigned int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // r12
  unsigned __int16 CurrentThreadCompositedDpi; // ax
  int v84; // ebx
  int v85; // edi
  INT v86; // eax
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // rax
  unsigned int v94; // eax
  unsigned int v95; // [rsp+20h] [rbp-98h]
  int v96; // [rsp+24h] [rbp-94h]
  int v97; // [rsp+28h] [rbp-90h]
  unsigned __int64 v98; // [rsp+30h] [rbp-88h] BYREF
  __int64 v99; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v100; // [rsp+40h] [rbp-78h]
  int v101; // [rsp+44h] [rbp-74h]
  int v102; // [rsp+48h] [rbp-70h]
  int v103; // [rsp+50h] [rbp-68h] BYREF
  int v104; // [rsp+54h] [rbp-64h]
  __int64 v105; // [rsp+58h] [rbp-60h] BYREF
  _DWORD v106[22]; // [rsp+60h] [rbp-58h] BYREF
  INT ca; // [rsp+C0h] [rbp+8h]

  v105 = 0;
  v103 = *a1;
  v104 = a1[2];
  v99 = 0;
  v98 = 0;
  CurrentThreadDpiAwarenessContext = W32GetCurrentThreadDpiAwarenessContext(a1);
  LogicalToPhysicalDPIPoint(&v105, &v103, CurrentThreadDpiAwarenessContext, 0);
  if ( *(_DWORD *)(W32GetUserSessionState(v6, v5, v7, v8) + 14668) )
    v13 = ((unsigned __int8)*(_DWORD *)(W32GetUserSessionState(v10, v9, v11, v12) + 14668) - 1) & 0x3F;
  else
    v13 = 63;
  v14 = v13;
  v15 = **(_DWORD ***)(W32GetUserSessionState(v10, v9, v11, v12) + 56744);
  v96 = v15[6];
  v19 = (unsigned int)v15[7];
  v97 = v15[7];
  v20 = v15[8];
  v101 = v20;
  v102 = v15[9];
  while ( 1 )
  {
    v21 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v19, v16, v17, v18) + 24LL * v14 + 14672) >> 16;
    if ( !(_WORD)v21 )
      break;
    v22 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v21, v16, v17, v18) + 24LL * v14 + 14676) >> 16;
    if ( !(_WORD)v22 )
      break;
    v23 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v22, v16, v17, v18) + 24LL * v14 + 14672) >> 16;
    v24 = (unsigned __int16)v23 + 1;
    v28 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v23, v25, v26, v27) + 24LL * v14 + 14676) >> 16;
    v29 = (unsigned __int16)v28 + 1;
    v30 = v20 - v96;
    UserSessionState = W32GetUserSessionState(v28, v31, v32, v33);
    if ( v24 == v30 )
      v39 = *(__int16 *)(UserSessionState + 24LL * v14 + 14672);
    else
      v39 = v96 + EngMulDiv(*(unsigned __int16 *)(UserSessionState + 24LL * v14 + 14672), v30, v24);
    v40 = v102 - v97;
    v41 = W32GetUserSessionState(v36, v35, v37, v38);
    if ( v29 == v40 )
      v42 = *(__int16 *)(v41 + 24LL * v14 + 14676);
    else
      v42 = v97 + EngMulDiv(*(unsigned __int16 *)(v41 + 24LL * v14 + 14676), v40, v29);
    if ( __PAIR64__(v42, v39) == v105 )
      goto LABEL_16;
    v43 = 0;
    if ( (W32GetCurrentThreadDpiAwarenessContext(v19) & 0xF) != 2 )
    {
      v98 = __PAIR64__(v42, v39);
      v94 = W32GetCurrentThreadDpiAwarenessContext(v19);
      PhysicalToLogicalDPIPoint(&v99, &v98, v94, 0);
      if ( (_DWORD)v99 == v103 )
        v43 = HIDWORD(v99) == v104;
    }
    if ( v43 )
    {
LABEL_16:
      if ( !*((_DWORD *)a1 + 2)
        || *((_DWORD *)a1 + 2) == *(_DWORD *)(W32GetUserSessionState(v19, v16, v17, v18) + 24LL * v14 + 14680) )
      {
        v44 = 1;
        goto LABEL_18;
      }
    }
    v14 = v14 ? ((_BYTE)v14 - 1) & 0x3F : 63;
    if ( v14 == v13 )
      break;
    v20 = v101;
  }
  v44 = 0;
LABEL_18:
  if ( v44 )
  {
    v100 = 0;
    v45 = v14 - v13 + 64;
    if ( v14 > v13 )
      v45 = v14 - v13;
    if ( (unsigned int)v45 >= a3 )
      v45 = a3;
    v95 = v45;
    v46 = 0;
    v100 = 0;
    v47 = a2;
    while ( 1 )
    {
      if ( v46 >= (unsigned int)v45 )
        return v46;
      v48 = *(_DWORD *)(W32GetUserSessionState(v45, v16, v17, v18) + 24LL * v14 + 14672);
      v53 = *(_DWORD *)(W32GetUserSessionState(v50, v49, v51, v52) + 24LL * v14 + 14676);
      v59 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v55, v54, v56, v57) + 24LL * v14 + 14672) >> 16;
      if ( !(_WORD)v59 || !HIWORD(*(_DWORD *)(W32GetUserSessionState(v59, v58, v60, v61) + 24LL * v14 + 14676)) )
        return v46;
      v65 = (unsigned int)HIWORD(v48) + 1;
      ca = v65;
      v66 = HIWORD(v53) + 1;
      v67 = v101 - v96;
      if ( (_DWORD)v65 == v101 - v96 )
      {
        v68 = W32GetUserSessionState(v65, v62, v63, v64);
        v69 = EngMulDiv(*(__int16 *)(v68 + 24LL * v14 + 14672), v67, ca);
      }
      else
      {
        v92 = W32GetUserSessionState(v65, v62, v63, v64);
        v69 = v96 + EngMulDiv(*(unsigned __int16 *)(v92 + 24LL * v14 + 14672), v67, ca);
      }
      LODWORD(v98) = v69;
      v74 = v102 - v97;
      v75 = W32GetUserSessionState(v71, v70, v72, v73);
      v76 = v66 == v74
          ? EngMulDiv(*(__int16 *)(v75 + 24LL * v14 + 14676), v74, v66)
          : v97 + EngMulDiv(*(unsigned __int16 *)(v75 + 24LL * v14 + 14676), v74, v66);
      HIDWORD(v98) = v76;
      v78 = W32GetCurrentThreadDpiAwarenessContext(v77);
      PhysicalToLogicalDPIPoint(&v99, &v98, v78, 0);
      v82 = v46;
      if ( a4 == 2 )
        break;
      *(_QWORD *)(v47 + 24LL * v46) = v99;
      v82 = v46;
      v87 = 3LL * v46;
      if ( *(int *)(v47 + 24LL * v46) < 0 )
        *(_DWORD *)(v47 + 24LL * v46) += 0x10000;
      if ( *(int *)(v47 + 24LL * v46 + 4) < 0 )
      {
        v86 = *(_DWORD *)(v47 + 24LL * v46 + 4) + 0x10000;
        goto LABEL_33;
      }
LABEL_34:
      v88 = *(unsigned int *)(W32GetUserSessionState(v87, v79, v80, v81) + 24LL * v14 + 14680);
      *(_DWORD *)(v47 + 24 * v82 + 8) = v88;
      *(_QWORD *)(v47 + 24 * v82 + 16) = *(_QWORD *)(W32GetUserSessionState(v88, v89, v90, v91) + 24LL * v14 + 14688);
      if ( v14 )
        v14 = ((_BYTE)v14 - 1) & 0x3F;
      else
        v14 = 63;
      v100 = ++v46;
      v45 = v95;
    }
    CurrentThreadCompositedDpi = GetCurrentThreadCompositedDpi(3LL * v46);
    GetScreenRectForDpi((__int64)v106, CurrentThreadCompositedDpi);
    v84 = v106[1];
    v85 = v106[3];
    *(_DWORD *)(a2 + 24LL * v46) = EngMulDiv((unsigned __int16)v99, 0x10000, v106[2] - v106[0] - 1);
    v86 = EngMulDiv(WORD2(v99), 0x10000, v85 - v84 - 1);
    v47 = a2;
    v87 = 3LL * v46;
LABEL_33:
    *(_DWORD *)(v47 + 8 * v87 + 4) = v86;
    goto LABEL_34;
  }
  UserSetLastError(1171);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14021119c  mov     r11, rsp
0x14021119f  mov     [r11+20h], r9d
0x1402111a3  mov     [r11+18h], r8d
0x1402111a7  mov     [r11+10h], rdx
0x1402111ab  mov     [r11+8], rcx
0x1402111af  push    rbx
0x1402111b0  push    rsi
0x1402111b1  push    rdi
0x1402111b2  push    r12
0x1402111b4  push    r13
0x1402111b6  push    r14
0x1402111b8  sub     rsp, 88h
0x1402111bf  xor     r13d, r13d
0x1402111c2  mov     [rsp+0B8h+var_98], r13d
0x1402111c7  mov     [r11-60h], r13
0x1402111cb  movsx   eax, word ptr [rcx]
0x1402111ce  mov     [rsp+0B8h+var_68], eax
0x1402111d2  movsx   eax, word ptr [rcx+4]
0x1402111d6  mov     [rsp+0B8h+var_64], eax
0x1402111da  mov     [r11-80h], r13
0x1402111de  mov     [rsp+0B8h+var_88], r13
0x1402111e3  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x1402111ea  nop     dword ptr [rax+rax+00h]
0x1402111ef  mov     r8d, eax
0x1402111f2  xor     r9d, r9d
0x1402111f5  lea     rdx, [rsp+0B8h+var_68]
0x1402111fa  lea     rcx, [rsp+0B8h+var_60]
0x1402111ff  call    cs:__imp_LogicalToPhysicalDPIPoint
0x140211206  nop     dword ptr [rax+rax+00h]
0x14021120b  call    cs:__imp_W32GetUserSessionState
0x140211212  nop     dword ptr [rax+rax+00h]
0x140211217  cmp     [rax+394Ch], r13d
0x14021121e  jz      loc_140211744
0x140211224  call    cs:__imp_W32GetUserSessionState
0x14021122b  nop     dword ptr [rax+rax+00h]
0x140211230  mov     ebx, [rax+394Ch]
0x140211236  dec     ebx
0x140211238  and     ebx, 3Fh
0x14021123b  mov     esi, ebx
0x14021123d  call    cs:__imp_W32GetUserSessionState
0x140211244  nop     dword ptr [rax+rax+00h]
0x140211249  mov     rcx, [rax+0DDA8h]
0x140211250  mov     rax, [rcx]
0x140211253  mov     ecx, [rax+18h]
0x140211256  mov     [rsp+0B8h+var_94], ecx
0x14021125a  mov     ecx, [rax+1Ch]
0x14021125d  mov     [rsp+0B8h+var_90], ecx
0x140211261  mov     r14d, [rax+20h]
0x140211265  mov     [rsp+0B8h+var_74], r14d
0x14021126a  mov     eax, [rax+24h]
0x14021126d  mov     [rsp+0B8h+var_70], eax
0x140211271  mov     eax, esi
0x140211273  lea     rdi, [rax+rax*2]
0x140211277  call    cs:__imp_W32GetUserSessionState
0x14021127e  nop     dword ptr [rax+rax+00h]
0x140211283  mov     ecx, [rax+rdi*8+3950h]
0x14021128a  shr     rcx, 10h
0x14021128e  test    cx, cx
0x140211291  jz      loc_14021173B
0x140211297  call    cs:__imp_W32GetUserSessionState
0x14021129e  nop     dword ptr [rax+rax+00h]
0x1402112a3  mov     ecx, [rax+rdi*8+3954h]
0x1402112aa  shr     rcx, 10h
0x1402112ae  test    cx, cx
0x1402112b1  jz      loc_14021173B
0x1402112b7  call    cs:__imp_W32GetUserSessionState
0x1402112be  nop     dword ptr [rax+rax+00h]
0x1402112c3  mov     ecx, [rax+rdi*8+3950h]
0x1402112ca  shr     rcx, 10h
0x1402112ce  movzx   r13d, cx
0x1402112d2  inc     r13d
0x1402112d5  call    cs:__imp_W32GetUserSessionState
0x1402112dc  nop     dword ptr [rax+rax+00h]
0x1402112e1  mov     ecx, [rax+rdi*8+3954h]
0x1402112e8  shr     rcx, 10h
0x1402112ec  movzx   r12d, cx
0x1402112f0  inc     r12d
0x1402112f3  sub     r14d, [rsp+0B8h+var_94]
0x1402112f8  call    cs:__imp_W32GetUserSessionState
0x1402112ff  nop     dword ptr [rax+rax+00h]
0x140211304  cmp     r13d, r14d
0x140211307  jnz     loc_14021174E
0x14021130d  movsx   r13d, word ptr [rax+rdi*8+3950h]
0x140211316  mov     r14d, [rsp+0B8h+var_70]
0x14021131b  sub     r14d, [rsp+0B8h+var_90]
0x140211320  call    cs:__imp_W32GetUserSessionState
0x140211327  nop     dword ptr [rax+rax+00h]
0x14021132c  cmp     r12d, r14d
0x14021132f  jnz     loc_140211775
0x140211335  movsx   r12d, word ptr [rax+rdi*8+3954h]
0x14021133e  cmp     r13d, [rsp+0B8h+var_60]
0x140211343  jz      short loc_14021137A
0x140211345  xor     eax, eax
0x140211347  mov     r14d, eax
0x14021134a  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x140211351  nop     dword ptr [rax+rax+00h]
0x140211356  and     al, 0Fh
0x140211358  cmp     al, 2
0x14021135a  jnz     loc_1402116D3
0x140211360  xor     r13d, r13d
0x140211363  test    r14d, r14d
0x140211366  jnz     short loc_140211384
0x140211368  test    esi, esi
0x14021136a  jz      loc_1402116C0
0x140211370  dec     esi
0x140211372  and     esi, 3Fh
0x140211375  jmp     loc_1402116C5
0x14021137a  cmp     r12d, [rsp+0B8h+var_5C]
0x14021137f  jnz     short loc_140211345
0x140211381  xor     r13d, r13d
0x140211384  mov     r14, qword ptr [rsp+0B8h+c]
0x14021138c  cmp     [r14+8], r13d
0x140211390  jz      short loc_1402113AB
0x140211392  call    cs:__imp_W32GetUserSessionState
0x140211399  nop     dword ptr [rax+rax+00h]
0x14021139e  mov     eax, [rax+rdi*8+3958h]
0x1402113a5  cmp     [r14+8], eax
0x1402113a9  jnz     short loc_140211368
0x1402113ab  mov     eax, 1
0x1402113b0  test    eax, eax
0x1402113b2  jz      loc_140211729
0x1402113b8  mov     [rsp+0B8h+var_78], r13d
0x1402113bd  mov     eax, esi
0x1402113bf  sub     eax, ebx
0x1402113c1  lea     ecx, [rax+40h]
0x1402113c4  cmp     esi, ebx
0x1402113c6  cmova   ecx, eax
0x1402113c9  cmp     ecx, [rsp+0B8h+arg_10]
0x1402113d0  cmovnb  ecx, [rsp+0B8h+arg_10]
0x1402113d8  mov     [rsp+0B8h+var_98], ecx
0x1402113dc  mov     r14d, r13d
0x1402113df  mov     [rsp+0B8h+var_78], r13d
0x1402113e4  mov     rdi, [rsp+0B8h+arg_8]
0x1402113ec  cmp     r14d, ecx
0x1402113ef  jnb     loc_1402116A4
0x1402113f5  mov     eax, esi
0x1402113f7  lea     r13, [rax+rax*2]
0x1402113fb  call    cs:__imp_W32GetUserSessionState
0x140211402  nop     dword ptr [rax+rax+00h]
0x140211407  mov     ebx, [rax+r13*8+3950h]
0x14021140f  call    cs:__imp_W32GetUserSessionState
0x140211416  nop     dword ptr [rax+rax+00h]
0x14021141b  mov     r12d, [rax+r13*8+3954h]
0x140211423  call    cs:__imp_W32GetUserSessionState
0x14021142a  nop     dword ptr [rax+rax+00h]
0x14021142f  mov     ecx, [rax+r13*8+3950h]
0x140211437  shr     rcx, 10h
0x14021143b  test    cx, cx
0x14021143e  jz      loc_1402116A4
0x140211444  call    cs:__imp_W32GetUserSessionState
0x14021144b  nop     dword ptr [rax+rax+00h]
0x140211450  mov     ecx, [rax+r13*8+3954h]
0x140211458  shr     rcx, 10h
0x14021145c  test    cx, cx
0x14021145f  jz      loc_1402116A4
0x140211465  shr     rbx, 10h
0x140211469  movzx   ecx, bx
0x14021146c  inc     ecx
0x14021146e  mov     [rsp+0B8h+c], ecx
0x140211475  shr     r12, 10h
0x140211479  movzx   r12d, r12w
0x14021147d  inc     r12d
0x140211480  mov     ebx, [rsp+0B8h+var_74]
0x140211484  sub     ebx, [rsp+0B8h+var_94]
0x140211488  cmp     ecx, ebx
0x14021148a  jnz     loc_14021163B
0x140211490  call    cs:__imp_W32GetUserSessionState
0x140211497  nop     dword ptr [rax+rax+00h]
0x14021149c  movsx   ecx, word ptr [rax+r13*8+3950h]; a
0x1402114a5  mov     r8d, [rsp+0B8h+c]; c
0x1402114ad  mov     edx, ebx; b
0x1402114af  call    cs:__imp_EngMulDiv
0x1402114b6  nop     dword ptr [rax+rax+00h]
0x1402114bb  mov     dword ptr [rsp+0B8h+var_88], eax
0x1402114bf  mov     ebx, [rsp+0B8h+var_70]
0x1402114c3  sub     ebx, [rsp+0B8h+var_90]
0x1402114c7  call    cs:__imp_W32GetUserSessionState
0x1402114ce  nop     dword ptr [rax+rax+00h]
0x1402114d3  mov     r8d, r12d; c
0x1402114d6  mov     edx, ebx; b
0x1402114d8  cmp     r12d, ebx
0x1402114db  jnz     loc_14021166F
0x1402114e1  movsx   ecx, word ptr [rax+r13*8+3954h]; a
0x1402114ea  call    cs:__imp_EngMulDiv
0x1402114f1  nop     dword ptr [rax+rax+00h]
0x1402114f6  mov     dword ptr [rsp+0B8h+var_88+4], eax
0x1402114fa  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x140211501  nop     dword ptr [rax+rax+00h]
0x140211506  mov     r8d, eax
0x140211509  xor     r9d, r9d
0x14021150c  lea     rdx, [rsp+0B8h+var_88]
0x140211511  lea     rcx, [rsp+0B8h+var_80]
0x140211516  call    cs:__imp_PhysicalToLogicalDPIPoint
0x14021151d  nop     dword ptr [rax+rax+00h]
0x140211522  mov     r12d, r14d
0x140211525  lea     rcx, [r12+r12*2]
0x140211529  cmp     [rsp+0B8h+arg_18], 2
0x140211531  jnz     loc_140211608
0x140211537  call    GetCurrentThreadCompositedDpi
0x14021153c  movzx   edx, ax
0x14021153f  lea     rcx, [rsp+0B8h+var_58]
0x140211544  call    GetScreenRectForDpi
0x140211549  mov     ebx, [rsp+0B8h+var_54]
0x14021154d  mov     r8d, [rsp+0B8h+var_50]
0x140211552  mov     edi, [rsp+0B8h+var_4C]
0x140211556  sub     r8d, [rsp+0B8h+var_58]
0x14021155b  dec     r8d; c
0x14021155e  movzx   ecx, word ptr [rsp+0B8h+var_80]; a
0x140211563  mov     edx, 10000h; b
0x140211568  call    cs:__imp_EngMulDiv
0x14021156f  nop     dword ptr [rax+rax+00h]
0x140211574  mov     rdx, [rsp+0B8h+arg_8]
0x14021157c  lea     rcx, [r12+r12*2]
0x140211580  mov     [rdx+rcx*8], eax
0x140211583  sub     edi, ebx
0x140211585  lea     r8d, [rdi-1]; c
0x140211589  movzx   ecx, word ptr [rsp+0B8h+var_7C]; a
0x14021158e  mov     edx, 10000h; b
0x140211593  call    cs:__imp_EngMulDiv
0x14021159a  nop     dword ptr [rax+rax+00h]
0x14021159f  mov     rdi, [rsp+0B8h+arg_8]
0x1402115a7  lea     rcx, [r12+r12*2]
0x1402115ab  mov     [rdi+rcx*8+4], eax
0x1402115af  lea     rbx, [r12+r12*2]
0x1402115b3  call    cs:__imp_W32GetUserSessionState
0x1402115ba  nop     dword ptr [rax+rax+00h]
0x1402115bf  mov     ecx, [rax+r13*8+3958h]
0x1402115c7  mov     [rdi+rbx*8+8], ecx
0x1402115cb  call    cs:__imp_W32GetUserSessionState
0x1402115d2  nop     dword ptr [rax+rax+00h]
0x1402115d7  mov     ecx, esi
0x1402115d9  lea     rcx, [rcx+rcx*2]
0x1402115dd  mov     rax, [rax+rcx*8+3960h]
0x1402115e5  mov     [rdi+rbx*8+10h], rax
0x1402115ea  test    esi, esi
0x1402115ec  jz      loc_14021168D
0x1402115f2  dec     esi
0x1402115f4  and     esi, 3Fh
0x1402115f7  inc     r14d
0x1402115fa  mov     [rsp+0B8h+var_78], r14d
0x1402115ff  mov     ecx, [rsp+0B8h+var_98]
0x140211603  jmp     loc_1402113EC
0x140211608  mov     eax, [rsp+0B8h+var_80]
0x14021160c  mov     [rdi+rcx*8], eax
0x14021160f  mov     eax, [rsp+0B8h+var_7C]
0x140211613  mov     [rdi+rcx*8+4], eax
0x140211617  mov     r12d, r14d
0x14021161a  lea     rcx, [r12+r12*2]
0x14021161e  mov     eax, [rdi+rcx*8]
0x140211621  test    eax, eax
0x140211623  js      short loc_140211697
0x140211625  mov     eax, [rdi+rcx*8+4]
0x140211629  test    eax, eax
0x14021162b  jns     short loc_1402115AF
0x14021162d  mov     eax, [rdi+rcx*8+4]
0x140211631  add     eax, 10000h
0x140211636  jmp     loc_1402115AB
0x14021163b  call    cs:__imp_W32GetUserSessionState
0x140211642  nop     dword ptr [rax+rax+00h]
0x140211647  movzx   ecx, word ptr [rax+r13*8+3950h]; a
0x140211650  mov     r8d, [rsp+0B8h+c]; c
0x140211658  mov     edx, ebx; b
0x14021165a  call    cs:__imp_EngMulDiv
0x140211661  nop     dword ptr [rax+rax+00h]
0x140211666  add     eax, [rsp+0B8h+var_94]
0x14021166a  jmp     loc_1402114BB
0x14021166f  movzx   ecx, word ptr [rax+r13*8+3954h]; a
0x140211678  call    cs:__imp_EngMulDiv
0x14021167f  nop     dword ptr [rax+rax+00h]
0x140211684  add     eax, [rsp+0B8h+var_90]
0x140211688  jmp     loc_1402114F6
0x14021168d  mov     esi, 3Fh ; '?'
0x140211692  jmp     loc_1402115F7
0x140211697  mov     eax, [rdi+rcx*8]
0x14021169a  add     eax, 10000h
0x14021169f  mov     [rdi+rcx*8], eax
0x1402116a2  jmp     short loc_140211625
0x1402116a4  jmp     short loc_1402116AB
0x1402116a6  mov     r14d, [rsp+0B8h+var_78]
0x1402116ab  mov     eax, r14d
0x1402116ae  add     rsp, 88h
0x1402116b5  pop     r14
0x1402116b7  pop     r13
0x1402116b9  pop     r12
0x1402116bb  pop     rdi
0x1402116bc  pop     rsi
0x1402116bd  pop     rbx
0x1402116be  retn
0x1402116c0  mov     esi, 3Fh ; '?'
0x1402116c5  cmp     esi, ebx
0x1402116c7  jz      short loc_14021173B
0x1402116c9  mov     r14d, [rsp+0B8h+var_74]
0x1402116ce  jmp     loc_140211271
0x1402116d3  mov     dword ptr [rsp+0B8h+var_88], r13d
0x1402116d8  mov     dword ptr [rsp+0B8h+var_88+4], r12d
0x1402116dd  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x1402116e4  nop     dword ptr [rax+rax+00h]
0x1402116e9  mov     r8d, eax
0x1402116ec  xor     r9d, r9d
0x1402116ef  lea     rdx, [rsp+0B8h+var_88]
  ... truncated ...
```
