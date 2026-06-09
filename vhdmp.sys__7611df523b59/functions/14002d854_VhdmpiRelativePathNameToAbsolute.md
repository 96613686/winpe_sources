# VhdmpiRelativePathNameToAbsolute

- ea: `0x14002d854`
- end: `0x14002da11`
- name: `VhdmpiRelativePathNameToAbsolute`
- size: `445`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, USHORT *NewLength)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d80c`
- `0x1400b0104`
- `0x1400c6ba0`
- `0x1400c7038`

## callees

- `0x140019310`
- `0x14002d854`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d8ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d972`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d98a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d8ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d972`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002d98a`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14002d9a6`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14002d9a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d9f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d9d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d9f1`
- `ntoskrnl!ExAllocatePool2` at `0x14002d87e`
- `ntoskrnl!ExAllocatePool2` at `0x14002d941`
- `ntoskrnl!ExAllocatePool2` at `0x14002d87e`
- `ntoskrnl!ExAllocatePool2` at `0x14002d941`

## pseudocode

```c
__int64 __fastcall VhdmpiRelativePathNameToAbsolute(PCUNICODE_STRING Source, PCUNICODE_STRING a2, USHORT *NewLength)
{
  __int64 Length; // rdx
  WCHAR *Pool2; // rax
  WCHAR *v8; // rbp
  NTSTATUS appended; // ebx
  void *v10; // rsi
  unsigned int v11; // edx
  __int64 v12; // rcx
  USHORT v13; // dx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  __int64 v16; // rax
  int LongPathDecorationAppropriate; // eax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-38h] BYREF

  Length = Source->Length;
  Destination = 0;
  Pool2 = (WCHAR *)ExAllocatePool2(256, Length, 1849968726);
  v8 = Pool2;
  if ( !Pool2 )
  {
    appended = -1073741670;
LABEL_24:
    *(_OWORD *)NewLength = 0;
    return (unsigned int)appended;
  }
  Destination.Buffer = Pool2;
  Destination.Length = 0;
  Destination.MaximumLength = Source->Length;
  v10 = 0;
  RtlAppendUnicodeStringToString(&Destination, Source);
  if ( Destination.Length < 8u )
    goto LABEL_4;
  v11 = (Destination.Length >> 1) - 1;
  if ( v11 >= 2 )
  {
    do
    {
      v12 = v11 - 1;
      if ( Destination.Buffer[v12] == 92 )
        break;
      --v11;
    }
    while ( (unsigned int)v12 >= 2 );
  }
  if ( Destination.Buffer[v11 - 1] == 92 )
  {
    v13 = 2 * v11;
    v14 = v13 + a2->Length;
    Destination.Length = v13;
    if ( v14 <= 0xFFFE )
    {
      v15 = v14 + 12;
      if ( v15 > 0xFFFE )
        v15 = 65534;
      v16 = ExAllocatePool2(256, v15, 1849968726);
      v10 = (void *)v16;
      if ( v16 )
      {
        *(_OWORD *)NewLength = 0;
        NewLength[1] = v15;
        *((_QWORD *)NewLength + 1) = v16;
        appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)NewLength, &Destination);
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)NewLength, a2);
          if ( appended >= 0 )
          {
            appended = FsRtlRemoveDotsFromPath(*((PWSTR *)NewLength + 1), *NewLength, NewLength);
            if ( appended >= 0 )
            {
              LongPathDecorationAppropriate = VhdmpiMakeLongPathDecorationAppropriate(NewLength);
              if ( LongPathDecorationAppropriate < 0 )
                LongPathDecorationAppropriate = -1073741562;
              appended = LongPathDecorationAppropriate;
            }
          }
        }
      }
      else
      {
        appended = -1073741670;
      }
    }
    else
    {
      appended = -1073741562;
    }
  }
  else
  {
LABEL_4:
    appended = -1073741811;
  }
  ExFreePoolWithTag(v8, 0x6E444856u);
  if ( appended < 0 )
  {
    if ( v10 )
      ExFreePoolWithTag(v10, 0x6E444856u);
    goto LABEL_24;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14002d854  push    rbx
0x14002d856  push    rbp
0x14002d857  push    rsi
0x14002d858  push    rdi
0x14002d859  push    r14
0x14002d85b  sub     rsp, 30h
0x14002d85f  mov     r14, rdx
0x14002d862  mov     rdi, r8
0x14002d865  movzx   edx, word ptr [rcx]
0x14002d868  mov     rbx, rcx
0x14002d86b  xorps   xmm0, xmm0
0x14002d86e  mov     ecx, 100h
0x14002d873  mov     r8d, 6E444856h
0x14002d879  movups  xmmword ptr [rsp+58h+Destination.Length], xmm0
0x14002d87e  call    cs:__imp_ExAllocatePool2
0x14002d885  nop     dword ptr [rax+rax+00h]
0x14002d88a  mov     rbp, rax
0x14002d88d  test    rax, rax
0x14002d890  jnz     short loc_14002D89C
0x14002d892  mov     ebx, 0C000009Ah
0x14002d897  jmp     loc_14002D9FD
0x14002d89c  xor     eax, eax
0x14002d89e  mov     [rsp+58h+Destination.Buffer], rbp
0x14002d8a3  mov     [rsp+58h+Destination.Length], ax
0x14002d8a8  lea     rcx, [rsp+58h+Destination]; Destination
0x14002d8ad  movzx   eax, word ptr [rbx]
0x14002d8b0  mov     rdx, rbx; Source
0x14002d8b3  mov     [rsp+58h+Destination.MaximumLength], ax
0x14002d8b8  xor     esi, esi
0x14002d8ba  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002d8c1  nop     dword ptr [rax+rax+00h]
0x14002d8c6  cmp     [rsp+58h+Destination.Length], 8
0x14002d8cc  jnb     short loc_14002D8D8
0x14002d8ce  mov     ebx, 0C000000Dh
0x14002d8d3  jmp     loc_14002D9CC
0x14002d8d8  movzx   edx, [rsp+58h+Destination.Length]
0x14002d8dd  mov     r8, [rsp+58h+Destination.Buffer]
0x14002d8e2  shr     edx, 1
0x14002d8e4  dec     edx
0x14002d8e6  cmp     edx, 2
0x14002d8e9  jb      short loc_14002D8FD
0x14002d8eb  lea     ecx, [rdx-1]
0x14002d8ee  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x14002d8f4  jz      short loc_14002D8FD
0x14002d8f6  mov     edx, ecx
0x14002d8f8  cmp     ecx, 2
0x14002d8fb  jnb     short loc_14002D8EB
0x14002d8fd  lea     eax, [rdx-1]
0x14002d900  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14002d906  jnz     short loc_14002D8CE
0x14002d908  movzx   ebx, word ptr [r14]
0x14002d90c  add     dx, dx
0x14002d90f  movzx   ecx, dx
0x14002d912  mov     eax, 0FFFEh
0x14002d917  add     ebx, ecx
0x14002d919  mov     [rsp+58h+Destination.Length], cx
0x14002d91e  cmp     ebx, eax
0x14002d920  jbe     short loc_14002D92C
0x14002d922  mov     ebx, 0C0000106h
0x14002d927  jmp     loc_14002D9CC
0x14002d92c  add     ebx, 0Ch
0x14002d92f  mov     ecx, 100h
0x14002d934  cmp     ebx, eax
0x14002d936  mov     r8d, 6E444856h
0x14002d93c  cmova   ebx, eax
0x14002d93f  mov     edx, ebx
0x14002d941  call    cs:__imp_ExAllocatePool2
0x14002d948  nop     dword ptr [rax+rax+00h]
0x14002d94d  mov     rsi, rax
0x14002d950  test    rax, rax
0x14002d953  jnz     short loc_14002D95C
0x14002d955  mov     ebx, 0C000009Ah
0x14002d95a  jmp     short loc_14002D9CC
0x14002d95c  xorps   xmm0, xmm0
0x14002d95f  lea     rdx, [rsp+58h+Destination]; Source
0x14002d964  movups  xmmword ptr [rdi], xmm0
0x14002d967  mov     rcx, rdi; Destination
0x14002d96a  mov     [rdi+2], bx
0x14002d96e  mov     [rdi+8], rax
0x14002d972  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002d979  nop     dword ptr [rax+rax+00h]
0x14002d97e  mov     ebx, eax
0x14002d980  test    eax, eax
0x14002d982  js      short loc_14002D9CC
0x14002d984  mov     rdx, r14; Source
0x14002d987  mov     rcx, rdi; Destination
0x14002d98a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002d991  nop     dword ptr [rax+rax+00h]
0x14002d996  mov     ebx, eax
0x14002d998  test    eax, eax
0x14002d99a  js      short loc_14002D9CC
0x14002d99c  movzx   edx, word ptr [rdi]; PathLength
0x14002d99f  mov     r8, rdi; NewLength
0x14002d9a2  mov     rcx, [rdi+8]; OriginalString
0x14002d9a6  call    cs:__imp_FsRtlRemoveDotsFromPath
0x14002d9ad  nop     dword ptr [rax+rax+00h]
0x14002d9b2  mov     ebx, eax
0x14002d9b4  test    eax, eax
0x14002d9b6  js      short loc_14002D9CC
0x14002d9b8  mov     rcx, rdi
0x14002d9bb  call    VhdmpiMakeLongPathDecorationAppropriate
0x14002d9c0  mov     ebx, 0C0000106h
0x14002d9c5  test    eax, eax
0x14002d9c7  cmovs   eax, ebx
0x14002d9ca  mov     ebx, eax
0x14002d9cc  mov     edx, 6E444856h; Tag
0x14002d9d1  mov     rcx, rbp; P
0x14002d9d4  call    cs:__imp_ExFreePoolWithTag
0x14002d9db  nop     dword ptr [rax+rax+00h]
0x14002d9e0  test    ebx, ebx
0x14002d9e2  jns     short loc_14002DA03
0x14002d9e4  test    rsi, rsi
0x14002d9e7  jz      short loc_14002D9FD
0x14002d9e9  mov     edx, 6E444856h; Tag
0x14002d9ee  mov     rcx, rsi; P
0x14002d9f1  call    cs:__imp_ExFreePoolWithTag
0x14002d9f8  nop     dword ptr [rax+rax+00h]
0x14002d9fd  xorps   xmm0, xmm0
0x14002da00  movups  xmmword ptr [rdi], xmm0
0x14002da03  mov     eax, ebx
0x14002da05  add     rsp, 30h
0x14002da09  pop     r14
0x14002da0b  pop     rdi
0x14002da0c  pop     rsi
0x14002da0d  pop     rbp
0x14002da0e  pop     rbx
0x14002da0f  retn
```
