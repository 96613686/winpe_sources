# ReadBinaryFromRegistry(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x18001ace4`
- end: `0x18001aeae`
- name: `?ReadBinaryFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `458`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int8 **, unsigned int *, DWORD cbData)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001a18c`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001ace4`
- `0x18002170a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ad9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ad9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ade9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ade9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ae7a`

## string_xrefs

- `0x18001acfb`: `ReadBinaryFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadBinaryFromRegistry(
        HKEY hKey,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        DWORD cbData)
{
  __int16 v8; // ax
  signed int v9; // ebx
  LSTATUS v10; // eax
  __int16 v11; // ax
  void *lpData; // rdi
  int v13; // eax
  bool v14; // sf
  unsigned int v15; // ecx
  int v17; // [rsp+30h] [rbp-48h] BYREF
  __int16 v18; // [rsp+34h] [rbp-44h]
  __int16 v19; // [rsp+36h] [rbp-42h]
  int v20; // [rsp+38h] [rbp-40h]
  const unsigned __int16 *Type; // [rsp+B8h] [rbp+40h] BYREF

  Type = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "ReadBinaryFromRegistry", 332, 2);
  LODWORD(Type) = 0;
  cbData = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v18 = 342;
  v8 = 343;
  if ( !a3 || (v18 = 343, v8 = 344, !a4) )
  {
    v9 = -2147024809;
LABEL_7:
    v19 = v8;
LABEL_25:
    v17 = v9;
    goto LABEL_26;
  }
  v18 = 344;
  v17 = 0;
  v10 = RegQueryValueExW(hKey, L"Sid", 0, (LPDWORD)&Type, 0, &cbData);
  v9 = v10;
  if ( v10 == 2 )
  {
    v9 = 1;
    v11 = 349;
LABEL_24:
    v18 = v11;
    goto LABEL_25;
  }
  if ( v10 > 0 )
    v9 = (unsigned __int16)v10 | 0x80070000;
  v17 = v9;
  if ( v9 < 0 )
  {
    v19 = 352;
    v20 = 1;
    goto LABEL_26;
  }
  v18 = 352;
  lpData = CoTaskMemAlloc(cbData);
  v8 = 355;
  if ( !lpData )
  {
    v9 = -2147024882;
    goto LABEL_7;
  }
  v17 = 0;
  v18 = 355;
  memset_0(lpData, 0, cbData);
  v13 = RegQueryValueExW(hKey, L"Sid", 0, (LPDWORD)&Type, (LPBYTE)lpData, &cbData);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  v17 = v13;
  v14 = v13 < 0;
  v11 = 359;
  if ( !v14 )
  {
    v18 = 359;
    v11 = 360;
    if ( (_DWORD)Type == 3 )
    {
      v15 = cbData;
      v9 = 0;
      *a3 = (unsigned __int8 *)lpData;
      *a4 = v15;
      goto LABEL_24;
    }
    v17 = -2147024809;
  }
  v19 = v11;
  CoTaskMemFree(lpData);
  v9 = v17;
LABEL_26:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ace4  mov     [rsp-30h+Type], rdx
0x18001ace9  push    rbp
0x18001acea  push    rbx
0x18001aceb  push    rsi
0x18001acec  push    rdi
0x18001aced  push    r14
0x18001acef  push    r15
0x18001acf1  mov     rbp, rsp
0x18001acf4  sub     rsp, 78h
0x18001acf8  mov     rsi, r9
0x18001acfb  lea     rdx, aReadbinaryfrom; "ReadBinaryFromRegistry"
0x18001ad02  mov     r14, r8
0x18001ad05  mov     r15, rcx
0x18001ad08  mov     r9d, 2; unsigned __int16
0x18001ad0e  lea     rcx, [rbp+var_48]; this
0x18001ad12  mov     r8d, 14Ch; unsigned __int16
0x18001ad18  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ad1d  mov     dword ptr [rbp+Type], 0
0x18001ad24  mov     [rbp+cbData], 0
0x18001ad2b  test    r14, r14
0x18001ad2e  jz      short loc_18001AD37
0x18001ad30  mov     qword ptr [r14], 0
0x18001ad37  test    rsi, rsi
0x18001ad3a  jz      short loc_18001AD42
0x18001ad3c  mov     dword ptr [rsi], 0
0x18001ad42  mov     eax, 156h
0x18001ad47  mov     [rbp+var_44], ax
0x18001ad4b  mov     eax, 157h
0x18001ad50  test    r14, r14
0x18001ad53  jnz     short loc_18001AD63
0x18001ad55  mov     ebx, 80070057h
0x18001ad5a  mov     [rbp+var_42], ax
0x18001ad5e  jmp     loc_18001AE93
0x18001ad63  mov     [rbp+var_44], ax
0x18001ad67  mov     eax, 158h
0x18001ad6c  test    rsi, rsi
0x18001ad6f  jz      short loc_18001AD55
0x18001ad71  mov     [rbp+var_44], ax
0x18001ad75  lea     r9, [rbp+Type]; lpType
0x18001ad79  lea     rax, [rbp+cbData]
0x18001ad7d  mov     [rbp+var_48], 0
0x18001ad84  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18001ad89  lea     rdx, ValueName; "Sid"
0x18001ad90  xor     r8d, r8d; lpReserved
0x18001ad93  mov     [rsp+78h+lpData], 0; lpData
0x18001ad9c  mov     rcx, r15; hKey
0x18001ad9f  call    cs:__imp_RegQueryValueExW
0x18001ada5  mov     ebx, eax
0x18001ada7  cmp     eax, 2
0x18001adaa  jnz     short loc_18001ADB9
0x18001adac  lea     ebx, [rax-1]
0x18001adaf  mov     eax, 15Dh
0x18001adb4  jmp     loc_18001AE8F
0x18001adb9  test    eax, eax
0x18001adbb  jle     short loc_18001ADC6
0x18001adbd  movzx   ebx, ax
0x18001adc0  or      ebx, 80070000h
0x18001adc6  mov     [rbp+var_48], ebx
0x18001adc9  mov     eax, 160h
0x18001adce  test    ebx, ebx
0x18001add0  jns     short loc_18001ADE2
0x18001add2  mov     [rbp+var_42], ax
0x18001add6  mov     [rbp+var_40], 1
0x18001addd  jmp     loc_18001AE96
0x18001ade2  mov     ecx, [rbp+cbData]; cb
0x18001ade5  mov     [rbp+var_44], ax
0x18001ade9  call    cs:__imp_CoTaskMemAlloc
0x18001adef  mov     rdi, rax
0x18001adf2  test    rax, rax
0x18001adf5  mov     eax, 163h
0x18001adfa  jnz     short loc_18001AE06
0x18001adfc  mov     ebx, 8007000Eh
0x18001ae01  jmp     loc_18001AD5A
0x18001ae06  mov     r8d, [rbp+cbData]; Size
0x18001ae0a  xor     edx, edx; Val
0x18001ae0c  mov     rcx, rdi; void *
0x18001ae0f  mov     [rbp+var_48], 0
0x18001ae16  mov     [rbp+var_44], ax
0x18001ae1a  call    memset_0
0x18001ae1f  lea     rax, [rbp+cbData]
0x18001ae23  xor     r8d, r8d; lpReserved
0x18001ae26  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18001ae2b  lea     r9, [rbp+Type]; lpType
0x18001ae2f  lea     rdx, ValueName; "Sid"
0x18001ae36  mov     [rsp+78h+lpData], rdi; lpData
0x18001ae3b  mov     rcx, r15; hKey
0x18001ae3e  call    cs:__imp_RegQueryValueExW
0x18001ae44  test    eax, eax
0x18001ae46  jle     short loc_18001AE50
0x18001ae48  movzx   eax, ax
0x18001ae4b  or      eax, 80070000h
0x18001ae50  mov     [rbp+var_48], eax
0x18001ae53  test    eax, eax
0x18001ae55  mov     eax, 167h
0x18001ae5a  js      short loc_18001AE73
0x18001ae5c  cmp     dword ptr [rbp+Type], 3
0x18001ae60  mov     [rbp+var_44], ax
0x18001ae64  mov     eax, 168h
0x18001ae69  jz      short loc_18001AE85
0x18001ae6b  mov     ebx, 80070057h
0x18001ae70  mov     [rbp+var_48], ebx
0x18001ae73  mov     rcx, rdi; pv
0x18001ae76  mov     [rbp+var_42], ax
0x18001ae7a  call    cs:__imp_CoTaskMemFree
0x18001ae80  mov     ebx, [rbp+var_48]
0x18001ae83  jmp     short loc_18001AE96
0x18001ae85  mov     ecx, [rbp+cbData]
0x18001ae88  xor     ebx, ebx
0x18001ae8a  mov     [r14], rdi
0x18001ae8d  mov     [rsi], ecx
0x18001ae8f  mov     [rbp+var_44], ax
0x18001ae93  mov     [rbp+var_48], ebx
0x18001ae96  lea     rcx, [rbp+var_48]; this
0x18001ae9a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ae9f  mov     eax, ebx
0x18001aea1  add     rsp, 78h
0x18001aea5  pop     r15
0x18001aea7  pop     r14
0x18001aea9  pop     rdi
0x18001aeaa  pop     rsi
0x18001aeab  pop     rbx
0x18001aeac  pop     rbp
0x18001aead  retn
```
