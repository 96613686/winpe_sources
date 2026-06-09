# TmpBindResourceManagerCompletionPort

- ea: `0x140012050`
- end: `0x14001214d`
- name: `TmpBindResourceManagerCompletionPort`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014a30`

## callees

- `0x140012050`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400120cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400120cb`
- `ntoskrnl!KeReleaseMutex` at `0x1400120e3`
- `ntoskrnl!KeReleaseMutex` at `0x140012131`
- `ntoskrnl!KeReleaseMutex` at `0x1400120e3`
- `ntoskrnl!KeReleaseMutex` at `0x140012131`
- `ntoskrnl!ObfDereferenceObject` at `0x1400120f2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400120f2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012095`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140012095`
- `ntoskrnl!IoCompletionObjectType` at `0x14001206a`

## pseudocode

```c
NTSTATUS __fastcall TmpBindResourceManagerCompletionPort(__int64 a1, KPROCESSOR_MODE a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // esi
  PVOID v9; // rbp
  struct _KMUTANT *v10; // rcx
  PVOID Object; // [rsp+80h] [rbp+18h] BYREF

  Object = 0;
  result = ObReferenceObjectByHandle(*(HANDLE *)a3, 1u, IoCompletionObjectType, a2, &Object, 0);
  v8 = result;
  if ( result >= 0 )
  {
    v9 = Object;
    KeWaitForSingleObject((PVOID)(a1 + 40), Executive, 0, 0, 0);
    v10 = (struct _KMUTANT *)(a1 + 40);
    if ( (*(_DWORD *)(a1 + 32) & 0x10) != 0 )
    {
      KeReleaseMutex(v10, 0);
      ObfDereferenceObject(v9);
      return -1073741436;
    }
    else
    {
      *(_QWORD *)(a1 + 568) = v9;
      *(_QWORD *)(a1 + 584) = a4;
      *(_QWORD *)(a1 + 576) = *(_QWORD *)(a3 + 8);
      *(_QWORD *)(a1 + 560) = a1 + 552;
      *(_QWORD *)(a1 + 552) = a1 + 552;
      _InterlockedOr((volatile signed __int32 *)(a1 + 32), 0x10u);
      KeReleaseMutex(v10, 0);
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012050  mov     r11, rsp
0x140012053  push    rbx
0x140012054  push    rbp
0x140012055  push    rsi
0x140012056  push    rdi
0x140012057  push    r14
0x140012059  push    r15
0x14001205b  sub     rsp, 38h
0x14001205f  mov     r14, r8
0x140012062  mov     qword ptr [r11-40h], 0
0x14001206a  mov     r8, cs:__imp_IoCompletionObjectType
0x140012071  lea     rax, [r11+18h]
0x140012075  mov     r15, r9
0x140012078  mov     qword ptr [r11+18h], 0
0x140012080  mov     rbx, rcx
0x140012083  mov     [r11-48h], rax
0x140012087  mov     rcx, [r14]; Handle
0x14001208a  mov     r9b, dl; AccessMode
0x14001208d  mov     r8, [r8]; ObjectType
0x140012090  mov     edx, 1; DesiredAccess
0x140012095  call    cs:__imp_ObReferenceObjectByHandle
0x14001209c  nop     dword ptr [rax+rax+00h]
0x1400120a1  mov     esi, eax
0x1400120a3  test    eax, eax
0x1400120a5  js      loc_14001213F
0x1400120ab  mov     rbp, [rsp+68h+Object]
0x1400120b3  lea     rdi, [rbx+28h]
0x1400120b7  mov     rcx, rdi; Object
0x1400120ba  mov     [rsp+68h+Timeout], 0; Timeout
0x1400120c3  xor     r9d, r9d; Alertable
0x1400120c6  xor     r8d, r8d; WaitMode
0x1400120c9  xor     edx, edx; WaitReason
0x1400120cb  call    cs:__imp_KeWaitForSingleObject
0x1400120d2  nop     dword ptr [rax+rax+00h]
0x1400120d7  mov     eax, [rbx+20h]
0x1400120da  xor     edx, edx; Wait
0x1400120dc  mov     rcx, rdi; Mutex
0x1400120df  test    al, 10h
0x1400120e1  jz      short loc_140012105
0x1400120e3  call    cs:__imp_KeReleaseMutex
0x1400120ea  nop     dword ptr [rax+rax+00h]
0x1400120ef  mov     rcx, rbp; Object
0x1400120f2  call    cs:__imp_ObfDereferenceObject
0x1400120f9  nop     dword ptr [rax+rax+00h]
0x1400120fe  mov     eax, 0C0000184h
0x140012103  jmp     short loc_14001213F
0x140012105  mov     [rbx+238h], rbp
0x14001210c  mov     [rbx+248h], r15
0x140012113  mov     rax, [r14+8]
0x140012117  mov     [rbx+240h], rax
0x14001211e  lea     rax, [rbx+228h]
0x140012125  mov     [rax+8], rax
0x140012129  mov     [rax], rax
0x14001212c  lock or dword ptr [rbx+20h], 10h
0x140012131  call    cs:__imp_KeReleaseMutex
0x140012138  nop     dword ptr [rax+rax+00h]
0x14001213d  mov     eax, esi
0x14001213f  add     rsp, 38h
0x140012143  pop     r15
0x140012145  pop     r14
0x140012147  pop     rdi
0x140012148  pop     rsi
0x140012149  pop     rbp
0x14001214a  pop     rbx
0x14001214b  retn
```
