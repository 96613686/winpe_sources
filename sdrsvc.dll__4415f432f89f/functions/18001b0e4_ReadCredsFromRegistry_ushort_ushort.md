# ReadCredsFromRegistry(ushort * *,ushort * *)

- ea: `0x18001b0e4`
- end: `0x18001b42f`
- name: `?ReadCredsFromRegistry@@YAJPEAPEAG0@Z`
- size: `843`
- prototype: `__int64 __fastcall(LPVOID *, unsigned __int8 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x1800101c0`
- `0x1800147fc`
- `0x1800179f4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001aeb4`
- `0x18001b0e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b18d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b1d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b18d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b3b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b3da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b3b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b3da`

## string_xrefs

- `0x18001b1b8`: `Security`
- `0x18001b0fb`: `ReadCredsFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadCredsFromRegistry(LPVOID *a1, unsigned __int8 **a2)
{
  unsigned __int8 *v4; // rbx
  __int16 v5; // ax
  int v6; // eax
  bool v7; // sf
  __int16 v8; // ax
  int v9; // eax
  __int16 v10; // ax
  _BYTE *v11; // rcx
  unsigned int v12; // r9d
  int v13; // eax
  _WORD *v14; // rax
  unsigned __int64 i; // rdx
  unsigned int v16; // r8d
  unsigned __int64 v17; // r10
  unsigned __int8 *v18; // rax
  unsigned __int64 j; // rdx
  unsigned int v20; // r8d
  unsigned __int64 v21; // r10
  __int64 v22; // rdx
  _BYTE *v23; // rax
  __int64 v24; // rax
  unsigned __int8 *v25; // rcx
  unsigned int v26; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  int v32; // [rsp+40h] [rbp-40h] BYREF
  __int16 v33; // [rsp+44h] [rbp-3Ch]
  __int16 v34; // [rsp+46h] [rbp-3Ah]
  unsigned int v35; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v36; // [rsp+B8h] [rbp+38h] BYREF
  unsigned __int8 *v37; // [rsp+C0h] [rbp+40h] BYREF
  HKEY v38; // [rsp+C8h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v32, "ReadCredsFromRegistry", 621, 1);
  hKey = 0;
  v4 = 0;
  v37 = 0;
  v38 = 0;
  pv = 0;
  v35 = 0;
  v36 = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 635;
  if ( !a1 || (v33 = 635, v5 = 636, !a2) )
  {
    v34 = v5;
    v32 = -2147024809;
    goto LABEL_57;
  }
  v33 = 636;
  v32 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x2001Fu,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v32 = v6;
  v7 = v6 < 0;
  v8 = 639;
  if ( !v7 )
  {
    v33 = 639;
    v9 = RegOpenKeyExW(hKey, L"Security", 0, 0x2001Fu, &v38);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v32 = v9;
    v7 = v9 < 0;
    v8 = 642;
    if ( !v7 )
    {
      v33 = 642;
      v32 = ReadBinaryFromRegistryEncrypted(
              v38,
              &c_wszSafedocsCredentialsUser,
              (unsigned __int8 **)&pv,
              &v35,
              phkResult);
      v10 = 644;
      if ( v32 < 0 )
      {
        v11 = pv;
        v12 = v35;
LABEL_43:
        v34 = v10;
        goto LABEL_44;
      }
      v33 = 644;
      v13 = ReadBinaryFromRegistryEncrypted(v38, &c_wszSafedocsCredentialsPassword, &v37, &v36, phkResulta);
      v11 = pv;
      v7 = v13 < 0;
      v32 = v13;
      v10 = 645;
      if ( v7 )
      {
        v12 = v35;
LABEL_42:
        v4 = v37;
        goto LABEL_43;
      }
      v12 = v35;
      v33 = 645;
      if ( pv )
      {
        v14 = pv;
        for ( i = (unsigned __int64)v35 >> 1; i; --i )
        {
          if ( !*v14 )
            break;
          ++v14;
        }
        v16 = i == 0 ? 0x80070057 : 0;
        if ( i )
          v17 = ((unsigned __int64)v35 >> 1) - i;
        else
          v17 = 0;
        if ( i )
        {
          v4 = v37;
          v33 = 648;
          v10 = 649;
          if ( 2 * v17 + 2 == v35 )
          {
            v32 = 0;
            v33 = 649;
            if ( v37 )
            {
              v18 = v37;
              for ( j = (unsigned __int64)v36 >> 1; j; --j )
              {
                if ( !*(_WORD *)v18 )
                  break;
                v18 += 2;
              }
              v20 = j == 0 ? 0x80070057 : 0;
              if ( j )
                v21 = ((unsigned __int64)v36 >> 1) - j;
              else
                v21 = 0;
              if ( j )
              {
                v33 = 650;
                v10 = 651;
                if ( 2 * v21 + 2 == v36 )
                {
                  *a1 = pv;
                  v12 = 0;
                  *a2 = v4;
                  v11 = 0;
                  v4 = 0;
                  v32 = 0;
                  v33 = 651;
                  v36 = 0;
LABEL_44:
                  if ( v11 )
                  {
                    v22 = v12;
                    v23 = v11;
                    if ( v12 )
                    {
                      do
                      {
                        *v23++ = 0;
                        --v22;
                      }
                      while ( v22 );
                    }
                    CoTaskMemFree(v11);
                  }
                  if ( v4 )
                  {
                    v24 = v36;
                    v25 = v4;
                    if ( v36 )
                    {
                      do
                      {
                        *v25++ = 0;
                        --v24;
                      }
                      while ( v24 );
                    }
                    CoTaskMemFree(v4);
                  }
                  goto LABEL_52;
                }
                goto LABEL_37;
              }
            }
            else
            {
              v20 = -2147024809;
            }
            v32 = v20;
            v10 = 650;
            goto LABEL_43;
          }
LABEL_37:
          v32 = -2147418113;
          goto LABEL_43;
        }
      }
      else
      {
        v16 = -2147024809;
      }
      v32 = v16;
      v10 = 648;
      goto LABEL_42;
    }
  }
  v34 = v8;
LABEL_52:
  if ( v38 )
  {
    RegCloseKey(v38);
    v38 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_57:
  v26 = v32;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v32);
  return v26;
}

```

## disassembly

```asm
0x18001b0e4  push    rbp
0x18001b0e6  push    rbx
0x18001b0e7  push    rsi
0x18001b0e8  push    rdi
0x18001b0e9  push    r14
0x18001b0eb  mov     rbp, rsp
0x18001b0ee  sub     rsp, 80h
0x18001b0f5  mov     rdi, rdx
0x18001b0f8  mov     rsi, rcx
0x18001b0fb  lea     rdx, aReadcredsfromr; "ReadCredsFromRegistry"
0x18001b102  mov     r9d, 1; unsigned __int16
0x18001b108  lea     rcx, [rbp+var_40]; this
0x18001b10c  mov     r8d, 26Dh; unsigned __int16
0x18001b112  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b117  xor     r14d, r14d
0x18001b11a  mov     [rbp+hKey], r14
0x18001b11e  mov     ebx, r14d
0x18001b121  mov     [rbp+arg_10], rbx
0x18001b125  mov     [rbp+arg_18], r14
0x18001b129  mov     [rbp+pv], r14
0x18001b12d  mov     [rbp+arg_0], r14d
0x18001b131  mov     [rbp+arg_8], r14d
0x18001b135  test    rsi, rsi
0x18001b138  jz      short loc_18001B13D
0x18001b13a  mov     [rsi], r14
0x18001b13d  test    rdi, rdi
0x18001b140  jz      short loc_18001B145
0x18001b142  mov     [rdi], r14
0x18001b145  mov     eax, 27Bh
0x18001b14a  test    rsi, rsi
0x18001b14d  jz      loc_18001B408
0x18001b153  mov     [rbp+var_3C], ax
0x18001b157  mov     eax, 27Ch
0x18001b15c  test    rdi, rdi
0x18001b15f  jz      loc_18001B408
0x18001b165  mov     [rbp+var_3C], ax
0x18001b169  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001b170  lea     rax, [rbp+hKey]
0x18001b174  mov     [rbp+var_40], r14d
0x18001b178  mov     r9d, 2001Fh; samDesired
0x18001b17e  mov     qword ptr [rsp+80h+phkResult], rax; phkResult
0x18001b183  xor     r8d, r8d; ulOptions
0x18001b186  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b18d  call    cs:__imp_RegOpenKeyExW
0x18001b193  test    eax, eax
0x18001b195  jle     short loc_18001B19F
0x18001b197  movzx   eax, ax
0x18001b19a  or      eax, 80070000h
0x18001b19f  mov     [rbp+var_40], eax
0x18001b1a2  test    eax, eax
0x18001b1a4  mov     eax, 27Fh
0x18001b1a9  jns     short loc_18001B1B4
0x18001b1ab  mov     [rbp+var_3A], ax
0x18001b1af  jmp     loc_18001B3E0
0x18001b1b4  mov     rcx, [rbp+hKey]; hKey
0x18001b1b8  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x18001b1bf  mov     [rbp+var_3C], ax
0x18001b1c3  mov     r9d, 2001Fh; samDesired
0x18001b1c9  lea     rax, [rbp+arg_18]
0x18001b1cd  xor     r8d, r8d; ulOptions
0x18001b1d0  mov     qword ptr [rsp+80h+phkResult], rax; int
0x18001b1d5  call    cs:__imp_RegOpenKeyExW
0x18001b1db  test    eax, eax
0x18001b1dd  jle     short loc_18001B1E7
0x18001b1df  movzx   eax, ax
0x18001b1e2  or      eax, 80070000h
0x18001b1e7  mov     [rbp+var_40], eax
0x18001b1ea  test    eax, eax
0x18001b1ec  mov     eax, 282h
0x18001b1f1  js      short loc_18001B1AB
0x18001b1f3  mov     rcx, [rbp+arg_18]; hKey
0x18001b1f7  lea     r9, [rbp+arg_0]; unsigned int *
0x18001b1fb  lea     r8, [rbp+pv]; unsigned __int8 **
0x18001b1ff  mov     [rbp+var_3C], ax
0x18001b203  lea     rdx, c_wszSafedocsCredentialsUser; lpValueName
0x18001b20a  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x18001b20f  mov     [rbp+var_40], eax
0x18001b212  test    eax, eax
0x18001b214  mov     eax, 284h
0x18001b219  jns     short loc_18001B228
0x18001b21b  mov     rcx, [rbp+pv]
0x18001b21f  mov     r9d, [rbp+arg_0]
0x18001b223  jmp     loc_18001B395
0x18001b228  mov     rcx, [rbp+arg_18]; hKey
0x18001b22c  lea     r9, [rbp+arg_8]; unsigned int *
0x18001b230  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x18001b234  mov     [rbp+var_3C], ax
0x18001b238  lea     rdx, c_wszSafedocsCredentialsPassword; lpValueName
0x18001b23f  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x18001b244  mov     rcx, [rbp+pv]; pv
0x18001b248  test    eax, eax
0x18001b24a  mov     [rbp+var_40], eax
0x18001b24d  mov     eax, 285h
0x18001b252  jns     short loc_18001B25D
0x18001b254  mov     r9d, [rbp+arg_0]
0x18001b258  jmp     loc_18001B391
0x18001b25d  mov     r9d, [rbp+arg_0]
0x18001b261  mov     [rbp+var_3C], ax
0x18001b265  test    rcx, rcx
0x18001b268  jz      loc_18001B382
0x18001b26e  mov     edx, r9d
0x18001b271  mov     rax, rcx
0x18001b274  shr     rdx, 1
0x18001b277  mov     r10, rdx
0x18001b27a  jz      short loc_18001B28C
0x18001b27c  cmp     [rax], r14w
0x18001b280  jz      short loc_18001B28C
0x18001b282  add     rax, 2
0x18001b286  sub     rdx, 1
0x18001b28a  jnz     short loc_18001B27C
0x18001b28c  mov     rax, rdx
0x18001b28f  neg     rax
0x18001b292  sbb     r8d, r8d
0x18001b295  not     r8d
0x18001b298  and     r8d, 80070057h
0x18001b29f  test    rdx, rdx
0x18001b2a2  jz      short loc_18001B2A9
0x18001b2a4  sub     r10, rdx
0x18001b2a7  jmp     short loc_18001B2AC
0x18001b2a9  mov     r10, r14
0x18001b2ac  test    rdx, rdx
0x18001b2af  jz      loc_18001B388
0x18001b2b5  mov     rbx, [rbp+arg_10]
0x18001b2b9  mov     eax, 288h
0x18001b2be  mov     [rbp+var_3C], ax
0x18001b2c2  lea     rax, ds:2[r10*2]
0x18001b2ca  cmp     rax, r9
0x18001b2cd  mov     eax, 289h
0x18001b2d2  jnz     loc_18001B368
0x18001b2d8  mov     [rbp+var_40], r14d
0x18001b2dc  mov     [rbp+var_3C], ax
0x18001b2e0  test    rbx, rbx
0x18001b2e3  jz      loc_18001B371
0x18001b2e9  mov     r11d, [rbp+arg_8]
0x18001b2ed  mov     rax, rbx
0x18001b2f0  mov     edx, r11d
0x18001b2f3  shr     rdx, 1
0x18001b2f6  mov     r10, rdx
0x18001b2f9  jz      short loc_18001B30B
0x18001b2fb  cmp     [rax], r14w
0x18001b2ff  jz      short loc_18001B30B
0x18001b301  add     rax, 2
0x18001b305  sub     rdx, 1
0x18001b309  jnz     short loc_18001B2FB
0x18001b30b  mov     rax, rdx
0x18001b30e  neg     rax
0x18001b311  sbb     r8d, r8d
0x18001b314  not     r8d
0x18001b317  and     r8d, 80070057h
0x18001b31e  test    rdx, rdx
0x18001b321  jz      short loc_18001B328
0x18001b323  sub     r10, rdx
0x18001b326  jmp     short loc_18001B32B
0x18001b328  mov     r10, r14
0x18001b32b  test    rdx, rdx
0x18001b32e  jz      short loc_18001B377
0x18001b330  mov     eax, 28Ah
0x18001b335  mov     [rbp+var_3C], ax
0x18001b339  lea     rax, ds:2[r10*2]
0x18001b341  cmp     rax, r11
0x18001b344  mov     eax, 28Bh
0x18001b349  jnz     short loc_18001B368
0x18001b34b  mov     [rsi], rcx
0x18001b34e  mov     r9d, r14d
0x18001b351  mov     [rdi], rbx
0x18001b354  mov     rcx, r14
0x18001b357  mov     rbx, r14
0x18001b35a  mov     [rbp+var_40], r14d
0x18001b35e  mov     [rbp+var_3C], ax
0x18001b362  mov     [rbp+arg_8], r14d
0x18001b366  jmp     short loc_18001B399
0x18001b368  mov     [rbp+var_40], 8000FFFFh
0x18001b36f  jmp     short loc_18001B395
0x18001b371  mov     r8d, 80070057h
0x18001b377  mov     [rbp+var_40], r8d
0x18001b37b  mov     eax, 28Ah
0x18001b380  jmp     short loc_18001B395
0x18001b382  mov     r8d, 80070057h
0x18001b388  mov     [rbp+var_40], r8d
0x18001b38c  mov     eax, 288h
0x18001b391  mov     rbx, [rbp+arg_10]
0x18001b395  mov     [rbp+var_3A], ax
0x18001b399  test    rcx, rcx
0x18001b39c  jz      short loc_18001B3BB
0x18001b39e  mov     edx, r9d
0x18001b3a1  mov     rax, rcx
0x18001b3a4  test    r9d, r9d
0x18001b3a7  jz      short loc_18001B3B5
0x18001b3a9  mov     [rax], r14b
0x18001b3ac  inc     rax
0x18001b3af  sub     rdx, 1
0x18001b3b3  jnz     short loc_18001B3A9
0x18001b3b5  call    cs:__imp_CoTaskMemFree
0x18001b3bb  test    rbx, rbx
0x18001b3be  jz      short loc_18001B3E0
0x18001b3c0  mov     eax, [rbp+arg_8]
0x18001b3c3  mov     rcx, rbx
0x18001b3c6  test    rax, rax
0x18001b3c9  jz      short loc_18001B3D7
0x18001b3cb  mov     [rcx], r14b
0x18001b3ce  inc     rcx
0x18001b3d1  sub     rax, 1
0x18001b3d5  jnz     short loc_18001B3CB
0x18001b3d7  mov     rcx, rbx; pv
0x18001b3da  call    cs:__imp_CoTaskMemFree
0x18001b3e0  mov     rcx, [rbp+arg_18]; hKey
0x18001b3e4  test    rcx, rcx
0x18001b3e7  jz      short loc_18001B3F3
0x18001b3e9  call    cs:__imp_RegCloseKey
0x18001b3ef  mov     [rbp+arg_18], r14
0x18001b3f3  mov     rcx, [rbp+hKey]; hKey
0x18001b3f7  test    rcx, rcx
0x18001b3fa  jz      short loc_18001B413
0x18001b3fc  call    cs:__imp_RegCloseKey
0x18001b402  mov     [rbp+hKey], r14
0x18001b406  jmp     short loc_18001B413
0x18001b408  mov     [rbp+var_3A], ax
0x18001b40c  mov     [rbp+var_40], 80070057h
0x18001b413  mov     ebx, [rbp+var_40]
0x18001b416  lea     rcx, [rbp+var_40]; this
0x18001b41a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b41f  mov     eax, ebx
0x18001b421  add     rsp, 80h
0x18001b428  pop     r14
0x18001b42a  pop     rdi
0x18001b42b  pop     rsi
0x18001b42c  pop     rbx
0x18001b42d  pop     rbp
0x18001b42e  retn
```
