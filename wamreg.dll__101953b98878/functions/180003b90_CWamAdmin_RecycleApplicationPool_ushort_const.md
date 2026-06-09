# CWamAdmin::RecycleApplicationPool(ushort const *)

- ea: `0x180003b90`
- end: `0x180003c39`
- name: `?RecycleApplicationPool@CWamAdmin@@UEAAJPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003b90`
- `0x1800041d4`
- `0x180007010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003be9`
- `ole32!CoCreateInstance` at `0x180003be9`

## pseudocode

```c
__int64 __fastcall CWamAdmin::RecycleApplicationPool(CWamAdmin *this, const unsigned __int16 *a2)
{
  int v3; // ebx
  HRESULT v4; // eax
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  if ( a2 )
  {
    v3 = ValidateAccessToAppPool(a2);
    if ( v3 >= 0 )
    {
      ppv = 0;
      v4 = CoCreateInstance(&CLSID_W3Control, 0, 0x4017u, &IID_IW3Control, &ppv);
      v3 = 0;
      if ( v4 < 0 )
        v3 = v4;
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, a2);
        if ( v3 >= 0 )
          v3 = 0;
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_0], rbx
0x180003b95  push    rdi
0x180003b96  sub     rsp, 30h
0x180003b9a  mov     [rsp+38h+arg_8], 0
0x180003ba3  mov     rdi, rdx
0x180003ba6  test    rdx, rdx
0x180003ba9  jnz     short loc_180003BB2
0x180003bab  mov     ebx, 80070057h
0x180003bb0  jmp     short loc_180003C2C
0x180003bb2  mov     rcx, rdi; unsigned __int16 *
0x180003bb5  call    ?ValidateAccessToAppPool@@YAJPEBG@Z; ValidateAccessToAppPool(ushort const *)
0x180003bba  mov     ebx, eax
0x180003bbc  test    eax, eax
0x180003bbe  js      short loc_180003C16
0x180003bc0  lea     rax, [rsp+38h+arg_8]
0x180003bc5  mov     [rsp+38h+arg_8], 0
0x180003bce  lea     r9, IID_IW3Control; riid
0x180003bd5  mov     [rsp+38h+ppv], rax; ppv
0x180003bda  xor     edx, edx; pUnkOuter
0x180003bdc  lea     rcx, CLSID_W3Control; rclsid
0x180003be3  mov     r8d, 4017h; dwClsContext
0x180003be9  call    cs:__imp_CoCreateInstance
0x180003bef  xor     ebx, ebx
0x180003bf1  test    eax, eax
0x180003bf3  cmovs   ebx, eax
0x180003bf6  test    ebx, ebx
0x180003bf8  js      short loc_180003C16
0x180003bfa  mov     rcx, [rsp+38h+arg_8]
0x180003bff  mov     rdx, rdi
0x180003c02  mov     rax, [rcx]
0x180003c05  mov     rax, [rax+18h]
0x180003c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0e  mov     ebx, eax
0x180003c10  test    eax, eax
0x180003c12  js      short loc_180003C16
0x180003c14  xor     ebx, ebx
0x180003c16  mov     rcx, [rsp+38h+arg_8]
0x180003c1b  test    rcx, rcx
0x180003c1e  jz      short loc_180003C2C
0x180003c20  mov     rax, [rcx]
0x180003c23  mov     rax, [rax+10h]
0x180003c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2c  mov     eax, ebx
0x180003c2e  mov     rbx, [rsp+38h+arg_0]
0x180003c33  add     rsp, 30h
0x180003c37  pop     rdi
0x180003c38  retn
```
