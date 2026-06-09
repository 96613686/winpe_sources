# Srv2Close

- ea: `0x14005ede0`
- end: `0x14005eeb4`
- name: `Srv2Close`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14008c170`

## callees

- `0x14002019c`
- `0x140020cf8`
- `0x140059338`
- `0x14005ede0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005ee95`
- `ntoskrnl!IofCompleteRequest` at `0x14005ee95`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005ee38`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005ee38`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ee81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ee81`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005ee60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005ee60`

## pseudocode

```c
__int64 __fastcall Srv2Close(__int64 a1, IRP *a2)
{
  unsigned int v3; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi

  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation->FileObject->FsContext )
    goto LABEL_10;
  if ( IoGetCurrentProcess() == Srv2ServerProcess )
  {
    KeEnterCriticalRegion();
    Smb2FsContextCleanup(CurrentStackLocation->FileObject->FsContext);
    CurrentStackLocation->FileObject->FsContext = 0;
    KeLeaveCriticalRegion();
LABEL_10:
    a2->IoStatus.Status = v3;
    IofCompleteRequest(a2, 2);
    return v3;
  }
  v3 = Srv2QueueIrpToSystem(a2);
  if ( v3 != 259 )
    goto LABEL_10;
  return v3;
}

```

## disassembly

```asm
0x14005ede0  mov     [rsp+arg_0], rbx
0x14005ede5  mov     [rsp+arg_8], rsi
0x14005edea  push    rdi
0x14005edeb  sub     rsp, 20h
0x14005edef  mov     rdi, rdx
0x14005edf2  xor     ebx, ebx
0x14005edf4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005edfb  lea     rax, WPP_GLOBAL_Control
0x14005ee02  cmp     rcx, rax
0x14005ee05  jz      short loc_14005EE27
0x14005ee07  mov     eax, [rcx+2Ch]
0x14005ee0a  test    al, 4
0x14005ee0c  jz      short loc_14005EE27
0x14005ee0e  cmp     byte ptr [rcx+29h], 2
0x14005ee12  jb      short loc_14005EE27
0x14005ee14  mov     rcx, [rcx+18h]
0x14005ee18  lea     edx, [rbx+0Eh]
0x14005ee1b  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14005ee22  call    WPP_SF_
0x14005ee27  mov     rsi, [rdi+0B8h]
0x14005ee2e  mov     rax, [rsi+30h]
0x14005ee32  cmp     [rax+18h], rbx
0x14005ee36  jz      short loc_14005EE8D
0x14005ee38  call    cs:__imp_IoGetCurrentProcess
0x14005ee3f  nop     dword ptr [rax+rax+00h]
0x14005ee44  cmp     rax, cs:Srv2ServerProcess
0x14005ee4b  jz      short loc_14005EE60
0x14005ee4d  mov     rcx, rdi; Context
0x14005ee50  call    Srv2QueueIrpToSystem
0x14005ee55  mov     ebx, eax
0x14005ee57  cmp     eax, 103h
0x14005ee5c  jz      short loc_14005EEA1
0x14005ee5e  jmp     short loc_14005EE8D
0x14005ee60  call    cs:__imp_KeEnterCriticalRegion
0x14005ee67  nop     dword ptr [rax+rax+00h]
0x14005ee6c  mov     rcx, [rsi+30h]
0x14005ee70  mov     rcx, [rcx+18h]
0x14005ee74  call    Smb2FsContextCleanup
0x14005ee79  mov     rcx, [rsi+30h]
0x14005ee7d  mov     [rcx+18h], rbx
0x14005ee81  call    cs:__imp_KeLeaveCriticalRegion
0x14005ee88  nop     dword ptr [rax+rax+00h]
0x14005ee8d  mov     dl, 2; PriorityBoost
0x14005ee8f  mov     [rdi+30h], ebx
0x14005ee92  mov     rcx, rdi; Irp
0x14005ee95  call    cs:__imp_IofCompleteRequest
0x14005ee9c  nop     dword ptr [rax+rax+00h]
0x14005eea1  mov     rsi, [rsp+28h+arg_8]
0x14005eea6  mov     eax, ebx
0x14005eea8  mov     rbx, [rsp+28h+arg_0]
0x14005eead  add     rsp, 20h
0x14005eeb1  pop     rdi
0x14005eeb2  retn
```
