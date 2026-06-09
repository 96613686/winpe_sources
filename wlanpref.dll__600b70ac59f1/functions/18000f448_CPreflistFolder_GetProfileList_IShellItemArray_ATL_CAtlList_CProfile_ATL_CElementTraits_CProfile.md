# CPreflistFolder::GetProfileList(IShellItemArray *,ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>> &)

- ea: `0x18000f448`
- end: `0x18000f5e4`
- name: `?GetProfileList@CPreflistFolder@@CAJPEAUIShellItemArray@@AEAV?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@@Z`
- size: `412`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e700`
- `0x18000f080`

## callees

- `0x180003458`
- `0x18000d4c8`
- `0x18000f448`
- `0x180011124`
- `0x180027594`
- `0x18002868c`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f59e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f59e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPreflistFolder::GetProfileList(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  unsigned int i; // edi
  int v6; // ebx
  _WORD *v7; // rdx
  unsigned __int16 v8; // ax
  _WORD *v9; // r8
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-59h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v14[96]; // [rsp+40h] [rbp-39h] BYREF

  v11 = 0;
  ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(a2);
  if ( !a1 )
    return 2147500037LL;
  result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 56LL))(a1, &v11);
  if ( (int)result >= 0 )
  {
    for ( i = 0; i < v11; ++i )
    {
      v10 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, i, &v10);
      if ( v6 < 0 )
        goto LABEL_17;
      v13 = 0;
      v6 = (**v10)(v10, &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5, &v13);
      if ( v6 < 0 )
        goto LABEL_16;
      pv = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v13 + 40LL))(v13, &pv);
      if ( v6 < 0 )
        goto LABEL_15;
      if ( !pv )
        goto LABEL_14;
      v7 = pv;
      v8 = *(_WORD *)pv;
      if ( !*(_WORD *)pv )
        goto LABEL_14;
      do
      {
        v9 = v7;
        v7 = (_WORD *)((char *)v7 + v8);
        v8 = *v7;
      }
      while ( *v7 );
      if ( !v9 )
      {
LABEL_14:
        v6 = -2147024809;
LABEL_15:
        CoTaskMemFree(pv);
        pv = 0;
LABEL_16:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
LABEL_17:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
        return (unsigned int)v6;
      }
      StructToProfile((CProfile *)v14, (const struct WPLDATA *)(v9 + 1));
      ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(a2, v14);
      CProfile::~CProfile((CProfile *)v14);
      CoTaskMemFree(pv);
      pv = 0;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f448  mov     [rsp-8+arg_10], rbx
0x18000f44d  push    rbp
0x18000f44e  push    rsi
0x18000f44f  push    rdi
0x18000f450  push    r14
0x18000f452  push    r15
0x18000f454  lea     rbp, [rsp-37h]
0x18000f459  sub     rsp, 0B0h
0x18000f460  mov     rax, cs:__security_cookie
0x18000f467  xor     rax, rsp
0x18000f46a  mov     [rbp+57h+var_30], rax
0x18000f46e  mov     r14, rdx
0x18000f471  mov     rsi, rcx
0x18000f474  xor     r15d, r15d
0x18000f477  mov     [rbp+57h+var_A8], r15d
0x18000f47b  mov     rcx, rdx
0x18000f47e  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x18000f483  test    rsi, rsi
0x18000f486  jnz     short loc_18000F492
0x18000f488  mov     eax, 80004005h
0x18000f48d  jmp     loc_18000F5C1
0x18000f492  mov     rax, [rsi]
0x18000f495  lea     rdx, [rbp+57h+var_A8]
0x18000f499  mov     rcx, rsi
0x18000f49c  mov     rax, [rax+38h]
0x18000f4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a5  test    eax, eax
0x18000f4a7  js      loc_18000F5C1
0x18000f4ad  mov     edi, r15d
0x18000f4b0  cmp     edi, [rbp+57h+var_A8]
0x18000f4b3  jnb     loc_18000F5BF
0x18000f4b9  mov     [rbp+57h+var_B0], r15
0x18000f4bd  mov     rax, [rsi]
0x18000f4c0  lea     r8, [rbp+57h+var_B0]
0x18000f4c4  mov     edx, edi
0x18000f4c6  mov     rcx, rsi
0x18000f4c9  mov     rax, [rax+40h]
0x18000f4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4d2  mov     ebx, eax
0x18000f4d4  test    eax, eax
0x18000f4d6  js      loc_18000F5B2
0x18000f4dc  mov     [rbp+57h+var_98], r15
0x18000f4e0  mov     rcx, [rbp+57h+var_B0]
0x18000f4e4  mov     rax, [rcx]
0x18000f4e7  lea     r8, [rbp+57h+var_98]
0x18000f4eb  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x18000f4f2  mov     rax, [rax]
0x18000f4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4fa  mov     ebx, eax
0x18000f4fc  test    eax, eax
0x18000f4fe  js      loc_18000F5A8
0x18000f504  mov     [rbp+57h+pv], r15
0x18000f508  mov     rcx, [rbp+57h+var_98]
0x18000f50c  mov     rax, [rcx]
0x18000f50f  lea     rdx, [rbp+57h+pv]
0x18000f513  mov     rax, [rax+28h]
0x18000f517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51c  mov     ebx, eax
0x18000f51e  mov     rcx, [rbp+57h+pv]; pv
0x18000f522  test    eax, eax
0x18000f524  js      short loc_18000F59E
0x18000f526  test    rcx, rcx
0x18000f529  jz      short loc_18000F599
0x18000f52b  mov     rdx, rcx
0x18000f52e  movzx   eax, word ptr [rcx]
0x18000f531  test    ax, ax
0x18000f534  jz      short loc_18000F599
0x18000f536  mov     r8, rdx
0x18000f539  movzx   eax, ax
0x18000f53c  add     rdx, rax
0x18000f53f  movzx   eax, word ptr [rdx]
0x18000f542  test    ax, ax
0x18000f545  jnz     short loc_18000F536
0x18000f547  test    r8, r8
0x18000f54a  jz      short loc_18000F599
0x18000f54c  lea     rdx, [r8+2]
0x18000f550  lea     rcx, [rbp+57h+var_90]
0x18000f554  call    ?StructToProfile@@YA?AVCProfile@@AEBUWPLDATA@@@Z; StructToProfile(WPLDATA const &)
0x18000f559  nop
0x18000f55a  lea     rdx, [rbp+57h+var_90]
0x18000f55e  mov     rcx, r14
0x18000f561  call    ?AddTail@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCProfile@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(CProfile const &)
0x18000f566  nop
0x18000f567  lea     rcx, [rbp+57h+var_90]; this
0x18000f56b  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000f570  nop
0x18000f571  mov     rcx, [rbp+57h+pv]; pv
0x18000f575  call    cs:__imp_CoTaskMemFree
0x18000f57b  mov     [rbp+57h+pv], r15
0x18000f57f  lea     rcx, [rbp+57h+var_98]
0x18000f583  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f588  nop
0x18000f589  lea     rcx, [rbp+57h+var_B0]
0x18000f58d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f592  inc     edi
0x18000f594  jmp     loc_18000F4B0
0x18000f599  mov     ebx, 80070057h
0x18000f59e  call    cs:__imp_CoTaskMemFree
0x18000f5a4  mov     [rbp+57h+pv], r15
0x18000f5a8  lea     rcx, [rbp+57h+var_98]
0x18000f5ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f5b1  nop
0x18000f5b2  lea     rcx, [rbp+57h+var_B0]
0x18000f5b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f5bb  mov     eax, ebx
0x18000f5bd  jmp     short loc_18000F5C1
0x18000f5bf  xor     eax, eax
0x18000f5c1  mov     rcx, [rbp+57h+var_30]
0x18000f5c5  xor     rcx, rsp; StackCookie
0x18000f5c8  call    __security_check_cookie
0x18000f5cd  mov     rbx, [rsp+0D0h+arg_10]
0x18000f5d5  add     rsp, 0B0h
0x18000f5dc  pop     r15
0x18000f5de  pop     r14
0x18000f5e0  pop     rdi
0x18000f5e1  pop     rsi
0x18000f5e2  pop     rbp
0x18000f5e3  retn
```
