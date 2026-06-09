# CDeviceFolder::_OnImportPictures(IDataObject *)

- ea: `0x1800598e0`
- end: `0x180059a38`
- name: `?_OnImportPictures@CDeviceFolder@@AEAAJPEAUIDataObject@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(CDeviceFolder *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180056bf0`

## callees

- `0x180004110`
- `0x180007860`
- `0x18000c150`
- `0x18000cb90`
- `0x180024aa4`
- `0x18002ff5c`
- `0x1800598e0`
- `0x1800628cc`
- `0x180062e70`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x1800599b5`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800599b5`
- `ole32!CoTaskMemFree` at `0x1800599c2`
- `ole32!CoTaskMemFree` at `0x1800599c2`
- `ole32!CoTaskMemAlloc` at `0x180059959`
- `ole32!CoTaskMemAlloc` at `0x180059959`
- `SHELL32!__imp_ILFindLastID` at `0x18005993e`
- `SHELL32!__imp_ILFindLastID` at `0x18005993e`
- `SHELL32!__imp_ILFree` at `0x180059988`
- `SHELL32!__imp_ILFree` at `0x180059988`

## pseudocode

```c
__int64 __fastcall CDeviceFolder::_OnImportPictures(CDeviceFolder *this, struct IDataObject *a2)
{
  unsigned int v2; // ebx
  __int64 HIDA; // rax
  unsigned __int16 *v4; // rdi
  const ITEMIDLIST *v5; // rax
  __int64 v6; // rcx
  ITEMIDLIST *v7; // rbx
  const struct _ITEMIDLIST *ID; // rax
  CDeviceFolder *v9; // rcx
  const struct DEVICEITEM *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  PVOID *v17; // rcx
  __int128 v19; // [rsp+20h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-38h]

  v20 = 0;
  v19 = 0;
  if ( !a2 )
  {
    v2 = -2147024809;
LABEL_15:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  HIDA = DataObj_GetHIDA(a2, &v19);
  if ( !HIDA )
    goto LABEL_14;
  v4 = 0;
  v5 = (const ITEMIDLIST *)IDA_ILClone(HIDA, 0);
  v7 = (ITEMIDLIST *)v5;
  if ( v5 )
  {
    ID = ILFindLastID(v5);
    v10 = CDeviceFolder::_IsValid(v9, ID);
    if ( v10 )
    {
      v4 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
      if ( v4 )
        StringCchCopyW(
          v4,
          0x104u,
          (const unsigned __int16 *)v10 + *(unsigned int *)((char *)v10 + 26) + *(unsigned int *)((char *)v10 + 30) + 19);
    }
    ILFree(v7);
  }
  ReleaseStgMediumHGLOBAL(v6, &v19);
  if ( !v4 )
  {
LABEL_14:
    v2 = -2147024882;
    goto LABEL_15;
  }
  v2 = 0;
  DllAddRef(v12, v11, v13);
  if ( SHCreateThread((LPTHREAD_START_ROUTINE)CDeviceFolder::s_ImageWizardThreadProc, v4, 8u, 0) )
    return v2;
  CoTaskMemFree(v4);
  DllRelease(v15, v14, v16);
  v2 = -2147467259;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, 2147500037LL);
    goto LABEL_15;
  }
LABEL_16:
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 )
    WPP_SF_d(v17[2], 143, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800598e0  push    rbx
0x1800598e2  push    rbp
0x1800598e3  push    rsi
0x1800598e4  push    rdi
0x1800598e5  sub     rsp, 48h
0x1800598e9  xor     ecx, ecx
0x1800598eb  lea     rbp, WPP_GLOBAL_Control
0x1800598f2  mov     [rsp+68h+var_38], rcx
0x1800598f7  xorps   xmm0, xmm0
0x1800598fa  mov     rax, rdx
0x1800598fd  movups  [rsp+68h+var_48], xmm0
0x180059902  test    rdx, rdx
0x180059905  jnz     short loc_180059911
0x180059907  mov     ebx, 80070057h
0x18005990c  jmp     loc_180059A03
0x180059911  lea     rdx, [rsp+68h+var_48]
0x180059916  mov     rcx, rax
0x180059919  call    DataObj_GetHIDA
0x18005991e  test    rax, rax
0x180059921  jz      loc_1800599FE
0x180059927  xor     edx, edx
0x180059929  mov     rcx, rax
0x18005992c  xor     edi, edi
0x18005992e  call    IDA_ILClone
0x180059933  mov     rbx, rax
0x180059936  test    rax, rax
0x180059939  jz      short loc_18005998E
0x18005993b  mov     rcx, rax; pidl
0x18005993e  call    cs:__imp_ILFindLastID
0x180059944  mov     rdx, rax; struct _ITEMIDLIST *
0x180059947  call    ?_IsValid@CDeviceFolder@@AEAAPEFBUDEVICEITEM@@PEFBU_ITEMIDLIST@@@Z; CDeviceFolder::_IsValid(_ITEMIDLIST const *)
0x18005994c  mov     rsi, rax
0x18005994f  test    rax, rax
0x180059952  jz      short loc_180059985
0x180059954  mov     ecx, 208h; cb
0x180059959  call    cs:__imp_CoTaskMemAlloc
0x18005995f  mov     rdi, rax
0x180059962  test    rax, rax
0x180059965  jz      short loc_180059985
0x180059967  mov     eax, [rsi+1Ah]
0x18005996a  mov     edx, 104h; unsigned __int64
0x18005996f  mov     ecx, [rsi+1Eh]
0x180059972  add     rax, 13h
0x180059976  add     rcx, rax
0x180059979  lea     r8, [rsi+rcx*2]; unsigned __int16 *
0x18005997d  mov     rcx, rdi; unsigned __int16 *
0x180059980  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059985  mov     rcx, rbx; pidl
0x180059988  call    cs:__imp_ILFree
0x18005998e  lea     rdx, [rsp+68h+var_48]
0x180059993  call    ReleaseStgMediumHGLOBAL
0x180059998  test    rdi, rdi
0x18005999b  jz      short loc_1800599FE
0x18005999d  xor     ebx, ebx
0x18005999f  call    DllAddRef
0x1800599a4  xor     r9d, r9d; pfnCallback
0x1800599a7  lea     r8d, [rbx+8]; flags
0x1800599ab  mov     rdx, rdi; pData
0x1800599ae  lea     rcx, ?s_ImageWizardThreadProc@CDeviceFolder@@CAKPEAX@Z; pfnThreadProc
0x1800599b5  call    cs:__imp_SHCreateThread
0x1800599bb  test    eax, eax
0x1800599bd  jnz     short loc_180059A2D
0x1800599bf  mov     rcx, rdi; pv
0x1800599c2  call    cs:__imp_CoTaskMemFree
0x1800599c8  call    DllRelease
0x1800599cd  mov     ebx, 80004005h
0x1800599d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599d9  cmp     rcx, rbp
0x1800599dc  jz      short loc_180059A2D
0x1800599de  test    byte ptr [rcx+1Ch], 2
0x1800599e2  jz      short loc_180059A0A
0x1800599e4  mov     rcx, [rcx+10h]
0x1800599e8  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800599ef  mov     edx, 8Eh
0x1800599f4  mov     r9d, ebx
0x1800599f7  call    WPP_SF_d
0x1800599fc  jmp     short loc_180059A03
0x1800599fe  mov     ebx, 8007000Eh
0x180059a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a0a  cmp     rcx, rbp
0x180059a0d  jz      short loc_180059A2D
0x180059a0f  test    byte ptr [rcx+1Ch], 2
0x180059a13  jz      short loc_180059A2D
0x180059a15  mov     rcx, [rcx+10h]
0x180059a19  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180059a20  mov     edx, 8Fh
0x180059a25  mov     r9d, ebx
0x180059a28  call    WPP_SF_d
0x180059a2d  mov     eax, ebx
0x180059a2f  add     rsp, 48h
0x180059a33  pop     rdi
0x180059a34  pop     rsi
0x180059a35  pop     rbp
0x180059a36  pop     rbx
0x180059a37  retn
```
