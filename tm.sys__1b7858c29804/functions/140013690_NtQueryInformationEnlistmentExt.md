# NtQueryInformationEnlistmentExt

- ea: `0x140013690`
- end: `0x140013947`
- name: `NtQueryInformationEnlistmentExt`
- size: `695`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass, PVOID EnlistmentInformation, ULONG EnlistmentInformationLength, PULONG ReturnLength)`
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
- `0x140013690`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400137af`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400137af`
- `ntoskrnl!KeReleaseMutex` at `0x140013901`
- `ntoskrnl!KeReleaseMutex` at `0x140013901`
- `ntoskrnl!ObfDereferenceObject` at `0x140013910`
- `ntoskrnl!ObfDereferenceObject` at `0x140013910`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013775`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140013775`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022144`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022161`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002217e`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002219b`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022144`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022161`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002217e`
- `ntoskrnl!ExSystemExceptionFilter` at `0x14002219b`
- `ntoskrnl!ProbeForWrite` at `0x14001371d`
- `ntoskrnl!ProbeForWrite` at `0x14001371d`

## pseudocode

```c
NTSTATUS __stdcall NtQueryInformationEnlistmentExt(
        HANDLE EnlistmentHandle,
        ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass,
        PVOID EnlistmentInformation,
        ULONG EnlistmentInformationLength,
        PULONG ReturnLength)
{
  KPROCESSOR_MODE v9; // r13
  unsigned int ULongFromUser; // eax
  int v11; // esi
  char *v12; // rbx
  __int32 v13; // r15d
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm2
  PVOID Object; // [rsp+40h] [rbp-78h] BYREF
  PRKMUTEX Mutex; // [rsp+48h] [rbp-70h]
  __int128 Src; // [rsp+50h] [rbp-68h] BYREF
  __int128 v21; // [rsp+60h] [rbp-58h]
  __int128 v22; // [rsp+70h] [rbp-48h]

  if ( (unsigned int)EnlistmentInformationClass > EnlistmentCrmInformation )
    return -1073741821;
  if ( EnlistmentInformationClass == EnlistmentBasicInformation && EnlistmentInformationLength != 48
    || EnlistmentInformationClass == EnlistmentCrmInformation && EnlistmentInformationLength != 48 )
  {
    return -1073741820;
  }
  v9 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v9 )
  {
    ProbeForWrite(EnlistmentInformation, EnlistmentInformationLength, 4u);
    if ( ReturnLength )
    {
      ULongFromUser = RtlReadULongFromUser(ReturnLength);
      RtlWriteULongToUser(ReturnLength, ULongFromUser);
    }
  }
  Object = 0;
  v11 = ObReferenceObjectByHandle(EnlistmentHandle, 1u, (POBJECT_TYPE)TmEnlistmentObjectType, v9, &Object, 0);
  if ( v11 >= 0 )
  {
    v12 = (char *)Object;
    Mutex = (PRKMUTEX)((char *)Object + 64);
    KeWaitForSingleObject((char *)Object + 64, Executive, 0, 0, 0);
    if ( EnlistmentInformationClass )
    {
      v13 = EnlistmentInformationClass - 1;
      if ( v13 )
      {
        if ( v13 == 1 )
        {
          v14 = 0;
          v15 = 0;
          v16 = 0;
          if ( (*((_DWORD *)v12 + 43) & 0x20) != 0 )
          {
            v14 = *(_OWORD *)(v12 + 280);
            v15 = *(_OWORD *)(v12 + 296);
            v16 = *(_OWORD *)(v12 + 264);
          }
          *(_OWORD *)EnlistmentInformation = v14;
          *((_OWORD *)EnlistmentInformation + 1) = v15;
          *((_OWORD *)EnlistmentInformation + 2) = v16;
          if ( ReturnLength )
            *ReturnLength = 48;
        }
      }
      else
      {
        if ( EnlistmentInformationLength >= *((_DWORD *)v12 + 52) )
          memmove(EnlistmentInformation, *((const void **)v12 + 25), *((unsigned int *)v12 + 52));
        else
          v11 = -1073741789;
        if ( ReturnLength )
          *ReturnLength = *((_DWORD *)v12 + 52);
      }
    }
    else
    {
      v21 = 0;
      v22 = 0;
      Src = *((_OWORD *)v12 + 3);
      v21 = *(_OWORD *)(*((_QWORD *)v12 + 20) + 176LL);
      v22 = *(_OWORD *)(*((_QWORD *)v12 + 19) + 136LL);
      if ( v9 )
        RtlCopyToUser(EnlistmentInformation, &Src, 0x30u);
      else
        RtlCopyVolatileMemory(EnlistmentInformation, &Src, 0x30u);
      if ( ReturnLength )
      {
        if ( v9 )
          RtlWriteULongToUser(ReturnLength, 48);
        else
          *ReturnLength = 48;
      }
    }
    KeReleaseMutex(Mutex, 0);
    ObfDereferenceObject(v12);
  }
  return v11;
}

```

## disassembly

```asm
0x140013690  mov     [rsp+arg_8], rbx
0x140013695  push    rsi
0x140013696  push    rdi
0x140013697  push    r12
0x140013699  push    r13
0x14001369b  push    r15
0x14001369d  sub     rsp, 90h
0x1400136a4  mov     rax, cs:__security_cookie
0x1400136ab  xor     rax, rsp
0x1400136ae  mov     [rsp+0B8h+var_38], rax
0x1400136b6  mov     [rsp+0B8h+var_88], r9d
0x1400136bb  mov     r12, r8
0x1400136be  mov     r15d, edx
0x1400136c1  mov     rbx, rcx
0x1400136c4  mov     rdi, [rsp+0B8h+ReturnLength]
0x1400136cc  cmp     edx, 2
0x1400136cf  jbe     short loc_1400136DB
0x1400136d1  mov     eax, 0C0000003h
0x1400136d6  jmp     loc_14001391E
0x1400136db  test    r15d, r15d
0x1400136de  jnz     short loc_1400136E6
0x1400136e0  cmp     r9d, 30h ; '0'
0x1400136e4  jnz     short loc_1400136F2
0x1400136e6  cmp     r15d, 2
0x1400136ea  jnz     short loc_1400136FC
0x1400136ec  cmp     r9d, 30h ; '0'
0x1400136f0  jz      short loc_1400136FC
0x1400136f2  mov     eax, 0C0000004h
0x1400136f7  jmp     loc_14001391E
0x1400136fc  mov     rax, gs:188h
0x140013705  mov     r13b, [rax+232h]
0x14001370c  test    r13b, r13b
0x14001370f  jz      short loc_140013747
0x140013711  mov     edx, r9d; Length
0x140013714  mov     r8d, 4; Alignment
0x14001371a  mov     rcx, r12; Address
0x14001371d  call    cs:__imp_ProbeForWrite
0x140013724  nop     dword ptr [rax+rax+00h]
0x140013729  test    rdi, rdi
0x14001372c  jz      short loc_140013740
0x14001372e  mov     rcx, rdi
0x140013731  call    RtlReadULongFromUser
0x140013736  mov     edx, eax
0x140013738  mov     rcx, rdi
0x14001373b  call    RtlWriteULongToUser
0x140013740  jmp     short loc_140013747
0x140013742  jmp     loc_14001391E
0x140013747  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x14001374e  mov     [rsp+0B8h+var_78], 0
0x140013757  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x140013760  lea     rax, [rsp+0B8h+var_78]
0x140013765  mov     [rsp+0B8h+Object], rax; Object
0x14001376a  mov     r9b, r13b; AccessMode
0x14001376d  mov     edx, 1; DesiredAccess
0x140013772  mov     rcx, rbx; Handle
0x140013775  call    cs:__imp_ObReferenceObjectByHandle
0x14001377c  nop     dword ptr [rax+rax+00h]
0x140013781  mov     esi, eax
0x140013783  test    eax, eax
0x140013785  js      loc_14001391C
0x14001378b  mov     rbx, [rsp+0B8h+var_78]
0x140013790  mov     [rsp+0B8h+var_80], rbx
0x140013795  lea     rcx, [rbx+40h]; Object
0x140013799  mov     [rsp+0B8h+Mutex], rcx
0x14001379e  mov     [rsp+0B8h+Object], 0; Timeout
0x1400137a7  xor     r9d, r9d; Alertable
0x1400137aa  xor     r8d, r8d; WaitMode
0x1400137ad  xor     edx, edx; WaitReason
0x1400137af  call    cs:__imp_KeWaitForSingleObject
0x1400137b6  nop     dword ptr [rax+rax+00h]
0x1400137bb  test    r15d, r15d
0x1400137be  jz      loc_140013874
0x1400137c4  sub     r15d, 1
0x1400137c8  jz      short loc_140013829
0x1400137ca  cmp     r15d, 1
0x1400137ce  jnz     loc_1400138FA
0x1400137d4  xorps   xmm0, xmm0
0x1400137d7  xorps   xmm1, xmm1
0x1400137da  xorps   xmm2, xmm2
0x1400137dd  mov     eax, [rbx+0ACh]
0x1400137e3  test    al, 20h
0x1400137e5  jz      short loc_1400137FC
0x1400137e7  movups  xmm0, xmmword ptr [rbx+118h]
0x1400137ee  movups  xmm1, xmmword ptr [rbx+128h]
0x1400137f5  movups  xmm2, xmmword ptr [rbx+108h]
0x1400137fc  movups  xmmword ptr [r12], xmm0
0x140013801  movups  xmmword ptr [r12+10h], xmm1
0x140013807  movups  xmmword ptr [r12+20h], xmm2
0x14001380d  test    rdi, rdi
0x140013810  jz      short loc_140013818
0x140013812  mov     dword ptr [rdi], 30h ; '0'
0x140013818  jmp     loc_1400138FA
0x14001381d  mov     esi, eax
0x14001381f  mov     rbx, [rsp+0B8h+var_80]
0x140013824  jmp     loc_1400138FA
0x140013829  mov     eax, [rbx+0D0h]
0x14001382f  cmp     [rsp+0B8h+var_88], eax
0x140013833  jnb     short loc_140013840
0x140013835  mov     esi, 0C0000023h
0x14001383a  mov     [rsp+0B8h+var_84], esi
0x14001383e  jmp     short loc_140013852
0x140013840  mov     r8, rax; Size
0x140013843  mov     rdx, [rbx+0C8h]; Src
0x14001384a  mov     rcx, r12; void *
0x14001384d  call    memmove
0x140013852  test    rdi, rdi
0x140013855  jz      short loc_14001385F
0x140013857  mov     eax, [rbx+0D0h]
0x14001385d  mov     [rdi], eax
0x14001385f  jmp     loc_1400138FA
0x140013864  mov     esi, eax
0x140013866  mov     [rsp+0B8h+var_84], eax
0x14001386a  mov     rbx, [rsp+0B8h+var_80]
0x14001386f  jmp     loc_1400138FA
0x140013874  xorps   xmm0, xmm0
0x140013877  movups  [rsp+0B8h+var_58], xmm0
0x14001387c  movups  [rsp+0B8h+var_48], xmm0
0x140013881  movups  xmm0, xmmword ptr [rbx+30h]
0x140013885  movdqu  [rsp+0B8h+Src], xmm0
0x14001388b  mov     rax, [rbx+0A0h]
0x140013892  movups  xmm1, xmmword ptr [rax+0B0h]
0x140013899  movdqu  [rsp+0B8h+var_58], xmm1
0x14001389f  mov     rax, [rbx+98h]
0x1400138a6  movups  xmm0, xmmword ptr [rax+88h]
0x1400138ad  movdqu  [rsp+0B8h+var_48], xmm0
0x1400138b3  mov     r8d, 30h ; '0'; Size
0x1400138b9  lea     rdx, [rsp+0B8h+Src]; Src
0x1400138be  mov     rcx, r12; void *
0x1400138c1  test    r13b, r13b
0x1400138c4  jz      short loc_1400138CD
0x1400138c6  call    RtlCopyToUser
0x1400138cb  jmp     short loc_1400138D2
0x1400138cd  call    RtlCopyVolatileMemory
0x1400138d2  test    rdi, rdi
0x1400138d5  jz      short loc_1400138F1
0x1400138d7  test    r13b, r13b
0x1400138da  jz      short loc_1400138EB
0x1400138dc  mov     edx, 30h ; '0'
0x1400138e1  mov     rcx, rdi
0x1400138e4  call    RtlWriteULongToUser
0x1400138e9  jmp     short loc_1400138F1
0x1400138eb  mov     dword ptr [rdi], 30h ; '0'
0x1400138f1  jmp     short loc_1400138FA
0x1400138f3  mov     esi, eax
0x1400138f5  mov     rbx, [rsp+0B8h+var_80]
0x1400138fa  xor     edx, edx; Wait
0x1400138fc  mov     rcx, [rsp+0B8h+Mutex]; Mutex
0x140013901  call    cs:__imp_KeReleaseMutex
0x140013908  nop     dword ptr [rax+rax+00h]
0x14001390d  mov     rcx, rbx; Object
0x140013910  call    cs:__imp_ObfDereferenceObject
0x140013917  nop     dword ptr [rax+rax+00h]
0x14001391c  mov     eax, esi
0x14001391e  mov     rcx, [rsp+0B8h+var_38]
0x140013926  xor     rcx, rsp; StackCookie
0x140013929  call    __security_check_cookie
0x14001392e  mov     rbx, [rsp+0B8h+arg_8]
0x140013936  add     rsp, 90h
0x14001393d  pop     r15
0x14001393f  pop     r13
0x140013941  pop     r12
0x140013943  pop     rdi
0x140013944  pop     rsi
0x140013945  retn
0x14002213b  push    rbp
0x14002213d  sub     rsp, 30h
0x140022141  mov     rbp, rdx
0x140022144  call    cs:__imp_ExSystemExceptionFilter
0x14002214b  nop     dword ptr [rax+rax+00h]
0x140022150  nop
0x140022151  add     rsp, 30h
0x140022155  pop     rbp
0x140022156  retn
0x140022158  push    rbp
0x14002215a  sub     rsp, 30h
0x14002215e  mov     rbp, rdx
0x140022161  call    cs:__imp_ExSystemExceptionFilter
0x140022168  nop     dword ptr [rax+rax+00h]
0x14002216d  nop
0x14002216e  add     rsp, 30h
0x140022172  pop     rbp
0x140022173  retn
0x140022175  push    rbp
0x140022177  sub     rsp, 30h
0x14002217b  mov     rbp, rdx
0x14002217e  call    cs:__imp_ExSystemExceptionFilter
0x140022185  nop     dword ptr [rax+rax+00h]
0x14002218a  nop
0x14002218b  add     rsp, 30h
0x14002218f  pop     rbp
0x140022190  retn
0x140022192  push    rbp
0x140022194  sub     rsp, 30h
0x140022198  mov     rbp, rdx
0x14002219b  call    cs:__imp_ExSystemExceptionFilter
0x1400221a2  nop     dword ptr [rax+rax+00h]
0x1400221a7  nop
0x1400221a8  add     rsp, 30h
0x1400221ac  pop     rbp
0x1400221ad  retn
```
