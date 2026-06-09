# UdfIsVolumeMounted

- ea: `0x14002e280`
- end: `0x14002e315`
- name: `UdfIsVolumeMounted`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x14002e280`
- `0x1400444c4`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b1ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002e2ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b1ee`

## pseudocode

```c
__int64 __fastcall UdfIsVolumeMounted(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r8

  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL);
  v5 = *(_QWORD *)(v4 + 32);
  *(_QWORD *)(v4 + 32) = v5;
  if ( (v5 & 7) != 0 && *(_QWORD *)(v4 + 24) )
  {
    *(_DWORD *)(a1 + 28) |= 0x200u;
    UdfAcquireResource(a1, *(_QWORD *)(a1 + 16) + 1480LL, 0, 1);
    UdfVerifyVcb(a1, *(_QWORD *)(a1 + 16), v6);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 16) + 1480LL));
  }
  UdfCompleteRequest(a1, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14002e280  mov     [rsp+arg_8], rbx
0x14002e285  mov     [rsp+arg_0], rcx
0x14002e28a  push    rdi
0x14002e28b  sub     rsp, 20h
0x14002e28f  mov     rdi, rdx
0x14002e292  mov     rbx, rcx
0x14002e295  mov     rax, [rdx+0B8h]
0x14002e29c  mov     rcx, [rax+30h]
0x14002e2a0  mov     rax, [rcx+20h]
0x14002e2a4  mov     [rcx+20h], rax
0x14002e2a8  test    al, 7
0x14002e2aa  jz      short loc_14002E2F9
0x14002e2ac  cmp     qword ptr [rcx+18h], 0
0x14002e2b1  jz      short loc_14002E2F9
0x14002e2b3  bts     dword ptr [rbx+1Ch], 9
0x14002e2b8  mov     rdx, [rbx+10h]
0x14002e2bc  add     rdx, 5C8h
0x14002e2c3  mov     r9d, 1
0x14002e2c9  xor     r8d, r8d
0x14002e2cc  mov     rcx, rbx
0x14002e2cf  call    UdfAcquireResource
0x14002e2d4  nop
0x14002e2d5  mov     rdx, [rbx+10h]
0x14002e2d9  mov     rcx, rbx
0x14002e2dc  call    UdfVerifyVcb
0x14002e2e1  nop
0x14002e2e2  mov     rcx, [rbx+10h]
0x14002e2e6  add     rcx, 5C8h; Resource
0x14002e2ed  call    cs:__imp_ExReleaseResourceLite
0x14002e2f4  nop     dword ptr [rax+rax+00h]
0x14002e2f9  xor     r8d, r8d
0x14002e2fc  mov     rdx, rdi
0x14002e2ff  mov     rcx, rbx
0x14002e302  call    UdfCompleteRequest
0x14002e307  xor     eax, eax
0x14002e309  mov     rbx, [rsp+28h+arg_8]
0x14002e30e  add     rsp, 20h
0x14002e312  pop     rdi
0x14002e313  retn
0x14005b1d6  push    rbp
0x14005b1d8  sub     rsp, 20h
0x14005b1dc  mov     rbp, rdx
0x14005b1df  mov     rax, [rbp+30h]
0x14005b1e3  mov     rcx, [rax+10h]
0x14005b1e7  add     rcx, 5C8h; Resource
0x14005b1ee  call    cs:__imp_ExReleaseResourceLite
0x14005b1f5  nop     dword ptr [rax+rax+00h]
0x14005b1fa  nop
0x14005b1fb  add     rsp, 20h
0x14005b1ff  pop     rbp
0x14005b200  retn
```
