# IopDevObjApplyPostCreationSettings

- ea: `0x140018244`
- end: `0x140018333`
- name: `IopDevObjApplyPostCreationSettings`
- size: `239`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400180b0`

## callees

- `0x140018244`
- `0x14001931c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140018319`
- `ntoskrnl!ZwClose` at `0x140018319`
- `ntoskrnl!ZwSetSecurityObject` at `0x140018306`
- `ntoskrnl!ZwSetSecurityObject` at `0x140018306`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400182e9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400182e9`
- `ntoskrnl!IoDeviceObjectType` at `0x1400182a5`

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
0x140018244  mov     rax, rsp
0x140018247  mov     [rax+8], rbx
0x14001824b  push    rsi
0x14001824c  sub     rsp, 40h
0x140018250  mov     dword ptr [rax+18h], 0
0x140018257  mov     rbx, rdx
0x14001825a  mov     byte ptr [rax+10h], 0
0x14001825e  mov     rsi, rcx
0x140018261  mov     qword ptr [rax+20h], 0
0x140018269  mov     eax, [rdx]
0x14001826b  test    al, 2
0x14001826d  jnz     short loc_140018276
0x14001826f  xor     eax, eax
0x140018271  jmp     loc_140018327
0x140018276  mov     rcx, [rbx+8]; SecurityDescriptor
0x14001827a  lea     r8, [rsp+48h+SecurityInformation]
0x14001827f  lea     rdx, [rsp+48h+arg_8]
0x140018284  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140018289  test    eax, eax
0x14001828b  js      loc_140018327
0x140018291  mov     eax, [rsp+48h+SecurityInformation]
0x140018295  and     al, 3
0x140018297  neg     al
0x140018299  lea     rax, [rsp+48h+arg_18]
0x14001829e  sbb     ecx, ecx
0x1400182a0  mov     [rsp+48h+Handle], rax; Handle
0x1400182a5  mov     rax, cs:IoDeviceObjectType
0x1400182ac  and     ecx, 80000h
0x1400182b2  mov     edx, ecx
0x1400182b4  mov     [rsp+48h+AccessMode], 0; AccessMode
0x1400182b9  bts     edx, 12h
0x1400182bd  test    byte ptr [rsp+48h+SecurityInformation], 4
0x1400182c2  cmovz   edx, ecx
0x1400182c5  mov     rcx, [rax]
0x1400182c8  mov     r9d, edx
0x1400182cb  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x1400182d0  bts     r9d, 18h
0x1400182d5  mov     rcx, rsi; Object
0x1400182d8  test    byte ptr [rsp+48h+SecurityInformation], 8
0x1400182dd  cmovz   r9d, edx; DesiredAccess
0x1400182e1  xor     r8d, r8d; PassedAccessState
0x1400182e4  mov     edx, 200h; HandleAttributes
0x1400182e9  call    cs:__imp_ObOpenObjectByPointer
0x1400182f0  nop     dword ptr [rax+rax+00h]
0x1400182f5  test    eax, eax
0x1400182f7  js      short loc_140018327
0x1400182f9  mov     r8, [rbx+8]; SecurityDescriptor
0x1400182fd  mov     edx, [rsp+48h+SecurityInformation]; SecurityInformation
0x140018301  mov     rcx, [rsp+48h+arg_18]; Handle
0x140018306  call    cs:__imp_ZwSetSecurityObject
0x14001830d  nop     dword ptr [rax+rax+00h]
0x140018312  mov     rcx, [rsp+48h+arg_18]; Handle
0x140018317  mov     ebx, eax
0x140018319  call    cs:__imp_ZwClose
0x140018320  nop     dword ptr [rax+rax+00h]
0x140018325  mov     eax, ebx
0x140018327  mov     rbx, [rsp+48h+arg_0]
0x14001832c  add     rsp, 40h
0x140018330  pop     rsi
0x140018331  retn
```
