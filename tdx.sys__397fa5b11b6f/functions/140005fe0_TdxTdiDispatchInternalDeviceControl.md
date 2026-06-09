# TdxTdiDispatchInternalDeviceControl

- ea: `0x140005fe0`
- end: `0x140006600`
- name: `TdxTdiDispatchInternalDeviceControl`
- size: `1568`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, IRP *)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010f10`

## callees

- `0x1400039c0`
- `0x140004920`
- `0x140004df4`
- `0x140005600`
- `0x140005688`
- `0x140005b00`
- `0x140005fe0`
- `0x140006608`
- `0x140006db0`
- `0x140009ad0`
- `0x14000aad0`
- `0x14000cb10`
- `0x14000f8d0`
- `0x140011cb4`
- `0x140012308`
- `0x140012894`
- `0x140013174`
- `0x1400135ec`
- `0x140013760`
- `0x140013bf8`
- `0x1400157cc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000614a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400062f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14000614a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400062f5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400060fa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400060fa`
- `ntoskrnl!IoFileObjectType` at `0x1400060d1`
- `ntoskrnl!IofCompleteRequest` at `0x140006076`
- `ntoskrnl!IofCompleteRequest` at `0x140006076`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000611d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006193`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006223`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000611d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006193`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006223`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000613b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000633c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400063d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006412`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000613b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000633c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400063d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006412`

## pseudocode

```c
__int64 __fastcall TdxTdiDispatchInternalDeviceControl(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  NTSTATUS v2; // ebp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  PFILE_OBJECT FileObject; // rcx
  PVOID FsContext2; // rax
  int *FsContext; // rsi
  int MinorFunction; // eax
  NTSTATUS AddressRequest; // eax
  KPROCESSOR_MODE RequestorMode; // r9
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  PVOID v13; // rdi
  __int64 v14; // r14
  KIRQL v15; // al
  KSPIN_LOCK *v16; // rcx
  KIRQL v17; // al
  int v18; // r8d
  KIRQL v19; // dl
  ULONG Length; // eax
  ULONG v21; // eax
  KIRQL v22; // al
  __int64 v23; // r14
  struct _LIST_ENTRY *v24; // r8
  PUNICODE_STRING FileName; // rcx
  PVOID Object; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  a2->IoStatus.Information = 0;
  if ( a1 == TdxDeviceObject )
  {
    v2 = -1073741822;
    goto LABEL_10;
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  FsContext2 = FileObject->FsContext2;
  if ( FsContext2 == (PVOID)1 )
  {
    FsContext = (int *)FileObject->FsContext;
    if ( CurrentStackLocation->MinorFunction == 9 )
      return TdxSendDatagramTransportAddress(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
    switch ( CurrentStackLocation->MinorFunction )
    {
      case 3u:
        AddressRequest = TdxConnectTransportAddress(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
        goto LABEL_8;
      case 6u:
        AddressRequest = TdxDisconnectTransportAddress(FileObject->FsContext, a2);
        goto LABEL_8;
      case 7u:
        return TdxSendTransportAddress(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
      case 0xAu:
        AddressRequest = TdxReceiveDatagramTransportAddress(FileObject->FsContext, a2);
        goto LABEL_8;
      case 0xBu:
        v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 1);
        v18 = *FsContext;
        v19 = v17;
        Length = CurrentStackLocation->Parameters.Read.Length;
        if ( (*FsContext & 2) != 0 )
        {
          if ( Length != 2 )
          {
            switch ( Length )
            {
              case 4u:
                *((_QWORD *)FsContext + 44) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
                *((_QWORD *)FsContext + 45) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
                break;
              case 8u:
                *((_QWORD *)FsContext + 46) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
                *((_QWORD *)FsContext + 47) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
                break;
              case 0xAu:
LABEL_66:
                *((_QWORD *)FsContext + 61) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
                *((_QWORD *)FsContext + 62) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
                break;
              default:
LABEL_59:
                v2 = -1073741811;
                break;
            }
            goto LABEL_23;
          }
LABEL_22:
          *((_QWORD *)FsContext + 59) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
          *((_QWORD *)FsContext + 60) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
LABEL_23:
          KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v19);
          break;
        }
        if ( Length == 2 )
          goto LABEL_22;
        switch ( Length )
        {
          case 0u:
            FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
            *((_QWORD *)FsContext + 49) = FileName;
            *((_QWORD *)FsContext + 50) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
            if ( !FileName || *((_QWORD *)FsContext + 42) || (v18 & 0x44) != 4 )
              goto LABEL_23;
            a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
            v24 = (struct _LIST_ENTRY *)*((_QWORD *)FsContext + 44);
            if ( (int *)v24->Flink != FsContext + 86 )
              __fastfail(3u);
            a2->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(FsContext + 86);
            a2->Tail.Overlay.ListEntry.Blink = v24;
            v24->Flink = &a2->Tail.Overlay.ListEntry;
            *((_QWORD *)FsContext + 44) = &a2->Tail.Overlay.ListEntry;
            if ( (*FsContext & 0x10) != 0 )
              KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v19);
            else
              TdxIssueListenRequest((int)FsContext);
            v2 = 259;
            break;
          case 1u:
            *((_QWORD *)FsContext + 51) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
            *((_QWORD *)FsContext + 52) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
            goto LABEL_23;
          case 3u:
            *((_QWORD *)FsContext + 53) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
            *((_QWORD *)FsContext + 54) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
            goto LABEL_23;
          case 5u:
            *((_QWORD *)FsContext + 55) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
            *((_QWORD *)FsContext + 56) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
            goto LABEL_23;
          case 6u:
            *((_QWORD *)FsContext + 57) = CurrentStackLocation->Parameters.QueryDirectory.FileName;
            *((_QWORD *)FsContext + 58) = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
            goto LABEL_23;
          case 7u:
          case 9u:
            goto LABEL_23;
          case 0xAu:
            goto LABEL_66;
          default:
            goto LABEL_59;
        }
        break;
      case 0xCu:
        v21 = CurrentStackLocation->Parameters.Read.Length;
        if ( v21 == 3 )
        {
          v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 1);
          if ( (*FsContext & 4) != 0 )
            goto LABEL_29;
          KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v22);
          v2 = -1073741811;
        }
        else
        {
          v2 = -1073741637;
          if ( v21 != 9 )
            v2 = -1073741811;
        }
        break;
      case 0xDu:
        goto LABEL_54;
      case 0x50u:
        goto LABEL_24;
      default:
        goto LABEL_40;
    }
  }
  else
  {
    if ( FsContext2 == (PVOID)2 )
    {
      MinorFunction = CurrentStackLocation->MinorFunction;
      FsContext = (int *)FileObject->FsContext;
      if ( MinorFunction == 7 )
      {
        AddressRequest = TdxSendConnection(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
      }
      else if ( MinorFunction == 80 )
      {
LABEL_24:
        AddressRequest = TdxIssueIoControlEndpointRequest(
                           FileObject->FsContext,
                           a2,
                           CurrentStackLocation->Parameters.QueryDirectory.FileName);
      }
      else
      {
        switch ( CurrentStackLocation->MinorFunction )
        {
          case 1u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_qs(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
                (_DWORD)FsContext,
                (__int64)"TdxAssociateConnection");
            }
            RequestorMode = a2->RequestorMode;
            SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
            Object = 0;
            v2 = ObReferenceObjectByHandle(
                   SecurityContext,
                   0,
                   (POBJECT_TYPE)IoFileObjectType,
                   RequestorMode,
                   &Object,
                   0);
            if ( v2 >= 0 )
            {
              v13 = Object;
              v14 = *((_QWORD *)Object + 3);
              v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 1);
              v16 = (KSPIN_LOCK *)(FsContext + 2);
              if ( *((_QWORD *)FsContext + 11) )
              {
                KeReleaseSpinLock(v16, v15);
                ObfDereferenceObject(v13);
                v2 = -1073741256;
              }
              else
              {
                KeReleaseSpinLock(v16, v15);
                v2 = TdxAssociateConnectionWithTransportAddress(v14, FsContext);
                ObfDereferenceObject(v13);
              }
            }
            goto LABEL_9;
          case 2u:
            AddressRequest = TdxDisassociateConnection(FileObject->FsContext);
            break;
          case 3u:
            AddressRequest = TdxConnectConnection(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
            break;
          case 4u:
            AddressRequest = TdxListenConnection(FileObject->FsContext);
            break;
          case 5u:
            AddressRequest = TdxAcceptConnection(FileObject->FsContext);
            break;
          case 6u:
            AddressRequest = TdxDisconnectConnection(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation);
            break;
          case 8u:
            AddressRequest = TdxReceiveConnection(FileObject->FsContext, a2, a2->Tail.Overlay.CurrentStackLocation, 0);
            break;
          case 0xCu:
            if ( CurrentStackLocation->Parameters.Read.Length == 3 )
            {
              v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 1);
              v23 = *((_QWORD *)FsContext + 11);
              if ( !v23 )
              {
                KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v22);
                v2 = -1073741255;
                goto LABEL_9;
              }
              if ( (unsigned int)(FsContext[19] - 4) <= 2 )
              {
LABEL_29:
                AddressRequest = TdxIssueQueryAddressRequest(FsContext, a2, v22);
              }
              else
              {
                KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v22);
                AddressRequest = TdxQueryInformationTransportAddress(v23, a2, CurrentStackLocation);
              }
            }
            else
            {
              if ( CurrentStackLocation->Parameters.Read.Length != 4 )
              {
                v2 = -1073741811;
                goto LABEL_9;
              }
              AddressRequest = TdxQueryConnectionInfo(FsContext);
            }
            break;
          case 0xDu:
LABEL_54:
            v2 = -1073741637;
            goto LABEL_10;
          default:
            goto LABEL_40;
        }
      }
    }
    else
    {
      if ( FsContext2 != (PVOID)3 || CurrentStackLocation->MinorFunction != 12 )
      {
LABEL_40:
        v2 = -1073741811;
        goto LABEL_10;
      }
      AddressRequest = TdxQueryInformationControlChannel(
                         FileObject->FsContext,
                         a2,
                         a2->Tail.Overlay.CurrentStackLocation);
    }
LABEL_8:
    v2 = AddressRequest;
  }
LABEL_9:
  if ( v2 != 259 )
  {
LABEL_10:
    a2->IoStatus.Status = v2;
    IofCompleteRequest(a2, 2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140005fe0  push    rbx
0x140005fe2  push    rbp
0x140005fe3  push    rsi
0x140005fe4  push    rdi
0x140005fe5  push    r14
0x140005fe7  push    r15
0x140005fe9  sub     rsp, 38h
0x140005fed  xor     ebp, ebp
0x140005fef  mov     rbx, rdx
0x140005ff2  mov     [rdx+38h], rbp
0x140005ff6  cmp     rcx, cs:TdxDeviceObject
0x140005ffd  jz      loc_140006385
0x140006003  mov     rdi, [rdx+0B8h]
0x14000600a  mov     rcx, [rdi+30h]
0x14000600e  mov     rax, [rcx+20h]
0x140006012  cmp     rax, 1
0x140006016  jnz     short loc_140006042
0x140006018  movzx   eax, byte ptr [rdi+1]
0x14000601c  mov     rsi, [rcx+18h]
0x140006020  cmp     eax, 9
0x140006023  jnz     loc_140006160
0x140006029  mov     r8, rdi
0x14000602c  mov     rcx, rsi
0x14000602f  call    TdxSendDatagramTransportAddress
0x140006034  add     rsp, 38h
0x140006038  pop     r15
0x14000603a  pop     r14
0x14000603c  pop     rdi
0x14000603d  pop     rsi
0x14000603e  pop     rbp
0x14000603f  pop     rbx
0x140006040  retn
0x140006042  cmp     rax, 2
0x140006046  jnz     loc_140006319
0x14000604c  movzx   eax, byte ptr [rdi+1]
0x140006050  mov     rsi, [rcx+18h]
0x140006054  cmp     eax, 7
0x140006057  jnz     short loc_140006086
0x140006059  mov     r8, rdi
0x14000605c  mov     rcx, rsi
0x14000605f  call    TdxSendConnection
0x140006064  mov     ebp, eax
0x140006066  cmp     ebp, 103h
0x14000606c  jz      short loc_140006082
0x14000606e  mov     dl, 2; PriorityBoost
0x140006070  mov     [rbx+30h], ebp
0x140006073  mov     rcx, rbx; Irp
0x140006076  call    cs:__imp_IofCompleteRequest
0x14000607d  nop     dword ptr [rax+rax+00h]
0x140006082  mov     eax, ebp
0x140006084  jmp     short loc_140006034
0x140006086  cmp     eax, 50h ; 'P'
0x140006089  jz      loc_1400061E3
0x14000608f  dec     eax; switch 13 cases
0x140006091  cmp     eax, 0Ch
0x140006094  ja      def_1400060AE; jumptable 00000001400060AE default case, cases 7,9-11
0x14000609a  cdqe
0x14000609c  lea     r14, cs:140000000h
0x1400060a3  mov     eax, ds:(jpt_1400060AE - 140000000h)[r14+rax*4]
0x1400060ab  add     rax, r14
0x1400060ae  jmp     rax; switch jump
0x1400060b4  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001400060AE case 1
0x1400060bb  lea     rax, WPP_GLOBAL_Control
0x1400060c2  cmp     rcx, rax
0x1400060c5  jz      short loc_1400060D1
0x1400060c7  cmp     byte ptr [rcx+29h], 5
0x1400060cb  jnb     loc_1400065B0
0x1400060d1  mov     r8, cs:__imp_IoFileObjectType
0x1400060d8  lea     rax, [rsp+68h+arg_0]
0x1400060dd  movzx   r9d, byte ptr [rbx+40h]; AccessMode
0x1400060e2  xor     edx, edx; DesiredAccess
0x1400060e4  mov     rcx, [rdi+8]; Handle
0x1400060e8  mov     [rsp+68h+HandleInformation], rbp; HandleInformation
0x1400060ed  mov     r8, [r8]; ObjectType
0x1400060f0  mov     [rsp+68h+arg_0], rbp
0x1400060f5  mov     [rsp+68h+Object], rax; Object
0x1400060fa  call    cs:__imp_ObReferenceObjectByHandle
0x140006101  nop     dword ptr [rax+rax+00h]
0x140006106  mov     ebp, eax
0x140006108  test    eax, eax
0x14000610a  js      loc_140006066
0x140006110  mov     rdi, [rsp+68h+arg_0]
0x140006115  lea     rcx, [rsi+8]; SpinLock
0x140006119  mov     r14, [rdi+18h]
0x14000611d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006124  nop     dword ptr [rax+rax+00h]
0x140006129  cmp     qword ptr [rsi+58h], 0
0x14000612e  lea     rcx, [rsi+8]; SpinLock
0x140006132  movzx   edx, al; NewIrql
0x140006135  jz      loc_1400062D9
0x14000613b  call    cs:__imp_KeReleaseSpinLock
0x140006142  nop     dword ptr [rax+rax+00h]
0x140006147  mov     rcx, rdi; Object
0x14000614a  call    cs:__imp_ObfDereferenceObject
0x140006151  nop     dword ptr [rax+rax+00h]
0x140006156  mov     ebp, 0C0000238h
0x14000615b  jmp     loc_140006066
0x140006160  add     eax, 0FFFFFFFDh; switch 78 cases
0x140006163  cmp     eax, 4Dh
0x140006166  ja      def_1400060AE; jumptable 00000001400060AE default case, cases 7,9-11
0x14000616c  lea     r14, cs:140000000h
0x140006173  cdqe
0x140006175  movzx   eax, ds:(byte_14001B4FD - 140000000h)[r14+rax]
0x14000617e  mov     edx, ds:(jpt_140006189 - 140000000h)[r14+rax*4]
0x140006186  add     rdx, r14
0x140006189  jmp     rdx; switch jump
0x14000618f  lea     rcx, [rsi+8]; jumptable 0000000140006189 case 11
0x140006193  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000619a  nop     dword ptr [rax+rax+00h]
0x14000619f  mov     r8d, [rsi]
0x1400061a2  movzx   edx, al; NewIrql
0x1400061a5  movsxd  rax, dword ptr [rdi+8]
0x1400061a9  test    r8b, 2
0x1400061ad  jz      short loc_1400061F4
0x1400061af  cmp     eax, 2
0x1400061b2  jnz     loc_140006442
0x1400061b8  mov     rax, [rdi+10h]
0x1400061bc  mov     [rsi+1D8h], rax
0x1400061c3  mov     rax, [rdi+18h]
0x1400061c7  mov     [rsi+1E0h], rax
0x1400061ce  lea     rcx, [rsi+8]; jumptable 000000014000620D cases 7,9
0x1400061d2  call    cs:__imp_KeReleaseSpinLock
0x1400061d9  nop     dword ptr [rax+rax+00h]
0x1400061de  jmp     loc_140006066
0x1400061e3  mov     r8, [rdi+10h]
0x1400061e7  mov     rcx, rsi
0x1400061ea  call    TdxIssueIoControlEndpointRequest
0x1400061ef  jmp     loc_140006064
0x1400061f4  cmp     eax, 2
0x1400061f7  jz      short loc_1400061B8
0x1400061f9  cmp     eax, 0Ah; switch 11 cases
0x1400061fc  ja      def_14000620D; jumptable 000000014000620D default case, cases 2,4,8
0x140006202  mov     ecx, ds:(jpt_14000620D - 140000000h)[r14+rax*4]
0x14000620a  add     rcx, r14
0x14000620d  jmp     rcx; switch jump
0x140006213  mov     eax, [rdi+8]; jumptable 0000000140006189 case 12
0x140006216  cmp     eax, 3
0x140006219  jnz     loc_1400063F6
0x14000621f  lea     rcx, [rsi+8]; SpinLock
0x140006223  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000622a  nop     dword ptr [rax+rax+00h]
0x14000622f  mov     edx, [rsi]
0x140006231  test    dl, 4
0x140006234  jz      loc_14000640B
0x14000623a  movzx   r8d, al
0x14000623e  mov     rdx, rbx
0x140006241  mov     rcx, rsi
0x140006244  call    TdxIssueQueryAddressRequest
0x140006249  jmp     loc_140006064
0x14000624e  mov     r8, rdi; jumptable 00000001400060AE case 3
0x140006251  mov     rcx, rsi
0x140006254  call    TdxConnectConnection
0x140006259  jmp     loc_140006064
0x14000625e  mov     r8, rdi; jumptable 0000000140006189 case 7
0x140006261  mov     rdx, rbx
0x140006264  mov     rcx, rsi
0x140006267  call    TdxSendTransportAddress
0x14000626c  add     rsp, 38h
0x140006270  pop     r15
0x140006272  pop     r14
0x140006274  pop     rdi
0x140006275  pop     rsi
0x140006276  pop     rbp
0x140006277  pop     rbx
0x140006278  retn
0x14000627a  mov     rcx, rsi; jumptable 00000001400060AE case 2
0x14000627d  call    TdxDisassociateConnection
0x140006282  jmp     loc_140006064
0x140006287  mov     r8, rdi; jumptable 00000001400060AE case 6
0x14000628a  mov     rcx, rsi
0x14000628d  call    TdxDisconnectConnection
0x140006292  jmp     loc_140006064
0x140006297  mov     ecx, [rdi+8]; jumptable 00000001400060AE case 12
0x14000629a  sub     ecx, 3
0x14000629d  jnz     loc_140006580
0x1400062a3  lea     rcx, [rsi+8]; SpinLock
0x1400062a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062ae  nop     dword ptr [rax+rax+00h]
0x1400062b3  mov     r14, [rsi+58h]
0x1400062b7  movzx   edx, al; NewIrql
0x1400062ba  test    r14, r14
0x1400062bd  jnz     short loc_140006329
0x1400062bf  lea     rcx, [rsi+8]; SpinLock
0x1400062c3  call    cs:__imp_KeReleaseSpinLock
0x1400062ca  nop     dword ptr [rax+rax+00h]
0x1400062cf  mov     ebp, 0C0000239h
0x1400062d4  jmp     loc_140006066
0x1400062d9  call    cs:__imp_KeReleaseSpinLock
0x1400062e0  nop     dword ptr [rax+rax+00h]
0x1400062e5  mov     rdx, rsi
0x1400062e8  mov     rcx, r14
0x1400062eb  call    TdxAssociateConnectionWithTransportAddress
0x1400062f0  mov     rcx, rdi; Object
0x1400062f3  mov     ebp, eax
0x1400062f5  call    cs:__imp_ObfDereferenceObject
0x1400062fc  nop     dword ptr [rax+rax+00h]
0x140006301  jmp     loc_140006066
0x140006306  xor     r9d, r9d; jumptable 00000001400060AE case 8
0x140006309  mov     r8, rdi
0x14000630c  mov     rcx, rsi
0x14000630f  call    TdxReceiveConnection
0x140006314  jmp     loc_140006064
0x140006319  cmp     rax, 3
0x14000631d  jz      short loc_14000636E
0x14000631f  mov     ebp, 0C000000Dh; jumptable 00000001400060AE default case, cases 7,9-11
0x140006324  jmp     loc_14000606E
0x140006329  mov     eax, [rsi+4Ch]
0x14000632c  sub     eax, 4
0x14000632f  cmp     eax, 2
0x140006332  jbe     loc_14000659C
0x140006338  lea     rcx, [rsi+8]; SpinLock
0x14000633c  call    cs:__imp_KeReleaseSpinLock
0x140006343  nop     dword ptr [rax+rax+00h]
0x140006348  mov     r8, rdi
0x14000634b  mov     rdx, rbx
0x14000634e  mov     rcx, r14
0x140006351  call    TdxQueryInformationTransportAddress
0x140006356  jmp     loc_140006064
0x14000635b  mov     r8, rdi; jumptable 0000000140006189 case 3
0x14000635e  mov     rdx, rbx
0x140006361  mov     rcx, rsi
0x140006364  call    TdxConnectTransportAddress
0x140006369  jmp     loc_140006064
0x14000636e  cmp     byte ptr [rdi+1], 0Ch
0x140006372  jnz     short def_1400060AE; jumptable 00000001400060AE default case, cases 7,9-11
0x140006374  mov     rcx, [rcx+18h]
0x140006378  mov     r8, rdi
0x14000637b  call    TdxQueryInformationControlChannel
0x140006380  jmp     loc_140006064
0x140006385  mov     ebp, 0C0000002h
0x14000638a  jmp     loc_14000606E
0x14000638f  mov     rax, [rbx+0B8h]
0x140006396  lea     rcx, [rsi+158h]
0x14000639d  or      byte ptr [rax+3], 1
0x1400063a1  mov     r8, [rcx+8]
0x1400063a5  cmp     [r8], rcx
0x1400063a8  jnz     loc_1400064EB
0x1400063ae  lea     rax, [rbx+0A8h]
0x1400063b5  mov     [rax], rcx
0x1400063b8  mov     [rax+8], r8
0x1400063bc  mov     [r8], rax
0x1400063bf  mov     [rcx+8], rax
0x1400063c3  mov     eax, [rsi]
0x1400063c5  test    al, 10h
0x1400063c7  jz      loc_1400064F2
0x1400063cd  lea     rcx, [rsi+8]; SpinLock
0x1400063d1  call    cs:__imp_KeReleaseSpinLock
0x1400063d8  nop     dword ptr [rax+rax+00h]
0x1400063dd  jmp     loc_1400064FA
0x1400063e2  mov     r8, [rdi+10h]; jumptable 0000000140006189 case 80
0x1400063e6  mov     rdx, rbx
0x1400063e9  mov     rcx, rsi
0x1400063ec  call    TdxIssueIoControlEndpointRequest
0x1400063f1  jmp     loc_140006064
0x1400063f6  cmp     eax, 9
0x1400063f9  mov     ebp, 0C00000BBh
0x1400063fe  mov     ecx, 0C000000Dh
0x140006403  cmovnz  ebp, ecx
0x140006406  jmp     loc_140006066
0x14000640b  movzx   edx, al; NewIrql
0x14000640e  lea     rcx, [rsi+8]; SpinLock
0x140006412  call    cs:__imp_KeReleaseSpinLock
0x140006419  nop     dword ptr [rax+rax+00h]
0x14000641e  mov     ebp, 0C000000Dh
0x140006423  jmp     loc_140006066
0x140006428  mov     ebp, 0C00000BBh; jumptable 00000001400060AE case 13
0x14000642d  jmp     loc_14000606E
0x140006432  mov     rdx, rbx; jumptable 0000000140006189 case 10
0x140006435  mov     rcx, rsi
0x140006438  call    TdxReceiveDatagramTransportAddress
0x14000643d  jmp     loc_140006064
0x140006442  cmp     eax, 4
0x140006445  jz      short loc_140006476
0x140006447  cmp     eax, 8
0x14000644a  jz      short loc_14000645B
0x14000644c  cmp     eax, 0Ah
0x14000644f  jz      short loc_1400064D0; jumptable 000000014000620D case 10
0x140006451  mov     ebp, 0C000000Dh; jumptable 000000014000620D default case, cases 2,4,8
0x140006456  jmp     loc_1400061CE; jumptable 000000014000620D cases 7,9
0x14000645b  mov     rax, [rdi+10h]
0x14000645f  mov     [rsi+170h], rax
0x140006466  mov     rax, [rdi+18h]
0x14000646a  mov     [rsi+178h], rax
0x140006471  jmp     loc_1400061CE; jumptable 000000014000620D cases 7,9
0x140006476  mov     rax, [rdi+10h]
0x14000647a  mov     [rsi+160h], rax
0x140006481  mov     rax, [rdi+18h]
0x140006485  mov     [rsi+168h], rax
0x14000648c  jmp     loc_1400061CE; jumptable 000000014000620D cases 7,9
0x140006491  mov     rcx, [rdi+10h]; jumptable 000000014000620D case 0
0x140006495  mov     [rsi+188h], rcx
0x14000649c  mov     rax, [rdi+18h]
0x1400064a0  mov     [rsi+190h], rax
0x1400064a7  test    rcx, rcx
0x1400064aa  jz      loc_1400061CE; jumptable 000000014000620D cases 7,9
0x1400064b0  cmp     [rsi+150h], rbp
0x1400064b7  jnz     loc_1400061CE; jumptable 000000014000620D cases 7,9
0x1400064bd  and     r8b, 44h
0x1400064c1  cmp     r8b, 4
0x1400064c5  jnz     loc_1400061CE; jumptable 000000014000620D cases 7,9
  ... truncated ...
```
