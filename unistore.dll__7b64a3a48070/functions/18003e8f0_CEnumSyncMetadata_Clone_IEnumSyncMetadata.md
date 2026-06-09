# CEnumSyncMetadata::Clone(IEnumSyncMetadata * *)

- ea: `0x18003e8f0`
- end: `0x18003ec3c`
- name: `?Clone@CEnumSyncMetadata@@UEAAJPEAPEAUIEnumSyncMetadata@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(CEnumSyncMetadata *__hidden this, struct IEnumSyncMetadata **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180028ef4`
- `0x18002e3d0`
- `0x18003bf70`
- `0x18003e8f0`
- `0x18003ec44`
- `0x180078a40`
- `0x180078a8c`
- `0x1800bf7e0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ebf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ebf0`

## string_xrefs

- `0x18003eb06`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003eb3a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003eb66`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003eba8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003ebfe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`

## pseudocode

```c
__int64 __fastcall CEnumSyncMetadata::Clone(CEnumSyncMetadata *this, struct IEnumSyncMetadata **a2)
{
  __int64 v2; // rbx
  unsigned int v5; // ecx
  HLOCAL v6; // rdi
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // edi
  _DWORD *v10; // rsi
  __int64 i; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // r15d
  int v17; // eax
  __int64 v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  struct IUnknown *v21; // rdx
  __int64 v22; // r15
  __int64 v23; // rcx
  __int64 v24; // r15
  __int64 v25; // rcx
  void *v26; // rcx
  void *v27; // rdi
  unsigned int v29; // ebx
  __int64 v30; // [rsp+30h] [rbp-10h] BYREF
  __int64 v31; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v32; // [rsp+88h] [rbp+48h] BYREF
  __int64 v33; // [rsp+90h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v30 = 0;
  v31 = 0;
  v33 = 0;
  if ( !a2 )
  {
    v29 = -2147467261;
    Log_UnistoreHREvent_0(
      2147500035LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      339);
LABEL_37:
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return v29;
  }
  v5 = *((_DWORD *)this + 14);
  v6 = 0;
  hMem = 0;
  if ( !v5 )
  {
LABEL_5:
    v10 = 0;
    if ( !*((_DWORD *)this + 18) )
      goto LABEL_9;
    v10 = operator new[](saturated_mul(*((unsigned int *)this + 18), 4u));
    if ( v10 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); i = (unsigned int)(i + 1) )
        v10[i] = *(_DWORD *)(*((_QWORD *)this + 8) + 4 * i);
LABEL_9:
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 4) + 168LL))(
              *((_QWORD *)this + 4),
              &v33);
      v16 = v12;
      if ( v12 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v12,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
          364);
        if ( v6 )
          LocalFree(v6);
        if ( v10 )
          operator delete(v10);
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      else
      {
        v17 = CUSObjectInternal<CEnumSyncMetadata>::CreateInstance(&v30, v13, v14, v15);
        v16 = v17;
        if ( v17 >= 0 )
        {
          v18 = v30;
          if ( v30 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
            v2 = v18;
          }
          if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3)) )
            Log_AssertionEvent_30(v20, v19, 371);
          *(_DWORD *)(v2 + 76) = *((_DWORD *)this + 19);
          v21 = (struct IUnknown *)*((_QWORD *)this + 3);
          if ( *(struct IUnknown **)(v2 + 24) != v21 )
            ATL::AtlComPtrAssign((struct IUnknown **)(v2 + 24), v21);
          v22 = v33;
          if ( *(_QWORD *)(v2 + 32) != v33 )
          {
            if ( v33 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
            v23 = *(_QWORD *)(v2 + 32);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            *(_QWORD *)(v2 + 32) = v22;
          }
          v24 = *((_QWORD *)this + 5);
          if ( *(_QWORD *)(v2 + 40) != v24 )
          {
            if ( v24 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24 + 8LL))(*((_QWORD *)this + 5));
            v25 = *(_QWORD *)(v2 + 40);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            *(_QWORD *)(v2 + 40) = v24;
          }
          *(_DWORD *)(v2 + 56) = *((_DWORD *)this + 14);
          *(_DWORD *)(v2 + 72) = *((_DWORD *)this + 18);
          v26 = *(void **)(v2 + 48);
          *(_QWORD *)(v2 + 48) = v6;
          v27 = *(void **)(v2 + 64);
          *(_QWORD *)(v2 + 64) = v10;
          *a2 = (struct IEnumSyncMetadata *)v2;
          if ( v26 )
            LocalFree(v26);
          if ( v27 )
            operator delete(v27);
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          return 0;
        }
        Log_UnistoreHREvent_0(
          (unsigned int)v17,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
          367);
        auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
        if ( v10 )
          operator delete(v10);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v33);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
      }
      return v16;
    }
    v29 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      355);
    if ( v6 )
      LocalFree(v6);
    goto LABEL_37;
  }
  v7 = *((_QWORD *)this + 6);
  v32 = 0;
  v8 = USCopyPropVals(v5, v7, 1, &hMem, &v32);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v6 = hMem;
    goto LABEL_5;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v8,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
    348);
  if ( hMem )
    LocalFree(hMem);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return v9;
}

```

## disassembly

```asm
0x18003e8f0  push    rbp
0x18003e8f2  push    rbx
0x18003e8f3  push    rsi
0x18003e8f4  push    rdi
0x18003e8f5  push    r12
0x18003e8f7  push    r14
0x18003e8f9  push    r15
0x18003e8fb  mov     rbp, rsp
0x18003e8fe  sub     rsp, 40h
0x18003e902  xor     ebx, ebx
0x18003e904  mov     [rbp+var_10], 0
0x18003e90c  mov     [rbp+var_8], rbx
0x18003e910  mov     r12, rdx
0x18003e913  mov     [rbp+arg_10], rbx
0x18003e917  mov     r14, rcx
0x18003e91a  test    rdx, rdx
0x18003e91d  jz      loc_18003EB01
0x18003e923  mov     ecx, [rcx+38h]
0x18003e926  lea     r15d, [rbx+1]
0x18003e92a  xor     edi, edi
0x18003e92c  mov     [rbp+hMem], rdi
0x18003e930  test    ecx, ecx
0x18003e932  jz      short loc_18003E95E
0x18003e934  mov     rdx, [r14+30h]
0x18003e938  lea     rax, [rbp+arg_8]
0x18003e93c  lea     r9, [rbp+hMem]
0x18003e940  mov     [rsp+40h+var_20], rax
0x18003e945  mov     r8d, r15d
0x18003e948  mov     [rbp+arg_8], ebx
0x18003e94b  call    USCopyPropVals
0x18003e950  mov     edi, eax
0x18003e952  test    eax, eax
0x18003e954  js      loc_18003EB60
0x18003e95a  mov     rdi, [rbp+hMem]
0x18003e95e  xor     esi, esi
0x18003e960  cmp     [r14+48h], ebx
0x18003e964  jbe     short loc_18003E9AA
0x18003e966  mov     ecx, [r14+48h]
0x18003e96a  lea     eax, [rsi+4]
0x18003e96d  mul     rcx
0x18003e970  lea     rcx, [rsi-1]
0x18003e974  cmovb   rax, rcx
0x18003e978  mov     rcx, rax; unsigned __int64
0x18003e97b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003e980  mov     rsi, rax
0x18003e983  test    rax, rax
0x18003e986  jz      loc_18003EB35
0x18003e98c  xor     r8d, r8d
0x18003e98f  cmp     [r14+48h], ebx
0x18003e993  jbe     short loc_18003E9AA
0x18003e995  mov     rax, [r14+40h]
0x18003e999  mov     ecx, [rax+r8*4]
0x18003e99d  mov     [rsi+r8*4], ecx
0x18003e9a1  add     r8d, r15d
0x18003e9a4  cmp     r8d, [r14+48h]
0x18003e9a8  jb      short loc_18003E995
0x18003e9aa  mov     rcx, [r14+20h]
0x18003e9ae  lea     rdx, [rbp+arg_10]
0x18003e9b2  mov     rax, [rcx]
0x18003e9b5  mov     rax, [rax+0A8h]
0x18003e9bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9c1  mov     r15d, eax
0x18003e9c4  test    eax, eax
0x18003e9c6  js      loc_18003EBA2
0x18003e9cc  lea     rcx, [rbp+var_10]
0x18003e9d0  call    ?CreateInstance@?$CUSObjectInternal@VCEnumSyncMetadata@@@@SAJPEAPEAVCEnumSyncMetadata@@@Z; CUSObjectInternal<CEnumSyncMetadata>::CreateInstance(CEnumSyncMetadata * *)
0x18003e9d5  mov     r15d, eax
0x18003e9d8  test    eax, eax
0x18003e9da  js      loc_18003EBF8
0x18003e9e0  mov     r15, [rbp+var_10]
0x18003e9e4  test    r15, r15
0x18003e9e7  jz      short loc_18003E9FB
0x18003e9e9  mov     rax, [r15]
0x18003e9ec  mov     rcx, r15
0x18003e9ef  mov     rax, [rax+8]
0x18003e9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9f8  mov     rbx, r15
0x18003e9fb  mov     rcx, [r14+18h]
0x18003e9ff  mov     rax, [rcx]
0x18003ea02  mov     rax, [rax+38h]
0x18003ea06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea0b  test    eax, eax
0x18003ea0d  jnz     short loc_18003EA1A
0x18003ea0f  mov     r8d, 173h
0x18003ea15  call    Log_AssertionEvent_30
0x18003ea1a  mov     eax, [r14+4Ch]
0x18003ea1e  lea     rcx, [rbx+18h]; struct IUnknown **
0x18003ea22  mov     [rbx+4Ch], eax
0x18003ea25  mov     rdx, [r14+18h]; struct IUnknown *
0x18003ea29  cmp     [rcx], rdx
0x18003ea2c  jz      short loc_18003EA33
0x18003ea2e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003ea33  mov     r15, [rbp+arg_10]
0x18003ea37  cmp     [rbx+20h], r15
0x18003ea3b  jz      short loc_18003EA6A
0x18003ea3d  test    r15, r15
0x18003ea40  jz      short loc_18003EA51
0x18003ea42  mov     rax, [r15]
0x18003ea45  mov     rcx, r15
0x18003ea48  mov     rax, [rax+8]
0x18003ea4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea51  mov     rcx, [rbx+20h]
0x18003ea55  test    rcx, rcx
0x18003ea58  jz      short loc_18003EA66
0x18003ea5a  mov     rax, [rcx]
0x18003ea5d  mov     rax, [rax+10h]
0x18003ea61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea66  mov     [rbx+20h], r15
0x18003ea6a  mov     r15, [r14+28h]
0x18003ea6e  cmp     [rbx+28h], r15
0x18003ea72  jz      short loc_18003EAA1
0x18003ea74  test    r15, r15
0x18003ea77  jz      short loc_18003EA88
0x18003ea79  mov     rax, [r15]
0x18003ea7c  mov     rcx, r15
0x18003ea7f  mov     rax, [rax+8]
0x18003ea83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea88  mov     rcx, [rbx+28h]
0x18003ea8c  test    rcx, rcx
0x18003ea8f  jz      short loc_18003EA9D
0x18003ea91  mov     rax, [rcx]
0x18003ea94  mov     rax, [rax+10h]
0x18003ea98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea9d  mov     [rbx+28h], r15
0x18003eaa1  mov     eax, [r14+38h]
0x18003eaa5  mov     [rbx+38h], eax
0x18003eaa8  mov     eax, [r14+48h]
0x18003eaac  mov     [rbx+48h], eax
0x18003eaaf  mov     rcx, [rbx+30h]; hMem
0x18003eab3  mov     [rbx+30h], rdi
0x18003eab7  mov     rdi, [rbx+40h]
0x18003eabb  mov     [rbx+40h], rsi
0x18003eabf  mov     [r12], rbx
0x18003eac3  test    rcx, rcx
0x18003eac6  jz      short loc_18003EACE
0x18003eac8  call    cs:__imp_LocalFree
0x18003eace  test    rdi, rdi
0x18003ead1  jz      short loc_18003EADB
0x18003ead3  mov     rcx, rdi; Block
0x18003ead6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003eadb  mov     rcx, [rbp+arg_10]
0x18003eadf  test    rcx, rcx
0x18003eae2  jz      short loc_18003EAF0
0x18003eae4  mov     rax, [rcx]
0x18003eae7  mov     rax, [rax+10h]
0x18003eaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaf0  xor     eax, eax
0x18003eaf2  add     rsp, 40h
0x18003eaf6  pop     r15
0x18003eaf8  pop     r14
0x18003eafa  pop     r12
0x18003eafc  pop     rdi
0x18003eafd  pop     rsi
0x18003eafe  pop     rbx
0x18003eaff  pop     rbp
0x18003eb00  retn
0x18003eb01  mov     ebx, 80004003h
0x18003eb06  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003eb0d  mov     ecx, ebx
0x18003eb0f  mov     r9d, 153h
0x18003eb15  xor     edx, edx
0x18003eb17  call    Log_UnistoreHREvent_0
0x18003eb1c  mov     rcx, [rbp+arg_10]
0x18003eb20  test    rcx, rcx
0x18003eb23  jz      short loc_18003EB31
0x18003eb25  mov     rdx, [rcx]
0x18003eb28  mov     rax, [rdx+10h]
0x18003eb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb31  mov     eax, ebx
0x18003eb33  jmp     short loc_18003EAF2
0x18003eb35  mov     ebx, 8007000Eh
0x18003eb3a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003eb41  mov     ecx, ebx
0x18003eb43  mov     r9d, 163h
0x18003eb49  xor     edx, edx
0x18003eb4b  call    Log_UnistoreHREvent_0
0x18003eb50  test    rdi, rdi
0x18003eb53  jz      short loc_18003EB1C
0x18003eb55  mov     rcx, rdi; hMem
0x18003eb58  call    cs:__imp_LocalFree
0x18003eb5e  jmp     short loc_18003EB1C
0x18003eb60  mov     r9d, 15Ch
0x18003eb66  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003eb6d  mov     edx, r15d
0x18003eb70  mov     ecx, edi
0x18003eb72  call    Log_UnistoreHREvent_0
0x18003eb77  mov     rcx, [rbp+hMem]; hMem
0x18003eb7b  test    rcx, rcx
0x18003eb7e  jz      short loc_18003EB86
0x18003eb80  call    cs:__imp_LocalFree
0x18003eb86  mov     rcx, [rbp+arg_10]
0x18003eb8a  test    rcx, rcx
0x18003eb8d  jz      short loc_18003EB9B
0x18003eb8f  mov     rax, [rcx]
0x18003eb92  mov     rax, [rax+10h]
0x18003eb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb9b  mov     eax, edi
0x18003eb9d  jmp     loc_18003EAF2
0x18003eba2  mov     r9d, 16Ch
0x18003eba8  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003ebaf  mov     edx, 1
0x18003ebb4  mov     ecx, r15d
0x18003ebb7  call    Log_UnistoreHREvent_0
0x18003ebbc  test    rdi, rdi
0x18003ebbf  jnz     short loc_18003EBED
0x18003ebc1  test    rsi, rsi
0x18003ebc4  jnz     short loc_18003EBE3
0x18003ebc6  mov     rcx, [rbp+arg_10]
0x18003ebca  test    rcx, rcx
0x18003ebcd  jz      short loc_18003EBDB
0x18003ebcf  mov     rax, [rcx]
0x18003ebd2  mov     rax, [rax+10h]
0x18003ebd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebdb  mov     eax, r15d
0x18003ebde  jmp     loc_18003EAF2
0x18003ebe3  mov     rcx, rsi; Block
0x18003ebe6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ebeb  jmp     short loc_18003EBC6
0x18003ebed  mov     rcx, rdi; hMem
0x18003ebf0  call    cs:__imp_LocalFree
0x18003ebf6  jmp     short loc_18003EBC1
0x18003ebf8  mov     r9d, 16Fh
0x18003ebfe  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003ec05  mov     edx, 1
0x18003ec0a  mov     ecx, r15d
0x18003ec0d  call    Log_UnistoreHREvent_0
0x18003ec12  lea     rcx, [rbp+hMem]
0x18003ec16  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18003ec1b  test    rsi, rsi
0x18003ec1e  jz      short loc_18003EC28
0x18003ec20  mov     rcx, rsi; Block
0x18003ec23  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ec28  lea     rcx, [rbp+arg_10]; void *
0x18003ec2c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003ec31  lea     rcx, [rbp+var_8]; void *
0x18003ec35  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003ec3a  jmp     short loc_18003EBDB
```
