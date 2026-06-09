# RegisterCLSIDInCategory

- ea: `0x1800518a0`
- end: `0x18005195b`
- name: `RegisterCLSIDInCategory`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045c4c`

## callees

- `0x1800518a0`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800518e9`
- `OLE32!CoCreateInstance` at `0x1800518e9`

## pseudocode

```c
__int64 __fastcall RegisterCLSIDInCategory(__int64 a1, __int128 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &v6);
  if ( v4 >= 0 )
  {
    v7 = *a2;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int128 *))(*(_QWORD *)v6 + 40LL))(v6, a1, 1, &v7);
  }
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800518a0  mov     r11, rsp
0x1800518a3  mov     [r11+10h], rbx
0x1800518a7  mov     [r11+18h], rsi
0x1800518ab  push    rdi
0x1800518ac  sub     rsp, 50h
0x1800518b0  mov     rax, cs:__security_cookie
0x1800518b7  xor     rax, rsp
0x1800518ba  mov     [rsp+58h+var_10], rax
0x1800518bf  mov     rdi, rdx
0x1800518c2  mov     qword ptr [r11-28h], 0
0x1800518ca  xor     edx, edx; pUnkOuter
0x1800518cc  lea     rax, [r11-28h]
0x1800518d0  mov     rsi, rcx
0x1800518d3  mov     [r11-38h], rax
0x1800518d7  lea     r9, IID_ICatRegister; riid
0x1800518de  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800518e5  lea     r8d, [rdx+1]; dwClsContext
0x1800518e9  call    cs:__imp_CoCreateInstance
0x1800518f0  nop     dword ptr [rax+rax+00h]
0x1800518f5  mov     ebx, eax
0x1800518f7  test    eax, eax
0x1800518f9  js      short loc_180051925
0x1800518fb  mov     rcx, [rsp+58h+var_28]
0x180051900  lea     r9, [rsp+58h+var_20]
0x180051905  movaps  xmm0, xmmword ptr [rdi]
0x180051908  mov     r8d, 1
0x18005190e  movdqu  [rsp+58h+var_20], xmm0
0x180051914  mov     rdx, rsi
0x180051917  mov     rax, [rcx]
0x18005191a  mov     rax, [rax+28h]
0x18005191e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051923  mov     ebx, eax
0x180051925  mov     rcx, [rsp+58h+var_28]
0x18005192a  test    rcx, rcx
0x18005192d  jz      short loc_18005193B
0x18005192f  mov     rax, [rcx]
0x180051932  mov     rax, [rax+10h]
0x180051936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005193b  mov     eax, ebx
0x18005193d  mov     rcx, [rsp+58h+var_10]
0x180051942  xor     rcx, rsp; StackCookie
0x180051945  call    __security_check_cookie
0x18005194a  mov     rbx, [rsp+58h+arg_8]
0x18005194f  mov     rsi, [rsp+58h+arg_10]
0x180051954  add     rsp, 50h
0x180051958  pop     rdi
0x180051959  retn
```
