# VidHandlerpMsrUnregisterEntry

- ea: `0x1400879e4`
- end: `0x140087aa3`
- name: `VidHandlerpMsrUnregisterEntry`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140074c30`

## callees

- `0x140021c60`
- `0x1400879e4`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140087a17`
- `ntoskrnl!RtlRbRemoveNode` at `0x140087a17`
- `winhvr!WinHvInstallIntercept` at `0x140087a69`
- `winhvr!WinHvInstallIntercept` at `0x140087a69`

## pseudocode

```c
__int64 __fastcall VidHandlerpMsrUnregisterEntry(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+24h] [rbp-24h]

  if ( *(_BYTE *)(a2 + 116) )
    result = RtlRbRemoveNode(a1 + 3424, a2 + 160);
  else
    *(_BYTE *)(a1 + 3417) = -1;
  if ( !*(_QWORD *)(a2 + 136) )
  {
    v6 = 0;
    if ( *(_BYTE *)(a2 + 116) )
    {
      HIDWORD(v6) = *(_DWORD *)(a2 + 120);
      v5 = 12;
    }
    else
    {
      v5 = 1;
    }
    result = WinHvInstallIntercept(*(_QWORD *)(a1 + 648), 0, &v5);
  }
  if ( *(_BYTE *)(a2 + 116) )
  {
    result = *(_QWORD *)(a1 + 1528);
    _InterlockedDecrement64((volatile signed __int64 *)(result + 504));
  }
  return result;
}

```

## disassembly

```asm
0x1400879e4  mov     [rsp+arg_10], rbx
0x1400879e9  push    rdi
0x1400879ea  sub     rsp, 40h
0x1400879ee  mov     rax, cs:__security_cookie
0x1400879f5  xor     rax, rsp
0x1400879f8  mov     [rsp+48h+var_18], rax
0x1400879fd  cmp     byte ptr [rdx+74h], 0
0x140087a01  mov     rbx, rdx
0x140087a04  mov     rdi, rcx
0x140087a07  jz      short loc_140087A25
0x140087a09  add     rdx, 0A0h
0x140087a10  add     rcx, 0D60h
0x140087a17  call    cs:__imp_RtlRbRemoveNode
0x140087a1e  nop     dword ptr [rax+rax+00h]
0x140087a23  jmp     short loc_140087A2C
0x140087a25  mov     byte ptr [rcx+0D59h], 0FFh
0x140087a2c  cmp     qword ptr [rbx+88h], 0
0x140087a34  jnz     short loc_140087A75
0x140087a36  xor     eax, eax
0x140087a38  mov     [rsp+48h+var_24], rax
0x140087a3d  cmp     [rbx+74h], al
0x140087a40  jz      short loc_140087A53
0x140087a42  mov     eax, [rbx+78h]
0x140087a45  mov     dword ptr [rsp+48h+var_24+4], eax
0x140087a49  mov     [rsp+48h+var_28], 0Ch
0x140087a51  jmp     short loc_140087A5B
0x140087a53  mov     [rsp+48h+var_28], 1
0x140087a5b  mov     rcx, [rdi+288h]
0x140087a62  lea     r8, [rsp+48h+var_28]
0x140087a67  xor     edx, edx
0x140087a69  call    cs:__imp_WinHvInstallIntercept
0x140087a70  nop     dword ptr [rax+rax+00h]
0x140087a75  cmp     byte ptr [rbx+74h], 0
0x140087a79  jz      short loc_140087A8A
0x140087a7b  mov     rax, [rdi+5F8h]
0x140087a82  lock dec qword ptr [rax+1F8h]
0x140087a8a  mov     rcx, [rsp+48h+var_18]
0x140087a8f  xor     rcx, rsp; StackCookie
0x140087a92  call    __security_check_cookie
0x140087a97  mov     rbx, [rsp+48h+arg_10]
0x140087a9c  add     rsp, 40h
0x140087aa0  pop     rdi
0x140087aa1  retn
```
