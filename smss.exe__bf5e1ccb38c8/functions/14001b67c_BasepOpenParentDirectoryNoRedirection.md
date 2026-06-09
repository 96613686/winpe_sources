# BasepOpenParentDirectoryNoRedirection

- ea: `0x14001b67c`
- end: `0x14001b7fb`
- name: `BasepOpenParentDirectoryNoRedirection`
- size: `383`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14001a3fc`

## callees

- `0x14001a39c`
- `0x14001b450`
- `0x14001b67c`
- `0x14001b804`
- `0x14001cabc`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x14001b7a5`
- `ntdll!NtClose` at `0x14001b7a5`
- `ntdll!RtlAllocateHeap` at `0x14001b6eb`
- `ntdll!RtlAllocateHeap` at `0x14001b6eb`
- `ntdll!RtlFreeHeap` at `0x14001b7cc`
- `ntdll!RtlFreeHeap` at `0x14001b7cc`

## pseudocode

```c
__int64 __fastcall BasepOpenParentDirectoryNoRedirection(PCUNICODE_STRING SourceString, _QWORD *a2)
{
  int FileRedirectionStatus; // ebx
  SIZE_T v5; // r8
  wchar_t *Heap; // rax
  wchar_t *v7; // rdi
  wchar_t *v8; // rbp
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rcx
  __int64 v14; // rcx
  void *File2; // rax
  void *v16; // rsi
  _OWORD v18[2]; // [rsp+30h] [rbp-268h] BYREF
  char v19; // [rsp+50h] [rbp-248h] BYREF

  memset(v18, 0, sizeof(v18));
  if ( !SourceString->Length )
    return (unsigned int)-1073741811;
  v5 = SourceString->Length + 2LL;
  if ( v5 <= 0x20A )
  {
    v8 = 0;
    v7 = (wchar_t *)&v19;
  }
  else
  {
    Heap = (wchar_t *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), KernelBaseGlobalData, v5);
    v7 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    v8 = Heap;
  }
  v9 = RtlStringCbCopyUnicodeString(v7, SourceString->Length + 2LL, SourceString);
  FileRedirectionStatus = v9;
  if ( v9 < 0 )
  {
    v13 = (unsigned int)v9;
LABEL_10:
    BaseSetLastNTError(v13);
    goto LABEL_23;
  }
  LODWORD(v14) = SourceString->Length >> 1;
  do
    v14 = (unsigned int)(v14 - 1);
  while ( (int)v14 >= 0 && v7[(unsigned int)v14] == 92 );
  if ( (int)v14 > 0 )
  {
    while ( v7[v14] != 92 )
    {
      v14 = (unsigned int)(v14 - 1);
      if ( (int)v14 < 0 )
        goto LABEL_15;
    }
    v7[v14 + 1] = 0;
    LODWORD(v18[0]) = 32;
    DWORD2(v18[0]) = 0x2000000;
    File2 = (void *)CreateFile2((_DWORD)v7, v10, v11, v12, (__int64)v18);
    v16 = File2;
    if ( File2 == (void *)-1LL )
      goto LABEL_23;
    FileRedirectionStatus = BasepGetFileRedirectionStatus((__int64)v7, File2);
    if ( FileRedirectionStatus < 0 )
    {
      NtClose(v16);
      v13 = (unsigned int)FileRedirectionStatus;
      goto LABEL_10;
    }
    *a2 = v16;
  }
  else
  {
LABEL_15:
    FileRedirectionStatus = -1073741811;
  }
LABEL_23:
  if ( v8 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
  return (unsigned int)FileRedirectionStatus;
}

```

## disassembly

```asm
0x14001b67c  mov     [rsp+arg_10], rbx
0x14001b681  push    rbp
0x14001b682  push    rsi
0x14001b683  push    rdi
0x14001b684  push    r14
0x14001b686  push    r15
0x14001b688  sub     rsp, 270h
0x14001b68f  mov     rax, cs:__security_cookie
0x14001b696  xor     rax, rsp
0x14001b699  mov     [rsp+298h+var_38], rax
0x14001b6a1  xorps   xmm0, xmm0
0x14001b6a4  xor     r15d, r15d
0x14001b6a7  mov     r14, rdx
0x14001b6aa  mov     rsi, rcx
0x14001b6ad  movups  [rsp+298h+var_268], xmm0
0x14001b6b2  movups  [rsp+298h+var_258], xmm0
0x14001b6b7  cmp     [rcx], r15w
0x14001b6bb  jnz     short loc_14001B6C7
0x14001b6bd  mov     ebx, 0C000000Dh
0x14001b6c2  jmp     loc_14001B7D2
0x14001b6c7  movzx   r8d, word ptr [rcx]
0x14001b6cb  add     r8, 2; Size
0x14001b6cf  cmp     r8, 20Ah
0x14001b6d6  jbe     short loc_14001B708
0x14001b6d8  mov     rcx, gs:60h
0x14001b6e1  mov     edx, cs:KernelBaseGlobalData; Flags
0x14001b6e7  mov     rcx, [rcx+30h]; HeapHandle
0x14001b6eb  call    cs:__imp_RtlAllocateHeap
0x14001b6f1  mov     rdi, rax
0x14001b6f4  test    rax, rax
0x14001b6f7  jnz     short loc_14001B703
0x14001b6f9  mov     ebx, 0C0000017h
0x14001b6fe  jmp     loc_14001B7D2
0x14001b703  mov     rbp, rax
0x14001b706  jmp     short loc_14001B710
0x14001b708  mov     rbp, r15
0x14001b70b  lea     rdi, [rsp+298h+var_248]
0x14001b710  movzx   edx, word ptr [rsi]
0x14001b713  mov     r8, rsi; SourceString
0x14001b716  add     rdx, 2; cbDest
0x14001b71a  mov     rcx, rdi; pszDest
0x14001b71d  call    RtlStringCbCopyUnicodeString
0x14001b722  mov     ebx, eax
0x14001b724  test    eax, eax
0x14001b726  jns     short loc_14001B734
0x14001b728  mov     ecx, eax
0x14001b72a  call    BaseSetLastNTError
0x14001b72f  jmp     loc_14001B7B5
0x14001b734  movzx   ecx, word ptr [rsi]
0x14001b737  shr     ecx, 1
0x14001b739  jmp     short loc_14001B742
0x14001b73b  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x14001b740  jnz     short loc_14001B747
0x14001b742  sub     ecx, 1
0x14001b745  jns     short loc_14001B73B
0x14001b747  test    ecx, ecx
0x14001b749  jg      short loc_14001B752
0x14001b74b  mov     ebx, 0C000000Dh
0x14001b750  jmp     short loc_14001B7B5
0x14001b752  cmp     word ptr [rdi+rcx*2], 5Ch ; '\'
0x14001b757  jz      short loc_14001B760
0x14001b759  sub     ecx, 1
0x14001b75c  jns     short loc_14001B752
0x14001b75e  jmp     short loc_14001B74B
0x14001b760  mov     [rdi+rcx*2+2], r15w
0x14001b766  lea     rax, [rsp+298h+var_268]
0x14001b76b  mov     rcx, rdi
0x14001b76e  mov     [rsp+298h+var_278], rax
0x14001b773  mov     dword ptr [rsp+298h+var_268], 20h ; ' '
0x14001b77b  mov     dword ptr [rsp+298h+var_268+8], 2000000h
0x14001b783  call    CreateFile2
0x14001b788  mov     rsi, rax
0x14001b78b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b78f  jz      short loc_14001B7B5
0x14001b791  mov     rdx, rax
0x14001b794  mov     rcx, rdi
0x14001b797  call    BasepGetFileRedirectionStatus
0x14001b79c  mov     ebx, eax
0x14001b79e  test    eax, eax
0x14001b7a0  jns     short loc_14001B7B2
0x14001b7a2  mov     rcx, rsi; Handle
0x14001b7a5  call    cs:__imp_NtClose
0x14001b7ab  mov     ecx, ebx
0x14001b7ad  jmp     loc_14001B72A
0x14001b7b2  mov     [r14], rsi
0x14001b7b5  test    rbp, rbp
0x14001b7b8  jz      short loc_14001B7D2
0x14001b7ba  mov     rcx, gs:60h
0x14001b7c3  mov     r8, rbp; BaseAddress
0x14001b7c6  xor     edx, edx; Flags
0x14001b7c8  mov     rcx, [rcx+30h]; HeapHandle
0x14001b7cc  call    cs:__imp_RtlFreeHeap
0x14001b7d2  mov     eax, ebx
0x14001b7d4  mov     rcx, [rsp+298h+var_38]
0x14001b7dc  xor     rcx, rsp; StackCookie
0x14001b7df  call    __security_check_cookie
0x14001b7e4  mov     rbx, [rsp+298h+arg_10]
0x14001b7ec  add     rsp, 270h
0x14001b7f3  pop     r15
0x14001b7f5  pop     r14
0x14001b7f7  pop     rdi
0x14001b7f8  pop     rsi
0x14001b7f9  pop     rbp
0x14001b7fa  retn
```
