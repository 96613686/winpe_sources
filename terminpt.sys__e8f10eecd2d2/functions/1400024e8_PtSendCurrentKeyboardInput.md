# PtSendCurrentKeyboardInput

- ea: `0x1400024e8`
- end: `0x14000269a`
- name: `PtSendCurrentKeyboardInput`
- size: `434`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000b2d0`

## callees

- `0x14000173c`
- `0x1400019a8`
- `0x1400024e8`
- `0x140002858`
- `0x14000293c`
- `0x140003130`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000259c`
- `ntoskrnl!KfRaiseIrql` at `0x14000259c`
- `ntoskrnl!KeLowerIrql` at `0x1400025c2`
- `ntoskrnl!KeLowerIrql` at `0x1400025c2`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000263f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000263f`

## pseudocode

```c
__int64 __fastcall PtSendCurrentKeyboardInput(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 result; // rax
  __int64 v7; // r14
  void (__fastcall *v8)(__int64, __int64, __int64, unsigned int *); // r15
  __int64 v9; // rbp
  KIRQL v10; // bl
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+28h] [rbp-40h]
  unsigned int v14; // [rsp+70h] [rbp+8h] BYREF
  _LARGE_INTEGER Interval; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  Interval.QuadPart = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      49,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  result = *(_QWORD *)(a1 + 64);
  if ( *(_DWORD *)(result + 64) )
  {
    v7 = *(_QWORD *)(result + 72);
    v8 = *(void (__fastcall **)(__int64, __int64, __int64, unsigned int *))(result + 80);
    v14 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      result = WPP_RECORDER_SF_sl(WPP_GLOBAL_Control->DeviceExtension, a2, a3, 50, v12);
    v9 = v4 + 12 * v3;
    if ( (_DWORD)v3 )
    {
      while ( 1 )
      {
        v14 = 0;
        v10 = KfRaiseIrql(2u);
        v8(v7, v4, v9, &v14);
        KeLowerIrql(v10);
        a2 = ((unsigned int)(v9 - v4) * (unsigned __int128)0xAAAAAAAAAAAAAAABuLL) >> 64;
        result = v14;
        v11 = ((int)v9 - (int)v4) / 0xCu - v14;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_sdd(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            a3,
            51,
            v12,
            v13,
            v14,
            ((int)v9 - (int)v4) / 0xCu - v14);
          result = v14;
        }
        if ( !v11 )
          break;
        Interval.QuadPart = -10000;
        v4 += 12 * result;
        KeDelayExecutionThread(0, 1u, &Interval);
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_sq(
             WPP_GLOBAL_Control->DeviceExtension,
             a2,
             a3,
             52,
             (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids,
             v13,
             a1);
  return result;
}

```

## disassembly

```asm
0x1400024e8  mov     rax, rsp
0x1400024eb  mov     [rax+10h], rbx
0x1400024ef  mov     [rax+18h], rbp
0x1400024f3  push    rsi
0x1400024f4  push    rdi
0x1400024f5  push    r13
0x1400024f7  push    r14
0x1400024f9  push    r15
0x1400024fb  sub     rsp, 40h
0x1400024ff  mov     ebx, r8d
0x140002502  mov     rdi, rdx
0x140002505  mov     rsi, rcx
0x140002508  mov     qword ptr [rax+20h], 0
0x140002510  lea     r13, WPP_RECORDER_INITIALIZED
0x140002517  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000251e  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x140002525  jz      short loc_140002541
0x140002527  mov     rcx, cs:WPP_GLOBAL_Control
0x14000252e  mov     r9d, 31h ; '1'
0x140002534  mov     [rax-48h], rbp
0x140002538  mov     rcx, [rcx+40h]
0x14000253c  call    WPP_RECORDER_SF_s
0x140002541  mov     rax, [rsi+40h]
0x140002545  cmp     dword ptr [rax+40h], 0
0x140002549  jz      loc_140002657
0x14000254f  mov     r14, [rax+48h]
0x140002553  mov     r15, [rax+50h]
0x140002557  mov     [rsp+68h+arg_0], 0
0x14000255f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140002566  jz      short loc_140002582
0x140002568  mov     rcx, cs:WPP_GLOBAL_Control
0x14000256f  mov     r9d, 32h ; '2'
0x140002575  mov     dword ptr [rsp+68h+var_38], ebx
0x140002579  mov     rcx, [rcx+40h]
0x14000257d  call    WPP_RECORDER_SF_sl
0x140002582  lea     rcx, [rbx+rbx*2]
0x140002586  lea     rbp, [rdi+rcx*4]
0x14000258a  test    ebx, ebx
0x14000258c  jz      loc_140002650
0x140002592  mov     cl, 2; NewIrql
0x140002594  mov     [rsp+68h+arg_0], 0
0x14000259c  call    cs:__imp_KfRaiseIrql
0x1400025a3  nop     dword ptr [rax+rax+00h]
0x1400025a8  lea     r9, [rsp+68h+arg_0]
0x1400025ad  mov     r8, rbp
0x1400025b0  mov     bl, al
0x1400025b2  mov     rdx, rdi
0x1400025b5  mov     rax, r15
0x1400025b8  mov     rcx, r14
0x1400025bb  call    _guard_dispatch_icall
0x1400025c0  mov     cl, bl; NewIrql
0x1400025c2  call    cs:__imp_KeLowerIrql
0x1400025c9  nop     dword ptr [rax+rax+00h]
0x1400025ce  mov     rcx, rbp
0x1400025d1  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400025db  sub     rcx, rdi
0x1400025de  mov     ecx, ecx
0x1400025e0  mul     rcx
0x1400025e3  mov     eax, [rsp+68h+arg_0]
0x1400025e7  mov     rbx, rdx
0x1400025ea  shr     rbx, 3
0x1400025ee  sub     ebx, eax
0x1400025f0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400025f7  jz      short loc_14000261B
0x1400025f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002600  mov     r9d, 33h ; '3'
0x140002606  mov     [rsp+68h+var_30], ebx
0x14000260a  mov     dword ptr [rsp+68h+var_38], eax
0x14000260e  mov     rcx, [rcx+40h]
0x140002612  call    WPP_RECORDER_SF_sdd
0x140002617  mov     eax, [rsp+68h+arg_0]
0x14000261b  test    ebx, ebx
0x14000261d  jz      short loc_140002650
0x14000261f  lea     rcx, [rax+rax*2]
0x140002623  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFFD8F0h
0x14000262f  lea     rdi, [rdi+rcx*4]
0x140002633  mov     dl, 1; Alertable
0x140002635  xor     ecx, ecx; WaitMode
0x140002637  lea     r8, [rsp+68h+Interval]; Interval
0x14000263f  call    cs:__imp_KeDelayExecutionThread
0x140002646  nop     dword ptr [rax+rax+00h]
0x14000264b  jmp     loc_140002592
0x140002650  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x140002657  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000265e  jz      short loc_140002680
0x140002660  mov     rcx, cs:WPP_GLOBAL_Control
0x140002667  mov     r9d, 34h ; '4'
0x14000266d  mov     [rsp+68h+var_38], rsi
0x140002672  mov     [rsp+68h+var_48], rbp
0x140002677  mov     rcx, [rcx+40h]
0x14000267b  call    WPP_RECORDER_SF_sq
0x140002680  lea     r11, [rsp+68h+var_28]
0x140002685  mov     rbx, [r11+38h]
0x140002689  mov     rbp, [r11+40h]
0x14000268d  mov     rsp, r11
0x140002690  pop     r15
0x140002692  pop     r14
0x140002694  pop     r13
0x140002696  pop     rdi
0x140002697  pop     rsi
0x140002698  retn
```
