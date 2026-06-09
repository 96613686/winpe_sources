# ClusApi::GroupEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002b300`
- end: `0x18002b3b0`
- name: `?OpenEnum@GroupEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `176`
- prototype: `unsigned int __fastcall(ClusApi::GroupEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002a99c`
- `0x18002b300`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b390`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002b36a`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002b36a`

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
0x18002b300  push    rbx
0x18002b302  push    rbp
0x18002b303  push    rsi
0x18002b304  push    rdi
0x18002b305  push    r14
0x18002b307  push    r15
0x18002b309  sub     rsp, 38h
0x18002b30d  lea     r15, [rcx+20h]
0x18002b311  xor     r14d, r14d
0x18002b314  mov     rax, [r15]
0x18002b317  inc     rax
0x18002b31a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b320  jnz     short loc_18002B39F
0x18002b322  mov     rbp, [rcx+58h]
0x18002b326  mov     rsi, [rcx+60h]
0x18002b32a  mov     rdi, [rcx+40h]
0x18002b32e  sub     rsi, rbp
0x18002b331  mov     rbx, [rcx+48h]
0x18002b335  mov     rcx, [rcx+30h]
0x18002b339  sub     rbx, rdi
0x18002b33c  sar     rsi, 1
0x18002b33f  sar     rbx, 1
0x18002b342  add     esi, esi
0x18002b344  add     ebx, ebx
0x18002b346  mov     rax, [rcx]
0x18002b349  mov     rax, [rax+188h]
0x18002b350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b355  mov     r9, rbp
0x18002b358  mov     [rsp+68h+var_40], r14d
0x18002b35d  mov     r8d, ebx
0x18002b360  mov     [rsp+68h+var_48], esi
0x18002b364  mov     rdx, rdi
0x18002b367  mov     rcx, rax
0x18002b36a  call    cs:__imp_ClusterGroupOpenEnumEx
0x18002b371  nop     dword ptr [rax+rax+00h]
0x18002b376  mov     rcx, r15
0x18002b379  mov     rbx, rax
0x18002b37c  call    ?Close@?$AutoHandle@PEAU_HGROUPENUMEX@@K$1?ClusterGroupCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUMEX *,ulong,&ClusterGroupCloseEnumEx(_HGROUPENUMEX *),0>::Close(void)
0x18002b381  lea     rax, [rbx+1]
0x18002b385  mov     [r15], rbx
0x18002b388  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b38e  jnz     short loc_18002B39F
0x18002b390  call    cs:__imp_GetLastError
0x18002b397  nop     dword ptr [rax+rax+00h]
0x18002b39c  mov     r14d, eax
0x18002b39f  mov     eax, r14d
0x18002b3a2  add     rsp, 38h
0x18002b3a6  pop     r15
0x18002b3a8  pop     r14
0x18002b3aa  pop     rdi
0x18002b3ab  pop     rsi
0x18002b3ac  pop     rbp
0x18002b3ad  pop     rbx
0x18002b3ae  retn
```
