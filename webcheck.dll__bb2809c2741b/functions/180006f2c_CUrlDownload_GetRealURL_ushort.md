# CUrlDownload::GetRealURL(ushort * *)

- ea: `0x180006f2c`
- end: `0x180007027`
- name: `?GetRealURL@CUrlDownload@@QEAAJPEAPEAG@Z`
- size: `251`
- prototype: `__int64 __fastcall(CUrlDownload *__hidden this, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f4b4`
- `0x1800200d8`
- `0x1800209e0`

## callees

- `0x180006f2c`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006ff1`
- `KERNEL32!LocalFree` at `0x180006ff1`
- `SHLWAPI!StrDupW` at `0x180006f58`
- `SHLWAPI!StrDupW` at `0x180006ffc`
- `SHLWAPI!StrDupW` at `0x18000700e`
- `SHLWAPI!StrDupW` at `0x180006f58`
- `SHLWAPI!StrDupW` at `0x180006ffc`
- `SHLWAPI!StrDupW` at `0x18000700e`
- `ole32!CoTaskMemFree` at `0x18000701c`
- `ole32!CoTaskMemFree` at `0x18000701c`

## pseudocode

```c
__int64 __fastcall CUrlDownload::GetRealURL(CUrlDownload *this, unsigned __int16 **a2)
{
  bool v2; // zf
  WCHAR *v5; // rcx
  void (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  PWSTR v8; // rax
  const WCHAR *v9; // rcx
  unsigned __int16 *v10; // rax
  WCHAR *v11; // rcx
  PCWSTR pszSrch; // [rsp+30h] [rbp+8h] BYREF
  __int64 v13; // [rsp+38h] [rbp+10h] BYREF

  v2 = *((_DWORD *)this + 38) == 0;
  *a2 = 0;
  if ( v2 )
  {
    v5 = (WCHAR *)*((_QWORD *)this + 92);
LABEL_3:
    if ( v5 )
      *a2 = StrDupW(v5);
    return *a2 == 0 ? 0x8007000E : 0;
  }
  v7 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 14);
  v13 = 0;
  pszSrch = 0;
  if ( v7 )
  {
    (**v7)(v7, &IID_ITargetContainer, &v13);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v13 + 24LL))(v13, &pszSrch);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  v5 = (WCHAR *)*((_QWORD *)this + 92);
  if ( !pszSrch )
    goto LABEL_3;
  if ( v5 )
    LocalFree(v5);
  v8 = StrDupW(pszSrch);
  v9 = pszSrch;
  *((_QWORD *)this + 92) = v8;
  v10 = StrDupW(v9);
  v11 = (WCHAR *)pszSrch;
  *a2 = v10;
  CoTaskMemFree(v11);
  return *a2 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180006f2c  mov     [rsp+arg_10], rbx
0x180006f31  push    rdi
0x180006f32  sub     rsp, 20h
0x180006f36  cmp     dword ptr [rcx+98h], 0
0x180006f3d  mov     rdi, rdx
0x180006f40  mov     rbx, rcx
0x180006f43  mov     qword ptr [rdx], 0
0x180006f4a  jnz     short loc_180006F7B
0x180006f4c  mov     rcx, [rcx+2E0h]; pszSrch
0x180006f53  test    rcx, rcx
0x180006f56  jz      short loc_180006F61
0x180006f58  call    cs:__imp_StrDupW
0x180006f5e  mov     [rdi], rax
0x180006f61  mov     rax, [rdi]
0x180006f64  mov     rbx, [rsp+28h+arg_10]
0x180006f69  neg     rax
0x180006f6c  sbb     eax, eax
0x180006f6e  not     eax
0x180006f70  and     eax, 8007000Eh
0x180006f75  add     rsp, 20h
0x180006f79  pop     rdi
0x180006f7a  retn
0x180006f7b  mov     rcx, [rcx+70h]
0x180006f7f  mov     [rsp+28h+arg_8], 0
0x180006f88  mov     [rsp+28h+pszSrch], 0
0x180006f91  test    rcx, rcx
0x180006f94  jz      short loc_180006FD9
0x180006f96  mov     rax, [rcx]
0x180006f99  lea     r8, [rsp+28h+arg_8]
0x180006f9e  lea     rdx, IID_ITargetContainer
0x180006fa5  mov     rax, [rax]
0x180006fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fad  mov     rcx, [rsp+28h+arg_8]
0x180006fb2  test    rcx, rcx
0x180006fb5  jz      short loc_180006FD9
0x180006fb7  mov     rax, [rcx]
0x180006fba  lea     rdx, [rsp+28h+pszSrch]
0x180006fbf  mov     rax, [rax+18h]
0x180006fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc8  mov     rcx, [rsp+28h+arg_8]
0x180006fcd  mov     rax, [rcx]
0x180006fd0  mov     rax, [rax+10h]
0x180006fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd9  cmp     [rsp+28h+pszSrch], 0
0x180006fdf  mov     rcx, [rbx+2E0h]; hMem
0x180006fe6  jz      loc_180006F53
0x180006fec  test    rcx, rcx
0x180006fef  jz      short loc_180006FF7
0x180006ff1  call    cs:__imp_LocalFree
0x180006ff7  mov     rcx, [rsp+28h+pszSrch]; pszSrch
0x180006ffc  call    cs:__imp_StrDupW
0x180007002  mov     rcx, [rsp+28h+pszSrch]; pszSrch
0x180007007  mov     [rbx+2E0h], rax
0x18000700e  call    cs:__imp_StrDupW
0x180007014  mov     rcx, [rsp+28h+pszSrch]; pv
0x180007019  mov     [rdi], rax
0x18000701c  call    cs:__imp_CoTaskMemFree
0x180007022  jmp     loc_180006F61
```
