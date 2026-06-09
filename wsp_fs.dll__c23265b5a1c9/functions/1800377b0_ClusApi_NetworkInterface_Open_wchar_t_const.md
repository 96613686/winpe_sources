# ClusApi::NetworkInterface::Open(wchar_t const *)

- ea: `0x1800377b0`
- end: `0x180037854`
- name: `?Open@NetworkInterface@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::NetworkInterface *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010b90`
- `0x180027bfc`
- `0x1800377b0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003781d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003781d`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800377f7`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800377f7`

## pseudocode

```c
__int64 __fastcall ClusApi::NetworkInterface::Open(ClusApi::NetworkInterface *this, const wchar_t *a2)
{
  HNETINTERFACE *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HNETINTERFACE v7; // rbx
  signed int LastError; // eax

  v2 = (HNETINTERFACE *)((char *)this + 8);
  v3 = 0;
  if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 392LL))(*((_QWORD *)this + 2));
    v7 = OpenClusterNetInterfaceEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HNETINTERFACE *,int,&int CloseClusterNetInterface(_HNETINTERFACE *),0>::Close(v2);
    *v2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::assign((char *)this + 32);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800377b0  push    rbx
0x1800377b2  push    rbp
0x1800377b3  push    rsi
0x1800377b4  push    rdi
0x1800377b5  push    r14
0x1800377b7  sub     rsp, 20h
0x1800377bb  lea     r14, [rcx+8]
0x1800377bf  xor     edi, edi
0x1800377c1  mov     rax, [r14]
0x1800377c4  mov     rbp, rdx
0x1800377c7  inc     rax
0x1800377ca  mov     rsi, rcx
0x1800377cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800377d3  jnz     short loc_180037846
0x1800377d5  mov     rcx, [rcx+10h]
0x1800377d9  mov     rax, [rcx]
0x1800377dc  mov     rax, [rax+188h]
0x1800377e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377e8  mov     rcx, rax; hCluster
0x1800377eb  xor     r9d, r9d; lpdwGrantedAccess
0x1800377ee  mov     r8d, 2000000h; dwDesiredAccess
0x1800377f4  mov     rdx, rbp; lpszInterfaceName
0x1800377f7  call    cs:__imp_OpenClusterNetInterfaceEx
0x1800377fe  nop     dword ptr [rax+rax+00h]
0x180037803  mov     rcx, r14
0x180037806  mov     rbx, rax
0x180037809  call    ?Close@?$AutoHandle@PEAU_HNETINTERFACE@@H$1?CloseClusterNetInterface@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETINTERFACE *,int,&CloseClusterNetInterface(_HNETINTERFACE *),0>::Close(void)
0x18003780e  lea     rax, [rbx+1]
0x180037812  mov     [r14], rbx
0x180037815  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003781b  jnz     short loc_18003783A
0x18003781d  call    cs:__imp_GetLastError
0x180037824  nop     dword ptr [rax+rax+00h]
0x180037829  mov     edi, eax
0x18003782b  test    eax, eax
0x18003782d  jle     short loc_180037846
0x18003782f  movzx   edi, ax
0x180037832  or      edi, 80070000h
0x180037838  jmp     short loc_180037846
0x18003783a  lea     rcx, [rsi+20h]
0x18003783e  mov     rdx, rbp
0x180037841  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180037846  mov     eax, edi
0x180037848  add     rsp, 20h
0x18003784c  pop     r14
0x18003784e  pop     rdi
0x18003784f  pop     rsi
0x180037850  pop     rbp
0x180037851  pop     rbx
0x180037852  retn
```
