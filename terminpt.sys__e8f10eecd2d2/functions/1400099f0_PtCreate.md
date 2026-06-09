# PtCreate

- ea: `0x1400099f0`
- end: `0x140009b50`
- name: `PtCreate`
- size: `352`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000af20`

## callees

- `0x14000173c`
- `0x140001a80`
- `0x1400099f0`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140009a5b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140009a5b`
- `ntoskrnl!IofCompleteRequest` at `0x140009ae8`
- `ntoskrnl!IofCompleteRequest` at `0x140009ae8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009b05`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009b05`

## pseudocode

```c
__int64 __fastcall PtCreate(__int64 a1, IRP *a2, int a3)
{
  __int64 v5; // rdi
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // r8d

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      10,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  v5 = *(_QWORD *)(a1 + 64);
  v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 24), PtCreate, File, 1u, 0x20u);
  if ( v7 >= 0 )
  {
    if ( *(_QWORD *)(v5 + 80) )
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)(v5 + 64)) > 1
        && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v8,
          12,
          (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v8,
          11,
          (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
      v7 = -1073741436;
    }
    a2->IoStatus.Status = v7;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 24), PtCreate, 0x20u);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      v8,
      13,
      (__int64)WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400099f0  push    rbx
0x1400099f2  push    rbp
0x1400099f3  push    rsi
0x1400099f4  push    rdi
0x1400099f5  push    r12
0x1400099f7  push    r14
0x1400099f9  push    r15
0x1400099fb  sub     rsp, 40h
0x1400099ff  mov     rsi, rdx
0x140009a02  mov     rbp, rcx
0x140009a05  lea     r15, WPP_RECORDER_INITIALIZED
0x140009a0c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009a13  lea     r12, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x140009a1a  jz      short loc_140009A37
0x140009a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a23  mov     r9d, 0Ah
0x140009a29  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009a2e  mov     rcx, [rcx+40h]
0x140009a32  call    WPP_RECORDER_SF_s
0x140009a37  mov     rdi, [rbp+40h]
0x140009a3b  lea     r8, File; File
0x140009a42  mov     r9d, 1; Line
0x140009a48  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140009a50  lea     rdx, PtCreate; Tag
0x140009a57  lea     rcx, [rdi+18h]; RemoveLock
0x140009a5b  call    cs:__imp_IoAcquireRemoveLockEx
0x140009a62  nop     dword ptr [rax+rax+00h]
0x140009a67  mov     ebx, eax
0x140009a69  test    eax, eax
0x140009a6b  js      loc_140009B11
0x140009a71  cmp     qword ptr [rdi+50h], 0
0x140009a76  jnz     short loc_140009AA3
0x140009a78  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009a7f  jz      short loc_140009A9C
0x140009a81  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a88  mov     r9d, 0Bh
0x140009a8e  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009a93  mov     rcx, [rcx+40h]
0x140009a97  call    WPP_RECORDER_SF_s
0x140009a9c  mov     ebx, 0C0000184h
0x140009aa1  jmp     short loc_140009AD8
0x140009aa3  mov     eax, 1
0x140009aa8  lock xadd [rdi+40h], eax
0x140009aad  inc     eax
0x140009aaf  cmp     eax, 1
0x140009ab2  jle     short loc_140009AD8
0x140009ab4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009abb  jz      short loc_140009AD8
0x140009abd  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ac4  mov     r9d, 0Ch
0x140009aca  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009acf  mov     rcx, [rcx+40h]
0x140009ad3  call    WPP_RECORDER_SF_s
0x140009ad8  xor     edx, edx; PriorityBoost
0x140009ada  mov     [rsi+30h], ebx
0x140009add  mov     rcx, rsi; Irp
0x140009ae0  mov     qword ptr [rsi+38h], 0
0x140009ae8  call    cs:__imp_IofCompleteRequest
0x140009aef  nop     dword ptr [rax+rax+00h]
0x140009af4  mov     r8d, 20h ; ' '; RemlockSize
0x140009afa  lea     rdx, PtCreate; Tag
0x140009b01  lea     rcx, [rdi+18h]; RemoveLock
0x140009b05  call    cs:__imp_IoReleaseRemoveLockEx
0x140009b0c  nop     dword ptr [rax+rax+00h]
0x140009b11  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009b18  jz      short loc_140009B3E
0x140009b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b21  mov     r9d, 0Dh
0x140009b27  mov     [rsp+78h+var_40], ebx
0x140009b2b  mov     [rsp+78h+var_48], rbp
0x140009b30  mov     qword ptr [rsp+78h+RemlockSize], r12
0x140009b35  mov     rcx, [rcx+40h]
0x140009b39  call    WPP_RECORDER_SF_sqd
0x140009b3e  mov     eax, ebx
0x140009b40  add     rsp, 40h
0x140009b44  pop     r15
0x140009b46  pop     r14
0x140009b48  pop     r12
0x140009b4a  pop     rdi
0x140009b4b  pop     rsi
0x140009b4c  pop     rbp
0x140009b4d  pop     rbx
0x140009b4e  retn
```
