# ChildReleaseInterruptResources

- ea: `0x140014680`
- end: `0x14001477b`
- name: `ChildReleaseInterruptResources`
- size: `251`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400027b0`
- `0x140012a30`
- `0x1400139a8`
- `0x140014680`
- `0x140017000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014759`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014759`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400146eb`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400146eb`
- `ntoskrnl!KfRaiseIrql` at `0x1400146f9`
- `ntoskrnl!KfRaiseIrql` at `0x1400146f9`
- `ntoskrnl!KeLowerIrql` at `0x14001470e`
- `ntoskrnl!KeLowerIrql` at `0x14001470e`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14001473d`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14001473d`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001471e`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001471e`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400146b7`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400146b7`

## pseudocode

```c
void __fastcall ChildReleaseInterruptResources(_DWORD *P)
{
  ULONG v2; // ecx
  KIRQL v3; // bl
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-30h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-20h] BYREF

  v2 = P[25];
  ProcNumber = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  if ( KeGetProcessorNumberFromIndex(v2, &ProcNumber) >= 0 )
  {
    *(_QWORD *)&Affinity.Group = ProcNumber.Group;
    Affinity.Mask = 1LL << ProcNumber.Number;
    KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
    v3 = KfRaiseIrql(2u);
    PncScanEventFlags();
    KeLowerIrql(v3);
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  }
  if ( *((_WORD *)P + 52) )
  {
    FreeEventFlag(*((unsigned __int16 *)P + 52));
    *((_WORD *)P + 52) = 0;
  }
  KeFlushQueuedDpcs();
  XPartDeref(*(_QWORD *)P);
  ExFreePoolWithTag(P, 0x73756256u);
}

```

## disassembly

```asm
0x140014680  push    rbp
0x140014682  push    rbx
0x140014683  push    rsi
0x140014684  push    rdi
0x140014685  mov     rbp, rsp
0x140014688  sub     rsp, 58h
0x14001468c  mov     rax, cs:__security_cookie
0x140014693  xor     rax, rsp
0x140014696  mov     [rbp+var_10], rax
0x14001469a  mov     rdi, rcx
0x14001469d  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x1400146a1  mov     ecx, [rcx+64h]; ProcIndex
0x1400146a4  xorps   xmm0, xmm0
0x1400146a7  xorps   xmm1, xmm1
0x1400146aa  xor     esi, esi
0x1400146ac  mov     dword ptr [rbp+ProcNumber.Group], esi
0x1400146af  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x1400146b3  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x1400146b7  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400146be  nop     dword ptr [rax+rax+00h]
0x1400146c3  test    eax, eax
0x1400146c5  js      short loc_14001472A
0x1400146c7  movzx   eax, [rbp+ProcNumber.Group]
0x1400146cb  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x1400146cf  mov     cl, [rbp+ProcNumber.Number]
0x1400146d2  xorps   xmm0, xmm0
0x1400146d5  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x1400146d9  mov     [rbp+Affinity.Group], ax
0x1400146dd  lea     eax, [rsi+1]
0x1400146e0  shl     rax, cl
0x1400146e3  lea     rcx, [rbp+Affinity]; Affinity
0x1400146e7  mov     [rbp+Affinity.Mask], rax
0x1400146eb  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1400146f2  nop     dword ptr [rax+rax+00h]
0x1400146f7  mov     cl, 2; NewIrql
0x1400146f9  call    cs:__imp_KfRaiseIrql
0x140014700  nop     dword ptr [rax+rax+00h]
0x140014705  mov     bl, al
0x140014707  call    PncScanEventFlags
0x14001470c  mov     cl, bl; NewIrql
0x14001470e  call    cs:__imp_KeLowerIrql
0x140014715  nop     dword ptr [rax+rax+00h]
0x14001471a  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001471e  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140014725  nop     dword ptr [rax+rax+00h]
0x14001472a  cmp     [rdi+68h], si
0x14001472e  jz      short loc_14001473D
0x140014730  movzx   ecx, word ptr [rdi+68h]
0x140014734  call    FreeEventFlag
0x140014739  mov     [rdi+68h], si
0x14001473d  call    cs:__imp_KeFlushQueuedDpcs
0x140014744  nop     dword ptr [rax+rax+00h]
0x140014749  mov     rcx, [rdi]
0x14001474c  call    XPartDeref
0x140014751  mov     edx, 73756256h; Tag
0x140014756  mov     rcx, rdi; P
0x140014759  call    cs:__imp_ExFreePoolWithTag
0x140014760  nop     dword ptr [rax+rax+00h]
0x140014765  mov     rcx, [rbp+var_10]
0x140014769  xor     rcx, rsp; StackCookie
0x14001476c  call    __security_check_cookie
0x140014771  add     rsp, 58h
0x140014775  pop     rdi
0x140014776  pop     rsi
0x140014777  pop     rbx
0x140014778  pop     rbp
0x140014779  retn
```
