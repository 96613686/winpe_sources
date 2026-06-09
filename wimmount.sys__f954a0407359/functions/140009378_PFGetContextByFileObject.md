# PFGetContextByFileObject

- ea: `0x140009378`
- end: `0x1400095c2`
- name: `PFGetContextByFileObject`
- size: `586`
- prototype: `__int64 __usercall@<rax>(PFLT_FILTER Filter@<rcx>, PFLT_INSTANCE Instance@<rdx>, PFILE_OBJECT FileObject@<r8>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001628`
- `0x140009aa0`

## callees

- `0x140002bb0`
- `0x140009378`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140009466`
- `ntoskrnl!KeInitializeEvent` at `0x140009466`
- `ntoskrnl!KeSetEvent` at `0x14000956e`
- `ntoskrnl!KeSetEvent` at `0x14000956e`
- `FLTMGR!FltAllocateContext` at `0x140009424`
- `FLTMGR!FltAllocateContext` at `0x140009424`
- `FLTMGR!FltSetStreamContext` at `0x1400094c6`
- `FLTMGR!FltSetStreamContext` at `0x1400094c6`
- `FLTMGR!FltDeleteStreamContext` at `0x140009583`
- `FLTMGR!FltDeleteStreamContext` at `0x140009583`
- `FLTMGR!FltGetStreamContext` at `0x1400093da`
- `FLTMGR!FltGetStreamContext` at `0x1400093da`
- `FLTMGR!FltQueryInformationFile` at `0x14000948d`
- `FLTMGR!FltQueryInformationFile` at `0x14000948d`
- `FLTMGR!FltFsControlFile` at `0x14000951b`
- `FLTMGR!FltFsControlFile` at `0x14000951b`
- `FLTMGR!FltReleaseContext` at `0x140009593`
- `FLTMGR!FltReleaseContext` at `0x140009593`

## pseudocode

```c
__int64 __fastcall PFGetContextByFileObject(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *a4,
        _BYTE *a5)
{
  char v8; // r12
  NTSTATUS StreamContext; // eax
  NTSTATUS v11; // ebx
  _OWORD *v12; // rax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  PFLT_CONTEXT NewContext; // [rsp+40h] [rbp-31h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-29h] BYREF
  __int64 FileInformation; // [rsp+50h] [rbp-21h] BYREF
  _DWORD OutputBuffer[8]; // [rsp+58h] [rbp-19h] BYREF

  *a4 = 0;
  NewContext = 0;
  *a5 = 0;
  Context = 0;
  v8 = 0;
  FileInformation = 0;
  memset(OutputBuffer, 0, 28);
  StreamContext = FltGetStreamContext(Instance, FileObject, &Context);
  v11 = StreamContext;
  if ( StreamContext >= 0 )
  {
    *a4 = Context;
    *a5 = 0;
    goto LABEL_17;
  }
  if ( StreamContext == -1073741275 )
  {
    v11 = FltAllocateContext(Filter, 8u, 0x38u, (POOL_TYPE)512, &NewContext);
    if ( v11 >= 0 )
    {
      v12 = NewContext;
      *(_OWORD *)NewContext = 0;
      v12[1] = 0;
      v12[2] = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_DWORD *)NewContext + 6) = 0;
      KeInitializeEvent((PRKEVENT)NewContext, NotificationEvent, 0);
      v11 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 8u, FileInternalInformation, 0);
      if ( v11 >= 0 )
      {
        *((_QWORD *)NewContext + 4) = FileInformation;
        v13 = FltSetStreamContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &Context);
        v11 = v13;
        if ( v13 == -1071906814 )
        {
          *a4 = Context;
          *a5 = 0;
LABEL_8:
          v11 = 0;
          goto LABEL_17;
        }
        if ( v13 >= 0 )
        {
          v8 = 1;
          v14 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, 0x1Cu, 0);
          v11 = v14;
          if ( v14 == -2147483643 || !v14 )
          {
            v11 = 0;
            if ( OutputBuffer[0] != -2147483640 )
              goto LABEL_17;
          }
          else
          {
            if ( v14 == -1073741195 )
              goto LABEL_8;
            if ( v14 < 0 )
              goto LABEL_17;
          }
          *a4 = NewContext;
          *a5 = 1;
          NewContext = 0;
        }
      }
    }
  }
LABEL_17:
  if ( NewContext )
  {
    if ( v8 )
    {
      KeSetEvent((PRKEVENT)NewContext, 0, 0);
      FltDeleteStreamContext(Instance, FileObject, 0);
    }
    FltReleaseContext(NewContext);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140009378  push    rbp
0x14000937a  push    rbx
0x14000937b  push    rsi
0x14000937c  push    rdi
0x14000937d  push    r12
0x14000937f  push    r13
0x140009381  push    r14
0x140009383  push    r15
0x140009385  lea     rbp, [rsp-17h]
0x14000938a  sub     rsp, 88h
0x140009391  mov     rax, cs:__security_cookie
0x140009398  xor     rax, rsp
0x14000939b  mov     [rbp+4Fh+var_48], rax
0x14000939f  mov     rsi, [rbp+4Fh+arg_20]
0x1400093a3  mov     r13, rcx
0x1400093a6  xor     ecx, ecx
0x1400093a8  mov     r15, r8
0x1400093ab  mov     r14, rdx
0x1400093ae  mov     [r9], rcx
0x1400093b1  xorps   xmm0, xmm0
0x1400093b4  mov     [rbp+4Fh+NewContext], rcx
0x1400093b8  mov     [rsi], cl
0x1400093ba  lea     r8, [rbp+4Fh+Context]; Context
0x1400093be  mov     [rbp+4Fh+Context], rcx
0x1400093c2  mov     r12b, cl
0x1400093c5  mov     [rbp+4Fh+FileInformation], rcx
0x1400093c9  mov     rdx, r15; FileObject
0x1400093cc  movups  xmmword ptr [rbp+4Fh+OutputBuffer], xmm0
0x1400093d0  mov     rcx, r14; Instance
0x1400093d3  mov     rdi, r9
0x1400093d6  movups  xmmword ptr [rbp+4Fh+OutputBuffer+0Ch], xmm0
0x1400093da  call    cs:__imp_FltGetStreamContext
0x1400093e1  nop     dword ptr [rax+rax+00h]
0x1400093e6  mov     ebx, eax
0x1400093e8  test    eax, eax
0x1400093ea  js      short loc_1400093FE
0x1400093ec  mov     rcx, [rbp+4Fh+Context]
0x1400093f0  xor     r13d, r13d
0x1400093f3  mov     [rdi], rcx
0x1400093f6  mov     [rsi], r13b
0x1400093f9  jmp     loc_14000955B
0x1400093fe  cmp     eax, 0C0000225h
0x140009403  jnz     loc_14000955B
0x140009409  mov     edx, 8; ContextType
0x14000940e  lea     rax, [rbp+4Fh+NewContext]
0x140009412  mov     r9d, 200h; PoolType
0x140009418  mov     [rsp+0C0h+ReturnedContext], rax; ReturnedContext
0x14000941d  mov     rcx, r13; Filter
0x140009420  lea     r8d, [rdx+30h]; ContextSize
0x140009424  call    cs:__imp_FltAllocateContext
0x14000942b  nop     dword ptr [rax+rax+00h]
0x140009430  xor     r13d, r13d
0x140009433  mov     ebx, eax
0x140009435  test    eax, eax
0x140009437  js      loc_14000955B
0x14000943d  mov     rax, [rbp+4Fh+NewContext]
0x140009441  xorps   xmm0, xmm0
0x140009444  xor     ecx, ecx
0x140009446  xor     r8d, r8d; State
0x140009449  xor     edx, edx; Type
0x14000944b  movups  xmmword ptr [rax], xmm0
0x14000944e  movups  xmmword ptr [rax+10h], xmm0
0x140009452  movups  xmmword ptr [rax+20h], xmm0
0x140009456  mov     [rax+30h], rcx
0x14000945a  mov     rax, [rbp+4Fh+NewContext]
0x14000945e  mov     [rax+18h], r13d
0x140009462  mov     rcx, [rbp+4Fh+NewContext]; Event
0x140009466  call    cs:__imp_KeInitializeEvent
0x14000946d  nop     dword ptr [rax+rax+00h]
0x140009472  lea     r9d, [r13+8]; Length
0x140009476  mov     [rsp+0C0h+LengthReturned], r13; LengthReturned
0x14000947b  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14000947f  mov     dword ptr [rsp+0C0h+ReturnedContext], 6; FileInformationClass
0x140009487  mov     rdx, r15; FileObject
0x14000948a  mov     rcx, r14; Instance
0x14000948d  call    cs:__imp_FltQueryInformationFile
0x140009494  nop     dword ptr [rax+rax+00h]
0x140009499  mov     ebx, eax
0x14000949b  test    eax, eax
0x14000949d  js      loc_14000955B
0x1400094a3  mov     rcx, [rbp+4Fh+NewContext]
0x1400094a7  lea     r8d, [r13+1]; Operation
0x1400094ab  mov     rax, [rbp+4Fh+FileInformation]
0x1400094af  mov     rdx, r15; FileObject
0x1400094b2  mov     [rcx+20h], rax
0x1400094b6  lea     rax, [rbp+4Fh+Context]
0x1400094ba  mov     r9, [rbp+4Fh+NewContext]; NewContext
0x1400094be  mov     rcx, r14; Instance
0x1400094c1  mov     [rsp+0C0h+ReturnedContext], rax; OldContext
0x1400094c6  call    cs:__imp_FltSetStreamContext
0x1400094cd  nop     dword ptr [rax+rax+00h]
0x1400094d2  mov     ebx, eax
0x1400094d4  cmp     eax, 0C01C0002h
0x1400094d9  jnz     short loc_1400094EA
0x1400094db  mov     rax, [rbp+4Fh+Context]
0x1400094df  mov     [rdi], rax
0x1400094e2  mov     [rsi], r13b
0x1400094e5  mov     ebx, r13d
0x1400094e8  jmp     short loc_14000955B
0x1400094ea  test    eax, eax
0x1400094ec  js      short loc_14000955B
0x1400094ee  mov     [rsp+0C0h+var_88], r13; LengthReturned
0x1400094f3  lea     rax, [rbp+4Fh+OutputBuffer]
0x1400094f7  mov     [rsp+0C0h+OutputBufferLength], 1Ch; OutputBufferLength
0x1400094ff  xor     r9d, r9d; InputBuffer
0x140009502  mov     [rsp+0C0h+LengthReturned], rax; OutputBuffer
0x140009507  mov     r8d, 900A8h; FsControlCode
0x14000950d  mov     rdx, r15; FileObject
0x140009510  mov     dword ptr [rsp+0C0h+ReturnedContext], r13d; InputBufferLength
0x140009515  mov     rcx, r14; Instance
0x140009518  mov     r12b, 1
0x14000951b  call    cs:__imp_FltFsControlFile
0x140009522  nop     dword ptr [rax+rax+00h]
0x140009527  mov     ebx, eax
0x140009529  cmp     eax, 80000005h
0x14000952e  jz      short loc_140009541
0x140009530  test    eax, eax
0x140009532  jz      short loc_140009541
0x140009534  cmp     eax, 0C0000275h
0x140009539  jz      short loc_1400094E5
0x14000953b  test    eax, eax
0x14000953d  jns     short loc_14000954D
0x14000953f  jmp     short loc_14000955B
0x140009541  cmp     [rbp+4Fh+OutputBuffer], 80000008h
0x140009548  mov     ebx, r13d
0x14000954b  jnz     short loc_14000955B
0x14000954d  mov     rax, [rbp+4Fh+NewContext]
0x140009551  mov     [rdi], rax
0x140009554  mov     [rsi], r12b
0x140009557  mov     [rbp+4Fh+NewContext], r13
0x14000955b  mov     rcx, [rbp+4Fh+NewContext]; Event
0x14000955f  test    rcx, rcx
0x140009562  jz      short loc_14000959F
0x140009564  test    r12b, r12b
0x140009567  jz      short loc_14000958F
0x140009569  xor     r8d, r8d; Wait
0x14000956c  xor     edx, edx; Increment
0x14000956e  call    cs:__imp_KeSetEvent
0x140009575  nop     dword ptr [rax+rax+00h]
0x14000957a  xor     r8d, r8d; OldContext
0x14000957d  mov     rdx, r15; FileObject
0x140009580  mov     rcx, r14; Instance
0x140009583  call    cs:__imp_FltDeleteStreamContext
0x14000958a  nop     dword ptr [rax+rax+00h]
0x14000958f  mov     rcx, [rbp+4Fh+NewContext]; Context
0x140009593  call    cs:__imp_FltReleaseContext
0x14000959a  nop     dword ptr [rax+rax+00h]
0x14000959f  mov     eax, ebx
0x1400095a1  mov     rcx, [rbp+4Fh+var_48]
0x1400095a5  xor     rcx, rsp; StackCookie
0x1400095a8  call    __security_check_cookie
0x1400095ad  add     rsp, 88h
0x1400095b4  pop     r15
0x1400095b6  pop     r14
0x1400095b8  pop     r13
0x1400095ba  pop     r12
0x1400095bc  pop     rdi
0x1400095bd  pop     rsi
0x1400095be  pop     rbx
0x1400095bf  pop     rbp
0x1400095c0  retn
```
