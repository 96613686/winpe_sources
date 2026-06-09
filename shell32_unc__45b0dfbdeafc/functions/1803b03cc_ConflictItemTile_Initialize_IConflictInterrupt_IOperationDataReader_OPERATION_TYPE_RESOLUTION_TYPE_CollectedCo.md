# ConflictItemTile::_Initialize(IConflictInterrupt *,IOperationDataReader *,OPERATION_TYPE,RESOLUTION_TYPE,CollectedConflictTelemetry *)

- ea: `0x1803b03cc`
- end: `0x1803b067e`
- name: `?_Initialize@ConflictItemTile@@AEAAJPEAUIConflictInterrupt@@PEAUIOperationDataReader@@W4OPERATION_TYPE@@W4RESOLUTION_TYPE@@PEAVCollectedConflictTelemetry@@@Z`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1803b529c`

## callees

- `0x180012e0c`
- `0x1802085f8`
- `0x180249490`
- `0x1803b03cc`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b063b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0518`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b0629`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803b063b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b04e8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b059a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b0600`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b04e8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b059a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1803b0600`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1803b0616`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1803b0616`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1803b0562`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1803b0562`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1803b04a6`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1803b05c1`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1803b04a6`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1803b05c1`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b04d7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b0589`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b05ef`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b04d7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b0589`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1803b05ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConflictItemTile::_Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v9; // edi
  const unsigned __int16 *v10; // rsi
  struct DirectUI::Value *Int; // rax
  DirectUI::Value *v12; // r14
  int v13; // ebx
  __int64 (__fastcall *v14)(__int64, _QWORD, LPVOID *, unsigned __int16 **); // rbx
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v16; // r14
  struct DirectUI::Value *v17; // rax
  DirectUI::Value *v18; // rdi
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-40h] BYREF

  *(_DWORD *)(a1 + 240) = a4;
  switch ( a5 )
  {
    case 1u:
      v9 = 9;
      v10 = L"IdTileKeepSource";
      break;
    case 2u:
      v9 = 10;
      v10 = L"IdTileKeepDest";
      break;
    case 3u:
      v9 = 11;
      v10 = L"IdTileDecideForEach";
      ATL::CComPtr<IItemThumbnailCallback>::operator=(a1 + 216, a2);
      ATL::CComPtr<IItemThumbnailCallback>::operator=(a1 + 224, a3);
      break;
    case 4u:
      v9 = 12;
      v10 = L"IdTileKeepAsWork";
      break;
    case 5u:
      v9 = 13;
      v10 = L"IdTileKeepAsPersonal";
      break;
    case 6u:
      v9 = 3;
      v10 = L"IdTileIgnore";
      break;
    default:
      v9 = 11;
      v10 = 0;
      break;
  }
  Int = (struct DirectUI::Value *)DirectUI::Value::CreateInt(a5, 0);
  v12 = Int;
  if ( !Int )
    return (unsigned int)-2147024882;
  v13 = DirectUI::Element::SetValue((DirectUI::Element *)a1, ConflictItemTile::TileTypeProp, 1, Int);
  DirectUI::Value::Release(v12);
  if ( v13 < 0 )
    return (unsigned int)v13;
  pv = 0;
  v21 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, unsigned __int16 **))(*(_QWORD *)a2 + 96LL);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  v13 = v14(a2, a5, &pv, &v21);
  if ( v13 >= 0 )
  {
    String = DirectUI::Value::CreateString((const unsigned __int16 *)pv, 0);
    v16 = String;
    if ( !String )
    {
LABEL_22:
      v13 = -2147024882;
      goto LABEL_25;
    }
    v13 = DirectUI::Element::SetValue((DirectUI::Element *)a1, ConflictItemTile::DescriptionProp, 1, String);
    DirectUI::Value::Release(v16);
    if ( v13 >= 0 )
    {
      v13 = ConflictItemTile::SetSubText((ConflictItemTile *)a1, v21);
      if ( v13 >= 0 )
      {
        v17 = (struct DirectUI::Value *)DirectUI::Value::CreateInt(v9, 0);
        v18 = v17;
        if ( v17 )
        {
          v13 = DirectUI::Element::SetValue((DirectUI::Element *)a1, InterruptButton::ResponseProp, 1, v17);
          DirectUI::Value::Release(v18);
          if ( v13 >= 0 )
            v13 = DirectUI::Element::SetID((DirectUI::Element *)a1, v10);
          goto LABEL_25;
        }
        goto LABEL_22;
      }
    }
  }
LABEL_25:
  CoTaskMemFree(v21);
  CoTaskMemFree(pv);
  if ( v13 >= 0 )
    *(_QWORD *)(a1 + 232) = a6;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1803b03cc  mov     [rsp+arg_18], rbx
0x1803b03d1  push    rbp
0x1803b03d2  push    rsi
0x1803b03d3  push    rdi
0x1803b03d4  push    r12
0x1803b03d6  push    r14
0x1803b03d8  sub     rsp, 50h
0x1803b03dc  mov     rax, cs:__security_cookie
0x1803b03e3  xor     rax, rsp
0x1803b03e6  mov     [rsp+78h+var_38], rax
0x1803b03eb  mov     rbx, r8
0x1803b03ee  mov     r12, rdx
0x1803b03f1  mov     rbp, rcx
0x1803b03f4  mov     [rcx+0F0h], r9d
0x1803b03fb  mov     edx, [rsp+78h+arg_20]
0x1803b0402  sub     edx, 1
0x1803b0405  jz      loc_1803B0491
0x1803b040b  sub     edx, 1
0x1803b040e  jz      short loc_1803B0483
0x1803b0410  sub     edx, 1
0x1803b0413  jz      short loc_1803B0457
0x1803b0415  sub     edx, 1
0x1803b0418  jz      short loc_1803B0449
0x1803b041a  sub     edx, 1
0x1803b041d  jz      short loc_1803B043B
0x1803b041f  cmp     edx, 1
0x1803b0422  jz      short loc_1803B042D
0x1803b0424  mov     edi, 0Bh
0x1803b0429  xor     esi, esi
0x1803b042b  jmp     short loc_1803B049D
0x1803b042d  mov     edi, 3
0x1803b0432  lea     rsi, aIdtileignore; "IdTileIgnore"
0x1803b0439  jmp     short loc_1803B049D
0x1803b043b  mov     edi, 0Dh
0x1803b0440  lea     rsi, aIdtilekeepaspe; "IdTileKeepAsPersonal"
0x1803b0447  jmp     short loc_1803B049D
0x1803b0449  mov     edi, 0Ch
0x1803b044e  lea     rsi, aIdtilekeepaswo; "IdTileKeepAsWork"
0x1803b0455  jmp     short loc_1803B049D
0x1803b0457  mov     edi, 0Bh
0x1803b045c  lea     rsi, aIdtiledecidefo; "IdTileDecideForEach"
0x1803b0463  add     rcx, 0D8h
0x1803b046a  mov     rdx, r12
0x1803b046d  call    ??4?$CComPtr@UIItemThumbnailCallback@@@ATL@@QEAAPEAUIItemThumbnailCallback@@PEAU2@@Z; ATL::CComPtr<IItemThumbnailCallback>::operator=(IItemThumbnailCallback *)
0x1803b0472  lea     rcx, [rbp+0E0h]
0x1803b0479  mov     rdx, rbx
0x1803b047c  call    ??4?$CComPtr@UIItemThumbnailCallback@@@ATL@@QEAAPEAUIItemThumbnailCallback@@PEAU2@@Z; ATL::CComPtr<IItemThumbnailCallback>::operator=(IItemThumbnailCallback *)
0x1803b0481  jmp     short loc_1803B049D
0x1803b0483  mov     edi, 0Ah
0x1803b0488  lea     rsi, aIdtilekeepdest; "IdTileKeepDest"
0x1803b048f  jmp     short loc_1803B049D
0x1803b0491  mov     edi, 9
0x1803b0496  lea     rsi, aIdtilekeepsour; "IdTileKeepSource"
0x1803b049d  xor     edx, edx
0x1803b049f  mov     ecx, [rsp+78h+arg_20]
0x1803b04a6  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x1803b04ad  nop     dword ptr [rax+rax+00h]
0x1803b04b2  mov     r14, rax
0x1803b04b5  test    rax, rax
0x1803b04b8  jnz     short loc_1803B04C4
0x1803b04ba  mov     ebx, 8007000Eh
0x1803b04bf  jmp     loc_1803B065A
0x1803b04c4  mov     r9, r14
0x1803b04c7  mov     r8d, 1
0x1803b04cd  lea     rdx, ?TileTypeProp@ConflictItemTile@@SAPEBUPropertyInfo@DirectUI@@XZ; ConflictItemTile::TileTypeProp(void)
0x1803b04d4  mov     rcx, rbp
0x1803b04d7  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1803b04de  nop     dword ptr [rax+rax+00h]
0x1803b04e3  mov     ebx, eax
0x1803b04e5  mov     rcx, r14
0x1803b04e8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1803b04ef  nop     dword ptr [rax+rax+00h]
0x1803b04f4  test    ebx, ebx
0x1803b04f6  js      loc_1803B065A
0x1803b04fc  mov     [rsp+78h+pv], 0
0x1803b0505  mov     [rsp+78h+var_40], 0
0x1803b050e  mov     rax, [r12]
0x1803b0512  mov     rbx, [rax+60h]
0x1803b0516  xor     ecx, ecx; pv
0x1803b0518  call    cs:__imp_CoTaskMemFree
0x1803b051f  nop     dword ptr [rax+rax+00h]
0x1803b0524  mov     rcx, [rsp+78h+pv]; pv
0x1803b0529  call    cs:__imp_CoTaskMemFree
0x1803b0530  nop     dword ptr [rax+rax+00h]
0x1803b0535  lea     r9, [rsp+78h+var_40]
0x1803b053a  lea     r8, [rsp+78h+pv]
0x1803b053f  mov     edx, [rsp+78h+arg_20]
0x1803b0546  mov     rcx, r12
0x1803b0549  mov     rax, rbx
0x1803b054c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803b0551  mov     ebx, eax
0x1803b0553  test    eax, eax
0x1803b0555  js      loc_1803B0624
0x1803b055b  xor     edx, edx
0x1803b055d  mov     rcx, [rsp+78h+pv]
0x1803b0562  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x1803b0569  nop     dword ptr [rax+rax+00h]
0x1803b056e  mov     r14, rax
0x1803b0571  test    rax, rax
0x1803b0574  jz      short loc_1803B05D5
0x1803b0576  mov     r9, rax
0x1803b0579  mov     r8d, 1
0x1803b057f  lea     rdx, ?DescriptionProp@ConflictItemTile@@SAPEBUPropertyInfo@DirectUI@@XZ; ConflictItemTile::DescriptionProp(void)
0x1803b0586  mov     rcx, rbp
0x1803b0589  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1803b0590  nop     dword ptr [rax+rax+00h]
0x1803b0595  mov     ebx, eax
0x1803b0597  mov     rcx, r14
0x1803b059a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1803b05a1  nop     dword ptr [rax+rax+00h]
0x1803b05a6  test    ebx, ebx
0x1803b05a8  js      short loc_1803B0624
0x1803b05aa  mov     rdx, [rsp+78h+var_40]; unsigned __int16 *
0x1803b05af  mov     rcx, rbp; this
0x1803b05b2  call    ?SetSubText@ConflictItemTile@@AEAAJPEBG@Z; ConflictItemTile::SetSubText(ushort const *)
0x1803b05b7  mov     ebx, eax
0x1803b05b9  test    eax, eax
0x1803b05bb  js      short loc_1803B0624
0x1803b05bd  xor     edx, edx
0x1803b05bf  mov     ecx, edi
0x1803b05c1  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x1803b05c8  nop     dword ptr [rax+rax+00h]
0x1803b05cd  mov     rdi, rax
0x1803b05d0  test    rax, rax
0x1803b05d3  jnz     short loc_1803B05DC
0x1803b05d5  mov     ebx, 8007000Eh
0x1803b05da  jmp     short loc_1803B0624
0x1803b05dc  mov     r9, rdi
0x1803b05df  mov     r8d, 1
0x1803b05e5  lea     rdx, ?ResponseProp@InterruptButton@@SAPEBUPropertyInfo@DirectUI@@XZ; InterruptButton::ResponseProp(void)
0x1803b05ec  mov     rcx, rbp
0x1803b05ef  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1803b05f6  nop     dword ptr [rax+rax+00h]
0x1803b05fb  mov     ebx, eax
0x1803b05fd  mov     rcx, rdi
0x1803b0600  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1803b0607  nop     dword ptr [rax+rax+00h]
0x1803b060c  test    ebx, ebx
0x1803b060e  js      short loc_1803B0624
0x1803b0610  mov     rdx, rsi
0x1803b0613  mov     rcx, rbp
0x1803b0616  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1803b061d  nop     dword ptr [rax+rax+00h]
0x1803b0622  mov     ebx, eax
0x1803b0624  mov     rcx, [rsp+78h+var_40]; pv
0x1803b0629  call    cs:__imp_CoTaskMemFree
0x1803b0630  nop     dword ptr [rax+rax+00h]
0x1803b0635  nop
0x1803b0636  mov     rcx, [rsp+78h+pv]; pv
0x1803b063b  call    cs:__imp_CoTaskMemFree
0x1803b0642  nop     dword ptr [rax+rax+00h]
0x1803b0647  test    ebx, ebx
0x1803b0649  js      short loc_1803B065A
0x1803b064b  mov     rax, [rsp+78h+arg_28]
0x1803b0653  mov     [rbp+0E8h], rax
0x1803b065a  mov     eax, ebx
0x1803b065c  mov     rcx, [rsp+78h+var_38]
0x1803b0661  xor     rcx, rsp; StackCookie
0x1803b0664  call    __security_check_cookie
0x1803b0669  mov     rbx, [rsp+78h+arg_18]
0x1803b0671  add     rsp, 50h
0x1803b0675  pop     r14
0x1803b0677  pop     r12
0x1803b0679  pop     rdi
0x1803b067a  pop     rsi
0x1803b067b  pop     rbp
0x1803b067c  retn
```
