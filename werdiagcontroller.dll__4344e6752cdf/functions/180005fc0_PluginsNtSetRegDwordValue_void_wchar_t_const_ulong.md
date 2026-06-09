# PluginsNtSetRegDwordValue(void *,wchar_t const *,ulong)

- ea: `0x180005fc0`
- end: `0x180006064`
- name: `?PluginsNtSetRegDwordValue@@YAJPEAXPEB_WK@Z`
- size: `164`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const wchar_t *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800028d0`
- `0x180002cc8`
- `0x1800034cc`
- `0x180005158`

## callees

- `0x180005fc0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180005feb`
- `ntdll!RtlInitUnicodeString` at `0x180005feb`
- `ntdll!DbgPrintEx` at `0x180006032`
- `ntdll!DbgPrintEx` at `0x18000604e`
- `ntdll!DbgPrintEx` at `0x180006032`
- `ntdll!DbgPrintEx` at `0x18000604e`
- `ntdll!NtSetValueKey` at `0x180006011`
- `ntdll!NtSetValueKey` at `0x180006011`

## pseudocode

```c
__int64 __fastcall PluginsNtSetRegDwordValue(HANDLE KeyHandle, const wchar_t *a2, int a3)
{
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF

  Data = a3;
  ValueName = 0;
  if ( a2 && KeyHandle )
  {
    RtlInitUnicodeString(&ValueName, a2);
    v5 = NtSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    v6 = v5;
    if ( v5 >= 0 )
      return 0;
    else
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed writing to value %S. NTSTATUS: %08X\n", a2, v5);
    return v6;
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
0x180005fc0  mov     rax, rsp
0x180005fc3  mov     [rax+8], rbx
0x180005fc7  mov     [rax+18h], r8d
0x180005fcb  push    rdi
0x180005fcc  sub     rsp, 40h
0x180005fd0  xorps   xmm0, xmm0
0x180005fd3  mov     rdi, rdx
0x180005fd6  mov     rbx, rcx
0x180005fd9  movups  xmmword ptr [rax-18h], xmm0
0x180005fdd  test    rdx, rdx
0x180005fe0  jz      short loc_180006040
0x180005fe2  test    rcx, rcx
0x180005fe5  jz      short loc_180006040
0x180005fe7  lea     rcx, [rax-18h]; DestinationString
0x180005feb  call    cs:__imp_RtlInitUnicodeString
0x180005ff1  mov     r9d, 4; Type
0x180005ff7  lea     rax, [rsp+48h+arg_10]
0x180005ffc  mov     [rsp+48h+DataSize], r9d; DataSize
0x180006001  lea     rdx, [rsp+48h+ValueName]; ValueName
0x180006006  xor     r8d, r8d; TitleIndex
0x180006009  mov     [rsp+48h+Data], rax; Data
0x18000600e  mov     rcx, rbx; KeyHandle
0x180006011  call    cs:__imp_NtSetValueKey
0x180006017  mov     ebx, eax
0x180006019  test    eax, eax
0x18000601b  jns     short loc_18000603A
0x18000601d  mov     r9, rdi
0x180006020  mov     dword ptr [rsp+48h+Data], eax
0x180006024  lea     r8, aWerdiagFailedW_3; "WERDIAG: Failed writing to value %S. NT"...
0x18000602b  xor     edx, edx; Level
0x18000602d  mov     ecx, 96h; ComponentId
0x180006032  call    cs:__imp_DbgPrintEx
0x180006038  jmp     short loc_18000603C
0x18000603a  xor     ebx, ebx
0x18000603c  mov     eax, ebx
0x18000603e  jmp     short loc_180006059
0x180006040  lea     r8, aWerdiagInvalid_3; "WERDIAG: Invalid parameters\n"
0x180006047  xor     edx, edx; Level
0x180006049  mov     ecx, 96h; ComponentId
0x18000604e  call    cs:__imp_DbgPrintEx
0x180006054  mov     eax, 0C000000Dh
0x180006059  mov     rbx, [rsp+48h+arg_0]
0x18000605e  add     rsp, 40h
0x180006062  pop     rdi
0x180006063  retn
```
