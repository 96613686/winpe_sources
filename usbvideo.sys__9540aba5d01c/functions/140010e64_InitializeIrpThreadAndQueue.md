# InitializeIrpThreadAndQueue

- ea: `0x140010e64`
- end: `0x140011038`
- name: `InitializeIrpThreadAndQueue`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015e60`

## callees

- `0x140010e64`
- `0x14001b15c`
- `0x14001f2e0`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140010f33`
- `ntoskrnl!PsCreateSystemThread` at `0x140010f33`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140010f67`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140010f67`
- `ntoskrnl!ZwClose` at `0x140010fc7`
- `ntoskrnl!ZwClose` at `0x140010fc7`
- `ntoskrnl!KeReleaseSemaphore` at `0x140010f90`
- `ntoskrnl!KeReleaseSemaphore` at `0x140010f90`

## pseudocode

```c
__int64 __fastcall InitializeIrpThreadAndQueue(__int64 a1, __int64 a2)
{
  NTSTATUS v2; // edi
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  void *ThreadHandle; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  ThreadHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a2);
  if ( *(_QWORD *)(a2 + 648) || (v2 = InitializeInterruptContext(a1, a2), v2 >= 0) )
  {
    if ( !*(_QWORD *)(a2 + 368) )
    {
      *(_BYTE *)(a2 + 356) = 0;
      v2 = PsCreateSystemThread(&ThreadHandle, 0, 0, 0, 0, (PKSTART_ROUTINE)ProcessIrpsThread, (PVOID)a2);
      if ( v2 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)v2;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a2);
      }
      else
      {
        v2 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, (PVOID *)(a2 + 368), 0);
        if ( v2 < 0 )
        {
          *(_BYTE *)(a2 + 356) = 1;
          KeReleaseSemaphore((PRKSEMAPHORE)(a2 + 608), 0, 1, 1u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a2);
        }
        ZwClose(ThreadHandle);
      }
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v6 = 14;
      goto LABEL_22;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v6 = 11;
LABEL_22:
      WPP_SF_q(v5->AttachedDevice, v6, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140010e64  mov     [rsp+arg_0], rbx
0x140010e69  mov     [rsp+arg_10], rsi
0x140010e6e  push    rdi
0x140010e6f  push    r14
0x140010e71  push    r15
0x140010e73  sub     rsp, 40h
0x140010e77  xor     edi, edi
0x140010e79  mov     rbx, rdx
0x140010e7c  mov     [rsp+58h+ThreadHandle], rdi
0x140010e81  mov     rsi, rcx
0x140010e84  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e8b  lea     r14, WPP_GLOBAL_Control
0x140010e92  lea     r15, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x140010e99  cmp     rcx, r14
0x140010e9c  jz      short loc_140010EB6
0x140010e9e  cmp     byte ptr [rcx+29h], 4
0x140010ea2  jb      short loc_140010EB6
0x140010ea4  mov     rcx, [rcx+18h]
0x140010ea8  lea     edx, [rdi+0Ah]
0x140010eab  mov     r9, rbx
0x140010eae  mov     r8, r15
0x140010eb1  call    WPP_SF_q
0x140010eb6  cmp     [rbx+288h], rdi
0x140010ebd  jnz     short loc_140010EF4
0x140010ebf  mov     rdx, rbx
0x140010ec2  mov     rcx, rsi
0x140010ec5  call    InitializeInterruptContext
0x140010eca  mov     edi, eax
0x140010ecc  test    eax, eax
0x140010ece  jns     short loc_140010EF4
0x140010ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ed7  cmp     rcx, r14
0x140010eda  jz      loc_140011021
0x140010ee0  cmp     byte ptr [rcx+29h], 2
0x140010ee4  jb      loc_140011021
0x140010eea  mov     edx, 0Bh
0x140010eef  jmp     loc_140011012
0x140010ef4  lea     rsi, [rbx+170h]
0x140010efb  cmp     qword ptr [rsi], 0
0x140010eff  jnz     loc_140010FFB
0x140010f05  lea     rax, ProcessIrpsThread
0x140010f0c  mov     [rsp+58h+StartContext], rbx; StartContext
0x140010f11  mov     [rsp+58h+StartRoutine], rax; StartRoutine
0x140010f16  lea     rcx, [rsp+58h+ThreadHandle]; ThreadHandle
0x140010f1b  xor     r9d, r9d; ProcessHandle
0x140010f1e  mov     [rsp+58h+ClientId], 0; ClientId
0x140010f27  xor     r8d, r8d; ObjectAttributes
0x140010f2a  mov     byte ptr [rbx+164h], 0
0x140010f31  xor     edx, edx; DesiredAccess
0x140010f33  call    cs:__imp_PsCreateSystemThread
0x140010f3a  nop     dword ptr [rax+rax+00h]
0x140010f3f  mov     edi, eax
0x140010f41  test    eax, eax
0x140010f43  js      loc_140010FD5
0x140010f49  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x140010f4e  xor     r9d, r9d; AccessMode
0x140010f51  mov     [rsp+58h+StartRoutine], 0; HandleInformation
0x140010f5a  xor     r8d, r8d; ObjectType
0x140010f5d  mov     edx, 1FFFFFh; DesiredAccess
0x140010f62  mov     [rsp+58h+ClientId], rsi; Object
0x140010f67  call    cs:__imp_ObReferenceObjectByHandle
0x140010f6e  nop     dword ptr [rax+rax+00h]
0x140010f73  mov     edi, eax
0x140010f75  test    eax, eax
0x140010f77  jns     short loc_140010FC2
0x140010f79  xor     edx, edx; Increment
0x140010f7b  mov     byte ptr [rbx+164h], 1
0x140010f82  lea     rcx, [rbx+260h]; Semaphore
0x140010f89  mov     r9b, 1; Wait
0x140010f8c  lea     r8d, [rdx+1]; Adjustment
0x140010f90  call    cs:__imp_KeReleaseSemaphore
0x140010f97  nop     dword ptr [rax+rax+00h]
0x140010f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fa3  cmp     rcx, r14
0x140010fa6  jz      short loc_140010FC2
0x140010fa8  cmp     byte ptr [rcx+29h], 2
0x140010fac  jb      short loc_140010FC2
0x140010fae  mov     rcx, [rcx+18h]
0x140010fb2  mov     edx, 0Ch
0x140010fb7  mov     r9, rbx
0x140010fba  mov     r8, r15
0x140010fbd  call    WPP_SF_q
0x140010fc2  mov     rcx, [rsp+58h+ThreadHandle]; Handle
0x140010fc7  call    cs:__imp_ZwClose
0x140010fce  nop     dword ptr [rax+rax+00h]
0x140010fd3  jmp     short loc_140010FFB
0x140010fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fdc  cmp     rcx, r14
0x140010fdf  jz      short loc_140011021
0x140010fe1  cmp     byte ptr [rcx+29h], 2
0x140010fe5  jb      short loc_140010FFB
0x140010fe7  mov     rcx, [rcx+18h]
0x140010feb  mov     edx, 0Dh
0x140010ff0  mov     r9, rbx
0x140010ff3  mov     r8, r15
0x140010ff6  call    WPP_SF_q
0x140010ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011002  cmp     rcx, r14
0x140011005  jz      short loc_140011021
0x140011007  cmp     byte ptr [rcx+29h], 4
0x14001100b  jb      short loc_140011021
0x14001100d  mov     edx, 0Eh
0x140011012  mov     rcx, [rcx+18h]
0x140011016  mov     r9, rbx
0x140011019  mov     r8, r15
0x14001101c  call    WPP_SF_q
0x140011021  mov     rbx, [rsp+58h+arg_0]
0x140011026  mov     eax, edi
0x140011028  mov     rsi, [rsp+58h+arg_10]
0x14001102d  add     rsp, 40h
0x140011031  pop     r15
0x140011033  pop     r14
0x140011035  pop     rdi
0x140011036  retn
```
