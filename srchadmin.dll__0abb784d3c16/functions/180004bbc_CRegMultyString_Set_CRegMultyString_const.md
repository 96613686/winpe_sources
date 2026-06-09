# CRegMultyString::Set(CRegMultyString const &)

- ea: `0x180004bbc`
- end: `0x180004d9c`
- name: `?Set@CRegMultyString@@QEAAJAEBV1@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CRegMultyString *__hidden this, const struct CRegMultyString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014738`

## callees

- `0x180004bbc`
- `0x180004da4`
- `0x1800057a0`
- `0x1800061c0`
- `0x18001a7fc`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180004cfe`
- `SHLWAPI!SHStrDupW` at `0x180004d13`
- `SHLWAPI!SHStrDupW` at `0x180004cfe`
- `SHLWAPI!SHStrDupW` at `0x180004d13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004c35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004c35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegMultyString::Set(LPCWSTR *this, const struct CRegMultyString *a2)
{
  const WCHAR *v4; // rsi
  int v5; // eax
  int v6; // ebx
  LSTATUS v7; // eax
  unsigned __int64 v8; // r14
  __int64 v9; // rax
  bool v10; // cf
  SIZE_T v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // r12
  LPCWSTR v14; // r13
  unsigned int i; // ebp
  LPWSTR *v16; // r15
  const BYTE *v17; // rcx
  __int64 v18; // rax
  LSTATUS v19; // eax
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp+10h]
  _QWORD *v23; // [rsp+A0h] [rbp+18h]

  v4 = 0;
  hKey = 0;
  v5 = CRegMultyString::DeleteInternal((CRegMultyString *)this);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, this[1], 0, 0, 0, 2u, 0, &hKey, 0);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 && *((_QWORD *)a2 + 2) )
    {
      v8 = *((unsigned int *)a2 + 6);
      v22 = v8;
      v9 = 16 * v8;
      if ( !is_mul_ok(v8, 0x10u) )
        v9 = -1;
      v10 = __CFADD__(v9, 8);
      v11 = v9 + 8;
      if ( v10 )
        v11 = -1;
      v12 = operator new(v11);
      v23 = v12;
      if ( v12 )
      {
        *v12 = v8;
        v4 = (const WCHAR *)(v12 + 1);
        `eh vector constructor iterator'(
          v12 + 1,
          0x10u,
          (unsigned int)v8,
          (void (*)(void *))CRegMultyString::CStrRegValue::CStrRegValue,
          (void (*)(void *))CRegMultyString::CStrRegValue::~CStrRegValue);
      }
      this[2] = v4;
      if ( v4 )
        *((_DWORD *)this + 6) = *((_DWORD *)a2 + 6);
      else
        v6 = -2147024888;
    }
  }
  v13 = *((_QWORD *)a2 + 2);
  v14 = this[2];
  for ( i = 0; v6 >= 0 && i < *((_DWORD *)this + 6); ++i )
  {
    v16 = (LPWSTR *)&v14[8 * i];
    v6 = SHStrDupW(*(LPCWSTR *)(v13 + 16LL * i), v16);
    if ( v6 >= 0 )
    {
      v6 = SHStrDupW(*(LPCWSTR *)(v13 + 16LL * i + 8), v16 + 1);
      if ( v6 >= 0 )
      {
        v17 = (const BYTE *)v16[1];
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v17[2 * v18] );
        v19 = RegSetValueExW(hKey, *v16, 0, 1u, v17, 2 * v18 + 2);
        v6 = v19;
        if ( v19 > 0 )
          v6 = (unsigned __int16)v19 | 0x80070000;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004bbc  mov     rax, rsp
0x180004bbf  mov     [rax+20h], rbx
0x180004bc3  push    rbp
0x180004bc4  push    rsi
0x180004bc5  push    rdi
0x180004bc6  push    r12
0x180004bc8  push    r13
0x180004bca  push    r14
0x180004bcc  push    r15
0x180004bce  sub     rsp, 50h
0x180004bd2  mov     rbp, rdx
0x180004bd5  mov     rdi, rcx
0x180004bd8  xor     esi, esi
0x180004bda  mov     [rax+8], rsi
0x180004bde  call    ?DeleteInternal@CRegMultyString@@IEAAJXZ; CRegMultyString::DeleteInternal(void)
0x180004be3  mov     ebx, eax
0x180004be5  mov     r14d, 80070000h
0x180004beb  test    eax, eax
0x180004bed  jle     short loc_180004BF5
0x180004bef  movzx   ebx, ax
0x180004bf2  or      ebx, r14d
0x180004bf5  or      r12, 0FFFFFFFFFFFFFFFFh
0x180004bf9  test    ebx, ebx
0x180004bfb  js      loc_180004CCF
0x180004c01  mov     [rsp+88h+lpdwDisposition], rsi; lpdwDisposition
0x180004c06  lea     rax, [rsp+88h+hKey]
0x180004c0e  mov     [rsp+88h+phkResult], rax; phkResult
0x180004c13  mov     [rsp+88h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180004c18  mov     [rsp+88h+samDesired], 2; samDesired
0x180004c20  mov     [rsp+88h+dwOptions], esi; dwOptions
0x180004c24  xor     r9d, r9d; lpClass
0x180004c27  xor     r8d, r8d; Reserved
0x180004c2a  mov     rdx, [rdi+8]; lpSubKey
0x180004c2e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004c35  call    cs:__imp_RegCreateKeyExW
0x180004c3b  mov     ebx, eax
0x180004c3d  test    eax, eax
0x180004c3f  jle     short loc_180004C47
0x180004c41  movzx   ebx, ax
0x180004c44  or      ebx, r14d
0x180004c47  test    ebx, ebx
0x180004c49  js      loc_180004CCF
0x180004c4f  cmp     [rbp+10h], rsi
0x180004c53  jz      short loc_180004CCF
0x180004c55  mov     r14d, [rbp+18h]
0x180004c59  mov     [rsp+88h+arg_8], r14
0x180004c61  mov     r15d, 10h
0x180004c67  mov     eax, r15d
0x180004c6a  mul     r14
0x180004c6d  cmovb   rax, r12
0x180004c71  add     rax, 8
0x180004c75  cmovb   rax, r12
0x180004c79  mov     rcx, rax; unsigned __int64
0x180004c7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c81  mov     [rsp+88h+arg_10], rax
0x180004c89  test    rax, rax
0x180004c8c  jz      short loc_180004CB7
0x180004c8e  mov     [rax], r14
0x180004c91  lea     rsi, [rax+8]
0x180004c95  lea     rax, ??1CStrRegValue@CRegMultyString@@QEAA@XZ; CRegMultyString::CStrRegValue::~CStrRegValue(void)
0x180004c9c  mov     qword ptr [rsp+88h+dwOptions], rax; void (*)(void *)
0x180004ca1  lea     r9, ??0CStrRegValue@CRegMultyString@@QEAA@XZ; void (*)(void *)
0x180004ca8  mov     r8d, r14d; unsigned __int64
0x180004cab  mov     edx, r15d; unsigned __int64
0x180004cae  mov     rcx, rsi; void *
0x180004cb1  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180004cb6  nop
0x180004cb7  mov     [rdi+10h], rsi
0x180004cbb  test    rsi, rsi
0x180004cbe  jz      short loc_180004CC8
0x180004cc0  mov     eax, [rbp+18h]
0x180004cc3  mov     [rdi+18h], eax
0x180004cc6  jmp     short loc_180004CCD
0x180004cc8  mov     ebx, 80070008h
0x180004ccd  xor     esi, esi
0x180004ccf  mov     r12, [rbp+10h]
0x180004cd3  mov     r13, [rdi+10h]
0x180004cd7  mov     ebp, esi
0x180004cd9  jmp     loc_180004D6D
0x180004cde  cmp     ebp, [rdi+18h]
0x180004ce1  jnb     loc_180004D75
0x180004ce7  mov     esi, ebp
0x180004ce9  add     rsi, rsi
0x180004cec  lea     r15, ds:0[rsi*8]
0x180004cf4  add     r15, r13
0x180004cf7  mov     rdx, r15; ppwsz
0x180004cfa  mov     rcx, [r12+rsi*8]; psz
0x180004cfe  call    cs:__imp_SHStrDupW
0x180004d04  mov     ebx, eax
0x180004d06  test    eax, eax
0x180004d08  js      short loc_180004D6B
0x180004d0a  lea     rdx, [r15+8]; ppwsz
0x180004d0e  mov     rcx, [r12+rsi*8+8]; psz
0x180004d13  call    cs:__imp_SHStrDupW
0x180004d19  mov     ebx, eax
0x180004d1b  xor     esi, esi
0x180004d1d  test    eax, eax
0x180004d1f  js      short loc_180004D6B
0x180004d21  mov     rcx, [r15+8]
0x180004d25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d29  inc     rax
0x180004d2c  cmp     [rcx+rax*2], si
0x180004d30  jnz     short loc_180004D29
0x180004d32  lea     eax, ds:2[rax*2]
0x180004d39  mov     [rsp+88h+samDesired], eax; cbData
0x180004d3d  mov     qword ptr [rsp+88h+dwOptions], rcx; lpData
0x180004d42  mov     r9d, 1; dwType
0x180004d48  xor     r8d, r8d; Reserved
0x180004d4b  mov     rdx, [r15]; lpValueName
0x180004d4e  mov     rcx, [rsp+88h+hKey]; hKey
0x180004d56  call    cs:__imp_RegSetValueExW
0x180004d5c  mov     ebx, eax
0x180004d5e  test    eax, eax
0x180004d60  jle     short loc_180004D6B
0x180004d62  movzx   ebx, ax
0x180004d65  or      ebx, 80070000h
0x180004d6b  inc     ebp
0x180004d6d  test    ebx, ebx
0x180004d6f  jns     loc_180004CDE
0x180004d75  lea     rcx, [rsp+88h+hKey]
0x180004d7d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180004d82  mov     eax, ebx
0x180004d84  mov     rbx, [rsp+88h+arg_18]
0x180004d8c  add     rsp, 50h
0x180004d90  pop     r15
0x180004d92  pop     r14
0x180004d94  pop     r13
0x180004d96  pop     r12
0x180004d98  pop     rdi
0x180004d99  pop     rsi
0x180004d9a  pop     rbp
0x180004d9b  retn
```
