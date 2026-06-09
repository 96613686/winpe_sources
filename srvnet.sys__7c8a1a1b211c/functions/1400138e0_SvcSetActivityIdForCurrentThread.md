# SvcSetActivityIdForCurrentThread

- ea: `0x1400138e0`
- end: `0x14001394a`
- name: `SvcSetActivityIdForCurrentThread`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x1400138e0`

## import_xrefs

- `ntoskrnl!IoSetActivityIdThread` at `0x140013928`
- `ntoskrnl!IoSetActivityIdThread` at `0x140013928`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400138f5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400138f5`
- `ntoskrnl!EtwActivityIdControl` at `0x14001390f`
- `ntoskrnl!EtwActivityIdControl` at `0x14001390f`

## pseudocode

```c
__int64 __fastcall SvcSetActivityIdForCurrentThread(__int64 a1, GUID *a2, __int64 *a3)
{
  NTSTATUS ActivityIdIrp; // ebx
  __int64 v6; // rax

  ActivityIdIrp = IoGetActivityIdIrp();
  if ( ActivityIdIrp >= 0 || (ActivityIdIrp = EtwActivityIdControl(3u, a2), ActivityIdIrp >= 0) )
    v6 = IoSetActivityIdThread(a2);
  else
    v6 = 0;
  *a3 = v6;
  return (unsigned int)ActivityIdIrp;
}

```

## disassembly

```asm
0x1400138e0  mov     [rsp+arg_0], rbx
0x1400138e5  mov     [rsp+arg_8], rsi
0x1400138ea  push    rdi
0x1400138eb  sub     rsp, 20h
0x1400138ef  mov     rsi, r8
0x1400138f2  mov     rdi, rdx
0x1400138f5  call    cs:__imp_IoGetActivityIdIrp
0x1400138fc  nop     dword ptr [rax+rax+00h]
0x140013901  mov     ebx, eax
0x140013903  test    eax, eax
0x140013905  jns     short loc_140013925
0x140013907  mov     rdx, rdi; ActivityId
0x14001390a  mov     ecx, 3; ControlCode
0x14001390f  call    cs:__imp_EtwActivityIdControl
0x140013916  nop     dword ptr [rax+rax+00h]
0x14001391b  mov     ebx, eax
0x14001391d  test    eax, eax
0x14001391f  jns     short loc_140013925
0x140013921  xor     eax, eax
0x140013923  jmp     short loc_140013934
0x140013925  mov     rcx, rdi
0x140013928  call    cs:__imp_IoSetActivityIdThread
0x14001392f  nop     dword ptr [rax+rax+00h]
0x140013934  mov     [rsi], rax
0x140013937  mov     eax, ebx
0x140013939  mov     rbx, [rsp+28h+arg_0]
0x14001393e  mov     rsi, [rsp+28h+arg_8]
0x140013943  add     rsp, 20h
0x140013947  pop     rdi
0x140013948  retn
```
