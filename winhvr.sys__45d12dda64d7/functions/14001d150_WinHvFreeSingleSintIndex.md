# WinHvFreeSingleSintIndex

- ea: `0x14001d150`
- end: `0x14001d20c`
- name: `WinHvFreeSingleSintIndex`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400010e8`
- `0x140009c50`
- `0x14001d150`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d1cb`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d1cb`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d1ec`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d1ec`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001d196`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14001d196`

## pseudocode

```c
void __fastcall WinHvFreeSingleSintIndex(unsigned int a1, ULONG a2)
{
  NTSTATUS ProcessorNumberFromIndex; // eax
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-30h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-20h] BYREF

  if ( a1 < 0x10 )
  {
    PreviousAffinity = 0;
    if ( WinHvpConnected )
    {
      ProcNumber = 0;
      Affinity = 0;
      ProcessorNumberFromIndex = KeGetProcessorNumberFromIndex(a2, &ProcNumber);
      Affinity.Group = ProcNumber.Group;
      Affinity.Mask = 1LL << ProcNumber.Number;
      if ( ProcessorNumberFromIndex >= 0 )
      {
        KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
        WinHvpSetVpRegister64Self(a1 + 655360);
        KeRevertToUserGroupAffinityThread(&PreviousAffinity);
      }
    }
  }
}

```

## disassembly

```asm
0x14001d150  cmp     ecx, 10h
0x14001d153  jnb     locret_14001D20A
0x14001d159  push    rbx
0x14001d15a  sub     rsp, 50h
0x14001d15e  mov     rax, cs:__security_cookie
0x14001d165  xor     rax, rsp
0x14001d168  mov     [rsp+58h+var_10], rax
0x14001d16d  cmp     cs:WinHvpConnected, 0
0x14001d174  xorps   xmm0, xmm0
0x14001d177  movups  xmmword ptr [rsp+58h+PreviousAffinity.Mask], xmm0
0x14001d17c  mov     eax, edx
0x14001d17e  mov     ebx, ecx
0x14001d180  jz      short loc_14001D1F8
0x14001d182  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x14001d187  mov     dword ptr [rsp+58h+ProcNumber.Group], 0
0x14001d18f  mov     ecx, eax; ProcIndex
0x14001d191  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x14001d196  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14001d19d  nop     dword ptr [rax+rax+00h]
0x14001d1a2  movzx   ecx, [rsp+58h+ProcNumber.Group]
0x14001d1a7  mov     edx, 1
0x14001d1ac  mov     [rsp+58h+Affinity.Group], cx
0x14001d1b1  mov     cl, [rsp+58h+ProcNumber.Number]
0x14001d1b5  shl     rdx, cl
0x14001d1b8  mov     [rsp+58h+Affinity.Mask], rdx
0x14001d1bd  test    eax, eax
0x14001d1bf  js      short loc_14001D1F8
0x14001d1c1  lea     rdx, [rsp+58h+PreviousAffinity]; PreviousAffinity
0x14001d1c6  lea     rcx, [rsp+58h+Affinity]; Affinity
0x14001d1cb  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001d1d2  nop     dword ptr [rax+rax+00h]
0x14001d1d7  lea     ecx, [rbx+0A0000h]
0x14001d1dd  mov     edx, 10000h
0x14001d1e2  call    WinHvpSetVpRegister64Self
0x14001d1e7  lea     rcx, [rsp+58h+PreviousAffinity]; PreviousAffinity
0x14001d1ec  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001d1f3  nop     dword ptr [rax+rax+00h]
0x14001d1f8  mov     rcx, [rsp+58h+var_10]
0x14001d1fd  xor     rcx, rsp; StackCookie
0x14001d200  call    __security_check_cookie
0x14001d205  add     rsp, 50h
0x14001d209  pop     rbx
0x14001d20a  retn
```
