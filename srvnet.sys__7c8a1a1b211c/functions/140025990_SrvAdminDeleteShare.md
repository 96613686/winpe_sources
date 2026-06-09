# SrvAdminDeleteShare

- ea: `0x140025990`
- end: `0x140025b34`
- name: `SrvAdminDeleteShare`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140023be0`

## callees

- `0x140007160`
- `0x1400088f0`
- `0x14000bc90`
- `0x1400227cc`
- `0x140025990`
- `0x140029b7c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140025aad`
- `ntoskrnl!KeBugCheckEx` at `0x140025aad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400259c9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400259de`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025a62`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400259c9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400259de`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140025a62`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140025a84`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140025a84`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a44`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025aee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025b02`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025b16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025a44`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025aee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025b02`
- `ntoskrnl!ExReleaseResourceLite` at `0x140025b16`

## pseudocode

```c
__int64 __fastcall SrvAdminDeleteShare(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  struct _ERESOURCE *v3; // r14
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // ebx
  _QWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v12[4]; // [rsp+40h] [rbp-48h] BYREF

  v3 = (struct _ERESOURCE *)(a1 + 200);
  v11[0] = 131074;
  v11[1] = L"*";
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 200), 1u);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
  if ( !a3 || !*a3 )
    a3 = (unsigned __int16 *)v11;
  v7 = SrvAdminLookupShareByName(a1, a2, a3);
  v8 = v7;
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 132) )
    {
      SrvAdminDereferenceShare(v7);
      ExReleaseResourceLite((PERESOURCE)(a1 + 96));
      v9 = -1073741790;
    }
    else
    {
      ExReleaseResourceLite((PERESOURCE)(a1 + 96));
      SrvAdminUpdateProvidersOfShare(v8, 2261015);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
      RfsTableRemove(*(PEX_SPIN_LOCK *)(a1 + 72));
      if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), (PVOID)(v8 + 8)) )
        KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\sashare.c", 0x3E0u, 0, 0);
      v12[0] = SE_AUDITID_DELETE_SHARE;
      SrvLibAuditShareAddOrDelete((unsigned __int16 *)v12, a2, a3, (_QWORD *)(v8 + 72));
      SrvAdminDereferenceShare(v8);
      SrvAdminDereferenceShare(v8);
      ExReleaseResourceLite((PERESOURCE)(a1 + 96));
      v9 = 0;
    }
  }
  else
  {
    ExReleaseResourceLite((PERESOURCE)(a1 + 96));
    v9 = -1073741772;
  }
  ExReleaseResourceLite(v3);
  return v9;
}

```

## disassembly

```asm
0x140025990  push    rbx
0x140025992  push    rbp
0x140025993  push    rsi
0x140025994  push    rdi
0x140025995  push    r12
0x140025997  push    r14
0x140025999  push    r15
0x14002599b  sub     rsp, 50h
0x14002599f  lea     r14, [rcx+0C8h]
0x1400259a6  mov     [rsp+88h+var_58], 20002h
0x1400259af  mov     r15, rdx
0x1400259b2  lea     rax, Buf2; "*"
0x1400259b9  mov     rbp, rcx
0x1400259bc  mov     [rsp+88h+var_50], rax
0x1400259c1  mov     rcx, r14; Resource
0x1400259c4  mov     dl, 1; Wait
0x1400259c6  mov     rsi, r8
0x1400259c9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400259d0  nop     dword ptr [rax+rax+00h]
0x1400259d5  lea     rdi, [rbp+60h]
0x1400259d9  mov     dl, 1; Wait
0x1400259db  mov     rcx, rdi; Resource
0x1400259de  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400259e5  nop     dword ptr [rax+rax+00h]
0x1400259ea  xor     r12d, r12d
0x1400259ed  test    rsi, rsi
0x1400259f0  jz      short loc_1400259F8
0x1400259f2  cmp     [rsi], r12w
0x1400259f6  jnz     short loc_1400259FD
0x1400259f8  lea     rsi, [rsp+88h+var_58]
0x1400259fd  mov     r8, rsi
0x140025a00  mov     rdx, r15
0x140025a03  mov     rcx, rbp
0x140025a06  call    SrvAdminLookupShareByName
0x140025a0b  mov     rbx, rax
0x140025a0e  test    rax, rax
0x140025a11  jz      loc_140025AFF
0x140025a17  cmp     [rax+84h], r12d
0x140025a1e  jz      short loc_140025A41
0x140025a20  mov     rcx, rax
0x140025a23  call    SrvAdminDereferenceShare
0x140025a28  mov     rcx, rdi; Resource
0x140025a2b  call    cs:__imp_ExReleaseResourceLite
0x140025a32  nop     dword ptr [rax+rax+00h]
0x140025a37  mov     ebx, 0C0000022h
0x140025a3c  jmp     loc_140025B13
0x140025a41  mov     rcx, rdi; Resource
0x140025a44  call    cs:__imp_ExReleaseResourceLite
0x140025a4b  nop     dword ptr [rax+rax+00h]
0x140025a50  mov     edx, 228017h
0x140025a55  mov     rcx, rbx
0x140025a58  call    SrvAdminUpdateProvidersOfShare
0x140025a5d  mov     dl, 1; Wait
0x140025a5f  mov     rcx, rdi; Resource
0x140025a62  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140025a69  nop     dword ptr [rax+rax+00h]
0x140025a6e  mov     edx, [rbx]
0x140025a70  mov     rcx, [rbp+48h]; SpinLock
0x140025a74  call    RfsTableRemove
0x140025a79  lea     rdx, [rbx+8]; Buffer
0x140025a7d  lea     rcx, [rbp+198h]; Table
0x140025a84  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140025a8b  nop     dword ptr [rax+rax+00h]
0x140025a90  test    al, al
0x140025a92  jnz     short loc_140025ABA
0x140025a94  xor     r9d, r9d; BugCheckParameter3
0x140025a97  mov     [rsp+88h+BugCheckParameter4], r12; BugCheckParameter4
0x140025a9c  mov     r8d, 3E0h; BugCheckParameter2
0x140025aa2  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140025aa9  lea     ecx, [r9+54h]; BugCheckCode
0x140025aad  call    cs:__imp_KeBugCheckEx
0x140025aba  movups  xmm0, cs:SE_AUDITID_DELETE_SHARE
0x140025ac1  lea     r9, [rbx+48h]
0x140025ac5  mov     r8, rsi
0x140025ac8  mov     rdx, r15
0x140025acb  lea     rcx, [rsp+88h+var_48]
0x140025ad0  movdqu  [rsp+88h+var_48], xmm0
0x140025ad6  call    SrvLibAuditShareAddOrDelete
0x140025adb  mov     rcx, rbx
0x140025ade  call    SrvAdminDereferenceShare
0x140025ae3  mov     rcx, rbx
0x140025ae6  call    SrvAdminDereferenceShare
0x140025aeb  mov     rcx, rdi; Resource
0x140025aee  call    cs:__imp_ExReleaseResourceLite
0x140025af5  nop     dword ptr [rax+rax+00h]
0x140025afa  mov     ebx, r12d
0x140025afd  jmp     short loc_140025B13
0x140025aff  mov     rcx, rdi; Resource
0x140025b02  call    cs:__imp_ExReleaseResourceLite
0x140025b09  nop     dword ptr [rax+rax+00h]
0x140025b0e  mov     ebx, 0C0000034h
0x140025b13  mov     rcx, r14; Resource
0x140025b16  call    cs:__imp_ExReleaseResourceLite
0x140025b1d  nop     dword ptr [rax+rax+00h]
0x140025b22  mov     eax, ebx
0x140025b24  add     rsp, 50h
0x140025b28  pop     r15
0x140025b2a  pop     r14
0x140025b2c  pop     r12
0x140025b2e  pop     rdi
0x140025b2f  pop     rsi
0x140025b30  pop     rbp
0x140025b31  pop     rbx
0x140025b32  retn
```
