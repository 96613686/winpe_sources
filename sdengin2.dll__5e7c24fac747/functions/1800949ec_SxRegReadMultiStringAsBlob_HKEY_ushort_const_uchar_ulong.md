# SxRegReadMultiStringAsBlob(HKEY__ *,ushort const *,uchar * *,ulong *)

- ea: `0x1800949ec`
- end: `0x180094b83`
- name: `?SxRegReadMultiStringAsBlob@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z`
- size: `407`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800948bc`

## callees

- `0x18004b6dc`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800949ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094ad5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180094ad5`
- `ole32!CoTaskMemFree` at `0x180094a8b`
- `ole32!CoTaskMemFree` at `0x180094b56`
- `ole32!CoTaskMemFree` at `0x180094a8b`
- `ole32!CoTaskMemFree` at `0x180094b56`
- `ole32!CoTaskMemAlloc` at `0x180094a94`
- `ole32!CoTaskMemAlloc` at `0x180094a94`

## string_xrefs

- `0x180094a17`: `SxRegReadMultiStringAsBlob`

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
0x1800949ec  mov     [rsp-28h+arg_0], rbx
0x1800949f1  mov     [rsp-28h+arg_18], rsi
0x1800949f6  push    rbp
0x1800949f7  push    rdi
0x1800949f8  push    r12
0x1800949fa  push    r14
0x1800949fc  push    r15
0x1800949fe  mov     rbp, rsp
0x180094a01  sub     rsp, 70h
0x180094a05  mov     rdi, r9
0x180094a08  mov     rsi, r8
0x180094a0b  mov     r15, rdx
0x180094a0e  mov     r12, rcx
0x180094a11  mov     r9d, 2; unsigned __int16
0x180094a17  lea     rdx, aSxregreadmulti_0; "SxRegReadMultiStringAsBlob"
0x180094a1e  mov     r8d, 153h; unsigned __int16
0x180094a24  lea     rcx, [rbp+var_40]; this
0x180094a28  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180094a2d  xor     ebx, ebx
0x180094a2f  mov     [rbp+Type], ebx
0x180094a32  lea     ecx, [rbx+40h]; unsigned int
0x180094a35  mov     [rbp+cbData], ecx
0x180094a38  test    rsi, rsi
0x180094a3b  jz      short loc_180094A40
0x180094a3d  mov     [rsi], rbx
0x180094a40  test    rdi, rdi
0x180094a43  jz      short loc_180094A47
0x180094a45  mov     [rdi], ebx
0x180094a47  mov     eax, 15Eh
0x180094a4c  test    r15, r15
0x180094a4f  jz      loc_180094B48
0x180094a55  mov     [rbp+var_3C], ax
0x180094a59  mov     eax, 15Fh
0x180094a5e  test    rsi, rsi
0x180094a61  jz      loc_180094B48
0x180094a67  mov     [rbp+var_3C], ax
0x180094a6b  mov     eax, 160h
0x180094a70  test    rdi, rdi
0x180094a73  jz      loc_180094B48
0x180094a79  mov     [rbp+var_40], ebx
0x180094a7c  mov     [rbp+var_3C], ax
0x180094a80  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180094a85  mov     rcx, rbx; pv
0x180094a88  mov     r14d, eax
0x180094a8b  call    cs:__imp_CoTaskMemFree
0x180094a91  mov     ecx, r14d; cb
0x180094a94  call    cs:__imp_CoTaskMemAlloc
0x180094a9a  mov     rbx, rax
0x180094a9d  test    rax, rax
0x180094aa0  mov     eax, 167h
0x180094aa5  jz      loc_180094B3F
0x180094aab  mov     [rbp+var_3C], ax
0x180094aaf  lea     r9, [rbp+Type]; lpType
0x180094ab3  lea     rax, [rbp+cbData]
0x180094ab7  mov     [rbp+var_40], 0
0x180094abe  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180094ac3  xor     r8d, r8d; lpReserved
0x180094ac6  mov     rdx, r15; lpValueName
0x180094ac9  mov     [rsp+70h+lpData], rbx; lpData
0x180094ace  mov     rcx, r12; hKey
0x180094ad1  mov     [rbp+cbData], r14d
0x180094ad5  call    cs:__imp_RegQueryValueExW
0x180094adb  test    eax, eax
0x180094add  jz      short loc_180094B14
0x180094adf  cmp     eax, 0EAh
0x180094ae4  jnz     short loc_180094AF7
0x180094ae6  mov     ecx, [rbp+cbData]
0x180094ae9  mov     eax, 16Fh
0x180094aee  mov     [rbp+var_40], 0
0x180094af5  jmp     short loc_180094A7C
0x180094af7  test    eax, eax
0x180094af9  jle     short loc_180094B03
0x180094afb  movzx   eax, ax
0x180094afe  or      eax, 80070000h
0x180094b03  mov     [rbp+var_40], eax
0x180094b06  mov     eax, 16Fh
0x180094b0b  mov     [rbp+var_38], 1
0x180094b12  jmp     short loc_180094B4F
0x180094b14  cmp     [rbp+Type], 7
0x180094b18  mov     eax, 175h
0x180094b1d  jnz     short loc_180094B36
0x180094b1f  mov     [rsi], rbx
0x180094b22  xor     ebx, ebx
0x180094b24  mov     [rbp+var_3C], ax
0x180094b28  mov     eax, [rbp+cbData]
0x180094b2b  mov     [rdi], eax
0x180094b2d  mov     [rbp+var_40], 0
0x180094b34  jmp     short loc_180094B53
0x180094b36  mov     [rbp+var_40], 8000FFFFh
0x180094b3d  jmp     short loc_180094B4F
0x180094b3f  mov     [rbp+var_40], 8007000Eh
0x180094b46  jmp     short loc_180094B4F
0x180094b48  mov     [rbp+var_40], 80070057h
0x180094b4f  mov     [rbp+var_3A], ax
0x180094b53  mov     rcx, rbx; pv
0x180094b56  call    cs:__imp_CoTaskMemFree
0x180094b5c  mov     ebx, [rbp+var_40]
0x180094b5f  lea     rcx, [rbp+var_40]; this
0x180094b63  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180094b68  lea     r11, [rsp+70h+var_s0]
0x180094b6d  mov     eax, ebx
0x180094b6f  mov     rbx, [r11+30h]
0x180094b73  mov     rsi, [r11+48h]
0x180094b77  mov     rsp, r11
0x180094b7a  pop     r15
0x180094b7c  pop     r14
0x180094b7e  pop     r12
0x180094b80  pop     rdi
0x180094b81  pop     rbp
0x180094b82  retn
```
