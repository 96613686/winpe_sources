# CSFPIntegrityCheckAndRepair::SFPCheckAllComponents(__MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *,int,ushort *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ISFPRebootCallback *,ISFPProgressCallback *)

- ea: `0x1800064f0`
- end: `0x180006652`
- name: `?SFPCheckAllComponents@CSFPIntegrityCheckAndRepair@@UEAAJPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0001@@HPEAGPEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAUISFPRebootCallback@@PEAUISFPProgressCallback@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, int, unsigned __int16 *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, struct ISFPRebootCallback *, struct ISFPProgressCallback *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800064f0`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::SFPCheckAllComponents(
        CSFPIntegrityCheckAndRepair *this,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *a2,
        int a3,
        unsigned __int16 *a4,
        int *a5,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a6,
        struct ISFPRebootCallback *a7,
        struct ISFPProgressCallback *a8)
{
  int v8; // edi
  int v11; // ebx
  int v12; // eax
  int v14; // [rsp+60h] [rbp-48h] BYREF
  int v15; // [rsp+64h] [rbp-44h]

  v8 = 1;
  v14 = 1;
  v15 = 1;
  if ( a6 && a5 )
  {
    *(_QWORD *)a6 = 0;
    *((_QWORD *)a6 + 1) = 0;
    *((_DWORD *)a6 + 4) = 0;
    *a5 = 0;
    v11 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, __int64, _QWORD, int, unsigned __int16 *, struct ISFPRebootCallback *, struct ISFPProgressCallback *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, int *))(*(_QWORD *)this + 80LL))(
            this,
            a2,
            1,
            0,
            a3,
            a4,
            a7,
            a8,
            a5,
            a6,
            &v14);
    if ( a2 )
    {
      v8 = v14;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, _QWORD, __int64))(*(_QWORD *)this + 80LL))(
              this,
              0,
              2);
      if ( v14 == 2 || v15 == 2 )
        v8 = 2;
      if ( v11 < 0 )
        return (unsigned int)v11;
      v11 = v12;
    }
    if ( v11 >= 0 && v8 == 2 )
      return (unsigned int)-2147010815;
    return (unsigned int)v11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800064f0  mov     r11, rsp
0x1800064f3  push    rbx
0x1800064f4  push    rbp
0x1800064f5  push    rsi
0x1800064f6  push    rdi
0x1800064f7  push    r12
0x1800064f9  push    r14
0x1800064fb  push    r15
0x1800064fd  sub     rsp, 70h
0x180006501  mov     rax, cs:__security_cookie
0x180006508  xor     rax, rsp
0x18000650b  mov     [rsp+0A8h+var_40], rax
0x180006510  mov     rsi, [rsp+0A8h+arg_28]
0x180006518  mov     edi, 1
0x18000651d  mov     r14, [rsp+0A8h+arg_20]
0x180006525  mov     r12, rdx
0x180006528  mov     rdx, [rsp+0A8h+arg_38]
0x180006530  mov     r15, rcx
0x180006533  mov     rcx, [rsp+0A8h+arg_30]
0x18000653b  mov     ebp, r8d
0x18000653e  mov     [rsp+0A8h+var_48], edi
0x180006542  mov     [rsp+0A8h+var_44], edi
0x180006546  test    rsi, rsi
0x180006549  jz      loc_180006631
0x18000654f  test    r14, r14
0x180006552  jz      loc_180006631
0x180006558  lea     r8, [r11-48h]
0x18000655c  mov     qword ptr [rsi], 0
0x180006563  mov     [r11-58h], r8
0x180006567  mov     r8d, edi
0x18000656a  mov     [r11-60h], rsi
0x18000656e  mov     [r11-68h], r14
0x180006572  mov     [r11-70h], rdx
0x180006576  mov     rdx, r12
0x180006579  mov     [r11-78h], rcx
0x18000657d  mov     rcx, r15
0x180006580  mov     qword ptr [rsi+8], 0
0x180006588  mov     dword ptr [rsi+10h], 0
0x18000658f  mov     [r11-80h], r9
0x180006593  xor     r9d, r9d
0x180006596  mov     dword ptr [r14], 0
0x18000659d  mov     rax, [r15]
0x1800065a0  mov     [rsp+0A8h+var_88], ebp
0x1800065a4  mov     rax, [rax+50h]
0x1800065a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ad  mov     ebx, eax
0x1800065af  test    r12, r12
0x1800065b2  jz      short loc_1800065BA
0x1800065b4  mov     edi, [rsp+0A8h+var_48]
0x1800065b8  jmp     short loc_18000661E
0x1800065ba  mov     rax, [r15]
0x1800065bd  lea     rcx, [rsp+0A8h+var_44]
0x1800065c2  mov     [rsp+0A8h+var_58], rcx
0x1800065c7  xor     r9d, r9d
0x1800065ca  mov     [rsp+0A8h+var_60], rsi
0x1800065cf  xor     edx, edx
0x1800065d1  mov     [rsp+0A8h+var_68], r14
0x1800065d6  mov     rcx, r15
0x1800065d9  mov     rax, [rax+50h]
0x1800065dd  mov     [rsp+0A8h+var_70], 0
0x1800065e6  lea     r8d, [r9+2]
0x1800065ea  mov     [rsp+0A8h+var_78], 0
0x1800065f3  mov     [rsp+0A8h+var_80], 0
0x1800065fc  mov     [rsp+0A8h+var_88], ebp
0x180006600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006605  cmp     [rsp+0A8h+var_48], 2
0x18000660a  jz      short loc_180006613
0x18000660c  cmp     [rsp+0A8h+var_44], 2
0x180006611  jnz     short loc_180006618
0x180006613  mov     edi, 2
0x180006618  test    ebx, ebx
0x18000661a  js      short loc_18000662D
0x18000661c  mov     ebx, eax
0x18000661e  test    ebx, ebx
0x180006620  js      short loc_18000662D
0x180006622  cmp     edi, 2
0x180006625  mov     eax, 80073701h
0x18000662a  cmovz   ebx, eax
0x18000662d  mov     eax, ebx
0x18000662f  jmp     short loc_180006636
0x180006631  mov     eax, 80070057h
0x180006636  mov     rcx, [rsp+0A8h+var_40]
0x18000663b  xor     rcx, rsp; StackCookie
0x18000663e  call    __security_check_cookie
0x180006643  add     rsp, 70h
0x180006647  pop     r15
0x180006649  pop     r14
0x18000664b  pop     r12
0x18000664d  pop     rdi
0x18000664e  pop     rsi
0x18000664f  pop     rbp
0x180006650  pop     rbx
0x180006651  retn
```
