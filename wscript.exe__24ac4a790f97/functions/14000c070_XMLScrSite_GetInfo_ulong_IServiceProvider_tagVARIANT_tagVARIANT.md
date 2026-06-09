# XMLScrSite::GetInfo(ulong,IServiceProvider *,tagVARIANT *,tagVARIANT *)

- ea: `0x14000c070`
- end: `0x14000c122`
- name: `?GetInfo@XMLScrSite@@UEAAJKPEAUIServiceProvider@@PEAUtagVARIANT@@1@Z`
- size: `178`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned int, struct IServiceProvider *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14000c070`
- `0x140014404`
- `0x140018010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x14000c101`
- `USER32!GetActiveWindow` at `0x14000c101`

## pseudocode

```c
__int64 __fastcall XMLScrSite::GetInfo(
        XMLScrSite *this,
        int a2,
        struct IServiceProvider *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5)
{
  int v6; // edx
  const unsigned __int16 *bstrVal; // rbx
  LONGLONG v9; // rcx

  v6 = a2 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
      return 2147500033LL;
    if ( !a4 )
      return 2147500037LL;
    if ( a4->vt != 8 )
      return 2147500037LL;
    bstrVal = a4->bstrVal;
    if ( (unsigned int)CompareStrsCaseInsensitive(bstrVal, L"WScript", 0xFFFFFFFFFFFFFFFFuLL) )
    {
      if ( (unsigned int)CompareStrsCaseInsensitive(bstrVal, L"WSH", 0xFFFFFFFFFFFFFFFFuLL) )
        return 2147500037LL;
    }
    a5->vt = 9;
    v9 = *(_QWORD *)(*((_QWORD *)this + 4) + 624LL);
    a5->llVal = v9;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v9 + 8LL))(v9);
  }
  else
  {
    a5->llVal = (LONGLONG)GetActiveWindow();
    a5->vt = 0x4000;
  }
  return 0;
}

```

## disassembly

```asm
0x14000c070  mov     [rsp+arg_0], rbx
0x14000c075  push    rdi
0x14000c076  sub     rsp, 20h
0x14000c07a  mov     rdi, rcx
0x14000c07d  sub     edx, 1
0x14000c080  jz      short loc_14000C101
0x14000c082  cmp     edx, 1
0x14000c085  jz      short loc_14000C091
0x14000c087  mov     eax, 80004001h
0x14000c08c  jmp     loc_14000C117
0x14000c091  test    r9, r9
0x14000c094  jz      short loc_14000C0FA
0x14000c096  mov     eax, 8
0x14000c09b  cmp     ax, [r9]
0x14000c09f  jnz     short loc_14000C0FA
0x14000c0a1  mov     rbx, [r9+8]
0x14000c0a5  lea     rdx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x14000c0ac  mov     rcx, rbx; unsigned __int16 *
0x14000c0af  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x14000c0b3  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x14000c0b8  test    eax, eax
0x14000c0ba  jz      short loc_14000C0D3
0x14000c0bc  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x14000c0c0  lea     rdx, ?GWSZ_WSH@@3QBGB; "WSH"
0x14000c0c7  mov     rcx, rbx; unsigned __int16 *
0x14000c0ca  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x14000c0cf  test    eax, eax
0x14000c0d1  jnz     short loc_14000C0FA
0x14000c0d3  mov     rdx, [rsp+28h+arg_20]
0x14000c0d8  mov     word ptr [rdx], 9
0x14000c0dd  mov     rax, [rdi+20h]
0x14000c0e1  mov     rcx, [rax+270h]
0x14000c0e8  mov     [rdx+8], rcx
0x14000c0ec  mov     rax, [rcx]
0x14000c0ef  mov     rax, [rax+8]
0x14000c0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0f8  jmp     short loc_14000C115
0x14000c0fa  mov     eax, 80004005h
0x14000c0ff  jmp     short loc_14000C117
0x14000c101  call    cs:__imp_GetActiveWindow
0x14000c107  mov     rcx, [rsp+28h+arg_20]
0x14000c10c  mov     [rcx+8], rax
0x14000c110  mov     word ptr [rcx], 4000h
0x14000c115  xor     eax, eax
0x14000c117  mov     rbx, [rsp+28h+arg_0]
0x14000c11c  add     rsp, 20h
0x14000c120  pop     rdi
0x14000c121  retn
```
