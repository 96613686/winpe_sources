# NtPrePrepareCompleteExt

- ea: `0x140013270`
- end: `0x14001339e`
- name: `NtPrePrepareCompleteExt`
- size: `302`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1fc`
- `0x140013270`
- `0x14001a000`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013387`
- `ntoskrnl!ObfDereferenceObject` at `0x140013387`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400132eb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400132eb`

## pseudocode

```c
NTSTATUS __stdcall NtPrePrepareCompleteExt(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
    LODWORD(v12) = 273;
    LODWORD(v11) = 8;
    v9[0] = (__int64)TmpTxActionDoPrePrepareComplete;
    LODWORD(v10) = 2;
    v4 = TmpProcessNotificationResponse(Object, (__int64)&v12, (__int64)&v11, (__int64)v9, (__int64)&v10);
    ObfDereferenceObject(v5);
  }
  return v4;
}

```

## disassembly

```asm
0x140013270  push    rbx
0x140013272  push    rsi
0x140013273  push    rdi
0x140013274  sub     rsp, 70h
0x140013278  mov     rdi, rdx
0x14001327b  mov     rsi, rcx
0x14001327e  mov     [rsp+88h+var_40], 0
0x140013287  mov     rax, gs:188h
0x140013290  mov     bl, [rax+232h]
0x140013296  test    bl, bl
0x140013298  jz      short loc_1400132BD
0x14001329a  test    rdx, rdx
0x14001329d  jz      short loc_1400132B6
0x14001329f  mov     rcx, rdx
0x1400132a2  call    RtlReadULong64FromUser
0x1400132a7  mov     [rsp+88h+var_40], rax
0x1400132ac  lea     rdi, [rsp+88h+var_40]
0x1400132b1  mov     [rsp+88h+var_28], rdi
0x1400132b6  jmp     short loc_1400132BD
0x1400132b8  jmp     loc_140013395
0x1400132bd  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x1400132c4  mov     [rsp+88h+var_38], 0
0x1400132cd  mov     [rsp+88h+HandleInformation], 0; HandleInformation
0x1400132d6  lea     rax, [rsp+88h+var_38]
0x1400132db  mov     [rsp+88h+Object], rax; Object
0x1400132e0  mov     r9b, bl; AccessMode
0x1400132e3  mov     edx, 8; DesiredAccess
0x1400132e8  mov     rcx, rsi; Handle
0x1400132eb  call    cs:__imp_ObReferenceObjectByHandle
0x1400132f2  nop     dword ptr [rax+rax+00h]
0x1400132f7  mov     esi, eax
0x1400132f9  test    eax, eax
0x1400132fb  js      loc_140013393
0x140013301  mov     rbx, [rsp+88h+var_38]
0x140013306  mov     [rsp+88h+var_48], 10Ah
0x14001330e  mov     dword ptr [rsp+88h+arg_18], 111h
0x140013319  mov     dword ptr [rsp+88h+arg_10], 8
0x140013324  lea     rax, TmpTxActionDoPrePrepareComplete
0x14001332b  mov     [rsp+88h+var_30], rax
0x140013330  mov     dword ptr [rsp+88h+arg_8], 2
0x14001333b  lea     rax, [rsp+88h+arg_8]
0x140013343  mov     [rsp+88h+var_50], rax; __int64
0x140013348  lea     rax, [rsp+88h+var_30]
0x14001334d  mov     [rsp+88h+var_58], rax; __int64
0x140013352  lea     rax, [rsp+88h+arg_10]
0x14001335a  mov     [rsp+88h+HandleInformation], rax; __int64
0x14001335f  lea     rax, [rsp+88h+arg_18]
0x140013367  mov     [rsp+88h+Object], rax; __int64
0x14001336c  lea     r9, [rsp+88h+var_48]
0x140013371  mov     r8d, 1
0x140013377  mov     rdx, rdi
0x14001337a  mov     rcx, rbx; Object
0x14001337d  call    TmpProcessNotificationResponse
0x140013382  mov     esi, eax
0x140013384  mov     rcx, rbx; Object
0x140013387  call    cs:__imp_ObfDereferenceObject
0x14001338e  nop     dword ptr [rax+rax+00h]
0x140013393  mov     eax, esi
0x140013395  add     rsp, 70h
0x140013399  pop     rdi
0x14001339a  pop     rsi
0x14001339b  pop     rbx
0x14001339c  retn
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
