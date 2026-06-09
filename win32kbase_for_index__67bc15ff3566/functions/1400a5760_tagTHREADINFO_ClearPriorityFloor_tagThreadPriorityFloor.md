# tagTHREADINFO::ClearPriorityFloor(tagThreadPriorityFloor)

- ea: `0x1400a5760`
- end: `0x1400a5b9a`
- name: `?ClearPriorityFloor@tagTHREADINFO@@QEAAXW4tagThreadPriorityFloor@@@Z`
- size: `1082`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400a5760`
- `0x1400a5ba0`
- `0x1400a5fe0`
- `0x1400a612c`
- `0x1400a6208`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400a57e0`
- `ntoskrnl!KeBugCheckEx` at `0x1400a57e0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a57af`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400a57af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a579a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a579a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5a8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a5a8e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a5a82`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400a5a82`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400a59b3`
- `ntoskrnl!PsAdjustWin32kPriorityFloor` at `0x1400a59b3`
- `ntoskrnl!PsGetThreadId` at `0x1400a5843`
- `ntoskrnl!PsGetThreadId` at `0x1400a594b`
- `ntoskrnl!PsGetThreadId` at `0x1400a5a1c`
- `ntoskrnl!PsGetThreadId` at `0x1400a5b0b`
- `ntoskrnl!PsGetThreadId` at `0x1400a5843`
- `ntoskrnl!PsGetThreadId` at `0x1400a594b`
- `ntoskrnl!PsGetThreadId` at `0x1400a5a1c`
- `ntoskrnl!PsGetThreadId` at `0x1400a5b0b`
- `WIN32K!W32GetUserSessionState` at `0x1400a585c`
- `WIN32K!W32GetUserSessionState` at `0x1400a595a`
- `WIN32K!W32GetUserSessionState` at `0x1400a5a2b`
- `WIN32K!W32GetUserSessionState` at `0x1400a5b1a`
- `WIN32K!W32GetUserSessionState` at `0x1400a585c`
- `WIN32K!W32GetUserSessionState` at `0x1400a595a`
- `WIN32K!W32GetUserSessionState` at `0x1400a5a2b`
- `WIN32K!W32GetUserSessionState` at `0x1400a5b1a`

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
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 UserSessionState; // rax
  int v14; // r8d
  int v15; // edx
  bool v16; // zf
  int v17; // edx
  unsigned __int16 v18; // ax
  unsigned int v19; // ebp
  bool v20; // di
  bool v21; // si
  char ThreadId; // bl
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rdx
  bool v30; // r12
  __int16 v31; // si
  int v32; // ebp
  char v33; // di
  char v34; // bl
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  bool v41; // di
  bool v42; // si
  char v43; // bl
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rax
  int v48; // r8d
  int v49; // edx
  int BugCheckParameter4; // [rsp+20h] [rbp-88h]
  int v51; // [rsp+28h] [rbp-80h]
  int v52; // [rsp+38h] [rbp-70h]
  char v53; // [rsp+B8h] [rbp+10h]

  v2 = 1;
  if ( a2 > 1 )
    goto LABEL_3;
  _mm_lfence();
  v4 = a2;
  v5 = LOBYTE(asc_1402564D0[4 * a2]);
  v53 = asc_1402564D0[4 * a2];
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1 + 216, 0);
  if ( !*((_BYTE *)a1 + v5 + 1744) )
    goto LABEL_3;
  v6 = *(_DWORD *)&asc_1402564D0[4 * v4 + 2];
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
    UserSessionState = W32GetUserSessionState(a1[57], v11, v12);
    LOBYTE(v14) = v10;
    LOBYTE(v15) = v9;
    WPP_RECORDER_AND_TRACE_SF_DDdd(*((_QWORD *)WPP_GLOBAL_Control + 3), v15, v14, *(_QWORD *)(UserSessionState + 69136));
    v8 = 4096;
    v7 = &WPP_GLOBAL_Control;
  }
  *((_DWORD *)a1 + 435) &= ~v6;
  v16 = (*((_BYTE *)a1 + (unsigned int)v5 + 1744))-- == 1;
  if ( v16 )
  {
    v17 = 1 << v5;
    if ( ((1 << v5) & (unsigned __int16)a1[217]) == 1 << v5 )
    {
      v18 = a1[217] & ~(_WORD)v17;
      *((_WORD *)a1 + 868) = v18;
      if ( v18 < v17 )
      {
        v16 = !_BitScanReverse(&v19, v18);
        if ( v16 )
        {
          v20 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v26 = W32GetUserSessionState(v24, v23, v25);
            LOBYTE(v27) = v21;
            LOBYTE(v28) = v20;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v28,
              v27,
              *(_QWORD *)(v26 + 69136),
              4,
              13,
              20,
              (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
              ThreadId);
            LOBYTE(v5) = v53;
          }
          v29 = 0;
        }
        else
        {
          v41 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v42 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v41 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v43 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
            v47 = W32GetUserSessionState(v45, v44, v46);
            LOBYTE(v48) = v42;
            LOBYTE(v49) = v41;
            WPP_RECORDER_AND_TRACE_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v49,
              v48,
              *(_QWORD *)(v47 + 69136),
              4,
              13,
              19,
              (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
              v19,
              v43);
            LOBYTE(v5) = v53;
          }
          v29 = v19;
        }
        PsAdjustWin32kPriorityFloor(*a1, v29, v8, v7);
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
  v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = *((_WORD *)a1 + 868);
    v32 = *((_DWORD *)a1 + 435);
    v33 = *((_BYTE *)a1 + (unsigned __int8)v5 + 1744);
    v34 = (unsigned __int8)PsGetThreadId((PETHREAD)*a1);
    v38 = W32GetUserSessionState(v36, v35, v37);
    LOBYTE(v39) = v30;
    LOBYTE(v40) = v2;
    WPP_RECORDER_AND_TRACE_SF_DdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v40,
      v39,
      *(_QWORD *)(v38 + 69136),
      BugCheckParameter4,
      v51,
      21,
      v52,
      v34,
      v53,
      v33,
      v32,
      v31);
  }
  ExReleasePushLockExclusiveEx(a1 + 216, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x1400a5760  mov     [rsp+arg_0], rbx
0x1400a5765  push    rbp
0x1400a5766  push    rsi
0x1400a5767  push    rdi
0x1400a5768  push    r12
0x1400a576a  push    r13
0x1400a576c  push    r14
0x1400a576e  push    r15
0x1400a5770  sub     rsp, 70h
0x1400a5774  mov     r15d, 1
0x1400a577a  mov     r14, rcx
0x1400a577d  cmp     edx, r15d
0x1400a5780  ja      short loc_1400A57C8
0x1400a5782  lfence
0x1400a5785  mov     esi, edx
0x1400a5787  lea     r12, asc_1402564D0; "\r"
0x1400a578e  movzx   ebx, byte ptr [r12+rsi*8]
0x1400a5793  mov     [rsp+0A8h+arg_8], bl
0x1400a579a  call    cs:__imp_KeEnterCriticalRegion
0x1400a57a1  nop     dword ptr [rax+rax+00h]
0x1400a57a6  xor     edx, edx
0x1400a57a8  lea     rcx, [r14+6C0h]
0x1400a57af  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400a57b6  nop     dword ptr [rax+rax+00h]
0x1400a57bb  cmp     byte ptr [r14+rbx+6D0h], 0
0x1400a57c4  mov     ebp, ebx
0x1400a57c6  jnz     short loc_1400A57ED
0x1400a57c8  xor     r9d, r9d; BugCheckParameter3
0x1400a57cb  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x1400a57d4  xor     r8d, r8d; BugCheckParameter2
0x1400a57d7  mov     ecx, 164h; BugCheckCode
0x1400a57dc  lea     edx, [r9+41h]; BugCheckParameter1
0x1400a57e0  call    cs:__imp_KeBugCheckEx
0x1400a57ed  mov     esi, [r12+rsi*8+4]
0x1400a57f2  mov     eax, esi
0x1400a57f4  and     eax, [r14+6CCh]
0x1400a57fb  cmp     eax, esi
0x1400a57fd  jnz     short loc_1400A57C8
0x1400a57ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5806  lea     r9, WPP_GLOBAL_Control
0x1400a580d  mov     r8d, 1000h
0x1400a5813  cmp     rcx, r9
0x1400a5816  jz      short loc_1400A5822
0x1400a5818  test    [rcx+2Ch], r8d
0x1400a581c  jnz     loc_1400A5AC1
0x1400a5822  xor     r12b, r12b
0x1400a5825  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a582c  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a5833  setnz   r13b
0x1400a5837  test    r12b, r12b
0x1400a583a  jz      loc_1400A5AB3
0x1400a5840  mov     rcx, [r14]; Thread
0x1400a5843  call    cs:__imp_PsGetThreadId
0x1400a584a  nop     dword ptr [rax+rax+00h]
0x1400a584f  mov     rcx, [r14+1C8h]
0x1400a5856  mov     rdi, rax
0x1400a5859  mov     ebx, [rcx+38h]
0x1400a585c  call    cs:__imp_W32GetUserSessionState
0x1400a5863  nop     dword ptr [rax+rax+00h]
0x1400a5868  movzx   ecx, bpl
0x1400a586c  mov     r8b, r13b
0x1400a586f  mov     [rsp+0A8h+var_50], ecx
0x1400a5873  mov     dl, r12b
0x1400a5876  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a587d  mov     r9, [rax+10E10h]
0x1400a5884  mov     [rsp+0A8h+var_58], esi
0x1400a5888  mov     [rsp+0A8h+var_60], edi
0x1400a588c  mov     rcx, [rcx+18h]
0x1400a5890  mov     [rsp+0A8h+var_68], ebx
0x1400a5894  mov     [rsp+0A8h+var_78], 12h
0x1400a589b  call    WPP_RECORDER_AND_TRACE_SF_DDdd
0x1400a58a0  mov     r8d, 1000h
0x1400a58a6  lea     r9, WPP_GLOBAL_Control
0x1400a58ad  lea     r10, WPP_RECORDER_INITIALIZED
0x1400a58b4  mov     bl, bpl
0x1400a58b7  not     esi
0x1400a58b9  and     [r14+6CCh], esi
0x1400a58c0  add     byte ptr [r14+rbp+6D0h], 0FFh
0x1400a58c9  jnz     loc_1400A59BF
0x1400a58cf  mov     cl, bl
0x1400a58d1  mov     edx, r15d
0x1400a58d4  shl     edx, cl
0x1400a58d6  movzx   ecx, word ptr [r14+6C8h]
0x1400a58de  mov     eax, ecx
0x1400a58e0  and     eax, edx
0x1400a58e2  cmp     eax, edx
0x1400a58e4  jnz     loc_1400A57C8
0x1400a58ea  movzx   eax, dx
0x1400a58ed  not     ax
0x1400a58f0  and     ax, cx
0x1400a58f3  movzx   ecx, ax
0x1400a58f6  mov     [r14+6C8h], cx
0x1400a58fe  cmp     ecx, edx
0x1400a5900  jge     loc_1400A59BF
0x1400a5906  bsr     ebp, ecx
0x1400a5909  mov     [rsp+0A8h+arg_10], 0
0x1400a5914  jnz     loc_1400A5AD3
0x1400a591a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5921  cmp     rcx, r9
0x1400a5924  jz      short loc_1400A5930
0x1400a5926  test    [rcx+2Ch], r8d
0x1400a592a  jnz     loc_1400A5B79
0x1400a5930  xor     dil, dil
0x1400a5933  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a593a  setnz   sil
0x1400a593e  test    dil, dil
0x1400a5941  jnz     short loc_1400A5948
0x1400a5943  test    sil, sil
0x1400a5946  jz      short loc_1400A59AE
0x1400a5948  mov     rcx, [r14]; Thread
0x1400a594b  call    cs:__imp_PsGetThreadId
0x1400a5952  nop     dword ptr [rax+rax+00h]
0x1400a5957  mov     rbx, rax
0x1400a595a  call    cs:__imp_W32GetUserSessionState
0x1400a5961  nop     dword ptr [rax+rax+00h]
0x1400a5966  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a596d  mov     r8b, sil
0x1400a5970  mov     [rsp+0A8h+var_68], ebx
0x1400a5974  mov     dl, dil
0x1400a5977  mov     r9, [rax+10E10h]
0x1400a597e  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x1400a5985  mov     rcx, [rcx+18h]
0x1400a5989  mov     [rsp+0A8h+var_70], rax
0x1400a598e  mov     [rsp+0A8h+var_78], 14h
0x1400a5995  mov     [rsp+0A8h+var_80], 0Dh
0x1400a599d  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400a59a2  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400a59a7  mov     bl, [rsp+0A8h+arg_8]
0x1400a59ae  xor     edx, edx
0x1400a59b0  mov     rcx, [r14]
0x1400a59b3  call    cs:__imp_PsAdjustWin32kPriorityFloor
0x1400a59ba  nop     dword ptr [rax+rax+00h]
0x1400a59bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a59c6  lea     rax, WPP_GLOBAL_Control
0x1400a59cd  cmp     rcx, rax
0x1400a59d0  jz      short loc_1400A59DF
0x1400a59d2  test    dword ptr [rcx+2Ch], 1000h
0x1400a59d9  jnz     loc_1400A5B8B
0x1400a59df  xor     r15b, r15b
0x1400a59e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400a59e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a59f0  setnz   r12b
0x1400a59f4  test    r15b, r15b
0x1400a59f7  jnz     short loc_1400A59FE
0x1400a59f9  test    r12b, r12b
0x1400a59fc  jz      short loc_1400A5A79
0x1400a59fe  mov     rcx, [r14]; Thread
0x1400a5a01  movzx   esi, word ptr [r14+6C8h]
0x1400a5a09  mov     ebp, [r14+6CCh]
0x1400a5a10  movzx   eax, bl
0x1400a5a13  movzx   edi, byte ptr [rax+r14+6D0h]
0x1400a5a1c  call    cs:__imp_PsGetThreadId
0x1400a5a23  nop     dword ptr [rax+rax+00h]
0x1400a5a28  mov     rbx, rax
0x1400a5a2b  call    cs:__imp_W32GetUserSessionState
0x1400a5a32  nop     dword ptr [rax+rax+00h]
0x1400a5a37  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5a3e  mov     r8b, r12b
0x1400a5a41  movzx   r10d, [rsp+0A8h+arg_8]
0x1400a5a4a  mov     dl, r15b
0x1400a5a4d  mov     [rsp+0A8h+var_48], esi
0x1400a5a51  mov     r9, [rax+10E10h]
0x1400a5a58  mov     rcx, [rcx+18h]
0x1400a5a5c  mov     [rsp+0A8h+var_50], ebp
0x1400a5a60  mov     [rsp+0A8h+var_58], edi
0x1400a5a64  mov     [rsp+0A8h+var_60], r10d
0x1400a5a69  mov     [rsp+0A8h+var_68], ebx
0x1400a5a6d  mov     [rsp+0A8h+var_78], 15h
0x1400a5a74  call    WPP_RECORDER_AND_TRACE_SF_DdddD
0x1400a5a79  xor     edx, edx
0x1400a5a7b  lea     rcx, [r14+6C0h]
0x1400a5a82  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400a5a89  nop     dword ptr [rax+rax+00h]
0x1400a5a8e  call    cs:__imp_KeLeaveCriticalRegion
0x1400a5a95  nop     dword ptr [rax+rax+00h]
0x1400a5a9a  mov     rbx, [rsp+0A8h+arg_0]
0x1400a5aa2  add     rsp, 70h
0x1400a5aa6  pop     r15
0x1400a5aa8  pop     r14
0x1400a5aaa  pop     r13
0x1400a5aac  pop     r12
0x1400a5aae  pop     rdi
0x1400a5aaf  pop     rsi
0x1400a5ab0  pop     rbp
0x1400a5ab1  retn
0x1400a5ab3  test    r13b, r13b
0x1400a5ab6  jnz     loc_1400A5840
0x1400a5abc  jmp     loc_1400A58B7
0x1400a5ac1  cmp     byte ptr [rcx+29h], 4
0x1400a5ac5  jb      loc_1400A5822
0x1400a5acb  mov     r12b, r15b
0x1400a5ace  jmp     loc_1400A5825
0x1400a5ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5ada  cmp     rcx, r9
0x1400a5add  jz      short loc_1400A5AF0
0x1400a5adf  test    [rcx+2Ch], r8d
0x1400a5ae3  jz      short loc_1400A5AF0
0x1400a5ae5  cmp     byte ptr [rcx+29h], 4
0x1400a5ae9  jb      short loc_1400A5AF0
0x1400a5aeb  mov     dil, r15b
0x1400a5aee  jmp     short loc_1400A5AF3
0x1400a5af0  xor     dil, dil
0x1400a5af3  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400a5afa  setnz   sil
0x1400a5afe  test    dil, dil
0x1400a5b01  jnz     short loc_1400A5B08
0x1400a5b03  test    sil, sil
0x1400a5b06  jz      short loc_1400A5B72
0x1400a5b08  mov     rcx, [r14]; Thread
0x1400a5b0b  call    cs:__imp_PsGetThreadId
0x1400a5b12  nop     dword ptr [rax+rax+00h]
0x1400a5b17  mov     rbx, rax
0x1400a5b1a  call    cs:__imp_W32GetUserSessionState
0x1400a5b21  nop     dword ptr [rax+rax+00h]
0x1400a5b26  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5b2d  mov     r8b, sil
0x1400a5b30  mov     [rsp+0A8h+var_60], ebx
0x1400a5b34  mov     dl, dil
0x1400a5b37  mov     [rsp+0A8h+var_68], ebp
0x1400a5b3b  mov     r9, [rax+10E10h]
0x1400a5b42  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x1400a5b49  mov     rcx, [rcx+18h]
0x1400a5b4d  mov     [rsp+0A8h+var_70], rax
0x1400a5b52  mov     [rsp+0A8h+var_78], 13h
0x1400a5b59  mov     [rsp+0A8h+var_80], 0Dh
0x1400a5b61  mov     byte ptr [rsp+0A8h+BugCheckParameter4], 4
0x1400a5b66  call    WPP_RECORDER_AND_TRACE_SF_dD
0x1400a5b6b  mov     bl, [rsp+0A8h+arg_8]
0x1400a5b72  mov     edx, ebp
0x1400a5b74  jmp     loc_1400A59B0
0x1400a5b79  cmp     byte ptr [rcx+29h], 4
0x1400a5b7d  jb      loc_1400A5930
0x1400a5b83  mov     dil, r15b
0x1400a5b86  jmp     loc_1400A5933
0x1400a5b8b  cmp     byte ptr [rcx+29h], 4
0x1400a5b8f  jnb     loc_1400A59E2
0x1400a5b95  jmp     loc_1400A59DF
```
