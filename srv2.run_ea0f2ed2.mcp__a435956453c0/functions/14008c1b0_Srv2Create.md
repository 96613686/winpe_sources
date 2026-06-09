# Srv2Create

- ea: `0x14008c1b0`
- end: `0x14008c2a3`
- name: `Srv2Create`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14008c170`

## callees

- `0x14002019c`
- `0x14008c1b0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008c222`
- `ntoskrnl!IofCompleteRequest` at `0x14008c222`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14008c1e2`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14008c1e2`
- `ntoskrnl!IoGetRequestorProcess` at `0x14008c1d3`
- `ntoskrnl!IoGetRequestorProcess` at `0x14008c1d3`
- `ntoskrnl!PsIsHostSilo` at `0x14008c1f1`
- `ntoskrnl!PsIsHostSilo` at `0x14008c1f1`

## pseudocode

```c
__int64 __fastcall Srv2Create(__int64 a1, IRP *a2)
{
  PEPROCESS RequestorProcess; // rax
  __int64 ProcessServerSilo; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  unsigned int v6; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
  }
  RequestorProcess = IoGetRequestorProcess(a2);
  ProcessServerSilo = PsGetProcessServerSilo(RequestorProcess);
  if ( (unsigned __int8)PsIsHostSilo(ProcessServerSilo) )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    v6 = 0;
    CurrentStackLocation->FileObject->FsContext = 0;
    CurrentStackLocation->FileObject->FsContext2 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
    }
    v6 = -1073741790;
  }
  a2->IoStatus.Status = v6;
  IofCompleteRequest(a2, 2);
  return v6;
}

```

## disassembly

```asm
0x14008c1b0  mov     [rsp+arg_0], rbx
0x14008c1b5  push    rdi
0x14008c1b6  sub     rsp, 20h
0x14008c1ba  mov     rdi, rdx
0x14008c1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c1c4  lea     rbx, WPP_GLOBAL_Control
0x14008c1cb  cmp     rcx, rbx
0x14008c1ce  jnz     short loc_14008C23C
0x14008c1d0  mov     rcx, rdi; Irp
0x14008c1d3  call    cs:__imp_IoGetRequestorProcess
0x14008c1da  nop     dword ptr [rax+rax+00h]
0x14008c1df  mov     rcx, rax
0x14008c1e2  call    cs:__imp_PsGetProcessServerSilo
0x14008c1e9  nop     dword ptr [rax+rax+00h]
0x14008c1ee  mov     rcx, rax
0x14008c1f1  call    cs:__imp_PsIsHostSilo
0x14008c1f8  nop     dword ptr [rax+rax+00h]
0x14008c1fd  test    al, al
0x14008c1ff  jz      short loc_14008C263
0x14008c201  mov     r8, [rdi+0B8h]
0x14008c208  xor     ebx, ebx
0x14008c20a  mov     rcx, [r8+30h]
0x14008c20e  mov     [rcx+18h], rbx
0x14008c212  mov     rcx, [r8+30h]
0x14008c216  mov     [rcx+20h], rbx
0x14008c21a  mov     dl, 2; PriorityBoost
0x14008c21c  mov     [rdi+30h], ebx
0x14008c21f  mov     rcx, rdi; Irp
0x14008c222  call    cs:__imp_IofCompleteRequest
0x14008c229  nop     dword ptr [rax+rax+00h]
0x14008c22e  mov     eax, ebx
0x14008c230  mov     rbx, [rsp+28h+arg_0]
0x14008c235  add     rsp, 20h
0x14008c239  pop     rdi
0x14008c23a  retn
0x14008c23c  mov     eax, [rcx+2Ch]
0x14008c23f  test    al, 4
0x14008c241  jz      short loc_14008C1D0
0x14008c243  cmp     byte ptr [rcx+29h], 2
0x14008c247  jb      short loc_14008C1D0
0x14008c249  mov     rcx, [rcx+18h]
0x14008c24d  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c254  mov     edx, 0Bh
0x14008c259  call    WPP_SF_
0x14008c25e  jmp     loc_14008C1D0
0x14008c263  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c26a  cmp     rcx, rbx
0x14008c26d  jz      loc_14009B734
0x14008c273  mov     eax, [rcx+2Ch]
0x14008c276  test    al, 4
0x14008c278  jz      loc_14009B734
0x14008c27e  cmp     byte ptr [rcx+29h], 1
0x14008c282  jb      loc_14009B734
0x14008c288  mov     rcx, [rcx+18h]
0x14008c28c  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c293  mov     edx, 0Ch
0x14008c298  call    WPP_SF_
0x14008c29d  nop
0x14008c29e  jmp     loc_14009B734
0x14009b734  mov     ebx, 0C0000022h
0x14009b739  jmp     loc_14008C21A
```
