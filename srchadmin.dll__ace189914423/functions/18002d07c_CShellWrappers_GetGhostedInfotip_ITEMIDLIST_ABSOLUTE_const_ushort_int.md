# CShellWrappers::GetGhostedInfotip(_ITEMIDLIST_ABSOLUTE const *,ushort *,int)

- ea: `0x18002d07c`
- end: `0x18002d175`
- name: `?GetGhostedInfotip@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAGH@Z`
- size: `249`
- prototype: `int(CShellWrappers *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025e38`

## callees

- `0x1800038ac`
- `0x18000957c`
- `0x18002d07c`
- `0x180032010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x18002d0b4`
- `SHELL32!SHBindToParent` at `0x18002d0b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d150`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CShellWrappers::GetGhostedInfotip(
        CShellWrappers *this,
        const ITEMIDLIST *a2,
        unsigned __int16 *a3,
        int a4)
{
  unsigned __int64 v4; // rdi
  HRESULT v6; // ebx
  void *v7; // rcx
  __int64 v9; // [rsp+40h] [rbp-28h] BYREF
  void *ppv; // [rsp+48h] [rbp-20h] BYREF
  LPCITEMIDLIST ppidlLast[3]; // [rsp+50h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+28h] BYREF

  pv = this;
  v4 = a4;
  ppv = 0;
  ppidlLast[0] = 0;
  v6 = SHBindToParent(a2, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, ppidlLast);
  if ( v6 >= 0 )
  {
    v9 = 0;
    v6 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           0,
           1,
           ppidlLast,
           &GUID_00021500_0000_0000_c000_000000000046,
           0,
           &v9);
    if ( v6 >= 0 )
    {
      pv = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v9 + 24LL))(v9, 0, &pv);
      v7 = pv;
      if ( v6 >= 0 )
      {
        if ( pv )
        {
          StringCchCopyW(a3, v4, (const unsigned __int16 *)pv);
          v7 = pv;
        }
        else
        {
          v6 = -2147467259;
        }
      }
      CoTaskMemFree(v7);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002d07c  mov     [rsp-20h+pv], rcx
0x18002d081  push    rbp
0x18002d082  push    rbx
0x18002d083  push    rsi
0x18002d084  push    rdi
0x18002d085  mov     rbp, rsp
0x18002d088  sub     rsp, 68h
0x18002d08c  movsxd  rdi, r9d
0x18002d08f  mov     rsi, r8
0x18002d092  mov     rcx, rdx; pidl
0x18002d095  mov     [rbp+ppv], 0
0x18002d09d  mov     [rbp+ppidlLast], 0
0x18002d0a5  lea     r9, [rbp+ppidlLast]; ppidlLast
0x18002d0a9  lea     r8, [rbp+ppv]; ppv
0x18002d0ad  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002d0b4  call    cs:__imp_SHBindToParent
0x18002d0ba  mov     ebx, eax
0x18002d0bc  test    eax, eax
0x18002d0be  js      loc_18002D161
0x18002d0c4  mov     [rbp+var_28], 0
0x18002d0cc  mov     rcx, [rbp+ppv]
0x18002d0d0  mov     rax, [rcx]
0x18002d0d3  lea     rdx, [rbp+var_28]
0x18002d0d7  mov     [rsp+68h+var_38], rdx
0x18002d0dc  mov     [rsp+68h+var_40], 0
0x18002d0e5  lea     rdx, _GUID_00021500_0000_0000_c000_000000000046
0x18002d0ec  mov     [rsp+68h+var_48], rdx
0x18002d0f1  lea     r9, [rbp+ppidlLast]
0x18002d0f5  xor     edx, edx
0x18002d0f7  lea     r8d, [rdx+1]
0x18002d0fb  mov     rax, [rax+50h]
0x18002d0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d104  mov     ebx, eax
0x18002d106  test    eax, eax
0x18002d108  js      short loc_18002D157
0x18002d10a  mov     [rbp+pv], 0
0x18002d112  mov     rcx, [rbp+var_28]
0x18002d116  mov     rax, [rcx]
0x18002d119  lea     r8, [rbp+pv]
0x18002d11d  xor     edx, edx
0x18002d11f  mov     rax, [rax+18h]
0x18002d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d128  mov     ebx, eax
0x18002d12a  mov     rcx, [rbp+pv]
0x18002d12e  test    eax, eax
0x18002d130  js      short loc_18002D150
0x18002d132  test    rcx, rcx
0x18002d135  jnz     short loc_18002D13E
0x18002d137  mov     ebx, 80004005h
0x18002d13c  jmp     short loc_18002D150
0x18002d13e  mov     rdx, rdi; unsigned __int64
0x18002d141  mov     r8, rcx; unsigned __int16 *
0x18002d144  mov     rcx, rsi; unsigned __int16 *
0x18002d147  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d14c  mov     rcx, [rbp+pv]; pv
0x18002d150  call    cs:__imp_CoTaskMemFree
0x18002d156  nop
0x18002d157  lea     rcx, [rbp+var_28]
0x18002d15b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d160  nop
0x18002d161  lea     rcx, [rbp+ppv]
0x18002d165  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002d16a  mov     eax, ebx
0x18002d16c  add     rsp, 68h
0x18002d170  pop     rdi
0x18002d171  pop     rsi
0x18002d172  pop     rbx
0x18002d173  pop     rbp
0x18002d174  retn
```
