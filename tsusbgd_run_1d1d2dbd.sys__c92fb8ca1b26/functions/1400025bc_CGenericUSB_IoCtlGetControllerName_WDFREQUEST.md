# CGenericUSB::IoCtlGetControllerName(WDFREQUEST__ *)

- ea: `0x1400025bc`
- end: `0x1400027dc`
- name: `?IoCtlGetControllerName@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `544`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x1400025bc`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlGetControllerName(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  int v4; // ebx
  __int64 v5; // [rsp+30h] [rbp-49h] BYREF
  __int64 v6; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v7[9]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v8; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v9; // [rsp+98h] [rbp+1Fh]
  __int64 v10; // [rsp+A8h] [rbp+2Fh]

  memset(v7, 0, sizeof(v7));
  v10 = 0;
  v6 = 0;
  v5 = 0;
  v8 = 0;
  v9 = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         4,
         &v5,
         &v6);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Eu,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v4);
LABEL_10:
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      a2,
      (unsigned int)v4);
    return;
  }
  v10 = 0;
  v8 = 0;
  LOWORD(v8) = 40;
  v9 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v8);
  v7[1] = v5;
  v7[2] = v6;
  LOWORD(v7[0]) = 15;
  LODWORD(v7[3]) = 2229284;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v7);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 (__fastcall *)(__int64, __int64, __int64), CGenericUSB *))WPP_MAIN_CB.Queue.ListEntry.Flink[130].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    GdEvtIoCompletionGetControllerName,
    this);
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          *((_QWORD *)this + 4),
          0) )
  {
    v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Fu,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v4);
    if ( v4 < 0 )
      goto LABEL_10;
  }
}

```

## disassembly

```asm
0x1400025bc  mov     [rsp-8+arg_10], rbx
0x1400025c1  push    rbp
0x1400025c2  push    rsi
0x1400025c3  push    rdi
0x1400025c4  lea     rbp, [rsp-47h]
0x1400025c9  sub     rsp, 0C0h
0x1400025d0  mov     rax, cs:__security_cookie
0x1400025d7  xor     rax, rsp
0x1400025da  mov     [rbp+57h+var_20], rax
0x1400025de  mov     rdi, rdx
0x1400025e1  mov     rsi, rcx
0x1400025e4  xor     edx, edx; Val
0x1400025e6  lea     rcx, [rbp+57h+var_90]; void *
0x1400025ea  lea     r8d, [rdx+48h]; Size
0x1400025ee  call    memset
0x1400025f3  xor     eax, eax
0x1400025f5  lea     rcx, [rbp+57h+var_98]
0x1400025f9  mov     [rbp+57h+var_28], rax
0x1400025fd  lea     r9, [rbp+57h+var_A0]
0x140002601  mov     [rbp+57h+var_98], rax
0x140002605  xorps   xmm0, xmm0
0x140002608  mov     [rbp+57h+var_A0], rax
0x14000260c  mov     r8d, 4
0x140002612  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002619  mov     rdx, rdi
0x14000261c  movups  [rbp+57h+var_48], xmm0
0x140002620  mov     [rsp+0D0h+var_B0], rcx
0x140002625  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000262c  movups  [rbp+57h+var_38], xmm0
0x140002630  mov     rax, [rax+870h]
0x140002637  call    _guard_dispatch_icall
0x14000263c  mov     ebx, eax
0x14000263e  test    eax, eax
0x140002640  jns     short loc_140002680
0x140002642  mov     rcx, cs:WPP_GLOBAL_Control
0x140002649  lea     rax, WPP_GLOBAL_Control
0x140002650  cmp     rcx, rax
0x140002653  jz      loc_14000279C
0x140002659  cmp     byte ptr [rcx+29h], 2
0x14000265d  jb      loc_14000279C
0x140002663  mov     rcx, [rcx+18h]
0x140002667  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000266e  mov     edx, 1Eh
0x140002673  mov     r9d, ebx
0x140002676  call    WPP_SF_d
0x14000267b  jmp     loc_14000279C
0x140002680  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002687  lea     r8, [rbp+57h+var_48]
0x14000268b  xor     eax, eax
0x14000268d  xorps   xmm0, xmm0
0x140002690  mov     [rbp+57h+var_28], rax
0x140002694  mov     rdx, rdi
0x140002697  movups  [rbp+57h+var_48], xmm0
0x14000269b  mov     eax, 28h ; '('
0x1400026a0  mov     word ptr [rbp+57h+var_48], ax
0x1400026a4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400026ab  movups  [rbp+57h+var_38], xmm0
0x1400026af  mov     rax, [rax+850h]
0x1400026b6  call    _guard_dispatch_icall
0x1400026bb  mov     rax, [rbp+57h+var_A0]
0x1400026bf  lea     r8, [rbp+57h+var_90]
0x1400026c3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400026ca  mov     rdx, rdi
0x1400026cd  mov     [rbp+57h+var_88], rax
0x1400026d1  mov     rax, [rbp+57h+var_98]
0x1400026d5  mov     [rbp+57h+var_80], rax
0x1400026d9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400026e0  mov     [rbp+57h+var_90], 0Fh
0x1400026e6  mov     [rbp+57h+var_78], 220424h
0x1400026ed  mov     rax, [rax+7E0h]
0x1400026f4  call    _guard_dispatch_icall
0x1400026f9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002700  lea     r8, GdEvtIoCompletionGetControllerName
0x140002707  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000270e  mov     r9, rsi
0x140002711  mov     rdx, rdi
0x140002714  mov     rax, [rax+820h]
0x14000271b  call    _guard_dispatch_icall
0x140002720  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002727  xor     r9d, r9d
0x14000272a  mov     r8, [rsi+20h]
0x14000272e  mov     rdx, rdi
0x140002731  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002738  mov     rax, [rax+7E8h]
0x14000273f  call    _guard_dispatch_icall
0x140002744  test    al, al
0x140002746  jnz     short loc_1400027BC
0x140002748  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000274f  mov     rdx, rdi
0x140002752  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002759  mov     rax, [rax+7F0h]
0x140002760  call    _guard_dispatch_icall
0x140002765  mov     ebx, eax
0x140002767  mov     rcx, cs:WPP_GLOBAL_Control
0x14000276e  lea     rax, WPP_GLOBAL_Control
0x140002775  cmp     rcx, rax
0x140002778  jz      short loc_140002798
0x14000277a  cmp     byte ptr [rcx+29h], 5
0x14000277e  jb      short loc_140002798
0x140002780  mov     rcx, [rcx+18h]
0x140002784  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000278b  mov     edx, 1Fh
0x140002790  mov     r9d, ebx
0x140002793  call    WPP_SF_d
0x140002798  test    ebx, ebx
0x14000279a  jns     short loc_1400027BC
0x14000279c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400027a3  mov     r8d, ebx
0x1400027a6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400027ad  mov     rdx, rdi
0x1400027b0  mov     rax, [rax+838h]
0x1400027b7  call    _guard_dispatch_icall
0x1400027bc  mov     rcx, [rbp+57h+var_20]
0x1400027c0  xor     rcx, rsp; StackCookie
0x1400027c3  call    __security_check_cookie
0x1400027c8  mov     rbx, [rsp+0D0h+arg_10]
0x1400027d0  add     rsp, 0C0h
0x1400027d7  pop     rdi
0x1400027d8  pop     rsi
0x1400027d9  pop     rbp
0x1400027da  retn
```
