# ClusApi::Network::Open(wchar_t const *)

- ea: `0x180037700`
- end: `0x1800377a4`
- name: `?Open@Network@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Network *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010b90`
- `0x180027c34`
- `0x180037700`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003776d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003776d`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180037747`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180037747`

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
      std::wstring::assign((char *)this + 48);
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
0x180037700  push    rbx
0x180037702  push    rbp
0x180037703  push    rsi
0x180037704  push    rdi
0x180037705  push    r14
0x180037707  sub     rsp, 20h
0x18003770b  lea     r14, [rcx+18h]
0x18003770f  xor     edi, edi
0x180037711  mov     rax, [r14]
0x180037714  mov     rbp, rdx
0x180037717  inc     rax
0x18003771a  mov     rsi, rcx
0x18003771d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037723  jnz     short loc_180037796
0x180037725  mov     rcx, [rcx+20h]
0x180037729  mov     rax, [rcx]
0x18003772c  mov     rax, [rax+188h]
0x180037733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037738  mov     rcx, rax; hCluster
0x18003773b  xor     r9d, r9d; lpdwGrantedAccess
0x18003773e  mov     r8d, 2000000h; dwDesiredAccess
0x180037744  mov     rdx, rbp; lpszNetworkName
0x180037747  call    cs:__imp_OpenClusterNetworkEx
0x18003774e  nop     dword ptr [rax+rax+00h]
0x180037753  mov     rcx, r14
0x180037756  mov     rbx, rax
0x180037759  call    ?Close@?$AutoHandle@PEAU_HNETWORK@@H$1?CloseClusterNetwork@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORK *,int,&CloseClusterNetwork(_HNETWORK *),0>::Close(void)
0x18003775e  lea     rax, [rbx+1]
0x180037762  mov     [r14], rbx
0x180037765  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003776b  jnz     short loc_18003778A
0x18003776d  call    cs:__imp_GetLastError
0x180037774  nop     dword ptr [rax+rax+00h]
0x180037779  mov     edi, eax
0x18003777b  test    eax, eax
0x18003777d  jle     short loc_180037796
0x18003777f  movzx   edi, ax
0x180037782  or      edi, 80070000h
0x180037788  jmp     short loc_180037796
0x18003778a  lea     rcx, [rsi+30h]
0x18003778e  mov     rdx, rbp
0x180037791  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180037796  mov     eax, edi
0x180037798  add     rsp, 20h
0x18003779c  pop     r14
0x18003779e  pop     rdi
0x18003779f  pop     rsi
0x1800377a0  pop     rbp
0x1800377a1  pop     rbx
0x1800377a2  retn
```
