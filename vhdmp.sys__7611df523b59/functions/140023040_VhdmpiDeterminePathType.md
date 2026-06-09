# VhdmpiDeterminePathType

- ea: `0x140023040`
- end: `0x140023356`
- name: `VhdmpiDeterminePathType`
- size: `790`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1400ec0d8`

## callees

- `0x140023040`
- `0x14005d7c0`
- `0x1400e1ca4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023095`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400230af`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400230c9`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140023095`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400230af`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x1400230c9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400231ff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023329`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400231ff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140023329`
- `ntoskrnl!ExAllocatePool2` at `0x140023120`
- `ntoskrnl!ExAllocatePool2` at `0x1400231ad`
- `ntoskrnl!ExAllocatePool2` at `0x1400232f5`
- `ntoskrnl!ExAllocatePool2` at `0x140023120`
- `ntoskrnl!ExAllocatePool2` at `0x1400231ad`
- `ntoskrnl!ExAllocatePool2` at `0x1400232f5`

## pseudocode

```c
__int64 __fastcall VhdmpiDeterminePathType(
        struct _UNICODE_STRING *SourceString,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  int v8; // r11d
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
  if ( v8 == 6 )
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
  if ( v8 != 2 )
  {
    if ( v8 == 1 )
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
0x140023040  push    rbx
0x140023042  push    rbp
0x140023043  push    rsi
0x140023044  push    rdi
0x140023045  push    r14
0x140023047  sub     rsp, 0A0h
0x14002304e  mov     rax, cs:__security_cookie
0x140023055  xor     rax, rsp
0x140023058  mov     [rsp+0C8h+var_38], rax
0x140023060  xorps   xmm0, xmm0
0x140023063  mov     rsi, r9
0x140023066  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x14002306b  mov     rbp, r8
0x14002306e  mov     rdi, rdx
0x140023071  mov     rbx, rcx
0x140023074  call    ?VhdmpiDetermineDosPathNameType@@YA?AW4_RTL_PATH_TYPE@@PEBU_UNICODE_STRING@@@Z; VhdmpiDetermineDosPathNameType(_UNICODE_STRING const *)
0x140023079  mov     r11d, eax
0x14002307c  mov     r14d, 2
0x140023082  cmp     eax, 6
0x140023085  jnz     short loc_140023101
0x140023087  cmp     word ptr [rbx], 0Eh
0x14002308b  jbe     short loc_1400230E1
0x14002308d  mov     rcx, [rbx+8]
0x140023091  movzx   ecx, word ptr [rcx+8]; SourceCharacter
0x140023095  call    cs:__imp_RtlUpcaseUnicodeChar
0x14002309c  nop     dword ptr [rax+rax+00h]
0x1400230a1  cmp     ax, 55h ; 'U'
0x1400230a5  jnz     short loc_1400230E1
0x1400230a7  mov     rcx, [rbx+8]
0x1400230ab  movzx   ecx, word ptr [rcx+0Ah]; SourceCharacter
0x1400230af  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400230b6  nop     dword ptr [rax+rax+00h]
0x1400230bb  cmp     ax, 4Eh ; 'N'
0x1400230bf  jnz     short loc_1400230E1
0x1400230c1  mov     rcx, [rbx+8]
0x1400230c5  movzx   ecx, word ptr [rcx+0Ch]; SourceCharacter
0x1400230c9  call    cs:__imp_RtlUpcaseUnicodeChar
0x1400230d0  nop     dword ptr [rax+rax+00h]
0x1400230d5  cmp     ax, 43h ; 'C'
0x1400230d9  jnz     short loc_1400230E1
0x1400230db  lea     eax, [r14-1]
0x1400230df  jmp     short loc_140023160
0x1400230e1  cmp     word ptr [rbx], 0Ch
0x1400230e5  jbe     loc_1400231DB
0x1400230eb  mov     rax, [rbx+8]
0x1400230ef  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x1400230f4  jnz     loc_1400231DB
0x1400230fa  mov     eax, 1
0x1400230ff  jmp     short loc_140023108
0x140023101  xor     eax, eax
0x140023103  cmp     r11d, r14d
0x140023106  jnz     short loc_140023154
0x140023108  shl     ax, 3
0x14002310c  mov     ecx, 40h ; '@'
0x140023111  add     ax, 4
0x140023115  mov     r8d, 6E444856h
0x14002311b  movzx   esi, ax
0x14002311e  mov     edx, esi
0x140023120  call    cs:__imp_ExAllocatePool2
0x140023127  nop     dword ptr [rax+rax+00h]
0x14002312c  test    rax, rax
0x14002312f  jnz     short loc_14002313B
0x140023131  mov     eax, 0C000009Ah
0x140023136  jmp     loc_140023337
0x14002313b  xorps   xmm0, xmm0
0x14002313e  mov     rdx, rbx
0x140023141  movups  xmmword ptr [rdi], xmm0
0x140023144  mov     [rdi+2], si
0x140023148  mov     rcx, rdi
0x14002314b  mov     [rdi+8], rax
0x14002314f  jmp     loc_140023329
0x140023154  mov     eax, 1
0x140023159  cmp     r11d, eax
0x14002315c  jnz     short loc_1400231DB
0x14002315e  xor     eax, eax
0x140023160  movzx   r8d, word ptr [rbx]
0x140023164  lea     r9d, ds:4[rax*2]
0x14002316c  mov     rcx, [rbx+8]
0x140023170  xor     eax, eax
0x140023172  xor     edx, edx
0x140023174  xor     edi, edi
0x140023176  cmp     ax, r8w
0x14002317a  jnb     short loc_14002319F
0x14002317c  movzx   eax, word ptr [rcx]
0x14002317f  cmp     ax, 5Ch ; '\'
0x140023183  jz      short loc_14002318B
0x140023185  cmp     ax, 2Fh ; '/'
0x140023189  jnz     short loc_140023192
0x14002318b  inc     edx
0x14002318d  cmp     edx, r9d
0x140023190  jz      short loc_14002319F
0x140023192  add     di, r14w
0x140023196  add     rcx, r14
0x140023199  cmp     di, r8w
0x14002319d  jb      short loc_14002317C
0x14002319f  movzx   edx, di
0x1400231a2  mov     ecx, 40h ; '@'
0x1400231a7  mov     r8d, 6E444856h
0x1400231ad  call    cs:__imp_ExAllocatePool2
0x1400231b4  nop     dword ptr [rax+rax+00h]
0x1400231b9  test    rax, rax
0x1400231bc  jz      loc_140023131
0x1400231c2  xorps   xmm0, xmm0
0x1400231c5  mov     rdx, rbx
0x1400231c8  movups  xmmword ptr [rsi], xmm0
0x1400231cb  mov     [rsi+2], di
0x1400231cf  mov     rcx, rsi
0x1400231d2  mov     [rsi+8], rax
0x1400231d6  jmp     loc_140023329
0x1400231db  xorps   xmm0, xmm0
0x1400231de  lea     rax, [rsp+0C8h+var_98]
0x1400231e3  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x1400231e8  mov     edi, 60h ; '`'
0x1400231ed  mov     [rsp+0C8h+DestinationString.Buffer], rax
0x1400231f2  mov     rdx, rbx; SourceString
0x1400231f5  mov     [rsp+0C8h+DestinationString.MaximumLength], di
0x1400231fa  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400231ff  call    cs:__imp_RtlCopyUnicodeString
0x140023206  nop     dword ptr [rax+rax+00h]
0x14002320b  movzx   r8d, [rsp+0C8h+DestinationString.Length]
0x140023211  mov     rax, [rsp+0C8h+DestinationString.Buffer]
0x140023216  cmp     r8w, di
0x14002321a  jz      short loc_140023232
0x14002321c  cmp     r8w, 62h ; 'b'
0x140023221  jnz     loc_140023335
0x140023227  cmp     word ptr [rax+60h], 5Ch ; '\'
0x14002322c  jnz     loc_140023335
0x140023232  cmp     word ptr [rax], 5Ch ; '\'
0x140023236  jnz     loc_140023335
0x14002323c  movzx   ecx, word ptr [rax+2]
0x140023240  cmp     cx, 3Fh ; '?'
0x140023244  jz      short loc_140023250
0x140023246  cmp     cx, 5Ch ; '\'
0x14002324a  jnz     loc_140023335
0x140023250  cmp     word ptr [rax+4], 3Fh ; '?'
0x140023255  jnz     loc_140023335
0x14002325b  cmp     word ptr [rax+6], 5Ch ; '\'
0x140023260  jnz     loc_140023335
0x140023266  cmp     word ptr [rax+8], 56h ; 'V'
0x14002326b  jnz     loc_140023335
0x140023271  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x140023276  jnz     loc_140023335
0x14002327c  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x140023281  jnz     loc_140023335
0x140023287  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x14002328c  jnz     loc_140023335
0x140023292  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x140023297  jnz     loc_140023335
0x14002329d  cmp     word ptr [rax+12h], 65h ; 'e'
0x1400232a2  jnz     loc_140023335
0x1400232a8  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1400232ad  jnz     loc_140023335
0x1400232b3  mov     r9w, 2Dh ; '-'
0x1400232b8  cmp     [rax+26h], r9w
0x1400232bd  jnz     short loc_140023335
0x1400232bf  cmp     [rax+30h], r9w
0x1400232c4  jnz     short loc_140023335
0x1400232c6  cmp     [rax+3Ah], r9w
0x1400232cb  jnz     short loc_140023335
0x1400232cd  cmp     [rax+44h], r9w
0x1400232d2  jnz     short loc_140023335
0x1400232d4  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1400232d9  jnz     short loc_140023335
0x1400232db  cmp     r8w, di
0x1400232df  jnz     short loc_140023335
0x1400232e1  cmp     cx, 5Ch ; '\'
0x1400232e5  jnz     short loc_140023335
0x1400232e7  mov     r8d, 6E444856h
0x1400232ed  mov     rdx, rdi
0x1400232f0  mov     ecx, 40h ; '@'
0x1400232f5  call    cs:__imp_ExAllocatePool2
0x1400232fc  nop     dword ptr [rax+rax+00h]
0x140023301  mov     rcx, rax
0x140023304  test    rax, rax
0x140023307  jz      loc_140023131
0x14002330d  movzx   eax, [rsp+0C8h+DestinationString.Length]
0x140023312  lea     rdx, [rsp+0C8h+DestinationString]; SourceString
0x140023317  xorps   xmm0, xmm0
0x14002331a  movups  xmmword ptr [rbp+0], xmm0
0x14002331e  mov     [rbp+8], rcx
0x140023322  mov     rcx, rbp; DestinationString
0x140023325  mov     [rbp+2], ax
0x140023329  call    cs:__imp_RtlCopyUnicodeString
0x140023330  nop     dword ptr [rax+rax+00h]
0x140023335  xor     eax, eax
0x140023337  mov     rcx, [rsp+0C8h+var_38]
0x14002333f  xor     rcx, rsp; StackCookie
0x140023342  call    __security_check_cookie
0x140023347  add     rsp, 0A0h
0x14002334e  pop     r14
0x140023350  pop     rdi
0x140023351  pop     rsi
0x140023352  pop     rbp
0x140023353  pop     rbx
0x140023354  retn
```
