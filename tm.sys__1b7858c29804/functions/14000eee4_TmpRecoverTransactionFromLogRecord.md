# TmpRecoverTransactionFromLogRecord

- ea: `0x14000eee4`
- end: `0x14000f09b`
- name: `TmpRecoverTransactionFromLogRecord`
- size: `439`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PHANDLE TransactionHandle, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001ca60`

## callees

- `0x14000edb0`
- `0x14000eee4`
- `0x14000f0a4`
- `0x140020a6c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000f071`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f071`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000ef93`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000ef93`
- `ntoskrnl!ZwCreateTransaction` at `0x14000f05b`
- `ntoskrnl!ZwCreateTransaction` at `0x14000f05b`

## pseudocode

```c
NTSTATUS __fastcall TmpRecoverTransactionFromLogRecord(
        __int64 a1,
        unsigned int a2,
        char a3,
        void *a4,
        __int64 a5,
        PHANDLE TransactionHandle,
        _BYTE *a7)
{
  int v10; // edi
  NTSTATUS result; // eax
  bool v12; // zf
  UNICODE_STRING *Description; // rcx
  int v14; // r9d
  PSECURITY_DESCRIPTOR v15; // [rsp+50h] [rbp-41h] BYREF
  __int128 v16; // [rsp+58h] [rbp-39h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-29h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  *TransactionHandle = 0;
  *a7 = 0;
  v15 = 0;
  v16 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = TmpNamespaceLookup((PRTL_AVL_TABLE)(a5 + 176), (PVOID)(a1 + 8));
  if ( v10 < 0 )
  {
    if ( a3 == 1 )
    {
      result = TmpRecoverSecurityDescriptor(a1, a2, *(_DWORD *)(a1 + 44), *(_DWORD *)(a1 + 40), &v15);
      if ( result < 0 )
        return result;
      v12 = *(_DWORD *)a1 == 260;
      Description = 0;
      ObjectAttributes.SecurityDescriptor = v15;
      if ( v12 && *(_DWORD *)(a1 + 36) >= 0x48u && *(_DWORD *)(a1 + 52) >= 0x10000001u )
      {
        v14 = *(_DWORD *)(a1 + 56);
        if ( v14 )
        {
          result = TmpRecoverUnicodeString(a1, a2, *(_DWORD *)(a1 + 60), v14, (__int64)&v16);
          if ( result < 0 )
            return result;
          Description = (UNICODE_STRING *)&v16;
        }
      }
      return ZwCreateTransaction(
               TransactionHandle,
               0x1F003Fu,
               &ObjectAttributes,
               (LPGUID)(a1 + 8),
               a4,
               0,
               0,
               0,
               0,
               Description);
    }
  }
  else
  {
    result = ObOpenObjectByPointer(0, 0x200u, 0, 0x1F003Fu, (POBJECT_TYPE)TmTransactionObjectType, 0, TransactionHandle);
    v10 = result;
    if ( result < 0 )
      return result;
    *a7 = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x14000eee4  mov     [rsp-8+arg_8], rbx
0x14000eee9  mov     [rsp-8+TmHandle], r9
0x14000eeee  push    rbp
0x14000eeef  push    rsi
0x14000eef0  push    rdi
0x14000eef1  push    r12
0x14000eef3  push    r13
0x14000eef5  push    r14
0x14000eef7  push    r15
0x14000eef9  lea     rbp, [rsp-0Fh]
0x14000eefe  sub     rsp, 0A0h
0x14000ef05  mov     r15, [rbp+3Fh+TransactionHandle]
0x14000ef09  xor     eax, eax
0x14000ef0b  mov     r14, [rbp+3Fh+arg_30]
0x14000ef0f  mov     rbx, rcx
0x14000ef12  xorps   xmm0, xmm0
0x14000ef15  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14000ef1d  mov     r12d, edx
0x14000ef20  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 200h
0x14000ef28  lea     rdx, [rcx+8]; Buffer
0x14000ef2c  mov     [r15], rax
0x14000ef2f  mov     rcx, [rbp+3Fh+arg_20]
0x14000ef33  mov     r13b, r8b
0x14000ef36  add     rcx, 0B0h; Table
0x14000ef3d  mov     [r14], al
0x14000ef40  lea     r8, [rbp+3Fh+Object]
0x14000ef44  mov     [rbp+3Fh+var_80], rax
0x14000ef48  movups  [rbp+3Fh+var_78], xmm0
0x14000ef4c  mov     [rbp+3Fh+Object], rax
0x14000ef50  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x14000ef54  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14000ef58  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ef5d  call    TmpNamespaceLookup
0x14000ef62  mov     rsi, [rbp+3Fh+Object]
0x14000ef66  mov     edi, eax
0x14000ef68  test    eax, eax
0x14000ef6a  js      short loc_14000EFB2
0x14000ef6c  mov     rax, cs:TmTransactionObjectType
0x14000ef73  mov     r9d, 1F003Fh; DesiredAccess
0x14000ef79  mov     [rsp+0D0h+Handle], r15; Handle
0x14000ef7e  xor     r8d, r8d; PassedAccessState
0x14000ef81  mov     [rsp+0D0h+AccessMode], 0; AccessMode
0x14000ef86  mov     edx, 200h; HandleAttributes
0x14000ef8b  mov     rcx, rsi; Object
0x14000ef8e  mov     [rsp+0D0h+ObjectType], rax; ObjectType
0x14000ef93  call    cs:__imp_ObOpenObjectByPointer
0x14000ef9a  nop     dword ptr [rax+rax+00h]
0x14000ef9f  mov     edi, eax
0x14000efa1  test    eax, eax
0x14000efa3  js      loc_14000F07F
0x14000efa9  mov     byte ptr [r14], 1
0x14000efad  jmp     loc_14000F069
0x14000efb2  cmp     r13b, 1
0x14000efb6  jnz     loc_14000F069
0x14000efbc  mov     r9d, [rbx+28h]
0x14000efc0  lea     rax, [rbp+3Fh+var_80]
0x14000efc4  mov     r8d, [rbx+2Ch]
0x14000efc8  mov     edx, r12d
0x14000efcb  mov     rcx, rbx
0x14000efce  mov     [rsp+0D0h+ObjectType], rax
0x14000efd3  call    TmpRecoverSecurityDescriptor
0x14000efd8  xor     edi, edi
0x14000efda  test    eax, eax
0x14000efdc  js      loc_14000F07F
0x14000efe2  cmp     dword ptr [rbx], 104h
0x14000efe8  mov     ecx, edi
0x14000efea  mov     rax, [rbp+3Fh+var_80]
0x14000efee  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x14000eff2  jnz     short loc_14000F02C
0x14000eff4  cmp     dword ptr [rbx+24h], 48h ; 'H'
0x14000eff8  jb      short loc_14000F02C
0x14000effa  cmp     dword ptr [rbx+34h], 10000001h
0x14000f001  jb      short loc_14000F02C
0x14000f003  mov     r9d, [rbx+38h]
0x14000f007  test    r9d, r9d
0x14000f00a  jz      short loc_14000F02C
0x14000f00c  mov     r8d, [rbx+3Ch]
0x14000f010  lea     rax, [rbp+3Fh+var_78]
0x14000f014  mov     edx, r12d
0x14000f017  mov     [rsp+0D0h+ObjectType], rax
0x14000f01c  mov     rcx, rbx
0x14000f01f  call    TmpRecoverUnicodeString
0x14000f024  test    eax, eax
0x14000f026  js      short loc_14000F07F
0x14000f028  lea     rcx, [rbp+3Fh+var_78]
0x14000f02c  mov     rax, [rbp+3Fh+TmHandle]
0x14000f030  lea     r9, [rbx+8]; Uow
0x14000f034  mov     [rsp+0D0h+Description], rcx; Description
0x14000f039  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14000f03d  mov     [rsp+0D0h+Timeout], rdi; Timeout
0x14000f042  mov     edx, 1F003Fh; DesiredAccess
0x14000f047  mov     [rsp+0D0h+IsolationFlags], edi; IsolationFlags
0x14000f04b  mov     rcx, r15; TransactionHandle
0x14000f04e  mov     dword ptr [rsp+0D0h+Handle], edi; IsolationLevel
0x14000f052  mov     dword ptr [rsp+0D0h+AccessMode], edi; CreateOptions
0x14000f056  mov     [rsp+0D0h+ObjectType], rax; TmHandle
0x14000f05b  call    cs:__imp_ZwCreateTransaction
0x14000f062  nop     dword ptr [rax+rax+00h]
0x14000f067  mov     edi, eax
0x14000f069  test    rsi, rsi
0x14000f06c  jz      short loc_14000F07D
0x14000f06e  mov     rcx, rsi; Object
0x14000f071  call    cs:__imp_ObfDereferenceObject
0x14000f078  nop     dword ptr [rax+rax+00h]
0x14000f07d  mov     eax, edi
0x14000f07f  mov     rbx, [rsp+0D0h+arg_8]
0x14000f087  add     rsp, 0A0h
0x14000f08e  pop     r15
0x14000f090  pop     r14
0x14000f092  pop     r13
0x14000f094  pop     r12
0x14000f096  pop     rdi
0x14000f097  pop     rsi
0x14000f098  pop     rbp
0x14000f099  retn
```
