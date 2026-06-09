# ClusApi::Group::Open(wchar_t const *)

- ea: `0x180036470`
- end: `0x180036507`
- name: `?Open@Group@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Group *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001072c`
- `0x180026ebc`
- `0x180036470`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364d7`
- `CLUSAPI!OpenClusterGroupEx` at `0x1800364b7`
- `CLUSAPI!OpenClusterGroupEx` at `0x1800364b7`

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
0x180036470  push    rbx
0x180036472  push    rbp
0x180036473  push    rsi
0x180036474  push    rdi
0x180036475  push    r14
0x180036477  sub     rsp, 20h
0x18003647b  lea     r14, [rcx+20h]
0x18003647f  xor     edi, edi
0x180036481  mov     rax, [r14]
0x180036484  mov     rbp, rdx
0x180036487  inc     rax
0x18003648a  mov     rsi, rcx
0x18003648d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036493  jnz     short loc_1800364FA
0x180036495  mov     rcx, [rcx+28h]
0x180036499  mov     rax, [rcx]
0x18003649c  mov     rax, [rax+188h]
0x1800364a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364a8  mov     rcx, rax; hCluster
0x1800364ab  xor     r9d, r9d; lpdwGrantedAccess
0x1800364ae  mov     r8d, 2000000h; dwDesiredAccess
0x1800364b4  mov     rdx, rbp; lpszGroupName
0x1800364b7  call    cs:__imp_OpenClusterGroupEx
0x1800364bd  mov     rcx, r14
0x1800364c0  mov     rbx, rax
0x1800364c3  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x1800364c8  lea     rax, [rbx+1]
0x1800364cc  mov     [r14], rbx
0x1800364cf  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800364d5  jnz     short loc_1800364EE
0x1800364d7  call    cs:__imp_GetLastError
0x1800364dd  mov     edi, eax
0x1800364df  test    eax, eax
0x1800364e1  jle     short loc_1800364FA
0x1800364e3  movzx   edi, ax
0x1800364e6  or      edi, 80070000h
0x1800364ec  jmp     short loc_1800364FA
0x1800364ee  lea     rcx, [rsi+38h]
0x1800364f2  mov     rdx, rbp
0x1800364f5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800364fa  mov     eax, edi
0x1800364fc  add     rsp, 20h
0x180036500  pop     r14
0x180036502  pop     rdi
0x180036503  pop     rsi
0x180036504  pop     rbp
0x180036505  pop     rbx
0x180036506  retn
```
