# PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)

- ea: `0x180005990`
- end: `0x180005a94`
- name: `?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z`
- size: `260`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const wchar_t *, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180002790`
- `0x1800028d0`
- `0x180002cc8`
- `0x1800034cc`
- `0x180003838`

## callees

- `0x180001ce0`
- `0x180001d10`
- `0x180005990`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800059d1`
- `ntdll!RtlInitUnicodeString` at `0x1800059d1`
- `ntdll!DbgPrintEx` at `0x1800059fe`
- `ntdll!DbgPrintEx` at `0x180005a5f`
- `ntdll!DbgPrintEx` at `0x180005a7f`
- `ntdll!DbgPrintEx` at `0x1800059fe`
- `ntdll!DbgPrintEx` at `0x180005a5f`
- `ntdll!DbgPrintEx` at `0x180005a7f`
- `ntdll!NtQueryValueKey` at `0x180005a2e`
- `ntdll!NtQueryValueKey` at `0x180005a2e`

## string_xrefs

- `0x180005a51`: `WERDIAG: Failed extracting registry value %S. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall PluginsNtGetRegDwordValue(HANDLE KeyHandle, const wchar_t *a2, unsigned int *a3)
{
  _DWORD *v6; // rdi
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp+10h] BYREF

  ResultLength = 0;
  DestinationString = 0;
  if ( a2 && KeyHandle )
  {
    *a3 = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    v6 = operator new(0x13u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      v8 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v6, 0x13u, &ResultLength);
      v7 = v8;
      if ( v8 >= 0 && v6[1] == 4 )
      {
        v7 = 0;
        *a3 = v6[3];
      }
      else
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed extracting registry value %S. NTSTATUS: %08X\n", a2, v8);
      }
      operator delete(v6);
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for key information structure\n");
      return (unsigned int)-1073741670;
    }
    return v7;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid parameters\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180005990  push    rbx
0x180005992  push    rsi
0x180005993  push    rdi
0x180005994  push    r14
0x180005996  sub     rsp, 48h
0x18000599a  mov     [rsp+68h+arg_8], 0
0x1800059a2  xorps   xmm0, xmm0
0x1800059a5  mov     r14, r8
0x1800059a8  mov     rsi, rdx
0x1800059ab  mov     rbx, rcx
0x1800059ae  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800059b3  test    rdx, rdx
0x1800059b6  jz      loc_180005A71
0x1800059bc  test    rcx, rcx
0x1800059bf  jz      loc_180005A71
0x1800059c5  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800059ca  mov     dword ptr [r8], 0
0x1800059d1  call    cs:__imp_RtlInitUnicodeString
0x1800059d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800059de  mov     ecx, 13h; unsigned __int64
0x1800059e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800059e8  mov     rdi, rax
0x1800059eb  test    rax, rax
0x1800059ee  jnz     short loc_180005A0B
0x1800059f0  lea     r8, aWerdiagOutOfRe_0; "WERDIAG: Out of resources allocating me"...
0x1800059f7  xor     edx, edx; Level
0x1800059f9  mov     ecx, 96h; ComponentId
0x1800059fe  call    cs:__imp_DbgPrintEx
0x180005a04  mov     ebx, 0C000009Ah
0x180005a09  jmp     short loc_180005A6D
0x180005a0b  lea     rax, [rsp+68h+arg_8]
0x180005a10  mov     r9, rdi; KeyValueInformation
0x180005a13  mov     [rsp+68h+ResultLength], rax; ResultLength
0x180005a18  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x180005a1d  mov     r8d, 2; KeyValueInformationClass
0x180005a23  mov     [rsp+68h+Length], 13h; Length
0x180005a2b  mov     rcx, rbx; KeyHandle
0x180005a2e  call    cs:__imp_NtQueryValueKey
0x180005a34  mov     ebx, eax
0x180005a36  test    eax, eax
0x180005a38  js      short loc_180005A4A
0x180005a3a  cmp     dword ptr [rdi+4], 4
0x180005a3e  jnz     short loc_180005A4A
0x180005a40  mov     eax, [rdi+0Ch]
0x180005a43  xor     ebx, ebx
0x180005a45  mov     [r14], eax
0x180005a48  jmp     short loc_180005A65
0x180005a4a  mov     r9, rsi
0x180005a4d  mov     [rsp+68h+Length], eax
0x180005a51  lea     r8, aWerdiagFailedE_2; "WERDIAG: Failed extracting registry val"...
0x180005a58  xor     edx, edx; Level
0x180005a5a  mov     ecx, 96h; ComponentId
0x180005a5f  call    cs:__imp_DbgPrintEx
0x180005a65  mov     rcx, rdi; Block
0x180005a68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a6d  mov     eax, ebx
0x180005a6f  jmp     short loc_180005A8A
0x180005a71  lea     r8, aWerdiagInvalid_3; "WERDIAG: Invalid parameters\n"
0x180005a78  xor     edx, edx; Level
0x180005a7a  mov     ecx, 96h; ComponentId
0x180005a7f  call    cs:__imp_DbgPrintEx
0x180005a85  mov     eax, 0C000000Dh
0x180005a8a  add     rsp, 48h
0x180005a8e  pop     r14
0x180005a90  pop     rdi
0x180005a91  pop     rsi
0x180005a92  pop     rbx
0x180005a93  retn
```
