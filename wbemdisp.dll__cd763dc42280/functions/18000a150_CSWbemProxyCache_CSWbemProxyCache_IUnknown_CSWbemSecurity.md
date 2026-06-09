# CSWbemProxyCache::CSWbemProxyCache(IUnknown *,CSWbemSecurity *)

- ea: `0x18000a150`
- end: `0x18000a25c`
- name: `??0CSWbemProxyCache@@QEAA@PEAUIUnknown@@PEAVCSWbemSecurity@@@Z`
- size: `268`
- prototype: `CSWbemProxyCache *__fastcall(CSWbemProxyCache *__hidden this, struct IUnknown *, struct ISWbemSecurity *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a270`

## callees

- `0x18000a150`
- `0x18000a7b0`
- `0x18000b0ac`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a1e3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a200`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a1e3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a200`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a176`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a176`
- `wbemcomn!_ThrowMemoryException_` at `0x18000a180`
- `wbemcomn!_ThrowMemoryException_` at `0x18000a180`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemProxyCache *__fastcall CSWbemProxyCache::CSWbemProxyCache(
        CSWbemProxyCache *this,
        struct IUnknown *a2,
        struct ISWbemSecurity *a3)
{
  CSWbemProxyCache *lpVtbl; // rcx
  struct _COAUTHIDENTITY *CoAuthIdentity; // rax
  struct ISWbemSecurityVtbl *v8; // rax
  const OLECHAR *QueryInterface; // rcx
  struct ISWbemSecurityVtbl *v10; // rax
  const OLECHAR *AddRef; // rcx
  struct ISWbemSecurityVtbl *v12; // rax

  *(_QWORD *)this = &CSWbemProxyCache::`vftable';
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0) )
    _ThrowMemoryException_();
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_WORD *)this + 160) = 1;
  if ( a3 )
  {
    lpVtbl = (CSWbemProxyCache *)a3[15].lpVtbl;
    if ( lpVtbl )
      CoAuthIdentity = CSWbemProxyCache::GetCoAuthIdentity(lpVtbl);
    else
      CoAuthIdentity = 0;
    *((_QWORD *)this + 35) = CoAuthIdentity;
    v8 = a3[15].lpVtbl;
    if ( v8 )
      QueryInterface = (const OLECHAR *)v8[3].QueryInterface;
    else
      QueryInterface = 0;
    *((_QWORD *)this + 36) = SysAllocString(QueryInterface);
    v10 = a3[15].lpVtbl;
    if ( v10 )
      AddRef = (const OLECHAR *)v10[3].AddRef;
    else
      AddRef = 0;
    *((_QWORD *)this + 37) = SysAllocString(AddRef);
    v12 = a3[15].lpVtbl;
    if ( v12 )
      LOBYTE(v12) = BYTE1(v12[3].GetTypeInfo);
    *((_BYTE *)this + 321) = (_BYTE)v12;
  }
  CSWbemProxyCache::InitializeCache(this, a2, a3, 1, 1);
  return this;
}

```

## disassembly

```asm
0x18000a150  mov     [rsp+arg_0], rcx
0x18000a155  push    rbx
0x18000a156  push    rbp
0x18000a157  push    rsi
0x18000a158  push    rdi
0x18000a159  sub     rsp, 38h
0x18000a15d  mov     rbx, r8
0x18000a160  mov     rsi, rdx
0x18000a163  mov     rdi, rcx
0x18000a166  lea     rax, ??_7CSWbemProxyCache@@6B@; const CSWbemProxyCache::`vftable'
0x18000a16d  mov     [rcx], rax
0x18000a170  add     rcx, 10h; lpCriticalSection
0x18000a174  xor     edx, edx; dwSpinCount
0x18000a176  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a17c  test    eax, eax
0x18000a17e  jnz     short loc_18000A187
0x18000a180  call    cs:__imp_?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x18000a186  nop
0x18000a187  mov     dword ptr [rdi+8], 1
0x18000a18e  xor     ebp, ebp
0x18000a190  mov     [rdi+118h], rbp
0x18000a197  mov     [rdi+120h], rbp
0x18000a19e  mov     [rdi+128h], rbp
0x18000a1a5  mov     [rdi+130h], rbp
0x18000a1ac  mov     [rdi+138h], rbp
0x18000a1b3  mov     word ptr [rdi+140h], 1
0x18000a1bc  test    rbx, rbx
0x18000a1bf  jz      short loc_18000A223
0x18000a1c1  mov     rcx, [rbx+78h]; this
0x18000a1c5  test    rcx, rcx
0x18000a1c8  jnz     short loc_18000A246
0x18000a1ca  mov     eax, ebp
0x18000a1cc  mov     [rdi+118h], rax
0x18000a1d3  mov     rax, [rbx+78h]
0x18000a1d7  test    rax, rax
0x18000a1da  jz      short loc_18000A251
0x18000a1dc  mov     rcx, [rax+120h]; psz
0x18000a1e3  call    cs:__imp_SysAllocString
0x18000a1e9  mov     [rdi+120h], rax
0x18000a1f0  mov     rax, [rbx+78h]
0x18000a1f4  test    rax, rax
0x18000a1f7  jz      short loc_18000A256
0x18000a1f9  mov     rcx, [rax+128h]; psz
0x18000a200  call    cs:__imp_SysAllocString
0x18000a206  mov     [rdi+128h], rax
0x18000a20d  mov     rax, [rbx+78h]
0x18000a211  test    rax, rax
0x18000a214  jz      short loc_18000A21D
0x18000a216  movzx   eax, byte ptr [rax+141h]
0x18000a21d  mov     [rdi+141h], al
0x18000a223  mov     [rsp+58h+var_38], 1; bool
0x18000a228  mov     r9b, 1; bool
0x18000a22b  mov     r8, rbx; struct ISWbemSecurity *
0x18000a22e  mov     rdx, rsi; struct IUnknown *
0x18000a231  mov     rcx, rdi; this
0x18000a234  call    ?InitializeCache@CSWbemProxyCache@@AEAAXPEAUIUnknown@@PEAUISWbemSecurity@@_N2@Z; CSWbemProxyCache::InitializeCache(IUnknown *,ISWbemSecurity *,bool,bool)
0x18000a239  nop
0x18000a23a  mov     rax, rdi
0x18000a23d  add     rsp, 38h
0x18000a241  pop     rdi
0x18000a242  pop     rsi
0x18000a243  pop     rbp
0x18000a244  pop     rbx
0x18000a245  retn
0x18000a246  call    ?GetCoAuthIdentity@CSWbemProxyCache@@QEAAPEAU_COAUTHIDENTITY@@XZ; CSWbemProxyCache::GetCoAuthIdentity(void)
0x18000a24b  nop
0x18000a24c  jmp     loc_18000A1CC
0x18000a251  mov     rcx, rbp
0x18000a254  jmp     short loc_18000A1E3
0x18000a256  mov     rcx, rbp
0x18000a259  jmp     short loc_18000A200
```
