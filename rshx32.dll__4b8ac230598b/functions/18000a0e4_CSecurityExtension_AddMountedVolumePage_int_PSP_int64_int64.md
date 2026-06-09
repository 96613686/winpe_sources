# CSecurityExtension::_AddMountedVolumePage(int (*)(_PSP *,__int64),__int64)

- ea: `0x18000a0e4`
- end: `0x18000a394`
- name: `?_AddMountedVolumePage@CSecurityExtension@@AEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `688`
- prototype: `__int64 __fastcall(CSecurityExtension *__hidden this, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008d90`

## callees

- `0x1800064d0`
- `0x18000a0e4`
- `0x18000a39c`
- `0x180016428`
- `0x18001654c`
- `0x1800167b4`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `SHELL32!DragQueryFileW` at `0x18000a1aa`
- `SHELL32!DragQueryFileW` at `0x18000a1aa`
- `SHLWAPI!PathAddBackslashW` at `0x18000a1dc`
- `SHLWAPI!PathAddBackslashW` at `0x18000a1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a280`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a377`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a389`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a389`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000a22d`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000a22d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000a1f0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000a1f0`
- `USER32!RegisterClipboardFormatW` at `0x18000a12e`
- `USER32!RegisterClipboardFormatW` at `0x18000a12e`
- `ole32!ReleaseStgMedium` at `0x18000a252`
- `ole32!ReleaseStgMedium` at `0x18000a252`

## string_xrefs

- `0x18000a127`: `MountedVolume`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::_AddMountedVolumePage(
        CSecurityExtension *this,
        int (*a2)(struct _PSP *, __int64),
        __int64 a3)
{
  unsigned __int16 v4; // cx
  __int64 v7; // rcx
  int v8; // ebx
  void *v10; // rdi
  int v11; // eax
  HINSTANCE v12; // rdx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+52h] [rbp-AEh]
  __int16 v18; // [rsp+56h] [rbp-AAh]
  __int64 v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+64h] [rbp-9Ch]
  __int64 v22; // [rsp+68h] [rbp-98h]
  STGMEDIUM hDrop; // [rsp+78h] [rbp-88h] BYREF
  WCHAR VolumeNameBuffer[64]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szFile[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR szVolumeName[264]; // [rsp+320h] [rbp+220h] BYREF

  v4 = g_cfMountedVolume;
  if ( !g_cfMountedVolume )
  {
    v4 = RegisterClipboardFormatW(L"MountedVolume");
    g_cfMountedVolume = v4;
  }
  v16 = v4;
  v7 = *((_QWORD *)this + 4);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 1;
  v22 = 1;
  memset(&hDrop, 0, sizeof(hDrop));
  v21 = -1;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, STGMEDIUM *))(*(_QWORD *)v7 + 24LL))(v7, &v16, &hDrop);
  if ( v8 >= 0 )
  {
    if ( !DragQueryFileW((HDROP)hDrop.hBitmap, 0, szFile, 0x104u) )
      goto LABEL_8;
    FileSystemFlags = 0;
    v15[0] = 8;
    v15[1] = 9;
    v14 = 0;
    PathAddBackslashW(szFile);
    if ( !GetVolumeNameForVolumeMountPointW(szFile, szVolumeName, 0x104u) )
      goto LABEL_8;
    if ( GetVolumeInformationW(szFile, VolumeNameBuffer, 0x40u, 0, 0, &FileSystemFlags, 0, 0) )
    {
      if ( (FileSystemFlags & 8) == 0 )
      {
LABEL_8:
        v8 = -2147467259;
        goto LABEL_9;
      }
    }
    else if ( GetLastError() != 5 )
    {
      goto LABEL_8;
    }
    v10 = (void *)EnablePrivileges(v15, 2);
    v8 = CheckFileAccess(szVolumeName, &v14);
    if ( v8 >= 0 )
    {
      if ( (v14 & 0x10E0000) != 0 )
      {
        v11 = *((_DWORD *)this + 11);
        if ( (v14 & 0x40000) == 0 )
          v11 |= 8u;
        if ( (v14 & 0x80000) == 0 )
        {
          if ( (v14 & 0x20000) != 0 )
            v11 |= 0x40u;
          else
            v11 &= ~1u;
        }
        if ( (v14 & 0x1000000) == 0 )
          v11 &= ~2u;
        v12 = g_hInstance;
        *((_DWORD *)this + 11) = v11 | 0x204;
        if ( !FormatStringID((unsigned __int16 **)this + 7, v12, 9u, VolumeNameBuffer, szFile) )
          LocalAllocString((unsigned __int16 **)this + 7, VolumeNameBuffer);
        if ( *((_QWORD *)this + 7) )
        {
          v8 = LocalAllocString((unsigned __int16 **)this + 8, szVolumeName);
          if ( v8 >= 0 )
            v8 = CSecurityExtension::_AddSecurityPage(this, a2, a3);
        }
        else
        {
          v8 = -2147024882;
        }
      }
      else
      {
        v8 = -2147024891;
      }
    }
    if ( v10 != (void *)-1LL )
    {
      SetThreadToken(0, v10);
      if ( v10 )
        CloseHandle(v10);
    }
  }
LABEL_9:
  if ( hDrop.tymed )
    ReleaseStgMedium(&hDrop);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a0e4  mov     [rsp-8+arg_8], rbx
0x18000a0e9  push    rbp
0x18000a0ea  push    rsi
0x18000a0eb  push    rdi
0x18000a0ec  push    r14
0x18000a0ee  push    r15
0x18000a0f0  lea     rbp, [rsp-440h]
0x18000a0f8  sub     rsp, 540h
0x18000a0ff  mov     rax, cs:__security_cookie
0x18000a106  xor     rax, rsp
0x18000a109  mov     [rbp+460h+var_30], rax
0x18000a110  mov     rsi, rcx
0x18000a113  xor     eax, eax
0x18000a115  movzx   ecx, cs:?g_cfMountedVolume@@3GA; ushort g_cfMountedVolume
0x18000a11c  mov     r15, r8
0x18000a11f  mov     r14, rdx
0x18000a122  cmp     ax, cx
0x18000a125  jnz     short loc_18000A13D
0x18000a127  lea     rcx, aMountedvolume; "MountedVolume"
0x18000a12e  call    cs:__imp_RegisterClipboardFormatW
0x18000a134  mov     ecx, eax
0x18000a136  mov     cs:?g_cfMountedVolume@@3GA, ax; ushort g_cfMountedVolume
0x18000a13d  xor     eax, eax
0x18000a13f  mov     [rsp+560h+var_510], cx
0x18000a144  mov     rcx, [rsi+20h]
0x18000a148  lea     r8, [rsp+560h+hDrop]
0x18000a14d  mov     [rbp+460h+var_4D8], rax
0x18000a151  lea     rdx, [rsp+560h+var_510]
0x18000a156  mov     [rsp+560h+var_50E], eax
0x18000a15a  xorps   xmm0, xmm0
0x18000a15d  mov     [rsp+560h+var_50A], ax
0x18000a162  mov     [rsp+560h+var_508], rax
0x18000a167  mov     eax, 1
0x18000a16c  mov     [rsp+560h+var_500], eax
0x18000a170  mov     [rsp+560h+var_4F8], rax
0x18000a175  movups  xmmword ptr [rsp+560h+hDrop], xmm0
0x18000a17a  mov     [rsp+560h+var_4FC], 0FFFFFFFFh
0x18000a182  mov     rax, [rcx]
0x18000a185  mov     rax, [rax+18h]
0x18000a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18e  mov     ebx, eax
0x18000a190  test    eax, eax
0x18000a192  js      loc_18000A246
0x18000a198  mov     rcx, [rbp+460h+hDrop+8]; hDrop
0x18000a19c  lea     r8, [rbp+460h+szFile]; lpszFile
0x18000a1a0  mov     ebx, 104h
0x18000a1a5  xor     edx, edx; iFile
0x18000a1a7  mov     r9d, ebx; cch
0x18000a1aa  call    cs:__imp_DragQueryFileW
0x18000a1b0  test    eax, eax
0x18000a1b2  jz      loc_18000A241
0x18000a1b8  lea     rcx, [rbp+460h+szFile]; pszPath
0x18000a1bc  mov     [rsp+560h+FileSystemFlags], 0
0x18000a1c4  mov     [rsp+560h+var_518], 8
0x18000a1cc  mov     [rsp+560h+var_514], 9
0x18000a1d4  mov     [rsp+560h+var_51C], 0
0x18000a1dc  call    cs:__imp_PathAddBackslashW
0x18000a1e2  mov     r8d, ebx; cchBufferLength
0x18000a1e5  lea     rdx, [rbp+460h+szVolumeName]; lpszVolumeName
0x18000a1ec  lea     rcx, [rbp+460h+szFile]; lpszVolumeMountPoint
0x18000a1f0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18000a1f6  test    eax, eax
0x18000a1f8  jz      short loc_18000A241
0x18000a1fa  mov     [rsp+560h+nFileSystemNameSize], 0; nFileSystemNameSize
0x18000a202  lea     rax, [rsp+560h+FileSystemFlags]
0x18000a207  xor     r9d, r9d; lpVolumeSerialNumber
0x18000a20a  mov     [rsp+560h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x18000a213  mov     [rsp+560h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000a218  lea     rdx, [rbp+460h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18000a21c  lea     rcx, [rbp+460h+szFile]; lpRootPathName
0x18000a220  mov     [rsp+560h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18000a229  lea     r8d, [r9+40h]; nVolumeNameSize
0x18000a22d  call    cs:__imp_GetVolumeInformationW
0x18000a233  test    eax, eax
0x18000a235  jz      short loc_18000A280
0x18000a237  test    [rsp+560h+FileSystemFlags], 8
0x18000a23f  jnz     short loc_18000A28B
0x18000a241  mov     ebx, 80004005h
0x18000a246  cmp     dword ptr [rsp+560h+hDrop], 0
0x18000a24b  jz      short loc_18000A258
0x18000a24d  lea     rcx, [rsp+560h+hDrop]; LPSTGMEDIUM
0x18000a252  call    cs:__imp_ReleaseStgMedium
0x18000a258  mov     eax, ebx
0x18000a25a  mov     rcx, [rbp+460h+var_30]
0x18000a261  xor     rcx, rsp; StackCookie
0x18000a264  call    __security_check_cookie
0x18000a269  mov     rbx, [rsp+560h+arg_8]
0x18000a271  add     rsp, 540h
0x18000a278  pop     r15
0x18000a27a  pop     r14
0x18000a27c  pop     rdi
0x18000a27d  pop     rsi
0x18000a27e  pop     rbp
0x18000a27f  retn
0x18000a280  call    cs:__imp_GetLastError
0x18000a286  cmp     eax, 5
0x18000a289  jnz     short loc_18000A241
0x18000a28b  mov     edx, 2
0x18000a290  lea     rcx, [rsp+560h+var_518]
0x18000a295  call    EnablePrivileges
0x18000a29a  lea     rdx, [rsp+560h+var_51C]; unsigned int *
0x18000a29f  mov     rdi, rax
0x18000a2a2  lea     rcx, [rbp+460h+szVolumeName]; unsigned __int16 *
0x18000a2a9  call    ?CheckFileAccess@@YAJPEBGPEAK@Z; CheckFileAccess(ushort const *,ulong *)
0x18000a2ae  mov     ebx, eax
0x18000a2b0  test    eax, eax
0x18000a2b2  js      loc_18000A368
0x18000a2b8  mov     ecx, [rsp+560h+var_51C]
0x18000a2bc  test    ecx, 10E0000h
0x18000a2c2  jnz     short loc_18000A2CE
0x18000a2c4  mov     ebx, 80070005h
0x18000a2c9  jmp     loc_18000A368
0x18000a2ce  mov     eax, [rsi+2Ch]
0x18000a2d1  bt      ecx, 12h
0x18000a2d5  jb      short loc_18000A2DA
0x18000a2d7  or      eax, 8
0x18000a2da  bt      ecx, 13h
0x18000a2de  jb      short loc_18000A2EE
0x18000a2e0  bt      ecx, 11h
0x18000a2e4  jb      short loc_18000A2EB
0x18000a2e6  and     eax, 0FFFFFFFEh
0x18000a2e9  jmp     short loc_18000A2EE
0x18000a2eb  or      eax, 40h
0x18000a2ee  bt      ecx, 18h
0x18000a2f2  jb      short loc_18000A2F7
0x18000a2f4  and     eax, 0FFFFFFFDh
0x18000a2f7  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18000a2fe  lea     rbx, [rsi+38h]
0x18000a302  or      eax, 204h
0x18000a307  lea     r9, [rbp+460h+VolumeNameBuffer]
0x18000a30b  mov     [rsi+2Ch], eax
0x18000a30e  mov     r8d, 9; unsigned int
0x18000a314  lea     rax, [rbp+460h+szFile]
0x18000a318  mov     rcx, rbx; unsigned __int16 **
0x18000a31b  mov     [rsp+560h+lpMaximumComponentLength], rax
0x18000a320  call    ?FormatStringID@@YAKPEAPEAGPEAUHINSTANCE__@@IZZ; FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x18000a325  test    eax, eax
0x18000a327  jnz     short loc_18000A335
0x18000a329  lea     rdx, [rbp+460h+VolumeNameBuffer]; unsigned __int16 *
0x18000a32d  mov     rcx, rbx; unsigned __int16 **
0x18000a330  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18000a335  cmp     qword ptr [rbx], 0
0x18000a339  jnz     short loc_18000A342
0x18000a33b  mov     ebx, 8007000Eh
0x18000a340  jmp     short loc_18000A368
0x18000a342  lea     rcx, [rsi+40h]; unsigned __int16 **
0x18000a346  lea     rdx, [rbp+460h+szVolumeName]; unsigned __int16 *
0x18000a34d  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x18000a352  mov     ebx, eax
0x18000a354  test    eax, eax
0x18000a356  js      short loc_18000A368
0x18000a358  mov     r8, r15; __int64
0x18000a35b  mov     rdx, r14; int (*)(struct _PSP *, __int64)
0x18000a35e  mov     rcx, rsi; this
0x18000a361  call    ?_AddSecurityPage@CSecurityExtension@@AEAAJP6AHPEAU_PSP@@_J@Z1@Z; CSecurityExtension::_AddSecurityPage(int (*)(_PSP *,__int64),__int64)
0x18000a366  mov     ebx, eax
0x18000a368  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a36c  jz      loc_18000A246
0x18000a372  mov     rdx, rdi; Token
0x18000a375  xor     ecx, ecx; Thread
0x18000a377  call    cs:__imp_SetThreadToken
0x18000a37d  test    rdi, rdi
0x18000a380  jz      loc_18000A246
0x18000a386  mov     rcx, rdi; hObject
0x18000a389  call    cs:__imp_CloseHandle
0x18000a38f  jmp     loc_18000A246
```
