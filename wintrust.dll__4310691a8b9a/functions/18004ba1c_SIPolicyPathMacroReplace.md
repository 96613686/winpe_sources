# SIPolicyPathMacroReplace

- ea: `0x18004ba1c`
- end: `0x18004bb14`
- name: `SIPolicyPathMacroReplace`
- size: `248`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1, PCUNICODE_STRING SourceString, PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004b770`

## callees

- `0x1800482c0`
- `0x18004ba1c`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18004baeb`
- `ntdll!RtlCopyUnicodeString` at `0x18004baeb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004baf9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004baf9`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ba71`
- `ntdll!RtlPrefixUnicodeString` at `0x18004ba71`

## pseudocode

```c
__int64 __fastcall SIPolicyPathMacroReplace(
        PCUNICODE_STRING String2,
        PCUNICODE_STRING String1,
        PCUNICODE_STRING SourceString,
        PUNICODE_STRING Destination)
{
  unsigned __int64 Length; // rax
  unsigned __int64 v9; // r10
  __int64 v10; // rdx
  int v11; // r9d
  WCHAR *v12; // rax
  __int64 v14; // rcx
  USHORT v15; // ax
  UNICODE_STRING Source; // [rsp+20h] [rbp-38h] BYREF

  Length = String2->Length;
  Source = 0;
  if ( (unsigned __int16)Length < String1->Length )
    return 3221225485LL;
  v9 = String1->Length;
  if ( Length > v9 + 2 && String2->Buffer[v9 >> 1] != 92 )
    return 3221225485LL;
  if ( !RtlPrefixUnicodeString(String1, String2, 1u) )
    return 3221225485LL;
  v10 = SourceString->Length;
  v11 = String1->Length;
  if ( (unsigned __int16)(-2 - v10) < String2->Length - v11 )
    return 3221225485LL;
  LOWORD(v10) = String2->Length + v10 - v11;
  Destination->Length = v10;
  Destination->MaximumLength = v10;
  v12 = (WCHAR *)MincryptAlloc((unsigned __int16)v10, v10);
  Destination->Buffer = v12;
  if ( !v12 )
    return 3221225495LL;
  v14 = String1->Length;
  v15 = String2->Length - v14;
  Source.Buffer = (PWSTR)((char *)String2->Buffer + v14);
  Source.MaximumLength = v15;
  Source.Length = v15;
  RtlCopyUnicodeString(Destination, SourceString);
  RtlAppendUnicodeStringToString(Destination, &Source);
  return 0;
}

```

## disassembly

```asm
0x18004ba1c  push    rbx
0x18004ba1e  push    rsi
0x18004ba1f  push    rdi
0x18004ba20  push    r14
0x18004ba22  push    r15
0x18004ba24  sub     rsp, 30h
0x18004ba28  movzx   eax, word ptr [rcx]
0x18004ba2b  xorps   xmm0, xmm0
0x18004ba2e  mov     r14, r9
0x18004ba31  mov     r15, r8
0x18004ba34  mov     rsi, rdx
0x18004ba37  mov     rdi, rcx
0x18004ba3a  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x18004ba3f  cmp     ax, [rdx]
0x18004ba42  jb      loc_18004BB03
0x18004ba48  movzx   r10d, word ptr [rdx]
0x18004ba4c  lea     r9, [r10+2]
0x18004ba50  cmp     rax, r9
0x18004ba53  jbe     short loc_18004BA68
0x18004ba55  mov     rax, [rcx+8]
0x18004ba59  shr     r10, 1
0x18004ba5c  cmp     word ptr [rax+r10*2], 5Ch ; '\'
0x18004ba62  jnz     loc_18004BB03
0x18004ba68  mov     r8b, 1; CaseInsensitive
0x18004ba6b  mov     rdx, rdi; String2
0x18004ba6e  mov     rcx, rsi; String1
0x18004ba71  call    cs:__imp_RtlPrefixUnicodeString
0x18004ba77  test    al, al
0x18004ba79  jz      loc_18004BB03
0x18004ba7f  movzx   r8d, word ptr [rdi]
0x18004ba83  mov     eax, 0FFFEh
0x18004ba88  movzx   edx, word ptr [r15]
0x18004ba8c  mov     ecx, r8d
0x18004ba8f  movzx   r9d, word ptr [rsi]
0x18004ba93  sub     ax, dx
0x18004ba96  sub     ecx, r9d
0x18004ba99  movzx   eax, ax
0x18004ba9c  cmp     eax, ecx
0x18004ba9e  jl      short loc_18004BB03
0x18004baa0  sub     dx, r9w
0x18004baa4  add     dx, r8w
0x18004baa8  movzx   ecx, dx
0x18004baab  mov     [r14], cx
0x18004baaf  mov     [r14+2], cx
0x18004bab4  call    MincryptAlloc
0x18004bab9  mov     [r14+8], rax
0x18004babd  test    rax, rax
0x18004bac0  jnz     short loc_18004BAC9
0x18004bac2  mov     eax, 0C0000017h
0x18004bac7  jmp     short loc_18004BB08
0x18004bac9  movzx   ecx, word ptr [rsi]
0x18004bacc  mov     rdx, r15; SourceString
0x18004bacf  movzx   eax, word ptr [rdi]
0x18004bad2  sub     ax, cx
0x18004bad5  add     rcx, [rdi+8]
0x18004bad9  mov     [rsp+58h+Source.Buffer], rcx
0x18004bade  mov     rcx, r14; DestinationString
0x18004bae1  mov     [rsp+58h+Source.MaximumLength], ax
0x18004bae6  mov     [rsp+58h+Source.Length], ax
0x18004baeb  call    cs:__imp_RtlCopyUnicodeString
0x18004baf1  lea     rdx, [rsp+58h+Source]; Source
0x18004baf6  mov     rcx, r14; Destination
0x18004baf9  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004baff  xor     eax, eax
0x18004bb01  jmp     short loc_18004BB08
0x18004bb03  mov     eax, 0C000000Dh
0x18004bb08  add     rsp, 30h
0x18004bb0c  pop     r15
0x18004bb0e  pop     r14
0x18004bb10  pop     rdi
0x18004bb11  pop     rsi
0x18004bb12  pop     rbx
0x18004bb13  retn
```
