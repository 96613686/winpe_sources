# RootFileReadWritePreprocess

- ea: `0x140006c20`
- end: `0x140006c9a`
- name: `RootFileReadWritePreprocess`
- size: `122`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002000`
- `0x140002380`
- `0x140006c20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006c80`
- `ntoskrnl!IofCompleteRequest` at `0x140006c80`

## pseudocode

```c
__int64 __fastcall RootFileReadWritePreprocess(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  PVOID FsContext; // rcx
  KSPIN_LOCK *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FsContext = CurrentStackLocation->FileObject->FsContext;
  if ( *((_DWORD *)FsContext + 2) != 7 || (*((_BYTE *)FsContext + 232) & 0x10) == 0 )
  {
    v7 = -1073741808;
LABEL_9:
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
    return v7;
  }
  v5 = (KSPIN_LOCK *)*((_QWORD *)FsContext + 47);
  if ( CurrentStackLocation->MajorFunction == 3 )
    v6 = PipeRead(v5, (__int64)a2);
  else
    v6 = PipeWrite(v5);
  v7 = v6;
  if ( v6 != 259 )
    goto LABEL_9;
  return v7;
}

```

## disassembly

```asm
0x140006c20  mov     [rsp+arg_0], rbx
0x140006c25  push    rdi
0x140006c26  sub     rsp, 20h
0x140006c2a  mov     rdi, rdx
0x140006c2d  mov     rdx, [rdx+0B8h]
0x140006c34  mov     rax, [rdx+30h]
0x140006c38  mov     rcx, [rax+18h]
0x140006c3c  mov     eax, [rcx+8]
0x140006c3f  cmp     eax, 7
0x140006c42  jnz     short loc_140006C73
0x140006c44  test    byte ptr [rcx+0E8h], 10h
0x140006c4b  jz      short loc_140006C73
0x140006c4d  cmp     byte ptr [rdx], 3
0x140006c50  mov     rdx, rdi
0x140006c53  mov     rcx, [rcx+178h]; SpinLock
0x140006c5a  jnz     short loc_140006C63
0x140006c5c  call    PipeRead
0x140006c61  jmp     short loc_140006C68
0x140006c63  call    PipeWrite
0x140006c68  mov     ebx, eax
0x140006c6a  cmp     eax, 103h
0x140006c6f  jz      short loc_140006C8C
0x140006c71  jmp     short loc_140006C78
0x140006c73  mov     ebx, 0C0000010h
0x140006c78  xor     edx, edx; PriorityBoost
0x140006c7a  mov     [rdi+30h], ebx
0x140006c7d  mov     rcx, rdi; Irp
0x140006c80  call    cs:__imp_IofCompleteRequest
0x140006c87  nop     dword ptr [rax+rax+00h]
0x140006c8c  mov     eax, ebx
0x140006c8e  mov     rbx, [rsp+28h+arg_0]
0x140006c93  add     rsp, 20h
0x140006c97  pop     rdi
0x140006c98  retn
```
