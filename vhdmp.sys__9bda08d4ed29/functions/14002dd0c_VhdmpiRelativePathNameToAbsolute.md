# VhdmpiRelativePathNameToAbsolute

- ea: `0x14002dd0c`
- end: `0x14002dec9`
- name: `VhdmpiRelativePathNameToAbsolute`
- size: `445`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING, USHORT *NewLength)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14002dcc4`
- `0x1400b0104`
- `0x1400c6b90`
- `0x1400c7028`

## callees

- `0x1400197b0`
- `0x14002dd0c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002dd72`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002de2a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002de42`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002dd72`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002de2a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002de42`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14002de5e`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14002de5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002de8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002de8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002dea9`
- `ntoskrnl!ExAllocatePool2` at `0x14002dd36`
- `ntoskrnl!ExAllocatePool2` at `0x14002ddf9`
- `ntoskrnl!ExAllocatePool2` at `0x14002dd36`
- `ntoskrnl!ExAllocatePool2` at `0x14002ddf9`

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
0x14002dd0c  push    rbx
0x14002dd0e  push    rbp
0x14002dd0f  push    rsi
0x14002dd10  push    rdi
0x14002dd11  push    r14
0x14002dd13  sub     rsp, 30h
0x14002dd17  mov     r14, rdx
0x14002dd1a  mov     rdi, r8
0x14002dd1d  movzx   edx, word ptr [rcx]
0x14002dd20  mov     rbx, rcx
0x14002dd23  xorps   xmm0, xmm0
0x14002dd26  mov     ecx, 100h
0x14002dd2b  mov     r8d, 6E444856h
0x14002dd31  movups  xmmword ptr [rsp+58h+Destination.Length], xmm0
0x14002dd36  call    cs:__imp_ExAllocatePool2
0x14002dd3d  nop     dword ptr [rax+rax+00h]
0x14002dd42  mov     rbp, rax
0x14002dd45  test    rax, rax
0x14002dd48  jnz     short loc_14002DD54
0x14002dd4a  mov     ebx, 0C000009Ah
0x14002dd4f  jmp     loc_14002DEB5
0x14002dd54  xor     eax, eax
0x14002dd56  mov     [rsp+58h+Destination.Buffer], rbp
0x14002dd5b  mov     [rsp+58h+Destination.Length], ax
0x14002dd60  lea     rcx, [rsp+58h+Destination]; Destination
0x14002dd65  movzx   eax, word ptr [rbx]
0x14002dd68  mov     rdx, rbx; Source
0x14002dd6b  mov     [rsp+58h+Destination.MaximumLength], ax
0x14002dd70  xor     esi, esi
0x14002dd72  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002dd79  nop     dword ptr [rax+rax+00h]
0x14002dd7e  cmp     [rsp+58h+Destination.Length], 8
0x14002dd84  jnb     short loc_14002DD90
0x14002dd86  mov     ebx, 0C000000Dh
0x14002dd8b  jmp     loc_14002DE84
0x14002dd90  movzx   edx, [rsp+58h+Destination.Length]
0x14002dd95  mov     r8, [rsp+58h+Destination.Buffer]
0x14002dd9a  shr     edx, 1
0x14002dd9c  dec     edx
0x14002dd9e  cmp     edx, 2
0x14002dda1  jb      short loc_14002DDB5
0x14002dda3  lea     ecx, [rdx-1]
0x14002dda6  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x14002ddac  jz      short loc_14002DDB5
0x14002ddae  mov     edx, ecx
0x14002ddb0  cmp     ecx, 2
0x14002ddb3  jnb     short loc_14002DDA3
0x14002ddb5  lea     eax, [rdx-1]
0x14002ddb8  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14002ddbe  jnz     short loc_14002DD86
0x14002ddc0  movzx   ebx, word ptr [r14]
0x14002ddc4  add     dx, dx
0x14002ddc7  movzx   ecx, dx
0x14002ddca  mov     eax, 0FFFEh
0x14002ddcf  add     ebx, ecx
0x14002ddd1  mov     [rsp+58h+Destination.Length], cx
0x14002ddd6  cmp     ebx, eax
0x14002ddd8  jbe     short loc_14002DDE4
0x14002ddda  mov     ebx, 0C0000106h
0x14002dddf  jmp     loc_14002DE84
0x14002dde4  add     ebx, 0Ch
0x14002dde7  mov     ecx, 100h
0x14002ddec  cmp     ebx, eax
0x14002ddee  mov     r8d, 6E444856h
0x14002ddf4  cmova   ebx, eax
0x14002ddf7  mov     edx, ebx
0x14002ddf9  call    cs:__imp_ExAllocatePool2
0x14002de00  nop     dword ptr [rax+rax+00h]
0x14002de05  mov     rsi, rax
0x14002de08  test    rax, rax
0x14002de0b  jnz     short loc_14002DE14
0x14002de0d  mov     ebx, 0C000009Ah
0x14002de12  jmp     short loc_14002DE84
0x14002de14  xorps   xmm0, xmm0
0x14002de17  lea     rdx, [rsp+58h+Destination]; Source
0x14002de1c  movups  xmmword ptr [rdi], xmm0
0x14002de1f  mov     rcx, rdi; Destination
0x14002de22  mov     [rdi+2], bx
0x14002de26  mov     [rdi+8], rax
0x14002de2a  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002de31  nop     dword ptr [rax+rax+00h]
0x14002de36  mov     ebx, eax
0x14002de38  test    eax, eax
0x14002de3a  js      short loc_14002DE84
0x14002de3c  mov     rdx, r14; Source
0x14002de3f  mov     rcx, rdi; Destination
0x14002de42  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002de49  nop     dword ptr [rax+rax+00h]
0x14002de4e  mov     ebx, eax
0x14002de50  test    eax, eax
0x14002de52  js      short loc_14002DE84
0x14002de54  movzx   edx, word ptr [rdi]; PathLength
0x14002de57  mov     r8, rdi; NewLength
0x14002de5a  mov     rcx, [rdi+8]; OriginalString
0x14002de5e  call    cs:__imp_FsRtlRemoveDotsFromPath
0x14002de65  nop     dword ptr [rax+rax+00h]
0x14002de6a  mov     ebx, eax
0x14002de6c  test    eax, eax
0x14002de6e  js      short loc_14002DE84
0x14002de70  mov     rcx, rdi
0x14002de73  call    VhdmpiMakeLongPathDecorationAppropriate
0x14002de78  mov     ebx, 0C0000106h
0x14002de7d  test    eax, eax
0x14002de7f  cmovs   eax, ebx
0x14002de82  mov     ebx, eax
0x14002de84  mov     edx, 6E444856h; Tag
0x14002de89  mov     rcx, rbp; P
0x14002de8c  call    cs:__imp_ExFreePoolWithTag
0x14002de93  nop     dword ptr [rax+rax+00h]
0x14002de98  test    ebx, ebx
0x14002de9a  jns     short loc_14002DEBB
0x14002de9c  test    rsi, rsi
0x14002de9f  jz      short loc_14002DEB5
0x14002dea1  mov     edx, 6E444856h; Tag
0x14002dea6  mov     rcx, rsi; P
0x14002dea9  call    cs:__imp_ExFreePoolWithTag
0x14002deb0  nop     dword ptr [rax+rax+00h]
0x14002deb5  xorps   xmm0, xmm0
0x14002deb8  movups  xmmword ptr [rdi], xmm0
0x14002debb  mov     eax, ebx
0x14002debd  add     rsp, 30h
0x14002dec1  pop     r14
0x14002dec3  pop     rdi
0x14002dec4  pop     rsi
0x14002dec5  pop     rbp
0x14002dec6  pop     rbx
0x14002dec7  retn
```
