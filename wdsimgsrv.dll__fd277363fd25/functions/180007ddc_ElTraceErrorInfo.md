# ElTraceErrorInfo

- ea: `0x180007ddc`
- end: `0x180007eae`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007eb4`
- `0x18000ad88`
- `0x18000cbd4`
- `0x18000fc04`
- `0x18000ffbc`
- `0x180010f6c`
- `0x180011e48`
- `0x18001560c`

## callees

- `0x180007ddc`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007e9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007e9c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007df3`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007df3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007e6a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007e6a`

## string_xrefs

- `0x180007e33`: `COM Error: '%s'`
- `0x180007e57`: `COM Error: '%s'`

## pseudocode

```c
void ElTraceErrorInfo()
{
  HRESULT ErrorInfo; // eax
  IErrorInfo *pperrinfo; // [rsp+30h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp+10h] BYREF

  pperrinfo = 0;
  bstrString = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  if ( ErrorInfo >= 0
    && ErrorInfo != 1
    && ((int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &bstrString) >= 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      g_ErrLibTraceFunctionEx(0x80000u, L"COM Error: '%s'", bstrString);
    }
    else if ( g_ErrLibTraceFunction )
    {
      g_ErrLibTraceFunction(L"COM Error: '%s'", bstrString);
    }
    SetErrorInfo(0, pperrinfo);
  }
  if ( pperrinfo )
  {
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    pperrinfo = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
}

```

## disassembly

```asm
0x180007ddc  sub     rsp, 28h
0x180007de0  and     [rsp+28h+pperrinfo], 0
0x180007de6  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180007deb  and     [rsp+28h+bstrString], 0
0x180007df1  xor     ecx, ecx; dwReserved
0x180007df3  call    cs:__imp_GetErrorInfo
0x180007dfa  nop     dword ptr [rax+rax+00h]
0x180007dff  test    eax, eax
0x180007e01  js      short loc_180007E76
0x180007e03  cmp     eax, 1
0x180007e06  jz      short loc_180007E76
0x180007e08  mov     rcx, [rsp+28h+pperrinfo]
0x180007e0d  lea     rdx, [rsp+28h+bstrString]
0x180007e12  mov     rax, [rcx]
0x180007e15  mov     rax, [rax+28h]
0x180007e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e1e  test    eax, eax
0x180007e20  js      short loc_180007E76
0x180007e22  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007e29  test    rax, rax
0x180007e2c  jz      short loc_180007E46
0x180007e2e  mov     r8, [rsp+28h+bstrString]
0x180007e33  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180007e3a  mov     ecx, 80000h
0x180007e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e44  jmp     short loc_180007E63
0x180007e46  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007e4d  test    rax, rax
0x180007e50  jz      short loc_180007E63
0x180007e52  mov     rdx, [rsp+28h+bstrString]
0x180007e57  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180007e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e63  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180007e68  xor     ecx, ecx; dwReserved
0x180007e6a  call    cs:__imp_SetErrorInfo
0x180007e71  nop     dword ptr [rax+rax+00h]
0x180007e76  mov     rcx, [rsp+28h+pperrinfo]
0x180007e7b  test    rcx, rcx
0x180007e7e  jz      short loc_180007E92
0x180007e80  mov     rax, [rcx]
0x180007e83  mov     rax, [rax+10h]
0x180007e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e8c  and     [rsp+28h+pperrinfo], 0
0x180007e92  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180007e97  test    rcx, rcx
0x180007e9a  jz      short loc_180007EA8
0x180007e9c  call    cs:__imp_SysFreeString
0x180007ea3  nop     dword ptr [rax+rax+00h]
0x180007ea8  add     rsp, 28h
0x180007eac  retn
```
