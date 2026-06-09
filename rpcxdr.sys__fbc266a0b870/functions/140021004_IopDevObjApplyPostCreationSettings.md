# IopDevObjApplyPostCreationSettings

- ea: `0x140021004`
- end: `0x1400210f3`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020e70`

## callees

- `0x140021004`
- `0x1400220dc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400210d9`
- `ntoskrnl!ZwClose` at `0x1400210d9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400210a9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400210a9`
- `ntoskrnl!IoDeviceObjectType` at `0x140021065`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400210c6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400210c6`

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
0x140021004  mov     rax, rsp
0x140021007  mov     [rax+8], rbx
0x14002100b  push    rsi
0x14002100c  sub     rsp, 40h
0x140021010  mov     dword ptr [rax+18h], 0
0x140021017  mov     rbx, rdx
0x14002101a  mov     byte ptr [rax+10h], 0
0x14002101e  mov     rsi, rcx
0x140021021  mov     qword ptr [rax+20h], 0
0x140021029  mov     eax, [rdx]
0x14002102b  test    al, 2
0x14002102d  jnz     short loc_140021036
0x14002102f  xor     eax, eax
0x140021031  jmp     loc_1400210E7
0x140021036  mov     rcx, [rbx+8]; SecurityDescriptor
0x14002103a  lea     r8, [rsp+48h+SecurityInformation]
0x14002103f  lea     rdx, [rsp+48h+arg_8]
0x140021044  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140021049  test    eax, eax
0x14002104b  js      loc_1400210E7
0x140021051  mov     eax, [rsp+48h+SecurityInformation]
0x140021055  and     al, 3
0x140021057  neg     al
0x140021059  lea     rax, [rsp+48h+arg_18]
0x14002105e  sbb     ecx, ecx
0x140021060  mov     [rsp+48h+Handle], rax; Handle
0x140021065  mov     rax, cs:IoDeviceObjectType
0x14002106c  and     ecx, 80000h
0x140021072  mov     edx, ecx
0x140021074  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140021079  bts     edx, 12h
0x14002107d  test    byte ptr [rsp+48h+SecurityInformation], 4
0x140021082  cmovz   edx, ecx
0x140021085  mov     rcx, [rax]
0x140021088  mov     r9d, edx
0x14002108b  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x140021090  bts     r9d, 18h
0x140021095  mov     rcx, rsi; Object
0x140021098  test    byte ptr [rsp+48h+SecurityInformation], 8
0x14002109d  cmovz   r9d, edx; DesiredAccess
0x1400210a1  xor     r8d, r8d; PassedAccessState
0x1400210a4  mov     edx, 200h; HandleAttributes
0x1400210a9  call    cs:__imp_ObOpenObjectByPointer
0x1400210b0  nop     dword ptr [rax+rax+00h]
0x1400210b5  test    eax, eax
0x1400210b7  js      short loc_1400210E7
0x1400210b9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400210bd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400210c1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400210c6  call    cs:__imp_ZwSetSecurityObject
0x1400210cd  nop     dword ptr [rax+rax+00h]
0x1400210d2  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400210d7  mov     ebx, eax
0x1400210d9  call    cs:__imp_ZwClose
0x1400210e0  nop     dword ptr [rax+rax+00h]
0x1400210e5  mov     eax, ebx
0x1400210e7  mov     rbx, [rsp+48h+arg_0]
0x1400210ec  add     rsp, 40h
0x1400210f0  pop     rsi
0x1400210f1  retn
```
