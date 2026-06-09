# TdxQueryConnectionInfoComplete

- ea: `0x140013900`
- end: `0x1400139a0`
- name: `TdxQueryConnectionInfoComplete`
- size: `160`
- prototype: `__int64 __fastcall(__int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013760`

## callees

- `0x1400047d0`
- `0x140013900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013964`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013964`
- `ntoskrnl!IofCompleteRequest` at `0x140013975`
- `ntoskrnl!IofCompleteRequest` at `0x140013975`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140013944`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140013944`

## string_xrefs

- `0x140013987`: `TdxQueryConnectionInfoComplete`

## pseudocode

```c
__int64 __fastcall TdxQueryConnectionInfoComplete(__int64 *a1, int a2, __int64 a3)
{
  __int64 v3; // rbp
  void *v5; // rsi
  IRP *v6; // rbx
  PMDL MdlAddress; // rdx
  ULONG_PTR v9; // [rsp+60h] [rbp+8h] BYREF

  v3 = *a1;
  v5 = (void *)a1[3];
  v6 = (IRP *)a1[1];
  if ( a2 >= 0 )
  {
    MdlAddress = v6->MdlAddress;
    v9 = 0;
    RtlCopyKernelBufferToMdl(v5, MdlAddress, 0, a3, &v9);
    v6->IoStatus.Information = v9;
  }
  else
  {
    v6->IoStatus.Information = 0;
  }
  v6->IoStatus.Status = a2;
  ExFreePoolWithTag(v5, 0x49436454u);
  IofCompleteRequest(v6, 0);
  return DbgTdxDereferenceConnection(v3, "TdxQueryConnectionInfoComplete", 3202);
}

```

## disassembly

```asm
0x140013900  push    rbx
0x140013902  push    rbp
0x140013903  push    rsi
0x140013904  push    rdi
0x140013905  sub     rsp, 38h
0x140013909  mov     rbp, [rcx]
0x14001390c  mov     edi, edx
0x14001390e  mov     rsi, [rcx+18h]
0x140013912  mov     rbx, [rcx+8]
0x140013916  test    edx, edx
0x140013918  jns     short loc_140013924
0x14001391a  mov     qword ptr [rbx+38h], 0
0x140013922  jmp     short loc_140013959
0x140013924  mov     rdx, [rbx+8]
0x140013928  lea     rax, [rsp+58h+arg_0]
0x14001392d  mov     r9, r8
0x140013930  mov     [rsp+58h+var_38], rax
0x140013935  xor     r8d, r8d
0x140013938  mov     [rsp+58h+arg_0], 0
0x140013941  mov     rcx, rsi
0x140013944  call    cs:__imp_RtlCopyKernelBufferToMdl
0x14001394b  nop     dword ptr [rax+rax+00h]
0x140013950  mov     rax, [rsp+58h+arg_0]
0x140013955  mov     [rbx+38h], rax
0x140013959  mov     edx, 49436454h; Tag
0x14001395e  mov     [rbx+30h], edi
0x140013961  mov     rcx, rsi; P
0x140013964  call    cs:__imp_ExFreePoolWithTag
0x14001396b  nop     dword ptr [rax+rax+00h]
0x140013970  xor     edx, edx; PriorityBoost
0x140013972  mov     rcx, rbx; Irp
0x140013975  call    cs:__imp_IofCompleteRequest
0x14001397c  nop     dword ptr [rax+rax+00h]
0x140013981  mov     r8d, 0C82h
0x140013987  lea     rdx, aTdxqueryconnec; "TdxQueryConnectionInfoComplete"
0x14001398e  mov     rcx, rbp
0x140013991  call    DbgTdxDereferenceConnection
0x140013996  add     rsp, 38h
0x14001399a  pop     rdi
0x14001399b  pop     rsi
0x14001399c  pop     rbp
0x14001399d  pop     rbx
0x14001399e  retn
```
