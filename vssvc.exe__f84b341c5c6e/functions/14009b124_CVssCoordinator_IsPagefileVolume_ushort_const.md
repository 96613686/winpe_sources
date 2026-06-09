# CVssCoordinator::IsPagefileVolume(ushort const *)

- ea: `0x14009b124`
- end: `0x14009b3ca`
- name: `?IsPagefileVolume@CVssCoordinator@@AEAA_NPEBG@Z`
- size: `678`
- prototype: `bool __fastcall(CVssCoordinator *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x14006f180`
- `0x14008aa50`

## callees

- `0x140008908`
- `0x140009a40`
- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140091560`
- `0x1400921dc`
- `0x14009992c`
- `0x14009b124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009b2f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14009b2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009b1d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009b1d6`
- `ntdll!NtQuerySystemInformation` at `0x14009b1cc`
- `ntdll!NtQuerySystemInformation` at `0x14009b1cc`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14009b2c6`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14009b2c6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14009b2e1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14009b2e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CVssCoordinator::IsPagefileVolume(CVssCoordinator *this, const unsigned __int16 *a2)
{
  DWORD LastError; // ebx
  unsigned int *v4; // rdi
  const WCHAR *v5; // rcx
  __int64 v6; // rax
  unsigned int *v7; // rbx
  bool v8; // bl
  void **v10; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpszFileName; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v12; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v13; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+4Ch] [rbp-B4h]
  int v17; // [rsp+50h] [rbp-B0h]
  _BYTE v18[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+D0h] [rbp-30h]
  LPVOID v20[14]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR szVolumeName[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE SystemInformation[560]; // [rsp+570h] [rbp+470h] BYREF

  v12 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v13 = L"CVssCoordinator::IsPagefileVolume";
  v14 = L"CORCOORC";
  v15 = 3002;
  v16 = 1;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v20, (__int64)&v12, 0);
  if ( NtQuerySystemInformation(SystemPageFileInformation, SystemInformation, 0x228u, 0) )
  {
    LastError = GetLastError();
    v12 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v13 = L"CVssCoordinator::IsPagefileVolume";
    v14 = L"CORCOORC";
    v15 = 3012;
    v16 = 1;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::Trace(v20, &v12, L"NtQuerySystemInformation failed with status %d", LastError);
  }
  else
  {
    v4 = (unsigned int *)SystemInformation;
    while ( v4[1] )
    {
      lpszFileName = 0;
      v10 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
      CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom((__int64)&v10, L"\\\\?\\GLOBALROOT");
      CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::Append(&v10, *((_QWORD *)v4 + 3));
      v5 = lpszFileName;
      v6 = -1;
      do
        ++v6;
      while ( lpszFileName[v6] );
      if ( lpszFileName[v6 - 1] != 92 )
      {
        CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::Append(&v10, L"\\");
        v5 = lpszFileName;
      }
      if ( GetVolumePathNameW(v5, szVolumePathName, 0x104u)
        && GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u)
        && !(unsigned int)_o__wcsicmp(szVolumeName, a2) )
      {
        v8 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v20, 1);
        CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v10);
        goto LABEL_17;
      }
      v7 = v4;
      v4 = (unsigned int *)((char *)v4 + *v4);
      CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v10);
      if ( v4 == v7 )
        goto LABEL_16;
    }
    v12 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v13 = L"CVssCoordinator::IsPagefileVolume";
    v14 = L"CORCOORC";
    v15 = 3024;
    v16 = 1;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::Trace(v20, &v12, L"NtQuerySystemInformation reports no pagefile");
  }
LABEL_16:
  v8 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v20, 0);
LABEL_17:
  CVssFunctionTracer::~CVssFunctionTracer(v20);
  return v8;
}

```

## disassembly

```asm
0x14009b124  push    rbp
0x14009b126  push    rbx
0x14009b127  push    rsi
0x14009b128  push    rdi
0x14009b129  push    r13
0x14009b12b  push    r14
0x14009b12d  lea     rbp, [rsp-6B8h]
0x14009b135  sub     rsp, 7B8h
0x14009b13c  mov     rax, cs:__security_cookie
0x14009b143  xor     rax, rsp
0x14009b146  mov     [rbp+6E0h+var_40], rax
0x14009b14d  mov     rsi, rdx
0x14009b150  lea     r13, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14009b157  mov     [rsp+7E0h+var_7B0], r13
0x14009b15c  lea     rbx, aCvsscoordinato_4; "CVssCoordinator::IsPagefileVolume"
0x14009b163  mov     [rsp+7E0h+var_7A8], rbx
0x14009b168  lea     rbx, aCorcoorc; "CORCOORC"
0x14009b16f  mov     [rsp+7E0h+var_7A0], rbx
0x14009b174  mov     [rsp+7E0h+var_798], 0BBAh
0x14009b17c  mov     [rsp+7E0h+var_794], 1
0x14009b184  mov     [rsp+7E0h+var_790], 0FFh
0x14009b18c  xor     r14d, r14d
0x14009b18f  mov     [rbp+6E0h+var_710], 1000000h
0x14009b196  xor     edx, edx; Val
0x14009b198  lea     r8d, [r14+78h]; Size
0x14009b19c  lea     rcx, [rsp+7E0h+var_788]; void *
0x14009b1a1  call    memset_0
0x14009b1a6  xor     r8d, r8d
0x14009b1a9  lea     rdx, [rsp+7E0h+var_7B0]
0x14009b1ae  lea     rcx, [rbp+6E0h+var_700]
0x14009b1b2  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14009b1b7  nop
0x14009b1b8  xor     r9d, r9d; ReturnLength
0x14009b1bb  mov     r8d, 228h; SystemInformationLength
0x14009b1c1  lea     rdx, [rbp+6E0h+SystemInformation]; SystemInformation
0x14009b1c8  lea     ecx, [r14+12h]; SystemInformationClass
0x14009b1cc  call    cs:__imp_NtQuerySystemInformation
0x14009b1d2  test    eax, eax
0x14009b1d4  jz      short loc_14009B247
0x14009b1d6  call    cs:__imp_GetLastError
0x14009b1dc  mov     ebx, eax
0x14009b1de  mov     [rsp+7E0h+var_7B0], r13
0x14009b1e3  lea     rax, aCvsscoordinato_4; "CVssCoordinator::IsPagefileVolume"
0x14009b1ea  mov     [rsp+7E0h+var_7A8], rax
0x14009b1ef  lea     rax, aCorcoorc; "CORCOORC"
0x14009b1f6  mov     [rsp+7E0h+var_7A0], rax
0x14009b1fb  mov     [rsp+7E0h+var_798], 0BC4h
0x14009b203  mov     [rsp+7E0h+var_794], 1
0x14009b20b  mov     [rsp+7E0h+var_790], 0FFh
0x14009b213  mov     [rbp+6E0h+var_710], 1000000h
0x14009b21a  xor     edx, edx; Val
0x14009b21c  lea     r8d, [r14+78h]; Size
0x14009b220  lea     rcx, [rsp+7E0h+var_788]; void *
0x14009b225  call    memset_0
0x14009b22a  mov     r9d, ebx
0x14009b22d  lea     r8, aNtquerysystemi_1; "NtQuerySystemInformation failed with st"...
0x14009b234  lea     rdx, [rsp+7E0h+var_7B0]
0x14009b239  lea     rcx, [rbp+6E0h+var_700]
0x14009b23d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14009b242  jmp     loc_14009B393
0x14009b247  lea     rdi, [rbp+6E0h+SystemInformation]
0x14009b24e  cmp     [rdi+4], r14d
0x14009b252  jz      loc_14009B332
0x14009b258  mov     [rsp+7E0h+lpszFileName], r14
0x14009b25d  lea     rax, ??_7?$CVssAutoCOMPtr@PEAU_VDS_LUN_INFORMATION@@@@6B@; const CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable'
0x14009b264  mov     [rsp+7E0h+var_7C0], rax
0x14009b269  lea     rdx, aGlobalroot_1; "\\\\?\\GLOBALROOT"
0x14009b270  lea     rcx, [rsp+7E0h+var_7C0]
0x14009b275  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x14009b27a  mov     rdx, [rdi+18h]
0x14009b27e  lea     rcx, [rsp+7E0h+var_7C0]
0x14009b283  call    ?Append@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::Append(ushort const *)
0x14009b288  mov     rcx, [rsp+7E0h+lpszFileName]
0x14009b28d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14009b291  inc     rax
0x14009b294  cmp     [rcx+rax*2], r14w
0x14009b299  jnz     short loc_14009B291
0x14009b29b  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x14009b2a1  jz      short loc_14009B2B9
0x14009b2a3  lea     rdx, pszSrc; "\\"
0x14009b2aa  lea     rcx, [rsp+7E0h+var_7C0]
0x14009b2af  call    ?Append@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::Append(ushort const *)
0x14009b2b4  mov     rcx, [rsp+7E0h+lpszFileName]; lpszFileName
0x14009b2b9  mov     r8d, 104h; cchBufferLength
0x14009b2bf  lea     rdx, [rbp+6E0h+szVolumePathName]; lpszVolumePathName
0x14009b2c6  call    cs:__imp_GetVolumePathNameW
0x14009b2cc  test    eax, eax
0x14009b2ce  jz      short loc_14009B2FC
0x14009b2d0  mov     r8d, 104h; cchBufferLength
0x14009b2d6  lea     rdx, [rbp+6E0h+szVolumeName]; lpszVolumeName
0x14009b2da  lea     rcx, [rbp+6E0h+szVolumePathName]; lpszVolumeMountPoint
0x14009b2e1  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14009b2e7  test    eax, eax
0x14009b2e9  jz      short loc_14009B2FC
0x14009b2eb  mov     rdx, rsi
0x14009b2ee  lea     rcx, [rbp+6E0h+szVolumeName]
0x14009b2f2  call    cs:__imp__o__wcsicmp
0x14009b2f8  test    eax, eax
0x14009b2fa  jz      short loc_14009B319
0x14009b2fc  mov     rbx, rdi
0x14009b2ff  mov     eax, [rdi]
0x14009b301  add     rdi, rax
0x14009b304  lea     rcx, [rsp+7E0h+var_7C0]
0x14009b309  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x14009b30e  cmp     rdi, rbx
0x14009b311  jnz     loc_14009B24E
0x14009b317  jmp     short loc_14009B393
0x14009b319  mov     dl, 1; bool
0x14009b31b  lea     rcx, [rbp+6E0h+var_700]; this
0x14009b31f  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x14009b324  mov     bl, al
0x14009b326  lea     rcx, [rsp+7E0h+var_7C0]
0x14009b32b  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x14009b330  jmp     short loc_14009B3A0
0x14009b332  mov     [rsp+7E0h+var_7B0], r13
0x14009b337  lea     rax, aCvsscoordinato_4; "CVssCoordinator::IsPagefileVolume"
0x14009b33e  mov     [rsp+7E0h+var_7A8], rax
0x14009b343  lea     rax, aCorcoorc; "CORCOORC"
0x14009b34a  mov     [rsp+7E0h+var_7A0], rax
0x14009b34f  mov     [rsp+7E0h+var_798], 0BD0h
0x14009b357  mov     [rsp+7E0h+var_794], 1
0x14009b35f  mov     [rsp+7E0h+var_790], 0FFh
0x14009b367  mov     [rbp+6E0h+var_710], 1000000h
0x14009b36e  xor     edx, edx; Val
0x14009b370  lea     r8d, [rdx+78h]; Size
0x14009b374  lea     rcx, [rsp+7E0h+var_788]; void *
0x14009b379  call    memset_0
0x14009b37e  lea     r8, aNtquerysystemi; "NtQuerySystemInformation reports no pag"...
0x14009b385  lea     rdx, [rsp+7E0h+var_7B0]
0x14009b38a  lea     rcx, [rbp+6E0h+var_700]
0x14009b38e  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14009b393  xor     edx, edx; bool
0x14009b395  lea     rcx, [rbp+6E0h+var_700]; this
0x14009b399  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x14009b39e  mov     bl, al
0x14009b3a0  lea     rcx, [rbp+6E0h+var_700]; this
0x14009b3a4  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14009b3a9  mov     al, bl
0x14009b3ab  mov     rcx, [rbp+6E0h+var_40]
0x14009b3b2  xor     rcx, rsp; StackCookie
0x14009b3b5  call    __security_check_cookie
0x14009b3ba  add     rsp, 7B8h
0x14009b3c1  pop     r14
0x14009b3c3  pop     r13
0x14009b3c5  pop     rdi
0x14009b3c6  pop     rsi
0x14009b3c7  pop     rbx
0x14009b3c8  pop     rbp
0x14009b3c9  retn
```
