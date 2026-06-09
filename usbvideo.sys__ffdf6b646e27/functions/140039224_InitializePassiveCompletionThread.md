# InitializePassiveCompletionThread

- ea: `0x140039224`
- end: `0x1400394c4`
- name: `InitializePassiveCompletionThread`
- size: `672`
- prototype: `__int64 __fastcall(PVOID StartContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011bc0`

## callees

- `0x14001ab4c`
- `0x14001b15c`
- `0x140039224`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140039301`
- `ntoskrnl!PsCreateSystemThread` at `0x140039301`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003935f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003935f`
- `ntoskrnl!KeSetPriorityThread` at `0x140039400`
- `ntoskrnl!KeSetPriorityThread` at `0x140039400`
- `ntoskrnl!ZwClose` at `0x140039443`
- `ntoskrnl!ZwClose` at `0x140039443`
- `ntoskrnl!KeInitializeSemaphore` at `0x140039289`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400392a1`
- `ntoskrnl!KeInitializeSemaphore` at `0x140039289`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400392a1`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039388`
- `ntoskrnl!KeReleaseSemaphore` at `0x140039388`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400392b4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400392b4`

## pseudocode

```c
__int64 __fastcall InitializePassiveCompletionThread(char *StartContext)
{
  NTSTATUS v2; // edi
  NTSTATUS v3; // eax
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  void *ThreadHandle; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  ThreadHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, StartContext);
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 464), 0, 0x7FFFFFFF);
  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 496), 0, 0x7FFFFFFF);
  KeInitializeSpinLock((PKSPIN_LOCK)StartContext + 57);
  *((_QWORD *)StartContext + 67) = StartContext + 528;
  *((_QWORD *)StartContext + 66) = StartContext + 528;
  if ( !*((_QWORD *)StartContext + 56) )
  {
    v3 = PsCreateSystemThread(&ThreadHandle, 0, 0, 0, 0, PassiveCompletionThread, StartContext);
    v2 = v3;
    if ( v3 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, StartContext);
      v2 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, (PVOID *)StartContext + 56, 0);
      if ( v2 >= 0 )
      {
        if ( KeSetPriorityThread(*((PKTHREAD *)StartContext + 56), 16) >= 0 )
          goto LABEL_18;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_18;
        v5 = 126;
      }
      else
      {
        StartContext[441] = 1;
        KeReleaseSemaphore((PRKSEMAPHORE)(StartContext + 464), 0, 1, 0);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_18;
        v5 = 125;
      }
      WPP_SF_qD(v4->AttachedDevice, v5, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, StartContext, v2);
LABEL_18:
      ZwClose(ThreadHandle);
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        127,
        WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
        StartContext,
        v3);
  }
LABEL_22:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      128,
      WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
      StartContext,
      v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140039224  mov     rax, rsp
0x140039227  mov     [rax+18h], rbx
0x14003922b  mov     [rax+20h], rsi
0x14003922f  mov     [rax+8], rcx
0x140039233  push    rdi
0x140039234  push    r14
0x140039236  push    r15
0x140039238  sub     rsp, 40h
0x14003923c  mov     rbx, rcx
0x14003923f  xor     edi, edi
0x140039241  mov     [rax+10h], rdi
0x140039245  lea     rsi, WPP_GLOBAL_Control
0x14003924c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039253  cmp     rcx, rsi
0x140039256  jz      short loc_140039274
0x140039258  cmp     byte ptr [rcx+29h], 5
0x14003925c  jb      short loc_140039274
0x14003925e  lea     edx, [rdi+7Ah]
0x140039261  mov     r9, rbx
0x140039264  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14003926b  mov     rcx, [rcx+18h]
0x14003926f  call    WPP_SF_q
0x140039274  lea     r15, [rbx+1D0h]
0x14003927b  mov     r14d, 7FFFFFFFh
0x140039281  mov     r8d, r14d; Limit
0x140039284  xor     edx, edx; Count
0x140039286  mov     rcx, r15; Semaphore
0x140039289  call    cs:__imp_KeInitializeSemaphore
0x140039290  nop     dword ptr [rax+rax+00h]
0x140039295  lea     rcx, [rbx+1F0h]; Semaphore
0x14003929c  mov     r8d, r14d; Limit
0x14003929f  xor     edx, edx; Count
0x1400392a1  call    cs:__imp_KeInitializeSemaphore
0x1400392a8  nop     dword ptr [rax+rax+00h]
0x1400392ad  lea     rcx, [rbx+1C8h]; SpinLock
0x1400392b4  call    cs:__imp_KeInitializeSpinLock
0x1400392bb  nop     dword ptr [rax+rax+00h]
0x1400392c0  lea     rax, [rbx+210h]
0x1400392c7  mov     [rax+8], rax
0x1400392cb  mov     [rax], rax
0x1400392ce  lea     r14, [rbx+1C0h]
0x1400392d5  cmp     [r14], rdi
0x1400392d8  jnz     loc_14003947F
0x1400392de  mov     [rsp+58h+StartContext], rbx; StartContext
0x1400392e3  lea     rax, PassiveCompletionThread
0x1400392ea  mov     [rsp+58h+StartRoutine], rax; StartRoutine
0x1400392ef  mov     [rsp+58h+ClientId], rdi; ClientId
0x1400392f4  xor     r9d, r9d; ProcessHandle
0x1400392f7  xor     r8d, r8d; ObjectAttributes
0x1400392fa  xor     edx, edx; DesiredAccess
0x1400392fc  lea     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x140039301  call    cs:__imp_PsCreateSystemThread
0x140039308  nop     dword ptr [rax+rax+00h]
0x14003930d  mov     edi, eax
0x14003930f  test    eax, eax
0x140039311  js      loc_140039451
0x140039317  mov     rcx, cs:WPP_GLOBAL_Control
0x14003931e  cmp     rcx, rsi
0x140039321  jz      short loc_140039341
0x140039323  cmp     byte ptr [rcx+29h], 5
0x140039327  jb      short loc_140039341
0x140039329  mov     edx, 7Bh ; '{'
0x14003932e  mov     r9, rbx
0x140039331  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039338  mov     rcx, [rcx+18h]
0x14003933c  call    WPP_SF_q
0x140039341  mov     [rsp+58h+StartRoutine], 0; HandleInformation
0x14003934a  mov     [rsp+58h+ClientId], r14; Object
0x14003934f  xor     r9d, r9d; AccessMode
0x140039352  xor     r8d, r8d; ObjectType
0x140039355  mov     edx, 1FFFFFh; DesiredAccess
0x14003935a  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x14003935f  call    cs:__imp_ObReferenceObjectByHandle
0x140039366  nop     dword ptr [rax+rax+00h]
0x14003936b  mov     edi, eax
0x14003936d  test    eax, eax
0x14003936f  jns     loc_1400393F8
0x140039375  mov     byte ptr [rbx+1B9h], 1
0x14003937c  xor     r9d, r9d; Wait
0x14003937f  xor     edx, edx; Increment
0x140039381  lea     r8d, [r9+1]; Adjustment
0x140039385  mov     rcx, r15; Semaphore
0x140039388  call    cs:__imp_KeReleaseSemaphore
0x14003938f  nop     dword ptr [rax+rax+00h]
0x140039394  jmp     short loc_1400393DF
0x140039396  lea     rax, WPP_GLOBAL_Control
0x14003939d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400393a4  cmp     rcx, rax
0x1400393a7  jz      short loc_1400393CE
0x1400393a9  cmp     byte ptr [rcx+29h], 2
0x1400393ad  jb      short loc_1400393CE
0x1400393af  mov     edx, 7Ch ; '|'
0x1400393b4  mov     rbx, [rsp+58h+arg_0]
0x1400393b9  mov     r9, rbx
0x1400393bc  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400393c3  mov     rcx, [rcx+18h]
0x1400393c7  call    WPP_SF_q
0x1400393cc  jmp     short loc_1400393D3
0x1400393ce  mov     rbx, [rsp+58h+arg_0]
0x1400393d3  mov     edi, 0C0000047h
0x1400393d8  lea     rsi, WPP_GLOBAL_Control
0x1400393df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400393e6  cmp     rcx, rsi
0x1400393e9  jz      short loc_14003943E
0x1400393eb  cmp     byte ptr [rcx+29h], 2
0x1400393ef  jb      short loc_14003943E
0x1400393f1  mov     edx, 7Dh ; '}'
0x1400393f6  jmp     short loc_140039427
0x1400393f8  mov     edx, 10h; Priority
0x1400393fd  mov     rcx, [r14]; Thread
0x140039400  call    cs:__imp_KeSetPriorityThread
0x140039407  nop     dword ptr [rax+rax+00h]
0x14003940c  test    eax, eax
0x14003940e  jns     short loc_14003943E
0x140039410  mov     rcx, cs:WPP_GLOBAL_Control
0x140039417  cmp     rcx, rsi
0x14003941a  jz      short loc_14003943E
0x14003941c  cmp     byte ptr [rcx+29h], 2
0x140039420  jb      short loc_14003943E
0x140039422  mov     edx, 7Eh ; '~'
0x140039427  mov     dword ptr [rsp+58h+ClientId], edi
0x14003942b  mov     r9, rbx
0x14003942e  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039435  mov     rcx, [rcx+18h]
0x140039439  call    WPP_SF_qD
0x14003943e  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x140039443  call    cs:__imp_ZwClose
0x14003944a  nop     dword ptr [rax+rax+00h]
0x14003944f  jmp     short loc_14003947F
0x140039451  mov     rcx, cs:WPP_GLOBAL_Control
0x140039458  cmp     rcx, rsi
0x14003945b  jz      short loc_14003947F
0x14003945d  cmp     byte ptr [rcx+29h], 2
0x140039461  jb      short loc_14003947F
0x140039463  mov     edx, 7Fh
0x140039468  mov     dword ptr [rsp+58h+ClientId], eax
0x14003946c  mov     r9, rbx
0x14003946f  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039476  mov     rcx, [rcx+18h]
0x14003947a  call    WPP_SF_qD
0x14003947f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039486  cmp     rcx, rsi
0x140039489  jz      short loc_1400394AD
0x14003948b  cmp     byte ptr [rcx+29h], 5
0x14003948f  jb      short loc_1400394AD
0x140039491  mov     edx, 80h
0x140039496  mov     dword ptr [rsp+58h+ClientId], edi
0x14003949a  mov     r9, rbx
0x14003949d  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400394a4  mov     rcx, [rcx+18h]
0x1400394a8  call    WPP_SF_qD
0x1400394ad  mov     eax, edi
0x1400394af  mov     rbx, [rsp+58h+arg_10]
0x1400394b4  mov     rsi, [rsp+58h+arg_18]
0x1400394b9  add     rsp, 40h
0x1400394bd  pop     r15
0x1400394bf  pop     r14
0x1400394c1  pop     rdi
0x1400394c2  retn
0x140041363  push    rbp
0x140041365  sub     rsp, 40h
0x140041369  mov     rbp, rdx
0x14004136c  mov     rax, [rcx]
0x14004136f  mov     ecx, [rax]
0x140041371  xor     eax, eax
0x140041373  cmp     ecx, 0C0000047h
0x140041379  setz    al
0x14004137c  add     rsp, 40h
0x140041380  pop     rbp
0x140041381  retn
```
