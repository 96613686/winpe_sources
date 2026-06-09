# HandleDisableFailure(void *)

- ea: `0x180009590`
- end: `0x18000981b`
- name: `?HandleDisableFailure@@YAJPEAX@Z`
- size: `651`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callees

- `0x180001b90`
- `0x180001cc8`
- `0x180002638`
- `0x180004838`
- `0x180004c48`
- `0x180004ce4`
- `0x1800055b0`
- `0x180009300`
- `0x180009590`
- `0x180009f14`
- `0x18000a0b0`
- `0x18000a3bc`
- `0x18000a616`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x1800096c3`
- `ntdll!WinSqmAddToStreamEx` at `0x1800096c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800097b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800097b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000961f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000961f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800097de`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800097de`
- `WSCAPI!wscAntiVirusGetStatus` at `0x180009652`
- `WSCAPI!wscAntiVirusGetStatus` at `0x180009652`
- `WSCAPI!wscProductInfoFree` at `0x1800097c6`
- `WSCAPI!wscProductInfoFree` at `0x1800097c6`
- `KERNEL32!ReleaseActCtx` at `0x1800097e7`
- `KERNEL32!ReleaseActCtx` at `0x1800097e7`

## string_xrefs

- `0x180009618`: `wscapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HandleDisableFailure(unsigned int *Parameter)
{
  int v2; // r14d
  __int64 v3; // rbx
  void *v4; // rsi
  char *v5; // rdi
  int v6; // r13d
  __int64 v7; // rbx
  __int64 v8; // rbx
  const wchar_t *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned __int16 *v12; // r12
  __int64 v14; // [rsp+30h] [rbp-A9h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-A1h] BYREF
  ULONG_PTR ulCookie; // [rsp+40h] [rbp-99h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-91h] BYREF
  __int64 v18; // [rsp+58h] [rbp-81h] BYREF
  int v19; // [rsp+60h] [rbp-79h] BYREF
  _QWORD v20[2]; // [rsp+64h] [rbp-75h] BYREF
  int v21; // [rsp+74h] [rbp-65h]
  int v22; // [rsp+78h] [rbp-61h]
  __int64 v23; // [rsp+7Ch] [rbp-5Dh]
  __int64 v24; // [rsp+8Ch] [rbp-4Dh]
  unsigned __int16 *v25; // [rsp+94h] [rbp-45h]
  int v26; // [rsp+9Ch] [rbp-3Dh]
  char *v27; // [rsp+A0h] [rbp-39h]
  __int64 v28; // [rsp+BCh] [rbp-1Dh]
  __int64 (__fastcall *v29)(HWND, unsigned int, unsigned __int64, __int64, __int64); // [rsp+ECh] [rbp+13h]
  unsigned int v30; // [rsp+140h] [rbp+67h] BYREF
  int v31; // [rsp+148h] [rbp+6Fh] BYREF
  unsigned __int16 *v32; // [rsp+150h] [rbp+77h] BYREF
  __int64 v33; // [rsp+158h] [rbp+7Fh] BYREF

  v31 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v18);
  v19 = 160;
  memset_0(v20, 0, 0x9Cu);
  v2 = 0;
  v33 = 0;
  v30 = 0;
  ulCookie = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v14);
  v3 = *Parameter;
  v32 = 0;
  v15 = 0;
  v4 = (void *)CreateAndActivateContext(&ulCookie);
  if ( !g_hinst )
  {
    g_hinst = LoadLibraryExW(L"wscapi.dll", 0, 0x800u);
    v2 = 1;
  }
  v5 = (char *)operator new[](0xCu, (const struct std::nothrow_t *)&std::nothrow);
  *(_DWORD *)v5 = 10;
  if ( (unsigned int)wscAntiVirusGetStatus(&v30, &v33) )
  {
    v6 = -2147023834;
    v7 = v14;
  }
  else
  {
    v8 = 10 * v3;
    v9 = *(const wchar_t **)(v33 + 8 * v8 + 8);
    memset((char *)v17 + 4, 0, 12);
    LODWORD(v17[0]) = 16;
    if ( !v9 || !*v9 )
      v9 = L"(null)";
    v17[1] = v9;
    HIDWORD(v17[0]) = 2;
    WinSqmAddToStreamEx(0, 11245, 1, v17, 0);
    GetResourceString(0x1782u, *(PCWSTR *)(v33 + 8 * v8 + 8), &v15);
    GetResourceString(0x1780u, *(PCWSTR *)(v33 + 8 * v8 + 8), &v32);
    v10 = ATL::CSimpleStringT<unsigned short,0>::StringLength(v32);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v14, v11, v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Remove(&v14);
    v7 = v14;
    *(_QWORD *)(v5 + 4) = v14;
    v20[1] = g_hinst;
    v20[0] = 0;
    v23 = 6019;
    v24 = 6017;
    v12 = v15;
    v25 = v15;
    v28 = 0;
    v26 = 1;
    v27 = v5;
    v22 = 32;
    v21 = 25;
    v29 = HDFDialogCallbackProc;
    v6 = SHFusionTaskDialogIndirect(&v19, &v31);
    if ( v6 >= 0 )
      operator delete(v5);
    if ( v12 )
      WscHeapFree(v12);
    if ( v32 )
      WscHeapFree(v32);
  }
  if ( v2 )
    FreeLibrary(g_hinst);
  wscProductInfoFree(v30, v33);
  if ( v4 != (void *)-1LL )
  {
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
    ReleaseActCtx(v4);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009590  push    rbp
0x180009592  push    rbx
0x180009593  push    rsi
0x180009594  push    rdi
0x180009595  push    r12
0x180009597  push    r13
0x180009599  push    r14
0x18000959b  lea     rbp, [rsp-27h]
0x1800095a0  sub     rsp, 100h
0x1800095a7  mov     rbx, rcx
0x1800095aa  xor     r13d, r13d
0x1800095ad  mov     [rbp+57h+arg_8], r13d
0x1800095b1  lea     rcx, [rsp+130h+var_D8]
0x1800095b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800095bb  nop
0x1800095bc  mov     [rbp+57h+var_D0], 0A0h
0x1800095c3  xor     edx, edx; Val
0x1800095c5  mov     r8d, 9Ch; Size
0x1800095cb  lea     rcx, [rbp+57h+var_CC]; void *
0x1800095cf  call    memset_0
0x1800095d4  mov     r14d, r13d
0x1800095d7  mov     [rbp+57h+arg_18], r13
0x1800095db  mov     [rbp+57h+arg_0], r13d
0x1800095df  mov     [rsp+130h+ulCookie], r13
0x1800095e4  lea     rcx, [rsp+130h+var_100]
0x1800095e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800095ee  nop
0x1800095ef  mov     ebx, [rbx]
0x1800095f1  mov     [rbp+57h+arg_10], r13
0x1800095f5  mov     [rsp+130h+var_F8], r13
0x1800095fa  lea     rcx, [rsp+130h+ulCookie]; lpCookie
0x1800095ff  call    CreateAndActivateContext
0x180009604  mov     rsi, rax
0x180009607  cmp     cs:?g_hinst@@3PEAUHINSTANCE__@@EA, r13; HINSTANCE__ * g_hinst
0x18000960e  jnz     short loc_180009630
0x180009610  xor     edx, edx; hFile
0x180009612  mov     r8d, 800h; dwFlags
0x180009618  lea     rcx, aWscapiDll_0; "wscapi.dll"
0x18000961f  call    cs:__imp_LoadLibraryExW
0x180009625  mov     cs:?g_hinst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hinst
0x18000962c  lea     r14d, [r13+1]
0x180009630  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009637  mov     ecx, 0Ch; unsigned __int64
0x18000963c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009641  mov     rdi, rax
0x180009644  mov     dword ptr [rax], 0Ah
0x18000964a  lea     rdx, [rbp+57h+arg_18]
0x18000964e  lea     rcx, [rbp+57h+arg_0]
0x180009652  call    cs:__imp_wscAntiVirusGetStatus
0x180009658  test    eax, eax
0x18000965a  jz      short loc_18000966C
0x18000965c  mov     r13d, 80070426h
0x180009662  mov     rbx, [rsp+130h+var_100]
0x180009667  jmp     loc_1800097AD
0x18000966c  lea     rbx, [rbx+rbx*4]
0x180009670  add     rbx, rbx
0x180009673  mov     rax, [rbp+57h+arg_18]
0x180009677  mov     rcx, [rax+rbx*8+8]
0x18000967c  xor     eax, eax
0x18000967e  mov     [rsp+130h+var_E4], rax
0x180009683  mov     [rsp+130h+var_DC], eax
0x180009687  mov     [rsp+130h+var_E8], 10h
0x18000968f  test    rcx, rcx
0x180009692  jz      short loc_18000969A
0x180009694  cmp     [rcx], r13w
0x180009698  jnz     short loc_1800096A1
0x18000969a  lea     rcx, aNull_0; "(null)"
0x1800096a1  mov     [rsp+130h+var_E4+4], rcx
0x1800096a6  mov     dword ptr [rsp+130h+var_E4], 2
0x1800096ae  mov     [rsp+130h+var_110], r13d
0x1800096b3  lea     r9, [rsp+130h+var_E8]
0x1800096b8  mov     edx, 2BEDh
0x1800096bd  xor     ecx, ecx
0x1800096bf  lea     r8d, [rcx+1]
0x1800096c3  call    cs:__imp_WinSqmAddToStreamEx
0x1800096c9  lea     r8, [rsp+130h+var_F8]; unsigned __int16 **
0x1800096ce  mov     rdx, [rbp+57h+arg_18]
0x1800096d2  mov     rdx, [rdx+rbx*8+8]; pszSource
0x1800096d7  mov     ecx, 1782h; uID
0x1800096dc  call    ?GetResourceString@@YAJHPEAGPEAPEAG@Z; GetResourceString(int,ushort *,ushort * *)
0x1800096e1  lea     r8, [rbp+57h+arg_10]; unsigned __int16 **
0x1800096e5  mov     rdx, [rbp+57h+arg_18]
0x1800096e9  mov     rdx, [rdx+rbx*8+8]; pszSource
0x1800096ee  mov     ecx, 1780h; uID
0x1800096f3  call    ?GetResourceString@@YAJHPEAGPEAPEAG@Z; GetResourceString(int,ushort *,ushort * *)
0x1800096f8  mov     rcx, [rbp+57h+arg_10]
0x1800096fc  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180009701  mov     r8d, eax
0x180009704  mov     rdx, rcx
0x180009707  lea     rcx, [rsp+130h+var_100]
0x18000970c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009711  lea     rcx, [rsp+130h+var_100]
0x180009716  call    ?Remove@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Remove(ushort)
0x18000971b  mov     rbx, [rsp+130h+var_100]
0x180009720  mov     [rdi+4], rbx
0x180009724  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18000972b  mov     [rbp+57h+var_C4], rax
0x18000972f  mov     [rbp+57h+var_CC], r13
0x180009733  mov     [rbp+57h+var_B4], 1783h
0x18000973b  mov     [rbp+57h+var_A4], 1781h
0x180009743  mov     r12, [rsp+130h+var_F8]
0x180009748  mov     [rbp+57h+var_9C], r12
0x18000974c  mov     [rbp+57h+var_74], r13
0x180009750  mov     [rbp+57h+var_94], 1
0x180009757  mov     [rbp+57h+var_90], rdi
0x18000975b  mov     [rbp+57h+var_B8], 20h ; ' '
0x180009762  mov     [rbp+57h+var_BC], 19h
0x180009769  lea     rax, ?HDFDialogCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; HDFDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x180009770  mov     [rbp+57h+var_44], rax
0x180009774  lea     rdx, [rbp+57h+arg_8]
0x180009778  lea     rcx, [rbp+57h+var_D0]
0x18000977c  call    SHFusionTaskDialogIndirect
0x180009781  mov     r13d, eax
0x180009784  test    eax, eax
0x180009786  js      short loc_180009790
0x180009788  mov     rcx, rdi; Block
0x18000978b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009790  test    r12, r12
0x180009793  jz      short loc_18000979D
0x180009795  mov     rcx, r12; void *
0x180009798  call    ?WscHeapFree@@YAXPEAX@Z; WscHeapFree(void *)
0x18000979d  cmp     [rbp+57h+arg_10], 0
0x1800097a2  jz      short loc_1800097AD
0x1800097a4  mov     rcx, [rbp+57h+arg_10]; void *
0x1800097a8  call    ?WscHeapFree@@YAXPEAX@Z; WscHeapFree(void *)
0x1800097ad  test    r14d, r14d
0x1800097b0  jz      short loc_1800097BF
0x1800097b2  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800097b9  call    cs:__imp_FreeLibrary
0x1800097bf  mov     rdx, [rbp+57h+arg_18]
0x1800097c3  mov     ecx, [rbp+57h+arg_0]
0x1800097c6  call    cs:__imp_wscProductInfoFree
0x1800097cc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800097d0  jz      short loc_1800097EE
0x1800097d2  mov     rdx, [rsp+130h+ulCookie]; ulCookie
0x1800097d7  test    rdx, rdx
0x1800097da  jz      short loc_1800097E4
0x1800097dc  xor     ecx, ecx; dwFlags
0x1800097de  call    cs:__imp_DeactivateActCtx
0x1800097e4  mov     rcx, rsi; hActCtx
0x1800097e7  call    cs:__imp_ReleaseActCtx
0x1800097ed  nop
0x1800097ee  lea     rcx, [rbx-18h]; this
0x1800097f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800097f7  nop
0x1800097f8  mov     rcx, [rsp+130h+var_D8]
0x1800097fd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180009801  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009806  mov     eax, r13d
0x180009809  add     rsp, 100h
0x180009810  pop     r14
0x180009812  pop     r13
0x180009814  pop     r12
0x180009816  pop     rdi
0x180009817  pop     rsi
0x180009818  pop     rbx
0x180009819  pop     rbp
0x18000981a  retn
```
