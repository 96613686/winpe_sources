# NtQueryInformationResourceManagerExt

- ea: `0x1400147e0`
- end: `0x140014a1e`
- name: `NtQueryInformationResourceManagerExt`
- size: `574`
- prototype: `NTSTATUS __stdcall(HANDLE ResourceManagerHandle, RESOURCEMANAGER_INFORMATION_CLASS ResourceManagerInformationClass, PVOID ResourceManagerInformation, ULONG ResourceManagerInformationLength, PULONG ReturnLength)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400024e0`
- `0x140002510`
- `0x140002640`
- `0x14000d198`
- `0x14000d238`
- `0x14000d2bc`
- `0x1400147e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001490e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001490e`
- `ntoskrnl!KeReleaseMutex` at `0x1400149eb`
- `ntoskrnl!KeReleaseMutex` at `0x140022403`
- `ntoskrnl!KeReleaseMutex` at `0x1400149eb`
- `ntoskrnl!KeReleaseMutex` at `0x140022403`
- `ntoskrnl!ObfDereferenceObject` at `0x1400149fa`
- `ntoskrnl!ObfDereferenceObject` at `0x140022412`
- `ntoskrnl!ObfDereferenceObject` at `0x1400149fa`
- `ntoskrnl!ObfDereferenceObject` at `0x140022412`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400148d5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400148d5`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400223a0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400223db`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022430`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400223a0`
- `ntoskrnl!ExSystemExceptionFilter` at `0x1400223db`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022430`
- `ntoskrnl!ProbeForWrite` at `0x140014883`
- `ntoskrnl!ProbeForWrite` at `0x140014883`

## pseudocode

```c
NTSTATUS __stdcall NtQueryInformationResourceManagerExt(
        HANDLE ResourceManagerHandle,
        RESOURCEMANAGER_INFORMATION_CLASS ResourceManagerInformationClass,
        PVOID ResourceManagerInformation,
        ULONG ResourceManagerInformationLength,
        PULONG ReturnLength)
{
  NTSTATUS result; // eax
  KPROCESSOR_MODE v8; // r12
  unsigned int ULongFromUser; // eax
  NTSTATUS v10; // ebx
  char *v11; // rsi
  struct _KMUTANT *v12; // r15
  bool v13; // zf
  char *v14; // r12
  ULONG v15; // edx
  int v16; // eax
  ULONG v17; // [rsp+34h] [rbp-94h]
  PVOID Object; // [rsp+48h] [rbp-80h] BYREF
  void *v19; // [rsp+50h] [rbp-78h]
  PULONG v20; // [rsp+58h] [rbp-70h]
  char *v21; // [rsp+60h] [rbp-68h]
  __int128 Src; // [rsp+68h] [rbp-60h] BYREF
  __int64 v23; // [rsp+78h] [rbp-50h]

  v19 = ResourceManagerInformation;
  v20 = ReturnLength;
  Src = 0;
  v23 = 0;
  v17 = 0;
  if ( ResourceManagerInformationClass )
    return -1073741821;
  v8 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v8 )
  {
    ProbeForWrite(ResourceManagerInformation, ResourceManagerInformationLength, 4u);
    if ( ReturnLength )
    {
      ULongFromUser = RtlReadULongFromUser(ReturnLength);
      RtlWriteULongToUser(ReturnLength, ULongFromUser);
    }
  }
  Object = 0;
  result = ObReferenceObjectByHandle(
             ResourceManagerHandle,
             1u,
             (POBJECT_TYPE)TmResourceManagerObjectType,
             v8,
             &Object,
             0);
  v10 = result;
  if ( result >= 0 )
  {
    v11 = (char *)Object;
    v12 = (struct _KMUTANT *)((char *)Object + 40);
    v21 = (char *)Object + 40;
    KeWaitForSingleObject((char *)Object + 40, Executive, 0, 0, 0);
    if ( ResourceManagerInformationLength >= 0x18 )
    {
      Src = 0;
      v23 = 0;
      Src = *(_OWORD *)(v11 + 136);
      LODWORD(v23) = *((unsigned __int16 *)v11 + 184);
      v13 = v8 == 0;
      v14 = (char *)v19;
      if ( v13 )
        RtlCopyVolatileMemory(v19, &Src, 0x18u);
      else
        RtlCopyToUser(v19, &Src, 0x18u);
      v15 = *((unsigned __int16 *)v11 + 184);
      v16 = v15 + 20;
      if ( v15 + 20 < 0x18 )
        v16 = 24;
      v17 = v16;
      if ( ResourceManagerInformationLength < v15 + 20 )
      {
        v10 = -2147483643;
        v15 = ResourceManagerInformationLength - 20;
      }
      memmove(v14 + 20, *((const void **)v11 + 47), v15);
    }
    else
    {
      v10 = -1073741789;
    }
    KeReleaseMutex(v12, 0);
    ObfDereferenceObject(v11);
    if ( ReturnLength )
      *ReturnLength = v17;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1400147e0  push    rbx
0x1400147e2  push    rsi
0x1400147e3  push    rdi
0x1400147e4  push    r12
0x1400147e6  push    r13
0x1400147e8  push    r14
0x1400147ea  push    r15
0x1400147ec  sub     rsp, 90h
0x1400147f3  mov     rax, cs:__security_cookie
0x1400147fa  xor     rax, rsp
0x1400147fd  mov     [rsp+0C8h+var_48], rax
0x140014805  mov     r13d, r9d
0x140014808  mov     r9, r8
0x14001480b  mov     [rsp+0C8h+var_78], r8
0x140014810  mov     rbx, rcx
0x140014813  mov     r14, [rsp+0C8h+ReturnLength]
0x14001481b  mov     [rsp+0C8h+var_70], r14
0x140014820  xorps   xmm0, xmm0
0x140014823  xor     eax, eax
0x140014825  movups  [rsp+0C8h+Src], xmm0
0x14001482a  mov     [rsp+0C8h+var_50], rax
0x14001482f  xor     edi, edi
0x140014831  mov     [rsp+0C8h+var_94], edi
0x140014835  test    edx, edx
0x140014837  jz      short loc_140014862
0x140014839  mov     eax, 0C0000003h
0x14001483e  mov     rcx, [rsp+0C8h+var_48]
0x140014846  xor     rcx, rsp; StackCookie
0x140014849  call    __security_check_cookie
0x14001484e  add     rsp, 90h
0x140014855  pop     r15
0x140014857  pop     r14
0x140014859  pop     r13
0x14001485b  pop     r12
0x14001485d  pop     rdi
0x14001485e  pop     rsi
0x14001485f  pop     rbx
0x140014860  retn
0x140014862  mov     rax, gs:188h
0x14001486b  mov     r12b, [rax+232h]
0x140014872  test    r12b, r12b
0x140014875  jz      short loc_1400148AA
0x140014877  mov     rdx, r13; Length
0x14001487a  mov     r8d, 4; Alignment
0x140014880  mov     rcx, r9; Address
0x140014883  call    cs:__imp_ProbeForWrite
0x14001488a  nop     dword ptr [rax+rax+00h]
0x14001488f  test    r14, r14
0x140014892  jz      short loc_1400148A6
0x140014894  mov     rcx, r14
0x140014897  call    RtlReadULongFromUser
0x14001489c  mov     edx, eax
0x14001489e  mov     rcx, r14
0x1400148a1  call    RtlWriteULongToUser
0x1400148a6  jmp     short loc_1400148AA
0x1400148a8  jmp     short loc_14001483E
0x1400148aa  mov     [rsp+0C8h+var_98], r12b
0x1400148af  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x1400148b6  mov     [rsp+0C8h+var_80], rdi
0x1400148bb  mov     [rsp+0C8h+HandleInformation], rdi; HandleInformation
0x1400148c0  lea     rax, [rsp+0C8h+var_80]
0x1400148c5  mov     [rsp+0C8h+Object], rax; Object
0x1400148ca  mov     r9b, r12b; AccessMode
0x1400148cd  mov     edx, 1; DesiredAccess
0x1400148d2  mov     rcx, rbx; Handle
0x1400148d5  call    cs:__imp_ObReferenceObjectByHandle
0x1400148dc  nop     dword ptr [rax+rax+00h]
0x1400148e1  mov     ebx, eax
0x1400148e3  test    eax, eax
0x1400148e5  js      loc_14001483E
0x1400148eb  mov     rsi, [rsp+0C8h+var_80]
0x1400148f0  mov     [rsp+0C8h+var_88], rsi
0x1400148f5  lea     r15, [rsi+28h]
0x1400148f9  mov     [rsp+0C8h+var_68], r15
0x1400148fe  mov     [rsp+0C8h+Object], rdi; Timeout
0x140014903  xor     r9d, r9d; Alertable
0x140014906  xor     r8d, r8d; WaitMode
0x140014909  xor     edx, edx; WaitReason
0x14001490b  mov     rcx, r15; Object
0x14001490e  call    cs:__imp_KeWaitForSingleObject
0x140014915  nop     dword ptr [rax+rax+00h]
0x14001491a  nop
0x14001491b  mov     ecx, 18h
0x140014920  cmp     r13d, ecx
0x140014923  jnb     short loc_14001492F
0x140014925  mov     ebx, 0C0000023h
0x14001492a  jmp     loc_1400149E6
0x14001492f  xorps   xmm0, xmm0
0x140014932  xor     eax, eax
0x140014934  movups  [rsp+0C8h+Src], xmm0
0x140014939  mov     [rsp+0C8h+var_50], rax
0x14001493e  movups  xmm0, xmmword ptr [rsi+88h]
0x140014945  movdqu  [rsp+0C8h+Src], xmm0
0x14001494b  movzx   eax, word ptr [rsi+170h]
0x140014952  mov     dword ptr [rsp+0C8h+var_50], eax
0x140014956  mov     word ptr [rsp+0C8h+var_50+4], di
0x14001495b  mov     r8, rcx; Size
0x14001495e  lea     rdx, [rsp+0C8h+Src]; Src
0x140014963  test    r12b, r12b
0x140014966  mov     r12, [rsp+0C8h+var_78]
0x14001496b  mov     rcx, r12; void *
0x14001496e  jz      short loc_140014977
0x140014970  call    RtlCopyToUser
0x140014975  jmp     short loc_14001497D
0x140014977  call    RtlCopyVolatileMemory
0x14001497c  nop
0x14001497d  movzx   edx, word ptr [rsi+170h]
0x140014984  lea     ecx, [rdx+14h]
0x140014987  mov     [rsp+0C8h+var_94], ecx
0x14001498b  mov     eax, ecx
0x14001498d  mov     r8d, 18h
0x140014993  cmp     ecx, r8d
0x140014996  cmovb   eax, r8d
0x14001499a  mov     [rsp+0C8h+var_94], eax
0x14001499e  cmp     r13d, ecx
0x1400149a1  jnb     short loc_1400149AC
0x1400149a3  mov     ebx, 80000005h
0x1400149a8  lea     edx, [r13-14h]
0x1400149ac  mov     r8d, edx; Size
0x1400149af  lea     rcx, [r12+14h]; void *
0x1400149b4  mov     rdx, [rsi+178h]; Src
0x1400149bb  call    memmove
0x1400149c0  jmp     short loc_1400149E6
0x1400149c2  mov     ebx, eax
0x1400149c4  mov     rsi, [rsp+0C8h+var_88]
0x1400149c9  mov     r14, [rsp+0C8h+var_70]
0x1400149ce  mov     r15, [rsp+0C8h+var_68]
0x1400149d3  jmp     short loc_1400149E6
0x1400149d5  mov     ebx, eax
0x1400149d7  mov     rsi, [rsp+0C8h+var_88]
0x1400149dc  mov     r14, [rsp+0C8h+var_70]
0x1400149e1  mov     r15, [rsp+0C8h+var_68]
0x1400149e6  xor     edx, edx; Wait
0x1400149e8  mov     rcx, r15; Mutex
0x1400149eb  call    cs:__imp_KeReleaseMutex
0x1400149f2  nop     dword ptr [rax+rax+00h]
0x1400149f7  mov     rcx, rsi; Object
0x1400149fa  call    cs:__imp_ObfDereferenceObject
0x140014a01  nop     dword ptr [rax+rax+00h]
0x140014a06  nop
0x140014a07  test    r14, r14
0x140014a0a  jz      short loc_140014A13
0x140014a0c  mov     eax, [rsp+0C8h+var_94]
0x140014a10  mov     [r14], eax
0x140014a13  jmp     short loc_140014A17
0x140014a15  mov     ebx, eax
0x140014a17  mov     eax, ebx
0x140014a19  jmp     loc_14001483E
0x140022397  push    rbp
0x140022399  sub     rsp, 30h
0x14002239d  mov     rbp, rdx
0x1400223a0  call    cs:__imp_ExSystemExceptionFilter
0x1400223a7  nop     dword ptr [rax+rax+00h]
0x1400223ac  nop
0x1400223ad  add     rsp, 30h
0x1400223b1  pop     rbp
0x1400223b2  retn
0x1400223b4  push    rbp
0x1400223b6  sub     rsp, 30h
0x1400223ba  mov     rbp, rdx
0x1400223bd  xor     eax, eax
0x1400223bf  cmp     [rbp+30h], al
0x1400223c2  setnz   al
0x1400223c5  mov     [rbp+38h], eax
0x1400223c8  mov     eax, [rbp+38h]
0x1400223cb  add     rsp, 30h
0x1400223cf  pop     rbp
0x1400223d0  retn
0x1400223d2  push    rbp
0x1400223d4  sub     rsp, 30h
0x1400223d8  mov     rbp, rdx
0x1400223db  call    cs:__imp_ExSystemExceptionFilter
0x1400223e2  nop     dword ptr [rax+rax+00h]
0x1400223e7  nop
0x1400223e8  add     rsp, 30h
0x1400223ec  pop     rbp
0x1400223ed  retn
0x1400223ef  push    rbx
0x1400223f1  push    rbp
0x1400223f2  sub     rsp, 38h
0x1400223f6  mov     rbp, rdx
0x1400223f9  mov     rbx, [rbp+40h]
0x1400223fd  lea     rcx, [rbx+28h]; Mutex
0x140022401  xor     edx, edx; Wait
0x140022403  call    cs:__imp_KeReleaseMutex
0x14002240a  nop     dword ptr [rax+rax+00h]
0x14002240f  mov     rcx, rbx; Object
0x140022412  call    cs:__imp_ObfDereferenceObject
0x140022419  nop     dword ptr [rax+rax+00h]
0x14002241e  nop
0x14002241f  add     rsp, 38h
0x140022423  pop     rbp
0x140022424  pop     rbx
0x140022425  retn
0x140022427  push    rbp
0x140022429  sub     rsp, 30h
0x14002242d  mov     rbp, rdx
0x140022430  call    cs:__imp_ExSystemExceptionFilter
0x140022437  nop     dword ptr [rax+rax+00h]
0x14002243c  nop
0x14002243d  add     rsp, 30h
0x140022441  pop     rbp
0x140022442  retn
```
