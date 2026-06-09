# HMEHelpers::CopyWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x18001688c`
- end: `0x180016995`
- name: `?CopyWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@0@Z`
- size: `265`
- prototype: `__int64 __fastcall(HMEHelpers *__hidden this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180004ce8`
- `0x180006bfc`

## callees

- `0x18000291e`
- `0x18001688c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800168e0`
- `ole32!CoTaskMemAlloc` at `0x1800168e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001693a`
- `OLEAUT32!__imp_SysAllocString` at `0x180016951`
- `OLEAUT32!__imp_SysAllocString` at `0x180016969`
- `OLEAUT32!__imp_SysAllocString` at `0x18001693a`
- `OLEAUT32!__imp_SysAllocString` at `0x180016951`
- `OLEAUT32!__imp_SysAllocString` at `0x180016969`

## pseudocode

```c
__int64 __fastcall HMEHelpers::CopyWMPDeviceSettings(
        HMEHelpers *this,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a3)
{
  void *v5; // rax
  unsigned int v6; // ebp
  int v7; // r14d
  __int64 v8; // rbx

  if ( this && a2 )
  {
    *(_DWORD *)a2 = *(_DWORD *)this;
    *((_DWORD *)a2 + 1) = *((_DWORD *)this + 1);
    *((_DWORD *)a2 + 4) = *((_DWORD *)this + 4);
    *((_DWORD *)a2 + 3) = *((_DWORD *)this + 3);
    *((_DWORD *)a2 + 2) = *((_DWORD *)this + 2);
    *(_QWORD *)((char *)a2 + 20) = *((unsigned int *)this + 5);
    v5 = CoTaskMemAlloc(32LL * *((int *)this + 6));
    *((_QWORD *)a2 + 4) = v5;
    if ( v5 )
    {
      v6 = 0;
      memset_0(v5, 0, 32LL * *((int *)this + 6));
      v7 = 0;
      for ( *((_DWORD *)a2 + 6) = *((_DWORD *)this + 6);
            v7 < *((_DWORD *)this + 6);
            *(_QWORD *)(v8 + *((_QWORD *)a2 + 4) + 8) = SysAllocString(*(const OLECHAR **)(v8 + *((_QWORD *)this + 4) + 8)) )
      {
        v8 = 32LL * v7;
        *(_DWORD *)(v8 + *((_QWORD *)a2 + 4) + 24) = *(_DWORD *)(v8 + *((_QWORD *)this + 4) + 24);
        *(_QWORD *)(v8 + *((_QWORD *)a2 + 4)) = SysAllocString(*(const OLECHAR **)(*((_QWORD *)this + 4) + v8));
        *(_QWORD *)(*((_QWORD *)a2 + 4) + v8 + 16) = SysAllocString(*(const OLECHAR **)(*((_QWORD *)this + 4) + v8 + 16));
        ++v7;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x18001688c  push    rbx
0x18001688e  push    rbp
0x18001688f  push    rsi
0x180016890  push    rdi
0x180016891  push    r14
0x180016893  sub     rsp, 20h
0x180016897  mov     rsi, rdx
0x18001689a  mov     rdi, rcx
0x18001689d  test    rcx, rcx
0x1800168a0  jz      loc_180016983
0x1800168a6  test    rdx, rdx
0x1800168a9  jz      loc_180016983
0x1800168af  mov     eax, [rcx]
0x1800168b1  mov     [rdx], eax
0x1800168b3  mov     eax, [rcx+4]
0x1800168b6  mov     [rdx+4], eax
0x1800168b9  mov     eax, [rcx+10h]
0x1800168bc  mov     [rdx+10h], eax
0x1800168bf  mov     eax, [rcx+0Ch]
0x1800168c2  mov     [rdx+0Ch], eax
0x1800168c5  mov     eax, [rcx+8]
0x1800168c8  mov     [rdx+8], eax
0x1800168cb  mov     eax, [rcx+14h]
0x1800168ce  mov     [rdx+14h], eax
0x1800168d1  mov     dword ptr [rdx+18h], 0
0x1800168d8  movsxd  rcx, dword ptr [rcx+18h]
0x1800168dc  shl     rcx, 5; cb
0x1800168e0  call    cs:__imp_CoTaskMemAlloc
0x1800168e6  mov     [rsi+20h], rax
0x1800168ea  test    rax, rax
0x1800168ed  jnz     short loc_1800168F9
0x1800168ef  mov     ebp, 8007000Eh
0x1800168f4  jmp     loc_180016988
0x1800168f9  movsxd  r8, dword ptr [rdi+18h]
0x1800168fd  xor     edx, edx; Val
0x1800168ff  shl     r8, 5; Size
0x180016903  mov     rcx, rax; void *
0x180016906  xor     ebp, ebp
0x180016908  call    memset_0
0x18001690d  mov     eax, [rdi+18h]
0x180016910  xor     r14d, r14d
0x180016913  mov     [rsi+18h], eax
0x180016916  cmp     [rdi+18h], ebp
0x180016919  jle     short loc_180016988
0x18001691b  mov     rax, [rdi+20h]
0x18001691f  mov     rcx, [rsi+20h]
0x180016923  movsxd  rbx, r14d
0x180016926  shl     rbx, 5
0x18001692a  mov     eax, [rbx+rax+18h]
0x18001692e  mov     [rbx+rcx+18h], eax
0x180016932  mov     rcx, [rdi+20h]
0x180016936  mov     rcx, [rcx+rbx]; psz
0x18001693a  call    cs:__imp_SysAllocString
0x180016940  mov     rcx, [rsi+20h]
0x180016944  mov     [rbx+rcx], rax
0x180016948  mov     rcx, [rdi+20h]
0x18001694c  mov     rcx, [rcx+rbx+10h]; psz
0x180016951  call    cs:__imp_SysAllocString
0x180016957  mov     rcx, [rsi+20h]
0x18001695b  mov     [rcx+rbx+10h], rax
0x180016960  mov     rcx, [rdi+20h]
0x180016964  mov     rcx, [rbx+rcx+8]; psz
0x180016969  call    cs:__imp_SysAllocString
0x18001696f  mov     rcx, [rsi+20h]
0x180016973  inc     r14d
0x180016976  mov     [rbx+rcx+8], rax
0x18001697b  cmp     r14d, [rdi+18h]
0x18001697f  jl      short loc_18001691B
0x180016981  jmp     short loc_180016988
0x180016983  mov     ebp, 80004003h
0x180016988  mov     eax, ebp
0x18001698a  add     rsp, 20h
0x18001698e  pop     r14
0x180016990  pop     rdi
0x180016991  pop     rsi
0x180016992  pop     rbp
0x180016993  pop     rbx
0x180016994  retn
```
