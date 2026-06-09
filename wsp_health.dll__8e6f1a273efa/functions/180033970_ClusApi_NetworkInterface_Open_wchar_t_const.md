# ClusApi::NetworkInterface::Open(wchar_t const *)

- ea: `0x180033970`
- end: `0x180033a14`
- name: `?Open@NetworkInterface@ClusApi@@UEAAJPEB_W@Z`
- size: `164`
- prototype: `int(ClusApi::NetworkInterface *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000f89c`
- `0x180023dbc`
- `0x180033970`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800339dd`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800339b7`
- `CLUSAPI!OpenClusterNetInterfaceEx` at `0x1800339b7`

## pseudocode

```c
__int64 __fastcall ClusApi::NetworkInterface::Open(ClusApi::NetworkInterface *this, const wchar_t *a2)
{
  HNETINTERFACE *v2; // r14
  unsigned int v3; // edi
  struct _HCLUSTER *v6; // rax
  HNETINTERFACE v7; // rbx
  signed int LastError; // eax

  v2 = (HNETINTERFACE *)((char *)this + 8);
  v3 = 0;
  if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 392LL))(*((_QWORD *)this + 2));
    v7 = OpenClusterNetInterfaceEx(v6, a2, 0x2000000u, 0);
    cxl::AutoHandle<_HNETINTERFACE *,int,&int CloseClusterNetInterface(_HNETINTERFACE *),0>::Close(v2);
    *v2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      std::wstring::assign((char *)this + 32, a2);
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
0x180033970  push    rbx
0x180033972  push    rbp
0x180033973  push    rsi
0x180033974  push    rdi
0x180033975  push    r14
0x180033977  sub     rsp, 20h
0x18003397b  lea     r14, [rcx+8]
0x18003397f  xor     edi, edi
0x180033981  mov     rax, [r14]
0x180033984  mov     rbp, rdx
0x180033987  inc     rax
0x18003398a  mov     rsi, rcx
0x18003398d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033993  jnz     short loc_180033A06
0x180033995  mov     rcx, [rcx+10h]
0x180033999  mov     rax, [rcx]
0x18003399c  mov     rax, [rax+188h]
0x1800339a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339a8  mov     rcx, rax; hCluster
0x1800339ab  xor     r9d, r9d; lpdwGrantedAccess
0x1800339ae  mov     r8d, 2000000h; dwDesiredAccess
0x1800339b4  mov     rdx, rbp; lpszInterfaceName
0x1800339b7  call    cs:__imp_OpenClusterNetInterfaceEx
0x1800339be  nop     dword ptr [rax+rax+00h]
0x1800339c3  mov     rcx, r14
0x1800339c6  mov     rbx, rax
0x1800339c9  call    ?Close@?$AutoHandle@PEAU_HNETINTERFACE@@H$1?CloseClusterNetInterface@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNETINTERFACE *,int,&CloseClusterNetInterface(_HNETINTERFACE *),0>::Close(void)
0x1800339ce  lea     rax, [rbx+1]
0x1800339d2  mov     [r14], rbx
0x1800339d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800339db  jnz     short loc_1800339FA
0x1800339dd  call    cs:__imp_GetLastError
0x1800339e4  nop     dword ptr [rax+rax+00h]
0x1800339e9  mov     edi, eax
0x1800339eb  test    eax, eax
0x1800339ed  jle     short loc_180033A06
0x1800339ef  movzx   edi, ax
0x1800339f2  or      edi, 80070000h
0x1800339f8  jmp     short loc_180033A06
0x1800339fa  lea     rcx, [rsi+20h]
0x1800339fe  mov     rdx, rbp
0x180033a01  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180033a06  mov     eax, edi
0x180033a08  add     rsp, 20h
0x180033a0c  pop     r14
0x180033a0e  pop     rdi
0x180033a0f  pop     rsi
0x180033a10  pop     rbp
0x180033a11  pop     rbx
0x180033a12  retn
```
