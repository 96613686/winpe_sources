# VhdmpiDeterminePathType

- ea: `0x140023460`
- end: `0x140023776`
- name: `VhdmpiDeterminePathType`
- size: `790`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1400ec068`

## callees

- `0x140023460`
- `0x14005dbb0`
- `0x1400e1c34`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234b5`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234cf`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234e9`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234b5`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234cf`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400234e9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002361f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023749`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002361f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023749`
- `ntoskrnl!ExAllocatePool2` at `0x140023540`
- `ntoskrnl!ExAllocatePool2` at `0x1400235cd`
- `ntoskrnl!ExAllocatePool2` at `0x140023715`
- `ntoskrnl!ExAllocatePool2` at `0x140023540`
- `ntoskrnl!ExAllocatePool2` at `0x1400235cd`
- `ntoskrnl!ExAllocatePool2` at `0x140023715`

## pseudocode

```c
__int64 __fastcall VhdmpiDeterminePathType(
        struct _UNICODE_STRING *SourceString,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  enum _RTL_PATH_TYPE v8; // r11d
  int v9; // eax
  __int16 v10; // ax
  USHORT v11; // si
  __int64 v12; // rax
  struct _UNICODE_STRING *p_DestinationString; // rdx
  struct _UNICODE_STRING *v15; // rcx
  PWSTR Buffer; // rcx
  int v17; // edx
  USHORT i; // di
  __int64 v19; // rax
  WCHAR v20; // cx
  __int64 Pool2; // rcx
  USHORT Length; // ax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-A8h] BYREF
  char v24; // [rsp+30h] [rbp-98h] BYREF

  DestinationString = 0;
  v8 = VhdmpiDetermineDosPathNameType(SourceString);
  if ( v8 == RtlPathTypeLocalDevice )
  {
    if ( SourceString->Length > 0xEu
      && RtlUpcaseUnicodeChar(SourceString->Buffer[4]) == 85
      && RtlUpcaseUnicodeChar(SourceString->Buffer[5]) == 78
      && RtlUpcaseUnicodeChar(SourceString->Buffer[6]) == 67 )
    {
      v9 = 1;
      goto LABEL_16;
    }
    if ( SourceString->Length > 0xCu && SourceString->Buffer[5] == 58 )
    {
      v10 = 1;
      goto LABEL_11;
    }
LABEL_23:
    *(_QWORD *)&DestinationString.Length = 6291456;
    DestinationString.Buffer = (PWSTR)&v24;
    RtlCopyUnicodeString(&DestinationString, SourceString);
    if ( DestinationString.Length != 96 && (DestinationString.Length != 98 || DestinationString.Buffer[48] != 92) )
      return 0;
    if ( *DestinationString.Buffer != 92 )
      return 0;
    v20 = DestinationString.Buffer[1];
    if ( v20 != 63 && v20 != 92 )
      return 0;
    if ( DestinationString.Buffer[2] != 63
      || DestinationString.Buffer[3] != 92
      || DestinationString.Buffer[4] != 86
      || DestinationString.Buffer[5] != 111
      || DestinationString.Buffer[6] != 108
      || DestinationString.Buffer[7] != 117
      || DestinationString.Buffer[8] != 109
      || DestinationString.Buffer[9] != 101
      || DestinationString.Buffer[10] != 123
      || DestinationString.Buffer[19] != 45
      || DestinationString.Buffer[24] != 45
      || DestinationString.Buffer[29] != 45
      || DestinationString.Buffer[34] != 45
      || DestinationString.Buffer[47] != 125
      || DestinationString.Length != 96
      || v20 != 92 )
    {
      return 0;
    }
    Pool2 = ExAllocatePool2(64, 96, 1849968726);
    if ( Pool2 )
    {
      Length = DestinationString.Length;
      p_DestinationString = &DestinationString;
      *a3 = 0;
      a3->Buffer = (PWSTR)Pool2;
      v15 = a3;
      a3->MaximumLength = Length;
      goto LABEL_47;
    }
    return 3221225626LL;
  }
  v10 = 0;
  if ( v8 != RtlPathTypeDriveAbsolute )
  {
    if ( v8 == RtlPathTypeUncAbsolute )
    {
      v9 = 0;
LABEL_16:
      Buffer = SourceString->Buffer;
      v17 = 0;
      for ( i = 0; i < SourceString->Length; ++Buffer )
      {
        if ( (*Buffer == 92 || *Buffer == 47) && ++v17 == 2 * v9 + 4 )
          break;
        i += 2;
      }
      v19 = ExAllocatePool2(64, i, 1849968726);
      if ( v19 )
      {
        p_DestinationString = SourceString;
        *a4 = 0;
        a4->MaximumLength = i;
        v15 = a4;
        a4->Buffer = (PWSTR)v19;
        goto LABEL_47;
      }
      return 3221225626LL;
    }
    goto LABEL_23;
  }
LABEL_11:
  v11 = 8 * v10 + 4;
  v12 = ExAllocatePool2(64, v11, 1849968726);
  if ( !v12 )
    return 3221225626LL;
  p_DestinationString = SourceString;
  *a2 = 0;
  a2->MaximumLength = v11;
  v15 = a2;
  a2->Buffer = (PWSTR)v12;
LABEL_47:
  RtlCopyUnicodeString(v15, p_DestinationString);
  return 0;
}

```

## disassembly

```asm
0x140023460  push    rbx
0x140023462  push    rbp
0x140023463  push    rsi
0x140023464  push    rdi
0x140023465  push    r14
0x140023467  sub     rsp, 0A0h
0x14002346e  mov     rax, cs:__security_cookie
0x140023475  xor     rax, rsp
0x140023478  mov     [rsp+0C8h+var_38], rax
0x140023480  xorps   xmm0, xmm0
0x140023483  mov     rsi, r9
0x140023486  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x14002348b  mov     rbp, r8
0x14002348e  mov     rdi, rdx
0x140023491  mov     rbx, rcx
0x140023494  call    ?VhdmpiDetermineDosPathNameType@@YA?AW4_RTL_PATH_TYPE@@PEBU_UNICODE_STRING@@@Z; VhdmpiDetermineDosPathNameType(_UNICODE_STRING const *)
0x140023499  mov     r11d, eax
0x14002349c  mov     r14d, 2
0x1400234a2  cmp     eax, 6
0x1400234a5  jnz     short loc_140023521
0x1400234a7  cmp     word ptr [rbx], 0Eh
0x1400234ab  jbe     short loc_140023501
0x1400234ad  mov     rcx, [rbx+8]
0x1400234b1  movzx   ecx, word ptr [rcx+8]; SourceCharacter
0x1400234b5  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400234bc  nop     dword ptr [rax+rax+00h]
0x1400234c1  cmp     ax, 55h ; 'U'
0x1400234c5  jnz     short loc_140023501
0x1400234c7  mov     rcx, [rbx+8]
0x1400234cb  movzx   ecx, word ptr [rcx+0Ah]; SourceCharacter
0x1400234cf  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400234d6  nop     dword ptr [rax+rax+00h]
0x1400234db  cmp     ax, 4Eh ; 'N'
0x1400234df  jnz     short loc_140023501
0x1400234e1  mov     rcx, [rbx+8]
0x1400234e5  movzx   ecx, word ptr [rcx+0Ch]; SourceCharacter
0x1400234e9  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400234f0  nop     dword ptr [rax+rax+00h]
0x1400234f5  cmp     ax, 43h ; 'C'
0x1400234f9  jnz     short loc_140023501
0x1400234fb  lea     eax, [r14-1]
0x1400234ff  jmp     short loc_140023580
0x140023501  cmp     word ptr [rbx], 0Ch
0x140023505  jbe     loc_1400235FB
0x14002350b  mov     rax, [rbx+8]
0x14002350f  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x140023514  jnz     loc_1400235FB
0x14002351a  mov     eax, 1
0x14002351f  jmp     short loc_140023528
0x140023521  xor     eax, eax
0x140023523  cmp     r11d, r14d
0x140023526  jnz     short loc_140023574
0x140023528  shl     ax, 3
0x14002352c  mov     ecx, 40h ; '@'
0x140023531  add     ax, 4
0x140023535  mov     r8d, 6E444856h
0x14002353b  movzx   esi, ax
0x14002353e  mov     edx, esi
0x140023540  call    cs:__imp_ExAllocatePool2
0x140023547  nop     dword ptr [rax+rax+00h]
0x14002354c  test    rax, rax
0x14002354f  jnz     short loc_14002355B
0x140023551  mov     eax, 0C000009Ah
0x140023556  jmp     loc_140023757
0x14002355b  xorps   xmm0, xmm0
0x14002355e  mov     rdx, rbx
0x140023561  movups  xmmword ptr [rdi], xmm0
0x140023564  mov     [rdi+2], si
0x140023568  mov     rcx, rdi
0x14002356b  mov     [rdi+8], rax
0x14002356f  jmp     loc_140023749
0x140023574  mov     eax, 1
0x140023579  cmp     r11d, eax
0x14002357c  jnz     short loc_1400235FB
0x14002357e  xor     eax, eax
0x140023580  movzx   r8d, word ptr [rbx]
0x140023584  lea     r9d, ds:4[rax*2]
0x14002358c  mov     rcx, [rbx+8]
0x140023590  xor     eax, eax
0x140023592  xor     edx, edx
0x140023594  xor     edi, edi
0x140023596  cmp     ax, r8w
0x14002359a  jnb     short loc_1400235BF
0x14002359c  movzx   eax, word ptr [rcx]
0x14002359f  cmp     ax, 5Ch ; '\'
0x1400235a3  jz      short loc_1400235AB
0x1400235a5  cmp     ax, 2Fh ; '/'
0x1400235a9  jnz     short loc_1400235B2
0x1400235ab  inc     edx
0x1400235ad  cmp     edx, r9d
0x1400235b0  jz      short loc_1400235BF
0x1400235b2  add     di, r14w
0x1400235b6  add     rcx, r14
0x1400235b9  cmp     di, r8w
0x1400235bd  jb      short loc_14002359C
0x1400235bf  movzx   edx, di
0x1400235c2  mov     ecx, 40h ; '@'
0x1400235c7  mov     r8d, 6E444856h
0x1400235cd  call    cs:__imp_ExAllocatePool2
0x1400235d4  nop     dword ptr [rax+rax+00h]
0x1400235d9  test    rax, rax
0x1400235dc  jz      loc_140023551
0x1400235e2  xorps   xmm0, xmm0
0x1400235e5  mov     rdx, rbx
0x1400235e8  movups  xmmword ptr [rsi], xmm0
0x1400235eb  mov     [rsi+2], di
0x1400235ef  mov     rcx, rsi
0x1400235f2  mov     [rsi+8], rax
0x1400235f6  jmp     loc_140023749
0x1400235fb  xorps   xmm0, xmm0
0x1400235fe  lea     rax, [rsp+0C8h+var_98]
0x140023603  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x140023608  mov     edi, 60h ; '`'
0x14002360d  mov     [rsp+0C8h+DestinationString.Buffer], rax
0x140023612  mov     rdx, rbx; SourceString
0x140023615  mov     [rsp+0C8h+DestinationString.MaximumLength], di
0x14002361a  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x14002361f  call    cs:__imp_RtlCopyUnicodeString
0x140023626  nop     dword ptr [rax+rax+00h]
0x14002362b  movzx   r8d, [rsp+0C8h+DestinationString.Length]
0x140023631  mov     rax, [rsp+0C8h+DestinationString.Buffer]
0x140023636  cmp     r8w, di
0x14002363a  jz      short loc_140023652
0x14002363c  cmp     r8w, 62h ; 'b'
0x140023641  jnz     loc_140023755
0x140023647  cmp     word ptr [rax+60h], 5Ch ; '\'
0x14002364c  jnz     loc_140023755
0x140023652  cmp     word ptr [rax], 5Ch ; '\'
0x140023656  jnz     loc_140023755
0x14002365c  movzx   ecx, word ptr [rax+2]
0x140023660  cmp     cx, 3Fh ; '?'
0x140023664  jz      short loc_140023670
0x140023666  cmp     cx, 5Ch ; '\'
0x14002366a  jnz     loc_140023755
0x140023670  cmp     word ptr [rax+4], 3Fh ; '?'
0x140023675  jnz     loc_140023755
0x14002367b  cmp     word ptr [rax+6], 5Ch ; '\'
0x140023680  jnz     loc_140023755
0x140023686  cmp     word ptr [rax+8], 56h ; 'V'
0x14002368b  jnz     loc_140023755
0x140023691  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x140023696  jnz     loc_140023755
0x14002369c  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x1400236a1  jnz     loc_140023755
0x1400236a7  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x1400236ac  jnz     loc_140023755
0x1400236b2  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x1400236b7  jnz     loc_140023755
0x1400236bd  cmp     word ptr [rax+12h], 65h ; 'e'
0x1400236c2  jnz     loc_140023755
0x1400236c8  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1400236cd  jnz     loc_140023755
0x1400236d3  mov     r9w, 2Dh ; '-'
0x1400236d8  cmp     [rax+26h], r9w
0x1400236dd  jnz     short loc_140023755
0x1400236df  cmp     [rax+30h], r9w
0x1400236e4  jnz     short loc_140023755
0x1400236e6  cmp     [rax+3Ah], r9w
0x1400236eb  jnz     short loc_140023755
0x1400236ed  cmp     [rax+44h], r9w
0x1400236f2  jnz     short loc_140023755
0x1400236f4  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1400236f9  jnz     short loc_140023755
0x1400236fb  cmp     r8w, di
0x1400236ff  jnz     short loc_140023755
0x140023701  cmp     cx, 5Ch ; '\'
0x140023705  jnz     short loc_140023755
0x140023707  mov     r8d, 6E444856h
0x14002370d  mov     rdx, rdi
0x140023710  mov     ecx, 40h ; '@'
0x140023715  call    cs:__imp_ExAllocatePool2
0x14002371c  nop     dword ptr [rax+rax+00h]
0x140023721  mov     rcx, rax
0x140023724  test    rax, rax
0x140023727  jz      loc_140023551
0x14002372d  movzx   eax, [rsp+0C8h+DestinationString.Length]
0x140023732  lea     rdx, [rsp+0C8h+DestinationString]; SourceString
0x140023737  xorps   xmm0, xmm0
0x14002373a  movups  xmmword ptr [rbp+0], xmm0
0x14002373e  mov     [rbp+8], rcx
0x140023742  mov     rcx, rbp; DestinationString
0x140023745  mov     [rbp+2], ax
0x140023749  call    cs:__imp_RtlCopyUnicodeString
0x140023750  nop     dword ptr [rax+rax+00h]
0x140023755  xor     eax, eax
0x140023757  mov     rcx, [rsp+0C8h+var_38]
0x14002375f  xor     rcx, rsp; StackCookie
0x140023762  call    __security_check_cookie
0x140023767  add     rsp, 0A0h
0x14002376e  pop     r14
0x140023770  pop     rdi
0x140023771  pop     rsi
0x140023772  pop     rbp
0x140023773  pop     rbx
0x140023774  retn
```
