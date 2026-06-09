# CWebCrawler::CheckOperationComplete(int)

- ea: `0x18001e91c`
- end: `0x18001eaac`
- name: `?CheckOperationComplete@CWebCrawler@@IEAAXH@Z`
- size: `400`
- prototype: `void __fastcall(CWebCrawler *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020860`
- `0x180020b50`

## callees

- `0x18001dc38`
- `0x18001e91c`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!LoadStringW` at `0x18001ea56`
- `USER32!LoadStringW` at `0x18001ea56`
- `WININET!DeleteUrlCacheGroup` at `0x18001e98d`
- `WININET!DeleteUrlCacheGroup` at `0x18001e98d`

## pseudocode

```c
void __fastcall CWebCrawler::CheckOperationComplete(CWebCrawler *this, int a2)
{
  int v3; // eax
  GROUPID v4; // rcx
  __int64 v5; // rcx
  struct ISubscriptionItem *v6; // rcx
  unsigned int v7; // r8d
  signed int v8; // r8d
  unsigned int v9; // edi
  const unsigned __int16 *v10; // [rsp+30h] [rbp-1C8h] BYREF
  __int128 v11; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-1B0h]
  WCHAR Buffer[200]; // [rsp+50h] [rbp-1A8h] BYREF

  if ( a2 )
  {
    if ( *((_DWORD *)this + 27) == 790526 )
    {
      if ( *((_DWORD *)this + 83) )
      {
        v3 = -2147024809;
        if ( *((int *)this + 74) > 1 )
          v3 = 790401;
        *((_DWORD *)this + 27) = v3;
      }
      else
      {
        *((_DWORD *)this + 27) = *((_DWORD *)this + 11) >= 0;
      }
    }
    v4 = *((_QWORD *)this + 35);
    if ( v4 )
      DeleteUrlCacheGroup(v4, 0, 0);
    v5 = *((_QWORD *)this + 10);
    v10 = L"GroupID";
    v12 = 0;
    v11 = 0;
    LOWORD(v11) = 6;
    *((_QWORD *)&v11 + 1) = *((_QWORD *)this + 34);
    (*(void (__fastcall **)(__int64, __int64, const unsigned __int16 **, __int128 *))(*(_QWORD *)v5 + 56LL))(
      v5,
      1,
      &v10,
      &v11);
    v6 = (struct ISubscriptionItem *)*((_QWORD *)this + 10);
    v7 = (unsigned int)(*((_DWORD *)this + 66) + 511) >> 10;
    *((_DWORD *)this + 26) = v7;
    WriteDWORD(v6, L"ActualSizeKB", v7);
    v8 = *((_DWORD *)this + 82);
    if ( v8 >= 0 )
      WriteDWORD(*((struct ISubscriptionItem **)this + 10), L"ActualProgressMax", v8);
    if ( *((_DWORD *)this + 84) )
    {
      v9 = -2146693122;
      if ( *((_DWORD *)this + 74) != 1 )
        v9 = 0;
      if ( LoadStringW(g_hinstMUI, 0x203Bu, Buffer, 200) )
        (*(void (__fastcall **)(_QWORD, char *, _QWORD, WCHAR *))(**((_QWORD **)this + 9) + 48LL))(
          *((_QWORD *)this + 9),
          (char *)this + 88,
          v9,
          Buffer);
    }
    (*(void (__fastcall **)(CWebCrawler *))(*(_QWORD *)this + 120LL))(this);
  }
}

```

## disassembly

```asm
0x18001e91c  test    edx, edx
0x18001e91e  jz      locret_18001EAAB
0x18001e924  mov     [rsp+arg_8], rbx
0x18001e929  push    rdi
0x18001e92a  sub     rsp, 1F0h
0x18001e931  mov     rax, cs:__security_cookie
0x18001e938  xor     rax, rsp
0x18001e93b  mov     [rsp+1F8h+var_18], rax
0x18001e943  cmp     dword ptr [rcx+6Ch], 0C0FFEh
0x18001e94a  mov     rbx, rcx
0x18001e94d  jnz     short loc_18001E97C
0x18001e94f  cmp     dword ptr [rcx+14Ch], 0
0x18001e956  jz      short loc_18001E971
0x18001e958  cmp     dword ptr [rbx+128h], 1
0x18001e95f  mov     eax, 80070057h
0x18001e964  mov     ecx, 0C0F81h
0x18001e969  cmovg   eax, ecx
0x18001e96c  mov     [rbx+6Ch], eax
0x18001e96f  jmp     short loc_18001E97C
0x18001e971  xor     eax, eax
0x18001e973  cmp     [rcx+2Ch], eax
0x18001e976  setnl   al
0x18001e979  mov     [rcx+6Ch], eax
0x18001e97c  mov     rcx, [rbx+118h]; GroupId
0x18001e983  test    rcx, rcx
0x18001e986  jz      short loc_18001E993
0x18001e988  xor     r8d, r8d; lpReserved
0x18001e98b  xor     edx, edx; dwFlags
0x18001e98d  call    cs:__imp_DeleteUrlCacheGroup
0x18001e993  mov     rcx, [rbx+50h]
0x18001e997  lea     rax, ?c_szPropCrawlGroupID@@3QBGB; "GroupID"
0x18001e99e  mov     [rsp+1F8h+var_1C8], rax
0x18001e9a3  lea     r9, [rsp+1F8h+var_1C0]
0x18001e9a8  xor     eax, eax
0x18001e9aa  lea     r8, [rsp+1F8h+var_1C8]
0x18001e9af  mov     [rsp+1F8h+var_1B0], rax
0x18001e9b4  xorps   xmm0, xmm0
0x18001e9b7  movups  [rsp+1F8h+var_1C0], xmm0
0x18001e9bc  mov     eax, 6
0x18001e9c1  mov     edx, 1
0x18001e9c6  mov     word ptr [rsp+1F8h+var_1C0], ax
0x18001e9cb  mov     rax, [rbx+110h]
0x18001e9d2  mov     qword ptr [rsp+1F8h+var_1C0+8], rax
0x18001e9d7  mov     rax, [rcx]
0x18001e9da  mov     rax, [rax+38h]
0x18001e9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e3  mov     r8d, [rbx+108h]
0x18001e9ea  lea     rdx, ?c_szPropCrawlActualSize@@3QBGB; "ActualSizeKB"
0x18001e9f1  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x18001e9f5  add     r8d, 1FFh
0x18001e9fc  shr     r8d, 0Ah; unsigned int
0x18001ea00  mov     [rbx+68h], r8d
0x18001ea04  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18001ea09  mov     r8d, [rbx+148h]; unsigned int
0x18001ea10  test    r8d, r8d
0x18001ea13  js      short loc_18001EA25
0x18001ea15  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x18001ea19  lea     rdx, ?c_szPropActualProgressMax@@3QBGB; "ActualProgressMax"
0x18001ea20  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18001ea25  cmp     dword ptr [rbx+150h], 0
0x18001ea2c  jz      short loc_18001EA7C
0x18001ea2e  mov     rcx, cs:g_hinstMUI; hInstance
0x18001ea35  lea     r8, [rsp+1F8h+Buffer]; lpBuffer
0x18001ea3a  xor     eax, eax
0x18001ea3c  mov     edi, 800C0FFEh
0x18001ea41  cmp     dword ptr [rbx+128h], 1
0x18001ea48  mov     r9d, 0C8h; cchBufferMax
0x18001ea4e  mov     edx, 203Bh; uID
0x18001ea53  cmovnz  edi, eax
0x18001ea56  call    cs:__imp_LoadStringW
0x18001ea5c  test    eax, eax
0x18001ea5e  jz      short loc_18001EA7C
0x18001ea60  mov     rcx, [rbx+48h]
0x18001ea64  lea     rdx, [rbx+58h]
0x18001ea68  lea     r9, [rsp+1F8h+Buffer]
0x18001ea6d  mov     r8d, edi
0x18001ea70  mov     rax, [rcx]
0x18001ea73  mov     rax, [rax+30h]
0x18001ea77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea7c  mov     rax, [rbx]
0x18001ea7f  mov     rcx, rbx
0x18001ea82  mov     rax, [rax+78h]
0x18001ea86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea8b  mov     rcx, [rsp+1F8h+var_18]
0x18001ea93  xor     rcx, rsp; StackCookie
0x18001ea96  call    __security_check_cookie
0x18001ea9b  mov     rbx, [rsp+1F8h+arg_8]
0x18001eaa3  add     rsp, 1F0h
0x18001eaaa  pop     rdi
0x18001eaab  retn
```
