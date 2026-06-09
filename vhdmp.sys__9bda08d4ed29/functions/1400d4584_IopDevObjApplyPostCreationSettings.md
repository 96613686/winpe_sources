# IopDevObjApplyPostCreationSettings

- ea: `0x1400d4584`
- end: `0x1400d4673`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d43f0`

## callees

- `0x1400d4584`
- `0x1400d4ce0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d4629`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400d4629`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400d4646`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400d4646`
- `ntoskrnl!ZwClose` at `0x1400d4659`
- `ntoskrnl!ZwClose` at `0x1400d4659`
- `ntoskrnl!IoDeviceObjectType` at `0x1400d45e5`

## pseudocode

```c
NTSTATUS __fastcall IopDevObjApplyPostCreationSettings(PVOID Object, __int64 a2)
{
  NTSTATUS result; // eax
  int v5; // edx
  ACCESS_MASK v6; // r9d
  NTSTATUS v7; // ebx
  unsigned __int8 v8; // [rsp+58h] [rbp+10h] BYREF
  SECURITY_INFORMATION SecurityInformation; // [rsp+60h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  SecurityInformation = 0;
  v8 = 0;
  Handle = 0;
  if ( (*(_DWORD *)a2 & 2) == 0 )
    return 0;
  result = SeUtilSecurityInfoFromSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8), &v8, &SecurityInformation);
  if ( result >= 0 )
  {
    v5 = ((SecurityInformation & 3) != 0 ? 0x80000 : 0) | 0x40000;
    if ( (SecurityInformation & 4) == 0 )
      v5 = (SecurityInformation & 3) != 0 ? 0x80000 : 0;
    v6 = v5 | 0x1000000;
    if ( (SecurityInformation & 8) == 0 )
      v6 = v5;
    result = ObOpenObjectByPointer(Object, 0x200u, 0, v6, IoDeviceObjectType, 0, &Handle);
    if ( result >= 0 )
    {
      v7 = ZwSetSecurityObject(Handle, SecurityInformation, *(PSECURITY_DESCRIPTOR *)(a2 + 8));
      ZwClose(Handle);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400d4584  mov     rax, rsp
0x1400d4587  mov     [rax+8], rbx
0x1400d458b  push    rsi
0x1400d458c  sub     rsp, 40h
0x1400d4590  mov     dword ptr [rax+18h], 0
0x1400d4597  mov     rbx, rdx
0x1400d459a  mov     byte ptr [rax+10h], 0
0x1400d459e  mov     rsi, rcx
0x1400d45a1  mov     qword ptr [rax+20h], 0
0x1400d45a9  mov     eax, [rdx]
0x1400d45ab  test    al, 2
0x1400d45ad  jnz     short loc_1400D45B6
0x1400d45af  xor     eax, eax
0x1400d45b1  jmp     loc_1400D4667
0x1400d45b6  mov     rcx, [rbx+8]; SecurityDescriptor
0x1400d45ba  lea     r8, [rsp+48h+SecurityInformation]
0x1400d45bf  lea     rdx, [rsp+48h+arg_8]
0x1400d45c4  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400d45c9  test    eax, eax
0x1400d45cb  js      loc_1400D4667
0x1400d45d1  mov     eax, [rsp+48h+SecurityInformation]
0x1400d45d5  and     al, 3
0x1400d45d7  neg     al
0x1400d45d9  lea     rax, [rsp+48h+arg_18]
0x1400d45de  sbb     ecx, ecx
0x1400d45e0  mov     [rsp+48h+Handle], rax; Handle
0x1400d45e5  mov     rax, cs:IoDeviceObjectType
0x1400d45ec  and     ecx, 80000h
0x1400d45f2  mov     edx, ecx
0x1400d45f4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400d45f9  bts     edx, 12h
0x1400d45fd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400d4602  cmovz   edx, ecx
0x1400d4605  mov     rcx, [rax]
0x1400d4608  mov     r9d, edx
0x1400d460b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400d4610  bts     r9d, 18h
0x1400d4615  mov     rcx, rsi; Object
0x1400d4618  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400d461d  cmovz   r9d, edx; DesiredAccess
0x1400d4621  xor     r8d, r8d; PassedAccessState
0x1400d4624  mov     edx, 200h; HandleAttributes
0x1400d4629  call    cs:__imp_ObOpenObjectByPointer
0x1400d4630  nop     dword ptr [rax+rax+00h]
0x1400d4635  test    eax, eax
0x1400d4637  js      short loc_1400D4667
0x1400d4639  mov     r8, [rbx+8]; SecurityDescriptor
0x1400d463d  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400d4641  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400d4646  call    cs:__imp_ZwSetSecurityObject
0x1400d464d  nop     dword ptr [rax+rax+00h]
0x1400d4652  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400d4657  mov     ebx, eax
0x1400d4659  call    cs:__imp_ZwClose
0x1400d4660  nop     dword ptr [rax+rax+00h]
0x1400d4665  mov     eax, ebx
0x1400d4667  mov     rbx, [rsp+48h+arg_0]
0x1400d466c  add     rsp, 40h
0x1400d4670  pop     rsi
0x1400d4671  retn
```
