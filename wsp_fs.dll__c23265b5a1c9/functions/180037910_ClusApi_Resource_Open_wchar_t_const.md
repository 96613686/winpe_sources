# ClusApi::Resource::Open(wchar_t const *)

- ea: `0x180037910`
- end: `0x1800379b4`
- name: `?Open@Resource@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Resource *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010b90`
- `0x180027ca4`
- `0x180037910`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003797d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003797d`
- `CLUSAPI!OpenClusterResourceEx` at `0x180037957`
- `CLUSAPI!OpenClusterResourceEx` at `0x180037957`

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
0x180037910  push    rbx
0x180037912  push    rbp
0x180037913  push    rsi
0x180037914  push    rdi
0x180037915  push    r14
0x180037917  sub     rsp, 20h
0x18003791b  lea     r14, [rcx+38h]
0x18003791f  xor     edi, edi
0x180037921  mov     rax, [r14]
0x180037924  mov     rbp, rdx
0x180037927  inc     rax
0x18003792a  mov     rsi, rcx
0x18003792d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037933  jnz     short loc_1800379A6
0x180037935  mov     rcx, [rcx+40h]
0x180037939  mov     rax, [rcx]
0x18003793c  mov     rax, [rax+188h]
0x180037943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037948  mov     rcx, rax; hCluster
0x18003794b  xor     r9d, r9d; lpdwGrantedAccess
0x18003794e  mov     r8d, 2000000h; dwDesiredAccess
0x180037954  mov     rdx, rbp; lpszResourceName
0x180037957  call    cs:__imp_OpenClusterResourceEx
0x18003795e  nop     dword ptr [rax+rax+00h]
0x180037963  mov     rcx, r14
0x180037966  mov     rbx, rax
0x180037969  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x18003796e  lea     rax, [rbx+1]
0x180037972  mov     [r14], rbx
0x180037975  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003797b  jnz     short loc_18003799A
0x18003797d  call    cs:__imp_GetLastError
0x180037984  nop     dword ptr [rax+rax+00h]
0x180037989  mov     edi, eax
0x18003798b  test    eax, eax
0x18003798d  jle     short loc_1800379A6
0x18003798f  movzx   edi, ax
0x180037992  or      edi, 80070000h
0x180037998  jmp     short loc_1800379A6
0x18003799a  lea     rcx, [rsi+50h]
0x18003799e  mov     rdx, rbp
0x1800379a1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800379a6  mov     eax, edi
0x1800379a8  add     rsp, 20h
0x1800379ac  pop     r14
0x1800379ae  pop     rdi
0x1800379af  pop     rsi
0x1800379b0  pop     rbp
0x1800379b1  pop     rbx
0x1800379b2  retn
```
