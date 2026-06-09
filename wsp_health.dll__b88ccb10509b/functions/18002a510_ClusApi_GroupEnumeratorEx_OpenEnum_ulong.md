# ClusApi::GroupEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002a510`
- end: `0x18002a5b3`
- name: `?OpenEnum@GroupEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `163`
- prototype: `unsigned int __fastcall(ClusApi::GroupEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029c48`
- `0x18002a510`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a59a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a59a`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002a57a`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002a57a`

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
0x18002a510  push    rbx
0x18002a512  push    rbp
0x18002a513  push    rsi
0x18002a514  push    rdi
0x18002a515  push    r14
0x18002a517  push    r15
0x18002a519  sub     rsp, 38h
0x18002a51d  lea     r15, [rcx+20h]
0x18002a521  xor     r14d, r14d
0x18002a524  mov     rax, [r15]
0x18002a527  inc     rax
0x18002a52a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a530  jnz     short loc_18002A5A3
0x18002a532  mov     rbp, [rcx+58h]
0x18002a536  mov     rsi, [rcx+60h]
0x18002a53a  mov     rdi, [rcx+40h]
0x18002a53e  sub     rsi, rbp
0x18002a541  mov     rbx, [rcx+48h]
0x18002a545  mov     rcx, [rcx+30h]
0x18002a549  sub     rbx, rdi
0x18002a54c  sar     rsi, 1
0x18002a54f  sar     rbx, 1
0x18002a552  add     esi, esi
0x18002a554  add     ebx, ebx
0x18002a556  mov     rax, [rcx]
0x18002a559  mov     rax, [rax+188h]
0x18002a560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a565  mov     r9, rbp
0x18002a568  mov     [rsp+68h+var_40], r14d
0x18002a56d  mov     r8d, ebx
0x18002a570  mov     [rsp+68h+var_48], esi
0x18002a574  mov     rdx, rdi
0x18002a577  mov     rcx, rax
0x18002a57a  call    cs:__imp_ClusterGroupOpenEnumEx
0x18002a580  mov     rcx, r15
0x18002a583  mov     rbx, rax
0x18002a586  call    ?Close@?$AutoHandle@PEAU_HGROUPENUMEX@@K$1?ClusterGroupCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUMEX *,ulong,&ClusterGroupCloseEnumEx(_HGROUPENUMEX *),0>::Close(void)
0x18002a58b  lea     rax, [rbx+1]
0x18002a58f  mov     [r15], rbx
0x18002a592  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a598  jnz     short loc_18002A5A3
0x18002a59a  call    cs:__imp_GetLastError
0x18002a5a0  mov     r14d, eax
0x18002a5a3  mov     eax, r14d
0x18002a5a6  add     rsp, 38h
0x18002a5aa  pop     r15
0x18002a5ac  pop     r14
0x18002a5ae  pop     rdi
0x18002a5af  pop     rsi
0x18002a5b0  pop     rbp
0x18002a5b1  pop     rbx
0x18002a5b2  retn
```
