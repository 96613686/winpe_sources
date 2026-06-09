# ConflictItemTile::_Initialize(IConflictInterrupt *,IOperationDataReader *,OPERATION_TYPE,RESOLUTION_TYPE,CollectedConflictTelemetry *)

- ea: `0x180389f5c`
- end: `0x18038a1b9`
- name: `?_Initialize@ConflictItemTile@@AEAAJPEAUIConflictInterrupt@@PEAUIOperationDataReader@@W4OPERATION_TYPE@@W4RESOLUTION_TYPE@@PEAVCollectedConflictTelemetry@@@Z`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18038e720`

## callees

- `0x1800125e8`
- `0x1801f099c`
- `0x180233280`
- `0x180389f5c`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a0a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a17d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a0a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a171`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18038a17d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a06c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a100`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a154`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a06c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a100`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18038a154`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18038a164`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18038a164`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18038a036`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18038a121`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18038a036`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x18038a121`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a061`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a0f5`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a149`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a061`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a0f5`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18038a149`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18038a0d4`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18038a0d4`

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
0x180389f5c  mov     [rsp+arg_18], rbx
0x180389f61  push    rbp
0x180389f62  push    rsi
0x180389f63  push    rdi
0x180389f64  push    r12
0x180389f66  push    r14
0x180389f68  sub     rsp, 50h
0x180389f6c  mov     rax, cs:__security_cookie
0x180389f73  xor     rax, rsp
0x180389f76  mov     [rsp+78h+var_38], rax
0x180389f7b  mov     rbx, r8
0x180389f7e  mov     r12, rdx
0x180389f81  mov     rbp, rcx
0x180389f84  mov     [rcx+0F0h], r9d
0x180389f8b  mov     edx, [rsp+78h+arg_20]
0x180389f92  sub     edx, 1
0x180389f95  jz      loc_18038A021
0x180389f9b  sub     edx, 1
0x180389f9e  jz      short loc_18038A013
0x180389fa0  sub     edx, 1
0x180389fa3  jz      short loc_180389FE7
0x180389fa5  sub     edx, 1
0x180389fa8  jz      short loc_180389FD9
0x180389faa  sub     edx, 1
0x180389fad  jz      short loc_180389FCB
0x180389faf  cmp     edx, 1
0x180389fb2  jz      short loc_180389FBD
0x180389fb4  mov     edi, 0Bh
0x180389fb9  xor     esi, esi
0x180389fbb  jmp     short loc_18038A02D
0x180389fbd  mov     edi, 3
0x180389fc2  lea     rsi, aIdtileignore; "IdTileIgnore"
0x180389fc9  jmp     short loc_18038A02D
0x180389fcb  mov     edi, 0Dh
0x180389fd0  lea     rsi, aIdtilekeepaspe; "IdTileKeepAsPersonal"
0x180389fd7  jmp     short loc_18038A02D
0x180389fd9  mov     edi, 0Ch
0x180389fde  lea     rsi, aIdtilekeepaswo; "IdTileKeepAsWork"
0x180389fe5  jmp     short loc_18038A02D
0x180389fe7  mov     edi, 0Bh
0x180389fec  lea     rsi, aIdtiledecidefo; "IdTileDecideForEach"
0x180389ff3  add     rcx, 0D8h
0x180389ffa  mov     rdx, r12
0x180389ffd  call    ??4?$CComPtr@UIItemThumbnailCallback@@@ATL@@QEAAPEAUIItemThumbnailCallback@@PEAU2@@Z; ATL::CComPtr<IItemThumbnailCallback>::operator=(IItemThumbnailCallback *)
0x18038a002  lea     rcx, [rbp+0E0h]
0x18038a009  mov     rdx, rbx
0x18038a00c  call    ??4?$CComPtr@UIItemThumbnailCallback@@@ATL@@QEAAPEAUIItemThumbnailCallback@@PEAU2@@Z; ATL::CComPtr<IItemThumbnailCallback>::operator=(IItemThumbnailCallback *)
0x18038a011  jmp     short loc_18038A02D
0x18038a013  mov     edi, 0Ah
0x18038a018  lea     rsi, aIdtilekeepdest; "IdTileKeepDest"
0x18038a01f  jmp     short loc_18038A02D
0x18038a021  mov     edi, 9
0x18038a026  lea     rsi, aIdtilekeepsour; "IdTileKeepSource"
0x18038a02d  xor     edx, edx
0x18038a02f  mov     ecx, [rsp+78h+arg_20]
0x18038a036  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x18038a03c  mov     r14, rax
0x18038a03f  test    rax, rax
0x18038a042  jnz     short loc_18038A04E
0x18038a044  mov     ebx, 8007000Eh
0x18038a049  jmp     loc_18038A196
0x18038a04e  mov     r9, r14
0x18038a051  mov     r8d, 1
0x18038a057  lea     rdx, ?TileTypeProp@ConflictItemTile@@SAPEBUPropertyInfo@DirectUI@@XZ; ConflictItemTile::TileTypeProp(void)
0x18038a05e  mov     rcx, rbp
0x18038a061  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18038a067  mov     ebx, eax
0x18038a069  mov     rcx, r14
0x18038a06c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18038a072  test    ebx, ebx
0x18038a074  js      loc_18038A196
0x18038a07a  mov     [rsp+78h+pv], 0
0x18038a083  mov     [rsp+78h+var_40], 0
0x18038a08c  mov     rax, [r12]
0x18038a090  mov     rbx, [rax+60h]
0x18038a094  xor     ecx, ecx; pv
0x18038a096  call    cs:__imp_CoTaskMemFree
0x18038a09c  mov     rcx, [rsp+78h+pv]; pv
0x18038a0a1  call    cs:__imp_CoTaskMemFree
0x18038a0a7  lea     r9, [rsp+78h+var_40]
0x18038a0ac  lea     r8, [rsp+78h+pv]
0x18038a0b1  mov     edx, [rsp+78h+arg_20]
0x18038a0b8  mov     rcx, r12
0x18038a0bb  mov     rax, rbx
0x18038a0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038a0c3  mov     ebx, eax
0x18038a0c5  test    eax, eax
0x18038a0c7  js      loc_18038A16C
0x18038a0cd  xor     edx, edx
0x18038a0cf  mov     rcx, [rsp+78h+pv]
0x18038a0d4  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x18038a0da  mov     r14, rax
0x18038a0dd  test    rax, rax
0x18038a0e0  jz      short loc_18038A12F
0x18038a0e2  mov     r9, rax
0x18038a0e5  mov     r8d, 1
0x18038a0eb  lea     rdx, ?DescriptionProp@ConflictItemTile@@SAPEBUPropertyInfo@DirectUI@@XZ; ConflictItemTile::DescriptionProp(void)
0x18038a0f2  mov     rcx, rbp
0x18038a0f5  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18038a0fb  mov     ebx, eax
0x18038a0fd  mov     rcx, r14
0x18038a100  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18038a106  test    ebx, ebx
0x18038a108  js      short loc_18038A16C
0x18038a10a  mov     rdx, [rsp+78h+var_40]; unsigned __int16 *
0x18038a10f  mov     rcx, rbp; this
0x18038a112  call    ?SetSubText@ConflictItemTile@@AEAAJPEBG@Z; ConflictItemTile::SetSubText(ushort const *)
0x18038a117  mov     ebx, eax
0x18038a119  test    eax, eax
0x18038a11b  js      short loc_18038A16C
0x18038a11d  xor     edx, edx
0x18038a11f  mov     ecx, edi
0x18038a121  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x18038a127  mov     rdi, rax
0x18038a12a  test    rax, rax
0x18038a12d  jnz     short loc_18038A136
0x18038a12f  mov     ebx, 8007000Eh
0x18038a134  jmp     short loc_18038A16C
0x18038a136  mov     r9, rdi
0x18038a139  mov     r8d, 1
0x18038a13f  lea     rdx, ?ResponseProp@InterruptButton@@SAPEBUPropertyInfo@DirectUI@@XZ; InterruptButton::ResponseProp(void)
0x18038a146  mov     rcx, rbp
0x18038a149  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18038a14f  mov     ebx, eax
0x18038a151  mov     rcx, rdi
0x18038a154  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18038a15a  test    ebx, ebx
0x18038a15c  js      short loc_18038A16C
0x18038a15e  mov     rdx, rsi
0x18038a161  mov     rcx, rbp
0x18038a164  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18038a16a  mov     ebx, eax
0x18038a16c  mov     rcx, [rsp+78h+var_40]; pv
0x18038a171  call    cs:__imp_CoTaskMemFree
0x18038a177  nop
0x18038a178  mov     rcx, [rsp+78h+pv]; pv
0x18038a17d  call    cs:__imp_CoTaskMemFree
0x18038a183  test    ebx, ebx
0x18038a185  js      short loc_18038A196
0x18038a187  mov     rax, [rsp+78h+arg_28]
0x18038a18f  mov     [rbp+0E8h], rax
0x18038a196  mov     eax, ebx
0x18038a198  mov     rcx, [rsp+78h+var_38]
0x18038a19d  xor     rcx, rsp; StackCookie
0x18038a1a0  call    __security_check_cookie
0x18038a1a5  mov     rbx, [rsp+78h+arg_18]
0x18038a1ad  add     rsp, 50h
0x18038a1b1  pop     r14
0x18038a1b3  pop     r12
0x18038a1b5  pop     rdi
0x18038a1b6  pop     rsi
0x18038a1b7  pop     rbp
0x18038a1b8  retn
```
