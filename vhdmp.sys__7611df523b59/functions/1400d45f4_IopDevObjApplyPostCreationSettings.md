# IopDevObjApplyPostCreationSettings

- ea: `0x1400d45f4`
- end: `0x1400d46e3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `NTSTATUS __fastcall(PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d4460`

## callees

- `0x1400d45f4`
- `0x1400d4d50`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d4699`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d4699`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400d46b6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400d46b6`
- `ntoskrnl!ZwClose` at `0x1400d46c9`
- `ntoskrnl!ZwClose` at `0x1400d46c9`
- `ntoskrnl!IoDeviceObjectType` at `0x1400d4655`

## pseudocode

```c
NTSTATUS __fastcall IopDevObjApplyPostCreationSettings(PVOID Object, __int64 a2)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  Handle = 0;
  if ( (*(_DWORD *)a2 & 2) == 0 )
    return 0;
  result = SeUtilSecurityInfoFromSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
  if ( result >= 0 )
  {
    result = ObOpenObjectByPointer(Object, 0x200u, 0, 0, IoDeviceObjectType, 0, &Handle);
    if ( result >= 0 )
    {
      v5 = ZwSetSecurityObject(Handle, 0, *(PSECURITY_DESCRIPTOR *)(a2 + 8));
      ZwClose(Handle);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400d45f4  mov     rax, rsp
0x1400d45f7  mov     [rax+8], rbx
0x1400d45fb  push    rsi
0x1400d45fc  sub     rsp, 40h
0x1400d4600  mov     dword ptr [rax+18h], 0
0x1400d4607  mov     rbx, rdx
0x1400d460a  mov     byte ptr [rax+10h], 0
0x1400d460e  mov     rsi, rcx
0x1400d4611  mov     qword ptr [rax+20h], 0
0x1400d4619  mov     eax, [rdx]
0x1400d461b  test    al, 2
0x1400d461d  jnz     short loc_1400D4626
0x1400d461f  xor     eax, eax
0x1400d4621  jmp     loc_1400D46D7
0x1400d4626  mov     rcx, [rbx+8]; SecurityDescriptor
0x1400d462a  lea     r8, [rsp+48h+SecurityInformation]
0x1400d462f  lea     rdx, [rsp+48h+arg_8]
0x1400d4634  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400d4639  test    eax, eax
0x1400d463b  js      loc_1400D46D7
0x1400d4641  mov     eax, [rsp+48h+SecurityInformation]
0x1400d4645  and     al, 3
0x1400d4647  neg     al
0x1400d4649  lea     rax, [rsp+48h+arg_18]
0x1400d464e  sbb     ecx, ecx
0x1400d4650  mov     [rsp+48h+Handle], rax; Handle
0x1400d4655  mov     rax, cs:IoDeviceObjectType
0x1400d465c  and     ecx, 80000h
0x1400d4662  mov     edx, ecx
0x1400d4664  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400d4669  bts     edx, 12h
0x1400d466d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400d4672  cmovz   edx, ecx
0x1400d4675  mov     rcx, [rax]
0x1400d4678  mov     r9d, edx
0x1400d467b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400d4680  bts     r9d, 18h
0x1400d4685  mov     rcx, rsi; Object
0x1400d4688  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400d468d  cmovz   r9d, edx; DesiredAccess
0x1400d4691  xor     r8d, r8d; PassedAccessState
0x1400d4694  mov     edx, 200h; HandleAttributes
0x1400d4699  call    cs:__imp_ObOpenObjectByPointer
0x1400d46a0  nop     dword ptr [rax+rax+00h]
0x1400d46a5  test    eax, eax
0x1400d46a7  js      short loc_1400D46D7
0x1400d46a9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400d46ad  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400d46b1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400d46b6  call    cs:__imp_ZwSetSecurityObject
0x1400d46bd  nop     dword ptr [rax+rax+00h]
0x1400d46c2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400d46c7  mov     ebx, eax
0x1400d46c9  call    cs:__imp_ZwClose
0x1400d46d0  nop     dword ptr [rax+rax+00h]
0x1400d46d5  mov     eax, ebx
0x1400d46d7  mov     rbx, [rsp+48h+arg_0]
0x1400d46dc  add     rsp, 40h
0x1400d46e0  pop     rsi
0x1400d46e1  retn
```
