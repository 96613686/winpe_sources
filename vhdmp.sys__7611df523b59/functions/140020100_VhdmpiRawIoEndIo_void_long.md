# VhdmpiRawIoEndIo(void *,long)

- ea: `0x140020100`
- end: `0x14002017d`
- name: `?VhdmpiRawIoEndIo@@YAXPEAXJ@Z`
- size: `125`
- prototype: `void __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400e23a4`

## callees

- `0x140020100`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002013a`
- `ntoskrnl!IofCompleteRequest` at `0x14002013a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002014d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002014d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020165`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020165`

## pseudocode

```c
void __fastcall VhdmpiRawIoEndIo(void *a1, int a2)
{
  IRP *v3; // rcx
  ULONG_PTR v4; // rax
  struct _EX_RUNDOWN_REF *FsContext2; // rbx

  v3 = *(IRP **)(*(_QWORD *)a1 + 96LL);
  v3->IoStatus.Status = a2;
  if ( a2 >= 0 )
    v4 = *(unsigned int *)(*(_QWORD *)a1 + 52LL);
  else
    v4 = 0;
  v3->IoStatus.Information = v4;
  FsContext2 = (struct _EX_RUNDOWN_REF *)v3->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2;
  IofCompleteRequest(v3, 0);
  ExReleaseRundownProtection(FsContext2 + 33);
  ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)a1 - 16LL), 0x61444856u);
}

```

## disassembly

```asm
0x140020100  mov     [rsp+arg_0], rbx
0x140020105  push    rdi
0x140020106  sub     rsp, 20h
0x14002010a  mov     rax, [rcx]
0x14002010d  mov     rdi, rcx
0x140020110  mov     rcx, [rax+60h]; Irp
0x140020114  mov     [rcx+30h], edx
0x140020117  test    edx, edx
0x140020119  jns     short loc_14002011F
0x14002011b  xor     eax, eax
0x14002011d  jmp     short loc_140020125
0x14002011f  mov     rax, [rdi]
0x140020122  mov     eax, [rax+34h]
0x140020125  mov     [rcx+38h], rax
0x140020129  mov     rax, [rcx+0B8h]
0x140020130  mov     rdx, [rax+30h]
0x140020134  mov     rbx, [rdx+20h]
0x140020138  xor     edx, edx; PriorityBoost
0x14002013a  call    cs:__imp_IofCompleteRequest
0x140020141  nop     dword ptr [rax+rax+00h]
0x140020146  lea     rcx, [rbx+108h]; RunRef
0x14002014d  call    cs:__imp_ExReleaseRundownProtection
0x140020154  nop     dword ptr [rax+rax+00h]
0x140020159  mov     rcx, [rdi]
0x14002015c  mov     edx, 61444856h; Tag
0x140020161  mov     rcx, [rcx-10h]; P
0x140020165  call    cs:__imp_ExFreePoolWithTag
0x14002016c  nop     dword ptr [rax+rax+00h]
0x140020171  mov     rbx, [rsp+28h+arg_0]
0x140020176  add     rsp, 20h
0x14002017a  pop     rdi
0x14002017b  retn
```
