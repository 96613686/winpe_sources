# SrvNetTdiOpenConnection

- ea: `0x1400511f0`
- end: `0x140051493`
- name: `SrvNetTdiOpenConnection`
- size: `675`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ce00`
- `0x1400161a4`

## callees

- `0x140008144`
- `0x14000d9c0`
- `0x14001389c`
- `0x140015790`
- `0x14002a3e0`
- `0x1400511f0`
- `0x14005149c`
- `0x140051710`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005132a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14005132a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140051311`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140051311`
- `ntoskrnl!NtCreateFile` at `0x1400512db`
- `ntoskrnl!NtCreateFile` at `0x1400512db`

## pseudocode

```c
__int64 __fastcall SrvNetTdiOpenConnection(__int64 a1)
{
  NTSTATUS v2; // edi
  PFILE_OBJECT *v3; // rsi
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  __int64 v5; // rcx
  __int64 TransportHandle; // rax
  __int64 v7; // r14
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-9h] BYREF
  _DWORD EaBuffer[2]; // [rsp+A8h] [rbp+7h] BYREF
  char v15[18]; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v16; // [rsp+C2h] [rbp+21h]
  __int16 v17; // [rsp+CAh] [rbp+29h]
  char v18; // [rsp+CCh] [rbp+2Bh]
  __int64 v19; // [rsp+CDh] [rbp+2Ch]
  __int16 v20; // [rsp+D5h] [rbp+34h]
  char v21; // [rsp+D7h] [rbp+36h]

  v19 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v18 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  if ( *(_DWORD *)(a1 + 480) )
    return 3221225659LL;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(*(_QWORD *)(a1 + 448) + 72LL);
  strcpy(v15, "ConnectionContext");
  v16 = a1;
  EaBuffer[0] = 0;
  EaBuffer[1] = 528640;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtCreateFile((PHANDLE)(a1 + 392), 0, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 0, 0, EaBuffer, 0x22u);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_12;
    }
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v10 = 30;
    goto LABEL_28;
  }
  v3 = (PFILE_OBJECT *)(a1 + 400);
  v2 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 392), 0, 0, 0, (PVOID *)(a1 + 400), 0);
  if ( v2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_12;
    }
    v10 = 31;
LABEL_27:
    AttachedDevice = v9->AttachedDevice;
LABEL_28:
    WPP_SF_d(AttachedDevice, v10, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids, (unsigned int)v2);
    goto LABEL_12;
  }
  RelatedDeviceObject = IoGetRelatedDeviceObject(*v3);
  v5 = *(_QWORD *)(a1 + 448);
  *(_QWORD *)(a1 + 408) = RelatedDeviceObject;
  TransportHandle = SrvNetEndpointGetTransportHandle(v5);
  v7 = TransportHandle;
  if ( !TransportHandle )
  {
    v2 = -1073741436;
LABEL_12:
    SrvNetTdiCloseConnection(a1);
    return (unsigned int)v2;
  }
  v2 = SrvNetTdiIssueAssociateRequest(*v3, a1 + 408, *(_QWORD *)(TransportHandle + 8));
  SrvNetDereferenceHandle(v7);
  if ( v2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_12;
    }
    v10 = 32;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400511f0  mov     r11, rsp
0x1400511f3  push    rbp
0x1400511f4  push    rbx
0x1400511f5  push    r15
0x1400511f7  lea     rbp, [r11-5Fh]
0x1400511fb  sub     rsp, 0E0h
0x140051202  mov     rax, cs:__security_cookie
0x140051209  xor     rax, rsp
0x14005120c  mov     [rbp+57h+var_20], rax
0x140051210  xor     eax, eax
0x140051212  xor     r15d, r15d
0x140051215  xorps   xmm0, xmm0
0x140051218  mov     rbx, rcx
0x14005121b  mov     [rbp+57h+var_2B], rax
0x14005121f  mov     [rbp+57h+var_23], ax
0x140051223  mov     [rbp+57h+var_21], al
0x140051226  mov     [rbp+57h+var_2E], r15w
0x14005122b  mov     [rbp+57h+var_2C], al
0x14005122e  mov     dword ptr [rbp+57h+ObjectAttributes+4], r15d
0x140051232  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r15d
0x140051236  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14005123a  cmp     [rcx+1E0h], eax
0x140051240  jnz     loc_1400513C5
0x140051246  movzx   eax, word ptr cs:aConnectioncont+10h; "t"
0x14005124d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140051251  movups  xmm0, xmmword ptr cs:aConnectioncont; "ConnectionContext"
0x140051258  mov     dword ptr [rsp+50h], 22h ; '"'; EaLength
0x140051260  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140051264  mov     word ptr [rbp+57h+var_48+10h], ax
0x140051268  xor     edx, edx; DesiredAccess
0x14005126a  mov     rax, [rcx+1C0h]
0x140051271  add     rax, 48h ; 'H'
0x140051275  mov     [r11+10h], rsi
0x140051279  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005127d  lea     rax, [rbp+57h+var_50]
0x140051281  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x140051286  mov     [rsp+0F0h+CreateOptions], r15d; CreateOptions
0x14005128b  mov     [rsp+0F0h+CreateDisposition], r15d; CreateDisposition
0x140051290  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140051294  mov     [rsp+0F0h+ShareAccess], r15d; ShareAccess
0x140051299  mov     [rbp+57h+var_36], rcx
0x14005129d  xorps   xmm0, xmm0
0x1400512a0  mov     [r11+18h], rdi
0x1400512a4  add     rcx, 188h; FileHandle
0x1400512ab  mov     [rsp+0F0h+FileAttributes], r15d; FileAttributes
0x1400512b0  mov     [rsp+0F0h+AllocationSize], r15; AllocationSize
0x1400512b5  mov     [r11+20h], r14
0x1400512b9  mov     [rbp+57h+var_50], r15d
0x1400512bd  mov     [rbp+57h+var_4C], 81100h
0x1400512c4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400512cb  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400512cf  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400512d6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400512db  call    cs:__imp_NtCreateFile
0x1400512e2  nop     dword ptr [rax+rax+00h]
0x1400512e7  mov     edi, eax
0x1400512e9  test    eax, eax
0x1400512eb  js      loc_140051409
0x1400512f1  mov     rcx, [rbx+188h]; Handle
0x1400512f8  lea     rsi, [rbx+190h]
0x1400512ff  mov     qword ptr [rsp+0F0h+FileAttributes], r15; HandleInformation
0x140051304  xor     r9d, r9d; AccessMode
0x140051307  xor     r8d, r8d; ObjectType
0x14005130a  mov     [rsp+0F0h+AllocationSize], rsi; Object
0x14005130f  xor     edx, edx; DesiredAccess
0x140051311  call    cs:__imp_ObReferenceObjectByHandle
0x140051318  nop     dword ptr [rax+rax+00h]
0x14005131d  mov     edi, eax
0x14005131f  test    eax, eax
0x140051321  js      loc_14005143B
0x140051327  mov     rcx, [rsi]; FileObject
0x14005132a  call    cs:__imp_IoGetRelatedDeviceObject
0x140051331  nop     dword ptr [rax+rax+00h]
0x140051336  mov     rcx, [rbx+1C0h]
0x14005133d  mov     [rbx+198h], rax
0x140051344  call    SrvNetEndpointGetTransportHandle
0x140051349  mov     r14, rax
0x14005134c  test    rax, rax
0x14005134f  jz      short loc_1400513CC
0x140051351  mov     r8, [rax+8]
0x140051355  lea     rdx, [rbx+198h]
0x14005135c  mov     rcx, [rsi]
0x14005135f  call    SrvNetTdiIssueAssociateRequest
0x140051364  mov     rcx, r14
0x140051367  mov     edi, eax
0x140051369  call    SrvNetDereferenceHandle
0x14005136e  test    edi, edi
0x140051370  js      short loc_1400513DD
0x140051372  mov     rcx, cs:WPP_GLOBAL_Control
0x140051379  lea     rax, WPP_GLOBAL_Control
0x140051380  cmp     rcx, rax
0x140051383  jz      short loc_140051392
0x140051385  test    dword ptr [rcx+2Ch], 400h
0x14005138c  jnz     loc_14005146F
0x140051392  xor     eax, eax
0x140051394  mov     rdi, [rsp+0F0h+arg_10]
0x14005139c  mov     rsi, [rsp+0F0h+arg_8]
0x1400513a4  mov     r14, [rsp+0F0h+arg_18]
0x1400513ac  mov     rcx, [rbp+57h+var_20]
0x1400513b0  xor     rcx, rsp; StackCookie
0x1400513b3  call    __security_check_cookie
0x1400513b8  add     rsp, 0E0h
0x1400513bf  pop     r15
0x1400513c1  pop     rbx
0x1400513c2  pop     rbp
0x1400513c3  retn
0x1400513c5  mov     eax, 0C00000BBh
0x1400513ca  jmp     short loc_1400513AC
0x1400513cc  mov     edi, 0C0000184h
0x1400513d1  mov     rcx, rbx
0x1400513d4  call    SrvNetTdiCloseConnection
0x1400513d9  mov     eax, edi
0x1400513db  jmp     short loc_140051394
0x1400513dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400513e4  lea     rax, WPP_GLOBAL_Control
0x1400513eb  cmp     rcx, rax
0x1400513ee  jz      short loc_1400513D1
0x1400513f0  test    dword ptr [rcx+2Ch], 400h
0x1400513f7  jz      short loc_1400513D1
0x1400513f9  cmp     byte ptr [rcx+29h], 1
0x1400513fd  jb      short loc_1400513D1
0x1400513ff  mov     edx, 20h ; ' '
0x140051404  jmp     loc_1400576F4
0x140051409  mov     r10, cs:WPP_GLOBAL_Control
0x140051410  lea     rax, WPP_GLOBAL_Control
0x140051417  cmp     r10, rax
0x14005141a  jz      short loc_1400513D1
0x14005141c  test    dword ptr [r10+2Ch], 400h
0x140051424  jz      short loc_1400513D1
0x140051426  cmp     byte ptr [r10+29h], 1
0x14005142b  jb      short loc_1400513D1
0x14005142d  mov     rcx, [r10+18h]
0x140051431  mov     edx, 1Eh
0x140051436  jmp     loc_1400576F8
0x14005143b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051442  lea     rax, WPP_GLOBAL_Control
0x140051449  cmp     rcx, rax
0x14005144c  jz      short loc_1400513D1
0x14005144e  test    dword ptr [rcx+2Ch], 400h
0x140051455  jz      loc_1400513D1
0x14005145b  cmp     byte ptr [rcx+29h], 1
0x14005145f  jb      loc_1400513D1
0x140051465  mov     edx, 1Fh
0x14005146a  jmp     loc_1400576F4
0x14005146f  cmp     byte ptr [rcx+29h], 2
0x140051473  jb      loc_140051392
0x140051479  mov     rcx, [rcx+18h]
0x14005147d  lea     r8, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids
0x140051484  mov     edx, 21h ; '!'
0x140051489  call    WPP_SF_
0x14005148e  jmp     loc_140051392
0x1400576f4  mov     rcx, [rcx+18h]
0x1400576f8  mov     r9d, edi
0x1400576fb  lea     r8, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids
0x140057702  call    WPP_SF_d
0x140057707  nop
0x140057708  jmp     loc_1400513D1
```
