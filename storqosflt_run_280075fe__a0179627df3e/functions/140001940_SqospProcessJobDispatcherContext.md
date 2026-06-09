# SqospProcessJobDispatcherContext

- ea: `0x140001940`
- end: `0x140001aa9`
- name: `SqospProcessJobDispatcherContext`
- size: `361`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140001380`
- `0x140006910`
- `0x1400069f0`
- `0x140006b04`

## callees

- `0x140001940`
- `0x140002300`
- `0x140004440`
- `0x140006a38`
- `0x140006e98`
- `0x140008a8c`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140001a73`
- `HAL!KeQueryPerformanceCounter` at `0x140001a73`
- `FLTMGR!FltReleaseContext` at `0x140001986`
- `FLTMGR!FltReleaseContext` at `0x140001986`

## pseudocode

```c
__int64 __fastcall SqospProcessJobDispatcherContext(__int64 a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v3; // rsi
  unsigned int v7; // ebp
  signed __int64 *v8; // rcx
  _QWORD *i; // rsi
  _QWORD *v11; // rdx
  LARGE_INTEGER *v12; // rdi
  char v13; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(KSPIN_LOCK **)a1;
  v7 = 2;
  if ( *(_QWORD *)a1 )
  {
    if ( *(_BYTE *)(a1 + 24) )
    {
      SqospLimiterProcessQueue(*(KSPIN_LOCK **)a1, a1);
      v3 = *(KSPIN_LOCK **)a1;
    }
    if ( *(_BYTE *)(a1 + 25) || a2 )
    {
      v13 = 0;
      v7 = SqospProcessBalancerQueue(a1, a2, a3, &v13);
      if ( !v13 )
      {
LABEL_7:
        FltReleaseContext(*(PFLT_CONTEXT *)a1);
        *(_QWORD *)a1 = 0;
        goto LABEL_8;
      }
      v3 = *(KSPIN_LOCK **)a1;
    }
    if ( ClientPort
      && *((_DWORD *)v3 + 47) == 2
      && MEMORY[0xFFFFF78000000008] >= v3[537]
      && !_interlockedbittestandset((volatile signed __int32 *)v3 + 1040, 0)
      && !(unsigned __int8)SqospQueueStatsWorkItem(v3) )
    {
      _interlockedbittestandreset((volatile signed __int32 *)v3 + 1040, 0);
    }
    goto LABEL_7;
  }
LABEL_8:
  v8 = *(signed __int64 **)(a1 + 16);
  if ( v8 )
  {
    if ( *(_BYTE *)(a1 + 26) )
    {
      for ( i = DvRemoveOrderedWorkQueue(v8); i; i = DvRemoveOrderedWorkQueue(*(signed __int64 **)(a1 + 16)) )
      {
        do
        {
          v11 = i;
          v12 = (LARGE_INTEGER *)(i - 14);
          i = (_QWORD *)*i;
          *v11 = 0;
          v12[21] = KeQueryPerformanceCounter(0);
          SqospDispatchDeferredJob(v12);
        }
        while ( i );
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140001940  mov     [rsp+arg_8], rbx
0x140001945  mov     [rsp+arg_10], rbp
0x14000194a  push    rsi
0x14000194b  push    rdi
0x14000194c  push    r14
0x14000194e  sub     rsp, 20h
0x140001952  mov     rsi, [rcx]
0x140001955  mov     r14, r8
0x140001958  mov     rdi, rdx
0x14000195b  mov     rbx, rcx
0x14000195e  mov     ebp, 2
0x140001963  test    rsi, rsi
0x140001966  jz      short loc_140001999
0x140001968  cmp     byte ptr [rcx+18h], 0
0x14000196c  jnz     short loc_1400019E8
0x14000196e  cmp     byte ptr [rbx+19h], 0
0x140001972  jnz     short loc_1400019C2
0x140001974  test    rdi, rdi
0x140001977  jnz     short loc_1400019C2
0x140001979  cmp     cs:ClientPort, 0
0x140001981  jnz     short loc_1400019FB
0x140001983  mov     rcx, [rbx]; Context
0x140001986  call    cs:__imp_FltReleaseContext
0x14000198d  nop     dword ptr [rax+rax+00h]
0x140001992  mov     qword ptr [rbx], 0
0x140001999  mov     rcx, [rbx+10h]
0x14000199d  test    rcx, rcx
0x1400019a0  jz      short loc_1400019AC
0x1400019a2  cmp     byte ptr [rbx+1Ah], 0
0x1400019a6  jnz     loc_140001A4F
0x1400019ac  mov     rbx, [rsp+38h+arg_8]
0x1400019b1  mov     eax, ebp
0x1400019b3  mov     rbp, [rsp+38h+arg_10]
0x1400019b8  add     rsp, 20h
0x1400019bc  pop     r14
0x1400019be  pop     rdi
0x1400019bf  pop     rsi
0x1400019c0  retn
0x1400019c2  lea     r9, [rsp+38h+arg_0]
0x1400019c7  mov     [rsp+38h+arg_0], 0
0x1400019cc  mov     r8, r14
0x1400019cf  mov     rdx, rdi
0x1400019d2  mov     rcx, rbx
0x1400019d5  call    SqospProcessBalancerQueue
0x1400019da  cmp     [rsp+38h+arg_0], 0
0x1400019df  mov     ebp, eax
0x1400019e1  jz      short loc_140001983
0x1400019e3  mov     rsi, [rbx]
0x1400019e6  jmp     short loc_140001979
0x1400019e8  mov     rdx, rbx
0x1400019eb  mov     rcx, rsi; Context
0x1400019ee  call    SqospLimiterProcessQueue
0x1400019f3  mov     rsi, [rbx]
0x1400019f6  jmp     loc_14000196E
0x1400019fb  cmp     dword ptr [rsi+0BCh], 2
0x140001a02  jnz     loc_140001983
0x140001a08  mov     rcx, 0FFFFF78000000008h
0x140001a12  mov     rcx, [rcx]
0x140001a15  cmp     rcx, [rsi+10C8h]
0x140001a1c  jb      loc_140001983
0x140001a22  lock bts dword ptr [rsi+1040h], 0
0x140001a2b  jb      loc_140001983
0x140001a31  mov     rcx, rsi; Context
0x140001a34  call    SqospQueueStatsWorkItem
0x140001a39  test    al, al
0x140001a3b  jnz     loc_140001983
0x140001a41  lock btr dword ptr [rsi+1040h], 0
0x140001a4a  jmp     loc_140001983
0x140001a4f  call    DvRemoveOrderedWorkQueue
0x140001a54  mov     rsi, rax
0x140001a57  test    rax, rax
0x140001a5a  jz      loc_1400019AC
0x140001a60  lea     rdx, [rsi]
0x140001a63  xor     ecx, ecx; PerformanceFrequency
0x140001a65  lea     rdi, [rsi-70h]
0x140001a69  mov     rsi, [rsi]
0x140001a6c  mov     qword ptr [rdx], 0
0x140001a73  call    cs:__imp_KeQueryPerformanceCounter
0x140001a7a  nop     dword ptr [rax+rax+00h]
0x140001a7f  mov     rcx, rdi; Entry
0x140001a82  mov     [rdi+0A8h], rax
0x140001a89  call    SqospDispatchDeferredJob
0x140001a8e  test    rsi, rsi
0x140001a91  jnz     short loc_140001A60
0x140001a93  mov     rcx, [rbx+10h]
0x140001a97  call    DvRemoveOrderedWorkQueue
0x140001a9c  mov     rsi, rax
0x140001a9f  test    rax, rax
0x140001aa2  jnz     short loc_140001A60
0x140001aa4  jmp     loc_1400019AC
```
