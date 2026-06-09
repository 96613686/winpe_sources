# CVssProviderRegInfo::GetDiffAreaForVolume(ushort *,ushort * &,__int64 &,long &)

- ea: `0x18002e7ec`
- end: `0x18002edd1`
- name: `?GetDiffAreaForVolume@CVssProviderRegInfo@@AEAA_NPEAGAEAPEAGAEA_JAEAJ@Z`
- size: `1509`
- prototype: `bool __fastcall(CVssProviderRegInfo *this, unsigned __int16 *, unsigned __int16 **, __int64 *, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002edd8`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180002138`
- `0x180003718`
- `0x1800049e0`
- `0x1800110a8`
- `0x18001c208`
- `0x18002a280`
- `0x18002e7ec`
- `0x180033a8c`
- `0x180033c78`
- `0x180035f44`
- `0x1800367b8`
- `0x180037080`
- `0x180037e24`
- `0x180037f24`
- `0x1800386cc`
- `0x18003874c`
- `0x180039f5c`
- `0x18003a05c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ec55`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ec55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebbd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002ebaf`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002ebaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ea0f`

## string_xrefs

- `0x18002eb16`: `Registry diff volume name for %s is %s`
- `0x18002ec18`: `GetVolumeNameForVolumeMountPointW( '%s'): 0x%08lx`
- `0x18002e942`: `SYSTEM\CurrentControlSet\Services\VSS\Volumes\Associations`

## pseudocode

```c
bool __fastcall CVssProviderRegInfo::GetDiffAreaForVolume(
        CVssProviderRegInfo *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        __int64 *a4,
        int *a5)
{
  unsigned int v9; // edi
  unsigned __int16 *v10; // rbx
  unsigned __int16 *CurrentKeyName; // rax
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rdx
  bool v14; // r9
  DWORD LastError; // ebx
  int AssociationFlags; // ebx
  unsigned __int16 *v17; // rbx
  __int64 v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h]
  int pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  void **v21; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v22; // [rsp+90h] [rbp-70h]
  const wchar_t *v23; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v24; // [rsp+A0h] [rbp-60h]
  const wchar_t *v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+B8h] [rbp-48h]
  _BYTE v29[120]; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+138h] [rbp+38h]
  __int64 v31; // [rsp+140h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+148h] [rbp+48h]
  void **v33; // [rsp+150h] [rbp+50h]
  __int64 v34; // [rsp+158h] [rbp+58h]
  _QWORD v35[4]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v36[8]; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v37; // [rsp+188h] [rbp+88h]
  unsigned int v38; // [rsp+18Ch] [rbp+8Ch]
  _QWORD v39[3]; // [rsp+198h] [rbp+98h] BYREF
  LPVOID v40; // [rsp+1B0h] [rbp+B0h] BYREF
  int v41; // [rsp+1B8h] [rbp+B8h]
  struct _GUID v42; // [rsp+220h] [rbp+120h] BYREF
  WCHAR szVolumeName[264]; // [rsp+230h] [rbp+130h] BYREF

  v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
  v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
  v25 = L"SPRREGMC";
  v26 = 240;
  v27 = 2;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v40, (__int64)&v23, 0);
  v42 = 0;
  GetVolumeGuid(a2, &v42);
  v34 = 0;
  v33 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  hKey = 0;
  v31 = 983103;
  if ( !CVssRegistryKey::Open(
          (CVssRegistryKey *)&v31,
          HKEY_LOCAL_MACHINE,
          L"%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Volumes\\Associations",
          v42.Data1,
          v42.Data2,
          v42.Data3,
          v42.Data4[0],
          v42.Data4[1],
          v42.Data4[2],
          v42.Data4[3],
          v42.Data4[4],
          v42.Data4[5],
          v42.Data4[6],
          v42.Data4[7]) )
    goto LABEL_2;
  v39[1] = 0;
  v39[0] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  CVssRegistryKeyIterator::Detach((CVssRegistryKeyIterator *)v36);
  CVssRegistryKeyIterator::Attach((CVssRegistryKeyIterator *)v36, (struct CVssRegistryKey *)&v31);
  v9 = v38;
  if ( v38 >= v37 )
  {
LABEL_4:
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v39);
LABEL_2:
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)&v31);
    CVssFunctionTracer::~CVssFunctionTracer(&v40);
    return 0;
  }
  v22 = 0;
  v21 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close((__int64)&v21);
  v10 = (unsigned __int16 *)CoTaskMemAlloc(0x64u);
  v22 = v10;
  if ( !v10 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  CurrentKeyName = CVssRegistryKeyIterator::GetCurrentKeyName((CVssRegistryKeyIterator *)v36);
  v41 = StringCchPrintfW(v10, 0x32u, L"%s%s%s", L"\\\\?\\Volume", CurrentKeyName, L"\\");
  if ( v41 < 0 )
  {
    v17 = CVssRegistryKeyIterator::GetCurrentKeyName((CVssRegistryKeyIterator *)v36);
    v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
    v25 = L"SPRREGMC";
    v26 = 269;
    v27 = 2;
    v28 = 255;
    v30 = 0x1000000;
    memset_0(v29, 0, sizeof(v29));
    CVssFunctionTracer::TranslateGenericError(
      &v40,
      &v23,
      (unsigned int)v41,
      L"StringCchPrintfW(,%s,%s,%s)",
      L"\\\\?\\Volume",
      v17,
      L"\\");
  }
  v35[3] = 0;
  v35[2] = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v35[1] = 0;
  v35[0] = 983103;
  v12 = CVssRegistryKeyIterator::GetCurrentKeyName((CVssRegistryKeyIterator *)v36);
  CVssRegistryKey::Open((CVssRegistryKey *)v35, hKey, v12);
  CVssRegistryKey::GetValue((CVssRegistryKey *)v35, v13, a4, v14);
  v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
  v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
  v25 = L"SPRREGMC";
  v26 = 280;
  v27 = 11;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CVssFunctionTracer::Trace(&v40, &v23, L"Registry diff volume name for %s is %s", a2, v10);
  v22 = 0;
  *a3 = v10;
  v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
  v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
  v25 = L"SPRREGMC";
  v26 = 285;
  v27 = 11;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CVssFunctionTracer::Trace(&v40, &v23, L"Internal diff volume name for %s is %s", a2, v10);
  if ( !GetVolumeNameForVolumeMountPointW(*a3, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
    v25 = L"SPRREGMC";
    v26 = 295;
    v27 = 11;
    v28 = 255;
    v30 = 0x1000000;
    memset_0(v29, 0, sizeof(v29));
    LODWORD(v18) = LastError;
    CVssFunctionTracer::LogGenericWarning(&v40, &v23, L"GetVolumeNameForVolumeMountPointW( '%s'): 0x%08lx", *a3, v18);
LABEL_10:
    *a5 |= 4u;
    CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v35);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v21);
    goto LABEL_4;
  }
  if ( (unsigned int)_o__wcsicmp(*a3, szVolumeName) )
    goto LABEL_10;
  v38 = v9 + 1;
  AssociationFlags = CVssDiffMgmt::GetAssociationFlags(a2, *a3);
  *a5 = AssociationFlags;
  v23 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
  v24 = L"CVssProviderRegInfo::GetDiffAreaForVolume";
  v25 = L"SPRREGMC";
  v26 = 317;
  v27 = 2;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  LODWORD(v19) = AssociationFlags;
  CVssFunctionTracer::Trace(
    &v40,
    &v23,
    L"An association is present: %s - %s (%I64d) with flags 0x%08lx",
    a2,
    *a3,
    *a4,
    v19);
  LOBYTE(AssociationFlags) = (*a5 & 4) == 0;
  CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v35);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v21);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(v39);
  CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)&v31);
  CVssFunctionTracer::~CVssFunctionTracer(&v40);
  return AssociationFlags;
}

```

## disassembly

```asm
0x18002e7ec  mov     [rsp-8+arg_0], rbx
0x18002e7f1  push    rbp
0x18002e7f2  push    rsi
0x18002e7f3  push    rdi
0x18002e7f4  push    r12
0x18002e7f6  push    r13
0x18002e7f8  push    r14
0x18002e7fa  push    r15
0x18002e7fc  lea     rbp, [rsp-350h]
0x18002e804  sub     rsp, 450h
0x18002e80b  mov     rax, cs:__security_cookie
0x18002e812  xor     rax, rsp
0x18002e815  mov     [rbp+380h+var_40], rax
0x18002e81c  mov     r13, r9
0x18002e81f  mov     r15, r8
0x18002e822  mov     r12, rdx
0x18002e825  mov     r14, [rbp+380h+arg_20]
0x18002e82c  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002e833  mov     [rbp+380h+var_3E8], rax
0x18002e837  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002e83e  mov     [rbp+380h+var_3E0], rax
0x18002e842  lea     rax, aSprregmc; "SPRREGMC"
0x18002e849  mov     [rbp+380h+var_3D8], rax
0x18002e84d  mov     [rbp+380h+var_3D0], 0F0h
0x18002e854  mov     [rbp+380h+var_3CC], 2
0x18002e85b  mov     [rbp+380h+var_3C8], 0FFh
0x18002e862  xor     ebx, ebx
0x18002e864  mov     [rbp+380h+var_348], 1000000h
0x18002e86b  xor     edx, edx; Val
0x18002e86d  lea     r8d, [rbx+78h]; Size
0x18002e871  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002e875  call    memset_0
0x18002e87a  xor     r8d, r8d
0x18002e87d  lea     rdx, [rbp+380h+var_3E8]
0x18002e881  lea     rcx, [rbp+380h+var_2D0]
0x18002e888  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18002e88d  nop
0x18002e88e  xorps   xmm0, xmm0
0x18002e891  movups  xmmword ptr [rbp+380h+var_260.Data1], xmm0
0x18002e898  lea     rdx, [rbp+380h+var_260]; struct _GUID *
0x18002e89f  mov     rcx, r12; unsigned __int16 *
0x18002e8a2  call    ?GetVolumeGuid@@YA_NPEBGAEAU_GUID@@@Z; GetVolumeGuid(ushort const *,_GUID &)
0x18002e8a7  mov     [rbp+380h+var_328], rbx
0x18002e8ab  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18002e8b2  mov     [rbp+380h+var_330], rax
0x18002e8b6  mov     [rbp+380h+hKey], rbx
0x18002e8ba  mov     [rbp+380h+var_340], 0F003Fh
0x18002e8c2  movzx   eax, [rbp+380h+var_260.Data4+7]
0x18002e8c9  movzx   ecx, [rbp+380h+var_260.Data4+6]
0x18002e8d0  movzx   edx, [rbp+380h+var_260.Data4+5]
0x18002e8d7  movzx   r8d, [rbp+380h+var_260.Data4+4]
0x18002e8df  movzx   r9d, [rbp+380h+var_260.Data4+3]
0x18002e8e7  movzx   r10d, [rbp+380h+var_260.Data4+2]
0x18002e8ef  movzx   r11d, [rbp+380h+var_260.Data4+1]
0x18002e8f7  movzx   ebx, [rbp+380h+var_260.Data4]
0x18002e8fe  movzx   edi, [rbp+380h+var_260.Data3]
0x18002e905  movzx   esi, [rbp+380h+var_260.Data2]
0x18002e90c  mov     [rsp+480h+var_410], eax
0x18002e910  mov     [rsp+480h+var_418], ecx
0x18002e914  mov     [rsp+480h+var_420], edx
0x18002e918  mov     [rsp+480h+var_428], r8d
0x18002e91d  mov     [rsp+480h+var_430], r9d
0x18002e922  mov     [rsp+480h+var_438], r10d
0x18002e927  mov     [rsp+480h+var_440], r11d
0x18002e92c  mov     [rsp+480h+var_448], ebx
0x18002e930  mov     dword ptr [rsp+480h+var_450], edi
0x18002e934  mov     dword ptr [rsp+480h+var_458], esi
0x18002e938  mov     eax, [rbp+380h+var_260.Data1]
0x18002e93e  mov     dword ptr [rsp+480h+var_460], eax
0x18002e942  lea     r9, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18002e949  lea     r8, aS8x4x4x2x2x2x2_0; "%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x18002e950  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002e957  lea     rcx, [rbp+380h+var_340]; this
0x18002e95b  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18002e960  xor     esi, esi
0x18002e962  test    al, al
0x18002e964  jnz     short loc_18002E9A8
0x18002e966  lea     rcx, [rbp+380h+var_340]; this
0x18002e96a  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18002e96f  nop
0x18002e970  lea     rcx, [rbp+380h+var_2D0]; this
0x18002e977  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18002e97c  xor     al, al
0x18002e97e  mov     rcx, [rbp+380h+var_40]
0x18002e985  xor     rcx, rsp; StackCookie
0x18002e988  call    __security_check_cookie
0x18002e98d  mov     rbx, [rsp+480h+arg_0]
0x18002e995  add     rsp, 450h
0x18002e99c  pop     r15
0x18002e99e  pop     r14
0x18002e9a0  pop     r13
0x18002e9a2  pop     r12
0x18002e9a4  pop     rdi
0x18002e9a5  pop     rsi
0x18002e9a6  pop     rbp
0x18002e9a7  retn
0x18002e9a8  mov     [rbp+380h+var_2E0], rsi
0x18002e9af  lea     rbx, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18002e9b6  mov     [rbp+380h+var_2E8], rbx
0x18002e9bd  lea     rcx, [rbp+380h+var_300]; this
0x18002e9c4  call    ?Detach@CVssRegistryKeyIterator@@QEAAXXZ; CVssRegistryKeyIterator::Detach(void)
0x18002e9c9  nop
0x18002e9ca  lea     rdx, [rbp+380h+var_340]; struct CVssRegistryKey *
0x18002e9ce  lea     rcx, [rbp+380h+var_300]; this
0x18002e9d5  call    ?Attach@CVssRegistryKeyIterator@@QEAAXAEAVCVssRegistryKey@@@Z; CVssRegistryKeyIterator::Attach(CVssRegistryKey &)
0x18002e9da  mov     edi, [rbp+380h+var_2F4]
0x18002e9e0  cmp     edi, [rbp+380h+var_2F8]
0x18002e9e6  jb      short loc_18002E9F9
0x18002e9e8  lea     rcx, [rbp+380h+var_2E8]
0x18002e9ef  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x18002e9f4  jmp     loc_18002E966
0x18002e9f9  mov     [rbp+380h+var_3F0], rsi
0x18002e9fd  mov     [rbp+380h+var_3F8], rbx
0x18002ea01  lea     rcx, [rbp+380h+var_3F8]
0x18002ea05  call    ?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)
0x18002ea0a  mov     ecx, 64h ; 'd'; cb
0x18002ea0f  call    cs:__imp_CoTaskMemAlloc
0x18002ea15  mov     rbx, rax
0x18002ea18  mov     [rbp+380h+var_3F0], rax
0x18002ea1c  test    rax, rax
0x18002ea1f  jnz     short loc_18002EA39
0x18002ea21  mov     [rbp+380h+pExceptionObject], 8007000Eh
0x18002ea28  lea     rdx, _TI1J; pThrowInfo
0x18002ea2f  lea     rcx, [rbp+380h+pExceptionObject]; pExceptionObject
0x18002ea33  call    _CxxThrowException_0
0x18002ea39  lea     rcx, [rbp+380h+var_300]; this
0x18002ea40  call    ?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ; CVssRegistryKeyIterator::GetCurrentKeyName(void)
0x18002ea45  lea     rcx, asc_18005C7B0; "\\"
0x18002ea4c  mov     [rsp+480h+var_458], rcx
0x18002ea51  mov     [rsp+480h+var_460], rax
0x18002ea56  lea     r9, aVolume_0; "\\\\?\\Volume"
0x18002ea5d  lea     r8, aSSS; "%s%s%s"
0x18002ea64  mov     edx, 32h ; '2'; unsigned __int64
0x18002ea69  mov     rcx, rbx; unsigned __int16 *
0x18002ea6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ea71  mov     [rbp+380h+var_2C8], eax
0x18002ea77  test    eax, eax
0x18002ea79  js      loc_18002ED3A
0x18002ea7f  mov     [rbp+380h+var_308], rsi
0x18002ea83  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18002ea8a  mov     [rbp+380h+var_310], rax
0x18002ea8e  mov     [rbp+380h+var_318], rsi
0x18002ea92  mov     [rbp+380h+var_320], 0F003Fh
0x18002ea9a  lea     rcx, [rbp+380h+var_300]; this
0x18002eaa1  call    ?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ; CVssRegistryKeyIterator::GetCurrentKeyName(void)
0x18002eaa6  mov     r8, rax; unsigned __int16 *
0x18002eaa9  mov     rdx, [rbp+380h+hKey]; hKey
0x18002eaad  lea     rcx, [rbp+380h+var_320]; this
0x18002eab1  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18002eab6  mov     r8, r13; __int64 *
0x18002eab9  lea     rcx, [rbp+380h+var_320]; this
0x18002eabd  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEA_J_N@Z; CVssRegistryKey::GetValue(ushort const *,__int64 &,bool)
0x18002eac2  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002eac9  mov     [rbp+380h+var_3E8], rax
0x18002eacd  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002ead4  mov     [rbp+380h+var_3E0], rax
0x18002ead8  lea     rax, aSprregmc; "SPRREGMC"
0x18002eadf  mov     [rbp+380h+var_3D8], rax
0x18002eae3  mov     [rbp+380h+var_3D0], 118h
0x18002eaea  mov     [rbp+380h+var_3CC], 0Bh
0x18002eaf1  mov     [rbp+380h+var_3C8], 0FFh
0x18002eaf8  mov     [rbp+380h+var_348], 1000000h
0x18002eaff  xor     edx, edx; Val
0x18002eb01  lea     r8d, [rdx+78h]; Size
0x18002eb05  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002eb09  call    memset_0
0x18002eb0e  mov     [rsp+480h+var_460], rbx
0x18002eb13  mov     r9, r12
0x18002eb16  lea     r8, aRegistryDiffVo; "Registry diff volume name for %s is %s"
0x18002eb1d  lea     rdx, [rbp+380h+var_3E8]
0x18002eb21  lea     rcx, [rbp+380h+var_2D0]
0x18002eb28  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002eb2d  mov     [rbp+380h+var_3F0], rsi
0x18002eb31  mov     [r15], rbx
0x18002eb34  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002eb3b  mov     [rbp+380h+var_3E8], rax
0x18002eb3f  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002eb46  mov     [rbp+380h+var_3E0], rax
0x18002eb4a  lea     rax, aSprregmc; "SPRREGMC"
0x18002eb51  mov     [rbp+380h+var_3D8], rax
0x18002eb55  mov     [rbp+380h+var_3D0], 11Dh
0x18002eb5c  mov     [rbp+380h+var_3CC], 0Bh
0x18002eb63  mov     [rbp+380h+var_3C8], 0FFh
0x18002eb6a  mov     [rbp+380h+var_348], 1000000h
0x18002eb71  xor     edx, edx; Val
0x18002eb73  lea     r8d, [rdx+78h]; Size
0x18002eb77  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002eb7b  call    memset_0
0x18002eb80  mov     [rsp+480h+var_460], rbx
0x18002eb85  mov     r9, r12
0x18002eb88  lea     r8, aInternalDiffVo; "Internal diff volume name for %s is %s"
0x18002eb8f  lea     rdx, [rbp+380h+var_3E8]
0x18002eb93  lea     rcx, [rbp+380h+var_2D0]
0x18002eb9a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002eb9f  mov     r8d, 104h; cchBufferLength
0x18002eba5  lea     rdx, [rbp+380h+szVolumeName]; lpszVolumeName
0x18002ebac  mov     rcx, [r15]; lpszVolumeMountPoint
0x18002ebaf  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002ebb5  test    eax, eax
0x18002ebb7  jnz     loc_18002EC4B
0x18002ebbd  call    cs:__imp_GetLastError
0x18002ebc3  mov     ebx, eax
0x18002ebc5  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002ebcc  mov     [rbp+380h+var_3E8], rax
0x18002ebd0  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002ebd7  mov     [rbp+380h+var_3E0], rax
0x18002ebdb  lea     rax, aSprregmc; "SPRREGMC"
0x18002ebe2  mov     [rbp+380h+var_3D8], rax
0x18002ebe6  mov     [rbp+380h+var_3D0], 127h
0x18002ebed  mov     [rbp+380h+var_3CC], 0Bh
0x18002ebf4  mov     [rbp+380h+var_3C8], 0FFh
0x18002ebfb  mov     [rbp+380h+var_348], 1000000h
0x18002ec02  xor     edx, edx; Val
0x18002ec04  lea     r8d, [rdx+78h]; Size
0x18002ec08  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002ec0c  call    memset_0
0x18002ec11  mov     dword ptr [rsp+480h+var_460], ebx
0x18002ec15  mov     r9, [r15]
0x18002ec18  lea     r8, aGetvolumenamef; "GetVolumeNameForVolumeMountPointW( '%s'"...
0x18002ec1f  lea     rdx, [rbp+380h+var_3E8]
0x18002ec23  lea     rcx, [rbp+380h+var_2D0]
0x18002ec2a  call    ?LogGenericWarning@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::LogGenericWarning(CVssDebugInfo,ushort const *,...)
0x18002ec2f  or      dword ptr [r14], 4
0x18002ec33  lea     rcx, [rbp+380h+var_320]; this
0x18002ec37  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18002ec3c  nop
0x18002ec3d  lea     rcx, [rbp+380h+var_3F8]
0x18002ec41  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x18002ec46  jmp     loc_18002E9E8
0x18002ec4b  lea     rdx, [rbp+380h+szVolumeName]
0x18002ec52  mov     rcx, [r15]
0x18002ec55  call    cs:__imp__o__wcsicmp
0x18002ec5b  test    eax, eax
0x18002ec5d  jnz     short loc_18002EC2F
0x18002ec5f  inc     edi
0x18002ec61  mov     [rbp+380h+var_2F4], edi
0x18002ec67  mov     rdx, [r15]; unsigned __int16 *
0x18002ec6a  mov     rcx, r12; unsigned __int16 *
0x18002ec6d  call    ?GetAssociationFlags@CVssDiffMgmt@@SAJPEAG0@Z; CVssDiffMgmt::GetAssociationFlags(ushort *,ushort *)
0x18002ec72  mov     ebx, eax
0x18002ec74  mov     [r14], eax
0x18002ec77  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002ec7e  mov     [rbp+380h+var_3E8], rax
0x18002ec82  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002ec89  mov     [rbp+380h+var_3E0], rax
0x18002ec8d  lea     rax, aSprregmc; "SPRREGMC"
0x18002ec94  mov     [rbp+380h+var_3D8], rax
0x18002ec98  mov     [rbp+380h+var_3D0], 13Dh
0x18002ec9f  mov     [rbp+380h+var_3CC], 2
0x18002eca6  mov     [rbp+380h+var_3C8], 0FFh
0x18002ecad  mov     [rbp+380h+var_348], 1000000h
0x18002ecb4  xor     edx, edx; Val
0x18002ecb6  lea     r8d, [rdx+78h]; Size
0x18002ecba  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002ecbe  call    memset_0
0x18002ecc3  mov     dword ptr [rsp+480h+var_450], ebx
0x18002ecc7  mov     rax, [r13+0]
0x18002eccb  mov     [rsp+480h+var_458], rax
0x18002ecd0  mov     rax, [r15]
0x18002ecd3  mov     [rsp+480h+var_460], rax
0x18002ecd8  mov     r9, r12
0x18002ecdb  lea     r8, aAnAssociationI; "An association is present: %s - %s (%I6"...
0x18002ece2  lea     rdx, [rbp+380h+var_3E8]
0x18002ece6  lea     rcx, [rbp+380h+var_2D0]
0x18002eced  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18002ecf2  test    dword ptr [r14], 4
0x18002ecf9  setz    bl
0x18002ecfc  lea     rcx, [rbp+380h+var_320]; this
0x18002ed00  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18002ed05  nop
0x18002ed06  lea     rcx, [rbp+380h+var_3F8]
0x18002ed0a  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x18002ed0f  nop
0x18002ed10  lea     rcx, [rbp+380h+var_2E8]
0x18002ed17  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x18002ed1c  nop
0x18002ed1d  lea     rcx, [rbp+380h+var_340]; this
0x18002ed21  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18002ed26  nop
0x18002ed27  lea     rcx, [rbp+380h+var_2D0]; this
0x18002ed2e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18002ed33  mov     al, bl
0x18002ed35  jmp     loc_18002E97E
0x18002ed3a  lea     rcx, [rbp+380h+var_300]; this
0x18002ed41  call    ?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ; CVssRegistryKeyIterator::GetCurrentKeyName(void)
0x18002ed46  mov     rbx, rax
0x18002ed49  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002ed50  mov     [rbp+380h+var_3E8], rax
0x18002ed54  lea     rax, aCvssproviderre; "CVssProviderRegInfo::GetDiffAreaForVolu"...
0x18002ed5b  mov     [rbp+380h+var_3E0], rax
0x18002ed5f  lea     rax, aSprregmc; "SPRREGMC"
0x18002ed66  mov     [rbp+380h+var_3D8], rax
0x18002ed6a  mov     [rbp+380h+var_3D0], 10Dh
0x18002ed71  mov     [rbp+380h+var_3CC], 2
0x18002ed78  mov     [rbp+380h+var_3C8], 0FFh
0x18002ed7f  mov     [rbp+380h+var_348], 1000000h
0x18002ed86  xor     edx, edx; Val
0x18002ed88  lea     r8d, [rdx+78h]; Size
0x18002ed8c  lea     rcx, [rbp+380h+var_3C0]; void *
0x18002ed90  call    memset_0
  ... truncated ...
```
