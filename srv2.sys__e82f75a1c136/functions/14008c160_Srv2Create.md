# Srv2Create

- ea: `0x14008c160`
- end: `0x14008c253`
- name: `Srv2Create`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14008c120`

## callees

- `0x14002019c`
- `0x14008c160`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008c1d2`
- `ntoskrnl!IofCompleteRequest` at `0x14008c1d2`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14008c192`
- `ntoskrnl!PsGetProcessServerSilo` at `0x14008c192`
- `ntoskrnl!IoGetRequestorProcess` at `0x14008c183`
- `ntoskrnl!IoGetRequestorProcess` at `0x14008c183`
- `ntoskrnl!PsIsHostSilo` at `0x14008c1a1`
- `ntoskrnl!PsIsHostSilo` at `0x14008c1a1`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids);
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
0x14008c160  mov     [rsp+arg_0], rbx
0x14008c165  push    rdi
0x14008c166  sub     rsp, 20h
0x14008c16a  mov     rdi, rdx
0x14008c16d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c174  lea     rbx, WPP_GLOBAL_Control
0x14008c17b  cmp     rcx, rbx
0x14008c17e  jnz     short loc_14008C1EC
0x14008c180  mov     rcx, rdi; Irp
0x14008c183  call    cs:__imp_IoGetRequestorProcess
0x14008c18a  nop     dword ptr [rax+rax+00h]
0x14008c18f  mov     rcx, rax
0x14008c192  call    cs:__imp_PsGetProcessServerSilo
0x14008c199  nop     dword ptr [rax+rax+00h]
0x14008c19e  mov     rcx, rax
0x14008c1a1  call    cs:__imp_PsIsHostSilo
0x14008c1a8  nop     dword ptr [rax+rax+00h]
0x14008c1ad  test    al, al
0x14008c1af  jz      short loc_14008C213
0x14008c1b1  mov     r8, [rdi+0B8h]
0x14008c1b8  xor     ebx, ebx
0x14008c1ba  mov     rcx, [r8+30h]
0x14008c1be  mov     [rcx+18h], rbx
0x14008c1c2  mov     rcx, [r8+30h]
0x14008c1c6  mov     [rcx+20h], rbx
0x14008c1ca  mov     dl, 2; PriorityBoost
0x14008c1cc  mov     [rdi+30h], ebx
0x14008c1cf  mov     rcx, rdi; Irp
0x14008c1d2  call    cs:__imp_IofCompleteRequest
0x14008c1d9  nop     dword ptr [rax+rax+00h]
0x14008c1de  mov     eax, ebx
0x14008c1e0  mov     rbx, [rsp+28h+arg_0]
0x14008c1e5  add     rsp, 20h
0x14008c1e9  pop     rdi
0x14008c1ea  retn
0x14008c1ec  mov     eax, [rcx+2Ch]
0x14008c1ef  test    al, 4
0x14008c1f1  jz      short loc_14008C180
0x14008c1f3  cmp     byte ptr [rcx+29h], 2
0x14008c1f7  jb      short loc_14008C180
0x14008c1f9  mov     rcx, [rcx+18h]
0x14008c1fd  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c204  mov     edx, 0Bh
0x14008c209  call    WPP_SF_
0x14008c20e  jmp     loc_14008C180
0x14008c213  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c21a  cmp     rcx, rbx
0x14008c21d  jz      loc_14009B6E4
0x14008c223  mov     eax, [rcx+2Ch]
0x14008c226  test    al, 4
0x14008c228  jz      loc_14009B6E4
0x14008c22e  cmp     byte ptr [rcx+29h], 1
0x14008c232  jb      loc_14009B6E4
0x14008c238  mov     rcx, [rcx+18h]
0x14008c23c  lea     r8, WPP_2eb7f2ea1cef30a03127f175d3f499fc_Traceguids
0x14008c243  mov     edx, 0Ch
0x14008c248  call    WPP_SF_
0x14008c24d  nop
0x14008c24e  jmp     loc_14009B6E4
0x14009b6e4  mov     ebx, 0C0000022h
0x14009b6e9  jmp     loc_14008C1CA
```
