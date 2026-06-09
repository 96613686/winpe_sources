# NtPropagationCompleteExt

- ea: `0x1400181c0`
- end: `0x1400182ab`
- name: `NtPropagationCompleteExt`
- size: `235`
- prototype: `NTSTATUS __stdcall(HANDLE ResourceManagerHandle, ULONG RequestCookie, ULONG BufferLength, PVOID Buffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400181c0`
- `0x140018664`
- `0x1400187b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001828d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001828d`
- `ntoskrnl!ObfDereferenceObject` at `0x140018277`
- `ntoskrnl!ObfDereferenceObject` at `0x140018277`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140018248`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140018248`

## pseudocode

```c
NTSTATUS __stdcall NtPropagationCompleteExt(
        HANDLE ResourceManagerHandle,
        ULONG RequestCookie,
        ULONG BufferLength,
        PVOID Buffer)
{
  PVOID v4; // rsi
  PVOID v8; // rdi
  KPROCESSOR_MODE v9; // bl
  int v10; // r14d
  PVOID v11; // rbx
  PVOID Object[11]; // [rsp+30h] [rbp-58h] BYREF

  v4 = Buffer;
  v8 = 0;
  v9 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v9 )
  {
    if ( BufferLength )
    {
      v8 = TmpProbeAndCaptureBuffer(Buffer, BufferLength, 1u);
      Object[1] = v8;
    }
    v4 = v8;
    Object[2] = v8;
  }
  Object[0] = 0;
  v10 = ObReferenceObjectByHandle(
          ResourceManagerHandle,
          0x40u,
          (POBJECT_TYPE)TmResourceManagerObjectType,
          v9,
          Object,
          0);
  if ( v10 >= 0 )
  {
    v11 = Object[0];
    v10 = TmPropagationCompleteExt((PKRESOURCEMANAGER)Object[0], RequestCookie, BufferLength, v4);
    ObfDereferenceObject(v11);
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return v10;
}

```

## disassembly

```asm
0x1400181c0  push    rbx
0x1400181c2  push    rsi
0x1400181c3  push    rdi
0x1400181c4  push    r12
0x1400181c6  push    r14
0x1400181c8  push    r15
0x1400181ca  sub     rsp, 58h
0x1400181ce  mov     rsi, r9
0x1400181d1  mov     r15d, r8d
0x1400181d4  mov     r12d, edx
0x1400181d7  mov     r14, rcx
0x1400181da  xor     edi, edi
0x1400181dc  mov     rax, gs:188h
0x1400181e5  mov     bl, [rax+232h]
0x1400181eb  test    bl, bl
0x1400181ed  jz      short loc_14001821A
0x1400181ef  test    r8d, r8d
0x1400181f2  jz      short loc_14001820B
0x1400181f4  lea     r8d, [rdi+1]
0x1400181f8  mov     edx, r15d; Size
0x1400181fb  mov     rcx, r9; Src
0x1400181fe  call    TmpProbeAndCaptureBuffer
0x140018203  mov     rdi, rax
0x140018206  mov     [rsp+88h+var_50], rax
0x14001820b  mov     rsi, rdi
0x14001820e  mov     [rsp+88h+var_48], rdi
0x140018213  jmp     short loc_14001821A
0x140018215  jmp     loc_14001829C
0x14001821a  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x140018221  mov     [rsp+88h+var_58], 0
0x14001822a  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x140018233  lea     rax, [rsp+88h+var_58]
0x140018238  mov     [rsp+88h+Object], rax; Object
0x14001823d  mov     r9b, bl; AccessMode
0x140018240  mov     edx, 40h ; '@'; DesiredAccess
0x140018245  mov     rcx, r14; Handle
0x140018248  call    cs:__imp_ObReferenceObjectByHandle
0x14001824f  nop     dword ptr [rax+rax+00h]
0x140018254  mov     r14d, eax
0x140018257  test    eax, eax
0x140018259  js      short loc_140018283
0x14001825b  mov     rbx, [rsp+88h+var_58]
0x140018260  mov     r9, rsi; Buffer
0x140018263  mov     r8d, r15d; BufferLength
0x140018266  mov     edx, r12d; RequestCookie
0x140018269  mov     rcx, rbx; ResourceManager
0x14001826c  call    TmPropagationCompleteExt
0x140018271  mov     r14d, eax
0x140018274  mov     rcx, rbx; Object
0x140018277  call    cs:__imp_ObfDereferenceObject
0x14001827e  nop     dword ptr [rax+rax+00h]
0x140018283  test    rdi, rdi
0x140018286  jz      short loc_140018299
0x140018288  xor     edx, edx; Tag
0x14001828a  mov     rcx, rdi; P
0x14001828d  call    cs:__imp_ExFreePoolWithTag
0x140018294  nop     dword ptr [rax+rax+00h]
0x140018299  mov     eax, r14d
0x14001829c  add     rsp, 58h
0x1400182a0  pop     r15
0x1400182a2  pop     r14
0x1400182a4  pop     r12
0x1400182a6  pop     rdi
0x1400182a7  pop     rsi
0x1400182a8  pop     rbx
0x1400182a9  retn
0x140022033  push    rbp
0x140022035  sub     rsp, 30h
0x140022039  mov     rbp, rdx
0x14002203c  call    cs:__imp_ExSystemExceptionFilter
0x140022043  nop     dword ptr [rax+rax+00h]
0x140022048  nop
0x140022049  add     rsp, 30h
0x14002204d  pop     rbp
0x14002204e  retn
```
