# SxRegReadMultiStringAsBlob(HKEY__ *,ushort const *,uchar * *,ulong *)

- ea: `0x18002e540`
- end: `0x18002e6d7`
- name: `?SxRegReadMultiStringAsBlob@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z`
- size: `407`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e410`

## callees

- `0x18000f8ac`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002e540`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e5df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e5e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e5e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e629`

## string_xrefs

- `0x18002e56b`: `SxRegReadMultiStringAsBlob`

## pseudocode

```c
__int64 __fastcall SxRegReadMultiStringAsBlob(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **a3, unsigned int *a4)
{
  void *lpData; // rbx
  DWORD v9; // ecx
  __int16 v10; // ax
  DWORD v11; // r14d
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  int i; // [rsp+30h] [rbp-40h] BYREF
  __int16 v18; // [rsp+34h] [rbp-3Ch]
  __int16 v19; // [rsp+36h] [rbp-3Ah]
  int v20; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&i, "SxRegReadMultiStringAsBlob", 339, 2);
  lpData = 0;
  Type = 0;
  v9 = 64;
  cbData = 64;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = 350;
  if ( lpValueName && (v18 = 350, v10 = 351, a3) && (v18 = 351, v10 = 352, a4) )
  {
    for ( i = 0; ; i = 0 )
    {
      v18 = v10;
      v11 = SxScaledGrowth(v9);
      CoTaskMemFree(lpData);
      lpData = CoTaskMemAlloc(v11);
      v10 = 359;
      if ( !lpData )
      {
        i = -2147024882;
        goto LABEL_21;
      }
      v18 = 359;
      i = 0;
      cbData = v11;
      v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)lpData, &cbData);
      if ( !v12 )
        break;
      if ( v12 != 234 )
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        i = v12;
        v10 = 367;
        v20 = 1;
        goto LABEL_21;
      }
      v9 = cbData;
      v10 = 367;
    }
    v10 = 373;
    if ( Type == 7 )
    {
      *a3 = (unsigned __int8 *)lpData;
      lpData = 0;
      v18 = 373;
      *a4 = cbData;
      i = 0;
      goto LABEL_22;
    }
    i = -2147418113;
  }
  else
  {
    i = -2147024809;
  }
LABEL_21:
  v19 = v10;
LABEL_22:
  CoTaskMemFree(lpData);
  v13 = i;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&i, v14, v15);
  return v13;
}

```

## disassembly

```asm
0x18002e540  mov     [rsp-28h+arg_0], rbx
0x18002e545  mov     [rsp-28h+arg_18], rsi
0x18002e54a  push    rbp
0x18002e54b  push    rdi
0x18002e54c  push    r12
0x18002e54e  push    r14
0x18002e550  push    r15
0x18002e552  mov     rbp, rsp
0x18002e555  sub     rsp, 70h
0x18002e559  mov     rdi, r9
0x18002e55c  mov     rsi, r8
0x18002e55f  mov     r15, rdx
0x18002e562  mov     r12, rcx
0x18002e565  mov     r9d, 2; unsigned __int16
0x18002e56b  lea     rdx, aSxregreadmulti_0; "SxRegReadMultiStringAsBlob"
0x18002e572  mov     r8d, 153h; unsigned __int16
0x18002e578  lea     rcx, [rbp+var_40]; this
0x18002e57c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002e581  xor     ebx, ebx
0x18002e583  mov     [rbp+Type], ebx
0x18002e586  lea     ecx, [rbx+40h]; unsigned int
0x18002e589  mov     [rbp+cbData], ecx
0x18002e58c  test    rsi, rsi
0x18002e58f  jz      short loc_18002E594
0x18002e591  mov     [rsi], rbx
0x18002e594  test    rdi, rdi
0x18002e597  jz      short loc_18002E59B
0x18002e599  mov     [rdi], ebx
0x18002e59b  mov     eax, 15Eh
0x18002e5a0  test    r15, r15
0x18002e5a3  jz      loc_18002E69C
0x18002e5a9  mov     [rbp+var_3C], ax
0x18002e5ad  mov     eax, 15Fh
0x18002e5b2  test    rsi, rsi
0x18002e5b5  jz      loc_18002E69C
0x18002e5bb  mov     [rbp+var_3C], ax
0x18002e5bf  mov     eax, 160h
0x18002e5c4  test    rdi, rdi
0x18002e5c7  jz      loc_18002E69C
0x18002e5cd  mov     [rbp+var_40], ebx
0x18002e5d0  mov     [rbp+var_3C], ax
0x18002e5d4  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x18002e5d9  mov     rcx, rbx; pv
0x18002e5dc  mov     r14d, eax
0x18002e5df  call    cs:__imp_CoTaskMemFree
0x18002e5e5  mov     ecx, r14d; cb
0x18002e5e8  call    cs:__imp_CoTaskMemAlloc
0x18002e5ee  mov     rbx, rax
0x18002e5f1  test    rax, rax
0x18002e5f4  mov     eax, 167h
0x18002e5f9  jz      loc_18002E693
0x18002e5ff  mov     [rbp+var_3C], ax
0x18002e603  lea     r9, [rbp+Type]; lpType
0x18002e607  lea     rax, [rbp+cbData]
0x18002e60b  mov     [rbp+var_40], 0
0x18002e612  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18002e617  xor     r8d, r8d; lpReserved
0x18002e61a  mov     rdx, r15; lpValueName
0x18002e61d  mov     [rsp+70h+lpData], rbx; lpData
0x18002e622  mov     rcx, r12; hKey
0x18002e625  mov     [rbp+cbData], r14d
0x18002e629  call    cs:__imp_RegQueryValueExW
0x18002e62f  test    eax, eax
0x18002e631  jz      short loc_18002E668
0x18002e633  cmp     eax, 0EAh
0x18002e638  jnz     short loc_18002E64B
0x18002e63a  mov     ecx, [rbp+cbData]
0x18002e63d  mov     eax, 16Fh
0x18002e642  mov     [rbp+var_40], 0
0x18002e649  jmp     short loc_18002E5D0
0x18002e64b  test    eax, eax
0x18002e64d  jle     short loc_18002E657
0x18002e64f  movzx   eax, ax
0x18002e652  or      eax, 80070000h
0x18002e657  mov     [rbp+var_40], eax
0x18002e65a  mov     eax, 16Fh
0x18002e65f  mov     [rbp+var_38], 1
0x18002e666  jmp     short loc_18002E6A3
0x18002e668  cmp     [rbp+Type], 7
0x18002e66c  mov     eax, 175h
0x18002e671  jnz     short loc_18002E68A
0x18002e673  mov     [rsi], rbx
0x18002e676  xor     ebx, ebx
0x18002e678  mov     [rbp+var_3C], ax
0x18002e67c  mov     eax, [rbp+cbData]
0x18002e67f  mov     [rdi], eax
0x18002e681  mov     [rbp+var_40], 0
0x18002e688  jmp     short loc_18002E6A7
0x18002e68a  mov     [rbp+var_40], 8000FFFFh
0x18002e691  jmp     short loc_18002E6A3
0x18002e693  mov     [rbp+var_40], 8007000Eh
0x18002e69a  jmp     short loc_18002E6A3
0x18002e69c  mov     [rbp+var_40], 80070057h
0x18002e6a3  mov     [rbp+var_3A], ax
0x18002e6a7  mov     rcx, rbx; pv
0x18002e6aa  call    cs:__imp_CoTaskMemFree
0x18002e6b0  mov     ebx, [rbp+var_40]
0x18002e6b3  lea     rcx, [rbp+var_40]; this
0x18002e6b7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002e6bc  lea     r11, [rsp+70h+var_s0]
0x18002e6c1  mov     eax, ebx
0x18002e6c3  mov     rbx, [r11+30h]
0x18002e6c7  mov     rsi, [r11+48h]
0x18002e6cb  mov     rsp, r11
0x18002e6ce  pop     r15
0x18002e6d0  pop     r14
0x18002e6d2  pop     r12
0x18002e6d4  pop     rdi
0x18002e6d5  pop     rbp
0x18002e6d6  retn
```
