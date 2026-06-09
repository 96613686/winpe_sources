# ClusApi::ResourceEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002f4a0`
- end: `0x18002f550`
- name: `?OpenEnum@ResourceEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `176`
- prototype: `unsigned int __fastcall(ClusApi::ResourceEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e8bc`
- `0x18002f4a0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f530`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002f50a`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002f50a`

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
0x18002f4a0  push    rbx
0x18002f4a2  push    rbp
0x18002f4a3  push    rsi
0x18002f4a4  push    rdi
0x18002f4a5  push    r14
0x18002f4a7  push    r15
0x18002f4a9  sub     rsp, 38h
0x18002f4ad  lea     r15, [rcx+20h]
0x18002f4b1  xor     r14d, r14d
0x18002f4b4  mov     rax, [r15]
0x18002f4b7  inc     rax
0x18002f4ba  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f4c0  jnz     short loc_18002F53F
0x18002f4c2  mov     rbp, [rcx+58h]
0x18002f4c6  mov     rsi, [rcx+60h]
0x18002f4ca  mov     rdi, [rcx+40h]
0x18002f4ce  sub     rsi, rbp
0x18002f4d1  mov     rbx, [rcx+48h]
0x18002f4d5  mov     rcx, [rcx+30h]
0x18002f4d9  sub     rbx, rdi
0x18002f4dc  sar     rsi, 1
0x18002f4df  sar     rbx, 1
0x18002f4e2  add     esi, esi
0x18002f4e4  add     ebx, ebx
0x18002f4e6  mov     rax, [rcx]
0x18002f4e9  mov     rax, [rax+188h]
0x18002f4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4f5  mov     r9, rbp
0x18002f4f8  mov     [rsp+68h+var_40], r14d
0x18002f4fd  mov     r8d, ebx
0x18002f500  mov     [rsp+68h+var_48], esi
0x18002f504  mov     rdx, rdi
0x18002f507  mov     rcx, rax
0x18002f50a  call    cs:__imp_ClusterResourceOpenEnumEx
0x18002f511  nop     dword ptr [rax+rax+00h]
0x18002f516  mov     rcx, r15
0x18002f519  mov     rbx, rax
0x18002f51c  call    ?Close@?$AutoHandle@PEAU_HRESENUMEX@@K$1?ClusterResourceCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUMEX *,ulong,&ClusterResourceCloseEnumEx(_HRESENUMEX *),0>::Close(void)
0x18002f521  lea     rax, [rbx+1]
0x18002f525  mov     [r15], rbx
0x18002f528  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f52e  jnz     short loc_18002F53F
0x18002f530  call    cs:__imp_GetLastError
0x18002f537  nop     dword ptr [rax+rax+00h]
0x18002f53c  mov     r14d, eax
0x18002f53f  mov     eax, r14d
0x18002f542  add     rsp, 38h
0x18002f546  pop     r15
0x18002f548  pop     r14
0x18002f54a  pop     rdi
0x18002f54b  pop     rsi
0x18002f54c  pop     rbp
0x18002f54d  pop     rbx
0x18002f54e  retn
```
