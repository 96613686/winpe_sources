# ElTraceErrorInfo

- ea: `0x180003130`
- end: `0x180003202`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003208`
- `0x180003c68`
- `0x180006714`
- `0x180006fe8`
- `0x1800077f8`
- `0x1800086e4`
- `0x18000d5b0`
- `0x18000d780`

## callees

- `0x180003130`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800031f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800031f0`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180003147`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180003147`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800031be`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800031be`

## string_xrefs

- `0x180003187`: `COM Error: '%s'`
- `0x1800031ab`: `COM Error: '%s'`

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
0x180003130  sub     rsp, 28h
0x180003134  and     [rsp+28h+pperrinfo], 0
0x18000313a  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x18000313f  and     [rsp+28h+bstrString], 0
0x180003145  xor     ecx, ecx; dwReserved
0x180003147  call    cs:__imp_GetErrorInfo
0x18000314e  nop     dword ptr [rax+rax+00h]
0x180003153  test    eax, eax
0x180003155  js      short loc_1800031CA
0x180003157  cmp     eax, 1
0x18000315a  jz      short loc_1800031CA
0x18000315c  mov     rcx, [rsp+28h+pperrinfo]
0x180003161  lea     rdx, [rsp+28h+bstrString]
0x180003166  mov     rax, [rcx]
0x180003169  mov     rax, [rax+28h]
0x18000316d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003172  test    eax, eax
0x180003174  js      short loc_1800031CA
0x180003176  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000317d  test    rax, rax
0x180003180  jz      short loc_18000319A
0x180003182  mov     r8, [rsp+28h+bstrString]
0x180003187  lea     rdx, aComErrorS; "COM Error: '%s'"
0x18000318e  mov     ecx, 80000h
0x180003193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003198  jmp     short loc_1800031B7
0x18000319a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800031a1  test    rax, rax
0x1800031a4  jz      short loc_1800031B7
0x1800031a6  mov     rdx, [rsp+28h+bstrString]
0x1800031ab  lea     rcx, aComErrorS; "COM Error: '%s'"
0x1800031b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b7  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x1800031bc  xor     ecx, ecx; dwReserved
0x1800031be  call    cs:__imp_SetErrorInfo
0x1800031c5  nop     dword ptr [rax+rax+00h]
0x1800031ca  mov     rcx, [rsp+28h+pperrinfo]
0x1800031cf  test    rcx, rcx
0x1800031d2  jz      short loc_1800031E6
0x1800031d4  mov     rax, [rcx]
0x1800031d7  mov     rax, [rax+10h]
0x1800031db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e0  and     [rsp+28h+pperrinfo], 0
0x1800031e6  mov     rcx, [rsp+28h+bstrString]; bstrString
0x1800031eb  test    rcx, rcx
0x1800031ee  jz      short loc_1800031FC
0x1800031f0  call    cs:__imp_SysFreeString
0x1800031f7  nop     dword ptr [rax+rax+00h]
0x1800031fc  add     rsp, 28h
0x180003200  retn
```
