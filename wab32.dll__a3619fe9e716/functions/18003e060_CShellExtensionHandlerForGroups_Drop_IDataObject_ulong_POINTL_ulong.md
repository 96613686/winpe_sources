# CShellExtensionHandlerForGroups::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18003e060`
- end: `0x18003e440`
- name: `?Drop@CShellExtensionHandlerForGroups@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `992`
- prototype: `__int64 __fastcall(CShellExtensionHandlerForGroups *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002818`
- `0x180005d08`
- `0x18000ccb4`
- `0x18000d8b4`
- `0x18000dd70`
- `0x180011890`
- `0x18002fc50`
- `0x18002fe40`
- `0x1800337cc`
- `0x18003e060`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!OpenFileStreamShareW` at `0x18003e373`
- `MSOERT2!OpenFileStreamShareW` at `0x18003e373`
- `SHLWAPI!PathFindExtensionW` at `0x18003e22d`
- `SHLWAPI!PathFindExtensionW` at `0x18003e22d`
- `SHLWAPI!StrCmpIW` at `0x18003e240`
- `SHLWAPI!StrCmpIW` at `0x18003e254`
- `SHLWAPI!StrCmpIW` at `0x18003e240`
- `SHLWAPI!StrCmpIW` at `0x18003e254`
- `SHELL32!DragQueryFileW` at `0x18003e1ff`
- `SHELL32!DragQueryFileW` at `0x18003e223`
- `SHELL32!DragQueryFileW` at `0x18003e1ff`
- `SHELL32!DragQueryFileW` at `0x18003e223`
- `KERNEL32!GlobalFree` at `0x18003e3d1`
- `KERNEL32!GlobalFree` at `0x18003e3d1`
- `KERNEL32!GlobalUnlock` at `0x18003e3ae`
- `KERNEL32!GlobalUnlock` at `0x18003e3ae`
- `KERNEL32!GlobalLock` at `0x18003e1d6`
- `KERNEL32!GlobalLock` at `0x18003e1d6`
- `KERNEL32!LocalFree` at `0x18003e292`
- `KERNEL32!LocalFree` at `0x18003e404`
- `KERNEL32!LocalFree` at `0x18003e292`
- `KERNEL32!LocalFree` at `0x18003e404`

## pseudocode

```c
__int64 __fastcall CShellExtensionHandlerForGroups::Drop(
        CShellExtensionHandlerForGroups *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  int EntryIDFromIContact; // ebx
  _QWORD *v8; // rax
  int SPropFromIContactProperties; // eax
  HDROP v10; // rax
  HDROP v11; // r15
  int LastError; // eax
  int v13; // esi
  UINT FileW; // eax
  UINT i; // edi
  const WCHAR *ExtensionW; // r13
  struct IContactProperties *v17; // rsi
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(struct IContactProperties *, LPVOID); // rax
  const WCHAR *v20; // rcx
  HGLOBAL v21; // rcx
  LPVOID pBuffer; // [rsp+30h] [rbp-D0h] BYREF
  struct CMapping *v24; // [rsp+38h] [rbp-C8h] BYREF
  struct IContactProperties *v25; // [rsp+40h] [rbp-C0h] BYREF
  struct IContact *v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v28[2]; // [rsp+58h] [rbp-A8h] BYREF
  HGLOBAL hMem[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int16 v31; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+82h] [rbp-7Eh]
  __int16 v33; // [rsp+86h] [rbp-7Ah]
  __int64 v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  __int64 v37; // [rsp+98h] [rbp-68h]
  WCHAR szFile[264]; // [rsp+A0h] [rbp-60h] BYREF

  v36 = -1;
  v31 = 15;
  v34 = 0;
  v32 = 0;
  v33 = 0;
  v35 = 1;
  v37 = 1;
  v30 = 0;
  *(_OWORD *)hMem = 0;
  memset_0(szFile, 0, 0x208u);
  pBuffer = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  if ( !a2 || !a5 )
    goto LABEL_34;
  if ( !*((_QWORD *)this - 10) )
  {
    EntryIDFromIContact = -2147418113;
    goto LABEL_35;
  }
  EntryIDFromIContact = MAPIAllocateBuffer(0x18u, &pBuffer);
  if ( EntryIDFromIContact >= 0 )
  {
    v8 = pBuffer;
    *(_OWORD *)pBuffer = 0;
    v8[2] = 0;
    EntryIDFromIContact = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IContactProperties **))this - 10))(
                            *((_QWORD *)this - 10),
                            &GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f,
                            &v25);
    if ( EntryIDFromIContact >= 0 )
    {
      *(_DWORD *)pBuffer = 1711280386;
      SPropFromIContactProperties = CContactStorage::GetSPropFromIContactProperties(v25, (struct _SPropValue *)pBuffer);
      EntryIDFromIContact = 0;
      if ( SPropFromIContactProperties != -2147024893 )
        EntryIDFromIContact = SPropFromIContactProperties;
      if ( EntryIDFromIContact >= 0 )
      {
        *(_DWORD *)pBuffer = 1711280386;
        EntryIDFromIContact = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, HGLOBAL *))a2->lpVtbl->GetData)(
                                a2,
                                &v31,
                                hMem);
        if ( EntryIDFromIContact >= 0 )
        {
          v10 = (HDROP)GlobalLock(hMem[1]);
          v11 = v10;
          if ( !v10 )
          {
            LastError = HrGetLastError();
LABEL_13:
            EntryIDFromIContact = LastError;
            goto LABEL_35;
          }
          v13 = 0;
          FileW = DragQueryFileW(v10, 0xFFFFFFFF, 0, 0);
          LODWORD(v24) = FileW;
          for ( i = 0; i < FileW; ++i )
          {
            DragQueryFileW(v11, i, szFile, 0x104u);
            ExtensionW = PathFindExtensionW(szFile);
            if ( !StrCmpIW(L".contact", ExtensionW) || !StrCmpIW(L".group", ExtensionW) )
            {
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v26);
              EntryIDFromIContact = CContactStorage::OpenContactReadOnly(szFile, &v26);
              if ( EntryIDFromIContact < 0 )
                goto LABEL_35;
              if ( v28[1] )
              {
                LocalFree(v28[1]);
                v28[1] = 0;
              }
              EntryIDFromIContact = GetEntryIDFromIContact(v26, (struct _SBinary *)v28);
              if ( EntryIDFromIContact < 0 )
                goto LABEL_35;
              v13 = 1;
              EntryIDFromIContact = AddPropToMVPBin((struct _SPropValue *)pBuffer, 0, v28[1], (unsigned int)v28[0], 1);
              if ( EntryIDFromIContact < 0 )
                goto LABEL_35;
            }
            FileW = (unsigned int)v24;
          }
          if ( v13 )
          {
            v17 = v25;
            v24 = 0;
            if ( v25 )
            {
              v18 = pBuffer;
              if ( pBuffer )
              {
                EntryIDFromIContact = CContactStorage::_GetMappingFromPropTag(*(_DWORD *)pBuffer, &v24);
                if ( EntryIDFromIContact >= 0 )
                {
                  v19 = (__int64 (__fastcall *)(struct IContactProperties *, LPVOID))*((_QWORD *)v24 + 2);
                  if ( !v19 || (EntryIDFromIContact = v19(v17, v18), EntryIDFromIContact >= 0) )
                  {
                    v20 = &Str;
                    if ( *((_DWORD *)this - 18) )
                      v20 = (const WCHAR *)*((_QWORD *)this - 8);
                    v27 = 0;
                    EntryIDFromIContact = OpenFileStreamShareW(v20, 3, 0x40000000, 4, &v27);
                    if ( EntryIDFromIContact >= 0 )
                    {
                      LastError = (*(__int64 (__fastcall **)(char *, __int64, __int64))(*((_QWORD *)this - 17) + 48LL))(
                                    (char *)this - 136,
                                    v27,
                                    1);
                      goto LABEL_13;
                    }
                  }
                }
                goto LABEL_35;
              }
            }
LABEL_34:
            EntryIDFromIContact = -2147024809;
          }
        }
      }
    }
  }
LABEL_35:
  v21 = hMem[1];
  if ( hMem[1] )
  {
    GlobalUnlock(hMem[1]);
    v21 = hMem[1];
  }
  if ( v30 )
  {
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v30);
  }
  else if ( v21 )
  {
    GlobalFree(v21);
    hMem[1] = 0;
  }
  MAPIFreeBuffer(pBuffer);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v25);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v26);
  if ( v28[1] )
    LocalFree(v28[1]);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v27);
  return (unsigned int)EntryIDFromIContact;
}

```

## disassembly

```asm
0x18003e060  mov     [rsp-8+arg_10], rbx
0x18003e065  push    rbp
0x18003e066  push    rsi
0x18003e067  push    rdi
0x18003e068  push    r12
0x18003e06a  push    r13
0x18003e06c  push    r14
0x18003e06e  push    r15
0x18003e070  lea     rbp, [rsp-1C0h]
0x18003e078  sub     rsp, 2C0h
0x18003e07f  mov     rax, cs:__security_cookie
0x18003e086  xor     rax, rsp
0x18003e089  mov     [rbp+1F0h+var_40], rax
0x18003e090  mov     eax, 0Fh
0x18003e095  mov     [rbp+1F0h+var_25C], 0FFFFFFFFh
0x18003e09c  mov     [rbp+1F0h+var_270], ax
0x18003e0a0  xor     r13d, r13d
0x18003e0a3  xor     eax, eax
0x18003e0a5  mov     [rbp+1F0h+var_268], r13
0x18003e0a9  mov     [rbp+1F0h+var_26E], eax
0x18003e0ac  mov     rdi, rdx
0x18003e0af  mov     [rbp+1F0h+var_26A], ax
0x18003e0b3  mov     r14, rcx
0x18003e0b6  lea     eax, [r13+1]
0x18003e0ba  xorps   xmm0, xmm0
0x18003e0bd  mov     [rbp+1F0h+var_260], eax
0x18003e0c0  lea     rcx, [rbp+1F0h+szFile]; void *
0x18003e0c4  mov     [rbp+1F0h+var_258], rax
0x18003e0c8  xor     edx, edx; Val
0x18003e0ca  xor     eax, eax
0x18003e0cc  mov     r8d, 208h; Size
0x18003e0d2  mov     [rsp+2F0h+var_278], rax
0x18003e0d7  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x18003e0dc  call    memset_0
0x18003e0e1  mov     [rsp+2F0h+pBuffer], r13
0x18003e0e6  xorps   xmm0, xmm0
0x18003e0e9  mov     [rsp+2F0h+var_2B0], r13
0x18003e0ee  mov     [rsp+2F0h+var_2A8], r13
0x18003e0f3  mov     [rsp+2F0h+var_2A0], r13
0x18003e0f8  movups  xmmword ptr [rsp+2F0h+var_298], xmm0
0x18003e0fd  test    rdi, rdi
0x18003e100  jz      loc_18003E39F
0x18003e106  cmp     [rbp+1F0h+arg_20], r13
0x18003e10d  jz      loc_18003E39F
0x18003e113  lea     r12, [r14-88h]
0x18003e11a  cmp     [r12+38h], r13
0x18003e11f  jnz     short loc_18003E12B
0x18003e121  mov     ebx, 8000FFFFh
0x18003e126  jmp     loc_18003E3A4
0x18003e12b  lea     rdx, [rsp+2F0h+pBuffer]; lppBuffer
0x18003e130  mov     ecx, 18h; cbSize
0x18003e135  call    ?MAPIAllocateBuffer@@YAJKPEAPEAX@Z; MAPIAllocateBuffer(ulong,void * *)
0x18003e13a  mov     ebx, eax
0x18003e13c  test    eax, eax
0x18003e13e  js      loc_18003E3A4
0x18003e144  mov     rax, [rsp+2F0h+pBuffer]
0x18003e149  lea     r8, [rsp+2F0h+var_2B0]
0x18003e14e  xor     ecx, ecx
0x18003e150  lea     rdx, _GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f
0x18003e157  xorps   xmm0, xmm0
0x18003e15a  movups  xmmword ptr [rax], xmm0
0x18003e15d  mov     [rax+10h], rcx
0x18003e161  mov     rcx, [r14-50h]
0x18003e165  mov     rax, [rcx]
0x18003e168  mov     rax, [rax]
0x18003e16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e170  mov     ebx, eax
0x18003e172  test    eax, eax
0x18003e174  js      loc_18003E3A4
0x18003e17a  mov     rax, [rsp+2F0h+pBuffer]
0x18003e17f  mov     esi, 66001102h
0x18003e184  mov     [rax], esi
0x18003e186  mov     rdx, [rsp+2F0h+pBuffer]; struct _SPropValue *
0x18003e18b  mov     rcx, [rsp+2F0h+var_2B0]; struct IContactProperties *
0x18003e190  call    ?GetSPropFromIContactProperties@CContactStorage@@SAJPEAUIContactProperties@@PEAU_SPropValue@@@Z; CContactStorage::GetSPropFromIContactProperties(IContactProperties *,_SPropValue *)
0x18003e195  cmp     eax, 80070003h
0x18003e19a  mov     ebx, r13d
0x18003e19d  cmovnz  ebx, eax
0x18003e1a0  test    ebx, ebx
0x18003e1a2  js      loc_18003E3A4
0x18003e1a8  mov     rax, [rsp+2F0h+pBuffer]
0x18003e1ad  lea     r8, [rsp+2F0h+hMem]
0x18003e1b2  lea     rdx, [rbp+1F0h+var_270]
0x18003e1b6  mov     rcx, rdi
0x18003e1b9  mov     [rax], esi
0x18003e1bb  mov     rax, [rdi]
0x18003e1be  mov     rax, [rax+18h]
0x18003e1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1c7  mov     ebx, eax
0x18003e1c9  test    eax, eax
0x18003e1cb  js      loc_18003E3A4
0x18003e1d1  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18003e1d6  call    cs:__imp_GlobalLock
0x18003e1dc  mov     r15, rax
0x18003e1df  test    rax, rax
0x18003e1e2  jnz     short loc_18003E1F0
0x18003e1e4  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003e1e9  mov     ebx, eax
0x18003e1eb  jmp     loc_18003E3A4
0x18003e1f0  xor     r9d, r9d; cch
0x18003e1f3  xor     r8d, r8d; lpszFile
0x18003e1f6  or      edx, 0FFFFFFFFh; iFile
0x18003e1f9  mov     rcx, r15; hDrop
0x18003e1fc  mov     esi, r13d
0x18003e1ff  call    cs:__imp_DragQueryFileW
0x18003e205  mov     dword ptr [rsp+2F0h+var_2B8], eax
0x18003e209  mov     edi, r13d
0x18003e20c  cmp     edi, eax
0x18003e20e  jnb     loc_18003E2EA
0x18003e214  mov     r9d, 104h; cch
0x18003e21a  lea     r8, [rbp+1F0h+szFile]; lpszFile
0x18003e21e  mov     edx, edi; iFile
0x18003e220  mov     rcx, r15; hDrop
0x18003e223  call    cs:__imp_DragQueryFileW
0x18003e229  lea     rcx, [rbp+1F0h+szFile]; pszPath
0x18003e22d  call    cs:__imp_PathFindExtensionW
0x18003e233  mov     rdx, rax; psz2
0x18003e236  lea     rcx, aContact_1; ".contact"
0x18003e23d  mov     r13, rax
0x18003e240  call    cs:__imp_StrCmpIW
0x18003e246  test    eax, eax
0x18003e248  jz      short loc_18003E263
0x18003e24a  mov     rdx, r13; psz2
0x18003e24d  lea     rcx, aGroup_0; ".group"
0x18003e254  call    cs:__imp_StrCmpIW
0x18003e25a  xor     r13d, r13d
0x18003e25d  test    eax, eax
0x18003e25f  jnz     short loc_18003E2DF
0x18003e261  jmp     short loc_18003E266
0x18003e263  xor     r13d, r13d
0x18003e266  lea     rcx, [rsp+2F0h+var_2A8]
0x18003e26b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003e270  lea     rdx, [rsp+2F0h+var_2A8]; struct IContact **
0x18003e275  lea     rcx, [rbp+1F0h+szFile]; unsigned __int16 *
0x18003e279  call    ?OpenContactReadOnly@CContactStorage@@SAJPEBGPEAPEAUIContact@@@Z; CContactStorage::OpenContactReadOnly(ushort const *,IContact * *)
0x18003e27e  mov     ebx, eax
0x18003e280  test    eax, eax
0x18003e282  js      loc_18003E3A4
0x18003e288  mov     rcx, [rsp+2F0h+var_298+8]; hMem
0x18003e28d  test    rcx, rcx
0x18003e290  jz      short loc_18003E29D
0x18003e292  call    cs:__imp_LocalFree
0x18003e298  mov     [rsp+2F0h+var_298+8], r13
0x18003e29d  mov     rcx, [rsp+2F0h+var_2A8]; struct IContact *
0x18003e2a2  lea     rdx, [rsp+2F0h+var_298]; struct _SBinary *
0x18003e2a7  call    ?GetEntryIDFromIContact@@YAJPEAUIContact@@PEAU_SBinary@@@Z; GetEntryIDFromIContact(IContact *,_SBinary *)
0x18003e2ac  mov     ebx, eax
0x18003e2ae  test    eax, eax
0x18003e2b0  js      loc_18003E3A4
0x18003e2b6  mov     r9d, dword ptr [rsp+2F0h+var_298]; unsigned int
0x18003e2bb  mov     esi, 1
0x18003e2c0  mov     r8, [rsp+2F0h+var_298+8]; void *
0x18003e2c5  xor     edx, edx; unsigned int
0x18003e2c7  mov     rcx, [rsp+2F0h+pBuffer]; lpObject
0x18003e2cc  mov     [rsp+2F0h+var_2D0], esi; int
0x18003e2d0  call    ?AddPropToMVPBin@@YAJPEAU_SPropValue@@KPEAXKH@Z; AddPropToMVPBin(_SPropValue *,ulong,void *,ulong,int)
0x18003e2d5  mov     ebx, eax
0x18003e2d7  test    eax, eax
0x18003e2d9  js      loc_18003E3A4
0x18003e2df  mov     eax, dword ptr [rsp+2F0h+var_2B8]
0x18003e2e3  inc     edi
0x18003e2e5  jmp     loc_18003E20C
0x18003e2ea  test    esi, esi
0x18003e2ec  jz      loc_18003E3A4
0x18003e2f2  mov     rsi, [rsp+2F0h+var_2B0]
0x18003e2f7  mov     [rsp+2F0h+var_2B8], r13
0x18003e2fc  test    rsi, rsi
0x18003e2ff  jz      loc_18003E39F
0x18003e305  mov     rdi, [rsp+2F0h+pBuffer]
0x18003e30a  test    rdi, rdi
0x18003e30d  jz      loc_18003E39F
0x18003e313  mov     ecx, [rdi]; unsigned int
0x18003e315  lea     rdx, [rsp+2F0h+var_2B8]; struct CMapping **
0x18003e31a  call    ?_GetMappingFromPropTag@CContactStorage@@CAJKPEAPEAVCMapping@@@Z; CContactStorage::_GetMappingFromPropTag(ulong,CMapping * *)
0x18003e31f  mov     ebx, eax
0x18003e321  test    eax, eax
0x18003e323  js      short loc_18003E3A4
0x18003e325  mov     r8, [rsp+2F0h+var_2B8]
0x18003e32a  mov     rax, [r8+10h]
0x18003e32e  test    rax, rax
0x18003e331  jz      short loc_18003E344
0x18003e333  mov     rdx, rdi
0x18003e336  mov     rcx, rsi
0x18003e339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e33e  mov     ebx, eax
0x18003e340  test    eax, eax
0x18003e342  js      short loc_18003E3A4
0x18003e344  lea     rcx, Str
0x18003e34b  cmp     [r14-48h], r13d
0x18003e34f  jz      short loc_18003E355
0x18003e351  mov     rcx, [r14-40h]
0x18003e355  mov     edx, 3
0x18003e35a  mov     [rsp+2F0h+var_2A0], r13
0x18003e35f  lea     rax, [rsp+2F0h+var_2A0]
0x18003e364  mov     r8d, 40000000h
0x18003e36a  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18003e36f  lea     r9d, [rdx+1]
0x18003e373  call    cs:__imp_OpenFileStreamShareW
0x18003e379  mov     ebx, eax
0x18003e37b  test    eax, eax
0x18003e37d  js      short loc_18003E3A4
0x18003e37f  mov     rax, [r12]
0x18003e383  mov     r8d, 1
0x18003e389  mov     rdx, [rsp+2F0h+var_2A0]
0x18003e38e  mov     rcx, r12
0x18003e391  mov     rax, [rax+30h]
0x18003e395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e39a  jmp     loc_18003E1E9
0x18003e39f  mov     ebx, 80070057h
0x18003e3a4  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18003e3a9  test    rcx, rcx
0x18003e3ac  jz      short loc_18003E3B9
0x18003e3ae  call    cs:__imp_GlobalUnlock
0x18003e3b4  mov     rcx, [rsp+2F0h+hMem+8]; hMem
0x18003e3b9  cmp     [rsp+2F0h+var_278], r13
0x18003e3be  jz      short loc_18003E3CC
0x18003e3c0  lea     rcx, [rsp+2F0h+var_278]
0x18003e3c5  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003e3ca  jmp     short loc_18003E3DC
0x18003e3cc  test    rcx, rcx
0x18003e3cf  jz      short loc_18003E3DC
0x18003e3d1  call    cs:__imp_GlobalFree
0x18003e3d7  mov     [rsp+2F0h+hMem+8], r13
0x18003e3dc  mov     rcx, [rsp+2F0h+pBuffer]; pv
0x18003e3e1  call    MAPIFreeBuffer
0x18003e3e6  lea     rcx, [rsp+2F0h+var_2B0]
0x18003e3eb  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003e3f0  lea     rcx, [rsp+2F0h+var_2A8]
0x18003e3f5  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003e3fa  mov     rcx, [rsp+2F0h+var_298+8]; hMem
0x18003e3ff  test    rcx, rcx
0x18003e402  jz      short loc_18003E40A
0x18003e404  call    cs:__imp_LocalFree
0x18003e40a  lea     rcx, [rsp+2F0h+var_2A0]
0x18003e40f  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003e414  mov     eax, ebx
0x18003e416  mov     rcx, [rbp+1F0h+var_40]
0x18003e41d  xor     rcx, rsp; StackCookie
0x18003e420  call    __security_check_cookie
0x18003e425  mov     rbx, [rsp+2F0h+arg_10]
0x18003e42d  add     rsp, 2C0h
0x18003e434  pop     r15
0x18003e436  pop     r14
0x18003e438  pop     r13
0x18003e43a  pop     r12
0x18003e43c  pop     rdi
0x18003e43d  pop     rsi
0x18003e43e  pop     rbp
0x18003e43f  retn
```
