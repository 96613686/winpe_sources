# CFirewall::AddAppException(ushort const *,ushort const *)

- ea: `0x180005be0`
- end: `0x180005e06`
- name: `?AddAppException@CFirewall@@QEAAJPEBG0@Z`
- size: `550`
- prototype: `int(CFirewall *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005be0`
- `0x180006070`
- `0x18000649c`
- `0x180007080`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005d9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005daf`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d9b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005daf`
- `OLE32!CoCreateInstance` at `0x180005ca4`
- `OLE32!CoCreateInstance` at `0x180005ca4`

## pseudocode

```c
__int64 __fastcall CFirewall::AddAppException(CFirewall *this, OLECHAR *a2, unsigned __int16 *a3)
{
  OLECHAR *v3; // rsi
  OLECHAR *v4; // rdi
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  BSTR v28; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  __int64 v30; // [rsp+40h] [rbp-10h] BYREF
  int v31; // [rsp+88h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF

  ppv = 0;
  v3 = 0;
  v31 = 0;
  v4 = 0;
  v30 = 0;
  bstrString = 0;
  v28 = 0;
  if ( a2 && a3 )
  {
    v8 = (unsigned int)CFirewall::AppExceptionExists(this, a3, &v31);
    if ( (int)ElValidateHr(v8, v9, v10, 408) < 0 )
      goto LABEL_19;
    if ( v31 )
      goto LABEL_19;
    v8 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 160LL))(
           *((_QWORD *)this + 1),
           &v30);
    if ( (int)ElValidateHr(v8, v11, v12, 420) < 0 )
      goto LABEL_19;
    v8 = (unsigned int)CoCreateInstance(
                         &GUID_ec9846b3_2762_4a6b_a214_6acb603462d2,
                         0,
                         1u,
                         &GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050,
                         &ppv);
    if ( (int)ElValidateHr(v8, v13, v14, 431) < 0 )
      goto LABEL_19;
    v8 = (unsigned int)SysAllocStringHr(a3, &bstrString);
    if ( (int)ElValidateHr(v8, v15, v16, 436) < 0 )
    {
      v4 = bstrString;
    }
    else
    {
      v8 = (unsigned int)SysAllocStringHr(a2, &v28);
      v19 = ElValidateHr(v8, v17, v18, 439);
      v4 = bstrString;
      if ( v19 < 0 )
      {
        v3 = v28;
      }
      else
      {
        v8 = (*(unsigned int (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 80LL))(ppv, bstrString);
        v22 = ElValidateHr(v8, v20, v21, 444);
        v3 = v28;
        if ( v22 >= 0 )
        {
          v8 = (*(unsigned int (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 64LL))(ppv, v28);
          if ( (int)ElValidateHr(v8, v23, v24, 449) >= 0 )
          {
            v8 = (*(unsigned int (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v30 + 64LL))(v30, ppv);
            ElValidateHr(v8, v25, v26, 454);
          }
        }
      }
    }
  }
  else
  {
    LODWORD(v8) = -2147024809;
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
    SysFreeString(v3);
LABEL_19:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005be0  mov     [rsp-28h+arg_0], rbx
0x180005be5  mov     [rsp-28h+arg_10], rsi
0x180005bea  push    rbp
0x180005beb  push    rdi
0x180005bec  push    r13
0x180005bee  push    r14
0x180005bf0  push    r15
0x180005bf2  mov     rbp, rsp
0x180005bf5  sub     rsp, 50h
0x180005bf9  and     [rbp+arg_18], 0
0x180005bfe  xor     esi, esi
0x180005c00  and     [rbp+arg_8], esi
0x180005c03  xor     edi, edi
0x180005c05  and     [rbp+var_10], 0
0x180005c0a  mov     r14, r8
0x180005c0d  mov     [rbp+bstrString], rdi
0x180005c11  mov     r15, rdx
0x180005c14  mov     [rbp+var_20], rsi
0x180005c18  mov     r13, rcx
0x180005c1b  test    rdx, rdx
0x180005c1e  jz      loc_180005D8E
0x180005c24  test    r8, r8
0x180005c27  jz      loc_180005D8E
0x180005c2d  lea     r8, [rbp+arg_8]; int *
0x180005c31  mov     rdx, r14; unsigned __int16 *
0x180005c34  call    ?AppExceptionExists@CFirewall@@QEAAJPEBGPEAH@Z; CFirewall::AppExceptionExists(ushort const *,int *)
0x180005c39  mov     r9d, 198h
0x180005c3f  mov     ecx, eax
0x180005c41  mov     ebx, eax
0x180005c43  call    ElValidateHr
0x180005c48  test    eax, eax
0x180005c4a  js      loc_180005DBB
0x180005c50  cmp     [rbp+arg_8], esi
0x180005c53  jnz     loc_180005DBB
0x180005c59  mov     rcx, [r13+8]
0x180005c5d  lea     rdx, [rbp+var_10]
0x180005c61  mov     rax, [rcx]
0x180005c64  mov     rax, [rax+0A0h]
0x180005c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c70  mov     r9d, 1A4h
0x180005c76  mov     ecx, eax
0x180005c78  mov     ebx, eax
0x180005c7a  call    ElValidateHr
0x180005c7f  test    eax, eax
0x180005c81  js      loc_180005DBB
0x180005c87  lea     rax, [rbp+arg_18]
0x180005c8b  xor     edx, edx; pUnkOuter
0x180005c8d  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x180005c94  mov     [rsp+50h+ppv], rax; ppv
0x180005c99  lea     r8d, [rdi+1]; dwClsContext
0x180005c9d  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x180005ca4  call    cs:__imp_CoCreateInstance
0x180005cab  nop     dword ptr [rax+rax+00h]
0x180005cb0  mov     ecx, eax
0x180005cb2  mov     r9d, 1AFh
0x180005cb8  mov     ebx, eax
0x180005cba  call    ElValidateHr
0x180005cbf  test    eax, eax
0x180005cc1  js      loc_180005DBB
0x180005cc7  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180005ccb  mov     rcx, r14; psz
0x180005cce  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180005cd3  mov     r9d, 1B4h
0x180005cd9  mov     ecx, eax
0x180005cdb  mov     ebx, eax
0x180005cdd  call    ElValidateHr
0x180005ce2  test    eax, eax
0x180005ce4  js      loc_180005D88
0x180005cea  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x180005cee  mov     rcx, r15; psz
0x180005cf1  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180005cf6  mov     r9d, 1B7h
0x180005cfc  mov     ecx, eax
0x180005cfe  mov     ebx, eax
0x180005d00  call    ElValidateHr
0x180005d05  mov     rdi, [rbp+bstrString]
0x180005d09  test    eax, eax
0x180005d0b  js      short loc_180005D82
0x180005d0d  mov     rcx, [rbp+arg_18]
0x180005d11  mov     rdx, rdi
0x180005d14  mov     rax, [rcx]
0x180005d17  mov     rax, [rax+50h]
0x180005d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d20  mov     r9d, 1BCh
0x180005d26  mov     ecx, eax
0x180005d28  mov     ebx, eax
0x180005d2a  call    ElValidateHr
0x180005d2f  mov     rsi, [rbp+var_20]
0x180005d33  test    eax, eax
0x180005d35  js      short loc_180005D93
0x180005d37  mov     rcx, [rbp+arg_18]
0x180005d3b  mov     rdx, rsi
0x180005d3e  mov     rax, [rcx]
0x180005d41  mov     rax, [rax+40h]
0x180005d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4a  mov     r9d, 1C1h
0x180005d50  mov     ecx, eax
0x180005d52  mov     ebx, eax
0x180005d54  call    ElValidateHr
0x180005d59  test    eax, eax
0x180005d5b  js      short loc_180005D93
0x180005d5d  mov     rcx, [rbp+var_10]
0x180005d61  mov     rdx, [rbp+arg_18]
0x180005d65  mov     rax, [rcx]
0x180005d68  mov     rax, [rax+40h]
0x180005d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d71  mov     r9d, 1C6h
0x180005d77  mov     ecx, eax
0x180005d79  mov     ebx, eax
0x180005d7b  call    ElValidateHr
0x180005d80  jmp     short loc_180005D93
0x180005d82  mov     rsi, [rbp+var_20]
0x180005d86  jmp     short loc_180005D93
0x180005d88  mov     rdi, [rbp+bstrString]
0x180005d8c  jmp     short loc_180005D93
0x180005d8e  mov     ebx, 80070057h
0x180005d93  test    rdi, rdi
0x180005d96  jz      short loc_180005DA7
0x180005d98  mov     rcx, rdi; bstrString
0x180005d9b  call    cs:__imp_SysFreeString
0x180005da2  nop     dword ptr [rax+rax+00h]
0x180005da7  test    rsi, rsi
0x180005daa  jz      short loc_180005DBB
0x180005dac  mov     rcx, rsi; bstrString
0x180005daf  call    cs:__imp_SysFreeString
0x180005db6  nop     dword ptr [rax+rax+00h]
0x180005dbb  mov     rcx, [rbp+arg_18]
0x180005dbf  test    rcx, rcx
0x180005dc2  jz      short loc_180005DD5
0x180005dc4  mov     rax, [rcx]
0x180005dc7  mov     rax, [rax+10h]
0x180005dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd0  and     [rbp+arg_18], 0
0x180005dd5  mov     rcx, [rbp+var_10]
0x180005dd9  test    rcx, rcx
0x180005ddc  jz      short loc_180005DEA
0x180005dde  mov     rax, [rcx]
0x180005de1  mov     rax, [rax+10h]
0x180005de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dea  lea     r11, [rsp+50h+var_s0]
0x180005def  mov     eax, ebx
0x180005df1  mov     rbx, [r11+30h]
0x180005df5  mov     rsi, [r11+40h]
0x180005df9  mov     rsp, r11
0x180005dfc  pop     r15
0x180005dfe  pop     r14
0x180005e00  pop     r13
0x180005e02  pop     rdi
0x180005e03  pop     rbp
0x180005e04  retn
```
