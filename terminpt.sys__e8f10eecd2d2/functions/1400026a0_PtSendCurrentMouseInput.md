# PtSendCurrentMouseInput

- ea: `0x1400026a0`
- end: `0x140002852`
- name: `PtSendCurrentMouseInput`
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
- `0x1400026a0`
- `0x140002858`
- `0x14000293c`
- `0x140003130`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140002754`
- `ntoskrnl!KfRaiseIrql` at `0x140002754`
- `ntoskrnl!KeLowerIrql` at `0x14000277a`
- `ntoskrnl!KeLowerIrql` at `0x14000277a`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400027f7`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400027f7`

## pseudocode

```c
__int64 __fastcall PtSendCurrentMouseInput(__int64 a1, __int64 a2, unsigned int a3)
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
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  Interval.QuadPart = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      53,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  result = *(_QWORD *)(a1 + 64);
  if ( *(_DWORD *)(result + 64) )
  {
    v7 = *(_QWORD *)(result + 72);
    v8 = *(void (__fastcall **)(__int64, __int64, __int64, unsigned int *))(result + 80);
    v14 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      result = WPP_RECORDER_SF_sl(WPP_GLOBAL_Control->DeviceExtension, a2, a3, 54, v12);
    v9 = v4 + 24 * v3;
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
        v11 = ((int)v9 - (int)v4) / 0x18u - v14;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_sdd(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            a3,
            55,
            v12,
            v13,
            v14,
            ((int)v9 - (int)v4) / 0x18u - v14);
          result = v14;
        }
        if ( !v11 )
          break;
        Interval.QuadPart = -10000;
        v4 += 24 * result;
        KeDelayExecutionThread(0, 1u, &Interval);
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_sq(
             WPP_GLOBAL_Control->DeviceExtension,
             a2,
             a3,
             56,
             (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids,
             v13,
             a1);
  return result;
}

```

## disassembly

```asm
0x1400026a0  mov     rax, rsp
0x1400026a3  mov     [rax+10h], rbx
0x1400026a7  mov     [rax+18h], rbp
0x1400026ab  push    rsi
0x1400026ac  push    rdi
0x1400026ad  push    r13
0x1400026af  push    r14
0x1400026b1  push    r15
0x1400026b3  sub     rsp, 40h
0x1400026b7  mov     ebx, r8d
0x1400026ba  mov     rdi, rdx
0x1400026bd  mov     rsi, rcx
0x1400026c0  mov     qword ptr [rax+20h], 0
0x1400026c8  lea     r13, WPP_RECORDER_INITIALIZED
0x1400026cf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400026d6  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x1400026dd  jz      short loc_1400026F9
0x1400026df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026e6  mov     r9d, 35h ; '5'
0x1400026ec  mov     [rax-48h], rbp
0x1400026f0  mov     rcx, [rcx+40h]
0x1400026f4  call    WPP_RECORDER_SF_s
0x1400026f9  mov     rax, [rsi+40h]
0x1400026fd  cmp     dword ptr [rax+40h], 0
0x140002701  jz      loc_14000280F
0x140002707  mov     r14, [rax+48h]
0x14000270b  mov     r15, [rax+50h]
0x14000270f  mov     [rsp+68h+arg_0], 0
0x140002717  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000271e  jz      short loc_14000273A
0x140002720  mov     rcx, cs:WPP_GLOBAL_Control
0x140002727  mov     r9d, 36h ; '6'
0x14000272d  mov     dword ptr [rsp+68h+var_38], ebx
0x140002731  mov     rcx, [rcx+40h]
0x140002735  call    WPP_RECORDER_SF_sl
0x14000273a  lea     rcx, [rbx+rbx*2]
0x14000273e  lea     rbp, [rdi+rcx*8]
0x140002742  test    ebx, ebx
0x140002744  jz      loc_140002808
0x14000274a  mov     cl, 2; NewIrql
0x14000274c  mov     [rsp+68h+arg_0], 0
0x140002754  call    cs:__imp_KfRaiseIrql
0x14000275b  nop     dword ptr [rax+rax+00h]
0x140002760  lea     r9, [rsp+68h+arg_0]
0x140002765  mov     r8, rbp
0x140002768  mov     bl, al
0x14000276a  mov     rdx, rdi
0x14000276d  mov     rax, r15
0x140002770  mov     rcx, r14
0x140002773  call    _guard_dispatch_icall
0x140002778  mov     cl, bl; NewIrql
0x14000277a  call    cs:__imp_KeLowerIrql
0x140002781  nop     dword ptr [rax+rax+00h]
0x140002786  mov     rcx, rbp
0x140002789  mov     rax, 0AAAAAAAAAAAAAAABh
0x140002793  sub     rcx, rdi
0x140002796  mov     ecx, ecx
0x140002798  mul     rcx
0x14000279b  mov     eax, [rsp+68h+arg_0]
0x14000279f  mov     rbx, rdx
0x1400027a2  shr     rbx, 4
0x1400027a6  sub     ebx, eax
0x1400027a8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400027af  jz      short loc_1400027D3
0x1400027b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027b8  mov     r9d, 37h ; '7'
0x1400027be  mov     [rsp+68h+var_30], ebx
0x1400027c2  mov     dword ptr [rsp+68h+var_38], eax
0x1400027c6  mov     rcx, [rcx+40h]
0x1400027ca  call    WPP_RECORDER_SF_sdd
0x1400027cf  mov     eax, [rsp+68h+arg_0]
0x1400027d3  test    ebx, ebx
0x1400027d5  jz      short loc_140002808
0x1400027d7  lea     rcx, [rax+rax*2]
0x1400027db  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFFD8F0h
0x1400027e7  lea     rdi, [rdi+rcx*8]
0x1400027eb  mov     dl, 1; Alertable
0x1400027ed  xor     ecx, ecx; WaitMode
0x1400027ef  lea     r8, [rsp+68h+Interval]; Interval
0x1400027f7  call    cs:__imp_KeDelayExecutionThread
0x1400027fe  nop     dword ptr [rax+rax+00h]
0x140002803  jmp     loc_14000274A
0x140002808  lea     rbp, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x14000280f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140002816  jz      short loc_140002838
0x140002818  mov     rcx, cs:WPP_GLOBAL_Control
0x14000281f  mov     r9d, 38h ; '8'
0x140002825  mov     [rsp+68h+var_38], rsi
0x14000282a  mov     [rsp+68h+var_48], rbp
0x14000282f  mov     rcx, [rcx+40h]
0x140002833  call    WPP_RECORDER_SF_sq
0x140002838  lea     r11, [rsp+68h+var_28]
0x14000283d  mov     rbx, [r11+38h]
0x140002841  mov     rbp, [r11+40h]
0x140002845  mov     rsp, r11
0x140002848  pop     r15
0x14000284a  pop     r14
0x14000284c  pop     r13
0x14000284e  pop     rdi
0x14000284f  pop     rsi
0x140002850  retn
```
