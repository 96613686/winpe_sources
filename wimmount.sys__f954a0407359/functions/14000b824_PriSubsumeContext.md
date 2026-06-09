# PriSubsumeContext

- ea: `0x14000b824`
- end: `0x14000b900`
- name: `PriSubsumeContext`
- size: `220`
- prototype: `__int64 __fastcall(void *, __int64, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b110`

## callees

- `0x140001628`
- `0x14000aee0`
- `0x14000b824`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b8b3`
- `ntoskrnl!ZwClose` at `0x14000b8b3`
- `FLTMGR!FltObjectDereference` at `0x14000b8cc`
- `FLTMGR!FltObjectDereference` at `0x14000b8e5`
- `FLTMGR!FltObjectDereference` at `0x14000b8cc`
- `FLTMGR!FltObjectDereference` at `0x14000b8e5`

## pseudocode

```c
__int64 __fastcall PriSubsumeContext(void *a1, __int64 a2, __int64 a3, void **a4)
{
  int ObjectsFromUserHandle; // ebp
  HANDLE Handle; // [rsp+40h] [rbp-48h] BYREF
  PVOID FltObject; // [rsp+48h] [rbp-40h] BYREF
  PVOID v10; // [rsp+50h] [rbp-38h] BYREF

  FltObject = 0;
  v10 = 0;
  Handle = 0;
  ObjectsFromUserHandle = PriGetObjectsFromUserHandle(
                            a1,
                            0x120196u,
                            (struct _FLT_FILTER **)&FltObject,
                            (PFLT_INSTANCE *)&v10,
                            0,
                            &Handle,
                            0);
  if ( ObjectsFromUserHandle >= 0 )
    ObjectsFromUserHandle = PFSubsumeContext((PFLT_FILTER)FltObject, (PFLT_INSTANCE)v10, a3, a4);
  if ( Handle )
    ZwClose(Handle);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v10 )
    FltObjectDereference(v10);
  return (unsigned int)ObjectsFromUserHandle;
}

```

## disassembly

```asm
0x14000b824  mov     r11, rsp
0x14000b827  push    rbp
0x14000b828  push    r12
0x14000b82a  push    r14
0x14000b82c  push    r15
0x14000b82e  sub     rsp, 68h
0x14000b832  mov     qword ptr [r11-58h], 0
0x14000b83a  lea     rax, [r11-48h]
0x14000b83e  mov     r14, r9
0x14000b841  mov     [r11-60h], rax
0x14000b845  mov     r15, r8
0x14000b848  mov     qword ptr [r11-68h], 0
0x14000b850  mov     r12, rdx
0x14000b853  mov     qword ptr [r11-40h], 0
0x14000b85b  lea     r9, [r11-38h]
0x14000b85f  mov     qword ptr [r11-38h], 0
0x14000b867  lea     r8, [r11-40h]
0x14000b86b  mov     qword ptr [r11-48h], 0
0x14000b873  mov     edx, 120196h; DesiredAccess
0x14000b878  call    PriGetObjectsFromUserHandle
0x14000b87d  mov     ebp, eax
0x14000b87f  test    eax, eax
0x14000b881  js      short loc_14000B8A6
0x14000b883  mov     r8, [rsp+88h+Handle]
0x14000b888  mov     r9, r12
0x14000b88b  mov     rdx, [rsp+88h+var_38]; Instance
0x14000b890  mov     rcx, [rsp+88h+FltObject]; Filter
0x14000b895  mov     [rsp+88h+TargetHandle], r14; TargetHandle
0x14000b89a  mov     [rsp+88h+var_68], r15; __int64
0x14000b89f  call    PFSubsumeContext
0x14000b8a4  mov     ebp, eax
0x14000b8a6  cmp     [rsp+88h+Handle], 0
0x14000b8ac  jz      short loc_14000B8BF
0x14000b8ae  mov     rcx, [rsp+88h+Handle]; Handle
0x14000b8b3  call    cs:__imp_ZwClose
0x14000b8ba  nop     dword ptr [rax+rax+00h]
0x14000b8bf  cmp     [rsp+88h+FltObject], 0
0x14000b8c5  jz      short loc_14000B8D8
0x14000b8c7  mov     rcx, [rsp+88h+FltObject]; FltObject
0x14000b8cc  call    cs:__imp_FltObjectDereference
0x14000b8d3  nop     dword ptr [rax+rax+00h]
0x14000b8d8  cmp     [rsp+88h+var_38], 0
0x14000b8de  jz      short loc_14000B8F1
0x14000b8e0  mov     rcx, [rsp+88h+var_38]; FltObject
0x14000b8e5  call    cs:__imp_FltObjectDereference
0x14000b8ec  nop     dword ptr [rax+rax+00h]
0x14000b8f1  mov     eax, ebp
0x14000b8f3  add     rsp, 68h
0x14000b8f7  pop     r15
0x14000b8f9  pop     r14
0x14000b8fb  pop     r12
0x14000b8fd  pop     rbp
0x14000b8fe  retn
```
