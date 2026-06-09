# ClusApi::Network::Open(wchar_t const *)

- ea: `0x1800327e0`
- end: `0x180032877`
- name: `?Open@Network@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Network *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f3e8`
- `0x1800231dc`
- `0x1800327e0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032847`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180032827`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180032827`

## pseudocode

```c
__int64 __fastcall ClusApi::Network::Open(ClusApi::Network *this, const wchar_t *a2)
{
  HNETWORK *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HNETWORK v7; // rbx
  signed int LastError; // eax

  v2 = (HNETWORK *)((char *)this + 24);
  v3 = 0;
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 392LL))(*((_QWORD *)this + 4));
    v7 = OpenClusterNetworkEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HNETWORK *,int,&int CloseClusterNetwork(_HNETWORK *),0>::Close(v2);
    *v2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::assign((char *)this + 48, a2);
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
0x1800327e0  push    rbx
0x1800327e2  push    rbp
0x1800327e3  push    rsi
0x1800327e4  push    rdi
0x1800327e5  push    r14
0x1800327e7  sub     rsp, 20h
0x1800327eb  lea     r14, [rcx+18h]
0x1800327ef  xor     edi, edi
0x1800327f1  mov     rax, [r14]
0x1800327f4  mov     rbp, rdx
0x1800327f7  inc     rax
0x1800327fa  mov     rsi, rcx
0x1800327fd  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032803  jnz     short loc_18003286A
0x180032805  mov     rcx, [rcx+20h]
0x180032809  mov     rax, [rcx]
0x18003280c  mov     rax, [rax+188h]
0x180032813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032818  mov     rcx, rax; hCluster
0x18003281b  xor     r9d, r9d; lpdwGrantedAccess
0x18003281e  mov     r8d, 2000000h; dwDesiredAccess
0x180032824  mov     rdx, rbp; lpszNetworkName
0x180032827  call    cs:__imp_OpenClusterNetworkEx
0x18003282d  mov     rcx, r14
0x180032830  mov     rbx, rax
0x180032833  call    ?Close@?$AutoHandle@PEAU_HNETWORK@@H$1?CloseClusterNetwork@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORK *,int,&CloseClusterNetwork(_HNETWORK *),0>::Close(void)
0x180032838  lea     rax, [rbx+1]
0x18003283c  mov     [r14], rbx
0x18003283f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032845  jnz     short loc_18003285E
0x180032847  call    cs:__imp_GetLastError
0x18003284d  mov     edi, eax
0x18003284f  test    eax, eax
0x180032851  jle     short loc_18003286A
0x180032853  movzx   edi, ax
0x180032856  or      edi, 80070000h
0x18003285c  jmp     short loc_18003286A
0x18003285e  lea     rcx, [rsi+30h]
0x180032862  mov     rdx, rbp
0x180032865  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18003286a  mov     eax, edi
0x18003286c  add     rsp, 20h
0x180032870  pop     r14
0x180032872  pop     rdi
0x180032873  pop     rsi
0x180032874  pop     rbp
0x180032875  pop     rbx
0x180032876  retn
```
