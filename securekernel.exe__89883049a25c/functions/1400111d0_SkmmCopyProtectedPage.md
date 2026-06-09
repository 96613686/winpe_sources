# SkmmCopyProtectedPage

- ea: `0x1400111d0`
- end: `0x140011390`
- name: `SkmmCopyProtectedPage`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140002ef0`
- `0x14000e130`
- `0x1400111d0`
- `0x140061d60`
- `0x1400720b8`
- `0x140072594`
- `0x140072884`
- `0x140072fc4`

## pseudocode

```c
__int64 __fastcall SkmmCopyProtectedPage(
        ULONG_PTR a1,
        __int64 *a2,
        ULONG_PTR a3,
        __int64 *a4,
        __int64 BackTraceHash,
        char a6)
{
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned int v12; // ebx
  __int64 result; // rax
  __int64 v14; // r14
  __int64 (__fastcall **v15)(); // rax
  unsigned int v16; // eax
  unsigned __int64 v17; // rdx
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v18 = 0;
  if ( a1 != a3 && (*(_DWORD *)a2 & 0xFFF) == 0 && (*(_DWORD *)a4 & 0xFFF) == 0 )
  {
    v10 = a4[1];
    if ( !v10 )
    {
      v11 = a2[1];
      if ( v11 )
      {
        if ( a6 )
          return (unsigned int)-1073741811;
        else
          return (unsigned int)SkmiCopyKernelImagePage(a1, v11, (unsigned __int64)*a2 >> 12, a3, BackTraceHash, *a4);
      }
      else
      {
        return (unsigned int)SkmiCopyNormalKernelPage(a1, *a2, a3, *a4, BackTraceHash, a6);
      }
    }
    if ( !BackTraceHash )
    {
      result = SkobReferenceObjectByHandle(v10, 0, 1, 0, &v18, 0);
      if ( (int)result < 0 )
        return result;
      v14 = v18;
      v15 = *(__int64 (__fastcall ***)())(v18 - 16);
      if ( v15 == (__int64 (__fastcall **)())&SkmiImageType )
      {
        if ( a4[1] == a2[1] && *a4 == *a2 && a6 )
        {
          v16 = SkmiRelocateImagePage(a1, a3, v18, (unsigned __int64)*a2 >> 12);
LABEL_24:
          v12 = v16;
          goto LABEL_26;
        }
      }
      else if ( v15 == &SkpsProcessType )
      {
        v17 = a2[1];
        if ( a4[1] == v17 && *a4 == *a2 )
        {
          if ( a6 )
          {
            v12 = SkmiRelocatePrivatePage(a1, a3);
LABEL_26:
            SkobDereferenceObject(v14);
            return v12;
          }
        }
        else if ( a6 )
        {
          goto LABEL_25;
        }
        v16 = SkmiCopyPrivateImagePage(a1, v17, (unsigned __int64)*a2 >> 12, a3, v18, *a4);
        goto LABEL_24;
      }
LABEL_25:
      v12 = -1073741811;
      goto LABEL_26;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400111d0  mov     [rsp+arg_10], rbx
0x1400111d5  push    rbp
0x1400111d6  push    rsi
0x1400111d7  push    rdi
0x1400111d8  sub     rsp, 30h
0x1400111dc  mov     rbx, rdx
0x1400111df  mov     rdi, r9
0x1400111e2  xor     edx, edx
0x1400111e4  mov     rsi, r8
0x1400111e7  mov     [rsp+48h+arg_0], rdx
0x1400111ec  mov     rbp, rcx
0x1400111ef  cmp     rcx, r8
0x1400111f2  jz      loc_14001137D
0x1400111f8  test    dword ptr [rbx], 0FFFh
0x1400111fe  jnz     loc_14001137D
0x140011204  test    dword ptr [r9], 0FFFh
0x14001120b  jnz     loc_14001137D
0x140011211  mov     rcx, [r9+8]
0x140011215  test    rcx, rcx
0x140011218  jnz     short loc_140011286
0x14001121a  mov     rdx, [rbx+8]
0x14001121e  test    rdx, rdx
0x140011221  jz      short loc_14001125E
0x140011223  cmp     [rsp+48h+arg_28], cl
0x140011227  jz      short loc_140011233
0x140011229  mov     ebx, 0C000000Dh
0x14001122e  jmp     loc_140011379
0x140011233  mov     rax, [r9]
0x140011236  mov     rcx, rbp
0x140011239  mov     r8, [rbx]
0x14001123c  mov     r9, rsi
0x14001123f  mov     qword ptr [rsp+48h+var_20], rax
0x140011244  mov     rax, [rsp+48h+arg_20]
0x140011249  shr     r8, 0Ch
0x14001124d  mov     qword ptr [rsp+48h+BackTraceHash], rax
0x140011252  call    SkmiCopyKernelImagePage
0x140011257  mov     ebx, eax
0x140011259  jmp     loc_140011379
0x14001125e  movzx   eax, [rsp+48h+arg_28]
0x140011263  mov     rcx, rbp; BugCheckParameter3
0x140011266  mov     r9, [r9]
0x140011269  mov     rdx, [rbx]
0x14001126c  mov     [rsp+48h+var_20], al; char
0x140011270  mov     rax, [rsp+48h+arg_20]
0x140011275  mov     qword ptr [rsp+48h+BackTraceHash], rax; BackTraceHash
0x14001127a  call    SkmiCopyNormalKernelPage
0x14001127f  mov     ebx, eax
0x140011281  jmp     loc_140011379
0x140011286  cmp     [rsp+48h+arg_20], rdx
0x14001128b  jnz     loc_14001137D
0x140011291  lea     rax, [rsp+48h+arg_0]
0x140011296  mov     qword ptr [rsp+48h+var_20], rdx
0x14001129b  xor     r9d, r9d
0x14001129e  mov     qword ptr [rsp+48h+BackTraceHash], rax
0x1400112a3  mov     r8b, 1
0x1400112a6  call    SkobReferenceObjectByHandle
0x1400112ab  test    eax, eax
0x1400112ad  js      loc_140011382
0x1400112b3  mov     [rsp+48h+arg_8], r14
0x1400112b8  lea     rcx, SkmiImageType
0x1400112bf  mov     r14, [rsp+48h+arg_0]
0x1400112c4  mov     rax, [r14-10h]
0x1400112c8  cmp     rax, rcx
0x1400112cb  jnz     short loc_140011302
0x1400112cd  mov     rax, [rbx+8]
0x1400112d1  cmp     [rdi+8], rax
0x1400112d5  jnz     loc_140011367
0x1400112db  mov     r9, [rbx]
0x1400112de  cmp     [rdi], r9
0x1400112e1  jnz     loc_140011367
0x1400112e7  cmp     [rsp+48h+arg_28], 0
0x1400112ec  jz      short loc_140011367
0x1400112ee  shr     r9, 0Ch
0x1400112f2  mov     r8, r14
0x1400112f5  mov     rdx, rsi
0x1400112f8  mov     rcx, rbp
0x1400112fb  call    SkmiRelocateImagePage
0x140011300  jmp     short loc_140011363
0x140011302  lea     rcx, SkpsProcessType
0x140011309  cmp     rax, rcx
0x14001130c  jnz     short loc_140011367
0x14001130e  mov     rdx, [rbx+8]
0x140011312  cmp     [rdi+8], rdx
0x140011316  jnz     short loc_14001133D
0x140011318  mov     r9, [rbx]
0x14001131b  cmp     [rdi], r9
0x14001131e  jnz     short loc_14001133D
0x140011320  cmp     [rsp+48h+arg_28], 0
0x140011325  jz      short loc_140011344
0x140011327  shr     r9, 0Ch
0x14001132b  mov     r8, r14
0x14001132e  mov     rdx, rsi; ULONG_PTR
0x140011331  mov     rcx, rbp; BugCheckParameter3
0x140011334  call    SkmiRelocatePrivatePage
0x140011339  mov     ebx, eax
0x14001133b  jmp     short loc_14001136C
0x14001133d  cmp     [rsp+48h+arg_28], 0
0x140011342  jnz     short loc_140011367
0x140011344  mov     r8, [rbx]
0x140011347  mov     r9, rsi
0x14001134a  mov     rax, [rdi]
0x14001134d  mov     rcx, rbp; int
0x140011350  mov     qword ptr [rsp+48h+var_20], rax; __int64
0x140011355  shr     r8, 0Ch
0x140011359  mov     qword ptr [rsp+48h+BackTraceHash], r14; int
0x14001135e  call    SkmiCopyPrivateImagePage
0x140011363  mov     ebx, eax
0x140011365  jmp     short loc_14001136C
0x140011367  mov     ebx, 0C000000Dh
0x14001136c  mov     rcx, r14
0x14001136f  call    SkobDereferenceObject
0x140011374  mov     r14, [rsp+48h+arg_8]
0x140011379  mov     eax, ebx
0x14001137b  jmp     short loc_140011382
0x14001137d  mov     eax, 0C000000Dh
0x140011382  mov     rbx, [rsp+48h+arg_10]
0x140011387  add     rsp, 30h
0x14001138b  pop     rdi
0x14001138c  pop     rsi
0x14001138d  pop     rbp
0x14001138e  retn
```
