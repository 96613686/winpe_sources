# CFirewall::AddPortException(ushort const *,ulong,ulong)

- ea: `0x1800068f0`
- end: `0x180006b49`
- name: `?AddPortException@CFirewall@@QEAAJPEBGKK@Z`
- size: `601`
- prototype: `int(CFirewall *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800068f0`
- `0x180006f7c`
- `0x180007bb0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180006af8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006af8`
- `OLE32!CoCreateInstance` at `0x180006a22`
- `OLE32!CoCreateInstance` at `0x180006a22`

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
0x1800068f0  mov     [rsp-18h+arg_0], rbx
0x1800068f5  mov     [rsp-18h+arg_10], rsi
0x1800068fa  push    rbp
0x1800068fb  push    rdi
0x1800068fc  push    r14
0x1800068fe  mov     rbp, rsp
0x180006901  sub     rsp, 40h
0x180006905  xor     edi, edi
0x180006907  mov     esi, r8d
0x18000690a  and     [rbp+arg_8], rdi
0x18000690e  mov     rax, rdx
0x180006911  and     [rbp+var_8], rdi
0x180006915  mov     r14, rcx
0x180006918  mov     [rbp+bstrString], rdi
0x18000691c  test    rdx, rdx
0x18000691f  jz      loc_180006AEB
0x180006925  test    r8d, r8d
0x180006928  jz      loc_180006AEB
0x18000692e  cmp     r9d, 1
0x180006932  jnz     short loc_18000693A
0x180006934  lea     edi, [r9+10h]
0x180006938  jmp     short loc_180006948
0x18000693a  cmp     r9d, 2
0x18000693e  jnz     loc_180006AE4
0x180006944  lea     edi, [r9+4]
0x180006948  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x18000694c  mov     rcx, rax; psz
0x18000694f  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180006954  mov     r9d, 99h
0x18000695a  mov     ecx, eax
0x18000695c  mov     ebx, eax
0x18000695e  call    ElValidateHr
0x180006963  test    eax, eax
0x180006965  js      loc_180006ADE
0x18000696b  mov     rcx, [r14+8]
0x18000696f  lea     rdx, [rbp+var_8]
0x180006973  mov     rax, [rcx]
0x180006976  mov     rax, [rax+90h]
0x18000697d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006982  mov     r9d, 9Eh
0x180006988  mov     ecx, eax
0x18000698a  mov     ebx, eax
0x18000698c  call    ElValidateHr
0x180006991  test    eax, eax
0x180006993  js      loc_180006ADE
0x180006999  mov     rcx, [rbp+var_8]
0x18000699d  lea     r9, [rbp+arg_8]
0x1800069a1  mov     r8d, edi
0x1800069a4  mov     edx, esi
0x1800069a6  mov     rax, [rcx]
0x1800069a9  mov     rax, [rax+50h]
0x1800069ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b2  test    eax, eax
0x1800069b4  js      short loc_180006A05
0x1800069b6  mov     rcx, [rbp+arg_8]
0x1800069ba  mov     rdi, [rbp+bstrString]
0x1800069be  mov     rdx, rdi
0x1800069c1  mov     rax, [rcx]
0x1800069c4  mov     rax, [rax+40h]
0x1800069c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069cd  mov     r9d, 0A8h
0x1800069d3  mov     ecx, eax
0x1800069d5  mov     ebx, eax
0x1800069d7  call    ElValidateHr
0x1800069dc  test    eax, eax
0x1800069de  js      loc_180006AF0
0x1800069e4  mov     rcx, [rbp+arg_8]
0x1800069e8  or      edx, 0FFFFFFFFh
0x1800069eb  mov     rax, [rcx]
0x1800069ee  mov     rax, [rax+0A0h]
0x1800069f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069fa  mov     r9d, 0ADh
0x180006a00  jmp     loc_180006AD3
0x180006a05  xor     edx, edx; pUnkOuter
0x180006a07  lea     rax, [rbp+arg_8]
0x180006a0b  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x180006a12  mov     [rsp+40h+ppv], rax; ppv
0x180006a17  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x180006a1e  lea     r8d, [rdx+1]; dwClsContext
0x180006a22  call    cs:__imp_CoCreateInstance
0x180006a29  nop     dword ptr [rax+rax+00h]
0x180006a2e  mov     ecx, eax
0x180006a30  mov     r9d, 0BAh
0x180006a36  mov     ebx, eax
0x180006a38  call    ElValidateHr
0x180006a3d  test    eax, eax
0x180006a3f  js      loc_180006ADE
0x180006a45  mov     rcx, [rbp+arg_8]
0x180006a49  mov     edx, esi
0x180006a4b  mov     rax, [rcx]
0x180006a4e  mov     rax, [rax+70h]
0x180006a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a57  mov     r9d, 0BEh
0x180006a5d  mov     ecx, eax
0x180006a5f  mov     ebx, eax
0x180006a61  call    ElValidateHr
0x180006a66  test    eax, eax
0x180006a68  js      short loc_180006ADE
0x180006a6a  mov     rcx, [rbp+arg_8]
0x180006a6e  mov     edx, edi
0x180006a70  mov     rax, [rcx]
0x180006a73  mov     rax, [rax+60h]
0x180006a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7c  mov     r9d, 0C3h
0x180006a82  mov     ecx, eax
0x180006a84  mov     ebx, eax
0x180006a86  call    ElValidateHr
0x180006a8b  test    eax, eax
0x180006a8d  js      short loc_180006ADE
0x180006a8f  mov     rcx, [rbp+arg_8]
0x180006a93  mov     rdi, [rbp+bstrString]
0x180006a97  mov     rdx, rdi
0x180006a9a  mov     rax, [rcx]
0x180006a9d  mov     rax, [rax+40h]
0x180006aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa6  mov     r9d, 0C8h
0x180006aac  mov     ecx, eax
0x180006aae  mov     ebx, eax
0x180006ab0  call    ElValidateHr
0x180006ab5  test    eax, eax
0x180006ab7  js      short loc_180006AF0
0x180006ab9  mov     rcx, [rbp+var_8]
0x180006abd  mov     rdx, [rbp+arg_8]
0x180006ac1  mov     rax, [rcx]
0x180006ac4  mov     rax, [rax+40h]
0x180006ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006acd  mov     r9d, 0CDh
0x180006ad3  mov     ecx, eax
0x180006ad5  mov     ebx, eax
0x180006ad7  call    ElValidateHr
0x180006adc  jmp     short loc_180006AF0
0x180006ade  mov     rdi, [rbp+bstrString]
0x180006ae2  jmp     short loc_180006AF0
0x180006ae4  mov     ebx, 80070057h
0x180006ae9  jmp     short loc_180006B33
0x180006aeb  mov     ebx, 80070057h
0x180006af0  test    rdi, rdi
0x180006af3  jz      short loc_180006B04
0x180006af5  mov     rcx, rdi; bstrString
0x180006af8  call    cs:__imp_SysFreeString
0x180006aff  nop     dword ptr [rax+rax+00h]
0x180006b04  mov     rcx, [rbp+arg_8]
0x180006b08  test    rcx, rcx
0x180006b0b  jz      short loc_180006B1E
0x180006b0d  mov     rax, [rcx]
0x180006b10  mov     rax, [rax+10h]
0x180006b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b19  and     [rbp+arg_8], 0
0x180006b1e  mov     rcx, [rbp+var_8]
0x180006b22  test    rcx, rcx
0x180006b25  jz      short loc_180006B33
0x180006b27  mov     rax, [rcx]
0x180006b2a  mov     rax, [rax+10h]
0x180006b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b33  mov     rsi, [rsp+40h+arg_10]
0x180006b38  mov     eax, ebx
0x180006b3a  mov     rbx, [rsp+40h+arg_0]
0x180006b3f  add     rsp, 40h
0x180006b43  pop     r14
0x180006b45  pop     rdi
0x180006b46  pop     rbp
0x180006b47  retn
```
