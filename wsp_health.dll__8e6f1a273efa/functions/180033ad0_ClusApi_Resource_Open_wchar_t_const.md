# ClusApi::Resource::Open(wchar_t const *)

- ea: `0x180033ad0`
- end: `0x180033b74`
- name: `?Open@Resource@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Resource *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f89c`
- `0x180023e64`
- `0x180033ad0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b3d`
- `CLUSAPI!OpenClusterResourceEx` at `0x180033b17`
- `CLUSAPI!OpenClusterResourceEx` at `0x180033b17`

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
      std::wstring::assign((char *)this + 80, a2);
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
0x180033ad0  push    rbx
0x180033ad2  push    rbp
0x180033ad3  push    rsi
0x180033ad4  push    rdi
0x180033ad5  push    r14
0x180033ad7  sub     rsp, 20h
0x180033adb  lea     r14, [rcx+38h]
0x180033adf  xor     edi, edi
0x180033ae1  mov     rax, [r14]
0x180033ae4  mov     rbp, rdx
0x180033ae7  inc     rax
0x180033aea  mov     rsi, rcx
0x180033aed  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033af3  jnz     short loc_180033B66
0x180033af5  mov     rcx, [rcx+40h]
0x180033af9  mov     rax, [rcx]
0x180033afc  mov     rax, [rax+188h]
0x180033b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b08  mov     rcx, rax; hCluster
0x180033b0b  xor     r9d, r9d; lpdwGrantedAccess
0x180033b0e  mov     r8d, 2000000h; dwDesiredAccess
0x180033b14  mov     rdx, rbp; lpszResourceName
0x180033b17  call    cs:__imp_OpenClusterResourceEx
0x180033b1e  nop     dword ptr [rax+rax+00h]
0x180033b23  mov     rcx, r14
0x180033b26  mov     rbx, rax
0x180033b29  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180033b2e  lea     rax, [rbx+1]
0x180033b32  mov     [r14], rbx
0x180033b35  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033b3b  jnz     short loc_180033B5A
0x180033b3d  call    cs:__imp_GetLastError
0x180033b44  nop     dword ptr [rax+rax+00h]
0x180033b49  mov     edi, eax
0x180033b4b  test    eax, eax
0x180033b4d  jle     short loc_180033B66
0x180033b4f  movzx   edi, ax
0x180033b52  or      edi, 80070000h
0x180033b58  jmp     short loc_180033B66
0x180033b5a  lea     rcx, [rsi+50h]
0x180033b5e  mov     rdx, rbp
0x180033b61  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033b66  mov     eax, edi
0x180033b68  add     rsp, 20h
0x180033b6c  pop     r14
0x180033b6e  pop     rdi
0x180033b6f  pop     rsi
0x180033b70  pop     rbp
0x180033b71  pop     rbx
0x180033b72  retn
```
