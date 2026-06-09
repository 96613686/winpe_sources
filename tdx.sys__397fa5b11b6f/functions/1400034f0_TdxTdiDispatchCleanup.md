# TdxTdiDispatchCleanup

- ea: `0x1400034f0`
- end: `0x140003582`
- name: `TdxTdiDispatchCleanup`
- size: `146`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400034f0`
- `0x1400042e0`
- `0x1400075b0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003518`
- `ntoskrnl!IofCompleteRequest` at `0x140003518`

## pseudocode

```c
__int64 __fastcall TdxTdiDispatchCleanup(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  unsigned int v3; // edi
  PFILE_OBJECT FileObject; // rcx
  PVOID FsContext2; // rdx
  unsigned int v7; // eax

  a2->IoStatus.Information = 0;
  if ( a1 != TdxDeviceObject )
  {
    FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
    FsContext2 = FileObject->FsContext2;
    if ( FsContext2 == (PVOID)2 )
    {
      v7 = TdxDeleteConnection(FileObject->FsContext, a2);
    }
    else
    {
      if ( FsContext2 != (PVOID)1 )
      {
        v3 = -1073741811;
        if ( FsContext2 == (PVOID)3 )
          v3 = 0;
        goto LABEL_3;
      }
      v7 = TdxDeleteTransportAddress(FileObject->FsContext, a2);
    }
    v3 = v7;
    if ( v7 == 259 )
      return v3;
    goto LABEL_3;
  }
  v3 = 0;
LABEL_3:
  a2->IoStatus.Status = v3;
  IofCompleteRequest(a2, 0);
  return v3;
}

```

## disassembly

```asm
0x1400034f0  mov     [rsp+arg_0], rbx
0x1400034f5  push    rdi
0x1400034f6  sub     rsp, 20h
0x1400034fa  mov     qword ptr [rdx+38h], 0
0x140003502  mov     rbx, rdx
0x140003505  cmp     rcx, cs:TdxDeviceObject
0x14000350c  jnz     short loc_140003532
0x14000350e  xor     edi, edi
0x140003510  xor     edx, edx; PriorityBoost
0x140003512  mov     [rbx+30h], edi
0x140003515  mov     rcx, rbx; Irp
0x140003518  call    cs:__imp_IofCompleteRequest
0x14000351f  nop     dword ptr [rax+rax+00h]
0x140003524  mov     rbx, [rsp+28h+arg_0]
0x140003529  mov     eax, edi
0x14000352b  add     rsp, 20h
0x14000352f  pop     rdi
0x140003530  retn
0x140003532  mov     rax, [rdx+0B8h]
0x140003539  mov     rcx, [rax+30h]
0x14000353d  mov     rdx, [rcx+20h]
0x140003541  cmp     rdx, 2
0x140003545  jnz     short loc_14000355E
0x140003547  mov     rcx, [rcx+18h]
0x14000354b  mov     rdx, rbx
0x14000354e  call    TdxDeleteConnection
0x140003553  mov     edi, eax
0x140003555  cmp     eax, 103h
0x14000355a  jz      short loc_140003524
0x14000355c  jmp     short loc_140003510
0x14000355e  cmp     rdx, 1
0x140003562  jnz     short loc_140003572
0x140003564  mov     rcx, [rcx+18h]
0x140003568  mov     rdx, rbx
0x14000356b  call    TdxDeleteTransportAddress
0x140003570  jmp     short loc_140003553
0x140003572  xor     eax, eax
0x140003574  mov     edi, 0C000000Dh
0x140003579  cmp     rdx, 3
0x14000357d  cmovz   edi, eax
0x140003580  jmp     short loc_140003510
```
