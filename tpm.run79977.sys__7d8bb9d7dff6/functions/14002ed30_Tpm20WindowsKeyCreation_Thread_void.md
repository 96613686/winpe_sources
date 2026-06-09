# Tpm20WindowsKeyCreation_Thread(void *)

- ea: `0x14002ed30`
- end: `0x14002f0a7`
- name: `?Tpm20WindowsKeyCreation_Thread@@YAXPEAX@Z`
- size: `887`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1400078b8`
- `0x140008a5c`
- `0x140009278`
- `0x14000e3ac`
- `0x14001c3b4`
- `0x14001d14c`
- `0x14001d170`
- `0x14002ed30`
- `0x140039780`
- `0x140045158`
- `0x140045430`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002efbc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002efbc`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002ef4d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002ef4d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002f089`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002f089`
- `ntoskrnl!KeSetEvent` at `0x14002ef8b`
- `ntoskrnl!KeSetEvent` at `0x14002ef8b`

## pseudocode

```c
void __fastcall Tpm20WindowsKeyCreation_Thread(_QWORD *a1, unsigned int a2)
{
  void *v2; // rbp
  int v4; // edi
  TpmStack **v5; // r15
  TpmStack *v6; // rax
  ThreadWithCancel *v7; // rbx
  unsigned __int8 *v8; // r12
  TpmStack *v9; // rdi
  PDEVICE_OBJECT v10; // rcx
  ThreadWithCancel *v11; // rax
  unsigned __int8 *v12; // rax
  __int128 Object; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 retaddr; // [rsp+98h] [rbp+0h]
  int v15; // [rsp+A0h] [rbp+8h]
  void *v16; // [rsp+A8h] [rbp+10h] BYREF
  TpmStack *v17; // [rsp+B0h] [rbp+18h]
  TpmStack *v18; // [rsp+B8h] [rbp+20h]

  v2 = 0;
  v16 = 0;
  Object = 0;
  if ( !a1 )
  {
    v4 = -1073741811;
    goto LABEL_47;
  }
  v5 = (TpmStack **)a1[1];
  v6 = 0;
  v7 = 0;
  v17 = 0;
  if ( v5 )
  {
    if ( *(_DWORD *)v5 < 3u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
      v4 = -1073741811;
LABEL_42:
      TpmFree(v5);
      v6 = v17;
      goto LABEL_43;
    }
    v8 = 0;
    v9 = v5[1];
    v18 = v5[2];
    v15 = *((_DWORD *)v5 + 6);
    v17 = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    v11 = (ThreadWithCancel *)ThreadWithCancel::operator new((unsigned __int64)v10);
    v7 = v11;
    if ( v11 )
    {
      *((_QWORD *)v11 + 1) = 0;
      *(_QWORD *)v11 = WindowsKeyCreation_SubThread;
      *((_QWORD *)v11 + 2) = 0;
      *((_QWORD *)v11 + 3) = 0;
      v4 = TpmStack::CreateTpmContext(v9, &v16);
      if ( v4 < 0 )
      {
        v2 = v16;
LABEL_38:
        if ( v18 )
          (*((void (__fastcall **)(PKDPC, TpmStack *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 263))(
            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
            v18,
            (unsigned int)v4);
        if ( v8 )
          TpmFree(v8);
        goto LABEL_42;
      }
      v12 = TpmAlloc(1, 0x20u, retaddr);
      v8 = v12;
      if ( v12 )
      {
        v2 = v16;
        *(_DWORD *)v12 = 3;
        *((_QWORD *)v12 + 1) = v17;
        *((_DWORD *)v12 + 6) = v15;
        *((_QWORD *)v12 + 2) = v2;
        v4 = ThreadWithCancel::Start(v7, v12);
        if ( v4 >= 0 )
        {
          *(_QWORD *)&Object = *((_QWORD *)v7 + 2);
          *((_QWORD *)&Object + 1) = a1[3];
          v4 = KeWaitForMultipleObjects(2u, (PVOID *)&Object, WaitAny, Executive, 0, 0, 0, 0);
          if ( v4 == 1 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(
                WPP_GLOBAL_Control->AttachedDevice,
                (unsigned int)(v4 + 44),
                WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
            }
            KeSetEvent(*((PRKEVENT *)v7 + 3), 0, 0);
            TpmStack::CancelTpmContext(v17, v2);
            KeWaitForSingleObject(*((PVOID *)v7 + 2), Executive, 0, 0, 0);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
            (unsigned int)v4);
        }
        goto LABEL_38;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
      v2 = v16;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
      v7 = 0;
    }
    v4 = -1073741670;
    goto LABEL_38;
  }
  v4 = -1073741811;
LABEL_43:
  if ( v2 )
    TpmStack::DeleteTpmContext(v6, v2);
  if ( v7 )
    ThreadWithCancel::`scalar deleting destructor'(v7, a2);
LABEL_47:
  PsTerminateSystemThread(v4);
}

```

## disassembly

```asm
0x14002ed30  mov     rax, rsp
0x14002ed33  push    rbx
0x14002ed34  push    rbp
0x14002ed35  push    rsi
0x14002ed36  push    rdi
0x14002ed37  push    r12
0x14002ed39  push    r13
0x14002ed3b  push    r14
0x14002ed3d  push    r15
0x14002ed3f  sub     rsp, 58h
0x14002ed43  xor     ebp, ebp
0x14002ed45  xorps   xmm0, xmm0
0x14002ed48  mov     [rax+10h], rbp
0x14002ed4c  mov     r13, rcx
0x14002ed4f  movups  xmmword ptr [rax-58h], xmm0
0x14002ed53  test    rcx, rcx
0x14002ed56  jnz     short loc_14002ED62
0x14002ed58  mov     edi, 0C000000Dh
0x14002ed5d  jmp     loc_14002F087
0x14002ed62  mov     r15, [rcx+8]
0x14002ed66  xor     eax, eax
0x14002ed68  xor     ebx, ebx
0x14002ed6a  mov     [rsp+98h+arg_10], rax
0x14002ed72  test    r15, r15
0x14002ed75  jnz     short loc_14002ED81
0x14002ed77  mov     edi, 0C000000Dh
0x14002ed7c  jmp     loc_14002F06A
0x14002ed81  cmp     dword ptr [r15], 3
0x14002ed85  jnb     short loc_14002EDC0
0x14002ed87  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ed8e  lea     rsi, WPP_GLOBAL_Control
0x14002ed95  cmp     rcx, rsi
0x14002ed98  jz      short loc_14002EDB6
0x14002ed9a  mov     eax, [rcx+2Ch]
0x14002ed9d  test    al, 1
0x14002ed9f  jz      short loc_14002EDB6
0x14002eda1  mov     rcx, [rcx+18h]
0x14002eda5  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002edac  mov     edx, 28h ; '('
0x14002edb1  call    WPP_SF_
0x14002edb6  mov     edi, 0C000000Dh
0x14002edbb  jmp     loc_14002F05A
0x14002edc0  mov     rax, [r15+10h]
0x14002edc4  xor     r12d, r12d
0x14002edc7  mov     rdi, [r15+8]
0x14002edcb  mov     [rsp+98h+arg_18], rax
0x14002edd3  mov     eax, [r15+18h]
0x14002edd7  mov     [rsp+98h+arg_0], eax
0x14002edde  mov     [rsp+98h+arg_10], rdi
0x14002ede6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002eded  lea     rsi, WPP_GLOBAL_Control
0x14002edf4  lea     r14, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002edfb  cmp     rcx, rsi
0x14002edfe  jz      short loc_14002EE18
0x14002ee00  mov     eax, [rcx+2Ch]
0x14002ee03  test    al, 4
0x14002ee05  jz      short loc_14002EE18
0x14002ee07  mov     rcx, [rcx+18h]
0x14002ee0b  lea     edx, [r12+29h]
0x14002ee10  mov     r8, r14
0x14002ee13  call    WPP_SF_
0x14002ee18  call    ??2ThreadWithCancel@@SAPEAX_K@Z; ThreadWithCancel::operator new(unsigned __int64)
0x14002ee1d  mov     rbx, rax
0x14002ee20  test    rax, rax
0x14002ee23  jz      loc_14002EFF8
0x14002ee29  mov     [rbx+8], rbp
0x14002ee2d  lea     rax, ?WindowsKeyCreation_SubThread@@YAXPEAX@Z; WindowsKeyCreation_SubThread(void *)
0x14002ee34  mov     [rbx], rax
0x14002ee37  lea     rdx, [rsp+98h+arg_8]; void **
0x14002ee3f  mov     [rbx+10h], rbp
0x14002ee43  mov     rcx, rdi; this
0x14002ee46  mov     [rbx+18h], rbp
0x14002ee4a  call    ?CreateTpmContext@TpmStack@@QEAAJPEAPEAX@Z; TpmStack::CreateTpmContext(void * *)
0x14002ee4f  mov     edi, eax
0x14002ee51  test    eax, eax
0x14002ee53  js      loc_14002EFEE
0x14002ee59  mov     r8, [rsp+98h]; unsigned __int64
0x14002ee61  mov     edx, 20h ; ' '; unsigned __int64
0x14002ee66  mov     cl, 1; bool
0x14002ee68  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14002ee6d  mov     r12, rax
0x14002ee70  test    rax, rax
0x14002ee73  jnz     short loc_14002EEA6
0x14002ee75  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ee7c  cmp     rcx, rsi
0x14002ee7f  jz      short loc_14002EE99
0x14002ee81  mov     eax, [rcx+2Ch]
0x14002ee84  test    al, 1
0x14002ee86  jz      short loc_14002EE99
0x14002ee88  mov     rcx, [rcx+18h]
0x14002ee8c  lea     edx, [r12+2Bh]
0x14002ee91  mov     r8, r14
0x14002ee94  call    WPP_SF_
0x14002ee99  mov     rbp, [rsp+98h+arg_8]
0x14002eea1  jmp     loc_14002F01E
0x14002eea6  mov     rbp, [rsp+98h+arg_8]
0x14002eeae  mov     rdx, r12; void *
0x14002eeb1  mov     dword ptr [rax], 3
0x14002eeb7  mov     rcx, rbx; this
0x14002eeba  mov     rax, [rsp+98h+arg_10]
0x14002eec2  mov     [r12+8], rax
0x14002eec7  mov     eax, [rsp+98h+arg_0]
0x14002eece  mov     [r12+18h], eax
0x14002eed3  mov     [r12+10h], rbp
0x14002eed8  call    ?Start@ThreadWithCancel@@QEAAJPEAX@Z; ThreadWithCancel::Start(void *)
0x14002eedd  xor     ecx, ecx
0x14002eedf  mov     edi, eax
0x14002eee1  test    eax, eax
0x14002eee3  jns     short loc_14002EF19
0x14002eee5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002eeec  cmp     rcx, rsi
0x14002eeef  jz      loc_14002F023
0x14002eef5  mov     eax, [rcx+2Ch]
0x14002eef8  test    al, 2
0x14002eefa  jz      loc_14002F023
0x14002ef00  mov     rcx, [rcx+18h]
0x14002ef04  mov     edx, 2Ch ; ','
0x14002ef09  mov     r9d, edi
0x14002ef0c  mov     r8, r14
0x14002ef0f  call    WPP_SF_d
0x14002ef14  jmp     loc_14002F023
0x14002ef19  mov     rax, [rbx+10h]
0x14002ef1d  lea     rdx, [rsp+98h+Object]; Object
0x14002ef22  mov     [rsp+98h+WaitBlockArray], rcx; WaitBlockArray
0x14002ef27  xor     r9d, r9d; WaitReason
0x14002ef2a  mov     [rsp+98h+Timeout], rcx; Timeout
0x14002ef2f  mov     [rsp+98h+Alertable], cl; Alertable
0x14002ef33  mov     [rsp+98h+Object], rax
0x14002ef38  mov     rax, [r13+18h]
0x14002ef3c  lea     r8d, [r9+1]; WaitType
0x14002ef40  mov     [rsp+98h+WaitMode], cl; WaitMode
0x14002ef44  lea     ecx, [r9+2]; Count
0x14002ef48  mov     [rsp+98h+var_50], rax
0x14002ef4d  call    cs:__imp_KeWaitForMultipleObjects
0x14002ef54  nop     dword ptr [rax+rax+00h]
0x14002ef59  mov     edi, eax
0x14002ef5b  cmp     eax, 1
0x14002ef5e  jnz     short loc_14002EFC8
0x14002ef60  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ef67  cmp     rcx, rsi
0x14002ef6a  jz      short loc_14002EF82
0x14002ef6c  mov     eax, [rcx+2Ch]
0x14002ef6f  test    al, 4
0x14002ef71  jz      short loc_14002EF82
0x14002ef73  mov     rcx, [rcx+18h]
0x14002ef77  lea     edx, [rdi+2Ch]
0x14002ef7a  mov     r8, r14
0x14002ef7d  call    WPP_SF_
0x14002ef82  mov     rcx, [rbx+18h]; Event
0x14002ef86  xor     r8d, r8d; Wait
0x14002ef89  xor     edx, edx; Increment
0x14002ef8b  call    cs:__imp_KeSetEvent
0x14002ef92  nop     dword ptr [rax+rax+00h]
0x14002ef97  mov     rcx, [rsp+98h+arg_10]; this
0x14002ef9f  mov     rdx, rbp; void *
0x14002efa2  call    ?CancelTpmContext@TpmStack@@QEAAXPEAX@Z; TpmStack::CancelTpmContext(void *)
0x14002efa7  mov     rcx, [rbx+10h]; Object
0x14002efab  xor     r9d, r9d; Alertable
0x14002efae  xor     r8d, r8d; WaitMode
0x14002efb1  mov     qword ptr [rsp+98h+WaitMode], 0; Timeout
0x14002efba  xor     edx, edx; WaitReason
0x14002efbc  call    cs:__imp_KeWaitForSingleObject
0x14002efc3  nop     dword ptr [rax+rax+00h]
0x14002efc8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002efcf  cmp     rcx, rsi
0x14002efd2  jz      short loc_14002F023
0x14002efd4  mov     eax, [rcx+2Ch]
0x14002efd7  test    al, 4
0x14002efd9  jz      short loc_14002F023
0x14002efdb  mov     rcx, [rcx+18h]
0x14002efdf  mov     edx, 2Eh ; '.'
0x14002efe4  mov     r8, r14
0x14002efe7  call    WPP_SF_
0x14002efec  jmp     short loc_14002F023
0x14002efee  mov     rbp, [rsp+98h+arg_8]
0x14002eff6  jmp     short loc_14002F023
0x14002eff8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002efff  cmp     rcx, rsi
0x14002f002  jz      short loc_14002F01C
0x14002f004  mov     eax, [rcx+2Ch]
0x14002f007  test    al, 1
0x14002f009  jz      short loc_14002F01C
0x14002f00b  mov     rcx, [rcx+18h]
0x14002f00f  mov     edx, 2Ah ; '*'
0x14002f014  mov     r8, r14
0x14002f017  call    WPP_SF_
0x14002f01c  xor     ebx, ebx
0x14002f01e  mov     edi, 0C000009Ah
0x14002f023  mov     rdx, [rsp+98h+arg_18]
0x14002f02b  test    rdx, rdx
0x14002f02e  jz      short loc_14002F04D
0x14002f030  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002f037  mov     r8d, edi
0x14002f03a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002f041  mov     rax, [rax+838h]
0x14002f048  call    _guard_dispatch_icall
0x14002f04d  test    r12, r12
0x14002f050  jz      short loc_14002F05A
0x14002f052  mov     rcx, r12; void *
0x14002f055  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002f05a  mov     rcx, r15; void *
0x14002f05d  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14002f062  mov     rax, [rsp+98h+arg_10]
0x14002f06a  test    rbp, rbp
0x14002f06d  jz      short loc_14002F07A
0x14002f06f  mov     rdx, rbp; void *
0x14002f072  mov     rcx, rax; this
0x14002f075  call    ?DeleteTpmContext@TpmStack@@QEAAXPEAX@Z; TpmStack::DeleteTpmContext(void *)
0x14002f07a  test    rbx, rbx
0x14002f07d  jz      short loc_14002F087
0x14002f07f  mov     rcx, rbx; this
0x14002f082  call    ??_GThreadWithCancel@@QEAAPEAXI@Z; ThreadWithCancel::`scalar deleting destructor'(uint)
0x14002f087  mov     ecx, edi; ExitStatus
0x14002f089  call    cs:__imp_PsTerminateSystemThread
0x14002f090  nop     dword ptr [rax+rax+00h]
0x14002f095  add     rsp, 58h
0x14002f099  pop     r15
0x14002f09b  pop     r14
0x14002f09d  pop     r13
0x14002f09f  pop     r12
0x14002f0a1  pop     rdi
0x14002f0a2  pop     rsi
0x14002f0a3  pop     rbp
0x14002f0a4  pop     rbx
0x14002f0a5  retn
```
