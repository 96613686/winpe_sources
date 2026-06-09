# BlbDeleteSppMetadataFile(uchar,_GUID,ushort *,ushort *)

- ea: `0x1400f649c`
- end: `0x1400f682e`
- name: `?BlbDeleteSppMetadataFile@@YAJEU_GUID@@PEAG1@Z`
- size: `914`
- prototype: `int(unsigned __int8, struct _GUID *__struct_ptr, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x1400227f8`
- `0x140043980`
- `0x14007f738`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140083d38`
- `0x14008fed0`
- `0x1400f649c`
- `0x140134cc6`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400f665b`
- `KERNEL32!DeleteFileW` at `0x1400f6758`
- `KERNEL32!DeleteFileW` at `0x1400f665b`
- `KERNEL32!DeleteFileW` at `0x1400f6758`
- `KERNEL32!GetLastError` at `0x1400f6665`
- `KERNEL32!GetLastError` at `0x1400f6670`
- `KERNEL32!GetLastError` at `0x1400f6762`
- `KERNEL32!GetLastError` at `0x1400f676d`
- `KERNEL32!GetLastError` at `0x1400f6665`
- `KERNEL32!GetLastError` at `0x1400f6670`
- `KERNEL32!GetLastError` at `0x1400f6762`
- `KERNEL32!GetLastError` at `0x1400f676d`
- `ole32!CoTaskMemFree` at `0x1400f66d2`
- `ole32!CoTaskMemFree` at `0x1400f67e3`
- `ole32!CoTaskMemFree` at `0x1400f66d2`
- `ole32!CoTaskMemFree` at `0x1400f67e3`

## pseudocode

```c
__int64 __fastcall BlbDeleteSppMetadataFile(char a1, struct _GUID *a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  signed int IsClientSKU; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rdi
  signed int LastError; // eax
  int v13; // edx
  signed int v14; // eax
  unsigned __int8 v16[8]; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-30h] BYREF
  struct _GUID v18; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID v19; // [rsp+50h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids);
  }
  lpFileName = 0;
  v16[0] = 0;
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbspputils.cpp", 0x2BBu, "guidBackupSetId != GUID_NULL");
  IsClientSKU = BlbutilIsClientSKU(v16);
  if ( IsClientSKU >= 0 )
  {
    if ( !v16[0] )
      goto LABEL_56;
    if ( a1 )
    {
      v19 = *a2;
      v18 = g_guidBootVolumeId;
      IsClientSKU = CSPPMetadataManager::GetSPPMetadataFilePath(&v19, a3, a4, &v18, 0, (unsigned __int16 **)&lpFileName);
      if ( IsClientSKU < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 16;
LABEL_19:
          WPP_SF_d(v9[2], v10, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids);
          v11 = (WCHAR *)lpFileName;
LABEL_53:
          v9 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_54;
        }
        goto LABEL_40;
      }
      v11 = (WCHAR *)lpFileName;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids, lpFileName);
      }
      if ( !DeleteFileW(v11) && GetLastError() != 2 )
      {
        LastError = GetLastError();
        IsClientSKU = LastError;
        if ( LastError > 0 )
          IsClientSKU = (unsigned __int16)LastError | 0x80070000;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v13 = 18;
LABEL_32:
          WPP_SF_Sd(
            (unsigned int)v9[2],
            v13,
            (unsigned int)WPP_412ba3de64bc36743846074deeb0fafd_Traceguids,
            (_DWORD)v11,
            IsClientSKU);
          goto LABEL_53;
        }
        goto LABEL_54;
      }
      if ( v11 )
      {
        CoTaskMemFree(v11);
        lpFileName = 0;
      }
    }
    v18 = *a2;
    v19 = g_guidBootVolumeId;
    IsClientSKU = CSPPMetadataManager::GetSPPMetadataFilePath(&v18, 0, 0, &v19, 1, (unsigned __int16 **)&lpFileName);
    if ( IsClientSKU < 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 19;
        goto LABEL_19;
      }
LABEL_40:
      v11 = (WCHAR *)lpFileName;
      goto LABEL_54;
    }
    v11 = (WCHAR *)lpFileName;
    if ( DeleteFileW(lpFileName) )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids, v11);
        goto LABEL_53;
      }
    }
    else
    {
      if ( GetLastError() == 2 )
        goto LABEL_53;
      v14 = GetLastError();
      IsClientSKU = v14;
      if ( v14 > 0 )
        IsClientSKU = (unsigned __int16)v14 | 0x80070000;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = 20;
        goto LABEL_32;
      }
    }
LABEL_54:
    if ( v11 )
    {
      CoTaskMemFree(v11);
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)IsClientSKU;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids);
LABEL_56:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_57:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_(v9[2], 22, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids);
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x1400f649c  push    rbp
0x1400f649e  push    rbx
0x1400f649f  push    rsi
0x1400f64a0  push    rdi
0x1400f64a1  push    r14
0x1400f64a3  push    r15
0x1400f64a5  mov     rbp, rsp
0x1400f64a8  sub     rsp, 68h
0x1400f64ac  mov     r14, r9
0x1400f64af  mov     r15, r8
0x1400f64b2  mov     rsi, rdx
0x1400f64b5  mov     dil, cl
0x1400f64b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f64bf  lea     rax, WPP_GLOBAL_Control
0x1400f64c6  cmp     rcx, rax
0x1400f64c9  jz      short loc_1400F64EC
0x1400f64cb  test    byte ptr [rcx+1Ch], 1
0x1400f64cf  jz      short loc_1400F64EC
0x1400f64d1  cmp     byte ptr [rcx+19h], 4
0x1400f64d5  jb      short loc_1400F64EC
0x1400f64d7  mov     rcx, [rcx+10h]
0x1400f64db  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f64e2  mov     edx, 0Eh
0x1400f64e7  call    WPP_SF_
0x1400f64ec  mov     r8d, 10h; Size
0x1400f64f2  mov     [rbp+lpFileName], 0
0x1400f64fa  lea     rdx, GUID_NULL; Buf2
0x1400f6501  mov     [rbp+var_38], 0
0x1400f6505  mov     rcx, rsi; Buf1
0x1400f6508  call    memcmp_0
0x1400f650d  test    eax, eax
0x1400f650f  jnz     short loc_1400F6529
0x1400f6511  lea     r8, aGuidbackupseti_0; "guidBackupSetId != GUID_NULL"
0x1400f6518  mov     edx, 2BBh; unsigned int
0x1400f651d  lea     rcx, aBaseStorBlbEng_25; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f6524  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f6529  lea     rcx, [rbp+var_38]; unsigned __int8 *
0x1400f652d  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x1400f6532  mov     ebx, eax
0x1400f6534  test    eax, eax
0x1400f6536  jns     short loc_1400F6580
0x1400f6538  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f653f  lea     r14, WPP_GLOBAL_Control
0x1400f6546  cmp     rcx, r14
0x1400f6549  jz      loc_1400F681F
0x1400f654f  test    byte ptr [rcx+1Ch], 1
0x1400f6553  jz      loc_1400F67F9
0x1400f6559  cmp     byte ptr [rcx+19h], 2
0x1400f655d  jb      loc_1400F67F9
0x1400f6563  mov     rcx, [rcx+10h]
0x1400f6567  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f656e  mov     edx, 0Fh
0x1400f6573  mov     r9d, eax
0x1400f6576  call    WPP_SF_d
0x1400f657b  jmp     loc_1400F67F2
0x1400f6580  cmp     [rbp+var_38], 0
0x1400f6584  jz      loc_1400F67EB
0x1400f658a  test    dil, dil
0x1400f658d  jz      loc_1400F66E2
0x1400f6593  movups  xmm0, xmmword ptr cs:?g_guidBootVolumeId@@3U_GUID@@A.Data1; _GUID g_guidBootVolumeId ...
0x1400f659a  lea     rax, [rbp+lpFileName]
0x1400f659e  mov     r8, r14; unsigned __int16 *
0x1400f65a1  movaps  xmm1, xmmword ptr [rsi]
0x1400f65a4  lea     r9, [rbp+var_28]; struct _GUID
0x1400f65a8  mov     [rsp+68h+var_40], rax; unsigned __int16 **
0x1400f65ad  lea     rcx, [rbp+var_18]; struct _GUID
0x1400f65b1  mov     rdx, r15; unsigned __int16 *
0x1400f65b4  movdqa  xmmword ptr [rbp+var_18.Data1], xmm1
0x1400f65b9  movdqu  xmmword ptr [rbp+var_28.Data1], xmm0
0x1400f65be  mov     [rsp+68h+var_48], 0; int
0x1400f65c6  call    ?GetSPPMetadataFilePath@CSPPMetadataManager@@SAJU_GUID@@PEAG10HPEAPEAG@Z; CSPPMetadataManager::GetSPPMetadataFilePath(_GUID,ushort *,ushort *,_GUID,int,ushort * *)
0x1400f65cb  mov     ebx, eax
0x1400f65cd  test    eax, eax
0x1400f65cf  jns     short loc_1400F661D
0x1400f65d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f65d8  lea     r14, WPP_GLOBAL_Control
0x1400f65df  cmp     rcx, r14
0x1400f65e2  jz      loc_1400F6748
0x1400f65e8  test    byte ptr [rcx+1Ch], 1
0x1400f65ec  jz      loc_1400F6748
0x1400f65f2  cmp     byte ptr [rcx+19h], 2
0x1400f65f6  jb      loc_1400F6748
0x1400f65fc  mov     edx, 10h
0x1400f6601  mov     rcx, [rcx+10h]
0x1400f6605  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f660c  mov     r9d, eax
0x1400f660f  call    WPP_SF_d
0x1400f6614  mov     rdi, [rbp+lpFileName]
0x1400f6618  jmp     loc_1400F67D4
0x1400f661d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f6624  lea     r14, WPP_GLOBAL_Control
0x1400f662b  mov     rdi, [rbp+lpFileName]
0x1400f662f  cmp     rcx, r14
0x1400f6632  jz      short loc_1400F6658
0x1400f6634  test    byte ptr [rcx+1Ch], 1
0x1400f6638  jz      short loc_1400F6658
0x1400f663a  cmp     byte ptr [rcx+19h], 4
0x1400f663e  jb      short loc_1400F6658
0x1400f6640  mov     rcx, [rcx+10h]
0x1400f6644  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f664b  mov     edx, 11h
0x1400f6650  mov     r9, rdi
0x1400f6653  call    WPP_SF_S
0x1400f6658  mov     rcx, rdi; lpFileName
0x1400f665b  call    cs:__imp_DeleteFileW
0x1400f6661  test    eax, eax
0x1400f6663  jnz     short loc_1400F66CA
0x1400f6665  call    cs:__imp_GetLastError
0x1400f666b  cmp     eax, 2
0x1400f666e  jz      short loc_1400F66CA
0x1400f6670  call    cs:__imp_GetLastError
0x1400f6676  mov     ebx, eax
0x1400f6678  test    eax, eax
0x1400f667a  jle     short loc_1400F6685
0x1400f667c  movzx   ebx, ax
0x1400f667f  or      ebx, 80070000h
0x1400f6685  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f668c  cmp     rcx, r14
0x1400f668f  jz      loc_1400F67DB
0x1400f6695  test    byte ptr [rcx+1Ch], 1
0x1400f6699  jz      loc_1400F67DB
0x1400f669f  cmp     byte ptr [rcx+19h], 4
0x1400f66a3  jb      loc_1400F67DB
0x1400f66a9  mov     edx, 12h
0x1400f66ae  mov     rcx, [rcx+10h]
0x1400f66b2  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f66b9  mov     r9, rdi
0x1400f66bc  mov     [rsp+68h+var_48], ebx
0x1400f66c0  call    WPP_SF_Sd
0x1400f66c5  jmp     loc_1400F67D4
0x1400f66ca  test    rdi, rdi
0x1400f66cd  jz      short loc_1400F66E9
0x1400f66cf  mov     rcx, rdi; pv
0x1400f66d2  call    cs:__imp_CoTaskMemFree
0x1400f66d8  mov     [rbp+lpFileName], 0
0x1400f66e0  jmp     short loc_1400F66E9
0x1400f66e2  lea     r14, WPP_GLOBAL_Control
0x1400f66e9  movups  xmm0, xmmword ptr cs:?g_guidBootVolumeId@@3U_GUID@@A.Data1; _GUID g_guidBootVolumeId ...
0x1400f66f0  lea     rax, [rbp+lpFileName]
0x1400f66f4  xor     r8d, r8d; unsigned __int16 *
0x1400f66f7  movaps  xmm1, xmmword ptr [rsi]
0x1400f66fa  lea     r9, [rbp+var_18]; struct _GUID
0x1400f66fe  mov     [rsp+68h+var_40], rax; unsigned __int16 **
0x1400f6703  lea     rcx, [rbp+var_28]; struct _GUID
0x1400f6707  xor     edx, edx; unsigned __int16 *
0x1400f6709  movdqa  xmmword ptr [rbp+var_28.Data1], xmm1
0x1400f670e  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x1400f6713  mov     [rsp+68h+var_48], 1; int
0x1400f671b  call    ?GetSPPMetadataFilePath@CSPPMetadataManager@@SAJU_GUID@@PEAG10HPEAPEAG@Z; CSPPMetadataManager::GetSPPMetadataFilePath(_GUID,ushort *,ushort *,_GUID,int,ushort * *)
0x1400f6720  mov     ebx, eax
0x1400f6722  test    eax, eax
0x1400f6724  jns     short loc_1400F6751
0x1400f6726  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f672d  cmp     rcx, r14
0x1400f6730  jz      short loc_1400F6748
0x1400f6732  test    byte ptr [rcx+1Ch], 1
0x1400f6736  jz      short loc_1400F6748
0x1400f6738  cmp     byte ptr [rcx+19h], 2
0x1400f673c  jb      short loc_1400F6748
0x1400f673e  mov     edx, 13h
0x1400f6743  jmp     loc_1400F6601
0x1400f6748  mov     rdi, [rbp+lpFileName]
0x1400f674c  jmp     loc_1400F67DB
0x1400f6751  mov     rdi, [rbp+lpFileName]
0x1400f6755  mov     rcx, rdi; lpFileName
0x1400f6758  call    cs:__imp_DeleteFileW
0x1400f675e  test    eax, eax
0x1400f6760  jnz     short loc_1400F67A4
0x1400f6762  call    cs:__imp_GetLastError
0x1400f6768  cmp     eax, 2
0x1400f676b  jz      short loc_1400F67D4
0x1400f676d  call    cs:__imp_GetLastError
0x1400f6773  mov     ebx, eax
0x1400f6775  test    eax, eax
0x1400f6777  jle     short loc_1400F6782
0x1400f6779  movzx   ebx, ax
0x1400f677c  or      ebx, 80070000h
0x1400f6782  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f6789  cmp     rcx, r14
0x1400f678c  jz      short loc_1400F67DB
0x1400f678e  test    byte ptr [rcx+1Ch], 1
0x1400f6792  jz      short loc_1400F67DB
0x1400f6794  cmp     byte ptr [rcx+19h], 4
0x1400f6798  jb      short loc_1400F67DB
0x1400f679a  mov     edx, 14h
0x1400f679f  jmp     loc_1400F66AE
0x1400f67a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f67ab  cmp     rcx, r14
0x1400f67ae  jz      short loc_1400F67DB
0x1400f67b0  test    byte ptr [rcx+1Ch], 1
0x1400f67b4  jz      short loc_1400F67DB
0x1400f67b6  cmp     byte ptr [rcx+19h], 4
0x1400f67ba  jb      short loc_1400F67DB
0x1400f67bc  mov     rcx, [rcx+10h]
0x1400f67c0  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f67c7  mov     edx, 15h
0x1400f67cc  mov     r9, rdi
0x1400f67cf  call    WPP_SF_S
0x1400f67d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f67db  test    rdi, rdi
0x1400f67de  jz      short loc_1400F67F9
0x1400f67e0  mov     rcx, rdi; pv
0x1400f67e3  call    cs:__imp_CoTaskMemFree
0x1400f67e9  jmp     short loc_1400F67F2
0x1400f67eb  lea     r14, WPP_GLOBAL_Control
0x1400f67f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f67f9  cmp     rcx, r14
0x1400f67fc  jz      short loc_1400F681F
0x1400f67fe  test    byte ptr [rcx+1Ch], 1
0x1400f6802  jz      short loc_1400F681F
0x1400f6804  cmp     byte ptr [rcx+19h], 4
0x1400f6808  jb      short loc_1400F681F
0x1400f680a  mov     rcx, [rcx+10h]
0x1400f680e  lea     r8, WPP_412ba3de64bc36743846074deeb0fafd_Traceguids
0x1400f6815  mov     edx, 16h
0x1400f681a  call    WPP_SF_
0x1400f681f  mov     eax, ebx
0x1400f6821  add     rsp, 68h
0x1400f6825  pop     r15
0x1400f6827  pop     r14
0x1400f6829  pop     rdi
0x1400f682a  pop     rsi
0x1400f682b  pop     rbx
0x1400f682c  pop     rbp
0x1400f682d  retn
```
