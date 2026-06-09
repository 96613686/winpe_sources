# PluginsNtSetRegStringValue(void *,wchar_t const *,wchar_t const *)

- ea: `0x18000606c`
- end: `0x180006121`
- name: `?PluginsNtSetRegStringValue@@YAJPEAXPEB_W1@Z`
- size: `181`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800034cc`
- `0x180003e10`

## callees

- `0x18000606c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000609c`
- `ntdll!RtlInitUnicodeString` at `0x18000609c`
- `ntdll!DbgPrintEx` at `0x1800060f1`
- `ntdll!DbgPrintEx` at `0x18000610d`
- `ntdll!DbgPrintEx` at `0x1800060f1`
- `ntdll!DbgPrintEx` at `0x18000610d`
- `ntdll!NtSetValueKey` at `0x1800060d0`
- `ntdll!NtSetValueKey` at `0x1800060d0`

## pseudocode

```c
__int64 __fastcall PluginsNtSetRegStringValue(HANDLE KeyHandle, const wchar_t *a2, wchar_t *a3)
{
  __int64 v6; // rax
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  if ( a2 && KeyHandle && a3 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = NtSetValueKey(KeyHandle, &DestinationString, 0, 1u, a3, 2 * v6 + 2);
    v8 = v7;
    if ( v7 >= 0 )
      return 0;
    else
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed writing to value %S. NTSTATUS %08X\n", a2, v7);
    return v8;
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
0x18000606c  push    rbx
0x18000606e  push    rbp
0x18000606f  push    rsi
0x180006070  push    rdi
0x180006071  sub     rsp, 48h
0x180006075  xor     ebp, ebp
0x180006077  xorps   xmm0, xmm0
0x18000607a  mov     rbx, r8
0x18000607d  mov     rdi, rdx
0x180006080  mov     rsi, rcx
0x180006083  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180006088  test    rdx, rdx
0x18000608b  jz      short loc_1800060FF
0x18000608d  test    rcx, rcx
0x180006090  jz      short loc_1800060FF
0x180006092  test    rbx, rbx
0x180006095  jz      short loc_1800060FF
0x180006097  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000609c  call    cs:__imp_RtlInitUnicodeString
0x1800060a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800060a6  inc     rax
0x1800060a9  cmp     [rbx+rax*2], bp
0x1800060ad  jnz     short loc_1800060A6
0x1800060af  lea     eax, ds:2[rax*2]
0x1800060b6  mov     r9d, 1; Type
0x1800060bc  mov     [rsp+68h+DataSize], eax; DataSize
0x1800060c0  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x1800060c5  xor     r8d, r8d; TitleIndex
0x1800060c8  mov     [rsp+68h+Data], rbx; Data
0x1800060cd  mov     rcx, rsi; KeyHandle
0x1800060d0  call    cs:__imp_NtSetValueKey
0x1800060d6  mov     ebx, eax
0x1800060d8  test    eax, eax
0x1800060da  jns     short loc_1800060F9
0x1800060dc  mov     r9, rdi
0x1800060df  mov     dword ptr [rsp+68h+Data], eax
0x1800060e3  lea     r8, aWerdiagFailedW_1; "WERDIAG: Failed writing to value %S. NT"...
0x1800060ea  xor     edx, edx; Level
0x1800060ec  mov     ecx, 96h; ComponentId
0x1800060f1  call    cs:__imp_DbgPrintEx
0x1800060f7  jmp     short loc_1800060FB
0x1800060f9  mov     ebx, ebp
0x1800060fb  mov     eax, ebx
0x1800060fd  jmp     short loc_180006118
0x1800060ff  lea     r8, aWerdiagInvalid_3; "WERDIAG: Invalid parameters\n"
0x180006106  xor     edx, edx; Level
0x180006108  mov     ecx, 96h; ComponentId
0x18000610d  call    cs:__imp_DbgPrintEx
0x180006113  mov     eax, 0C000000Dh
0x180006118  add     rsp, 48h
0x18000611c  pop     rdi
0x18000611d  pop     rsi
0x18000611e  pop     rbp
0x18000611f  pop     rbx
0x180006120  retn
```
