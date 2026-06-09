# CUsbFilterControl::AllocateClaimCheckCollectionSnapshot(ulong *,WDFCOLLECTION__ * *)

- ea: `0x140006278`
- end: `0x1400065e1`
- name: `?AllocateClaimCheckCollectionSnapshot@CUsbFilterControl@@QEAAJPEAKPEAPEAUWDFCOLLECTION__@@@Z`
- size: `873`
- prototype: `__int64 __fastcall(CUsbFilterControl *__hidden this, unsigned int *, struct WDFCOLLECTION__ **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003258`

## callees

- `0x140004f48`
- `0x140006278`
- `0x1400065e8`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::AllocateClaimCheckCollectionSnapshot(
        CUsbFilterControl *this,
        unsigned int *a2,
        struct WDFCOLLECTION__ **a3)
{
  void *v3; // rdi
  int v6; // ebx
  unsigned __int64 v7; // rax
  unsigned int v8; // r14d
  unsigned int v9; // r12d
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int128 v14; // [rsp+70h] [rbp-9h] BYREF
  __int64 v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  __int128 v17; // [rsp+90h] [rbp+17h]
  __int64 v18; // [rsp+A0h] [rbp+27h]
  struct WDFCOLLECTION__ *v19; // [rsp+F0h] [rbp+77h] BYREF
  void *v20; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = 0;
  v19 = 0;
  v20 = 0;
  if ( a3 )
  {
    v18 = 0;
    v7 = *(_QWORD *)this;
    v15 = 0;
    v16 = 0x100000001LL;
    v17 = v7;
    v14 = 0;
    LODWORD(v14) = 56;
    v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, struct WDFCOLLECTION__ **))WPP_MAIN_CB.Queue.ListEntry.Flink[6].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           &v14,
           &v19);
    if ( v6 >= 0 )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *(_QWORD *)this);
      v8 = 0;
      v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             *((_QWORD *)this + 2));
      if ( v9 )
      {
        while ( 1 )
        {
          v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  *((_QWORD *)this + 2),
                  v8);
          v11 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  v10,
                  off_14000F0B8);
          v6 = CUsbFilterControl::AllocateDeviceClaimCheckObject(
                 *(CUsbFilterControl **)(v11 + 56),
                 *(struct WDFFILEOBJECT__ **)v11,
                 *(struct _EPROCESS **)(v11 + 8),
                 **(const unsigned __int16 ***)(v11 + 24),
                 *(_QWORD *)(v11 + 32),
                 *(_DWORD *)(v11 + 16),
                 **(const unsigned __int16 ***)(v11 + 48),
                 *(_QWORD *)(v11 + 56),
                 *(_DWORD *)(v11 + 40),
                 **(const unsigned __int16 ***)(v11 + 72),
                 *(_QWORD *)(v11 + 80),
                 *(_DWORD *)(v11 + 64),
                 &v20);
          if ( v6 < 0 )
            break;
          v3 = v20;
          v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFCOLLECTION__ *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Blink)(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 v19,
                 v20);
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0x2Cu,
                (__int64)WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
                v6);
            goto LABEL_12;
          }
          if ( ++v8 >= v9 )
            goto LABEL_11;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x2Bu,
            (__int64)WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
            v6);
        v3 = v20;
      }
      else
      {
LABEL_11:
        v6 = 0;
        *a3 = v19;
        v19 = 0;
      }
LABEL_12:
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *(_QWORD *)this);
      if ( v3 )
        ((void (__fastcall *)(struct _LIST_ENTRY *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v3);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Au,
        (__int64)WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
        v6);
    }
    if ( v19 )
    {
      while ( 1 )
      {
        v12 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Blink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
        if ( !v12 )
          break;
        ((void (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v12);
      }
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFCOLLECTION__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        v19);
    }
  }
  else
  {
    v6 = 0;
    *a2 = *((_DWORD *)this + 6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140006278  mov     [rsp-8+arg_0], rbx
0x14000627d  mov     [rsp-8+arg_8], rsi
0x140006282  push    rbp
0x140006283  push    rdi
0x140006284  push    r12
0x140006286  push    r14
0x140006288  push    r15
0x14000628a  lea     rbp, [rsp-37h]
0x14000628f  sub     rsp, 0B0h
0x140006296  xor     edi, edi
0x140006298  mov     [rbp+57h+arg_10], 0
0x1400062a0  mov     [rbp+57h+arg_18], rdi
0x1400062a4  mov     r15, r8
0x1400062a7  mov     rsi, rcx
0x1400062aa  test    r8, r8
0x1400062ad  jnz     short loc_1400062BB
0x1400062af  mov     eax, [rcx+18h]
0x1400062b2  xor     ebx, ebx
0x1400062b4  mov     [rdx], eax
0x1400062b6  jmp     loc_1400065C2
0x1400062bb  xor     eax, eax
0x1400062bd  lea     r8, [rbp+57h+arg_10]
0x1400062c1  mov     [rbp+57h+var_30], rax
0x1400062c5  lea     rdx, [rbp+57h+var_60]
0x1400062c9  mov     rax, [rcx]
0x1400062cc  xorps   xmm0, xmm0
0x1400062cf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400062d6  movups  [rbp+57h+var_50], xmm0
0x1400062da  mov     dword ptr [rbp+57h+var_50+8], 1
0x1400062e1  movups  [rbp+57h+var_40], xmm0
0x1400062e5  mov     qword ptr [rbp+57h+var_40], rax
0x1400062e9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400062f0  movups  [rbp+57h+var_60], xmm0
0x1400062f4  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x1400062fb  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x140006302  mov     rax, [rax+68h]
0x140006306  call    _guard_dispatch_icall
0x14000630b  mov     ebx, eax
0x14000630d  test    eax, eax
0x14000630f  jns     short loc_14000634F
0x140006311  mov     rcx, cs:WPP_GLOBAL_Control
0x140006318  lea     rax, WPP_GLOBAL_Control
0x14000631f  cmp     rcx, rax
0x140006322  jz      loc_1400064D9
0x140006328  cmp     byte ptr [rcx+29h], 2
0x14000632c  jb      loc_1400064D9
0x140006332  mov     rcx, [rcx+18h]
0x140006336  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x14000633d  mov     edx, 2Ah ; '*'
0x140006342  mov     r9d, ebx
0x140006345  call    WPP_SF_d
0x14000634a  jmp     loc_1400064D9
0x14000634f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006356  mov     rdx, [rsi]
0x140006359  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006360  mov     rax, [rax+9B0h]
0x140006367  call    _guard_dispatch_icall
0x14000636c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006373  mov     rdx, [rsi+10h]
0x140006377  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000637e  mov     rax, [rax+70h]
0x140006382  call    _guard_dispatch_icall
0x140006387  xor     r14d, r14d
0x14000638a  mov     r12d, eax
0x14000638d  test    eax, eax
0x14000638f  jz      loc_140006489
0x140006395  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x14000639c  mov     r8d, r14d
0x14000639f  mov     rdx, [rsi+10h]
0x1400063a3  mov     rax, [rcx+90h]
0x1400063aa  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400063b1  call    _guard_dispatch_icall
0x1400063b6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x1400063bd  mov     rdx, rax
0x1400063c0  mov     r8, cs:off_14000F0B8
0x1400063c7  mov     r9, [rcx+650h]
0x1400063ce  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400063d5  mov     rax, r9
0x1400063d8  call    _guard_dispatch_icall
0x1400063dd  mov     r10, rax
0x1400063e0  lea     rcx, [rbp+57h+arg_18]
0x1400063e4  mov     [rsp+0D0h+var_70], rcx; void **
0x1400063e9  mov     rdx, [rax+48h]
0x1400063ed  mov     rax, [rax+30h]
0x1400063f1  mov     ecx, [r10+40h]
0x1400063f5  mov     r9, [r10+18h]
0x1400063f9  mov     r8, [r10+8]; struct _EPROCESS *
0x1400063fd  mov     rax, [rax]
0x140006400  mov     [rsp+0D0h+var_78], ecx; unsigned int
0x140006404  mov     rcx, [r10+50h]
0x140006408  mov     r9, [r9]; unsigned __int16 *
0x14000640b  mov     [rsp+0D0h+var_80], rcx; unsigned __int64
0x140006410  mov     rcx, [rdx]
0x140006413  mov     rdx, [r10]; struct WDFFILEOBJECT__ *
0x140006416  mov     [rsp+0D0h+var_88], rcx; unsigned __int16 *
0x14000641b  mov     ecx, [r10+28h]
0x14000641f  mov     [rsp+0D0h+var_90], ecx; unsigned int
0x140006423  mov     rcx, [r10+38h]; this
0x140006427  mov     [rsp+0D0h+var_98], rcx; unsigned __int64
0x14000642c  mov     [rsp+0D0h+var_A0], rax; unsigned __int16 *
0x140006431  mov     eax, [r10+10h]
0x140006435  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x140006439  mov     rax, [r10+20h]
0x14000643d  mov     [rsp+0D0h+var_B0], rax; unsigned __int64
0x140006442  call    ?AllocateDeviceClaimCheckObject@CUsbFilterControl@@AEAAJPEAUWDFFILEOBJECT__@@PEAU_EPROCESS@@PEBG_KK23K23KPEAPEAX@Z; CUsbFilterControl::AllocateDeviceClaimCheckObject(WDFFILEOBJECT__ *,_EPROCESS *,ushort const *,unsigned __int64,ulong,ushort const *,unsigned __int64,ulong,ushort const *,unsigned __int64,ulong,void * *)
0x140006447  mov     ebx, eax
0x140006449  test    eax, eax
0x14000644b  js      loc_14000656A
0x140006451  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006458  mov     rdi, [rbp+57h+arg_18]
0x14000645c  mov     rdx, [rbp+57h+arg_10]
0x140006460  mov     r8, rdi
0x140006463  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000646a  mov     rax, [rax+78h]
0x14000646e  call    _guard_dispatch_icall
0x140006473  mov     ebx, eax
0x140006475  test    eax, eax
0x140006477  js      loc_14000652C
0x14000647d  inc     r14d
0x140006480  cmp     r14d, r12d
0x140006483  jb      loc_140006395
0x140006489  mov     rax, [rbp+57h+arg_10]
0x14000648d  xor     ebx, ebx
0x14000648f  mov     [r15], rax
0x140006492  mov     [rbp+57h+arg_10], 0
0x14000649a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400064a1  mov     rdx, [rsi]
0x1400064a4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400064ab  mov     rax, [rax+9B8h]
0x1400064b2  call    _guard_dispatch_icall
0x1400064b7  test    rdi, rdi
0x1400064ba  jz      short loc_1400064D9
0x1400064bc  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400064c3  mov     rdx, rdi
0x1400064c6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400064cd  mov     rax, [rax+680h]
0x1400064d4  call    _guard_dispatch_icall
0x1400064d9  mov     rdx, [rbp+57h+arg_10]
0x1400064dd  test    rdx, rdx
0x1400064e0  jz      loc_1400065C2
0x1400064e6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400064ed  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400064f4  mov     rax, [rax+98h]
0x1400064fb  call    _guard_dispatch_icall
0x140006500  mov     rdx, rax
0x140006503  test    rax, rax
0x140006506  jz      loc_1400065A4
0x14000650c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140006513  mov     rax, [rcx+680h]
0x14000651a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006521  call    _guard_dispatch_icall
0x140006526  mov     rdx, [rbp+57h+arg_10]
0x14000652a  jmp     short loc_1400064E6
0x14000652c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006533  lea     rax, WPP_GLOBAL_Control
0x14000653a  cmp     rcx, rax
0x14000653d  jz      loc_14000649A
0x140006543  cmp     byte ptr [rcx+29h], 2
0x140006547  jb      loc_14000649A
0x14000654d  mov     rcx, [rcx+18h]
0x140006551  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006558  mov     edx, 2Ch ; ','
0x14000655d  mov     r9d, ebx
0x140006560  call    WPP_SF_d
0x140006565  jmp     loc_14000649A
0x14000656a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006571  lea     rax, WPP_GLOBAL_Control
0x140006578  cmp     rcx, rax
0x14000657b  jz      short loc_14000659B
0x14000657d  cmp     byte ptr [rcx+29h], 2
0x140006581  jb      short loc_14000659B
0x140006583  mov     rcx, [rcx+18h]
0x140006587  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x14000658e  mov     edx, 2Bh ; '+'
0x140006593  mov     r9d, ebx
0x140006596  call    WPP_SF_d
0x14000659b  mov     rdi, [rbp+57h+arg_18]
0x14000659f  jmp     loc_14000649A
0x1400065a4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400065ab  mov     rdx, [rbp+57h+arg_10]
0x1400065af  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400065b6  mov     rax, [rax+680h]
0x1400065bd  call    _guard_dispatch_icall
0x1400065c2  lea     r11, [rsp+0D0h+var_20]
0x1400065ca  mov     eax, ebx
0x1400065cc  mov     rbx, [r11+30h]
0x1400065d0  mov     rsi, [r11+38h]
0x1400065d4  mov     rsp, r11
0x1400065d7  pop     r15
0x1400065d9  pop     r14
0x1400065db  pop     r12
0x1400065dd  pop     rdi
0x1400065de  pop     rbp
0x1400065df  retn
```
