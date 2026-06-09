# MpCreateHandleContext

- ea: `0x140054230`
- end: `0x140054492`
- name: `MpCreateHandleContext`
- size: `610`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400036a0`
- `0x14002e850`
- `0x140032be0`
- `0x1400408b0`
- `0x140042be0`
- `0x140053f20`
- `0x140071b28`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140011bc0`
- `0x140054230`

## import_xrefs

- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140054334`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140054334`
- `ntoskrnl!IoGetCurrentProcess` at `0x140054325`
- `ntoskrnl!IoGetCurrentProcess` at `0x140054325`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140054310`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140054310`
- `FLTMGR!FltReleaseContext` at `0x140054408`
- `FLTMGR!FltReleaseContext` at `0x140054484`
- `FLTMGR!FltReleaseContext` at `0x14008ca62`
- `FLTMGR!FltReleaseContext` at `0x140054408`
- `FLTMGR!FltReleaseContext` at `0x140054484`
- `FLTMGR!FltReleaseContext` at `0x14008ca62`
- `FLTMGR!FltInitializePushLock` at `0x14005435d`
- `FLTMGR!FltInitializePushLock` at `0x140054372`
- `FLTMGR!FltInitializePushLock` at `0x14005435d`
- `FLTMGR!FltInitializePushLock` at `0x140054372`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400543ad`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400543ad`
- `FLTMGR!FltAllocateContext` at `0x140054290`
- `FLTMGR!FltAllocateContext` at `0x140054290`

## pseudocode

```c
__int64 __fastcall MpCreateHandleContext(__int64 a1, PFLT_CONTEXT *a2, _BYTE *a3)
{
  NTSTATUS v6; // edi
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  _QWORD *v11; // rax
  PFLT_CONTEXT NewContext; // [rsp+38h] [rbp-40h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+40h] [rbp-38h] BYREF

  NewContext = 0;
  OldContext = 0;
  if ( a3 )
    *a3 = 0;
  v6 = FltAllocateContext(*(PFLT_FILTER *)(a1 + 8), 0x10u, 0x78u, PagedPool, &NewContext);
  if ( v6 >= 0 )
  {
    memset(NewContext, 0, 0x78u);
    *(_WORD *)NewContext = -9724;
    *((_WORD *)NewContext + 1) = 120;
    *((_QWORD *)NewContext + 2) = KeGetCurrentThread();
    v8 = NewContext;
    v8[3] = PsGetCurrentProcessId();
    v9 = NewContext;
    CurrentProcess = IoGetCurrentProcess();
    v9[4] = PsGetProcessCreateTimeQuadPart(CurrentProcess);
    v11 = (char *)NewContext + 48;
    *((_QWORD *)NewContext + 7) = (char *)NewContext + 48;
    *v11 = v11;
    FltInitializePushLock((PULONG_PTR)NewContext + 8);
    FltInitializePushLock((PULONG_PTR)NewContext + 9);
    *((_QWORD *)NewContext + 12) = 0;
    *((_QWORD *)NewContext + 13) = 0;
    v6 = FltSetStreamHandleContext(
           *(PFLT_INSTANCE *)(a1 + 24),
           *(PFILE_OBJECT *)(a1 + 32),
           FLT_SET_CONTEXT_KEEP_IF_EXISTS,
           NewContext,
           &OldContext);
    if ( v6 >= 0 )
    {
      *a2 = NewContext;
      NewContext = 0;
      goto LABEL_17;
    }
    FltReleaseContext(NewContext);
    NewContext = 0;
    if ( v6 == -1071906814 )
    {
      *a2 = OldContext;
      if ( a3 )
        *a3 = 1;
      v6 = 0;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v7 = 52;
      goto LABEL_9;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v7 = 51;
LABEL_9:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids,
      KeGetCurrentThread(),
      v6);
  }
LABEL_17:
  if ( NewContext )
    FltReleaseContext(NewContext);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140054230  mov     [rsp+arg_18], rbx
0x140054235  push    rsi
0x140054236  push    rdi
0x140054237  push    r12
0x140054239  push    r14
0x14005423b  push    r15
0x14005423d  sub     rsp, 50h
0x140054241  mov     rax, cs:__security_cookie
0x140054248  xor     rax, rsp
0x14005424b  mov     [rsp+78h+var_30], rax
0x140054250  mov     rbx, r8
0x140054253  mov     r14, rdx
0x140054256  mov     rsi, rcx
0x140054259  xor     r15d, r15d
0x14005425c  mov     [rsp+78h+NewContext], r15
0x140054261  mov     [rsp+78h+OldContext], r15
0x140054266  test    r8, r8
0x140054269  jz      short loc_14005426E
0x14005426b  mov     [r8], r15b
0x14005426e  mov     edx, 10h; ContextType
0x140054273  lea     rax, [rsp+78h+NewContext]
0x140054278  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14005427d  mov     r9d, 1; PoolType
0x140054283  mov     r12d, 78h ; 'x'
0x140054289  mov     r8d, r12d; ContextSize
0x14005428c  mov     rcx, [rcx+8]; Filter
0x140054290  call    cs:__imp_FltAllocateContext
0x140054297  nop     dword ptr [rax+rax+00h]
0x14005429c  mov     edi, eax
0x14005429e  mov     [rsp+78h+var_48], eax
0x1400542a2  test    eax, eax
0x1400542a4  jns     short loc_1400542D3
0x1400542a6  lea     rax, WPP_GLOBAL_Control
0x1400542ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400542b4  cmp     rcx, rax
0x1400542b7  jz      loc_140054455
0x1400542bd  mov     ecx, [rcx+2Ch]
0x1400542c0  test    cl, 1
0x1400542c3  jz      loc_140054455
0x1400542c9  mov     edx, 33h ; '3'
0x1400542ce  jmp     loc_1400543DA
0x1400542d3  mov     r8, r12; Size
0x1400542d6  xor     edx, edx; Val
0x1400542d8  mov     rcx, [rsp+78h+NewContext]; void *
0x1400542dd  call    memset
0x1400542e2  mov     ecx, 0DA04h
0x1400542e7  mov     rax, [rsp+78h+NewContext]
0x1400542ec  mov     [rax], cx
0x1400542ef  mov     rax, [rsp+78h+NewContext]
0x1400542f4  mov     [rax+2], r12w
0x1400542f9  mov     rcx, gs:188h
0x140054302  mov     rax, [rsp+78h+NewContext]
0x140054307  mov     [rax+10h], rcx
0x14005430b  mov     rdi, [rsp+78h+NewContext]
0x140054310  call    cs:__imp_PsGetCurrentProcessId
0x140054317  nop     dword ptr [rax+rax+00h]
0x14005431c  mov     [rdi+18h], rax
0x140054320  mov     rdi, [rsp+78h+NewContext]
0x140054325  call    cs:__imp_IoGetCurrentProcess
0x14005432c  nop     dword ptr [rax+rax+00h]
0x140054331  mov     rcx, rax; Process
0x140054334  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14005433b  nop     dword ptr [rax+rax+00h]
0x140054340  mov     [rdi+20h], rax
0x140054344  mov     rax, [rsp+78h+NewContext]
0x140054349  add     rax, 30h ; '0'
0x14005434d  mov     [rax+8], rax
0x140054351  mov     [rax], rax
0x140054354  mov     rcx, [rsp+78h+NewContext]
0x140054359  add     rcx, 40h ; '@'; PushLock
0x14005435d  call    cs:__imp_FltInitializePushLock
0x140054364  nop     dword ptr [rax+rax+00h]
0x140054369  mov     rcx, [rsp+78h+NewContext]
0x14005436e  add     rcx, 48h ; 'H'; PushLock
0x140054372  call    cs:__imp_FltInitializePushLock
0x140054379  nop     dword ptr [rax+rax+00h]
0x14005437e  mov     rax, [rsp+78h+NewContext]
0x140054383  mov     [rax+60h], r15
0x140054387  mov     rax, [rsp+78h+NewContext]
0x14005438c  mov     [rax+68h], r15
0x140054390  lea     rax, [rsp+78h+OldContext]
0x140054395  mov     [rsp+78h+ReturnedContext], rax; OldContext
0x14005439a  mov     r9, [rsp+78h+NewContext]; NewContext
0x14005439f  mov     r8d, 1; Operation
0x1400543a5  mov     rdx, [rsi+20h]; FileObject
0x1400543a9  mov     rcx, [rsi+18h]; Instance
0x1400543ad  call    cs:__imp_FltSetStreamHandleContext
0x1400543b4  nop     dword ptr [rax+rax+00h]
0x1400543b9  mov     edi, eax
0x1400543bb  mov     [rsp+78h+var_48], eax
0x1400543bf  test    eax, eax
0x1400543c1  js      short loc_140054403
0x1400543c3  mov     rax, [rsp+78h+NewContext]
0x1400543c8  mov     [r14], rax
0x1400543cb  mov     [rsp+78h+NewContext], r15
0x1400543d0  jmp     loc_140054455
0x1400543d5  mov     edx, 34h ; '4'
0x1400543da  lfence
0x1400543dd  mov     r9, gs:188h
0x1400543e6  mov     dword ptr [rsp+78h+ReturnedContext], edi
0x1400543ea  lea     r8, WPP_49dcc05efb723005c5388b24d04d6cac_Traceguids
0x1400543f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400543f8  mov     rcx, [rcx+18h]
0x1400543fc  call    WPP_SF_qD
0x140054401  jmp     short loc_140054455
0x140054403  mov     rcx, [rsp+78h+NewContext]; Context
0x140054408  call    cs:__imp_FltReleaseContext
0x14005440f  nop     dword ptr [rax+rax+00h]
0x140054414  mov     [rsp+78h+NewContext], r15
0x140054419  cmp     edi, 0C01C0002h
0x14005441f  jz      short loc_14005443D
0x140054421  lea     rax, WPP_GLOBAL_Control
0x140054428  mov     rcx, cs:WPP_GLOBAL_Control
0x14005442f  cmp     rcx, rax
0x140054432  jz      short loc_140054455
0x140054434  mov     eax, [rcx+2Ch]
0x140054437  test    al, 1
0x140054439  jz      short loc_140054455
0x14005443b  jmp     short loc_1400543D5
0x14005443d  mov     rax, [rsp+78h+OldContext]
0x140054442  mov     [r14], rax
0x140054445  test    rbx, rbx
0x140054448  jz      short loc_14005444D
0x14005444a  mov     byte ptr [rbx], 1
0x14005444d  mov     edi, r15d
0x140054450  mov     [rsp+78h+var_48], r15d
0x140054455  mov     rcx, [rsp+78h+NewContext]; Context
0x14005445a  test    rcx, rcx
0x14005445d  jnz     short loc_140054484
0x14005445f  mov     eax, edi
0x140054461  mov     rcx, [rsp+78h+var_30]
0x140054466  xor     rcx, rsp; StackCookie
0x140054469  call    __security_check_cookie
0x14005446e  mov     rbx, [rsp+78h+arg_18]
0x140054476  add     rsp, 50h
0x14005447a  pop     r15
0x14005447c  pop     r14
0x14005447e  pop     r12
0x140054480  pop     rdi
0x140054481  pop     rsi
0x140054482  retn
0x140054484  call    cs:__imp_FltReleaseContext
0x14005448b  nop     dword ptr [rax+rax+00h]
0x140054490  jmp     short loc_14005445F
0x14008ca50  push    rbp
0x14008ca52  sub     rsp, 30h
0x14008ca56  mov     rbp, rdx
0x14008ca59  mov     rcx, [rbp+38h]; Context
0x14008ca5d  test    rcx, rcx
0x14008ca60  jz      short loc_14008CA6F
0x14008ca62  call    cs:__imp_FltReleaseContext
0x14008ca69  nop     dword ptr [rax+rax+00h]
0x14008ca6e  nop
0x14008ca6f  add     rsp, 30h
0x14008ca73  pop     rbp
0x14008ca74  retn
```
