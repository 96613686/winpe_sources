# WinHvpDeletePartition

- ea: `0x1400202cc`
- end: `0x14002049b`
- name: `WinHvpDeletePartition`
- size: `463`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14001f740`
- `0x14001f890`
- `0x14001f8b0`

## callees

- `0x140001008`
- `0x140001038`
- `0x140007310`
- `0x1400077f8`
- `0x140009c50`
- `0x140009c90`
- `0x1400202cc`
- `0x1400204a4`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14002033f`
- `HAL!KeQueryPerformanceCounter` at `0x1400203ab`
- `HAL!KeQueryPerformanceCounter` at `0x14002033f`
- `HAL!KeQueryPerformanceCounter` at `0x1400203ab`

## string_xrefs

- `0x140020407`: `WinHvpDeletePartition`

## pseudocode

```c
__int64 __fastcall WinHvpDeletePartition(unsigned __int64 a1, __int64 (__fastcall *a2)(unsigned __int64))
{
  int v4; // eax
  __int64 v5; // rdx
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v10; // r8
  __int64 v11; // rbx
  LARGE_INTEGER v12; // rax
  __int64 v13; // rcx
  __int16 v14; // r8
  __int16 v16; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+34h] [rbp-35h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+40h] [rbp-29h] BYREF
  const char *v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  __int16 *v22; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  int *v24; // [rsp+80h] [rbp+17h]
  __int64 v25; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 *v26; // [rsp+90h] [rbp+27h]
  __int64 v27; // [rsp+98h] [rbp+2Fh]

  v4 = WinHvFinalizePartition(a1);
  v6 = 0;
  if ( v4 != -1070268409 )
    v6 = v4;
  if ( v6 < 0 )
  {
    v7 = *(_QWORD *)&WinHvpBlackbox;
    if ( *(_QWORD *)&WinHvpBlackbox )
    {
      v8 = 2LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&WinHvpBlackbox + 4LL), 1u) & 0x3F);
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v8 + 8) = 8;
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v8 + 12) = a1;
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v7 = *(_QWORD *)&WinHvpBlackbox;
      *(LARGE_INTEGER *)(*(_QWORD *)&WinHvpBlackbox + 8 * v8 + 16) = PerformanceCounter;
    }
    v10 = 1978;
    goto LABEL_15;
  }
  v6 = a2(a1);
  if ( v6 < 0 )
  {
    if ( *(_QWORD *)&WinHvpBlackbox )
    {
      v11 = 2LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&WinHvpBlackbox + 4LL), 1u) & 0x3F);
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v11 + 8) = 9;
      *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v11 + 12) = a1;
      v12 = KeQueryPerformanceCounter(0);
      v7 = *(_QWORD *)&WinHvpBlackbox;
      *(LARGE_INTEGER *)(*(_QWORD *)&WinHvpBlackbox + 8 * v11 + 16) = v12;
    }
    v10 = 1989;
    goto LABEL_15;
  }
  v6 = WinHvpDeleteHvPartition(a1);
  if ( (int)WinHvpDeleteWinHvPartition(a1, 0) < 0 )
    __int2c();
  if ( v6 < 0 )
  {
    v10 = 2006;
LABEL_15:
    if ( (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn(v7, v5, v10) )
    {
      v16 = v14;
      v20 = "WinHvpDeletePartition";
      v21 = 22;
      v22 = &v16;
      v23 = 2;
      v24 = &v17;
      v17 = v6;
      v26 = &v18;
      v25 = 4;
      v18 = a1;
      v27 = 8;
      tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)byte_14000E885, 0, 0, 6u, &v19);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400202cc  mov     [rsp-8+arg_10], rbx
0x1400202d1  push    rbp
0x1400202d2  push    rsi
0x1400202d3  push    rdi
0x1400202d4  lea     rbp, [rsp-47h]
0x1400202d9  sub     rsp, 0B0h
0x1400202e0  mov     rax, cs:__security_cookie
0x1400202e7  xor     rax, rsp
0x1400202ea  mov     [rbp+57h+var_20], rax
0x1400202ee  mov     rbx, rdx
0x1400202f1  mov     rsi, rcx
0x1400202f4  call    WinHvFinalizePartition
0x1400202f9  xor     edi, edi
0x1400202fb  cmp     eax, 0C0350007h
0x140020300  cmovnz  edi, eax
0x140020303  test    edi, edi
0x140020305  jns     short loc_140020362
0x140020307  mov     rcx, cs:WinHvpBlackbox
0x14002030e  test    rcx, rcx
0x140020311  jz      short loc_140020357
0x140020313  mov     ebx, 1
0x140020318  lock xadd [rcx+4], ebx
0x14002031d  mov     rax, cs:WinHvpBlackbox
0x140020324  and     ebx, 3Fh
0x140020327  add     rbx, rbx
0x14002032a  xor     ecx, ecx; PerformanceFrequency
0x14002032c  mov     dword ptr [rax+rbx*8+8], 8
0x140020334  mov     rax, cs:WinHvpBlackbox
0x14002033b  mov     [rax+rbx*8+0Ch], esi
0x14002033f  call    cs:__imp_KeQueryPerformanceCounter
0x140020346  nop     dword ptr [rax+rax+00h]
0x14002034b  mov     rcx, cs:WinHvpBlackbox
0x140020352  mov     [rcx+rbx*8+10h], rax
0x140020357  mov     r8d, 7BAh
0x14002035d  jmp     loc_1400203F3
0x140020362  mov     rcx, rsi
0x140020365  mov     rax, rbx
0x140020368  call    _guard_dispatch_icall
0x14002036d  mov     edi, eax
0x14002036f  test    eax, eax
0x140020371  jns     short loc_1400203CB
0x140020373  mov     rax, cs:WinHvpBlackbox
0x14002037a  test    rax, rax
0x14002037d  jz      short loc_1400203C3
0x14002037f  mov     ebx, 1
0x140020384  lock xadd [rax+4], ebx
0x140020389  mov     rax, cs:WinHvpBlackbox
0x140020390  and     ebx, 3Fh
0x140020393  add     rbx, rbx
0x140020396  xor     ecx, ecx; PerformanceFrequency
0x140020398  mov     dword ptr [rax+rbx*8+8], 9
0x1400203a0  mov     rax, cs:WinHvpBlackbox
0x1400203a7  mov     [rax+rbx*8+0Ch], esi
0x1400203ab  call    cs:__imp_KeQueryPerformanceCounter
0x1400203b2  nop     dword ptr [rax+rax+00h]
0x1400203b7  mov     rcx, cs:WinHvpBlackbox
0x1400203be  mov     [rcx+rbx*8+10h], rax
0x1400203c3  mov     r8d, 7C5h
0x1400203c9  jmp     short loc_1400203F3
0x1400203cb  mov     rcx, rsi
0x1400203ce  call    WinHvpDeleteHvPartition
0x1400203d3  xor     edx, edx
0x1400203d5  mov     rcx, rsi
0x1400203d8  mov     edi, eax
0x1400203da  call    WinHvpDeleteWinHvPartition
0x1400203df  test    eax, eax
0x1400203e1  jns     short loc_1400203E5
0x1400203e3  int     2Ch; Windows NT - assertion failure
0x1400203e5  test    edi, edi
0x1400203e7  jns     loc_140020479
0x1400203ed  mov     r8d, 7D6h
0x1400203f3  mov     eax, cs:dword_140011000
0x1400203f9  cmp     eax, 2
0x1400203fc  jbe     short loc_140020479
0x1400203fe  call    _tlgKeywordOn
0x140020403  test    al, al
0x140020405  jz      short loc_140020479
0x140020407  lea     rax, aWinhvpdeletepa; "WinHvpDeletePartition"
0x14002040e  mov     [rbp+57h+var_90], r8w
0x140020413  mov     [rbp+57h+var_60], rax
0x140020417  lea     rdx, byte_14000E885
0x14002041e  lea     rax, [rbp+57h+var_90]
0x140020422  mov     [rbp+57h+var_58], 16h
0x14002042a  mov     [rbp+57h+var_50], rax
0x14002042e  xor     r9d, r9d
0x140020431  lea     rax, [rbp+57h+var_8C]
0x140020435  mov     [rbp+57h+var_48], 2
0x14002043d  mov     [rbp+57h+var_40], rax
0x140020441  xor     r8d, r8d
0x140020444  lea     rax, [rbp+57h+var_88]
0x140020448  mov     [rbp+57h+var_8C], edi
0x14002044b  mov     [rbp+57h+var_30], rax
0x14002044f  lea     rax, [rbp+57h+var_80]
0x140020453  mov     [rsp+0C0h+var_98], rax
0x140020458  mov     [rsp+0C0h+var_A0], 6
0x140020460  mov     [rbp+57h+var_38], 4
0x140020468  mov     [rbp+57h+var_88], rsi
0x14002046c  mov     [rbp+57h+var_28], 8
0x140020474  call    _tlgWriteTransfer_EtwWriteTransfer
0x140020479  mov     eax, edi
0x14002047b  mov     rcx, [rbp+57h+var_20]
0x14002047f  xor     rcx, rsp; StackCookie
0x140020482  call    __security_check_cookie
0x140020487  mov     rbx, [rsp+0C0h+arg_10]
0x14002048f  add     rsp, 0B0h
0x140020496  pop     rdi
0x140020497  pop     rsi
0x140020498  pop     rbp
0x140020499  retn
```
