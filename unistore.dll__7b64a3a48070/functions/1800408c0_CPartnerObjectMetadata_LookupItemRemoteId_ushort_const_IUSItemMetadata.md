# CPartnerObjectMetadata::LookupItemRemoteId(ushort const *,IUSItemMetadata * *)

- ea: `0x1800408c0`
- end: `0x180040bc1`
- name: `?LookupItemRemoteId@CPartnerObjectMetadata@@UEAAJPEBGPEAPEAUIUSItemMetadata@@@Z`
- size: `769`
- prototype: `int(CPartnerObjectMetadata *__hidden this, const unsigned __int16 *, struct IUSItemMetadata **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180028ef4`
- `0x1800408c0`
- `0x180040bc8`
- `0x180040de8`
- `0x180078a4c`
- `0x1800bd4e0`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a92`

## string_xrefs

- `0x180040aa8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\objectimpl.h`
- `0x180040abf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040ad6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040b1b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040b3b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`
- `0x180040b9b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\partnerobjectmetadata.cpp`

## pseudocode

```c
__int64 __fastcall CPartnerObjectMetadata::LookupItemRemoteId(
        CPartnerObjectMetadata *this,
        const unsigned __int16 *a2,
        struct IUSItemMetadata **a3)
{
  int ItemIdFromRemoteId; // ebx
  unsigned int v6; // r13d
  unsigned int v7; // esi
  __int64 v8; // r15
  unsigned int v9; // r14d
  void *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, __int64, _DWORD *, HLOCAL *, _QWORD); // r15
  __int64 v18; // rdx
  _DWORD *v19; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r9
  HLOCAL hMem; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v29[4]; // [rsp+48h] [rbp-18h] BYREF

  v27 = 0;
  if ( a3 )
  {
    *a3 = 0;
    ItemIdFromRemoteId = CPartnerObjectMetadata::GetItemIdFromRemoteId(
                           *((struct IDBVolume **)this + 5),
                           *((_DWORD *)this + 14),
                           a2,
                           &v27);
    if ( ItemIdFromRemoteId >= 0 )
    {
      v6 = v27;
      v7 = 1;
      if ( v27 == -1 )
        return v7;
      v8 = *((_QWORD *)this + 5);
      v28 = 0;
      *a3 = 0;
      if ( v8 )
      {
        v9 = -2147024882;
        v10 = operator new(0x50u);
        if ( !v10
          || (v11 = ATL::CComObject<CPartnerObjectMetadata>::CComObject<CPartnerObjectMetadata>(v10), (v12 = v11) == 0) )
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
LABEL_24:
          Log_UnistoreHREvent_0(
            v9,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
            1080);
          return v9;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        v13 = *(_QWORD *)(v12 + 48);
        v28 = v12;
        v29[0] = -2080309229;
        v29[1] = -2079784941;
        v29[2] = 131075;
        hMem = 0;
        if ( v13 != v8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
          v14 = *(_QWORD *)(v12 + 48);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          *(_QWORD *)(v12 + 48) = v8;
          v13 = v8;
        }
        *(_DWORD *)(v12 + 64) = v6;
        v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v13 + 48LL))(
                v13,
                15,
                v6,
                v12 + 56);
        v9 = v15;
        if ( v15 < 0 )
        {
          v25 = 1453;
        }
        else
        {
          v16 = *(_QWORD *)(v12 + 56);
          v17 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *, HLOCAL *, _QWORD))(*(_QWORD *)v16 + 40LL);
          if ( hMem )
            LocalFree(hMem);
          hMem = 0;
          v15 = v17(v16, 3, v29, &hMem, 0);
          v9 = v15;
          if ( v15 >= 0 )
          {
            v19 = hMem;
            if ( (*((_WORD *)hMem + 3) & 0x100) != 0 )
            {
              Log_AssertionEvent_27(hMem, v18, 1458);
              v19 = hMem;
            }
            *(_DWORD *)(v12 + 72) = v19[2] | 0x30000;
            if ( (*((_WORD *)v19 + 15) & 0x100) != 0 )
            {
              Log_AssertionEvent_27(v19, v18, 1461);
              v19 = hMem;
            }
            *(_DWORD *)(v12 + 68) = v19[8];
            if ( (*((_WORD *)v19 + 27) & 0x100) != 0 )
            {
              Log_AssertionEvent_27(v19, v18, 1464);
              v19 = hMem;
            }
            *(_DWORD *)(v12 + 76) = v19[14];
            LocalFree(v19);
            v7 = 0;
            *a3 = (struct IUSItemMetadata *)v12;
            return v7;
          }
          v25 = 1456;
        }
        Log_UnistoreHREvent_0(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
          v25);
        auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
        v23 = 470;
        v24 = 1;
      }
      else
      {
        v23 = 464;
        v24 = 0;
        v9 = -2147024809;
      }
      Log_UnistoreHREvent_0(
        v9,
        v24,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
        v23);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
      goto LABEL_24;
    }
    v21 = 1071;
    v22 = 1;
  }
  else
  {
    v21 = 1066;
    v22 = 0;
    ItemIdFromRemoteId = -2147467261;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)ItemIdFromRemoteId,
    v22,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\partnerobjectmetadata.cpp",
    v21);
  return (unsigned int)ItemIdFromRemoteId;
}

```

## disassembly

```asm
0x1800408c0  mov     [rsp-38h+arg_18], rbx
0x1800408c5  push    rbp
0x1800408c6  push    rsi
0x1800408c7  push    rdi
0x1800408c8  push    r12
0x1800408ca  push    r13
0x1800408cc  push    r14
0x1800408ce  push    r15
0x1800408d0  mov     rbp, rsp
0x1800408d3  sub     rsp, 60h
0x1800408d7  mov     rax, cs:__security_cookie
0x1800408de  xor     rax, rsp
0x1800408e1  mov     [rbp+var_8], rax
0x1800408e5  xor     r14d, r14d
0x1800408e8  mov     r12, r8
0x1800408eb  mov     [rbp+var_28], r14d
0x1800408ef  mov     r15, rcx
0x1800408f2  test    r8, r8
0x1800408f5  jz      loc_180040B0E
0x1800408fb  mov     [r8], r14
0x1800408fe  lea     r9, [rbp+var_28]; unsigned int *
0x180040902  mov     r8, rdx; unsigned __int16 *
0x180040905  mov     edx, [rcx+38h]; unsigned int
0x180040908  mov     rcx, [rcx+28h]; struct IDBVolume *
0x18004090c  call    ?GetItemIdFromRemoteId@CPartnerObjectMetadata@@SAJPEAVIDBVolume@@KPEBGPEAK@Z; CPartnerObjectMetadata::GetItemIdFromRemoteId(IDBVolume *,ulong,ushort const *,ulong *)
0x180040911  mov     ebx, eax
0x180040913  test    eax, eax
0x180040915  js      loc_180040B80
0x18004091b  mov     r13d, [rbp+var_28]
0x18004091f  lea     esi, [r14+1]
0x180040923  cmp     r13d, 0FFFFFFFFh
0x180040927  jz      loc_180040A9E
0x18004092d  mov     r15, [r15+28h]
0x180040931  mov     [rbp+var_20], r14
0x180040935  mov     [r12], r14
0x180040939  test    r15, r15
0x18004093c  jz      loc_180040B2D
0x180040942  lea     ecx, [rsi+4Fh]; Size
0x180040945  mov     r14d, 8007000Eh
0x18004094b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040950  test    rax, rax
0x180040953  jz      loc_180040AA2
0x180040959  mov     rcx, rax
0x18004095c  call    ??0?$CComObject@VCPartnerObjectMetadata@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPartnerObjectMetadata>::CComObject<CPartnerObjectMetadata>(void *)
0x180040961  mov     rbx, rax
0x180040964  test    rax, rax
0x180040967  jz      loc_180040AA2
0x18004096d  mov     rax, [rax]
0x180040970  mov     rcx, rbx
0x180040973  mov     rax, [rax+8]
0x180040977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004097c  mov     rcx, [rbx+30h]
0x180040980  mov     [rbp+var_20], rbx
0x180040984  mov     [rbp+var_18], 84010013h
0x18004098b  mov     [rbp+var_14], 84090013h
0x180040992  mov     [rbp+var_10], 20003h
0x180040999  mov     [rbp+hMem], 0
0x1800409a1  cmp     rcx, r15
0x1800409a4  jz      short loc_1800409D1
0x1800409a6  mov     rax, [r15]
0x1800409a9  mov     rcx, r15
0x1800409ac  mov     rax, [rax+8]
0x1800409b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409b5  mov     rcx, [rbx+30h]
0x1800409b9  test    rcx, rcx
0x1800409bc  jz      short loc_1800409CA
0x1800409be  mov     rax, [rcx]
0x1800409c1  mov     rax, [rax+10h]
0x1800409c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409ca  mov     [rbx+30h], r15
0x1800409ce  mov     rcx, r15
0x1800409d1  mov     [rbx+40h], r13d
0x1800409d5  lea     r9, [rbx+38h]
0x1800409d9  mov     rax, [rcx]
0x1800409dc  mov     r8d, r13d
0x1800409df  mov     edx, 0Fh
0x1800409e4  mov     rdi, rbx
0x1800409e7  mov     rax, [rax+30h]
0x1800409eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409f0  mov     r14d, eax
0x1800409f3  test    eax, eax
0x1800409f5  js      loc_180040B8D
0x1800409fb  mov     r14, [rbx+38h]
0x1800409ff  mov     rcx, [rbp+hMem]; hMem
0x180040a03  mov     rax, [r14]
0x180040a06  mov     r15, [rax+28h]
0x180040a0a  test    rcx, rcx
0x180040a0d  jz      short loc_180040A15
0x180040a0f  call    cs:__imp_LocalFree
0x180040a15  lea     r9, [rbp+hMem]
0x180040a19  mov     [rbp+hMem], 0
0x180040a21  lea     r8, [rbp+var_18]
0x180040a25  mov     [rsp+60h+var_40], 0
0x180040a2e  mov     edx, 3
0x180040a33  mov     rcx, r14
0x180040a36  mov     rax, r15
0x180040a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a3e  mov     r14d, eax
0x180040a41  test    eax, eax
0x180040a43  js      loc_180040B95
0x180040a49  mov     rcx, [rbp+hMem]
0x180040a4d  mov     esi, 100h
0x180040a52  test    [rcx+6], si
0x180040a56  jz      short loc_180040A67
0x180040a58  mov     r8d, 5B2h
0x180040a5e  call    Log_AssertionEvent_27
0x180040a63  mov     rcx, [rbp+hMem]; hMem
0x180040a67  mov     eax, [rcx+8]
0x180040a6a  or      eax, 30000h
0x180040a6f  mov     [rdi+48h], eax
0x180040a72  test    [rcx+1Eh], si
0x180040a76  jnz     loc_180040B58
0x180040a7c  mov     eax, [rcx+20h]
0x180040a7f  mov     [rdi+44h], eax
0x180040a82  test    [rcx+36h], si
0x180040a86  jnz     loc_180040B6C
0x180040a8c  mov     eax, [rcx+38h]
0x180040a8f  mov     [rdi+4Ch], eax
0x180040a92  call    cs:__imp_LocalFree
0x180040a98  xor     esi, esi
0x180040a9a  mov     [r12], rbx
0x180040a9e  mov     eax, esi
0x180040aa0  jmp     short loc_180040AEA
0x180040aa2  mov     r9d, 179h
0x180040aa8  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040aaf  mov     edx, esi
0x180040ab1  mov     ecx, r14d
0x180040ab4  call    Log_UnistoreHREvent_0
0x180040ab9  mov     r9d, 1D3h
0x180040abf  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040ac6  mov     edx, esi
0x180040ac8  mov     ecx, r14d
0x180040acb  call    Log_UnistoreHREvent_0
0x180040ad0  mov     r9d, 438h
0x180040ad6  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040add  mov     edx, esi
0x180040adf  mov     ecx, r14d
0x180040ae2  call    Log_UnistoreHREvent_0
0x180040ae7  mov     eax, r14d
0x180040aea  mov     rcx, [rbp+var_8]
0x180040aee  xor     rcx, rsp; StackCookie
0x180040af1  call    __security_check_cookie
0x180040af6  mov     rbx, [rsp+60h+arg_18]
0x180040afe  add     rsp, 60h
0x180040b02  pop     r15
0x180040b04  pop     r14
0x180040b06  pop     r13
0x180040b08  pop     r12
0x180040b0a  pop     rdi
0x180040b0b  pop     rsi
0x180040b0c  pop     rbp
0x180040b0d  retn
0x180040b0e  mov     r9d, 42Ah
0x180040b14  xor     edx, edx
0x180040b16  mov     ebx, 80004003h
0x180040b1b  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040b22  mov     ecx, ebx
0x180040b24  call    Log_UnistoreHREvent_0
0x180040b29  mov     eax, ebx
0x180040b2b  jmp     short loc_180040AEA
0x180040b2d  mov     r9d, 1D0h
0x180040b33  xor     edx, edx
0x180040b35  mov     r14d, 80070057h
0x180040b3b  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040b42  mov     ecx, r14d
0x180040b45  call    Log_UnistoreHREvent_0
0x180040b4a  lea     rcx, [rbp+var_20]; void *
0x180040b4e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180040b53  jmp     loc_180040AD0
0x180040b58  mov     r8d, 5B5h
0x180040b5e  call    Log_AssertionEvent_27
0x180040b63  mov     rcx, [rbp+hMem]
0x180040b67  jmp     loc_180040A7C
0x180040b6c  mov     r8d, 5B8h
0x180040b72  call    Log_AssertionEvent_27
0x180040b77  mov     rcx, [rbp+hMem]
0x180040b7b  jmp     loc_180040A8C
0x180040b80  mov     r9d, 42Fh
0x180040b86  mov     edx, 1
0x180040b8b  jmp     short loc_180040B1B
0x180040b8d  mov     r9d, 5ADh
0x180040b93  jmp     short loc_180040B9B
0x180040b95  mov     r9d, 5B0h
0x180040b9b  lea     r8, aOnecoreuapBase_56; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180040ba2  mov     edx, esi
0x180040ba4  mov     ecx, eax
0x180040ba6  call    Log_UnistoreHREvent_0
0x180040bab  lea     rcx, [rbp+hMem]
0x180040baf  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180040bb4  mov     r9d, 1D6h
0x180040bba  mov     edx, esi
0x180040bbc  jmp     loc_180040B3B
```
