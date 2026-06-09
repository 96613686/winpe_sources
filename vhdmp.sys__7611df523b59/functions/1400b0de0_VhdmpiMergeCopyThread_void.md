# VhdmpiMergeCopyThread(void *)

- ea: `0x1400b0de0`
- end: `0x1400b0f5c`
- name: `?VhdmpiMergeCopyThread@@YAXPEAX@Z`
- size: `380`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14003204c`
- `0x1400b0de0`
- `0x1400e9444`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400b0f40`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400b0f40`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b0e0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b0e0d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b0f32`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400b0f32`
- `ntoskrnl!KeSetEvent` at `0x1400b0f11`
- `ntoskrnl!KeSetEvent` at `0x1400b0f11`

## pseudocode

```c
void __fastcall VhdmpiMergeCopyThread(char *StartContext)
{
  unsigned int *v1; // rdi
  unsigned __int64 v3; // r14
  unsigned __int64 v4; // rbx
  int v5; // r12d
  unsigned __int64 v6; // rcx
  signed __int32 v7; // r15d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rbx
  unsigned int v10; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v11; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int64 v12; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int64 v13; // [rsp+A8h] [rbp+58h] BYREF

  v1 = *(unsigned int **)StartContext;
  do
  {
    KeWaitForSingleObject(*((PVOID *)StartContext + 2), Executive, 0, 0, 0);
    v3 = *((_QWORD *)v1 + 9);
    v4 = *((_QWORD *)StartContext + 4);
    if ( v4 == v3 )
      break;
    v5 = 0;
    v6 = v4 + v1[14];
    v10 = 0;
    v7 = 0;
    v11 = 0;
    if ( v6 <= v3 )
      v3 = v6;
    while ( 1 )
    {
      v12 = v4;
      if ( v4 >= v3 )
        break;
      v8 = v3 - v4;
      if ( v3 - v4 > v1[15] )
        v8 = v1[15];
      v13 = v8;
      VhdmpiMergeGetNextCopyRange((struct VHD_INTERNAL_MERGE_CONTEXT *)v1, v3, &v12, &v13);
      if ( !v13 )
        break;
      v9 = v12;
      v7 = VhdmpiMergeIoSize(
             *(struct _VHD_VIRTUAL_DISK **)v1,
             *((struct _VHD_BACKING_STORE_HEADER **)v1 + 4),
             *((struct _VHD_BACKING_STORE_HEADER **)v1 + 5),
             (struct _VHD_INTERNAL_IO_CONTEXT *)(StartContext + 40),
             v12 + v13,
             v1[15],
             v12,
             &v10,
             &v11);
      if ( v7 >= 0 && v11 )
        *(_BYTE *)(*(_QWORD *)StartContext + 27LL) = 1;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)v1 + 92, v7, 0);
      if ( v5 < 0 || v7 < 0 )
        break;
      v4 = v10 + v9;
      v10 = 0;
      v11 = 0;
    }
    KeSetEvent(*((PRKEVENT *)StartContext + 3), 0, 0);
    if ( v5 < 0 )
      break;
  }
  while ( v7 >= 0 );
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)v1 + 47);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400b0de0  push    rbp
0x1400b0de2  push    rbx
0x1400b0de3  push    rsi
0x1400b0de4  push    rdi
0x1400b0de5  push    r12
0x1400b0de7  push    r14
0x1400b0de9  push    r15
0x1400b0deb  mov     rbp, rsp
0x1400b0dee  sub     rsp, 50h
0x1400b0df2  mov     rdi, [rcx]
0x1400b0df5  mov     rsi, rcx
0x1400b0df8  mov     rcx, [rsi+10h]; Object
0x1400b0dfc  xor     r9d, r9d; Alertable
0x1400b0dff  xor     r8d, r8d; WaitMode
0x1400b0e02  mov     [rsp+50h+Timeout], 0; Timeout
0x1400b0e0b  xor     edx, edx; WaitReason
0x1400b0e0d  call    cs:__imp_KeWaitForSingleObject
0x1400b0e14  nop     dword ptr [rax+rax+00h]
0x1400b0e19  mov     r14, [rdi+48h]
0x1400b0e1d  mov     rbx, [rsi+20h]
0x1400b0e21  cmp     rbx, r14
0x1400b0e24  jz      loc_1400B0F2B
0x1400b0e2a  mov     ecx, [rdi+38h]
0x1400b0e2d  xor     r12d, r12d
0x1400b0e30  add     rcx, rbx
0x1400b0e33  mov     [rbp+arg_0], r12d
0x1400b0e37  xor     r15d, r15d
0x1400b0e3a  mov     [rbp+arg_8], r12d
0x1400b0e3e  cmp     rcx, r14
0x1400b0e41  cmovbe  r14, rcx
0x1400b0e45  mov     [rbp+arg_10], rbx
0x1400b0e49  cmp     rbx, r14
0x1400b0e4c  jnb     loc_1400B0F08
0x1400b0e52  mov     eax, [rdi+3Ch]
0x1400b0e55  lea     r9, [rbp+arg_18]; unsigned __int64 *
0x1400b0e59  mov     rcx, r14
0x1400b0e5c  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x1400b0e60  sub     rcx, rbx
0x1400b0e63  mov     rdx, r14; unsigned __int64
0x1400b0e66  cmp     rcx, rax
0x1400b0e69  cmova   rcx, rax
0x1400b0e6d  mov     [rbp+arg_18], rcx
0x1400b0e71  mov     rcx, rdi; struct VHD_INTERNAL_MERGE_CONTEXT *
0x1400b0e74  call    ?VhdmpiMergeGetNextCopyRange@@YAXPEAUVHD_INTERNAL_MERGE_CONTEXT@@_KPEA_K2@Z; VhdmpiMergeGetNextCopyRange(VHD_INTERNAL_MERGE_CONTEXT *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1400b0e79  mov     rcx, [rbp+arg_18]
0x1400b0e7d  test    rcx, rcx
0x1400b0e80  jz      loc_1400B0F08
0x1400b0e86  mov     rbx, [rbp+arg_10]
0x1400b0e8a  lea     rax, [rbp+arg_8]
0x1400b0e8e  mov     r8, [rdi+28h]; struct _VHD_BACKING_STORE_HEADER *
0x1400b0e92  lea     r9, [rsi+28h]; struct _VHD_INTERNAL_IO_CONTEXT *
0x1400b0e96  mov     rdx, [rdi+20h]; struct _VHD_BACKING_STORE_HEADER *
0x1400b0e9a  add     rcx, rbx
0x1400b0e9d  mov     [rsp+50h+var_10], rax; unsigned int *
0x1400b0ea2  lea     rax, [rbp+arg_0]
0x1400b0ea6  mov     [rsp+50h+var_18], rax; unsigned int *
0x1400b0eab  mov     eax, [rdi+3Ch]
0x1400b0eae  mov     [rsp+50h+var_20], rbx; unsigned __int64
0x1400b0eb3  mov     [rsp+50h+var_28], eax; unsigned int
0x1400b0eb7  mov     [rsp+50h+Timeout], rcx; unsigned __int64
0x1400b0ebc  mov     rcx, [rdi]; struct _VHD_VIRTUAL_DISK *
0x1400b0ebf  call    ?VhdmpiMergeIoSize@@YAJPEAU_VHD_VIRTUAL_DISK@@PEAU_VHD_BACKING_STORE_HEADER@@1PEAU_VHD_INTERNAL_IO_CONTEXT@@_KK3PEAK4@Z; VhdmpiMergeIoSize(_VHD_VIRTUAL_DISK *,_VHD_BACKING_STORE_HEADER *,_VHD_BACKING_STORE_HEADER *,_VHD_INTERNAL_IO_CONTEXT *,unsigned __int64,ulong,unsigned __int64,ulong *,ulong *)
0x1400b0ec4  mov     r15d, eax
0x1400b0ec7  test    eax, eax
0x1400b0ec9  js      short loc_1400B0ED8
0x1400b0ecb  cmp     [rbp+arg_8], 0
0x1400b0ecf  jz      short loc_1400B0ED8
0x1400b0ed1  mov     rcx, [rsi]
0x1400b0ed4  mov     byte ptr [rcx+1Bh], 1
0x1400b0ed8  xor     eax, eax
0x1400b0eda  lock cmpxchg [rdi+170h], r15d
0x1400b0ee3  mov     r12d, eax
0x1400b0ee6  test    eax, eax
0x1400b0ee8  js      short loc_1400B0F08
0x1400b0eea  test    r15d, r15d
0x1400b0eed  js      short loc_1400B0F08
0x1400b0eef  mov     ecx, [rbp+arg_0]
0x1400b0ef2  add     rbx, rcx
0x1400b0ef5  mov     [rbp+arg_0], 0
0x1400b0efc  mov     [rbp+arg_8], 0
0x1400b0f03  jmp     loc_1400B0E45
0x1400b0f08  mov     rcx, [rsi+18h]; Event
0x1400b0f0c  xor     r8d, r8d; Wait
0x1400b0f0f  xor     edx, edx; Increment
0x1400b0f11  call    cs:__imp_KeSetEvent
0x1400b0f18  nop     dword ptr [rax+rax+00h]
0x1400b0f1d  test    r12d, r12d
0x1400b0f20  js      short loc_1400B0F2B
0x1400b0f22  test    r15d, r15d
0x1400b0f25  jns     loc_1400B0DF8
0x1400b0f2b  lea     rcx, [rdi+178h]; RunRef
0x1400b0f32  call    cs:__imp_ExReleaseRundownProtection
0x1400b0f39  nop     dword ptr [rax+rax+00h]
0x1400b0f3e  xor     ecx, ecx; ExitStatus
0x1400b0f40  call    cs:__imp_PsTerminateSystemThread
0x1400b0f47  nop     dword ptr [rax+rax+00h]
0x1400b0f4c  add     rsp, 50h
0x1400b0f50  pop     r15
0x1400b0f52  pop     r14
0x1400b0f54  pop     r12
0x1400b0f56  pop     rdi
0x1400b0f57  pop     rsi
0x1400b0f58  pop     rbx
0x1400b0f59  pop     rbp
0x1400b0f5a  retn
```
