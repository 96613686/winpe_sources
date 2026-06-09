# SmpQueryPathFromRegistry

- ea: `0x140012204`
- end: `0x14001231a`
- name: `SmpQueryPathFromRegistry`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x140009100`
- `0x140011c50`

## callees

- `0x140012204`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x140012267`
- `ntdll!NtQueryValueKey` at `0x140012267`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1400122bc`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1400122bc`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400122e1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400122e1`

## pseudocode

```c
NTSTATUS __fastcall SmpQueryPathFromRegistry(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        const WCHAR *a3,
        struct _UNICODE_STRING *a4)
{
  NTSTATUS result; // eax
  const WCHAR *Buffer; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING Source; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v12; // [rsp+64h] [rbp-9Ch]
  _BYTE v13[516]; // [rsp+6Ch] [rbp-94h] BYREF
  char v14; // [rsp+270h] [rbp+170h] BYREF

  ResultLength = 528;
  Source = 0;
  Destination = 0;
  result = NtQueryValueKey(SmpCrashDumpKey, a2, KeyValuePartialInformation, KeyValueInformation, 0x210u, &ResultLength);
  if ( result >= 0 )
  {
    if ( v12 == 2 )
    {
      *(_DWORD *)&Destination.Length = 33816576;
      Source.Length = ResultLength - 12;
      Source.MaximumLength = ResultLength - 12;
      Source.Buffer = (PWSTR)v13;
      Destination.Buffer = (PWSTR)&v14;
      result = RtlExpandEnvironmentStrings_U(0, &Source, &Destination, 0);
      if ( result >= 0 )
      {
        Buffer = Destination.Buffer;
        if ( Destination.Buffer )
          return RtlDosPathNameToNtPathName_U(Buffer, a4, 0, 0) == 0 ? 0xC0000001 : 0;
      }
    }
    else if ( v12 == 1 )
    {
      Buffer = (const WCHAR *)v13;
      return RtlDosPathNameToNtPathName_U(Buffer, a4, 0, 0) == 0 ? 0xC0000001 : 0;
    }
  }
  if ( !a3 )
    return result;
  Buffer = a3;
  return RtlDosPathNameToNtPathName_U(Buffer, a4, 0, 0) == 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x140012204  push    rbp
0x140012206  push    rbx
0x140012207  push    rdi
0x140012208  lea     rbp, [rsp-390h]
0x140012210  sub     rsp, 490h
0x140012217  mov     rax, cs:__security_cookie
0x14001221e  xor     rax, rsp
0x140012221  mov     [rbp+3A0h+var_20], rax
0x140012228  mov     ecx, 210h
0x14001222d  lea     rax, [rsp+4A0h+var_470]
0x140012232  mov     [rsp+4A0h+ResultLength], rax; ResultLength
0x140012237  mov     rdi, r9
0x14001223a  mov     [rsp+4A0h+Length], ecx; Length
0x14001223e  lea     r9, [rsp+4A0h+KeyValueInformation]; KeyValueInformation
0x140012243  mov     rbx, r8
0x140012246  mov     [rsp+4A0h+var_470], ecx
0x14001224a  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x140012251  xorps   xmm0, xmm0
0x140012254  xorps   xmm1, xmm1
0x140012257  mov     r8d, 2; KeyValueInformationClass
0x14001225d  movups  xmmword ptr [rsp+4A0h+Source.Length], xmm0
0x140012262  movups  xmmword ptr [rsp+4A0h+Destination.Length], xmm1
0x140012267  call    cs:__imp_NtQueryValueKey
0x14001226d  test    eax, eax
0x14001226f  js      short loc_1400122D0
0x140012271  cmp     [rsp+4A0h+var_43C], 2
0x140012276  jnz     loc_14001230C
0x14001227c  movzx   eax, word ptr [rsp+4A0h+var_470]
0x140012281  lea     r8, [rsp+4A0h+Destination]; Destination
0x140012286  sub     ax, 0Ch
0x14001228a  mov     dword ptr [rsp+4A0h+Destination.Length], 2040000h
0x140012292  mov     [rsp+4A0h+Source.Length], ax
0x140012297  lea     rdx, [rsp+4A0h+Source]; Source
0x14001229c  mov     [rsp+4A0h+Source.MaximumLength], ax
0x1400122a1  xor     r9d, r9d; Length
0x1400122a4  lea     rax, [rsp+4A0h+var_434]
0x1400122a9  xor     ecx, ecx; Environment
0x1400122ab  mov     [rsp+4A0h+Source.Buffer], rax
0x1400122b0  lea     rax, [rbp+3A0h+var_230]
0x1400122b7  mov     [rsp+4A0h+Destination.Buffer], rax
0x1400122bc  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x1400122c2  test    eax, eax
0x1400122c4  js      short loc_1400122D0
0x1400122c6  mov     rcx, [rsp+4A0h+Destination.Buffer]
0x1400122cb  test    rcx, rcx
0x1400122ce  jnz     short loc_1400122D8
0x1400122d0  test    rbx, rbx
0x1400122d3  jz      short loc_1400122F2
0x1400122d5  mov     rcx, rbx; DosPathName
0x1400122d8  xor     r9d, r9d; DirectoryInfo
0x1400122db  xor     r8d, r8d; NtFileNamePart
0x1400122de  mov     rdx, rdi; NtPathName
0x1400122e1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400122e7  neg     al
0x1400122e9  sbb     eax, eax
0x1400122eb  not     eax
0x1400122ed  and     eax, 0C0000001h
0x1400122f2  mov     rcx, [rbp+3A0h+var_20]
0x1400122f9  xor     rcx, rsp; StackCookie
0x1400122fc  call    __security_check_cookie
0x140012301  add     rsp, 490h
0x140012308  pop     rdi
0x140012309  pop     rbx
0x14001230a  pop     rbp
0x14001230b  retn
0x14001230c  cmp     [rsp+4A0h+var_43C], 1
0x140012311  jnz     short loc_1400122D0
0x140012313  lea     rcx, [rsp+4A0h+var_434]
0x140012318  jmp     short loc_1400122D8
```
