# GetInterfaceAttributes2(tagWDS_MAC_ADDRESS *,tagWDS_INTERFACE_ATTRIBUTES * *)

- ea: `0x180023c50`
- end: `0x180023e4c`
- name: `?GetInterfaceAttributes2@@YAKPEAUtagWDS_MAC_ADDRESS@@PEAPEAUtagWDS_INTERFACE_ATTRIBUTES@@@Z`
- size: `508`
- prototype: `unsigned int __fastcall(struct tagWDS_MAC_ADDRESS *Buf2, struct tagWDS_INTERFACE_ATTRIBUTES **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018240`

## callees

- `0x180023c50`
- `0x180025850`
- `0x1800266a0`
- `0x180026d22`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180023cb3`
- `KERNEL32!GetProcAddress` at `0x180023cd1`
- `KERNEL32!GetProcAddress` at `0x180023cb3`
- `KERNEL32!GetProcAddress` at `0x180023cd1`
- `KERNEL32!GetModuleHandleW` at `0x180023c9b`
- `KERNEL32!GetModuleHandleW` at `0x180023c9b`
- `IPHLPAPI!AddIPAddress` at `0x180023c82`

## string_xrefs

- `0x180023d0d`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023d41`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023db4`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall GetInterfaceAttributes2(struct tagWDS_MAC_ADDRESS *Buf2, struct tagWDS_INTERFACE_ATTRIBUTES **a2)
{
  __int64 v2; // rbx
  HMODULE ModuleHandleW; // rax
  HMODULE v6; // rdi
  unsigned int v7; // edi
  const char *v8; // rdx
  const char *v9; // rdx
  unsigned int *v10; // rbp
  unsigned int v11; // esi
  size_t v12; // r14
  struct tagWDS_INTERFACE_ATTRIBUTES *v13; // rax
  unsigned int *v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = 0;
  v2 = 0;
  if ( !_InterlockedExchangeAdd(&dword_180033624, 0) )
  {
    _InterlockedCompareExchange64((volatile signed __int64 *)&g_pfnIphlpapiReference, (signed __int64)AddIPAddress, 0);
    ModuleHandleW = GetModuleHandleW(L"Iphlpapi");
    v6 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      _InterlockedCompareExchange64(&qword_180033630, (signed __int64)GetProcAddress(ModuleHandleW, "GetIfTable2"), 0);
      _InterlockedCompareExchange64(&qword_180033628, (signed __int64)GetProcAddress(v6, "FreeMibTable"), 0);
    }
    _InterlockedExchange(&dword_180033624, 1);
  }
  if ( qword_180033630 && qword_180033628
    || (v7 = 120,
        !ElValidateWin32(0x78u, (const char *)a2, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xAE3u)) )
  {
    v7 = ((__int64 (__fastcall *)(unsigned int **))qword_180033630)(&v15);
    if ( !ElValidateWin32(v7, v8, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xAEBu) )
    {
      v10 = v15;
      v11 = 0;
      if ( *v15 )
      {
        v12 = *((unsigned int *)Buf2 + 4);
        do
        {
          v2 = (__int64)&v10[338 * v11 + 2];
          if ( *(_DWORD *)(v2 + 1056) == (_DWORD)v12
            && !memcmp_0((const void *)(v2 + 1060), Buf2, v12)
            && *(_DWORD *)(v2 + 1156) == 1 )
          {
            break;
          }
          v2 = 0;
          ++v11;
        }
        while ( v11 < *v10 );
        if ( v2 )
          goto LABEL_17;
      }
      v7 = 2;
      if ( !ElValidateWin32(2u, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0xB02u) )
      {
LABEL_17:
        v13 = (struct tagWDS_INTERFACE_ATTRIBUTES *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v13 )
        {
          *(_QWORD *)v13 = *(_QWORD *)(v2 + 1192);
          *((_QWORD *)v13 + 1) = *(_QWORD *)(v2 + 1200);
          *((_QWORD *)v13 + 2) = *(_QWORD *)(v2 + 1208);
          *((_QWORD *)v13 + 3) = *(_QWORD *)(v2 + 1280);
          *a2 = v13;
        }
        else
        {
          v7 = 8;
        }
      }
    }
  }
  if ( v15 )
    ((void (__fastcall *)(unsigned int *))qword_180033628)(v15);
  return v7;
}

```

## disassembly

```asm
0x180023c50  mov     [rsp+arg_0], rbx
0x180023c55  mov     [rsp+arg_8], rbp
0x180023c5a  push    rsi
0x180023c5b  push    rdi
0x180023c5c  push    r12
0x180023c5e  push    r14
0x180023c60  push    r15
0x180023c62  sub     rsp, 20h
0x180023c66  and     [rsp+48h+arg_10], 0
0x180023c6c  xor     ebx, ebx
0x180023c6e  xor     eax, eax
0x180023c70  mov     r12, rdx
0x180023c73  mov     r15, rcx
0x180023c76  lock xadd cs:dword_180033624, eax
0x180023c7e  test    eax, eax
0x180023c80  jnz     short loc_180023CF0
0x180023c82  mov     r8, cs:__imp_AddIPAddress
0x180023c89  xor     eax, eax
0x180023c8b  lock cmpxchg cs:?g_pfnIphlpapiReference@@3PEAXEA, r8; void * g_pfnIphlpapiReference
0x180023c94  lea     rcx, ModuleName; "Iphlpapi"
0x180023c9b  call    cs:__imp_GetModuleHandleW
0x180023ca1  mov     rdi, rax
0x180023ca4  test    rax, rax
0x180023ca7  jz      short loc_180023CE5
0x180023ca9  lea     rdx, ProcName; "GetIfTable2"
0x180023cb0  mov     rcx, rax; hModule
0x180023cb3  call    cs:__imp_GetProcAddress
0x180023cb9  mov     rcx, rax
0x180023cbc  xor     eax, eax
0x180023cbe  lock cmpxchg cs:qword_180033630, rcx
0x180023cc7  lea     rdx, aFreemibtable; "FreeMibTable"
0x180023cce  mov     rcx, rdi; hModule
0x180023cd1  call    cs:__imp_GetProcAddress
0x180023cd7  mov     rcx, rax
0x180023cda  xor     eax, eax
0x180023cdc  lock cmpxchg cs:qword_180033628, rcx
0x180023ce5  mov     eax, 1
0x180023cea  xchg    eax, cs:dword_180033624
0x180023cf0  mov     rax, cs:qword_180033630
0x180023cf7  test    rax, rax
0x180023cfa  jz      short loc_180023D08
0x180023cfc  mov     rax, cs:qword_180033628
0x180023d03  test    rax, rax
0x180023d06  jnz     short loc_180023D29
0x180023d08  mov     edi, 78h ; 'x'
0x180023d0d  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023d14  mov     ecx, edi; unsigned int
0x180023d16  mov     r9d, 0AE3h; unsigned int
0x180023d1c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023d21  test    eax, eax
0x180023d23  jnz     loc_180023E19
0x180023d29  mov     rax, cs:qword_180033630
0x180023d30  lea     rcx, [rsp+48h+arg_10]
0x180023d35  call    cs:__guard_dispatch_icall_fptr
0x180023d3b  mov     r9d, 0AEBh; unsigned int
0x180023d41  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023d48  mov     ecx, eax; unsigned int
0x180023d4a  mov     edi, eax
0x180023d4c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023d51  test    eax, eax
0x180023d53  jnz     loc_180023E19
0x180023d59  mov     rbp, [rsp+48h+arg_10]
0x180023d5e  xor     esi, esi
0x180023d60  cmp     [rbp+0], ebx
0x180023d63  jbe     short loc_180023DAF
0x180023d65  mov     r14d, [r15+10h]
0x180023d69  mov     eax, esi
0x180023d6b  lea     rbx, [rbp+8]
0x180023d6f  imul    rcx, rax, 548h
0x180023d76  add     rbx, rcx
0x180023d79  cmp     [rbx+420h], r14d
0x180023d80  jnz     short loc_180023DA1
0x180023d82  mov     r8, r14; Size
0x180023d85  lea     rcx, [rbx+424h]; Buf1
0x180023d8c  mov     rdx, r15; Buf2
0x180023d8f  call    memcmp_0
0x180023d94  test    eax, eax
0x180023d96  jnz     short loc_180023DA1
0x180023d98  cmp     dword ptr [rbx+484h], 1
0x180023d9f  jz      short loc_180023DAA
0x180023da1  xor     ebx, ebx
0x180023da3  inc     esi
0x180023da5  cmp     esi, [rbp+0]
0x180023da8  jb      short loc_180023D69
0x180023daa  test    rbx, rbx
0x180023dad  jnz     short loc_180023DCC
0x180023daf  mov     edi, 2
0x180023db4  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023dbb  mov     ecx, edi; unsigned int
0x180023dbd  mov     r9d, 0B02h; unsigned int
0x180023dc3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023dc8  test    eax, eax
0x180023dca  jnz     short loc_180023E19
0x180023dcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023dd3  mov     ecx, 20h ; ' '; unsigned __int64
0x180023dd8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023ddd  mov     rcx, rax
0x180023de0  test    rax, rax
0x180023de3  jnz     short loc_180023DEA
0x180023de5  lea     edi, [rax+8]
0x180023de8  jmp     short loc_180023E19
0x180023dea  mov     rax, [rbx+4A8h]
0x180023df1  mov     [rcx], rax
0x180023df4  mov     rax, [rbx+4B0h]
0x180023dfb  mov     [rcx+8], rax
0x180023dff  mov     rax, [rbx+4B8h]
0x180023e06  mov     [rcx+10h], rax
0x180023e0a  mov     rax, [rbx+500h]
0x180023e11  mov     [rcx+18h], rax
0x180023e15  mov     [r12], rcx
0x180023e19  cmp     [rsp+48h+arg_10], 0
0x180023e1f  jz      short loc_180023E33
0x180023e21  mov     rax, cs:qword_180033628
0x180023e28  mov     rcx, [rsp+48h+arg_10]
0x180023e2d  call    cs:__guard_dispatch_icall_fptr
0x180023e33  mov     rbx, [rsp+48h+arg_0]
0x180023e38  mov     eax, edi
0x180023e3a  mov     rbp, [rsp+48h+arg_8]
0x180023e3f  add     rsp, 20h
0x180023e43  pop     r15
0x180023e45  pop     r14
0x180023e47  pop     r12
0x180023e49  pop     rdi
0x180023e4a  pop     rsi
0x180023e4b  retn
```
