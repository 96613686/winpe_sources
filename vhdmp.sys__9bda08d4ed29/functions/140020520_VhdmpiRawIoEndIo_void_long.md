# VhdmpiRawIoEndIo(void *,long)

- ea: `0x140020520`
- end: `0x14002059d`
- name: `?VhdmpiRawIoEndIo@@YAXPEAXJ@Z`
- size: `125`
- prototype: `void __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400e2334`

## callees

- `0x140020520`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002055a`
- `ntoskrnl!IofCompleteRequest` at `0x14002055a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002056d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002056d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020585`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020585`

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
0x140020520  mov     [rsp+arg_0], rbx
0x140020525  push    rdi
0x140020526  sub     rsp, 20h
0x14002052a  mov     rax, [rcx]
0x14002052d  mov     rdi, rcx
0x140020530  mov     rcx, [rax+60h]; Irp
0x140020534  mov     [rcx+30h], edx
0x140020537  test    edx, edx
0x140020539  jns     short loc_14002053F
0x14002053b  xor     eax, eax
0x14002053d  jmp     short loc_140020545
0x14002053f  mov     rax, [rdi]
0x140020542  mov     eax, [rax+34h]
0x140020545  mov     [rcx+38h], rax
0x140020549  mov     rax, [rcx+0B8h]
0x140020550  mov     rdx, [rax+30h]
0x140020554  mov     rbx, [rdx+20h]
0x140020558  xor     edx, edx; PriorityBoost
0x14002055a  call    cs:__imp_IofCompleteRequest
0x140020561  nop     dword ptr [rax+rax+00h]
0x140020566  lea     rcx, [rbx+108h]; RunRef
0x14002056d  call    cs:__imp_ExReleaseRundownProtection
0x140020574  nop     dword ptr [rax+rax+00h]
0x140020579  mov     rcx, [rdi]
0x14002057c  mov     edx, 61444856h; Tag
0x140020581  mov     rcx, [rcx-10h]; P
0x140020585  call    cs:__imp_ExFreePoolWithTag
0x14002058c  nop     dword ptr [rax+rax+00h]
0x140020591  mov     rbx, [rsp+28h+arg_0]
0x140020596  add     rsp, 20h
0x14002059a  pop     rdi
0x14002059b  retn
```
