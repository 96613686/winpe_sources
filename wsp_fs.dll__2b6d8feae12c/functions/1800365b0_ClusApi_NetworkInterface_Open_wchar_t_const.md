# ClusApi::NetworkInterface::Open(wchar_t const *)

- ea: `0x1800365b0`
- end: `0x180036647`
- name: `?Open@NetworkInterface@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::NetworkInterface *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001072c`
- `0x180026eec`
- `0x1800365b0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036617`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800365f7`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800365f7`

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
0x1800365b0  push    rbx
0x1800365b2  push    rbp
0x1800365b3  push    rsi
0x1800365b4  push    rdi
0x1800365b5  push    r14
0x1800365b7  sub     rsp, 20h
0x1800365bb  lea     r14, [rcx+8]
0x1800365bf  xor     edi, edi
0x1800365c1  mov     rax, [r14]
0x1800365c4  mov     rbp, rdx
0x1800365c7  inc     rax
0x1800365ca  mov     rsi, rcx
0x1800365cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800365d3  jnz     short loc_18003663A
0x1800365d5  mov     rcx, [rcx+10h]
0x1800365d9  mov     rax, [rcx]
0x1800365dc  mov     rax, [rax+188h]
0x1800365e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365e8  mov     rcx, rax; hCluster
0x1800365eb  xor     r9d, r9d; lpdwGrantedAccess
0x1800365ee  mov     r8d, 2000000h; dwDesiredAccess
0x1800365f4  mov     rdx, rbp; lpszInterfaceName
0x1800365f7  call    cs:__imp_OpenClusterNetInterfaceEx
0x1800365fd  mov     rcx, r14
0x180036600  mov     rbx, rax
0x180036603  call    ?Close@?$AutoHandle@PEAU_HNETINTERFACE@@H$1?CloseClusterNetInterface@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETINTERFACE *,int,&CloseClusterNetInterface(_HNETINTERFACE *),0>::Close(void)
0x180036608  lea     rax, [rbx+1]
0x18003660c  mov     [r14], rbx
0x18003660f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036615  jnz     short loc_18003662E
0x180036617  call    cs:__imp_GetLastError
0x18003661d  mov     edi, eax
0x18003661f  test    eax, eax
0x180036621  jle     short loc_18003663A
0x180036623  movzx   edi, ax
0x180036626  or      edi, 80070000h
0x18003662c  jmp     short loc_18003663A
0x18003662e  lea     rcx, [rsi+20h]
0x180036632  mov     rdx, rbp
0x180036635  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18003663a  mov     eax, edi
0x18003663c  add     rsp, 20h
0x180036640  pop     r14
0x180036642  pop     rdi
0x180036643  pop     rsi
0x180036644  pop     rbp
0x180036645  pop     rbx
0x180036646  retn
```
