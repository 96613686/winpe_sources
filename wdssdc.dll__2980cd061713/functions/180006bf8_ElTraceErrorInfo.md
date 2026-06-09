# ElTraceErrorInfo

- ea: `0x180006bf8`
- end: `0x180006cd3`
- name: `ElTraceErrorInfo`
- size: `219`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006cdc`
- `0x180007808`
- `0x18000c178`
- `0x18000c634`
- `0x18000c94c`

## callees

- `0x180006bf8`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006cc1`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006c15`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006c15`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006c8c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006c8c`

## string_xrefs

- `0x180006c55`: `COM Error: '%s'`
- `0x180006c79`: `COM Error: '%s'`

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
0x180006bf8  sub     rsp, 28h
0x180006bfc  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180006c01  mov     [rsp+28h+pperrinfo], 0
0x180006c0a  xor     ecx, ecx; dwReserved
0x180006c0c  mov     [rsp+28h+bstrString], 0
0x180006c15  call    cs:__imp_GetErrorInfo
0x180006c1c  nop     dword ptr [rax+rax+00h]
0x180006c21  test    eax, eax
0x180006c23  js      short loc_180006C98
0x180006c25  cmp     eax, 1
0x180006c28  jz      short loc_180006C98
0x180006c2a  mov     rcx, [rsp+28h+pperrinfo]
0x180006c2f  lea     rdx, [rsp+28h+bstrString]
0x180006c34  mov     rax, [rcx]
0x180006c37  mov     rax, [rax+28h]
0x180006c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c40  test    eax, eax
0x180006c42  js      short loc_180006C98
0x180006c44  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006c4b  test    rax, rax
0x180006c4e  jz      short loc_180006C68
0x180006c50  mov     r8, [rsp+28h+bstrString]
0x180006c55  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180006c5c  mov     ecx, 80000h
0x180006c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c66  jmp     short loc_180006C85
0x180006c68  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006c6f  test    rax, rax
0x180006c72  jz      short loc_180006C85
0x180006c74  mov     rdx, [rsp+28h+bstrString]
0x180006c79  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180006c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c85  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180006c8a  xor     ecx, ecx; dwReserved
0x180006c8c  call    cs:__imp_SetErrorInfo
0x180006c93  nop     dword ptr [rax+rax+00h]
0x180006c98  mov     rcx, [rsp+28h+pperrinfo]
0x180006c9d  test    rcx, rcx
0x180006ca0  jz      short loc_180006CB7
0x180006ca2  mov     rax, [rcx]
0x180006ca5  mov     rax, [rax+10h]
0x180006ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cae  mov     [rsp+28h+pperrinfo], 0
0x180006cb7  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180006cbc  test    rcx, rcx
0x180006cbf  jz      short loc_180006CCD
0x180006cc1  call    cs:__imp_SysFreeString
0x180006cc8  nop     dword ptr [rax+rax+00h]
0x180006ccd  add     rsp, 28h
0x180006cd1  retn
```
