# MpAsyncScanWorkerThread

- ea: `0x1400661b0`
- end: `0x140066398`
- name: `MpAsyncScanWorkerThread`
- size: `488`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003d20`
- `0x1400051bc`
- `0x1400118d0`
- `0x140055d50`
- `0x140056dc0`
- `0x1400661b0`
- `0x1400663a0`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400662a8`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400662a8`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140066219`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140066286`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140066219`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140066286`

## pseudocode

```c
void __fastcall MpAsyncScanWorkerThread(PVOID StartContext)
{
  NTSTATUS v2; // eax
  bool v3; // sf
  int v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // rdx
  KPROCESSOR_MODE WaitMode[4]; // [rsp+20h] [rbp-48h]
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  PVOID Object[2]; // [rsp+48h] [rbp-20h] BYREF

  v8 = 0;
  Object[0] = (char *)MpAsyncScanData + 144;
  Object[1] = (char *)MpAsyncScanData + 168;
  v2 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
  v3 = v2 < 0;
  if ( v2 )
  {
    while ( !v3 )
    {
      v4 = MpAsyncScanDequeue(&v8);
      if ( v4 >= 0 )
      {
        v5 = v8;
        *(_DWORD *)(v8 + 40) |= 1u;
        if ( !*(_BYTE *)(MpData + 2464) || *(_QWORD *)(MpData + 2472) )
          MpDoScanFile(v5);
        MpCleanupScanRequestContext(&v8);
        goto LABEL_5;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        v6 = 25;
        *(_DWORD *)WaitMode = v4;
LABEL_18:
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v6,
          WPP_e14b9b336f94348117623c9565965302_Traceguids,
          KeGetCurrentThread(),
          *(_DWORD *)WaitMode);
      }
LABEL_5:
      v8 = 0;
      v2 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
      v3 = v2 < 0;
      if ( !v2 )
        goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_5;
    v6 = 24;
    *(_DWORD *)WaitMode = v2;
    goto LABEL_18;
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e14b9b336f94348117623c9565965302_Traceguids, StartContext);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400661b0  mov     r11, rsp
0x1400661b3  mov     [r11+10h], rbx
0x1400661b7  mov     [r11+18h], rsi
0x1400661bb  push    rdi
0x1400661bc  sub     rsp, 60h
0x1400661c0  mov     rax, cs:__security_cookie
0x1400661c7  xor     rax, rsp
0x1400661ca  mov     [rsp+68h+var_10], rax
0x1400661cf  xor     edi, edi
0x1400661d1  lea     rdx, [r11-20h]; Object
0x1400661d5  mov     [r11-30h], rdi
0x1400661d9  mov     rbx, rcx
0x1400661dc  mov     rcx, cs:MpAsyncScanData
0x1400661e3  xor     r9d, r9d; WaitReason
0x1400661e6  mov     [r11-38h], rdi
0x1400661ea  mov     r8d, 1; WaitType
0x1400661f0  mov     [rsp+68h+Alertable], dil; Alertable
0x1400661f5  mov     [r11-28h], rdi
0x1400661f9  lea     rax, [rcx+90h]
0x140066200  mov     [rsp+68h+WaitMode], dil; WaitMode
0x140066205  mov     [r11-20h], rax
0x140066209  lea     rax, [rcx+0A8h]
0x140066210  mov     ecx, 2; Count
0x140066215  mov     [r11-18h], rax
0x140066219  call    cs:__imp_KeWaitForMultipleObjects
0x140066220  nop     dword ptr [rax+rax+00h]
0x140066225  lea     rsi, WPP_GLOBAL_Control
0x14006622c  test    eax, eax
0x14006622e  jz      short loc_140066296
0x140066230  js      loc_14006630D
0x140066236  lea     rcx, [rsp+68h+var_28]
0x14006623b  call    MpAsyncScanDequeue
0x140066240  mov     ecx, eax
0x140066242  test    eax, eax
0x140066244  jns     loc_1400662D5
0x14006624a  mov     rax, cs:WPP_GLOBAL_Control
0x140066251  cmp     rax, rsi
0x140066254  jnz     loc_140066334
0x14006625a  mov     [rsp+68h+WaitBlockArray], rdi; WaitBlockArray
0x14006625f  lea     rdx, [rsp+68h+Object]; Object
0x140066264  mov     [rsp+68h+Timeout], rdi; Timeout
0x140066269  xor     r9d, r9d; WaitReason
0x14006626c  mov     [rsp+68h+Alertable], dil; Alertable
0x140066271  mov     r8d, 1; WaitType
0x140066277  mov     ecx, 2; Count
0x14006627c  mov     [rsp+68h+WaitMode], dil; WaitMode
0x140066281  mov     [rsp+68h+var_28], rdi
0x140066286  call    cs:__imp_KeWaitForMultipleObjects
0x14006628d  nop     dword ptr [rax+rax+00h]
0x140066292  test    eax, eax
0x140066294  jnz     short loc_140066230
0x140066296  mov     rcx, cs:WPP_GLOBAL_Control
0x14006629d  cmp     rcx, rsi
0x1400662a0  jnz     loc_140066370
0x1400662a6  xor     ecx, ecx; ExitStatus
0x1400662a8  call    cs:__imp_PsTerminateSystemThread
0x1400662af  nop     dword ptr [rax+rax+00h]
0x1400662b4  mov     rcx, [rsp+68h+var_10]
0x1400662b9  xor     rcx, rsp; StackCookie
0x1400662bc  call    __security_check_cookie
0x1400662c1  mov     rbx, [rsp+68h+arg_8]
0x1400662c6  mov     rsi, [rsp+68h+arg_10]
0x1400662ce  add     rsp, 60h
0x1400662d2  pop     rdi
0x1400662d3  retn
0x1400662d5  mov     rcx, [rsp+68h+var_28]
0x1400662da  or      dword ptr [rcx+28h], 1
0x1400662de  mov     rax, cs:MpData
0x1400662e5  cmp     [rax+9A0h], dil
0x1400662ec  jnz     short loc_140066302
0x1400662ee  call    MpDoScanFile
0x1400662f3  lea     rcx, [rsp+68h+var_28]
0x1400662f8  call    MpCleanupScanRequestContext
0x1400662fd  jmp     loc_14006625A
0x140066302  cmp     [rax+9A8h], rdi
0x140066309  jnz     short loc_1400662EE
0x14006630b  jmp     short loc_1400662F3
0x14006630d  mov     rcx, cs:WPP_GLOBAL_Control
0x140066314  cmp     rcx, rsi
0x140066317  jz      loc_14006625A
0x14006631d  mov     ecx, [rcx+2Ch]
0x140066320  test    cl, 1
0x140066323  jz      loc_14006625A
0x140066329  mov     edx, 18h
0x14006632e  mov     dword ptr [rsp+68h+WaitMode], eax
0x140066332  jmp     short loc_14006634B
0x140066334  mov     eax, [rax+2Ch]
0x140066337  test    al, 1
0x140066339  jz      loc_14006625A
0x14006633f  lfence
0x140066342  mov     edx, 19h
0x140066347  mov     dword ptr [rsp+68h+WaitMode], ecx
0x14006634b  mov     r9, gs:188h
0x140066354  lea     r8, WPP_e14b9b336f94348117623c9565965302_Traceguids
0x14006635b  mov     rcx, cs:WPP_GLOBAL_Control
0x140066362  mov     rcx, [rcx+18h]
0x140066366  call    WPP_SF_qD
0x14006636b  jmp     loc_14006625A
0x140066370  mov     eax, [rcx+2Ch]
0x140066373  test    al, 4
0x140066375  jz      loc_1400662A6
0x14006637b  mov     rcx, [rcx+18h]
0x14006637f  lea     r8, WPP_e14b9b336f94348117623c9565965302_Traceguids
0x140066386  mov     edx, 17h
0x14006638b  mov     r9, rbx
0x14006638e  call    WPP_SF_q
0x140066393  jmp     loc_1400662A6
```
