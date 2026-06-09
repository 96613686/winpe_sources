# ElTraceErrorInfo(void)

- ea: `0x18003d074`
- end: `0x18003d149`
- name: `?ElTraceErrorInfo@@YAXXZ`
- size: `213`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d028`

## callees

- `0x18003d074`
- `0x180060e70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003d138`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d138`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18003d08b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18003d08b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003d105`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18003d105`

## string_xrefs

- `0x18003d0cc`: `COM Error: '%s'`
- `0x18003d0f1`: `COM Error: '%s'`

## pseudocode

```c
void ElTraceErrorInfo(void)
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
0x18003d074  sub     rsp, 28h
0x18003d078  and     [rsp+28h+pperrinfo], 0
0x18003d07e  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x18003d083  and     [rsp+28h+bstrString], 0
0x18003d089  xor     ecx, ecx; dwReserved
0x18003d08b  call    cs:__imp_GetErrorInfo
0x18003d092  nop     dword ptr [rax+rax+00h]
0x18003d097  test    eax, eax
0x18003d099  js      short loc_18003D111
0x18003d09b  cmp     eax, 1
0x18003d09e  jz      short loc_18003D111
0x18003d0a0  mov     rcx, [rsp+28h+pperrinfo]
0x18003d0a5  lea     rdx, [rsp+28h+bstrString]
0x18003d0aa  mov     rax, [rcx]
0x18003d0ad  mov     rax, [rax+28h]
0x18003d0b1  call    cs:__guard_dispatch_icall_fptr
0x18003d0b7  test    eax, eax
0x18003d0b9  js      short loc_18003D111
0x18003d0bb  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18003d0c2  test    rax, rax
0x18003d0c5  jz      short loc_18003D0E0
0x18003d0c7  mov     r8, [rsp+28h+bstrString]
0x18003d0cc  lea     rdx, aComErrorS; "COM Error: '%s'"
0x18003d0d3  mov     ecx, 80000h
0x18003d0d8  call    cs:__guard_dispatch_icall_fptr
0x18003d0de  jmp     short loc_18003D0FE
0x18003d0e0  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18003d0e7  test    rax, rax
0x18003d0ea  jz      short loc_18003D0FE
0x18003d0ec  mov     rdx, [rsp+28h+bstrString]
0x18003d0f1  lea     rcx, aComErrorS; "COM Error: '%s'"
0x18003d0f8  call    cs:__guard_dispatch_icall_fptr
0x18003d0fe  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x18003d103  xor     ecx, ecx; dwReserved
0x18003d105  call    cs:__imp_SetErrorInfo
0x18003d10c  nop     dword ptr [rax+rax+00h]
0x18003d111  mov     rcx, [rsp+28h+pperrinfo]
0x18003d116  test    rcx, rcx
0x18003d119  jz      short loc_18003D12E
0x18003d11b  mov     rax, [rcx]
0x18003d11e  mov     rax, [rax+10h]
0x18003d122  call    cs:__guard_dispatch_icall_fptr
0x18003d128  and     [rsp+28h+pperrinfo], 0
0x18003d12e  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18003d133  test    rcx, rcx
0x18003d136  jz      short loc_18003D144
0x18003d138  call    cs:__imp_SysFreeString
0x18003d13f  nop     dword ptr [rax+rax+00h]
0x18003d144  add     rsp, 28h
0x18003d148  retn
```
