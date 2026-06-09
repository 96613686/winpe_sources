# SrvAdminRemoveAllShares

- ea: `0x140026064`
- end: `0x140026131`
- name: `SrvAdminRemoveAllShares`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014284`

## callees

- `0x140007160`
- `0x14000ef40`
- `0x140026064`
- `0x140029b7c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140026113`
- `ntoskrnl!KeBugCheckEx` at `0x140026113`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002609e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002609e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400260c0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400260c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400260e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400260e4`

## pseudocode

```c
__int64 __fastcall SrvAdminRemoveAllShares(__int64 a1)
{
  volatile LONG *i; // rcx
  __int64 result; // rax
  __int64 v4; // rbx

  for ( i = *(volatile LONG **)(a1 + 72); ; i = *(volatile LONG **)(a1 + 72) )
  {
    result = RfsTableEnumerate(i);
    v4 = result;
    if ( !result )
      break;
    ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
    RfsTableRemove(*(PEX_SPIN_LOCK *)(a1 + 72));
    if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), (PVOID)(v4 + 8)) )
      KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\sashare.c", 0x494u, 0, 0);
    SrvAdminDereferenceShare(v4);
    SrvAdminDereferenceShare(v4);
    ExReleaseResourceLite((PERESOURCE)(a1 + 96));
  }
  return result;
}

```

## disassembly

```asm
0x140026064  mov     [rsp+arg_8], rbx
0x140026069  mov     [rsp+arg_10], rsi
0x14002606e  push    rdi
0x14002606f  sub     rsp, 30h
0x140026073  mov     rdi, rcx
0x140026076  mov     [rsp+38h+arg_0], 0
0x14002607e  mov     rcx, [rcx+48h]; SpinLock
0x140026082  lea     rdx, [rsp+38h+arg_0]
0x140026087  call    RfsTableEnumerate
0x14002608c  mov     rbx, rax
0x14002608f  test    rax, rax
0x140026092  jz      loc_140026120
0x140026098  mov     dl, 1; Wait
0x14002609a  lea     rcx, [rdi+60h]; Resource
0x14002609e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400260a5  nop     dword ptr [rax+rax+00h]
0x1400260aa  mov     edx, [rbx]
0x1400260ac  mov     rcx, [rdi+48h]; SpinLock
0x1400260b0  call    RfsTableRemove
0x1400260b5  lea     rdx, [rbx+8]; Buffer
0x1400260b9  lea     rcx, [rdi+198h]; Table
0x1400260c0  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400260c7  nop     dword ptr [rax+rax+00h]
0x1400260cc  test    al, al
0x1400260ce  jz      short loc_1400260F6
0x1400260d0  mov     rcx, rbx
0x1400260d3  call    SrvAdminDereferenceShare
0x1400260d8  mov     rcx, rbx
0x1400260db  call    SrvAdminDereferenceShare
0x1400260e0  lea     rcx, [rdi+60h]; Resource
0x1400260e4  call    cs:__imp_ExReleaseResourceLite
0x1400260eb  nop     dword ptr [rax+rax+00h]
0x1400260f0  mov     rcx, [rdi+48h]
0x1400260f4  jmp     short loc_140026082
0x1400260f6  xor     r9d, r9d; BugCheckParameter3
0x1400260f9  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140026102  mov     r8d, 494h; BugCheckParameter2
0x140026108  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14002610f  lea     ecx, [r9+54h]; BugCheckCode
0x140026113  call    cs:__imp_KeBugCheckEx
0x140026120  mov     rbx, [rsp+38h+arg_8]
0x140026125  mov     rsi, [rsp+38h+arg_10]
0x14002612a  add     rsp, 30h
0x14002612e  pop     rdi
0x14002612f  retn
```
