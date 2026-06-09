# TdxReceiveConnectionCancelRoutine

- ea: `0x1400139b0`
- end: `0x140013ac6`
- name: `TdxReceiveConnectionCancelRoutine`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140003590`
- `0x1400047d0`
- `0x140008620`
- `0x140008ef0`
- `0x1400139b0`
- `0x140018590`
- `0x140018900`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400139f7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400139f7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400139e9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400139e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013a35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013aa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013a35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013aa7`

## string_xrefs

- `0x140013a83`: `TdxReceiveConnectionTlFlushRequestComplete`

## pseudocode

```c
void __fastcall TdxReceiveConnectionCancelRoutine(__int64 a1, __int64 a2)
{
  KIRQL v2; // si
  __int64 v3; // rbx
  _QWORD v4[10]; // [rsp+20h] [rbp-58h] BYREF

  v2 = *(_BYTE *)(a2 + 69);
  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) + 24LL);
  memset(v4, 0, sizeof(v4));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 8));
  IoReleaseCancelSpinLock(2u);
  if ( (unsigned int)(*(_DWORD *)(v3 + 76) - 3) > 3 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v2);
  }
  else
  {
    DbgTdxReferenceConnection(v3, "TdxReceiveConnectionCancelRoutine", 2700);
    TdxIncrementTlEndpointReference(v3);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 8), v2);
    v4[1] = v3;
    v4[0] = TdxReceiveConnectionTlFlushRequestComplete;
    LODWORD(v4[3]) = 4;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v3 + 264) + 8LL))(*(_QWORD *)(v3 + 288), v4) != 259 )
      DbgTdxDereferenceConnection(v3, (__int64)"TdxReceiveConnectionTlFlushRequestComplete", 2733);
    TdxDecrementTlEndpointReference(v3, 0, 0);
  }
}

```

## disassembly

```asm
0x1400139b0  mov     [rsp+arg_0], rbx
0x1400139b5  mov     [rsp+arg_8], rsi
0x1400139ba  push    rdi
0x1400139bb  sub     rsp, 70h
0x1400139bf  mov     rax, [rdx+0B8h]
0x1400139c6  mov     sil, [rdx+45h]
0x1400139ca  xor     edx, edx; Val
0x1400139cc  mov     rcx, [rax+30h]
0x1400139d0  lea     r8d, [rdx+50h]; Size
0x1400139d4  mov     rbx, [rcx+18h]
0x1400139d8  lea     rcx, [rsp+78h+var_58]; void *
0x1400139dd  call    memset
0x1400139e2  lea     rdi, [rbx+8]
0x1400139e6  mov     rcx, rdi; SpinLock
0x1400139e9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400139f0  nop     dword ptr [rax+rax+00h]
0x1400139f5  mov     cl, 2; Irql
0x1400139f7  call    cs:__imp_IoReleaseCancelSpinLock
0x1400139fe  nop     dword ptr [rax+rax+00h]
0x140013a03  mov     eax, [rbx+4Ch]
0x140013a06  sub     eax, 3
0x140013a09  cmp     eax, 3
0x140013a0c  ja      loc_140013AA1
0x140013a12  mov     r8d, 0A8Ch
0x140013a18  lea     rdx, aTdxreceiveconn_0; "TdxReceiveConnectionCancelRoutine"
0x140013a1f  mov     rcx, rbx
0x140013a22  call    DbgTdxReferenceConnection
0x140013a27  mov     rcx, rbx
0x140013a2a  call    TdxIncrementTlEndpointReference
0x140013a2f  mov     dl, sil; NewIrql
0x140013a32  mov     rcx, rdi; SpinLock
0x140013a35  call    cs:__imp_KeReleaseSpinLock
0x140013a3c  nop     dword ptr [rax+rax+00h]
0x140013a41  mov     [rsp+78h+var_50], rbx
0x140013a46  lea     rax, TdxReceiveConnectionTlFlushRequestComplete
0x140013a4d  mov     [rsp+78h+var_58], rax
0x140013a52  lea     rdx, [rsp+78h+var_58]
0x140013a57  mov     [rsp+78h+var_40], 4
0x140013a5f  mov     rax, [rbx+108h]
0x140013a66  mov     rcx, [rbx+120h]
0x140013a6d  mov     rax, [rax+8]
0x140013a71  call    _guard_dispatch_icall
0x140013a76  cmp     eax, 103h
0x140013a7b  jz      short loc_140013A92
0x140013a7d  mov     r8d, 0AADh
0x140013a83  lea     rdx, aTdxreceiveconn; "TdxReceiveConnectionTlFlushRequestCompl"...
0x140013a8a  mov     rcx, rbx
0x140013a8d  call    DbgTdxDereferenceConnection
0x140013a92  xor     r8d, r8d
0x140013a95  xor     edx, edx
0x140013a97  mov     rcx, rbx
0x140013a9a  call    TdxDecrementTlEndpointReference
0x140013a9f  jmp     short loc_140013AB3
0x140013aa1  mov     dl, sil; NewIrql
0x140013aa4  mov     rcx, rdi; SpinLock
0x140013aa7  call    cs:__imp_KeReleaseSpinLock
0x140013aae  nop     dword ptr [rax+rax+00h]
0x140013ab3  lea     r11, [rsp+78h+var_8]
0x140013ab8  mov     rbx, [r11+10h]
0x140013abc  mov     rsi, [r11+18h]
0x140013ac0  mov     rsp, r11
0x140013ac3  pop     rdi
0x140013ac4  retn
```
