# PriSubsumeContext

- ea: `0x14000b784`
- end: `0x14000b860`
- name: `PriSubsumeContext`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b070`

## callees

- `0x140001628`
- `0x14000ae40`
- `0x14000b784`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000b813`
- `ntoskrnl!ZwClose` at `0x14000b813`
- `FLTMGR!FltObjectDereference` at `0x14000b82c`
- `FLTMGR!FltObjectDereference` at `0x14000b845`
- `FLTMGR!FltObjectDereference` at `0x14000b82c`
- `FLTMGR!FltObjectDereference` at `0x14000b845`

## pseudocode

```c
__int64 __fastcall PriSubsumeContext(void *a1, char *a2, char *a3, void **a4)
{
  int ObjectsFromUserHandle; // ebp
  HANDLE Handle; // [rsp+40h] [rbp-48h] BYREF
  PVOID FltObject; // [rsp+48h] [rbp-40h] BYREF
  PVOID v11; // [rsp+50h] [rbp-38h] BYREF

  FltObject = 0;
  v11 = 0;
  Handle = 0;
  ObjectsFromUserHandle = PriGetObjectsFromUserHandle(
                            a1,
                            0x120196u,
                            (struct _FLT_FILTER **)&FltObject,
                            (PFLT_INSTANCE *)&v11,
                            0,
                            &Handle,
                            0);
  if ( ObjectsFromUserHandle >= 0 )
    ObjectsFromUserHandle = PFSubsumeContext((PFLT_FILTER)FltObject, (PFLT_INSTANCE)v11, Handle, a2, a3, a4);
  if ( Handle )
    ZwClose(Handle);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v11 )
    FltObjectDereference(v11);
  return (unsigned int)ObjectsFromUserHandle;
}

```

## disassembly

```asm
0x14000b784  mov     r11, rsp
0x14000b787  push    rbp
0x14000b788  push    r12
0x14000b78a  push    r14
0x14000b78c  push    r15
0x14000b78e  sub     rsp, 68h
0x14000b792  mov     qword ptr [r11-58h], 0
0x14000b79a  lea     rax, [r11-48h]
0x14000b79e  mov     r14, r9
0x14000b7a1  mov     [r11-60h], rax
0x14000b7a5  mov     r15, r8
0x14000b7a8  mov     qword ptr [r11-68h], 0
0x14000b7b0  mov     r12, rdx
0x14000b7b3  mov     qword ptr [r11-40h], 0
0x14000b7bb  lea     r9, [r11-38h]
0x14000b7bf  mov     qword ptr [r11-38h], 0
0x14000b7c7  lea     r8, [r11-40h]
0x14000b7cb  mov     qword ptr [r11-48h], 0
0x14000b7d3  mov     edx, 120196h; DesiredAccess
0x14000b7d8  call    PriGetObjectsFromUserHandle
0x14000b7dd  mov     ebp, eax
0x14000b7df  test    eax, eax
0x14000b7e1  js      short loc_14000B806
0x14000b7e3  mov     r8, [rsp+88h+Handle]
0x14000b7e8  mov     r9, r12
0x14000b7eb  mov     rdx, [rsp+88h+var_38]; Instance
0x14000b7f0  mov     rcx, [rsp+88h+FltObject]; Filter
0x14000b7f5  mov     [rsp+88h+TargetHandle], r14; TargetHandle
0x14000b7fa  mov     [rsp+88h+var_68], r15; __int64
0x14000b7ff  call    PFSubsumeContext
0x14000b804  mov     ebp, eax
0x14000b806  cmp     [rsp+88h+Handle], 0
0x14000b80c  jz      short loc_14000B81F
0x14000b80e  mov     rcx, [rsp+88h+Handle]; Handle
0x14000b813  call    cs:__imp_ZwClose
0x14000b81a  nop     dword ptr [rax+rax+00h]
0x14000b81f  cmp     [rsp+88h+FltObject], 0
0x14000b825  jz      short loc_14000B838
0x14000b827  mov     rcx, [rsp+88h+FltObject]; FltObject
0x14000b82c  call    cs:__imp_FltObjectDereference
0x14000b833  nop     dword ptr [rax+rax+00h]
0x14000b838  cmp     [rsp+88h+var_38], 0
0x14000b83e  jz      short loc_14000B851
0x14000b840  mov     rcx, [rsp+88h+var_38]; FltObject
0x14000b845  call    cs:__imp_FltObjectDereference
0x14000b84c  nop     dword ptr [rax+rax+00h]
0x14000b851  mov     eax, ebp
0x14000b853  add     rsp, 68h
0x14000b857  pop     r15
0x14000b859  pop     r14
0x14000b85b  pop     r12
0x14000b85d  pop     rbp
0x14000b85e  retn
```
