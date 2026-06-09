# PassiveCompletionThread

- ea: `0x1400015b0`
- end: `0x140001762`
- name: `PassiveCompletionThread`
- size: `434`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400015b0`
- `0x140001768`
- `0x140001bcc`
- `0x1400029a0`
- `0x140002f64`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x140001638`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140001638`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000172d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14000172d`

## pseudocode

```c
void __fastcall __noreturn PassiveCompletionThread(char *StartContext)
{
  __int64 v1; // rdi
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  NTSTATUS v5; // eax
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  PVOID Object[7]; // [rsp+40h] [rbp-38h] BYREF

  v1 = *(_QWORD *)StartContext;
  Object[0] = StartContext + 496;
  Object[1] = StartContext + 464;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    do
    {
      while ( 1 )
      {
LABEL_5:
        while ( 1 )
        {
          v5 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
          if ( !v5 )
            break;
          if ( v5 == 1 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v1);
            while ( 1 )
            {
              v11 = PassiveCompletionRemoveNextIrp(StartContext);
              if ( !v11 )
                break;
              CaptureReQueueUrb(*(_QWORD *)(v11 + 120));
            }
            if ( StartContext[441] )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v1);
              PsTerminateSystemThread(0);
            }
          }
          else
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v4 = 137;
              goto LABEL_4;
            }
          }
        }
        v6 = PassiveCompletionRemoveNextIrp(StartContext);
        if ( !v6 )
          break;
        v7 = *(_QWORD *)(v6 + 120);
        if ( v7 )
        {
          v8 = *(_QWORD *)(v7 + 16);
          if ( v8 )
          {
            v9 = *(_QWORD *)(v8 + 16);
            if ( v9 )
            {
              v10 = *(_QWORD *)(v7 + 24);
              if ( *(_DWORD *)(v9 + 380) )
                CaptureCompleteBulk(v9, v10);
              else
                CaptureCompleteIsoch(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 24LL), v10);
            }
          }
        }
      }
      v3 = WPP_GLOBAL_Control;
    }
    while ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u );
    v4 = 134;
  }
  else
  {
    v4 = 133;
  }
LABEL_4:
  WPP_SF_q(v3->AttachedDevice, v4, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v1);
  goto LABEL_5;
}

```

## disassembly

```asm
0x1400015b0  push    rbx
0x1400015b2  push    rbp
0x1400015b3  push    rdi
0x1400015b4  push    r14
0x1400015b6  sub     rsp, 58h
0x1400015ba  mov     rdi, [rcx]
0x1400015bd  lea     rax, [rcx+1F0h]
0x1400015c4  mov     [rsp+78h+Object], rax
0x1400015c9  mov     rbx, rcx
0x1400015cc  lea     rax, [rcx+1D0h]
0x1400015d3  mov     [rsp+78h+var_30], rax
0x1400015d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015df  lea     rbp, WPP_GLOBAL_Control
0x1400015e6  lea     r14, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400015ed  cmp     rcx, rbp
0x1400015f0  jz      short loc_14000160C
0x1400015f2  cmp     byte ptr [rcx+29h], 4
0x1400015f6  jb      short loc_14000160C
0x1400015f8  mov     edx, 85h
0x1400015fd  mov     rcx, [rcx+18h]
0x140001601  mov     r9, rdi
0x140001604  mov     r8, r14
0x140001607  call    WPP_SF_q
0x14000160c  xor     r9d, r9d; WaitReason
0x14000160f  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x140001618  mov     [rsp+78h+Timeout], 0; Timeout
0x140001621  lea     rdx, [rsp+78h+Object]; Object
0x140001626  mov     [rsp+78h+Alertable], 0; Alertable
0x14000162b  mov     [rsp+78h+WaitMode], 0; WaitMode
0x140001630  lea     r8d, [r9+1]; WaitType
0x140001634  lea     ecx, [r9+2]; Count
0x140001638  call    cs:__imp_KeWaitForMultipleObjects
0x14000163f  nop     dword ptr [rax+rax+00h]
0x140001644  test    eax, eax
0x140001646  jnz     short loc_1400016B2
0x140001648  mov     rcx, rbx
0x14000164b  call    PassiveCompletionRemoveNextIrp
0x140001650  test    rax, rax
0x140001653  jnz     short loc_14000166E
0x140001655  mov     rcx, cs:WPP_GLOBAL_Control
0x14000165c  cmp     rcx, rbp
0x14000165f  jz      short loc_14000160C
0x140001661  cmp     byte ptr [rcx+29h], 3
0x140001665  jb      short loc_14000160C
0x140001667  mov     edx, 86h
0x14000166c  jmp     short loc_1400015FD
0x14000166e  mov     r8, [rax+78h]
0x140001672  test    r8, r8
0x140001675  jz      short loc_14000160C
0x140001677  mov     rax, [r8+10h]
0x14000167b  test    rax, rax
0x14000167e  jz      short loc_14000160C
0x140001680  mov     rcx, [rax+10h]
0x140001684  test    rcx, rcx
0x140001687  jz      short loc_14000160C
0x140001689  cmp     dword ptr [rcx+17Ch], 0
0x140001690  mov     rdx, [r8+18h]
0x140001694  jz      short loc_1400016A0
0x140001696  call    CaptureCompleteBulk
0x14000169b  jmp     loc_14000160C
0x1400016a0  mov     rcx, [rdi+18h]
0x1400016a4  mov     rcx, [rcx+18h]
0x1400016a8  call    CaptureCompleteIsoch
0x1400016ad  jmp     loc_14000160C
0x1400016b2  cmp     eax, 1
0x1400016b5  jnz     loc_14000173E
0x1400016bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016c2  cmp     rcx, rbp
0x1400016c5  jz      short loc_1400016EC
0x1400016c7  cmp     byte ptr [rcx+29h], 2
0x1400016cb  jb      short loc_1400016EC
0x1400016cd  mov     rcx, [rcx+18h]
0x1400016d1  mov     edx, 87h
0x1400016d6  mov     r9, rdi
0x1400016d9  mov     r8, r14
0x1400016dc  call    WPP_SF_q
0x1400016e1  jmp     short loc_1400016EC
0x1400016e3  mov     rcx, [rax+78h]
0x1400016e7  call    CaptureReQueueUrb
0x1400016ec  mov     rcx, rbx
0x1400016ef  call    PassiveCompletionRemoveNextIrp
0x1400016f4  test    rax, rax
0x1400016f7  jnz     short loc_1400016E3
0x1400016f9  cmp     [rbx+1B9h], al
0x1400016ff  jz      loc_14000160C
0x140001705  mov     rcx, cs:WPP_GLOBAL_Control
0x14000170c  cmp     rcx, rbp
0x14000170f  jz      short loc_14000172B
0x140001711  cmp     byte ptr [rcx+29h], 4
0x140001715  jb      short loc_14000172B
0x140001717  mov     rcx, [rcx+18h]
0x14000171b  mov     edx, 88h
0x140001720  mov     r9, rdi
0x140001723  mov     r8, r14
0x140001726  call    WPP_SF_q
0x14000172b  xor     ecx, ecx; ExitStatus
0x14000172d  call    cs:__imp_PsTerminateSystemThread
0x140001734  nop     dword ptr [rax+rax+00h]
0x140001739  jmp     loc_14000160C
0x14000173e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001745  cmp     rcx, rbp
0x140001748  jz      loc_14000160C
0x14000174e  cmp     byte ptr [rcx+29h], 2
0x140001752  jb      loc_14000160C
0x140001758  mov     edx, 89h
0x14000175d  jmp     loc_1400015FD
```
