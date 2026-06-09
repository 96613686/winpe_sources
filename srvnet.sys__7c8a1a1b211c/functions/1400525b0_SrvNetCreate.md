# SrvNetCreate

- ea: `0x1400525b0`
- end: `0x1400526f9`
- name: `SrvNetCreate`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000caa0`
- `0x140015790`
- `0x1400525b0`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x1400526e1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400526e1`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400525df`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400525df`
- `ntoskrnl!IofCompleteRequest` at `0x140052639`
- `ntoskrnl!IofCompleteRequest` at `0x140052639`
- `ntoskrnl!PsIsHostSilo` at `0x1400525fd`
- `ntoskrnl!PsIsHostSilo` at `0x1400525fd`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400525ee`
- `ntoskrnl!PsGetProcessServerSilo` at `0x1400525ee`

## pseudocode

```c
__int64 __fastcall SrvNetCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PEPROCESS RequestorProcess; // rax
  __int64 ProcessServerSilo; // rax
  PERESOURCE v6; // rdi
  unsigned int v7; // edi
  PIO_SECURITY_CONTEXT SecurityContext; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
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
    v6 = SrvNetDeviceExtension;
    if ( !SrvNetDeviceExtension[4].SharedWaiters )
    {
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( SecurityContext )
      {
        if ( (SecurityContext->DesiredAccess & 0x10000) != 0 )
          v6[4].SharedWaiters = IoGetCurrentProcess();
      }
    }
    v7 = SrvAdminOpenInstanceHandle(CurrentStackLocation->DeviceObject, CurrentStackLocation->FileObject);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6feed98b03653c48bfec8caf18231585_Traceguids);
    }
    v7 = -1073741790;
  }
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 2);
  return v7;
}

```

## disassembly

```asm
0x1400525b0  mov     [rsp+arg_0], rbx
0x1400525b5  mov     [rsp+arg_8], rsi
0x1400525ba  push    rdi
0x1400525bb  sub     rsp, 20h
0x1400525bf  mov     rsi, [rdx+0B8h]
0x1400525c6  mov     rbx, rdx
0x1400525c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400525d0  lea     rdi, WPP_GLOBAL_Control
0x1400525d7  cmp     rcx, rdi
0x1400525da  jnz     short loc_140052658
0x1400525dc  mov     rcx, rbx; Irp
0x1400525df  call    cs:__imp_IoGetRequestorProcess
0x1400525e6  nop     dword ptr [rax+rax+00h]
0x1400525eb  mov     rcx, rax
0x1400525ee  call    cs:__imp_PsGetProcessServerSilo
0x1400525f5  nop     dword ptr [rax+rax+00h]
0x1400525fa  mov     rcx, rax
0x1400525fd  call    cs:__imp_PsIsHostSilo
0x140052604  nop     dword ptr [rax+rax+00h]
0x140052609  test    al, al
0x14005260b  jz      short loc_140052687
0x14005260d  mov     rdi, cs:SrvNetDeviceExtension
0x140052614  cmp     qword ptr [rdi+1C0h], 0
0x14005261c  jz      loc_1400526C7
0x140052622  mov     rdx, [rsi+30h]
0x140052626  mov     rcx, [rsi+28h]
0x14005262a  call    SrvAdminOpenInstanceHandle
0x14005262f  mov     edi, eax
0x140052631  mov     dl, 2; PriorityBoost
0x140052633  mov     [rbx+30h], edi
0x140052636  mov     rcx, rbx; Irp
0x140052639  call    cs:__imp_IofCompleteRequest
0x140052640  nop     dword ptr [rax+rax+00h]
0x140052645  mov     rbx, [rsp+28h+arg_0]
0x14005264a  mov     eax, edi
0x14005264c  mov     rsi, [rsp+28h+arg_8]
0x140052651  add     rsp, 20h
0x140052655  pop     rdi
0x140052656  retn
0x140052658  mov     eax, [rcx+2Ch]
0x14005265b  test    al, 2
0x14005265d  jz      loc_1400525DC
0x140052663  cmp     byte ptr [rcx+29h], 2
0x140052667  jb      loc_1400525DC
0x14005266d  mov     rcx, [rcx+18h]
0x140052671  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x140052678  mov     edx, 0Bh
0x14005267d  call    WPP_SF_
0x140052682  jmp     loc_1400525DC
0x140052687  mov     rcx, cs:WPP_GLOBAL_Control
0x14005268e  cmp     rcx, rdi
0x140052691  jz      loc_1400577A8
0x140052697  mov     eax, [rcx+2Ch]
0x14005269a  test    al, 2
0x14005269c  jz      loc_1400577A8
0x1400526a2  cmp     byte ptr [rcx+29h], 1
0x1400526a6  jb      loc_1400577A8
0x1400526ac  mov     rcx, [rcx+18h]
0x1400526b0  lea     r8, WPP_6feed98b03653c48bfec8caf18231585_Traceguids
0x1400526b7  mov     edx, 0Ch
0x1400526bc  call    WPP_SF_
0x1400526c1  nop
0x1400526c2  jmp     loc_1400577A8
0x1400526c7  mov     rax, [rsi+8]
0x1400526cb  test    rax, rax
0x1400526ce  jz      loc_140052622
0x1400526d4  test    dword ptr [rax+10h], 10000h
0x1400526db  jz      loc_140052622
0x1400526e1  call    cs:__imp_IoGetCurrentProcess
0x1400526e8  nop     dword ptr [rax+rax+00h]
0x1400526ed  mov     [rdi+1C0h], rax
0x1400526f4  jmp     loc_140052622
0x1400577a8  mov     edi, 0C0000022h
0x1400577ad  jmp     loc_140052631
```
