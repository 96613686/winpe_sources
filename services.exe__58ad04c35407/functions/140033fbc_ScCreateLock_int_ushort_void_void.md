# ScCreateLock(int,ushort *,void *,void * *)

- ea: `0x140033fbc`
- end: `0x14003422c`
- name: `?ScCreateLock@@YAKHPEAGPEAXPEAPEAX@Z`
- size: `624`
- prototype: `unsigned int(int, unsigned __int16 *, void *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001761c`
- `0x1400421b4`

## callees

- `0x140004c58`
- `0x14000cee0`
- `0x14001f99c`
- `0x14002d6cc`
- `0x140033fbc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400341d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400341d5`
- `ntdll!RtlLengthSid` at `0x140034044`
- `ntdll!RtlLengthSid` at `0x1400340cf`
- `ntdll!RtlLengthSid` at `0x140034044`
- `ntdll!RtlLengthSid` at `0x1400340cf`
- `ntdll!RtlNtStatusToDosError` at `0x1400341c9`
- `ntdll!RtlNtStatusToDosError` at `0x1400341c9`
- `ntdll!RtlCopySid` at `0x140034179`
- `ntdll!RtlCopySid` at `0x140034179`
- `ntdll!RtlFreeHeap` at `0x1400341c1`
- `ntdll!RtlFreeHeap` at `0x1400341c1`
- `ntdll!RtlAllocateHeap` at `0x140034067`
- `ntdll!RtlAllocateHeap` at `0x140034067`

## pseudocode

```c
ULONG __fastcall ScCreateLock(int a1, unsigned __int16 *a2, void *a3, void **a4)
{
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v11; // rbx
  __int64 v12; // rdx
  _QWORD *Heap; // rbx
  __int64 v14; // r8
  PRPC_ASYNC_STATE v15; // rcx
  ULONG v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS v18; // esi
  DWORD TickCount; // eax
  struct _API_LOCK *v20; // rcx
  _QWORD *v21; // rax

  if ( a1 )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = (unsigned int)(2 * v8 + 50);
  }
  else
  {
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 15, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids);
      return 31;
    }
    v7 = -1;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v9 = RtlLengthSid(a3) + 50 + 2 * (_DWORD)v11;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v9);
  if ( !Heap )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 16, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids);
    return 8;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x200) != 0 )
  {
    if ( a3 )
    {
      v16 = RtlLengthSid(a3);
      v15 = WPP_GLOBAL_Control;
    }
    else
    {
      v16 = 0;
    }
    WPP_SF_dqd(v15->StubInfo, v12, v14, (unsigned int)v9, Heap, v16);
  }
  *((_DWORD *)Heap + 4) = 1281978433;
  Heap[3] = Heap + 6;
  StringCbCopyW((unsigned __int16 *)Heap + 24, v9 - 48, a2);
  if ( a3 )
  {
    do
      ++v7;
    while ( a2[v7] );
    Heap[5] = Heap[3] + 2 * (v7 + 1);
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x200) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->StubInfo,
        18,
        WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids,
        (unsigned int)(v9 + (_DWORD)Heap - *((_DWORD *)Heap + 10)));
    }
    v17 = RtlCopySid(v9 + (_DWORD)Heap - *((_DWORD *)Heap + 10), (PSID)Heap[5], a3);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 19, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids, (unsigned int)v17);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return RtlNtStatusToDosError(v18);
    }
  }
  else
  {
    Heap[5] = 0;
  }
  TickCount = GetTickCount();
  v20 = ScGlobalApiLockList;
  *((_DWORD *)Heap + 8) = TickCount;
  if ( v20 )
  {
    Heap[1] = *((_QWORD *)v20 + 1);
    *Heap = v20;
    *((_QWORD *)v20 + 1) = Heap;
    v21 = (_QWORD *)Heap[1];
    if ( v21 )
      *v21 = Heap;
  }
  else
  {
    ScGlobalApiLockList = (struct _API_LOCK *)Heap;
    Heap[1] = 0;
    *Heap = 0;
  }
  *a4 = Heap;
  return 0;
}

```

## disassembly

```asm
0x140033fbc  push    rbx
0x140033fbe  push    rbp
0x140033fbf  push    rsi
0x140033fc0  push    rdi
0x140033fc1  push    r12
0x140033fc3  push    r13
0x140033fc5  push    r14
0x140033fc7  push    r15
0x140033fc9  sub     rsp, 38h
0x140033fcd  xor     edi, edi
0x140033fcf  mov     r12, r9
0x140033fd2  mov     rbp, r8
0x140033fd5  mov     r15, rdx
0x140033fd8  test    ecx, ecx
0x140033fda  jz      short loc_140033FF6
0x140033fdc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140033fe0  mov     rax, rsi
0x140033fe3  inc     rax
0x140033fe6  cmp     [rdx+rax*2], di
0x140033fea  jnz     short loc_140033FE3
0x140033fec  lea     r14d, ds:32h[rax*2]
0x140033ff4  jmp     short loc_140034052
0x140033ff6  test    rbp, rbp
0x140033ff9  jnz     short loc_140034031
0x140033ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140034002  lea     rdi, WPP_GLOBAL_Control
0x140034009  cmp     rcx, rdi
0x14003400c  jz      short loc_140034027
0x14003400e  test    byte ptr [rcx+1Ch], 1
0x140034012  jz      short loc_140034027
0x140034014  mov     rcx, [rcx+10h]
0x140034018  lea     edx, [rbp+0Fh]
0x14003401b  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140034022  call    WPP_SF_
0x140034027  mov     eax, 1Fh
0x14003402c  jmp     loc_14003421B
0x140034031  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140034035  mov     rbx, rsi
0x140034038  inc     rbx
0x14003403b  cmp     [rdx+rbx*2], di
0x14003403f  jnz     short loc_140034038
0x140034041  mov     rcx, rbp; Sid
0x140034044  call    cs:__imp_RtlLengthSid
0x14003404a  lea     r14d, [rax+32h]
0x14003404e  lea     r14d, [r14+rbx*2]
0x140034052  mov     rcx, gs:60h
0x14003405b  mov     edx, 8; Flags
0x140034060  mov     r8d, r14d; Size
0x140034063  mov     rcx, [rcx+30h]; HeapHandle
0x140034067  call    cs:__imp_RtlAllocateHeap
0x14003406d  mov     rbx, rax
0x140034070  test    rax, rax
0x140034073  jnz     short loc_1400340AB
0x140034075  mov     rcx, cs:WPP_GLOBAL_Control
0x14003407c  lea     rdi, WPP_GLOBAL_Control
0x140034083  cmp     rcx, rdi
0x140034086  jz      short loc_1400340A1
0x140034088  test    byte ptr [rcx+1Ch], 1
0x14003408c  jz      short loc_1400340A1
0x14003408e  mov     rcx, [rcx+10h]
0x140034092  lea     edx, [rax+10h]
0x140034095  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x14003409c  call    WPP_SF_
0x1400340a1  mov     eax, 8
0x1400340a6  jmp     loc_14003421B
0x1400340ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400340b2  lea     rdi, WPP_GLOBAL_Control
0x1400340b9  cmp     rcx, rdi
0x1400340bc  jz      short loc_1400340F5
0x1400340be  test    dword ptr [rcx+1Ch], 200h
0x1400340c5  jz      short loc_1400340F5
0x1400340c7  test    rbp, rbp
0x1400340ca  jz      short loc_1400340DE
0x1400340cc  mov     rcx, rbp; Sid
0x1400340cf  call    cs:__imp_RtlLengthSid
0x1400340d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400340dc  jmp     short loc_1400340E0
0x1400340de  xor     eax, eax
0x1400340e0  mov     rcx, [rcx+10h]
0x1400340e4  mov     r9d, r14d
0x1400340e7  mov     [rsp+78h+var_50], eax
0x1400340eb  mov     [rsp+78h+var_58], rbx
0x1400340f0  call    WPP_SF_dqd
0x1400340f5  lea     rcx, [rbx+30h]; unsigned __int16 *
0x1400340f9  mov     dword ptr [rbx+10h], 4C697041h
0x140034100  lea     rdx, [r14-30h]; unsigned __int64
0x140034104  mov     [rbx+18h], rcx
0x140034108  mov     r8, r15; unsigned __int16 *
0x14003410b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140034110  xor     r13d, r13d
0x140034113  test    rbp, rbp
0x140034116  jz      loc_1400341D1
0x14003411c  inc     rsi
0x14003411f  cmp     [r15+rsi*2], r13w
0x140034124  jnz     short loc_14003411C
0x140034126  mov     rax, [rbx+18h]
0x14003412a  lea     rcx, [rsi+1]
0x14003412e  lea     rcx, [rax+rcx*2]
0x140034132  mov     [rbx+28h], rcx
0x140034136  mov     rcx, cs:WPP_GLOBAL_Control
0x14003413d  cmp     rcx, rdi
0x140034140  jz      short loc_14003416A
0x140034142  test    dword ptr [rcx+1Ch], 200h
0x140034149  jz      short loc_14003416A
0x14003414b  mov     rcx, [rcx+10h]
0x14003414f  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x140034156  mov     r9d, ebx
0x140034159  mov     edx, 12h
0x14003415e  sub     r9d, [rbx+28h]
0x140034162  add     r9d, r14d
0x140034165  call    WPP_SF_d
0x14003416a  mov     rdx, [rbx+28h]; DestinationSid
0x14003416e  mov     ecx, ebx
0x140034170  sub     ecx, [rbx+28h]
0x140034173  mov     r8, rbp; SourceSid
0x140034176  add     ecx, r14d; DestinationSidLength
0x140034179  call    cs:__imp_RtlCopySid
0x14003417f  mov     esi, eax
0x140034181  test    eax, eax
0x140034183  jns     short loc_1400341D5
0x140034185  mov     rcx, cs:WPP_GLOBAL_Control
0x14003418c  cmp     rcx, rdi
0x14003418f  jz      short loc_1400341AF
0x140034191  test    byte ptr [rcx+1Ch], 1
0x140034195  jz      short loc_1400341AF
0x140034197  mov     rcx, [rcx+10h]
0x14003419b  lea     r8, WPP_9bea6622adc83b58cb93c7b141eb961f_Traceguids
0x1400341a2  mov     edx, 13h
0x1400341a7  mov     r9d, eax
0x1400341aa  call    WPP_SF_d
0x1400341af  mov     rcx, gs:60h
0x1400341b8  mov     r8, rbx; P
0x1400341bb  xor     edx, edx; Flags
0x1400341bd  mov     rcx, [rcx+30h]; HeapHandle
0x1400341c1  call    cs:__imp_RtlFreeHeap
0x1400341c7  mov     ecx, esi; Status
0x1400341c9  call    cs:__imp_RtlNtStatusToDosError
0x1400341cf  jmp     short loc_14003421B
0x1400341d1  mov     [rbx+28h], r13
0x1400341d5  call    cs:__imp_GetTickCount
0x1400341db  mov     rcx, cs:?ScGlobalApiLockList@@3PEAU_API_LOCK@@EA; _API_LOCK * ScGlobalApiLockList
0x1400341e2  mov     [rbx+20h], eax
0x1400341e5  test    rcx, rcx
0x1400341e8  jz      short loc_140034207
0x1400341ea  mov     rax, [rcx+8]
0x1400341ee  mov     [rbx+8], rax
0x1400341f2  mov     [rbx], rcx
0x1400341f5  mov     [rcx+8], rbx
0x1400341f9  mov     rax, [rbx+8]
0x1400341fd  test    rax, rax
0x140034200  jz      short loc_140034215
0x140034202  mov     [rax], rbx
0x140034205  jmp     short loc_140034215
0x140034207  mov     cs:?ScGlobalApiLockList@@3PEAU_API_LOCK@@EA, rbx; _API_LOCK * ScGlobalApiLockList
0x14003420e  mov     [rbx+8], r13
0x140034212  mov     [rbx], r13
0x140034215  mov     [r12], rbx
0x140034219  xor     eax, eax
0x14003421b  add     rsp, 38h
0x14003421f  pop     r15
0x140034221  pop     r14
0x140034223  pop     r13
0x140034225  pop     r12
0x140034227  pop     rdi
0x140034228  pop     rsi
0x140034229  pop     rbp
0x14003422a  pop     rbx
0x14003422b  retn
```
