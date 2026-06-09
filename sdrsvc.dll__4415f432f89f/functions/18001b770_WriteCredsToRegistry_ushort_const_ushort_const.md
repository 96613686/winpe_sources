# WriteCredsToRegistry(ushort const *,ushort const *)

- ea: `0x18001b770`
- end: `0x18001b9f5`
- name: `?WriteCredsToRegistry@@YAJPEBG0@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ff90`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001a71c`
- `0x18001a898`
- `0x18001b640`
- `0x18001b770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b9ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b7fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b7fb`

## string_xrefs

- `0x18001b826`: `Security`
- `0x18001b78c`: `WriteCredsToRegistry`

## pseudocode

```c
__int64 __fastcall WriteCredsToRegistry(const unsigned __int8 *a1, const unsigned __int8 *a2)
{
  __int16 v4; // ax
  int v5; // eax
  bool v6; // sf
  __int16 v7; // ax
  const unsigned __int16 *v8; // rdx
  __int16 v9; // ax
  __int64 v10; // rdx
  const unsigned __int8 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  const unsigned __int8 *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // r9
  unsigned int v17; // ebx
  signed int v19; // [rsp+30h] [rbp-40h] BYREF
  __int16 v20; // [rsp+34h] [rbp-3Ch]
  __int16 v21; // [rsp+36h] [rbp-3Ah]
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "WriteCredsToRegistry", 0x2BBu, 1u);
  v4 = 708;
  phkResult = 0;
  hKey = 0;
  if ( !a1 || (v20 = 708, v4 = 709, !a2) )
  {
    v21 = v4;
    v19 = -2147024809;
    goto LABEL_31;
  }
  v20 = 709;
  v19 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x2001Fu,
         &phkResult);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v19 = v5;
  v6 = v5 < 0;
  v7 = 712;
  if ( !v6 )
  {
    v20 = 712;
    v19 = DeleteRegistryKeyTree(phkResult, L"Security", 1);
    v7 = 715;
    if ( v19 >= 0 )
    {
      v20 = 715;
      v19 = CreateProtectedRegistryKey(phkResult, v8, &hKey);
      v9 = 718;
      if ( v19 >= 0 )
      {
        v20 = 718;
        v10 = 0x7FFFFFFF;
        v11 = a1;
        do
        {
          if ( !*(_WORD *)v11 )
            break;
          v11 += 2;
          --v10;
        }
        while ( v10 );
        if ( !v10 )
        {
          v19 = -2147024809;
          v9 = 720;
          goto LABEL_25;
        }
        v12 = (2 * (0x7FFFFFFF - v10)) & -(__int64)(v10 != 0);
        v20 = 720;
        v9 = 721;
        if ( v12 != (unsigned int)v12 )
          goto LABEL_22;
        v19 = 0;
        v20 = 721;
        v19 = WriteBinaryToRegistryEncrypted(
                hKey,
                &c_wszSafedocsCredentialsUser,
                a1,
                v10 != 0 ? 2 * (0x7FFFFFFF - v10) + 2 : 2);
        v9 = 723;
        if ( v19 >= 0 )
        {
          v20 = 723;
          v13 = 0x7FFFFFFF;
          v14 = a2;
          do
          {
            if ( !*(_WORD *)v14 )
              break;
            v14 += 2;
            --v13;
          }
          while ( v13 );
          if ( !v13 )
          {
            v19 = v13 == 0 ? 0x80070057 : 0;
            v21 = 725;
            goto LABEL_26;
          }
          v15 = 2 * (0x7FFFFFFF - v13);
          v20 = 725;
          v16 = v13 != 0 ? (unsigned int)v15 : 0;
          v9 = 726;
          if ( (v15 & -(__int64)(v13 != 0)) == v16 )
          {
            v19 = 0;
            v20 = 726;
            v19 = WriteBinaryToRegistryEncrypted(hKey, &c_wszSafedocsCredentialsPassword, a2, (int)v16 + 2);
            v9 = 728;
            if ( v19 >= 0 )
            {
              v20 = 728;
              goto LABEL_26;
            }
            goto LABEL_25;
          }
LABEL_22:
          v19 = -2147418113;
        }
      }
LABEL_25:
      v21 = v9;
LABEL_26:
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_28;
    }
  }
  v21 = v7;
LABEL_28:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
LABEL_31:
  v17 = v19;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
  return v17;
}

```

## disassembly

```asm
0x18001b770  mov     [rsp-18h+arg_8], rbx
0x18001b775  mov     [rsp-18h+arg_18], rsi
0x18001b77a  push    rbp
0x18001b77b  push    r14
0x18001b77d  push    r15
0x18001b77f  mov     rbp, rsp
0x18001b782  sub     rsp, 70h
0x18001b786  mov     rsi, rdx
0x18001b789  mov     r14, rcx
0x18001b78c  lea     rdx, aWritecredstore; "WriteCredsToRegistry"
0x18001b793  mov     r9d, 1; unsigned __int16
0x18001b799  lea     rcx, [rbp+var_40]; this
0x18001b79d  mov     r8d, 2BBh; unsigned __int16
0x18001b7a3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b7a8  xor     r15d, r15d
0x18001b7ab  mov     eax, 2C4h
0x18001b7b0  mov     [rbp+arg_10], r15
0x18001b7b4  mov     [rbp+hKey], r15
0x18001b7b8  test    r14, r14
0x18001b7bb  jz      loc_18001B9C6
0x18001b7c1  mov     [rbp+var_3C], ax
0x18001b7c5  mov     eax, 2C5h
0x18001b7ca  test    rsi, rsi
0x18001b7cd  jz      loc_18001B9C6
0x18001b7d3  mov     [rbp+var_3C], ax
0x18001b7d7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001b7de  lea     rax, [rbp+arg_10]
0x18001b7e2  mov     [rbp+var_40], r15d
0x18001b7e6  mov     r9d, 2001Fh; samDesired
0x18001b7ec  mov     [rsp+70h+phkResult], rax; phkResult
0x18001b7f1  xor     r8d, r8d; ulOptions
0x18001b7f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b7fb  call    cs:__imp_RegOpenKeyExW
0x18001b801  test    eax, eax
0x18001b803  jle     short loc_18001B80D
0x18001b805  movzx   eax, ax
0x18001b808  or      eax, 80070000h
0x18001b80d  mov     [rbp+var_40], eax
0x18001b810  test    eax, eax
0x18001b812  mov     eax, 2C8h
0x18001b817  jns     short loc_18001B822
0x18001b819  mov     [rbp+var_3A], ax
0x18001b81d  jmp     loc_18001B9B1
0x18001b822  mov     rcx, [rbp+arg_10]; hKey
0x18001b826  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x18001b82d  mov     r8d, 1; int
0x18001b833  mov     [rbp+var_3C], ax
0x18001b837  call    ?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z; DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)
0x18001b83c  mov     [rbp+var_40], eax
0x18001b83f  test    eax, eax
0x18001b841  mov     eax, 2CBh
0x18001b846  js      short loc_18001B819
0x18001b848  mov     rcx, [rbp+arg_10]; hKey
0x18001b84c  lea     r8, [rbp+hKey]; HKEY *
0x18001b850  mov     [rbp+var_3C], ax
0x18001b854  call    ?CreateProtectedRegistryKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; CreateProtectedRegistryKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001b859  mov     [rbp+var_40], eax
0x18001b85c  test    eax, eax
0x18001b85e  mov     eax, 2CEh
0x18001b863  js      loc_18001B99D
0x18001b869  mov     ebx, 7FFFFFFFh
0x18001b86e  mov     [rbp+var_3C], ax
0x18001b872  mov     edx, ebx
0x18001b874  mov     rax, r14
0x18001b877  cmp     [rax], r15w
0x18001b87b  jz      short loc_18001B887
0x18001b87d  add     rax, 2
0x18001b881  sub     rdx, 1
0x18001b885  jnz     short loc_18001B877
0x18001b887  mov     rax, rdx
0x18001b88a  neg     rax
0x18001b88d  sbb     ecx, ecx
0x18001b88f  not     ecx
0x18001b891  and     ecx, 80070057h
0x18001b897  test    rdx, rdx
0x18001b89a  jz      loc_18001B995
0x18001b8a0  mov     rax, rbx
0x18001b8a3  sub     rax, rdx
0x18001b8a6  add     rax, rax
0x18001b8a9  neg     rdx
0x18001b8ac  sbb     rcx, rcx
0x18001b8af  and     rcx, rax
0x18001b8b2  mov     eax, 2D0h
0x18001b8b7  mov     r9d, ecx
0x18001b8ba  mov     [rbp+var_3C], ax
0x18001b8be  mov     eax, 2D1h
0x18001b8c3  cmp     rcx, r9
0x18001b8c6  jnz     loc_18001B97E
0x18001b8cc  mov     rcx, [rbp+hKey]; hKey
0x18001b8d0  lea     rdx, c_wszSafedocsCredentialsUser; lpValueName
0x18001b8d7  add     r9d, 2; unsigned int
0x18001b8db  mov     [rbp+var_40], r15d
0x18001b8df  mov     r8, r14; unsigned __int8 *
0x18001b8e2  mov     [rbp+var_3C], ax
0x18001b8e6  call    ?WriteBinaryToRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEBEK@Z; WriteBinaryToRegistryEncrypted(HKEY__ *,ushort const *,uchar const *,ulong)
0x18001b8eb  mov     [rbp+var_40], eax
0x18001b8ee  test    eax, eax
0x18001b8f0  mov     eax, 2D3h
0x18001b8f5  js      loc_18001B99D
0x18001b8fb  mov     [rbp+var_3C], ax
0x18001b8ff  mov     rcx, rbx
0x18001b902  mov     rax, rsi
0x18001b905  cmp     [rax], r15w
0x18001b909  jz      short loc_18001B915
0x18001b90b  add     rax, 2
0x18001b90f  sub     rcx, 1
0x18001b913  jnz     short loc_18001B905
0x18001b915  mov     rax, rcx
0x18001b918  neg     rax
0x18001b91b  sbb     edx, edx
0x18001b91d  not     edx
0x18001b91f  and     edx, 80070057h
0x18001b925  test    rcx, rcx
0x18001b928  jz      short loc_18001B987
0x18001b92a  sub     rbx, rcx
0x18001b92d  add     rbx, rbx
0x18001b930  neg     rcx
0x18001b933  mov     ecx, 2D5h
0x18001b938  sbb     rax, rax
0x18001b93b  mov     [rbp+var_3C], cx
0x18001b93f  and     rax, rbx
0x18001b942  mov     r9d, eax
0x18001b945  cmp     rax, r9
0x18001b948  lea     eax, [rcx+1]
0x18001b94b  jnz     short loc_18001B97E
0x18001b94d  mov     rcx, [rbp+hKey]; hKey
0x18001b951  lea     rdx, c_wszSafedocsCredentialsPassword; lpValueName
0x18001b958  add     r9d, 2; unsigned int
0x18001b95c  mov     [rbp+var_40], r15d
0x18001b960  mov     r8, rsi; unsigned __int8 *
0x18001b963  mov     [rbp+var_3C], ax
0x18001b967  call    ?WriteBinaryToRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEBEK@Z; WriteBinaryToRegistryEncrypted(HKEY__ *,ushort const *,uchar const *,ulong)
0x18001b96c  mov     [rbp+var_40], eax
0x18001b96f  test    eax, eax
0x18001b971  mov     eax, 2D8h
0x18001b976  js      short loc_18001B99D
0x18001b978  mov     [rbp+var_3C], ax
0x18001b97c  jmp     short loc_18001B9A1
0x18001b97e  mov     [rbp+var_40], 8000FFFFh
0x18001b985  jmp     short loc_18001B99D
0x18001b987  mov     ecx, 2D5h
0x18001b98c  mov     [rbp+var_40], edx
0x18001b98f  mov     [rbp+var_3A], cx
0x18001b993  jmp     short loc_18001B9A1
0x18001b995  mov     [rbp+var_40], ecx
0x18001b998  mov     eax, 2D0h
0x18001b99d  mov     [rbp+var_3A], ax
0x18001b9a1  cmp     [rbp+hKey], r15
0x18001b9a5  jz      short loc_18001B9B1
0x18001b9a7  mov     rcx, [rbp+hKey]; hKey
0x18001b9ab  call    cs:__imp_RegCloseKey
0x18001b9b1  mov     rcx, [rbp+arg_10]; hKey
0x18001b9b5  test    rcx, rcx
0x18001b9b8  jz      short loc_18001B9D1
0x18001b9ba  call    cs:__imp_RegCloseKey
0x18001b9c0  mov     [rbp+arg_10], r15
0x18001b9c4  jmp     short loc_18001B9D1
0x18001b9c6  mov     [rbp+var_3A], ax
0x18001b9ca  mov     [rbp+var_40], 80070057h
0x18001b9d1  mov     ebx, [rbp+var_40]
0x18001b9d4  lea     rcx, [rbp+var_40]; this
0x18001b9d8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b9dd  lea     r11, [rsp+70h+var_s0]
0x18001b9e2  mov     eax, ebx
0x18001b9e4  mov     rbx, [r11+28h]
0x18001b9e8  mov     rsi, [r11+38h]
0x18001b9ec  mov     rsp, r11
0x18001b9ef  pop     r15
0x18001b9f1  pop     r14
0x18001b9f3  pop     rbp
0x18001b9f4  retn
```
