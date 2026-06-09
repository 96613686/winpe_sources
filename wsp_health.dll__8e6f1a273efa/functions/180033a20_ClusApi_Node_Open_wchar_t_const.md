# ClusApi::Node::Open(wchar_t const *)

- ea: `0x180033a20`
- end: `0x180033ac4`
- name: `?Open@Node@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Node *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f89c`
- `0x180023e2c`
- `0x180033a20`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a8d`
- `CLUSAPI!OpenClusterNodeEx` at `0x180033a67`
- `CLUSAPI!OpenClusterNodeEx` at `0x180033a67`

## pseudocode

```c
__int64 __fastcall ClusApi::Node::Open(ClusApi::Node *this, const wchar_t *a2)
{
  HNODE *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HNODE v7; // rbx
  signed int LastError; // eax

  v2 = (HNODE *)((char *)this + 24);
  v3 = 0;
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 392LL))(*((_QWORD *)this + 4));
    v7 = OpenClusterNodeEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(v2);
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
0x180033a20  push    rbx
0x180033a22  push    rbp
0x180033a23  push    rsi
0x180033a24  push    rdi
0x180033a25  push    r14
0x180033a27  sub     rsp, 20h
0x180033a2b  lea     r14, [rcx+18h]
0x180033a2f  xor     edi, edi
0x180033a31  mov     rax, [r14]
0x180033a34  mov     rbp, rdx
0x180033a37  inc     rax
0x180033a3a  mov     rsi, rcx
0x180033a3d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033a43  jnz     short loc_180033AB6
0x180033a45  mov     rcx, [rcx+20h]
0x180033a49  mov     rax, [rcx]
0x180033a4c  mov     rax, [rax+188h]
0x180033a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a58  mov     rcx, rax; hCluster
0x180033a5b  xor     r9d, r9d; lpdwGrantedAccess
0x180033a5e  mov     r8d, 2000000h; dwDesiredAccess
0x180033a64  mov     rdx, rbp; lpszNodeName
0x180033a67  call    cs:__imp_OpenClusterNodeEx
0x180033a6e  nop     dword ptr [rax+rax+00h]
0x180033a73  mov     rcx, r14
0x180033a76  mov     rbx, rax
0x180033a79  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180033a7e  lea     rax, [rbx+1]
0x180033a82  mov     [r14], rbx
0x180033a85  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033a8b  jnz     short loc_180033AAA
0x180033a8d  call    cs:__imp_GetLastError
0x180033a94  nop     dword ptr [rax+rax+00h]
0x180033a99  mov     edi, eax
0x180033a9b  test    eax, eax
0x180033a9d  jle     short loc_180033AB6
0x180033a9f  movzx   edi, ax
0x180033aa2  or      edi, 80070000h
0x180033aa8  jmp     short loc_180033AB6
0x180033aaa  lea     rcx, [rsi+30h]
0x180033aae  mov     rdx, rbp
0x180033ab1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033ab6  mov     eax, edi
0x180033ab8  add     rsp, 20h
0x180033abc  pop     r14
0x180033abe  pop     rdi
0x180033abf  pop     rsi
0x180033ac0  pop     rbp
0x180033ac1  pop     rbx
0x180033ac2  retn
```
