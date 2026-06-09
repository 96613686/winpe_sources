# _GetMouseMovePointsEx

- ea: `0x14021119c`
- end: `0x14021179c`
- name: `_GetMouseMovePointsEx`
- size: `1536`
- prototype: ``
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
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // esi
  _DWORD *v9; // rax
  __int64 v10; // rcx
  int v11; // r14d
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  INT v15; // r13d
  unsigned __int64 v16; // rcx
  INT v17; // r12d
  INT v18; // r14d
  __int64 UserSessionState; // rax
  __int64 v20; // rcx
  unsigned int v21; // r13d
  INT v22; // r14d
  __int64 v23; // rax
  unsigned int v24; // r12d
  BOOL v25; // r14d
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // r14d
  __int64 v29; // rdi
  int v30; // ebx
  __int64 v31; // rcx
  int v32; // r12d
  __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  INT v36; // r12d
  INT v37; // ebx
  __int64 v38; // rax
  INT v39; // eax
  __int64 v40; // rcx
  INT v41; // ebx
  __int64 v42; // rax
  INT v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // eax
  __int64 v46; // r12
  unsigned __int16 CurrentThreadCompositedDpi; // ax
  int v48; // ebx
  int v49; // edi
  INT v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned int v55; // eax
  unsigned int v56; // [rsp+20h] [rbp-98h]
  int v57; // [rsp+24h] [rbp-94h]
  int v58; // [rsp+28h] [rbp-90h]
  unsigned __int64 v59; // [rsp+30h] [rbp-88h] BYREF
  __int64 v60; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v61; // [rsp+40h] [rbp-78h]
  int v62; // [rsp+44h] [rbp-74h]
  int v63; // [rsp+48h] [rbp-70h]
  int v64; // [rsp+50h] [rbp-68h] BYREF
  int v65; // [rsp+54h] [rbp-64h]
  __int64 v66; // [rsp+58h] [rbp-60h] BYREF
  _DWORD v67[22]; // [rsp+60h] [rbp-58h] BYREF
  INT ca; // [rsp+C0h] [rbp+8h]

  v66 = 0;
  v64 = *a1;
  v65 = a1[2];
  v60 = 0;
  v59 = 0;
  CurrentThreadDpiAwarenessContext = W32GetCurrentThreadDpiAwarenessContext(a1);
  LogicalToPhysicalDPIPoint(&v66, &v64, CurrentThreadDpiAwarenessContext, 0);
  if ( *(_DWORD *)(W32GetUserSessionState(v5) + 14668) )
    v7 = ((unsigned __int8)*(_DWORD *)(W32GetUserSessionState(v6) + 14668) - 1) & 0x3F;
  else
    v7 = 63;
  v8 = v7;
  v9 = **(_DWORD ***)(W32GetUserSessionState(v6) + 56744);
  v57 = v9[6];
  v10 = (unsigned int)v9[7];
  v58 = v9[7];
  v11 = v9[8];
  v62 = v11;
  v63 = v9[9];
  while ( 1 )
  {
    v12 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v10) + 24LL * v8 + 14672) >> 16;
    if ( !(_WORD)v12 )
      break;
    v13 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v12) + 24LL * v8 + 14676) >> 16;
    if ( !(_WORD)v13 )
      break;
    v14 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v13) + 24LL * v8 + 14672) >> 16;
    v15 = (unsigned __int16)v14 + 1;
    v16 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v14) + 24LL * v8 + 14676) >> 16;
    v17 = (unsigned __int16)v16 + 1;
    v18 = v11 - v57;
    UserSessionState = W32GetUserSessionState(v16);
    if ( v15 == v18 )
      v21 = *(__int16 *)(UserSessionState + 24LL * v8 + 14672);
    else
      v21 = v57 + EngMulDiv(*(unsigned __int16 *)(UserSessionState + 24LL * v8 + 14672), v18, v15);
    v22 = v63 - v58;
    v23 = W32GetUserSessionState(v20);
    if ( v17 == v22 )
      v24 = *(__int16 *)(v23 + 24LL * v8 + 14676);
    else
      v24 = v58 + EngMulDiv(*(unsigned __int16 *)(v23 + 24LL * v8 + 14676), v22, v17);
    if ( __PAIR64__(v24, v21) == v66 )
      goto LABEL_16;
    v25 = 0;
    if ( (W32GetCurrentThreadDpiAwarenessContext(v10) & 0xF) != 2 )
    {
      v59 = __PAIR64__(v24, v21);
      v55 = W32GetCurrentThreadDpiAwarenessContext(v10);
      PhysicalToLogicalDPIPoint(&v60, &v59, v55, 0);
      if ( (_DWORD)v60 == v64 )
        v25 = HIDWORD(v60) == v65;
    }
    if ( v25 )
    {
LABEL_16:
      if ( !*((_DWORD *)a1 + 2) || *((_DWORD *)a1 + 2) == *(_DWORD *)(W32GetUserSessionState(v10) + 24LL * v8 + 14680) )
      {
        v26 = 1;
        goto LABEL_18;
      }
    }
    v8 = v8 ? ((_BYTE)v8 - 1) & 0x3F : 63;
    if ( v8 == v7 )
      break;
    v11 = v62;
  }
  v26 = 0;
LABEL_18:
  if ( v26 )
  {
    v61 = 0;
    v27 = v8 - v7 + 64;
    if ( v8 > v7 )
      v27 = v8 - v7;
    if ( (unsigned int)v27 >= a3 )
      v27 = a3;
    v56 = v27;
    v28 = 0;
    v61 = 0;
    v29 = a2;
    while ( 1 )
    {
      if ( v28 >= (unsigned int)v27 )
        return v28;
      v30 = *(_DWORD *)(W32GetUserSessionState(v27) + 24LL * v8 + 14672);
      v32 = *(_DWORD *)(W32GetUserSessionState(v31) + 24LL * v8 + 14676);
      v34 = (unsigned __int64)*(unsigned int *)(W32GetUserSessionState(v33) + 24LL * v8 + 14672) >> 16;
      if ( !(_WORD)v34 || !HIWORD(*(_DWORD *)(W32GetUserSessionState(v34) + 24LL * v8 + 14676)) )
        return v28;
      v35 = (unsigned int)HIWORD(v30) + 1;
      ca = v35;
      v36 = HIWORD(v32) + 1;
      v37 = v62 - v57;
      if ( (_DWORD)v35 == v62 - v57 )
      {
        v38 = W32GetUserSessionState(v35);
        v39 = EngMulDiv(*(__int16 *)(v38 + 24LL * v8 + 14672), v37, ca);
      }
      else
      {
        v53 = W32GetUserSessionState(v35);
        v39 = v57 + EngMulDiv(*(unsigned __int16 *)(v53 + 24LL * v8 + 14672), v37, ca);
      }
      LODWORD(v59) = v39;
      v41 = v63 - v58;
      v42 = W32GetUserSessionState(v40);
      v43 = v36 == v41
          ? EngMulDiv(*(__int16 *)(v42 + 24LL * v8 + 14676), v41, v36)
          : v58 + EngMulDiv(*(unsigned __int16 *)(v42 + 24LL * v8 + 14676), v41, v36);
      HIDWORD(v59) = v43;
      v45 = W32GetCurrentThreadDpiAwarenessContext(v44);
      PhysicalToLogicalDPIPoint(&v60, &v59, v45, 0);
      v46 = v28;
      if ( a4 == 2 )
        break;
      *(_QWORD *)(v29 + 24LL * v28) = v60;
      v46 = v28;
      v51 = 3LL * v28;
      if ( *(int *)(v29 + 24LL * v28) < 0 )
        *(_DWORD *)(v29 + 24LL * v28) += 0x10000;
      if ( *(int *)(v29 + 24LL * v28 + 4) < 0 )
      {
        v50 = *(_DWORD *)(v29 + 24LL * v28 + 4) + 0x10000;
        goto LABEL_33;
      }
LABEL_34:
      v52 = *(unsigned int *)(W32GetUserSessionState(v51) + 24LL * v8 + 14680);
      *(_DWORD *)(v29 + 24 * v46 + 8) = v52;
      *(_QWORD *)(v29 + 24 * v46 + 16) = *(_QWORD *)(W32GetUserSessionState(v52) + 24LL * v8 + 14688);
      if ( v8 )
        v8 = ((_BYTE)v8 - 1) & 0x3F;
      else
        v8 = 63;
      v61 = ++v28;
      v27 = v56;
    }
    CurrentThreadCompositedDpi = GetCurrentThreadCompositedDpi(3LL * v28);
    GetScreenRectForDpi(v67, CurrentThreadCompositedDpi);
    v48 = v67[1];
    v49 = v67[3];
    *(_DWORD *)(a2 + 24LL * v28) = EngMulDiv((unsigned __int16)v60, 0x10000, v67[2] - v67[0] - 1);
    v50 = EngMulDiv(WORD2(v60), 0x10000, v49 - v48 - 1);
    v29 = a2;
    v51 = 3LL * v28;
LABEL_33:
    *(_DWORD *)(v29 + 8 * v51 + 4) = v50;
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
