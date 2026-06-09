# BPrintEMFJobNow(void *,void *,_EMF_ATTRIBUTE_INFO *,ulong,_devicemodeW *,_PAGE_NUMBER *,_PRINTPROCESSORDATA *)

- ea: `0x180003890`
- end: `0x180003b2f`
- name: `?BPrintEMFJobNow@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@KPEAU_devicemodeW@@PEAU_PAGE_NUMBER@@PEAU_PRINTPROCESSORDATA@@@Z`
- size: `671`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, void *@<rdx>, struct _EMF_ATTRIBUTE_INFO *@<r8>, unsigned int@<r9d>, struct _devicemodeW *, struct _PAGE_NUMBER *, struct _PRINTPROCESSORDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002400`

## callees

- `0x180003890`
- `0x1800047f0`
- `0x180006b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003985`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003985`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000395f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000395f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000391d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000391d`
- `GDI32!GdiStartDocEMF` at `0x1800039be`
- `GDI32!GdiStartDocEMF` at `0x180003a14`
- `GDI32!GdiStartDocEMF` at `0x1800039be`
- `GDI32!GdiStartDocEMF` at `0x180003a14`
- `GDI32!GdiEndDocEMF` at `0x180003a02`
- `GDI32!GdiEndDocEMF` at `0x180003b0c`
- `GDI32!GdiEndDocEMF` at `0x180003a02`
- `GDI32!GdiEndDocEMF` at `0x180003b0c`

## pseudocode

```c
__int64 __fastcall BPrintEMFJobNow(
        void *a1,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        unsigned int a4,
        struct _devicemodeW *a5,
        struct _PAGE_NUMBER *a6,
        struct _PRINTPROCESSORDATA *a7)
{
  DWORD LastError; // edi
  unsigned int v11; // ebx
  int v12; // r14d
  int v13; // eax
  struct _PRINTPROCESSORDATA *v14; // r15
  int v15; // eax
  unsigned int v16; // ecx
  unsigned int v18; // [rsp+40h] [rbp-88h]
  unsigned int v19; // [rsp+48h] [rbp-80h]
  int v20; // [rsp+4Ch] [rbp-7Ch]
  DWORD cbData; // [rsp+50h] [rbp-78h] BYREF
  int v22; // [rsp+54h] [rbp-74h]
  HKEY hKey; // [rsp+60h] [rbp-68h] BYREF
  DOCINFOW pDocInfo; // [rsp+68h] [rbp-60h] BYREF
  int Data; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v26; // [rsp+E8h] [rbp+20h]

  v26 = a4;
  memset(&pDocInfo, 0, sizeof(pDocInfo));
  LastError = 0;
  v11 = 0;
  v12 = 0;
  v20 = *((_DWORD *)a3 + 11);
  v19 = *((_DWORD *)a3 + 12);
  v22 = *((_DWORD *)a3 + 17);
  if ( dword_18000D438 == -1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &hKey) )
    {
      Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"ThrowDriverException", 0, 0, (LPBYTE)&Data, &cbData) || (v13 = 1, Data != 1) )
        v13 = 0;
      dword_18000D438 = v13;
      RegCloseKey(hKey);
    }
  }
  pDocInfo.cbSize = 40;
  v14 = a7;
  pDocInfo.lpszDocName = (LPCWSTR)*((_QWORD *)a7 + 7);
  pDocInfo.lpszOutput = (LPCWSTR)*((_QWORD *)a7 + 8);
  pDocInfo.lpszDatatype = 0;
  if ( GdiStartDocEMF(a1, &pDocInfo) )
  {
    v12 = 1;
    if ( *((_DWORD *)a3 + 21) )
    {
      v15 = (unsigned __int16)v20;
      v16 = (unsigned __int16)v20;
      v18 = (unsigned __int16)v20;
      while ( v16 )
      {
        if ( v22 && v16 != v15 )
        {
          if ( !GdiEndDocEMF(a1) || !GdiStartDocEMF(a1, &pDocInfo) )
          {
            v12 = 0;
            goto LABEL_24;
          }
          v16 = v18;
        }
        if ( v16 > v19 )
        {
          SetDrvCopies(a2, a5, v19);
          v18 -= v19;
        }
        else
        {
          SetDrvCopies(a2, a5, v16);
          v18 = 0;
        }
        if ( !PrintEMFSingleCopy(a1, a2, a3, a6, v26, a5, v14) )
          goto LABEL_24;
        v16 = v18;
        v15 = (unsigned __int16)v20;
      }
    }
    else if ( !PrintEMFSingleCopy(a1, a2, a3, a6, v26, a5, v14) )
    {
      goto LABEL_24;
    }
    v11 = 1;
  }
LABEL_24:
  if ( !v11 )
    LastError = GetLastError();
  if ( v12 )
    GdiEndDocEMF(a1);
  SetLastError(LastError);
  return v11;
}

```

## disassembly

```asm
0x180003890  mov     r11, rsp
0x180003893  mov     [r11+20h], r9d
0x180003897  mov     [r11+8], rcx
0x18000389b  push    rbx
0x18000389c  push    rsi
0x18000389d  push    rdi
0x18000389e  push    r12
0x1800038a0  push    r13
0x1800038a2  push    r14
0x1800038a4  push    r15
0x1800038a6  sub     rsp, 90h
0x1800038ad  mov     rsi, r8
0x1800038b0  mov     r13, rdx
0x1800038b3  mov     r12, rcx
0x1800038b6  xorps   xmm0, xmm0
0x1800038b9  xor     eax, eax
0x1800038bb  movups  xmmword ptr [rsp+0C8h+pDocInfo.cbSize], xmm0
0x1800038c0  movups  xmmword ptr [rsp+0C8h+pDocInfo.lpszOutput], xmm0
0x1800038c5  mov     [r11-40h], rax
0x1800038c9  xor     edi, edi
0x1800038cb  mov     ebx, edi
0x1800038cd  mov     r14d, edi
0x1800038d0  mov     [rsp+0C8h+var_84], edi
0x1800038d4  mov     eax, [r8+2Ch]
0x1800038d8  mov     [rsp+0C8h+var_7C], eax
0x1800038dc  mov     eax, [r8+30h]
0x1800038e0  mov     [rsp+0C8h+var_80], eax
0x1800038e4  mov     eax, [r8+44h]
0x1800038e8  mov     [rsp+0C8h+var_74], eax
0x1800038ec  cmp     cs:dword_18000D438, 0FFFFFFFFh
0x1800038f3  jnz     loc_18000398C
0x1800038f9  mov     [r11-68h], rdi
0x1800038fd  lea     rax, [r11-68h]
0x180003901  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180003906  mov     r9d, 20019h; samDesired
0x18000390c  xor     r8d, r8d; ulOptions
0x18000390f  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Pri"...
0x180003916  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000391d  call    cs:__imp_RegOpenKeyExW
0x180003923  test    eax, eax
0x180003925  jnz     short loc_18000398C
0x180003927  mov     [rsp+0C8h+Data], edi
0x18000392e  mov     [rsp+0C8h+cbData], 4
0x180003936  lea     rax, [rsp+0C8h+cbData]
0x18000393b  mov     [rsp+0C8h+lpcbData], rax; lpcbData
0x180003940  lea     rax, [rsp+0C8h+Data]
0x180003948  mov     [rsp+0C8h+phkResult], rax; lpData
0x18000394d  xor     r9d, r9d; lpType
0x180003950  xor     r8d, r8d; lpReserved
0x180003953  lea     rdx, ValueName; "ThrowDriverException"
0x18000395a  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18000395f  call    cs:__imp_RegQueryValueExW
0x180003965  test    eax, eax
0x180003967  jnz     short loc_180003978
0x180003969  cmp     [rsp+0C8h+Data], 1
0x180003971  mov     eax, 1
0x180003976  jz      short loc_18000397A
0x180003978  mov     eax, edi
0x18000397a  mov     cs:dword_18000D438, eax
0x180003980  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180003985  call    cs:__imp_RegCloseKey
0x18000398b  nop
0x18000398c  mov     [rsp+0C8h+pDocInfo.cbSize], 28h ; '('
0x180003994  mov     r15, [rsp+0C8h+arg_30]
0x18000399c  mov     rax, [r15+38h]
0x1800039a0  mov     [rsp+0C8h+pDocInfo.lpszDocName], rax
0x1800039a5  mov     rax, [r15+40h]
0x1800039a9  mov     [rsp+0C8h+pDocInfo.lpszOutput], rax
0x1800039ae  mov     [rsp+0C8h+pDocInfo.lpszDatatype], rdi
0x1800039b6  lea     rdx, [rsp+0C8h+pDocInfo]; pDocInfo
0x1800039bb  mov     rcx, r12; SpoolFileHandle
0x1800039be  call    cs:__imp_GdiStartDocEMF
0x1800039c4  test    eax, eax
0x1800039c6  jz      loc_180003AF8
0x1800039cc  mov     r14d, 1
0x1800039d2  mov     [rsp+0C8h+var_84], r14d
0x1800039d7  cmp     dword ptr [rsi+54h], 0
0x1800039db  jz      loc_180003AAB
0x1800039e1  movzx   eax, word ptr [rsp+0C8h+var_7C]
0x1800039e6  mov     ecx, eax
0x1800039e8  mov     [rsp+0C8h+var_88], eax
0x1800039ec  test    ecx, ecx
0x1800039ee  jz      loc_180003AE2
0x1800039f4  cmp     [rsp+0C8h+var_74], 0
0x1800039f9  jz      short loc_180003A2E
0x1800039fb  cmp     ecx, eax
0x1800039fd  jz      short loc_180003A2E
0x1800039ff  mov     rcx, r12; SpoolFileHandle
0x180003a02  call    cs:__imp_GdiEndDocEMF
0x180003a08  test    eax, eax
0x180003a0a  jz      short loc_180003A1E
0x180003a0c  lea     rdx, [rsp+0C8h+pDocInfo]; pDocInfo
0x180003a11  mov     rcx, r12; SpoolFileHandle
0x180003a14  call    cs:__imp_GdiStartDocEMF
0x180003a1a  test    eax, eax
0x180003a1c  jnz     short loc_180003A2A
0x180003a1e  mov     r14d, edi
0x180003a21  mov     [rsp+0C8h+var_84], edi
0x180003a25  jmp     loc_180003AF8
0x180003a2a  mov     ecx, [rsp+0C8h+var_88]
0x180003a2e  mov     eax, [rsp+0C8h+var_80]
0x180003a32  mov     rdx, [rsp+0C8h+arg_20]; struct _devicemodeW *
0x180003a3a  cmp     ecx, eax
0x180003a3c  ja      short loc_180003A4F
0x180003a3e  mov     r8d, ecx; unsigned int
0x180003a41  mov     rcx, r13; hdc
0x180003a44  call    ?SetDrvCopies@@YAHPEAXPEAU_devicemodeW@@K@Z; SetDrvCopies(void *,_devicemodeW *,ulong)
0x180003a49  mov     [rsp+0C8h+var_88], edi
0x180003a4d  jmp     short loc_180003A66
0x180003a4f  mov     r8d, eax; unsigned int
0x180003a52  mov     rcx, r13; hdc
0x180003a55  call    ?SetDrvCopies@@YAHPEAXPEAU_devicemodeW@@K@Z; SetDrvCopies(void *,_devicemodeW *,ulong)
0x180003a5a  mov     eax, [rsp+0C8h+var_88]
0x180003a5e  sub     eax, [rsp+0C8h+var_80]
0x180003a62  mov     [rsp+0C8h+var_88], eax
0x180003a66  mov     [rsp+0C8h+var_98], r15; struct _PRINTPROCESSORDATA *
0x180003a6b  mov     rax, [rsp+0C8h+arg_20]
0x180003a73  mov     [rsp+0C8h+lpcbData], rax; struct _devicemodeW *
0x180003a78  mov     eax, [rsp+0C8h+arg_18]
0x180003a7f  mov     dword ptr [rsp+0C8h+phkResult], eax; unsigned int
0x180003a83  mov     r9, [rsp+0C8h+arg_28]; struct _PAGE_NUMBER *
0x180003a8b  mov     r8, rsi; struct _EMF_ATTRIBUTE_INFO *
0x180003a8e  mov     rdx, r13; void *
0x180003a91  mov     rcx, r12; void *
0x180003a94  call    ?PrintEMFSingleCopy@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@KPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z; PrintEMFSingleCopy(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)
0x180003a99  test    eax, eax
0x180003a9b  jz      short loc_180003AF8
0x180003a9d  mov     ecx, [rsp+0C8h+var_88]
0x180003aa1  movzx   eax, word ptr [rsp+0C8h+var_7C]
0x180003aa6  jmp     loc_1800039EC
0x180003aab  mov     [rsp+0C8h+var_98], r15; struct _PRINTPROCESSORDATA *
0x180003ab0  mov     rax, [rsp+0C8h+arg_20]
0x180003ab8  mov     [rsp+0C8h+lpcbData], rax; struct _devicemodeW *
0x180003abd  mov     eax, [rsp+0C8h+arg_18]
0x180003ac4  mov     dword ptr [rsp+0C8h+phkResult], eax; unsigned int
0x180003ac8  mov     r9, [rsp+0C8h+arg_28]; struct _PAGE_NUMBER *
0x180003ad0  mov     r8, rsi; struct _EMF_ATTRIBUTE_INFO *
0x180003ad3  mov     rdx, r13; void *
0x180003ad6  mov     rcx, r12; void *
0x180003ad9  call    ?PrintEMFSingleCopy@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@PEAU_PAGE_NUMBER@@KPEAU_devicemodeW@@PEAU_PRINTPROCESSORDATA@@@Z; PrintEMFSingleCopy(void *,void *,_EMF_ATTRIBUTE_INFO *,_PAGE_NUMBER *,ulong,_devicemodeW *,_PRINTPROCESSORDATA *)
0x180003ade  test    eax, eax
0x180003ae0  jz      short loc_180003AF8
0x180003ae2  mov     ebx, r14d
0x180003ae5  jmp     short loc_180003AF8
0x180003ae7  xor     edi, edi
0x180003ae9  mov     r12, [rsp+0C8h+arg_0]
0x180003af1  mov     ebx, edi
0x180003af3  mov     r14d, [rsp+0C8h+var_84]
0x180003af8  test    ebx, ebx
0x180003afa  jnz     short loc_180003B04
0x180003afc  call    cs:__imp_GetLastError
0x180003b02  mov     edi, eax
0x180003b04  test    r14d, r14d
0x180003b07  jz      short loc_180003B12
0x180003b09  mov     rcx, r12; SpoolFileHandle
0x180003b0c  call    cs:__imp_GdiEndDocEMF
0x180003b12  mov     ecx, edi; dwErrCode
0x180003b14  call    cs:__imp_SetLastError
0x180003b1a  mov     eax, ebx
0x180003b1c  add     rsp, 90h
0x180003b23  pop     r15
0x180003b25  pop     r14
0x180003b27  pop     r13
0x180003b29  pop     r12
0x180003b2b  pop     rdi
0x180003b2c  pop     rsi
0x180003b2d  pop     rbx
0x180003b2e  retn
0x180007830  push    rbp
0x180007832  sub     rsp, 40h
0x180007836  mov     rbp, rdx
0x180007839  xor     eax, eax
0x18000783b  cmp     cs:dword_18000D438, 1
0x180007842  setnz   al
0x180007845  add     rsp, 40h
0x180007849  pop     rbp
0x18000784a  retn
```
