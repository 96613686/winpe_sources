# ClusApi::Group::Open(wchar_t const *)

- ea: `0x180032740`
- end: `0x1800327d7`
- name: `?Open@Group@ClusApi@@UEAAJPEB_W@Z`
- size: `151`
- prototype: `int(ClusApi::Group *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f3e8`
- `0x18002317c`
- `0x180032740`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327a7`
- `CLUSAPI!OpenClusterGroupEx` at `0x180032787`
- `CLUSAPI!OpenClusterGroupEx` at `0x180032787`

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
      std::wstring::assign((char *)this + 56, a2);
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
0x180032740  push    rbx
0x180032742  push    rbp
0x180032743  push    rsi
0x180032744  push    rdi
0x180032745  push    r14
0x180032747  sub     rsp, 20h
0x18003274b  lea     r14, [rcx+20h]
0x18003274f  xor     edi, edi
0x180032751  mov     rax, [r14]
0x180032754  mov     rbp, rdx
0x180032757  inc     rax
0x18003275a  mov     rsi, rcx
0x18003275d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032763  jnz     short loc_1800327CA
0x180032765  mov     rcx, [rcx+28h]
0x180032769  mov     rax, [rcx]
0x18003276c  mov     rax, [rax+188h]
0x180032773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032778  mov     rcx, rax; hCluster
0x18003277b  xor     r9d, r9d; lpdwGrantedAccess
0x18003277e  mov     r8d, 2000000h; dwDesiredAccess
0x180032784  mov     rdx, rbp; lpszGroupName
0x180032787  call    cs:__imp_OpenClusterGroupEx
0x18003278d  mov     rcx, r14
0x180032790  mov     rbx, rax
0x180032793  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x180032798  lea     rax, [rbx+1]
0x18003279c  mov     [r14], rbx
0x18003279f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800327a5  jnz     short loc_1800327BE
0x1800327a7  call    cs:__imp_GetLastError
0x1800327ad  mov     edi, eax
0x1800327af  test    eax, eax
0x1800327b1  jle     short loc_1800327CA
0x1800327b3  movzx   edi, ax
0x1800327b6  or      edi, 80070000h
0x1800327bc  jmp     short loc_1800327CA
0x1800327be  lea     rcx, [rsi+38h]
0x1800327c2  mov     rdx, rbp
0x1800327c5  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800327ca  mov     eax, edi
0x1800327cc  add     rsp, 20h
0x1800327d0  pop     r14
0x1800327d2  pop     rdi
0x1800327d3  pop     rsi
0x1800327d4  pop     rbp
0x1800327d5  pop     rbx
0x1800327d6  retn
```
