# SvcShareCleanup

- ea: `0x140023ae0`
- end: `0x140023bd5`
- name: `SvcShareCleanup`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x140007160`
- `0x14000ef40`
- `0x1400227cc`
- `0x140023ae0`
- `0x140029b7c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140023bad`
- `ntoskrnl!KeBugCheckEx` at `0x140023bad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023b00`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023b39`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023b00`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023b39`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023b5b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023b5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023b7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023bbd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023b7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023bbd`

## pseudocode

```c
__int64 __fastcall SvcShareCleanup(__int64 a1)
{
  struct _ERESOURCE *v1; // rsi
  __int64 v3; // rax
  __int64 v4; // rbx

  v1 = (struct _ERESOURCE *)(a1 + 200);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 200), 1u);
  while ( 1 )
  {
    v3 = RfsTableEnumerate(*(PEX_SPIN_LOCK *)(a1 + 72));
    v4 = v3;
    if ( !v3 )
      break;
    SrvAdminUpdateProvidersOfShare(v3, 2261015);
    ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
    RfsTableRemove(*(PEX_SPIN_LOCK *)(a1 + 72));
    if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), (PVOID)(v4 + 8)) )
      KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\svcshare.c", 0x711u, 0, 0);
    SrvAdminDereferenceShare(v4);
    SrvAdminDereferenceShare(v4);
    ExReleaseResourceLite((PERESOURCE)(a1 + 96));
  }
  ExReleaseResourceLite(v1);
  return 0;
}

```

## disassembly

```asm
0x140023ae0  push    rbx
0x140023ae2  push    rbp
0x140023ae3  push    rsi
0x140023ae4  push    rdi
0x140023ae5  sub     rsp, 38h
0x140023ae9  lea     rsi, [rcx+0C8h]
0x140023af0  mov     [rsp+58h+arg_0], 0
0x140023af8  mov     rdi, rcx
0x140023afb  mov     dl, 1; Wait
0x140023afd  mov     rcx, rsi; Resource
0x140023b00  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140023b07  nop     dword ptr [rax+rax+00h]
0x140023b0c  mov     rcx, [rdi+48h]; SpinLock
0x140023b10  lea     rdx, [rsp+58h+arg_0]
0x140023b15  call    RfsTableEnumerate
0x140023b1a  mov     rbx, rax
0x140023b1d  test    rax, rax
0x140023b20  jz      loc_140023BBA
0x140023b26  mov     edx, 228017h
0x140023b2b  mov     rcx, rax
0x140023b2e  call    SrvAdminUpdateProvidersOfShare
0x140023b33  mov     dl, 1; Wait
0x140023b35  lea     rcx, [rdi+60h]; Resource
0x140023b39  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140023b40  nop     dword ptr [rax+rax+00h]
0x140023b45  mov     edx, [rbx]
0x140023b47  mov     rcx, [rdi+48h]; SpinLock
0x140023b4b  call    RfsTableRemove
0x140023b50  lea     rdx, [rbx+8]; Buffer
0x140023b54  lea     rcx, [rdi+198h]; Table
0x140023b5b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140023b62  nop     dword ptr [rax+rax+00h]
0x140023b67  test    al, al
0x140023b69  jz      short loc_140023B90
0x140023b6b  mov     rcx, rbx
0x140023b6e  call    SrvAdminDereferenceShare
0x140023b73  mov     rcx, rbx
0x140023b76  call    SrvAdminDereferenceShare
0x140023b7b  lea     rcx, [rdi+60h]; Resource
0x140023b7f  call    cs:__imp_ExReleaseResourceLite
0x140023b86  nop     dword ptr [rax+rax+00h]
0x140023b8b  jmp     loc_140023B0C
0x140023b90  xor     r9d, r9d; BugCheckParameter3
0x140023b93  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x140023b9c  mov     r8d, 711h; BugCheckParameter2
0x140023ba2  lea     rdx, aOnecoreBaseFsR; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140023ba9  lea     ecx, [r9+54h]; BugCheckCode
0x140023bad  call    cs:__imp_KeBugCheckEx
0x140023bba  mov     rcx, rsi; Resource
0x140023bbd  call    cs:__imp_ExReleaseResourceLite
0x140023bc4  nop     dword ptr [rax+rax+00h]
0x140023bc9  xor     eax, eax
0x140023bcb  add     rsp, 38h
0x140023bcf  pop     rdi
0x140023bd0  pop     rsi
0x140023bd1  pop     rbp
0x140023bd2  pop     rbx
0x140023bd3  retn
```
