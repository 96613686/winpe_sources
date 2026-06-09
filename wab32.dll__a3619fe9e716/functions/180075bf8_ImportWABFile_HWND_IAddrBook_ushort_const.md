# ImportWABFile(HWND__ *,IAddrBook *,ushort const *)

- ea: `0x180075bf8`
- end: `0x180075fc1`
- name: `?ImportWABFile@@YAJPEAUHWND__@@PEAUIAddrBook@@PEBG@Z`
- size: `969`
- prototype: `__int64 __fastcall(HWND, struct IAddrBook *, LPCWSTR pszPath)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180074f10`
- `0x180075194`
- `0x180075fd0`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x1800093c4`
- `0x18002fe40`
- `0x180042774`
- `0x180045530`
- `0x1800455d0`
- `0x180045af4`
- `0x180069e24`
- `0x180075bf8`
- `0x18007627c`
- `0x180076400`
- `0x18007671c`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `SHLWAPI!SHRegSetUSValueW` at `0x180075e98`
- `SHLWAPI!SHRegSetUSValueW` at `0x180075e98`
- `SHLWAPI!PathFindFileNameW` at `0x180075e72`
- `SHLWAPI!PathFindFileNameW` at `0x180075e72`
- `KERNEL32!LocalFree` at `0x180075eff`
- `KERNEL32!LocalFree` at `0x180075f0e`
- `KERNEL32!LocalFree` at `0x180075eff`
- `KERNEL32!LocalFree` at `0x180075f0e`
- `KERNEL32!DeleteFileW` at `0x180075ee1`
- `KERNEL32!DeleteFileW` at `0x180075ee1`
- `RPCRT4!UuidCreate` at `0x180075ca2`
- `RPCRT4!UuidCreate` at `0x180075ca2`
- `USER32!EnableWindow` at `0x180075d1f`
- `USER32!EnableWindow` at `0x180075f21`
- `USER32!EnableWindow` at `0x180075d1f`
- `USER32!EnableWindow` at `0x180075f21`

## pseudocode

```c
__int64 __fastcall ImportWABFile(HWND a1, struct IAddrBook *a2, LPCWSTR pszPath)
{
  unsigned int v3; // r15d
  int v7; // r12d
  const struct _GUID *v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  int FileToImport; // ebx
  unsigned int v12; // edx
  const unsigned __int16 *v13; // rcx
  int v14; // eax
  struct CWABStorage *v15; // rdi
  int v16; // ebx
  unsigned int v17; // r14d
  int v18; // eax
  const WCHAR *FileNameW; // rax
  int v20; // edx
  const struct _GUID *v21; // rcx
  unsigned __int64 v22; // r8
  int cbData; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  __int16 pvData; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  struct CWABStorage *v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL hMem[2]; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v32; // [rsp+88h] [rbp-78h]
  void *v33; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h]
  UUID Uuid; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v38[264]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = 0;
  v25 = 0;
  v27 = 0;
  v36 = 0;
  v7 = 0;
  v29 = 0;
  v35 = 0;
  *(_OWORD *)pv = 0;
  STRW::STRW((STRW *)&v33, v38, 0x104u);
  v28 = 0;
  v32 = 0;
  Uuid = 0;
  *(_OWORD *)hMem = 0;
  v9 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v9 )
    ShellPrivateTraceEvent(v8, 0x34u, v9, 1u);
  if ( UuidCreate(&Uuid) )
  {
    FileToImport = -2147024882;
  }
  else
  {
    FileToImport = GetFileToImport(v10, pszPath, &v33);
    if ( FileToImport >= 0 )
    {
      v13 = &Str;
      if ( (_DWORD)v33 )
        v13 = lpFileName[0];
      v14 = CWABStorage::OpenStoreFromFile(v13, v12, a1, &v28);
      v15 = v28;
      FileToImport = v14;
      if ( v14 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(struct CWABStorage *))(*(_QWORD *)v28 + 72LL))(v28);
        if ( v16 )
        {
          if ( a1 )
          {
            EnableWindow(a1, 0);
            CreateShowAbortDialog(a1, 4419, 6010, v16 + 1, cbData);
          }
          FileToImport = _MapOldNamedPropsToNewNamedProps(v15, a2, (struct NamedPropertyMapping *)hMem);
          if ( FileToImport >= 0 )
          {
            FileToImport = ((__int64 (__fastcall *)(struct IAddrBook *, LPVOID *, LPVOID *))a2->lpVtbl->GetPAB)(
                             a2,
                             pv,
                             &pv[1]);
            if ( FileToImport >= 0 )
            {
              v17 = 0;
LABEL_16:
              if ( v17 >= 2 )
              {
                pvData = 0;
                FileNameW = PathFindFileNameW(pszPath);
                SHRegSetUSValueW(L"Software\\Microsoft\\WAB\\Import", FileNameW, 1u, &pvData, 2u, 2u);
              }
              else
              {
                *(_QWORD *)&v29 = 0xFFE000300000004LL;
                LODWORD(v35) = 268304387;
                DWORD2(v35) = *((_DWORD *)&qword_18009E2F8 + v17);
                *((_QWORD *)&v29 + 1) = &v35;
                FileToImport = (*(__int64 (__fastcall **)(struct CWABStorage *, _QWORD, _QWORD, __int128 *, unsigned int *, __int64 *))(*(_QWORD *)v15 + 24LL))(
                                 v15,
                                 0,
                                 0,
                                 &v29,
                                 &v25,
                                 &v27);
                if ( FileToImport >= 0 )
                {
                  while ( 1 )
                  {
                    if ( v3 >= v25 )
                    {
                      (*(void (__fastcall **)(struct CWABStorage *, _QWORD, __int64))(*(_QWORD *)v15 + 56LL))(
                        v15,
                        v25,
                        v27);
                      v3 = 0;
                      v27 = 0;
                      ++v17;
                      v25 = 0;
                      goto LABEL_16;
                    }
                    if ( (unsigned int)bTimeToAbort() )
                      break;
                    v18 = _ImportContact(
                            (struct _SBinary *)(v27 + 16LL * v3),
                            &Uuid,
                            (const struct NamedPropertyMapping *)hMem,
                            v15,
                            a1 != 0);
                    FileToImport = v18;
                    if ( v18 < 0 )
                      v7 = v18;
                    ++v3;
                  }
                  FileToImport = -2147221229;
                }
              }
            }
          }
        }
        else
        {
          FileToImport = 0;
        }
      }
      if ( v15 )
      {
        (*(void (__fastcall **)(struct CWABStorage *, _QWORD, __int64))(*(_QWORD *)v15 + 56LL))(v15, v25, v27);
        (*(void (__fastcall **)(struct CWABStorage *, __int64))(*(_QWORD *)v15 + 168LL))(v15, 1);
      }
    }
  }
  if ( (_DWORD)v33 )
    DeleteFileW(lpFileName[0]);
  if ( pv[1] )
    MAPIFreeBuffer(pv[1]);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v32 )
    LocalFree(v32);
  if ( a1 )
  {
    EnableWindow(a1, 1);
    CloseAbortDlg();
    if ( FileToImport == -2147221229 )
      goto LABEL_46;
    if ( FileToImport >= 0 )
      v20 = (v7 < 0) + 4422;
    else
      v20 = 4421;
    ShowMessageBox(a1, v20, 64);
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 7);
    if ( v22 )
      ShellPrivateTraceEvent(v21, 0x34u, v22, 2u);
  }
  if ( FileToImport >= 0 && v7 < 0 )
    FileToImport = 263040;
LABEL_46:
  LODWORD(v33) = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpFileName);
  return (unsigned int)FileToImport;
}

```

## disassembly

```asm
0x180075bf8  mov     [rsp-8+arg_18], rbx
0x180075bfd  push    rbp
0x180075bfe  push    rsi
0x180075bff  push    rdi
0x180075c00  push    r12
0x180075c02  push    r13
0x180075c04  push    r14
0x180075c06  push    r15
0x180075c08  lea     rbp, [rsp-200h]
0x180075c10  sub     rsp, 300h
0x180075c17  mov     rax, cs:__security_cookie
0x180075c1e  xor     rax, rsp
0x180075c21  mov     [rbp+230h+var_40], rax
0x180075c28  xor     r15d, r15d
0x180075c2b  mov     r13, r8
0x180075c2e  mov     rsi, rcx
0x180075c31  mov     [rsp+330h+var_2F0], r15d
0x180075c36  xorps   xmm0, xmm0
0x180075c39  mov     [rsp+330h+var_2E8], r15
0x180075c3e  xor     eax, eax
0x180075c40  lea     rcx, [rbp+230h+var_2A0]; this
0x180075c44  mov     r14, rdx
0x180075c47  mov     [rbp+230h+var_270], rax
0x180075c4b  xorps   xmm1, xmm1
0x180075c4e  lea     rdx, [rbp+230h+var_250]; unsigned __int16 *
0x180075c52  mov     r8d, 104h; unsigned int
0x180075c58  mov     r12d, r15d
0x180075c5b  movups  [rsp+330h+var_2D8], xmm0
0x180075c60  movups  [rbp+230h+var_280], xmm1
0x180075c64  movups  xmmword ptr [rsp+330h+pv], xmm0
0x180075c69  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180075c6e  xor     eax, eax
0x180075c70  mov     [rsp+330h+var_2E0], r15
0x180075c75  mov     [rbp+230h+var_2A8], rax
0x180075c79  mov     rax, cs:WPP_GLOBAL_Control
0x180075c80  movups  xmmword ptr [rbp+230h+Uuid.Data1], xmm0
0x180075c84  movups  xmmword ptr [rsp+330h+hMem], xmm0
0x180075c89  mov     r8, [rax+38h]; unsigned __int64
0x180075c8d  test    r8, r8
0x180075c90  jz      short loc_180075C9E
0x180075c92  mov     r9b, 1; unsigned __int8
0x180075c95  lea     edx, [r15+34h]; unsigned int
0x180075c99  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180075c9e  lea     rcx, [rbp+230h+Uuid]; Uuid
0x180075ca2  call    cs:__imp_UuidCreate
0x180075ca8  test    eax, eax
0x180075caa  jz      short loc_180075CB6
0x180075cac  mov     ebx, 8007000Eh
0x180075cb1  jmp     loc_180075ED7
0x180075cb6  lea     r8, [rbp+230h+var_2A0]
0x180075cba  mov     rdx, r13
0x180075cbd  call    _GetFileToImport
0x180075cc2  mov     ebx, eax
0x180075cc4  test    eax, eax
0x180075cc6  js      loc_180075ED7
0x180075ccc  cmp     dword ptr [rbp+230h+var_2A0], r15d
0x180075cd0  lea     rcx, Str
0x180075cd7  lea     r9, [rsp+330h+var_2E0]; struct CWABStorage **
0x180075cdc  mov     r8, rsi; HWND
0x180075cdf  cmovnz  rcx, [rbp+230h+lpFileName]; unsigned __int16 *
0x180075ce4  call    ?OpenStoreFromFile@CWABStorage@@SAJPEBGKPEAUHWND__@@PEAPEAV1@@Z; CWABStorage::OpenStoreFromFile(ushort const *,ulong,HWND__ *,CWABStorage * *)
0x180075ce9  mov     rdi, [rsp+330h+var_2E0]
0x180075cee  mov     ebx, eax
0x180075cf0  test    eax, eax
0x180075cf2  js      loc_180075E9E
0x180075cf8  mov     rax, [rdi]
0x180075cfb  mov     rcx, rdi
0x180075cfe  mov     rax, [rax+48h]
0x180075d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d07  mov     ebx, eax
0x180075d09  test    eax, eax
0x180075d0b  jnz     short loc_180075D15
0x180075d0d  mov     ebx, r15d
0x180075d10  jmp     loc_180075E9E
0x180075d15  test    rsi, rsi
0x180075d18  jz      short loc_180075D3C
0x180075d1a  xor     edx, edx; bEnable
0x180075d1c  mov     rcx, rsi; hWnd
0x180075d1f  call    cs:__imp_EnableWindow
0x180075d25  lea     r9d, [rbx+1]; int
0x180075d29  mov     edx, 1143h; int
0x180075d2e  mov     r8d, 177Ah; int
0x180075d34  mov     rcx, rsi; HWND
0x180075d37  call    ?CreateShowAbortDialog@@YAXPEAUHWND__@@HHHH@Z; CreateShowAbortDialog(HWND__ *,int,int,int,int)
0x180075d3c  lea     r8, [rsp+330h+hMem]; struct NamedPropertyMapping *
0x180075d41  mov     rdx, r14; struct IAddrBook *
0x180075d44  mov     rcx, rdi; struct CWABStorage *
0x180075d47  call    ?_MapOldNamedPropsToNewNamedProps@@YAJPEAVCWABStorage@@PEAUIAddrBook@@PEAUNamedPropertyMapping@@@Z; _MapOldNamedPropsToNewNamedProps(CWABStorage *,IAddrBook *,NamedPropertyMapping *)
0x180075d4c  mov     ebx, eax
0x180075d4e  test    eax, eax
0x180075d50  js      loc_180075E9E
0x180075d56  mov     rax, [r14]
0x180075d59  lea     r8, [rsp+330h+pv+8]
0x180075d5e  lea     rdx, [rsp+330h+pv]
0x180075d63  mov     rcx, r14
0x180075d66  mov     rax, [rax+0C8h]
0x180075d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d72  mov     ebx, eax
0x180075d74  test    eax, eax
0x180075d76  js      loc_180075E9E
0x180075d7c  mov     r14d, r15d
0x180075d7f  cmp     r14d, 2
0x180075d83  jnb     loc_180075E69
0x180075d89  mov     eax, r14d
0x180075d8c  lea     rcx, qword_18009E2F8
0x180075d93  mov     dword ptr [rsp+330h+var_2D8+4], 0FFE0003h
0x180075d9b  lea     r9, [rsp+330h+var_2D8]
0x180075da0  mov     dword ptr [rsp+330h+var_2D8], 4
0x180075da8  xor     r8d, r8d
0x180075dab  mov     dword ptr [rbp+230h+var_280], 0FFE0003h
0x180075db2  xor     edx, edx
0x180075db4  mov     eax, [rcx+rax*4]
0x180075db7  lea     rcx, [rsp+330h+var_2E8]
0x180075dbc  mov     dword ptr [rbp+230h+var_280+8], eax
0x180075dbf  lea     rax, [rbp+230h+var_280]
0x180075dc3  mov     qword ptr [rsp+330h+dwFlags], rcx
0x180075dc8  lea     rcx, [rsp+330h+var_2F0]
0x180075dcd  mov     qword ptr [rsp+330h+var_2D8+8], rax
0x180075dd2  mov     rax, [rdi]
0x180075dd5  mov     qword ptr [rsp+330h+cbData], rcx
0x180075dda  mov     rcx, rdi
0x180075ddd  mov     rax, [rax+18h]
0x180075de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075de6  mov     ebx, eax
0x180075de8  test    eax, eax
0x180075dea  js      loc_180075E9E
0x180075df0  mov     edx, [rsp+330h+var_2F0]
0x180075df4  cmp     r15d, edx
0x180075df7  jnb     short loc_180075E36
0x180075df9  call    ?bTimeToAbort@@YAHXZ; bTimeToAbort(void)
0x180075dfe  test    eax, eax
0x180075e00  jnz     short loc_180075E5F
0x180075e02  test    rsi, rsi
0x180075e05  mov     ecx, r15d
0x180075e08  mov     r9, rdi; struct CWABStorage *
0x180075e0b  lea     r8, [rsp+330h+hMem]; struct NamedPropertyMapping *
0x180075e10  setnz   al
0x180075e13  lea     rdx, [rbp+230h+Uuid]; struct _GUID *
0x180075e17  shl     rcx, 4
0x180075e1b  add     rcx, [rsp+330h+var_2E8]; struct _SBinary *
0x180075e20  mov     [rsp+330h+cbData], eax; int
0x180075e24  call    ?_ImportContact@@YAJPEAU_SBinary@@PEBU_GUID@@PEBUNamedPropertyMapping@@PEAVCWABStorage@@H@Z; _ImportContact(_SBinary *,_GUID const *,NamedPropertyMapping const *,CWABStorage *,int)
0x180075e29  test    eax, eax
0x180075e2b  mov     ebx, eax
0x180075e2d  cmovs   r12d, eax
0x180075e31  inc     r15d
0x180075e34  jmp     short loc_180075DF0
0x180075e36  mov     rax, [rdi]
0x180075e39  mov     rcx, rdi
0x180075e3c  mov     r8, [rsp+330h+var_2E8]
0x180075e41  mov     rax, [rax+38h]
0x180075e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e4a  xor     r15d, r15d
0x180075e4d  mov     [rsp+330h+var_2E8], r15
0x180075e52  inc     r14d
0x180075e55  mov     [rsp+330h+var_2F0], r15d
0x180075e5a  jmp     loc_180075D7F
0x180075e5f  mov     ebx, 80040113h
0x180075e64  xor     r15d, r15d
0x180075e67  jmp     short loc_180075E9E
0x180075e69  mov     rcx, r13; pszPath
0x180075e6c  mov     [rsp+330h+pvData], r15w
0x180075e72  call    cs:__imp_PathFindFileNameW
0x180075e78  mov     ecx, 2
0x180075e7d  lea     r9, [rsp+330h+pvData]; pvData
0x180075e82  mov     [rsp+330h+dwFlags], ecx; dwFlags
0x180075e86  mov     rdx, rax; pwzValue
0x180075e89  mov     [rsp+330h+cbData], ecx; cbData
0x180075e8d  lea     r8d, [rcx-1]; dwType
0x180075e91  lea     rcx, aSoftwareMicros_15; "Software\\Microsoft\\WAB\\Import"
0x180075e98  call    cs:__imp_SHRegSetUSValueW
0x180075e9e  test    rdi, rdi
0x180075ea1  jz      short loc_180075ED7
0x180075ea3  mov     rax, [rdi]
0x180075ea6  mov     rcx, rdi
0x180075ea9  mov     r8, [rsp+330h+var_2E8]
0x180075eae  mov     edx, [rsp+330h+var_2F0]
0x180075eb2  mov     rax, [rax+38h]
0x180075eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ebb  test    rdi, rdi
0x180075ebe  jz      short loc_180075ED7
0x180075ec0  mov     rax, [rdi]
0x180075ec3  mov     edx, 1
0x180075ec8  mov     rcx, rdi
0x180075ecb  mov     rax, [rax+0A8h]
0x180075ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ed7  cmp     dword ptr [rbp+230h+var_2A0], r15d
0x180075edb  jz      short loc_180075EE7
0x180075edd  mov     rcx, [rbp+230h+lpFileName]; lpFileName
0x180075ee1  call    cs:__imp_DeleteFileW
0x180075ee7  mov     rcx, [rsp+330h+pv+8]; pv
0x180075eec  test    rcx, rcx
0x180075eef  jz      short loc_180075EF6
0x180075ef1  call    MAPIFreeBuffer
0x180075ef6  mov     rcx, [rbp+230h+hMem+8]; hMem
0x180075efa  test    rcx, rcx
0x180075efd  jz      short loc_180075F05
0x180075eff  call    cs:__imp_LocalFree
0x180075f05  mov     rcx, [rbp+230h+var_2A8]; hMem
0x180075f09  test    rcx, rcx
0x180075f0c  jz      short loc_180075F14
0x180075f0e  call    cs:__imp_LocalFree
0x180075f14  test    rsi, rsi
0x180075f17  jz      short loc_180075F79
0x180075f19  mov     edx, 1; bEnable
0x180075f1e  mov     rcx, rsi; hWnd
0x180075f21  call    cs:__imp_EnableWindow
0x180075f27  call    ?CloseAbortDlg@@YAXXZ; CloseAbortDlg(void)
0x180075f2c  cmp     ebx, 80040113h
0x180075f32  jz      short loc_180075F88
0x180075f34  test    ebx, ebx
0x180075f36  jns     short loc_180075F3F
0x180075f38  mov     edx, 1145h
0x180075f3d  jmp     short loc_180075F4E
0x180075f3f  test    r12d, r12d
0x180075f42  mov     edx, r15d
0x180075f45  sets    dl
0x180075f48  add     edx, 1146h; int
0x180075f4e  mov     r8d, 40h ; '@'; int
0x180075f54  mov     rcx, rsi; hWnd
0x180075f57  call    ?ShowMessageBox@@YAHPEAUHWND__@@HH@Z; ShowMessageBox(HWND__ *,int,int)
0x180075f5c  mov     rax, cs:WPP_GLOBAL_Control
0x180075f63  mov     r8, [rax+38h]; unsigned __int64
0x180075f67  test    r8, r8
0x180075f6a  jz      short loc_180075F79
0x180075f6c  mov     r9b, 2; unsigned __int8
0x180075f6f  mov     edx, 34h ; '4'; unsigned int
0x180075f74  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180075f79  test    ebx, ebx
0x180075f7b  js      short loc_180075F88
0x180075f7d  test    r12d, r12d
0x180075f80  mov     eax, 40380h
0x180075f85  cmovs   ebx, eax
0x180075f88  lea     rcx, [rbp+230h+lpFileName]; this
0x180075f8c  mov     dword ptr [rbp+230h+var_2A0], r15d
0x180075f90  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x180075f95  mov     eax, ebx
0x180075f97  mov     rcx, [rbp+230h+var_40]
0x180075f9e  xor     rcx, rsp; StackCookie
0x180075fa1  call    __security_check_cookie
0x180075fa6  mov     rbx, [rsp+330h+arg_18]
0x180075fae  add     rsp, 300h
0x180075fb5  pop     r15
0x180075fb7  pop     r14
0x180075fb9  pop     r13
0x180075fbb  pop     r12
0x180075fbd  pop     rdi
0x180075fbe  pop     rsi
0x180075fbf  pop     rbp
0x180075fc0  retn
```
