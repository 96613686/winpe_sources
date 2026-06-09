# CFileSource::Save(ICachedPrivateProfile *)

- ea: `0x180034b08`
- end: `0x180034d53`
- name: `?Save@CFileSource@@QEAAJPEAUICachedPrivateProfile@@@Z`
- size: `587`
- prototype: `int(CFileSource *__hidden this, struct ICachedPrivateProfile *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049300`
- `0x1800613a0`

## callees

- `0x1800089c0`
- `0x1800179e0`
- `0x180034b08`
- `0x1800358c0`
- `0x18003630c`
- `0x180060d9c`
- `0x180061018`
- `0x180061090`
- `0x18006d010`

## import_xrefs

- `SHELL32!__imp_ILFindChild` at `0x180034c0b`
- `SHELL32!__imp_ILFindChild` at `0x180034c0b`
- `SHELL32!__imp_ILGetSize` at `0x180034c18`
- `SHELL32!__imp_ILGetSize` at `0x180034c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034c84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d24`

## pseudocode

```c
__int64 __fastcall CFileSource::Save(CFileSource *this, struct ICachedPrivateProfile *a2)
{
  const struct _ITEMIDLIST_RELATIVE *v2; // r8
  unsigned int v5; // r13d
  int v6; // edi
  __int64 v7; // rax
  void *v8; // rbx
  LPVOID v9; // r8
  void *v10; // rsi
  int **v11; // r12
  int *v12; // r12
  int v13; // r12d
  unsigned int v14; // r14d
  unsigned int v15; // ebx
  CFileSource *v16; // rcx
  const ITEMIDLIST *Ptr; // rax
  UINT v18; // eax
  __int64 v19; // rax
  void *v20; // rbx
  __int64 (__fastcall *v21)(struct ICachedPrivateProfile *, unsigned __int16 *, void *); // rax
  int v22; // eax
  void *v23; // rbx
  void *v24; // r8
  __int64 v26; // [rsp+20h] [rbp-49h]
  LPVOID pv; // [rsp+30h] [rbp-39h] BYREF
  __int64 v28; // [rsp+38h] [rbp-31h]
  unsigned int v29; // [rsp+40h] [rbp-29h]
  CFileSource *v30; // [rsp+48h] [rbp-21h]
  struct _ITEMIDLIST_RELATIVE *v31; // [rsp+50h] [rbp-19h]
  unsigned __int16 v32[24]; // [rsp+58h] [rbp-11h] BYREF

  v2 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)this + 1);
  v30 = this;
  v5 = 0;
  pv = 0;
  v28 = 0;
  v6 = CFileSource::s_SavePIDL((struct CMultiSzBuilderW *)&pv, L"ImagesRootPIDL", v2);
  if ( v6 < 0 )
  {
    v10 = pv;
    goto LABEL_22;
  }
  v7 = *(_QWORD *)a2;
  v8 = pv;
  v9 = pv;
  pv = 0;
  v10 = 0;
  v28 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, LPVOID))(v7 + 88))(
         a2,
         L"Slideshow",
         v9);
  CoTaskMemFree(v8);
  if ( v6 >= 0 )
  {
    v11 = (int **)*((_QWORD *)this + 2);
    if ( v11 && (v12 = *v11) != 0 )
      v13 = *v12;
    else
      v13 = 0;
    v14 = 1;
    v15 = 0;
    v29 = (int)(float)(o_sqrtf_0((float)v13) + 1.0);
    while ( 1 )
    {
      if ( v5 >= v13 )
      {
        if ( !v15 )
          goto LABEL_20;
        LODWORD(v26) = v14;
        v6 = StringCchPrintfW(v32, 0x15u, L"%s%u", L"Slideshow", v26);
        if ( v6 >= 0 )
        {
          v23 = v10;
          v24 = v10;
          v10 = 0;
          v6 = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, void *))(*(_QWORD *)a2 + 88LL))(
                 a2,
                 v32,
                 v24);
          CoTaskMemFree(v23);
          ++v14;
          if ( v6 >= 0 )
LABEL_20:
            CFileSource::_RemoveExtraSections(v16, a2, v14);
        }
        goto LABEL_22;
      }
      Ptr = (const ITEMIDLIST *)g_pfn_DPA_GetPtr(**((HDPA **)v30 + 2), v5);
      v31 = (struct _ITEMIDLIST_RELATIVE *)ILFindChild(*((LPITEMIDLIST *)v30 + 1), Ptr);
      v18 = ILGetSize((LPCITEMIDLIST)v31);
      v16 = (CFileSource *)(2 * ((unsigned int)v28 + v18) + 40);
      if ( (unsigned int)v16 <= 0x100000 && v15 < v29 )
        goto LABEL_13;
      LODWORD(v26) = v14;
      v6 = StringCchPrintfW(v32, 0x15u, L"%s%u", L"Slideshow", v26);
      if ( v6 >= 0 )
        break;
LABEL_15:
      ++v15;
      ++v5;
      if ( v6 < 0 )
        goto LABEL_22;
    }
    v19 = *(_QWORD *)a2;
    v20 = v10;
    v10 = 0;
    pv = 0;
    v21 = *(__int64 (__fastcall **)(struct ICachedPrivateProfile *, unsigned __int16 *, void *))(v19 + 88);
    v28 = 0;
    v6 = v21(a2, v32, v20);
    CoTaskMemFree(v20);
    v15 = 0;
    ++v14;
LABEL_13:
    if ( v6 >= 0 )
    {
      v22 = CFileSource::s_SaveChildPIDL((struct CMultiSzBuilderW *)&pv, v31, v15);
      v10 = pv;
      v6 = v22;
    }
    goto LABEL_15;
  }
LABEL_22:
  CoTaskMemFree(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180034b08  mov     [rsp-8+arg_10], rbx
0x180034b0d  push    rbp
0x180034b0e  push    rsi
0x180034b0f  push    rdi
0x180034b10  push    r12
0x180034b12  push    r13
0x180034b14  push    r14
0x180034b16  push    r15
0x180034b18  lea     rbp, [rsp-27h]
0x180034b1d  sub     rsp, 90h
0x180034b24  mov     rax, cs:__security_cookie
0x180034b2b  xor     rax, rsp
0x180034b2e  mov     [rbp+57h+var_38], rax
0x180034b32  mov     r8, [rcx+8]; struct _ITEMIDLIST_RELATIVE *
0x180034b36  mov     r15, rdx
0x180034b39  mov     r14, rcx
0x180034b3c  mov     [rbp+57h+var_78], rcx
0x180034b40  xor     r13d, r13d
0x180034b43  lea     rdx, aImagesrootpidl; "ImagesRootPIDL"
0x180034b4a  lea     rcx, [rbp+57h+pv]; this
0x180034b4e  mov     [rbp+57h+pv], r13
0x180034b52  mov     [rbp+57h+var_88], r13
0x180034b56  call    ?s_SavePIDL@CFileSource@@CAJPEAVCMultiSzBuilderW@@PEBGPEFBU_ITEMIDLIST_RELATIVE@@@Z; CFileSource::s_SavePIDL(CMultiSzBuilderW *,ushort const *,_ITEMIDLIST_RELATIVE const *)
0x180034b5b  mov     edi, eax
0x180034b5d  test    eax, eax
0x180034b5f  js      loc_180034D1D
0x180034b65  mov     rax, [r15]
0x180034b68  lea     rdx, aSlideshow; "Slideshow"
0x180034b6f  mov     rbx, [rbp+57h+pv]
0x180034b73  mov     rcx, r15
0x180034b76  mov     r8, rbx
0x180034b79  mov     [rbp+57h+pv], r13
0x180034b7d  mov     esi, r13d
0x180034b80  mov     [rbp+57h+var_88], r13
0x180034b84  mov     rax, [rax+58h]
0x180034b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b8d  mov     rcx, rbx; pv
0x180034b90  mov     edi, eax
0x180034b92  call    cs:__imp_CoTaskMemFree
0x180034b98  test    edi, edi
0x180034b9a  js      loc_180034D21
0x180034ba0  mov     r12, [r14+10h]
0x180034ba4  test    r12, r12
0x180034ba7  jz      short loc_180034BB8
0x180034ba9  mov     r12, [r12]
0x180034bad  test    r12, r12
0x180034bb0  jz      short loc_180034BB8
0x180034bb2  mov     r12d, [r12]
0x180034bb6  jmp     short loc_180034BBB
0x180034bb8  mov     r12d, r13d
0x180034bbb  mov     eax, r12d
0x180034bbe  xorps   xmm0, xmm0
0x180034bc1  mov     r14d, 1
0x180034bc7  mov     ebx, r13d
0x180034bca  cvtsi2ss xmm0, rax; X
0x180034bcf  call    _o_sqrtf_0
0x180034bd4  addss   xmm0, cs:__real@3f800000
0x180034bdc  cvttss2si eax, xmm0
0x180034be0  mov     [rbp+57h+var_80], eax
0x180034be3  cmp     r13d, r12d
0x180034be6  jnb     loc_180034CB8
0x180034bec  mov     rcx, [rbp+57h+var_78]
0x180034bf0  mov     edx, r13d; i
0x180034bf3  mov     rcx, [rcx+10h]
0x180034bf7  mov     rcx, [rcx]; hdpa
0x180034bfa  call    cs:g_pfn_DPA_GetPtr
0x180034c00  mov     rdx, rax; pidlChild
0x180034c03  mov     rax, [rbp+57h+var_78]
0x180034c07  mov     rcx, [rax+8]; pidlParent
0x180034c0b  call    cs:__imp_ILFindChild
0x180034c11  mov     rcx, rax; pidl
0x180034c14  mov     [rbp+57h+var_70], rax
0x180034c18  call    cs:__imp_ILGetSize
0x180034c1e  add     eax, dword ptr [rbp+57h+var_88]
0x180034c21  lea     ecx, ds:28h[rax*2]
0x180034c28  cmp     ecx, 100000h
0x180034c2e  ja      short loc_180034C35
0x180034c30  cmp     ebx, [rbp+57h+var_80]
0x180034c33  jb      short loc_180034C8F
0x180034c35  lea     r9, aSlideshow; "Slideshow"
0x180034c3c  mov     [rsp+0C0h+var_A0], r14d
0x180034c41  lea     r8, aSU; "%s%u"
0x180034c48  mov     edx, 15h; unsigned __int64
0x180034c4d  lea     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x180034c51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034c56  mov     edi, eax
0x180034c58  test    eax, eax
0x180034c5a  js      short loc_180034CA9
0x180034c5c  mov     rax, [r15]
0x180034c5f  lea     rdx, [rbp+57h+var_68]
0x180034c63  mov     rbx, rsi
0x180034c66  mov     rcx, r15
0x180034c69  xor     esi, esi
0x180034c6b  mov     r8, rbx
0x180034c6e  mov     [rbp+57h+pv], rsi
0x180034c72  mov     rax, [rax+58h]
0x180034c76  mov     [rbp+57h+var_88], rsi
0x180034c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c7f  mov     rcx, rbx; pv
0x180034c82  mov     edi, eax
0x180034c84  call    cs:__imp_CoTaskMemFree
0x180034c8a  xor     ebx, ebx
0x180034c8c  inc     r14d
0x180034c8f  test    edi, edi
0x180034c91  js      short loc_180034CA9
0x180034c93  mov     rdx, [rbp+57h+var_70]; struct _ITEMIDLIST_RELATIVE *
0x180034c97  lea     rcx, [rbp+57h+pv]; this
0x180034c9b  mov     r8d, ebx; unsigned int
0x180034c9e  call    ?s_SaveChildPIDL@CFileSource@@CAJPEAVCMultiSzBuilderW@@PEFBU_ITEMIDLIST_RELATIVE@@K@Z; CFileSource::s_SaveChildPIDL(CMultiSzBuilderW *,_ITEMIDLIST_RELATIVE const *,ulong)
0x180034ca3  mov     rsi, [rbp+57h+pv]
0x180034ca7  mov     edi, eax
0x180034ca9  inc     ebx
0x180034cab  inc     r13d
0x180034cae  test    edi, edi
0x180034cb0  jns     loc_180034BE3
0x180034cb6  jmp     short loc_180034D21
0x180034cb8  test    ebx, ebx
0x180034cba  jz      short loc_180034D10
0x180034cbc  lea     r9, aSlideshow; "Slideshow"
0x180034cc3  mov     [rsp+0C0h+var_A0], r14d
0x180034cc8  lea     r8, aSU; "%s%u"
0x180034ccf  mov     edx, 15h; unsigned __int64
0x180034cd4  lea     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x180034cd8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034cdd  mov     edi, eax
0x180034cdf  test    eax, eax
0x180034ce1  js      short loc_180034D21
0x180034ce3  mov     rax, [r15]
0x180034ce6  lea     rdx, [rbp+57h+var_68]
0x180034cea  mov     rbx, rsi
0x180034ced  mov     rcx, r15
0x180034cf0  mov     r8, rbx
0x180034cf3  xor     esi, esi
0x180034cf5  mov     rax, [rax+58h]
0x180034cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cfe  mov     rcx, rbx; pv
0x180034d01  mov     edi, eax
0x180034d03  call    cs:__imp_CoTaskMemFree
0x180034d09  inc     r14d
0x180034d0c  test    edi, edi
0x180034d0e  js      short loc_180034D21
0x180034d10  mov     r8d, r14d; unsigned int
0x180034d13  mov     rdx, r15; struct ICachedPrivateProfile *
0x180034d16  call    ?_RemoveExtraSections@CFileSource@@AEAAXPEAUICachedPrivateProfile@@K@Z; CFileSource::_RemoveExtraSections(ICachedPrivateProfile *,ulong)
0x180034d1b  jmp     short loc_180034D21
0x180034d1d  mov     rsi, [rbp+57h+pv]
0x180034d21  mov     rcx, rsi; pv
0x180034d24  call    cs:__imp_CoTaskMemFree
0x180034d2a  mov     eax, edi
0x180034d2c  mov     rcx, [rbp+57h+var_38]
0x180034d30  xor     rcx, rsp; StackCookie
0x180034d33  call    __security_check_cookie
0x180034d38  mov     rbx, [rsp+0C0h+arg_10]
0x180034d40  add     rsp, 90h
0x180034d47  pop     r15
0x180034d49  pop     r14
0x180034d4b  pop     r13
0x180034d4d  pop     r12
0x180034d4f  pop     rdi
0x180034d50  pop     rsi
0x180034d51  pop     rbp
0x180034d52  retn
```
