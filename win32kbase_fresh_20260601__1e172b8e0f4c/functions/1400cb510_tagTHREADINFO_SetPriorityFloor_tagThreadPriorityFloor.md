# tagTHREADINFO::SetPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400cb510`
- end: `0x1400cb887`
- name: `?SetPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400cb510`
- `0x1400cb890`
- `0x1400cb9dc`
- `0x1400cbab8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400cb58a`
- `ntoskrnl!KeBugCheckEx` at `0x1400cb58a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cb558`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400cb558`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cb543`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cb543`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cb81a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cb81a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cb80e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400cb80e`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400cb740`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400cb740`
- `ntoskrnl!PsGetThreadId` at `0x1400cb5ef`
- `ntoskrnl!PsGetThreadId` at `0x1400cb6cd`
- `ntoskrnl!PsGetThreadId` at `0x1400cb7ad`
- `ntoskrnl!PsGetThreadId` at `0x1400cb5ef`
- `ntoskrnl!PsGetThreadId` at `0x1400cb6cd`
- `ntoskrnl!PsGetThreadId` at `0x1400cb7ad`
- `WIN32K!W32GetUserSessionState` at `0x1400cb608`
- `WIN32K!W32GetUserSessionState` at `0x1400cb6dc`
- `WIN32K!W32GetUserSessionState` at `0x1400cb7bc`
- `WIN32K!W32GetUserSessionState` at `0x1400cb608`
- `WIN32K!W32GetUserSessionState` at `0x1400cb6dc`
- `WIN32K!W32GetUserSessionState` at `0x1400cb7bc`

## pseudocode

```c
void __fastcall tagTHREADINFO::SetPriorityFloor(_QWORD *a1, unsigned int a2)
{
  char v2; // r15
  __int64 v4; // rsi
  __int64 v5; // r13
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r12
  int v9; // esi
  bool v10; // bp
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 UserSessionState; // rax
  int v14; // edx
  int v15; // r8d
  bool v16; // si
  char ThreadId; // bl
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // edx
  int v23; // r8d
  _WORD *v24; // rax
  bool v25; // r13
  __int16 v26; // di
  int v27; // esi
  char v28; // bp
  char v29; // bl
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v37; // [rsp+28h] [rbp-80h]
  int v38; // [rsp+38h] [rbp-70h]
  bool v39; // [rsp+B8h] [rbp+10h]
  bool v40; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1
    || (_mm_lfence(),
        v4 = a2,
        v5 = LOBYTE(asc_1402571F0[4 * a2]),
        KeEnterCriticalRegion(),
        ExAcquirePushLockExclusiveEx(a1 + 216, 0),
        v8 = (unsigned int)v5,
        *((_BYTE *)a1 + v5 + 1744) == 0xFF)
    || (v9 = *(_DWORD *)&asc_1402571F0[4 * v4 + 2], (v9 & *((_DWORD *)a1 + 435)) == v9) )
  {
    KeBugCheckEx(0x164u, 0x41u, 0, 0, 0);
  }
  v10 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId((PETHREAD)*a1);
    UserSessionState = W32GetUserSessionState(a1[57], v11, v12);
    LOBYTE(v14) = v10;
    LOBYTE(v15) = v39;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v14, v15, *(_QWORD *)(UserSessionState + 69136));
  }
  *((_DWORD *)a1 + 435) |= v9;
  if ( ++*((_BYTE *)a1 + v5 + 1744) == 1 )
  {
    if ( *((unsigned __int16 *)a1 + 868) >= 1 << v5 )
    {
      v24 = a1 + 217;
    }
    else
    {
      v16 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v40 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
        v21 = W32GetUserSessionState(v19, v18, v20);
        LOBYTE(v22) = v16;
        LOBYTE(v23) = v40;
        WPP_RECORDER_AND_TRACE_SF_dD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v22,
          v23,
          *(_QWORD *)(v21 + 69136),
          4,
          13,
          16,
          (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
          v5,
          ThreadId);
      }
      PsAdjustWin32kPriorityFloor(*a1, (unsigned int)v5, v6, v7);
      v24 = a1 + 217;
    }
    *((_WORD *)a1 + 868) = *v24 | (1 << v5);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v2 = 0;
  }
  v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = *((_WORD *)a1 + 868);
    v27 = *((_DWORD *)a1 + 435);
    v28 = *((_BYTE *)a1 + v8 + 1744);
    v29 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v33 = W32GetUserSessionState(v31, v30, v32);
    LOBYTE(v34) = v25;
    LOBYTE(v35) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v35,
      v34,
      *(_QWORD *)(v33 + 69136),
      BugCheckParameter4,
      v37,
      17,
      v38,
      v29,
      v8,
      v28,
      v27,
      v26);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0, v6, v7);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400cb510  mov     [rsp+arg_0], rbx
0x1400cb515  push    rbp
0x1400cb516  push    rsi
0x1400cb517  push    rdi
0x1400cb518  push    r12
0x1400cb51a  push    r13
0x1400cb51c  push    r14
0x1400cb51e  push    r15
0x1400cb520  sub     rsp, 70h
0x1400cb524  mov     r15d, 1
0x1400cb52a  mov     r14, rcx
0x1400cb52d  cmp     edx, r15d
0x1400cb530  ja      short loc_1400CB572
0x1400cb532  lfence
0x1400cb535  mov     esi, edx
0x1400cb537  lea     rdi, asc_1402571F0; "\r"
0x1400cb53e  movzx   r13d, byte ptr [rdi+rsi*8]
0x1400cb543  call    cs:__imp_KeEnterCriticalRegion
0x1400cb54a  nop     dword ptr [rax+rax+00h]
0x1400cb54f  xor     edx, edx
0x1400cb551  lea     rcx, [r14+6C0h]
0x1400cb558  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400cb55f  nop     dword ptr [rax+rax+00h]
0x1400cb564  cmp     byte ptr [r13+r14+6D0h], 0FFh
0x1400cb56d  mov     r12d, r13d
0x1400cb570  jnz     short loc_1400CB597
0x1400cb572  xor     r9d, r9d; BugCheckParameter3
0x1400cb575  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400cb57e  xor     r8d, r8d; BugCheckParameter2
0x1400cb581  mov     ecx, 164h; BugCheckCode
0x1400cb586  lea     edx, [r9+41h]; BugCheckParameter1
0x1400cb58a  call    cs:__imp_KeBugCheckEx
0x1400cb597  mov     esi, [rdi+rsi*8+4]
0x1400cb59b  mov     eax, [r14+6CCh]
0x1400cb5a2  and     eax, esi
0x1400cb5a4  cmp     eax, esi
0x1400cb5a6  jz      short loc_1400CB572
0x1400cb5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb5af  lea     rbx, WPP_GLOBAL_Control
0x1400cb5b6  cmp     rcx, rbx
0x1400cb5b9  jz      short loc_1400CB5C8
0x1400cb5bb  test    dword ptr [rcx+2Ch], 1000h
0x1400cb5c2  jnz     loc_1400CB854
0x1400cb5c8  xor     bpl, bpl
0x1400cb5cb  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400cb5d2  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400cb5d9  setnz   al
0x1400cb5dc  mov     [rsp+0A8h+arg_8], al
0x1400cb5e3  test    bpl, bpl
0x1400cb5e6  jz      loc_1400CB83F
0x1400cb5ec  mov     rcx, [r14]; Thread
0x1400cb5ef  call    cs:__imp_PsGetThreadId
0x1400cb5f6  nop     dword ptr [rax+rax+00h]
0x1400cb5fb  mov     rcx, [r14+1C8h]
0x1400cb602  mov     rdi, rax
0x1400cb605  mov     ebx, [rcx+38h]
0x1400cb608  call    cs:__imp_W32GetUserSessionState
0x1400cb60f  nop     dword ptr [rax+rax+00h]
0x1400cb614  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb61b  mov     dl, bpl
0x1400cb61e  mov     r8b, [rsp+0A8h+arg_8]
0x1400cb626  mov     [rsp+0A8h+var_50], r13d
0x1400cb62b  mov     r9, [rax+10E10h]
0x1400cb632  mov     rcx, [rcx+18h]
0x1400cb636  mov     [rsp+0A8h+var_58], esi
0x1400cb63a  mov     [rsp+0A8h+var_60], edi
0x1400cb63e  mov     [rsp+0A8h+var_68], ebx
0x1400cb642  mov     [rsp+0A8h+var_78], 0Fh
0x1400cb649  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400cb64e  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400cb655  lea     rbx, WPP_GLOBAL_Control
0x1400cb65c  or      [r14+6CCh], esi
0x1400cb663  add     [r13+r14+6D0h], r15b
0x1400cb66b  cmp     [r13+r14+6D0h], r15b
0x1400cb673  jnz     loc_1400CB75A
0x1400cb679  mov     cl, r13b
0x1400cb67c  lea     rbp, [r14+6C8h]
0x1400cb683  movzx   eax, word ptr [rbp+0]
0x1400cb687  mov     edi, r15d
0x1400cb68a  shl     edi, cl
0x1400cb68c  cmp     eax, edi
0x1400cb68e  jge     loc_1400CB84C
0x1400cb694  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb69b  cmp     rcx, rbx
0x1400cb69e  jz      short loc_1400CB6AD
0x1400cb6a0  test    dword ptr [rcx+2Ch], 1000h
0x1400cb6a7  jnz     loc_1400CB866
0x1400cb6ad  xor     sil, sil
0x1400cb6b0  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400cb6b7  setnz   al
0x1400cb6ba  mov     [rsp+0A8h+arg_8], al
0x1400cb6c1  test    sil, sil
0x1400cb6c4  jnz     short loc_1400CB6CA
0x1400cb6c6  test    al, al
0x1400cb6c8  jz      short loc_1400CB73A
0x1400cb6ca  mov     rcx, [r14]; Thread
0x1400cb6cd  call    cs:__imp_PsGetThreadId
0x1400cb6d4  nop     dword ptr [rax+rax+00h]
0x1400cb6d9  mov     rbx, rax
0x1400cb6dc  call    cs:__imp_W32GetUserSessionState
0x1400cb6e3  nop     dword ptr [rax+rax+00h]
0x1400cb6e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb6ef  mov     dl, sil
0x1400cb6f2  mov     r8b, [rsp+0A8h+arg_8]
0x1400cb6fa  mov     [rsp+0A8h+var_60], ebx
0x1400cb6fe  mov     r9, [rax+10E10h]
0x1400cb705  lea     rax, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400cb70c  mov     rcx, [rcx+18h]
0x1400cb710  mov     [rsp+0A8h+var_68], r13d
0x1400cb715  mov     [rsp+0A8h+var_70], rax
0x1400cb71a  mov     [rsp+0A8h+var_78], 10h
0x1400cb721  mov     [rsp+0A8h+var_80], 0Dh
0x1400cb729  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400cb72e  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400cb733  lea     rbx, WPP_GLOBAL_Control
0x1400cb73a  mov     rcx, [r14]
0x1400cb73d  mov     edx, r13d
0x1400cb740  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400cb747  nop     dword ptr [rax+rax+00h]
0x1400cb74c  lea     rax, [r14+6C8h]
0x1400cb753  or      di, [rax]
0x1400cb756  mov     [rbp+0], di
0x1400cb75a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb761  cmp     rcx, rbx
0x1400cb764  jz      short loc_1400CB773
0x1400cb766  test    dword ptr [rcx+2Ch], 1000h
0x1400cb76d  jnz     loc_1400CB878
0x1400cb773  xor     r15b, r15b
0x1400cb776  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cb77d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cb784  setnz   r13b
0x1400cb788  test    r15b, r15b
0x1400cb78b  jnz     short loc_1400CB792
0x1400cb78d  test    r13b, r13b
0x1400cb790  jz      short loc_1400CB805
0x1400cb792  mov     rcx, [r14]; Thread
0x1400cb795  movzx   edi, word ptr [r14+6C8h]
0x1400cb79d  mov     esi, [r14+6CCh]
0x1400cb7a4  movzx   ebp, byte ptr [r12+r14+6D0h]
0x1400cb7ad  call    cs:__imp_PsGetThreadId
0x1400cb7b4  nop     dword ptr [rax+rax+00h]
0x1400cb7b9  mov     rbx, rax
0x1400cb7bc  call    cs:__imp_W32GetUserSessionState
0x1400cb7c3  nop     dword ptr [rax+rax+00h]
0x1400cb7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb7cf  mov     r8b, r13b
0x1400cb7d2  mov     [rsp+0A8h+var_48], edi
0x1400cb7d6  mov     dl, r15b
0x1400cb7d9  mov     [rsp+0A8h+var_50], esi
0x1400cb7dd  mov     r9, [rax+10E10h]
0x1400cb7e4  mov     rcx, [rcx+18h]
0x1400cb7e8  mov     [rsp+0A8h+var_58], ebp
0x1400cb7ec  movzx   r10d, r12b
0x1400cb7f0  mov     [rsp+0A8h+var_60], r10d
0x1400cb7f5  mov     [rsp+0A8h+var_68], ebx
0x1400cb7f9  mov     [rsp+0A8h+var_78], 11h
0x1400cb800  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400cb805  xor     edx, edx
0x1400cb807  lea     rcx, [r14+6C0h]
0x1400cb80e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400cb815  nop     dword ptr [rax+rax+00h]
0x1400cb81a  call    cs:__imp_KeLeaveCriticalRegion
0x1400cb821  nop     dword ptr [rax+rax+00h]
0x1400cb826  mov     rbx, [rsp+0A8h+arg_0]
0x1400cb82e  add     rsp, 70h
0x1400cb832  pop     r15
0x1400cb834  pop     r14
0x1400cb836  pop     r13
0x1400cb838  pop     r12
0x1400cb83a  pop     rdi
0x1400cb83b  pop     rsi
0x1400cb83c  pop     rbp
0x1400cb83d  retn
0x1400cb83f  test    al, al
0x1400cb841  jz      loc_1400CB65C
0x1400cb847  jmp     loc_1400CB5EC
0x1400cb84c  mov     rax, rbp
0x1400cb84f  jmp     loc_1400CB753
0x1400cb854  cmp     byte ptr [rcx+29h], 4
0x1400cb858  jb      loc_1400CB5C8
0x1400cb85e  mov     bpl, r15b
0x1400cb861  jmp     loc_1400CB5CB
0x1400cb866  cmp     byte ptr [rcx+29h], 4
0x1400cb86a  jb      loc_1400CB6AD
0x1400cb870  mov     sil, r15b
0x1400cb873  jmp     loc_1400CB6B0
0x1400cb878  cmp     byte ptr [rcx+29h], 4
0x1400cb87c  jnb     loc_1400CB776
0x1400cb882  jmp     loc_1400CB773
```
