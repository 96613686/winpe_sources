# ReadBinaryFromRegistry(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x18008b04c`
- end: `0x18008b22f`
- name: `?ReadBinaryFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `483`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180090e40`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008b04c`
- `0x1800cf56a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b1b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b1b2`
- `ole32!CoTaskMemFree` at `0x18008b1f4`
- `ole32!CoTaskMemFree` at `0x18008b1f4`
- `ole32!CoTaskMemAlloc` at `0x18008b157`
- `ole32!CoTaskMemAlloc` at `0x18008b157`

## string_xrefs

- `0x18008b063`: `ReadBinaryFromRegistry`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "ReadBinaryFromRegistry", 0x14Cu, 2u);
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
0x18008b04c  mov     [rsp-30h+Type], rdx
0x18008b051  push    rbp
0x18008b052  push    rbx
0x18008b053  push    rsi
0x18008b054  push    rdi
0x18008b055  push    r14
0x18008b057  push    r15
0x18008b059  mov     rbp, rsp
0x18008b05c  sub     rsp, 78h
0x18008b060  mov     rsi, r9
0x18008b063  lea     rdx, aReadbinaryfrom; "ReadBinaryFromRegistry"
0x18008b06a  mov     r14, r8
0x18008b06d  mov     r15, rcx
0x18008b070  mov     r9d, 2; unsigned __int16
0x18008b076  lea     rcx, [rbp+var_48]; this
0x18008b07a  mov     r8d, 14Ch; unsigned __int16
0x18008b080  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008b085  mov     dword ptr [rbp+Type], 0
0x18008b08c  mov     [rbp+cbData], 0
0x18008b093  test    r14, r14
0x18008b096  jz      short loc_18008B09F
0x18008b098  mov     qword ptr [r14], 0
0x18008b09f  test    rsi, rsi
0x18008b0a2  jz      short loc_18008B0AA
0x18008b0a4  mov     dword ptr [rsi], 0
0x18008b0aa  mov     eax, 156h
0x18008b0af  mov     [rbp+var_44], ax
0x18008b0b3  mov     eax, 157h
0x18008b0b8  test    r14, r14
0x18008b0bb  jnz     short loc_18008B0CB
0x18008b0bd  mov     ebx, 80070057h
0x18008b0c2  mov     [rbp+var_42], ax
0x18008b0c6  jmp     loc_18008B213
0x18008b0cb  mov     [rbp+var_44], ax
0x18008b0cf  mov     eax, 158h
0x18008b0d4  test    rsi, rsi
0x18008b0d7  jz      short loc_18008B0BD
0x18008b0d9  mov     [rbp+var_44], ax
0x18008b0dd  lea     r9, [rbp+Type]; lpType
0x18008b0e1  lea     rax, [rbp+cbData]
0x18008b0e5  mov     [rbp+var_48], 0
0x18008b0ec  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18008b0f1  lea     rdx, ValueName; "Sid"
0x18008b0f8  xor     r8d, r8d; lpReserved
0x18008b0fb  mov     [rsp+78h+lpData], 0; lpData
0x18008b104  mov     rcx, r15; hKey
0x18008b107  call    cs:__imp_RegQueryValueExW
0x18008b10e  nop     dword ptr [rax+rax+00h]
0x18008b113  mov     ebx, eax
0x18008b115  cmp     eax, 2
0x18008b118  jnz     short loc_18008B127
0x18008b11a  lea     ebx, [rax-1]
0x18008b11d  mov     eax, 15Dh
0x18008b122  jmp     loc_18008B20F
0x18008b127  test    eax, eax
0x18008b129  jle     short loc_18008B134
0x18008b12b  movzx   ebx, ax
0x18008b12e  or      ebx, 80070000h
0x18008b134  mov     [rbp+var_48], ebx
0x18008b137  mov     eax, 160h
0x18008b13c  test    ebx, ebx
0x18008b13e  jns     short loc_18008B150
0x18008b140  mov     [rbp+var_42], ax
0x18008b144  mov     [rbp+var_40], 1
0x18008b14b  jmp     loc_18008B216
0x18008b150  mov     ecx, [rbp+cbData]; cb
0x18008b153  mov     [rbp+var_44], ax
0x18008b157  call    cs:__imp_CoTaskMemAlloc
0x18008b15e  nop     dword ptr [rax+rax+00h]
0x18008b163  mov     rdi, rax
0x18008b166  test    rax, rax
0x18008b169  mov     eax, 163h
0x18008b16e  jnz     short loc_18008B17A
0x18008b170  mov     ebx, 8007000Eh
0x18008b175  jmp     loc_18008B0C2
0x18008b17a  mov     r8d, [rbp+cbData]; Size
0x18008b17e  xor     edx, edx; Val
0x18008b180  mov     rcx, rdi; void *
0x18008b183  mov     [rbp+var_48], 0
0x18008b18a  mov     [rbp+var_44], ax
0x18008b18e  call    memset_0
0x18008b193  lea     rax, [rbp+cbData]
0x18008b197  xor     r8d, r8d; lpReserved
0x18008b19a  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18008b19f  lea     r9, [rbp+Type]; lpType
0x18008b1a3  lea     rdx, ValueName; "Sid"
0x18008b1aa  mov     [rsp+78h+lpData], rdi; lpData
0x18008b1af  mov     rcx, r15; hKey
0x18008b1b2  call    cs:__imp_RegQueryValueExW
0x18008b1b9  nop     dword ptr [rax+rax+00h]
0x18008b1be  test    eax, eax
0x18008b1c0  jle     short loc_18008B1CA
0x18008b1c2  movzx   eax, ax
0x18008b1c5  or      eax, 80070000h
0x18008b1ca  mov     [rbp+var_48], eax
0x18008b1cd  test    eax, eax
0x18008b1cf  mov     eax, 167h
0x18008b1d4  js      short loc_18008B1ED
0x18008b1d6  cmp     dword ptr [rbp+Type], 3
0x18008b1da  mov     [rbp+var_44], ax
0x18008b1de  mov     eax, 168h
0x18008b1e3  jz      short loc_18008B205
0x18008b1e5  mov     ebx, 80070057h
0x18008b1ea  mov     [rbp+var_48], ebx
0x18008b1ed  mov     rcx, rdi; pv
0x18008b1f0  mov     [rbp+var_42], ax
0x18008b1f4  call    cs:__imp_CoTaskMemFree
0x18008b1fb  nop     dword ptr [rax+rax+00h]
0x18008b200  mov     ebx, [rbp+var_48]
0x18008b203  jmp     short loc_18008B216
0x18008b205  mov     ecx, [rbp+cbData]
0x18008b208  xor     ebx, ebx
0x18008b20a  mov     [r14], rdi
0x18008b20d  mov     [rsi], ecx
0x18008b20f  mov     [rbp+var_44], ax
0x18008b213  mov     [rbp+var_48], ebx
0x18008b216  lea     rcx, [rbp+var_48]; this
0x18008b21a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008b21f  mov     eax, ebx
0x18008b221  add     rsp, 78h
0x18008b225  pop     r15
0x18008b227  pop     r14
0x18008b229  pop     rdi
0x18008b22a  pop     rsi
0x18008b22b  pop     rbx
0x18008b22c  pop     rbp
0x18008b22d  retn
```
