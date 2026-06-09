# Srv2Cleanup

- ea: `0x140091b80`
- end: `0x140091c7c`
- name: `Srv2Cleanup`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14008c170`

## callees

- `0x14002019c`
- `0x140020cf8`
- `0x140059338`
- `0x14005f440`
- `0x140091b80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140091c5d`
- `ntoskrnl!IofCompleteRequest` at `0x140091c5d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140091bde`
- `ntoskrnl!IoGetCurrentProcess` at `0x140091bde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140091c49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140091c49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091c06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091c06`

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
0x140091b80  mov     [rsp+arg_0], rbx
0x140091b85  mov     [rsp+arg_8], rsi
0x140091b8a  push    rdi
0x140091b8b  sub     rsp, 20h
0x140091b8f  mov     rsi, rdx
0x140091b92  xor     edi, edi
0x140091b94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140091b9b  lea     rax, WPP_GLOBAL_Control
0x140091ba2  cmp     rcx, rax
0x140091ba5  jz      short loc_140091BC7
0x140091ba7  mov     eax, [rcx+2Ch]
0x140091baa  test    al, 4
0x140091bac  jz      short loc_140091BC7
0x140091bae  cmp     byte ptr [rcx+29h], 2
0x140091bb2  jb      short loc_140091BC7
0x140091bb4  mov     rcx, [rcx+18h]
0x140091bb8  lea     edx, [rdi+0Dh]
0x140091bbb  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x140091bc2  call    WPP_SF_
0x140091bc7  mov     rbx, [rsi+0B8h]
0x140091bce  mov     rax, [rbx+30h]
0x140091bd2  cmp     [rax+18h], rdi
0x140091bd6  jnz     short loc_140091BDE
0x140091bd8  cmp     [rax+20h], rdi
0x140091bdc  jz      short loc_140091C55
0x140091bde  call    cs:__imp_IoGetCurrentProcess
0x140091be5  nop     dword ptr [rax+rax+00h]
0x140091bea  cmp     rax, cs:Srv2ServerProcess
0x140091bf1  jz      short loc_140091C06
0x140091bf3  mov     rcx, rsi; Context
0x140091bf6  call    Srv2QueueIrpToSystem
0x140091bfb  mov     edi, eax
0x140091bfd  cmp     eax, 103h
0x140091c02  jnz     short loc_140091C55
0x140091c04  jmp     short loc_140091C69
0x140091c06  call    cs:__imp_KeEnterCriticalRegion
0x140091c0d  nop     dword ptr [rax+rax+00h]
0x140091c12  mov     rax, [rbx+30h]
0x140091c16  mov     rcx, [rax+18h]
0x140091c1a  test    rcx, rcx
0x140091c1d  jz      short loc_140091C2C
0x140091c1f  call    Smb2FsContextCleanup
0x140091c24  mov     rax, [rbx+30h]
0x140091c28  mov     [rax+18h], rdi
0x140091c2c  mov     rax, [rbx+30h]
0x140091c30  cmp     [rax+20h], rdi
0x140091c34  jz      short loc_140091C49
0x140091c36  cmp     cs:Smb2ServerStage, edi
0x140091c3c  jnz     short loc_140091C49
0x140091c3e  xor     ecx, ecx
0x140091c40  mov     [rax+20h], rdi
0x140091c44  call    Srv2ShutdownDriver
0x140091c49  call    cs:__imp_KeLeaveCriticalRegion
0x140091c50  nop     dword ptr [rax+rax+00h]
0x140091c55  mov     dl, 2; PriorityBoost
0x140091c57  mov     [rsi+30h], edi
0x140091c5a  mov     rcx, rsi; Irp
0x140091c5d  call    cs:__imp_IofCompleteRequest
0x140091c64  nop     dword ptr [rax+rax+00h]
0x140091c69  mov     rbx, [rsp+28h+arg_0]
0x140091c6e  mov     eax, edi
0x140091c70  mov     rsi, [rsp+28h+arg_8]
0x140091c75  add     rsp, 20h
0x140091c79  pop     rdi
0x140091c7a  retn
```
