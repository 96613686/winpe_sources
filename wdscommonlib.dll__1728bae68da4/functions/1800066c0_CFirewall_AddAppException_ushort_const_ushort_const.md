# CFirewall::AddAppException(ushort const *,ushort const *)

- ea: `0x1800066c0`
- end: `0x1800068e6`
- name: `?AddAppException@CFirewall@@QEAAJPEBG0@Z`
- size: `550`
- prototype: `int(CFirewall *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800066c0`
- `0x180006b50`
- `0x180006f7c`
- `0x180007bb0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000687b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000688f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000687b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000688f`
- `OLE32!CoCreateInstance` at `0x180006784`
- `OLE32!CoCreateInstance` at `0x180006784`

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
0x1800066c0  mov     [rsp-28h+arg_0], rbx
0x1800066c5  mov     [rsp-28h+arg_10], rsi
0x1800066ca  push    rbp
0x1800066cb  push    rdi
0x1800066cc  push    r13
0x1800066ce  push    r14
0x1800066d0  push    r15
0x1800066d2  mov     rbp, rsp
0x1800066d5  sub     rsp, 50h
0x1800066d9  and     [rbp+arg_18], 0
0x1800066de  xor     esi, esi
0x1800066e0  and     [rbp+arg_8], esi
0x1800066e3  xor     edi, edi
0x1800066e5  and     [rbp+var_10], 0
0x1800066ea  mov     r14, r8
0x1800066ed  mov     [rbp+bstrString], rdi
0x1800066f1  mov     r15, rdx
0x1800066f4  mov     [rbp+var_20], rsi
0x1800066f8  mov     r13, rcx
0x1800066fb  test    rdx, rdx
0x1800066fe  jz      loc_18000686E
0x180006704  test    r8, r8
0x180006707  jz      loc_18000686E
0x18000670d  lea     r8, [rbp+arg_8]; int *
0x180006711  mov     rdx, r14; unsigned __int16 *
0x180006714  call    ?AppExceptionExists@CFirewall@@QEAAJPEBGPEAH@Z; CFirewall::AppExceptionExists(ushort const *,int *)
0x180006719  mov     r9d, 198h
0x18000671f  mov     ecx, eax
0x180006721  mov     ebx, eax
0x180006723  call    ElValidateHr
0x180006728  test    eax, eax
0x18000672a  js      loc_18000689B
0x180006730  cmp     [rbp+arg_8], esi
0x180006733  jnz     loc_18000689B
0x180006739  mov     rcx, [r13+8]
0x18000673d  lea     rdx, [rbp+var_10]
0x180006741  mov     rax, [rcx]
0x180006744  mov     rax, [rax+0A0h]
0x18000674b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006750  mov     r9d, 1A4h
0x180006756  mov     ecx, eax
0x180006758  mov     ebx, eax
0x18000675a  call    ElValidateHr
0x18000675f  test    eax, eax
0x180006761  js      loc_18000689B
0x180006767  lea     rax, [rbp+arg_18]
0x18000676b  xor     edx, edx; pUnkOuter
0x18000676d  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x180006774  mov     [rsp+50h+ppv], rax; ppv
0x180006779  lea     r8d, [rdi+1]; dwClsContext
0x18000677d  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x180006784  call    cs:__imp_CoCreateInstance
0x18000678b  nop     dword ptr [rax+rax+00h]
0x180006790  mov     ecx, eax
0x180006792  mov     r9d, 1AFh
0x180006798  mov     ebx, eax
0x18000679a  call    ElValidateHr
0x18000679f  test    eax, eax
0x1800067a1  js      loc_18000689B
0x1800067a7  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x1800067ab  mov     rcx, r14; psz
0x1800067ae  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800067b3  mov     r9d, 1B4h
0x1800067b9  mov     ecx, eax
0x1800067bb  mov     ebx, eax
0x1800067bd  call    ElValidateHr
0x1800067c2  test    eax, eax
0x1800067c4  js      loc_180006868
0x1800067ca  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x1800067ce  mov     rcx, r15; psz
0x1800067d1  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800067d6  mov     r9d, 1B7h
0x1800067dc  mov     ecx, eax
0x1800067de  mov     ebx, eax
0x1800067e0  call    ElValidateHr
0x1800067e5  mov     rdi, [rbp+bstrString]
0x1800067e9  test    eax, eax
0x1800067eb  js      short loc_180006862
0x1800067ed  mov     rcx, [rbp+arg_18]
0x1800067f1  mov     rdx, rdi
0x1800067f4  mov     rax, [rcx]
0x1800067f7  mov     rax, [rax+50h]
0x1800067fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006800  mov     r9d, 1BCh
0x180006806  mov     ecx, eax
0x180006808  mov     ebx, eax
0x18000680a  call    ElValidateHr
0x18000680f  mov     rsi, [rbp+var_20]
0x180006813  test    eax, eax
0x180006815  js      short loc_180006873
0x180006817  mov     rcx, [rbp+arg_18]
0x18000681b  mov     rdx, rsi
0x18000681e  mov     rax, [rcx]
0x180006821  mov     rax, [rax+40h]
0x180006825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682a  mov     r9d, 1C1h
0x180006830  mov     ecx, eax
0x180006832  mov     ebx, eax
0x180006834  call    ElValidateHr
0x180006839  test    eax, eax
0x18000683b  js      short loc_180006873
0x18000683d  mov     rcx, [rbp+var_10]
0x180006841  mov     rdx, [rbp+arg_18]
0x180006845  mov     rax, [rcx]
0x180006848  mov     rax, [rax+40h]
0x18000684c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006851  mov     r9d, 1C6h
0x180006857  mov     ecx, eax
0x180006859  mov     ebx, eax
0x18000685b  call    ElValidateHr
0x180006860  jmp     short loc_180006873
0x180006862  mov     rsi, [rbp+var_20]
0x180006866  jmp     short loc_180006873
0x180006868  mov     rdi, [rbp+bstrString]
0x18000686c  jmp     short loc_180006873
0x18000686e  mov     ebx, 80070057h
0x180006873  test    rdi, rdi
0x180006876  jz      short loc_180006887
0x180006878  mov     rcx, rdi; bstrString
0x18000687b  call    cs:__imp_SysFreeString
0x180006882  nop     dword ptr [rax+rax+00h]
0x180006887  test    rsi, rsi
0x18000688a  jz      short loc_18000689B
0x18000688c  mov     rcx, rsi; bstrString
0x18000688f  call    cs:__imp_SysFreeString
0x180006896  nop     dword ptr [rax+rax+00h]
0x18000689b  mov     rcx, [rbp+arg_18]
0x18000689f  test    rcx, rcx
0x1800068a2  jz      short loc_1800068B5
0x1800068a4  mov     rax, [rcx]
0x1800068a7  mov     rax, [rax+10h]
0x1800068ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b0  and     [rbp+arg_18], 0
0x1800068b5  mov     rcx, [rbp+var_10]
0x1800068b9  test    rcx, rcx
0x1800068bc  jz      short loc_1800068CA
0x1800068be  mov     rax, [rcx]
0x1800068c1  mov     rax, [rax+10h]
0x1800068c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ca  lea     r11, [rsp+50h+var_s0]
0x1800068cf  mov     eax, ebx
0x1800068d1  mov     rbx, [r11+30h]
0x1800068d5  mov     rsi, [r11+40h]
0x1800068d9  mov     rsp, r11
0x1800068dc  pop     r15
0x1800068de  pop     r14
0x1800068e0  pop     r13
0x1800068e2  pop     rdi
0x1800068e3  pop     rbp
0x1800068e4  retn
```
