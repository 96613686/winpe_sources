# EcQuickConfig(void)

- ea: `0x180003930`
- end: `0x180003969`
- name: `?EcQuickConfig@@YAHXZ`
- size: `57`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180003930`
- `0x18000908c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003951`

## pseudocode

```c
__int64 EcQuickConfig(void)
{
  unsigned int v0; // ebx
  DWORD v1; // edi
  wmi::Exception *v3; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v0 = 0;
    v1 = 0;
    SetupChannelAndService(1);
  }
  catch ( wmi::Exception *v3 )
  {
    v0 = 0;
    v1 = (**(__int64 (__fastcall ***)(wmi::Exception *))v3)(v3);
  }
  v0 = 0;
  v1 = 0;
  SetupChannelAndService(1);
}

```

## disassembly

```asm
0x180003930  mov     [rsp+arg_8], rbx
0x180003935  push    rdi
0x180003936  sub     rsp, 30h
0x18000393a  xor     ebx, ebx
0x18000393c  mov     edi, ebx
0x18000393e  lea     ecx, [rbx+1]; int
0x180003941  call    ?SetupChannelAndService@@YAHH@Z; SetupChannelAndService(int)
0x180003946  nop
0x180003947  jmp     short loc_18000394F
0x180003949  xor     ebx, ebx
0x18000394b  mov     edi, [rsp+38h+arg_0]
0x18000394f  mov     ecx, edi; dwErrCode
0x180003951  call    cs:__imp_SetLastError
0x180003957  test    edi, edi
0x180003959  setz    bl
0x18000395c  mov     eax, ebx
0x18000395e  mov     rbx, [rsp+38h+arg_8]
0x180003963  add     rsp, 30h
0x180003967  pop     rdi
0x180003968  retn
```
