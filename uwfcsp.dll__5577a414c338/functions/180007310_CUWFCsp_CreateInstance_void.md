# CUWFCsp::CreateInstance(void)

- ea: `0x180007310`
- end: `0x180007365`
- name: `?CreateInstance@CUWFCsp@@SAPEAUIUnknown@@XZ`
- size: `85`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180002c54`
- `0x180007310`

## pseudocode

```c
struct IUnknown *CUWFCsp::CreateInstance(void)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)operator new(0x30u);
  if ( result )
  {
    result[2].lpVtbl = 0;
    result[4].lpVtbl = (struct IUnknownVtbl *)&off_180027A48;
    result->lpVtbl = (struct IUnknownVtbl *)&CUWFCsp::`vftable'{for `IConfigServiceProvider2'};
    result[1].lpVtbl = (struct IUnknownVtbl *)&CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'};
    LODWORD(result[3].lpVtbl) = 0;
    LODWORD(result[5].lpVtbl) = 1;
    _InterlockedIncrement(&dword_180028594);
  }
  return result;
}

```

## disassembly

```asm
0x180007310  sub     rsp, 28h
0x180007314  mov     ecx, 30h ; '0'; Size
0x180007319  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000731e  test    rax, rax
0x180007321  jz      short loc_180007360
0x180007323  lea     rcx, off_180027A48
0x18000732a  mov     qword ptr [rax+10h], 0
0x180007332  mov     [rax+20h], rcx
0x180007336  lea     rcx, ??_7CUWFCsp@@6BIConfigServiceProvider2@@@; const CUWFCsp::`vftable'{for `IConfigServiceProvider2'}
0x18000733d  mov     [rax], rcx
0x180007340  lea     rcx, ??_7CConfigServiceProvider2Impl@@6BICSPValidate@@@; const CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'}
0x180007347  mov     [rax+8], rcx
0x18000734b  mov     dword ptr [rax+18h], 0
0x180007352  mov     dword ptr [rax+28h], 1
0x180007359  lock inc cs:dword_180028594
0x180007360  add     rsp, 28h
0x180007364  retn
```
