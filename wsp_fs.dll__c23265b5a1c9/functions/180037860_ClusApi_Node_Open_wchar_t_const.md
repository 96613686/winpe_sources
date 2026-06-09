# ClusApi::Node::Open(wchar_t const *)

- ea: `0x180037860`
- end: `0x180037904`
- name: `?Open@Node@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Node *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010b90`
- `0x180027c6c`
- `0x180037860`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378cd`
- `CLUSAPI!OpenClusterNodeEx` at `0x1800378a7`
- `CLUSAPI!OpenClusterNodeEx` at `0x1800378a7`

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
0x180037860  push    rbx
0x180037862  push    rbp
0x180037863  push    rsi
0x180037864  push    rdi
0x180037865  push    r14
0x180037867  sub     rsp, 20h
0x18003786b  lea     r14, [rcx+18h]
0x18003786f  xor     edi, edi
0x180037871  mov     rax, [r14]
0x180037874  mov     rbp, rdx
0x180037877  inc     rax
0x18003787a  mov     rsi, rcx
0x18003787d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037883  jnz     short loc_1800378F6
0x180037885  mov     rcx, [rcx+20h]
0x180037889  mov     rax, [rcx]
0x18003788c  mov     rax, [rax+188h]
0x180037893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037898  mov     rcx, rax; hCluster
0x18003789b  xor     r9d, r9d; lpdwGrantedAccess
0x18003789e  mov     r8d, 2000000h; dwDesiredAccess
0x1800378a4  mov     rdx, rbp; lpszNodeName
0x1800378a7  call    cs:__imp_OpenClusterNodeEx
0x1800378ae  nop     dword ptr [rax+rax+00h]
0x1800378b3  mov     rcx, r14
0x1800378b6  mov     rbx, rax
0x1800378b9  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x1800378be  lea     rax, [rbx+1]
0x1800378c2  mov     [r14], rbx
0x1800378c5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800378cb  jnz     short loc_1800378EA
0x1800378cd  call    cs:__imp_GetLastError
0x1800378d4  nop     dword ptr [rax+rax+00h]
0x1800378d9  mov     edi, eax
0x1800378db  test    eax, eax
0x1800378dd  jle     short loc_1800378F6
0x1800378df  movzx   edi, ax
0x1800378e2  or      edi, 80070000h
0x1800378e8  jmp     short loc_1800378F6
0x1800378ea  lea     rcx, [rsi+30h]
0x1800378ee  mov     rdx, rbp
0x1800378f1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800378f6  mov     eax, edi
0x1800378f8  add     rsp, 20h
0x1800378fc  pop     r14
0x1800378fe  pop     rdi
0x1800378ff  pop     rsi
0x180037900  pop     rbp
0x180037901  pop     rbx
0x180037902  retn
```
