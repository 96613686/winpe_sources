# ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x18008b238`
- end: `0x18008b482`
- name: `?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `586`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18008b488`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008b238`
- `0x1800927e8`
- `0x1800cf56a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b2f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b386`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b2f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008b386`
- `ole32!CoTaskMemFree` at `0x18008b429`
- `ole32!CoTaskMemFree` at `0x18008b44f`
- `ole32!CoTaskMemFree` at `0x18008b429`
- `ole32!CoTaskMemFree` at `0x18008b44f`
- `ole32!CoTaskMemAlloc` at `0x18008b332`
- `ole32!CoTaskMemAlloc` at `0x18008b332`

## string_xrefs

- `0x18008b261`: `ReadBinaryFromRegistryEncrypted`

## pseudocode

```c
__int64 __fastcall ReadBinaryFromRegistryEncrypted(
        HKEY hKey,
        LPCWSTR lpValueName,
        unsigned __int8 **a3,
        unsigned int *a4,
        DWORD cbData)
{
  __int16 v9; // ax
  signed int v10; // ebx
  LSTATUS v11; // eax
  void *lpData; // rdi
  int v13; // eax
  bool v14; // sf
  __int16 v15; // ax
  int v16; // eax
  __int64 v17; // rdx
  unsigned __int8 *v18; // rcx
  unsigned __int8 *i; // rax
  __int64 v20; // rax
  _BYTE *v21; // rcx
  int v23; // [rsp+30h] [rbp-40h] BYREF
  __int16 v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+36h] [rbp-3Ah]
  int v26; // [rsp+38h] [rbp-38h]
  DWORD Type; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int8 *v29; // [rsp+C8h] [rbp+58h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "ReadBinaryFromRegistryEncrypted", 0x182u, 1u);
  Type = 0;
  cbData = 0;
  v29 = 0;
  v28 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = 398;
  if ( !lpValueName || (v24 = 398, v9 = 399, !a3) || (v24 = 399, v9 = 400, !a4) )
  {
    v10 = -2147024809;
LABEL_7:
    v23 = v10;
    v25 = v9;
    goto LABEL_32;
  }
  v24 = 400;
  v23 = 0;
  v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v10 = v11;
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0x80070000;
  v23 = v10;
  if ( v10 < 0 )
  {
    v25 = 408;
    v26 = 1;
    goto LABEL_32;
  }
  v24 = 408;
  lpData = CoTaskMemAlloc(cbData);
  v9 = 411;
  if ( !lpData )
  {
    v10 = -2147024882;
    goto LABEL_7;
  }
  v23 = 0;
  v24 = 411;
  memset_0(lpData, 0, cbData);
  v13 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)lpData, &cbData);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  v23 = v13;
  v14 = v13 < 0;
  v15 = 415;
  if ( !v14 )
  {
    v24 = 415;
    v15 = 416;
    if ( Type == 3 )
    {
      v23 = 0;
      v24 = 416;
      v16 = DecryptBlob((const unsigned __int8 *)lpData, cbData, &v29, &v28);
      v17 = v28;
      v23 = v16;
      if ( v16 >= 0 )
      {
        v24 = 418;
        v18 = 0;
        *a3 = v29;
        *a4 = v17;
      }
      else
      {
        v18 = v29;
        v25 = 418;
      }
      if ( v18 )
      {
        for ( i = v18; v17; --v17 )
          *i++ = 0;
        CoTaskMemFree(v18);
      }
      goto LABEL_29;
    }
    v23 = -2147024809;
  }
  v25 = v15;
LABEL_29:
  v20 = cbData;
  v21 = lpData;
  if ( cbData )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  CoTaskMemFree(lpData);
  v10 = v23;
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008b238  mov     [rsp-38h+arg_0], rbx
0x18008b23d  push    rbp
0x18008b23e  push    rsi
0x18008b23f  push    rdi
0x18008b240  push    r12
0x18008b242  push    r13
0x18008b244  push    r14
0x18008b246  push    r15
0x18008b248  mov     rbp, rsp
0x18008b24b  sub     rsp, 70h
0x18008b24f  mov     rsi, r9
0x18008b252  mov     r14, r8
0x18008b255  mov     r15, rdx
0x18008b258  mov     r12, rcx
0x18008b25b  mov     r9d, 1; unsigned __int16
0x18008b261  lea     rdx, aReadbinaryfrom_0; "ReadBinaryFromRegistryEncrypted"
0x18008b268  mov     r8d, 182h; unsigned __int16
0x18008b26e  lea     rcx, [rbp+var_40]; this
0x18008b272  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008b277  xor     r13d, r13d
0x18008b27a  mov     [rbp+Type], r13d
0x18008b27e  mov     [rbp+cbData], r13d
0x18008b282  mov     [rbp+arg_18], r13
0x18008b286  mov     [rbp+arg_10], r13d
0x18008b28a  test    r14, r14
0x18008b28d  jz      short loc_18008B292
0x18008b28f  mov     [r14], r13
0x18008b292  test    rsi, rsi
0x18008b295  jz      short loc_18008B29A
0x18008b297  mov     [rsi], r13d
0x18008b29a  mov     eax, 18Eh
0x18008b29f  test    r15, r15
0x18008b2a2  jnz     short loc_18008B2B5
0x18008b2a4  mov     ebx, 80070057h
0x18008b2a9  mov     [rbp+var_40], ebx
0x18008b2ac  mov     [rbp+var_3A], ax
0x18008b2b0  jmp     loc_18008B45E
0x18008b2b5  mov     [rbp+var_3C], ax
0x18008b2b9  mov     eax, 18Fh
0x18008b2be  test    r14, r14
0x18008b2c1  jz      short loc_18008B2A4
0x18008b2c3  mov     [rbp+var_3C], ax
0x18008b2c7  mov     eax, 190h
0x18008b2cc  test    rsi, rsi
0x18008b2cf  jz      short loc_18008B2A4
0x18008b2d1  mov     [rbp+var_3C], ax
0x18008b2d5  lea     r9, [rbp+Type]; lpType
0x18008b2d9  lea     rax, [rbp+cbData]
0x18008b2dd  mov     [rbp+var_40], r13d
0x18008b2e1  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18008b2e6  xor     r8d, r8d; lpReserved
0x18008b2e9  mov     rdx, r15; lpValueName
0x18008b2ec  mov     [rsp+70h+lpData], r13; lpData
0x18008b2f1  mov     rcx, r12; hKey
0x18008b2f4  call    cs:__imp_RegQueryValueExW
0x18008b2fb  nop     dword ptr [rax+rax+00h]
0x18008b300  mov     ebx, eax
0x18008b302  test    eax, eax
0x18008b304  jle     short loc_18008B30F
0x18008b306  movzx   ebx, ax
0x18008b309  or      ebx, 80070000h
0x18008b30f  mov     [rbp+var_40], ebx
0x18008b312  mov     eax, 198h
0x18008b317  test    ebx, ebx
0x18008b319  jns     short loc_18008B32B
0x18008b31b  mov     [rbp+var_3A], ax
0x18008b31f  mov     [rbp+var_38], 1
0x18008b326  jmp     loc_18008B45E
0x18008b32b  mov     ecx, [rbp+cbData]; cb
0x18008b32e  mov     [rbp+var_3C], ax
0x18008b332  call    cs:__imp_CoTaskMemAlloc
0x18008b339  nop     dword ptr [rax+rax+00h]
0x18008b33e  mov     rdi, rax
0x18008b341  test    rax, rax
0x18008b344  mov     eax, 19Bh
0x18008b349  jnz     short loc_18008B355
0x18008b34b  mov     ebx, 8007000Eh
0x18008b350  jmp     loc_18008B2A9
0x18008b355  mov     r8d, [rbp+cbData]; Size
0x18008b359  xor     edx, edx; Val
0x18008b35b  mov     rcx, rdi; void *
0x18008b35e  mov     [rbp+var_40], r13d
0x18008b362  mov     [rbp+var_3C], ax
0x18008b366  call    memset_0
0x18008b36b  lea     rax, [rbp+cbData]
0x18008b36f  xor     r8d, r8d; lpReserved
0x18008b372  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18008b377  lea     r9, [rbp+Type]; lpType
0x18008b37b  mov     rdx, r15; lpValueName
0x18008b37e  mov     [rsp+70h+lpData], rdi; lpData
0x18008b383  mov     rcx, r12; hKey
0x18008b386  call    cs:__imp_RegQueryValueExW
0x18008b38d  nop     dword ptr [rax+rax+00h]
0x18008b392  test    eax, eax
0x18008b394  jle     short loc_18008B39E
0x18008b396  movzx   eax, ax
0x18008b399  or      eax, 80070000h
0x18008b39e  mov     [rbp+var_40], eax
0x18008b3a1  test    eax, eax
0x18008b3a3  mov     eax, 19Fh
0x18008b3a8  jns     short loc_18008B3B3
0x18008b3aa  mov     [rbp+var_3A], ax
0x18008b3ae  jmp     loc_18008B435
0x18008b3b3  cmp     [rbp+Type], 3
0x18008b3b7  mov     [rbp+var_3C], ax
0x18008b3bb  mov     eax, 1A0h
0x18008b3c0  jz      short loc_18008B3CC
0x18008b3c2  mov     ebx, 80070057h
0x18008b3c7  mov     [rbp+var_40], ebx
0x18008b3ca  jmp     short loc_18008B3AA
0x18008b3cc  mov     edx, [rbp+cbData]; unsigned int
0x18008b3cf  lea     r9, [rbp+arg_10]; unsigned int *
0x18008b3d3  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x18008b3d7  mov     [rbp+var_40], r13d
0x18008b3db  mov     rcx, rdi; unsigned __int8 *
0x18008b3de  mov     [rbp+var_3C], ax
0x18008b3e2  call    ?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z; DecryptBlob(uchar const *,ulong,uchar * *,ulong *)
0x18008b3e7  mov     edx, [rbp+arg_10]
0x18008b3ea  test    eax, eax
0x18008b3ec  mov     [rbp+var_40], eax
0x18008b3ef  mov     eax, 1A2h
0x18008b3f4  jns     short loc_18008B400
0x18008b3f6  mov     rcx, [rbp+arg_18]
0x18008b3fa  mov     [rbp+var_3A], ax
0x18008b3fe  jmp     short loc_18008B410
0x18008b400  mov     [rbp+var_3C], ax
0x18008b404  mov     rcx, r13; pv
0x18008b407  mov     rax, [rbp+arg_18]
0x18008b40b  mov     [r14], rax
0x18008b40e  mov     [rsi], edx
0x18008b410  test    rcx, rcx
0x18008b413  jz      short loc_18008B435
0x18008b415  mov     rax, rcx
0x18008b418  test    rdx, rdx
0x18008b41b  jz      short loc_18008B429
0x18008b41d  mov     [rax], r13b
0x18008b420  inc     rax
0x18008b423  sub     rdx, 1
0x18008b427  jnz     short loc_18008B41D
0x18008b429  call    cs:__imp_CoTaskMemFree
0x18008b430  nop     dword ptr [rax+rax+00h]
0x18008b435  mov     eax, [rbp+cbData]
0x18008b438  mov     rcx, rdi
0x18008b43b  test    rax, rax
0x18008b43e  jz      short loc_18008B44C
0x18008b440  mov     [rcx], r13b
0x18008b443  inc     rcx
0x18008b446  sub     rax, 1
0x18008b44a  jnz     short loc_18008B440
0x18008b44c  mov     rcx, rdi; pv
0x18008b44f  call    cs:__imp_CoTaskMemFree
0x18008b456  nop     dword ptr [rax+rax+00h]
0x18008b45b  mov     ebx, [rbp+var_40]
0x18008b45e  lea     rcx, [rbp+var_40]; this
0x18008b462  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008b467  mov     eax, ebx
0x18008b469  mov     rbx, [rsp+70h+arg_0]
0x18008b471  add     rsp, 70h
0x18008b475  pop     r15
0x18008b477  pop     r14
0x18008b479  pop     r13
0x18008b47b  pop     r12
0x18008b47d  pop     rdi
0x18008b47e  pop     rsi
0x18008b47f  pop     rbp
0x18008b480  retn
```
