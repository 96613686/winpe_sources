# NtUserMsgWaitForMultipleObjectsEx

- ea: `0x1400c2110`
- end: `0x1400c26a3`
- name: `NtUserMsgWaitForMultipleObjectsEx`
- size: `1427`
- prototype: `__int64 __fastcall(unsigned int, volatile void *, int, int, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400c2110`
- `0x1400c26b0`
- `0x1400c2a10`
- `0x1400c2a64`
- `0x1400c2ab8`
- `0x1400c2b20`
- `0x1400c2e00`
- `0x140257240`
- `0x1402a4d38`
- `0x140342240`
- `0x140342540`

## import_xrefs

- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x1400c25e5`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x1400c25e5`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400c21eb`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400c2207`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400c21eb`
- `ntoskrnl!ZwCancelWaitCompletionPacket` at `0x1400c2207`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400c2436`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400c2436`
- `ntoskrnl!KeSetEvent` at `0x1400c2222`
- `ntoskrnl!KeSetEvent` at `0x1400c2222`
- `ntoskrnl!ProbeForRead` at `0x1400c245e`
- `ntoskrnl!ProbeForRead` at `0x1400c245e`
- `ntoskrnl!PsGetProcessPeb` at `0x1400c223e`
- `ntoskrnl!PsGetProcessPeb` at `0x1400c223e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c222f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c222f`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c214c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c21ca`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2510`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2592`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2625`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c214c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c21ca`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2510`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2592`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c2625`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400c23b1`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400c23b1`
- `win32kbase!EnterCrit` at `0x1400c2140`
- `win32kbase!EnterCrit` at `0x1400c2140`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c24a8`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c24a8`
- `win32kbase!Win32FreePool` at `0x1400c2489`
- `win32kbase!Win32FreePool` at `0x1400c2489`
- `win32kbase!Win32FreePool` at `0x1400c24e1`

## pseudocode

```c
__int64 __fastcall NtUserMsgWaitForMultipleObjectsEx(unsigned int a1, volatile void *a2, int a3, int a4, int a5)
{
  unsigned __int16 v5; // bx
  __int64 v7; // rsi
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // r12
  __int64 *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 CurrentProcess; // rax
  void *v19; // rbx
  __int64 v20; // r8
  _OWORD *v21; // rax
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  _OWORD *v24; // rcx
  _OWORD *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // rax
  _QWORD *v28; // rbx
  int *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r10
  int v34; // eax
  __int64 CurrentProcessWow64Process; // rax
  ULONG v36; // r8d
  __int64 *v38; // rax
  __int64 v39; // rbx
  _QWORD *v40; // rax
  _QWORD *v41; // rcx
  int *v42; // rax
  __int64 *v43; // rax
  int v44; // [rsp+40h] [rbp-928h] BYREF
  int v45; // [rsp+44h] [rbp-924h] BYREF
  int v46; // [rsp+48h] [rbp-920h]
  int v47; // [rsp+4Ch] [rbp-91Ch]
  int v48; // [rsp+50h] [rbp-918h]
  int v49; // [rsp+54h] [rbp-914h]
  int v50; // [rsp+58h] [rbp-910h]
  void *v51; // [rsp+60h] [rbp-908h]
  __int64 ProcessPeb; // [rsp+68h] [rbp-900h]
  __int64 InputEvent; // [rsp+70h] [rbp-8F8h]
  _BYTE v54[24]; // [rsp+78h] [rbp-8F0h] BYREF
  _BYTE v55[32]; // [rsp+90h] [rbp-8D8h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-8B8h]
  __int64 v57; // [rsp+B8h] [rbp-8B0h]
  __int64 v58; // [rsp+C0h] [rbp-8A8h]
  _BYTE v59[1160]; // [rsp+4E0h] [rbp-488h] BYREF

  v5 = a4;
  v47 = a4;
  v48 = a3;
  v7 = a1;
  EnterCrit(0, 0);
  CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    CurrentThreadWin32Thread = (_QWORD *)*CurrentThreadWin32Thread;
  if ( (a5 & 0xFFFFFFE0) != 0 || (unsigned int)v7 > 0x3F )
  {
    v12 = -1;
    UserSetLastError(87);
    goto LABEL_32;
  }
  v11 = CurrentThreadWin32Thread[60];
  if ( v11 && ((a5 & 1) == 0 || !(_DWORD)v7) )
  {
    v13 = *(unsigned int *)(v11 + 4);
    if ( (a5 & 4) != 0 )
    {
      v44 = *(_DWORD *)(v11 + 8);
      v42 = &v44;
    }
    else
    {
      v45 = 0;
      v42 = &v45;
    }
    if ( ((unsigned __int16)(v13 | *v42) & v5) != 0 )
    {
      v12 = v7;
      goto LABEL_32;
    }
  }
  v12 = -1;
  InputEvent = xxxGetInputEvent(v5 | ((unsigned __int16)a5 << 16));
  if ( InputEvent )
  {
    v49 = -1;
    v51 = 0;
    if ( (a5 & 1) != 0 )
    {
      v14 = 0;
      v15 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v15 )
        v16 = *v15;
      else
        v16 = 0;
      if ( (unsigned int)ZwCancelWaitCompletionPacket(*(_QWORD *)(v16 + 1640), 0) == 259 )
      {
        LOBYTE(v17) = 1;
        ZwCancelWaitCompletionPacket(*(_QWORD *)(v16 + 1640), v17);
        KeSetEvent(*(PRKEVENT *)(v16 + 760), 1, 0);
      }
    }
    else
    {
      v43 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v43 )
        v13 = *v43;
      else
        v13 = 0;
      v14 = *(_QWORD *)(v13 + 1624);
      if ( !v14 )
        goto LABEL_32;
    }
    CurrentProcess = PsGetCurrentProcess();
    ProcessPeb = PsGetProcessPeb(CurrentProcess);
    v19 = *(void **)(ProcessPeb + 32);
    memset_0(v55, 0, 0x450u);
    RtlCopyFromUser(v55, v19, 0x450u);
    v21 = v59;
    v22 = v55;
    v23 = 8;
    do
    {
      *v21 = *v22;
      v21[1] = v22[1];
      v21[2] = v22[2];
      v21[3] = v22[3];
      v21[4] = v22[4];
      v21[5] = v22[5];
      v21[6] = v22[6];
      v21[7] = v22[7];
      v21 += 8;
      v22 += 8;
      --v23;
    }
    while ( v23 );
    *v21 = *v22;
    v21[1] = v22[1];
    v21[2] = v22[2];
    v21[3] = v22[3];
    v21[4] = v22[4];
    v24 = v55;
    v25 = v59;
    v26 = 8;
    do
    {
      *v24 = *v25;
      v24[1] = v25[1];
      v24[2] = v25[2];
      v24[3] = v25[3];
      v24[4] = v25[4];
      v24[5] = v25[5];
      v24[6] = v25[6];
      v24[7] = v25[7];
      v24 += 8;
      v25 += 8;
      --v26;
    }
    while ( v26 );
    *v24 = *v25;
    v24[1] = v25[1];
    v24[2] = v25[2];
    v24[3] = v25[3];
    v24[4] = v25[4];
    if ( (_DWORD)v7 )
    {
      CurrentProcessWow64Process = PsGetCurrentProcessWow64Process(v24, 0, v20);
      v36 = 1;
      if ( !CurrentProcessWow64Process )
        v36 = 4;
      ProbeForRead(a2, 8 * v7, v36);
    }
    v27 = (_QWORD *)Win32AllocPoolWithQuotaZInit(8LL * (unsigned int)(v7 + 1), 2037609301);
    v28 = v27;
    v51 = v27;
    if ( v27 )
    {
      memmove(v27, (const void *)a2, 8 * v7);
      v30 = 0;
      v46 = 0;
      v31 = v58;
      v32 = v57;
      v33 = v56;
      while ( (unsigned int)v30 < (unsigned int)v7 )
      {
        v29 = (int *)&v28[v30];
        v34 = *v29;
        if ( *v29 == -11 )
        {
          *(_QWORD *)v29 = v32;
        }
        else if ( v34 == -12 )
        {
          *(_QWORD *)v29 = v31;
        }
        else if ( v34 == -10 )
        {
          *(_QWORD *)v29 = v33;
        }
        v30 = (unsigned int)(v30 + 1);
        v46 = v30;
      }
      if ( (a5 & 8) != 0 )
        SetWaitForQueueAttach(1, v29, v31, v32);
      if ( (a5 & 1) != 0 )
        v14 = InputEvent;
      v28[v7] = v14;
      Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
        v54,
        v28,
        Win32FreePool,
        v32);
      v12 = xxxMsgWaitForMultipleObjectsEx(v7, (_DWORD)v28, v48, v47, a5);
      v38 = (__int64 *)PsGetCurrentThreadWin32Thread();
      if ( v38 )
        v39 = *v38;
      else
        v39 = 0;
      _InterlockedExchange(
        (volatile __int32 *)(*(_QWORD *)(v39 + 480) + 20LL),
        (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
      if ( !*(_DWORD *)(v39 + 1304) )
        xxxUpdateInputHangInfo(0, 1);
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v39 + 480) + 16LL), 0);
      *(_QWORD *)(v39 + 1360) &= ~0x400uLL;
      Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(v54);
      if ( (a5 & 1) != 0 )
      {
        v40 = (_QWORD *)PsGetCurrentThreadWin32Thread();
        if ( v40 )
          v41 = (_QWORD *)*v40;
        else
          v41 = 0;
        ZwAssociateWaitCompletionPacket(v41[205], v41[202], v41[204], 0, 0xFFFFFFFF80000000uLL, 0, 0, 0);
      }
    }
    else
    {
      v50 = -1;
      UserSetLastError(8);
    }
  }
LABEL_32:
  UserSessionSwitchLeaveCrit(v13, v9, v10);
  return v12;
}

```

## disassembly

```asm
0x1400c2110  push    rbx
0x1400c2112  push    rsi
0x1400c2113  push    rdi
0x1400c2114  push    r12
0x1400c2116  push    r13
0x1400c2118  push    r14
0x1400c211a  push    r15
0x1400c211c  sub     rsp, 930h
0x1400c2123  mov     ebx, r9d
0x1400c2126  mov     [rsp+968h+var_91C], ebx
0x1400c212a  mov     [rsp+968h+var_918], r8d
0x1400c212f  mov     r13, rdx
0x1400c2132  mov     esi, ecx
0x1400c2134  mov     r15d, [rsp+968h+arg_20]
0x1400c213c  xor     edx, edx
0x1400c213e  xor     ecx, ecx
0x1400c2140  call    cs:__imp_EnterCrit
0x1400c2147  nop     dword ptr [rax+rax+00h]
0x1400c214c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c2153  nop     dword ptr [rax+rax+00h]
0x1400c2158  test    rax, rax
0x1400c215b  jz      short loc_1400C2160
0x1400c215d  mov     rax, [rax]
0x1400c2160  test    r15d, 0FFFFFFE0h
0x1400c2167  jnz     loc_1400C2667
0x1400c216d  cmp     esi, 3Fh ; '?'
0x1400c2170  ja      loc_1400C2667
0x1400c2176  mov     r14d, r15d
0x1400c2179  and     r14d, 1
0x1400c217d  mov     rax, [rax+1E0h]
0x1400c2184  test    rax, rax
0x1400c2187  jnz     loc_1400C25F6
0x1400c218d  mov     edi, 0FFFFFFFFh
0x1400c2192  movzx   ecx, r15w
0x1400c2196  shl     ecx, 10h
0x1400c2199  movzx   eax, bx
0x1400c219c  or      ecx, eax
0x1400c219e  call    xxxGetInputEvent
0x1400c21a3  mov     [rsp+968h+var_8F8], rax
0x1400c21a8  test    rax, rax
0x1400c21ab  jz      loc_1400C24A8
0x1400c21b1  mov     [rsp+968h+var_914], edi
0x1400c21b5  mov     [rsp+968h+var_908], 0
0x1400c21be  test    r14d, r14d
0x1400c21c1  jz      loc_1400C2625
0x1400c21c7  xor     r12d, r12d
0x1400c21ca  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c21d1  nop     dword ptr [rax+rax+00h]
0x1400c21d6  test    rax, rax
0x1400c21d9  jz      loc_1400C267B
0x1400c21df  mov     rbx, [rax]
0x1400c21e2  xor     edx, edx
0x1400c21e4  mov     rcx, [rbx+668h]
0x1400c21eb  call    cs:__imp_ZwCancelWaitCompletionPacket
0x1400c21f2  nop     dword ptr [rax+rax+00h]
0x1400c21f7  cmp     eax, 103h
0x1400c21fc  jnz     short loc_1400C222F
0x1400c21fe  mov     dl, 1
0x1400c2200  mov     rcx, [rbx+668h]
0x1400c2207  call    cs:__imp_ZwCancelWaitCompletionPacket
0x1400c220e  nop     dword ptr [rax+rax+00h]
0x1400c2213  xor     r8d, r8d; Wait
0x1400c2216  mov     edx, 1; Increment
0x1400c221b  mov     rcx, [rbx+2F8h]; Event
0x1400c2222  call    cs:__imp_KeSetEvent
0x1400c2229  nop     dword ptr [rax+rax+00h]
0x1400c222e  nop
0x1400c222f  call    cs:__imp_PsGetCurrentProcess
0x1400c2236  nop     dword ptr [rax+rax+00h]
0x1400c223b  mov     rcx, rax
0x1400c223e  call    cs:__imp_PsGetProcessPeb
0x1400c2245  nop     dword ptr [rax+rax+00h]
0x1400c224a  mov     [rsp+968h+var_900], rax
0x1400c224f  mov     rax, [rsp+968h+var_900]
0x1400c2254  mov     rbx, [rax+20h]
0x1400c2258  xor     edx, edx; Val
0x1400c225a  mov     r8d, 450h; Size
0x1400c2260  lea     rcx, [rsp+968h+var_8D8]; void *
0x1400c2268  call    memset_0
0x1400c226d  mov     r8d, 450h; Size
0x1400c2273  mov     rdx, rbx; Src
0x1400c2276  lea     rcx, [rsp+968h+var_8D8]; void *
0x1400c227e  call    RtlCopyFromUser
0x1400c2283  lea     rax, [rsp+968h+var_488]
0x1400c228b  lea     rcx, [rsp+968h+var_8D8]
0x1400c2293  mov     edx, 8
0x1400c2298  movups  xmm0, xmmword ptr [rcx]
0x1400c229b  movups  xmmword ptr [rax], xmm0
0x1400c229e  movups  xmm1, xmmword ptr [rcx+10h]
0x1400c22a2  movups  xmmword ptr [rax+10h], xmm1
0x1400c22a6  movups  xmm0, xmmword ptr [rcx+20h]
0x1400c22aa  movups  xmmword ptr [rax+20h], xmm0
0x1400c22ae  movups  xmm1, xmmword ptr [rcx+30h]
0x1400c22b2  movups  xmmword ptr [rax+30h], xmm1
0x1400c22b6  movups  xmm0, xmmword ptr [rcx+40h]
0x1400c22ba  movups  xmmword ptr [rax+40h], xmm0
0x1400c22be  movups  xmm1, xmmword ptr [rcx+50h]
0x1400c22c2  movups  xmmword ptr [rax+50h], xmm1
0x1400c22c6  movups  xmm0, xmmword ptr [rcx+60h]
0x1400c22ca  movups  xmmword ptr [rax+60h], xmm0
0x1400c22ce  movups  xmm1, xmmword ptr [rcx+70h]
0x1400c22d2  movups  xmmword ptr [rax+70h], xmm1
0x1400c22d6  lea     rax, [rax+80h]
0x1400c22dd  lea     rcx, [rcx+80h]
0x1400c22e4  sub     rdx, 1
0x1400c22e8  jnz     short loc_1400C2298
0x1400c22ea  movups  xmm0, xmmword ptr [rcx]
0x1400c22ed  movups  xmmword ptr [rax], xmm0
0x1400c22f0  movups  xmm1, xmmword ptr [rcx+10h]
0x1400c22f4  movups  xmmword ptr [rax+10h], xmm1
0x1400c22f8  movups  xmm0, xmmword ptr [rcx+20h]
0x1400c22fc  movups  xmmword ptr [rax+20h], xmm0
0x1400c2300  movups  xmm1, xmmword ptr [rcx+30h]
0x1400c2304  movups  xmmword ptr [rax+30h], xmm1
0x1400c2308  movups  xmm0, xmmword ptr [rcx+40h]
0x1400c230c  movups  xmmword ptr [rax+40h], xmm0
0x1400c2310  lea     rcx, [rsp+968h+var_8D8]
0x1400c2318  lea     rax, [rsp+968h+var_488]
0x1400c2320  mov     edx, 8
0x1400c2325  movups  xmm0, xmmword ptr [rax]
0x1400c2328  movups  xmmword ptr [rcx], xmm0
0x1400c232b  movups  xmm1, xmmword ptr [rax+10h]
0x1400c232f  movups  xmmword ptr [rcx+10h], xmm1
0x1400c2333  movups  xmm0, xmmword ptr [rax+20h]
0x1400c2337  movups  xmmword ptr [rcx+20h], xmm0
0x1400c233b  movups  xmm1, xmmword ptr [rax+30h]
0x1400c233f  movups  xmmword ptr [rcx+30h], xmm1
0x1400c2343  movups  xmm0, xmmword ptr [rax+40h]
0x1400c2347  movups  xmmword ptr [rcx+40h], xmm0
0x1400c234b  movups  xmm1, xmmword ptr [rax+50h]
0x1400c234f  movups  xmmword ptr [rcx+50h], xmm1
0x1400c2353  movups  xmm0, xmmword ptr [rax+60h]
0x1400c2357  movups  xmmword ptr [rcx+60h], xmm0
0x1400c235b  movups  xmm1, xmmword ptr [rax+70h]
0x1400c235f  movups  xmmword ptr [rcx+70h], xmm1
0x1400c2363  lea     rcx, [rcx+80h]
0x1400c236a  lea     rax, [rax+80h]
0x1400c2371  sub     rdx, 1
0x1400c2375  jnz     short loc_1400C2325
0x1400c2377  movups  xmm0, xmmword ptr [rax]
0x1400c237a  movups  xmmword ptr [rcx], xmm0
0x1400c237d  movups  xmm1, xmmword ptr [rax+10h]
0x1400c2381  movups  xmmword ptr [rcx+10h], xmm1
0x1400c2385  movups  xmm0, xmmword ptr [rax+20h]
0x1400c2389  movups  xmmword ptr [rcx+20h], xmm0
0x1400c238d  movups  xmm1, xmmword ptr [rax+30h]
0x1400c2391  movups  xmmword ptr [rcx+30h], xmm1
0x1400c2395  movups  xmm0, xmmword ptr [rax+40h]
0x1400c2399  movups  xmmword ptr [rcx+40h], xmm0
0x1400c239d  test    esi, esi
0x1400c239f  jnz     loc_1400C2436
0x1400c23a5  lea     ecx, [rsi+1]
0x1400c23a8  shl     rcx, 3
0x1400c23ac  mov     edx, 79737355h
0x1400c23b1  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x1400c23b8  nop     dword ptr [rax+rax+00h]
0x1400c23bd  mov     rbx, rax
0x1400c23c0  mov     [rsp+968h+var_908], rax
0x1400c23c5  test    rax, rax
0x1400c23c8  jz      loc_1400C246F
0x1400c23ce  mov     rdi, rsi
0x1400c23d1  shl     rdi, 3
0x1400c23d5  mov     r8, rdi; Size
0x1400c23d8  mov     rdx, r13; Src
0x1400c23db  mov     rcx, rax; void *
0x1400c23de  call    memmove
0x1400c23e3  xor     ecx, ecx
0x1400c23e5  mov     [rsp+968h+var_920], ecx
0x1400c23e9  mov     r8, [rsp+968h+var_8A8]
0x1400c23f1  mov     r9, [rsp+968h+var_8B0]
0x1400c23f9  mov     r10, [rsp+968h+var_8B8]
0x1400c2401  cmp     ecx, esi
0x1400c2403  jnb     short loc_1400C2422
0x1400c2405  lea     rdx, [rbx+rcx*8]
0x1400c2409  mov     eax, [rdx]
0x1400c240b  cmp     eax, 0FFFFFFF5h
0x1400c240e  jz      short loc_1400C2427
0x1400c2410  cmp     eax, 0FFFFFFF4h
0x1400c2413  jz      short loc_1400C2431
0x1400c2415  cmp     eax, 0FFFFFFF6h
0x1400c2418  jz      short loc_1400C242C
0x1400c241a  inc     ecx
0x1400c241c  mov     [rsp+968h+var_920], ecx
0x1400c2420  jmp     short loc_1400C2401
0x1400c2422  jmp     loc_1400C24CA
0x1400c2427  mov     [rdx], r9
0x1400c242a  jmp     short loc_1400C241A
0x1400c242c  mov     [rdx], r10
0x1400c242f  jmp     short loc_1400C241A
0x1400c2431  mov     [rdx], r8
0x1400c2434  jmp     short loc_1400C241A
0x1400c2436  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1400c243d  nop     dword ptr [rax+rax+00h]
0x1400c2442  mov     ecx, 4
0x1400c2447  mov     r8d, 1
0x1400c244d  test    rax, rax
0x1400c2450  cmovz   r8d, ecx; Alignment
0x1400c2454  mov     rdx, rsi
0x1400c2457  shl     rdx, 3; Length
0x1400c245b  mov     rcx, r13; Address
0x1400c245e  call    cs:__imp_ProbeForRead
0x1400c2465  nop     dword ptr [rax+rax+00h]
0x1400c246a  jmp     loc_1400C23A5
0x1400c246f  mov     [rsp+968h+var_910], edi
0x1400c2473  mov     ecx, 8
0x1400c2478  call    UserSetLastError
0x1400c247d  jmp     short loc_1400C24A8
0x1400c247f  mov     rcx, [rsp+968h+var_908]
0x1400c2484  test    rcx, rcx
0x1400c2487  jz      short loc_1400C2495
0x1400c2489  call    cs:__imp_Win32FreePool
0x1400c2490  nop     dword ptr [rax+rax+00h]
0x1400c2495  mov     edi, [rsp+968h+var_914]
0x1400c2499  mov     [rsp+968h+var_910], edi
0x1400c249d  mov     ecx, 57h ; 'W'
0x1400c24a2  call    UserSetLastError
0x1400c24a7  nop
0x1400c24a8  call    cs:__imp_UserSessionSwitchLeaveCrit
0x1400c24af  nop     dword ptr [rax+rax+00h]
0x1400c24b4  mov     eax, edi
0x1400c24b6  add     rsp, 930h
0x1400c24bd  pop     r15
0x1400c24bf  pop     r14
0x1400c24c1  pop     r13
0x1400c24c3  pop     r12
0x1400c24c5  pop     rdi
0x1400c24c6  pop     rsi
0x1400c24c7  pop     rbx
0x1400c24c8  retn
0x1400c24ca  test    r15b, 8
0x1400c24ce  jnz     loc_1400C2694
0x1400c24d4  test    r14d, r14d
0x1400c24d7  cmovnz  r12, [rsp+968h+var_8F8]
0x1400c24dd  mov     [rdi+rbx], r12
0x1400c24e1  mov     r8, cs:__imp_Win32FreePool
0x1400c24e8  mov     rdx, rbx
0x1400c24eb  lea     rcx, [rsp+968h+var_8F0]
0x1400c24f0  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400c24f5  mov     dword ptr [rsp+968h+var_948], r15d
0x1400c24fa  mov     r9d, [rsp+968h+var_91C]
0x1400c24ff  mov     r8d, [rsp+968h+var_918]
0x1400c2504  mov     rdx, rbx
0x1400c2507  mov     ecx, esi
0x1400c2509  call    xxxMsgWaitForMultipleObjectsEx
0x1400c250e  mov     edi, eax
0x1400c2510  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c2517  nop     dword ptr [rax+rax+00h]
0x1400c251c  test    rax, rax
0x1400c251f  jz      loc_1400C2682
0x1400c2525  mov     rbx, [rax]
0x1400c2528  mov     rax, 0FFFFF78000000320h
0x1400c2532  mov     rax, [rax]
0x1400c2535  mov     rcx, 0FFFFF78000000004h
0x1400c253f  mov     ecx, [rcx]
0x1400c2541  imul    rcx, rax
0x1400c2545  shr     rcx, 18h
0x1400c2549  mov     rax, [rbx+1E0h]
0x1400c2550  xchg    ecx, [rax+14h]
0x1400c2553  cmp     dword ptr [rbx+518h], 0
0x1400c255a  jnz     short loc_1400C2568
0x1400c255c  mov     edx, 1
0x1400c2561  xor     ecx, ecx
0x1400c2563  call    ?xxxUpdateInputHangInfo@@YAXPEAUtagWND@@W4INPUTHANGTIME@@@Z; xxxUpdateInputHangInfo(tagWND *,INPUTHANGTIME)
0x1400c2568  mov     rcx, [rbx+1E0h]
0x1400c256f  xor     eax, eax
0x1400c2571  xchg    eax, [rcx+10h]
0x1400c2574  and     qword ptr [rbx+550h], 0FFFFFFFFFFFFFBFFh
0x1400c257f  lea     rcx, [rsp+968h+var_8F0]
0x1400c2584  call    ??1?$Win32RawLockedItem@UtagEVENT_PACKET_TARGETS@@$0A@@@QEAA@XZ; Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>::~Win32RawLockedItem<tagEVENT_PACKET_TARGETS,0>(void)
0x1400c2589  test    r14d, r14d
0x1400c258c  jz      loc_1400C24A8
0x1400c2592  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c2599  nop     dword ptr [rax+rax+00h]
0x1400c259e  test    rax, rax
0x1400c25a1  jz      loc_1400C2689
0x1400c25a7  mov     rcx, [rax]
0x1400c25aa  mov     [rsp+968h+var_930], 0
0x1400c25b3  mov     [rsp+968h+var_938], 0
0x1400c25bc  mov     [rsp+968h+var_940], 0
0x1400c25c4  mov     [rsp+968h+var_948], 0FFFFFFFF80000000h
0x1400c25cd  xor     r9d, r9d
0x1400c25d0  mov     r8, [rcx+660h]
0x1400c25d7  mov     rdx, [rcx+650h]
0x1400c25de  mov     rcx, [rcx+668h]
0x1400c25e5  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x1400c25ec  nop     dword ptr [rax+rax+00h]
0x1400c25f1  jmp     loc_1400C24A8
0x1400c25f6  test    r14d, r14d
0x1400c25f9  jnz     short loc_1400C265D
0x1400c25fb  mov     ecx, [rax+4]
0x1400c25fe  test    r15b, 4
0x1400c2602  jz      short loc_1400C264E
0x1400c2604  mov     eax, [rax+8]
0x1400c2607  mov     [rsp+968h+var_928], eax
0x1400c260b  lea     rax, [rsp+968h+var_928]
0x1400c2610  mov     eax, [rax]
0x1400c2612  or      ax, cx
0x1400c2615  test    bx, ax
0x1400c2618  jz      loc_1400C218D
0x1400c261e  mov     edi, esi
  ... truncated ...
```
