# ClusApi::ResourceEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002e570`
- end: `0x18002e613`
- name: `?OpenEnum@ResourceEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `163`
- prototype: `unsigned int __fastcall(ClusApi::ResourceEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002da48`
- `0x18002e570`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5fa`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002e5da`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002e5da`

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
0x18002e570  push    rbx
0x18002e572  push    rbp
0x18002e573  push    rsi
0x18002e574  push    rdi
0x18002e575  push    r14
0x18002e577  push    r15
0x18002e579  sub     rsp, 38h
0x18002e57d  lea     r15, [rcx+20h]
0x18002e581  xor     r14d, r14d
0x18002e584  mov     rax, [r15]
0x18002e587  inc     rax
0x18002e58a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e590  jnz     short loc_18002E603
0x18002e592  mov     rbp, [rcx+58h]
0x18002e596  mov     rsi, [rcx+60h]
0x18002e59a  mov     rdi, [rcx+40h]
0x18002e59e  sub     rsi, rbp
0x18002e5a1  mov     rbx, [rcx+48h]
0x18002e5a5  mov     rcx, [rcx+30h]
0x18002e5a9  sub     rbx, rdi
0x18002e5ac  sar     rsi, 1
0x18002e5af  sar     rbx, 1
0x18002e5b2  add     esi, esi
0x18002e5b4  add     ebx, ebx
0x18002e5b6  mov     rax, [rcx]
0x18002e5b9  mov     rax, [rax+188h]
0x18002e5c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5c5  mov     r9, rbp
0x18002e5c8  mov     [rsp+68h+var_40], r14d
0x18002e5cd  mov     r8d, ebx
0x18002e5d0  mov     [rsp+68h+var_48], esi
0x18002e5d4  mov     rdx, rdi
0x18002e5d7  mov     rcx, rax
0x18002e5da  call    cs:__imp_ClusterResourceOpenEnumEx
0x18002e5e0  mov     rcx, r15
0x18002e5e3  mov     rbx, rax
0x18002e5e6  call    ?Close@?$AutoHandle@PEAU_HRESENUMEX@@K$1?ClusterResourceCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUMEX *,ulong,&ClusterResourceCloseEnumEx(_HRESENUMEX *),0>::Close(void)
0x18002e5eb  lea     rax, [rbx+1]
0x18002e5ef  mov     [r15], rbx
0x18002e5f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e5f8  jnz     short loc_18002E603
0x18002e5fa  call    cs:__imp_GetLastError
0x18002e600  mov     r14d, eax
0x18002e603  mov     eax, r14d
0x18002e606  add     rsp, 38h
0x18002e60a  pop     r15
0x18002e60c  pop     r14
0x18002e60e  pop     rdi
0x18002e60f  pop     rsi
0x18002e610  pop     rbp
0x18002e611  pop     rbx
0x18002e612  retn
```
