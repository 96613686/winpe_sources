# GetPresentableVolumeName

- ea: `0x18000cd1c`
- end: `0x18000cf06`
- name: `GetPresentableVolumeName`
- size: `490`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b8c8`

## callees

- `0x1800081d8`
- `0x180009ac8`
- `0x18000cd1c`
- `0x18006fe84`
- `0x18006ff8c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cde0`
- `KERNEL32!GetLastError` at `0x18000cde0`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18000cdd6`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18000cdd6`
- `ole32!CoTaskMemFree` at `0x18000ced9`
- `ole32!CoTaskMemFree` at `0x18000ced9`
- `ole32!CoTaskMemRealloc` at `0x18000cdad`
- `ole32!CoTaskMemRealloc` at `0x18000cdad`

## pseudocode

```c
__int64 __fastcall GetPresentableVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2, DWORD a3)
{
  WCHAR *v5; // rbx
  __int16 v6; // ax
  DWORD v7; // eax
  WCHAR *v8; // rax
  signed int LastError; // eax
  WCHAR *v10; // r8
  const unsigned __int16 *v11; // rsi
  unsigned int v12; // r9d
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rax
  unsigned int v15; // ebx
  int v17; // [rsp+20h] [rbp-40h] BYREF
  __int16 v18; // [rsp+24h] [rbp-3Ch]
  __int16 v19; // [rsp+26h] [rbp-3Ah]
  DWORD cchBufferLength; // [rsp+A0h] [rbp+40h] BYREF

  cchBufferLength = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "GetPresentableVolumeName", 2163, 1);
  v5 = 0;
  cchBufferLength = 0;
  v6 = 2174;
  if ( !lpszVolumeName )
    goto LABEL_31;
  v18 = 2174;
  if ( !a2 )
  {
    v6 = 2175;
LABEL_31:
    v17 = -2147024809;
    goto LABEL_32;
  }
  v17 = 0;
  v18 = 2176;
  *a2 = 0;
  v7 = 261;
  for ( cchBufferLength = 261; ; v7 = cchBufferLength )
  {
    v8 = (WCHAR *)CoTaskMemRealloc(v5, 2LL * v7);
    v5 = v8;
    if ( !v8 )
    {
      v17 = -2147024882;
      v19 = 2187;
      goto LABEL_33;
    }
    v17 = 0;
    v18 = 2187;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v8, cchBufferLength, &cchBufferLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v17 = LastError;
    if ( LastError < 0 )
    {
      v19 = 2197;
      goto LABEL_33;
    }
    v18 = 2197;
  }
  v10 = v5;
  v11 = v5;
  v12 = -1;
  while ( *v10 )
  {
    if ( v10 >= &v5[cchBufferLength] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids);
      break;
    }
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    v14 = v10;
    if ( (unsigned int)v13 >= v12 )
      v14 = v11;
    v11 = v14;
    v10 += (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= v12 )
      LODWORD(v13) = v12;
    v12 = v13;
  }
  v17 = StringCchCopyW(a2, 0x104u, v11);
  v6 = 2229;
  if ( v17 >= 0 )
  {
    v18 = 2229;
    goto LABEL_33;
  }
LABEL_32:
  v19 = v6;
LABEL_33:
  CoTaskMemFree(v5);
  v15 = v17;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v15;
}

```

## disassembly

```asm
0x18000cd1c  mov     [rsp-28h+arg_0], rbx
0x18000cd21  mov     [rsp-28h+arg_8], rsi
0x18000cd26  mov     [rsp-28h+cchBufferLength], r8d
0x18000cd2b  push    rbp
0x18000cd2c  push    rdi
0x18000cd2d  push    r12
0x18000cd2f  push    r14
0x18000cd31  push    r15
0x18000cd33  mov     rbp, rsp
0x18000cd36  sub     rsp, 60h
0x18000cd3a  mov     rdi, rdx
0x18000cd3d  mov     rsi, rcx
0x18000cd40  mov     r9d, 1; unsigned __int16
0x18000cd46  mov     r8d, 873h; unsigned __int16
0x18000cd4c  lea     rdx, aGetpresentable; "GetPresentableVolumeName"
0x18000cd53  lea     rcx, [rbp+var_40]; this
0x18000cd57  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000cd5c  xor     r14d, r14d
0x18000cd5f  mov     ebx, r14d
0x18000cd62  mov     [rbp+cchBufferLength], r14d
0x18000cd66  mov     eax, 87Eh
0x18000cd6b  test    rsi, rsi
0x18000cd6e  jz      loc_18000CECB
0x18000cd74  mov     [rbp+var_3C], ax
0x18000cd78  test    rdi, rdi
0x18000cd7b  jz      loc_18000CEC6
0x18000cd81  mov     [rbp+var_40], r14d
0x18000cd85  mov     eax, 880h
0x18000cd8a  mov     [rbp+var_3C], ax
0x18000cd8e  mov     [rdi], r14w
0x18000cd92  mov     eax, 105h
0x18000cd97  mov     [rbp+cchBufferLength], eax
0x18000cd9a  mov     r12d, 88Bh
0x18000cda0  lea     r15d, [r12+0Ah]
0x18000cda5  mov     edx, eax
0x18000cda7  add     rdx, rdx; cb
0x18000cdaa  mov     rcx, rbx; pv
0x18000cdad  call    cs:__imp_CoTaskMemRealloc
0x18000cdb3  mov     rbx, rax
0x18000cdb6  test    rax, rax
0x18000cdb9  jz      loc_18000CEB8
0x18000cdbf  mov     [rbp+var_40], r14d
0x18000cdc3  mov     [rbp+var_3C], r12w
0x18000cdc8  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x18000cdcc  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x18000cdd0  mov     rdx, rax; lpszVolumePathNames
0x18000cdd3  mov     rcx, rsi; lpszVolumeName
0x18000cdd6  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000cddc  test    eax, eax
0x18000cdde  jnz     short loc_18000CE1E
0x18000cde0  call    cs:__imp_GetLastError
0x18000cde6  cmp     eax, 7Ah ; 'z'
0x18000cde9  jz      short loc_18000CE00
0x18000cdeb  cmp     eax, 0EAh
0x18000cdf0  jz      short loc_18000CE00
0x18000cdf2  test    eax, eax
0x18000cdf4  jle     short loc_18000CE03
0x18000cdf6  movzx   eax, ax
0x18000cdf9  or      eax, 80070000h
0x18000cdfe  jmp     short loc_18000CE03
0x18000ce00  mov     eax, r14d
0x18000ce03  mov     [rbp+var_40], eax
0x18000ce06  test    eax, eax
0x18000ce08  js      short loc_18000CE14
0x18000ce0a  mov     [rbp+var_3C], r15w
0x18000ce0f  mov     eax, [rbp+cchBufferLength]
0x18000ce12  jmp     short loc_18000CDA5
0x18000ce14  mov     [rbp+var_3A], r15w
0x18000ce19  jmp     loc_18000CED6
0x18000ce1e  mov     r8, rbx
0x18000ce21  mov     rsi, rbx
0x18000ce24  or      r9d, 0FFFFFFFFh
0x18000ce28  cmp     [r8], r14w
0x18000ce2c  jz      short loc_18000CE96
0x18000ce2e  mov     eax, [rbp+cchBufferLength]
0x18000ce31  lea     rcx, [rbx+rax*2]
0x18000ce35  cmp     r8, rcx
0x18000ce38  jnb     short loc_18000CE65
0x18000ce3a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ce3e  inc     rdx
0x18000ce41  cmp     [r8+rdx*2], r14w
0x18000ce46  jnz     short loc_18000CE3E
0x18000ce48  mov     rax, r8
0x18000ce4b  cmp     edx, r9d
0x18000ce4e  cmovnb  rax, rsi
0x18000ce52  mov     rsi, rax
0x18000ce55  lea     eax, [rdx+1]
0x18000ce58  lea     r8, [r8+rax*2]
0x18000ce5c  cmovnb  edx, r9d
0x18000ce60  mov     r9d, edx
0x18000ce63  jmp     short loc_18000CE28
0x18000ce65  lea     rax, WPP_GLOBAL_Control
0x18000ce6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce73  cmp     rcx, rax
0x18000ce76  jz      short loc_18000CE96
0x18000ce78  test    dword ptr [rcx+1Ch], 4000000h
0x18000ce7f  jz      short loc_18000CE96
0x18000ce81  mov     edx, 17h
0x18000ce86  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000ce8d  mov     rcx, [rcx+10h]
0x18000ce91  call    WPP_SF_
0x18000ce96  mov     r8, rsi; unsigned __int16 *
0x18000ce99  mov     edx, 104h; unsigned __int64
0x18000ce9e  mov     rcx, rdi; unsigned __int16 *
0x18000cea1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cea6  mov     [rbp+var_40], eax
0x18000cea9  test    eax, eax
0x18000ceab  mov     eax, 8B5h
0x18000ceb0  js      short loc_18000CED2
0x18000ceb2  mov     [rbp+var_3C], ax
0x18000ceb6  jmp     short loc_18000CED6
0x18000ceb8  mov     [rbp+var_40], 8007000Eh
0x18000cebf  mov     [rbp+var_3A], r12w
0x18000cec4  jmp     short loc_18000CED6
0x18000cec6  mov     eax, 87Fh
0x18000cecb  mov     [rbp+var_40], 80070057h
0x18000ced2  mov     [rbp+var_3A], ax
0x18000ced6  mov     rcx, rbx; pv
0x18000ced9  call    cs:__imp_CoTaskMemFree
0x18000cedf  mov     ebx, [rbp+var_40]
0x18000cee2  lea     rcx, [rbp+var_40]; this
0x18000cee6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ceeb  mov     eax, ebx
0x18000ceed  lea     r11, [rsp+60h+var_s0]
0x18000cef2  mov     rbx, [r11+30h]
0x18000cef6  mov     rsi, [r11+38h]
0x18000cefa  mov     rsp, r11
0x18000cefd  pop     r15
0x18000ceff  pop     r14
0x18000cf01  pop     r12
0x18000cf03  pop     rdi
0x18000cf04  pop     rbp
0x18000cf05  retn
```
