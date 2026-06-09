# WcOpenDefaultStream

- ea: `0x14001ef50`
- end: `0x14001f084`
- name: `WcOpenDefaultStream`
- size: `308`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, _QWORD *, PVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400184f0`

## callees

- `0x14001ef50`
- `0x14001fc48`
- `0x140029658`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001ef89`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ef89`
- `ntoskrnl!ObfDereferenceObject` at `0x14001f068`
- `ntoskrnl!ObfDereferenceObject` at `0x14001f068`
- `FLTMGR!FltClose` at `0x14001f053`
- `FLTMGR!FltClose` at `0x14001f053`
- `FLTMGR!FltReleaseContext` at `0x14001effe`
- `FLTMGR!FltReleaseContext` at `0x14001f013`
- `FLTMGR!FltReleaseContext` at `0x14001effe`
- `FLTMGR!FltReleaseContext` at `0x14001f013`

## pseudocode

```c
__int64 __fastcall WcOpenDefaultStream(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        _QWORD *a4,
        PVOID *a5)
{
  int SetContextFileObject; // ebx
  void *v10; // rdx
  PVOID v11; // rcx
  int FileObjecta; // [rsp+20h] [rbp-58h]
  PVOID Object; // [rsp+40h] [rbp-38h] BYREF
  void *v15; // [rsp+48h] [rbp-30h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-28h] BYREF
  PFLT_CONTEXT v17; // [rsp+58h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-18h] BYREF

  v15 = 0;
  Object = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  SetContextFileObject = WcRelativeStreamOpen(Instance, (PFILE_OBJECT *)&Object);
  if ( SetContextFileObject < 0 )
    goto LABEL_9;
  if ( !a3 )
    goto LABEL_8;
  v17 = 0;
  Context = 0;
  SetContextFileObject = WcGetSetContextFileObject(Instance, FileObject, a3, 0, FileObjecta, &Context, &v17);
  if ( Context )
    FltReleaseContext(Context);
  if ( v17 )
    FltReleaseContext(v17);
  if ( SetContextFileObject < 0 )
  {
LABEL_9:
    v10 = v15;
    v11 = Object;
  }
  else
  {
LABEL_8:
    v10 = 0;
    *a4 = v15;
    v15 = 0;
    *a5 = Object;
    v11 = 0;
    Object = 0;
  }
  if ( v10 )
  {
    FltClose(v10);
    v11 = Object;
  }
  if ( v11 )
    ObfDereferenceObject(v11);
  return (unsigned int)SetContextFileObject;
}

```

## disassembly

```asm
0x14001ef50  push    rbp
0x14001ef52  push    rbx
0x14001ef53  push    rsi
0x14001ef54  push    rdi
0x14001ef55  push    r14
0x14001ef57  push    r15
0x14001ef59  mov     rbp, rsp
0x14001ef5c  sub     rsp, 78h
0x14001ef60  mov     rsi, rdx
0x14001ef63  mov     [rbp+var_30], 0
0x14001ef6b  mov     r14, rcx
0x14001ef6e  mov     [rbp+Object], 0
0x14001ef76  xorps   xmm0, xmm0
0x14001ef79  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001ef7d  xor     edx, edx; SourceString
0x14001ef7f  mov     r15, r9
0x14001ef82  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001ef86  mov     rdi, r8
0x14001ef89  call    cs:__imp_RtlInitUnicodeString
0x14001ef90  nop     dword ptr [rax+rax+00h]
0x14001ef95  lea     rax, [rbp+Object]
0x14001ef99  mov     rdx, rsi
0x14001ef9c  lea     r9, [rbp+var_30]
0x14001efa0  mov     [rsp+78h+FileObject], rax; int
0x14001efa5  lea     r8, [rbp+DestinationString]
0x14001efa9  mov     rcx, r14; Instance
0x14001efac  call    WcRelativeStreamOpen
0x14001efb1  mov     ebx, eax
0x14001efb3  test    eax, eax
0x14001efb5  js      loc_14001F043
0x14001efbb  test    rdi, rdi
0x14001efbe  jz      short loc_14001F023
0x14001efc0  lea     rax, [rbp+var_20]
0x14001efc4  mov     [rbp+var_20], 0
0x14001efcc  mov     [rsp+78h+var_48], rax; __int64
0x14001efd1  xor     r9d, r9d
0x14001efd4  lea     rax, [rbp+Context]
0x14001efd8  mov     [rbp+Context], 0
0x14001efe0  mov     r8, rdi
0x14001efe3  mov     [rsp+78h+var_50], rax; __int64
0x14001efe8  mov     rdx, rsi; FileObject
0x14001efeb  mov     rcx, r14; Instance
0x14001efee  call    WcGetSetContextFileObject
0x14001eff3  mov     rcx, [rbp+Context]; Context
0x14001eff7  mov     ebx, eax
0x14001eff9  test    rcx, rcx
0x14001effc  jz      short loc_14001F00A
0x14001effe  call    cs:__imp_FltReleaseContext
0x14001f005  nop     dword ptr [rax+rax+00h]
0x14001f00a  mov     rcx, [rbp+var_20]; Context
0x14001f00e  test    rcx, rcx
0x14001f011  jz      short loc_14001F01F
0x14001f013  call    cs:__imp_FltReleaseContext
0x14001f01a  nop     dword ptr [rax+rax+00h]
0x14001f01f  test    ebx, ebx
0x14001f021  js      short loc_14001F043
0x14001f023  mov     rax, [rbp+var_30]
0x14001f027  xor     edx, edx
0x14001f029  mov     rcx, [rbp+arg_20]
0x14001f02d  mov     [r15], rax
0x14001f030  mov     rax, [rbp+Object]
0x14001f034  mov     [rbp+var_30], rdx
0x14001f038  mov     [rcx], rax
0x14001f03b  xor     ecx, ecx
0x14001f03d  mov     [rbp+Object], rcx
0x14001f041  jmp     short loc_14001F04B
0x14001f043  mov     rdx, [rbp+var_30]
0x14001f047  mov     rcx, [rbp+Object]
0x14001f04b  test    rdx, rdx
0x14001f04e  jz      short loc_14001F063
0x14001f050  mov     rcx, rdx; FileHandle
0x14001f053  call    cs:__imp_FltClose
0x14001f05a  nop     dword ptr [rax+rax+00h]
0x14001f05f  mov     rcx, [rbp+Object]; Object
0x14001f063  test    rcx, rcx
0x14001f066  jz      short loc_14001F074
0x14001f068  call    cs:__imp_ObfDereferenceObject
0x14001f06f  nop     dword ptr [rax+rax+00h]
0x14001f074  mov     eax, ebx
0x14001f076  add     rsp, 78h
0x14001f07a  pop     r15
0x14001f07c  pop     r14
0x14001f07e  pop     rdi
0x14001f07f  pop     rsi
0x14001f080  pop     rbx
0x14001f081  pop     rbp
0x14001f082  retn
```
