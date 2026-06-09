# ClusApi::Node::Open(wchar_t const *)

- ea: `0x180032920`
- end: `0x1800329b7`
- name: `?Open@Node@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Node *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f3e8`
- `0x18002320c`
- `0x180032920`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032987`
- `CLUSAPI!OpenClusterNodeEx` at `0x180032967`
- `CLUSAPI!OpenClusterNodeEx` at `0x180032967`

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
0x180032920  push    rbx
0x180032922  push    rbp
0x180032923  push    rsi
0x180032924  push    rdi
0x180032925  push    r14
0x180032927  sub     rsp, 20h
0x18003292b  lea     r14, [rcx+18h]
0x18003292f  xor     edi, edi
0x180032931  mov     rax, [r14]
0x180032934  mov     rbp, rdx
0x180032937  inc     rax
0x18003293a  mov     rsi, rcx
0x18003293d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032943  jnz     short loc_1800329AA
0x180032945  mov     rcx, [rcx+20h]
0x180032949  mov     rax, [rcx]
0x18003294c  mov     rax, [rax+188h]
0x180032953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032958  mov     rcx, rax; hCluster
0x18003295b  xor     r9d, r9d; lpdwGrantedAccess
0x18003295e  mov     r8d, 2000000h; dwDesiredAccess
0x180032964  mov     rdx, rbp; lpszNodeName
0x180032967  call    cs:__imp_OpenClusterNodeEx
0x18003296d  mov     rcx, r14
0x180032970  mov     rbx, rax
0x180032973  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x180032978  lea     rax, [rbx+1]
0x18003297c  mov     [r14], rbx
0x18003297f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032985  jnz     short loc_18003299E
0x180032987  call    cs:__imp_GetLastError
0x18003298d  mov     edi, eax
0x18003298f  test    eax, eax
0x180032991  jle     short loc_1800329AA
0x180032993  movzx   edi, ax
0x180032996  or      edi, 80070000h
0x18003299c  jmp     short loc_1800329AA
0x18003299e  lea     rcx, [rsi+30h]
0x1800329a2  mov     rdx, rbp
0x1800329a5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800329aa  mov     eax, edi
0x1800329ac  add     rsp, 20h
0x1800329b0  pop     r14
0x1800329b2  pop     rdi
0x1800329b3  pop     rsi
0x1800329b4  pop     rbp
0x1800329b5  pop     rbx
0x1800329b6  retn
```
