# ValidateAndGetItemPackageSid(_VAULT_ITEM_ELEMENT *,IVaultCredential *,CVaultSid * *)

- ea: `0x1800493d4`
- end: `0x1800495b7`
- name: `?ValidateAndGetItemPackageSid@@YAKPEAU_VAULT_ITEM_ELEMENT@@PEAUIVaultCredential@@PEAPEAVCVaultSid@@@Z`
- size: `483`
- prototype: `unsigned int __fastcall(struct _VAULT_ITEM_ELEMENT *, struct IVaultCredential *, struct CVaultSid **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180016250`

## callees

- `0x180003140`
- `0x18001a640`
- `0x180021d80`
- `0x18002b6f0`
- `0x180038d84`
- `0x18003b7b0`
- `0x1800493d4`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ValidateAndGetItemPackageSid(
        struct _VAULT_ITEM_ELEMENT *a1,
        struct IVaultCredential *a2,
        struct CVaultSid **a3)
{
  unsigned int IsDominantCaller; // ebx
  __int64 v8; // rax
  struct CVaultSid *v9; // rbx
  __int64 (__fastcall *v10)(_QWORD); // [rsp+20h] [rbp-30h] BYREF
  struct CVaultSid *v11; // [rsp+28h] [rbp-28h] BYREF
  int v12; // [rsp+30h] [rbp-20h]
  void (__fastcall *v13)(HLOCAL); // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+48h] [rbp-8h]
  int v16; // [rsp+88h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  v10 = AutoDereference<IVaultKeyManager>;
  IsDominantCaller = VaultValidatePackageSidElement(a1);
  if ( IsDominantCaller
    || (IsDominantCaller = CVaultSid::CreateVaultSid(*((PSID *)a1 + 2), &v11)) != 0
    || (v16 = 0, (IsDominantCaller = VaultIsDominantCaller(&v16)) != 0) )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
    return IsDominantCaller;
  }
  if ( v16 )
  {
    v13 = IVaultSecurable::FreeVaultSecurable;
    v14 = 0;
    v15 = 0;
    IsDominantCaller = VaultCreateVaultSecurable(3, qword_180053820, v11, &v14);
    if ( !IsDominantCaller )
    {
      IsDominantCaller = (*(__int64 (__fastcall **)(struct IVaultCredential *, __int64))(*(_QWORD *)a2 + 216LL))(
                           a2,
                           v14);
      if ( !IsDominantCaller )
      {
        v14 = 0;
        v8 = (*(__int64 (__fastcall **)(struct IVaultCredential *))(*(_QWORD *)a2 + 208LL))(a2);
        v9 = (struct CVaultSid *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
        v11 = v9;
        (**(void (__fastcall ***)(struct CVaultSid *))v9)(v9);
        v11 = 0;
        *a3 = v9;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
        return 0;
      }
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v13);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
    return IsDominantCaller;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v10);
  return 5;
}

```

## disassembly

```asm
0x1800493d4  mov     [rsp-18h+arg_0], rbx
0x1800493d9  mov     [rsp-18h+arg_8], rsi
0x1800493de  push    rbp
0x1800493df  push    rdi
0x1800493e0  push    r14
0x1800493e2  mov     rbp, rsp
0x1800493e5  sub     rsp, 50h
0x1800493e9  mov     r14, r8
0x1800493ec  mov     rdi, rdx
0x1800493ef  mov     rsi, rcx
0x1800493f2  mov     [rbp+var_28], 0
0x1800493fa  mov     [rbp+var_20], 0
0x180049401  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180049408  mov     [rbp+var_30], rax
0x18004940c  call    ?VaultValidatePackageSidElement@@YAKPEAU_VAULT_ITEM_ELEMENT@@@Z; VaultValidatePackageSidElement(_VAULT_ITEM_ELEMENT *)
0x180049411  mov     ebx, eax
0x180049413  test    eax, eax
0x180049415  jz      short loc_180049428
0x180049417  lea     rcx, [rbp+var_30]
0x18004941b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049420  nop
0x180049421  mov     eax, ebx
0x180049423  jmp     loc_1800495A4
0x180049428  lea     rdx, [rbp+var_28]; struct CVaultSid **
0x18004942c  mov     rcx, [rsi+10h]; pSourceSid
0x180049430  call    ?CreateVaultSid@CVaultSid@@SAKQEAXPEAPEAV1@@Z; CVaultSid::CreateVaultSid(void * const,CVaultSid * *)
0x180049435  mov     ebx, eax
0x180049437  test    eax, eax
0x180049439  jz      short loc_180049447
0x18004943b  lea     rcx, [rbp+var_30]
0x18004943f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049444  nop
0x180049445  jmp     short loc_180049421
0x180049447  mov     [rbp+arg_18], 0
0x18004944e  lea     rcx, [rbp+arg_18]; int *
0x180049452  call    ?VaultIsDominantCaller@@YAKPEAH@Z; VaultIsDominantCaller(int *)
0x180049457  mov     ebx, eax
0x180049459  test    eax, eax
0x18004945b  jz      short loc_180049469
0x18004945d  lea     rcx, [rbp+var_30]
0x180049461  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049466  nop
0x180049467  jmp     short loc_180049421
0x180049469  cmp     [rbp+arg_18], 0
0x18004946d  jnz     short loc_1800494B2
0x18004946f  lea     rax, WPP_GLOBAL_Control
0x180049476  mov     rcx, cs:WPP_GLOBAL_Control
0x18004947d  cmp     rcx, rax
0x180049480  jz      short loc_18004949E
0x180049482  test    byte ptr [rcx+1Ch], 2
0x180049486  jz      short loc_18004949E
0x180049488  mov     edx, 71h ; 'q'
0x18004948d  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180049494  mov     rcx, [rcx+10h]
0x180049498  call    WPP_SF_
0x18004949d  nop
0x18004949e  lea     rcx, [rbp+var_30]
0x1800494a2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800494a7  nop
0x1800494a8  mov     eax, 5
0x1800494ad  jmp     loc_1800495A4
0x1800494b2  lea     rax, ?FreeVaultSecurable@IVaultSecurable@@SAXPEAV1@@Z; IVaultSecurable::FreeVaultSecurable(IVaultSecurable *)
0x1800494b9  mov     [rbp+var_18], rax
0x1800494bd  mov     [rbp+var_10], 0
0x1800494c5  mov     [rbp+var_8], 0
0x1800494cc  lea     r9, [rbp+var_10]
0x1800494d0  mov     r8, [rbp+var_28]
0x1800494d4  lea     rdx, qword_180053820
0x1800494db  mov     ecx, 3
0x1800494e0  call    ?VaultCreateVaultSecurable@@YAKW4EVaultSecurableType@@AEBU_GUID@@PEAVCVaultSid@@PEAPEAVIVaultSecurable@@@Z; VaultCreateVaultSecurable(EVaultSecurableType,_GUID const &,CVaultSid *,IVaultSecurable * *)
0x1800494e5  mov     ebx, eax
0x1800494e7  test    eax, eax
0x1800494e9  jz      short loc_180049504
0x1800494eb  lea     rcx, [rbp+var_18]
0x1800494ef  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800494f4  nop
0x1800494f5  lea     rcx, [rbp+var_30]
0x1800494f9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800494fe  nop
0x1800494ff  jmp     loc_180049421
0x180049504  mov     rax, [rdi]
0x180049507  mov     rdx, [rbp+var_10]
0x18004950b  mov     rcx, rdi
0x18004950e  mov     rax, [rax+0D8h]
0x180049515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004951a  mov     ebx, eax
0x18004951c  test    eax, eax
0x18004951e  jz      short loc_180049539
0x180049520  lea     rcx, [rbp+var_18]
0x180049524  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049529  nop
0x18004952a  lea     rcx, [rbp+var_30]
0x18004952e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049533  nop
0x180049534  jmp     loc_180049421
0x180049539  mov     [rbp+var_10], 0
0x180049541  mov     rax, [rdi]
0x180049544  mov     rcx, rdi
0x180049547  mov     rax, [rax+0D0h]
0x18004954e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049553  mov     rdx, rax
0x180049556  mov     rcx, [rax]
0x180049559  mov     rax, [rcx+20h]
0x18004955d  mov     rcx, rdx
0x180049560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049565  mov     rbx, rax
0x180049568  lea     rcx, [rbp+var_30]
0x18004956c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049571  mov     [rbp+var_28], rbx
0x180049575  mov     rcx, [rbx]
0x180049578  mov     rax, [rcx]
0x18004957b  mov     rcx, rbx
0x18004957e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049583  mov     [rbp+var_28], 0
0x18004958b  mov     [r14], rbx
0x18004958e  lea     rcx, [rbp+var_18]
0x180049592  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049597  nop
0x180049598  lea     rcx, [rbp+var_30]
0x18004959c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800495a1  nop
0x1800495a2  xor     eax, eax
0x1800495a4  mov     rbx, [rsp+50h+arg_0]
0x1800495a9  mov     rsi, [rsp+50h+arg_8]
0x1800495ae  add     rsp, 50h
0x1800495b2  pop     r14
0x1800495b4  pop     rdi
0x1800495b5  pop     rbp
0x1800495b6  retn
```
