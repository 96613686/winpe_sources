# ElTraceErrorInfo

- ea: `0x180006ea4`
- end: `0x180006f76`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006f7c`
- `0x180008878`
- `0x18000ff48`
- `0x180011c88`
- `0x180017374`
- `0x180018348`
- `0x18001afd0`
- `0x18001f080`
- `0x180023c1c`
- `0x180026f50`
- `0x1800270a0`
- `0x1800283e4`
- `0x180028f4c`
- `0x180029938`
- `0x180029f84`
- `0x18002a950`
- `0x18002e284`

## callees

- `0x180006ea4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006f64`
- `OLEAUT32!__imp_SysFreeString` at `0x180006f64`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006ebb`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006ebb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006f32`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006f32`

## string_xrefs

- `0x180006efb`: `COM Error: '%s'`
- `0x180006f1f`: `COM Error: '%s'`

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
0x180006ea4  sub     rsp, 28h
0x180006ea8  and     [rsp+28h+pperrinfo], 0
0x180006eae  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180006eb3  and     [rsp+28h+bstrString], 0
0x180006eb9  xor     ecx, ecx; dwReserved
0x180006ebb  call    cs:__imp_GetErrorInfo
0x180006ec2  nop     dword ptr [rax+rax+00h]
0x180006ec7  test    eax, eax
0x180006ec9  js      short loc_180006F3E
0x180006ecb  cmp     eax, 1
0x180006ece  jz      short loc_180006F3E
0x180006ed0  mov     rcx, [rsp+28h+pperrinfo]
0x180006ed5  lea     rdx, [rsp+28h+bstrString]
0x180006eda  mov     rax, [rcx]
0x180006edd  mov     rax, [rax+28h]
0x180006ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee6  test    eax, eax
0x180006ee8  js      short loc_180006F3E
0x180006eea  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006ef1  test    rax, rax
0x180006ef4  jz      short loc_180006F0E
0x180006ef6  mov     r8, [rsp+28h+bstrString]
0x180006efb  lea     rdx, aComErrorS; "COM Error: '%s'"
0x180006f02  mov     ecx, 80000h
0x180006f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f0c  jmp     short loc_180006F2B
0x180006f0e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180006f15  test    rax, rax
0x180006f18  jz      short loc_180006F2B
0x180006f1a  mov     rdx, [rsp+28h+bstrString]
0x180006f1f  lea     rcx, aComErrorS; "COM Error: '%s'"
0x180006f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2b  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x180006f30  xor     ecx, ecx; dwReserved
0x180006f32  call    cs:__imp_SetErrorInfo
0x180006f39  nop     dword ptr [rax+rax+00h]
0x180006f3e  mov     rcx, [rsp+28h+pperrinfo]
0x180006f43  test    rcx, rcx
0x180006f46  jz      short loc_180006F5A
0x180006f48  mov     rax, [rcx]
0x180006f4b  mov     rax, [rax+10h]
0x180006f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f54  and     [rsp+28h+pperrinfo], 0
0x180006f5a  mov     rcx, [rsp+28h+bstrString]; bstrString
0x180006f5f  test    rcx, rcx
0x180006f62  jz      short loc_180006F70
0x180006f64  call    cs:__imp_SysFreeString
0x180006f6b  nop     dword ptr [rax+rax+00h]
0x180006f70  add     rsp, 28h
0x180006f74  retn
```
