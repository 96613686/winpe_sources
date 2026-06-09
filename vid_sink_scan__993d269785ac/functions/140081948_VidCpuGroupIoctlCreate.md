# VidCpuGroupIoctlCreate

- ea: `0x140081948`
- end: `0x140081aca`
- name: `VidCpuGroupIoctlCreate`
- size: `386`
- prototype: `__int64 __fastcall(void *Src, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400377bc`

## callees

- `0x1400116c8`
- `0x14002f524`
- `0x140075afc`
- `0x140081948`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400819ff`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400819ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081aa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081aa7`
- `ntoskrnl!ExAllocatePool2` at `0x1400819b7`
- `ntoskrnl!ExAllocatePool2` at `0x1400819b7`
- `winhvr!WinHvCreateCpuGroup` at `0x140081a24`
- `winhvr!WinHvCreateCpuGroup` at `0x140081a24`

## string_xrefs

- `0x140081991`: `VidCpuGroupIoctlCreate`
- `0x1400819e3`: `VidCpuGroupIoctlCreate`
- `0x140081a46`: `VidCpuGroupIoctlCreate`
- `0x140081a66`: `VidCpuGroupIoctlCreate`
- `0x140081a8e`: `VidCpuGroupIoctlCreate`

## pseudocode

```c
__int64 __fastcall VidCpuGroupIoctlCreate(void *Src, unsigned int a2, __int64 a3)
{
  __int64 v4; // r14
  void *Pool2; // rdi
  int CpuGroup; // ebx

  v4 = a2;
  Pool2 = 0;
  if ( a2 - 1 > 0x7FF )
  {
    CpuGroup = -1073741811;
    VidTraceErrorStatusInternal0("VidCpuGroupIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c", 86);
  }
  else if ( (int)VidSidServiceCheck() >= 0 )
  {
    Pool2 = (void *)ExAllocatePool2(65, 4 * v4, 1917084758);
    if ( Pool2 )
    {
      if ( 4 * v4 && ((unsigned __int8)Src & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Pool2, Src, 4 * v4);
      CpuGroup = WinHvCreateCpuGroup(Pool2, (unsigned int)v4, a3);
      if ( CpuGroup < 0 )
        VidTraceErrorStatusInternal0("VidCpuGroupIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c", 137);
    }
    else
    {
      CpuGroup = -1073741670;
      VidTraceErrorStatusInternal0("VidCpuGroupIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c", 109);
    }
  }
  else
  {
    CpuGroup = -1073741727;
    VidTraceErrorStatusInternal0("VidCpuGroupIoctlCreate", "onecore\\vm\\vid\\sys\\driver\\vidcpugroup.c", 94);
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  return (unsigned int)CpuGroup;
}

```

## disassembly

```asm
0x140081948  mov     [rsp+arg_0], rbx
0x14008194d  mov     [rsp+arg_8], rsi
0x140081952  push    rdi
0x140081953  push    r14
0x140081955  push    r15
0x140081957  sub     rsp, 20h
0x14008195b  mov     r15, r8
0x14008195e  mov     r14d, edx
0x140081961  mov     rsi, rcx
0x140081964  xor     edi, edi
0x140081966  lea     eax, [r14-1]
0x14008196a  cmp     eax, 7FFh
0x14008196f  ja      loc_140081A79
0x140081975  call    VidSidServiceCheck
0x14008197a  test    eax, eax
0x14008197c  jns     short loc_1400819A2
0x14008197e  mov     ebx, 0C0000061h
0x140081983  mov     r9d, ebx
0x140081986  lea     r8d, [rdi+5Eh]
0x14008198a  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140081991  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140081998  call    VidTraceErrorStatusInternal0
0x14008199d  jmp     loc_140081A9A
0x1400819a2  mov     rbx, r14
0x1400819a5  shl     rbx, 2
0x1400819a9  mov     r8d, 72446456h
0x1400819af  mov     rdx, rbx
0x1400819b2  mov     ecx, 41h ; 'A'
0x1400819b7  call    cs:__imp_ExAllocatePool2
0x1400819be  nop     dword ptr [rax+rax+00h]
0x1400819c3  mov     rdi, rax
0x1400819c6  mov     [rsp+38h+arg_18], rax
0x1400819cb  test    rax, rax
0x1400819ce  jnz     short loc_1400819F4
0x1400819d0  mov     ebx, 0C000009Ah
0x1400819d5  mov     r9d, ebx
0x1400819d8  lea     r8d, [rax+6Dh]
0x1400819dc  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x1400819e3  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x1400819ea  call    VidTraceErrorStatusInternal0
0x1400819ef  jmp     loc_140081A9A
0x1400819f4  test    rbx, rbx
0x1400819f7  jz      short loc_140081A0C
0x1400819f9  test    sil, 3
0x1400819fd  jz      short loc_140081A0C
0x1400819ff  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140081a06  nop     dword ptr [rax+rax+00h]
0x140081a0b  int     3; Trap to Debugger
0x140081a0c  mov     r8, rbx; Size
0x140081a0f  mov     rdx, rsi; Src
0x140081a12  mov     rcx, rdi; void *
0x140081a15  call    RtlCopyFromUser
0x140081a1a  nop
0x140081a1b  mov     r8, r15
0x140081a1e  mov     edx, r14d
0x140081a21  mov     rcx, rdi
0x140081a24  call    cs:__imp_WinHvCreateCpuGroup
0x140081a2b  nop     dword ptr [rax+rax+00h]
0x140081a30  mov     ebx, eax
0x140081a32  test    eax, eax
0x140081a34  jns     short loc_140081A9A
0x140081a36  mov     r9d, eax
0x140081a39  mov     r8d, 89h
0x140081a3f  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140081a46  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140081a4d  call    VidTraceErrorStatusInternal0
0x140081a52  jmp     short loc_140081A9A
0x140081a54  mov     ebx, eax
0x140081a56  mov     r9d, eax
0x140081a59  mov     r8d, 7Fh
0x140081a5f  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140081a66  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140081a6d  call    VidTraceErrorStatusInternal0
0x140081a72  mov     rdi, [rsp+38h+arg_18]
0x140081a77  jmp     short loc_140081A9A
0x140081a79  mov     ebx, 0C000000Dh
0x140081a7e  mov     r9d, ebx
0x140081a81  mov     r8d, 56h ; 'V'
0x140081a87  lea     rdx, aOnecoreVmVidSy_32; "onecore\\vm\\vid\\sys\\driver\\vidcpugr"...
0x140081a8e  lea     rcx, aVidcpugroupioc_0; "VidCpuGroupIoctlCreate"
0x140081a95  call    VidTraceErrorStatusInternal0
0x140081a9a  test    rdi, rdi
0x140081a9d  jz      short loc_140081AB3
0x140081a9f  mov     edx, 72446456h; Tag
0x140081aa4  mov     rcx, rdi; P
0x140081aa7  call    cs:__imp_ExFreePoolWithTag
0x140081aae  nop     dword ptr [rax+rax+00h]
0x140081ab3  mov     eax, ebx
0x140081ab5  mov     rbx, [rsp+38h+arg_0]
0x140081aba  mov     rsi, [rsp+38h+arg_8]
0x140081abf  add     rsp, 20h
0x140081ac3  pop     r15
0x140081ac5  pop     r14
0x140081ac7  pop     rdi
0x140081ac8  retn
```
