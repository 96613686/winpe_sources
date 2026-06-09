# SxRegReadMultiStringAsBlob(HKEY__ *,ushort const *,uchar * *,ulong *)

- ea: `0x180098d00`
- end: `0x180098eb3`
- name: `?SxRegReadMultiStringAsBlob@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z`
- size: `435`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180098bc8`

## callees

- `0x18004d38c`
- `0x180072e08`
- `0x180072f14`
- `0x180098d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180098df5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180098df5`
- `ole32!CoTaskMemFree` at `0x180098d9f`
- `ole32!CoTaskMemFree` at `0x180098e7f`
- `ole32!CoTaskMemFree` at `0x180098d9f`
- `ole32!CoTaskMemFree` at `0x180098e7f`
- `ole32!CoTaskMemAlloc` at `0x180098dae`
- `ole32!CoTaskMemAlloc` at `0x180098dae`

## string_xrefs

- `0x180098d2b`: `SxRegReadMultiStringAsBlob`

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
  int i; // [rsp+30h] [rbp-40h] BYREF
  __int16 v16; // [rsp+34h] [rbp-3Ch]
  __int16 v17; // [rsp+36h] [rbp-3Ah]
  int v18; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+A8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+B0h] [rbp+40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&i, "SxRegReadMultiStringAsBlob", 0x153u, 2u);
  lpData = 0;
  Type = 0;
  v9 = 64;
  cbData = 64;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = 350;
  if ( lpValueName && (v16 = 350, v10 = 351, a3) && (v16 = 351, v10 = 352, a4) )
  {
    for ( i = 0; ; i = 0 )
    {
      v16 = v10;
      v11 = SxScaledGrowth(v9);
      CoTaskMemFree(lpData);
      lpData = CoTaskMemAlloc(v11);
      v10 = 359;
      if ( !lpData )
      {
        i = -2147024882;
        goto LABEL_21;
      }
      v16 = 359;
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
        v18 = 1;
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
      v16 = 373;
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
  v17 = v10;
LABEL_22:
  CoTaskMemFree(lpData);
  v13 = i;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&i);
  return v13;
}

```

## disassembly

```asm
0x180098d00  mov     [rsp-28h+arg_0], rbx
0x180098d05  mov     [rsp-28h+arg_18], rsi
0x180098d0a  push    rbp
0x180098d0b  push    rdi
0x180098d0c  push    r12
0x180098d0e  push    r14
0x180098d10  push    r15
0x180098d12  mov     rbp, rsp
0x180098d15  sub     rsp, 70h
0x180098d19  mov     rdi, r9
0x180098d1c  mov     rsi, r8
0x180098d1f  mov     r15, rdx
0x180098d22  mov     r12, rcx
0x180098d25  mov     r9d, 2; unsigned __int16
0x180098d2b  lea     rdx, aSxregreadmulti_0; "SxRegReadMultiStringAsBlob"
0x180098d32  mov     r8d, 153h; unsigned __int16
0x180098d38  lea     rcx, [rbp+var_40]; this
0x180098d3c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180098d41  xor     ebx, ebx
0x180098d43  mov     [rbp+Type], ebx
0x180098d46  lea     ecx, [rbx+40h]; unsigned int
0x180098d49  mov     [rbp+cbData], ecx
0x180098d4c  test    rsi, rsi
0x180098d4f  jz      short loc_180098D54
0x180098d51  mov     [rsi], rbx
0x180098d54  test    rdi, rdi
0x180098d57  jz      short loc_180098D5B
0x180098d59  mov     [rdi], ebx
0x180098d5b  mov     eax, 15Eh
0x180098d60  test    r15, r15
0x180098d63  jz      loc_180098E71
0x180098d69  mov     [rbp+var_3C], ax
0x180098d6d  mov     eax, 15Fh
0x180098d72  test    rsi, rsi
0x180098d75  jz      loc_180098E71
0x180098d7b  mov     [rbp+var_3C], ax
0x180098d7f  mov     eax, 160h
0x180098d84  test    rdi, rdi
0x180098d87  jz      loc_180098E71
0x180098d8d  mov     [rbp+var_40], ebx
0x180098d90  mov     [rbp+var_3C], ax
0x180098d94  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180098d99  mov     rcx, rbx; pv
0x180098d9c  mov     r14d, eax
0x180098d9f  call    cs:__imp_CoTaskMemFree
0x180098da6  nop     dword ptr [rax+rax+00h]
0x180098dab  mov     ecx, r14d; cb
0x180098dae  call    cs:__imp_CoTaskMemAlloc
0x180098db5  nop     dword ptr [rax+rax+00h]
0x180098dba  mov     rbx, rax
0x180098dbd  test    rax, rax
0x180098dc0  mov     eax, 167h
0x180098dc5  jz      loc_180098E68
0x180098dcb  mov     [rbp+var_3C], ax
0x180098dcf  lea     r9, [rbp+Type]; lpType
0x180098dd3  lea     rax, [rbp+cbData]
0x180098dd7  mov     [rbp+var_40], 0
0x180098dde  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180098de3  xor     r8d, r8d; lpReserved
0x180098de6  mov     rdx, r15; lpValueName
0x180098de9  mov     [rsp+70h+lpData], rbx; lpData
0x180098dee  mov     rcx, r12; hKey
0x180098df1  mov     [rbp+cbData], r14d
0x180098df5  call    cs:__imp_RegQueryValueExW
0x180098dfc  nop     dword ptr [rax+rax+00h]
0x180098e01  test    eax, eax
0x180098e03  jz      short loc_180098E3D
0x180098e05  cmp     eax, 0EAh
0x180098e0a  jnz     short loc_180098E20
0x180098e0c  mov     ecx, [rbp+cbData]
0x180098e0f  mov     eax, 16Fh
0x180098e14  mov     [rbp+var_40], 0
0x180098e1b  jmp     loc_180098D90
0x180098e20  test    eax, eax
0x180098e22  jle     short loc_180098E2C
0x180098e24  movzx   eax, ax
0x180098e27  or      eax, 80070000h
0x180098e2c  mov     [rbp+var_40], eax
0x180098e2f  mov     eax, 16Fh
0x180098e34  mov     [rbp+var_38], 1
0x180098e3b  jmp     short loc_180098E78
0x180098e3d  cmp     [rbp+Type], 7
0x180098e41  mov     eax, 175h
0x180098e46  jnz     short loc_180098E5F
0x180098e48  mov     [rsi], rbx
0x180098e4b  xor     ebx, ebx
0x180098e4d  mov     [rbp+var_3C], ax
0x180098e51  mov     eax, [rbp+cbData]
0x180098e54  mov     [rdi], eax
0x180098e56  mov     [rbp+var_40], 0
0x180098e5d  jmp     short loc_180098E7C
0x180098e5f  mov     [rbp+var_40], 8000FFFFh
0x180098e66  jmp     short loc_180098E78
0x180098e68  mov     [rbp+var_40], 8007000Eh
0x180098e6f  jmp     short loc_180098E78
0x180098e71  mov     [rbp+var_40], 80070057h
0x180098e78  mov     [rbp+var_3A], ax
0x180098e7c  mov     rcx, rbx; pv
0x180098e7f  call    cs:__imp_CoTaskMemFree
0x180098e86  nop     dword ptr [rax+rax+00h]
0x180098e8b  mov     ebx, [rbp+var_40]
0x180098e8e  lea     rcx, [rbp+var_40]; this
0x180098e92  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180098e97  lea     r11, [rsp+70h+var_s0]
0x180098e9c  mov     eax, ebx
0x180098e9e  mov     rbx, [r11+30h]
0x180098ea2  mov     rsi, [r11+48h]
0x180098ea6  mov     rsp, r11
0x180098ea9  pop     r15
0x180098eab  pop     r14
0x180098ead  pop     r12
0x180098eaf  pop     rdi
0x180098eb0  pop     rbp
0x180098eb1  retn
```
