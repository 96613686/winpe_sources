# SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)

- ea: `0x18000783c`
- end: `0x1800078f6`
- name: `?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z`
- size: `186`
- prototype: `__int64 __fastcall(HWND, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007770`
- `0x18000868c`

## callees

- `0x18000783c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007879`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007879`

## pseudocode

```c
__int64 __fastcall SHCreateFileOperation(HWND a1, unsigned int a2, const struct _GUID *a3, void **a4)
{
  HRESULT v6; // ebx
  LPVOID v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v6 = CoCreateInstance(&CLSID_FileOperation, 0, 3u, &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8, &v8);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, a2);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v8 + 72LL))(v8, 0);
      if ( v6 >= 0 )
        v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))v8)(
               v8,
               &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8,
               a4);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000783c  mov     r11, rsp
0x18000783f  mov     [r11+8], rbx
0x180007843  mov     [r11+10h], rsi
0x180007847  mov     [r11+18h], r8
0x18000784b  push    rdi
0x18000784c  sub     rsp, 30h
0x180007850  mov     edi, edx
0x180007852  mov     qword ptr [r11+18h], 0
0x18000785a  xor     edx, edx; pUnkOuter
0x18000785c  lea     rax, [r11+18h]
0x180007860  mov     rsi, r9
0x180007863  mov     [r11-18h], rax
0x180007867  lea     r9, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8; riid
0x18000786e  lea     rcx, CLSID_FileOperation; rclsid
0x180007875  lea     r8d, [rdx+3]; dwClsContext
0x180007879  call    cs:__imp_CoCreateInstance
0x18000787f  mov     ebx, eax
0x180007881  test    eax, eax
0x180007883  js      short loc_1800078E4
0x180007885  mov     rcx, [rsp+38h+arg_10]
0x18000788a  mov     edx, edi
0x18000788c  mov     rax, [rcx]
0x18000788f  mov     rax, [rax+28h]
0x180007893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007898  mov     ebx, eax
0x18000789a  test    eax, eax
0x18000789c  js      short loc_1800078D3
0x18000789e  mov     rcx, [rsp+38h+arg_10]
0x1800078a3  xor     edx, edx
0x1800078a5  mov     rax, [rcx]
0x1800078a8  mov     rax, [rax+48h]
0x1800078ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b1  mov     ebx, eax
0x1800078b3  test    eax, eax
0x1800078b5  js      short loc_1800078D3
0x1800078b7  mov     rcx, [rsp+38h+arg_10]
0x1800078bc  lea     rdx, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8
0x1800078c3  mov     r8, rsi
0x1800078c6  mov     rax, [rcx]
0x1800078c9  mov     rax, [rax]
0x1800078cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d1  mov     ebx, eax
0x1800078d3  mov     rcx, [rsp+38h+arg_10]
0x1800078d8  mov     rax, [rcx]
0x1800078db  mov     rax, [rax+10h]
0x1800078df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e4  mov     rsi, [rsp+38h+arg_8]
0x1800078e9  mov     eax, ebx
0x1800078eb  mov     rbx, [rsp+38h+arg_0]
0x1800078f0  add     rsp, 30h
0x1800078f4  pop     rdi
0x1800078f5  retn
```
