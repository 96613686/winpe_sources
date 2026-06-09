# UdfOplockComplete

- ea: `0x14003a700`
- end: `0x14003a79c`
- name: `UdfOplockComplete`
- size: `156`
- prototype: `void __stdcall(PVOID Context, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400030e0`
- `0x14000c640`
- `0x14003a700`
- `0x1400537b0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003a75f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a75f`

## pseudocode

```c
void __fastcall UdfOplockComplete(__int16 ***Context, PIRP Irp)
{
  NTSTATUS Status; // r8d
  __int16 **v5; // rdx
  char v6; // [rsp+48h] [rbp+10h] BYREF

  Status = Irp->IoStatus.Status;
  v6 = 0;
  if ( Status )
  {
    UdfCompleteRequest(Context, Irp, Status);
  }
  else
  {
    if ( !*((_BYTE *)Context + 56) )
    {
      v5 = Context[5];
      if ( v5 )
      {
        UdfTeardownStructures((__int64)Context, *v5, 0, 0, &v6);
        if ( !v6 )
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)*Context[5] + 17) + 80LL) + 8LL));
        *Context[5] = 0;
        Context[5] = 0;
      }
    }
    UdfAddToWorkque(Context, Irp);
  }
}

```

## disassembly

```asm
0x14003a700  mov     [rsp+arg_0], rbx
0x14003a705  push    rdi
0x14003a706  sub     rsp, 30h
0x14003a70a  mov     r8d, [rdx+30h]
0x14003a70e  mov     rdi, rdx
0x14003a711  mov     [rsp+38h+arg_8], 0
0x14003a716  mov     rbx, rcx
0x14003a719  test    r8d, r8d
0x14003a71c  jnz     short loc_14003A78B
0x14003a71e  cmp     [rcx+38h], r8b
0x14003a722  jnz     short loc_14003A77E
0x14003a724  mov     rdx, [rcx+28h]
0x14003a728  test    rdx, rdx
0x14003a72b  jz      short loc_14003A77E
0x14003a72d  mov     rdx, [rdx]
0x14003a730  lea     rax, [rsp+38h+arg_8]
0x14003a735  xor     r9d, r9d
0x14003a738  mov     [rsp+38h+var_18], rax
0x14003a73d  call    UdfTeardownStructures
0x14003a742  cmp     [rsp+38h+arg_8], 0
0x14003a747  jnz     short loc_14003A76B
0x14003a749  mov     rax, [rbx+28h]
0x14003a74d  mov     rcx, [rax]
0x14003a750  mov     rax, [rcx+88h]
0x14003a757  mov     rcx, [rax+50h]
0x14003a75b  add     rcx, 8; Resource
0x14003a75f  call    cs:__imp_ExReleaseResourceLite
0x14003a766  nop     dword ptr [rax+rax+00h]
0x14003a76b  mov     rax, [rbx+28h]
0x14003a76f  mov     qword ptr [rax], 0
0x14003a776  mov     qword ptr [rbx+28h], 0
0x14003a77e  mov     rdx, rdi; Context2
0x14003a781  mov     rcx, rbx; Context1
0x14003a784  call    UdfAddToWorkque
0x14003a789  jmp     short loc_14003A790
0x14003a78b  call    UdfCompleteRequest
0x14003a790  mov     rbx, [rsp+38h+arg_0]
0x14003a795  add     rsp, 30h
0x14003a799  pop     rdi
0x14003a79a  retn
```
