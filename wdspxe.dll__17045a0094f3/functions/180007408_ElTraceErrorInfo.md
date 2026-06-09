# ElTraceErrorInfo

- ea: `0x180007408`
- end: `0x1800074da`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800074e0`

## callees

- `0x180007408`
- `0x180013010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800074c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800074c8`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000741f`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000741f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007496`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180007496`

## string_xrefs

- `0x18000745f`: `COM Error: '%s'`
- `0x180007483`: `COM Error: '%s'`

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
0x180007408  sub     rsp, 28h
0x18000740c  and     [rsp+28h+pperrinfo], 0
0x180007412  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180007417  and     [rsp+28h+bstrString], 0
0x18000741d  xor     ecx, ecx; dwReserved
0x18000741f  call    cs:__imp_GetErrorInfo
0x180007426  nop     dword ptr [rax+rax+00h]
0x18000742b  test    eax, eax
0x18000742d  js      short loc_1800074A2
0x18000742f  cmp     eax, 1
0x180007432  jz      short loc_1800074A2
0x180007434  mov     rcx, [rsp+28h+pperrinfo]
0x180007439  lea     rdx, [rsp+28h+bstrString]
0x18000743e  mov     rax, [rcx]
0x180007441  mov     rax, [rax+28h]
0x180007445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000744a  test    eax, eax
0x18000744c  js      short loc_1800074A2
0x18000744e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180007455  test    rax, rax
0x180007458  jz      short loc_180007472
0x18000745a  mov     r8, [rsp+28h+bstrString]
0x18000745f  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180007466  mov     ecx, 80000h
0x18000746b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007470  jmp     short loc_18000748F
0x180007472  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007479  test    rax, rax
0x18000747c  jz      short loc_18000748F
0x18000747e  mov     rdx, [rsp+28h+bstrString]
0x180007483  lea     rcx, aComErrorS; "COM Error: '%s'"
0x18000748a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748f  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180007494  xor     ecx, ecx; dwReserved
0x180007496  call    cs:__imp_SetErrorInfo
0x18000749d  nop     dword ptr [rax+rax+00h]
0x1800074a2  mov     rcx, [rsp+28h+pperrinfo]
0x1800074a7  test    rcx, rcx
0x1800074aa  jz      short loc_1800074BE
0x1800074ac  mov     rax, [rcx]
0x1800074af  mov     rax, [rax+10h]
0x1800074b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b8  and     [rsp+28h+pperrinfo], 0
0x1800074be  mov     rcx, [rsp+28h+bstrString]; bstrString
0x1800074c3  test    rcx, rcx
0x1800074c6  jz      short loc_1800074D4
0x1800074c8  call    cs:__imp_SysFreeString
0x1800074cf  nop     dword ptr [rax+rax+00h]
0x1800074d4  add     rsp, 28h
0x1800074d8  retn
```
