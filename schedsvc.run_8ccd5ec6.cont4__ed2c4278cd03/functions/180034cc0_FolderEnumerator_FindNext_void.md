# FolderEnumerator::FindNext(void)

- ea: `0x180034cc0`
- end: `0x1800351c2`
- name: `?FindNext@FolderEnumerator@@QEAA_NXZ`
- size: `1282`
- prototype: `bool __fastcall(FolderEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180027990`

## callees

- `0x18000cc40`
- `0x180034cc0`
- `0x180054824`
- `0x18005a2bc`
- `0x180082a40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180034e6c`
- `OLEAUT32!__imp_SysAllocString` at `0x180034e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180034f3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180034f3a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034d28`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034d28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034d61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034d61`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034da3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034da3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034de3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034de3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034e41`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall FolderEnumerator::FindNext(FolderEnumerator *this)
{
  DWORD i; // edi
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  bool v5; // zf
  __int64 v6; // rdi
  HKEY v7; // rax
  _QWORD *v8; // rdi
  BSTR v9; // rax
  struct IErrorInfo *v10; // rdx
  void *v12; // rcx
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+74h] [rbp-8Ch]
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[4]; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-74h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  for ( i = *((_DWORD *)this + 9) + 1; ; ++i )
  {
    phkResult = 0;
    Type = 0;
    cbData = 0;
    *(_DWORD *)Data = 0;
    cchName = 261;
    v3 = RegEnumKeyExW(*((HKEY *)this + 3), i, Name, &cchName, 0, 0, 0, 0);
    if ( v3 == 259 )
      break;
    if ( v3 )
    {
      v16 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v17 = &qword_1800A8718;
      v18 = 0;
      v19 = 0;
      v20 = v3;
      v21 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v4 = RegOpenKeyExW(*((HKEY *)this + 3), Name, 0, 0x20019u, &phkResult);
    if ( v4 )
    {
      v16 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v17 = &qword_1800A8718;
      v18 = 0;
      v19 = 0;
      v20 = v4;
      v21 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    Type = 1;
    cbData = 0;
    if ( RegQueryValueExW(phkResult, L"Id", 0, &Type, 0, &cbData) == 2 )
    {
      v5 = *((_BYTE *)this + 32) == 0;
    }
    else
    {
      if ( Type != 1 )
      {
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 1359;
        v21 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( cbData > 0x50 )
      {
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 1359;
        v21 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( *((_BYTE *)this + 32) )
        goto LABEL_9;
      Type = 4;
      cbData = 4;
      if ( RegQueryValueExW(phkResult, L"Index", 0, &Type, Data, &cbData) )
      {
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 1359;
        v21 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( Type != 4 )
      {
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 1359;
        v21 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      if ( cbData != 4 )
      {
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 1359;
        v21 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      v5 = *(_DWORD *)Data == 0;
    }
    if ( !v5 )
    {
      if ( phkResult )
        RegCloseKey(phkResult);
      *((_DWORD *)this + 9) = i;
      v6 = *((_QWORD *)this + 5);
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 )
        {
          if ( *(_QWORD *)v6 )
          {
            SysFreeString(*(BSTR *)v6);
            *(_QWORD *)v6 = 0;
          }
          v12 = *(void **)(v6 + 8);
          if ( v12 )
          {
            operator delete(v12);
            *(_QWORD *)(v6 + 8) = 0;
          }
          HeapFree(g_PrivateHeap, 0, (LPVOID)v6);
        }
        *((_QWORD *)this + 5) = 0;
      }
      v7 = (HKEY)HeapAlloc(g_PrivateHeap, 0, 0x18u);
      v8 = v7;
      if ( !v7 )
      {
        v16 = 0;
        v17 = &qword_1800A8718;
        v18 = 0;
        v19 = 0;
        v20 = 14;
        v21 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      phkResult = v7;
      *((_QWORD *)v7 + 1) = 0;
      *((_DWORD *)v7 + 4) = 1;
      v9 = SysAllocString(Name);
      *v8 = v9;
      if ( !v9 )
        _com_raise_error(-2147024882, v10);
      *((_QWORD *)this + 5) = v8;
      return 1;
    }
LABEL_9:
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180034cc0  push    rbp
0x180034cc2  push    rbx
0x180034cc3  push    rsi
0x180034cc4  push    rdi
0x180034cc5  lea     rbp, [rsp-1B8h]
0x180034ccd  sub     rsp, 2B8h
0x180034cd4  mov     rax, cs:__security_cookie
0x180034cdb  xor     rax, rsp
0x180034cde  mov     [rbp+1D0h+var_30], rax
0x180034ce5  mov     rbx, rcx
0x180034ce8  mov     edi, [rcx+24h]
0x180034ceb  inc     edi
0x180034ced  xor     esi, esi
0x180034cef  nop
0x180034cf0  mov     [rbp+1D0h+phkResult], rsi
0x180034cf4  mov     [rsp+2D0h+Type], esi
0x180034cf8  mov     [rsp+2D0h+cbData], esi
0x180034cfc  mov     dword ptr [rbp+1D0h+Data], esi
0x180034cff  mov     [rbp+1D0h+cchName], 105h
0x180034d06  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180034d0b  mov     [rsp+2D0h+lpcchClass], rsi; lpcchClass
0x180034d10  mov     [rsp+2D0h+lpClass], rsi; lpClass
0x180034d15  mov     [rsp+2D0h+lpReserved], rsi; lpReserved
0x180034d1a  lea     r9, [rbp+1D0h+cchName]; lpcchName
0x180034d1e  lea     r8, [rbp+1D0h+Name]; lpName
0x180034d22  mov     edx, edi; dwIndex
0x180034d24  mov     rcx, [rbx+18h]; hKey
0x180034d28  call    cs:__imp_RegEnumKeyExW
0x180034d2f  nop     dword ptr [rax+rax+00h]
0x180034d34  cmp     eax, 103h
0x180034d39  jz      loc_180034E8C
0x180034d3f  test    eax, eax
0x180034d41  jnz     loc_18003517C
0x180034d47  lea     rax, [rbp+1D0h+phkResult]
0x180034d4b  mov     [rsp+2D0h+lpReserved], rax; phkResult
0x180034d50  mov     r9d, 20019h; samDesired
0x180034d56  xor     r8d, r8d; ulOptions
0x180034d59  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x180034d5d  mov     rcx, [rbx+18h]; hKey
0x180034d61  call    cs:__imp_RegOpenKeyExW
0x180034d68  nop     dword ptr [rax+rax+00h]
0x180034d6d  test    eax, eax
0x180034d6f  jnz     loc_180035136
0x180034d75  mov     [rsp+2D0h+Type], 1
0x180034d7d  mov     [rsp+2D0h+cbData], esi
0x180034d81  lea     rax, [rsp+2D0h+cbData]
0x180034d86  mov     [rsp+2D0h+lpClass], rax; lpcbData
0x180034d8b  mov     [rsp+2D0h+lpReserved], rsi; lpData
0x180034d90  lea     r9, [rsp+2D0h+Type]; lpType
0x180034d95  xor     r8d, r8d; lpReserved
0x180034d98  lea     rdx, aId; "Id"
0x180034d9f  mov     rcx, [rbp+1D0h+phkResult]; hKey
0x180034da3  call    cs:__imp_RegQueryValueExW
0x180034daa  nop     dword ptr [rax+rax+00h]
0x180034daf  cmp     eax, 2
0x180034db2  jz      short loc_180034DF4
0x180034db4  cmp     [rsp+2D0h+Type], 1
0x180034db9  jnz     loc_1800350EC
0x180034dbf  cmp     [rsp+2D0h+cbData], 50h ; 'P'
0x180034dc4  ja      loc_1800350A2
0x180034dca  cmp     byte ptr [rbx+20h], 0
0x180034dce  jz      loc_180034EBF
0x180034dd4  inc     edi
0x180034dd6  mov     rcx, [rbp+1D0h+phkResult]; hKey
0x180034dda  test    rcx, rcx
0x180034ddd  jz      loc_180034CF0
0x180034de3  call    cs:__imp_RegCloseKey
0x180034dea  nop     dword ptr [rax+rax+00h]
0x180034def  jmp     loc_180034CF0
0x180034df4  cmp     byte ptr [rbx+20h], 0
0x180034df8  jz      short loc_180034DD4
0x180034dfa  mov     rcx, [rbp+1D0h+phkResult]; hKey
0x180034dfe  test    rcx, rcx
0x180034e01  jz      short loc_180034E0F
0x180034e03  call    cs:__imp_RegCloseKey
0x180034e0a  nop     dword ptr [rax+rax+00h]
0x180034e0f  mov     [rbx+24h], edi
0x180034e12  mov     rdi, [rbx+28h]
0x180034e16  test    rdi, rdi
0x180034e19  jz      short loc_180034E32
0x180034e1b  mov     eax, 0FFFFFFFFh
0x180034e20  lock xadd [rdi+10h], eax
0x180034e25  cmp     eax, 1
0x180034e28  jz      loc_180034F32
0x180034e2e  mov     [rbx+28h], rsi
0x180034e32  xor     edx, edx; dwFlags
0x180034e34  mov     r8d, 18h; dwBytes
0x180034e3a  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180034e41  call    cs:__imp_HeapAlloc
0x180034e48  nop     dword ptr [rax+rax+00h]
0x180034e4d  mov     rdi, rax
0x180034e50  test    rax, rax
0x180034e53  jz      loc_180034F7A
0x180034e59  mov     [rbp+1D0h+phkResult], rax
0x180034e5d  mov     [rax+8], rsi
0x180034e61  mov     dword ptr [rax+10h], 1
0x180034e68  lea     rcx, [rbp+1D0h+Name]; psz
0x180034e6c  call    cs:__imp_SysAllocString
0x180034e73  nop     dword ptr [rax+rax+00h]
0x180034e78  mov     [rdi], rax
0x180034e7b  test    rax, rax
0x180034e7e  jz      loc_180034F27
0x180034e84  mov     [rbx+28h], rdi
0x180034e88  mov     al, 1
0x180034e8a  jmp     short loc_180034EA3
0x180034e8c  mov     rcx, [rbp+1D0h+phkResult]; hKey
0x180034e90  test    rcx, rcx
0x180034e93  jz      short loc_180034EA1
0x180034e95  call    cs:__imp_RegCloseKey
0x180034e9c  nop     dword ptr [rax+rax+00h]
0x180034ea1  xor     al, al
0x180034ea3  mov     rcx, [rbp+1D0h+var_30]
0x180034eaa  xor     rcx, rsp; StackCookie
0x180034ead  call    __security_check_cookie
0x180034eb2  add     rsp, 2B8h
0x180034eb9  pop     rdi
0x180034eba  pop     rsi
0x180034ebb  pop     rbx
0x180034ebc  pop     rbp
0x180034ebd  retn
0x180034ebf  mov     [rsp+2D0h+Type], 4
0x180034ec7  mov     [rsp+2D0h+cbData], 4
0x180034ecf  lea     rax, [rsp+2D0h+cbData]
0x180034ed4  mov     [rsp+2D0h+lpClass], rax; lpcbData
0x180034ed9  lea     rax, [rbp+1D0h+Data]
0x180034edd  mov     [rsp+2D0h+lpReserved], rax; lpData
0x180034ee2  lea     r9, [rsp+2D0h+Type]; lpType
0x180034ee7  xor     r8d, r8d; lpReserved
0x180034eea  lea     rdx, aIndex; "Index"
0x180034ef1  mov     rcx, [rbp+1D0h+phkResult]; hKey
0x180034ef5  call    cs:__imp_RegQueryValueExW
0x180034efc  nop     dword ptr [rax+rax+00h]
0x180034f01  test    eax, eax
0x180034f03  jnz     loc_180035058
0x180034f09  cmp     [rsp+2D0h+Type], 4
0x180034f0e  jnz     loc_18003500E
0x180034f14  cmp     [rsp+2D0h+cbData], 4
0x180034f19  jnz     loc_180034FC4
0x180034f1f  cmp     dword ptr [rbp+1D0h+Data], eax
0x180034f22  jmp     loc_180034DF8
0x180034f27  mov     ecx, 8007000Eh; int
0x180034f2c  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180034f32  mov     rcx, [rdi]; bstrString
0x180034f35  test    rcx, rcx
0x180034f38  jz      short loc_180034F49
0x180034f3a  call    cs:__imp_SysFreeString
0x180034f41  nop     dword ptr [rax+rax+00h]
0x180034f46  mov     [rdi], rsi
0x180034f49  mov     rcx, [rdi+8]; void *
0x180034f4d  test    rcx, rcx
0x180034f50  jnz     short loc_180034F6F
0x180034f52  mov     r8, rdi; lpMem
0x180034f55  xor     edx, edx; dwFlags
0x180034f57  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180034f5e  call    cs:__imp_HeapFree
0x180034f65  nop     dword ptr [rax+rax+00h]
0x180034f6a  jmp     loc_180034E2E
0x180034f6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034f74  mov     [rdi+8], rsi
0x180034f78  jmp     short loc_180034F52
0x180034f7a  mov     [rsp+2D0h+var_280], 0
0x180034f7f  lea     rcx, qword_1800A8718
0x180034f86  mov     [rsp+2D0h+var_278], rcx
0x180034f8b  mov     [rsp+2D0h+var_270], rsi
0x180034f90  mov     [rsp+2D0h+var_268], rsi
0x180034f95  mov     [rsp+2D0h+var_260], 0Eh
0x180034f9d  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x180034fa6  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180034fad  mov     [rsp+2D0h+pExceptionObject], rax
0x180034fb2  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180034fb9  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x180034fbe  call    _CxxThrowException_0
0x180034fc4  mov     [rsp+2D0h+var_280], 0
0x180034fc9  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180034fd0  mov     [rsp+2D0h+pExceptionObject], rcx
0x180034fd5  lea     rcx, qword_1800A8718
0x180034fdc  mov     [rsp+2D0h+var_278], rcx
0x180034fe1  mov     [rsp+2D0h+var_270], rsi
0x180034fe6  mov     [rsp+2D0h+var_268], rsi
0x180034feb  mov     [rsp+2D0h+var_260], 54Fh
0x180034ff3  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x180034ffc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180035003  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x180035008  call    _CxxThrowException_0
0x18003500e  mov     [rsp+2D0h+var_280], 0
0x180035013  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18003501a  mov     [rsp+2D0h+pExceptionObject], rcx
0x18003501f  lea     rcx, qword_1800A8718
0x180035026  mov     [rsp+2D0h+var_278], rcx
0x18003502b  mov     [rsp+2D0h+var_270], rsi
0x180035030  mov     [rsp+2D0h+var_268], rsi
0x180035035  mov     [rsp+2D0h+var_260], 54Fh
0x18003503d  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x180035046  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003504d  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x180035052  call    _CxxThrowException_0
0x180035058  mov     [rsp+2D0h+var_280], 0
0x18003505d  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180035064  mov     [rsp+2D0h+pExceptionObject], rcx
0x180035069  lea     rcx, qword_1800A8718
0x180035070  mov     [rsp+2D0h+var_278], rcx
0x180035075  mov     [rsp+2D0h+var_270], rsi
0x18003507a  mov     [rsp+2D0h+var_268], rsi
0x18003507f  mov     [rsp+2D0h+var_260], 54Fh
0x180035087  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x180035090  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180035097  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18003509c  call    _CxxThrowException_0
0x1800350a2  mov     [rsp+2D0h+var_280], 0
0x1800350a7  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800350ae  mov     [rsp+2D0h+pExceptionObject], rcx
0x1800350b3  lea     rcx, qword_1800A8718
0x1800350ba  mov     [rsp+2D0h+var_278], rcx
0x1800350bf  mov     [rsp+2D0h+var_270], rsi
0x1800350c4  mov     [rsp+2D0h+var_268], rsi
0x1800350c9  mov     [rsp+2D0h+var_260], 54Fh
0x1800350d1  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x1800350da  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800350e1  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x1800350e6  call    _CxxThrowException_0
0x1800350ec  mov     [rsp+2D0h+var_280], 0
0x1800350f1  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800350f8  mov     [rsp+2D0h+pExceptionObject], rcx
0x1800350fd  lea     rcx, qword_1800A8718
0x180035104  mov     [rsp+2D0h+var_278], rcx
0x180035109  mov     [rsp+2D0h+var_270], rsi
0x18003510e  mov     [rsp+2D0h+var_268], rsi
0x180035113  mov     [rsp+2D0h+var_260], 54Fh
0x18003511b  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x180035124  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18003512b  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x180035130  call    _CxxThrowException_0
0x180035136  mov     [rsp+2D0h+var_280], 0
0x18003513b  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180035142  mov     [rsp+2D0h+pExceptionObject], rcx
0x180035147  lea     rcx, qword_1800A8718
0x18003514e  mov     [rsp+2D0h+var_278], rcx
0x180035153  mov     [rsp+2D0h+var_270], rsi
0x180035158  mov     [rsp+2D0h+var_268], rsi
0x18003515d  mov     [rsp+2D0h+var_260], eax
0x180035161  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x18003516a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180035171  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x180035176  call    _CxxThrowException_0
0x18003517c  mov     [rsp+2D0h+var_280], 0
0x180035181  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180035188  mov     [rsp+2D0h+pExceptionObject], rcx
0x18003518d  lea     rcx, qword_1800A8718
0x180035194  mov     [rsp+2D0h+var_278], rcx
0x180035199  mov     [rsp+2D0h+var_270], rsi
0x18003519e  mov     [rsp+2D0h+var_268], rsi
0x1800351a3  mov     [rsp+2D0h+var_260], eax
0x1800351a7  mov     [rsp+2D0h+var_25C], 0FFFFFFFFFFFFFFFFh
0x1800351b0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800351b7  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x1800351bc  call    _CxxThrowException_0
```
