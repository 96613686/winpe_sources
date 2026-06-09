# CGenericUSB::IoCtlGenericForwardUSB(WDFREQUEST__ *,ulong,unsigned __int64)

- ea: `0x140002318`
- end: `0x1400025b5`
- name: `?IoCtlGenericForwardUSB@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@K_K@Z`
- size: `669`
- prototype: `void __fastcall(CGenericUSB *this, struct WDFREQUEST__ *, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140002318`
- `0x140003a10`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlGenericForwardUSB(CGenericUSB *this, struct WDFREQUEST__ *a2, int a3, __int64 a4)
{
  __int64 v8; // r13
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // [rsp+30h] [rbp-69h] BYREF
  __int64 v12; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v13[9]; // [rsp+40h] [rbp-59h] BYREF
  __int128 v14; // [rsp+88h] [rbp-11h] BYREF
  __int128 v15; // [rsp+98h] [rbp-1h]
  __int64 v16; // [rsp+A8h] [rbp+Fh]

  memset(v13, 0, sizeof(v13));
  v16 = 0;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         off_140009018);
  if ( a4 )
  {
    v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2,
           a4,
           &v12,
           &v11);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x15u,
          (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
          v9);
LABEL_17:
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        a2,
        (unsigned int)v9);
      return;
    }
    v10 = v11;
    if ( v11 != a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 22, v11, v11);
      v9 = -1073741811;
      goto LABEL_17;
    }
  }
  else
  {
    v10 = 0;
    v12 = 0;
    v11 = 0;
  }
  *(_QWORD *)(v8 + 1768) = v10;
  v16 = 0;
  v14 = 0;
  LOWORD(v14) = 40;
  v15 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v14);
  v13[1] = v12;
  LOWORD(v13[0]) = 15;
  LODWORD(v13[3]) = a3;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v13);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 (__fastcall *)(__int64, __int64, __int64), CGenericUSB *))WPP_MAIN_CB.Queue.ListEntry.Flink[130].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    GdEvtIoCompletionGeneric,
    this);
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          *((_QWORD *)this + 4),
          0) )
  {
    v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x17u,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v9);
    if ( v9 < 0 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x140002318  push    rbp
0x14000231a  push    rbx
0x14000231b  push    rsi
0x14000231c  push    rdi
0x14000231d  push    r13
0x14000231f  push    r14
0x140002321  push    r15
0x140002323  lea     rbp, [rsp-27h]
0x140002328  sub     rsp, 0C0h
0x14000232f  mov     rax, cs:__security_cookie
0x140002336  xor     rax, rsp
0x140002339  mov     [rbp+57h+var_40], rax
0x14000233d  mov     rdi, rdx
0x140002340  mov     r15d, r8d
0x140002343  xor     edx, edx; Val
0x140002345  mov     r14, rcx
0x140002348  lea     rcx, [rbp+57h+var_B0]; void *
0x14000234c  mov     rsi, r9
0x14000234f  lea     r8d, [rdx+48h]; Size
0x140002353  call    memset
0x140002358  mov     r8, cs:off_140009018
0x14000235f  xor     eax, eax
0x140002361  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002368  xorps   xmm0, xmm0
0x14000236b  mov     [rbp+57h+var_48], rax
0x14000236f  mov     rdx, rdi
0x140002372  mov     [rbp+57h+var_C0], rax
0x140002376  mov     [rbp+57h+var_B8], rax
0x14000237a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002381  movups  [rbp+57h+var_68], xmm0
0x140002385  movups  [rbp+57h+var_58], xmm0
0x140002389  mov     rax, [rax+650h]
0x140002390  call    _guard_dispatch_icall
0x140002395  mov     r13, rax
0x140002398  test    rsi, rsi
0x14000239b  jz      loc_14000244F
0x1400023a1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400023a8  lea     r9, [rbp+57h+var_B8]
0x1400023ac  mov     r8, rsi
0x1400023af  mov     rdx, rdi
0x1400023b2  mov     rax, [rcx+870h]
0x1400023b9  lea     rcx, [rbp+57h+var_C0]
0x1400023bd  mov     [rsp+0F0h+var_D0], rcx
0x1400023c2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400023c9  call    _guard_dispatch_icall
0x1400023ce  mov     ebx, eax
0x1400023d0  test    eax, eax
0x1400023d2  jns     short loc_140002412
0x1400023d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023db  lea     rax, WPP_GLOBAL_Control
0x1400023e2  cmp     rcx, rax
0x1400023e5  jz      loc_140002576
0x1400023eb  cmp     byte ptr [rcx+29h], 2
0x1400023ef  jb      loc_140002576
0x1400023f5  mov     rcx, [rcx+18h]
0x1400023f9  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002400  mov     edx, 15h
0x140002405  mov     r9d, ebx
0x140002408  call    WPP_SF_d
0x14000240d  jmp     loc_140002576
0x140002412  mov     r8, [rbp+57h+var_C0]
0x140002416  cmp     r8, rsi
0x140002419  jz      short loc_14000245E
0x14000241b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002422  lea     rax, WPP_GLOBAL_Control
0x140002429  cmp     rcx, rax
0x14000242c  jz      short loc_140002445
0x14000242e  cmp     byte ptr [rcx+29h], 2
0x140002432  jb      short loc_140002445
0x140002434  mov     rcx, [rcx+18h]
0x140002438  mov     edx, 16h
0x14000243d  mov     r9, r8
0x140002440  call    WPP_SF_i
0x140002445  mov     ebx, 0C000000Dh
0x14000244a  jmp     loc_140002576
0x14000244f  xor     r8d, r8d
0x140002452  mov     [rbp+57h+var_B8], 0
0x14000245a  mov     [rbp+57h+var_C0], r8
0x14000245e  mov     [r13+6E8h], r8
0x140002465  xor     eax, eax
0x140002467  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000246e  lea     r8, [rbp+57h+var_68]
0x140002472  mov     [rbp+57h+var_48], rax
0x140002476  xorps   xmm0, xmm0
0x140002479  movups  [rbp+57h+var_68], xmm0
0x14000247d  mov     eax, 28h ; '('
0x140002482  mov     rdx, rdi
0x140002485  mov     word ptr [rbp+57h+var_68], ax
0x140002489  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002490  movups  [rbp+57h+var_58], xmm0
0x140002494  mov     rax, [rax+850h]
0x14000249b  call    _guard_dispatch_icall
0x1400024a0  mov     rax, [rbp+57h+var_B8]
0x1400024a4  lea     r8, [rbp+57h+var_B0]
0x1400024a8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400024af  mov     rdx, rdi
0x1400024b2  mov     [rbp+57h+var_A8], rax
0x1400024b6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400024bd  mov     [rbp+57h+var_B0], 0Fh
0x1400024c3  mov     [rbp+57h+var_98], r15d
0x1400024c7  mov     rax, [rax+7E0h]
0x1400024ce  call    _guard_dispatch_icall
0x1400024d3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400024da  lea     r8, GdEvtIoCompletionGeneric
0x1400024e1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400024e8  mov     r9, r14
0x1400024eb  mov     rdx, rdi
0x1400024ee  mov     rax, [rax+820h]
0x1400024f5  call    _guard_dispatch_icall
0x1400024fa  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002501  xor     r9d, r9d
0x140002504  mov     r8, [r14+20h]
0x140002508  mov     rdx, rdi
0x14000250b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002512  mov     rax, [rax+7E8h]
0x140002519  call    _guard_dispatch_icall
0x14000251e  test    al, al
0x140002520  jnz     short loc_140002596
0x140002522  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002529  mov     rdx, rdi
0x14000252c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002533  mov     rax, [rax+7F0h]
0x14000253a  call    _guard_dispatch_icall
0x14000253f  mov     ebx, eax
0x140002541  mov     rcx, cs:WPP_GLOBAL_Control
0x140002548  lea     rax, WPP_GLOBAL_Control
0x14000254f  cmp     rcx, rax
0x140002552  jz      short loc_140002572
0x140002554  cmp     byte ptr [rcx+29h], 5
0x140002558  jb      short loc_140002572
0x14000255a  mov     rcx, [rcx+18h]
0x14000255e  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002565  mov     edx, 17h
0x14000256a  mov     r9d, ebx
0x14000256d  call    WPP_SF_d
0x140002572  test    ebx, ebx
0x140002574  jns     short loc_140002596
0x140002576  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000257d  mov     r8d, ebx
0x140002580  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002587  mov     rdx, rdi
0x14000258a  mov     rax, [rax+838h]
0x140002591  call    _guard_dispatch_icall
0x140002596  mov     rcx, [rbp+57h+var_40]
0x14000259a  xor     rcx, rsp; StackCookie
0x14000259d  call    __security_check_cookie
0x1400025a2  add     rsp, 0C0h
0x1400025a9  pop     r15
0x1400025ab  pop     r14
0x1400025ad  pop     r13
0x1400025af  pop     rdi
0x1400025b0  pop     rsi
0x1400025b1  pop     rbx
0x1400025b2  pop     rbp
0x1400025b3  retn
```
