# CPartnerObjectMetadata::CreateItemInstance(IDBVolume *,ulong,IUSItemMetadata * *)

- ea: `0x180040618`
- end: `0x1800408ad`
- name: `?CreateItemInstance@CPartnerObjectMetadata@@SAJPEAVIDBVolume@@KPEAPEAUIUSItemMetadata@@@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct IDBVolume *, unsigned int, struct IUSItemMetadata **)`
- caller_count: `5`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003f150`
- `0x18005d2f0`
- `0x180064dc0`
- `0x180065210`
- `0x1800be160`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180028ef4`
- `0x180040618`
- `0x180040de8`
- `0x180078a4c`
- `0x1800bd4e0`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004072b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800407c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004072b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800407c3`

## string_xrefs

- `0x1800407f9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\objectimpl.h`
- `0x180040813`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040831`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040858`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040884`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`

## pseudocode

```c
__int64 __fastcall CPartnerObjectMetadata::CreateItemInstance(
        struct IDBVolume *a1,
        unsigned int a2,
        struct IUSItemMetadata **a3)
{
  void *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  struct IDBVolume *v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _DWORD *, HLOCAL *, _QWORD); // r15
  __int64 v15; // rdx
  _DWORD *v16; // rcx
  __int64 result; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r9
  HLOCAL hMem; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v23[4]; // [rsp+40h] [rbp-20h] BYREF

  v22 = 0;
  if ( !a3 )
  {
    Log_UnistoreHREvent_0(
      2147500035LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
      461);
    return 2147500035LL;
  }
  *a3 = 0;
  if ( !a1 )
  {
    v18 = 464;
    v19 = 0;
    v12 = -2147024809;
LABEL_23:
    Log_UnistoreHREvent_0(
      v12,
      v19,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
      v18);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v22);
    return v12;
  }
  v6 = operator new(0x50u);
  if ( !v6 || (v7 = ATL::CComObject<CPartnerObjectMetadata>::CComObject<CPartnerObjectMetadata>(v6), (v8 = v7) == 0) )
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\objectimpl.h",
      377);
    Log_UnistoreHREvent_0(
      2147942414LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
      467);
    return 2147942414LL;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v9 = *(struct IDBVolume **)(v8 + 48);
  v22 = v8;
  v23[0] = -2080309229;
  v23[1] = -2079784941;
  v23[2] = 131075;
  hMem = 0;
  if ( v9 != a1 )
  {
    (*(void (__fastcall **)(struct IDBVolume *))(*(_QWORD *)a1 + 8LL))(a1);
    v10 = *(_QWORD *)(v8 + 48);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *(_QWORD *)(v8 + 48) = a1;
    v9 = a1;
  }
  *(_DWORD *)(v8 + 64) = a2;
  v11 = (*(__int64 (__fastcall **)(struct IDBVolume *, __int64, _QWORD, __int64))(*(_QWORD *)v9 + 48LL))(
          v9,
          15,
          a2,
          v8 + 56);
  v12 = v11;
  if ( v11 < 0 )
  {
    v20 = 1453;
LABEL_26:
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
      v20);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    v18 = 470;
    v19 = 1;
    goto LABEL_23;
  }
  v13 = *(_QWORD *)(v8 + 56);
  v14 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *, HLOCAL *, _QWORD))(*(_QWORD *)v13 + 40LL);
  if ( hMem )
    LocalFree(hMem);
  hMem = 0;
  v11 = v14(v13, 3, v23, &hMem, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    v20 = 1456;
    goto LABEL_26;
  }
  v16 = hMem;
  if ( (*((_WORD *)hMem + 3) & 0x100) != 0 )
  {
    Log_AssertionEvent_27(hMem, v15, 1458);
    v16 = hMem;
  }
  *(_DWORD *)(v8 + 72) = v16[2] | 0x30000;
  if ( (*((_WORD *)v16 + 15) & 0x100) != 0 )
  {
    Log_AssertionEvent_27(v16, v15, 1461);
    v16 = hMem;
  }
  *(_DWORD *)(v8 + 68) = v16[8];
  if ( (*((_WORD *)v16 + 27) & 0x100) != 0 )
  {
    Log_AssertionEvent_27(v16, v15, 1464);
    v16 = hMem;
  }
  *(_DWORD *)(v8 + 76) = v16[14];
  LocalFree(v16);
  result = 0;
  *a3 = (struct IUSItemMetadata *)v8;
  return result;
}

```

## disassembly

```asm
0x180040618  mov     [rsp-28h+arg_8], rbx
0x18004061d  mov     [rsp-28h+arg_18], rsi
0x180040622  push    rbp
0x180040623  push    rdi
0x180040624  push    r12
0x180040626  push    r14
0x180040628  push    r15
0x18004062a  mov     rbp, rsp
0x18004062d  sub     rsp, 60h
0x180040631  mov     rax, cs:__security_cookie
0x180040638  xor     rax, rsp
0x18004063b  mov     [rbp+var_10], rax
0x18004063f  xor     edi, edi
0x180040641  mov     r14, r8
0x180040644  mov     [rbp+var_28], rdi
0x180040648  mov     r12d, edx
0x18004064b  mov     rsi, rcx
0x18004064e  test    r8, r8
0x180040651  jz      loc_18004082C
0x180040657  mov     [r8], rdi
0x18004065a  test    rcx, rcx
0x18004065d  jz      loc_18004084B
0x180040663  lea     ecx, [rdi+50h]; Size
0x180040666  mov     r15d, 8007000Eh
0x18004066c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040671  test    rax, rax
0x180040674  jz      loc_1800407F3
0x18004067a  mov     rcx, rax
0x18004067d  call    ??0?$CComObject@VCPartnerObjectMetadata@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPartnerObjectMetadata>::CComObject<CPartnerObjectMetadata>(void *)
0x180040682  mov     rbx, rax
0x180040685  test    rax, rax
0x180040688  jz      loc_1800407F3
0x18004068e  mov     rax, [rax]
0x180040691  mov     rcx, rbx
0x180040694  mov     rax, [rax+8]
0x180040698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004069d  mov     rcx, [rbx+30h]
0x1800406a1  mov     [rbp+var_28], rbx
0x1800406a5  mov     [rbp+var_20], 84010013h
0x1800406ac  mov     [rbp+var_1C], 84090013h
0x1800406b3  mov     [rbp+var_18], 20003h
0x1800406ba  mov     [rbp+hMem], rdi
0x1800406be  cmp     rcx, rsi
0x1800406c1  jz      short loc_1800406EE
0x1800406c3  mov     rax, [rsi]
0x1800406c6  mov     rcx, rsi
0x1800406c9  mov     rax, [rax+8]
0x1800406cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406d2  mov     rcx, [rbx+30h]
0x1800406d6  test    rcx, rcx
0x1800406d9  jz      short loc_1800406E7
0x1800406db  mov     rax, [rcx]
0x1800406de  mov     rax, [rax+10h]
0x1800406e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406e7  mov     [rbx+30h], rsi
0x1800406eb  mov     rcx, rsi
0x1800406ee  mov     [rbx+40h], r12d
0x1800406f2  lea     r9, [rbx+38h]
0x1800406f6  mov     rax, [rcx]
0x1800406f9  mov     r8d, r12d
0x1800406fc  mov     edx, 0Fh
0x180040701  mov     rsi, rbx
0x180040704  mov     rax, [rax+30h]
0x180040708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004070d  mov     edi, eax
0x18004070f  test    eax, eax
0x180040711  js      loc_180040876
0x180040717  mov     rdi, [rbx+38h]
0x18004071b  mov     rcx, [rbp+hMem]; hMem
0x18004071f  mov     rax, [rdi]
0x180040722  mov     r15, [rax+28h]
0x180040726  test    rcx, rcx
0x180040729  jz      short loc_180040731
0x18004072b  call    cs:__imp_LocalFree
0x180040731  lea     r9, [rbp+hMem]
0x180040735  mov     [rbp+hMem], 0
0x18004073d  lea     r8, [rbp+var_20]
0x180040741  mov     [rsp+60h+var_40], 0
0x18004074a  mov     edx, 3
0x18004074f  mov     rcx, rdi
0x180040752  mov     rax, r15
0x180040755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004075a  mov     edi, eax
0x18004075c  test    eax, eax
0x18004075e  js      loc_18004087E
0x180040764  mov     rcx, [rbp+hMem]
0x180040768  mov     edi, 100h
0x18004076d  test    [rcx+6], di
0x180040771  jz      short loc_180040782
0x180040773  mov     r8d, 5B2h
0x180040779  call    Log_AssertionEvent_27
0x18004077e  mov     rcx, [rbp+hMem]
0x180040782  mov     eax, [rcx+8]
0x180040785  or      eax, 30000h
0x18004078a  mov     [rsi+48h], eax
0x18004078d  test    [rcx+1Eh], di
0x180040791  jz      short loc_1800407A2
0x180040793  mov     r8d, 5B5h
0x180040799  call    Log_AssertionEvent_27
0x18004079e  mov     rcx, [rbp+hMem]
0x1800407a2  mov     eax, [rcx+20h]
0x1800407a5  mov     [rsi+44h], eax
0x1800407a8  test    [rcx+36h], di
0x1800407ac  jz      short loc_1800407BD
0x1800407ae  mov     r8d, 5B8h
0x1800407b4  call    Log_AssertionEvent_27
0x1800407b9  mov     rcx, [rbp+hMem]; hMem
0x1800407bd  mov     eax, [rcx+38h]
0x1800407c0  mov     [rsi+4Ch], eax
0x1800407c3  call    cs:__imp_LocalFree
0x1800407c9  xor     eax, eax
0x1800407cb  mov     [r14], rbx
0x1800407ce  mov     rcx, [rbp+var_10]
0x1800407d2  xor     rcx, rsp; StackCookie
0x1800407d5  call    __security_check_cookie
0x1800407da  lea     r11, [rsp+60h+var_s0]
0x1800407df  mov     rbx, [r11+38h]
0x1800407e3  mov     rsi, [r11+48h]
0x1800407e7  mov     rsp, r11
0x1800407ea  pop     r15
0x1800407ec  pop     r14
0x1800407ee  pop     r12
0x1800407f0  pop     rdi
0x1800407f1  pop     rbp
0x1800407f2  retn
0x1800407f3  mov     r9d, 179h
0x1800407f9  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040800  mov     edx, 1
0x180040805  mov     ecx, r15d
0x180040808  call    Log_UnistoreHREvent_0
0x18004080d  mov     r9d, 1D3h
0x180040813  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004081a  mov     edx, 1
0x18004081f  mov     ecx, r15d
0x180040822  call    Log_UnistoreHREvent_0
0x180040827  mov     eax, r15d
0x18004082a  jmp     short loc_1800407CE
0x18004082c  mov     ebx, 80004003h
0x180040831  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040838  mov     ecx, ebx
0x18004083a  mov     r9d, 1CDh
0x180040840  xor     edx, edx
0x180040842  call    Log_UnistoreHREvent_0
0x180040847  mov     eax, ebx
0x180040849  jmp     short loc_1800407CE
0x18004084b  mov     r9d, 1D0h
0x180040851  xor     edx, edx
0x180040853  mov     edi, 80070057h
0x180040858  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004085f  mov     ecx, edi
0x180040861  call    Log_UnistoreHREvent_0
0x180040866  lea     rcx, [rbp+var_28]; void *
0x18004086a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18004086f  mov     eax, edi
0x180040871  jmp     loc_1800407CE
0x180040876  mov     r9d, 5ADh
0x18004087c  jmp     short loc_180040884
0x18004087e  mov     r9d, 5B0h
0x180040884  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004088b  mov     edx, 1
0x180040890  mov     ecx, eax
0x180040892  call    Log_UnistoreHREvent_0
0x180040897  lea     rcx, [rbp+hMem]
0x18004089b  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x1800408a0  mov     r9d, 1D6h
0x1800408a6  mov     edx, 1
0x1800408ab  jmp     short loc_180040858
```
