# CWebCrawler::OnAuthenticate(HWND__ * *,ushort * *,ushort * *)

- ea: `0x1800209e0`
- end: `0x180020ac0`
- name: `?OnAuthenticate@CWebCrawler@@UEAAJPEAPEAUHWND__@@PEAPEAG1@Z`
- size: `224`
- prototype: `int(CWebCrawler *__hidden this, HWND *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006f2c`
- `0x18001d794`
- `0x18001da30`
- `0x18001faa0`
- `0x1800209e0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180020a3a`
- `KERNEL32!LocalFree` at `0x180020a3a`
- `ole32!CoTaskMemFree` at `0x180020a7d`
- `ole32!CoTaskMemFree` at `0x180020a92`
- `ole32!CoTaskMemFree` at `0x180020a7d`
- `ole32!CoTaskMemFree` at `0x180020a92`
- `OLEAUT32!__imp_SysFreeString` at `0x180020aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180020aa4`

## pseudocode

```c
__int64 __fastcall CWebCrawler::OnAuthenticate(CWebCrawler *this, HWND *a2, unsigned __int16 **a3, LPVOID *a4)
{
  CUrlDownload *v5; // rcx
  const unsigned __int16 *v8; // rdx
  BSTR bstrString; // [rsp+20h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF

  hMem = 0;
  v5 = (CUrlDownload *)*((_QWORD *)this + 29);
  bstrString = 0;
  CUrlDownload::GetRealURL(v5, (unsigned __int16 **)&hMem);
  if ( hMem )
  {
    CWebCrawler::GetHostName((PCWSTR)hMem, &bstrString);
    LocalFree(hMem);
    if ( bstrString )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)this + 26);
      if ( !v8 || !(unsigned int)MyAsciiCmpW(bstrString, v8) )
      {
        ReadOLESTR(*((struct ISubscriptionItem **)this - 4), L"Username", a3);
        if ( *a3 )
        {
          CoTaskMemFree(*a3);
          *a3 = 0;
        }
        if ( *a4 )
        {
          CoTaskMemFree(*a4);
          *a4 = 0;
        }
      }
      SysFreeString(bstrString);
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800209e0  mov     rax, rsp
0x1800209e3  mov     [rax+10h], rsi
0x1800209e7  mov     [rax+18h], rdi
0x1800209eb  push    r14
0x1800209ed  sub     rsp, 30h
0x1800209f1  mov     rsi, rcx
0x1800209f4  mov     qword ptr [rax+8], 0
0x1800209fc  mov     rcx, [rcx+0E8h]; this
0x180020a03  lea     rdx, [rax+8]; unsigned __int16 **
0x180020a07  mov     r14, r9
0x180020a0a  mov     qword ptr [rax-18h], 0
0x180020a12  mov     rdi, r8
0x180020a15  call    ?GetRealURL@CUrlDownload@@QEAAJPEAPEAG@Z; CUrlDownload::GetRealURL(ushort * *)
0x180020a1a  cmp     [rsp+38h+hMem], 0
0x180020a20  jz      loc_180020AAA
0x180020a26  mov     rcx, [rsp+38h+hMem]; pwszSrc
0x180020a2b  lea     rdx, [rsp+38h+bstrString]; unsigned __int16 **
0x180020a30  call    ?GetHostName@CWebCrawler@@KAJPEBGPEAPEAG@Z; CWebCrawler::GetHostName(ushort const *,ushort * *)
0x180020a35  mov     rcx, [rsp+38h+hMem]; hMem
0x180020a3a  call    cs:__imp_LocalFree
0x180020a40  cmp     [rsp+38h+bstrString], 0
0x180020a46  jz      short loc_180020AAA
0x180020a48  mov     rdx, [rsi+0D0h]; unsigned __int16 *
0x180020a4f  test    rdx, rdx
0x180020a52  jz      short loc_180020A62
0x180020a54  mov     rcx, [rsp+38h+bstrString]; unsigned __int16 *
0x180020a59  call    ?MyAsciiCmpW@@YAHPEBG0@Z; MyAsciiCmpW(ushort const *,ushort const *)
0x180020a5e  test    eax, eax
0x180020a60  jnz     short loc_180020A9F
0x180020a62  mov     rcx, [rsi-20h]; struct ISubscriptionItem *
0x180020a66  lea     rdx, ?c_szPropCrawlUsername@@3QBGB; "Username"
0x180020a6d  mov     r8, rdi; unsigned __int16 **
0x180020a70  call    ?ReadOLESTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z; ReadOLESTR(ISubscriptionItem *,ushort const *,ushort * *)
0x180020a75  mov     rcx, [rdi]; pv
0x180020a78  test    rcx, rcx
0x180020a7b  jz      short loc_180020A8A
0x180020a7d  call    cs:__imp_CoTaskMemFree
0x180020a83  mov     qword ptr [rdi], 0
0x180020a8a  mov     rcx, [r14]; pv
0x180020a8d  test    rcx, rcx
0x180020a90  jz      short loc_180020A9F
0x180020a92  call    cs:__imp_CoTaskMemFree
0x180020a98  mov     qword ptr [r14], 0
0x180020a9f  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180020aa4  call    cs:__imp_SysFreeString
0x180020aaa  mov     rsi, [rsp+38h+arg_8]
0x180020aaf  mov     eax, 80004005h
0x180020ab4  mov     rdi, [rsp+38h+arg_10]
0x180020ab9  add     rsp, 30h
0x180020abd  pop     r14
0x180020abf  retn
```
