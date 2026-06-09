# SclpCanonicalizePaths

- ea: `0x180004c88`
- end: `0x180004f56`
- name: `SclpCanonicalizePaths`
- size: `718`
- prototype: `__int64 __fastcall(void *, _WORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180002010`

## callees

- `0x180004c88`
- `0x180007ac4`
- `0x18000a524`
- `0x18000a7f0`
- `0x18000a8c4`
- `0x180014ebc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004cc2`
- `ntdll!RtlAllocateHeap` at `0x180004cc2`
- `ntdll!RtlFreeHeap` at `0x180004d95`
- `ntdll!RtlFreeHeap` at `0x180004e1c`
- `ntdll!RtlFreeHeap` at `0x180004ed4`
- `ntdll!RtlFreeHeap` at `0x180004f07`
- `ntdll!RtlFreeHeap` at `0x180004f24`
- `ntdll!RtlFreeHeap` at `0x180004d95`
- `ntdll!RtlFreeHeap` at `0x180004e1c`
- `ntdll!RtlFreeHeap` at `0x180004ed4`
- `ntdll!RtlFreeHeap` at `0x180004f07`
- `ntdll!RtlFreeHeap` at `0x180004f24`

## string_xrefs

- `0x180004dc4`: `SclDosPathToNtPath error with %ws. Error: 0x%08X`
- `0x180004ddb`: `SclpCanonicalizePaths`
- `0x180004e70`: `SclpCanonicalizePaths`
- `0x180004e59`: `CanonicalizeObjectPath error with %ws. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall SclpCanonicalizePaths(void *a1, _WORD *a2, _QWORD *a3)
{
  PVOID Heap; // r14
  int v5; // ebx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  _WORD *v8; // rcx
  __int64 v9; // rax
  WCHAR *v10; // rsi
  void *v11; // rdi
  unsigned __int64 v12; // r15
  int NextString; // eax
  int v14; // eax
  int v15; // esi
  int v16; // eax
  int v17; // edi
  __int64 v19; // [rsp+38h] [rbp-28h]
  PCWSTR SourceString; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  PVOID v22; // [rsp+50h] [rbp-10h] BYREF
  __int64 v23; // [rsp+58h] [rbp-8h] BYREF
  void *v24; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v25; // [rsp+B0h] [rbp+50h]
  unsigned __int64 v26; // [rsp+B8h] [rbp+58h]

  v25 = a3;
  v24 = a1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4u);
  if ( !Heap )
    return (unsigned int)-1073741801;
  v23 = 2;
  if ( !a2 )
    return (unsigned int)-1073741811;
  if ( *a2 )
  {
    v7 = 0;
    v8 = a2;
    do
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      if ( v9 )
        v7 += v9 + 1;
      v8 += v9 + 1;
    }
    while ( *v8 );
    v6 = 2 * v7 + 2;
  }
  else
  {
    v6 = 2;
  }
  v5 = 0;
  v26 = v6;
  v10 = 0;
  SourceString = 0;
  v11 = 0;
  v24 = 0;
  v12 = 0;
  v21 = 0;
  while ( 1 )
  {
    v22 = 0;
    NextString = SclMultiSzFindNextString((unsigned __int64)a2, v6, v12, &v21, &v22);
    if ( NextString == -2147483622 )
      break;
    if ( NextString < 0 )
      goto LABEL_32;
    if ( v10 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      SourceString = 0;
    }
    v12 = v21;
    v14 = SclDosPathToNtPath(v21, &SourceString);
    v15 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v19) = v14;
      SclLogGenericMessage(
        0,
        3,
        (int)SclEvent_Generic_Error,
        1027,
        (__int64)"SclpCanonicalizePaths",
        "SclDosPathToNtPath error with %ws. Error: 0x%08X",
        v12,
        v19);
      v5 = v15;
      v10 = (WCHAR *)SourceString;
      goto LABEL_20;
    }
    if ( v11 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      v24 = 0;
    }
    v10 = (WCHAR *)SourceString;
    v16 = CanonicalizeObjectPath(SourceString, (__int64)&v24);
    v17 = v16;
    if ( v16 == -1073741772 || v16 == -1073741766 )
    {
LABEL_27:
      v11 = v24;
LABEL_20:
      v6 = v26;
    }
    else
    {
      if ( v16 < 0 )
      {
        LODWORD(v19) = v16;
        SclLogGenericMessage(
          0,
          3,
          (int)SclEvent_Generic_Error,
          1049,
          (__int64)"SclpCanonicalizePaths",
          "CanonicalizeObjectPath error with %ws. Error: 0x%08X",
          v12,
          v19);
        v5 = v17;
        goto LABEL_27;
      }
      v11 = v24;
      v22 = Heap;
      NextString = SclMultiSzPrependString(Heap, (__int64)&v23);
      if ( NextString < 0 )
      {
LABEL_32:
        v5 = NextString;
        break;
      }
      if ( Heap )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = v22;
      v6 = v26;
    }
  }
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v5 >= 0 )
    *v25 = Heap;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004c88  mov     [rsp-38h+arg_8], rbx
0x180004c8d  mov     [rsp-38h+arg_10], r8
0x180004c92  mov     [rsp-38h+arg_0], rcx
0x180004c97  push    rbp
0x180004c98  push    rsi
0x180004c99  push    rdi
0x180004c9a  push    r12
0x180004c9c  push    r13
0x180004c9e  push    r14
0x180004ca0  push    r15
0x180004ca2  mov     rbp, rsp
0x180004ca5  sub     rsp, 60h
0x180004ca9  mov     rcx, gs:60h
0x180004cb2  mov     r13, rdx
0x180004cb5  mov     edx, 8; Flags
0x180004cba  mov     rcx, [rcx+30h]; HeapHandle
0x180004cbe  lea     r8d, [rdx-4]; Size
0x180004cc2  call    cs:__imp_RtlAllocateHeap
0x180004cc8  xor     r8d, r8d
0x180004ccb  mov     r14, rax
0x180004cce  test    rax, rax
0x180004cd1  jnz     short loc_180004CDD
0x180004cd3  mov     ebx, 0C0000017h
0x180004cd8  jmp     loc_180004F3C
0x180004cdd  mov     r12d, 2
0x180004ce3  mov     [rbp+var_8], r12
0x180004ce7  test    r13, r13
0x180004cea  jz      loc_180004F37
0x180004cf0  cmp     r8w, [r13+0]
0x180004cf5  jnz     short loc_180004CFC
0x180004cf7  mov     eax, r12d
0x180004cfa  jmp     short loc_180004D30
0x180004cfc  mov     rdx, r8
0x180004cff  mov     rcx, r13
0x180004d02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d06  inc     rax
0x180004d09  cmp     [rcx+rax*2], r8w
0x180004d0e  jnz     short loc_180004D06
0x180004d10  test    rax, rax
0x180004d13  jz      short loc_180004D1B
0x180004d15  inc     rdx
0x180004d18  add     rdx, rax
0x180004d1b  lea     rcx, [rcx+rax*2]
0x180004d1f  add     rcx, r12
0x180004d22  cmp     r8w, [rcx]
0x180004d26  jnz     short loc_180004D02
0x180004d28  lea     rax, ds:2[rdx*2]
0x180004d30  mov     ebx, r8d
0x180004d33  mov     [rbp+arg_18], rax
0x180004d37  mov     rsi, r8
0x180004d3a  mov     [rbp+SourceString], r8
0x180004d3e  mov     rdi, r8
0x180004d41  mov     [rbp+arg_0], r8
0x180004d45  mov     r15, r8
0x180004d48  mov     [rbp+var_18], r8
0x180004d4c  lea     rcx, [rbp+var_10]
0x180004d50  mov     [rbp+var_10], r8
0x180004d54  mov     [rsp+60h+var_40], rcx
0x180004d59  lea     r9, [rbp+var_18]
0x180004d5d  mov     rcx, r13
0x180004d60  mov     r8, r15
0x180004d63  mov     rdx, rax
0x180004d66  call    SclMultiSzFindNextString
0x180004d6b  cmp     eax, 8000001Ah
0x180004d70  jz      loc_180004EF0
0x180004d76  test    eax, eax
0x180004d78  js      loc_180004EEE
0x180004d7e  test    rsi, rsi
0x180004d81  jz      short loc_180004DA3
0x180004d83  mov     rcx, gs:60h
0x180004d8c  mov     r8, rsi; P
0x180004d8f  xor     edx, edx; Flags
0x180004d91  mov     rcx, [rcx+30h]; HeapHandle
0x180004d95  call    cs:__imp_RtlFreeHeap
0x180004d9b  mov     [rbp+SourceString], 0
0x180004da3  mov     r15, [rbp+var_18]
0x180004da7  lea     rdx, [rbp+SourceString]
0x180004dab  mov     rcx, r15
0x180004dae  call    SclDosPathToNtPath
0x180004db3  mov     esi, eax
0x180004db5  test    eax, eax
0x180004db7  jns     short loc_180004E05
0x180004db9  mov     dword ptr [rsp+60h+var_28], eax
0x180004dbd  lea     r8, SclEvent_Generic_Error
0x180004dc4  lea     rax, aScldospathtont; "SclDosPathToNtPath error with %ws. Erro"...
0x180004dcb  mov     [rsp+60h+var_30], r15
0x180004dd0  mov     [rsp+60h+var_38], rax
0x180004dd5  mov     r9d, 403h
0x180004ddb  lea     rax, aSclpcanonicali_0; "SclpCanonicalizePaths"
0x180004de2  mov     edx, 3
0x180004de7  xor     ecx, ecx
0x180004de9  mov     [rsp+60h+var_40], rax
0x180004dee  call    SclLogGenericMessage
0x180004df3  mov     ebx, esi
0x180004df5  mov     rsi, [rbp+SourceString]
0x180004df9  mov     rax, [rbp+arg_18]
0x180004dfd  xor     r8d, r8d
0x180004e00  jmp     loc_180004D4C
0x180004e05  test    rdi, rdi
0x180004e08  jz      short loc_180004E2A
0x180004e0a  mov     rcx, gs:60h
0x180004e13  mov     r8, rdi; P
0x180004e16  xor     edx, edx; Flags
0x180004e18  mov     rcx, [rcx+30h]; HeapHandle
0x180004e1c  call    cs:__imp_RtlFreeHeap
0x180004e22  mov     [rbp+arg_0], 0
0x180004e2a  mov     rsi, [rbp+SourceString]
0x180004e2e  lea     rdx, [rbp+arg_0]
0x180004e32  mov     rcx, rsi; SourceString
0x180004e35  call    CanonicalizeObjectPath
0x180004e3a  mov     edi, eax
0x180004e3c  cmp     eax, 0C0000034h
0x180004e41  jz      short loc_180004E8A
0x180004e43  cmp     eax, 0C000003Ah
0x180004e48  jz      short loc_180004E8A
0x180004e4a  test    eax, eax
0x180004e4c  jns     short loc_180004E93
0x180004e4e  mov     dword ptr [rsp+60h+var_28], eax
0x180004e52  lea     r8, SclEvent_Generic_Error
0x180004e59  lea     rax, aCanonicalizeob; "CanonicalizeObjectPath error with %ws. "...
0x180004e60  mov     [rsp+60h+var_30], r15
0x180004e65  mov     [rsp+60h+var_38], rax
0x180004e6a  mov     r9d, 419h
0x180004e70  lea     rax, aSclpcanonicali_0; "SclpCanonicalizePaths"
0x180004e77  mov     edx, 3
0x180004e7c  xor     ecx, ecx
0x180004e7e  mov     [rsp+60h+var_40], rax
0x180004e83  call    SclLogGenericMessage
0x180004e88  mov     ebx, edi
0x180004e8a  mov     rdi, [rbp+arg_0]
0x180004e8e  jmp     loc_180004DF9
0x180004e93  mov     rdi, [rbp+arg_0]
0x180004e97  lea     rax, [rbp+var_8]
0x180004e9b  mov     r8, rdi
0x180004e9e  mov     [rbp+var_10], r14
0x180004ea2  lea     r9, [rbp+var_10]
0x180004ea6  mov     [rsp+60h+var_40], rax; __int64
0x180004eab  mov     rdx, r12
0x180004eae  mov     rcx, r14; Src
0x180004eb1  call    SclMultiSzPrependString
0x180004eb6  xor     r8d, r8d
0x180004eb9  test    eax, eax
0x180004ebb  js      short loc_180004EEE
0x180004ebd  test    r14, r14
0x180004ec0  jz      short loc_180004EDD
0x180004ec2  mov     rcx, gs:60h
0x180004ecb  mov     r8, r14; P
0x180004ece  xor     edx, edx; Flags
0x180004ed0  mov     rcx, [rcx+30h]; HeapHandle
0x180004ed4  call    cs:__imp_RtlFreeHeap
0x180004eda  xor     r8d, r8d
0x180004edd  mov     r14, [rbp+var_10]
0x180004ee1  mov     r12, [rbp+var_8]
0x180004ee5  mov     rax, [rbp+arg_18]
0x180004ee9  jmp     loc_180004D4C
0x180004eee  mov     ebx, eax
0x180004ef0  test    rdi, rdi
0x180004ef3  jz      short loc_180004F0D
0x180004ef5  mov     rcx, gs:60h
0x180004efe  mov     r8, rdi; P
0x180004f01  xor     edx, edx; Flags
0x180004f03  mov     rcx, [rcx+30h]; HeapHandle
0x180004f07  call    cs:__imp_RtlFreeHeap
0x180004f0d  test    rsi, rsi
0x180004f10  jz      short loc_180004F2A
0x180004f12  mov     rcx, gs:60h
0x180004f1b  mov     r8, rsi; P
0x180004f1e  xor     edx, edx; Flags
0x180004f20  mov     rcx, [rcx+30h]; HeapHandle
0x180004f24  call    cs:__imp_RtlFreeHeap
0x180004f2a  test    ebx, ebx
0x180004f2c  js      short loc_180004F3C
0x180004f2e  mov     rax, [rbp+arg_10]
0x180004f32  mov     [rax], r14
0x180004f35  jmp     short loc_180004F3C
0x180004f37  mov     ebx, 0C000000Dh
0x180004f3c  mov     eax, ebx
0x180004f3e  mov     rbx, [rsp+60h+arg_8]
0x180004f46  add     rsp, 60h
0x180004f4a  pop     r15
0x180004f4c  pop     r14
0x180004f4e  pop     r13
0x180004f50  pop     r12
0x180004f52  pop     rdi
0x180004f53  pop     rsi
0x180004f54  pop     rbp
0x180004f55  retn
```
