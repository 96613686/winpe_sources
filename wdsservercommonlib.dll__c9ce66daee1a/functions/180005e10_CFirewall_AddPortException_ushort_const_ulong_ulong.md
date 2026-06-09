# CFirewall::AddPortException(ushort const *,ulong,ulong)

- ea: `0x180005e10`
- end: `0x180006069`
- name: `?AddPortException@CFirewall@@QEAAJPEBGKK@Z`
- size: `601`
- prototype: `int(CFirewall *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005e10`
- `0x18000649c`
- `0x180007080`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006018`
- `OLEAUT32!__imp_SysFreeString` at `0x180006018`
- `OLE32!CoCreateInstance` at `0x180005f42`
- `OLE32!CoCreateInstance` at `0x180005f42`

## pseudocode

```c
__int64 __fastcall CFirewall::AddPortException(CFirewall *this, OLECHAR *a2, unsigned int a3, int a4)
{
  OLECHAR *v4; // rdi
  unsigned int v7; // edi
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  __int64 v29; // [rsp+38h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+28h] BYREF

  v4 = 0;
  ppv = 0;
  v29 = 0;
  bstrString = 0;
  if ( !a2 || !a3 )
  {
    LODWORD(v8) = -2147024809;
    goto LABEL_21;
  }
  if ( a4 == 1 )
  {
    v7 = 17;
  }
  else
  {
    if ( a4 != 2 )
    {
      LODWORD(v8) = -2147024809;
      return (unsigned int)v8;
    }
    v7 = 6;
  }
  v8 = (unsigned int)SysAllocStringHr(a2, &bstrString);
  if ( (int)ElValidateHr(v8, v9, v10, 153) < 0 )
    goto LABEL_18;
  v8 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 144LL))(
         *((_QWORD *)this + 1),
         &v29);
  if ( (int)ElValidateHr(v8, v11, v12, 158) < 0 )
    goto LABEL_18;
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID *))(*(_QWORD *)v29 + 80LL))(v29, a3, v7, &ppv) >= 0 )
  {
    v4 = bstrString;
    v8 = (*(unsigned int (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 64LL))(ppv, bstrString);
    if ( (int)ElValidateHr(v8, v13, v14, 168) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, 0xFFFFFFFFLL);
      v18 = 173;
LABEL_17:
      LODWORD(v8) = v15;
      ElValidateHr(v15, v16, v17, v18);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  v8 = (unsigned int)CoCreateInstance(
                       &GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5,
                       0,
                       1u,
                       &GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7,
                       &ppv);
  if ( (int)ElValidateHr(v8, v19, v20, 186) < 0
    || (v8 = (*(unsigned int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, a3),
        (int)ElValidateHr(v8, v21, v22, 190) < 0)
    || (v8 = (*(unsigned int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, v7),
        (int)ElValidateHr(v8, v23, v24, 195) < 0) )
  {
LABEL_18:
    v4 = bstrString;
    goto LABEL_21;
  }
  v4 = bstrString;
  v8 = (*(unsigned int (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 64LL))(ppv, bstrString);
  if ( (int)ElValidateHr(v8, v25, v26, 200) >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v29 + 64LL))(v29, ppv);
    v18 = 205;
    goto LABEL_17;
  }
LABEL_21:
  if ( v4 )
    SysFreeString(v4);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005e10  mov     [rsp-18h+arg_0], rbx
0x180005e15  mov     [rsp-18h+arg_10], rsi
0x180005e1a  push    rbp
0x180005e1b  push    rdi
0x180005e1c  push    r14
0x180005e1e  mov     rbp, rsp
0x180005e21  sub     rsp, 40h
0x180005e25  xor     edi, edi
0x180005e27  mov     esi, r8d
0x180005e2a  and     [rbp+arg_8], rdi
0x180005e2e  mov     rax, rdx
0x180005e31  and     [rbp+var_8], rdi
0x180005e35  mov     r14, rcx
0x180005e38  mov     [rbp+bstrString], rdi
0x180005e3c  test    rdx, rdx
0x180005e3f  jz      loc_18000600B
0x180005e45  test    r8d, r8d
0x180005e48  jz      loc_18000600B
0x180005e4e  cmp     r9d, 1
0x180005e52  jnz     short loc_180005E5A
0x180005e54  lea     edi, [r9+10h]
0x180005e58  jmp     short loc_180005E68
0x180005e5a  cmp     r9d, 2
0x180005e5e  jnz     loc_180006004
0x180005e64  lea     edi, [r9+4]
0x180005e68  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180005e6c  mov     rcx, rax; psz
0x180005e6f  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180005e74  mov     r9d, 99h
0x180005e7a  mov     ecx, eax
0x180005e7c  mov     ebx, eax
0x180005e7e  call    ElValidateHr
0x180005e83  test    eax, eax
0x180005e85  js      loc_180005FFE
0x180005e8b  mov     rcx, [r14+8]
0x180005e8f  lea     rdx, [rbp+var_8]
0x180005e93  mov     rax, [rcx]
0x180005e96  mov     rax, [rax+90h]
0x180005e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea2  mov     r9d, 9Eh
0x180005ea8  mov     ecx, eax
0x180005eaa  mov     ebx, eax
0x180005eac  call    ElValidateHr
0x180005eb1  test    eax, eax
0x180005eb3  js      loc_180005FFE
0x180005eb9  mov     rcx, [rbp+var_8]
0x180005ebd  lea     r9, [rbp+arg_8]
0x180005ec1  mov     r8d, edi
0x180005ec4  mov     edx, esi
0x180005ec6  mov     rax, [rcx]
0x180005ec9  mov     rax, [rax+50h]
0x180005ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed2  test    eax, eax
0x180005ed4  js      short loc_180005F25
0x180005ed6  mov     rcx, [rbp+arg_8]
0x180005eda  mov     rdi, [rbp+bstrString]
0x180005ede  mov     rdx, rdi
0x180005ee1  mov     rax, [rcx]
0x180005ee4  mov     rax, [rax+40h]
0x180005ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eed  mov     r9d, 0A8h
0x180005ef3  mov     ecx, eax
0x180005ef5  mov     ebx, eax
0x180005ef7  call    ElValidateHr
0x180005efc  test    eax, eax
0x180005efe  js      loc_180006010
0x180005f04  mov     rcx, [rbp+arg_8]
0x180005f08  or      edx, 0FFFFFFFFh
0x180005f0b  mov     rax, [rcx]
0x180005f0e  mov     rax, [rax+0A0h]
0x180005f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f1a  mov     r9d, 0ADh
0x180005f20  jmp     loc_180005FF3
0x180005f25  xor     edx, edx; pUnkOuter
0x180005f27  lea     rax, [rbp+arg_8]
0x180005f2b  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x180005f32  mov     [rsp+40h+ppv], rax; ppv
0x180005f37  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x180005f3e  lea     r8d, [rdx+1]; dwClsContext
0x180005f42  call    cs:__imp_CoCreateInstance
0x180005f49  nop     dword ptr [rax+rax+00h]
0x180005f4e  mov     ecx, eax
0x180005f50  mov     r9d, 0BAh
0x180005f56  mov     ebx, eax
0x180005f58  call    ElValidateHr
0x180005f5d  test    eax, eax
0x180005f5f  js      loc_180005FFE
0x180005f65  mov     rcx, [rbp+arg_8]
0x180005f69  mov     edx, esi
0x180005f6b  mov     rax, [rcx]
0x180005f6e  mov     rax, [rax+70h]
0x180005f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f77  mov     r9d, 0BEh
0x180005f7d  mov     ecx, eax
0x180005f7f  mov     ebx, eax
0x180005f81  call    ElValidateHr
0x180005f86  test    eax, eax
0x180005f88  js      short loc_180005FFE
0x180005f8a  mov     rcx, [rbp+arg_8]
0x180005f8e  mov     edx, edi
0x180005f90  mov     rax, [rcx]
0x180005f93  mov     rax, [rax+60h]
0x180005f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9c  mov     r9d, 0C3h
0x180005fa2  mov     ecx, eax
0x180005fa4  mov     ebx, eax
0x180005fa6  call    ElValidateHr
0x180005fab  test    eax, eax
0x180005fad  js      short loc_180005FFE
0x180005faf  mov     rcx, [rbp+arg_8]
0x180005fb3  mov     rdi, [rbp+bstrString]
0x180005fb7  mov     rdx, rdi
0x180005fba  mov     rax, [rcx]
0x180005fbd  mov     rax, [rax+40h]
0x180005fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc6  mov     r9d, 0C8h
0x180005fcc  mov     ecx, eax
0x180005fce  mov     ebx, eax
0x180005fd0  call    ElValidateHr
0x180005fd5  test    eax, eax
0x180005fd7  js      short loc_180006010
0x180005fd9  mov     rcx, [rbp+var_8]
0x180005fdd  mov     rdx, [rbp+arg_8]
0x180005fe1  mov     rax, [rcx]
0x180005fe4  mov     rax, [rax+40h]
0x180005fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fed  mov     r9d, 0CDh
0x180005ff3  mov     ecx, eax
0x180005ff5  mov     ebx, eax
0x180005ff7  call    ElValidateHr
0x180005ffc  jmp     short loc_180006010
0x180005ffe  mov     rdi, [rbp+bstrString]
0x180006002  jmp     short loc_180006010
0x180006004  mov     ebx, 80070057h
0x180006009  jmp     short loc_180006053
0x18000600b  mov     ebx, 80070057h
0x180006010  test    rdi, rdi
0x180006013  jz      short loc_180006024
0x180006015  mov     rcx, rdi; bstrString
0x180006018  call    cs:__imp_SysFreeString
0x18000601f  nop     dword ptr [rax+rax+00h]
0x180006024  mov     rcx, [rbp+arg_8]
0x180006028  test    rcx, rcx
0x18000602b  jz      short loc_18000603E
0x18000602d  mov     rax, [rcx]
0x180006030  mov     rax, [rax+10h]
0x180006034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006039  and     [rbp+arg_8], 0
0x18000603e  mov     rcx, [rbp+var_8]
0x180006042  test    rcx, rcx
0x180006045  jz      short loc_180006053
0x180006047  mov     rax, [rcx]
0x18000604a  mov     rax, [rax+10h]
0x18000604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006053  mov     rsi, [rsp+40h+arg_10]
0x180006058  mov     eax, ebx
0x18000605a  mov     rbx, [rsp+40h+arg_0]
0x18000605f  add     rsp, 40h
0x180006063  pop     r14
0x180006065  pop     rdi
0x180006066  pop     rbp
0x180006067  retn
```
