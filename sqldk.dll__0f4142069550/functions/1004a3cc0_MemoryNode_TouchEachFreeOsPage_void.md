# MemoryNode::TouchEachFreeOsPage(void *)

- ea: `0x1004a3cc0`
- end: `0x1004a3dc2`
- name: `?TouchEachFreeOsPage@MemoryNode@@SAPEAXPEAX@Z`
- size: `258`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x100403070`
- `0x1004a3cc0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x1004a3cf5`
- `KERNEL32!InitializeSListHead` at `0x1004a3cf5`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a3d18`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a3d74`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a3d18`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a3d74`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3cfe`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d23`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d3a`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d81`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3cfe`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d23`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d3a`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a3d81`
- `KERNEL32!QueryDepthSList` at `0x1004a3cdc`
- `KERNEL32!QueryDepthSList` at `0x1004a3cdc`

## pseudocode

```c
void *__fastcall MemoryNode::TouchEachFreeOsPage(_QWORD *a1)
{
  union _SLIST_HEADER *v1; // rdi
  struct _SLIST_ENTRY *v2; // rbx
  PSLIST_ENTRY v3; // rax
  PSLIST_ENTRY v4; // rbx
  _BYTE *v5; // rax
  _BYTE *i; // rcx
  PSLIST_ENTRY v7; // rax
  union _SLIST_HEADER ListHead; // [rsp+20h] [rbp-28h] BYREF

  v1 = (union _SLIST_HEADER *)a1[1];
  if ( !QueryDepthSList(v1) )
    return 0;
  InitializeSListHead(&ListHead);
  v2 = InterlockedPopEntrySList(v1);
  while ( v2 )
  {
    InterlockedPushEntrySList(&ListHead, v2);
    v2 = 0;
    v3 = InterlockedPopEntrySList(v1);
    if ( v3 )
      v2 = v3;
  }
  v4 = InterlockedPopEntrySList(&ListHead);
  while ( v4 )
  {
    v5 = (_BYTE *)*((_QWORD *)&v4[2].Next + 1);
    for ( i = v5 + 0x1000000; v5 < i; v5 += 4096 )
      *v5 = 0;
    InterlockedPushEntrySList(v1, v4);
    v4 = 0;
    v7 = InterlockedPopEntrySList(&ListHead);
    if ( v7 )
      v4 = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x1004a3cc0  push    rdi
0x1004a3cc2  sub     rsp, 40h
0x1004a3cc6  mov     rax, cs:__security_cookie
0x1004a3ccd  xor     rax, rsp
0x1004a3cd0  mov     [rsp+48h+var_18], rax
0x1004a3cd5  mov     rdi, [rcx+8]
0x1004a3cd9  mov     rcx, rdi; ListHead
0x1004a3cdc  call    cs:__imp_QueryDepthSList
0x1004a3ce2  test    ax, ax
0x1004a3ce5  jz      loc_1004A3DAD
0x1004a3ceb  lea     rcx, [rsp+48h+ListHead]; ListHead
0x1004a3cf0  mov     [rsp+48h+arg_8], rbx
0x1004a3cf5  call    cs:__imp_InitializeSListHead
0x1004a3cfb  mov     rcx, rdi; ListHead
0x1004a3cfe  call    cs:__imp_InterlockedPopEntrySList
0x1004a3d04  mov     rbx, rax
0x1004a3d07  test    rax, rax
0x1004a3d0a  jz      short loc_1004A3D35
0x1004a3d0c  nop     dword ptr [rax]
0x1004a3d0f  nop
0x1004a3d10  mov     rdx, rbx; ListEntry
0x1004a3d13  lea     rcx, [rsp+48h+ListHead]; ListHead
0x1004a3d18  call    cs:__imp_InterlockedPushEntrySList
0x1004a3d1e  mov     rcx, rdi; ListHead
0x1004a3d21  xor     ebx, ebx
0x1004a3d23  call    cs:__imp_InterlockedPopEntrySList
0x1004a3d29  test    rax, rax
0x1004a3d2c  cmovnz  rbx, rax
0x1004a3d30  test    rbx, rbx
0x1004a3d33  jnz     short loc_1004A3D10
0x1004a3d35  lea     rcx, [rsp+48h+ListHead]; ListHead
0x1004a3d3a  call    cs:__imp_InterlockedPopEntrySList
0x1004a3d40  mov     rbx, rax
0x1004a3d43  test    rax, rax
0x1004a3d46  jz      short loc_1004A3D93
0x1004a3d48  nop     dword ptr [rax+rax]
0x1004a3d4c  nop     dword ptr [rax+00h]
0x1004a3d50  mov     rax, [rbx+28h]
0x1004a3d54  lea     rcx, [rax+1000000h]
0x1004a3d5b  cmp     rax, rcx
0x1004a3d5e  jnb     short loc_1004A3D6E
0x1004a3d60  mov     byte ptr [rax], 0
0x1004a3d63  add     rax, 1000h
0x1004a3d69  cmp     rax, rcx
0x1004a3d6c  jb      short loc_1004A3D60
0x1004a3d6e  mov     rdx, rbx; ListEntry
0x1004a3d71  mov     rcx, rdi; ListHead
0x1004a3d74  call    cs:__imp_InterlockedPushEntrySList
0x1004a3d7a  lea     rcx, [rsp+48h+ListHead]; ListHead
0x1004a3d7f  xor     ebx, ebx
0x1004a3d81  call    cs:__imp_InterlockedPopEntrySList
0x1004a3d87  test    rax, rax
0x1004a3d8a  cmovnz  rbx, rax
0x1004a3d8e  test    rbx, rbx
0x1004a3d91  jnz     short loc_1004A3D50
0x1004a3d93  mov     rbx, [rsp+48h+arg_8]
0x1004a3d98  xor     eax, eax
0x1004a3d9a  mov     rcx, [rsp+48h+var_18]
0x1004a3d9f  xor     rcx, rsp; StackCookie
0x1004a3da2  call    __security_check_cookie
0x1004a3da7  add     rsp, 40h
0x1004a3dab  pop     rdi
0x1004a3dac  retn
0x1004a3dad  xor     eax, eax
0x1004a3daf  mov     rcx, [rsp+48h+var_18]
0x1004a3db4  xor     rcx, rsp; StackCookie
0x1004a3db7  call    __security_check_cookie
0x1004a3dbc  add     rsp, 40h
0x1004a3dc0  pop     rdi
0x1004a3dc1  retn
```
