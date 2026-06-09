# ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x180087840`
- end: `0x180087a68`
- name: `?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `552`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, unsigned __int8 **@<r8>, unsigned int *@<r9>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180087a70`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180087840`
- `0x18008e878`
- `0x1800c97da`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800878fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087982`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800878fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087982`
- `ole32!CoTaskMemFree` at `0x180087a1c`
- `ole32!CoTaskMemFree` at `0x180087a3c`
- `ole32!CoTaskMemFree` at `0x180087a1c`
- `ole32!CoTaskMemFree` at `0x180087a3c`
- `ole32!CoTaskMemAlloc` at `0x180087934`
- `ole32!CoTaskMemAlloc` at `0x180087934`

## string_xrefs

- `0x180087869`: `ReadBinaryFromRegistryEncrypted`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "ReadBinaryFromRegistryEncrypted", 386, 1);
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
0x180087840  mov     [rsp-38h+arg_0], rbx
0x180087845  push    rbp
0x180087846  push    rsi
0x180087847  push    rdi
0x180087848  push    r12
0x18008784a  push    r13
0x18008784c  push    r14
0x18008784e  push    r15
0x180087850  mov     rbp, rsp
0x180087853  sub     rsp, 70h
0x180087857  mov     rsi, r9
0x18008785a  mov     r14, r8
0x18008785d  mov     r15, rdx
0x180087860  mov     r12, rcx
0x180087863  mov     r9d, 1; unsigned __int16
0x180087869  lea     rdx, aReadbinaryfrom_0; "ReadBinaryFromRegistryEncrypted"
0x180087870  mov     r8d, 182h; unsigned __int16
0x180087876  lea     rcx, [rbp+var_40]; this
0x18008787a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008787f  xor     r13d, r13d
0x180087882  mov     [rbp+Type], r13d
0x180087886  mov     [rbp+cbData], r13d
0x18008788a  mov     [rbp+arg_18], r13
0x18008788e  mov     [rbp+arg_10], r13d
0x180087892  test    r14, r14
0x180087895  jz      short loc_18008789A
0x180087897  mov     [r14], r13
0x18008789a  test    rsi, rsi
0x18008789d  jz      short loc_1800878A2
0x18008789f  mov     [rsi], r13d
0x1800878a2  mov     eax, 18Eh
0x1800878a7  test    r15, r15
0x1800878aa  jnz     short loc_1800878BD
0x1800878ac  mov     ebx, 80070057h
0x1800878b1  mov     [rbp+var_40], ebx
0x1800878b4  mov     [rbp+var_3A], ax
0x1800878b8  jmp     loc_180087A45
0x1800878bd  mov     [rbp+var_3C], ax
0x1800878c1  mov     eax, 18Fh
0x1800878c6  test    r14, r14
0x1800878c9  jz      short loc_1800878AC
0x1800878cb  mov     [rbp+var_3C], ax
0x1800878cf  mov     eax, 190h
0x1800878d4  test    rsi, rsi
0x1800878d7  jz      short loc_1800878AC
0x1800878d9  mov     [rbp+var_3C], ax
0x1800878dd  lea     r9, [rbp+Type]; lpType
0x1800878e1  lea     rax, [rbp+cbData]
0x1800878e5  mov     [rbp+var_40], r13d
0x1800878e9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800878ee  xor     r8d, r8d; lpReserved
0x1800878f1  mov     rdx, r15; lpValueName
0x1800878f4  mov     [rsp+70h+lpData], r13; lpData
0x1800878f9  mov     rcx, r12; hKey
0x1800878fc  call    cs:__imp_RegQueryValueExW
0x180087902  mov     ebx, eax
0x180087904  test    eax, eax
0x180087906  jle     short loc_180087911
0x180087908  movzx   ebx, ax
0x18008790b  or      ebx, 80070000h
0x180087911  mov     [rbp+var_40], ebx
0x180087914  mov     eax, 198h
0x180087919  test    ebx, ebx
0x18008791b  jns     short loc_18008792D
0x18008791d  mov     [rbp+var_3A], ax
0x180087921  mov     [rbp+var_38], 1
0x180087928  jmp     loc_180087A45
0x18008792d  mov     ecx, [rbp+cbData]; cb
0x180087930  mov     [rbp+var_3C], ax
0x180087934  call    cs:__imp_CoTaskMemAlloc
0x18008793a  mov     rdi, rax
0x18008793d  test    rax, rax
0x180087940  mov     eax, 19Bh
0x180087945  jnz     short loc_180087951
0x180087947  mov     ebx, 8007000Eh
0x18008794c  jmp     loc_1800878B1
0x180087951  mov     r8d, [rbp+cbData]; Size
0x180087955  xor     edx, edx; Val
0x180087957  mov     rcx, rdi; void *
0x18008795a  mov     [rbp+var_40], r13d
0x18008795e  mov     [rbp+var_3C], ax
0x180087962  call    memset_0
0x180087967  lea     rax, [rbp+cbData]
0x18008796b  xor     r8d, r8d; lpReserved
0x18008796e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180087973  lea     r9, [rbp+Type]; lpType
0x180087977  mov     rdx, r15; lpValueName
0x18008797a  mov     [rsp+70h+lpData], rdi; lpData
0x18008797f  mov     rcx, r12; hKey
0x180087982  call    cs:__imp_RegQueryValueExW
0x180087988  test    eax, eax
0x18008798a  jle     short loc_180087994
0x18008798c  movzx   eax, ax
0x18008798f  or      eax, 80070000h
0x180087994  mov     [rbp+var_40], eax
0x180087997  test    eax, eax
0x180087999  mov     eax, 19Fh
0x18008799e  jns     short loc_1800879A6
0x1800879a0  mov     [rbp+var_3A], ax
0x1800879a4  jmp     short loc_180087A22
0x1800879a6  cmp     [rbp+Type], 3
0x1800879aa  mov     [rbp+var_3C], ax
0x1800879ae  mov     eax, 1A0h
0x1800879b3  jz      short loc_1800879BF
0x1800879b5  mov     ebx, 80070057h
0x1800879ba  mov     [rbp+var_40], ebx
0x1800879bd  jmp     short loc_1800879A0
0x1800879bf  mov     edx, [rbp+cbData]; unsigned int
0x1800879c2  lea     r9, [rbp+arg_10]; unsigned int *
0x1800879c6  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x1800879ca  mov     [rbp+var_40], r13d
0x1800879ce  mov     rcx, rdi; unsigned __int8 *
0x1800879d1  mov     [rbp+var_3C], ax
0x1800879d5  call    ?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z; DecryptBlob(uchar const *,ulong,uchar * *,ulong *)
0x1800879da  mov     edx, [rbp+arg_10]
0x1800879dd  test    eax, eax
0x1800879df  mov     [rbp+var_40], eax
0x1800879e2  mov     eax, 1A2h
0x1800879e7  jns     short loc_1800879F3
0x1800879e9  mov     rcx, [rbp+arg_18]
0x1800879ed  mov     [rbp+var_3A], ax
0x1800879f1  jmp     short loc_180087A03
0x1800879f3  mov     [rbp+var_3C], ax
0x1800879f7  mov     rcx, r13; pv
0x1800879fa  mov     rax, [rbp+arg_18]
0x1800879fe  mov     [r14], rax
0x180087a01  mov     [rsi], edx
0x180087a03  test    rcx, rcx
0x180087a06  jz      short loc_180087A22
0x180087a08  mov     rax, rcx
0x180087a0b  test    rdx, rdx
0x180087a0e  jz      short loc_180087A1C
0x180087a10  mov     [rax], r13b
0x180087a13  inc     rax
0x180087a16  sub     rdx, 1
0x180087a1a  jnz     short loc_180087A10
0x180087a1c  call    cs:__imp_CoTaskMemFree
0x180087a22  mov     eax, [rbp+cbData]
0x180087a25  mov     rcx, rdi
0x180087a28  test    rax, rax
0x180087a2b  jz      short loc_180087A39
0x180087a2d  mov     [rcx], r13b
0x180087a30  inc     rcx
0x180087a33  sub     rax, 1
0x180087a37  jnz     short loc_180087A2D
0x180087a39  mov     rcx, rdi; pv
0x180087a3c  call    cs:__imp_CoTaskMemFree
0x180087a42  mov     ebx, [rbp+var_40]
0x180087a45  lea     rcx, [rbp+var_40]; this
0x180087a49  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180087a4e  mov     eax, ebx
0x180087a50  mov     rbx, [rsp+70h+arg_0]
0x180087a58  add     rsp, 70h
0x180087a5c  pop     r15
0x180087a5e  pop     r14
0x180087a60  pop     r13
0x180087a62  pop     r12
0x180087a64  pop     rdi
0x180087a65  pop     rsi
0x180087a66  pop     rbp
0x180087a67  retn
```
