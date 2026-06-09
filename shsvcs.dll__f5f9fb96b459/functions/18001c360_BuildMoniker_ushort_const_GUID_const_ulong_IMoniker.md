# _BuildMoniker(ushort const *,_GUID const &,ulong,IMoniker * *)

- ea: `0x18001c360`
- end: `0x18001c44d`
- name: `?_BuildMoniker@@YAJPEBGAEBU_GUID@@KPEAPEAUIMoniker@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *, unsigned int, struct IMoniker **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c4f0`
- `0x18002a494`

## callees

- `0x180005df4`
- `0x18001c360`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `ext-ms-win-com-ole32-l1-1-5!CreateClassMoniker` at `0x18001c39b`
- `ext-ms-win-com-ole32-l1-1-5!CreateClassMoniker` at `0x18001c39b`
- `ext-ms-win-com-ole32-l1-1-0!CreateItemMoniker` at `0x18001c3e4`
- `ext-ms-win-com-ole32-l1-1-0!CreateItemMoniker` at `0x18001c3e4`

## pseudocode

```c
__int64 __fastcall _BuildMoniker(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        unsigned int a3,
        struct IMoniker **a4)
{
  HRESULT v6; // ebx
  LPMONIKER v8; // [rsp+30h] [rbp-78h] BYREF
  LPMONIKER ppmk; // [rsp+38h] [rbp-70h] BYREF
  OLECHAR szItem[32]; // [rsp+40h] [rbp-68h] BYREF

  *a4 = 0;
  ppmk = 0;
  v6 = CreateClassMoniker(a2, &ppmk);
  if ( v6 >= 0 )
  {
    v8 = 0;
    v6 = StringCchPrintfW(szItem, 0x1Eu, L"session:%d", a3);
    if ( v6 >= 0 )
    {
      v6 = CreateItemMoniker(L"!", szItem, &v8);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(LPMONIKER, LPMONIKER, _QWORD, struct IMoniker **))ppmk->lpVtbl->ComposeWith)(
               ppmk,
               v8,
               0,
               a4);
        ((void (__fastcall *)(LPMONIKER))v8->lpVtbl->Release)(v8);
      }
    }
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c360  push    rbx
0x18001c362  push    rsi
0x18001c363  push    rdi
0x18001c364  sub     rsp, 90h
0x18001c36b  mov     rax, cs:__security_cookie
0x18001c372  xor     rax, rsp
0x18001c375  mov     [rsp+0A8h+var_28], rax
0x18001c37d  mov     rcx, rdx; rclsid
0x18001c380  mov     qword ptr [r9], 0
0x18001c387  lea     rdx, [rsp+0A8h+ppmk]; ppmk
0x18001c38c  mov     [rsp+0A8h+ppmk], 0
0x18001c395  mov     rsi, r9
0x18001c398  mov     edi, r8d
0x18001c39b  call    cs:__imp_CreateClassMoniker
0x18001c3a1  mov     ebx, eax
0x18001c3a3  test    eax, eax
0x18001c3a5  js      loc_18001C430
0x18001c3ab  mov     r9d, edi
0x18001c3ae  mov     [rsp+0A8h+var_78], 0
0x18001c3b7  lea     r8, aSessionD; "session:%d"
0x18001c3be  mov     edx, 1Eh; unsigned __int64
0x18001c3c3  lea     rcx, [rsp+0A8h+szItem]; unsigned __int16 *
0x18001c3c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c3cd  mov     ebx, eax
0x18001c3cf  test    eax, eax
0x18001c3d1  js      short loc_18001C41F
0x18001c3d3  lea     r8, [rsp+0A8h+var_78]; ppmk
0x18001c3d8  lea     rdx, [rsp+0A8h+szItem]; lpszItem
0x18001c3dd  lea     rcx, szDelim; "!"
0x18001c3e4  call    cs:__imp_CreateItemMoniker
0x18001c3ea  mov     ebx, eax
0x18001c3ec  test    eax, eax
0x18001c3ee  js      short loc_18001C41F
0x18001c3f0  mov     rcx, [rsp+0A8h+ppmk]
0x18001c3f5  mov     r9, rsi
0x18001c3f8  mov     rdx, [rsp+0A8h+var_78]
0x18001c3fd  xor     r8d, r8d
0x18001c400  mov     rax, [rcx]
0x18001c403  mov     rax, [rax+58h]
0x18001c407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c40c  mov     rcx, [rsp+0A8h+var_78]
0x18001c411  mov     ebx, eax
0x18001c413  mov     rax, [rcx]
0x18001c416  mov     rax, [rax+10h]
0x18001c41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c41f  mov     rcx, [rsp+0A8h+ppmk]
0x18001c424  mov     rax, [rcx]
0x18001c427  mov     rax, [rax+10h]
0x18001c42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c430  mov     eax, ebx
0x18001c432  mov     rcx, [rsp+0A8h+var_28]
0x18001c43a  xor     rcx, rsp; StackCookie
0x18001c43d  call    __security_check_cookie
0x18001c442  add     rsp, 90h
0x18001c449  pop     rdi
0x18001c44a  pop     rsi
0x18001c44b  pop     rbx
0x18001c44c  retn
```
