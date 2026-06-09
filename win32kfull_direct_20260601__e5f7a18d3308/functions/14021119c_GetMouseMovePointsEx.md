# _GetMouseMovePointsEx

- ea: `0x14021119c`
- end: `0x14021179c`
- name: `_GetMouseMovePointsEx`
- size: `1536`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
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
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // esi
  _DWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r14d
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  INT v18; // r13d
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  INT v21; // r12d
  INT v22; // r14d
  __int64 v23; // rdx
  __int64 UserSessionState; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned int v27; // r13d
  INT v28; // r14d
  __int64 v29; // rax
  unsigned int v30; // r12d
  BOOL v31; // r14d
  int v32; // eax
  __int64 v33; // rcx
  unsigned int v34; // r14d
  __int64 v35; // rdi
  int v36; // ebx
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // r12d
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  unsigned __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  INT v46; // r12d
  INT v47; // ebx
  __int64 v48; // rax
  INT v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  INT v52; // ebx
  __int64 v53; // rax
  INT v54; // eax
  __int64 v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r12
  unsigned __int16 CurrentThreadCompositedDpi; // ax
  int v60; // ebx
  int v61; // edi
  INT v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rax
  unsigned int v68; // eax
  unsigned int v69; // [rsp+20h] [rbp-98h]
  int v70; // [rsp+24h] [rbp-94h]
  int v71; // [rsp+28h] [rbp-90h]
  unsigned __int64 v72; // [rsp+30h] [rbp-88h] BYREF
  __int64 v73; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v74; // [rsp+40h] [rbp-78h]
  int v75; // [rsp+44h] [rbp-74h]
  int v76; // [rsp+48h] [rbp-70h]
  int v77; // [rsp+50h] [rbp-68h] BYREF
  int v78; // [rsp+54h] [rbp-64h]
  __int64 v79; // [rsp+58h] [rbp-60h] BYREF
  _DWORD v80[22]; // [rsp+60h] [rbp-58h] BYREF
  INT ca; // [rsp+C0h] [rbp+8h]

  v79 = 0;
  v77 = *a1;
  v78 = a1[2];
  v73 = 0;
  v72 = 0;
  CurrentThreadDpiAwarenessContext = W32GetCurrentThreadDpiAwarenessContext(a1);
  LogicalToPhysicalDPIPoint(&v79, &v77, CurrentThreadDpiAwarenessContext, 0);
  if ( *(_DWORD *)(W32GetUserSessionState(v6, v5) + 14668) )
    v9 = ((unsigned __int8)*(_DWORD *)(W32GetUserSessionState(v8, v7) + 14668) - 1) & 0x3F;
  else
    v9 = 63;
  v10 = v9;
  v11 = **(_DWORD ***)(W32GetUserSessionState(v8, v7) + 56744);
  v70 = v11[6];
  v13 = (unsigned int)v11[7];
  v71 = v11[7];
  v14 = v11[8];
  v75 = v14;
  v76 = v11[9];
  while ( 1 )
  {
    v15 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v13, v12) + 24LL * v10 + 14672) >> 16;
    if ( !(_WORD)v15 )
      break;
    v16 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v15, v12) + 24LL * v10 + 14676) >> 16;
    if ( !(_WORD)v16 )
      break;
    v17 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v16, v12) + 24LL * v10 + 14672) >> 16;
    v18 = (unsigned __int16)v17 + 1;
    v20 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v17, v19) + 24LL * v10 + 14676) >> 16;
    v21 = (unsigned __int16)v20 + 1;
    v22 = v14 - v70;
    UserSessionState = W32GetUserSessionState(v20, v23);
    if ( v18 == v22 )
      v27 = *(__int16 *)(UserSessionState + 24LL * v10 + 14672);
    else
      v27 = v70 + EngMulDiv(*(unsigned __int16 *)(UserSessionState + 24LL * v10 + 14672), v22, v18);
    v28 = v76 - v71;
    v29 = W32GetUserSessionState(v26, v25);
    if ( v21 == v28 )
      v30 = *(__int16 *)(v29 + 24LL * v10 + 14676);
    else
      v30 = v71 + EngMulDiv(*(unsigned __int16 *)(v29 + 24LL * v10 + 14676), v28, v21);
    if ( __PAIR64__(v30, v27) == v79 )
      goto LABEL_16;
    v31 = 0;
    if ( (W32GetCurrentThreadDpiAwarenessContext(v13) & 0xF) != 2 )
    {
      v72 = __PAIR64__(v30, v27);
      v68 = W32GetCurrentThreadDpiAwarenessContext(v13);
      PhysicalToLogicalDPIPoint(&v73, &v72, v68, 0);
      if ( (_DWORD)v73 == v77 )
        v31 = HIDWORD(v73) == v78;
    }
    if ( v31 )
    {
LABEL_16:
      if ( !*((_DWORD *)a1 + 2)
        || *((_DWORD *)a1 + 2) == *(_DWORD *)(W32GetUserSessionState(v13, v12) + 24LL * v10 + 14680) )
      {
        v32 = 1;
        goto LABEL_18;
      }
    }
    v10 = v10 ? ((_BYTE)v10 - 1) & 0x3F : 63;
    if ( v10 == v9 )
      break;
    v14 = v75;
  }
  v32 = 0;
LABEL_18:
  if ( v32 )
  {
    v74 = 0;
    v33 = v10 - v9 + 64;
    if ( v10 > v9 )
      v33 = v10 - v9;
    if ( (unsigned int)v33 >= a3 )
      v33 = a3;
    v69 = v33;
    v34 = 0;
    v74 = 0;
    v35 = a2;
    while ( 1 )
    {
      if ( v34 >= (unsigned int)v33 )
        return v34;
      v36 = *(_DWORD *)(W32GetUserSessionState(v33, v12) + 24LL * v10 + 14672);
      v39 = *(_DWORD *)(W32GetUserSessionState(v38, v37) + 24LL * v10 + 14676);
      v43 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v41, v40) + 24LL * v10 + 14672) >> 16;
      if ( !(_WORD)v43 || !HIWORD(*(_DWORD *)(W32GetUserSessionState(v43, v42) + 24LL * v10 + 14676)) )
        return v34;
      v45 = (unsigned int)HIWORD(v36) + 1;
      ca = v45;
      v46 = HIWORD(v39) + 1;
      v47 = v75 - v70;
      if ( (_DWORD)v45 == v75 - v70 )
      {
        v48 = W32GetUserSessionState(v45, v44);
        v49 = EngMulDiv(*(__int16 *)(v48 + 24LL * v10 + 14672), v47, ca);
      }
      else
      {
        v66 = W32GetUserSessionState(v45, v44);
        v49 = v70 + EngMulDiv(*(unsigned __int16 *)(v66 + 24LL * v10 + 14672), v47, ca);
      }
      LODWORD(v72) = v49;
      v52 = v76 - v71;
      v53 = W32GetUserSessionState(v51, v50);
      v54 = v46 == v52
          ? EngMulDiv(*(__int16 *)(v53 + 24LL * v10 + 14676), v52, v46)
          : v71 + EngMulDiv(*(unsigned __int16 *)(v53 + 24LL * v10 + 14676), v52, v46);
      HIDWORD(v72) = v54;
      v56 = W32GetCurrentThreadDpiAwarenessContext(v55);
      PhysicalToLogicalDPIPoint(&v73, &v72, v56, 0);
      v58 = v34;
      if ( a4 == 2 )
        break;
      *(_QWORD *)(v35 + 24LL * v34) = v73;
      v58 = v34;
      v63 = 3LL * v34;
      if ( *(int *)(v35 + 24LL * v34) < 0 )
        *(_DWORD *)(v35 + 24LL * v34) += 0x10000;
      if ( *(int *)(v35 + 24LL * v34 + 4) < 0 )
      {
        v62 = *(_DWORD *)(v35 + 24LL * v34 + 4) + 0x10000;
        goto LABEL_33;
      }
LABEL_34:
      v64 = *(unsigned int *)(W32GetUserSessionState(v63, v57) + 24LL * v10 + 14680);
      *(_DWORD *)(v35 + 24 * v58 + 8) = v64;
      *(_QWORD *)(v35 + 24 * v58 + 16) = *(_QWORD *)(W32GetUserSessionState(v64, v65) + 24LL * v10 + 14688);
      if ( v10 )
        v10 = ((_BYTE)v10 - 1) & 0x3F;
      else
        v10 = 63;
      v74 = ++v34;
      v33 = v69;
    }
    CurrentThreadCompositedDpi = GetCurrentThreadCompositedDpi(3LL * v34);
    GetScreenRectForDpi(v80, CurrentThreadCompositedDpi);
    v60 = v80[1];
    v61 = v80[3];
    *(_DWORD *)(a2 + 24LL * v34) = EngMulDiv((unsigned __int16)v73, 0x10000, v80[2] - v80[0] - 1);
    v62 = EngMulDiv(WORD2(v73), 0x10000, v61 - v60 - 1);
    v35 = a2;
    v63 = 3LL * v34;
LABEL_33:
    *(_DWORD *)(v35 + 8 * v63 + 4) = v62;
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
