# CGenericUSB::IoCtlRecordFailure(WDFREQUEST__ *)

- ea: `0x140003368`
- end: `0x14000360a`
- name: `?IoCtlRecordFailure@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `674`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140003368`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlRecordFailure(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  __int64 v4; // r14
  int v5; // ebx
  __int64 v6; // r9
  unsigned int *v7; // [rsp+30h] [rbp-49h] BYREF
  __int64 v8; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v9[9]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v10; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v11; // [rsp+98h] [rbp+1Fh]
  __int64 v12; // [rsp+A8h] [rbp+2Fh]

  memset(v9, 0, sizeof(v9));
  v12 = 0;
  v8 = 0;
  v7 = 0;
  v10 = 0;
  v11 = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         off_140009018);
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned int **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         20,
         &v7,
         &v8);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x24u,
        (__int64)WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v5);
LABEL_14:
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      a2,
      (unsigned int)v5);
    return;
  }
  v6 = *v7;
  if ( v6 != v8 )
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x25u,
        (__int64)WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v6);
    goto LABEL_14;
  }
  v12 = 0;
  v10 = 0;
  LOWORD(v10) = 40;
  v11 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v10);
  v9[1] = v7;
  LOWORD(v9[0]) = 15;
  LODWORD(v9[3]) = 2228267;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v9);
  *(_QWORD *)(v4 + 1768) = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 (__fastcall *)(__int64, __int64, __int64), _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[130].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    GdEvtIoCompletionGeneric,
    0);
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          *((_QWORD *)this + 4),
          0) )
  {
    v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x26u,
        (__int64)WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v5);
    if ( v5 < 0 )
      goto LABEL_14;
  }
}

```

## disassembly

```asm
0x140003368  mov     [rsp-8+arg_10], rbx
0x14000336d  mov     [rsp-8+arg_18], rsi
0x140003372  push    rbp
0x140003373  push    rdi
0x140003374  push    r14
0x140003376  lea     rbp, [rsp-47h]
0x14000337b  sub     rsp, 0C0h
0x140003382  mov     rax, cs:__security_cookie
0x140003389  xor     rax, rsp
0x14000338c  mov     [rbp+57h+var_20], rax
0x140003390  mov     rdi, rdx
0x140003393  mov     rsi, rcx
0x140003396  xor     edx, edx; Val
0x140003398  lea     rcx, [rbp+57h+var_90]; void *
0x14000339c  lea     r8d, [rdx+48h]; Size
0x1400033a0  call    memset
0x1400033a5  mov     r8, cs:off_140009018
0x1400033ac  xor     eax, eax
0x1400033ae  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400033b5  xorps   xmm0, xmm0
0x1400033b8  mov     [rbp+57h+var_28], rax
0x1400033bc  mov     rdx, rdi
0x1400033bf  mov     [rbp+57h+var_98], rax
0x1400033c3  mov     [rbp+57h+var_A0], rax
0x1400033c7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400033ce  movups  [rbp+57h+var_48], xmm0
0x1400033d2  movups  [rbp+57h+var_38], xmm0
0x1400033d6  mov     rax, [rax+650h]
0x1400033dd  call    _guard_dispatch_icall
0x1400033e2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400033e9  lea     r9, [rbp+57h+var_A0]
0x1400033ed  mov     r14, rax
0x1400033f0  mov     r8d, 14h
0x1400033f6  mov     rdx, rdi
0x1400033f9  mov     rax, [rcx+868h]
0x140003400  lea     rcx, [rbp+57h+var_98]
0x140003404  mov     [rsp+0D0h+var_B0], rcx
0x140003409  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003410  call    _guard_dispatch_icall
0x140003415  mov     ebx, eax
0x140003417  test    eax, eax
0x140003419  jns     short loc_140003459
0x14000341b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003422  lea     rax, WPP_GLOBAL_Control
0x140003429  cmp     rcx, rax
0x14000342c  jz      loc_1400035C5
0x140003432  cmp     byte ptr [rcx+29h], 2
0x140003436  jb      loc_1400035C5
0x14000343c  mov     rcx, [rcx+18h]
0x140003440  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140003447  mov     edx, 24h ; '$'
0x14000344c  mov     r9d, ebx
0x14000344f  call    WPP_SF_d
0x140003454  jmp     loc_1400035C5
0x140003459  mov     rax, [rbp+57h+var_A0]
0x14000345d  mov     r9d, [rax]
0x140003460  cmp     r9, [rbp+57h+var_98]
0x140003464  jz      short loc_1400034A6
0x140003466  mov     ebx, 0C000000Dh
0x14000346b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003472  lea     rax, WPP_GLOBAL_Control
0x140003479  cmp     rcx, rax
0x14000347c  jz      loc_1400035C5
0x140003482  cmp     byte ptr [rcx+29h], 2
0x140003486  jb      loc_1400035C5
0x14000348c  mov     rcx, [rcx+18h]
0x140003490  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140003497  mov     edx, 25h ; '%'
0x14000349c  call    WPP_SF_d
0x1400034a1  jmp     loc_1400035C5
0x1400034a6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400034ad  lea     r8, [rbp+57h+var_48]
0x1400034b1  xor     eax, eax
0x1400034b3  xorps   xmm0, xmm0
0x1400034b6  mov     [rbp+57h+var_28], rax
0x1400034ba  mov     rdx, rdi
0x1400034bd  movups  [rbp+57h+var_48], xmm0
0x1400034c1  mov     eax, 28h ; '('
0x1400034c6  mov     word ptr [rbp+57h+var_48], ax
0x1400034ca  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400034d1  movups  [rbp+57h+var_38], xmm0
0x1400034d5  mov     rax, [rax+850h]
0x1400034dc  call    _guard_dispatch_icall
0x1400034e1  mov     rax, [rbp+57h+var_A0]
0x1400034e5  lea     r8, [rbp+57h+var_90]
0x1400034e9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400034f0  mov     rdx, rdi
0x1400034f3  mov     [rbp+57h+var_88], rax
0x1400034f7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400034fe  mov     [rbp+57h+var_90], 0Fh
0x140003504  mov     [rbp+57h+var_78], 22002Bh
0x14000350b  mov     rax, [rax+7E0h]
0x140003512  call    _guard_dispatch_icall
0x140003517  mov     qword ptr [r14+6E8h], 0
0x140003522  lea     r8, GdEvtIoCompletionGeneric
0x140003529  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003530  xor     r9d, r9d
0x140003533  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000353a  mov     rdx, rdi
0x14000353d  mov     rax, [rax+820h]
0x140003544  call    _guard_dispatch_icall
0x140003549  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003550  xor     r9d, r9d
0x140003553  mov     r8, [rsi+20h]
0x140003557  mov     rdx, rdi
0x14000355a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003561  mov     rax, [rax+7E8h]
0x140003568  call    _guard_dispatch_icall
0x14000356d  test    al, al
0x14000356f  jnz     short loc_1400035E5
0x140003571  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003578  mov     rdx, rdi
0x14000357b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003582  mov     rax, [rax+7F0h]
0x140003589  call    _guard_dispatch_icall
0x14000358e  mov     ebx, eax
0x140003590  mov     rcx, cs:WPP_GLOBAL_Control
0x140003597  lea     rax, WPP_GLOBAL_Control
0x14000359e  cmp     rcx, rax
0x1400035a1  jz      short loc_1400035C1
0x1400035a3  cmp     byte ptr [rcx+29h], 5
0x1400035a7  jb      short loc_1400035C1
0x1400035a9  mov     rcx, [rcx+18h]
0x1400035ad  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x1400035b4  mov     edx, 26h ; '&'
0x1400035b9  mov     r9d, ebx
0x1400035bc  call    WPP_SF_d
0x1400035c1  test    ebx, ebx
0x1400035c3  jns     short loc_1400035E5
0x1400035c5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400035cc  mov     r8d, ebx
0x1400035cf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400035d6  mov     rdx, rdi
0x1400035d9  mov     rax, [rax+838h]
0x1400035e0  call    _guard_dispatch_icall
0x1400035e5  mov     rcx, [rbp+57h+var_20]
0x1400035e9  xor     rcx, rsp; StackCookie
0x1400035ec  call    __security_check_cookie
0x1400035f1  lea     r11, [rsp+0D0h+var_10]
0x1400035f9  mov     rbx, [r11+30h]
0x1400035fd  mov     rsi, [r11+38h]
0x140003601  mov     rsp, r11
0x140003604  pop     r14
0x140003606  pop     rdi
0x140003607  pop     rbp
0x140003608  retn
```
