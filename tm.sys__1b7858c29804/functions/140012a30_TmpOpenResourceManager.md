# TmpOpenResourceManager

- ea: `0x140012a30`
- end: `0x140012b9b`
- name: `TmpOpenResourceManager`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140012a30`
- `0x14001d510`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140012a56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012a83`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012af0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012a56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012a83`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012af0`
- `ntoskrnl!KeReleaseMutex` at `0x140012acd`
- `ntoskrnl!KeReleaseMutex` at `0x140012b08`
- `ntoskrnl!KeReleaseMutex` at `0x140012b1d`
- `ntoskrnl!KeReleaseMutex` at `0x140012acd`
- `ntoskrnl!KeReleaseMutex` at `0x140012b08`
- `ntoskrnl!KeReleaseMutex` at `0x140012b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b79`
- `ntoskrnl!ObfDereferenceObject` at `0x140012b5d`
- `ntoskrnl!ObfDereferenceObject` at `0x140012b5d`
- `ntoskrnl!KeResetEvent` at `0x140012abc`
- `ntoskrnl!KeResetEvent` at `0x140012abc`
- `ntoskrnl!KeInitializeQueue` at `0x140012aad`
- `ntoskrnl!KeInitializeQueue` at `0x140012aad`
- `ntoskrnl!KeRundownQueue` at `0x140012a99`
- `ntoskrnl!KeRundownQueue` at `0x140012a99`

## pseudocode

```c
__int64 __fastcall TmpOpenResourceManager(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PLIST_ENTRY v5; // rbp
  unsigned int v6; // r14d
  int v7; // ebx
  _QWORD *p_Flink; // rbx
  void *v9; // rcx
  void *v10; // rdi

  v5 = 0;
  v6 = 0;
  KeWaitForSingleObject((PVOID)(a4 + 40), Executive, 0, 0, 0);
  if ( *(_DWORD *)(a4 + 28) == 1 )
  {
    KeWaitForSingleObject((PVOID)(a4 + 216), Executive, 0, 0, 0);
    v5 = KeRundownQueue((PRKQUEUE)(a4 + 152));
    KeInitializeQueue((PRKQUEUE)(a4 + 152), 0);
    KeResetEvent((PRKEVENT)a4);
    KeReleaseMutex((PRKMUTEX)(a4 + 216), 0);
    KeWaitForSingleObject((PVOID)(a4 + 488), Executive, 0, 0, 0);
    *(_BYTE *)(a4 + 548) = 0;
    KeReleaseMutex((PRKMUTEX)(a4 + 488), 0);
  }
  v7 = *(_DWORD *)(a4 + 32);
  KeReleaseMutex((PRKMUTEX)(a4 + 40), 0);
  if ( (v7 & 8) != 0 )
    v6 = TmpNamespaceForEach(&TmpTmNamespace);
  if ( v5 )
  {
    p_Flink = &v5->Flink;
    do
    {
      v9 = (void *)p_Flink[2];
      v10 = p_Flink;
      if ( v9 )
      {
        ObfDereferenceObject(v9);
        p_Flink[2] = 0;
      }
      p_Flink = (_QWORD *)*p_Flink;
      ExFreePoolWithTag(v10, 0);
    }
    while ( v5 != (PLIST_ENTRY)p_Flink );
  }
  return v6;
}

```

## disassembly

```asm
0x140012a30  push    rbx
0x140012a32  push    rbp
0x140012a33  push    rsi
0x140012a34  push    rdi
0x140012a35  push    r14
0x140012a37  push    r15
0x140012a39  sub     rsp, 38h
0x140012a3d  mov     rsi, r9
0x140012a40  xor     ebp, ebp
0x140012a42  xor     r9d, r9d; Alertable
0x140012a45  mov     [rsp+68h+Timeout], rbp; Timeout
0x140012a4a  xor     r8d, r8d; WaitMode
0x140012a4d  xor     edx, edx; WaitReason
0x140012a4f  xor     r14d, r14d
0x140012a52  lea     rcx, [rsi+28h]; Object
0x140012a56  call    cs:__imp_KeWaitForSingleObject
0x140012a5d  nop     dword ptr [rax+rax+00h]
0x140012a62  cmp     dword ptr [rsi+1Ch], 1
0x140012a66  jnz     loc_140012B14
0x140012a6c  lea     rdi, [rsi+0D8h]
0x140012a73  mov     [rsp+68h+Timeout], rbp; Timeout
0x140012a78  mov     rcx, rdi; Object
0x140012a7b  xor     r9d, r9d; Alertable
0x140012a7e  xor     r8d, r8d; WaitMode
0x140012a81  xor     edx, edx; WaitReason
0x140012a83  call    cs:__imp_KeWaitForSingleObject
0x140012a8a  nop     dword ptr [rax+rax+00h]
0x140012a8f  lea     rbx, [rsi+98h]
0x140012a96  mov     rcx, rbx; Queue
0x140012a99  call    cs:__imp_KeRundownQueue
0x140012aa0  nop     dword ptr [rax+rax+00h]
0x140012aa5  xor     edx, edx; Count
0x140012aa7  mov     rcx, rbx; Queue
0x140012aaa  mov     rbp, rax
0x140012aad  call    cs:__imp_KeInitializeQueue
0x140012ab4  nop     dword ptr [rax+rax+00h]
0x140012ab9  mov     rcx, rsi; Event
0x140012abc  call    cs:__imp_KeResetEvent
0x140012ac3  nop     dword ptr [rax+rax+00h]
0x140012ac8  xor     edx, edx; Wait
0x140012aca  mov     rcx, rdi; Mutex
0x140012acd  call    cs:__imp_KeReleaseMutex
0x140012ad4  nop     dword ptr [rax+rax+00h]
0x140012ad9  lea     rbx, [rsi+1E8h]
0x140012ae0  mov     [rsp+68h+Timeout], r14; Timeout
0x140012ae5  mov     rcx, rbx; Object
0x140012ae8  xor     r9d, r9d; Alertable
0x140012aeb  xor     r8d, r8d; WaitMode
0x140012aee  xor     edx, edx; WaitReason
0x140012af0  call    cs:__imp_KeWaitForSingleObject
0x140012af7  nop     dword ptr [rax+rax+00h]
0x140012afc  xor     edx, edx; Wait
0x140012afe  mov     [rsi+224h], r14b
0x140012b05  mov     rcx, rbx; Mutex
0x140012b08  call    cs:__imp_KeReleaseMutex
0x140012b0f  nop     dword ptr [rax+rax+00h]
0x140012b14  mov     ebx, [rsi+20h]
0x140012b17  lea     rcx, [rsi+28h]; Mutex
0x140012b1b  xor     edx, edx; Wait
0x140012b1d  call    cs:__imp_KeReleaseMutex
0x140012b24  nop     dword ptr [rax+rax+00h]
0x140012b29  test    bl, 8
0x140012b2c  jz      short loc_140012B49
0x140012b2e  mov     r9, rsi
0x140012b31  lea     r8, TmpNotifyResourceManagerTmOnline
0x140012b38  xor     edx, edx
0x140012b3a  lea     rcx, TmpTmNamespace; Table
0x140012b41  call    TmpNamespaceForEach
0x140012b46  mov     r14d, eax
0x140012b49  test    rbp, rbp
0x140012b4c  jz      short loc_140012B8A
0x140012b4e  mov     rbx, rbp
0x140012b51  mov     rcx, [rbx+10h]; Object
0x140012b55  mov     rdi, rbx
0x140012b58  test    rcx, rcx
0x140012b5b  jz      short loc_140012B71
0x140012b5d  call    cs:__imp_ObfDereferenceObject
0x140012b64  nop     dword ptr [rax+rax+00h]
0x140012b69  mov     qword ptr [rbx+10h], 0
0x140012b71  mov     rbx, [rbx]
0x140012b74  xor     edx, edx; Tag
0x140012b76  mov     rcx, rdi; P
0x140012b79  call    cs:__imp_ExFreePoolWithTag
0x140012b80  nop     dword ptr [rax+rax+00h]
0x140012b85  cmp     rbp, rbx
0x140012b88  jnz     short loc_140012B51
0x140012b8a  mov     eax, r14d
0x140012b8d  add     rsp, 38h
0x140012b91  pop     r15
0x140012b93  pop     r14
0x140012b95  pop     rdi
0x140012b96  pop     rsi
0x140012b97  pop     rbp
0x140012b98  pop     rbx
0x140012b99  retn
```
