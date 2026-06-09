# ClusApi::ResourceEnumeratorEx::OpenEnum(ulong)

- ea: `0x18002b660`
- end: `0x18002b710`
- name: `?OpenEnum@ResourceEnumeratorEx@ClusApi@@MEAAKK@Z`
- size: `176`
- prototype: `unsigned int __fastcall(ClusApi::ResourceEnumeratorEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002aa7c`
- `0x18002b660`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6f0`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002b6ca`
- `CLUSAPI!ClusterResourceOpenEnumEx` at `0x18002b6ca`

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
0x18002b660  push    rbx
0x18002b662  push    rbp
0x18002b663  push    rsi
0x18002b664  push    rdi
0x18002b665  push    r14
0x18002b667  push    r15
0x18002b669  sub     rsp, 38h
0x18002b66d  lea     r15, [rcx+20h]
0x18002b671  xor     r14d, r14d
0x18002b674  mov     rax, [r15]
0x18002b677  inc     rax
0x18002b67a  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b680  jnz     short loc_18002B6FF
0x18002b682  mov     rbp, [rcx+58h]
0x18002b686  mov     rsi, [rcx+60h]
0x18002b68a  mov     rdi, [rcx+40h]
0x18002b68e  sub     rsi, rbp
0x18002b691  mov     rbx, [rcx+48h]
0x18002b695  mov     rcx, [rcx+30h]
0x18002b699  sub     rbx, rdi
0x18002b69c  sar     rsi, 1
0x18002b69f  sar     rbx, 1
0x18002b6a2  add     esi, esi
0x18002b6a4  add     ebx, ebx
0x18002b6a6  mov     rax, [rcx]
0x18002b6a9  mov     rax, [rax+188h]
0x18002b6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6b5  mov     r9, rbp
0x18002b6b8  mov     [rsp+68h+var_40], r14d
0x18002b6bd  mov     r8d, ebx
0x18002b6c0  mov     [rsp+68h+var_48], esi
0x18002b6c4  mov     rdx, rdi
0x18002b6c7  mov     rcx, rax
0x18002b6ca  call    cs:__imp_ClusterResourceOpenEnumEx
0x18002b6d1  nop     dword ptr [rax+rax+00h]
0x18002b6d6  mov     rcx, r15
0x18002b6d9  mov     rbx, rax
0x18002b6dc  call    ?Close@?$AutoHandle@PEAU_HRESENUMEX@@K$1?ClusterResourceCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HRESENUMEX *,ulong,&ClusterResourceCloseEnumEx(_HRESENUMEX *),0>::Close(void)
0x18002b6e1  lea     rax, [rbx+1]
0x18002b6e5  mov     [r15], rbx
0x18002b6e8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b6ee  jnz     short loc_18002B6FF
0x18002b6f0  call    cs:__imp_GetLastError
0x18002b6f7  nop     dword ptr [rax+rax+00h]
0x18002b6fc  mov     r14d, eax
0x18002b6ff  mov     eax, r14d
0x18002b702  add     rsp, 38h
0x18002b706  pop     r15
0x18002b708  pop     r14
0x18002b70a  pop     rdi
0x18002b70b  pop     rsi
0x18002b70c  pop     rbp
0x18002b70d  pop     rbx
0x18002b70e  retn
```
