# SHCreatePropertyBagOnRegKey

- ea: `0x180005a40`
- end: `0x180005b83`
- name: `SHCreatePropertyBagOnRegKey`
- size: `323`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, unsigned int@<r8d>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004d10`
- `0x180004ef0`

## callees

- `0x180005a40`
- `0x180005b8c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005b78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005b78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ab8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ab8`

## pseudocode

```c
__int64 __fastcall SHCreatePropertyBagOnRegKey(HKEY hKey, LPCWSTR lpSubKey, unsigned int a3, __int64 a4, _QWORD *a5)
{
  HANDLE ProcessHeap; // rax
  CBasePropertyBag *v10; // rax
  CBasePropertyBag *v11; // rdi
  REGSAM samDesired; // r9d
  LSTATUS Key; // eax
  unsigned int v15; // ebx
  bool v16; // sf
  int v17; // ecx

  *a5 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = (CBasePropertyBag *)HeapAlloc(ProcessHeap, 8u, 0x28u);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  CBasePropertyBag::CBasePropertyBag(v10, a3);
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 1) = &CRegPropertyBag::`vftable'{for `IPropertyBag2'};
  *(_QWORD *)v11 = &CRegPropertyBag::`vftable'{for `IPropertyBag'};
  *((_QWORD *)v11 + 2) = &CBasePropertyBag::`vftable'{for `IDataProvider'};
  v17 = *((_DWORD *)v11 + 7);
  if ( (v17 & 3) == 1 )
  {
    samDesired = 0;
    goto LABEL_13;
  }
  samDesired = 131097;
  if ( (v17 & 3) != 0 )
LABEL_13:
    samDesired |= 0x20006u;
  if ( (v17 & 0x1000) != 0 )
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, (PHKEY)v11 + 4, 0);
  else
    Key = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, (PHKEY)v11 + 4);
  v15 = Key;
  v16 = Key < 0;
  if ( Key > 0 )
  {
    v15 = (unsigned __int16)Key | 0x80070000;
    v16 = 1;
  }
  if ( !v16 )
    v15 = (**(__int64 (__fastcall ***)(CBasePropertyBag *, __int64, _QWORD *))v11)(v11, a4, a5);
  (*(void (__fastcall **)(CBasePropertyBag *))(*(_QWORD *)v11 + 16LL))(v11);
  return v15;
}

```

## disassembly

```asm
0x180005a40  push    rbx
0x180005a42  push    rbp
0x180005a43  push    rsi
0x180005a44  push    rdi
0x180005a45  push    r12
0x180005a47  push    r14
0x180005a49  push    r15
0x180005a4b  sub     rsp, 50h
0x180005a4f  mov     rsi, [rsp+88h+arg_20]
0x180005a57  xor     r12d, r12d
0x180005a5a  mov     r15, r9
0x180005a5d  mov     ebx, r8d
0x180005a60  mov     rbp, rdx
0x180005a63  mov     r14, rcx
0x180005a66  mov     [rsi], r12
0x180005a69  call    cs:__imp_GetProcessHeap
0x180005a6f  mov     edx, 8; dwFlags
0x180005a74  mov     r8d, 28h ; '('; dwBytes
0x180005a7a  mov     rcx, rax; hHeap
0x180005a7d  call    cs:__imp_HeapAlloc
0x180005a83  mov     rdi, rax
0x180005a86  test    rax, rax
0x180005a89  jnz     short loc_180005B07
0x180005a8b  mov     eax, 8007000Eh
0x180005a90  jmp     short loc_180005AF8
0x180005a92  mov     r9d, 20019h; samDesired
0x180005a98  test    eax, eax
0x180005a9a  jnz     loc_180005B4D
0x180005aa0  xor     r8d, r8d; Reserved
0x180005aa3  bt      ecx, 0Ch
0x180005aa7  mov     rcx, r14; hKey
0x180005aaa  jb      loc_180005B59
0x180005ab0  mov     [rsp+88h+phkResult], rdx; phkResult
0x180005ab5  mov     rdx, rbp; lpSubKey
0x180005ab8  call    cs:__imp_RegOpenKeyExW
0x180005abe  mov     ebx, eax
0x180005ac0  test    eax, eax
0x180005ac2  jle     short loc_180005ACF
0x180005ac4  movzx   ebx, bx
0x180005ac7  or      ebx, 80070000h
0x180005acd  test    ebx, ebx
0x180005acf  js      short loc_180005AE7
0x180005ad1  mov     rax, [rdi]
0x180005ad4  mov     r8, rsi
0x180005ad7  mov     rdx, r15
0x180005ada  mov     rcx, rdi
0x180005add  mov     rax, [rax]
0x180005ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae5  mov     ebx, eax
0x180005ae7  mov     rax, [rdi]
0x180005aea  mov     rcx, rdi
0x180005aed  mov     rax, [rax+10h]
0x180005af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af6  mov     eax, ebx
0x180005af8  add     rsp, 50h
0x180005afc  pop     r15
0x180005afe  pop     r14
0x180005b00  pop     r12
0x180005b02  pop     rdi
0x180005b03  pop     rsi
0x180005b04  pop     rbp
0x180005b05  pop     rbx
0x180005b06  retn
0x180005b07  mov     edx, ebx; unsigned int
0x180005b09  mov     rcx, rdi; this
0x180005b0c  call    ??0CBasePropertyBag@@IEAA@K@Z; CBasePropertyBag::CBasePropertyBag(ulong)
0x180005b11  lea     rax, ??_7CRegPropertyBag@@6BIPropertyBag2@@@; const CRegPropertyBag::`vftable'{for `IPropertyBag2'}
0x180005b18  mov     [rdi+20h], r12
0x180005b1c  mov     [rdi+8], rax
0x180005b20  lea     rcx, ??_7CRegPropertyBag@@6BIPropertyBag@@@; const CRegPropertyBag::`vftable'{for `IPropertyBag'}
0x180005b27  lea     rax, ??_7CBasePropertyBag@@6BIDataProvider@@@; const CBasePropertyBag::`vftable'{for `IDataProvider'}
0x180005b2e  mov     [rdi], rcx
0x180005b31  mov     [rdi+10h], rax
0x180005b35  lea     rdx, [rdi+20h]
0x180005b39  mov     ecx, [rdi+1Ch]
0x180005b3c  mov     eax, ecx
0x180005b3e  and     eax, 3
0x180005b41  cmp     eax, 1
0x180005b44  jnz     loc_180005A92
0x180005b4a  mov     r9d, r12d
0x180005b4d  or      r9d, 20006h
0x180005b54  jmp     loc_180005AA0
0x180005b59  mov     [rsp+88h+lpdwDisposition], r12; lpdwDisposition
0x180005b5e  mov     [rsp+88h+var_50], rdx; phkResult
0x180005b63  mov     rdx, rbp; lpSubKey
0x180005b66  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180005b6b  mov     [rsp+88h+samDesired], r9d; samDesired
0x180005b70  xor     r9d, r9d; lpClass
0x180005b73  mov     dword ptr [rsp+88h+phkResult], r12d; dwOptions
0x180005b78  call    cs:__imp_RegCreateKeyExW
0x180005b7e  jmp     loc_180005ABE
```
