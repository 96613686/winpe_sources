# SrvNetCleanup

- ea: `0x140053090`
- end: `0x1400530f1`
- name: `SrvNetCleanup`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140050640`

## callees

- `0x140015790`
- `0x140053090`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400530bf`
- `ntoskrnl!IofCompleteRequest` at `0x1400530bf`

## pseudocode

```c
__int64 __fastcall SrvNetCleanup(__int64 a1, IRP *a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
  }
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 2);
  return 0;
}

```

## disassembly

```asm
0x140053090  push    rbx
0x140053092  sub     rsp, 20h
0x140053096  mov     rbx, rdx
0x140053099  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400530a0  lea     rax, WPP_GLOBAL_Control
0x1400530a7  cmp     rcx, rax
0x1400530aa  jz      short loc_1400530B3
0x1400530ac  mov     eax, [rcx+2Ch]
0x1400530af  test    al, 2
0x1400530b1  jnz     short loc_1400530D4
0x1400530b3  mov     dl, 2; PriorityBoost
0x1400530b5  mov     dword ptr [rbx+30h], 0
0x1400530bc  mov     rcx, rbx; Irp
0x1400530bf  call    cs:__imp_IofCompleteRequest
0x1400530c6  nop     dword ptr [rax+rax+00h]
0x1400530cb  xor     eax, eax
0x1400530cd  add     rsp, 20h
0x1400530d1  pop     rbx
0x1400530d2  retn
0x1400530d4  cmp     byte ptr [rcx+29h], 2
0x1400530d8  jb      short loc_1400530B3
0x1400530da  mov     rcx, [rcx+18h]
0x1400530de  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x1400530e5  mov     edx, 0Dh
0x1400530ea  call    WPP_SF_
0x1400530ef  jmp     short loc_1400530B3
```
