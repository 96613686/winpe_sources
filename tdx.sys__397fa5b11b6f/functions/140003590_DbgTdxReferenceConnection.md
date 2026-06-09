# DbgTdxReferenceConnection

- ea: `0x140003590`
- end: `0x1400036a8`
- name: `DbgTdxReferenceConnection`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010b0`
- `0x1400012b0`
- `0x140001550`
- `0x1400023b0`
- `0x140002920`
- `0x140002ccc`
- `0x140002fb0`
- `0x140003c9c`
- `0x1400043b0`
- `0x140004df4`
- `0x140005688`
- `0x140005b00`
- `0x14000aad0`
- `0x140010100`
- `0x140013460`
- `0x1400135ec`
- `0x140013760`
- `0x1400139b0`
- `0x140015c20`

## callees

- `0x140003590`
- `0x140013af4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035b6`
- `ntoskrnl!RtlGetCallersAddress` at `0x140003604`
- `ntoskrnl!RtlGetCallersAddress` at `0x140003604`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000362c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000362c`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall DbgTdxReferenceConnection(__int64 a1, __int64 a2, int a3)
{
  KIRQL v6; // di
  int v7; // r9d
  __int64 v8; // r14
  int v9; // edx
  int v10; // r8d
  PDEVICE_OBJECT *result; // rax
  PVOID CallersAddress; // [rsp+70h] [rbp+8h] BYREF

  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 368));
  v7 = *(_DWORD *)(a1 + 16) + 1;
  v8 = a1 + 32LL * *(unsigned int *)(a1 + 632);
  CallersAddress = 0;
  *(_DWORD *)(v8 + 400) = v7;
  *(_QWORD *)(v8 + 376) = a2;
  *(_DWORD *)(v8 + 384) = a3;
  RtlGetCallersAddress(&CallersAddress, (PVOID *)(v8 + 392));
  *(_DWORD *)(a1 + 632) = ((unsigned __int8)*(_DWORD *)(a1 + 632) + 1) & 7;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 368), v6);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    result = (PDEVICE_OBJECT *)WPP_SF_qdssD(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 v9,
                                 v10,
                                 a1,
                                 *(_DWORD *)(v8 + 400),
                                 (__int64)"++",
                                 a2,
                                 a3);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x140003590  mov     [rsp+arg_8], rbx
0x140003595  mov     [rsp+arg_10], rbp
0x14000359a  push    rsi
0x14000359b  push    rdi
0x14000359c  push    r12
0x14000359e  push    r14
0x1400035a0  push    r15
0x1400035a2  sub     rsp, 40h
0x1400035a6  mov     rbp, rcx
0x1400035a9  mov     r15d, r8d
0x1400035ac  add     rcx, 170h; SpinLock
0x1400035b3  mov     r12, rdx
0x1400035b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400035bd  nop     dword ptr [rax+rax+00h]
0x1400035c2  mov     r14d, [rbp+278h]
0x1400035c9  lea     rcx, [rsp+68h+CallersAddress]; CallersAddress
0x1400035ce  mov     r9d, [rbp+10h]
0x1400035d2  movzx   edi, al
0x1400035d5  inc     r9d
0x1400035d8  shl     r14, 5
0x1400035dc  add     r14, rbp
0x1400035df  mov     [rsp+68h+CallersAddress], 0
0x1400035e8  lea     rdx, [r14+188h]; CallersCaller
0x1400035ef  mov     [r14+190h], r9d
0x1400035f6  mov     [r14+178h], r12
0x1400035fd  mov     [r14+180h], r15d
0x140003604  call    cs:__imp_RtlGetCallersAddress
0x14000360b  nop     dword ptr [rax+rax+00h]
0x140003610  mov     eax, [rbp+278h]
0x140003616  lea     rcx, [rbp+170h]; SpinLock
0x14000361d  inc     eax
0x14000361f  movzx   edx, dil; NewIrql
0x140003623  and     eax, 7
0x140003626  mov     [rbp+278h], eax
0x14000362c  call    cs:__imp_KeReleaseSpinLock
0x140003633  nop     dword ptr [rax+rax+00h]
0x140003638  mov     rcx, cs:WPP_GLOBAL_Control
0x14000363f  lea     rax, WPP_GLOBAL_Control
0x140003646  cmp     rcx, rax
0x140003649  jz      short loc_140003651
0x14000364b  cmp     byte ptr [rcx+29h], 5
0x14000364f  jnb     short loc_140003670
0x140003651  lock inc dword ptr [rbp+10h]
0x140003655  mov     rbx, [rsp+68h+arg_8]
0x14000365a  mov     rbp, [rsp+68h+arg_10]
0x140003662  add     rsp, 40h
0x140003666  pop     r15
0x140003668  pop     r14
0x14000366a  pop     r12
0x14000366c  pop     rdi
0x14000366d  pop     rsi
0x14000366e  retn
0x140003670  test    dword ptr [rcx+2Ch], 200h
0x140003677  jz      short loc_140003651
0x140003679  mov     rcx, [rcx+18h]
0x14000367d  lea     rax, asc_14001A510; "++"
0x140003684  mov     [rsp+68h+var_30], r15d
0x140003689  mov     r9, rbp
0x14000368c  mov     [rsp+68h+var_38], r12
0x140003691  mov     [rsp+68h+var_40], rax
0x140003696  mov     eax, [r14+190h]
0x14000369d  mov     [rsp+68h+var_48], eax
0x1400036a1  call    WPP_SF_qdssD
0x1400036a6  jmp     short loc_140003651
```
