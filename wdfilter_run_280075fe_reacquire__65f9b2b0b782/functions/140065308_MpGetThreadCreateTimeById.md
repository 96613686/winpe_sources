# MpGetThreadCreateTimeById

- ea: `0x140065308`
- end: `0x1400653fc`
- name: `MpGetThreadCreateTimeById`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140063a70`

## callees

- `0x1400118d0`
- `0x140065308`
- `0x1400653fc`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14006538f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14006538f`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14006534c`
- `ntoskrnl!PsLookupThreadByThreadId` at `0x14006534c`
- `ntoskrnl!ZwClose` at `0x1400653cd`
- `ntoskrnl!ZwClose` at `0x1400653cd`
- `ntoskrnl!PsThreadType` at `0x140065371`
- `ntoskrnl!ObfDereferenceObject` at `0x1400653a2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400653a2`

## pseudocode

```c
__int64 __fastcall MpGetThreadCreateTimeById(void *a1, __int64 a2)
{
  NTSTATUS TimeByHandle; // ebx
  PVOID Object; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-20h] BYREF

  Handle = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  Object = 0;
  TimeByHandle = PsLookupThreadByThreadId(a1, (PETHREAD *)&Object);
  if ( TimeByHandle >= 0
    && (TimeByHandle = ObOpenObjectByPointer(Object, 0x200u, 0, 0x800u, (POBJECT_TYPE)PsThreadType, 0, &Handle),
        ObfDereferenceObject(Object),
        TimeByHandle >= 0) )
  {
    TimeByHandle = MpGetThreadCreateTimeByHandle(Handle, a2);
    ZwClose(Handle);
  }
  else
  {
    _mm_lfence();
  }
  return (unsigned int)TimeByHandle;
}

```

## disassembly

```asm
0x140065308  mov     r11, rsp
0x14006530b  mov     [r11+18h], rbx
0x14006530f  push    rdi
0x140065310  sub     rsp, 60h
0x140065314  mov     rax, cs:__security_cookie
0x14006531b  xor     rax, rsp
0x14006531e  mov     [rsp+68h+var_18], rax
0x140065323  mov     qword ptr [r11-20h], 0
0x14006532b  mov     rdi, rdx
0x14006532e  test    rcx, rcx
0x140065331  jz      loc_1400653DB
0x140065337  test    rdx, rdx
0x14006533a  jz      loc_1400653DB
0x140065340  lea     rdx, [r11-28h]; Thread
0x140065344  mov     qword ptr [r11-28h], 0
0x14006534c  call    cs:__imp_PsLookupThreadByThreadId
0x140065353  nop     dword ptr [rax+rax+00h]
0x140065358  mov     ebx, eax
0x14006535a  test    eax, eax
0x14006535c  js      short loc_1400653B2
0x14006535e  lea     rax, [rsp+68h+var_20]
0x140065363  mov     r9d, 800h; DesiredAccess
0x140065369  mov     [rsp+68h+Handle], rax; Handle
0x14006536e  xor     r8d, r8d; PassedAccessState
0x140065371  mov     rax, cs:__imp_PsThreadType
0x140065378  mov     edx, 200h; HandleAttributes
0x14006537d  mov     [rsp+68h+AccessMode], 0; AccessMode
0x140065382  mov     rcx, [rax]
0x140065385  mov     [rsp+68h+ObjectType], rcx; ObjectType
0x14006538a  mov     rcx, [rsp+68h+Object]; Object
0x14006538f  call    cs:__imp_ObOpenObjectByPointer
0x140065396  nop     dword ptr [rax+rax+00h]
0x14006539b  mov     rcx, [rsp+68h+Object]; Object
0x1400653a0  mov     ebx, eax
0x1400653a2  call    cs:__imp_ObfDereferenceObject
0x1400653a9  nop     dword ptr [rax+rax+00h]
0x1400653ae  test    ebx, ebx
0x1400653b0  jns     short loc_1400653B9
0x1400653b2  lfence
0x1400653b5  mov     eax, ebx
0x1400653b7  jmp     short loc_1400653E0
0x1400653b9  mov     rcx, [rsp+68h+var_20]
0x1400653be  mov     rdx, rdi
0x1400653c1  call    MpGetThreadCreateTimeByHandle
0x1400653c6  mov     rcx, [rsp+68h+var_20]; Handle
0x1400653cb  mov     ebx, eax
0x1400653cd  call    cs:__imp_ZwClose
0x1400653d4  nop     dword ptr [rax+rax+00h]
0x1400653d9  jmp     short loc_1400653B5
0x1400653db  mov     eax, 0C000000Dh
0x1400653e0  mov     rcx, [rsp+68h+var_18]
0x1400653e5  xor     rcx, rsp; StackCookie
0x1400653e8  call    __security_check_cookie
0x1400653ed  mov     rbx, [rsp+68h+arg_10]
0x1400653f5  add     rsp, 60h
0x1400653f9  pop     rdi
0x1400653fa  retn
```
