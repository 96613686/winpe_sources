# ClusApi::ResourceEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002a830`
- end: `0x18002a8d3`
- name: `?OpenEnum@ResourceEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `163`
- prototype: `unsigned int __fastcall(ClusApi::ResourceEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029d08`
- `0x18002a830`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8ba`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002a89a`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002a89a`

## pseudocode

```c
__int64 __fastcall ClusApi::ResourceEnumeratorEx::OpenEnum(ClusApi::ResourceEnumeratorEx *this)
{
  __int64 *v1; // r15
  unsigned int v2; // r14d
  __int64 v3; // rbp
  __int64 v4; // rdi
  int v5; // esi
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rbx

  v1 = (__int64 *)((char *)this + 32);
  v2 = 0;
  if ( ((*((_QWORD *)this + 4) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v3 = *((_QWORD *)this + 11);
    v4 = *((_QWORD *)this + 8);
    v5 = 2 * ((*((_QWORD *)this + 12) - v3) >> 1);
    v6 = 2 * ((*((_QWORD *)this + 9) - v4) >> 1);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 392LL))(*((_QWORD *)this + 6));
    v8 = ClusterResourceOpenEnumEx(v7, v4, v6, v3, v5, 0);
    cxl::AutoHandle<_HRESENUMEX *,unsigned long,&unsigned long ClusterResourceCloseEnumEx(_HRESENUMEX *),0>::Close(v1);
    *v1 = v8;
    if ( ((v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x18002a830  push    rbx
0x18002a832  push    rbp
0x18002a833  push    rsi
0x18002a834  push    rdi
0x18002a835  push    r14
0x18002a837  push    r15
0x18002a839  sub     rsp, 38h
0x18002a83d  lea     r15, [rcx+20h]
0x18002a841  xor     r14d, r14d
0x18002a844  mov     rax, [r15]
0x18002a847  inc     rax
0x18002a84a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a850  jnz     short loc_18002A8C3
0x18002a852  mov     rbp, [rcx+58h]
0x18002a856  mov     rsi, [rcx+60h]
0x18002a85a  mov     rdi, [rcx+40h]
0x18002a85e  sub     rsi, rbp
0x18002a861  mov     rbx, [rcx+48h]
0x18002a865  mov     rcx, [rcx+30h]
0x18002a869  sub     rbx, rdi
0x18002a86c  sar     rsi, 1
0x18002a86f  sar     rbx, 1
0x18002a872  add     esi, esi
0x18002a874  add     ebx, ebx
0x18002a876  mov     rax, [rcx]
0x18002a879  mov     rax, [rax+188h]
0x18002a880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a885  mov     r9, rbp
0x18002a888  mov     [rsp+68h+var_40], r14d
0x18002a88d  mov     r8d, ebx
0x18002a890  mov     [rsp+68h+var_48], esi
0x18002a894  mov     rdx, rdi
0x18002a897  mov     rcx, rax
0x18002a89a  call    cs:__imp_ClusterResourceOpenEnumEx
0x18002a8a0  mov     rcx, r15
0x18002a8a3  mov     rbx, rax
0x18002a8a6  call    ?Close@?$AutoHandle@PEAU_HRESENUMEX@@K$1?ClusterResourceCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUMEX *,ulong,&ClusterResourceCloseEnumEx(_HRESENUMEX *),0>::Close(void)
0x18002a8ab  lea     rax, [rbx+1]
0x18002a8af  mov     [r15], rbx
0x18002a8b2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a8b8  jnz     short loc_18002A8C3
0x18002a8ba  call    cs:__imp_GetLastError
0x18002a8c0  mov     r14d, eax
0x18002a8c3  mov     eax, r14d
0x18002a8c6  add     rsp, 38h
0x18002a8ca  pop     r15
0x18002a8cc  pop     r14
0x18002a8ce  pop     rdi
0x18002a8cf  pop     rsi
0x18002a8d0  pop     rbp
0x18002a8d1  pop     rbx
0x18002a8d2  retn
```
