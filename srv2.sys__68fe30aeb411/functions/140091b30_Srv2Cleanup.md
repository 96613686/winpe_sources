# Srv2Cleanup

- ea: `0x140091b30`
- end: `0x140091c2c`
- name: `Srv2Cleanup`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14008c120`

## callees

- `0x14002019c`
- `0x140020cf8`
- `0x140059338`
- `0x14005f440`
- `0x140091b30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140091c0d`
- `ntoskrnl!IofCompleteRequest` at `0x140091c0d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140091b8e`
- `ntoskrnl!IoGetCurrentProcess` at `0x140091b8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140091bf9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140091bf9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091bb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091bb6`

## pseudocode

```c
__int64 __fastcall Srv2Cleanup(__int64 a1, IRP *a2)
{
  unsigned int v3; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PFILE_OBJECT FileObject; // rax
  PFILE_OBJECT v6; // rax

  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject->FsContext || FileObject->FsContext2 )
  {
    if ( IoGetCurrentProcess() == Srv2ServerProcess )
    {
      KeEnterCriticalRegion();
      if ( CurrentStackLocation->FileObject->FsContext )
      {
        Smb2FsContextCleanup();
        CurrentStackLocation->FileObject->FsContext = 0;
      }
      v6 = CurrentStackLocation->FileObject;
      if ( v6->FsContext2 && !Smb2ServerStage )
      {
        v6->FsContext2 = 0;
        Srv2ShutdownDriver(0);
      }
      KeLeaveCriticalRegion();
    }
    else
    {
      v3 = Srv2QueueIrpToSystem(a2);
      if ( v3 == 259 )
        return v3;
    }
  }
  a2->IoStatus.Status = v3;
  IofCompleteRequest(a2, 2);
  return v3;
}

```

## disassembly

```asm
0x140091b30  mov     [rsp+arg_0], rbx
0x140091b35  mov     [rsp+arg_8], rsi
0x140091b3a  push    rdi
0x140091b3b  sub     rsp, 20h
0x140091b3f  mov     rsi, rdx
0x140091b42  xor     edi, edi
0x140091b44  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091b4b  lea     rax, WPP_GLOBAL_Control
0x140091b52  cmp     rcx, rax
0x140091b55  jz      short loc_140091B77
0x140091b57  mov     eax, [rcx+2Ch]
0x140091b5a  test    al, 4
0x140091b5c  jz      short loc_140091B77
0x140091b5e  cmp     byte ptr [rcx+29h], 2
0x140091b62  jb      short loc_140091B77
0x140091b64  mov     rcx, [rcx+18h]
0x140091b68  lea     edx, [rdi+0Dh]
0x140091b6b  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x140091b72  call    WPP_SF_
0x140091b77  mov     rbx, [rsi+0B8h]
0x140091b7e  mov     rax, [rbx+30h]
0x140091b82  cmp     [rax+18h], rdi
0x140091b86  jnz     short loc_140091B8E
0x140091b88  cmp     [rax+20h], rdi
0x140091b8c  jz      short loc_140091C05
0x140091b8e  call    cs:__imp_IoGetCurrentProcess
0x140091b95  nop     dword ptr [rax+rax+00h]
0x140091b9a  cmp     rax, cs:Srv2ServerProcess
0x140091ba1  jz      short loc_140091BB6
0x140091ba3  mov     rcx, rsi; Context
0x140091ba6  call    Srv2QueueIrpToSystem
0x140091bab  mov     edi, eax
0x140091bad  cmp     eax, 103h
0x140091bb2  jnz     short loc_140091C05
0x140091bb4  jmp     short loc_140091C19
0x140091bb6  call    cs:__imp_KeEnterCriticalRegion
0x140091bbd  nop     dword ptr [rax+rax+00h]
0x140091bc2  mov     rax, [rbx+30h]
0x140091bc6  mov     rcx, [rax+18h]
0x140091bca  test    rcx, rcx
0x140091bcd  jz      short loc_140091BDC
0x140091bcf  call    Smb2FsContextCleanup
0x140091bd4  mov     rax, [rbx+30h]
0x140091bd8  mov     [rax+18h], rdi
0x140091bdc  mov     rax, [rbx+30h]
0x140091be0  cmp     [rax+20h], rdi
0x140091be4  jz      short loc_140091BF9
0x140091be6  cmp     cs:Smb2ServerStage, edi
0x140091bec  jnz     short loc_140091BF9
0x140091bee  xor     ecx, ecx
0x140091bf0  mov     [rax+20h], rdi
0x140091bf4  call    Srv2ShutdownDriver
0x140091bf9  call    cs:__imp_KeLeaveCriticalRegion
0x140091c00  nop     dword ptr [rax+rax+00h]
0x140091c05  mov     dl, 2; PriorityBoost
0x140091c07  mov     [rsi+30h], edi
0x140091c0a  mov     rcx, rsi; Irp
0x140091c0d  call    cs:__imp_IofCompleteRequest
0x140091c14  nop     dword ptr [rax+rax+00h]
0x140091c19  mov     rbx, [rsp+28h+arg_0]
0x140091c1e  mov     eax, edi
0x140091c20  mov     rsi, [rsp+28h+arg_8]
0x140091c25  add     rsp, 20h
0x140091c29  pop     rdi
0x140091c2a  retn
```
