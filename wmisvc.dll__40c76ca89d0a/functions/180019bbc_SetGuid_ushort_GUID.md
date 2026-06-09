# SetGuid(ushort *,_GUID &)

- ea: `0x180019bbc`
- end: `0x180019c4a`
- name: `?SetGuid@@YAHPEAGAEAU_GUID@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ae4c`

## callees

- `0x1800021f0`
- `0x180003b08`
- `0x1800079f0`
- `0x180019bbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180019bf0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180019c1f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180019bf0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180019c1f`

## pseudocode

```c
__int64 __fastcall SetGuid(LPCOLESTR lpsz, LPCLSID pclsid)
{
  unsigned int v4; // edi
  LPCOLESTR lpsza; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  CAutoWChar::CAutoWChar((CAutoWChar *)&lpsza, 262);
  if ( lpsza
    && (CLSIDFromString(lpsz, pclsid) >= 0
     || (int)StringCchPrintfW((unsigned __int16 *)lpsza, 0x106u, L"{%s}", lpsz) >= 0
     && CLSIDFromString(lpsza, pclsid) >= 0) )
  {
    v4 = 1;
  }
  CAutoWChar::~CAutoWChar((void **)&lpsza);
  return v4;
}

```

## disassembly

```asm
0x180019bbc  mov     [rsp+arg_0], rbp
0x180019bc1  mov     [rsp+arg_8], rsi
0x180019bc6  push    rdi
0x180019bc7  sub     rsp, 20h
0x180019bcb  mov     rsi, rdx
0x180019bce  mov     rbp, rcx
0x180019bd1  xor     edi, edi
0x180019bd3  mov     edx, 106h; int
0x180019bd8  lea     rcx, [rsp+28h+lpsz]; this
0x180019bdd  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x180019be2  nop
0x180019be3  cmp     [rsp+28h+lpsz], rdi
0x180019be8  jz      short loc_180019C2E
0x180019bea  mov     rdx, rsi; pclsid
0x180019bed  mov     rcx, rbp; lpsz
0x180019bf0  call    cs:__imp_CLSIDFromString
0x180019bf6  test    eax, eax
0x180019bf8  jns     short loc_180019C29
0x180019bfa  mov     r9, rbp
0x180019bfd  lea     r8, aS; "{%s}"
0x180019c04  mov     edx, 106h; unsigned __int64
0x180019c09  mov     rcx, [rsp+28h+lpsz]; unsigned __int16 *
0x180019c0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019c13  test    eax, eax
0x180019c15  js      short loc_180019C2E
0x180019c17  mov     rdx, rsi; pclsid
0x180019c1a  mov     rcx, [rsp+28h+lpsz]; lpsz
0x180019c1f  call    cs:__imp_CLSIDFromString
0x180019c25  test    eax, eax
0x180019c27  js      short loc_180019C2E
0x180019c29  mov     edi, 1
0x180019c2e  lea     rcx, [rsp+28h+lpsz]; this
0x180019c33  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180019c38  mov     eax, edi
0x180019c3a  mov     rbp, [rsp+28h+arg_0]
0x180019c3f  mov     rsi, [rsp+28h+arg_8]
0x180019c44  add     rsp, 20h
0x180019c48  pop     rdi
0x180019c49  retn
```
