# CGenericUSB::IoCtlQueryDeviceText(WDFREQUEST__ *,unsigned __int64)

- ea: `0x140003118`
- end: `0x140003362`
- name: `?IoCtlQueryDeviceText@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@_K@Z`
- size: `586`
- prototype: `void __fastcall(CGenericUSB *this, struct WDFREQUEST__ *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003c10`

## callees

- `0x140001ac0`
- `0x140003118`
- `0x140003a10`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlQueryDeviceText(CGenericUSB *this, struct WDFREQUEST__ *a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // [rsp+30h] [rbp-49h] BYREF
  _DWORD *v9; // [rsp+38h] [rbp-41h] BYREF
  __int128 v10; // [rsp+40h] [rbp-39h] BYREF
  __int128 v11; // [rsp+50h] [rbp-29h]
  __int64 v12; // [rsp+60h] [rbp-19h]
  _DWORD v13[18]; // [rsp+68h] [rbp-11h] BYREF

  memset(v13, 0, sizeof(v13));
  v12 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         8,
         &v9,
         &v8);
  if ( v6 < 0 )
  {
LABEL_12:
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      a2,
      (unsigned int)v6);
    return;
  }
  if ( v8 != a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 24, v7, v8);
    v6 = -1073741811;
    goto LABEL_12;
  }
  v12 = 0;
  v10 = 0;
  LOWORD(v10) = 40;
  v11 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v10);
  *(_DWORD *)(((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[142].Blink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                a2)
            + 48) = -1073741637;
  LOWORD(v13[0]) = 3099;
  v13[2] = *v9;
  v13[4] = v9[1];
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _DWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v13);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, void (__fastcall *)(struct WDFREQUEST__ *, __int64, struct _WDF_REQUEST_COMPLETION_PARAMS *), CGenericUSB *))WPP_MAIN_CB.Queue.ListEntry.Flink[130].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    GdEvtIoCompletionQueryDeviceText,
    this);
  if ( !((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a2,
          *((_QWORD *)this + 4),
          0) )
  {
    v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x19u,
        (__int64)&WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
        v6);
    if ( v6 < 0 )
      goto LABEL_12;
  }
}

```

## disassembly

```asm
0x140003118  mov     [rsp-8+arg_10], rbx
0x14000311d  mov     [rsp-8+arg_18], rsi
0x140003122  push    rbp
0x140003123  push    rdi
0x140003124  push    r14
0x140003126  lea     rbp, [rsp-47h]
0x14000312b  sub     rsp, 0C0h
0x140003132  mov     rax, cs:__security_cookie
0x140003139  xor     rax, rsp
0x14000313c  mov     [rbp+57h+var_20], rax
0x140003140  mov     rdi, rdx
0x140003143  mov     rsi, r8
0x140003146  xor     edx, edx; Val
0x140003148  mov     r14, rcx
0x14000314b  lea     rcx, [rbp+57h+var_68]; void *
0x14000314f  lea     r8d, [rdx+48h]; Size
0x140003153  call    memset
0x140003158  xor     eax, eax
0x14000315a  lea     rcx, [rbp+57h+var_A0]
0x14000315e  mov     [rbp+57h+var_70], rax
0x140003162  lea     r9, [rbp+57h+var_98]
0x140003166  mov     [rbp+57h+var_A0], rax
0x14000316a  xorps   xmm0, xmm0
0x14000316d  mov     [rbp+57h+var_98], rax
0x140003171  mov     r8d, 8
0x140003177  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000317e  mov     rdx, rdi
0x140003181  movups  [rbp+57h+var_90], xmm0
0x140003185  mov     [rsp+0D0h+var_B0], rcx
0x14000318a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003191  movups  [rbp+57h+var_80], xmm0
0x140003195  mov     rax, [rax+868h]
0x14000319c  call    _guard_dispatch_icall
0x1400031a1  mov     ebx, eax
0x1400031a3  test    eax, eax
0x1400031a5  js      loc_14000331D
0x1400031ab  mov     r9, [rbp+57h+var_A0]
0x1400031af  cmp     r9, rsi
0x1400031b2  jz      short loc_1400031E5
0x1400031b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031bb  lea     rax, WPP_GLOBAL_Control
0x1400031c2  cmp     rcx, rax
0x1400031c5  jz      short loc_1400031DB
0x1400031c7  cmp     byte ptr [rcx+29h], 2
0x1400031cb  jb      short loc_1400031DB
0x1400031cd  mov     rcx, [rcx+18h]
0x1400031d1  mov     edx, 18h
0x1400031d6  call    WPP_SF_i
0x1400031db  mov     ebx, 0C000000Dh
0x1400031e0  jmp     loc_14000331D
0x1400031e5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400031ec  lea     r8, [rbp+57h+var_90]
0x1400031f0  xor     eax, eax
0x1400031f2  xorps   xmm0, xmm0
0x1400031f5  mov     [rbp+57h+var_70], rax
0x1400031f9  mov     rdx, rdi
0x1400031fc  movups  [rbp+57h+var_90], xmm0
0x140003200  mov     eax, 28h ; '('
0x140003205  mov     word ptr [rbp+57h+var_90], ax
0x140003209  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003210  movups  [rbp+57h+var_80], xmm0
0x140003214  mov     rax, [rax+850h]
0x14000321b  call    _guard_dispatch_icall
0x140003220  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003227  mov     rdx, rdi
0x14000322a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003231  mov     rax, [rax+8E8h]
0x140003238  call    _guard_dispatch_icall
0x14000323d  lea     r8, [rbp+57h+var_68]
0x140003241  mov     rdx, rdi
0x140003244  mov     dword ptr [rax+30h], 0C00000BBh
0x14000324b  mov     rcx, [rbp+57h+var_98]
0x14000324f  mov     [rbp+57h+var_68], 0C1Bh
0x140003255  mov     eax, [rcx]
0x140003257  mov     [rbp+57h+var_60], eax
0x14000325a  mov     eax, [rcx+4]
0x14000325d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003264  mov     [rbp+57h+var_58], eax
0x140003267  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000326e  mov     rax, [rax+7E0h]
0x140003275  call    _guard_dispatch_icall
0x14000327a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003281  lea     r8, GdEvtIoCompletionQueryDeviceText
0x140003288  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000328f  mov     r9, r14
0x140003292  mov     rdx, rdi
0x140003295  mov     rax, [rax+820h]
0x14000329c  call    _guard_dispatch_icall
0x1400032a1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400032a8  xor     r9d, r9d
0x1400032ab  mov     r8, [r14+20h]
0x1400032af  mov     rdx, rdi
0x1400032b2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400032b9  mov     rax, [rax+7E8h]
0x1400032c0  call    _guard_dispatch_icall
0x1400032c5  test    al, al
0x1400032c7  jnz     short loc_14000333D
0x1400032c9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400032d0  mov     rdx, rdi
0x1400032d3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400032da  mov     rax, [rax+7F0h]
0x1400032e1  call    _guard_dispatch_icall
0x1400032e6  mov     ebx, eax
0x1400032e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032ef  lea     rax, WPP_GLOBAL_Control
0x1400032f6  cmp     rcx, rax
0x1400032f9  jz      short loc_140003319
0x1400032fb  cmp     byte ptr [rcx+29h], 5
0x1400032ff  jb      short loc_140003319
0x140003301  mov     rcx, [rcx+18h]
0x140003305  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x14000330c  mov     edx, 19h
0x140003311  mov     r9d, ebx
0x140003314  call    WPP_SF_d
0x140003319  test    ebx, ebx
0x14000331b  jns     short loc_14000333D
0x14000331d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003324  mov     r8d, ebx
0x140003327  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000332e  mov     rdx, rdi
0x140003331  mov     rax, [rax+838h]
0x140003338  call    _guard_dispatch_icall
0x14000333d  mov     rcx, [rbp+57h+var_20]
0x140003341  xor     rcx, rsp; StackCookie
0x140003344  call    __security_check_cookie
0x140003349  lea     r11, [rsp+0D0h+var_10]
0x140003351  mov     rbx, [r11+30h]
0x140003355  mov     rsi, [r11+38h]
0x140003359  mov     rsp, r11
0x14000335c  pop     r14
0x14000335e  pop     rdi
0x14000335f  pop     rbp
0x140003360  retn
```
