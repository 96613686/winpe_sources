# SmpCreatePagingFileDescriptor

- ea: `0x14000fa74`
- end: `0x14000fcf2`
- name: `SmpCreatePagingFileDescriptor`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fcf8`

## callees

- `0x1400010ec`
- `0x140003114`
- `0x140004610`
- `0x14000d4c0`
- `0x14000fa74`
- `0x14001106c`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x14000fc0a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x14000fc0a`
- `ntdll!RtlAllocateHeap` at `0x14000fba4`
- `ntdll!RtlAllocateHeap` at `0x14000fba4`
- `ntdll!RtlFreeHeap` at `0x14000fc60`
- `ntdll!RtlFreeHeap` at `0x14000fc60`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb5d`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb67`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb88`
- `ntdll!RtlFreeUnicodeString` at `0x14000fbb6`
- `ntdll!RtlFreeUnicodeString` at `0x14000fc48`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb5d`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb67`
- `ntdll!RtlFreeUnicodeString` at `0x14000fb88`
- `ntdll!RtlFreeUnicodeString` at `0x14000fbb6`
- `ntdll!RtlFreeUnicodeString` at `0x14000fc48`

## string_xrefs

- `0x14000fab5`: `SmpCreatePagingFileDescriptor`
- `0x14000faff`: `SmpCreatePagingFileDescriptor`
- `0x14000fb48`: `SmpCreatePagingFileDescriptor`
- `0x14000fc2b`: `SmpCreatePagingFileDescriptor`

## pseudocode

```c
__int64 __fastcall SmpCreatePagingFileDescriptor(__int64 a1)
{
  unsigned int v2; // ebx
  int v4; // eax
  __int64 v5; // r8
  int v6; // eax
  int v7; // esi
  _QWORD *Heap; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  WCHAR v12; // ax
  _QWORD *v13; // rcx
  _QWORD *v14; // rcx
  UNICODE_STRING String; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-10h] BYREF
  ULONG Value; // [rsp+78h] [rbp+28h] BYREF
  ULONG v18; // [rsp+80h] [rbp+30h] BYREF

  Value = 0;
  v18 = 0;
  UnicodeString = 0;
  String = 0;
  if ( (unsigned int)SmpNumberOfPagefileDescriptors >= 0x10 )
  {
    v2 = -1073741673;
    SmLogFailureInt((unsigned int)"SmpCreatePagingFileDescriptor", 953, SmpNumberOfPagefileDescriptors, 0, -1073741673);
    return v2;
  }
  v4 = SmpParseCommandLine(a1, 0, &UnicodeString, 0, &String);
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( a1 )
      v5 = *(_QWORD *)(a1 + 8);
    else
      v5 = 0;
    SmpLogFailureString("SmpCreatePagingFileDescriptor", 973, v5, (unsigned int)v4);
    return v2;
  }
  SmpRegistrySpecifierPresent = 1;
  Value = 0;
  v18 = 0;
  if ( !String.Buffer )
    goto LABEL_14;
  v6 = SmpParseSwapOrPageFileArguments(&String, &Value, &v18);
  v2 = v6;
  if ( v6 < 0 )
  {
    SmpLogFailure("SmpCreatePagingFileDescriptor", 1006, (unsigned int)v6);
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&String);
    return v2;
  }
  if ( !Value || (v7 = 0, !v18) )
LABEL_14:
    v7 = 1;
  RtlFreeUnicodeString(&String);
  Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 8u, 0x60u);
  v9 = Heap;
  if ( !Heap )
  {
    RtlFreeUnicodeString(&UnicodeString);
    return 3221225495LL;
  }
  *((_OWORD *)Heap + 2) = *(_OWORD *)a1;
  *((struct _UNICODE_STRING *)Heap + 1) = UnicodeString;
  v10 = Heap[3];
  Heap[7] = (unsigned __int64)Value << 20;
  Heap[6] = (unsigned __int64)Value << 20;
  v11 = v18;
  *((_DWORD *)v9 + 23) &= ~2u;
  v9[8] = v11 << 20;
  *((_DWORD *)v9 + 23) |= 2 * v7;
  v12 = RtlUpcaseUnicodeChar(*(_WORD *)(v10 + 8));
  *(_WORD *)(v9[3] + 8LL) = v12;
  if ( v12 == 63 )
  {
    if ( SmpAnyDriveDescriptorCreated == 1 )
    {
      SmpLogFailureString("SmpCreatePagingFileDescriptor", 1056, *(_QWORD *)(a1 + 8), 3221225485LL);
      RtlFreeUnicodeString(&UnicodeString);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v9);
      return 3221225485LL;
    }
    *((_DWORD *)v9 + 23) |= 4u;
    SmpAnyDriveDescriptorCreated = 1;
  }
  if ( (*((_BYTE *)v9 + 92) & 2) == 0 || v12 != 63 && v12 != SmpOsVolumeLetter )
  {
    v14 = (_QWORD *)qword_140030C48;
    if ( *(PVOID **)qword_140030C48 == &SmpPagingFileDescriptorList )
    {
      *v9 = &SmpPagingFileDescriptorList;
      v9[1] = v14;
      *v14 = v9;
      qword_140030C48 = (__int64)v9;
      goto LABEL_29;
    }
LABEL_27:
    __fastfail(3u);
  }
  v13 = SmpPagingFileDescriptorList;
  if ( *((PVOID **)SmpPagingFileDescriptorList + 1) != &SmpPagingFileDescriptorList )
    goto LABEL_27;
  *v9 = SmpPagingFileDescriptorList;
  v9[1] = &SmpPagingFileDescriptorList;
  v13[1] = v9;
  SmpPagingFileDescriptorList = v9;
LABEL_29:
  ++SmpNumberOfPagefileDescriptors;
  return 0;
}

```

## disassembly

```asm
0x14000fa74  mov     [rsp-18h+arg_0], rbx
0x14000fa79  push    rbp
0x14000fa7a  push    rsi
0x14000fa7b  push    rdi
0x14000fa7c  mov     rbp, rsp
0x14000fa7f  sub     rsp, 50h
0x14000fa83  mov     eax, cs:SmpNumberOfPagefileDescriptors
0x14000fa89  xor     r9d, r9d
0x14000fa8c  mov     [rbp+Value], 0
0x14000fa93  xorps   xmm0, xmm0
0x14000fa96  mov     [rbp+arg_10], 0
0x14000fa9d  xorps   xmm1, xmm1
0x14000faa0  mov     rdi, rcx
0x14000faa3  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14000faa7  movups  xmmword ptr [rbp+String.Length], xmm1
0x14000faab  cmp     eax, 10h
0x14000faae  jb      short loc_14000FAD4
0x14000fab0  mov     ebx, 0C0000097h
0x14000fab5  lea     rcx, aSmpcreatepagin_0; "SmpCreatePagingFileDescriptor"
0x14000fabc  mov     r8d, eax
0x14000fabf  mov     dword ptr [rsp+50h+var_30], ebx
0x14000fac3  mov     edx, 3B9h
0x14000fac8  call    SmLogFailureInt
0x14000facd  mov     eax, ebx
0x14000facf  jmp     loc_14000FCE5
0x14000fad4  lea     rax, [rbp+String]
0x14000fad8  xor     edx, edx
0x14000fada  lea     r8, [rbp+UnicodeString]
0x14000fade  mov     [rsp+50h+var_30], rax
0x14000fae3  call    SmpParseCommandLine
0x14000fae8  mov     ebx, eax
0x14000faea  test    eax, eax
0x14000faec  jns     short loc_14000FB12
0x14000faee  test    rdi, rdi
0x14000faf1  jz      short loc_14000FAF9
0x14000faf3  mov     r8, [rdi+8]
0x14000faf7  jmp     short loc_14000FAFC
0x14000faf9  xor     r8d, r8d
0x14000fafc  mov     r9d, ebx
0x14000faff  lea     rcx, aSmpcreatepagin_0; "SmpCreatePagingFileDescriptor"
0x14000fb06  mov     edx, 3CDh
0x14000fb0b  call    SmpLogFailureString
0x14000fb10  jmp     short loc_14000FACD
0x14000fb12  cmp     [rbp+String.Buffer], 0
0x14000fb17  mov     cs:SmpRegistrySpecifierPresent, 1
0x14000fb1e  mov     [rbp+Value], 0
0x14000fb25  mov     [rbp+arg_10], 0
0x14000fb2c  jz      short loc_14000FB7F
0x14000fb2e  lea     r8, [rbp+arg_10]; PULONG
0x14000fb32  lea     rdx, [rbp+Value]; Value
0x14000fb36  lea     rcx, [rbp+String]; String
0x14000fb3a  call    SmpParseSwapOrPageFileArguments
0x14000fb3f  mov     ebx, eax
0x14000fb41  test    eax, eax
0x14000fb43  jns     short loc_14000FB72
0x14000fb45  mov     r8d, eax
0x14000fb48  lea     rcx, aSmpcreatepagin_0; "SmpCreatePagingFileDescriptor"
0x14000fb4f  mov     edx, 3EEh
0x14000fb54  call    SmpLogFailure
0x14000fb59  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14000fb5d  call    cs:__imp_RtlFreeUnicodeString
0x14000fb63  lea     rcx, [rbp+String]; UnicodeString
0x14000fb67  call    cs:__imp_RtlFreeUnicodeString
0x14000fb6d  jmp     loc_14000FACD
0x14000fb72  cmp     [rbp+Value], 0
0x14000fb76  jz      short loc_14000FB7F
0x14000fb78  xor     esi, esi
0x14000fb7a  cmp     [rbp+arg_10], esi
0x14000fb7d  jnz     short loc_14000FB84
0x14000fb7f  mov     esi, 1
0x14000fb84  lea     rcx, [rbp+String]; UnicodeString
0x14000fb88  call    cs:__imp_RtlFreeUnicodeString
0x14000fb8e  mov     rcx, gs:60h
0x14000fb97  mov     edx, 8; Flags
0x14000fb9c  mov     rcx, [rcx+30h]; HeapHandle
0x14000fba0  lea     r8d, [rdx+58h]; Size
0x14000fba4  call    cs:__imp_RtlAllocateHeap
0x14000fbaa  mov     rbx, rax
0x14000fbad  test    rax, rax
0x14000fbb0  jnz     short loc_14000FBC6
0x14000fbb2  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14000fbb6  call    cs:__imp_RtlFreeUnicodeString
0x14000fbbc  mov     eax, 0C0000017h
0x14000fbc1  jmp     loc_14000FCE5
0x14000fbc6  movups  xmm0, xmmword ptr [rdi]
0x14000fbc9  movdqu  xmmword ptr [rax+20h], xmm0
0x14000fbce  movups  xmm1, xmmword ptr [rbp+UnicodeString.Length]
0x14000fbd2  movdqu  xmmword ptr [rax+10h], xmm1
0x14000fbd7  mov     eax, [rbp+Value]
0x14000fbda  mov     rcx, [rbx+18h]
0x14000fbde  shl     rax, 14h
0x14000fbe2  mov     [rbx+38h], rax
0x14000fbe6  mov     eax, [rbp+Value]
0x14000fbe9  shl     rax, 14h
0x14000fbed  mov     [rbx+30h], rax
0x14000fbf1  mov     eax, [rbp+arg_10]
0x14000fbf4  and     dword ptr [rbx+5Ch], 0FFFFFFFDh
0x14000fbf8  shl     rax, 14h
0x14000fbfc  mov     [rbx+40h], rax
0x14000fc00  lea     eax, [rsi+rsi]
0x14000fc03  or      [rbx+5Ch], eax
0x14000fc06  movzx   ecx, word ptr [rcx+8]; SourceCharacter
0x14000fc0a  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000fc10  mov     rcx, [rbx+18h]
0x14000fc14  mov     [rcx+8], ax
0x14000fc18  cmp     ax, 3Fh ; '?'
0x14000fc1c  jnz     short loc_14000FC75
0x14000fc1e  cmp     cs:SmpAnyDriveDescriptorCreated, 1
0x14000fc25  jnz     short loc_14000FC6A
0x14000fc27  mov     r8, [rdi+8]
0x14000fc2b  lea     rcx, aSmpcreatepagin_0; "SmpCreatePagingFileDescriptor"
0x14000fc32  mov     esi, 0C000000Dh
0x14000fc37  mov     edx, 420h
0x14000fc3c  mov     r9d, esi
0x14000fc3f  call    SmpLogFailureString
0x14000fc44  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14000fc48  call    cs:__imp_RtlFreeUnicodeString
0x14000fc4e  mov     rcx, gs:60h
0x14000fc57  mov     r8, rbx; BaseAddress
0x14000fc5a  xor     edx, edx; Flags
0x14000fc5c  mov     rcx, [rcx+30h]; HeapHandle
0x14000fc60  call    cs:__imp_RtlFreeHeap
0x14000fc66  mov     eax, esi
0x14000fc68  jmp     short loc_14000FCE5
0x14000fc6a  or      dword ptr [rbx+5Ch], 4
0x14000fc6e  mov     cs:SmpAnyDriveDescriptorCreated, 1
0x14000fc75  test    byte ptr [rbx+5Ch], 2
0x14000fc79  jz      short loc_14000FCB2
0x14000fc7b  cmp     ax, 3Fh ; '?'
0x14000fc7f  jz      short loc_14000FC8A
0x14000fc81  cmp     ax, cs:SmpOsVolumeLetter
0x14000fc88  jnz     short loc_14000FCB2
0x14000fc8a  mov     rcx, cs:SmpPagingFileDescriptorList
0x14000fc91  lea     rax, SmpPagingFileDescriptorList
0x14000fc98  cmp     [rcx+8], rax
0x14000fc9c  jnz     short loc_14000FCC5
0x14000fc9e  mov     [rbx], rcx
0x14000fca1  mov     [rbx+8], rax
0x14000fca5  mov     [rcx+8], rbx
0x14000fca9  mov     cs:SmpPagingFileDescriptorList, rbx
0x14000fcb0  jmp     short loc_14000FCDD
0x14000fcb2  mov     rcx, cs:qword_140030C48
0x14000fcb9  lea     rax, SmpPagingFileDescriptorList
0x14000fcc0  cmp     [rcx], rax
0x14000fcc3  jz      short loc_14000FCCC
0x14000fcc5  mov     ecx, 3
0x14000fcca  int     29h; Win8: RtlFailFast(ecx)
0x14000fccc  mov     [rbx], rax
0x14000fccf  mov     [rbx+8], rcx
0x14000fcd3  mov     [rcx], rbx
0x14000fcd6  mov     cs:qword_140030C48, rbx
0x14000fcdd  inc     cs:SmpNumberOfPagefileDescriptors
0x14000fce3  xor     eax, eax
0x14000fce5  mov     rbx, [rsp+50h+arg_0]
0x14000fcea  add     rsp, 50h
0x14000fcee  pop     rdi
0x14000fcef  pop     rsi
0x14000fcf0  pop     rbp
0x14000fcf1  retn
```
