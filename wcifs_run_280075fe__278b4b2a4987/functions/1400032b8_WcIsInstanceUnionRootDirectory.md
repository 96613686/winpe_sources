# WcIsInstanceUnionRootDirectory

- ea: `0x1400032b8`
- end: `0x140003393`
- name: `WcIsInstanceUnionRootDirectory`
- size: `219`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140030a70`

## callees

- `0x1400032b8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400032f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400032f3`
- `FLTMGR!FltQueryInformationFile` at `0x140003342`
- `FLTMGR!FltQueryInformationFile` at `0x140003342`
- `FLTMGR!FltReleaseContext` at `0x140003377`
- `FLTMGR!FltReleaseContext` at `0x140003377`
- `FLTMGR!FltGetInstanceContext` at `0x140003306`
- `FLTMGR!FltGetInstanceContext` at `0x140003306`

## pseudocode

```c
bool __fastcall WcIsInstanceUnionRootDirectory(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)
{
  bool v4; // bl
  PFLT_CONTEXT v5; // rcx
  __int64 FileInformation; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  ULONG LengthReturned; // [rsp+80h] [rbp+30h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+38h] BYREF

  Context = 0;
  FileInformation = 0;
  LengthReturned = 0;
  DestinationString = 0;
  v4 = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( FltGetInstanceContext(Instance, &Context) < 0 )
    goto LABEL_5;
  v5 = Context;
  if ( !*((_QWORD *)Context + 7) )
    goto LABEL_6;
  if ( FltQueryInformationFile(Instance, FileObject, &FileInformation, 8u, FileInternalInformation, &LengthReturned) < 0 )
  {
LABEL_5:
    v5 = Context;
  }
  else
  {
    v5 = Context;
    v4 = FileInformation == *((_QWORD *)Context + 36);
  }
LABEL_6:
  if ( v5 )
    FltReleaseContext(v5);
  return v4;
}

```

## disassembly

```asm
0x1400032b8  mov     [rsp-18h+arg_0], rbx
0x1400032bd  push    rbp
0x1400032be  push    rsi
0x1400032bf  push    rdi
0x1400032c0  mov     rbp, rsp
0x1400032c3  sub     rsp, 50h
0x1400032c7  mov     rsi, rdx
0x1400032ca  mov     [rbp+Context], 0
0x1400032d2  mov     rdi, rcx
0x1400032d5  mov     [rbp+FileInformation], 0
0x1400032dd  xorps   xmm0, xmm0
0x1400032e0  mov     [rbp+arg_10], 0
0x1400032e7  xor     edx, edx; SourceString
0x1400032e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400032ed  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400032f1  xor     bl, bl
0x1400032f3  call    cs:__imp_RtlInitUnicodeString
0x1400032fa  nop     dword ptr [rax+rax+00h]
0x1400032ff  lea     rdx, [rbp+Context]; Context
0x140003303  mov     rcx, rdi; Instance
0x140003306  call    cs:__imp_FltGetInstanceContext
0x14000330d  nop     dword ptr [rax+rax+00h]
0x140003312  test    eax, eax
0x140003314  js      short loc_14000336E
0x140003316  mov     rcx, [rbp+Context]
0x14000331a  cmp     qword ptr [rcx+38h], 0
0x14000331f  jz      short loc_140003372
0x140003321  lea     rax, [rbp+arg_10]
0x140003325  mov     r9d, 8; Length
0x14000332b  mov     [rsp+50h+LengthReturned], rax; LengthReturned
0x140003330  lea     r8, [rbp+FileInformation]; FileInformation
0x140003334  mov     rdx, rsi; FileObject
0x140003337  mov     [rsp+50h+FileInformationClass], 6; FileInformationClass
0x14000333f  mov     rcx, rdi; Instance
0x140003342  call    cs:__imp_FltQueryInformationFile
0x140003349  nop     dword ptr [rax+rax+00h]
0x14000334e  test    eax, eax
0x140003350  js      short loc_14000336E
0x140003352  mov     rcx, [rbp+Context]
0x140003356  mov     edx, 1
0x14000335b  movzx   ebx, bl
0x14000335e  mov     rax, [rcx+120h]
0x140003365  cmp     [rbp+FileInformation], rax
0x140003369  cmovz   ebx, edx
0x14000336c  jmp     short loc_140003372
0x14000336e  mov     rcx, [rbp+Context]; Context
0x140003372  test    rcx, rcx
0x140003375  jz      short loc_140003383
0x140003377  call    cs:__imp_FltReleaseContext
0x14000337e  nop     dword ptr [rax+rax+00h]
0x140003383  mov     al, bl
0x140003385  mov     rbx, [rsp+50h+arg_0]
0x14000338a  add     rsp, 50h
0x14000338e  pop     rdi
0x14000338f  pop     rsi
0x140003390  pop     rbp
0x140003391  retn
```
