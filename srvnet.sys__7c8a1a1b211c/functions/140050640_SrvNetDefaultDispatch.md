# SrvNetDefaultDispatch

- ea: `0x140050640`
- end: `0x1400507b2`
- name: `SrvNetDefaultDispatch`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000caa0`
- `0x14001389c`
- `0x140015790`
- `0x140050640`
- `0x1400507c0`
- `0x140052700`
- `0x140053090`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14005079a`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005079a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140050698`
- `ntoskrnl!IoGetRequestorProcess` at `0x140050698`
- `ntoskrnl!IofCompleteRequest` at `0x1400506f2`
- `ntoskrnl!IofCompleteRequest` at `0x1400576b7`
- `ntoskrnl!IofCompleteRequest` at `0x1400506f2`
- `ntoskrnl!IofCompleteRequest` at `0x1400576b7`
- `ntoskrnl!PsIsHostSilo` at `0x1400506b6`
- `ntoskrnl!PsIsHostSilo` at `0x1400506b6`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400506a7`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400506a7`

## pseudocode

```c
__int64 __fastcall SrvNetDefaultDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  UCHAR MajorFunction; // dl
  PEPROCESS RequestorProcess; // rax
  __int64 ProcessServerSilo; // rax
  PERESOURCE v8; // rsi
  unsigned int v9; // edi
  PIO_SECURITY_CONTEXT SecurityContext; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction == 13 )
    return SrvNetDeviceControl(a1, (__int64)a2);
  if ( MajorFunction )
  {
    switch ( MajorFunction )
    {
      case 2u:
        return SrvNetClose(a1, a2);
      case 0xEu:
        return SrvNetDeviceControl(a1, (__int64)a2);
      case 0x12u:
        return SrvNetCleanup(a1, a2);
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_6feed98b03653c48bfec8caf18231585_Traceguids,
            CurrentStackLocation->MajorFunction);
        }
        a2->IoStatus.Status = -1073741822;
        IofCompleteRequest(a2, 2);
        return 3221225474LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
    }
    RequestorProcess = IoGetRequestorProcess(a2);
    ProcessServerSilo = PsGetProcessServerSilo(RequestorProcess);
    if ( (unsigned __int8)PsIsHostSilo(ProcessServerSilo) )
    {
      v8 = SrvNetDeviceExtension;
      if ( !SrvNetDeviceExtension[4].SharedWaiters )
      {
        SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
        if ( SecurityContext )
        {
          if ( (SecurityContext->DesiredAccess & 0x10000) != 0 )
            v8[4].SharedWaiters = IoGetCurrentProcess();
        }
      }
      v9 = SrvAdminOpenInstanceHandle(CurrentStackLocation->DeviceObject, CurrentStackLocation->FileObject);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
      }
      v9 = -1073741790;
    }
    a2->IoStatus.Status = v9;
    IofCompleteRequest(a2, 2);
    return v9;
  }
}

```

## disassembly

```asm
0x140050640  mov     [rsp+arg_0], rbx
0x140050645  mov     [rsp+arg_8], rsi
0x14005064a  push    rdi
0x14005064b  sub     rsp, 20h
0x14005064f  mov     rdi, [rdx+0B8h]
0x140050656  mov     rbx, rdx
0x140050659  movzx   edx, byte ptr [rdi]
0x14005065c  cmp     dl, 0Dh
0x14005065f  jnz     short loc_14005067A
0x140050661  mov     rdx, rbx
0x140050664  call    SrvNetDeviceControl
0x140050669  mov     rbx, [rsp+28h+arg_0]
0x14005066e  mov     rsi, [rsp+28h+arg_8]
0x140050673  add     rsp, 20h
0x140050677  pop     rdi
0x140050678  retn
0x14005067a  test    dl, dl
0x14005067c  jnz     loc_140057660
0x140050682  mov     rcx, cs:WPP_GLOBAL_Control
0x140050689  lea     rsi, WPP_GLOBAL_Control
0x140050690  cmp     rcx, rsi
0x140050693  jnz     short loc_140050711
0x140050695  mov     rcx, rbx; Irp
0x140050698  call    cs:__imp_IoGetRequestorProcess
0x14005069f  nop     dword ptr [rax+rax+00h]
0x1400506a4  mov     rcx, rax
0x1400506a7  call    cs:__imp_PsGetProcessServerSilo
0x1400506ae  nop     dword ptr [rax+rax+00h]
0x1400506b3  mov     rcx, rax
0x1400506b6  call    cs:__imp_PsIsHostSilo
0x1400506bd  nop     dword ptr [rax+rax+00h]
0x1400506c2  test    al, al
0x1400506c4  jz      short loc_140050740
0x1400506c6  mov     rsi, cs:SrvNetDeviceExtension
0x1400506cd  cmp     qword ptr [rsi+1C0h], 0
0x1400506d5  jz      loc_140050780
0x1400506db  mov     rdx, [rdi+30h]
0x1400506df  mov     rcx, [rdi+28h]
0x1400506e3  call    SrvAdminOpenInstanceHandle
0x1400506e8  mov     edi, eax
0x1400506ea  mov     dl, 2; PriorityBoost
0x1400506ec  mov     [rbx+30h], edi
0x1400506ef  mov     rcx, rbx; Irp
0x1400506f2  call    cs:__imp_IofCompleteRequest
0x1400506f9  nop     dword ptr [rax+rax+00h]
0x1400506fe  mov     rbx, [rsp+28h+arg_0]
0x140050703  mov     eax, edi
0x140050705  mov     rsi, [rsp+28h+arg_8]
0x14005070a  add     rsp, 20h
0x14005070e  pop     rdi
0x14005070f  retn
0x140050711  mov     eax, [rcx+2Ch]
0x140050714  test    al, 2
0x140050716  jz      loc_140050695
0x14005071c  cmp     byte ptr [rcx+29h], 2
0x140050720  jb      loc_140050695
0x140050726  mov     rcx, [rcx+18h]
0x14005072a  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x140050731  mov     edx, 0Bh
0x140050736  call    WPP_SF_
0x14005073b  jmp     loc_140050695
0x140050740  mov     rcx, cs:WPP_GLOBAL_Control
0x140050747  cmp     rcx, rsi
0x14005074a  jz      loc_1400576E9
0x140050750  mov     eax, [rcx+2Ch]
0x140050753  test    al, 2
0x140050755  jz      loc_1400576E9
0x14005075b  cmp     byte ptr [rcx+29h], 1
0x14005075f  jb      loc_1400576E9
0x140050765  mov     rcx, [rcx+18h]
0x140050769  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x140050770  mov     edx, 0Ch
0x140050775  call    WPP_SF_
0x14005077a  nop
0x14005077b  jmp     loc_1400576E9
0x140050780  mov     rax, [rdi+8]
0x140050784  test    rax, rax
0x140050787  jz      loc_1400506DB
0x14005078d  test    dword ptr [rax+10h], 10000h
0x140050794  jz      loc_1400506DB
0x14005079a  call    cs:__imp_IoGetCurrentProcess
0x1400507a1  nop     dword ptr [rax+rax+00h]
0x1400507a6  mov     [rsi+1C0h], rax
0x1400507ad  jmp     loc_1400506DB
0x140057660  cmp     dl, 2
0x140057663  jz      short loc_1400576DB
0x140057665  cmp     dl, 0Eh
0x140057668  jz      loc_140050661
0x14005766e  cmp     dl, 12h
0x140057671  jz      short loc_1400576CD
0x140057673  mov     rcx, cs:WPP_GLOBAL_Control
0x14005767a  lea     rsi, WPP_GLOBAL_Control
0x140057681  cmp     rcx, rsi
0x140057684  jz      short loc_1400576AB
0x140057686  mov     eax, [rcx+2Ch]
0x140057689  test    al, 2
0x14005768b  jz      short loc_1400576AB
0x14005768d  cmp     byte ptr [rcx+29h], 2
0x140057691  jb      short loc_1400576AB
0x140057693  mov     rcx, [rcx+18h]
0x140057697  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x14005769e  mov     r9d, edx
0x1400576a1  mov     edx, 0Ah
0x1400576a6  call    WPP_SF_d
0x1400576ab  mov     dl, 2; PriorityBoost
0x1400576ad  mov     dword ptr [rbx+30h], 0C0000002h
0x1400576b4  mov     rcx, rbx; Irp
0x1400576b7  call    cs:__imp_IofCompleteRequest
0x1400576be  nop     dword ptr [rax+rax+00h]
0x1400576c3  mov     eax, 0C0000002h
0x1400576c8  jmp     loc_140050669
0x1400576cd  mov     rdx, rbx
0x1400576d0  call    SrvNetCleanup
0x1400576d5  nop
0x1400576d6  jmp     loc_140050669
0x1400576db  mov     rdx, rbx
0x1400576de  call    SrvNetClose
0x1400576e3  nop
0x1400576e4  jmp     loc_140050669
0x1400576e9  mov     edi, 0C0000022h
0x1400576ee  jmp     loc_1400506EA
```
