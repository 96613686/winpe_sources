# UdfProcessException

- ea: `0x140015a34`
- end: `0x140015dce`
- name: `UdfProcessException`
- size: `922`
- prototype: `__int64 __fastcall(PVOID Context1, PIRP Irp)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`
- `0x140009b94`

## callees

- `0x1400030e0`
- `0x140009b94`
- `0x14000b128`
- `0x14000ca10`
- `0x14000cad4`
- `0x140015a34`
- `0x14002dc10`

## import_xrefs

- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140015b5f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140015b5f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140015bdd`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140015bdd`
- `ntoskrnl!CcMdlWriteAbort` at `0x140015a85`
- `ntoskrnl!CcMdlWriteAbort` at `0x140015a85`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140015ad1`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140015ad1`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015c57`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015c89`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015d0f`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015d2f`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015c57`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015c89`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015d0f`
- `ntoskrnl!IoGetDeviceToVerify` at `0x140015d2f`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015c6f`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015ca3`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015dab`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015c6f`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015ca3`
- `ntoskrnl!IoSetDeviceToVerify` at `0x140015dab`
- `ntoskrnl!IoRaiseHardError` at `0x140015d9a`
- `ntoskrnl!IoRaiseHardError` at `0x140015d9a`

## pseudocode

```c
__int64 __fastcall UdfProcessException(_DWORD *Context1, PIRP Irp, NTSTATUS a3)
{
  unsigned int v3; // ebx
  PIRP v4; // rsi
  PVOID v5; // rdi
  struct _MDL *MdlAddress; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // ecx
  struct _DEVICE_OBJECT *DeviceToVerify; // rbx
  __int64 v13; // rax
  PFILE_OBJECT FileObject; // rcx
  struct _VPB *Vpb; // r13
  struct _KTHREAD *Thread; // r12
  struct _DEVICE_OBJECT *v17; // r15
  __int64 v18; // rax

  v3 = a3;
  v4 = Irp;
  v5 = Context1;
  if ( !Context1 )
    goto LABEL_30;
  v3 = Context1[6];
  if ( *((_BYTE *)Context1 + 56) == 4 && (*((_BYTE *)Context1 + 57) & 6) == 6 )
  {
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress )
    {
      CcMdlWriteAbort(v4->Tail.Overlay.CurrentStackLocation->FileObject, MdlAddress);
      v4->MdlAddress = 0;
    }
  }
  if ( v3 == -1073741608 )
  {
    if ( (*((_DWORD *)v5 + 7) & 8) != 0 )
LABEL_8:
      v3 = UdfFsdPostRequest(v5, v4);
  }
  else
  {
    if ( v3 == -2147483626 && (*((_DWORD *)v5 + 7) & 0x10) != 0 && KeAreAllApcsDisabled() )
      goto LABEL_8;
    if ( v3 == -1073741566 || v3 == -1073741774 )
    {
      v7 = *((_QWORD *)v5 + 2);
      if ( v7 )
      {
        if ( (*((_DWORD *)v5 + 7) & 0x10) != 0 && (*(_DWORD *)(v7 + 48) & 0x4010) == 0 )
        {
          v8 = *(_QWORD *)(*((_QWORD *)v5 + 1) + 184LL);
          if ( *(_QWORD *)(v8 + 48) )
          {
            v9 = *((_QWORD *)v5 + 2);
            if ( MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v9 + 2144) > 0x2FAF080u )
            {
              *(_QWORD *)(v9 + 2144) = MEMORY[0xFFFFF78000000014];
              FsRtlNotifyVolumeEvent(*(PFILE_OBJECT *)(v8 + 48), 7u);
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x80000) != 0 )
              {
                WPP_SF_(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  11,
                  WPP_ff7573e102473c13b86ff0e95821cb5b_Traceguids);
              }
            }
          }
        }
      }
    }
  }
  if ( v3 == 259 || v3 == -1073741608 )
    return v3;
  *((_DWORD *)v5 + 7) &= ~2u;
  v4->IoStatus.Status = v3;
  v10 = *((_DWORD *)v5 + 7);
  if ( (v10 & 0x10) == 0 )
  {
    if ( IoGetTopLevelIrp() == (PIRP)2 && v3 == -2147483626 )
      v3 = -1073741740;
    goto LABEL_28;
  }
  if ( v3 + 1073741662 > 1 && v3 + 1073741806 > 2 )
  {
    if ( v3 == -2147483626 )
    {
LABEL_37:
      DeviceToVerify = IoGetDeviceToVerify(v4->Tail.Overlay.Thread);
      IoSetDeviceToVerify(v4->Tail.Overlay.Thread, 0);
      if ( !DeviceToVerify )
      {
        DeviceToVerify = IoGetDeviceToVerify(KeGetCurrentThread());
        IoSetDeviceToVerify(KeGetCurrentThread(), 0);
      }
      v13 = *((_QWORD *)v5 + 2);
      if ( v13 )
        DeviceToVerify = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v13 + 8) + 16LL);
      Irp = v4;
      Context1 = v5;
      if ( !DeviceToVerify )
      {
        v3 = -1073741437;
        goto LABEL_29;
      }
      return UdfPerformVerify(v5, v4, DeviceToVerify);
    }
    if ( v3 != -1073741643 )
    {
LABEL_28:
      Context1 = v5;
      Irp = v4;
LABEL_29:
      a3 = v3;
LABEL_30:
      UdfCompleteRequest(Context1, Irp, a3);
      return v3;
    }
  }
  if ( v3 == -2147483626 )
    goto LABEL_37;
  if ( (v10 & 0x200) != 0 )
    goto LABEL_28;
  FileObject = v4->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject )
    Vpb = FileObject->Vpb;
  else
    Vpb = 0;
  Thread = v4->Tail.Overlay.Thread;
  v17 = IoGetDeviceToVerify(Thread);
  if ( !v17 )
  {
    Thread = KeGetCurrentThread();
    v17 = IoGetDeviceToVerify(Thread);
  }
  v18 = *((_QWORD *)v5 + 2);
  if ( v18 )
    v17 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v18 + 8) + 16LL);
  if ( !v17 )
    goto LABEL_28;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x80000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 12, WPP_ff7573e102473c13b86ff0e95821cb5b_Traceguids);
  }
  v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  IoRaiseHardError(v4, Vpb, v17);
  IoSetDeviceToVerify(Thread, 0);
  UdfCompleteRequest(v5, 0, 0);
  return 259;
}

```

## disassembly

```asm
0x140015a34  mov     [rsp+arg_8], rdx
0x140015a39  mov     [rsp+arg_0], rcx
0x140015a3e  push    rbx
0x140015a3f  push    rsi
0x140015a40  push    rdi
0x140015a41  push    r12
0x140015a43  push    r13
0x140015a45  push    r14
0x140015a47  push    r15
0x140015a49  sub     rsp, 20h
0x140015a4d  mov     ebx, r8d
0x140015a50  mov     rsi, rdx
0x140015a53  mov     rdi, rcx
0x140015a56  test    rcx, rcx
0x140015a59  jz      loc_140015C06
0x140015a5f  mov     ebx, [rcx+18h]
0x140015a62  cmp     byte ptr [rcx+38h], 4
0x140015a66  jnz     short loc_140015A99
0x140015a68  mov     al, [rcx+39h]
0x140015a6b  and     al, 6
0x140015a6d  cmp     al, 6
0x140015a6f  jnz     short loc_140015A99
0x140015a71  mov     rdx, [rdx+8]; MdlChain
0x140015a75  test    rdx, rdx
0x140015a78  jz      short loc_140015A99
0x140015a7a  mov     rcx, [rsi+0B8h]
0x140015a81  mov     rcx, [rcx+30h]; FileObject
0x140015a85  call    cs:__imp_CcMdlWriteAbort
0x140015a8c  nop     dword ptr [rax+rax+00h]
0x140015a91  mov     qword ptr [rsi+8], 0
0x140015a99  cmp     ebx, 0C00000D8h
0x140015a9f  jnz     short loc_140015AC2
0x140015aa1  mov     eax, [rdi+1Ch]
0x140015aa4  test    al, 8
0x140015aa6  jz      loc_140015B9E
0x140015aac  mov     rdx, rsi; Context2
0x140015aaf  mov     rcx, rdi; Context1
0x140015ab2  call    UdfFsdPostRequest
0x140015ab7  mov     ebx, eax
0x140015ab9  mov     [rsp+58h+arg_10], eax
0x140015abd  jmp     loc_140015B9E
0x140015ac2  cmp     ebx, 80000016h
0x140015ac8  jnz     short loc_140015AE1
0x140015aca  mov     eax, [rdi+1Ch]
0x140015acd  test    al, 10h
0x140015acf  jz      short loc_140015AE1
0x140015ad1  call    cs:__imp_KeAreAllApcsDisabled
0x140015ad8  nop     dword ptr [rax+rax+00h]
0x140015add  test    al, al
0x140015adf  jnz     short loc_140015AAC
0x140015ae1  cmp     ebx, 0C0000102h
0x140015ae7  jz      short loc_140015AF5
0x140015ae9  cmp     ebx, 0C0000032h
0x140015aef  jnz     loc_140015B9E
0x140015af5  mov     rcx, [rdi+10h]
0x140015af9  test    rcx, rcx
0x140015afc  jz      loc_140015B9E
0x140015b02  mov     eax, [rdi+1Ch]
0x140015b05  test    al, 10h
0x140015b07  jz      loc_140015B9E
0x140015b0d  test    dword ptr [rcx+30h], 4010h
0x140015b14  jnz     loc_140015B9E
0x140015b1a  mov     rax, [rdi+8]
0x140015b1e  mov     rcx, [rax+0B8h]
0x140015b25  cmp     qword ptr [rcx+30h], 0
0x140015b2a  jz      short loc_140015B9E
0x140015b2c  mov     rdx, 0FFFFF78000000014h
0x140015b36  mov     rdx, [rdx]
0x140015b39  mov     r8, [rdi+10h]
0x140015b3d  mov     rax, rdx
0x140015b40  sub     rax, [r8+860h]
0x140015b47  cmp     rax, 2FAF080h
0x140015b4d  jbe     short loc_140015B9E
0x140015b4f  mov     [r8+860h], rdx
0x140015b56  mov     edx, 7; EventCode
0x140015b5b  mov     rcx, [rcx+30h]; FileObject
0x140015b5f  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140015b66  nop     dword ptr [rax+rax+00h]
0x140015b6b  lea     r14, WPP_GLOBAL_Control
0x140015b72  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b79  cmp     rcx, r14
0x140015b7c  jz      short loc_140015BA5
0x140015b7e  test    dword ptr [rcx+2Ch], 80000h
0x140015b85  jz      short loc_140015BA5
0x140015b87  mov     edx, 0Bh
0x140015b8c  lea     r8, WPP_ff7573e102473c13b86ff0e95821cb5b_Traceguids
0x140015b93  mov     rcx, [rcx+18h]
0x140015b97  call    WPP_SF_
0x140015b9c  jmp     short loc_140015BA5
0x140015b9e  lea     r14, WPP_GLOBAL_Control
0x140015ba5  jmp     short loc_140015BBE
0x140015ba7  mov     ebx, eax
0x140015ba9  mov     [rsp+58h+arg_10], eax
0x140015bad  lea     r14, WPP_GLOBAL_Control
0x140015bb4  mov     rsi, [rsp+58h+arg_8]
0x140015bb9  mov     rdi, [rsp+58h+arg_0]
0x140015bbe  cmp     ebx, 103h
0x140015bc4  jz      short loc_140015C0B
0x140015bc6  cmp     ebx, 0C00000D8h
0x140015bcc  jz      short loc_140015C0B
0x140015bce  and     dword ptr [rdi+1Ch], 0FFFFFFFDh
0x140015bd2  mov     [rsi+30h], ebx
0x140015bd5  mov     ecx, [rdi+1Ch]
0x140015bd8  test    cl, 10h
0x140015bdb  jnz     short loc_140015C1E
0x140015bdd  call    cs:__imp_IoGetTopLevelIrp
0x140015be4  nop     dword ptr [rax+rax+00h]
0x140015be9  cmp     rax, 2
0x140015bed  jnz     short loc_140015BFD
0x140015bef  mov     eax, 0C0000054h
0x140015bf4  cmp     ebx, 80000016h
0x140015bfa  cmovz   ebx, eax
0x140015bfd  mov     rcx, rdi
0x140015c00  mov     rdx, rsi
0x140015c03  mov     r8d, ebx
0x140015c06  call    UdfCompleteRequest
0x140015c0b  mov     eax, ebx
0x140015c0d  add     rsp, 20h
0x140015c11  pop     r15
0x140015c13  pop     r14
0x140015c15  pop     r13
0x140015c17  pop     r12
0x140015c19  pop     rdi
0x140015c1a  pop     rsi
0x140015c1b  pop     rbx
0x140015c1c  retn
0x140015c1e  lea     eax, [rbx+3FFFFF5Eh]
0x140015c24  cmp     eax, 1
0x140015c27  jbe     short loc_140015C44
0x140015c29  lea     eax, [rbx+3FFFFFEEh]
0x140015c2f  cmp     eax, 2
0x140015c32  jbe     short loc_140015C44
0x140015c34  cmp     ebx, 80000016h
0x140015c3a  jz      short loc_140015C50
0x140015c3c  cmp     ebx, 0C00000B5h
0x140015c42  jnz     short loc_140015BFD
0x140015c44  cmp     ebx, 80000016h
0x140015c4a  jnz     loc_140015CE2
0x140015c50  mov     rcx, [rsi+98h]; Thread
0x140015c57  call    cs:__imp_IoGetDeviceToVerify
0x140015c5e  nop     dword ptr [rax+rax+00h]
0x140015c63  mov     rbx, rax
0x140015c66  xor     edx, edx; DeviceObject
0x140015c68  mov     rcx, [rsi+98h]; Thread
0x140015c6f  call    cs:__imp_IoSetDeviceToVerify
0x140015c76  nop     dword ptr [rax+rax+00h]
0x140015c7b  test    rbx, rbx
0x140015c7e  jnz     short loc_140015CAF
0x140015c80  mov     rcx, gs:188h; Thread
0x140015c89  call    cs:__imp_IoGetDeviceToVerify
0x140015c90  nop     dword ptr [rax+rax+00h]
0x140015c95  mov     rbx, rax
0x140015c98  mov     rcx, gs:188h; Thread
0x140015ca1  xor     edx, edx; DeviceObject
0x140015ca3  call    cs:__imp_IoSetDeviceToVerify
0x140015caa  nop     dword ptr [rax+rax+00h]
0x140015caf  mov     rax, [rdi+10h]
0x140015cb3  test    rax, rax
0x140015cb6  jz      short loc_140015CC0
0x140015cb8  mov     rax, [rax+8]
0x140015cbc  mov     rbx, [rax+10h]
0x140015cc0  mov     rdx, rsi; Irp
0x140015cc3  mov     rcx, rdi; Context1
0x140015cc6  test    rbx, rbx
0x140015cc9  jnz     short loc_140015CD5
0x140015ccb  mov     ebx, 0C0000183h
0x140015cd0  jmp     loc_140015C03
0x140015cd5  mov     r8, rbx; DeviceObject
0x140015cd8  call    UdfPerformVerify
0x140015cdd  jmp     loc_140015C0D
0x140015ce2  bt      ecx, 9
0x140015ce6  jb      loc_140015BFD
0x140015cec  mov     rax, [rsi+0B8h]
0x140015cf3  mov     rcx, [rax+30h]
0x140015cf7  test    rcx, rcx
0x140015cfa  jz      short loc_140015D02
0x140015cfc  mov     r13, [rcx+10h]
0x140015d00  jmp     short loc_140015D05
0x140015d02  xor     r13d, r13d
0x140015d05  mov     r12, [rsi+98h]
0x140015d0c  mov     rcx, r12; Thread
0x140015d0f  call    cs:__imp_IoGetDeviceToVerify
0x140015d16  nop     dword ptr [rax+rax+00h]
0x140015d1b  mov     r15, rax
0x140015d1e  test    rax, rax
0x140015d21  jnz     short loc_140015D3E
0x140015d23  mov     r12, gs:188h
0x140015d2c  mov     rcx, r12; Thread
0x140015d2f  call    cs:__imp_IoGetDeviceToVerify
0x140015d36  nop     dword ptr [rax+rax+00h]
0x140015d3b  mov     r15, rax
0x140015d3e  mov     rax, [rdi+10h]
0x140015d42  test    rax, rax
0x140015d45  jz      short loc_140015D4F
0x140015d47  mov     rax, [rax+8]
0x140015d4b  mov     r15, [rax+10h]
0x140015d4f  test    r15, r15
0x140015d52  jz      loc_140015BFD
0x140015d58  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d5f  cmp     rcx, r14
0x140015d62  jz      short loc_140015D85
0x140015d64  test    dword ptr [rcx+2Ch], 80000h
0x140015d6b  jz      short loc_140015D85
0x140015d6d  mov     edx, 0Ch
0x140015d72  mov     r9d, ebx
0x140015d75  lea     r8, WPP_ff7573e102473c13b86ff0e95821cb5b_Traceguids
0x140015d7c  mov     rcx, [rcx+18h]
0x140015d80  call    WPP_SF_d
0x140015d85  mov     r8, [rsi+0B8h]
0x140015d8c  or      byte ptr [r8+3], 1
0x140015d91  mov     r8, r15; RealDeviceObject
0x140015d94  mov     rdx, r13; Vpb
0x140015d97  mov     rcx, rsi; Irp
0x140015d9a  call    cs:__imp_IoRaiseHardError
0x140015da1  nop     dword ptr [rax+rax+00h]
0x140015da6  xor     edx, edx; DeviceObject
0x140015da8  mov     rcx, r12; Thread
0x140015dab  call    cs:__imp_IoSetDeviceToVerify
0x140015db2  nop     dword ptr [rax+rax+00h]
0x140015db7  xor     r8d, r8d
0x140015dba  xor     edx, edx
0x140015dbc  mov     rcx, rdi
0x140015dbf  call    UdfCompleteRequest
0x140015dc4  mov     eax, 103h
0x140015dc9  jmp     loc_140015C0D
0x14001db52  push    rbp
0x14001db54  sub     rsp, 20h
0x14001db58  mov     rbp, rdx
0x14001db5b  mov     rdx, rcx
0x14001db5e  mov     rcx, [rbp+60h]
0x14001db62  call    UdfExceptionFilter
0x14001db67  nop
0x14001db68  add     rsp, 20h
0x14001db6c  pop     rbp
0x14001db6d  retn
```
