# SrvNetCreateAndPadNetBiosName

- ea: `0x140054a70`
- end: `0x140054b2a`
- name: `SrvNetCreateAndPadNetBiosName`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001ea1c`
- `0x140054750`

## callees

- `0x14002a3e0`
- `0x14002a540`
- `0x140054a70`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140054b02`
- `ntoskrnl!RtlUnicodeStringToOemString` at `0x140054b02`

## pseudocode

```c
NTSTATUS __fastcall SrvNetCreateAndPadNetBiosName(__int64 a1, struct _STRING *a2)
{
  USHORT v3; // ax
  const void *v4; // rdx
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v7[40]; // [rsp+30h] [rbp-38h] BYREF

  SourceString.MaximumLength = 34;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  SourceString.Buffer = (PWSTR)v7;
  v3 = *(_WORD *)a1;
  if ( *(_WORD *)a1 >= 0x20u )
    v3 = 32;
  v4 = *(const void **)(a1 + 8);
  SourceString.Length = v3;
  memmove(v7, v4, v3);
  if ( SourceString.Length < 0x20u )
    memmove((char *)SourceString.Buffer + SourceString.Length, L"                ", 32LL - SourceString.Length);
  SourceString.Length = 32;
  return RtlUnicodeStringToOemString(a2, &SourceString, 1u);
}

```

## disassembly

```asm
0x140054a70  mov     [rsp+arg_10], rbx
0x140054a75  push    rdi
0x140054a76  sub     rsp, 60h
0x140054a7a  mov     rax, cs:__security_cookie
0x140054a81  xor     rax, rsp
0x140054a84  mov     [rsp+68h+var_10], rax
0x140054a89  mov     eax, 22h ; '"'
0x140054a8e  mov     edi, 20h ; ' '
0x140054a93  mov     [rsp+68h+SourceString.MaximumLength], ax
0x140054a98  mov     rbx, rdx
0x140054a9b  xor     eax, eax
0x140054a9d  mov     dword ptr [rsp+68h+SourceString+4], eax
0x140054aa1  lea     rax, [rsp+68h+var_38]
0x140054aa6  mov     [rsp+68h+SourceString.Buffer], rax
0x140054aab  movzx   eax, word ptr [rcx]
0x140054aae  cmp     ax, di
0x140054ab1  jb      short loc_140054AB5
0x140054ab3  mov     eax, edi
0x140054ab5  mov     rdx, [rcx+8]; Src
0x140054ab9  lea     rcx, [rsp+68h+var_38]; void *
0x140054abe  movzx   r8d, ax; Size
0x140054ac2  mov     [rsp+68h+SourceString.Length], ax
0x140054ac7  call    memmove
0x140054acc  cmp     [rsp+68h+SourceString.Length], di
0x140054ad1  jnb     short loc_140054AF2
0x140054ad3  movzx   edx, [rsp+68h+SourceString.Length]
0x140054ad8  mov     r8, rdi
0x140054adb  mov     rcx, [rsp+68h+SourceString.Buffer]
0x140054ae0  sub     r8, rdx; Size
0x140054ae3  add     rcx, rdx; void *
0x140054ae6  lea     rdx, asc_14002FCB8; "                "
0x140054aed  call    memmove
0x140054af2  mov     r8b, 1; AllocateDestinationString
0x140054af5  mov     [rsp+68h+SourceString.Length], di
0x140054afa  lea     rdx, [rsp+68h+SourceString]; SourceString
0x140054aff  mov     rcx, rbx; DestinationString
0x140054b02  call    cs:__imp_RtlUnicodeStringToOemString
0x140054b09  nop     dword ptr [rax+rax+00h]
0x140054b0e  mov     rcx, [rsp+68h+var_10]
0x140054b13  xor     rcx, rsp; StackCookie
0x140054b16  call    __security_check_cookie
0x140054b1b  mov     rbx, [rsp+68h+arg_10]
0x140054b23  add     rsp, 60h
0x140054b27  pop     rdi
0x140054b28  retn
```
