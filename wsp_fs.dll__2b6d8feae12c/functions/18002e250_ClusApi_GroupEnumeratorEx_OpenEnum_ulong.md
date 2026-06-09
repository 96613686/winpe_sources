# ClusApi::GroupEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002e250`
- end: `0x18002e2f3`
- name: `?OpenEnum@GroupEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `163`
- prototype: `unsigned int __fastcall(ClusApi::GroupEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d988`
- `0x18002e250`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2da`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002e2ba`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002e2ba`

## pseudocode

```c
__int64 __fastcall ClusApi::GroupEnumeratorEx::OpenEnum(ClusApi::GroupEnumeratorEx *this)
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
    v8 = ClusterGroupOpenEnumEx(v7, v4, v6, v3, v5, 0);
    cxl::AutoHandle<_HGROUPENUMEX *,unsigned long,&unsigned long ClusterGroupCloseEnumEx(_HGROUPENUMEX *),0>::Close(v1);
    *v1 = v8;
    if ( ((v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x18002e250  push    rbx
0x18002e252  push    rbp
0x18002e253  push    rsi
0x18002e254  push    rdi
0x18002e255  push    r14
0x18002e257  push    r15
0x18002e259  sub     rsp, 38h
0x18002e25d  lea     r15, [rcx+20h]
0x18002e261  xor     r14d, r14d
0x18002e264  mov     rax, [r15]
0x18002e267  inc     rax
0x18002e26a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e270  jnz     short loc_18002E2E3
0x18002e272  mov     rbp, [rcx+58h]
0x18002e276  mov     rsi, [rcx+60h]
0x18002e27a  mov     rdi, [rcx+40h]
0x18002e27e  sub     rsi, rbp
0x18002e281  mov     rbx, [rcx+48h]
0x18002e285  mov     rcx, [rcx+30h]
0x18002e289  sub     rbx, rdi
0x18002e28c  sar     rsi, 1
0x18002e28f  sar     rbx, 1
0x18002e292  add     esi, esi
0x18002e294  add     ebx, ebx
0x18002e296  mov     rax, [rcx]
0x18002e299  mov     rax, [rax+188h]
0x18002e2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2a5  mov     r9, rbp
0x18002e2a8  mov     [rsp+68h+var_40], r14d
0x18002e2ad  mov     r8d, ebx
0x18002e2b0  mov     [rsp+68h+var_48], esi
0x18002e2b4  mov     rdx, rdi
0x18002e2b7  mov     rcx, rax
0x18002e2ba  call    cs:__imp_ClusterGroupOpenEnumEx
0x18002e2c0  mov     rcx, r15
0x18002e2c3  mov     rbx, rax
0x18002e2c6  call    ?Close@?$AutoHandle@PEAU_HGROUPENUMEX@@K$1?ClusterGroupCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUMEX *,ulong,&ClusterGroupCloseEnumEx(_HGROUPENUMEX *),0>::Close(void)
0x18002e2cb  lea     rax, [rbx+1]
0x18002e2cf  mov     [r15], rbx
0x18002e2d2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e2d8  jnz     short loc_18002E2E3
0x18002e2da  call    cs:__imp_GetLastError
0x18002e2e0  mov     r14d, eax
0x18002e2e3  mov     eax, r14d
0x18002e2e6  add     rsp, 38h
0x18002e2ea  pop     r15
0x18002e2ec  pop     r14
0x18002e2ee  pop     rdi
0x18002e2ef  pop     rsi
0x18002e2f0  pop     rbp
0x18002e2f1  pop     rbx
0x18002e2f2  retn
```
