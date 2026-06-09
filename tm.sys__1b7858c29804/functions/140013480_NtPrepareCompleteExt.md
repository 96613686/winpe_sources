# NtPrepareCompleteExt

- ea: `0x140013480`
- end: `0x1400135ae`
- name: `NtPrepareCompleteExt`
- size: `302`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1fc`
- `0x140013480`
- `0x14001a000`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013597`
- `ntoskrnl!ObfDereferenceObject` at `0x140013597`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400134fb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400134fb`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022121`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022121`

## pseudocode

```c
NTSTATUS __stdcall NtPrepareCompleteExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  KPROCESSOR_MODE v3; // bl
  int v4; // esi
  PVOID v5; // rbx
  __int64 ULong64FromUser; // [rsp+48h] [rbp-40h] BYREF
  PVOID Object; // [rsp+50h] [rbp-38h] BYREF
  __int64 v9[6]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v10; // [rsp+98h] [rbp+10h] BYREF
  __int64 v11; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+20h] BYREF

  ULong64FromUser = 0;
  v3 = *((_BYTE *)KeGetCurrentThread() + 562);
  if ( v3 && TmVirtualClock )
  {
    ULong64FromUser = RtlReadULong64FromUser(TmVirtualClock);
    v9[1] = (__int64)&ULong64FromUser;
  }
  Object = 0;
  v4 = ObReferenceObjectByHandle(EnlistmentHandle, 8u, (POBJECT_TYPE)TmEnlistmentObjectType, v3, &Object, 0);
  if ( v4 >= 0 )
  {
    v5 = Object;
    LODWORD(v12) = 258;
    LODWORD(v11) = 2;
    v9[0] = (__int64)TmpTxActionDoPrepareComplete;
    LODWORD(v10) = 0;
    v4 = TmpProcessNotificationResponse(Object, (__int64)&v12, (__int64)&v11, (__int64)v9, (__int64)&v10);
    ObfDereferenceObject(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x140013480  push    rbx
0x140013482  push    rsi
0x140013483  push    rdi
0x140013484  sub     rsp, 70h
0x140013488  mov     rdi, rdx
0x14001348b  mov     rsi, rcx
0x14001348e  mov     [rsp+88h+var_40], 0
0x140013497  mov     rax, gs:188h
0x1400134a0  mov     bl, [rax+232h]
0x1400134a6  test    bl, bl
0x1400134a8  jz      short loc_1400134CD
0x1400134aa  test    rdx, rdx
0x1400134ad  jz      short loc_1400134C6
0x1400134af  mov     rcx, rdx
0x1400134b2  call    RtlReadULong64FromUser
0x1400134b7  mov     [rsp+88h+var_40], rax
0x1400134bc  lea     rdi, [rsp+88h+var_40]
0x1400134c1  mov     [rsp+88h+var_28], rdi
0x1400134c6  jmp     short loc_1400134CD
0x1400134c8  jmp     loc_1400135A5
0x1400134cd  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x1400134d4  mov     [rsp+88h+var_38], 0
0x1400134dd  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x1400134e6  lea     rax, [rsp+88h+var_38]
0x1400134eb  mov     [rsp+88h+Object], rax; Object
0x1400134f0  mov     r9b, bl; AccessMode
0x1400134f3  mov     edx, 8; DesiredAccess
0x1400134f8  mov     rcx, rsi; Handle
0x1400134fb  call    cs:__imp_ObReferenceObjectByHandle
0x140013502  nop     dword ptr [rax+rax+00h]
0x140013507  mov     esi, eax
0x140013509  test    eax, eax
0x14001350b  js      loc_1400135A3
0x140013511  mov     rbx, [rsp+88h+var_38]
0x140013516  mov     [rsp+88h+var_48], 101h
0x14001351e  mov     dword ptr [rsp+88h+arg_18], 102h
0x140013529  mov     dword ptr [rsp+88h+arg_10], 2
0x140013534  lea     rax, TmpTxActionDoPrepareComplete
0x14001353b  mov     [rsp+88h+var_30], rax
0x140013540  mov     dword ptr [rsp+88h+arg_8], 0
0x14001354b  lea     rax, [rsp+88h+arg_8]
0x140013553  mov     [rsp+88h+var_50], rax; __int64
0x140013558  lea     rax, [rsp+88h+var_30]
0x14001355d  mov     [rsp+88h+var_58], rax; __int64
0x140013562  lea     rax, [rsp+88h+arg_10]
0x14001356a  mov     [rsp+88h+HandleInformation], rax; __int64
0x14001356f  lea     rax, [rsp+88h+arg_18]
0x140013577  mov     [rsp+88h+Object], rax; __int64
0x14001357c  lea     r9, [rsp+88h+var_48]
0x140013581  mov     r8d, 1
0x140013587  mov     rdx, rdi
0x14001358a  mov     rcx, rbx; Object
0x14001358d  call    TmpProcessNotificationResponse
0x140013592  mov     esi, eax
0x140013594  mov     rcx, rbx; Object
0x140013597  call    cs:__imp_ObfDereferenceObject
0x14001359e  nop     dword ptr [rax+rax+00h]
0x1400135a3  mov     eax, esi
0x1400135a5  add     rsp, 70h
0x1400135a9  pop     rdi
0x1400135aa  pop     rsi
0x1400135ab  pop     rbx
0x1400135ac  retn
0x140022118  push    rbp
0x14002211a  sub     rsp, 40h
0x14002211e  mov     rbp, rdx
0x140022121  call    cs:__imp_ExSystemExceptionFilter
0x140022128  nop     dword ptr [rax+rax+00h]
0x14002212d  nop
0x14002212e  add     rsp, 40h
0x140022132  pop     rbp
0x140022133  retn
```
