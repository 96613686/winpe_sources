# ClusApi::Group::Open(wchar_t const *)

- ea: `0x180033810`
- end: `0x1800338b4`
- name: `?Open@Group@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::Group *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f89c`
- `0x180023d84`
- `0x180033810`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003387d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003387d`
- `CLUSAPI!OpenClusterGroupEx` at `0x180033857`
- `CLUSAPI!OpenClusterGroupEx` at `0x180033857`

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
0x180033810  push    rbx
0x180033812  push    rbp
0x180033813  push    rsi
0x180033814  push    rdi
0x180033815  push    r14
0x180033817  sub     rsp, 20h
0x18003381b  lea     r14, [rcx+20h]
0x18003381f  xor     edi, edi
0x180033821  mov     rax, [r14]
0x180033824  mov     rbp, rdx
0x180033827  inc     rax
0x18003382a  mov     rsi, rcx
0x18003382d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033833  jnz     short loc_1800338A6
0x180033835  mov     rcx, [rcx+28h]
0x180033839  mov     rax, [rcx]
0x18003383c  mov     rax, [rax+188h]
0x180033843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033848  mov     rcx, rax; hCluster
0x18003384b  xor     r9d, r9d; lpdwGrantedAccess
0x18003384e  mov     r8d, 2000000h; dwDesiredAccess
0x180033854  mov     rdx, rbp; lpszGroupName
0x180033857  call    cs:__imp_OpenClusterGroupEx
0x18003385e  nop     dword ptr [rax+rax+00h]
0x180033863  mov     rcx, r14
0x180033866  mov     rbx, rax
0x180033869  call    ?Close@?$AutoHandle@PEAU_HGROUP@@H$1?CloseClusterGroup@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUP *,int,&CloseClusterGroup(_HGROUP *),0>::Close(void)
0x18003386e  lea     rax, [rbx+1]
0x180033872  mov     [r14], rbx
0x180033875  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003387b  jnz     short loc_18003389A
0x18003387d  call    cs:__imp_GetLastError
0x180033884  nop     dword ptr [rax+rax+00h]
0x180033889  mov     edi, eax
0x18003388b  test    eax, eax
0x18003388d  jle     short loc_1800338A6
0x18003388f  movzx   edi, ax
0x180033892  or      edi, 80070000h
0x180033898  jmp     short loc_1800338A6
0x18003389a  lea     rcx, [rsi+38h]
0x18003389e  mov     rdx, rbp
0x1800338a1  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800338a6  mov     eax, edi
0x1800338a8  add     rsp, 20h
0x1800338ac  pop     r14
0x1800338ae  pop     rdi
0x1800338af  pop     rsi
0x1800338b0  pop     rbp
0x1800338b1  pop     rbx
0x1800338b2  retn
```
