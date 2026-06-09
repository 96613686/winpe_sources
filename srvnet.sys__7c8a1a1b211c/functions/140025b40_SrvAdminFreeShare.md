# SrvAdminFreeShare

- ea: `0x140025b40`
- end: `0x140025b7a`
- name: `SrvAdminFreeShare`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140007160`
- `0x140025b40`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140025b5f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140025b5f`

## pseudocode

```c
__int64 __fastcall SrvAdminFreeShare(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(a1 + 160) + 408LL), (PVOID)(a1 + 8));
    return SrvAdminDereferenceShare(a1);
  }
  return result;
}

```

## disassembly

```asm
0x140025b40  test    rcx, rcx
0x140025b43  jz      short locret_140025B78
0x140025b45  push    rbx
0x140025b46  sub     rsp, 20h
0x140025b4a  mov     rbx, rcx
0x140025b4d  lea     rdx, [rcx+8]; Buffer
0x140025b51  mov     rcx, [rcx+0A0h]
0x140025b58  add     rcx, 198h; Table
0x140025b5f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140025b66  nop     dword ptr [rax+rax+00h]
0x140025b6b  mov     rcx, rbx
0x140025b6e  call    SrvAdminDereferenceShare
0x140025b73  add     rsp, 20h
0x140025b77  pop     rbx
0x140025b78  retn
```
