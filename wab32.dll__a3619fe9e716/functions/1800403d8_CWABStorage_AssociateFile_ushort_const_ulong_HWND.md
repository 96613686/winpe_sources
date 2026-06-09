# CWABStorage::AssociateFile(ushort const *,ulong,HWND__ *)

- ea: `0x1800403d8`
- end: `0x180040753`
- name: `?AssociateFile@CWABStorage@@IEAAJPEBGKPEAUHWND__@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(CWABStorage *__hidden this, const unsigned __int16 *, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180042774`

## callees

- `0x180001d18`
- `0x1800045e4`
- `0x18001d778`
- `0x180030ec0`
- `0x180031618`
- `0x1800323b8`
- `0x180032704`
- `0x1800403d8`
- `0x18004273c`
- `0x180045008`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180040712`
- `KERNEL32!ReleaseMutex` at `0x180040712`
- `KERNEL32!CreateMutexW` at `0x18004045b`
- `KERNEL32!CreateMutexW` at `0x18004045b`
- `KERNEL32!MoveFileW` at `0x18004063d`
- `KERNEL32!MoveFileW` at `0x18004063d`
- `KERNEL32!LocalAlloc` at `0x180040437`
- `KERNEL32!LocalAlloc` at `0x1800404ad`
- `KERNEL32!LocalAlloc` at `0x1800404eb`
- `KERNEL32!LocalAlloc` at `0x180040437`
- `KERNEL32!LocalAlloc` at `0x1800404ad`
- `KERNEL32!LocalAlloc` at `0x1800404eb`
- `KERNEL32!CloseHandle` at `0x180040620`
- `KERNEL32!CloseHandle` at `0x1800406ff`
- `KERNEL32!CloseHandle` at `0x180040620`
- `KERNEL32!CloseHandle` at `0x1800406ff`
- `KERNEL32!DeleteFileW` at `0x180040612`
- `KERNEL32!DeleteFileW` at `0x180040653`
- `KERNEL32!DeleteFileW` at `0x180040612`
- `KERNEL32!DeleteFileW` at `0x180040653`
- `KERNEL32!FindFirstFileW` at `0x180040522`
- `KERNEL32!FindFirstFileW` at `0x180040522`
- `KERNEL32!FindClose` at `0x18004053e`
- `KERNEL32!FindClose` at `0x18004053e`
- `USER32!GetDesktopWindow` at `0x18004054e`
- `USER32!GetDesktopWindow` at `0x18004054e`

## string_xrefs

- `0x180040450`: `Local\MPSWabDataAccessMutex`

## pseudocode

```c
__int64 __fastcall CWABStorage::AssociateFile(CWABStorage *this, const unsigned __int16 *a2, __int64 a3, HWND a4)
{
  HANDLE v6; // rsi
  int v8; // r12d
  HLOCAL v9; // rax
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // r14
  unsigned __int16 *v13; // rcx
  HANDLE FirstFileW; // rax
  HWND v15; // rdx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  int v21; // r14d
  HANDLE hObject; // [rsp+20h] [rbp-E0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = 0;
  v9 = LocalAlloc(0x40u, 0x38u);
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
LABEL_2:
    v10 = -2147024882;
    goto LABEL_37;
  }
  *(_QWORD *)(*((_QWORD *)this + 1) + 48LL) = CreateMutexW(0, 0, L"Local\\MPSWabDataAccessMutex");
  if ( (unsigned int)CWABStorage::LockFile(this) )
  {
    v8 = 1;
    *(_QWORD *)(*((_QWORD *)this + 1) + 24LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 1) + 40LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 1) + 24LL) = LocalAlloc(0x40u, 0xA4u);
    if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) )
      goto LABEL_2;
    if ( a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
    }
    else
    {
      LODWORD(v11) = 0;
    }
    v12 = (unsigned int)(v11 + 1);
    *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = LocalAlloc(0x40u, 2 * v12);
    v13 = *(unsigned __int16 **)(*((_QWORD *)this + 1) + 16LL);
    if ( !v13 )
      goto LABEL_2;
    StringCchCopyW(v13, (unsigned int)v12, a2);
    FirstFileW = FindFirstFileW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL), &FindFileData);
    v6 = FirstFileW;
    if ( FirstFileW == (HANDLE)-1LL )
    {
      v10 = -2147467259;
    }
    else
    {
      FindClose(FirstFileW);
      hObject = 0;
      if ( !a4 )
        GetDesktopWindow();
      do
      {
        v16 = OpenWABFile(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL), v15, &hObject);
        v6 = hObject;
        v10 = v16;
        if ( hObject == (HANDLE)-1LL || v16 < 0 )
          break;
        v17 = VerifyWABVersion(hObject, *((_QWORD *)this + 1));
        v10 = v17;
        if ( v17 >= 0 )
        {
          v20 = *((_QWORD *)this + 1);
          if ( !*(_DWORD *)(*(_QWORD *)(v20 + 24) + 128LL)
            && ((int)HrDoQuickWABIntegrityCheck((struct _tagMPSWabFileInfo *)v20, v6) < 0
             || !(unsigned int)ReloadMPSWabFileInfo(*((struct _tagMPSWabFileInfo **)this + 1), v6))
            || (v21 = 0, (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 24LL) + 128LL) & 0x110) != 0) )
          {
            v21 = 1;
            v10 = HrDoDetailedWABIntegrityCheck(*((struct _tagMPSWabFileInfo **)this + 1), v6);
            if ( v10 < 0 )
              goto LABEL_39;
          }
          v10 = 0;
          *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) = 0;
          if ( v21 )
            goto LABEL_39;
          break;
        }
        if ( v17 != -2147221232 )
          break;
        StringCchCopyW(FileName, 0x104u, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 16LL));
        v18 = -1;
        do
          ++v18;
        while ( FileName[v18] );
        if ( (unsigned int)v18 < 2 )
        {
          v10 = -2147418113;
          break;
        }
        v19 = v18 - 2;
        if ( 2 * (unsigned __int64)v19 >= 0x208 )
          _report_rangecheckfailure();
        FileName[v19] = 0;
        StringCchCatW(FileName, 0x104u, L"~b");
        DeleteFileW(FileName);
        if ( v6 )
        {
          CloseHandle(v6);
          v6 = 0;
          hObject = 0;
        }
      }
      while ( MoveFileW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL), FileName)
           || DeleteFileW(*(LPCWSTR *)(*((_QWORD *)this + 1) + 16LL)) );
    }
  }
  else
  {
    v10 = -2147024891;
  }
LABEL_37:
  if ( (int)HrDoQuickWABIntegrityCheck(*((struct _tagMPSWabFileInfo **)this + 1), v6) < 0 )
    v10 = HrDoDetailedWABIntegrityCheck(*((struct _tagMPSWabFileInfo **)this + 1), v6);
LABEL_39:
  if ( v6 )
    CloseHandle(v6);
  if ( v8 )
    ReleaseMutex(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL));
  if ( v10 >= 0 )
    *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) = 1;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800403d8  mov     [rsp-8+arg_10], rbx
0x1800403dd  push    rbp
0x1800403de  push    rsi
0x1800403df  push    rdi
0x1800403e0  push    r12
0x1800403e2  push    r13
0x1800403e4  push    r14
0x1800403e6  push    r15
0x1800403e8  lea     rbp, [rsp-3A0h]
0x1800403f0  sub     rsp, 4A0h
0x1800403f7  mov     rax, cs:__security_cookie
0x1800403fe  xor     rax, rsp
0x180040401  mov     [rbp+3D0h+var_40], rax
0x180040408  mov     rbx, rdx
0x18004040b  mov     rdi, rcx
0x18004040e  xor     r13d, r13d
0x180040411  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x180040416  xor     edx, edx; Val
0x180040418  mov     r8d, 250h; Size
0x18004041e  mov     esi, r13d
0x180040421  mov     r15, r9
0x180040424  call    memset_0
0x180040429  lea     r14d, [r13+40h]
0x18004042d  mov     r12d, r13d
0x180040430  mov     ecx, r14d; uFlags
0x180040433  lea     edx, [r13+38h]; uBytes
0x180040437  call    cs:__imp_LocalAlloc
0x18004043d  mov     [rdi+8], rax
0x180040441  test    rax, rax
0x180040444  jnz     short loc_180040450
0x180040446  mov     ebx, 8007000Eh
0x18004044b  jmp     loc_1800406D9
0x180040450  lea     r8, Name; "Local\\MPSWabDataAccessMutex"
0x180040457  xor     edx, edx; bInitialOwner
0x180040459  xor     ecx, ecx; lpMutexAttributes
0x18004045b  call    cs:__imp_CreateMutexW
0x180040461  mov     rcx, [rdi+8]
0x180040465  mov     [rcx+30h], rax
0x180040469  mov     rcx, rdi; this
0x18004046c  call    ?LockFile@CWABStorage@@AEAAHXZ; CWABStorage::LockFile(void)
0x180040471  test    eax, eax
0x180040473  jnz     short loc_18004047F
0x180040475  mov     ebx, 80070005h
0x18004047a  jmp     loc_1800406D9
0x18004047f  mov     rax, [rdi+8]
0x180040483  mov     edx, 0A4h; uBytes
0x180040488  mov     ecx, r14d; uFlags
0x18004048b  mov     r12d, 1
0x180040491  mov     [rax+18h], r13
0x180040495  mov     rax, [rdi+8]
0x180040499  mov     [rax+10h], r13
0x18004049d  mov     rax, [rdi+8]
0x1800404a1  mov     [rax+20h], r13
0x1800404a5  mov     rax, [rdi+8]
0x1800404a9  mov     [rax+28h], r13
0x1800404ad  call    cs:__imp_LocalAlloc
0x1800404b3  mov     rcx, [rdi+8]
0x1800404b7  mov     [rcx+18h], rax
0x1800404bb  mov     rax, [rdi+8]
0x1800404bf  cmp     [rax+18h], r13
0x1800404c3  jz      short loc_180040446
0x1800404c5  test    rbx, rbx
0x1800404c8  jz      short loc_1800404DA
0x1800404ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800404ce  inc     rax
0x1800404d1  cmp     [rbx+rax*2], r13w
0x1800404d6  jnz     short loc_1800404CE
0x1800404d8  jmp     short loc_1800404DD
0x1800404da  mov     rax, r13
0x1800404dd  inc     eax
0x1800404df  mov     ecx, 40h ; '@'; uFlags
0x1800404e4  mov     r14d, eax
0x1800404e7  lea     rdx, [rax+rax]; uBytes
0x1800404eb  call    cs:__imp_LocalAlloc
0x1800404f1  mov     rcx, [rdi+8]
0x1800404f5  mov     [rcx+10h], rax
0x1800404f9  mov     rax, [rdi+8]
0x1800404fd  mov     rcx, [rax+10h]; unsigned __int16 *
0x180040501  test    rcx, rcx
0x180040504  jz      loc_180040446
0x18004050a  mov     r8, rbx; unsigned __int16 *
0x18004050d  mov     edx, r14d; unsigned __int64
0x180040510  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040515  mov     rcx, [rdi+8]
0x180040519  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x18004051e  mov     rcx, [rcx+10h]; lpFileName
0x180040522  call    cs:__imp_FindFirstFileW
0x180040528  mov     rsi, rax
0x18004052b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004052f  jnz     short loc_18004053B
0x180040531  mov     ebx, 80004005h
0x180040536  jmp     loc_1800406D9
0x18004053b  mov     rcx, rax; hFindFile
0x18004053e  call    cs:__imp_FindClose
0x180040544  mov     [rsp+4D0h+hObject], r13
0x180040549  test    r15, r15
0x18004054c  jnz     short loc_180040554
0x18004054e  call    cs:__imp_GetDesktopWindow
0x180040554  mov     r14d, 104h
0x18004055a  mov     rcx, [rdi+8]
0x18004055e  lea     r8, [rsp+4D0h+hObject]; void **
0x180040563  mov     rcx, [rcx+10h]; lpFileName
0x180040567  call    ?OpenWABFile@@YAJPEAGPEAUHWND__@@PEAPEAX@Z; OpenWABFile(ushort *,HWND__ *,void * *)
0x18004056c  mov     rsi, [rsp+4D0h+hObject]
0x180040571  mov     ebx, eax
0x180040573  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180040577  jz      loc_1800406D9
0x18004057d  test    eax, eax
0x18004057f  js      loc_1800406D9
0x180040585  mov     rdx, [rdi+8]
0x180040589  mov     rcx, rsi
0x18004058c  call    _VerifyWABVersion
0x180040591  mov     ebx, eax
0x180040593  test    eax, eax
0x180040595  jns     loc_180040670
0x18004059b  cmp     eax, 80040110h
0x1800405a0  jnz     loc_1800406D9
0x1800405a6  mov     r8, [rdi+8]
0x1800405aa  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x1800405b1  mov     rdx, r14; unsigned __int64
0x1800405b4  mov     r8, [r8+10h]; unsigned __int16 *
0x1800405b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800405bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800405c1  lea     r11, [rbp+3D0h+FileName]
0x1800405c8  inc     rax
0x1800405cb  cmp     [r11+rax*2], r13w
0x1800405d0  jnz     short loc_1800405C8
0x1800405d2  cmp     eax, 2
0x1800405d5  jb      loc_180040669
0x1800405db  add     eax, 0FFFFFFFEh
0x1800405de  mov     ecx, eax
0x1800405e0  add     rcx, rcx
0x1800405e3  cmp     rcx, 208h
0x1800405ea  jnb     short loc_180040663
0x1800405ec  mov     [rbp+rcx+3D0h+FileName], r13w
0x1800405f5  lea     r8, aB; "~b"
0x1800405fc  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x180040603  mov     rdx, r14; unsigned __int64
0x180040606  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004060b  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x180040612  call    cs:__imp_DeleteFileW
0x180040618  test    rsi, rsi
0x18004061b  jz      short loc_18004062E
0x18004061d  mov     rcx, rsi; hObject
0x180040620  call    cs:__imp_CloseHandle
0x180040626  mov     rsi, r13
0x180040629  mov     [rsp+4D0h+hObject], r13
0x18004062e  mov     rcx, [rdi+8]
0x180040632  lea     rdx, [rbp+3D0h+FileName]; lpNewFileName
0x180040639  mov     rcx, [rcx+10h]; lpExistingFileName
0x18004063d  call    cs:__imp_MoveFileW
0x180040643  test    eax, eax
0x180040645  jnz     loc_18004055A
0x18004064b  mov     rcx, [rdi+8]
0x18004064f  mov     rcx, [rcx+10h]; lpFileName
0x180040653  call    cs:__imp_DeleteFileW
0x180040659  test    eax, eax
0x18004065b  jnz     loc_18004055A
0x180040661  jmp     short loc_1800406D9
0x180040663  call    __report_rangecheckfailure
0x180040669  mov     ebx, 8000FFFFh
0x18004066e  jmp     short loc_1800406D9
0x180040670  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040674  mov     rax, [rcx+18h]
0x180040678  cmp     [rax+80h], r13d
0x18004067f  jnz     short loc_18004069D
0x180040681  mov     rdx, rsi; void *
0x180040684  call    ?HrDoQuickWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoQuickWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x180040689  test    eax, eax
0x18004068b  js      short loc_1800406B4
0x18004068d  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040691  mov     rdx, rsi; void *
0x180040694  call    ?ReloadMPSWabFileInfo@@YAHPEAU_tagMPSWabFileInfo@@PEAX@Z; ReloadMPSWabFileInfo(_tagMPSWabFileInfo *,void *)
0x180040699  test    eax, eax
0x18004069b  jz      short loc_1800406B4
0x18004069d  mov     rax, [rdi+8]
0x1800406a1  mov     r14d, r13d
0x1800406a4  mov     rcx, [rax+18h]
0x1800406a8  test    dword ptr [rcx+80h], 110h
0x1800406b2  jz      short loc_1800406C9
0x1800406b4  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x1800406b8  mov     rdx, rsi; void *
0x1800406bb  mov     r14d, r12d
0x1800406be  call    ?HrDoDetailedWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoDetailedWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x1800406c3  mov     ebx, eax
0x1800406c5  test    eax, eax
0x1800406c7  js      short loc_1800406F7
0x1800406c9  mov     rax, [rdi+8]
0x1800406cd  mov     ebx, r13d
0x1800406d0  mov     [rax+8], r13d
0x1800406d4  test    r14d, r14d
0x1800406d7  jnz     short loc_1800406F7
0x1800406d9  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x1800406dd  mov     rdx, rsi; void *
0x1800406e0  call    ?HrDoQuickWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoQuickWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x1800406e5  test    eax, eax
0x1800406e7  jns     short loc_1800406F7
0x1800406e9  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x1800406ed  mov     rdx, rsi; void *
0x1800406f0  call    ?HrDoDetailedWABIntegrityCheck@@YAJPEAU_tagMPSWabFileInfo@@PEAX@Z; HrDoDetailedWABIntegrityCheck(_tagMPSWabFileInfo *,void *)
0x1800406f5  mov     ebx, eax
0x1800406f7  test    rsi, rsi
0x1800406fa  jz      short loc_180040705
0x1800406fc  mov     rcx, rsi; hObject
0x1800406ff  call    cs:__imp_CloseHandle
0x180040705  test    r12d, r12d
0x180040708  jz      short loc_180040718
0x18004070a  mov     rcx, [rdi+8]
0x18004070e  mov     rcx, [rcx+30h]; hMutex
0x180040712  call    cs:__imp_ReleaseMutex
0x180040718  test    ebx, ebx
0x18004071a  js      short loc_180040727
0x18004071c  mov     rax, [rdi+8]
0x180040720  mov     dword ptr [rax+4], 1
0x180040727  mov     eax, ebx
0x180040729  mov     rcx, [rbp+3D0h+var_40]
0x180040730  xor     rcx, rsp; StackCookie
0x180040733  call    __security_check_cookie
0x180040738  mov     rbx, [rsp+4D0h+arg_10]
0x180040740  add     rsp, 4A0h
0x180040747  pop     r15
0x180040749  pop     r14
0x18004074b  pop     r13
0x18004074d  pop     r12
0x18004074f  pop     rdi
0x180040750  pop     rsi
0x180040751  pop     rbp
0x180040752  retn
```
