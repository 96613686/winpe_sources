# ReadCredsFromRegistry(ushort * *,ushort * *)

- ea: `0x180087a70`
- end: `0x180087d30`
- name: `?ReadCredsFromRegistry@@YAJPEAPEAG0@Z`
- size: `704`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028300`
- `0x18003f2c4`
- `0x1800891ec`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180087840`
- `0x180087a70`
- `0x18008873c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087cf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087d06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087cf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087d06`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087b2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087b73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087b2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087b73`
- `ole32!CoTaskMemFree` at `0x180087cbf`
- `ole32!CoTaskMemFree` at `0x180087ce4`
- `ole32!CoTaskMemFree` at `0x180087cbf`
- `ole32!CoTaskMemFree` at `0x180087ce4`

## string_xrefs

- `0x180087b59`: `Security`
- `0x180087a8b`: `ReadCredsFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadCredsFromRegistry(unsigned __int16 **a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  __int16 v5; // ax
  int v6; // eax
  bool v7; // sf
  __int16 v8; // ax
  int v9; // eax
  _BYTE *v10; // r11
  __int64 v11; // rdi
  int v12; // eax
  __int16 v13; // ax
  __int16 v14; // ax
  __int64 v15; // r15
  __int64 v16; // rcx
  _BYTE *v17; // rax
  __int64 v18; // rax
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ebx
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  int v27; // [rsp+48h] [rbp-38h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-34h]
  __int16 v29; // [rsp+4Eh] [rbp-32h]
  unsigned int v30; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+D0h] [rbp+50h] BYREF
  HKEY v33; // [rsp+D8h] [rbp+58h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "ReadCredsFromRegistry", 621, 1);
  hKey = 0;
  v4 = 0;
  v32 = 0;
  v33 = 0;
  pv = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 635;
  if ( !a1 || (v28 = 635, v5 = 636, !a2) )
  {
    v27 = -2147024809;
    v29 = v5;
    goto LABEL_39;
  }
  v28 = 636;
  v27 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x2001Fu,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v27 = v6;
  v7 = v6 < 0;
  v8 = 639;
  if ( !v7 )
  {
    v28 = 639;
    v9 = RegOpenKeyExW(hKey, L"Security", 0, 0x2001Fu, &v33);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v27 = v9;
    v7 = v9 < 0;
    v8 = 642;
    if ( !v7 )
    {
      v28 = 642;
      v27 = ReadBinaryFromRegistryEncrypted(
              v33,
              &c_wszSafedocsCredentialsUser,
              (unsigned __int8 **)&pv,
              &v30,
              phkResult);
      if ( v27 < 0 )
      {
        v10 = pv;
        LODWORD(v11) = v30;
        v29 = 644;
LABEL_27:
        if ( v10 )
        {
          v16 = (unsigned int)v11;
          v17 = v10;
          if ( (_DWORD)v11 )
          {
            do
            {
              *v17++ = 0;
              --v16;
            }
            while ( v16 );
          }
          CoTaskMemFree(v10);
        }
        if ( v4 )
        {
          v18 = v31;
          v19 = v4;
          if ( v31 )
          {
            do
            {
              *(_BYTE *)v19 = 0;
              v19 = (unsigned __int16 *)((char *)v19 + 1);
              --v18;
            }
            while ( v18 );
          }
          CoTaskMemFree(v4);
        }
        goto LABEL_35;
      }
      v28 = 644;
      v12 = ReadBinaryFromRegistryEncrypted(
              v33,
              &c_wszSafedocsCredentialsPassword,
              (unsigned __int8 **)&v32,
              &v31,
              phkResulta);
      v10 = pv;
      v7 = v12 < 0;
      v27 = v12;
      v13 = 645;
      if ( v7 )
      {
        LODWORD(v11) = v30;
LABEL_19:
        v4 = v32;
        v29 = v13;
        goto LABEL_27;
      }
      v11 = v30;
      v28 = 645;
      v27 = StringCbLengthW((const unsigned __int16 *)pv, v30, &v25);
      v13 = 648;
      if ( v27 < 0 )
        goto LABEL_19;
      v4 = v32;
      v28 = 648;
      v14 = 649;
      if ( v25 + 2 == v11 )
      {
        v15 = v31;
        v27 = 0;
        v28 = 649;
        v27 = StringCbLengthW(v32, v31, &v25);
        v14 = 650;
        if ( v27 < 0 )
          goto LABEL_23;
        v28 = 650;
        v14 = 651;
        if ( v25 + 2 == v15 )
        {
          *a1 = (unsigned __int16 *)v10;
          LODWORD(v11) = 0;
          *a2 = v4;
          v10 = 0;
          v4 = 0;
          v27 = 0;
          v28 = 651;
          v31 = 0;
          goto LABEL_27;
        }
      }
      v27 = -2147418113;
LABEL_23:
      v29 = v14;
      goto LABEL_27;
    }
  }
  v29 = v8;
LABEL_35:
  if ( v33 )
  {
    RegCloseKey(v33);
    v33 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_39:
  v20 = v27;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v20;
}

```

## disassembly

```asm
0x180087a70  push    rbp
0x180087a72  push    rbx
0x180087a73  push    rsi
0x180087a74  push    rdi
0x180087a75  push    r12
0x180087a77  push    r14
0x180087a79  push    r15
0x180087a7b  mov     rbp, rsp
0x180087a7e  sub     rsp, 80h
0x180087a85  mov     rsi, rdx
0x180087a88  mov     r14, rcx
0x180087a8b  lea     rdx, aReadcredsfromr; "ReadCredsFromRegistry"
0x180087a92  mov     r9d, 1; unsigned __int16
0x180087a98  lea     rcx, [rbp+var_38]; this
0x180087a9c  mov     r8d, 26Dh; unsigned __int16
0x180087aa2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180087aa7  xor     r12d, r12d
0x180087aaa  mov     [rbp+hKey], r12
0x180087aae  mov     ebx, r12d
0x180087ab1  mov     [rbp+arg_10], rbx
0x180087ab5  mov     [rbp+arg_18], r12
0x180087ab9  mov     [rbp+pv], r12
0x180087abd  mov     [rbp+arg_0], r12d
0x180087ac1  mov     [rbp+arg_8], r12d
0x180087ac5  mov     [rbp+var_48], r12
0x180087ac9  test    r14, r14
0x180087acc  jz      short loc_180087AD1
0x180087ace  mov     [r14], r12
0x180087ad1  test    rsi, rsi
0x180087ad4  jz      short loc_180087AD9
0x180087ad6  mov     [rsi], r12
0x180087ad9  mov     eax, 27Bh
0x180087ade  test    r14, r14
0x180087ae1  jnz     short loc_180087AF3
0x180087ae3  mov     [rbp+var_38], 80070057h
0x180087aea  mov     [rbp+var_32], ax
0x180087aee  jmp     loc_180087D10
0x180087af3  mov     [rbp+var_34], ax
0x180087af7  mov     eax, 27Ch
0x180087afc  test    rsi, rsi
0x180087aff  jz      short loc_180087AE3
0x180087b01  mov     [rbp+var_34], ax
0x180087b05  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180087b0c  lea     rax, [rbp+hKey]
0x180087b10  mov     [rbp+var_38], r12d
0x180087b14  mov     r15d, 2001Fh
0x180087b1a  mov     qword ptr [rsp+80h+phkResult], rax; phkResult
0x180087b1f  mov     r9d, r15d; samDesired
0x180087b22  xor     r8d, r8d; ulOptions
0x180087b25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087b2c  call    cs:__imp_RegOpenKeyExW
0x180087b32  mov     edi, 80070000h
0x180087b37  test    eax, eax
0x180087b39  jle     short loc_180087B40
0x180087b3b  movzx   eax, ax
0x180087b3e  or      eax, edi
0x180087b40  mov     [rbp+var_38], eax
0x180087b43  test    eax, eax
0x180087b45  mov     eax, 27Fh
0x180087b4a  jns     short loc_180087B55
0x180087b4c  mov     [rbp+var_32], ax
0x180087b50  jmp     loc_180087CEA
0x180087b55  mov     rcx, [rbp+hKey]; hKey
0x180087b59  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x180087b60  mov     [rbp+var_34], ax
0x180087b64  mov     r9d, r15d; samDesired
0x180087b67  lea     rax, [rbp+arg_18]
0x180087b6b  xor     r8d, r8d; ulOptions
0x180087b6e  mov     qword ptr [rsp+80h+phkResult], rax; int
0x180087b73  call    cs:__imp_RegOpenKeyExW
0x180087b79  test    eax, eax
0x180087b7b  jle     short loc_180087B82
0x180087b7d  movzx   eax, ax
0x180087b80  or      eax, edi
0x180087b82  mov     [rbp+var_38], eax
0x180087b85  test    eax, eax
0x180087b87  mov     eax, 282h
0x180087b8c  js      short loc_180087B4C
0x180087b8e  mov     rcx, [rbp+arg_18]; hKey
0x180087b92  lea     r9, [rbp+arg_0]; unsigned int *
0x180087b96  lea     r8, [rbp+pv]; unsigned __int8 **
0x180087b9a  mov     [rbp+var_34], ax
0x180087b9e  lea     rdx, c_wszSafedocsCredentialsUser; lpValueName
0x180087ba5  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x180087baa  mov     [rbp+var_38], eax
0x180087bad  test    eax, eax
0x180087baf  mov     eax, 284h
0x180087bb4  jns     short loc_180087BC6
0x180087bb6  mov     r11, [rbp+pv]
0x180087bba  mov     edi, [rbp+arg_0]
0x180087bbd  mov     [rbp+var_32], ax
0x180087bc1  jmp     loc_180087CA2
0x180087bc6  mov     rcx, [rbp+arg_18]; hKey
0x180087bca  lea     r9, [rbp+arg_8]; unsigned int *
0x180087bce  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x180087bd2  mov     [rbp+var_34], ax
0x180087bd6  lea     rdx, c_wszSafedocsCredentialsPassword; lpValueName
0x180087bdd  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x180087be2  mov     r11, [rbp+pv]
0x180087be6  test    eax, eax
0x180087be8  mov     [rbp+var_38], eax
0x180087beb  mov     eax, 285h
0x180087bf0  jns     short loc_180087C02
0x180087bf2  mov     edi, [rbp+arg_0]
0x180087bf5  mov     rbx, [rbp+arg_10]
0x180087bf9  mov     [rbp+var_32], ax
0x180087bfd  jmp     loc_180087CA2
0x180087c02  mov     edi, [rbp+arg_0]
0x180087c05  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180087c09  mov     edx, edi; unsigned __int64
0x180087c0b  mov     [rbp+var_34], ax
0x180087c0f  mov     rcx, r11; unsigned __int16 *
0x180087c12  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180087c17  mov     [rbp+var_38], eax
0x180087c1a  test    eax, eax
0x180087c1c  mov     eax, 288h
0x180087c21  js      short loc_180087BF5
0x180087c23  mov     rbx, [rbp+arg_10]
0x180087c27  mov     [rbp+var_34], ax
0x180087c2b  mov     rax, [rbp+var_48]
0x180087c2f  add     rax, 2
0x180087c33  cmp     rax, rdi
0x180087c36  mov     eax, 289h
0x180087c3b  jz      short loc_180087C4A
0x180087c3d  mov     [rbp+var_38], 8000FFFFh
0x180087c44  mov     [rbp+var_32], ax
0x180087c48  jmp     short loc_180087CA2
0x180087c4a  mov     r15d, [rbp+arg_8]
0x180087c4e  lea     r8, [rbp+var_48]; unsigned __int64 *
0x180087c52  mov     edx, r15d; unsigned __int64
0x180087c55  mov     [rbp+var_38], r12d
0x180087c59  mov     rcx, rbx; unsigned __int16 *
0x180087c5c  mov     [rbp+var_34], ax
0x180087c60  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180087c65  mov     [rbp+var_38], eax
0x180087c68  test    eax, eax
0x180087c6a  mov     eax, 28Ah
0x180087c6f  js      short loc_180087C44
0x180087c71  mov     [rbp+var_34], ax
0x180087c75  mov     rax, [rbp+var_48]
0x180087c79  add     rax, 2
0x180087c7d  cmp     rax, r15
0x180087c80  mov     eax, 28Bh
0x180087c85  jnz     short loc_180087C3D
0x180087c87  mov     [r14], r11
0x180087c8a  mov     edi, r12d
0x180087c8d  mov     [rsi], rbx
0x180087c90  mov     r11, r12
0x180087c93  mov     rbx, r12
0x180087c96  mov     [rbp+var_38], r12d
0x180087c9a  mov     [rbp+var_34], ax
0x180087c9e  mov     [rbp+arg_8], r12d
0x180087ca2  test    r11, r11
0x180087ca5  jz      short loc_180087CC5
0x180087ca7  mov     ecx, edi
0x180087ca9  mov     rax, r11
0x180087cac  test    edi, edi
0x180087cae  jz      short loc_180087CBC
0x180087cb0  mov     [rax], r12b
0x180087cb3  inc     rax
0x180087cb6  sub     rcx, 1
0x180087cba  jnz     short loc_180087CB0
0x180087cbc  mov     rcx, r11; pv
0x180087cbf  call    cs:__imp_CoTaskMemFree
0x180087cc5  test    rbx, rbx
0x180087cc8  jz      short loc_180087CEA
0x180087cca  mov     eax, [rbp+arg_8]
0x180087ccd  mov     rcx, rbx
0x180087cd0  test    rax, rax
0x180087cd3  jz      short loc_180087CE1
0x180087cd5  mov     [rcx], r12b
0x180087cd8  inc     rcx
0x180087cdb  sub     rax, 1
0x180087cdf  jnz     short loc_180087CD5
0x180087ce1  mov     rcx, rbx; pv
0x180087ce4  call    cs:__imp_CoTaskMemFree
0x180087cea  mov     rcx, [rbp+arg_18]; hKey
0x180087cee  test    rcx, rcx
0x180087cf1  jz      short loc_180087CFD
0x180087cf3  call    cs:__imp_RegCloseKey
0x180087cf9  mov     [rbp+arg_18], r12
0x180087cfd  mov     rcx, [rbp+hKey]; hKey
0x180087d01  test    rcx, rcx
0x180087d04  jz      short loc_180087D10
0x180087d06  call    cs:__imp_RegCloseKey
0x180087d0c  mov     [rbp+hKey], r12
0x180087d10  mov     ebx, [rbp+var_38]
0x180087d13  lea     rcx, [rbp+var_38]; this
0x180087d17  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180087d1c  mov     eax, ebx
0x180087d1e  add     rsp, 80h
0x180087d25  pop     r15
0x180087d27  pop     r14
0x180087d29  pop     r12
0x180087d2b  pop     rdi
0x180087d2c  pop     rsi
0x180087d2d  pop     rbx
0x180087d2e  pop     rbp
0x180087d2f  retn
```
