# VidHandlerpCpuidUnregisterEntry

- ea: `0x1400861e4`
- end: `0x140086260`
- name: `VidHandlerpCpuidUnregisterEntry`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140073c48`

## callees

- `0x140021650`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14008623b`
- `ntoskrnl!RtlRbRemoveNode` at `0x14008623b`
- `winhvr!WinHvInstallIntercept` at `0x140086221`
- `winhvr!WinHvInstallIntercept` at `0x140086221`

## pseudocode

```c
__int64 __fastcall VidHandlerpCpuidUnregisterEntry(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+28h] [rbp-20h]

  v2 = *(_DWORD *)(a2 + 116);
  v6 = 2;
  v7 = v2;
  WinHvInstallIntercept(*(_QWORD *)(a1 + 648), 0, &v6);
  return RtlRbRemoveNode(a1 + 3456, a2 + 160);
}

```

## disassembly

```asm
0x1400861e4  mov     [rsp+arg_10], rbx
0x1400861e9  push    rdi
0x1400861ea  sub     rsp, 40h
0x1400861ee  mov     rax, cs:__security_cookie
0x1400861f5  xor     rax, rsp
0x1400861f8  mov     [rsp+48h+var_18], rax
0x1400861fd  mov     eax, [rdx+74h]
0x140086200  lea     r8, [rsp+48h+var_28]
0x140086205  mov     rdi, rdx
0x140086208  mov     [rsp+48h+var_28], 2
0x140086211  mov     rbx, rcx
0x140086214  mov     [rsp+48h+var_20], eax
0x140086218  mov     rcx, [rcx+288h]
0x14008621f  xor     edx, edx
0x140086221  call    cs:__imp_WinHvInstallIntercept
0x140086228  nop     dword ptr [rax+rax+00h]
0x14008622d  lea     rdx, [rdi+0A0h]
0x140086234  lea     rcx, [rbx+0D80h]
0x14008623b  call    cs:__imp_RtlRbRemoveNode
0x140086242  nop     dword ptr [rax+rax+00h]
0x140086247  mov     rcx, [rsp+48h+var_18]
0x14008624c  xor     rcx, rsp; StackCookie
0x14008624f  call    __security_check_cookie
0x140086254  mov     rbx, [rsp+48h+arg_10]
0x140086259  add     rsp, 40h
0x14008625d  pop     rdi
0x14008625e  retn
```
