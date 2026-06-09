# TdxIncrementTlEndpointReference

- ea: `0x140008ef0`
- end: `0x140009002`
- name: `TdxIncrementTlEndpointReference`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140005688`
- `0x140005b00`
- `0x140006db0`
- `0x140009ad0`
- `0x14000aad0`
- `0x140010100`
- `0x140013460`
- `0x140013760`
- `0x1400139b0`

## callees

- `0x140008ef0`
- `0x140013af4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008f0b`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008f68`
- `ntoskrnl!RtlGetCallersAddress` at `0x140008f68`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f90`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008f90`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall TdxIncrementTlEndpointReference(__int64 a1)
{
  KIRQL v2; // al
  int v3; // edx
  __int64 v4; // r14
  KIRQL v5; // di
  __int64 v6; // rdx
  __int64 v7; // r8
  PDEVICE_OBJECT *result; // rax
  int v9; // [rsp+20h] [rbp-58h]
  int v10; // [rsp+38h] [rbp-40h]
  PVOID CallersAddress; // [rsp+80h] [rbp+8h] BYREF

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 72));
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  v3 = *(_DWORD *)(a1 + 16) + 1;
  v4 = a1 + 32LL * *(unsigned int *)(a1 + 632);
  CallersAddress = 0;
  v5 = v2;
  *(_DWORD *)(v4 + 400) = v3;
  *(_QWORD *)(v4 + 376) = "TdxIncrementTlEndpointReference";
  *(_DWORD *)(v4 + 384) = 332;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v4 + 392));
  *(_DWORD *)(a1 + 632) = ((unsigned __int8)*(_DWORD *)(a1 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 368), v5);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v10 = 332;
    v9 = *(_DWORD *)(v4 + 400);
    result = (PDEVICE_OBJECT *)WPP_SF_qdssD(
                                 (__int64)WPP_GLOBAL_Control->AttachedDevice,
                                 v6,
                                 v7,
                                 a1,
                                 v9,
                                 "++",
                                 "TdxIncrementTlEndpointReference",
                                 v10);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x140008ef0  push    rbx
0x140008ef2  push    rbp
0x140008ef3  push    rsi
0x140008ef4  push    rdi
0x140008ef5  push    r14
0x140008ef7  push    r15
0x140008ef9  sub     rsp, 48h
0x140008efd  mov     rbp, rcx
0x140008f00  lock inc dword ptr [rcx+48h]
0x140008f04  add     rcx, 170h; SpinLock
0x140008f0b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008f12  nop     dword ptr [rax+rax+00h]
0x140008f17  mov     edx, [rbp+10h]
0x140008f1a  lea     r15, aTdxincrementtl; "TdxIncrementTlEndpointReference"
0x140008f21  mov     r14d, [rbp+278h]
0x140008f28  lea     rcx, [rsp+78h+CallersAddress]; CallersAddress
0x140008f30  inc     edx
0x140008f32  shl     r14, 5
0x140008f36  add     r14, rbp
0x140008f39  mov     [rsp+78h+CallersAddress], 0
0x140008f45  movzx   edi, al
0x140008f48  mov     [r14+190h], edx
0x140008f4f  lea     rdx, [r14+188h]; CallersCaller
0x140008f56  mov     [r14+178h], r15
0x140008f5d  mov     dword ptr [r14+180h], 14Ch
0x140008f68  call    cs:__imp_RtlGetCallersAddress
0x140008f6f  nop     dword ptr [rax+rax+00h]
0x140008f74  mov     eax, [rbp+278h]
0x140008f7a  lea     rcx, [rbp+170h]; SpinLock
0x140008f81  inc     eax
0x140008f83  movzx   edx, dil; NewIrql
0x140008f87  and     eax, 7
0x140008f8a  mov     [rbp+278h], eax
0x140008f90  call    cs:__imp_KeReleaseSpinLock
0x140008f97  nop     dword ptr [rax+rax+00h]
0x140008f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fa3  lea     rax, WPP_GLOBAL_Control
0x140008faa  cmp     rcx, rax
0x140008fad  jz      short loc_140008FB5
0x140008faf  cmp     byte ptr [rcx+29h], 5
0x140008fb3  jnb     short loc_140008FC7
0x140008fb5  lock inc dword ptr [rbp+10h]
0x140008fb9  add     rsp, 48h
0x140008fbd  pop     r15
0x140008fbf  pop     r14
0x140008fc1  pop     rdi
0x140008fc2  pop     rsi
0x140008fc3  pop     rbp
0x140008fc4  pop     rbx
0x140008fc5  retn
0x140008fc7  test    dword ptr [rcx+2Ch], 200h
0x140008fce  jz      short loc_140008FB5
0x140008fd0  mov     rcx, [rcx+18h]
0x140008fd4  lea     rax, asc_14001A510; "++"
0x140008fdb  mov     [rsp+78h+var_40], 14Ch
0x140008fe3  mov     r9, rbp
0x140008fe6  mov     [rsp+78h+var_48], r15
0x140008feb  mov     [rsp+78h+var_50], rax
0x140008ff0  mov     eax, [r14+190h]
0x140008ff7  mov     [rsp+78h+var_58], eax
0x140008ffb  call    WPP_SF_qdssD
0x140009000  jmp     short loc_140008FB5
```
