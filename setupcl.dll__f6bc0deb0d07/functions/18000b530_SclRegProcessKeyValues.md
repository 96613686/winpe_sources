# SclRegProcessKeyValues

- ea: `0x18000b530`
- end: `0x18000b732`
- name: `SclRegProcessKeyValues`
- size: `514`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64 *, __int64, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000acec`

## callees

- `0x18000923c`
- `0x18000a524`
- `0x18000ab90`
- `0x18000b530`
- `0x18000c21c`
- `0x18000c70c`
- `0x18000d124`
- `0x180012660`

## string_xrefs

- `0x18000b6c3`: `(%lx): Failure during enumeration of values.`

## pseudocode

```c
__int64 __fastcall SclRegProcessKeyValues(_BYTE *a1, __int64 a2, __int64 *a3, __int64 a4, char *a5)
{
  int v5; // ebx
  char v6; // r14
  __int64 v8; // r13
  __int64 *v9; // r15
  int v11; // edi
  int v12; // eax
  int v13; // eax
  __int64 v14; // r15
  __int64 v15; // rcx
  __int64 v16; // rcx
  _QWORD *v17; // rdi
  int v18; // eax
  __int64 v20; // [rsp+30h] [rbp-30h]
  char v21; // [rsp+50h] [rbp-10h] BYREF
  _BYTE v22[3]; // [rsp+51h] [rbp-Fh] BYREF
  int v23; // [rsp+54h] [rbp-Ch] BYREF
  _QWORD *v24; // [rsp+58h] [rbp-8h] BYREF

  v5 = 0;
  v6 = 0;
  v24 = 0;
  v8 = a4;
  v9 = a3;
  v11 = 0;
  while ( v5 >= 0 )
  {
    v22[0] = 0;
    v21 = 0;
    v23 = 0;
    v12 = SclRegEnumerateValueKey(a2, v11, 1, (int)v9, v8, (__int64)&v23);
    v5 = v12;
    if ( v12 == -2147483622 )
    {
      v17 = v24;
      v5 = 0;
      do
      {
        if ( !v17 )
          break;
        v18 = SclRegApplyRename(a1, a2, (__int64)v17);
        v17 = (_QWORD *)*v17;
        v5 = v18;
      }
      while ( v18 >= 0 );
      if ( v5 >= 0 )
        *a5 = v6;
      break;
    }
    if ( v12 < 0 )
    {
      v16 = (__int64)(a1 + 1152);
      if ( !a1 )
        v16 = 0;
      SclLogGenericMessage(
        v16,
        3,
        (int)SclEvent_Generic_Error,
        843,
        (__int64)"SclRegProcessKeyValues",
        "(%lx): Failure during enumeration of values.",
        v12);
      break;
    }
    v13 = SclRegProcessValue(a1, a2, v9, v8, &v21);
    v14 = *v9;
    v5 = v13;
    if ( v13 >= 0 )
    {
      if ( v21 )
        v6 = 1;
      v5 = SclStringNeedsProcessing(a1, v14 + 20, (unsigned __int64)*(unsigned int *)(v14 + 16) >> 1, v22);
      if ( v5 >= 0 && v22[0] )
      {
        v6 = 1;
        v5 = SclpRegAddProcessItemToList((__int64)a1, &v24, (_WORD *)(v14 + 20), *(_DWORD *)(v14 + 16) >> 1, 1);
      }
    }
    else
    {
      v15 = (__int64)(a1 + 1152);
      LODWORD(v20) = v13;
      if ( !a1 )
        v15 = 0;
      SclLogGenericMessage(
        v15,
        3,
        (int)SclEvent_Generic_Error,
        864,
        (__int64)"SclRegProcessKeyValues",
        "(%lx): Failed to process value [%.*ws]",
        v20,
        (unsigned __int64)*(unsigned int *)(v14 + 16) >> 1,
        v14 + 20);
    }
    v9 = a3;
    v8 = a4;
    ++v11;
  }
  SclpFreeRenameList(&v24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b530  mov     [rsp-38h+arg_0], rbx
0x18000b535  mov     [rsp-38h+arg_18], r9
0x18000b53a  mov     [rsp-38h+arg_10], r8
0x18000b53f  push    rbp
0x18000b540  push    rsi
0x18000b541  push    rdi
0x18000b542  push    r12
0x18000b544  push    r13
0x18000b546  push    r14
0x18000b548  push    r15
0x18000b54a  mov     rbp, rsp
0x18000b54d  sub     rsp, 60h
0x18000b551  xor     ebx, ebx
0x18000b553  xor     r14b, r14b
0x18000b556  mov     rsi, rcx
0x18000b559  mov     [rbp+var_8], rbx
0x18000b55d  mov     r13, r9
0x18000b560  mov     r15, r8
0x18000b563  mov     r12, rdx
0x18000b566  xor     edi, edi
0x18000b568  lea     ecx, [rbx+1]
0x18000b56b  test    ebx, ebx
0x18000b56d  js      loc_18000B70F
0x18000b573  lea     rax, [rbp+var_C]
0x18000b577  mov     [rbp+var_F], 0
0x18000b57b  mov     r8d, ecx
0x18000b57e  mov     [rsp+60h+var_38], rax
0x18000b583  mov     r9, r15
0x18000b586  mov     [rsp+60h+var_40], r13
0x18000b58b  mov     edx, edi
0x18000b58d  mov     [rbp+var_10], 0
0x18000b591  mov     rcx, r12
0x18000b594  mov     [rbp+var_C], 0
0x18000b59b  call    SclRegEnumerateValueKey
0x18000b5a0  mov     ebx, eax
0x18000b5a2  cmp     eax, 8000001Ah
0x18000b5a7  jz      loc_18000B6E2
0x18000b5ad  test    eax, eax
0x18000b5af  js      loc_18000B69D
0x18000b5b5  lea     rax, [rbp+var_10]
0x18000b5b9  mov     r9, r13
0x18000b5bc  mov     r8, r15
0x18000b5bf  mov     [rsp+60h+var_40], rax
0x18000b5c4  mov     rdx, r12
0x18000b5c7  mov     rcx, rsi
0x18000b5ca  call    SclRegProcessValue
0x18000b5cf  mov     r15, [r15]
0x18000b5d2  mov     ebx, eax
0x18000b5d4  lea     r13, [r15+14h]
0x18000b5d8  test    eax, eax
0x18000b5da  jns     short loc_18000B632
0x18000b5dc  mov     edx, [r15+10h]
0x18000b5e0  lea     rcx, [rsi+480h]
0x18000b5e7  xor     eax, eax
0x18000b5e9  shr     rdx, 1
0x18000b5ec  mov     [rsp+60h+var_20], r13
0x18000b5f1  lea     r8, SclEvent_Generic_Error
0x18000b5f8  mov     [rsp+60h+var_28], rdx
0x18000b5fd  test    rsi, rsi
0x18000b600  mov     dword ptr [rsp+60h+var_30], ebx
0x18000b604  mov     r9d, 360h
0x18000b60a  cmovz   rcx, rax
0x18000b60e  mov     edx, 3
0x18000b613  lea     rax, aLxFailedToProc_5; "(%lx): Failed to process value [%.*ws]"
0x18000b61a  mov     [rsp+60h+var_38], rax
0x18000b61f  lea     rax, aSclregprocessk_0; "SclRegProcessKeyValues"
0x18000b626  mov     [rsp+60h+var_40], rax
0x18000b62b  call    SclLogGenericMessage
0x18000b630  jmp     short loc_18000B689
0x18000b632  mov     r8d, [r15+10h]
0x18000b636  lea     r9, [rbp+var_F]
0x18000b63a  cmp     [rbp+var_10], 0
0x18000b63e  mov     eax, 1
0x18000b643  movzx   r14d, r14b
0x18000b647  mov     rdx, r13
0x18000b64a  cmovnz  r14d, eax
0x18000b64e  mov     rcx, rsi
0x18000b651  shr     r8, 1
0x18000b654  call    SclStringNeedsProcessing
0x18000b659  mov     ebx, eax
0x18000b65b  test    eax, eax
0x18000b65d  js      short loc_18000B689
0x18000b65f  cmp     [rbp+var_F], 0
0x18000b663  jz      short loc_18000B689
0x18000b665  mov     r9d, [r15+10h]
0x18000b669  lea     rdx, [rbp+var_8]
0x18000b66d  mov     eax, 1
0x18000b672  shr     r9d, 1
0x18000b675  mov     r8, r13
0x18000b678  mov     dword ptr [rsp+60h+var_40], eax
0x18000b67c  mov     rcx, rsi
0x18000b67f  mov     r14b, al
0x18000b682  call    SclpRegAddProcessItemToList
0x18000b687  mov     ebx, eax
0x18000b689  mov     r15, [rbp+arg_10]
0x18000b68d  mov     ecx, 1
0x18000b692  mov     r13, [rbp+arg_18]
0x18000b696  add     edi, ecx
0x18000b698  jmp     loc_18000B56B
0x18000b69d  xor     eax, eax
0x18000b69f  mov     dword ptr [rsp+60h+var_30], ebx
0x18000b6a3  test    rsi, rsi
0x18000b6a6  lea     rcx, [rsi+480h]
0x18000b6ad  mov     r9d, 34Bh
0x18000b6b3  lea     r8, SclEvent_Generic_Error
0x18000b6ba  cmovz   rcx, rax
0x18000b6be  mov     edx, 3
0x18000b6c3  lea     rax, aLxFailureDurin_0; "(%lx): Failure during enumeration of va"...
0x18000b6ca  mov     [rsp+60h+var_38], rax
0x18000b6cf  lea     rax, aSclregprocessk_0; "SclRegProcessKeyValues"
0x18000b6d6  mov     [rsp+60h+var_40], rax
0x18000b6db  call    SclLogGenericMessage
0x18000b6e0  jmp     short loc_18000B70F
0x18000b6e2  mov     rdi, [rbp+var_8]
0x18000b6e6  xor     ebx, ebx
0x18000b6e8  test    rdi, rdi
0x18000b6eb  jz      short loc_18000B704
0x18000b6ed  mov     r8, rdi
0x18000b6f0  mov     rdx, r12
0x18000b6f3  mov     rcx, rsi
0x18000b6f6  call    SclRegApplyRename
0x18000b6fb  mov     rdi, [rdi]
0x18000b6fe  mov     ebx, eax
0x18000b700  test    eax, eax
0x18000b702  jns     short loc_18000B6E8
0x18000b704  test    ebx, ebx
0x18000b706  js      short loc_18000B70F
0x18000b708  mov     rax, [rbp+arg_20]
0x18000b70c  mov     [rax], r14b
0x18000b70f  lea     rcx, [rbp+var_8]
0x18000b713  call    SclpFreeRenameList
0x18000b718  mov     eax, ebx
0x18000b71a  mov     rbx, [rsp+60h+arg_0]
0x18000b722  add     rsp, 60h
0x18000b726  pop     r15
0x18000b728  pop     r14
0x18000b72a  pop     r13
0x18000b72c  pop     r12
0x18000b72e  pop     rdi
0x18000b72f  pop     rsi
0x18000b730  pop     rbp
0x18000b731  retn
```
