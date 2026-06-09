# AddMIMEFileTypesPS(int (*)(_PSP *,__int64),__int64)

- ea: `0x180001fa0`
- end: `0x180002028`
- name: `?AddMIMEFileTypesPS@@YAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `136`
- prototype: `__int64 __fastcall(int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001fa0`
- `0x180003010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180001fd9`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180001fd9`

## pseudocode

```c
__int64 __fastcall AddMIMEFileTypesPS(int (*a1)(struct _PSP *, __int64), __int64 a2)
{
  HRESULT v4; // ebx
  void *v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v4 = SHCoCreateInstance(0, &CLSID_FileTypes, 0, &IID_IShellPropSheetExt, &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, int (*)(struct _PSP *, __int64), __int64))(*(_QWORD *)v6 + 24LL))(
           v6,
           a1,
           a2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001fa0  mov     r11, rsp
0x180001fa3  mov     [r11+8], rbx
0x180001fa7  mov     [r11+10h], rsi
0x180001fab  push    rdi
0x180001fac  sub     rsp, 30h
0x180001fb0  mov     rdi, rdx
0x180001fb3  mov     qword ptr [r11+18h], 0
0x180001fbb  mov     rsi, rcx
0x180001fbe  lea     rax, [r11+18h]
0x180001fc2  lea     rdx, CLSID_FileTypes; pclsid
0x180001fc9  mov     [r11-18h], rax
0x180001fcd  xor     ecx, ecx; pszCLSID
0x180001fcf  lea     r9, IID_IShellPropSheetExt; riid
0x180001fd6  xor     r8d, r8d; pUnkOuter
0x180001fd9  call    cs:__imp_SHCoCreateInstance
0x180001fe0  nop     dword ptr [rax+rax+00h]
0x180001fe5  mov     ebx, eax
0x180001fe7  test    eax, eax
0x180001fe9  js      short loc_180002015
0x180001feb  mov     rcx, [rsp+38h+arg_10]
0x180001ff0  mov     r8, rdi
0x180001ff3  mov     rdx, rsi
0x180001ff6  mov     rax, [rcx]
0x180001ff9  mov     rax, [rax+18h]
0x180001ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002002  mov     rcx, [rsp+38h+arg_10]
0x180002007  mov     ebx, eax
0x180002009  mov     rax, [rcx]
0x18000200c  mov     rax, [rax+10h]
0x180002010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002015  mov     rsi, [rsp+38h+arg_8]
0x18000201a  mov     eax, ebx
0x18000201c  mov     rbx, [rsp+38h+arg_0]
0x180002021  add     rsp, 30h
0x180002025  pop     rdi
0x180002026  retn
```
