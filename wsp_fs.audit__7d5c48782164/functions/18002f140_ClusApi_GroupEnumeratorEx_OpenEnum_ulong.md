# ClusApi::GroupEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002f140`
- end: `0x18002f1f0`
- name: `?OpenEnum@GroupEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `176`
- prototype: `unsigned int __fastcall(ClusApi::GroupEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e7dc`
- `0x18002f140`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1d0`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002f1aa`
- `CLUSAPI!ClusterGroupOpenEnumEx` at `0x18002f1aa`

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
0x18002f140  push    rbx
0x18002f142  push    rbp
0x18002f143  push    rsi
0x18002f144  push    rdi
0x18002f145  push    r14
0x18002f147  push    r15
0x18002f149  sub     rsp, 38h
0x18002f14d  lea     r15, [rcx+20h]
0x18002f151  xor     r14d, r14d
0x18002f154  mov     rax, [r15]
0x18002f157  inc     rax
0x18002f15a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f160  jnz     short loc_18002F1DF
0x18002f162  mov     rbp, [rcx+58h]
0x18002f166  mov     rsi, [rcx+60h]
0x18002f16a  mov     rdi, [rcx+40h]
0x18002f16e  sub     rsi, rbp
0x18002f171  mov     rbx, [rcx+48h]
0x18002f175  mov     rcx, [rcx+30h]
0x18002f179  sub     rbx, rdi
0x18002f17c  sar     rsi, 1
0x18002f17f  sar     rbx, 1
0x18002f182  add     esi, esi
0x18002f184  add     ebx, ebx
0x18002f186  mov     rax, [rcx]
0x18002f189  mov     rax, [rax+188h]
0x18002f190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f195  mov     r9, rbp
0x18002f198  mov     [rsp+68h+var_40], r14d
0x18002f19d  mov     r8d, ebx
0x18002f1a0  mov     [rsp+68h+var_48], esi
0x18002f1a4  mov     rdx, rdi
0x18002f1a7  mov     rcx, rax
0x18002f1aa  call    cs:__imp_ClusterGroupOpenEnumEx
0x18002f1b1  nop     dword ptr [rax+rax+00h]
0x18002f1b6  mov     rcx, r15
0x18002f1b9  mov     rbx, rax
0x18002f1bc  call    ?Close@?$AutoHandle@PEAU_HGROUPENUMEX@@K$1?ClusterGroupCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HGROUPENUMEX *,ulong,&ClusterGroupCloseEnumEx(_HGROUPENUMEX *),0>::Close(void)
0x18002f1c1  lea     rax, [rbx+1]
0x18002f1c5  mov     [r15], rbx
0x18002f1c8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f1ce  jnz     short loc_18002F1DF
0x18002f1d0  call    cs:__imp_GetLastError
0x18002f1d7  nop     dword ptr [rax+rax+00h]
0x18002f1dc  mov     r14d, eax
0x18002f1df  mov     eax, r14d
0x18002f1e2  add     rsp, 38h
0x18002f1e6  pop     r15
0x18002f1e8  pop     r14
0x18002f1ea  pop     rdi
0x18002f1eb  pop     rsi
0x18002f1ec  pop     rbp
0x18002f1ed  pop     rbx
0x18002f1ee  retn
```
