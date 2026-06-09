# SclExpandString

- ea: `0x180007b30`
- end: `0x180007c21`
- name: `SclExpandString`
- size: `241`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002b98`
- `0x180004428`
- `0x180004844`
- `0x180007cac`

## callees

- `0x180007b30`
- `0x18000a524`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180007b7e`
- `ntdll!RtlInitUnicodeString` at `0x180007b7e`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180007ba0`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180007ba0`

## pseudocode

```c
__int64 __fastcall SclExpandString(PCWSTR SourceString, void *a2)
{
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  DestinationString = 0;
  Destination = 0;
  if ( SourceString && a2 )
  {
    memset_0(a2, 0, 0x208u);
    RtlInitUnicodeString(&DestinationString, SourceString);
    *(_DWORD *)&Destination.Length = 33947648;
    Destination.Buffer = (PWSTR)a2;
    v4 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, 0);
    if ( v4 >= 0 )
    {
      if ( (unsigned __int16)(Destination.Length >> 1) < 0x104u )
      {
        *((_WORD *)a2 + (Destination.Length >> 1)) = 0;
        return (unsigned int)v4;
      }
      v4 = -2147483643;
    }
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 246, (__int64)"SclExpandString");
    return (unsigned int)v4;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180007b30  mov     rax, rsp
0x180007b33  mov     [rax+8], rbx
0x180007b37  mov     [rax+10h], rsi
0x180007b3b  push    rdi
0x180007b3c  sub     rsp, 60h
0x180007b40  xorps   xmm0, xmm0
0x180007b43  xorps   xmm1, xmm1
0x180007b46  mov     rdi, rdx
0x180007b49  mov     rsi, rcx
0x180007b4c  movups  xmmword ptr [rax-18h], xmm0
0x180007b50  movups  xmmword ptr [rax-28h], xmm1
0x180007b54  test    rcx, rcx
0x180007b57  jz      loc_180007C0C
0x180007b5d  test    rdx, rdx
0x180007b60  jz      loc_180007C0C
0x180007b66  xor     edx, edx; Val
0x180007b68  mov     r8d, 208h; Size
0x180007b6e  mov     rcx, rdi; void *
0x180007b71  call    memset_0
0x180007b76  mov     rdx, rsi; SourceString
0x180007b79  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180007b7e  call    cs:__imp_RtlInitUnicodeString
0x180007b84  xor     r9d, r9d; Length
0x180007b87  mov     dword ptr [rsp+68h+Destination.Length], 2060000h
0x180007b8f  lea     r8, [rsp+68h+Destination]; Destination
0x180007b94  mov     [rsp+68h+Destination.Buffer], rdi
0x180007b99  lea     rdx, [rsp+68h+DestinationString]; Source
0x180007b9e  xor     ecx, ecx; Environment
0x180007ba0  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180007ba6  mov     ebx, eax
0x180007ba8  test    eax, eax
0x180007baa  js      short loc_180007BCE
0x180007bac  movzx   ecx, [rsp+68h+Destination.Length]
0x180007bb1  mov     eax, 104h
0x180007bb6  shr     cx, 1
0x180007bb9  cmp     cx, ax
0x180007bbc  jnb     short loc_180007BC9
0x180007bbe  movzx   edx, cx
0x180007bc1  xor     ecx, ecx
0x180007bc3  mov     [rdi+rdx*2], cx
0x180007bc7  jmp     short loc_180007C08
0x180007bc9  mov     ebx, 80000005h
0x180007bce  mov     [rsp+68h+var_30], rsi
0x180007bd3  lea     rax, aLxFailedToExpa_0; "(%lx): Failed to expand [%ws]!"
0x180007bda  mov     [rsp+68h+var_38], ebx
0x180007bde  lea     r8, SclEvent_Generic_Error
0x180007be5  mov     [rsp+68h+var_40], rax
0x180007bea  mov     r9d, 0F6h
0x180007bf0  lea     rax, aSclexpandstrin; "SclExpandString"
0x180007bf7  mov     edx, 3
0x180007bfc  xor     ecx, ecx
0x180007bfe  mov     [rsp+68h+var_48], rax
0x180007c03  call    SclLogGenericMessage
0x180007c08  mov     eax, ebx
0x180007c0a  jmp     short loc_180007C11
0x180007c0c  mov     eax, 0C000000Dh
0x180007c11  mov     rbx, [rsp+68h+arg_0]
0x180007c16  mov     rsi, [rsp+68h+arg_8]
0x180007c1b  add     rsp, 60h
0x180007c1f  pop     rdi
0x180007c20  retn
```
