# CreateStorageItemVectorFromShellItemArray(IShellItemArray *,ushort const *,ulong,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> * *)

- ea: `0x1800613f0`
- end: `0x1800615b1`
- name: `?CreateStorageItemVectorFromShellItemArray@@YAJPEAUIShellItemArray@@PEBGKPEAPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180061350`

## callees

- `0x18000775c`
- `0x180008b68`
- `0x1800613f0`
- `0x180081010`

## import_xrefs

- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800614f3`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800614f3`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage` at `0x1800614b4`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage` at `0x1800614b4`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x1800614e1`
- `ext-ms-win-shell-shell32-l1-2-0!CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x1800614e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CreateStorageItemVectorFromShellItemArray(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int StorageItemFromShellItem_FullTrustCaller; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+48h] BYREF

  *a4 = 0;
  v20 = 0;
  v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
         a1,
         &v20);
  if ( v8 >= 0 )
  {
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 56LL))(a1, &v21);
    v9 = 0;
    if ( v8 >= 0 )
    {
      while ( v9 < v21 )
      {
        v19 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a1 + 64LL))(a1, v9, &v19);
        if ( v8 >= 0 )
        {
          v18 = 0;
          v10 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v18);
          v11 = a3 | 1;
          if ( (int)CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage(
                      v19,
                      a3 | 1u,
                      &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                      v10) >= 0
            || ((v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v18),
                 !a2)
              ? (StorageItemFromShellItem_FullTrustCaller = CreateStorageItemFromShellItem_FullTrustCaller(
                                                              v19,
                                                              v11,
                                                              &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                                                              v12))
              : (StorageItemFromShellItem_FullTrustCaller = CreateStorageItemFromShellItem_FullTrustCaller_ForPackage(
                                                              v19,
                                                              v11,
                                                              a2,
                                                              &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                                                              v12)),
                v8 = StorageItemFromShellItem_FullTrustCaller,
                StorageItemFromShellItem_FullTrustCaller >= 0) )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 104LL))(v20, v18);
          }
          v14 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
        v15 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        ++v9;
        if ( v8 < 0 )
          goto LABEL_18;
      }
      v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v20)(
             v20,
             &GUID_802508e2_9c2c_5b91_89a8_39bcf7223344,
             a4);
    }
  }
LABEL_18:
  v16 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800613f0  mov     [rsp-28h+arg_0], rbx
0x1800613f5  mov     [rsp-28h+arg_8], rsi
0x1800613fa  push    rbp
0x1800613fb  push    rdi
0x1800613fc  push    r12
0x1800613fe  push    r14
0x180061400  push    r15
0x180061402  mov     rbp, rsp
0x180061405  sub     rsp, 50h
0x180061409  mov     r15, r9
0x18006140c  mov     r12d, r8d
0x18006140f  mov     r14, rdx
0x180061412  mov     rsi, rcx
0x180061415  mov     qword ptr [r9], 0
0x18006141c  mov     [rbp+var_10], 0
0x180061424  lea     rdx, [rbp+var_10]
0x180061428  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)
0x18006142d  mov     ebx, eax
0x18006142f  test    eax, eax
0x180061431  js      loc_180061578
0x180061437  mov     [rbp+arg_18], 0
0x18006143e  mov     rax, [rsi]
0x180061441  lea     rdx, [rbp+arg_18]
0x180061445  mov     rcx, rsi
0x180061448  mov     rax, [rax+38h]
0x18006144c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061451  mov     ebx, eax
0x180061453  xor     edi, edi
0x180061455  test    eax, eax
0x180061457  js      loc_180061578
0x18006145d  cmp     edi, [rbp+arg_18]
0x180061460  jnb     loc_18006155D
0x180061466  mov     [rbp+var_18], 0
0x18006146e  mov     rax, [rsi]
0x180061471  lea     r8, [rbp+var_18]
0x180061475  mov     edx, edi
0x180061477  mov     rcx, rsi
0x18006147a  mov     rax, [rax+40h]
0x18006147e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061483  mov     ebx, eax
0x180061485  test    eax, eax
0x180061487  js      loc_180061533
0x18006148d  mov     [rbp+var_20], 0
0x180061495  lea     rcx, [rbp+var_20]
0x180061499  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18006149e  mov     ebx, r12d
0x1800614a1  or      ebx, 1
0x1800614a4  mov     r9, rax
0x1800614a7  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800614ae  mov     edx, ebx
0x1800614b0  mov     rcx, [rbp+var_18]
0x1800614b4  call    cs:__imp_CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage
0x1800614ba  test    eax, eax
0x1800614bc  jns     short loc_1800614FF
0x1800614be  lea     rcx, [rbp+var_20]
0x1800614c2  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x1800614c7  mov     edx, ebx
0x1800614c9  mov     rcx, [rbp+var_18]
0x1800614cd  test    r14, r14
0x1800614d0  jz      short loc_1800614E9
0x1800614d2  mov     [rsp+50h+var_30], rax
0x1800614d7  lea     r9, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800614de  mov     r8, r14
0x1800614e1  call    cs:__imp_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage
0x1800614e7  jmp     short loc_1800614F9
0x1800614e9  mov     r9, rax
0x1800614ec  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800614f3  call    cs:__imp_CreateStorageItemFromShellItem_FullTrustCaller
0x1800614f9  mov     ebx, eax
0x1800614fb  test    eax, eax
0x1800614fd  js      short loc_180061515
0x1800614ff  mov     rcx, [rbp+var_10]
0x180061503  mov     rax, [rcx]
0x180061506  mov     rdx, [rbp+var_20]
0x18006150a  mov     rax, [rax+68h]
0x18006150e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061513  mov     ebx, eax
0x180061515  mov     rcx, [rbp+var_20]
0x180061519  test    rcx, rcx
0x18006151c  jz      short loc_180061533
0x18006151e  mov     [rbp+var_20], 0
0x180061526  mov     rax, [rcx]
0x180061529  mov     rax, [rax+10h]
0x18006152d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061532  nop
0x180061533  mov     rcx, [rbp+var_18]
0x180061537  test    rcx, rcx
0x18006153a  jz      short loc_180061551
0x18006153c  mov     [rbp+var_18], 0
0x180061544  mov     rax, [rcx]
0x180061547  mov     rax, [rax+10h]
0x18006154b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061550  nop
0x180061551  inc     edi
0x180061553  test    ebx, ebx
0x180061555  jns     loc_18006145D
0x18006155b  jmp     short loc_180061578
0x18006155d  mov     rcx, [rbp+var_10]
0x180061561  mov     rax, [rcx]
0x180061564  mov     r8, r15
0x180061567  lea     rdx, _GUID_802508e2_9c2c_5b91_89a8_39bcf7223344
0x18006156e  mov     rax, [rax]
0x180061571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061576  mov     ebx, eax
0x180061578  mov     rcx, [rbp+var_10]
0x18006157c  test    rcx, rcx
0x18006157f  jz      short loc_180061596
0x180061581  mov     [rbp+var_10], 0
0x180061589  mov     rax, [rcx]
0x18006158c  mov     rax, [rax+10h]
0x180061590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061595  nop
0x180061596  mov     eax, ebx
0x180061598  lea     r11, [rsp+50h+var_s0]
0x18006159d  mov     rbx, [r11+30h]
0x1800615a1  mov     rsi, [r11+38h]
0x1800615a5  mov     rsp, r11
0x1800615a8  pop     r15
0x1800615aa  pop     r14
0x1800615ac  pop     r12
0x1800615ae  pop     rdi
0x1800615af  pop     rbp
0x1800615b0  retn
```
