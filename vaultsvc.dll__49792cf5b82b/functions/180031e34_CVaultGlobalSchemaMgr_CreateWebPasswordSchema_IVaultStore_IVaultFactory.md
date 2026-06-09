# CVaultGlobalSchemaMgr::CreateWebPasswordSchema(IVaultStore *,IVaultFactory *)

- ea: `0x180031e34`
- end: `0x1800320f1`
- name: `?CreateWebPasswordSchema@CVaultGlobalSchemaMgr@@AEAAKPEAUIVaultStore@@PEAUIVaultFactory@@@Z`
- size: `701`
- prototype: `unsigned int __fastcall(CVaultGlobalSchemaMgr *__hidden this, struct IVaultStore *, struct IVaultFactory *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c348`

## callees

- `0x180003140`
- `0x180031e34`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultGlobalSchemaMgr::CreateWebPasswordSchema(
        CVaultGlobalSchemaMgr *this,
        struct IVaultStore *a2,
        struct IVaultFactory *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int i; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edi
  __int64 (__fastcall *v14)(_QWORD); // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-20h] BYREF
  int v16; // [rsp+40h] [rbp-18h]

  v14 = AutoDereference<IVaultKeyManager>;
  v15 = 0;
  v16 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IVaultFactory *, __int64 *, _QWORD, __int64, __int64 *))(*(_QWORD *)a3 + 8LL))(
         a3,
         &Vault_Schema_WebPassword,
         0,
         10,
         &v15);
  v5 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v4);
    goto LABEL_25;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v15 + 64LL))(
         v15,
         L"Windows Web Password Credential");
  v5 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v6);
    goto LABEL_25;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 48LL))(v15, 7, 0);
  v5 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v7);
    goto LABEL_25;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v15 + 40LL))(v15, 7, 0, 4);
  v5 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v8);
    goto LABEL_25;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 56LL))(v15, 7, 0);
  v5 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v9);
LABEL_25:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return v5;
  }
  for ( i = 100; ; ++i )
  {
    if ( i >= 0x6B )
    {
      v5 = (*(__int64 (__fastcall **)(struct IVaultStore *, __int64))(*(_QWORD *)a2 + 96LL))(a2, v15);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
      return v5;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v15 + 72LL))(v15, i, 8);
    v12 = v11;
    if ( v11 )
      break;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, i, v11);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
  return v12;
}

```

## disassembly

```asm
0x180031e34  push    rbp
0x180031e36  push    rbx
0x180031e37  push    rsi
0x180031e38  push    rdi
0x180031e39  mov     rbp, rsp
0x180031e3c  sub     rsp, 58h
0x180031e40  mov     r10, r8
0x180031e43  mov     rsi, rdx
0x180031e46  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180031e4d  mov     [rbp+var_28], rax
0x180031e51  mov     [rbp+var_20], 0
0x180031e59  mov     [rbp+var_18], 0
0x180031e60  mov     rax, [r8]
0x180031e63  lea     rcx, [rbp+var_20]
0x180031e67  mov     [rsp+58h+var_38], rcx
0x180031e6c  mov     edi, 0Ah
0x180031e71  mov     r9d, edi
0x180031e74  xor     r8d, r8d
0x180031e77  lea     rdx, Vault_Schema_WebPassword
0x180031e7e  mov     rcx, r10
0x180031e81  mov     rax, [rax+8]
0x180031e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e8a  mov     ebx, eax
0x180031e8c  test    eax, eax
0x180031e8e  jz      short loc_180031ECE
0x180031e90  lea     r8, WPP_GLOBAL_Control
0x180031e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e9e  cmp     rcx, r8
0x180031ea1  jz      short loc_180031EBF
0x180031ea3  test    byte ptr [rcx+1Ch], 2
0x180031ea7  jz      short loc_180031EBF
0x180031ea9  mov     edx, edi
0x180031eab  mov     r9d, eax
0x180031eae  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x180031eb5  mov     rcx, [rcx+10h]
0x180031eb9  call    WPP_SF_d
0x180031ebe  nop
0x180031ebf  lea     rcx, [rbp+var_28]
0x180031ec3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031ec8  nop
0x180031ec9  jmp     loc_1800320E6
0x180031ece  mov     rcx, [rbp+var_20]
0x180031ed2  mov     rax, [rcx]
0x180031ed5  lea     rdx, aWindowsWebPass; "Windows Web Password Credential"
0x180031edc  mov     rax, [rax+40h]
0x180031ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ee5  mov     ebx, eax
0x180031ee7  test    eax, eax
0x180031ee9  jz      short loc_180031F2C
0x180031eeb  lea     r8, WPP_GLOBAL_Control
0x180031ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ef9  cmp     rcx, r8
0x180031efc  jz      short loc_180031F1D
0x180031efe  test    byte ptr [rcx+1Ch], 2
0x180031f02  jz      short loc_180031F1D
0x180031f04  mov     edx, 0Bh
0x180031f09  mov     r9d, eax
0x180031f0c  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x180031f13  mov     rcx, [rcx+10h]
0x180031f17  call    WPP_SF_d
0x180031f1c  nop
0x180031f1d  lea     rcx, [rbp+var_28]
0x180031f21  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031f26  nop
0x180031f27  jmp     loc_1800320E6
0x180031f2c  mov     rcx, [rbp+var_20]
0x180031f30  mov     rax, [rcx]
0x180031f33  mov     r9d, 4
0x180031f39  xor     r8d, r8d
0x180031f3c  lea     edi, [r9+3]
0x180031f40  mov     edx, edi
0x180031f42  mov     rax, [rax+30h]
0x180031f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f4b  mov     ebx, eax
0x180031f4d  test    eax, eax
0x180031f4f  jz      short loc_180031F90
0x180031f51  lea     r8, WPP_GLOBAL_Control
0x180031f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f5f  cmp     rcx, r8
0x180031f62  jz      short loc_180031F81
0x180031f64  test    byte ptr [rcx+1Ch], 2
0x180031f68  jz      short loc_180031F81
0x180031f6a  lea     edx, [rdi+5]
0x180031f6d  mov     r9d, eax
0x180031f70  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x180031f77  mov     rcx, [rcx+10h]
0x180031f7b  call    WPP_SF_d
0x180031f80  nop
0x180031f81  lea     rcx, [rbp+var_28]
0x180031f85  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031f8a  nop
0x180031f8b  jmp     loc_1800320E6
0x180031f90  mov     rcx, [rbp+var_20]
0x180031f94  mov     rax, [rcx]
0x180031f97  mov     r9d, 4
0x180031f9d  xor     r8d, r8d
0x180031fa0  mov     edx, edi
0x180031fa2  mov     rax, [rax+28h]
0x180031fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fab  mov     ebx, eax
0x180031fad  test    eax, eax
0x180031faf  jz      short loc_180031FF2
0x180031fb1  lea     r8, WPP_GLOBAL_Control
0x180031fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180031fbf  cmp     rcx, r8
0x180031fc2  jz      short loc_180031FE3
0x180031fc4  test    byte ptr [rcx+1Ch], 2
0x180031fc8  jz      short loc_180031FE3
0x180031fca  mov     edx, 0Dh
0x180031fcf  mov     r9d, eax
0x180031fd2  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x180031fd9  mov     rcx, [rcx+10h]
0x180031fdd  call    WPP_SF_d
0x180031fe2  nop
0x180031fe3  lea     rcx, [rbp+var_28]
0x180031fe7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031fec  nop
0x180031fed  jmp     loc_1800320E6
0x180031ff2  mov     rcx, [rbp+var_20]
0x180031ff6  mov     rax, [rcx]
0x180031ff9  xor     r8d, r8d
0x180031ffc  mov     edx, edi
0x180031ffe  mov     rax, [rax+38h]
0x180032002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032007  mov     ebx, eax
0x180032009  test    eax, eax
0x18003200b  jz      short loc_18003204E
0x18003200d  lea     r8, WPP_GLOBAL_Control
0x180032014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003201b  cmp     rcx, r8
0x18003201e  jz      short loc_18003203F
0x180032020  test    byte ptr [rcx+1Ch], 2
0x180032024  jz      short loc_18003203F
0x180032026  mov     edx, 0Eh
0x18003202b  mov     r9d, eax
0x18003202e  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x180032035  mov     rcx, [rcx+10h]
0x180032039  call    WPP_SF_d
0x18003203e  nop
0x18003203f  lea     rcx, [rbp+var_28]
0x180032043  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180032048  nop
0x180032049  jmp     loc_1800320E6
0x18003204e  mov     ebx, 64h ; 'd'
0x180032053  cmp     ebx, 6Bh ; 'k'
0x180032056  jnb     short loc_1800320C7
0x180032058  mov     rcx, [rbp+var_20]
0x18003205c  mov     rax, [rcx]
0x18003205f  mov     dword ptr [rsp+58h+var_38], 8
0x180032067  xor     r9d, r9d
0x18003206a  lea     r8d, [r9+8]
0x18003206e  mov     edx, ebx
0x180032070  mov     rax, [rax+48h]
0x180032074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032079  mov     edi, eax
0x18003207b  test    eax, eax
0x18003207d  jnz     short loc_180032083
0x18003207f  inc     ebx
0x180032081  jmp     short loc_180032053
0x180032083  lea     r8, WPP_GLOBAL_Control
0x18003208a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032091  cmp     rcx, r8
0x180032094  jz      short loc_1800320B9
0x180032096  test    byte ptr [rcx+1Ch], 2
0x18003209a  jz      short loc_1800320B9
0x18003209c  mov     edx, 0Fh
0x1800320a1  mov     dword ptr [rsp+58h+var_38], edi
0x1800320a5  mov     r9d, ebx
0x1800320a8  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x1800320af  mov     rcx, [rcx+10h]
0x1800320b3  call    WPP_SF_dd
0x1800320b8  nop
0x1800320b9  lea     rcx, [rbp+var_28]
0x1800320bd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800320c2  nop
0x1800320c3  mov     eax, edi
0x1800320c5  jmp     short loc_1800320E8
0x1800320c7  mov     rax, [rsi]
0x1800320ca  mov     rdx, [rbp+var_20]
0x1800320ce  mov     rcx, rsi
0x1800320d1  mov     rax, [rax+60h]
0x1800320d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320da  mov     ebx, eax
0x1800320dc  lea     rcx, [rbp+var_28]
0x1800320e0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800320e5  nop
0x1800320e6  mov     eax, ebx
0x1800320e8  add     rsp, 58h
0x1800320ec  pop     rdi
0x1800320ed  pop     rsi
0x1800320ee  pop     rbx
0x1800320ef  pop     rbp
0x1800320f0  retn
```
