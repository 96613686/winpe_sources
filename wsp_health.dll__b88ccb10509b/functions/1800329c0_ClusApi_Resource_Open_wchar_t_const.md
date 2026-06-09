# ClusApi::Resource::Open(wchar_t const *)

- ea: `0x1800329c0`
- end: `0x180032a57`
- name: `?Open@Resource@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Resource *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f3e8`
- `0x18002323c`
- `0x1800329c0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a27`
- `CLUSAPI!OpenClusterResourceEx` at `0x180032a07`
- `CLUSAPI!OpenClusterResourceEx` at `0x180032a07`

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
0x1800329c0  push    rbx
0x1800329c2  push    rbp
0x1800329c3  push    rsi
0x1800329c4  push    rdi
0x1800329c5  push    r14
0x1800329c7  sub     rsp, 20h
0x1800329cb  lea     r14, [rcx+38h]
0x1800329cf  xor     edi, edi
0x1800329d1  mov     rax, [r14]
0x1800329d4  mov     rbp, rdx
0x1800329d7  inc     rax
0x1800329da  mov     rsi, rcx
0x1800329dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800329e3  jnz     short loc_180032A4A
0x1800329e5  mov     rcx, [rcx+40h]
0x1800329e9  mov     rax, [rcx]
0x1800329ec  mov     rax, [rax+188h]
0x1800329f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329f8  mov     rcx, rax; hCluster
0x1800329fb  xor     r9d, r9d; lpdwGrantedAccess
0x1800329fe  mov     r8d, 2000000h; dwDesiredAccess
0x180032a04  mov     rdx, rbp; lpszResourceName
0x180032a07  call    cs:__imp_OpenClusterResourceEx
0x180032a0d  mov     rcx, r14
0x180032a10  mov     rbx, rax
0x180032a13  call    ?Close@?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>::Close(void)
0x180032a18  lea     rax, [rbx+1]
0x180032a1c  mov     [r14], rbx
0x180032a1f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032a25  jnz     short loc_180032A3E
0x180032a27  call    cs:__imp_GetLastError
0x180032a2d  mov     edi, eax
0x180032a2f  test    eax, eax
0x180032a31  jle     short loc_180032A4A
0x180032a33  movzx   edi, ax
0x180032a36  or      edi, 80070000h
0x180032a3c  jmp     short loc_180032A4A
0x180032a3e  lea     rcx, [rsi+50h]
0x180032a42  mov     rdx, rbp
0x180032a45  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180032a4a  mov     eax, edi
0x180032a4c  add     rsp, 20h
0x180032a50  pop     r14
0x180032a52  pop     rdi
0x180032a53  pop     rsi
0x180032a54  pop     rbp
0x180032a55  pop     rbx
0x180032a56  retn
```
