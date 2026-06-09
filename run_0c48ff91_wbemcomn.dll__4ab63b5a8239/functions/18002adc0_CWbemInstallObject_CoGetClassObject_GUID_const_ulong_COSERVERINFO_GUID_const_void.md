# CWbemInstallObject::CoGetClassObject(_GUID const &,ulong,_COSERVERINFO *,_GUID const &,void * *)

- ea: `0x18002adc0`
- end: `0x18002af93`
- name: `?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z`
- size: `467`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int, struct _COSERVERINFO *, const struct _GUID *, LPVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800273d0`

## callees

- `0x180011e40`
- `0x1800154d0`
- `0x18002adc0`
- `0x18002cb10`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002af3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002af3d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002af0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002af0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002aea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002aea5`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002adf9`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18002adf9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ae3e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002ae3e`

## string_xrefs

- `0x18002af36`: `DllGetClassObject`

## pseudocode

```c
HRESULT __fastcall CWbemInstallObject::CoGetClassObject(
        const struct _GUID *a1,
        DWORD a2,
        struct _COSERVERINFO *a3,
        const struct _GUID *a4,
        LPVOID *ppv)
{
  HRESULT result; // eax
  int i; // ebx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  HMODULE *v11; // rbx
  const WCHAR *v12; // rdi
  HMODULE Library; // rax
  bool v14; // sf
  FARPROC ProcAddress; // rax
  GUID pclsid; // [rsp+30h] [rbp-258h] BYREF
  WCHAR LibFileName[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( !CWbemInstallObject::m_bOffline )
    return CoGetClassObject(a1, a2, a3, a4, ppv);
  if ( CWbemInstallObject::IsInitialized() )
  {
    pclsid = 0;
    for ( i = 0; i < 11; ++i )
    {
      result = CLSIDFromString((LPCOLESTR)*(&CWbemInstallObject::m_rgClsidDllMap + 2 * i), &pclsid);
      if ( result < 0 )
        return result;
      v8 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a1->Data1;
      if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a1->Data1 )
        v8 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a1->Data4;
      if ( !v8 )
      {
        _mm_lfence();
        v9 = dword_180068258[4 * i];
        if ( v9 >= 6 )
          return -2147217407;
        v10 = 16 * v9;
        v11 = (HMODULE *)((char *)&unk_180068308 + v10);
        if ( *(_QWORD *)((char *)&unk_180068308 + v10) )
          goto LABEL_21;
        v12 = *(const WCHAR **)((char *)&CWbemInstallObject::m_rgDllModules + v10);
        if ( GetModuleHandleExW(0, v12, (HMODULE *)((char *)&unk_180068308 + v10)) )
          goto LABEL_21;
        result = StringCchCopyW(LibFileName, 0x105u, CWbemInstallObject::m_pwszBinaryPath);
        if ( result >= 0 )
        {
          result = StringCchCatW(LibFileName, 0x105u, L"\\");
          if ( result >= 0 )
          {
            result = StringCchCatW(LibFileName, 0x105u, v12);
            if ( result >= 0 )
            {
              Library = LoadLibraryExW(LibFileName, 0, 0);
              *v11 = Library;
              if ( Library )
                goto LABEL_21;
              result = GetLastError();
              v14 = result < 0;
              if ( result > 0 )
              {
                result = (unsigned __int16)result | 0x80070000;
                v14 = result < 0;
              }
              if ( !v14 )
              {
LABEL_21:
                ProcAddress = GetProcAddress(*v11, "DllGetClassObject");
                if ( ProcAddress )
                {
                  return ((__int64 (__fastcall *)(const struct _GUID *, GUID *, LPVOID *))ProcAddress)(
                           a1,
                           &IID_IClassFactory,
                           ppv);
                }
                else
                {
                  result = GetLastError();
                  if ( result > 0 )
                    return (unsigned __int16)result | 0x80070000;
                }
              }
            }
          }
        }
        return result;
      }
    }
  }
  return -2147217407;
}

```

## disassembly

```asm
0x18002adc0  push    rbx
0x18002adc2  push    rbp
0x18002adc3  push    rsi
0x18002adc4  push    rdi
0x18002adc5  push    r14
0x18002adc7  sub     rsp, 260h
0x18002adce  mov     rax, cs:__security_cookie
0x18002add5  xor     rax, rsp
0x18002add8  mov     [rsp+288h+var_38], rax
0x18002ade0  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x18002ade7  mov     rsi, rcx
0x18002adea  mov     rbp, [rsp+288h+arg_20]
0x18002adf2  jnz     short loc_18002AE04
0x18002adf4  mov     [rsp+288h+ppv], rbp; ppv
0x18002adf9  call    cs:__imp_CoGetClassObject
0x18002adff  jmp     loc_18002AF75
0x18002ae04  call    ?IsInitialized@CWbemInstallObject@@CA_NXZ; CWbemInstallObject::IsInitialized(void)
0x18002ae09  test    al, al
0x18002ae0b  jz      loc_18002AF70
0x18002ae11  xorps   xmm0, xmm0
0x18002ae14  lea     r14, __ImageBase
0x18002ae1b  movups  xmmword ptr [rsp+288h+pclsid.Data1], xmm0
0x18002ae20  xor     ebx, ebx
0x18002ae22  cmp     ebx, 0Bh
0x18002ae25  jge     loc_18002AF70
0x18002ae2b  movsxd  rdi, ebx
0x18002ae2e  lea     rdx, [rsp+288h+pclsid]; pclsid
0x18002ae33  add     rdi, rdi
0x18002ae36  mov     rcx, rva ?m_rgClsidDllMap@CWbemInstallObject@@0PAUClsidDllMapping@@A[r14+rdi*8]; lpsz
0x18002ae3e  call    cs:__imp_CLSIDFromString
0x18002ae44  test    eax, eax
0x18002ae46  js      loc_18002AF75
0x18002ae4c  mov     rax, qword ptr [rsp+288h+pclsid.Data1]
0x18002ae51  sub     rax, [rsi]
0x18002ae54  jnz     short loc_18002AE5F
0x18002ae56  mov     rax, qword ptr [rsp+288h+pclsid.Data4]
0x18002ae5b  sub     rax, [rsi+8]
0x18002ae5f  test    rax, rax
0x18002ae62  jz      short loc_18002AE68
0x18002ae64  inc     ebx
0x18002ae66  jmp     short loc_18002AE22
0x18002ae68  lfence
0x18002ae6b  movsxd  rax, rva dword_180068258[r14+rdi*8]
0x18002ae73  cmp     rax, 6
0x18002ae77  jnb     loc_18002AF70
0x18002ae7d  shl     rax, 4
0x18002ae81  lea     rbx, rva unk_180068308[r14]
0x18002ae88  add     rbx, rax
0x18002ae8b  cmp     qword ptr [rbx], 0
0x18002ae8f  jnz     loc_18002AF33
0x18002ae95  mov     rdi, [rax+r14+68300h]
0x18002ae9d  mov     r8, rbx; phModule
0x18002aea0  mov     rdx, rdi; lpModuleName
0x18002aea3  xor     ecx, ecx; dwFlags
0x18002aea5  call    cs:__imp_GetModuleHandleExW
0x18002aeab  test    eax, eax
0x18002aead  jnz     loc_18002AF33
0x18002aeb3  mov     r8, cs:?m_pwszBinaryPath@CWbemInstallObject@@0PEBGEB; unsigned __int16 *
0x18002aeba  lea     rcx, [rsp+288h+LibFileName]; unsigned __int16 *
0x18002aebf  mov     r14d, 105h
0x18002aec5  mov     edx, r14d; unsigned __int64
0x18002aec8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002aecd  test    eax, eax
0x18002aecf  js      loc_18002AF75
0x18002aed5  lea     r8, asc_18004CC00; "\\"
0x18002aedc  mov     edx, r14d; unsigned __int64
0x18002aedf  lea     rcx, [rsp+288h+LibFileName]; unsigned __int16 *
0x18002aee4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002aee9  test    eax, eax
0x18002aeeb  js      loc_18002AF75
0x18002aef1  mov     r8, rdi; unsigned __int16 *
0x18002aef4  lea     rcx, [rsp+288h+LibFileName]; unsigned __int16 *
0x18002aef9  mov     edx, r14d; unsigned __int64
0x18002aefc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002af01  test    eax, eax
0x18002af03  js      short loc_18002AF75
0x18002af05  xor     r8d, r8d; dwFlags
0x18002af08  lea     rcx, [rsp+288h+LibFileName]; lpLibFileName
0x18002af0d  xor     edx, edx; hFile
0x18002af0f  call    cs:__imp_LoadLibraryExW
0x18002af15  mov     [rbx], rax
0x18002af18  test    rax, rax
0x18002af1b  jnz     short loc_18002AF33
0x18002af1d  call    cs:__imp_GetLastError
0x18002af23  test    eax, eax
0x18002af25  jle     short loc_18002AF31
0x18002af27  movzx   eax, ax
0x18002af2a  or      eax, 80070000h
0x18002af2f  test    eax, eax
0x18002af31  js      short loc_18002AF75
0x18002af33  mov     rcx, [rbx]; hModule
0x18002af36  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x18002af3d  call    cs:__imp_GetProcAddress
0x18002af43  test    rax, rax
0x18002af46  jz      short loc_18002AF5C
0x18002af48  mov     r8, rbp
0x18002af4b  lea     rdx, IID_IClassFactory
0x18002af52  mov     rcx, rsi
0x18002af55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af5a  jmp     short loc_18002AF75
0x18002af5c  call    cs:__imp_GetLastError
0x18002af62  test    eax, eax
0x18002af64  jle     short loc_18002AF75
0x18002af66  movzx   eax, ax
0x18002af69  or      eax, 80070000h
0x18002af6e  jmp     short loc_18002AF75
0x18002af70  mov     eax, 80041001h
0x18002af75  mov     rcx, [rsp+288h+var_38]
0x18002af7d  xor     rcx, rsp; StackCookie
0x18002af80  call    __security_check_cookie
0x18002af85  add     rsp, 260h
0x18002af8c  pop     r14
0x18002af8e  pop     rdi
0x18002af8f  pop     rsi
0x18002af90  pop     rbp
0x18002af91  pop     rbx
0x18002af92  retn
```
