# IopDevObjApplyPostCreationSettings

- ea: `0x140020434`
- end: `0x140020523`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400202a0`

## callees

- `0x140020434`
- `0x14002151c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140020509`
- `ntoskrnl!ZwClose` at `0x140020509`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400204d9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400204d9`
- `ntoskrnl!IoDeviceObjectType` at `0x140020495`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400204f6`
- `ntoskrnl!ZwSetSecurityObject` at `0x1400204f6`

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
0x140020434  mov     rax, rsp
0x140020437  mov     [rax+8], rbx
0x14002043b  push    rsi
0x14002043c  sub     rsp, 40h
0x140020440  mov     dword ptr [rax+18h], 0
0x140020447  mov     rbx, rdx
0x14002044a  mov     byte ptr [rax+10h], 0
0x14002044e  mov     rsi, rcx
0x140020451  mov     qword ptr [rax+20h], 0
0x140020459  mov     eax, [rdx]
0x14002045b  test    al, 2
0x14002045d  jnz     short loc_140020466
0x14002045f  xor     eax, eax
0x140020461  jmp     loc_140020517
0x140020466  mov     rcx, [rbx+8]; SecurityDescriptor
0x14002046a  lea     r8, [rsp+48h+SecurityInformation]
0x14002046f  lea     rdx, [rsp+48h+arg_8]
0x140020474  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140020479  test    eax, eax
0x14002047b  js      loc_140020517
0x140020481  mov     eax, [rsp+48h+SecurityInformation]
0x140020485  and     al, 3
0x140020487  neg     al
0x140020489  lea     rax, [rsp+48h+arg_18]
0x14002048e  sbb     ecx, ecx
0x140020490  mov     [rsp+48h+Handle], rax; Handle
0x140020495  mov     rax, cs:IoDeviceObjectType
0x14002049c  and     ecx, 80000h
0x1400204a2  mov     edx, ecx
0x1400204a4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400204a9  bts     edx, 12h
0x1400204ad  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400204b2  cmovz   edx, ecx
0x1400204b5  mov     rcx, [rax]
0x1400204b8  mov     r9d, edx
0x1400204bb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400204c0  bts     r9d, 18h
0x1400204c5  mov     rcx, rsi; Object
0x1400204c8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400204cd  cmovz   r9d, edx; DesiredAccess
0x1400204d1  xor     r8d, r8d; PassedAccessState
0x1400204d4  mov     edx, 200h; HandleAttributes
0x1400204d9  call    cs:__imp_ObOpenObjectByPointer
0x1400204e0  nop     dword ptr [rax+rax+00h]
0x1400204e5  test    eax, eax
0x1400204e7  js      short loc_140020517
0x1400204e9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400204ed  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x1400204f1  mov     rcx, [rsp+48h+arg_18]; Handle
0x1400204f6  call    cs:__imp_ZwSetSecurityObject
0x1400204fd  nop     dword ptr [rax+rax+00h]
0x140020502  mov     rcx, [rsp+48h+arg_18]; Handle
0x140020507  mov     ebx, eax
0x140020509  call    cs:__imp_ZwClose
0x140020510  nop     dword ptr [rax+rax+00h]
0x140020515  mov     eax, ebx
0x140020517  mov     rbx, [rsp+48h+arg_0]
0x14002051c  add     rsp, 40h
0x140020520  pop     rsi
0x140020521  retn
```
