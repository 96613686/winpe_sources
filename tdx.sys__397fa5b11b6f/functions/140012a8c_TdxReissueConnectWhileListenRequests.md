# TdxReissueConnectWhileListenRequests

- ea: `0x140012a8c`
- end: `0x140012b2d`
- name: `TdxReissueConnectWhileListenRequests`
- size: `161`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003c9c`
- `0x1400106c0`
- `0x140011fd0`

## callees

- `0x1400047d0`
- `0x140004df4`
- `0x1400054ec`
- `0x140012a8c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012b0d`
- `ntoskrnl!IofCompleteRequest` at `0x140012b0d`

## pseudocode

```c
void __fastcall TdxReissueConnectWhileListenRequests(PIRP Irp, __int64 a2)
{
  PIRP v3; // rdi
  IRP *v4; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  __int64 FsContext; // rbx
  NTSTATUS v7; // ebp

  if ( Irp )
  {
    v3 = Irp;
    do
    {
      v4 = (IRP *)v3->Tail.Overlay.DriverContext[2];
      v3->Tail.Overlay.DriverContext[2] = 0;
      CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
      FsContext = (__int64)CurrentStackLocation->FileObject->FsContext;
      v7 = TdxConnectConnection(FsContext, v3, CurrentStackLocation);
      DbgTdxDereferenceTransportAddress(a2, "minio\\netio\\session\\tdi\\address.c", 4145);
      DbgTdxDereferenceConnection(FsContext, (__int64)"TdxReissueConnectWhileListenRequests", 4146);
      if ( v7 != 259 )
      {
        v3->IoStatus.Status = v7;
        IofCompleteRequest(v3, 2);
      }
      v3 = v4;
    }
    while ( v4 );
  }
}

```

## disassembly

```asm
0x140012a8c  test    rcx, rcx
0x140012a8f  jz      locret_140012B2B
0x140012a95  push    rbx
0x140012a96  push    rbp
0x140012a97  push    rsi
0x140012a98  push    rdi
0x140012a99  push    r14
0x140012a9b  sub     rsp, 20h
0x140012a9f  mov     r14, rdx
0x140012aa2  mov     rdi, rcx
0x140012aa5  mov     rsi, [rdi+88h]
0x140012aac  mov     rdx, rdi
0x140012aaf  mov     qword ptr [rdi+88h], 0
0x140012aba  mov     r8, [rdi+0B8h]
0x140012ac1  mov     rax, [r8+30h]
0x140012ac5  mov     rbx, [rax+18h]
0x140012ac9  mov     rcx, rbx
0x140012acc  call    TdxConnectConnection
0x140012ad1  mov     r8d, 1031h
0x140012ad7  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140012ade  mov     rcx, r14
0x140012ae1  mov     ebp, eax
0x140012ae3  call    DbgTdxDereferenceTransportAddress
0x140012ae8  mov     r8d, 1032h
0x140012aee  lea     rdx, aTdxreissueconn; "TdxReissueConnectWhileListenRequests"
0x140012af5  mov     rcx, rbx
0x140012af8  call    DbgTdxDereferenceConnection
0x140012afd  cmp     ebp, 103h
0x140012b03  jz      short loc_140012B19
0x140012b05  mov     dl, 2; PriorityBoost
0x140012b07  mov     [rdi+30h], ebp
0x140012b0a  mov     rcx, rdi; Irp
0x140012b0d  call    cs:__imp_IofCompleteRequest
0x140012b14  nop     dword ptr [rax+rax+00h]
0x140012b19  mov     rdi, rsi
0x140012b1c  test    rsi, rsi
0x140012b1f  jnz     short loc_140012AA5
0x140012b21  add     rsp, 20h
0x140012b25  pop     r14
0x140012b27  pop     rdi
0x140012b28  pop     rsi
0x140012b29  pop     rbp
0x140012b2a  pop     rbx
0x140012b2b  retn
```
