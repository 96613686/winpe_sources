# ElTraceErrorInfo(void)

- ea: `0x180025a18`
- end: `0x180025adb`
- name: `?ElTraceErrorInfo@@YAXXZ`
- size: `195`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800259d8`

## callees

- `0x180025a18`
- `0x180026d70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180025ad0`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ad0`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025a2f`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025a2f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180025aa3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180025aa3`

## string_xrefs

- `0x180025a6a`: `COM Error: '%s'`
- `0x180025a8f`: `COM Error: '%s'`

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
0x180025a18  sub     rsp, 28h
0x180025a1c  and     [rsp+28h+pperrinfo], 0
0x180025a22  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180025a27  and     [rsp+28h+bstrString], 0
0x180025a2d  xor     ecx, ecx; dwReserved
0x180025a2f  call    cs:__imp_GetErrorInfo
0x180025a35  test    eax, eax
0x180025a37  js      short loc_180025AA9
0x180025a39  cmp     eax, 1
0x180025a3c  jz      short loc_180025AA9
0x180025a3e  mov     rcx, [rsp+28h+pperrinfo]
0x180025a43  lea     rdx, [rsp+28h+bstrString]
0x180025a48  mov     rax, [rcx]
0x180025a4b  mov     rax, [rax+28h]
0x180025a4f  call    cs:__guard_dispatch_icall_fptr
0x180025a55  test    eax, eax
0x180025a57  js      short loc_180025AA9
0x180025a59  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025a60  test    rax, rax
0x180025a63  jz      short loc_180025A7E
0x180025a65  mov     r8, [rsp+28h+bstrString]
0x180025a6a  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180025a71  mov     ecx, 80000h
0x180025a76  call    cs:__guard_dispatch_icall_fptr
0x180025a7c  jmp     short loc_180025A9C
0x180025a7e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025a85  test    rax, rax
0x180025a88  jz      short loc_180025A9C
0x180025a8a  mov     rdx, [rsp+28h+bstrString]
0x180025a8f  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180025a96  call    cs:__guard_dispatch_icall_fptr
0x180025a9c  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180025aa1  xor     ecx, ecx; dwReserved
0x180025aa3  call    cs:__imp_SetErrorInfo
0x180025aa9  mov     rcx, [rsp+28h+pperrinfo]
0x180025aae  test    rcx, rcx
0x180025ab1  jz      short loc_180025AC6
0x180025ab3  mov     rax, [rcx]
0x180025ab6  mov     rax, [rax+10h]
0x180025aba  call    cs:__guard_dispatch_icall_fptr
0x180025ac0  and     [rsp+28h+pperrinfo], 0
0x180025ac6  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180025acb  test    rcx, rcx
0x180025ace  jz      short loc_180025AD6
0x180025ad0  call    cs:__imp_SysFreeString
0x180025ad6  add     rsp, 28h
0x180025ada  retn
```
