# CImageCache::GetClientImages(void *,ulong,CWdsMetadata const *,CDynArray<CImageCache::Image *,CDeallocatePointer> *)

- ea: `0x18000891c`
- end: `0x180008c69`
- name: `?GetClientImages@CImageCache@@QEAAKPEAXKPEBVCWdsMetadata@@PEAV?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@@Z`
- size: `845`
- prototype: `__int64 __usercall@<rax>(struct CMRSWLock *@<rcx>, HANDLE ClientToken@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007c28`

## callees

- `0x180002878`
- `0x1800029e8`
- `0x1800080d0`
- `0x180008150`
- `0x1800081d0`
- `0x18000891c`
- `0x18000aeac`
- `0x18000c590`
- `0x180012c20`
- `0x180017010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008aa8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008abe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008c1c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008aa8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008abe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008c1c`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180008c45`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180008c45`

## string_xrefs

- `0x1800089a9`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x180008a20`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x180008a7c`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x180008adc`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x180008b0b`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`

## pseudocode

```c
__int64 __fastcall CImageCache::GetClientImages(
        struct CMRSWLock *a1,
        HANDLE ClientToken,
        int a3,
        __int64 a4,
        __int64 a5)
{
  HANDLE v5; // r14
  struct CMRSWLock *v6; // rbx
  CImageCache::Image *v7; // r13
  __int64 v8; // r15
  __int64 v9; // rsi
  char v10; // di
  unsigned int i; // eax
  __int64 v12; // rdx
  struct Image *v13; // r12
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // edx
  __int64 v20; // rdx
  const wchar_t *v21; // r14
  void **v23; // [rsp+28h] [rbp-B1h]
  __int64 v24; // [rsp+30h] [rbp-A9h]
  __int64 v25; // [rsp+38h] [rbp-A1h]
  __int64 v26; // [rsp+40h] [rbp-99h]
  __int64 v27; // [rsp+48h] [rbp-91h]
  __int64 v28; // [rsp+50h] [rbp-89h]
  __int64 v29; // [rsp+58h] [rbp-81h]
  __int64 v30; // [rsp+60h] [rbp-79h]
  __int64 v31; // [rsp+68h] [rbp-71h]
  __int64 v32; // [rsp+70h] [rbp-69h]
  __int64 v33; // [rsp+78h] [rbp-61h]
  __int64 v34; // [rsp+80h] [rbp-59h]
  __int64 v35; // [rsp+88h] [rbp-51h]
  WINBOOL AccessStatus; // [rsp+A8h] [rbp-31h] BYREF
  unsigned int v37; // [rsp+ACh] [rbp-2Dh]
  CImageCache::Image *v38; // [rsp+B0h] [rbp-29h] BYREF
  struct Image *v39; // [rsp+B8h] [rbp-21h] BYREF
  CMRSWLock *v40; // [rsp+C0h] [rbp-19h] BYREF
  int v41; // [rsp+C8h] [rbp-11h]
  void *v42; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v43; // [rsp+D8h] [rbp-1h]
  char v46; // [rsp+148h] [rbp+6Fh]

  v46 = a3;
  v5 = ClientToken;
  v6 = a1;
  v7 = 0;
  AccessStatus = 0;
  LODWORD(v8) = 0;
  v38 = 0;
  v39 = 0;
  v9 = a4;
  v10 = a3;
  CAutoReaderLock::CAutoReaderLock((CAutoReaderLock *)&v40, a1, a3);
  if ( !*((_DWORD *)v6 + 39) )
  {
    for ( i = 0; ; i = v37 + 1 )
    {
      v37 = i;
      if ( i >= *((_DWORD *)v6 + 35) )
        goto LABEL_34;
      LODWORD(v8) = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem((char *)v6 + 128, i, &v39);
      if ( (unsigned int)ElValidateWin32_0(
                           (unsigned int)v8,
                           v12,
                           "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                           241) )
        goto LABEL_34;
      v13 = v39;
      if ( *((_DWORD *)v39 + 10)
        && ((v10 & 1) != 0 || *((_DWORD *)v39 + 8) == 2)
        && ((v10 & 2) != 0 || *((_DWORD *)v39 + 8) != 3) )
      {
        v14 = pWdsImgAccessCheckBySDDL(v5, *((LPCWSTR *)v39 + 3), &AccessStatus);
        LODWORD(v8) = v14;
        if ( v14 == 5 )
        {
          LODWORD(v8) = 0;
          continue;
        }
        if ( (unsigned int)ElValidateWin32_0(v14, v15, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 283) )
          goto LABEL_34;
        if ( AccessStatus )
        {
          if ( v9 && *((_DWORD *)v13 + 11) )
          {
            v42 = 0;
            v43 = 0;
            v23 = &v42;
            LODWORD(v8) = CWdsMetadataStoreManagementClient::MatchFilter((char *)v6 + 160, v9, (char *)v13 + 48);
            if ( (unsigned int)ElValidateWin32_0(
                                 (unsigned int)v8,
                                 v16,
                                 "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
                                 305) )
            {
              if ( !v42 )
                goto LABEL_34;
              operator delete[](v42);
LABEL_32:
              if ( v7 )
                CImageCache::Image::`scalar deleting destructor'(v7, v19);
              goto LABEL_34;
            }
            if ( HIDWORD(v43) != 1 )
            {
              if ( v42 )
                operator delete[](v42);
              continue;
            }
            if ( v42 )
              operator delete[](v42);
          }
          v8 = CImageCache::DuplicateImageInfo(v13, &v38);
          v18 = ElValidateWin32_0(v8, v17, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 317);
          v7 = v38;
          if ( v18 )
            goto LABEL_32;
          v8 = (unsigned int)CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(a5, v38);
          if ( (unsigned int)ElValidateWin32_0(v8, v20, "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp", 320) )
            goto LABEL_32;
          v7 = 0;
          v38 = 0;
          if ( g_ErrLibTraceFunction )
          {
            v21 = L"Present";
            if ( !*((_DWORD *)v13 + 11) )
              v21 = L"Not Present";
            LODWORD(v35) = *((unsigned __int8 *)v13 + 63);
            LODWORD(v34) = *((unsigned __int8 *)v13 + 62);
            LODWORD(v33) = *((unsigned __int8 *)v13 + 61);
            LODWORD(v32) = *((unsigned __int8 *)v13 + 60);
            LODWORD(v31) = *((unsigned __int8 *)v13 + 59);
            LODWORD(v30) = *((unsigned __int8 *)v13 + 58);
            LODWORD(v29) = *((unsigned __int8 *)v13 + 57);
            LODWORD(v28) = *((unsigned __int8 *)v13 + 56);
            LODWORD(v27) = *((unsigned __int16 *)v13 + 27);
            LODWORD(v26) = *((unsigned __int16 *)v13 + 26);
            LODWORD(v25) = *((_DWORD *)v13 + 12);
            LODWORD(v24) = *((_DWORD *)v13 + 16);
            LODWORD(v23) = *((_DWORD *)v13 + 8);
            g_ErrLibTraceFunction(
              L"Selected Image: Group=[%s], Name=[%s], Index=[%u], Format=[%u], Priority=[%u], Metadata ID=[{%08X-%04X-%04"
               "X-%02X%02X-%02X%02X%02X%02X%02X%02X}] (%s)",
              *(_QWORD *)v13,
              *((_QWORD *)v13 + 2),
              *((unsigned int *)v13 + 9),
              v23,
              v24,
              v25,
              v26,
              v27,
              v28,
              v29,
              v30,
              v31,
              v32,
              v33,
              v34,
              v35,
              v21);
            v6 = a1;
            v10 = v46;
            v9 = a4;
            v5 = ClientToken;
          }
        }
      }
    }
  }
  LODWORD(v8) = 5023;
LABEL_34:
  if ( v41 == 1 )
    CMRSWLock::ReaderRelease(v40);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000891c  mov     rax, rsp
0x18000891f  mov     [rax+20h], r9
0x180008923  mov     [rax+18h], r8d
0x180008927  mov     [rax+10h], rdx
0x18000892b  mov     [rax+8], rcx
0x18000892f  push    rbp
0x180008930  push    rbx
0x180008931  push    rsi
0x180008932  push    rdi
0x180008933  push    r12
0x180008935  push    r13
0x180008937  push    r14
0x180008939  push    r15
0x18000893b  lea     rbp, [rax-57h]
0x18000893f  sub     rsp, 0E8h
0x180008946  mov     r14, rdx
0x180008949  mov     rbx, rcx
0x18000894c  mov     rdx, rcx; struct CMRSWLock *
0x18000894f  xor     r13d, r13d
0x180008952  and     [rbp+4Fh+AccessStatus], r13d
0x180008956  lea     rcx, [rbp+4Fh+var_68]; this
0x18000895a  xor     r15d, r15d
0x18000895d  mov     [rbp+4Fh+var_78], r13
0x180008961  and     [rbp+4Fh+var_70], r15
0x180008965  mov     rsi, r9
0x180008968  mov     edi, r8d
0x18000896b  call    ??0CAutoReaderLock@@QEAA@PEAVCMRSWLock@@H@Z; CAutoReaderLock::CAutoReaderLock(CMRSWLock *,int)
0x180008970  cmp     [rbx+9Ch], r13d
0x180008977  jz      short loc_180008984
0x180008979  mov     r15d, 139Fh
0x18000897f  jmp     loc_180008C35
0x180008984  xor     eax, eax
0x180008986  mov     [rbp+4Fh+var_7C], eax
0x180008989  cmp     eax, [rbx+8Ch]
0x18000898f  jnb     loc_180008C35
0x180008995  lea     rcx, [rbx+80h]
0x18000899c  mov     edx, eax
0x18000899e  lea     r8, [rbp+4Fh+var_70]
0x1800089a2  call    ?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)
0x1800089a7  mov     ecx, eax
0x1800089a9  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x1800089b0  mov     r9d, 0F1h
0x1800089b6  mov     r15d, eax
0x1800089b9  call    ElValidateWin32_0
0x1800089be  test    eax, eax
0x1800089c0  jnz     loc_180008C35
0x1800089c6  mov     r12, [rbp+4Fh+var_70]
0x1800089ca  cmp     [r12+28h], eax
0x1800089cf  jz      loc_180008C0D
0x1800089d5  test    dil, 1
0x1800089d9  jnz     short loc_1800089E7
0x1800089db  cmp     dword ptr [r12+20h], 2
0x1800089e1  jnz     loc_180008C0D
0x1800089e7  test    dil, 2
0x1800089eb  jnz     short loc_1800089F9
0x1800089ed  cmp     dword ptr [r12+20h], 3
0x1800089f3  jz      loc_180008C0D
0x1800089f9  mov     rdx, [r12+18h]; StringSecurityDescriptor
0x1800089fe  lea     r8, [rbp+4Fh+AccessStatus]; AccessStatus
0x180008a02  mov     rcx, r14; ClientToken
0x180008a05  call    ?pWdsImgAccessCheckBySDDL@@YAKPEAXPEAGPEAH@Z; pWdsImgAccessCheckBySDDL(void *,ushort *,int *)
0x180008a0a  mov     r15d, eax
0x180008a0d  cmp     eax, 5
0x180008a10  jnz     short loc_180008A1A
0x180008a12  xor     r15d, r15d
0x180008a15  jmp     loc_180008C0D
0x180008a1a  mov     r9d, 11Bh
0x180008a20  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008a27  mov     ecx, eax
0x180008a29  call    ElValidateWin32_0
0x180008a2e  test    eax, eax
0x180008a30  jnz     loc_180008C35
0x180008a36  xor     eax, eax
0x180008a38  cmp     [rbp+4Fh+AccessStatus], eax
0x180008a3b  jz      loc_180008C0D
0x180008a41  test    rsi, rsi
0x180008a44  jz      loc_180008ACA
0x180008a4a  cmp     [r12+2Ch], eax
0x180008a4f  jz      short loc_180008ACA
0x180008a51  mov     [rbp+4Fh+var_58], rax
0x180008a55  lea     r8, [r12+30h]
0x180008a5a  mov     [rbp+4Fh+var_50], rax
0x180008a5e  lea     rcx, [rbx+0A0h]
0x180008a65  lea     rax, [rbp+4Fh+var_58]
0x180008a69  mov     rdx, rsi
0x180008a6c  mov     [rsp+120h+var_100], rax
0x180008a71  call    ?MatchFilter@CWdsMetadataStoreManagementClient@@QEAAKPEBVCWdsMetadata@@PEAU_GUID@@KPEAV?$CDynArray@U_GUID@@VCDeallocateNone@@@@@Z; CWdsMetadataStoreManagementClient::MatchFilter(CWdsMetadata const *,_GUID *,ulong,CDynArray<_GUID,CDeallocateNone> *)
0x180008a76  mov     r9d, 131h
0x180008a7c  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008a83  mov     ecx, eax
0x180008a85  mov     r15d, eax
0x180008a88  call    ElValidateWin32_0
0x180008a8d  mov     rcx, [rbp+4Fh+var_58]
0x180008a91  test    eax, eax
0x180008a93  jnz     loc_180008C17
0x180008a99  cmp     dword ptr [rbp+4Fh+var_50+4], 1
0x180008a9d  jz      short loc_180008AB9
0x180008a9f  test    rcx, rcx
0x180008aa2  jz      loc_180008C0D
0x180008aa8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008aaf  nop     dword ptr [rax+rax+00h]
0x180008ab4  jmp     loc_180008C0D
0x180008ab9  test    rcx, rcx
0x180008abc  jz      short loc_180008ACA
0x180008abe  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008ac5  nop     dword ptr [rax+rax+00h]
0x180008aca  lea     rdx, [rbp+4Fh+var_78]; struct Image **
0x180008ace  mov     rcx, r12; struct Image *
0x180008ad1  call    ?DuplicateImageInfo@CImageCache@@SAKPEAUImage@1@PEAPEAU21@@Z; CImageCache::DuplicateImageInfo(CImageCache::Image *,CImageCache::Image * *)
0x180008ad6  mov     r9d, 13Dh
0x180008adc  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008ae3  mov     ecx, eax
0x180008ae5  mov     r15d, eax
0x180008ae8  call    ElValidateWin32_0
0x180008aed  mov     r13, [rbp+4Fh+var_78]
0x180008af1  test    eax, eax
0x180008af3  jnz     loc_180008C28
0x180008af9  mov     rcx, [rbp+4Fh+arg_20]
0x180008afd  mov     rdx, r13
0x180008b00  call    ?AddItem@?$CDynArray@PEAUImage@CImageCache@@VCDeallocatePointer@@@@QEAAKPEAUImage@CImageCache@@@Z; CDynArray<CImageCache::Image *,CDeallocatePointer>::AddItem(CImageCache::Image *)
0x180008b05  mov     r9d, 140h
0x180008b0b  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x180008b12  mov     ecx, eax
0x180008b14  mov     r15d, eax
0x180008b17  call    ElValidateWin32_0
0x180008b1c  test    eax, eax
0x180008b1e  jnz     loc_180008C28
0x180008b24  xor     r13d, r13d
0x180008b27  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, r13; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008b2e  mov     [rbp+4Fh+var_78], r13
0x180008b32  jz      loc_180008C0D
0x180008b38  movzx   ecx, byte ptr [r12+3Eh]
0x180008b3e  lea     rax, aNotPresent; "Not Present"
0x180008b45  movzx   edx, byte ptr [r12+3Dh]
0x180008b4b  lea     r14, aPresent; "Present"
0x180008b52  movzx   r8d, byte ptr [r12+3Ch]
0x180008b58  movzx   r9d, byte ptr [r12+3Bh]
0x180008b5e  cmp     [r12+2Ch], r13d
0x180008b63  movzx   r10d, byte ptr [r12+3Ah]
0x180008b69  movzx   r11d, byte ptr [r12+39h]
0x180008b6f  cmovz   r14, rax
0x180008b73  movzx   eax, byte ptr [r12+3Fh]
0x180008b79  movzx   ebx, byte ptr [r12+38h]
0x180008b7f  movzx   edi, word ptr [r12+36h]
0x180008b85  movzx   esi, word ptr [r12+34h]
0x180008b8b  mov     [rsp+88h], r14
0x180008b93  mov     dword ptr [rsp+120h+var_A0], eax
0x180008b9a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008ba1  mov     dword ptr [rsp+120h+var_A8], ecx
0x180008ba5  mov     ecx, [r12+30h]
0x180008baa  mov     dword ptr [rsp+120h+var_B0], edx
0x180008bae  mov     rdx, [r12]
0x180008bb2  mov     dword ptr [rsp+120h+var_B8], r8d
0x180008bb7  mov     r8, [r12+10h]
0x180008bbc  mov     dword ptr [rsp+120h+var_C0], r9d
0x180008bc1  mov     r9d, [r12+24h]
0x180008bc6  mov     dword ptr [rsp+120h+var_C8], r10d
0x180008bcb  mov     dword ptr [rsp+120h+var_D0], r11d
0x180008bd0  mov     dword ptr [rsp+120h+var_D8], ebx
0x180008bd4  mov     dword ptr [rsp+120h+var_E0], edi
0x180008bd8  mov     dword ptr [rsp+120h+var_E8], esi
0x180008bdc  mov     dword ptr [rsp+120h+var_F0], ecx
0x180008be0  mov     ecx, [r12+40h]
0x180008be5  mov     dword ptr [rsp+120h+var_F8], ecx
0x180008be9  mov     ecx, [r12+20h]
0x180008bee  mov     dword ptr [rsp+120h+var_100], ecx
0x180008bf2  lea     rcx, aSelectedImageG; "Selected Image: Group=[%s], Name=[%s], "...
0x180008bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bfe  mov     rbx, [rbp+4Fh+arg_0]
0x180008c02  mov     edi, [rbp+4Fh+arg_10]
0x180008c05  mov     rsi, [rbp+4Fh+arg_18]
0x180008c09  mov     r14, [rbp+4Fh+arg_8]
0x180008c0d  mov     eax, [rbp+4Fh+var_7C]
0x180008c10  inc     eax
0x180008c12  jmp     loc_180008986
0x180008c17  test    rcx, rcx
0x180008c1a  jz      short loc_180008C35
0x180008c1c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008c23  nop     dword ptr [rax+rax+00h]
0x180008c28  test    r13, r13
0x180008c2b  jz      short loc_180008C35
0x180008c2d  mov     rcx, r13; this
0x180008c30  call    ??_GImage@CImageCache@@QEAAPEAXI@Z; CImageCache::Image::`scalar deleting destructor'(uint)
0x180008c35  mov     eax, [rbp+4Fh+var_60]
0x180008c38  test    eax, eax
0x180008c3a  jz      short loc_180008C51
0x180008c3c  cmp     eax, 1
0x180008c3f  jnz     short loc_180008C51
0x180008c41  mov     rcx, [rbp+4Fh+var_68]
0x180008c45  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180008c4c  nop     dword ptr [rax+rax+00h]
0x180008c51  mov     eax, r15d
0x180008c54  add     rsp, 0E8h
0x180008c5b  pop     r15
0x180008c5d  pop     r14
0x180008c5f  pop     r13
0x180008c61  pop     r12
0x180008c63  pop     rdi
0x180008c64  pop     rsi
0x180008c65  pop     rbx
0x180008c66  pop     rbp
0x180008c67  retn
```
