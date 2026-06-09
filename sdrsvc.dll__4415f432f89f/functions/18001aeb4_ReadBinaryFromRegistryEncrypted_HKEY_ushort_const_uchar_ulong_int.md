# ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)

- ea: `0x18001aeb4`
- end: `0x18001b0dc`
- name: `?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z`
- size: `552`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int8 **, unsigned int *, unsigned int cbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b0e4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001aeb4`
- `0x18001bc78`
- `0x18002170a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001af70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001aff6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001af70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001aff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001afa8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b090`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0b0`

## string_xrefs

- `0x18001aedd`: `ReadBinaryFromRegistryEncrypted`

## pseudocode

```c
__int64 __fastcall ReadBinaryFromRegistryEncrypted(
        HKEY hKey,
        LPCWSTR lpValueName,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned int cbData)
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
      v16 = DecryptBlob((BYTE *)lpData, cbData, &v29, &v28);
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
0x18001aeb4  mov     [rsp-38h+arg_0], rbx
0x18001aeb9  push    rbp
0x18001aeba  push    rsi
0x18001aebb  push    rdi
0x18001aebc  push    r12
0x18001aebe  push    r13
0x18001aec0  push    r14
0x18001aec2  push    r15
0x18001aec4  mov     rbp, rsp
0x18001aec7  sub     rsp, 70h
0x18001aecb  mov     rsi, r9
0x18001aece  mov     r14, r8
0x18001aed1  mov     r15, rdx
0x18001aed4  mov     r12, rcx
0x18001aed7  mov     r9d, 1; unsigned __int16
0x18001aedd  lea     rdx, aReadbinaryfrom_0; "ReadBinaryFromRegistryEncrypted"
0x18001aee4  mov     r8d, 182h; unsigned __int16
0x18001aeea  lea     rcx, [rbp+var_40]; this
0x18001aeee  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001aef3  xor     r13d, r13d
0x18001aef6  mov     [rbp+Type], r13d
0x18001aefa  mov     [rbp+cbData], r13d
0x18001aefe  mov     [rbp+arg_18], r13
0x18001af02  mov     [rbp+arg_10], r13d
0x18001af06  test    r14, r14
0x18001af09  jz      short loc_18001AF0E
0x18001af0b  mov     [r14], r13
0x18001af0e  test    rsi, rsi
0x18001af11  jz      short loc_18001AF16
0x18001af13  mov     [rsi], r13d
0x18001af16  mov     eax, 18Eh
0x18001af1b  test    r15, r15
0x18001af1e  jnz     short loc_18001AF31
0x18001af20  mov     ebx, 80070057h
0x18001af25  mov     [rbp+var_40], ebx
0x18001af28  mov     [rbp+var_3A], ax
0x18001af2c  jmp     loc_18001B0B9
0x18001af31  mov     [rbp+var_3C], ax
0x18001af35  mov     eax, 18Fh
0x18001af3a  test    r14, r14
0x18001af3d  jz      short loc_18001AF20
0x18001af3f  mov     [rbp+var_3C], ax
0x18001af43  mov     eax, 190h
0x18001af48  test    rsi, rsi
0x18001af4b  jz      short loc_18001AF20
0x18001af4d  mov     [rbp+var_3C], ax
0x18001af51  lea     r9, [rbp+Type]; lpType
0x18001af55  lea     rax, [rbp+cbData]
0x18001af59  mov     [rbp+var_40], r13d
0x18001af5d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001af62  xor     r8d, r8d; lpReserved
0x18001af65  mov     rdx, r15; lpValueName
0x18001af68  mov     [rsp+70h+lpData], r13; lpData
0x18001af6d  mov     rcx, r12; hKey
0x18001af70  call    cs:__imp_RegQueryValueExW
0x18001af76  mov     ebx, eax
0x18001af78  test    eax, eax
0x18001af7a  jle     short loc_18001AF85
0x18001af7c  movzx   ebx, ax
0x18001af7f  or      ebx, 80070000h
0x18001af85  mov     [rbp+var_40], ebx
0x18001af88  mov     eax, 198h
0x18001af8d  test    ebx, ebx
0x18001af8f  jns     short loc_18001AFA1
0x18001af91  mov     [rbp+var_3A], ax
0x18001af95  mov     [rbp+var_38], 1
0x18001af9c  jmp     loc_18001B0B9
0x18001afa1  mov     ecx, [rbp+cbData]; cb
0x18001afa4  mov     [rbp+var_3C], ax
0x18001afa8  call    cs:__imp_CoTaskMemAlloc
0x18001afae  mov     rdi, rax
0x18001afb1  test    rax, rax
0x18001afb4  mov     eax, 19Bh
0x18001afb9  jnz     short loc_18001AFC5
0x18001afbb  mov     ebx, 8007000Eh
0x18001afc0  jmp     loc_18001AF25
0x18001afc5  mov     r8d, [rbp+cbData]; Size
0x18001afc9  xor     edx, edx; Val
0x18001afcb  mov     rcx, rdi; void *
0x18001afce  mov     [rbp+var_40], r13d
0x18001afd2  mov     [rbp+var_3C], ax
0x18001afd6  call    memset_0
0x18001afdb  lea     rax, [rbp+cbData]
0x18001afdf  xor     r8d, r8d; lpReserved
0x18001afe2  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001afe7  lea     r9, [rbp+Type]; lpType
0x18001afeb  mov     rdx, r15; lpValueName
0x18001afee  mov     [rsp+70h+lpData], rdi; lpData
0x18001aff3  mov     rcx, r12; hKey
0x18001aff6  call    cs:__imp_RegQueryValueExW
0x18001affc  test    eax, eax
0x18001affe  jle     short loc_18001B008
0x18001b000  movzx   eax, ax
0x18001b003  or      eax, 80070000h
0x18001b008  mov     [rbp+var_40], eax
0x18001b00b  test    eax, eax
0x18001b00d  mov     eax, 19Fh
0x18001b012  jns     short loc_18001B01A
0x18001b014  mov     [rbp+var_3A], ax
0x18001b018  jmp     short loc_18001B096
0x18001b01a  cmp     [rbp+Type], 3
0x18001b01e  mov     [rbp+var_3C], ax
0x18001b022  mov     eax, 1A0h
0x18001b027  jz      short loc_18001B033
0x18001b029  mov     ebx, 80070057h
0x18001b02e  mov     [rbp+var_40], ebx
0x18001b031  jmp     short loc_18001B014
0x18001b033  mov     edx, [rbp+cbData]; unsigned int
0x18001b036  lea     r9, [rbp+arg_10]; unsigned int *
0x18001b03a  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x18001b03e  mov     [rbp+var_40], r13d
0x18001b042  mov     rcx, rdi; unsigned __int8 *
0x18001b045  mov     [rbp+var_3C], ax
0x18001b049  call    ?DecryptBlob@@YAJPEBEKPEAPEAEPEAK@Z; DecryptBlob(uchar const *,ulong,uchar * *,ulong *)
0x18001b04e  mov     edx, [rbp+arg_10]
0x18001b051  test    eax, eax
0x18001b053  mov     [rbp+var_40], eax
0x18001b056  mov     eax, 1A2h
0x18001b05b  jns     short loc_18001B067
0x18001b05d  mov     rcx, [rbp+arg_18]
0x18001b061  mov     [rbp+var_3A], ax
0x18001b065  jmp     short loc_18001B077
0x18001b067  mov     [rbp+var_3C], ax
0x18001b06b  mov     rcx, r13; pv
0x18001b06e  mov     rax, [rbp+arg_18]
0x18001b072  mov     [r14], rax
0x18001b075  mov     [rsi], edx
0x18001b077  test    rcx, rcx
0x18001b07a  jz      short loc_18001B096
0x18001b07c  mov     rax, rcx
0x18001b07f  test    rdx, rdx
0x18001b082  jz      short loc_18001B090
0x18001b084  mov     [rax], r13b
0x18001b087  inc     rax
0x18001b08a  sub     rdx, 1
0x18001b08e  jnz     short loc_18001B084
0x18001b090  call    cs:__imp_CoTaskMemFree
0x18001b096  mov     eax, [rbp+cbData]
0x18001b099  mov     rcx, rdi
0x18001b09c  test    rax, rax
0x18001b09f  jz      short loc_18001B0AD
0x18001b0a1  mov     [rcx], r13b
0x18001b0a4  inc     rcx
0x18001b0a7  sub     rax, 1
0x18001b0ab  jnz     short loc_18001B0A1
0x18001b0ad  mov     rcx, rdi; pv
0x18001b0b0  call    cs:__imp_CoTaskMemFree
0x18001b0b6  mov     ebx, [rbp+var_40]
0x18001b0b9  lea     rcx, [rbp+var_40]; this
0x18001b0bd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b0c2  mov     eax, ebx
0x18001b0c4  mov     rbx, [rsp+70h+arg_0]
0x18001b0cc  add     rsp, 70h
0x18001b0d0  pop     r15
0x18001b0d2  pop     r14
0x18001b0d4  pop     r13
0x18001b0d6  pop     r12
0x18001b0d8  pop     rdi
0x18001b0d9  pop     rsi
0x18001b0da  pop     rbp
0x18001b0db  retn
```
