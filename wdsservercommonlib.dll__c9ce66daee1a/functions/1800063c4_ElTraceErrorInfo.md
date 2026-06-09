# ElTraceErrorInfo

- ea: `0x1800063c4`
- end: `0x180006496`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000649c`
- `0x180007d30`
- `0x18000f398`
- `0x180011088`
- `0x1800165e4`
- `0x1800175a8`
- `0x18001a190`
- `0x18001e0dc`
- `0x180022b9c`
- `0x180025e30`
- `0x180025f80`
- `0x180027294`
- `0x180027de8`
- `0x1800287cc`
- `0x180028dd8`
- `0x180029770`
- `0x18002d064`

## callees

- `0x1800063c4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006484`
- `OLEAUT32!__imp_SysFreeString` at `0x180006484`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800063db`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800063db`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006452`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006452`

## string_xrefs

- `0x18000641b`: `COM Error: '%s'`
- `0x18000643f`: `COM Error: '%s'`

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
0x1800063c4  sub     rsp, 28h
0x1800063c8  and     [rsp+28h+pperrinfo], 0
0x1800063ce  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x1800063d3  and     [rsp+28h+bstrString], 0
0x1800063d9  xor     ecx, ecx; dwReserved
0x1800063db  call    cs:__imp_GetErrorInfo
0x1800063e2  nop     dword ptr [rax+rax+00h]
0x1800063e7  test    eax, eax
0x1800063e9  js      short loc_18000645E
0x1800063eb  cmp     eax, 1
0x1800063ee  jz      short loc_18000645E
0x1800063f0  mov     rcx, [rsp+28h+pperrinfo]
0x1800063f5  lea     rdx, [rsp+28h+bstrString]
0x1800063fa  mov     rax, [rcx]
0x1800063fd  mov     rax, [rax+28h]
0x180006401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006406  test    eax, eax
0x180006408  js      short loc_18000645E
0x18000640a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006411  test    rax, rax
0x180006414  jz      short loc_18000642E
0x180006416  mov     r8, [rsp+28h+bstrString]
0x18000641b  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180006422  mov     ecx, 80000h
0x180006427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642c  jmp     short loc_18000644B
0x18000642e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006435  test    rax, rax
0x180006438  jz      short loc_18000644B
0x18000643a  mov     rdx, [rsp+28h+bstrString]
0x18000643f  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180006446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000644b  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180006450  xor     ecx, ecx; dwReserved
0x180006452  call    cs:__imp_SetErrorInfo
0x180006459  nop     dword ptr [rax+rax+00h]
0x18000645e  mov     rcx, [rsp+28h+pperrinfo]
0x180006463  test    rcx, rcx
0x180006466  jz      short loc_18000647A
0x180006468  mov     rax, [rcx]
0x18000646b  mov     rax, [rax+10h]
0x18000646f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006474  and     [rsp+28h+pperrinfo], 0
0x18000647a  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000647f  test    rcx, rcx
0x180006482  jz      short loc_180006490
0x180006484  call    cs:__imp_SysFreeString
0x18000648b  nop     dword ptr [rax+rax+00h]
0x180006490  add     rsp, 28h
0x180006494  retn
```
