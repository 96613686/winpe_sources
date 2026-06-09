# SrvNetClose

- ea: `0x140052700`
- end: `0x1400527ab`
- name: `SrvNetClose`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140050640`

## callees

- `0x140005100`
- `0x14000e1f8`
- `0x140015790`
- `0x140052700`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052757`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052757`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052736`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052736`
- `ntoskrnl!IofCompleteRequest` at `0x14005276f`
- `ntoskrnl!IofCompleteRequest` at `0x14005276f`

## pseudocode

```c
__int64 __fastcall SrvNetClose(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
  }
  KeEnterCriticalRegion();
  SrvAdminCloseInstanceHandle(a1, CurrentStackLocation->FileObject);
  SrvAdminCloseClusSvcHandle(CurrentStackLocation->FileObject);
  KeLeaveCriticalRegion();
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 2);
  return 0;
}

```

## disassembly

```asm
0x140052700  mov     [rsp+arg_0], rbx
0x140052705  mov     [rsp+arg_8], rsi
0x14005270a  push    rdi
0x14005270b  sub     rsp, 20h
0x14005270f  mov     rdi, [rdx+0B8h]
0x140052716  mov     rbx, rdx
0x140052719  mov     rsi, rcx
0x14005271c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052723  lea     rax, WPP_GLOBAL_Control
0x14005272a  cmp     rcx, rax
0x14005272d  jz      short loc_140052736
0x14005272f  mov     eax, [rcx+2Ch]
0x140052732  test    al, 2
0x140052734  jnz     short loc_14005278E
0x140052736  call    cs:__imp_KeEnterCriticalRegion
0x14005273d  nop     dword ptr [rax+rax+00h]
0x140052742  mov     rdx, [rdi+30h]
0x140052746  mov     rcx, rsi
0x140052749  call    SrvAdminCloseInstanceHandle
0x14005274e  mov     rcx, [rdi+30h]
0x140052752  call    SrvAdminCloseClusSvcHandle
0x140052757  call    cs:__imp_KeLeaveCriticalRegion
0x14005275e  nop     dword ptr [rax+rax+00h]
0x140052763  mov     dl, 2; PriorityBoost
0x140052765  mov     dword ptr [rbx+30h], 0
0x14005276c  mov     rcx, rbx; Irp
0x14005276f  call    cs:__imp_IofCompleteRequest
0x140052776  nop     dword ptr [rax+rax+00h]
0x14005277b  mov     rbx, [rsp+28h+arg_0]
0x140052780  xor     eax, eax
0x140052782  mov     rsi, [rsp+28h+arg_8]
0x140052787  add     rsp, 20h
0x14005278b  pop     rdi
0x14005278c  retn
0x14005278e  cmp     byte ptr [rcx+29h], 2
0x140052792  jb      short loc_140052736
0x140052794  mov     rcx, [rcx+18h]
0x140052798  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x14005279f  mov     edx, 0Eh
0x1400527a4  call    WPP_SF_
0x1400527a9  jmp     short loc_140052736
```
