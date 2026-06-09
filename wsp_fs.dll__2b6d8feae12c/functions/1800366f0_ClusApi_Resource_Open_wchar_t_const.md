# ClusApi::Resource::Open(wchar_t const *)

- ea: `0x1800366f0`
- end: `0x180036787`
- name: `?Open@Resource@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Resource *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001072c`
- `0x180026f7c`
- `0x1800366f0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036757`
- `CLUSAPI!OpenClusterResourceEx` at `0x180036737`
- `CLUSAPI!OpenClusterResourceEx` at `0x180036737`

## pseudocode

```c
__int64 __fastcall ClusApi::Resource::Open(ClusApi::Resource *this, const wchar_t *a2)
{
  HRESOURCE *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HRESOURCE v7; // rbx
  signed int LastError; // eax

  v2 = (HRESOURCE *)((char *)this + 56);
  v3 = 0;
  if ( ((*((_QWORD *)this + 7) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 392LL))(*((_QWORD *)this + 8));
    v7 = OpenClusterResourceEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>::Close(v2);
    *v2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::assign((char *)this + 80);
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
0x1800366f0  push    rbx
0x1800366f2  push    rbp
0x1800366f3  push    rsi
0x1800366f4  push    rdi
0x1800366f5  push    r14
0x1800366f7  sub     rsp, 20h
0x1800366fb  lea     r14, [rcx+38h]
0x1800366ff  xor     edi, edi
0x180036701  mov     rax, [r14]
0x180036704  mov     rbp, rdx
0x180036707  inc     rax
0x18003670a  mov     rsi, rcx
0x18003670d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036713  jnz     short loc_18003677A
0x180036715  mov     rcx, [rcx+40h]
0x180036719  mov     rax, [rcx]
0x18003671c  mov     rax, [rax+188h]
0x180036723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036728  mov     rcx, rax; hCluster
0x18003672b  xor     r9d, r9d; lpdwGrantedAccess
0x18003672e  mov     r8d, 2000000h; dwDesiredAccess
0x180036734  mov     rdx, rbp; lpszResourceName
0x180036737  call    cs:__imp_OpenClusterResourceEx
0x18003673d  mov     rcx, r14
0x180036740  mov     rbx, rax
0x180036743  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180036748  lea     rax, [rbx+1]
0x18003674c  mov     [r14], rbx
0x18003674f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036755  jnz     short loc_18003676E
0x180036757  call    cs:__imp_GetLastError
0x18003675d  mov     edi, eax
0x18003675f  test    eax, eax
0x180036761  jle     short loc_18003677A
0x180036763  movzx   edi, ax
0x180036766  or      edi, 80070000h
0x18003676c  jmp     short loc_18003677A
0x18003676e  lea     rcx, [rsi+50h]
0x180036772  mov     rdx, rbp
0x180036775  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18003677a  mov     eax, edi
0x18003677c  add     rsp, 20h
0x180036780  pop     r14
0x180036782  pop     rdi
0x180036783  pop     rsi
0x180036784  pop     rbp
0x180036785  pop     rbx
0x180036786  retn
```
