# OncRpcWiMgrpWorker

- ea: `0x14000f490`
- end: `0x14000f6f5`
- name: `OncRpcWiMgrpWorker`
- size: `613`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140005830`
- `0x14000d04c`
- `0x14000f490`
- `0x140015680`
- `0x1400202b0`
- `0x1400203a4`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14000f626`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000f626`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14000f4f7`
- `ntoskrnl!KeSetBasePriorityThread` at `0x14000f4f7`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14000f505`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14000f505`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14000f52f`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14000f52f`
- `ntoskrnl!KeQueryGroupAffinity` at `0x14000f548`
- `ntoskrnl!KeQueryGroupAffinity` at `0x14000f548`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000f560`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000f560`
- `ntoskrnl!KeRemoveQueue` at `0x14000f5bc`
- `ntoskrnl!KeRemoveQueue` at `0x14000f5bc`
- `ntoskrnl!KeSetIdealProcessorThread` at `0x14000f58e`
- `ntoskrnl!KeSetIdealProcessorThread` at `0x14000f58e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4de`
- `ntoskrnl!ExAllocatePool2` at `0x14000f653`
- `ntoskrnl!ExAllocatePool2` at `0x14000f653`

## pseudocode

```c
void __fastcall __noreturn OncRpcWiMgrpWorker(_DWORD *StartContext)
{
  __int64 v1; // rbx
  bool v2; // di
  bool v3; // si
  union _LARGE_INTEGER *v4; // rbp
  PLIST_ENTRY v5; // rax
  PLIST_ENTRY v6; // rdi
  _DWORD *Pool2; // rax
  unsigned int v8; // ecx
  _PROCESSOR_NUMBER ProcNumber; // [rsp+40h] [rbp-48h] BYREF
  _GROUP_AFFINITY Affinity; // [rsp+48h] [rbp-40h] BYREF

  v1 = *(_QWORD *)StartContext;
  v2 = (StartContext[2] & 2) != 0;
  ProcNumber = 0;
  Affinity = 0;
  v3 = 0;
  ExFreePoolWithTag(StartContext, 0x52505452u);
  KeSetBasePriorityThread(KeGetCurrentThread(), 4);
  IoSetThreadHardErrorMode(0);
  if ( (*(_DWORD *)(*((_QWORD *)DeviceExtension + 29) + 120LL) & 1) != 0
    && KeGetProcessorNumberFromIndex(*(_DWORD *)(v1 + 112), &ProcNumber) >= 0 )
  {
    Affinity.Group = ProcNumber.Group;
    Affinity.Mask = KeQueryGroupAffinity(ProcNumber.Group);
    KeSetSystemGroupAffinityThread(&Affinity, 0);
    if ( (*(_DWORD *)(*((_QWORD *)DeviceExtension + 29) + 120LL) & 2) == 0 )
      KeSetIdealProcessorThread(KeGetCurrentThread(), ProcNumber.Number);
  }
  v4 = (union _LARGE_INTEGER *)((v1 + 120) & -(__int64)v2);
  while ( 1 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v1 + 108), 1u);
    v5 = KeRemoveQueue((PRKQUEUE)(v1 + 32), 0, v4);
    _InterlockedDecrement((volatile signed __int32 *)(v1 + 108));
    v6 = v5;
    if ( v5 == (PLIST_ENTRY)258 )
    {
      if ( v3 && qword_14001A490 )
        qword_14001A490();
      _InterlockedDecrement((volatile signed __int32 *)(v1 + 104));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids,
          *(unsigned int *)(v1 + 112),
          *(_DWORD *)(v1 + 104));
      }
      PsTerminateSystemThread(0);
    }
    _InterlockedDecrement((volatile signed __int32 *)(v1 + 128));
    if ( (unsigned __int8)OncRpcWiMgrpCheckSpinUp(v6) )
    {
      Pool2 = (_DWORD *)ExAllocatePool2(64, 16, 1380996178);
      if ( Pool2 )
      {
        v8 = Pool2[2] & 0xFFFFFFFE;
        *(_QWORD *)Pool2 = v1;
        Pool2[2] = v8 | 2;
        OncRpcWiMgrpWorkerThreadCreate(Pool2);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        WPP_SF_dddd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids,
          *(unsigned int *)(v1 + 112),
          *(_DWORD *)(v1 + 104),
          *(_DWORD *)(v1 + 108),
          *(_DWORD *)(v1 + 128));
      }
    }
    LODWORD(v6[2].Blink) &= ~4u;
    if ( !v3 )
    {
      if ( qword_14001A488 )
        v3 = (int)qword_14001A488() >= 0;
    }
    ((void (__fastcall *)(struct _LIST_ENTRY *))v6[1].Blink)(v6[2].Flink);
  }
}

```

## disassembly

```asm
0x14000f490  mov     [rsp+arg_8], rbx
0x14000f495  mov     [rsp+arg_10], rbp
0x14000f49a  push    rsi
0x14000f49b  push    rdi
0x14000f49c  push    r12
0x14000f49e  push    r14
0x14000f4a0  push    r15
0x14000f4a2  sub     rsp, 60h
0x14000f4a6  mov     rax, cs:__security_cookie
0x14000f4ad  xor     rax, rsp
0x14000f4b0  mov     [rsp+88h+var_30], rax
0x14000f4b5  mov     edi, [rcx+8]
0x14000f4b8  xorps   xmm0, xmm0
0x14000f4bb  mov     rbx, [rcx]
0x14000f4be  mov     r15d, 1
0x14000f4c4  shr     edi, 1
0x14000f4c6  mov     edx, 52505452h; Tag
0x14000f4cb  and     dil, r15b
0x14000f4ce  mov     dword ptr [rsp+88h+ProcNumber.Group], 0
0x14000f4d6  movups  xmmword ptr [rsp+88h+Affinity.Mask], xmm0
0x14000f4db  xor     sil, sil
0x14000f4de  call    cs:__imp_ExFreePoolWithTag
0x14000f4e5  nop     dword ptr [rax+rax+00h]
0x14000f4ea  mov     rcx, gs:188h; Thread
0x14000f4f3  lea     edx, [r15+3]; Increment
0x14000f4f7  call    cs:__imp_KeSetBasePriorityThread
0x14000f4fe  nop     dword ptr [rax+rax+00h]
0x14000f503  xor     ecx, ecx; EnableHardErrors
0x14000f505  call    cs:__imp_IoSetThreadHardErrorMode
0x14000f50c  nop     dword ptr [rax+rax+00h]
0x14000f511  mov     rax, cs:DeviceExtension
0x14000f518  mov     rcx, [rax+0E8h]
0x14000f51f  mov     eax, [rcx+78h]
0x14000f522  test    r15b, al
0x14000f525  jz      short loc_14000F59A
0x14000f527  mov     ecx, [rbx+70h]; ProcIndex
0x14000f52a  lea     rdx, [rsp+88h+ProcNumber]; ProcNumber
0x14000f52f  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14000f536  nop     dword ptr [rax+rax+00h]
0x14000f53b  test    eax, eax
0x14000f53d  js      short loc_14000F59A
0x14000f53f  mov     ecx, dword ptr [rsp+88h+ProcNumber.Group]; GroupNumber
0x14000f543  mov     [rsp+88h+Affinity.Group], cx
0x14000f548  call    cs:__imp_KeQueryGroupAffinity
0x14000f54f  nop     dword ptr [rax+rax+00h]
0x14000f554  xor     edx, edx; PreviousAffinity
0x14000f556  lea     rcx, [rsp+88h+Affinity]; Affinity
0x14000f55b  mov     [rsp+88h+Affinity.Mask], rax
0x14000f560  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14000f567  nop     dword ptr [rax+rax+00h]
0x14000f56c  mov     rax, cs:DeviceExtension
0x14000f573  mov     rcx, [rax+0E8h]
0x14000f57a  mov     eax, [rcx+78h]
0x14000f57d  test    al, 2
0x14000f57f  jnz     short loc_14000F59A
0x14000f581  mov     rcx, gs:188h; Thread
0x14000f58a  mov     dl, [rsp+88h+ProcNumber.Number]; Processor
0x14000f58e  call    cs:__imp_KeSetIdealProcessorThread
0x14000f595  nop     dword ptr [rax+rax+00h]
0x14000f59a  neg     dil
0x14000f59d  lea     rax, [rbx+78h]
0x14000f5a1  lea     r12, WPP_GLOBAL_Control
0x14000f5a8  sbb     rbp, rbp
0x14000f5ab  and     rbp, rax
0x14000f5ae  lock add [rbx+6Ch], r15d
0x14000f5b3  mov     r8, rbp; Timeout
0x14000f5b6  lea     rcx, [rbx+20h]; Queue
0x14000f5ba  xor     edx, edx; WaitMode
0x14000f5bc  call    cs:__imp_KeRemoveQueue
0x14000f5c3  nop     dword ptr [rax+rax+00h]
0x14000f5c8  lock dec dword ptr [rbx+6Ch]
0x14000f5cc  mov     rdi, rax
0x14000f5cf  cmp     rax, 102h
0x14000f5d5  jnz     short loc_14000F632
0x14000f5d7  test    sil, sil
0x14000f5da  jz      short loc_14000F5ED
0x14000f5dc  mov     rax, cs:qword_14001A490
0x14000f5e3  test    rax, rax
0x14000f5e6  jz      short loc_14000F5ED
0x14000f5e8  call    _guard_dispatch_icall
0x14000f5ed  lock dec dword ptr [rbx+68h]
0x14000f5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5f8  cmp     rcx, r12
0x14000f5fb  jz      short loc_14000F624
0x14000f5fd  mov     eax, [rcx+2Ch]
0x14000f600  test    al, al
0x14000f602  jns     short loc_14000F624
0x14000f604  mov     eax, [rbx+68h]
0x14000f607  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x14000f60e  mov     r9d, [rbx+70h]
0x14000f612  mov     edx, 0Eh
0x14000f617  mov     rcx, [rcx+18h]
0x14000f61b  mov     [rsp+88h+var_68], eax
0x14000f61f  call    WPP_SF_Dd
0x14000f624  xor     ecx, ecx; ExitStatus
0x14000f626  call    cs:__imp_PsTerminateSystemThread
0x14000f62d  nop     dword ptr [rax+rax+00h]
0x14000f632  lock dec dword ptr [rbx+80h]
0x14000f639  mov     rcx, rdi
0x14000f63c  call    OncRpcWiMgrpCheckSpinUp
0x14000f641  test    al, al
0x14000f643  jz      short loc_14000F6BF
0x14000f645  mov     edx, 10h
0x14000f64a  mov     r8d, 52505452h
0x14000f650  lea     ecx, [rdx+30h]
0x14000f653  call    cs:__imp_ExAllocatePool2
0x14000f65a  nop     dword ptr [rax+rax+00h]
0x14000f65f  test    rax, rax
0x14000f662  jz      short loc_14000F67B
0x14000f664  mov     ecx, [rax+8]
0x14000f667  and     ecx, 0FFFFFFFEh
0x14000f66a  mov     [rax], rbx
0x14000f66d  or      ecx, 2
0x14000f670  mov     [rax+8], ecx
0x14000f673  mov     rcx, rax; P
0x14000f676  call    OncRpcWiMgrpWorkerThreadCreate
0x14000f67b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f682  cmp     rcx, r12
0x14000f685  jz      short loc_14000F6BF
0x14000f687  mov     eax, [rcx+2Ch]
0x14000f68a  test    al, al
0x14000f68c  jns     short loc_14000F6BF
0x14000f68e  mov     eax, [rbx+80h]
0x14000f694  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x14000f69b  mov     r9d, [rbx+70h]
0x14000f69f  mov     edx, 0Fh
0x14000f6a4  mov     rcx, [rcx+18h]
0x14000f6a8  mov     [rsp+88h+var_58], eax
0x14000f6ac  mov     eax, [rbx+6Ch]
0x14000f6af  mov     [rsp+88h+var_60], eax
0x14000f6b3  mov     eax, [rbx+68h]
0x14000f6b6  mov     [rsp+88h+var_68], eax
0x14000f6ba  call    WPP_SF_dddd
0x14000f6bf  and     dword ptr [rdi+28h], 0FFFFFFFBh
0x14000f6c3  test    sil, sil
0x14000f6c6  jnz     short loc_14000F6E3
0x14000f6c8  mov     rax, cs:qword_14001A488
0x14000f6cf  test    rax, rax
0x14000f6d2  jz      short loc_14000F6E3
0x14000f6d4  call    _guard_dispatch_icall
0x14000f6d9  test    eax, eax
0x14000f6db  movzx   esi, sil
0x14000f6df  cmovns  esi, r15d
0x14000f6e3  mov     rax, [rdi+18h]
0x14000f6e7  mov     rcx, [rdi+20h]
0x14000f6eb  call    _guard_dispatch_icall
0x14000f6f0  jmp     loc_14000F5AE
```
