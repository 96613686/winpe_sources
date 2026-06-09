# ClusApi::Network::Open(wchar_t const *)

- ea: `0x180036510`
- end: `0x1800365a7`
- name: `?Open@Network@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Network *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001072c`
- `0x180026f1c`
- `0x180036510`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036577`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180036557`
- `CLUSAPI!OpenClusterNetworkEx` at `0x180036557`

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
0x180036510  push    rbx
0x180036512  push    rbp
0x180036513  push    rsi
0x180036514  push    rdi
0x180036515  push    r14
0x180036517  sub     rsp, 20h
0x18003651b  lea     r14, [rcx+18h]
0x18003651f  xor     edi, edi
0x180036521  mov     rax, [r14]
0x180036524  mov     rbp, rdx
0x180036527  inc     rax
0x18003652a  mov     rsi, rcx
0x18003652d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036533  jnz     short loc_18003659A
0x180036535  mov     rcx, [rcx+20h]
0x180036539  mov     rax, [rcx]
0x18003653c  mov     rax, [rax+188h]
0x180036543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036548  mov     rcx, rax; hCluster
0x18003654b  xor     r9d, r9d; lpdwGrantedAccess
0x18003654e  mov     r8d, 2000000h; dwDesiredAccess
0x180036554  mov     rdx, rbp; lpszNetworkName
0x180036557  call    cs:__imp_OpenClusterNetworkEx
0x18003655d  mov     rcx, r14
0x180036560  mov     rbx, rax
0x180036563  call    ?Close@?$AutoHandle@PEAU_HNETWORK@@H$1?CloseClusterNetwork@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETWORK *,int,&CloseClusterNetwork(_HNETWORK *),0>::Close(void)
0x180036568  lea     rax, [rbx+1]
0x18003656c  mov     [r14], rbx
0x18003656f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036575  jnz     short loc_18003658E
0x180036577  call    cs:__imp_GetLastError
0x18003657d  mov     edi, eax
0x18003657f  test    eax, eax
0x180036581  jle     short loc_18003659A
0x180036583  movzx   edi, ax
0x180036586  or      edi, 80070000h
0x18003658c  jmp     short loc_18003659A
0x18003658e  lea     rcx, [rsi+30h]
0x180036592  mov     rdx, rbp
0x180036595  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18003659a  mov     eax, edi
0x18003659c  add     rsp, 20h
0x1800365a0  pop     r14
0x1800365a2  pop     rdi
0x1800365a3  pop     rsi
0x1800365a4  pop     rbp
0x1800365a5  pop     rbx
0x1800365a6  retn
```
