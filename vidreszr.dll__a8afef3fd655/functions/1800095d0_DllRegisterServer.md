# DllRegisterServer

- ea: `0x1800095d0`
- end: `0x1800098fe`
- name: `DllRegisterServer`
- size: `814`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001968`
- `0x180001dc0`
- `0x180004da0`
- `0x1800095d0`
- `0x180014378`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180009603`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180009603`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800097d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800097d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000977d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000977d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009786`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800097ec`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180009701`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180009770`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180009701`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180009770`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800096c8`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180009724`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800096c8`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180009724`
- `MFPlat!MFTRegister` at `0x1800098c1`
- `MFPlat!MFTRegister` at `0x1800098c1`
- `msdmo!DMORegister` at `0x180009846`
- `msdmo!DMORegister` at `0x180009846`

## string_xrefs

- `0x18000967a`: `CLSID\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`
- `0x1800097c1`: `ThreadingModel`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  HKEY v1; // rbx
  HKEY v2; // rdi
  __int64 cbData; // rax
  HKEY v4; // rcx
  LSTATUS v5; // eax
  DMO_PARTIAL_MEDIATYPE *v6; // rdi
  DMO_PARTIAL_MEDIATYPE *pOutTypes; // rax
  unsigned __int64 v8; // rdx
  DMO_PARTIAL_MEDIATYPE *v9; // rbx
  int v10; // esi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  int v13; // eax
  HRESULT v14; // ecx
  HKEY hKey[2]; // [rsp+70h] [rbp-208h] BYREF
  HKEY phkResult[2]; // [rsp+80h] [rbp-1F8h] BYREF
  WCHAR SubKey[80]; // [rsp+90h] [rbp-1E8h] BYREF
  CHAR Filename[272]; // [rsp+130h] [rbp-148h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = StringCchPrintfW(
             SubKey,
             0x50u,
             L"CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
             CLSID_CResizerDMO.Data1,
             CLSID_CResizerDMO.Data2,
             CLSID_CResizerDMO.Data3,
             CLSID_CResizerDMO.Data4[0],
             CLSID_CResizerDMO.Data4[1],
             CLSID_CResizerDMO.Data4[2],
             CLSID_CResizerDMO.Data4[3],
             CLSID_CResizerDMO.Data4[4],
             CLSID_CResizerDMO.Data4[5],
             CLSID_CResizerDMO.Data4[6],
             CLSID_CResizerDMO.Data4[7]);
  if ( result >= 0 )
  {
    phkResult[0] = 0;
    if ( RegCreateKeyW(HKEY_CLASSES_ROOT, SubKey, phkResult) )
      return -2147467259;
    v1 = phkResult[0];
    if ( !phkResult[0] )
      return -2147467259;
    if ( RegSetValueA(phkResult[0], 0, 1u, "Resizer DMO", 0xBu) )
    {
LABEL_13:
      RegCloseKey(v1);
      return -2147467259;
    }
    hKey[0] = 0;
    if ( RegCreateKeyW(phkResult[0], L"InprocServer32", hKey) )
    {
      hKey[0] = 0;
      goto LABEL_13;
    }
    v2 = hKey[0];
    if ( !hKey[0] )
      goto LABEL_13;
    cbData = -1;
    do
      ++cbData;
    while ( Filename[cbData] );
    if ( RegSetValueA(hKey[0], 0, 1u, Filename, cbData) )
    {
      v4 = v2;
LABEL_12:
      RegCloseKey(v4);
      goto LABEL_13;
    }
    v5 = RegSetValueExA(hKey[0], "ThreadingModel", 0, 1u, "Both", 5u);
    v4 = v2;
    if ( v5 )
      goto LABEL_12;
    RegCloseKey(v2);
    RegCloseKey(v1);
    v6 = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray();
    pOutTypes = (DMO_PARTIAL_MEDIATYPE *)GuidPairArray();
    v9 = pOutTypes;
    if ( v6 )
    {
      if ( pOutTypes )
      {
        v10 = DMORegister(L"Resizer DMO", &CLSID_CResizerDMO, &DMOCATEGORY_VIDEO_EFFECT, 0, 0xCu, v6, 0xCu, pOutTypes);
        operator delete(v6, v11);
        operator delete(v9, v12);
        if ( v10 >= 0 )
        {
          *(GUID *)phkResult = MFT_CATEGORY_VIDEO_EFFECT;
          *(GUID *)hKey = CLSID_CResizerDMO;
          v13 = MFTRegister(
                  (CLSID *)hKey,
                  (GUID *)phkResult,
                  (LPWSTR)L"Resizer DMO",
                  0,
                  0xCu,
                  &pOutputTypes,
                  0xCu,
                  &pOutputTypes,
                  0);
          v14 = 0;
          if ( v13 < 0 )
            return v13;
          return v14;
        }
        else
        {
          return v10;
        }
      }
      else
      {
        operator delete(v6, v8);
        return -2147024882;
      }
    }
    else
    {
      if ( pOutTypes )
        operator delete(pOutTypes, v8);
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800095d0  push    rbx
0x1800095d2  push    rbp
0x1800095d3  push    rsi
0x1800095d4  push    rdi
0x1800095d5  sub     rsp, 258h
0x1800095dc  mov     rax, cs:__security_cookie
0x1800095e3  xor     rax, rsp
0x1800095e6  mov     [rsp+278h+var_38], rax
0x1800095ee  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800095f5  lea     rdx, [rsp+278h+Filename]; lpFilename
0x1800095fd  mov     r8d, 104h; nSize
0x180009603  call    cs:__imp_GetModuleFileNameA
0x180009609  movzx   r9d, cs:CLSID_CResizerDMO.Data4+2
0x180009611  movzx   r8d, cs:CLSID_CResizerDMO.Data4+1
0x180009619  movzx   edx, cs:CLSID_CResizerDMO.Data4
0x180009620  movzx   ecx, cs:CLSID_CResizerDMO.Data3
0x180009627  movzx   esi, cs:CLSID_CResizerDMO.Data4+7
0x18000962e  movzx   edi, cs:CLSID_CResizerDMO.Data4+6
0x180009635  movzx   ebx, cs:CLSID_CResizerDMO.Data4+5
0x18000963c  movzx   r11d, cs:CLSID_CResizerDMO.Data4+4
0x180009644  movzx   r10d, cs:CLSID_CResizerDMO.Data4+3
0x18000964c  movzx   eax, cs:CLSID_CResizerDMO.Data2
0x180009653  mov     [rsp+278h+var_210], esi
0x180009657  mov     [rsp+278h+var_218], edi
0x18000965b  mov     [rsp+278h+var_220], ebx
0x18000965f  mov     [rsp+278h+var_228], r11d
0x180009664  mov     [rsp+278h+var_230], r10d
0x180009669  mov     dword ptr [rsp+278h+pAttributes], r9d
0x18000966e  mov     r9d, cs:CLSID_CResizerDMO.Data1
0x180009675  mov     dword ptr [rsp+278h+pOutTypes], r8d
0x18000967a  lea     r8, aClsid08x04x04x; "CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x180009681  mov     [rsp+278h+cOutTypes], edx
0x180009685  mov     edx, 50h ; 'P'; unsigned __int64
0x18000968a  mov     [rsp+278h+var_250], ecx
0x18000968e  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x180009696  mov     [rsp+278h+cbData], eax
0x18000969a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000969f  test    eax, eax
0x1800096a1  js      loc_180009791
0x1800096a7  xor     ebp, ebp
0x1800096a9  lea     r8, [rsp+278h+phkResult]; phkResult
0x1800096b1  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x1800096b9  mov     [rsp+278h+phkResult], rbp
0x1800096c1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800096c8  call    cs:__imp_RegCreateKeyW
0x1800096ce  test    eax, eax
0x1800096d0  jnz     loc_18000978C
0x1800096d6  mov     rbx, [rsp+278h+phkResult]
0x1800096de  test    rbx, rbx
0x1800096e1  jz      loc_18000978C
0x1800096e7  lea     r9, Data; "Resizer DMO"
0x1800096ee  mov     [rsp+278h+cbData], 0Bh; cbData
0x1800096f6  xor     edx, edx; lpSubKey
0x1800096f8  mov     r8d, 1; dwType
0x1800096fe  mov     rcx, rbx; hKey
0x180009701  call    cs:__imp_RegSetValueA
0x180009707  test    eax, eax
0x180009709  jnz     short loc_180009783
0x18000970b  mov     rcx, [rsp+278h+phkResult]; hKey
0x180009713  lea     r8, [rsp+278h+hKey]; phkResult
0x180009718  lea     rdx, SubKey; "InprocServer32"
0x18000971f  mov     [rsp+278h+hKey], rbp
0x180009724  call    cs:__imp_RegCreateKeyW
0x18000972a  test    eax, eax
0x18000972c  jz      short loc_180009735
0x18000972e  mov     [rsp+278h+hKey], rbp
0x180009733  jmp     short loc_180009783
0x180009735  mov     rdi, [rsp+278h+hKey]
0x18000973a  test    rdi, rdi
0x18000973d  jz      short loc_180009783
0x18000973f  lea     rcx, [rsp+278h+Filename]
0x180009747  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000974e  xchg    ax, ax
0x180009750  inc     rax
0x180009753  cmp     [rcx+rax], bpl
0x180009757  jnz     short loc_180009750
0x180009759  lea     r9, [rsp+278h+Filename]; lpData
0x180009761  mov     [rsp+278h+cbData], eax; cbData
0x180009765  xor     edx, edx; lpSubKey
0x180009767  mov     r8d, 1; dwType
0x18000976d  mov     rcx, rdi; hKey
0x180009770  call    cs:__imp_RegSetValueA
0x180009776  test    eax, eax
0x180009778  jz      short loc_1800097AD
0x18000977a  mov     rcx, rdi; hKey
0x18000977d  call    cs:__imp_RegCloseKey
0x180009783  mov     rcx, rbx; hKey
0x180009786  call    cs:__imp_RegCloseKey
0x18000978c  mov     eax, 80004005h
0x180009791  mov     rcx, [rsp+278h+var_38]
0x180009799  xor     rcx, rsp; StackCookie
0x18000979c  call    __security_check_cookie
0x1800097a1  add     rsp, 258h
0x1800097a8  pop     rdi
0x1800097a9  pop     rsi
0x1800097aa  pop     rbp
0x1800097ab  pop     rbx
0x1800097ac  retn
0x1800097ad  mov     rcx, [rsp+278h+hKey]; hKey
0x1800097b2  lea     rax, aBoth; "Both"
0x1800097b9  mov     [rsp+278h+var_250], 5; cbData
0x1800097c1  lea     rdx, ValueName; "ThreadingModel"
0x1800097c8  mov     r9d, 1; dwType
0x1800097ce  mov     qword ptr [rsp+278h+cbData], rax; lpData
0x1800097d3  xor     r8d, r8d; Reserved
0x1800097d6  call    cs:__imp_RegSetValueExA
0x1800097dc  mov     rcx, rdi; hKey
0x1800097df  test    eax, eax
0x1800097e1  jnz     short loc_18000977D
0x1800097e3  call    cs:__imp_RegCloseKey
0x1800097e9  mov     rcx, rbx; hKey
0x1800097ec  call    cs:__imp_RegCloseKey
0x1800097f2  call    GuidPairArray
0x1800097f7  mov     rdi, rax
0x1800097fa  call    GuidPairArray
0x1800097ff  mov     rbx, rax
0x180009802  test    rdi, rdi
0x180009805  jz      loc_1800098E7
0x18000980b  test    rax, rax
0x18000980e  jz      loc_1800098D5
0x180009814  mov     [rsp+278h+pOutTypes], rax; pOutTypes
0x180009819  lea     r8, DMOCATEGORY_VIDEO_EFFECT; guidCategory
0x180009820  mov     [rsp+278h+cOutTypes], 0Ch; cOutTypes
0x180009828  lea     rdx, CLSID_CResizerDMO; clsidDMO
0x18000982f  mov     qword ptr [rsp+278h+var_250], rdi; pInTypes
0x180009834  lea     rcx, pszName; "Resizer DMO"
0x18000983b  xor     r9d, r9d; dwFlags
0x18000983e  mov     [rsp+278h+cbData], 0Ch; cInTypes
0x180009846  call    cs:__imp_DMORegister
0x18000984c  mov     rcx, rdi; void *
0x18000984f  mov     esi, eax
0x180009851  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009856  mov     rcx, rbx; void *
0x180009859  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000985e  test    esi, esi
0x180009860  jns     short loc_180009869
0x180009862  mov     eax, esi
0x180009864  jmp     loc_180009791
0x180009869  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_EFFECT.Data1
0x180009870  mov     [rsp+278h+pAttributes], rbp; pAttributes
0x180009875  lea     rax, pOutputTypes
0x18000987c  movups  xmm1, xmmword ptr cs:CLSID_CResizerDMO.Data1
0x180009883  mov     [rsp+278h+pOutTypes], rax; pOutputTypes
0x180009888  lea     r8, pszName; "Resizer DMO"
0x18000988f  mov     [rsp+278h+cOutTypes], 0Ch; cOutputTypes
0x180009897  lea     rdx, [rsp+278h+phkResult]; guidCategory
0x18000989f  mov     qword ptr [rsp+278h+var_250], rax; pInputTypes
0x1800098a4  lea     rcx, [rsp+278h+hKey]; clsidMFT
0x1800098a9  xor     r9d, r9d; Flags
0x1800098ac  mov     [rsp+278h+cbData], 0Ch; cInputTypes
0x1800098b4  movaps  xmmword ptr [rsp+278h+phkResult], xmm0
0x1800098bc  movaps  xmmword ptr [rsp+278h+hKey], xmm1
0x1800098c1  call    cs:__imp_MFTRegister
0x1800098c7  test    eax, eax
0x1800098c9  mov     ecx, ebp
0x1800098cb  cmovs   ecx, eax
0x1800098ce  mov     eax, ecx
0x1800098d0  jmp     loc_180009791
0x1800098d5  mov     rcx, rdi; void *
0x1800098d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800098dd  mov     eax, 8007000Eh
0x1800098e2  jmp     loc_180009791
0x1800098e7  test    rbx, rbx
0x1800098ea  jz      short loc_1800098F4
0x1800098ec  mov     rcx, rbx; void *
0x1800098ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800098f4  mov     eax, 8007000Eh
0x1800098f9  jmp     loc_180009791
```
