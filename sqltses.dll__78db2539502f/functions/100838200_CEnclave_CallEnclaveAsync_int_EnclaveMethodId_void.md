# CEnclave::CallEnclaveAsync(int,EnclaveMethodId,void *)

- ea: `0x100838200`
- end: `0x10083846a`
- name: `?CallEnclaveAsync@CEnclave@@AEAAXHW4EnclaveMethodId@@PEAX@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100838470`

## callees

- `0x10049f780`
- `0x100838200`

## import_xrefs

- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10083830f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1008383f5`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10083830f`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1008383f5`
- `sqldk!SystemThread_TlsIndex` at `0x100838252`
- `sqldk!SystemThread_TlsOffset` at `0x10083825b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838276`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100838276`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10083833b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10083841d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10083833b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10083841d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnclave::CallEnclaveAsync(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r13
  signed __int64 v10; // rbp
  __int64 v11; // rsi
  int v12; // ebx
  __int64 v13; // rax
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-B8h]
  int v16; // [rsp+30h] [rbp-A8h]
  int v17; // [rsp+40h] [rbp-98h] BYREF
  __int64 v18; // [rsp+48h] [rbp-90h]
  int v19; // [rsp+50h] [rbp-88h] BYREF
  __int64 v20; // [rsp+58h] [rbp-80h]
  __int64 v21; // [rsp+60h] [rbp-78h]
  __int64 v22; // [rsp+68h] [rbp-70h]
  __int64 v23; // [rsp+70h] [rbp-68h]
  int v24; // [rsp+78h] [rbp-60h] BYREF
  __int64 v25; // [rsp+80h] [rbp-58h]
  __int64 v26; // [rsp+88h] [rbp-50h]
  __int64 v27; // [rsp+90h] [rbp-48h]
  __int64 v28; // [rsp+98h] [rbp-40h]
  __int64 v29; // [rsp+A0h] [rbp-38h]

  v29 = -2;
  v7 = *(_QWORD *)(a1 + 176) + 16520LL * a2;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v16 = !(*(_BYTE *)(v9 + 616) & 1);
  *(_DWORD *)(v9 + 616) |= 1u;
  v10 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 16408), 1u);
  v11 = v7 + 16 * ((v10 & 0x3FF) + 1);
  while ( *(_QWORD *)(v11 + 8) != v10 )
  {
    v19 = 4195808;
    v20 = 0;
    v22 = 0;
    v21 = 0;
    v23 = 0;
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 200));
    LOBYTE(v15) = 1;
    if ( (unsigned int)WaitableBase::Wait(v7 + 16464, 0xFFFFFFFFLL, &v19, 0, v15) )
      utassert_fail(1u, "SOS_OK == status", "enclavewrapper.cpp", 509, 0);
  }
  v17 = a3;
  v18 = a4;
  if ( _InterlockedExchange64((volatile __int64 *)v11, (__int64)&v17) == -1 )
    EventAutoInternal<SuspendQueueSLock>::Signal(v7 + 16416, 0);
  v12 = 0;
  while ( *(_QWORD *)(v11 + 8) == v10 )
  {
    if ( v12 >= 200 )
    {
      v24 = 4195808;
      v25 = 0;
      v27 = 0;
      v26 = 0;
      v28 = 0;
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 184));
      LOBYTE(v15) = 1;
      if ( (unsigned int)WaitableBase::Wait(v7 + 16464, 0xFFFFFFFFLL, &v24, 0, v15) )
        utassert_fail(1u, "SOS_OK == status", "enclavewrapper.cpp", 548, 0);
    }
    else
    {
      v13 = 100;
      do
      {
        _mm_pause();
        --v13;
      }
      while ( v13 );
      ++v12;
    }
  }
  _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 192), v12);
  result = (unsigned int)~v16;
  *(_DWORD *)(v9 + 616) &= result;
  return result;
}

```

## disassembly

```asm
0x100838200  mov     rax, rsp
0x100838203  push    rdi
0x100838204  push    r12
0x100838206  push    r13
0x100838208  push    r14
0x10083820a  push    r15
0x10083820c  sub     rsp, 0B0h
0x100838213  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x10083821b  mov     [rax+8], rbx
0x10083821f  mov     [rax+10h], rbp
0x100838223  mov     [rax+18h], rsi
0x100838227  mov     r15, r9
0x10083822a  mov     r12d, r8d
0x10083822d  mov     rdi, rcx
0x100838230  movsxd  rax, edx
0x100838233  imul    r14, rax, 4088h
0x10083823a  add     r14, [rcx+0B0h]
0x100838241  xor     r8d, r8d
0x100838244  mov     [rsp+0D8h+var_A8], r8d
0x100838249  mov     r10, gs:58h
0x100838252  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100838259  mov     edx, [rax]
0x10083825b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100838262  mov     ebx, [rax]
0x100838264  add     rbx, [r10+rdx*8]
0x100838268  mov     r13, [rbx+100h]
0x10083826f  test    r13, r13
0x100838272  jnz     short loc_100838286
0x100838274  xor     ecx, ecx
0x100838276  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10083827c  mov     r13, [rbx+100h]
0x100838283  xor     r8d, r8d
0x100838286  mov     [rsp+0D8h+var_A0], r13
0x10083828b  mov     ecx, [r13+268h]
0x100838292  mov     eax, ecx
0x100838294  and     eax, 1
0x100838297  xor     eax, 1
0x10083829a  mov     [rsp+0D8h+var_A8], eax
0x10083829e  or      ecx, 1
0x1008382a1  mov     [r13+268h], ecx
0x1008382a8  mov     ebp, 1
0x1008382ad  lock xadd [r14+4018h], rbp
0x1008382b6  mov     rsi, rbp
0x1008382b9  and     esi, 3FFh
0x1008382bf  inc     rsi
0x1008382c2  shl     rsi, 4
0x1008382c6  add     rsi, r14
0x1008382c9  mov     rax, [rsi+8]
0x1008382cd  cmp     rax, rbp
0x1008382d0  jz      short loc_100838350
0x1008382d2  mov     [rsp+0D8h+var_88], 4005E0h
0x1008382da  mov     [rsp+0D8h+var_80], r8
0x1008382df  mov     [rsp+0D8h+var_70], r8
0x1008382e4  mov     [rsp+0D8h+var_78], r8
0x1008382e9  mov     [rsp+0D8h+var_68], r8
0x1008382ee  lock inc qword ptr [rdi+0C8h]
0x1008382f6  mov     byte ptr [rsp+0D8h+var_B8], 1
0x1008382fb  xor     r9d, r9d
0x1008382fe  lea     r8, [rsp+0D8h+var_88]
0x100838303  mov     edx, 0FFFFFFFFh
0x100838308  lea     rcx, [r14+4050h]
0x10083830f  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100838315  test    eax, eax
0x100838317  jz      short loc_100838341
0x100838319  mov     qword ptr [rsp+0D8h+var_B8], 0
0x100838322  mov     r9d, 1FDh
0x100838328  lea     r8, aEnclavewrapper; "enclavewrapper.cpp"
0x10083832f  lea     rdx, aSosOkStatus; "SOS_OK == status"
0x100838336  mov     ecx, 1
0x10083833b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100838341  mov     rax, [rsi+8]
0x100838345  cmp     rax, rbp
0x100838348  mov     r8d, 0
0x10083834e  jnz     short loc_1008382D2
0x100838350  mov     [rsp+0D8h+var_98], r12d
0x100838355  mov     [rsp+0D8h+var_90], r15
0x10083835a  lea     rax, [rsp+0D8h+var_98]
0x10083835f  xchg    rax, [rsi]
0x100838362  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100838366  jnz     short loc_100838376
0x100838368  lea     rcx, [r14+4020h]
0x10083836f  xor     edx, edx
0x100838371  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838376  xor     r15d, r15d
0x100838379  mov     ebx, r15d
0x10083837c  mov     rax, [rsi+8]
0x100838380  cmp     rax, rbp
0x100838383  jnz     loc_100838430
0x100838389  nop     dword ptr [rax]
0x10083838c  nop     dword ptr [rax+00h]
0x100838390  cmp     ebx, 0C8h
0x100838396  jge     short loc_1008383AC
0x100838398  mov     eax, 64h ; 'd'
0x10083839d  nop     dword ptr [rax]
0x1008383a0  pause
0x1008383a2  sub     rax, 1
0x1008383a6  jnz     short loc_1008383A0
0x1008383a8  inc     ebx
0x1008383aa  jmp     short loc_100838423
0x1008383ac  mov     [rsp+0D8h+var_60], 4005E0h
0x1008383b4  mov     [rsp+0D8h+var_58], r15
0x1008383bc  mov     [rsp+0D8h+var_48], r15
0x1008383c4  mov     [rsp+0D8h+var_50], r15
0x1008383cc  mov     [rsp+0D8h+var_40], r15
0x1008383d4  lock inc qword ptr [rdi+0B8h]
0x1008383dc  lea     rcx, [r14+4050h]
0x1008383e3  mov     byte ptr [rsp+0D8h+var_B8], 1
0x1008383e8  xor     r9d, r9d
0x1008383eb  lea     r8, [rsp+0D8h+var_60]
0x1008383f0  mov     edx, 0FFFFFFFFh
0x1008383f5  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x1008383fb  test    eax, eax
0x1008383fd  jz      short loc_100838423
0x1008383ff  mov     qword ptr [rsp+0D8h+var_B8], r15
0x100838404  mov     r9d, 224h
0x10083840a  lea     r8, aEnclavewrapper; "enclavewrapper.cpp"
0x100838411  lea     rdx, aSosOkStatus; "SOS_OK == status"
0x100838418  mov     ecx, 1
0x10083841d  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100838423  mov     rax, [rsi+8]
0x100838427  cmp     rax, rbp
0x10083842a  jz      loc_100838390
0x100838430  movsxd  rax, ebx
0x100838433  lock xadd [rdi+0C0h], rax
0x10083843c  mov     eax, [rsp+0D8h+var_A8]
0x100838440  not     eax
0x100838442  and     [r13+268h], eax
0x100838449  lea     r11, [rsp+0D8h+var_28]
0x100838451  mov     rbx, [r11+30h]
0x100838455  mov     rbp, [r11+38h]
0x100838459  mov     rsi, [r11+40h]
0x10083845d  mov     rsp, r11
0x100838460  pop     r15
0x100838462  pop     r14
0x100838464  pop     r13
0x100838466  pop     r12
0x100838468  pop     rdi
0x100838469  retn
```
