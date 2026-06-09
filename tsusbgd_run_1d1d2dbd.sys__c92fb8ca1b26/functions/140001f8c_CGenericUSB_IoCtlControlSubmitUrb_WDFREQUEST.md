# CGenericUSB::IoCtlControlSubmitUrb(WDFREQUEST__ *)

- ea: `0x140001f8c`
- end: `0x140002220`
- name: `?IoCtlControlSubmitUrb@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `660`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140001f8c`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlControlSubmitUrb(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  CGenericUSB *v4; // rbx
  __int64 v5; // rax
  CGenericUSB **v6; // rcx
  int v7; // ebp
  CGenericUSB *v8; // rcx
  CGenericUSB **v9; // rax
  _QWORD v10[9]; // [rsp+30h] [rbp-68h] BYREF

  memset(v10, 0, sizeof(v10));
  v4 = (CGenericUSB *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                        a2,
                        off_140009018);
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[138].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2);
  if ( v5 )
    v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[70].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           v5);
  *((_QWORD *)v4 + 2) = a2;
  *((_QWORD *)v4 + 3) = v5;
  ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *((_QWORD *)this + 10));
  v6 = (CGenericUSB **)*((_QWORD *)this + 9);
  if ( *v6 != (CGenericUSB *)((char *)this + 64) )
    goto LABEL_13;
  *(_QWORD *)v4 = (char *)this + 64;
  *((_QWORD *)v4 + 1) = v6;
  *v6 = v4;
  *((_QWORD *)this + 9) = v4;
  ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *((_QWORD *)this + 10));
  memset(v10, 0, sizeof(v10));
  LOWORD(v10[0]) = 15;
  LODWORD(v10[3]) = 2228227;
  v10[1] = *((_QWORD *)v4 + 217);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v10);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, CGenericUSB *))WPP_MAIN_CB.Queue.ListEntry.Flink[130].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    GdEvtIoCompletionSubmitUrb,
    this);
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          *((_QWORD *)this + 4),
          0) )
  {
    v7 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x27u,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v7);
    if ( v7 < 0 )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *((_QWORD *)this + 10));
      v8 = *(CGenericUSB **)v4;
      if ( *(CGenericUSB **)(*(_QWORD *)v4 + 8LL) == v4 )
      {
        v9 = (CGenericUSB **)*((_QWORD *)v4 + 1);
        if ( *v9 == v4 )
        {
          *v9 = v8;
          *((_QWORD *)v8 + 1) = v9;
          ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Blink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            *((_QWORD *)this + 10));
          ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            a2,
            (unsigned int)v7,
            0);
          return;
        }
      }
LABEL_13:
      __fastfail(3u);
    }
  }
}

```

## disassembly

```asm
0x140001f8c  mov     [rsp+arg_10], rbx
0x140001f91  push    rbp
0x140001f92  push    rsi
0x140001f93  push    rdi
0x140001f94  sub     rsp, 80h
0x140001f9b  mov     rax, cs:__security_cookie
0x140001fa2  xor     rax, rsp
0x140001fa5  mov     [rsp+98h+var_20], rax
0x140001faa  mov     rdi, rdx
0x140001fad  mov     rsi, rcx
0x140001fb0  mov     ebp, 48h ; 'H'
0x140001fb5  lea     rcx, [rsp+98h+var_68]; void *
0x140001fba  mov     r8d, ebp; Size
0x140001fbd  xor     edx, edx; Val
0x140001fbf  call    memset
0x140001fc4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001fcb  mov     rdx, rdi
0x140001fce  mov     r8, cs:off_140009018
0x140001fd5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001fdc  mov     rax, [rax+650h]
0x140001fe3  call    _guard_dispatch_icall
0x140001fe8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140001fef  mov     rbx, rax
0x140001ff2  mov     rdx, rdi
0x140001ff5  mov     rax, [rcx+8A8h]
0x140001ffc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002003  call    _guard_dispatch_icall
0x140002008  mov     rdx, rax
0x14000200b  test    rax, rax
0x14000200e  jz      short loc_14000202A
0x140002010  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140002017  mov     rax, [rcx+460h]
0x14000201e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002025  call    _guard_dispatch_icall
0x14000202a  mov     [rbx+10h], rdi
0x14000202e  mov     [rbx+18h], rax
0x140002032  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002039  mov     rdx, [rsi+50h]
0x14000203d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002044  mov     rax, [rax+9E0h]
0x14000204b  call    _guard_dispatch_icall
0x140002050  lea     rax, [rsi+40h]
0x140002054  mov     rcx, [rax+8]
0x140002058  cmp     [rcx], rax
0x14000205b  jnz     loc_140002219
0x140002061  mov     [rbx], rax
0x140002064  mov     [rbx+8], rcx
0x140002068  mov     [rcx], rbx
0x14000206b  mov     [rax+8], rbx
0x14000206f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002076  mov     rdx, [rsi+50h]
0x14000207a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002081  mov     rax, [rax+9E8h]
0x140002088  call    _guard_dispatch_icall
0x14000208d  mov     r8, rbp; Size
0x140002090  lea     rcx, [rsp+98h+var_68]; void *
0x140002095  xor     edx, edx; Val
0x140002097  call    memset
0x14000209c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400020a3  lea     r8, [rsp+98h+var_68]
0x1400020a8  mov     [rsp+98h+var_68], 0Fh
0x1400020af  mov     rdx, rdi
0x1400020b2  mov     [rsp+98h+var_50], 220003h
0x1400020ba  mov     rax, [rbx+6C8h]
0x1400020c1  mov     [rsp+98h+var_60], rax
0x1400020c6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400020cd  mov     rax, [rax+7E0h]
0x1400020d4  call    _guard_dispatch_icall
0x1400020d9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400020e0  lea     r8, GdEvtIoCompletionSubmitUrb
0x1400020e7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400020ee  mov     r9, rsi
0x1400020f1  mov     rdx, rdi
0x1400020f4  mov     rax, [rax+820h]
0x1400020fb  call    _guard_dispatch_icall
0x140002100  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002107  xor     r9d, r9d
0x14000210a  mov     r8, [rsi+20h]
0x14000210e  mov     rdx, rdi
0x140002111  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002118  mov     rax, [rax+7E8h]
0x14000211f  call    _guard_dispatch_icall
0x140002124  test    al, al
0x140002126  jnz     loc_1400021F8
0x14000212c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002133  mov     rdx, rdi
0x140002136  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000213d  mov     rax, [rax+7F0h]
0x140002144  call    _guard_dispatch_icall
0x140002149  mov     ebp, eax
0x14000214b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002152  lea     rax, WPP_GLOBAL_Control
0x140002159  cmp     rcx, rax
0x14000215c  jz      short loc_14000217C
0x14000215e  cmp     byte ptr [rcx+29h], 5
0x140002162  jb      short loc_14000217C
0x140002164  mov     rcx, [rcx+18h]
0x140002168  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000216f  mov     edx, 27h ; '''
0x140002174  mov     r9d, ebp
0x140002177  call    WPP_SF_d
0x14000217c  test    ebp, ebp
0x14000217e  jns     short loc_1400021F8
0x140002180  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002187  mov     rdx, [rsi+50h]
0x14000218b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002192  mov     rax, [rax+9E0h]
0x140002199  call    _guard_dispatch_icall
0x14000219e  mov     rcx, [rbx]
0x1400021a1  cmp     [rcx+8], rbx
0x1400021a5  jnz     short loc_140002219
0x1400021a7  mov     rax, [rbx+8]
0x1400021ab  cmp     [rax], rbx
0x1400021ae  jnz     short loc_140002219
0x1400021b0  mov     [rax], rcx
0x1400021b3  mov     [rcx+8], rax
0x1400021b7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400021be  mov     rdx, [rsi+50h]
0x1400021c2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400021c9  mov     rax, [rax+9E8h]
0x1400021d0  call    _guard_dispatch_icall
0x1400021d5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400021dc  xor     r9d, r9d
0x1400021df  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400021e6  mov     r8d, ebp
0x1400021e9  mov     rdx, rdi
0x1400021ec  mov     rax, [rax+848h]
0x1400021f3  call    _guard_dispatch_icall
0x1400021f8  mov     rcx, [rsp+98h+var_20]
0x1400021fd  xor     rcx, rsp; StackCookie
0x140002200  call    __security_check_cookie
0x140002205  mov     rbx, [rsp+98h+arg_10]
0x14000220d  add     rsp, 80h
0x140002214  pop     rdi
0x140002215  pop     rsi
0x140002216  pop     rbp
0x140002217  retn
0x140002219  mov     ecx, 3
0x14000221e  int     29h; Win8: RtlFailFast(ecx)
```
