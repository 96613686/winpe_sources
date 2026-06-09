# HUBSM_AddEvent

- ea: `0x14000a53c`
- end: `0x14000aa44`
- name: `HUBSM_AddEvent`
- size: `1288`
- prototype: ``
- caller_count: `125`
- callee_count: `5`
- tags: ``

## callers

- `0x1400048d8`
- `0x14000497c`
- `0x1400050b4`
- `0x140005200`
- `0x140005abc`
- `0x140005dd0`
- `0x1400073f4`
- `0x140007660`
- `0x1400078c8`
- `0x140007b70`
- `0x140007ca0`
- `0x140007e10`
- `0x140008250`
- `0x140008b20`
- `0x140008c60`
- `0x140008df0`
- `0x140008f00`
- `0x1400096d0`
- `0x1400097c0`
- `0x1400098f0`
- `0x140009ae0`
- `0x140009c90`
- `0x14000a3c0`
- `0x14000a450`
- `0x14000a4c0`
- `0x14000a520`
- `0x14000aa4c`
- `0x14000aa70`
- `0x14000ce50`
- `0x14000d120`
- `0x14000d580`
- `0x14000da60`
- `0x1400102e0`
- `0x140010364`
- `0x140010464`
- `0x1400104b0`
- `0x14001111c`
- `0x14001133c`
- `0x140011540`
- `0x14001166c`
- `0x140011858`
- `0x140011968`
- `0x1400119a4`
- `0x140011a4c`
- `0x140011b64`
- `0x140011c00`
- `0x140011c3c`
- `0x140014f80`
- `0x1400153c0`
- `0x140015610`

## callees

- `0x1400067ac`
- `0x14000a53c`
- `0x14000abc0`
- `0x14000bbcc`
- `0x140045570`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000a692`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a692`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a9d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a5b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a766`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a5b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a766`
- `ntoskrnl!KeLowerIrql` at `0x14000a7e5`
- `ntoskrnl!KeLowerIrql` at `0x14000a7e5`
- `ntoskrnl!KfRaiseIrql` at `0x14000a792`
- `ntoskrnl!KfRaiseIrql` at `0x14000a792`

## pseudocode

```c
__int64 __fastcall HUBSM_AddEvent(__int64 a1, int a2)
{
  __int64 v4; // rax
  KIRQL v5; // al
  __int64 v6; // rcx
  KIRQL v7; // si
  unsigned __int8 v8; // cl
  char v9; // r8
  unsigned __int8 v10; // dl
  int v11; // r9d
  __int64 v12; // rax
  char v13; // al
  unsigned __int8 v14; // dl
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  KIRQL v22; // [rsp+58h] [rbp+10h] BYREF

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(
         WdfDriverGlobals,
         *(_QWORD *)(a1 + 960));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1640))(
    WdfDriverGlobals,
    v4,
    "Add Event Tag",
    1136,
    "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\smengine.c");
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 840));
  v6 = *(unsigned __int8 *)(a1 + 833);
  v7 = v5;
  v22 = v5;
  *(_DWORD *)(a1 + 4 * v6 + 768) = a2;
  *(_BYTE *)(a1 + 833) = (*(_BYTE *)(a1 + 833) + 1) & 0xF;
  if ( a2 == 3039 || a2 == 3043 || a2 == 4055 || a2 == 4059 )
  {
    v8 = *(_BYTE *)(a1 + 948);
    v9 = 0;
    v10 = v8;
    if ( v8 == *(_BYTE *)(a1 + 949) )
    {
      *(_BYTE *)(a1 + 949) = v8;
    }
    else
    {
      do
      {
        v11 = *(_DWORD *)(a1 + 4LL * v10 + 884);
        if ( v11 == a2 )
        {
          v9 = 1;
        }
        else
        {
          v12 = v8;
          v8 = (v8 + 1) & 0xF;
          *(_DWORD *)(a1 + 4 * v12 + 884) = v11;
        }
        v13 = *(_BYTE *)(a1 + 949);
        v10 = (v10 + 1) & 0xF;
      }
      while ( v10 != v13 );
      v14 = v8;
      if ( v8 != v13 )
      {
        do
        {
          v15 = v8 & 0xF;
          v8 = (v8 + 1) & 0xF;
          *(_DWORD *)(a1 + 4 * v15 + 884) = 1000;
        }
        while ( v8 != *(_BYTE *)(a1 + 949) );
      }
      *(_BYTE *)(a1 + 949) = v14;
      if ( v9 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 840), v7);
        v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 840));
        v22 = v7;
      }
    }
  }
  if ( *(_BYTE *)(a1 + 1048) )
  {
    if ( a2 == 1002 )
    {
      *(_BYTE *)(a1 + 1048) = 0;
      v16 = HUBSM_ExecuteEntryFunctionsAndPushPopStateMachinesForCurrentState(a1);
      if ( v16 != 1003 )
      {
        v17 = v16;
LABEL_22:
        HUBSM_RunStateMachine(a1, v17, &v22, 0);
        v7 = v22;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 4LL * *(unsigned __int8 *)(a1 + 949) + 884) = a2;
      *(_BYTE *)(a1 + 949) = (*(_BYTE *)(a1 + 949) + 1) & 0xF;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 4LL * *(unsigned __int8 *)(a1 + 949) + 884) = a2;
    *(_BYTE *)(a1 + 949) = (*(_BYTE *)(a1 + 949) + 1) & 0xF;
    if ( !*(_BYTE *)(a1 + 848) )
    {
      v18 = *(_QWORD *)(a1 + 960);
      *(_BYTE *)(a1 + 848) = 1;
      v19 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v18);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015
                                                                                                + 1640))(
        WdfDriverGlobals,
        v19,
        "State Machine Tag",
        1235,
        "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\smengine.c");
      v17 = 1000;
      goto LABEL_22;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 840), v7);
  v20 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1632))(
          WdfDriverGlobals,
          *(_QWORD *)(a1 + 960));
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const char *, __int64, const char *))(WdfFunctions_01015 + 1648))(
           WdfDriverGlobals,
           v20,
           "Add Event Tag",
           1252,
           "onecore\\drivers\\wdm\\usb\\usb3\\hub\\src\\smengine.c");
}

```

## disassembly

```asm
0x14000a53c  mov     [rsp+arg_0], rbx
0x14000a541  mov     [rsp+arg_10], rbp
0x14000a546  push    rsi
0x14000a547  push    r14
0x14000a549  push    r15
0x14000a54b  sub     rsp, 30h
0x14000a54f  mov     rax, cs:WdfFunctions_01015
0x14000a556  mov     ebx, edx
0x14000a558  mov     rdx, [rcx+3C0h]
0x14000a55f  mov     rbp, rcx
0x14000a562  mov     rcx, cs:WdfDriverGlobals
0x14000a569  mov     rax, [rax+660h]
0x14000a570  call    _guard_dispatch_icall
0x14000a575  mov     rdx, cs:WdfFunctions_01015
0x14000a57c  lea     r14, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000a583  mov     rcx, cs:WdfDriverGlobals
0x14000a58a  lea     r8, AddEventTag; "Add Event Tag"
0x14000a591  mov     r9d, 470h
0x14000a597  mov     [rsp+48h+var_28], r14
0x14000a59c  mov     r10, [rdx+668h]
0x14000a5a3  mov     rdx, rax
0x14000a5a6  mov     rax, r10
0x14000a5a9  call    _guard_dispatch_icall
0x14000a5ae  lea     r15, [rbp+348h]
0x14000a5b5  mov     rcx, r15; SpinLock
0x14000a5b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a5bf  nop     dword ptr [rax+rax+00h]
0x14000a5c4  movzx   ecx, byte ptr [rbp+341h]
0x14000a5cb  mov     sil, al
0x14000a5ce  mov     [rsp+48h+arg_8], al
0x14000a5d2  mov     [rbp+rcx*4+300h], ebx
0x14000a5d9  mov     cl, [rbp+341h]
0x14000a5df  inc     cl
0x14000a5e1  and     cl, 0Fh
0x14000a5e4  mov     [rbp+341h], cl
0x14000a5ea  cmp     ebx, 0BDFh
0x14000a5f0  jz      short loc_14000A60E
0x14000a5f2  cmp     ebx, 0BE3h
0x14000a5f8  jz      short loc_14000A60E
0x14000a5fa  cmp     ebx, 0FD7h
0x14000a600  jz      short loc_14000A60E
0x14000a602  cmp     ebx, 0FDBh
0x14000a608  jnz     loc_14000A8DA
0x14000a60e  mov     cl, [rbp+3B4h]
0x14000a614  xor     r8b, r8b
0x14000a617  mov     dl, cl
0x14000a619  cmp     cl, [rbp+3B5h]
0x14000a61f  jz      loc_14000A8D4
0x14000a625  movzx   eax, dl
0x14000a628  mov     r9d, [rbp+rax*4+374h]
0x14000a630  cmp     r9d, ebx
0x14000a633  jz      short loc_14000A647
0x14000a635  movzx   eax, cl
0x14000a638  inc     cl
0x14000a63a  and     cl, 0Fh
0x14000a63d  mov     [rbp+rax*4+374h], r9d
0x14000a645  jmp     short loc_14000A64A
0x14000a647  mov     r8b, 1
0x14000a64a  mov     al, [rbp+3B5h]
0x14000a650  inc     dl
0x14000a652  and     dl, 0Fh
0x14000a655  cmp     dl, al
0x14000a657  jnz     short loc_14000A625
0x14000a659  mov     dl, cl
0x14000a65b  cmp     cl, al
0x14000a65d  jz      short loc_14000A67D
0x14000a65f  movzx   eax, cl
0x14000a662  inc     cl
0x14000a664  and     eax, 0Fh
0x14000a667  and     cl, 0Fh
0x14000a66a  mov     dword ptr [rbp+rax*4+374h], 3E8h
0x14000a675  cmp     cl, [rbp+3B5h]
0x14000a67b  jnz     short loc_14000A65F
0x14000a67d  mov     [rbp+3B5h], dl
0x14000a683  test    r8b, r8b
0x14000a686  jz      loc_14000A8DA
0x14000a68c  mov     dl, sil; NewIrql
0x14000a68f  mov     rcx, r15; SpinLock
0x14000a692  call    cs:__imp_KeReleaseSpinLock
0x14000a699  nop     dword ptr [rax+rax+00h]
0x14000a69e  mov     eax, 0FC7h
0x14000a6a3  cmp     ebx, eax
0x14000a6a5  ja      loc_14000A87E
0x14000a6ab  jz      short loc_14000A6D4
0x14000a6ad  mov     eax, ebx
0x14000a6af  sub     eax, 0BBEh
0x14000a6b4  jz      loc_14000A77E
0x14000a6ba  sub     eax, 3F9h
0x14000a6bf  jz      short loc_14000A6D4
0x14000a6c1  sub     eax, 4
0x14000a6c4  jz      short loc_14000A6D4
0x14000a6c6  sub     eax, 4
0x14000a6c9  jz      short loc_14000A6D4
0x14000a6cb  cmp     eax, 4
0x14000a6ce  jnz     loc_14000A763
0x14000a6d4  mov     rsi, [rbp+3C0h]
0x14000a6db  mov     rax, cs:WdfFunctions_01015
0x14000a6e2  mov     rcx, cs:WdfDriverGlobals
0x14000a6e9  mov     rdx, [rsi+1D0h]
0x14000a6f0  mov     rax, [rax+8E8h]
0x14000a6f7  call    _guard_dispatch_icall
0x14000a6fc  mov     rcx, rax
0x14000a6ff  mov     rax, cs:g_IoGetActivityIdIrp
0x14000a706  test    rax, rax
0x14000a709  jz      short loc_14000A763
0x14000a70b  lea     r14, [rbp+3F4h]
0x14000a712  mov     rdx, r14
0x14000a715  call    _guard_dispatch_icall
0x14000a71a  test    eax, eax
0x14000a71c  js      short loc_14000A75C
0x14000a71e  mov     rax, cs:g_IoSetActivityIdIrp
0x14000a725  test    rax, rax
0x14000a728  jz      short loc_14000A754
0x14000a72a  mov     rcx, [rsi+110h]
0x14000a731  mov     rdx, r14
0x14000a734  call    _guard_dispatch_icall
0x14000a739  mov     rax, cs:g_IoSetActivityIdIrp
0x14000a740  test    rax, rax
0x14000a743  jz      short loc_14000A754
0x14000a745  mov     rcx, [rsi+1B0h]
0x14000a74c  mov     rdx, r14
0x14000a74f  call    _guard_dispatch_icall
0x14000a754  lock or dword ptr [rsi+66Ch], 40h
0x14000a75c  lea     r14, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\usb\\usb3\\hub\\"...
0x14000a763  mov     rcx, r15; SpinLock
0x14000a766  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a76d  nop     dword ptr [rax+rax+00h]
0x14000a772  mov     sil, al
0x14000a775  mov     [rsp+48h+arg_8], al
0x14000a779  jmp     loc_14000A8DA
0x14000a77e  mov     r14, [rbp+3C0h]
0x14000a785  mov     cl, 2; NewIrql
0x14000a787  mov     eax, [r14+538h]
0x14000a78e  test    cl, al
0x14000a790  jnz     short loc_14000A7FE
0x14000a792  call    cs:__imp_KfRaiseIrql
0x14000a799  nop     dword ptr [rax+rax+00h]
0x14000a79e  mov     rcx, cs:WdfFunctions_01015
0x14000a7a5  mov     sil, al
0x14000a7a8  mov     rdx, [r14+530h]
0x14000a7af  mov     rax, [rcx+660h]
0x14000a7b6  mov     rcx, cs:WdfDriverGlobals
0x14000a7bd  call    _guard_dispatch_icall
0x14000a7c2  mov     rcx, cs:WdfFunctions_01015
0x14000a7c9  mov     rdx, rax
0x14000a7cc  mov     r8, [rcx+680h]
0x14000a7d3  mov     rcx, cs:WdfDriverGlobals
0x14000a7da  mov     rax, r8
0x14000a7dd  call    _guard_dispatch_icall
0x14000a7e2  mov     cl, sil; NewIrql
0x14000a7e5  call    cs:__imp_KeLowerIrql
0x14000a7ec  nop     dword ptr [rax+rax+00h]
0x14000a7f1  mov     qword ptr [r14+530h], 0
0x14000a7fc  jmp     short loc_14000A857
0x14000a7fe  mov     rax, [r14+530h]
0x14000a805  test    dword ptr [rax+66Ch], 400h
0x14000a80f  jz      short loc_14000A857
0x14000a811  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000a818  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000a81f  jz      short loc_14000A845
0x14000a821  mov     rcx, [r14+598h]
0x14000a828  lea     rax, WPP_0cc843adf6153b7d46bf14e0910357bd_Traceguids
0x14000a82f  mov     r9d, 0Eh
0x14000a835  mov     [rsp+48h+var_28], rax
0x14000a83a  mov     dl, 4
0x14000a83c  lea     r8d, [r9-9]
0x14000a840  call    WPP_RECORDER_SF_
0x14000a845  mov     rax, [r14+530h]
0x14000a84c  lock and dword ptr [rax+66Ch], 0FFFFFBFFh
0x14000a857  lock and dword ptr [r14+538h], 0FFFFFFFEh
0x14000a860  cmp     dword ptr [r14+590h], 4
0x14000a868  jz      loc_14000A75C
0x14000a86e  mov     dword ptr [r14+590h], 0
0x14000a879  jmp     loc_14000A75C
0x14000a87e  mov     eax, ebx
0x14000a880  sub     eax, 0FCBh
0x14000a885  jz      loc_14000A6D4
0x14000a88b  sub     eax, 4
0x14000a88e  jz      loc_14000A6D4
0x14000a894  sub     eax, 14h
0x14000a897  jz      short loc_14000A8A7
0x14000a899  sub     eax, 4
0x14000a89c  jz      short loc_14000A8A7
0x14000a89e  cmp     eax, 1Ch
0x14000a8a1  jnz     loc_14000A763
0x14000a8a7  mov     rsi, [rbp+3C0h]
0x14000a8ae  mov     eax, [rsi+66Ch]
0x14000a8b4  test    al, al
0x14000a8b6  jns     loc_14000A763
0x14000a8bc  movups  xmm0, xmmword ptr [rsi+888h]
0x14000a8c3  lea     r14, [rbp+3F4h]
0x14000a8ca  movdqu  xmmword ptr [r14], xmm0
0x14000a8cf  jmp     loc_14000A71E
0x14000a8d4  mov     [rbp+3B5h], cl
0x14000a8da  cmp     byte ptr [rbp+418h], 0
0x14000a8e1  jz      short loc_14000A92F
0x14000a8e3  cmp     ebx, 3EAh
0x14000a8e9  jnz     short loc_14000A90C
0x14000a8eb  mov     rcx, rbp
0x14000a8ee  mov     byte ptr [rbp+418h], 0
0x14000a8f5  call    HUBSM_ExecuteEntryFunctionsAndPushPopStateMachinesForCurrentState
0x14000a8fa  cmp     eax, 3EBh
0x14000a8ff  jz      loc_14000A9CA
0x14000a905  mov     edx, eax
0x14000a907  jmp     loc_14000A9B5
0x14000a90c  movzx   eax, byte ptr [rbp+3B5h]
0x14000a913  mov     [rbp+rax*4+374h], ebx
0x14000a91a  mov     al, [rbp+3B5h]
0x14000a920  inc     al
0x14000a922  and     al, 0Fh
0x14000a924  mov     [rbp+3B5h], al
0x14000a92a  jmp     loc_14000A9CA
0x14000a92f  movzx   eax, byte ptr [rbp+3B5h]
0x14000a936  mov     [rbp+rax*4+374h], ebx
0x14000a93d  mov     al, [rbp+3B5h]
0x14000a943  inc     al
0x14000a945  and     al, 0Fh
0x14000a947  mov     [rbp+3B5h], al
0x14000a94d  cmp     byte ptr [rbp+350h], 0
0x14000a954  jnz     short loc_14000A9CA
0x14000a956  mov     rdx, [rbp+3C0h]
0x14000a95d  mov     byte ptr [rbp+350h], 1
0x14000a964  mov     rax, cs:WdfFunctions_01015
0x14000a96b  mov     rcx, cs:WdfDriverGlobals
0x14000a972  mov     rax, [rax+660h]
0x14000a979  call    _guard_dispatch_icall
0x14000a97e  mov     rcx, cs:WdfFunctions_01015
0x14000a985  lea     r8, StateMachineTag; "State Machine Tag"
0x14000a98c  mov     rdx, rax
0x14000a98f  mov     [rsp+48h+var_28], r14
0x14000a994  mov     r9d, 4D3h
0x14000a99a  mov     r10, [rcx+668h]
0x14000a9a1  mov     rcx, cs:WdfDriverGlobals
0x14000a9a8  mov     rax, r10
0x14000a9ab  call    _guard_dispatch_icall
0x14000a9b0  mov     edx, 3E8h
0x14000a9b5  xor     r9d, r9d
0x14000a9b8  lea     r8, [rsp+48h+arg_8]
0x14000a9bd  mov     rcx, rbp
0x14000a9c0  call    HUBSM_RunStateMachine
0x14000a9c5  mov     sil, [rsp+48h+arg_8]
0x14000a9ca  mov     dl, sil; NewIrql
0x14000a9cd  mov     rcx, r15; SpinLock
0x14000a9d0  call    cs:__imp_KeReleaseSpinLock
0x14000a9d7  nop     dword ptr [rax+rax+00h]
0x14000a9dc  mov     rax, cs:WdfFunctions_01015
0x14000a9e3  mov     rdx, [rbp+3C0h]
0x14000a9ea  mov     rcx, cs:WdfDriverGlobals
0x14000a9f1  mov     rax, [rax+660h]
0x14000a9f8  call    _guard_dispatch_icall
0x14000a9fd  mov     rcx, cs:WdfFunctions_01015
0x14000aa04  lea     r8, AddEventTag; "Add Event Tag"
0x14000aa0b  mov     rdx, rax
0x14000aa0e  mov     [rsp+48h+var_28], r14
0x14000aa13  mov     r9d, 4E4h
0x14000aa19  mov     r10, [rcx+670h]
0x14000aa20  mov     rcx, cs:WdfDriverGlobals
0x14000aa27  mov     rax, r10
0x14000aa2a  call    _guard_dispatch_icall
0x14000aa2f  mov     rbx, [rsp+48h+arg_0]
0x14000aa34  mov     rbp, [rsp+48h+arg_10]
0x14000aa39  add     rsp, 30h
0x14000aa3d  pop     r15
0x14000aa3f  pop     r14
0x14000aa41  pop     rsi
0x14000aa42  retn
```
