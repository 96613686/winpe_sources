# ElTraceErrorInfo(void)

- ea: `0x180014f28`
- end: `0x180014feb`
- name: `?ElTraceErrorInfo@@YAXXZ`
- size: `195`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014ee0`

## callees

- `0x180014f28`
- `0x180015cc0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180014fe0`
- `OLEAUT32!__imp_SysFreeString` at `0x180014fe0`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180014f3f`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180014f3f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014fb3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014fb3`

## string_xrefs

- `0x180014f7a`: `COM Error: '%s'`
- `0x180014f9f`: `COM Error: '%s'`

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
0x180014f28  sub     rsp, 28h
0x180014f2c  and     [rsp+28h+pperrinfo], 0
0x180014f32  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180014f37  and     [rsp+28h+bstrString], 0
0x180014f3d  xor     ecx, ecx; dwReserved
0x180014f3f  call    cs:__imp_GetErrorInfo
0x180014f45  test    eax, eax
0x180014f47  js      short loc_180014FB9
0x180014f49  cmp     eax, 1
0x180014f4c  jz      short loc_180014FB9
0x180014f4e  mov     rcx, [rsp+28h+pperrinfo]
0x180014f53  lea     rdx, [rsp+28h+bstrString]
0x180014f58  mov     rax, [rcx]
0x180014f5b  mov     rax, [rax+28h]
0x180014f5f  call    cs:__guard_dispatch_icall_fptr
0x180014f65  test    eax, eax
0x180014f67  js      short loc_180014FB9
0x180014f69  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014f70  test    rax, rax
0x180014f73  jz      short loc_180014F8E
0x180014f75  mov     r8, [rsp+28h+bstrString]
0x180014f7a  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180014f81  mov     ecx, 80000h
0x180014f86  call    cs:__guard_dispatch_icall_fptr
0x180014f8c  jmp     short loc_180014FAC
0x180014f8e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014f95  test    rax, rax
0x180014f98  jz      short loc_180014FAC
0x180014f9a  mov     rdx, [rsp+28h+bstrString]
0x180014f9f  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180014fa6  call    cs:__guard_dispatch_icall_fptr
0x180014fac  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180014fb1  xor     ecx, ecx; dwReserved
0x180014fb3  call    cs:__imp_SetErrorInfo
0x180014fb9  mov     rcx, [rsp+28h+pperrinfo]
0x180014fbe  test    rcx, rcx
0x180014fc1  jz      short loc_180014FD6
0x180014fc3  mov     rax, [rcx]
0x180014fc6  mov     rax, [rax+10h]
0x180014fca  call    cs:__guard_dispatch_icall_fptr
0x180014fd0  and     [rsp+28h+pperrinfo], 0
0x180014fd6  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180014fdb  test    rcx, rcx
0x180014fde  jz      short loc_180014FE6
0x180014fe0  call    cs:__imp_SysFreeString
0x180014fe6  add     rsp, 28h
0x180014fea  retn
```
