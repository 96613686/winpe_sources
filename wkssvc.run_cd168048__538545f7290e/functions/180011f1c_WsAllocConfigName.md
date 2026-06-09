# WsAllocConfigName

- ea: `0x180011f1c`
- end: `0x180011fda`
- name: `WsAllocConfigName`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002fe70`

## callees

- `0x180007cd4`
- `0x180011f1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f30`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011f30`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011f82`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011f9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011fb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011f82`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011f9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011fb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011f6a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011f6a`

## string_xrefs

- `0x180011f5e`: `System\CurrentControlSet\Services\`
- `0x180011f26`: `ServicesActive`

## pseudocode

```c
__int64 WsAllocConfigName()
{
  __int64 v0; // rax
  const WCHAR *v1; // rbx
  __int64 result; // rax

  if ( (unsigned int)_o__wcsicmp(L"ServicesActive", L"ServicesActive") )
    return 87;
  v0 = NetpMemoryAllocate(126);
  v1 = (const WCHAR *)v0;
  if ( !v0 )
    return 8;
  _o_wcscpy_s(v0, 63, L"System\\CurrentControlSet\\Services\\");
  _o_wcscat_s(v1, 63, L"LanmanWorkstation");
  _o_wcscat_s(v1, 63, L"\\");
  _o_wcscat_s(v1, 63, L"Parameters");
  result = 0;
  RegPathToWatch = v1;
  return result;
}

```

## disassembly

```asm
0x180011f1c  mov     [rsp+arg_0], rbx
0x180011f21  push    rdi
0x180011f22  sub     rsp, 20h
0x180011f26  lea     rcx, aServicesactive; "ServicesActive"
0x180011f2d  mov     rdx, rcx
0x180011f30  call    cs:__imp__o__wcsicmp
0x180011f37  nop     dword ptr [rax+rax+00h]
0x180011f3c  test    eax, eax
0x180011f3e  jnz     loc_180011FC9
0x180011f44  lea     ecx, [rax+7Eh]
0x180011f47  call    NetpMemoryAllocate
0x180011f4c  mov     rbx, rax
0x180011f4f  test    rax, rax
0x180011f52  jnz     short loc_180011F59
0x180011f54  lea     eax, [rbx+8]
0x180011f57  jmp     short loc_180011FCE
0x180011f59  mov     edi, 3Fh ; '?'
0x180011f5e  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\"
0x180011f65  mov     edx, edi
0x180011f67  mov     rcx, rbx
0x180011f6a  call    cs:__imp__o_wcscpy_s
0x180011f71  nop     dword ptr [rax+rax+00h]
0x180011f76  lea     r8, aLanmanworkstat; "LanmanWorkstation"
0x180011f7d  mov     edx, edi
0x180011f7f  mov     rcx, rbx
0x180011f82  call    cs:__imp__o_wcscat_s
0x180011f89  nop     dword ptr [rax+rax+00h]
0x180011f8e  lea     r8, Src; "\\"
0x180011f95  mov     edx, edi
0x180011f97  mov     rcx, rbx
0x180011f9a  call    cs:__imp__o_wcscat_s
0x180011fa1  nop     dword ptr [rax+rax+00h]
0x180011fa6  lea     r8, aParameters; "Parameters"
0x180011fad  mov     edx, edi
0x180011faf  mov     rcx, rbx
0x180011fb2  call    cs:__imp__o_wcscat_s
0x180011fb9  nop     dword ptr [rax+rax+00h]
0x180011fbe  xor     eax, eax
0x180011fc0  mov     cs:RegPathToWatch, rbx
0x180011fc7  jmp     short loc_180011FCE
0x180011fc9  mov     eax, 57h ; 'W'
0x180011fce  mov     rbx, [rsp+28h+arg_0]
0x180011fd3  add     rsp, 20h
0x180011fd7  pop     rdi
0x180011fd8  retn
```
