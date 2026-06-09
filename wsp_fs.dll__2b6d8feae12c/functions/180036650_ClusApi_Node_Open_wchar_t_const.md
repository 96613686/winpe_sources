# ClusApi::Node::Open(wchar_t const *)

- ea: `0x180036650`
- end: `0x1800366e7`
- name: `?Open@Node@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Node *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001072c`
- `0x180026f4c`
- `0x180036650`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366b7`
- `CLUSAPI!OpenClusterNodeEx` at `0x180036697`
- `CLUSAPI!OpenClusterNodeEx` at `0x180036697`

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
0x180036650  push    rbx
0x180036652  push    rbp
0x180036653  push    rsi
0x180036654  push    rdi
0x180036655  push    r14
0x180036657  sub     rsp, 20h
0x18003665b  lea     r14, [rcx+18h]
0x18003665f  xor     edi, edi
0x180036661  mov     rax, [r14]
0x180036664  mov     rbp, rdx
0x180036667  inc     rax
0x18003666a  mov     rsi, rcx
0x18003666d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036673  jnz     short loc_1800366DA
0x180036675  mov     rcx, [rcx+20h]
0x180036679  mov     rax, [rcx]
0x18003667c  mov     rax, [rax+188h]
0x180036683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036688  mov     rcx, rax; hCluster
0x18003668b  xor     r9d, r9d; lpdwGrantedAccess
0x18003668e  mov     r8d, 2000000h; dwDesiredAccess
0x180036694  mov     rdx, rbp; lpszNodeName
0x180036697  call    cs:__imp_OpenClusterNodeEx
0x18003669d  mov     rcx, r14
0x1800366a0  mov     rbx, rax
0x1800366a3  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x1800366a8  lea     rax, [rbx+1]
0x1800366ac  mov     [r14], rbx
0x1800366af  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800366b5  jnz     short loc_1800366CE
0x1800366b7  call    cs:__imp_GetLastError
0x1800366bd  mov     edi, eax
0x1800366bf  test    eax, eax
0x1800366c1  jle     short loc_1800366DA
0x1800366c3  movzx   edi, ax
0x1800366c6  or      edi, 80070000h
0x1800366cc  jmp     short loc_1800366DA
0x1800366ce  lea     rcx, [rsi+30h]
0x1800366d2  mov     rdx, rbp
0x1800366d5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800366da  mov     eax, edi
0x1800366dc  add     rsp, 20h
0x1800366e0  pop     r14
0x1800366e2  pop     rdi
0x1800366e3  pop     rsi
0x1800366e4  pop     rbp
0x1800366e5  pop     rbx
0x1800366e6  retn
```
