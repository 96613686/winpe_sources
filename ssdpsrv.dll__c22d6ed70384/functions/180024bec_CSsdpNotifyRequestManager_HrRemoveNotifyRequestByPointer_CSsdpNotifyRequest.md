# CSsdpNotifyRequestManager::HrRemoveNotifyRequestByPointer(CSsdpNotifyRequest *)

- ea: `0x180024bec`
- end: `0x180024c64`
- name: `?HrRemoveNotifyRequestByPointer@CSsdpNotifyRequestManager@@QEAAJPEAVCSsdpNotifyRequest@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CSsdpNotifyRequest *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fb90`
- `0x18002de90`

## callees

- `0x180015d9c`
- `0x180024bec`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bfc`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrRemoveNotifyRequestByPointer(
        struct _RTL_CRITICAL_SECTION *this,
        struct CSsdpNotifyRequest *a2)
{
  EnterCriticalSection(this);
  LODWORD(a2) = CSsdpNotifyRequestManager::HrRemoveInternal((CSsdpNotifyRequestManager *)this, 0, 0, 0, a2);
  LeaveCriticalSection(this);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x180024bec  mov     [rsp+arg_0], rbx
0x180024bf1  push    rdi
0x180024bf2  sub     rsp, 30h
0x180024bf6  mov     rbx, rdx
0x180024bf9  mov     rdi, rcx
0x180024bfc  call    cs:__imp_EnterCriticalSection
0x180024c02  mov     [rsp+38h+var_18], rbx; struct CSsdpNotifyRequest *
0x180024c07  xor     r9d, r9d; void *
0x180024c0a  xor     r8d, r8d; int
0x180024c0d  xor     edx, edx; int
0x180024c0f  mov     rcx, rdi; this
0x180024c12  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x180024c17  mov     ebx, eax
0x180024c19  mov     rcx, rdi; lpCriticalSection
0x180024c1c  call    cs:__imp_LeaveCriticalSection
0x180024c22  mov     eax, ebx
0x180024c24  jmp     short loc_180024C59
0x180024c26  lea     rax, WPP_GLOBAL_Control
0x180024c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c34  cmp     rcx, rax
0x180024c37  jz      short loc_180024C54
0x180024c39  test    byte ptr [rcx+1Ch], 1
0x180024c3d  jz      short loc_180024C54
0x180024c3f  mov     edx, 5Bh ; '['
0x180024c44  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180024c4b  mov     rcx, [rcx+10h]
0x180024c4f  call    WPP_SF_
0x180024c54  mov     eax, 80004005h
0x180024c59  mov     rbx, [rsp+38h+arg_0]
0x180024c5e  add     rsp, 30h
0x180024c62  pop     rdi
0x180024c63  retn
```
