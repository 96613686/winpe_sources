# SmpCheckFolderForRedirections

- ea: `0x1400130f4`
- end: `0x1400132d2`
- name: `SmpCheckFolderForRedirections`
- size: `478`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140015ef8`
- `0x140016958`
- `0x140016b94`

## callees

- `0x1400130f4`
- `0x1400158e4`
- `0x14001598c`
- `0x14001a090`
- `0x14001cc11`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140013134`
- `ntdll!RtlInitUnicodeString` at `0x140013134`
- `ntdll!NtClose` at `0x140013197`
- `ntdll!NtClose` at `0x140013197`
- `ntdll!RtlAllocateHeap` at `0x1400131eb`
- `ntdll!RtlAllocateHeap` at `0x1400131eb`
- `ntdll!RtlFreeHeap` at `0x1400131b7`
- `ntdll!RtlFreeHeap` at `0x1400131b7`

## pseudocode

```c
bool __fastcall SmpCheckFolderForRedirections(unsigned __int16 *a1, HANDLE *a2)
{
  bool IsNotARedirection; // si
  int FileAttributesW; // eax
  unsigned __int8 v6; // r14
  __int64 v7; // rbx
  __int64 v9; // r15
  PWSTR Buffer; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v12; // [rsp+40h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp+48h] BYREF

  Handle = (HANDLE)-1LL;
  IsNotARedirection = 0;
  memset(&v12, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( *a1 >= 0xEu )
  {
    FileAttributesW = InternalGetFileAttributesW(*((PCWSTR *)a1 + 1));
    if ( FileAttributesW == -1 )
      goto LABEL_6;
    if ( (FileAttributesW & 0x400) != 0 )
      goto LABEL_11;
    if ( (FileAttributesW & 0x10) == 0 )
LABEL_6:
      v6 = 0;
    else
      v6 = 1;
    v7 = (*a1 >> 1) - 1;
    if ( !v6 )
    {
      if ( *a1 >> 1 == 1 )
        goto LABEL_11;
      while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v7) != 92 )
      {
        v7 = (unsigned int)(v7 - 1);
        if ( !(_DWORD)v7 )
          goto LABEL_11;
      }
    }
    DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                        *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                                        SmBaseTag,
                                        2LL * (unsigned int)(v7 + 3));
    if ( DestinationString.Buffer )
    {
      v9 = (unsigned int)(v7 + 1);
      memcpy_0(DestinationString.Buffer, *((const void **)a1 + 1), 2 * v9);
      Buffer = DestinationString.Buffer;
      DestinationString.Length = 2 * v7 + 2;
      DestinationString.MaximumLength = 2 * v7 + 4;
      if ( v6 && DestinationString.Buffer[v7] != 92 )
      {
        DestinationString.Buffer[v9] = 92;
        LODWORD(v7) = v7 + 1;
        ++DestinationString.Length;
        ++DestinationString.MaximumLength;
        Buffer = DestinationString.Buffer;
      }
      Buffer[(unsigned int)(v7 + 1)] = 0;
      v12.RootDirectory = 0;
      v12.Length = 48;
      v12.ObjectName = &DestinationString;
      v12.Attributes = 64;
      *(_OWORD *)&v12.SecurityDescriptor = 0;
      if ( SmpOpenTargetFile(&Handle, 0x100080u, &v12, 0, v6 + 2) >= 0 )
      {
        IsNotARedirection = SmpPathCanBeTrustedIsNotARedirection(Handle, &DestinationString.Length, 1);
        if ( IsNotARedirection )
        {
          *a2 = Handle;
          goto LABEL_13;
        }
      }
    }
  }
LABEL_11:
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
LABEL_13:
  if ( DestinationString.Buffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, DestinationString.Buffer);
  return IsNotARedirection;
}

```

## disassembly

```asm
0x1400130f4  push    rbp
0x1400130f6  push    rbx
0x1400130f7  push    rsi
0x1400130f8  push    rdi
0x1400130f9  push    r12
0x1400130fb  push    r13
0x1400130fd  push    r14
0x1400130ff  push    r15
0x140013101  mov     rbp, rsp
0x140013104  sub     rsp, 78h
0x140013108  xorps   xmm0, xmm0
0x14001310b  mov     [rbp+Handle], 0FFFFFFFFFFFFFFFFh
0x140013113  mov     r13, rdx
0x140013116  mov     rdi, rcx
0x140013119  movups  [rbp+var_28], xmm0
0x14001311d  xor     eax, eax
0x14001311f  lea     rcx, [rbp+DestinationString]; DestinationString
0x140013123  xor     edx, edx; SourceString
0x140013125  xor     sil, sil
0x140013128  movups  [rbp+var_28+0Ch], xmm0
0x14001312c  movups  xmmword ptr [rbp+var_38], xmm0
0x140013130  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140013134  call    cs:__imp_RtlInitUnicodeString
0x14001313a  cmp     word ptr [rdi], 0Eh
0x14001313e  jb      short loc_14001318D
0x140013140  mov     rcx, [rdi+8]; Name
0x140013144  call    InternalGetFileAttributesW
0x140013149  or      r8d, 0FFFFFFFFh
0x14001314d  mov     ecx, 1
0x140013152  cmp     eax, r8d
0x140013155  jz      short loc_140013166
0x140013157  bt      eax, 0Ah
0x14001315b  jb      short loc_14001318D
0x14001315d  test    al, 10h
0x14001315f  jz      short loc_140013166
0x140013161  mov     r14b, cl
0x140013164  jmp     short loc_140013169
0x140013166  xor     r14b, r14b
0x140013169  movzx   ebx, word ptr [rdi]
0x14001316c  mov     edx, 5Ch ; '\'
0x140013171  shr     ebx, 1
0x140013173  sub     ebx, ecx
0x140013175  test    r14b, r14b
0x140013178  jnz     short loc_1400131D1
0x14001317a  test    ebx, ebx
0x14001317c  jz      short loc_14001318D
0x14001317e  mov     rcx, [rdi+8]
0x140013182  cmp     [rcx+rbx*2], dx
0x140013186  jz      short loc_1400131D1
0x140013188  add     ebx, r8d
0x14001318b  jnz     short loc_140013182
0x14001318d  mov     rcx, [rbp+Handle]; Handle
0x140013191  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140013195  jz      short loc_14001319D
0x140013197  call    cs:__imp_NtClose
0x14001319d  cmp     [rbp+DestinationString.Buffer], 0
0x1400131a2  jz      short loc_1400131BD
0x1400131a4  mov     rcx, gs:60h
0x1400131ad  xor     edx, edx; Flags
0x1400131af  mov     r8, [rbp+DestinationString.Buffer]; BaseAddress
0x1400131b3  mov     rcx, [rcx+30h]; HeapHandle
0x1400131b7  call    cs:__imp_RtlFreeHeap
0x1400131bd  mov     al, sil
0x1400131c0  add     rsp, 78h
0x1400131c4  pop     r15
0x1400131c6  pop     r14
0x1400131c8  pop     r13
0x1400131ca  pop     r12
0x1400131cc  pop     rdi
0x1400131cd  pop     rsi
0x1400131ce  pop     rbx
0x1400131cf  pop     rbp
0x1400131d0  retn
0x1400131d1  mov     rcx, gs:60h
0x1400131da  lea     r8d, [rbx+3]
0x1400131de  mov     edx, cs:SmBaseTag; Flags
0x1400131e4  add     r8, r8; Size
0x1400131e7  mov     rcx, [rcx+30h]; HeapHandle
0x1400131eb  call    cs:__imp_RtlAllocateHeap
0x1400131f1  mov     [rbp+DestinationString.Buffer], rax
0x1400131f5  mov     rcx, rax; void *
0x1400131f8  test    rax, rax
0x1400131fb  jz      short loc_14001318D
0x1400131fd  mov     rdx, [rdi+8]; Src
0x140013201  lea     r15d, [rbx+1]
0x140013205  lea     r12, [r15+r15]
0x140013209  mov     r8, r12; MaxCount
0x14001320c  call    memcpy_0
0x140013211  mov     rdx, [rbp+DestinationString.Buffer]
0x140013215  movzx   ecx, bx
0x140013218  add     cx, cx
0x14001321b  mov     r8d, 2
0x140013221  lea     eax, [r8+rcx]
0x140013225  add     cx, 4
0x140013229  mov     [rbp+DestinationString.Length], ax
0x14001322d  lea     edi, [r8-1]
0x140013231  mov     [rbp+DestinationString.MaximumLength], cx
0x140013235  test    r14b, r14b
0x140013238  jz      short loc_140013257
0x14001323a  lea     ecx, [rdi+5Bh]
0x14001323d  cmp     [rdx+rbx*2], cx
0x140013241  jz      short loc_140013257
0x140013243  mov     [r12+rdx], cx
0x140013248  mov     ebx, r15d
0x14001324b  add     [rbp+DestinationString.Length], di
0x14001324f  add     [rbp+DestinationString.MaximumLength], di
0x140013253  mov     rdx, [rbp+DestinationString.Buffer]
0x140013257  xor     eax, eax
0x140013259  lea     ecx, [rbx+1]
0x14001325c  mov     [rdx+rcx*2], ax
0x140013260  xorps   xmm0, xmm0
0x140013263  mov     qword ptr [rbp+var_38+8], rax
0x140013267  lea     rcx, [rbp+Handle]; int
0x14001326b  lea     rax, [rbp+DestinationString]
0x14001326f  mov     [rbp+var_38], 30h ; '0'
0x140013276  mov     qword ptr [rbp+var_28], rax
0x14001327a  xor     r9d, r9d; int
0x14001327d  movzx   eax, r14b
0x140013281  mov     edx, 100080h; int
0x140013286  add     eax, r8d
0x140013289  mov     dword ptr [rbp+var_28+8], 40h ; '@'
0x140013290  lea     r8, [rbp+var_38]; int
0x140013294  mov     [rsp+78h+var_58], eax; ULONG
0x140013298  movdqu  [rbp+var_18], xmm0
0x14001329d  call    SmpOpenTargetFile
0x1400132a2  test    eax, eax
0x1400132a4  js      loc_14001318D
0x1400132aa  mov     rcx, [rbp+Handle]
0x1400132ae  lea     rdx, [rbp+DestinationString]
0x1400132b2  mov     r8d, edi
0x1400132b5  call    SmpPathCanBeTrustedIsNotARedirection
0x1400132ba  mov     sil, al
0x1400132bd  test    al, al
0x1400132bf  jz      loc_14001318D
0x1400132c5  mov     rcx, [rbp+Handle]
0x1400132c9  mov     [r13+0], rcx
0x1400132cd  jmp     loc_14001319D
```
