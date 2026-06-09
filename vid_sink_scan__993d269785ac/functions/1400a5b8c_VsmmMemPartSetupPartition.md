# VsmmMemPartSetupPartition

- ea: `0x1400a5b8c`
- end: `0x1400a6260`
- name: `VsmmMemPartSetupPartition`
- size: `1748`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x14008d084`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400217a0`
- `0x1400a5938`
- `0x1400a5b8c`
- `0x1400bc520`
- `0x1400fbd7c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a5c17`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a5e6b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a5c17`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a5e6b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5d4e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5d78`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5dae`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5d4e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5d78`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a5dae`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a5edc`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a623a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a5edc`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a623a`
- `ntoskrnl!PsProcessType` at `0x1400a5ebe`
- `ntoskrnl!PsJobType` at `0x1400a5bf0`
- `ntoskrnl!PsPartitionType` at `0x1400a5e40`
- `ntoskrnl!PsPartitionType` at `0x1400a621b`
- `ntoskrnl!ZwClose` at `0x1400a5d38`
- `ntoskrnl!ZwClose` at `0x1400a5d64`
- `ntoskrnl!ZwClose` at `0x1400a5d38`
- `ntoskrnl!ZwClose` at `0x1400a5d64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5d9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5d9a`
- `ntoskrnl!ExAllocatePool2` at `0x1400a5fb6`
- `ntoskrnl!ExAllocatePool2` at `0x1400a5fb6`
- `ntoskrnl!ObfReferenceObject` at `0x1400a5f67`
- `ntoskrnl!ObfReferenceObject` at `0x1400a5f67`
- `ntoskrnl!ObQueryNameString` at `0x1400a5f8a`
- `ntoskrnl!ObQueryNameString` at `0x1400a6049`
- `ntoskrnl!ObQueryNameString` at `0x1400a5f8a`
- `ntoskrnl!ObQueryNameString` at `0x1400a6049`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a60e8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a6116`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a60e8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a6116`

## pseudocode

```c
__int64 __fastcall VsmmMemPartSetupPartition(__int64 a1, void *a2)
{
  _OBJECT_NAME_INFORMATION *p_ObjectNameInfo; // r14
  PVOID v4; // rsi
  int v5; // r12d
  NTSTATUS v6; // ebx
  PVOID *v7; // rax
  PVOID *v8; // rcx
  __int16 *v9; // rdx
  PVOID v10; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  NTSTATUS v15; // eax
  __int64 v16; // rax
  struct _OBJECT_NAME_INFORMATION *Pool2; // rax
  unsigned int v18; // ebx
  const UNICODE_STRING *MemPartName; // rax
  const UNICODE_STRING *v20; // rax
  int Object; // [rsp+20h] [rbp-E0h]
  PVOID v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ReturnLength; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v27; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  PVOID v29; // [rsp+70h] [rbp-90h] BYREF
  PVOID v30; // [rsp+78h] [rbp-88h] BYREF
  char v31[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[16]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  PVOID *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  _DWORD *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  __int64 v42; // [rsp+100h] [rbp+0h]
  _DWORD v43[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  _DWORD *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  wchar_t *Buffer; // [rsp+130h] [rbp+30h]
  _DWORD v49[2]; // [rsp+138h] [rbp+38h] BYREF
  _OBJECT_NAME_INFORMATION ObjectNameInfo; // [rsp+140h] [rbp+40h] BYREF

  ReturnLength = 0;
  v27 = 0;
  p_ObjectNameInfo = 0;
  v29 = 0;
  v4 = 0;
  Handle = 0;
  v5 = 1;
  if ( !a2 )
  {
    v16 = *(_QWORD *)(a1 + 10272);
    v22 = 0;
    if ( !v16 || !*(_QWORD *)(v16 + 96) )
      goto LABEL_24;
    v4 = *(PVOID *)(v16 + 96);
    goto LABEL_37;
  }
  v30 = 0;
  v6 = ObReferenceObjectByHandle(a2, 5u, (POBJECT_TYPE)PsJobType, 1, &v30, 0);
  v22 = v30;
  if ( v6 >= 0 )
  {
    v4 = (PVOID)(*((__int64 (**)(void))VidDeviceExtension + 266))();
    if ( !v4 )
    {
LABEL_24:
      v12 = VsmmMemReserveMemPartGet(0);
      v13 = v12;
      if ( v12 )
      {
        v14 = *(_DWORD *)(v12 + 32);
        if ( (v14 & 0xFFFFFFFA) != 0 || v14 == 1 )
        {
LABEL_33:
          v10 = 0;
          *(_QWORD *)(a1 + 10360) = v13;
          v6 = 0;
          *(_QWORD *)(a1 + 10280) = v22;
          *(_DWORD *)(a1 + 10352) = v5;
          goto LABEL_9;
        }
      }
      v6 = VsmmMemPartOpenSystemMemoryPartition(&v27);
      if ( v6 < 0 )
        goto LABEL_8;
      v25 = 0;
      v15 = ObReferenceObjectByHandle(v27, 0x1F0003u, PsPartitionType, 0, &v25, 0);
      v4 = v25;
      v6 = v15;
      if ( v15 < 0 )
        goto LABEL_8;
      v5 = 0;
LABEL_30:
      v6 = (*((__int64 (__fastcall **)(PVOID, PVOID *))VidDeviceExtension + 267))(v4, &v29);
      if ( v6 < 0 )
        goto LABEL_8;
      v6 = ObOpenObjectByPointer(v29, 0x200u, 0, 2u, (POBJECT_TYPE)PsProcessType, 0, &Handle);
      if ( v6 < 0 )
        goto LABEL_8;
      v13 = (__int64)v4;
      *(_QWORD *)(a1 + 10368) = v27;
      v4 = 0;
      *(_QWORD *)(a1 + 10376) = Handle;
      v27 = 0;
      Handle = 0;
      goto LABEL_33;
    }
LABEL_37:
    ObfReferenceObject(v4);
    ReturnLength = 144;
    v6 = ObQueryNameString(v4, &ObjectNameInfo, 0x90u, &ReturnLength);
    if ( v6 == -1073741820 )
    {
      Pool2 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(256, ReturnLength, 1833788502);
      p_ObjectNameInfo = Pool2;
      if ( !Pool2 )
      {
        v6 = -1073741670;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_8;
        tlgCreate1Sz_char(v32, "VsmmMemPartSetupPartition");
        tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        LODWORD(v25) = 2291;
        v7 = &v25;
        v23 = -1073741670;
        v8 = (PVOID *)&v23;
        v9 = (__int16 *)&dword_14004BDFC;
        goto LABEL_6;
      }
      v6 = ObQueryNameString(v4, Pool2, ReturnLength, &ReturnLength);
    }
    else
    {
      p_ObjectNameInfo = &ObjectNameInfo;
    }
    if ( v6 >= 0 )
    {
      if ( p_ObjectNameInfo->Name.Buffer )
      {
        v18 = 0;
        while ( 1 )
        {
          MemPartName = (const UNICODE_STRING *)VsmmMemReserveGetMemPartName(v18);
          if ( RtlEqualUnicodeString(&p_ObjectNameInfo->Name, MemPartName, 1u) )
            break;
          if ( (int)++v18 >= 2 )
          {
            if ( v18 != 2 )
              goto LABEL_57;
            v20 = (const UNICODE_STRING *)VsmmMemReserveGetMemPartName(0xFFFFFFFFLL);
            if ( !RtlEqualUnicodeString(&p_ObjectNameInfo->Name, v20, 1u) )
              goto LABEL_57;
            break;
          }
        }
        v6 = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v32, "VsmmMemPartSetupPartition");
          tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
          LODWORD(v25) = 2350;
          v34 = &v25;
          v8 = (PVOID *)&v23;
          v23 = -1073741811;
          v38 = a1 + 656;
          v9 = (__int16 *)byte_14004BC9D;
          v47 = 2;
          v40 = v43;
          v42 = *(_QWORD *)(a1 + 128);
          v43[0] = *(unsigned __int16 *)(a1 + 120);
          v26 = *(_QWORD *)(a1 + 648);
          v44 = &v26;
          v46 = v49;
          Buffer = p_ObjectNameInfo->Name.Buffer;
          v49[0] = p_ObjectNameInfo->Name.Length;
          Object = 12;
          v49[1] = 0;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
LABEL_57:
      v6 = ObOpenObjectByPointer(v4, 0x200u, 0, 0x1F0003u, PsPartitionType, 0, &v27);
      if ( v6 < 0 )
        goto LABEL_8;
      v5 = 2;
      goto LABEL_30;
    }
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_8;
    tlgCreate1Sz_char(v32, "VsmmMemPartSetupPartition");
    tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    LODWORD(v25) = 2304;
    v7 = &v25;
    v23 = v6;
    v8 = (PVOID *)&v23;
    v9 = &word_14004BD8E;
LABEL_6:
    v34 = v7;
    v38 = a1 + 656;
    v40 = v43;
    v42 = *(_QWORD *)(a1 + 128);
    v43[0] = *(unsigned __int16 *)(a1 + 120);
    v26 = *(_QWORD *)(a1 + 648);
    v44 = &v26;
    Object = 10;
LABEL_7:
    v36 = v8;
    v37 = 4;
    v35 = 4;
    v45 = 8;
    v43[1] = 0;
    v41 = 2;
    v39 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v9, 0, 0, Object, v31);
    goto LABEL_8;
  }
  if ( (unsigned int)dword_140064110 > 2 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v32, "VsmmMemPartSetupPartition");
      tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
      v23 = 2223;
      v7 = (PVOID *)&v23;
      LODWORD(v25) = v6;
      v8 = &v25;
      v9 = (__int16 *)qword_14004BD20;
      goto LABEL_6;
    }
LABEL_8:
    v10 = v22;
    goto LABEL_9;
  }
  v10 = v30;
LABEL_9:
  if ( Handle )
    ZwClose(Handle);
  if ( v29 )
    ObfDereferenceObject(v29);
  if ( v27 )
    ZwClose(v27);
  if ( v4 )
    ObfDereferenceObject(v4);
  if ( p_ObjectNameInfo && p_ObjectNameInfo != &ObjectNameInfo )
    ExFreePoolWithTag(p_ObjectNameInfo, 0x6D4D6456u);
  if ( v10 )
    ObfDereferenceObject(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400a5b8c  mov     [rsp-8+arg_10], rbx
0x1400a5b91  push    rbp
0x1400a5b92  push    rsi
0x1400a5b93  push    rdi
0x1400a5b94  push    r12
0x1400a5b96  push    r13
0x1400a5b98  push    r14
0x1400a5b9a  push    r15
0x1400a5b9c  lea     rbp, [rsp-0E0h]
0x1400a5ba4  sub     rsp, 1E0h
0x1400a5bab  mov     rax, cs:__security_cookie
0x1400a5bb2  xor     rax, rsp
0x1400a5bb5  mov     [rbp+110h+var_40], rax
0x1400a5bbc  xor     r13d, r13d
0x1400a5bbf  mov     rax, rdx
0x1400a5bc2  mov     [rsp+210h+ReturnLength], r13d
0x1400a5bc7  mov     r15, rcx
0x1400a5bca  mov     [rsp+210h+var_1B0], r13
0x1400a5bcf  mov     r14d, r13d
0x1400a5bd2  mov     [rsp+210h+var_1A0], r13
0x1400a5bd7  mov     esi, r13d
0x1400a5bda  mov     [rsp+210h+Handle], r13
0x1400a5bdf  lea     edi, [r13+2]
0x1400a5be3  lea     r12d, [r13+1]
0x1400a5be7  test    rdx, rdx
0x1400a5bea  jz      loc_1400A5F3F
0x1400a5bf0  mov     r8, cs:PsJobType
0x1400a5bf7  lea     rcx, [rsp+210h+var_198]
0x1400a5bfc  mov     [rsp+210h+HandleInformation], r13; HandleInformation
0x1400a5c01  lea     edx, [rdi+3]; DesiredAccess
0x1400a5c04  mov     [rsp+210h+Object], rcx; Object
0x1400a5c09  mov     r9b, r12b; AccessMode
0x1400a5c0c  mov     rcx, rax; Handle
0x1400a5c0f  mov     [rsp+210h+var_198], r13
0x1400a5c14  mov     r8, [r8]; ObjectType
0x1400a5c17  call    cs:__imp_ObReferenceObjectByHandle
0x1400a5c1e  nop     dword ptr [rax+rax+00h]
0x1400a5c23  mov     rcx, [rsp+210h+var_198]
0x1400a5c28  mov     ebx, eax
0x1400a5c2a  mov     [rsp+210h+var_1D0], rcx
0x1400a5c2f  test    eax, eax
0x1400a5c31  jns     loc_1400A5DE7
0x1400a5c37  mov     eax, cs:dword_140064110
0x1400a5c3d  cmp     eax, edi
0x1400a5c3f  jbe     loc_1400A6258
0x1400a5c45  mov     edx, 100h
0x1400a5c4a  lea     rcx, dword_140064110
0x1400a5c51  call    _tlgKeywordOn
0x1400a5c56  test    al, al
0x1400a5c58  jz      loc_1400A5D29
0x1400a5c5e  lea     rdx, aVsmmmempartset; "VsmmMemPartSetupPartition"
0x1400a5c65  lea     rcx, [rbp+110h+var_170]
0x1400a5c69  call    _tlgCreate1Sz_char
0x1400a5c6e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a5c75  lea     rcx, [rbp+110h+var_160]
0x1400a5c79  call    _tlgCreate1Sz_char
0x1400a5c7e  mov     [rsp+210h+var_1C8], 8AFh
0x1400a5c86  lea     rax, [rsp+210h+var_1C8]
0x1400a5c8b  mov     dword ptr [rsp+210h+var_1C0], ebx
0x1400a5c8f  lea     rcx, [rsp+210h+var_1C0]
0x1400a5c94  lea     rdx, qword_14004BD20
0x1400a5c9b  mov     [rbp+110h+var_150], rax
0x1400a5c9f  lea     rax, [r15+290h]
0x1400a5ca6  mov     [rbp+110h+var_130], rax
0x1400a5caa  lea     rax, [rbp+110h+var_108]
0x1400a5cae  mov     [rbp+110h+var_120], rax
0x1400a5cb2  mov     rax, [r15+80h]
0x1400a5cb9  mov     [rbp+110h+var_110], rax
0x1400a5cbd  movzx   eax, word ptr [r15+78h]
0x1400a5cc2  mov     [rbp+110h+var_108], eax
0x1400a5cc5  mov     rax, [r15+288h]
0x1400a5ccc  mov     [rsp+210h+var_1B8], rax
0x1400a5cd1  lea     rax, [rsp+210h+var_1B8]
0x1400a5cd6  mov     [rbp+110h+var_100], rax
0x1400a5cda  lea     rax, [rbp+110h+var_190]
0x1400a5cde  mov     [rsp+210h+HandleInformation], rax
0x1400a5ce3  mov     dword ptr [rsp+210h+Object], 0Ah
0x1400a5ceb  mov     [rbp+110h+var_140], rcx
0x1400a5cef  xor     r9d, r9d
0x1400a5cf2  lea     rcx, dword_140064110
0x1400a5cf9  mov     [rbp+110h+var_138], 4
0x1400a5d01  xor     r8d, r8d
0x1400a5d04  mov     [rbp+110h+var_148], 4
0x1400a5d0c  mov     [rbp+110h+var_F8], 8
0x1400a5d14  mov     [rbp+110h+var_104], r13d
0x1400a5d18  mov     [rbp+110h+var_118], rdi
0x1400a5d1c  mov     [rbp+110h+var_128], 10h
0x1400a5d24  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a5d29  mov     rdi, [rsp+210h+var_1D0]
0x1400a5d2e  mov     rcx, [rsp+210h+Handle]; Handle
0x1400a5d33  test    rcx, rcx
0x1400a5d36  jz      short loc_1400A5D44
0x1400a5d38  call    cs:__imp_ZwClose
0x1400a5d3f  nop     dword ptr [rax+rax+00h]
0x1400a5d44  mov     rcx, [rsp+210h+var_1A0]; Object
0x1400a5d49  test    rcx, rcx
0x1400a5d4c  jz      short loc_1400A5D5A
0x1400a5d4e  call    cs:__imp_ObfDereferenceObject
0x1400a5d55  nop     dword ptr [rax+rax+00h]
0x1400a5d5a  mov     rcx, [rsp+210h+var_1B0]; Handle
0x1400a5d5f  test    rcx, rcx
0x1400a5d62  jz      short loc_1400A5D70
0x1400a5d64  call    cs:__imp_ZwClose
0x1400a5d6b  nop     dword ptr [rax+rax+00h]
0x1400a5d70  test    rsi, rsi
0x1400a5d73  jz      short loc_1400A5D84
0x1400a5d75  mov     rcx, rsi; Object
0x1400a5d78  call    cs:__imp_ObfDereferenceObject
0x1400a5d7f  nop     dword ptr [rax+rax+00h]
0x1400a5d84  test    r14, r14
0x1400a5d87  jz      short loc_1400A5DA6
0x1400a5d89  lea     rax, [rbp+110h+ObjectNameInfo]
0x1400a5d8d  cmp     r14, rax
0x1400a5d90  jz      short loc_1400A5DA6
0x1400a5d92  mov     edx, 6D4D6456h; Tag
0x1400a5d97  mov     rcx, r14; P
0x1400a5d9a  call    cs:__imp_ExFreePoolWithTag
0x1400a5da1  nop     dword ptr [rax+rax+00h]
0x1400a5da6  test    rdi, rdi
0x1400a5da9  jz      short loc_1400A5DBA
0x1400a5dab  mov     rcx, rdi; Object
0x1400a5dae  call    cs:__imp_ObfDereferenceObject
0x1400a5db5  nop     dword ptr [rax+rax+00h]
0x1400a5dba  mov     eax, ebx
0x1400a5dbc  mov     rcx, [rbp+110h+var_40]
0x1400a5dc3  xor     rcx, rsp; StackCookie
0x1400a5dc6  call    __security_check_cookie
0x1400a5dcb  mov     rbx, [rsp+210h+arg_10]
0x1400a5dd3  add     rsp, 1E0h
0x1400a5dda  pop     r15
0x1400a5ddc  pop     r14
0x1400a5dde  pop     r13
0x1400a5de0  pop     r12
0x1400a5de2  pop     rdi
0x1400a5de3  pop     rsi
0x1400a5de4  pop     rbp
0x1400a5de5  retn
0x1400a5de7  mov     rax, cs:VidDeviceExtension
0x1400a5dee  mov     rax, [rax+850h]
0x1400a5df5  call    _guard_dispatch_icall
0x1400a5dfa  mov     rsi, rax
0x1400a5dfd  test    rax, rax
0x1400a5e00  jnz     loc_1400A5F64
0x1400a5e06  xor     ecx, ecx
0x1400a5e08  call    VsmmMemReserveMemPartGet
0x1400a5e0d  mov     rcx, rax
0x1400a5e10  test    rax, rax
0x1400a5e13  jz      short loc_1400A5E2C
0x1400a5e15  mov     eax, [rax+20h]
0x1400a5e18  test    eax, 0FFFFFFFAh
0x1400a5e1d  jnz     loc_1400A5F1A
0x1400a5e23  cmp     eax, r12d
0x1400a5e26  jz      loc_1400A5F1A
0x1400a5e2c  lea     rcx, [rsp+210h+var_1B0]
0x1400a5e31  call    VsmmMemPartOpenSystemMemoryPartition
0x1400a5e36  mov     ebx, eax
0x1400a5e38  test    eax, eax
0x1400a5e3a  js      loc_1400A5D29
0x1400a5e40  mov     r8, cs:__imp_PsPartitionType
0x1400a5e47  lea     rax, [rsp+210h+var_1C0]
0x1400a5e4c  mov     rcx, [rsp+210h+var_1B0]; Handle
0x1400a5e51  xor     r9d, r9d; AccessMode
0x1400a5e54  mov     [rsp+210h+HandleInformation], r13; HandleInformation
0x1400a5e59  mov     edx, 1F0003h; DesiredAccess
0x1400a5e5e  mov     [rsp+210h+var_1C0], r13
0x1400a5e63  mov     r8, [r8]; ObjectType
0x1400a5e66  mov     [rsp+210h+Object], rax; Object
0x1400a5e6b  call    cs:__imp_ObReferenceObjectByHandle
0x1400a5e72  nop     dword ptr [rax+rax+00h]
0x1400a5e77  mov     rsi, [rsp+210h+var_1C0]
0x1400a5e7c  mov     ebx, eax
0x1400a5e7e  test    eax, eax
0x1400a5e80  js      loc_1400A5D29
0x1400a5e86  mov     r12d, r13d
0x1400a5e89  mov     rax, cs:VidDeviceExtension
0x1400a5e90  lea     rdx, [rsp+210h+var_1A0]
0x1400a5e95  mov     rcx, rsi
0x1400a5e98  mov     rax, [rax+858h]
0x1400a5e9f  call    _guard_dispatch_icall
0x1400a5ea4  mov     ebx, eax
0x1400a5ea6  test    eax, eax
0x1400a5ea8  js      loc_1400A5D29
0x1400a5eae  lea     rax, [rsp+210h+Handle]
0x1400a5eb3  mov     r9d, edi; DesiredAccess
0x1400a5eb6  mov     [rsp+210h+var_1E0], rax; Handle
0x1400a5ebb  xor     r8d, r8d; PassedAccessState
0x1400a5ebe  mov     rax, cs:__imp_PsProcessType
0x1400a5ec5  mov     edx, 200h; HandleAttributes
0x1400a5eca  mov     byte ptr [rsp+210h+HandleInformation], r13b; AccessMode
0x1400a5ecf  mov     rcx, [rax]
0x1400a5ed2  mov     [rsp+210h+Object], rcx; ObjectType
0x1400a5ed7  mov     rcx, [rsp+210h+var_1A0]; Object
0x1400a5edc  call    cs:__imp_ObOpenObjectByPointer
0x1400a5ee3  nop     dword ptr [rax+rax+00h]
0x1400a5ee8  mov     ebx, eax
0x1400a5eea  test    eax, eax
0x1400a5eec  js      loc_1400A5D29
0x1400a5ef2  mov     rax, [rsp+210h+var_1B0]
0x1400a5ef7  mov     rcx, rsi
0x1400a5efa  mov     [r15+2880h], rax
0x1400a5f01  mov     rsi, r13
0x1400a5f04  mov     rax, [rsp+210h+Handle]
0x1400a5f09  mov     [r15+2888h], rax
0x1400a5f10  mov     [rsp+210h+var_1B0], r13
0x1400a5f15  mov     [rsp+210h+Handle], r13
0x1400a5f1a  mov     rax, [rsp+210h+var_1D0]
0x1400a5f1f  mov     rdi, r13
0x1400a5f22  mov     [r15+2878h], rcx
0x1400a5f29  mov     ebx, r13d
0x1400a5f2c  mov     [r15+2828h], rax
0x1400a5f33  mov     [r15+2870h], r12d
0x1400a5f3a  jmp     loc_1400A5D2E
0x1400a5f3f  mov     rax, [rcx+2820h]
0x1400a5f46  mov     [rsp+210h+var_1D0], r13
0x1400a5f4b  test    rax, rax
0x1400a5f4e  jz      loc_1400A5E06
0x1400a5f54  mov     rcx, [rax+60h]
0x1400a5f58  test    rcx, rcx
0x1400a5f5b  jz      loc_1400A5E06
0x1400a5f61  mov     rsi, rcx
0x1400a5f64  mov     rcx, rsi; Object
0x1400a5f67  call    cs:__imp_ObfReferenceObject
0x1400a5f6e  nop     dword ptr [rax+rax+00h]
0x1400a5f73  mov     r8d, 90h; Length
0x1400a5f79  lea     r9, [rsp+210h+ReturnLength]; ReturnLength
0x1400a5f7e  lea     rdx, [rbp+110h+ObjectNameInfo]; ObjectNameInfo
0x1400a5f82  mov     [rsp+210h+ReturnLength], r8d
0x1400a5f87  mov     rcx, rsi; Object
0x1400a5f8a  call    cs:__imp_ObQueryNameString
0x1400a5f91  nop     dword ptr [rax+rax+00h]
0x1400a5f96  mov     ebx, eax
0x1400a5f98  mov     r13d, 100h
0x1400a5f9e  cmp     eax, 0C0000004h
0x1400a5fa3  jnz     loc_1400A6059
0x1400a5fa9  mov     edx, [rsp+210h+ReturnLength]
0x1400a5fad  mov     r8d, 6D4D6456h
0x1400a5fb3  mov     ecx, r13d
0x1400a5fb6  call    cs:__imp_ExAllocatePool2
0x1400a5fbd  nop     dword ptr [rax+rax+00h]
0x1400a5fc2  mov     r14, rax
0x1400a5fc5  test    rax, rax
0x1400a5fc8  jnz     short loc_1400A6039
0x1400a5fca  mov     ecx, cs:dword_140064110
0x1400a5fd0  mov     ebx, 0C000009Ah
0x1400a5fd5  cmp     ecx, edi
0x1400a5fd7  jbe     loc_1400A5D29
0x1400a5fdd  mov     edx, r13d
0x1400a5fe0  lea     rcx, dword_140064110
0x1400a5fe7  call    _tlgKeywordOn
0x1400a5fec  xor     r13d, r13d
0x1400a5fef  test    al, al
0x1400a5ff1  jz      loc_1400A5D29
0x1400a5ff7  lea     rdx, aVsmmmempartset; "VsmmMemPartSetupPartition"
0x1400a5ffe  lea     rcx, [rbp+110h+var_170]
0x1400a6002  call    _tlgCreate1Sz_char
0x1400a6007  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a600e  lea     rcx, [rbp+110h+var_160]
0x1400a6012  call    _tlgCreate1Sz_char
0x1400a6017  mov     dword ptr [rsp+210h+var_1C0], 8F3h
0x1400a601f  lea     rax, [rsp+210h+var_1C0]
0x1400a6024  mov     [rsp+210h+var_1C8], ebx
0x1400a6028  lea     rcx, [rsp+210h+var_1C8]
0x1400a602d  lea     rdx, dword_14004BDFC
0x1400a6034  jmp     loc_1400A5C9B
0x1400a6039  mov     r8d, [rsp+210h+ReturnLength]; Length
0x1400a603e  lea     r9, [rsp+210h+ReturnLength]; ReturnLength
0x1400a6043  mov     rdx, rax; ObjectNameInfo
0x1400a6046  mov     rcx, rsi; Object
0x1400a6049  call    cs:__imp_ObQueryNameString
0x1400a6050  nop     dword ptr [rax+rax+00h]
0x1400a6055  mov     ebx, eax
0x1400a6057  jmp     short loc_1400A605D
0x1400a6059  lea     r14, [rbp+110h+ObjectNameInfo]
0x1400a605d  test    ebx, ebx
0x1400a605f  jns     short loc_1400A60CB
0x1400a6061  mov     eax, cs:dword_140064110
0x1400a6067  cmp     eax, edi
0x1400a6069  jbe     loc_1400A5D29
0x1400a606f  mov     rdx, r13
0x1400a6072  lea     rcx, dword_140064110
0x1400a6079  call    _tlgKeywordOn
0x1400a607e  xor     r13d, r13d
0x1400a6081  test    al, al
0x1400a6083  jz      loc_1400A5D29
0x1400a6089  lea     rdx, aVsmmmempartset; "VsmmMemPartSetupPartition"
0x1400a6090  lea     rcx, [rbp+110h+var_170]
0x1400a6094  call    _tlgCreate1Sz_char
0x1400a6099  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a60a0  lea     rcx, [rbp+110h+var_160]
0x1400a60a4  call    _tlgCreate1Sz_char
0x1400a60a9  mov     dword ptr [rsp+210h+var_1C0], 900h
0x1400a60b1  lea     rax, [rsp+210h+var_1C0]
0x1400a60b6  mov     [rsp+210h+var_1C8], ebx
0x1400a60ba  lea     rcx, [rsp+210h+var_1C8]
0x1400a60bf  lea     rdx, word_14004BD8E
0x1400a60c6  jmp     loc_1400A5C9B
0x1400a60cb  cmp     qword ptr [r14+8], 0
0x1400a60d0  jz      loc_1400A6208
0x1400a60d6  xor     ebx, ebx
0x1400a60d8  mov     ecx, ebx
  ... truncated ...
```
