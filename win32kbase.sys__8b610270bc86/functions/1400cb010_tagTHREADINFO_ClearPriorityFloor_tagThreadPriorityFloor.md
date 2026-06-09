# tagTHREADINFO::ClearPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400cb010`
- end: `0x1400cb44a`
- name: `?ClearPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `1082`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400cb010`
- `0x1400cb450`
- `0x1400cb890`
- `0x1400cb9dc`
- `0x1400cbab8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400cb090`
- `ntoskrnl!KeBugCheckEx` at `0x1400cb090`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cb05f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cb05f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cb04a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cb04a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cb33e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cb33e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cb332`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cb332`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400cb263`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400cb263`
- `ntoskrnl!PsGetThreadId` at `0x1400cb0f3`
- `ntoskrnl!PsGetThreadId` at `0x1400cb1fb`
- `ntoskrnl!PsGetThreadId` at `0x1400cb2cc`
- `ntoskrnl!PsGetThreadId` at `0x1400cb3bb`
- `ntoskrnl!PsGetThreadId` at `0x1400cb0f3`
- `ntoskrnl!PsGetThreadId` at `0x1400cb1fb`
- `ntoskrnl!PsGetThreadId` at `0x1400cb2cc`
- `ntoskrnl!PsGetThreadId` at `0x1400cb3bb`
- `WIN32K!W32GetUserSessionState` at `0x1400cb10c`
- `WIN32K!W32GetUserSessionState` at `0x1400cb20a`
- `WIN32K!W32GetUserSessionState` at `0x1400cb2db`
- `WIN32K!W32GetUserSessionState` at `0x1400cb3ca`
- `WIN32K!W32GetUserSessionState` at `0x1400cb10c`
- `WIN32K!W32GetUserSessionState` at `0x1400cb20a`
- `WIN32K!W32GetUserSessionState` at `0x1400cb2db`
- `WIN32K!W32GetUserSessionState` at `0x1400cb3ca`

## pseudocode

```c
void __fastcall tagTHREADINFO::ClearPriorityFloor(_QWORD *a1, unsigned int a2)
{
  char v2; // r15
  __int64 v4; // rsi
  __int64 v5; // rbx
  int v6; // esi
  CTouchProcessor **v7; // r9
  __int64 v8; // r8
  bool v9; // r12
  bool v10; // r13
  __int64 UserSessionState; // rax
  int v12; // r8d
  int v13; // edx
  bool v14; // zf
  int v15; // edx
  unsigned __int16 v16; // ax
  unsigned int v17; // ebp
  bool v18; // di
  bool v19; // si
  char ThreadId; // bl
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  __int64 v25; // rdx
  bool v26; // r12
  __int16 v27; // si
  int v28; // ebp
  char v29; // di
  char v30; // bl
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  bool v35; // di
  bool v36; // si
  char v37; // bl
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v43; // [rsp+28h] [rbp-80h]
  int v44; // [rsp+38h] [rbp-70h]
  char v45; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1 )
    goto LABEL_3;
  _mm_lfence();
  v4 = a2;
  v5 = LOBYTE(asc_1402571F0[4 * a2]);
  v45 = asc_1402571F0[4 * a2];
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 216, 0);
  if ( !*((_BYTE *)a1 + v5 + 1744) )
    goto LABEL_3;
  v6 = *(_DWORD *)&asc_1402571F0[4 * v4 + 2];
  if ( (*((_DWORD *)a1 + 435) & v6) != v6 )
    goto LABEL_3;
  v7 = &WPP_GLOBAL_Control;
  v8 = 4096;
  v9 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId((PETHREAD)*a1);
    UserSessionState = W32GetUserSessionState(a1[57]);
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v9;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v13, v12, *(_QWORD *)(UserSessionState + 69136));
    v8 = 4096;
    v7 = &WPP_GLOBAL_Control;
  }
  *((_DWORD *)a1 + 435) &= ~v6;
  v14 = (*((_BYTE *)a1 + (unsigned int)v5 + 1744))-- == 1;
  if ( v14 )
  {
    v15 = 1 << v5;
    if ( ((1 << v5) & (unsigned __int16)a1[217]) == 1 << v5 )
    {
      v16 = a1[217] & ~(_WORD)v15;
      *((_WORD *)a1 + 868) = v16;
      if ( v16 < v15 )
      {
        v14 = !_BitScanReverse(&v17, v16);
        if ( v14 )
        {
          v18 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v22 = W32GetUserSessionState(v21);
            LOBYTE(v23) = v19;
            LOBYTE(v24) = v18;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v24,
              v23,
              *(_QWORD *)(v22 + 69136),
              4,
              13,
              20,
              (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
              ThreadId);
            LOBYTE(v5) = v45;
          }
          v25 = 0;
        }
        else
        {
          v35 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v36 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v35 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v37 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v39 = W32GetUserSessionState(v38);
            LOBYTE(v40) = v36;
            LOBYTE(v41) = v35;
            WPP_RECORDER_AND_TRACE_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v41,
              v40,
              *(_QWORD *)(v39 + 69136),
              4,
              13,
              19,
              (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
              v17,
              v37);
            LOBYTE(v5) = v45;
          }
          v25 = v17;
        }
        PsAdjustWin32kPriorityFloor(*a1, v25, v8, v7);
      }
      goto LABEL_22;
    }
LABEL_3:
    KeBugCheckEx(0x164u, 0x41u, 0, 0, 0);
  }
LABEL_22:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v2 = 0;
  }
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v27 = *((_WORD *)a1 + 868);
    v28 = *((_DWORD *)a1 + 435);
    v29 = *((_BYTE *)a1 + (unsigned __int8)v5 + 1744);
    v30 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v32 = W32GetUserSessionState(v31);
    LOBYTE(v33) = v26;
    LOBYTE(v34) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v34,
      v33,
      *(_QWORD *)(v32 + 69136),
      BugCheckParameter4,
      v43,
      21,
      v44,
      v30,
      v45,
      v29,
      v28,
      v27);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0, v8, v7);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400cb010  mov     [rsp+arg_0], rbx
0x1400cb015  push    rbp
0x1400cb016  push    rsi
0x1400cb017  push    rdi
0x1400cb018  push    r12
0x1400cb01a  push    r13
0x1400cb01c  push    r14
0x1400cb01e  push    r15
0x1400cb020  sub     rsp, 70h
0x1400cb024  mov     r15d, 1
0x1400cb02a  mov     r14, rcx
0x1400cb02d  cmp     edx, r15d
0x1400cb030  ja      short loc_1400CB078
0x1400cb032  lfence
0x1400cb035  mov     esi, edx
0x1400cb037  lea     r12, asc_1402571F0; "\r"
0x1400cb03e  movzx   ebx, byte ptr [r12+rsi*8]
0x1400cb043  mov     [rsp+0A8h+arg_8], bl
0x1400cb04a  call    cs:__imp_KeEnterCriticalRegion
0x1400cb051  nop     dword ptr [rax+rax+00h]
0x1400cb056  xor     edx, edx
0x1400cb058  lea     rcx, [r14+6C0h]
0x1400cb05f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400cb066  nop     dword ptr [rax+rax+00h]
0x1400cb06b  cmp     byte ptr [r14+rbx+6D0h], 0
0x1400cb074  mov     ebp, ebx
0x1400cb076  jnz     short loc_1400CB09D
0x1400cb078  xor     r9d, r9d; BugCheckParameter3
0x1400cb07b  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400cb084  xor     r8d, r8d; BugCheckParameter2
0x1400cb087  mov     ecx, 164h; BugCheckCode
0x1400cb08c  lea     edx, [r9+41h]; BugCheckParameter1
0x1400cb090  call    cs:__imp_KeBugCheckEx
0x1400cb09d  mov     esi, [r12+rsi*8+4]
0x1400cb0a2  mov     eax, esi
0x1400cb0a4  and     eax, [r14+6CCh]
0x1400cb0ab  cmp     eax, esi
0x1400cb0ad  jnz     short loc_1400CB078
0x1400cb0af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb0b6  lea     r9, WPP_GLOBAL_Control
0x1400cb0bd  mov     r8d, 1000h
0x1400cb0c3  cmp     rcx, r9
0x1400cb0c6  jz      short loc_1400CB0D2
0x1400cb0c8  test    [rcx+2Ch], r8d
0x1400cb0cc  jnz     loc_1400CB371
0x1400cb0d2  xor     r12b, r12b
0x1400cb0d5  lea     r10, WPP_RECORDER_INITIALIZED
0x1400cb0dc  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400cb0e3  setnz   r13b
0x1400cb0e7  test    r12b, r12b
0x1400cb0ea  jz      loc_1400CB363
0x1400cb0f0  mov     rcx, [r14]; Thread
0x1400cb0f3  call    cs:__imp_PsGetThreadId
0x1400cb0fa  nop     dword ptr [rax+rax+00h]
0x1400cb0ff  mov     rcx, [r14+1C8h]
0x1400cb106  mov     rdi, rax
0x1400cb109  mov     ebx, [rcx+38h]
0x1400cb10c  call    cs:__imp_W32GetUserSessionState
0x1400cb113  nop     dword ptr [rax+rax+00h]
0x1400cb118  movzx   ecx, bpl
0x1400cb11c  mov     r8b, r13b
0x1400cb11f  mov     [rsp+0A8h+var_50], ecx
0x1400cb123  mov     dl, r12b
0x1400cb126  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb12d  mov     r9, [rax+10E10h]
0x1400cb134  mov     [rsp+0A8h+var_58], esi
0x1400cb138  mov     [rsp+0A8h+var_60], edi
0x1400cb13c  mov     rcx, [rcx+18h]
0x1400cb140  mov     [rsp+0A8h+var_68], ebx
0x1400cb144  mov     [rsp+0A8h+var_78], 12h
0x1400cb14b  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400cb150  mov     r8d, 1000h
0x1400cb156  lea     r9, WPP_GLOBAL_Control
0x1400cb15d  lea     r10, WPP_RECORDER_INITIALIZED
0x1400cb164  mov     bl, bpl
0x1400cb167  not     esi
0x1400cb169  and     [r14+6CCh], esi
0x1400cb170  add     byte ptr [r14+rbp+6D0h], 0FFh
0x1400cb179  jnz     loc_1400CB26F
0x1400cb17f  mov     cl, bl
0x1400cb181  mov     edx, r15d
0x1400cb184  shl     edx, cl
0x1400cb186  movzx   ecx, word ptr [r14+6C8h]
0x1400cb18e  mov     eax, ecx
0x1400cb190  and     eax, edx
0x1400cb192  cmp     eax, edx
0x1400cb194  jnz     loc_1400CB078
0x1400cb19a  movzx   eax, dx
0x1400cb19d  not     ax
0x1400cb1a0  and     ax, cx
0x1400cb1a3  movzx   ecx, ax
0x1400cb1a6  mov     [r14+6C8h], cx
0x1400cb1ae  cmp     ecx, edx
0x1400cb1b0  jge     loc_1400CB26F
0x1400cb1b6  bsr     ebp, ecx
0x1400cb1b9  mov     [rsp+0A8h+arg_10], 0
0x1400cb1c4  jnz     loc_1400CB383
0x1400cb1ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb1d1  cmp     rcx, r9
0x1400cb1d4  jz      short loc_1400CB1E0
0x1400cb1d6  test    [rcx+2Ch], r8d
0x1400cb1da  jnz     loc_1400CB429
0x1400cb1e0  xor     dil, dil
0x1400cb1e3  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400cb1ea  setnz   sil
0x1400cb1ee  test    dil, dil
0x1400cb1f1  jnz     short loc_1400CB1F8
0x1400cb1f3  test    sil, sil
0x1400cb1f6  jz      short loc_1400CB25E
0x1400cb1f8  mov     rcx, [r14]; Thread
0x1400cb1fb  call    cs:__imp_PsGetThreadId
0x1400cb202  nop     dword ptr [rax+rax+00h]
0x1400cb207  mov     rbx, rax
0x1400cb20a  call    cs:__imp_W32GetUserSessionState
0x1400cb211  nop     dword ptr [rax+rax+00h]
0x1400cb216  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb21d  mov     r8b, sil
0x1400cb220  mov     [rsp+0A8h+var_68], ebx
0x1400cb224  mov     dl, dil
0x1400cb227  mov     r9, [rax+10E10h]
0x1400cb22e  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400cb235  mov     rcx, [rcx+18h]
0x1400cb239  mov     [rsp+0A8h+var_70], rax
0x1400cb23e  mov     [rsp+0A8h+var_78], 14h
0x1400cb245  mov     [rsp+0A8h+var_80], 0Dh
0x1400cb24d  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400cb252  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400cb257  mov     bl, [rsp+0A8h+arg_8]
0x1400cb25e  xor     edx, edx
0x1400cb260  mov     rcx, [r14]
0x1400cb263  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400cb26a  nop     dword ptr [rax+rax+00h]
0x1400cb26f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb276  lea     rax, WPP_GLOBAL_Control
0x1400cb27d  cmp     rcx, rax
0x1400cb280  jz      short loc_1400CB28F
0x1400cb282  test    dword ptr [rcx+2Ch], 1000h
0x1400cb289  jnz     loc_1400CB43B
0x1400cb28f  xor     r15b, r15b
0x1400cb292  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cb299  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cb2a0  setnz   r12b
0x1400cb2a4  test    r15b, r15b
0x1400cb2a7  jnz     short loc_1400CB2AE
0x1400cb2a9  test    r12b, r12b
0x1400cb2ac  jz      short loc_1400CB329
0x1400cb2ae  mov     rcx, [r14]; Thread
0x1400cb2b1  movzx   esi, word ptr [r14+6C8h]
0x1400cb2b9  mov     ebp, [r14+6CCh]
0x1400cb2c0  movzx   eax, bl
0x1400cb2c3  movzx   edi, byte ptr [rax+r14+6D0h]
0x1400cb2cc  call    cs:__imp_PsGetThreadId
0x1400cb2d3  nop     dword ptr [rax+rax+00h]
0x1400cb2d8  mov     rbx, rax
0x1400cb2db  call    cs:__imp_W32GetUserSessionState
0x1400cb2e2  nop     dword ptr [rax+rax+00h]
0x1400cb2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb2ee  mov     r8b, r12b
0x1400cb2f1  movzx   r10d, [rsp+0A8h+arg_8]
0x1400cb2fa  mov     dl, r15b
0x1400cb2fd  mov     [rsp+0A8h+var_48], esi
0x1400cb301  mov     r9, [rax+10E10h]
0x1400cb308  mov     rcx, [rcx+18h]
0x1400cb30c  mov     [rsp+0A8h+var_50], ebp
0x1400cb310  mov     [rsp+0A8h+var_58], edi
0x1400cb314  mov     [rsp+0A8h+var_60], r10d
0x1400cb319  mov     [rsp+0A8h+var_68], ebx
0x1400cb31d  mov     [rsp+0A8h+var_78], 15h
0x1400cb324  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400cb329  xor     edx, edx
0x1400cb32b  lea     rcx, [r14+6C0h]
0x1400cb332  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400cb339  nop     dword ptr [rax+rax+00h]
0x1400cb33e  call    cs:__imp_KeLeaveCriticalRegion
0x1400cb345  nop     dword ptr [rax+rax+00h]
0x1400cb34a  mov     rbx, [rsp+0A8h+arg_0]
0x1400cb352  add     rsp, 70h
0x1400cb356  pop     r15
0x1400cb358  pop     r14
0x1400cb35a  pop     r13
0x1400cb35c  pop     r12
0x1400cb35e  pop     rdi
0x1400cb35f  pop     rsi
0x1400cb360  pop     rbp
0x1400cb361  retn
0x1400cb363  test    r13b, r13b
0x1400cb366  jnz     loc_1400CB0F0
0x1400cb36c  jmp     loc_1400CB167
0x1400cb371  cmp     byte ptr [rcx+29h], 4
0x1400cb375  jb      loc_1400CB0D2
0x1400cb37b  mov     r12b, r15b
0x1400cb37e  jmp     loc_1400CB0D5
0x1400cb383  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb38a  cmp     rcx, r9
0x1400cb38d  jz      short loc_1400CB3A0
0x1400cb38f  test    [rcx+2Ch], r8d
0x1400cb393  jz      short loc_1400CB3A0
0x1400cb395  cmp     byte ptr [rcx+29h], 4
0x1400cb399  jb      short loc_1400CB3A0
0x1400cb39b  mov     dil, r15b
0x1400cb39e  jmp     short loc_1400CB3A3
0x1400cb3a0  xor     dil, dil
0x1400cb3a3  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400cb3aa  setnz   sil
0x1400cb3ae  test    dil, dil
0x1400cb3b1  jnz     short loc_1400CB3B8
0x1400cb3b3  test    sil, sil
0x1400cb3b6  jz      short loc_1400CB422
0x1400cb3b8  mov     rcx, [r14]; Thread
0x1400cb3bb  call    cs:__imp_PsGetThreadId
0x1400cb3c2  nop     dword ptr [rax+rax+00h]
0x1400cb3c7  mov     rbx, rax
0x1400cb3ca  call    cs:__imp_W32GetUserSessionState
0x1400cb3d1  nop     dword ptr [rax+rax+00h]
0x1400cb3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb3dd  mov     r8b, sil
0x1400cb3e0  mov     [rsp+0A8h+var_60], ebx
0x1400cb3e4  mov     dl, dil
0x1400cb3e7  mov     [rsp+0A8h+var_68], ebp
0x1400cb3eb  mov     r9, [rax+10E10h]
0x1400cb3f2  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400cb3f9  mov     rcx, [rcx+18h]
0x1400cb3fd  mov     [rsp+0A8h+var_70], rax
0x1400cb402  mov     [rsp+0A8h+var_78], 13h
0x1400cb409  mov     [rsp+0A8h+var_80], 0Dh
0x1400cb411  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400cb416  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400cb41b  mov     bl, [rsp+0A8h+arg_8]
0x1400cb422  mov     edx, ebp
0x1400cb424  jmp     loc_1400CB260
0x1400cb429  cmp     byte ptr [rcx+29h], 4
0x1400cb42d  jb      loc_1400CB1E0
0x1400cb433  mov     dil, r15b
0x1400cb436  jmp     loc_1400CB1E3
0x1400cb43b  cmp     byte ptr [rcx+29h], 4
0x1400cb43f  jnb     loc_1400CB292
0x1400cb445  jmp     loc_1400CB28F
```
