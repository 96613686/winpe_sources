# ElTraceErrorInfo

- ea: `0x18000671c`
- end: `0x1800067ee`
- name: `ElTraceErrorInfo`
- size: `210`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067f4`
- `0x180007b14`
- `0x180009af8`
- `0x18000b048`
- `0x18000c478`
- `0x18000eb74`
- `0x18000fca8`
- `0x180010984`
- `0x1800137c4`
- `0x180013cb0`
- `0x18001470c`
- `0x180015214`
- `0x180015fac`
- `0x180016f20`
- `0x18001811c`
- `0x180018b34`
- `0x18001959c`
- `0x180019ecc`
- `0x18001e168`

## callees

- `0x18000671c`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800067dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067dc`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006733`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180006733`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800067aa`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800067aa`

## string_xrefs

- `0x180006773`: `COM Error: '%s'`
- `0x180006797`: `COM Error: '%s'`

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
0x18000671c  sub     rsp, 28h
0x180006720  and     [rsp+28h+pperrinfo], 0
0x180006726  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x18000672b  and     [rsp+28h+bstrString], 0
0x180006731  xor     ecx, ecx; dwReserved
0x180006733  call    cs:__imp_GetErrorInfo
0x18000673a  nop     dword ptr [rax+rax+00h]
0x18000673f  test    eax, eax
0x180006741  js      short loc_1800067B6
0x180006743  cmp     eax, 1
0x180006746  jz      short loc_1800067B6
0x180006748  mov     rcx, [rsp+28h+pperrinfo]
0x18000674d  lea     rdx, [rsp+28h+bstrString]
0x180006752  mov     rax, [rcx]
0x180006755  mov     rax, [rax+28h]
0x180006759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000675e  test    eax, eax
0x180006760  js      short loc_1800067B6
0x180006762  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006769  test    rax, rax
0x18000676c  jz      short loc_180006786
0x18000676e  mov     r8, [rsp+28h+bstrString]
0x180006773  lea     rdx, aComErrorS; "COM Error: '%s'"
0x18000677a  mov     ecx, 80000h
0x18000677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006784  jmp     short loc_1800067A3
0x180006786  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000678d  test    rax, rax
0x180006790  jz      short loc_1800067A3
0x180006792  mov     rdx, [rsp+28h+bstrString]
0x180006797  lea     rcx, aComErrorS; "COM Error: '%s'"
0x18000679e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a3  mov     rdx, [rsp+28h+pperrinfo]; perrinfo
0x1800067a8  xor     ecx, ecx; dwReserved
0x1800067aa  call    cs:__imp_SetErrorInfo
0x1800067b1  nop     dword ptr [rax+rax+00h]
0x1800067b6  mov     rcx, [rsp+28h+pperrinfo]
0x1800067bb  test    rcx, rcx
0x1800067be  jz      short loc_1800067D2
0x1800067c0  mov     rax, [rcx]
0x1800067c3  mov     rax, [rax+10h]
0x1800067c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067cc  and     [rsp+28h+pperrinfo], 0
0x1800067d2  mov     rcx, [rsp+28h+bstrString]; bstrString
0x1800067d7  test    rcx, rcx
0x1800067da  jz      short loc_1800067E8
0x1800067dc  call    cs:__imp_SysFreeString
0x1800067e3  nop     dword ptr [rax+rax+00h]
0x1800067e8  add     rsp, 28h
0x1800067ec  retn
```
