# Srv2FreeInstance

- ea: `0x14005daf8`
- end: `0x14005dbcf`
- name: `Srv2FreeInstance`
- size: `215`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14005dbe0`

## callees

- `0x14000c3f0`
- `0x1400222ec`
- `0x14005daf8`
- `0x140060828`
- `0x140061ea4`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005db8a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005db8a`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005dba6`
- `ntoskrnl!IoUninitializeWorkItem` at `0x14005dba6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005dbb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005dbb7`

## pseudocode

```c
__int64 __fastcall Srv2FreeInstance(char *P)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_ce36e4dedee63ec6b47e75c75daf32d1_Traceguids, P);
  }
  if ( P[168] )
    Smb2ProviderCleanupInstance((__int64)P);
  v2 = (void *)*((_QWORD *)P + 19);
  if ( v2 )
    RfsThreadPoolClose(v2);
  v3 = (void *)*((_QWORD *)P + 18);
  if ( v3 )
    RfsThreadPoolClose(v3);
  v4 = (void *)*((_QWORD *)P + 17);
  if ( v4 )
    RfsThreadPoolClose(v4);
  if ( P[171] )
    ExDeleteResourceLite((PERESOURCE)(P + 16));
  if ( P[172] )
    IoUninitializeWorkItem(*((PIO_WORKITEM *)P + 25));
  ExFreePoolWithTag(P, 0);
  return Srv2DereferenceDriver();
}

```

## disassembly

```asm
0x14005daf8  push    rbx
0x14005dafa  sub     rsp, 20h
0x14005dafe  mov     rbx, rcx
0x14005db01  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005db08  lea     rax, WPP_GLOBAL_Control
0x14005db0f  cmp     rcx, rax
0x14005db12  jz      short loc_14005DB39
0x14005db14  mov     eax, [rcx+2Ch]
0x14005db17  test    al, 1
0x14005db19  jz      short loc_14005DB39
0x14005db1b  cmp     byte ptr [rcx+29h], 2
0x14005db1f  jb      short loc_14005DB39
0x14005db21  mov     rcx, [rcx+18h]
0x14005db25  lea     r8, WPP_ce36e4dedee63ec6b47e75c75daf32d1_Traceguids
0x14005db2c  mov     edx, 0Ah
0x14005db31  mov     r9, rbx
0x14005db34  call    WPP_SF_q
0x14005db39  cmp     byte ptr [rbx+0A8h], 0
0x14005db40  jz      short loc_14005DB4A
0x14005db42  mov     rcx, rbx
0x14005db45  call    Smb2ProviderCleanupInstance
0x14005db4a  mov     rcx, [rbx+98h]; P
0x14005db51  test    rcx, rcx
0x14005db54  jz      short loc_14005DB5B
0x14005db56  call    RfsThreadPoolClose
0x14005db5b  mov     rcx, [rbx+90h]; P
0x14005db62  test    rcx, rcx
0x14005db65  jz      short loc_14005DB6C
0x14005db67  call    RfsThreadPoolClose
0x14005db6c  mov     rcx, [rbx+88h]; P
0x14005db73  test    rcx, rcx
0x14005db76  jz      short loc_14005DB7D
0x14005db78  call    RfsThreadPoolClose
0x14005db7d  cmp     byte ptr [rbx+0ABh], 0
0x14005db84  jz      short loc_14005DB96
0x14005db86  lea     rcx, [rbx+10h]; Resource
0x14005db8a  call    cs:__imp_ExDeleteResourceLite
0x14005db91  nop     dword ptr [rax+rax+00h]
0x14005db96  cmp     byte ptr [rbx+0ACh], 0
0x14005db9d  jz      short loc_14005DBB2
0x14005db9f  mov     rcx, [rbx+0C8h]; IoWorkItem
0x14005dba6  call    cs:__imp_IoUninitializeWorkItem
0x14005dbad  nop     dword ptr [rax+rax+00h]
0x14005dbb2  xor     edx, edx; Tag
0x14005dbb4  mov     rcx, rbx; P
0x14005dbb7  call    cs:__imp_ExFreePoolWithTag
0x14005dbbe  nop     dword ptr [rax+rax+00h]
0x14005dbc3  call    Srv2DereferenceDriver
0x14005dbc8  add     rsp, 20h
0x14005dbcc  pop     rbx
0x14005dbcd  retn
```
