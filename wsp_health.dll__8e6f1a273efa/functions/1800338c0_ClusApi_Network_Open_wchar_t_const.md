# ClusApi::Network::Open(wchar_t const *)

- ea: `0x1800338c0`
- end: `0x180033964`
- name: `?Open@Network@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Network *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f89c`
- `0x180023df4`
- `0x1800338c0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003392d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003392d`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180033907`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180033907`

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
0x1800338c0  push    rbx
0x1800338c2  push    rbp
0x1800338c3  push    rsi
0x1800338c4  push    rdi
0x1800338c5  push    r14
0x1800338c7  sub     rsp, 20h
0x1800338cb  lea     r14, [rcx+18h]
0x1800338cf  xor     edi, edi
0x1800338d1  mov     rax, [r14]
0x1800338d4  mov     rbp, rdx
0x1800338d7  inc     rax
0x1800338da  mov     rsi, rcx
0x1800338dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800338e3  jnz     short loc_180033956
0x1800338e5  mov     rcx, [rcx+20h]
0x1800338e9  mov     rax, [rcx]
0x1800338ec  mov     rax, [rax+188h]
0x1800338f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338f8  mov     rcx, rax; hCluster
0x1800338fb  xor     r9d, r9d; lpdwGrantedAccess
0x1800338fe  mov     r8d, 2000000h; dwDesiredAccess
0x180033904  mov     rdx, rbp; lpszNetworkName
0x180033907  call    cs:__imp_OpenClusterNetworkEx
0x18003390e  nop     dword ptr [rax+rax+00h]
0x180033913  mov     rcx, r14
0x180033916  mov     rbx, rax
0x180033919  call    ?Close@?$AutoHandle@PEAU_HNETWORK@@H$1?CloseClusterNetwork@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORK *,int,&CloseClusterNetwork(_HNETWORK *),0>::Close(void)
0x18003391e  lea     rax, [rbx+1]
0x180033922  mov     [r14], rbx
0x180033925  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003392b  jnz     short loc_18003394A
0x18003392d  call    cs:__imp_GetLastError
0x180033934  nop     dword ptr [rax+rax+00h]
0x180033939  mov     edi, eax
0x18003393b  test    eax, eax
0x18003393d  jle     short loc_180033956
0x18003393f  movzx   edi, ax
0x180033942  or      edi, 80070000h
0x180033948  jmp     short loc_180033956
0x18003394a  lea     rcx, [rsi+30h]
0x18003394e  mov     rdx, rbp
0x180033951  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033956  mov     eax, edi
0x180033958  add     rsp, 20h
0x18003395c  pop     r14
0x18003395e  pop     rdi
0x18003395f  pop     rsi
0x180033960  pop     rbp
0x180033961  pop     rbx
0x180033962  retn
```
