# NtEnumerateTransactionObjectExt

- ea: `0x1400168d0`
- end: `0x140016b05`
- name: `NtEnumerateTransactionObjectExt`
- size: `565`
- prototype: `NTSTATUS __stdcall(HANDLE RootObjectHandle, KTMOBJECT_TYPE QueryType, PKTMOBJECT_CURSOR ObjectCursor, ULONG ObjectCursorLength, PULONG ReturnLength)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400014d4`
- `0x1400024e0`
- `0x14000d238`
- `0x14000d2bc`
- `0x1400168d0`
- `0x140019a88`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140016ab2`
- `ntoskrnl!ObfDereferenceObject` at `0x140016ab2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016a42`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140016a42`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140016997`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140016997`
- `ntoskrnl!ProbeForWrite` at `0x140016953`
- `ntoskrnl!ProbeForWrite` at `0x140016953`
- `ntoskrnl!ProbeForRead` at `0x14001696b`
- `ntoskrnl!ProbeForRead` at `0x14001696b`

## pseudocode

```c
NTSTATUS __stdcall NtEnumerateTransactionObjectExt(
        HANDLE RootObjectHandle,
        KTMOBJECT_TYPE QueryType,
        PKTMOBJECT_CURSOR ObjectCursor,
        ULONG ObjectCursorLength,
        PULONG ReturnLength)
{
  HANDLE v8; // r10
  KPROCESSOR_MODE v9; // r14
  unsigned int ULongFromUser; // eax
  struct _RTL_AVL_TABLE *v11; // rsi
  POBJECT_TYPE *v12; // r8
  ACCESS_MASK v13; // edx
  HANDLE v14; // rdi
  NTSTATUS result; // eax
  __int32 v16; // ebx
  NTSTATUS v17; // ebx
  ULONG v18; // [rsp+30h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-80h] BYREF
  NTSTATUS v20; // [rsp+40h] [rbp-78h]
  GUID v21; // [rsp+50h] [rbp-68h] BYREF
  GUID LastQuery; // [rsp+60h] [rbp-58h] BYREF

  v8 = RootObjectHandle;
  Handle = RootObjectHandle;
  v9 = *((_BYTE *)KeGetCurrentThread() + 562);
  LastQuery = 0;
  v18 = 0;
  if ( QueryType >= KTMOBJECT_INVALID || ObjectCursorLength < 0x24 )
    return -1073741811;
  if ( v9 )
  {
    ProbeForWrite(ObjectCursor, ObjectCursorLength, 4u);
    ProbeForRead(ObjectCursor, 0x10u, 4u);
    ULongFromUser = RtlReadULongFromUser(ReturnLength);
    RtlWriteULongToUser(ReturnLength, ULongFromUser);
    v21 = 0;
    if ( ((unsigned __int8)ObjectCursor & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v21, ObjectCursor, 0x10u);
    LastQuery = v21;
    v8 = Handle;
  }
  else
  {
    LastQuery = ObjectCursor->LastQuery;
  }
  LODWORD(v11) = 0;
  v12 = 0;
  v13 = 0;
  if ( QueryType == KTMOBJECT_TRANSACTION )
  {
    if ( !v8 )
    {
      v11 = &TmpTransactionsNamespace;
      goto LABEL_18;
    }
    goto LABEL_15;
  }
  if ( QueryType != KTMOBJECT_TRANSACTION_MANAGER )
  {
    if ( QueryType != KTMOBJECT_RESOURCE_MANAGER )
    {
      if ( QueryType == KTMOBJECT_ENLISTMENT )
      {
        v12 = TmResourceManagerObjectType;
LABEL_16:
        v13 = 1;
        goto LABEL_18;
      }
      return -1073741811;
    }
LABEL_15:
    v12 = TmTransactionManagerObjectType;
    goto LABEL_16;
  }
  v11 = &TmpTmNamespace;
LABEL_18:
  v14 = 0;
  if ( v12 )
  {
    Handle = 0;
    result = ObReferenceObjectByHandle(v8, v13, (POBJECT_TYPE)v12, v9, &Handle, 0);
    if ( result < 0 )
      return result;
    v14 = Handle;
    if ( QueryType )
    {
      v16 = QueryType - 2;
      if ( v16 )
      {
        if ( v16 == 1 )
          LODWORD(v11) = (_DWORD)Handle + 384;
      }
      else
      {
        LODWORD(v11) = (_DWORD)Handle + 344;
      }
    }
    else
    {
      LODWORD(v11) = (_DWORD)Handle + 176;
    }
  }
  v17 = TmpNamespaceEnumerate(
          (_DWORD)v11,
          (unsigned int)&LastQuery,
          (_DWORD)ObjectCursor,
          ObjectCursorLength,
          (__int64)&v18,
          v9);
  v20 = v17;
  if ( v14 )
    ObfDereferenceObject(v14);
  *ReturnLength = v18;
  return v17;
}

```

## disassembly

```asm
0x1400168d0  push    rbx
0x1400168d2  push    rsi
0x1400168d3  push    rdi
0x1400168d4  push    r12
0x1400168d6  push    r13
0x1400168d8  push    r14
0x1400168da  push    r15
0x1400168dc  sub     rsp, 80h
0x1400168e3  mov     rax, cs:__security_cookie
0x1400168ea  xor     rax, rsp
0x1400168ed  mov     [rsp+0B8h+var_48], rax
0x1400168f2  mov     r13d, r9d
0x1400168f5  mov     r15, r8
0x1400168f8  mov     ebx, edx
0x1400168fa  mov     r10, rcx
0x1400168fd  mov     [rsp+0B8h+Handle], rcx
0x140016902  mov     r12, [rsp+0B8h+ReturnLength]
0x14001690a  mov     rax, gs:188h
0x140016913  mov     r14b, [rax+232h]
0x14001691a  xorps   xmm0, xmm0
0x14001691d  movups  [rsp+0B8h+var_58], xmm0
0x140016922  mov     [rsp+0B8h+var_88], 0
0x14001692a  mov     edi, 4
0x14001692f  cmp     edx, edi
0x140016931  jge     loc_140016ADF
0x140016937  cmp     r13d, 24h ; '$'
0x14001693b  jb      loc_140016ADF
0x140016941  test    r14b, r14b
0x140016944  jz      loc_1400169CB
0x14001694a  mov     edx, r13d; Length
0x14001694d  mov     r8d, edi; Alignment
0x140016950  mov     rcx, r15; Address
0x140016953  call    cs:__imp_ProbeForWrite
0x14001695a  nop     dword ptr [rax+rax+00h]
0x14001695f  mov     r8d, edi; Alignment
0x140016962  lea     edi, [r8+0Ch]
0x140016966  mov     edx, edi; Length
0x140016968  mov     rcx, r15; Address
0x14001696b  call    cs:__imp_ProbeForRead
0x140016972  nop     dword ptr [rax+rax+00h]
0x140016977  mov     rcx, r12
0x14001697a  call    RtlReadULongFromUser
0x14001697f  mov     edx, eax
0x140016981  mov     rcx, r12
0x140016984  call    RtlWriteULongToUser
0x140016989  xorps   xmm0, xmm0
0x14001698c  movups  [rsp+0B8h+var_68], xmm0
0x140016991  test    r15b, 3
0x140016995  jz      short loc_1400169A4
0x140016997  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14001699e  nop     dword ptr [rax+rax+00h]
0x1400169a3  int     3; Trap to Debugger
0x1400169a4  mov     r8, rdi; Size
0x1400169a7  mov     rdx, r15; Src
0x1400169aa  lea     rcx, [rsp+0B8h+var_68]; void *
0x1400169af  call    RtlCopyFromUser
0x1400169b4  movaps  xmm0, [rsp+0B8h+var_68]
0x1400169b9  movdqa  [rsp+0B8h+var_58], xmm0
0x1400169bf  mov     r10, [rsp+0B8h+Handle]
0x1400169c4  jmp     short loc_1400169D5
0x1400169c6  jmp     loc_140016AE4
0x1400169cb  movups  xmm0, xmmword ptr [r8]
0x1400169cf  movdqu  [rsp+0B8h+var_58], xmm0
0x1400169d5  xor     esi, esi
0x1400169d7  xor     r8d, r8d; ObjectType
0x1400169da  xor     edx, edx; DesiredAccess
0x1400169dc  mov     ecx, ebx
0x1400169de  test    ebx, ebx
0x1400169e0  jz      short loc_140016A07
0x1400169e2  sub     ecx, 1
0x1400169e5  jz      short loc_1400169FE
0x1400169e7  sub     ecx, 1
0x1400169ea  jz      short loc_140016A0C
0x1400169ec  cmp     ecx, 1
0x1400169ef  jnz     loc_140016ADF
0x1400169f5  mov     r8, cs:TmResourceManagerObjectType
0x1400169fc  jmp     short loc_140016A13
0x1400169fe  lea     rsi, TmpTmNamespace
0x140016a05  jmp     short loc_140016A21
0x140016a07  test    r10, r10
0x140016a0a  jz      short loc_140016A1A
0x140016a0c  mov     r8, cs:TmTransactionManagerObjectType
0x140016a13  mov     edx, 1
0x140016a18  jmp     short loc_140016A21
0x140016a1a  lea     rsi, TmpTransactionsNamespace
0x140016a21  xor     edi, edi
0x140016a23  test    r8, r8
0x140016a26  jz      short loc_140016A82
0x140016a28  mov     [rsp+0B8h+Handle], rdi
0x140016a2d  mov     [rsp+0B8h+HandleInformation], rdi; HandleInformation
0x140016a32  lea     rax, [rsp+0B8h+Handle]
0x140016a37  mov     [rsp+0B8h+Object], rax; Object
0x140016a3c  mov     r9b, r14b; AccessMode
0x140016a3f  mov     rcx, r10; Handle
0x140016a42  call    cs:__imp_ObReferenceObjectByHandle
0x140016a49  nop     dword ptr [rax+rax+00h]
0x140016a4e  test    eax, eax
0x140016a50  js      loc_140016AE4
0x140016a56  mov     rdi, [rsp+0B8h+Handle]
0x140016a5b  test    ebx, ebx
0x140016a5d  jz      short loc_140016A7B
0x140016a5f  sub     ebx, 2
0x140016a62  jz      short loc_140016A72
0x140016a64  cmp     ebx, 1
0x140016a67  jnz     short loc_140016A82
0x140016a69  lea     rsi, [rdi+180h]
0x140016a70  jmp     short loc_140016A82
0x140016a72  lea     rsi, [rdi+158h]
0x140016a79  jmp     short loc_140016A82
0x140016a7b  lea     rsi, [rdi+0B0h]
0x140016a82  mov     byte ptr [rsp+0B8h+HandleInformation], r14b
0x140016a87  lea     rax, [rsp+0B8h+var_88]
0x140016a8c  mov     [rsp+0B8h+Object], rax
0x140016a91  mov     r9d, r13d
0x140016a94  mov     r8, r15
0x140016a97  lea     rdx, [rsp+0B8h+var_58]
0x140016a9c  mov     rcx, rsi
0x140016a9f  call    TmpNamespaceEnumerate
0x140016aa4  mov     ebx, eax
0x140016aa6  mov     [rsp+0B8h+var_78], eax
0x140016aaa  test    rdi, rdi
0x140016aad  jz      short loc_140016ABE
0x140016aaf  mov     rcx, rdi; Object
0x140016ab2  call    cs:__imp_ObfDereferenceObject
0x140016ab9  nop     dword ptr [rax+rax+00h]
0x140016abe  test    r14b, r14b
0x140016ac1  jnz     short loc_140016ACD
0x140016ac3  mov     ecx, [rsp+0B8h+var_88]
0x140016ac7  mov     [r12], ecx
0x140016acb  jmp     short loc_140016ADB
0x140016acd  mov     eax, [rsp+0B8h+var_88]
0x140016ad1  mov     [r12], eax
0x140016ad5  jmp     short loc_140016ADB
0x140016ad7  mov     ebx, [rsp+0B8h+var_78]
0x140016adb  mov     eax, ebx
0x140016add  jmp     short loc_140016AE4
0x140016adf  mov     eax, 0C000000Dh
0x140016ae4  mov     rcx, [rsp+0B8h+var_48]
0x140016ae9  xor     rcx, rsp; StackCookie
0x140016aec  call    __security_check_cookie
0x140016af1  add     rsp, 80h
0x140016af8  pop     r15
0x140016afa  pop     r14
0x140016afc  pop     r13
0x140016afe  pop     r12
0x140016b00  pop     rdi
0x140016b01  pop     rsi
0x140016b02  pop     rbx
0x140016b03  retn
0x1400226bc  push    rbp
0x1400226be  sub     rsp, 30h
0x1400226c2  mov     rbp, rdx
0x1400226c5  call    cs:__imp_ExSystemExceptionFilter
0x1400226cc  nop     dword ptr [rax+rax+00h]
0x1400226d1  nop
0x1400226d2  add     rsp, 30h
0x1400226d6  pop     rbp
0x1400226d7  retn
0x1400226d9  push    rbp
0x1400226db  sub     rsp, 30h
0x1400226df  mov     rbp, rdx
0x1400226e2  call    cs:__imp_ExSystemExceptionFilter
0x1400226e9  nop     dword ptr [rax+rax+00h]
0x1400226ee  nop
0x1400226ef  add     rsp, 30h
0x1400226f3  pop     rbp
0x1400226f4  retn
```
