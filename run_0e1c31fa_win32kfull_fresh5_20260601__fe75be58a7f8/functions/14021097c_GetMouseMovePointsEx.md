# _GetMouseMovePointsEx

- ea: `0x14021097c`
- end: `0x140210f7c`
- name: `_GetMouseMovePointsEx`
- size: `1536`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140210860`

## callees

- `0x1400bf200`
- `0x1400bf38c`
- `0x1400c2a10`
- `0x14021097c`

## import_xrefs

- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140210cf6`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140210ed9`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140210cf6`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x140210ed9`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402109c3`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210b2a`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210cda`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210ebd`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x1402109c3`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210b2a`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210cda`
- `win32kbase!W32GetCurrentThreadDpiAwarenessContext` at `0x140210ebd`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402109df`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402109df`
- `win32kbase!EngMulDiv` at `0x140210c8f`
- `win32kbase!EngMulDiv` at `0x140210cca`
- `win32kbase!EngMulDiv` at `0x140210d48`
- `win32kbase!EngMulDiv` at `0x140210d73`
- `win32kbase!EngMulDiv` at `0x140210e3a`
- `win32kbase!EngMulDiv` at `0x140210e58`
- `win32kbase!EngMulDiv` at `0x140210f3c`
- `win32kbase!EngMulDiv` at `0x140210f63`
- `win32kbase!EngMulDiv` at `0x140210c8f`
- `win32kbase!EngMulDiv` at `0x140210cca`
- `win32kbase!EngMulDiv` at `0x140210d48`
- `win32kbase!EngMulDiv` at `0x140210d73`
- `win32kbase!EngMulDiv` at `0x140210e3a`
- `win32kbase!EngMulDiv` at `0x140210e58`
- `win32kbase!EngMulDiv` at `0x140210f3c`
- `win32kbase!EngMulDiv` at `0x140210f63`
- `WIN32K!W32GetUserSessionState` at `0x1402109eb`
- `WIN32K!W32GetUserSessionState` at `0x140210a04`
- `WIN32K!W32GetUserSessionState` at `0x140210a1d`
- `WIN32K!W32GetUserSessionState` at `0x140210a57`
- `WIN32K!W32GetUserSessionState` at `0x140210a77`
- `WIN32K!W32GetUserSessionState` at `0x140210a97`
- `WIN32K!W32GetUserSessionState` at `0x140210ab5`
- `WIN32K!W32GetUserSessionState` at `0x140210ad8`
- `WIN32K!W32GetUserSessionState` at `0x140210b00`
- `WIN32K!W32GetUserSessionState` at `0x140210b72`
- `WIN32K!W32GetUserSessionState` at `0x140210bdb`
- `WIN32K!W32GetUserSessionState` at `0x140210bef`
- `WIN32K!W32GetUserSessionState` at `0x140210c03`
- `WIN32K!W32GetUserSessionState` at `0x140210c24`
- `WIN32K!W32GetUserSessionState` at `0x140210c70`
- `WIN32K!W32GetUserSessionState` at `0x140210ca7`
- `WIN32K!W32GetUserSessionState` at `0x140210d93`
- `WIN32K!W32GetUserSessionState` at `0x140210dab`
- `WIN32K!W32GetUserSessionState` at `0x140210e1b`
- `WIN32K!W32GetUserSessionState` at `0x1402109eb`
- `WIN32K!W32GetUserSessionState` at `0x140210a04`
- `WIN32K!W32GetUserSessionState` at `0x140210a1d`
- `WIN32K!W32GetUserSessionState` at `0x140210a57`
- `WIN32K!W32GetUserSessionState` at `0x140210a77`
- `WIN32K!W32GetUserSessionState` at `0x140210a97`
- `WIN32K!W32GetUserSessionState` at `0x140210ab5`
- `WIN32K!W32GetUserSessionState` at `0x140210ad8`
- `WIN32K!W32GetUserSessionState` at `0x140210b00`
- `WIN32K!W32GetUserSessionState` at `0x140210b72`
- `WIN32K!W32GetUserSessionState` at `0x140210bdb`
- `WIN32K!W32GetUserSessionState` at `0x140210bef`
- `WIN32K!W32GetUserSessionState` at `0x140210c03`
- `WIN32K!W32GetUserSessionState` at `0x140210c24`
- `WIN32K!W32GetUserSessionState` at `0x140210c70`
- `WIN32K!W32GetUserSessionState` at `0x140210ca7`
- `WIN32K!W32GetUserSessionState` at `0x140210d93`
- `WIN32K!W32GetUserSessionState` at `0x140210dab`
- `WIN32K!W32GetUserSessionState` at `0x140210e1b`

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
0x14021097c  mov     r11, rsp
0x14021097f  mov     [r11+20h], r9d
0x140210983  mov     [r11+18h], r8d
0x140210987  mov     [r11+10h], rdx
0x14021098b  mov     [r11+8], rcx
0x14021098f  push    rbx
0x140210990  push    rsi
0x140210991  push    rdi
0x140210992  push    r12
0x140210994  push    r13
0x140210996  push    r14
0x140210998  sub     rsp, 88h
0x14021099f  xor     r13d, r13d
0x1402109a2  mov     [rsp+0B8h+var_98], r13d
0x1402109a7  mov     [r11-60h], r13
0x1402109ab  movsx   eax, word ptr [rcx]
0x1402109ae  mov     [rsp+0B8h+var_68], eax
0x1402109b2  movsx   eax, word ptr [rcx+4]
0x1402109b6  mov     [rsp+0B8h+var_64], eax
0x1402109ba  mov     [r11-80h], r13
0x1402109be  mov     [rsp+0B8h+var_88], r13
0x1402109c3  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x1402109ca  nop     dword ptr [rax+rax+00h]
0x1402109cf  mov     r8d, eax
0x1402109d2  xor     r9d, r9d
0x1402109d5  lea     rdx, [rsp+0B8h+var_68]
0x1402109da  lea     rcx, [rsp+0B8h+var_60]
0x1402109df  call    cs:__imp_LogicalToPhysicalDPIPoint
0x1402109e6  nop     dword ptr [rax+rax+00h]
0x1402109eb  call    cs:__imp_W32GetUserSessionState
0x1402109f2  nop     dword ptr [rax+rax+00h]
0x1402109f7  cmp     [rax+394Ch], r13d
0x1402109fe  jz      loc_140210F24
0x140210a04  call    cs:__imp_W32GetUserSessionState
0x140210a0b  nop     dword ptr [rax+rax+00h]
0x140210a10  mov     ebx, [rax+394Ch]
0x140210a16  dec     ebx
0x140210a18  and     ebx, 3Fh
0x140210a1b  mov     esi, ebx
0x140210a1d  call    cs:__imp_W32GetUserSessionState
0x140210a24  nop     dword ptr [rax+rax+00h]
0x140210a29  mov     rcx, [rax+0DDA8h]
0x140210a30  mov     rax, [rcx]
0x140210a33  mov     ecx, [rax+18h]
0x140210a36  mov     [rsp+0B8h+var_94], ecx
0x140210a3a  mov     ecx, [rax+1Ch]
0x140210a3d  mov     [rsp+0B8h+var_90], ecx
0x140210a41  mov     r14d, [rax+20h]
0x140210a45  mov     [rsp+0B8h+var_74], r14d
0x140210a4a  mov     eax, [rax+24h]
0x140210a4d  mov     [rsp+0B8h+var_70], eax
0x140210a51  mov     eax, esi
0x140210a53  lea     rdi, [rax+rax*2]
0x140210a57  call    cs:__imp_W32GetUserSessionState
0x140210a5e  nop     dword ptr [rax+rax+00h]
0x140210a63  mov     ecx, [rax+rdi*8+3950h]
0x140210a6a  shr     rcx, 10h
0x140210a6e  test    cx, cx
0x140210a71  jz      loc_140210F1B
0x140210a77  call    cs:__imp_W32GetUserSessionState
0x140210a7e  nop     dword ptr [rax+rax+00h]
0x140210a83  mov     ecx, [rax+rdi*8+3954h]
0x140210a8a  shr     rcx, 10h
0x140210a8e  test    cx, cx
0x140210a91  jz      loc_140210F1B
0x140210a97  call    cs:__imp_W32GetUserSessionState
0x140210a9e  nop     dword ptr [rax+rax+00h]
0x140210aa3  mov     ecx, [rax+rdi*8+3950h]
0x140210aaa  shr     rcx, 10h
0x140210aae  movzx   r13d, cx
0x140210ab2  inc     r13d
0x140210ab5  call    cs:__imp_W32GetUserSessionState
0x140210abc  nop     dword ptr [rax+rax+00h]
0x140210ac1  mov     ecx, [rax+rdi*8+3954h]
0x140210ac8  shr     rcx, 10h
0x140210acc  movzx   r12d, cx
0x140210ad0  inc     r12d
0x140210ad3  sub     r14d, [rsp+0B8h+var_94]
0x140210ad8  call    cs:__imp_W32GetUserSessionState
0x140210adf  nop     dword ptr [rax+rax+00h]
0x140210ae4  cmp     r13d, r14d
0x140210ae7  jnz     loc_140210F2E
0x140210aed  movsx   r13d, word ptr [rax+rdi*8+3950h]
0x140210af6  mov     r14d, [rsp+0B8h+var_70]
0x140210afb  sub     r14d, [rsp+0B8h+var_90]
0x140210b00  call    cs:__imp_W32GetUserSessionState
0x140210b07  nop     dword ptr [rax+rax+00h]
0x140210b0c  cmp     r12d, r14d
0x140210b0f  jnz     loc_140210F55
0x140210b15  movsx   r12d, word ptr [rax+rdi*8+3954h]
0x140210b1e  cmp     r13d, [rsp+0B8h+var_60]
0x140210b23  jz      short loc_140210B5A
0x140210b25  xor     eax, eax
0x140210b27  mov     r14d, eax
0x140210b2a  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x140210b31  nop     dword ptr [rax+rax+00h]
0x140210b36  and     al, 0Fh
0x140210b38  cmp     al, 2
0x140210b3a  jnz     loc_140210EB3
0x140210b40  xor     r13d, r13d
0x140210b43  test    r14d, r14d
0x140210b46  jnz     short loc_140210B64
0x140210b48  test    esi, esi
0x140210b4a  jz      loc_140210EA0
0x140210b50  dec     esi
0x140210b52  and     esi, 3Fh
0x140210b55  jmp     loc_140210EA5
0x140210b5a  cmp     r12d, [rsp+0B8h+var_5C]
0x140210b5f  jnz     short loc_140210B25
0x140210b61  xor     r13d, r13d
0x140210b64  mov     r14, qword ptr [rsp+0B8h+c]
0x140210b6c  cmp     [r14+8], r13d
0x140210b70  jz      short loc_140210B8B
0x140210b72  call    cs:__imp_W32GetUserSessionState
0x140210b79  nop     dword ptr [rax+rax+00h]
0x140210b7e  mov     eax, [rax+rdi*8+3958h]
0x140210b85  cmp     [r14+8], eax
0x140210b89  jnz     short loc_140210B48
0x140210b8b  mov     eax, 1
0x140210b90  test    eax, eax
0x140210b92  jz      loc_140210F09
0x140210b98  mov     [rsp+0B8h+var_78], r13d
0x140210b9d  mov     eax, esi
0x140210b9f  sub     eax, ebx
0x140210ba1  lea     ecx, [rax+40h]
0x140210ba4  cmp     esi, ebx
0x140210ba6  cmova   ecx, eax
0x140210ba9  cmp     ecx, [rsp+0B8h+arg_10]
0x140210bb0  cmovnb  ecx, [rsp+0B8h+arg_10]
0x140210bb8  mov     [rsp+0B8h+var_98], ecx
0x140210bbc  mov     r14d, r13d
0x140210bbf  mov     [rsp+0B8h+var_78], r13d
0x140210bc4  mov     rdi, [rsp+0B8h+arg_8]
0x140210bcc  cmp     r14d, ecx
0x140210bcf  jnb     loc_140210E84
0x140210bd5  mov     eax, esi
0x140210bd7  lea     r13, [rax+rax*2]
0x140210bdb  call    cs:__imp_W32GetUserSessionState
0x140210be2  nop     dword ptr [rax+rax+00h]
0x140210be7  mov     ebx, [rax+r13*8+3950h]
0x140210bef  call    cs:__imp_W32GetUserSessionState
0x140210bf6  nop     dword ptr [rax+rax+00h]
0x140210bfb  mov     r12d, [rax+r13*8+3954h]
0x140210c03  call    cs:__imp_W32GetUserSessionState
0x140210c0a  nop     dword ptr [rax+rax+00h]
0x140210c0f  mov     ecx, [rax+r13*8+3950h]
0x140210c17  shr     rcx, 10h
0x140210c1b  test    cx, cx
0x140210c1e  jz      loc_140210E84
0x140210c24  call    cs:__imp_W32GetUserSessionState
0x140210c2b  nop     dword ptr [rax+rax+00h]
0x140210c30  mov     ecx, [rax+r13*8+3954h]
0x140210c38  shr     rcx, 10h
0x140210c3c  test    cx, cx
0x140210c3f  jz      loc_140210E84
0x140210c45  shr     rbx, 10h
0x140210c49  movzx   ecx, bx
0x140210c4c  inc     ecx
0x140210c4e  mov     [rsp+0B8h+c], ecx
0x140210c55  shr     r12, 10h
0x140210c59  movzx   r12d, r12w
0x140210c5d  inc     r12d
0x140210c60  mov     ebx, [rsp+0B8h+var_74]
0x140210c64  sub     ebx, [rsp+0B8h+var_94]
0x140210c68  cmp     ecx, ebx
0x140210c6a  jnz     loc_140210E1B
0x140210c70  call    cs:__imp_W32GetUserSessionState
0x140210c77  nop     dword ptr [rax+rax+00h]
0x140210c7c  movsx   ecx, word ptr [rax+r13*8+3950h]; a
0x140210c85  mov     r8d, [rsp+0B8h+c]; c
0x140210c8d  mov     edx, ebx; b
0x140210c8f  call    cs:__imp_EngMulDiv
0x140210c96  nop     dword ptr [rax+rax+00h]
0x140210c9b  mov     dword ptr [rsp+0B8h+var_88], eax
0x140210c9f  mov     ebx, [rsp+0B8h+var_70]
0x140210ca3  sub     ebx, [rsp+0B8h+var_90]
0x140210ca7  call    cs:__imp_W32GetUserSessionState
0x140210cae  nop     dword ptr [rax+rax+00h]
0x140210cb3  mov     r8d, r12d; c
0x140210cb6  mov     edx, ebx; b
0x140210cb8  cmp     r12d, ebx
0x140210cbb  jnz     loc_140210E4F
0x140210cc1  movsx   ecx, word ptr [rax+r13*8+3954h]; a
0x140210cca  call    cs:__imp_EngMulDiv
0x140210cd1  nop     dword ptr [rax+rax+00h]
0x140210cd6  mov     dword ptr [rsp+0B8h+var_88+4], eax
0x140210cda  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x140210ce1  nop     dword ptr [rax+rax+00h]
0x140210ce6  mov     r8d, eax
0x140210ce9  xor     r9d, r9d
0x140210cec  lea     rdx, [rsp+0B8h+var_88]
0x140210cf1  lea     rcx, [rsp+0B8h+var_80]
0x140210cf6  call    cs:__imp_PhysicalToLogicalDPIPoint
0x140210cfd  nop     dword ptr [rax+rax+00h]
0x140210d02  mov     r12d, r14d
0x140210d05  lea     rcx, [r12+r12*2]
0x140210d09  cmp     [rsp+0B8h+arg_18], 2
0x140210d11  jnz     loc_140210DE8
0x140210d17  call    GetCurrentThreadCompositedDpi
0x140210d1c  movzx   edx, ax
0x140210d1f  lea     rcx, [rsp+0B8h+var_58]
0x140210d24  call    GetScreenRectForDpi
0x140210d29  mov     ebx, [rsp+0B8h+var_54]
0x140210d2d  mov     r8d, [rsp+0B8h+var_50]
0x140210d32  mov     edi, [rsp+0B8h+var_4C]
0x140210d36  sub     r8d, [rsp+0B8h+var_58]
0x140210d3b  dec     r8d; c
0x140210d3e  movzx   ecx, word ptr [rsp+0B8h+var_80]; a
0x140210d43  mov     edx, 10000h; b
0x140210d48  call    cs:__imp_EngMulDiv
0x140210d4f  nop     dword ptr [rax+rax+00h]
0x140210d54  mov     rdx, [rsp+0B8h+arg_8]
0x140210d5c  lea     rcx, [r12+r12*2]
0x140210d60  mov     [rdx+rcx*8], eax
0x140210d63  sub     edi, ebx
0x140210d65  lea     r8d, [rdi-1]; c
0x140210d69  movzx   ecx, word ptr [rsp+0B8h+var_7C]; a
0x140210d6e  mov     edx, 10000h; b
0x140210d73  call    cs:__imp_EngMulDiv
0x140210d7a  nop     dword ptr [rax+rax+00h]
0x140210d7f  mov     rdi, [rsp+0B8h+arg_8]
0x140210d87  lea     rcx, [r12+r12*2]
0x140210d8b  mov     [rdi+rcx*8+4], eax
0x140210d8f  lea     rbx, [r12+r12*2]
0x140210d93  call    cs:__imp_W32GetUserSessionState
0x140210d9a  nop     dword ptr [rax+rax+00h]
0x140210d9f  mov     ecx, [rax+r13*8+3958h]
0x140210da7  mov     [rdi+rbx*8+8], ecx
0x140210dab  call    cs:__imp_W32GetUserSessionState
0x140210db2  nop     dword ptr [rax+rax+00h]
0x140210db7  mov     ecx, esi
0x140210db9  lea     rcx, [rcx+rcx*2]
0x140210dbd  mov     rax, [rax+rcx*8+3960h]
0x140210dc5  mov     [rdi+rbx*8+10h], rax
0x140210dca  test    esi, esi
0x140210dcc  jz      loc_140210E6D
0x140210dd2  dec     esi
0x140210dd4  and     esi, 3Fh
0x140210dd7  inc     r14d
0x140210dda  mov     [rsp+0B8h+var_78], r14d
0x140210ddf  mov     ecx, [rsp+0B8h+var_98]
0x140210de3  jmp     loc_140210BCC
0x140210de8  mov     eax, [rsp+0B8h+var_80]
0x140210dec  mov     [rdi+rcx*8], eax
0x140210def  mov     eax, [rsp+0B8h+var_7C]
0x140210df3  mov     [rdi+rcx*8+4], eax
0x140210df7  mov     r12d, r14d
0x140210dfa  lea     rcx, [r12+r12*2]
0x140210dfe  mov     eax, [rdi+rcx*8]
0x140210e01  test    eax, eax
0x140210e03  js      short loc_140210E77
0x140210e05  mov     eax, [rdi+rcx*8+4]
0x140210e09  test    eax, eax
0x140210e0b  jns     short loc_140210D8F
0x140210e0d  mov     eax, [rdi+rcx*8+4]
0x140210e11  add     eax, 10000h
0x140210e16  jmp     loc_140210D8B
0x140210e1b  call    cs:__imp_W32GetUserSessionState
0x140210e22  nop     dword ptr [rax+rax+00h]
0x140210e27  movzx   ecx, word ptr [rax+r13*8+3950h]; a
0x140210e30  mov     r8d, [rsp+0B8h+c]; c
0x140210e38  mov     edx, ebx; b
0x140210e3a  call    cs:__imp_EngMulDiv
0x140210e41  nop     dword ptr [rax+rax+00h]
0x140210e46  add     eax, [rsp+0B8h+var_94]
0x140210e4a  jmp     loc_140210C9B
0x140210e4f  movzx   ecx, word ptr [rax+r13*8+3954h]; a
0x140210e58  call    cs:__imp_EngMulDiv
0x140210e5f  nop     dword ptr [rax+rax+00h]
0x140210e64  add     eax, [rsp+0B8h+var_90]
0x140210e68  jmp     loc_140210CD6
0x140210e6d  mov     esi, 3Fh ; '?'
0x140210e72  jmp     loc_140210DD7
0x140210e77  mov     eax, [rdi+rcx*8]
0x140210e7a  add     eax, 10000h
0x140210e7f  mov     [rdi+rcx*8], eax
0x140210e82  jmp     short loc_140210E05
0x140210e84  jmp     short loc_140210E8B
0x140210e86  mov     r14d, [rsp+0B8h+var_78]
0x140210e8b  mov     eax, r14d
0x140210e8e  add     rsp, 88h
0x140210e95  pop     r14
0x140210e97  pop     r13
0x140210e99  pop     r12
0x140210e9b  pop     rdi
0x140210e9c  pop     rsi
0x140210e9d  pop     rbx
0x140210e9e  retn
0x140210ea0  mov     esi, 3Fh ; '?'
0x140210ea5  cmp     esi, ebx
0x140210ea7  jz      short loc_140210F1B
0x140210ea9  mov     r14d, [rsp+0B8h+var_74]
0x140210eae  jmp     loc_140210A51
0x140210eb3  mov     dword ptr [rsp+0B8h+var_88], r13d
0x140210eb8  mov     dword ptr [rsp+0B8h+var_88+4], r12d
0x140210ebd  call    cs:__imp_W32GetCurrentThreadDpiAwarenessContext
0x140210ec4  nop     dword ptr [rax+rax+00h]
0x140210ec9  mov     r8d, eax
0x140210ecc  xor     r9d, r9d
0x140210ecf  lea     rdx, [rsp+0B8h+var_88]
  ... truncated ...
```
