# HTTP2ProxyVirtualConnection::RemoveConnectionFromCookieCollection(void)

- ea: `0x180016cd8`
- end: `0x180016df1`
- name: `?RemoveConnectionFromCookieCollection@HTTP2ProxyVirtualConnection@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(HTTP2ProxyVirtualConnection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098d0`

## callees

- `0x18000f290`
- `0x180016cd8`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180016d7f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180016d7f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016d8e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016d8e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016d20`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016d20`
- `RPCRT4!I_RpcFree` at `0x180016d9f`
- `RPCRT4!I_RpcFree` at `0x180016d9f`
- `RPCRT4!I_RpcLogEvent` at `0x180016d53`
- `RPCRT4!I_RpcLogEvent` at `0x180016d53`

## pseudocode

```c
void __fastcall HTTP2ProxyVirtualConnection::RemoveConnectionFromCookieCollection(HTTP2ProxyVirtualConnection *this)
{
  int v2; // ebp
  int v3; // eax
  struct CookieCollection *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ecx
  void *v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  __int64 v13; // rax
  signed __int32 v14[8]; // [rsp+0h] [rbp-58h] BYREF

  if ( *((_DWORD *)this + 102) )
  {
    v2 = 0;
    v3 = (*(__int64 (__fastcall **)(HTTP2ProxyVirtualConnection *))(*(_QWORD *)this + 184LL))(this);
    v4 = g_pOutProxyCookieCollection;
    if ( v3 )
      v4 = (struct CookieCollection *)g_pInProxyCookieCollection;
    RtlAcquireSRWLockExclusive((char *)v4 + 112);
    v5 = *((_QWORD *)this + 52);
    _InterlockedOr(v14, 0);
    LOBYTE(v6) = 45;
    LOBYTE(v7) = 114;
    I_RpcLogEvent(v7, v6, v5, 119, *(_DWORD *)(v5 + 56), 1, 1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 56), 0xFFFFFFFF) == 1 )
    {
      v8 = *((_DWORD *)v4 + 30);
      v9 = (void *)(*((_QWORD *)this + 52) + 32LL);
      if ( v8 )
      {
        if ( v8 == 1 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)v4, v9);
      }
      else
      {
        v10 = (_QWORD *)GenericTable<HTTP2ServerCookie,0,&int DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(
                          v4,
                          v9);
        if ( v10 )
        {
          v11 = *v10;
          if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10) )
            __fastfail(3u);
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          v13 = *(_QWORD *)v4;
          --*((_DWORD *)v4 + 4);
          *((_QWORD *)v4 + 3) = v13;
        }
      }
      v2 = 1;
    }
    RtlReleaseSRWLockExclusive((char *)v4 + 112);
    if ( v2 )
      I_RpcFree(*((void **)this + 52));
  }
}

```

## disassembly

```asm
0x180016cd8  mov     [rsp+arg_8], rbx
0x180016cdd  mov     [rsp+arg_10], rbp
0x180016ce2  push    rsi
0x180016ce3  push    rdi
0x180016ce4  push    r14
0x180016ce6  sub     rsp, 40h
0x180016cea  cmp     dword ptr [rcx+198h], 0
0x180016cf1  mov     rsi, rcx
0x180016cf4  jz      loc_180016DA5
0x180016cfa  mov     rax, [rcx]
0x180016cfd  xor     ebp, ebp
0x180016cff  mov     rax, [rax+0B8h]
0x180016d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0b  mov     rdi, cs:?g_pOutProxyCookieCollection@@3PEAVCookieCollection@@EA; CookieCollection * g_pOutProxyCookieCollection
0x180016d12  test    eax, eax
0x180016d14  cmovnz  rdi, cs:?g_pInProxyCookieCollection@@3PEAVCookieCollection@@EA; CookieCollection * g_pInProxyCookieCollection
0x180016d1c  lea     rcx, [rdi+70h]
0x180016d20  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180016d26  mov     rbx, [rsi+1A0h]
0x180016d2d  lock or [rsp+58h+var_58], ebp
0x180016d31  mov     eax, [rbx+38h]
0x180016d34  lea     r9d, [rbp+77h]
0x180016d38  mov     [rsp+58h+var_28], 1
0x180016d40  mov     r8, rbx
0x180016d43  mov     [rsp+58h+var_30], 1
0x180016d4b  mov     dl, 2Dh ; '-'
0x180016d4d  mov     cl, 72h ; 'r'
0x180016d4f  mov     [rsp+58h+var_38], eax
0x180016d53  call    cs:__imp_I_RpcLogEvent
0x180016d59  or      eax, 0FFFFFFFFh
0x180016d5c  lock xadd [rbx+38h], eax
0x180016d61  cmp     eax, 1
0x180016d64  jnz     short loc_180016D8A
0x180016d66  mov     rdx, [rsi+1A0h]
0x180016d6d  mov     ecx, [rdi+78h]
0x180016d70  add     rdx, 20h ; ' '; Buffer
0x180016d74  test    ecx, ecx
0x180016d76  jz      short loc_180016DB8
0x180016d78  cmp     ecx, eax
0x180016d7a  jnz     short loc_180016D85
0x180016d7c  mov     rcx, rdi; Table
0x180016d7f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180016d85  mov     ebp, 1
0x180016d8a  lea     rcx, [rdi+70h]
0x180016d8e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180016d94  test    ebp, ebp
0x180016d96  jz      short loc_180016DA5
0x180016d98  mov     rcx, [rsi+1A0h]; Object
0x180016d9f  call    cs:__imp_I_RpcFree
0x180016da5  mov     rbx, [rsp+58h+arg_8]
0x180016daa  mov     rbp, [rsp+58h+arg_10]
0x180016daf  add     rsp, 40h
0x180016db3  pop     r14
0x180016db5  pop     rdi
0x180016db6  pop     rsi
0x180016db7  retn
0x180016db8  mov     rcx, rdi
0x180016dbb  call    ?ListFind@?$GenericTable@VHTTP2ServerCookie@@$0A@$1??$DefaultCompareKeys@VHTTP2Cookie@@@@YAHAEBVHTTP2Cookie@@0@Z@@AEAAPEAVHTTP2ServerCookie@@AEAVHTTP2Cookie@@@Z; GenericTable<HTTP2ServerCookie,0,&DefaultCompareKeys<HTTP2Cookie>(HTTP2Cookie const &,HTTP2Cookie const &)>::ListFind(HTTP2Cookie &)
0x180016dc0  test    rax, rax
0x180016dc3  jz      short loc_180016D85
0x180016dc5  mov     rcx, [rax]
0x180016dc8  cmp     [rcx+8], rax
0x180016dcc  jnz     short loc_180016DEA
0x180016dce  mov     rdx, [rax+8]
0x180016dd2  cmp     [rdx], rax
0x180016dd5  jnz     short loc_180016DEA
0x180016dd7  mov     [rdx], rcx
0x180016dda  mov     [rcx+8], rdx
0x180016dde  mov     rax, [rdi]
0x180016de1  dec     dword ptr [rdi+10h]
0x180016de4  mov     [rdi+18h], rax
0x180016de8  jmp     short loc_180016D85
0x180016dea  mov     ecx, 3
0x180016def  int     29h; Win8: RtlFailFast(ecx)
```
