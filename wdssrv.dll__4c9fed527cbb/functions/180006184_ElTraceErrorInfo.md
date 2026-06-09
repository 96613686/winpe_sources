# ElTraceErrorInfo

- ea: `0x180006184`
- end: `0x180006256`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005600`
- `0x18001ae58`
- `0x18001b748`

## callees

- `0x180006184`
- `0x18001d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006244`
- `OLEAUT32!__imp_SysFreeString` at `0x180006244`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000619b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000619b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006212`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006212`

## string_xrefs

- `0x1800061db`: `COM Error: '%s'`
- `0x1800061ff`: `COM Error: '%s'`

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
0x180006184  sub     rsp, 28h
0x180006188  and     [rsp+28h+pperrinfo], 0
0x18000618e  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180006193  and     [rsp+28h+bstrString], 0
0x180006199  xor     ecx, ecx; dwReserved
0x18000619b  call    cs:__imp_GetErrorInfo
0x1800061a2  nop     dword ptr [rax+rax+00h]
0x1800061a7  test    eax, eax
0x1800061a9  js      short loc_18000621E
0x1800061ab  cmp     eax, 1
0x1800061ae  jz      short loc_18000621E
0x1800061b0  mov     rcx, [rsp+28h+pperrinfo]
0x1800061b5  lea     rdx, [rsp+28h+bstrString]
0x1800061ba  mov     rax, [rcx]
0x1800061bd  mov     rax, [rax+28h]
0x1800061c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c6  test    eax, eax
0x1800061c8  js      short loc_18000621E
0x1800061ca  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800061d1  test    rax, rax
0x1800061d4  jz      short loc_1800061EE
0x1800061d6  mov     r8, [rsp+28h+bstrString]
0x1800061db  lea     rdx, aComErrorS; "COM Error: '%s'"
0x1800061e2  mov     ecx, 80000h
0x1800061e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ec  jmp     short loc_18000620B
0x1800061ee  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800061f5  test    rax, rax
0x1800061f8  jz      short loc_18000620B
0x1800061fa  mov     rdx, [rsp+28h+bstrString]
0x1800061ff  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180006206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620b  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180006210  xor     ecx, ecx; dwReserved
0x180006212  call    cs:__imp_SetErrorInfo
0x180006219  nop     dword ptr [rax+rax+00h]
0x18000621e  mov     rcx, [rsp+28h+pperrinfo]
0x180006223  test    rcx, rcx
0x180006226  jz      short loc_18000623A
0x180006228  mov     rax, [rcx]
0x18000622b  mov     rax, [rax+10h]
0x18000622f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006234  and     [rsp+28h+pperrinfo], 0
0x18000623a  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000623f  test    rcx, rcx
0x180006242  jz      short loc_180006250
0x180006244  call    cs:__imp_SysFreeString
0x18000624b  nop     dword ptr [rax+rax+00h]
0x180006250  add     rsp, 28h
0x180006254  retn
```
