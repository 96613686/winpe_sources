# WinSetupMonDeviceControl

- ea: `0x140007d40`
- end: `0x140007db2`
- name: `WinSetupMonDeviceControl`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007668`
- `0x140007d40`
- `0x14001f130`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140007d98`
- `ntoskrnl!IofCompleteRequest` at `0x140007d98`

## pseudocode

```c
__int64 __fastcall WinSetupMonDeviceControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  unsigned int v4; // edi
  int v5; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2228627 )
  {
    LOBYTE(a1) = a2->RequestorMode;
    v5 = WinSetupMonProcessMessage(
           a1,
           CurrentStackLocation->Parameters.CreatePipe.Parameters,
           CurrentStackLocation->Parameters.Create.Options);
    v4 = v5;
    if ( v5 < 0 )
      TraceError("WinSetupMonDeviceControl: WinSetupMonMessage failed", (unsigned int)v5);
  }
  else
  {
    v4 = -1073741637;
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v4;
  IofCompleteRequest(a2, 0);
  return v4;
}

```

## disassembly

```asm
0x140007d40  mov     [rsp+arg_0], rbx
0x140007d45  push    rdi
0x140007d46  sub     rsp, 30h
0x140007d4a  mov     rbx, rdx
0x140007d4d  mov     rdx, [rdx+0B8h]
0x140007d54  cmp     dword ptr [rdx+18h], 220193h
0x140007d5b  jz      short loc_140007D64
0x140007d5d  mov     edi, 0C00000BBh
0x140007d62  jmp     short loc_140007D88
0x140007d64  mov     r8d, [rdx+10h]
0x140007d68  mov     rdx, [rdx+20h]
0x140007d6c  mov     cl, [rbx+40h]
0x140007d6f  call    WinSetupMonProcessMessage
0x140007d74  mov     edi, eax
0x140007d76  test    eax, eax
0x140007d78  jns     short loc_140007D88
0x140007d7a  mov     edx, eax
0x140007d7c  lea     rcx, aWinsetupmondev; "WinSetupMonDeviceControl: WinSetupMonMe"...
0x140007d83  call    TraceError
0x140007d88  xor     edx, edx; PriorityBoost
0x140007d8a  mov     qword ptr [rbx+38h], 0
0x140007d92  mov     rcx, rbx; Irp
0x140007d95  mov     [rbx+30h], edi
0x140007d98  call    cs:__imp_IofCompleteRequest
0x140007d9f  nop     dword ptr [rax+rax+00h]
0x140007da4  mov     rbx, [rsp+38h+arg_0]
0x140007da9  mov     eax, edi
0x140007dab  add     rsp, 30h
0x140007daf  pop     rdi
0x140007db0  retn
```
