# ClusApi::Group::Open(wchar_t const *)

- ea: `0x180037650`
- end: `0x1800376f4`
- name: `?Open@Group@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Group *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010b90`
- `0x180027bc4`
- `0x180037650`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376bd`
- `CLUSAPI!OpenClusterGroupEx` at `0x180037697`
- `CLUSAPI!OpenClusterGroupEx` at `0x180037697`

## pseudocode

```c
__int64 __fastcall ClusApi::Group::Open(ClusApi::Group *this, const wchar_t *a2)
{
  HGROUP *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HGROUP v7; // rbx
  signed int LastError; // eax

  v2 = (HGROUP *)((char *)this + 32);
  v3 = 0;
  if ( ((*((_QWORD *)this + 4) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 392LL))(*((_QWORD *)this + 5));
    v7 = OpenClusterGroupEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HGROUP *,int,&int CloseClusterGroup(_HGROUP *),0>::Close(v2);
    *v2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::assign((char *)this + 56);
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
0x180037650  push    rbx
0x180037652  push    rbp
0x180037653  push    rsi
0x180037654  push    rdi
0x180037655  push    r14
0x180037657  sub     rsp, 20h
0x18003765b  lea     r14, [rcx+20h]
0x18003765f  xor     edi, edi
0x180037661  mov     rax, [r14]
0x180037664  mov     rbp, rdx
0x180037667  inc     rax
0x18003766a  mov     rsi, rcx
0x18003766d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037673  jnz     short loc_1800376E6
0x180037675  mov     rcx, [rcx+28h]
0x180037679  mov     rax, [rcx]
0x18003767c  mov     rax, [rax+188h]
0x180037683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037688  mov     rcx, rax; hCluster
0x18003768b  xor     r9d, r9d; lpdwGrantedAccess
0x18003768e  mov     r8d, 2000000h; dwDesiredAccess
0x180037694  mov     rdx, rbp; lpszGroupName
0x180037697  call    cs:__imp_OpenClusterGroupEx
0x18003769e  nop     dword ptr [rax+rax+00h]
0x1800376a3  mov     rcx, r14
0x1800376a6  mov     rbx, rax
0x1800376a9  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800376ae  lea     rax, [rbx+1]
0x1800376b2  mov     [r14], rbx
0x1800376b5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800376bb  jnz     short loc_1800376DA
0x1800376bd  call    cs:__imp_GetLastError
0x1800376c4  nop     dword ptr [rax+rax+00h]
0x1800376c9  mov     edi, eax
0x1800376cb  test    eax, eax
0x1800376cd  jle     short loc_1800376E6
0x1800376cf  movzx   edi, ax
0x1800376d2  or      edi, 80070000h
0x1800376d8  jmp     short loc_1800376E6
0x1800376da  lea     rcx, [rsi+38h]
0x1800376de  mov     rdx, rbp
0x1800376e1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800376e6  mov     eax, edi
0x1800376e8  add     rsp, 20h
0x1800376ec  pop     r14
0x1800376ee  pop     rdi
0x1800376ef  pop     rsi
0x1800376f0  pop     rbp
0x1800376f1  pop     rbx
0x1800376f2  retn
```
