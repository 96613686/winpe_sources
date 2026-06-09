# CCodeDownload::UpdateFileList(HKEY__ *,ulong *,ushort const * * *,int * *)

- ea: `0x1800c6b98`
- end: `0x1800c6f5c`
- name: `?UpdateFileList@CCodeDownload@@AEAAJPEAUHKEY__@@PEAKPEAPEAPEBGPEAPEAH@Z`
- size: `964`
- prototype: `int(CCodeDownload *__hidden this, HKEY, unsigned int *, const unsigned __int16 ***, int **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c6104`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x18005cc10`
- `0x1800c6b98`
- `0x1800c78ac`
- `0x1800c79c0`
- `0x18010e6d8`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6cf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6e4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6cf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c6e4d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c6e0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c6ec2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c6e0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c6ec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6ed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6f31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6ed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6f31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c6dc8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800c6dc8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c6d38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c6e89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c6d38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c6e89`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x1800c6d98`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x1800c6d98`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800c6db2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800c6db2`

## pseudocode

```c
__int64 __fastcall CCodeDownload::UpdateFileList(
        CCodeDownload *this,
        HKEY a2,
        unsigned int *a3,
        const unsigned __int16 ***a4,
        int **a5)
{
  unsigned __int64 v6; // r15
  _QWORD *v7; // r12
  int *v8; // rdi
  const unsigned __int16 **v9; // r14
  int v10; // ecx
  int v11; // ebx
  int i; // esi
  __int64 v13; // rax
  _QWORD *v14; // r13
  const CHAR *v15; // r8
  int v16; // r12d
  LSTATUS Key; // eax
  HKEY v18; // rcx
  int v19; // ebx
  DWORD j; // edx
  bool v21; // cc
  HKEY v22; // r12
  int IsNeeded; // [rsp+50h] [rbp-B0h]
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchValueName[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v28; // [rsp+68h] [rbp-98h]
  unsigned int *v29; // [rsp+70h] [rbp-90h]
  const unsigned __int16 ***v30; // [rsp+78h] [rbp-88h]
  int **v31; // [rsp+80h] [rbp-80h]
  CHAR ValueName[272]; // [rsp+90h] [rbp-70h] BYREF

  v6 = *((int *)this + 24);
  v7 = (_QWORD *)*((_QWORD *)this + 10);
  v31 = a5;
  v30 = a4;
  v29 = a3;
  v28 = a2;
  hKey = 0;
  v8 = 0;
  IsNeeded = InstallBrokerIsNeeded((unsigned int)this);
  v9 = 0;
  v10 = IsNeeded;
  if ( IsNeeded )
  {
    if ( (int)v6 <= 0 )
    {
LABEL_9:
      v11 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= (int)v6 )
        {
          *v29 = v6;
          *v30 = v9;
          *v31 = v8;
          goto LABEL_36;
        }
        v13 = v7[2];
        v14 = (_QWORD *)*v7;
        v15 = *(const CHAR **)(v13 + 8);
        v16 = *(_DWORD *)(v13 + 20);
        if ( v10 )
        {
          if ( v15 )
          {
            v11 = Ansi2Unicode(v15, (WCHAR **)&v9[i]);
            if ( v11 < 0 )
              goto LABEL_37;
          }
          v8[i] = v16;
        }
        else
        {
          StringCchCopyA(ValueName, 0x104u, v15);
          Key = RegSetValueExA(hKey, ValueName, 0, 1u, &Default, 1u);
          v21 = Key <= 0;
          if ( Key )
            goto LABEL_33;
          if ( v16 )
          {
            v22 = v28;
            *(_QWORD *)cchValueName = 0;
            if ( RegOpenKeyExA(v28, "FilesFlags", 0, 0xF003Fu, (PHKEY)cchValueName)
              && (Key = RegCreateKeyExA(v22, "Files", 0, 0, 0, 0x2000000u, 0, (PHKEY)cchValueName, 0),
                  v21 = Key <= 0,
                  Key)
              || (Type = 1,
                  Key = RegSetValueExA(*(HKEY *)cchValueName, "RedirectToHKCU", 0, 4u, (const BYTE *)&Type, 4u),
                  v21 = Key <= 0,
                  Key) )
            {
LABEL_33:
              if ( !v21 )
                goto LABEL_19;
              v11 = Key;
              goto LABEL_36;
            }
            RegCloseKey(*(HKEY *)cchValueName);
          }
        }
        v10 = IsNeeded;
        v7 = v14;
      }
    }
    v9 = (const unsigned __int16 **)operator new(saturated_mul(v6, 8u));
    if ( !v9 )
    {
      v11 = -2147024882;
      goto LABEL_41;
    }
    v8 = (int *)operator new(saturated_mul(v6, 4u));
    if ( !v8 )
    {
      v11 = -2147024882;
LABEL_38:
      CDLFreeStringArray((unsigned int)v6, v9);
LABEL_39:
      if ( v8 )
        operator delete(v8);
      goto LABEL_41;
    }
    memset_0(v9, 0, 8 * v6);
    memset_0(v8, 0, 4 * v6);
LABEL_8:
    v10 = IsNeeded;
    goto LABEL_9;
  }
  if ( !RegOpenKeyExA(a2, "Files", 0, 0xF003Fu, &hKey)
    || !(_DWORD)v6
    || (Key = RegCreateKeyExA(a2, "Files", 0, 0, 0, 0x2000000u, 0, &hKey, 0), (v11 = Key) == 0) )
  {
    v18 = hKey;
    if ( hKey )
    {
      Type = 1;
      v19 = 1;
      cchValueName[0] = 260;
      for ( j = 0; !RegEnumValueA(v18, j, ValueName, cchValueName, 0, &Type, 0, 0); j = v19++ )
      {
        cchValueName[0] = 260;
        if ( GetFileAttributesA(ValueName) == -1 )
        {
          v19 = 0;
          RegDeleteValueA(hKey, ValueName);
        }
        v18 = hKey;
      }
    }
    goto LABEL_8;
  }
  if ( Key > 0 )
LABEL_19:
    v11 = (unsigned __int16)Key | 0x80070000;
LABEL_36:
  if ( v11 < 0 )
  {
LABEL_37:
    if ( !v9 )
      goto LABEL_39;
    goto LABEL_38;
  }
LABEL_41:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800c6b98  push    rbp
0x1800c6b9a  push    rbx
0x1800c6b9b  push    rsi
0x1800c6b9c  push    rdi
0x1800c6b9d  push    r12
0x1800c6b9f  push    r13
0x1800c6ba1  push    r14
0x1800c6ba3  push    r15
0x1800c6ba5  lea     rbp, [rsp-0B8h]
0x1800c6bad  sub     rsp, 1B8h
0x1800c6bb4  mov     rax, cs:__security_cookie
0x1800c6bbb  xor     rax, rsp
0x1800c6bbe  mov     [rbp+0F0h+var_50], rax
0x1800c6bc5  mov     r13, [rbp+0F0h+arg_20]
0x1800c6bcc  mov     rbx, rdx
0x1800c6bcf  movsxd  r15, dword ptr [rcx+60h]
0x1800c6bd3  mov     r12, [rcx+50h]
0x1800c6bd7  mov     [rbp+0F0h+var_170], r13
0x1800c6bdb  mov     [rsp+1F0h+var_178], r9
0x1800c6be0  mov     [rsp+1F0h+var_180], r8
0x1800c6be5  mov     [rsp+1F0h+var_188], rdx
0x1800c6bea  mov     [rsp+1F0h+hKey], 0
0x1800c6bf3  call    ?InstallBrokerIsNeeded@@YAHK@Z; InstallBrokerIsNeeded(ulong)
0x1800c6bf8  xor     edi, edi
0x1800c6bfa  mov     [rsp+1F0h+var_1A0], eax
0x1800c6bfe  xor     r14d, r14d
0x1800c6c01  mov     ecx, eax
0x1800c6c03  lea     esi, [rdi+1]
0x1800c6c06  test    eax, eax
0x1800c6c08  jz      loc_1800C6CDC
0x1800c6c0e  test    r15d, r15d
0x1800c6c11  jle     short loc_1800C6C8C
0x1800c6c13  lea     eax, [rdi+8]
0x1800c6c16  mov     rbx, r15
0x1800c6c19  mul     r15
0x1800c6c1c  lea     rdi, [r14-1]
0x1800c6c20  cmovb   rax, rdi
0x1800c6c24  mov     rcx, rax; Size
0x1800c6c27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c6c2c  mov     r14, rax
0x1800c6c2f  test    rax, rax
0x1800c6c32  jnz     short loc_1800C6C3E
0x1800c6c34  mov     ebx, 8007000Eh
0x1800c6c39  jmp     loc_1800C6F27
0x1800c6c3e  mov     eax, 4
0x1800c6c43  mul     rbx
0x1800c6c46  cmovb   rax, rdi
0x1800c6c4a  mov     rcx, rax; Size
0x1800c6c4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c6c52  mov     rdi, rax
0x1800c6c55  test    rax, rax
0x1800c6c58  jnz     short loc_1800C6C64
0x1800c6c5a  mov     ebx, 8007000Eh
0x1800c6c5f  jmp     loc_1800C6F0F
0x1800c6c64  lea     r8, ds:0[r15*8]; Size
0x1800c6c6c  xor     edx, edx; Val
0x1800c6c6e  mov     rcx, r14; void *
0x1800c6c71  call    memset_0
0x1800c6c76  lea     r8, ds:0[r15*4]; Size
0x1800c6c7e  xor     edx, edx; Val
0x1800c6c80  mov     rcx, rdi; void *
0x1800c6c83  call    memset_0
0x1800c6c88  mov     ecx, [rsp+1F0h+var_1A0]
0x1800c6c8c  xor     ebx, ebx
0x1800c6c8e  xor     esi, esi
0x1800c6c90  cmp     esi, r15d
0x1800c6c93  jge     loc_1800C6EEF
0x1800c6c99  mov     rax, [r12+10h]
0x1800c6c9e  mov     r13, [r12]
0x1800c6ca2  mov     r8, [rax+8]; char *
0x1800c6ca6  mov     r12d, [rax+14h]
0x1800c6caa  test    ecx, ecx
0x1800c6cac  jz      loc_1800C6DD9
0x1800c6cb2  test    r8, r8
0x1800c6cb5  jz      short loc_1800C6CD0
0x1800c6cb7  movsxd  rax, esi
0x1800c6cba  mov     rcx, r8; lpMultiByteStr
0x1800c6cbd  lea     rdx, [r14+rax*8]
0x1800c6cc1  call    Ansi2Unicode
0x1800c6cc6  mov     ebx, eax
0x1800c6cc8  test    eax, eax
0x1800c6cca  js      loc_1800C6F0A
0x1800c6cd0  movsxd  rcx, esi
0x1800c6cd3  mov     [rdi+rcx*4], r12d
0x1800c6cd7  jmp     loc_1800C6ED7
0x1800c6cdc  lea     rax, [rsp+1F0h+hKey]
0x1800c6ce1  mov     r9d, 0F003Fh; samDesired
0x1800c6ce7  xor     r8d, r8d; ulOptions
0x1800c6cea  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800c6cef  lea     rdx, aFiles; "Files"
0x1800c6cf6  mov     rcx, rbx; hKey
0x1800c6cf9  call    cs:__imp_RegOpenKeyExA
0x1800c6cff  test    eax, eax
0x1800c6d01  jz      short loc_1800C6D58
0x1800c6d03  test    r15d, r15d
0x1800c6d06  jz      short loc_1800C6D58
0x1800c6d08  mov     [rsp+1F0h+lpdwDisposition], rdi; lpdwDisposition
0x1800c6d0d  lea     rax, [rsp+1F0h+hKey]
0x1800c6d12  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x1800c6d17  lea     rdx, aFiles; "Files"
0x1800c6d1e  mov     [rsp+1F0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800c6d23  xor     r9d, r9d; lpClass
0x1800c6d26  mov     [rsp+1F0h+samDesired], 2000000h; samDesired
0x1800c6d2e  xor     r8d, r8d; Reserved
0x1800c6d31  mov     rcx, rbx; hKey
0x1800c6d34  mov     dword ptr [rsp+1F0h+phkResult], edi; dwOptions
0x1800c6d38  call    cs:__imp_RegCreateKeyExA
0x1800c6d3e  mov     ebx, eax
0x1800c6d40  test    eax, eax
0x1800c6d42  jz      short loc_1800C6D58
0x1800c6d44  jle     loc_1800C6F06
0x1800c6d4a  movzx   ebx, ax
0x1800c6d4d  or      ebx, 80070000h
0x1800c6d53  jmp     loc_1800C6F06
0x1800c6d58  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800c6d5d  test    rcx, rcx
0x1800c6d60  jz      loc_1800C6C88
0x1800c6d66  mov     [rsp+1F0h+Type], esi
0x1800c6d6a  mov     ebx, esi
0x1800c6d6c  mov     [rsp+1F0h+cchValueName], 104h
0x1800c6d74  xor     edx, edx; dwIndex
0x1800c6d76  mov     [rsp+1F0h+var_1B8], rdi; lpcbData
0x1800c6d7b  lea     rax, [rsp+1F0h+Type]
0x1800c6d80  mov     [rsp+1F0h+lpSecurityAttributes], rdi; lpData
0x1800c6d85  lea     r9, [rsp+1F0h+cchValueName]; lpcchValueName
0x1800c6d8a  mov     qword ptr [rsp+1F0h+samDesired], rax; lpType
0x1800c6d8f  lea     r8, [rbp+0F0h+ValueName]; lpValueName
0x1800c6d93  mov     [rsp+1F0h+phkResult], rdi; lpReserved
0x1800c6d98  call    cs:__imp_RegEnumValueA
0x1800c6d9e  test    eax, eax
0x1800c6da0  jnz     loc_1800C6C88
0x1800c6da6  lea     rcx, [rbp+0F0h+ValueName]; lpFileName
0x1800c6daa  mov     [rsp+1F0h+cchValueName], 104h
0x1800c6db2  call    cs:__imp_GetFileAttributesA
0x1800c6db8  cmp     eax, 0FFFFFFFFh
0x1800c6dbb  jnz     short loc_1800C6DCE
0x1800c6dbd  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800c6dc2  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x1800c6dc6  xor     ebx, ebx
0x1800c6dc8  call    cs:__imp_RegDeleteValueA
0x1800c6dce  mov     rcx, [rsp+1F0h+hKey]
0x1800c6dd3  mov     edx, ebx
0x1800c6dd5  add     ebx, esi
0x1800c6dd7  jmp     short loc_1800C6D76
0x1800c6dd9  mov     edx, 104h; unsigned __int64
0x1800c6dde  lea     rcx, [rbp+0F0h+ValueName]; char *
0x1800c6de2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c6de7  mov     ecx, 1
0x1800c6dec  lea     rax, Default
0x1800c6df3  mov     [rsp+1F0h+samDesired], ecx; cbData
0x1800c6df7  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x1800c6dfb  mov     r9d, ecx; dwType
0x1800c6dfe  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800c6e03  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800c6e08  xor     r8d, r8d; Reserved
0x1800c6e0b  call    cs:__imp_RegSetValueExA
0x1800c6e11  test    eax, eax
0x1800c6e13  jnz     loc_1800C6EE5
0x1800c6e19  test    r12d, r12d
0x1800c6e1c  jz      loc_1800C6ED7
0x1800c6e22  mov     r12, [rsp+1F0h+var_188]
0x1800c6e27  lea     rax, [rsp+1F0h+cchValueName]
0x1800c6e2c  mov     rcx, r12; hKey
0x1800c6e2f  mov     qword ptr [rsp+1F0h+cchValueName], 0
0x1800c6e38  mov     r9d, 0F003Fh; samDesired
0x1800c6e3e  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800c6e43  xor     r8d, r8d; ulOptions
0x1800c6e46  lea     rdx, aFilesflags; "FilesFlags"
0x1800c6e4d  call    cs:__imp_RegOpenKeyExA
0x1800c6e53  xor     ecx, ecx
0x1800c6e55  test    eax, eax
0x1800c6e57  jz      short loc_1800C6E93
0x1800c6e59  mov     [rsp+1F0h+lpdwDisposition], rcx; lpdwDisposition
0x1800c6e5e  lea     rax, [rsp+1F0h+cchValueName]
0x1800c6e63  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x1800c6e68  lea     rdx, aFiles; "Files"
0x1800c6e6f  mov     [rsp+1F0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800c6e74  xor     r9d, r9d; lpClass
0x1800c6e77  mov     [rsp+1F0h+samDesired], 2000000h; samDesired
0x1800c6e7f  xor     r8d, r8d; Reserved
0x1800c6e82  mov     dword ptr [rsp+1F0h+phkResult], ecx; dwOptions
0x1800c6e86  mov     rcx, r12; hKey
0x1800c6e89  call    cs:__imp_RegCreateKeyExA
0x1800c6e8f  test    eax, eax
0x1800c6e91  jnz     short loc_1800C6EE5
0x1800c6e93  mov     rcx, qword ptr [rsp+1F0h+cchValueName]; hKey
0x1800c6e98  lea     rax, [rsp+1F0h+Type]
0x1800c6e9d  mov     [rsp+1F0h+samDesired], 4; cbData
0x1800c6ea5  lea     rdx, aRedirecttohkcu; "RedirectToHKCU"
0x1800c6eac  mov     r9d, 4; dwType
0x1800c6eb2  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800c6eb7  xor     r8d, r8d; Reserved
0x1800c6eba  mov     [rsp+1F0h+Type], 1
0x1800c6ec2  call    cs:__imp_RegSetValueExA
0x1800c6ec8  test    eax, eax
0x1800c6eca  jnz     short loc_1800C6EE5
0x1800c6ecc  mov     rcx, qword ptr [rsp+1F0h+cchValueName]; hKey
0x1800c6ed1  call    cs:__imp_RegCloseKey
0x1800c6ed7  mov     ecx, [rsp+1F0h+var_1A0]
0x1800c6edb  mov     r12, r13
0x1800c6ede  inc     esi
0x1800c6ee0  jmp     loc_1800C6C90
0x1800c6ee5  jg      loc_1800C6D4A
0x1800c6eeb  mov     ebx, eax
0x1800c6eed  jmp     short loc_1800C6F06
0x1800c6eef  mov     rax, [rsp+1F0h+var_180]
0x1800c6ef4  mov     [rax], r15d
0x1800c6ef7  mov     rax, [rsp+1F0h+var_178]
0x1800c6efc  mov     [rax], r14
0x1800c6eff  mov     rax, [rbp+0F0h+var_170]
0x1800c6f03  mov     [rax], rdi
0x1800c6f06  test    ebx, ebx
0x1800c6f08  jns     short loc_1800C6F27
0x1800c6f0a  test    r14, r14
0x1800c6f0d  jz      short loc_1800C6F1A
0x1800c6f0f  mov     rdx, r14
0x1800c6f12  mov     ecx, r15d
0x1800c6f15  call    CDLFreeStringArray
0x1800c6f1a  test    rdi, rdi
0x1800c6f1d  jz      short loc_1800C6F27
0x1800c6f1f  mov     rcx, rdi; void *
0x1800c6f22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c6f27  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800c6f2c  test    rcx, rcx
0x1800c6f2f  jz      short loc_1800C6F37
0x1800c6f31  call    cs:__imp_RegCloseKey
0x1800c6f37  mov     eax, ebx
0x1800c6f39  mov     rcx, [rbp+0F0h+var_50]
0x1800c6f40  xor     rcx, rsp; StackCookie
0x1800c6f43  call    __security_check_cookie
0x1800c6f48  add     rsp, 1B8h
0x1800c6f4f  pop     r15
0x1800c6f51  pop     r14
0x1800c6f53  pop     r13
0x1800c6f55  pop     r12
0x1800c6f57  pop     rdi
0x1800c6f58  pop     rsi
0x1800c6f59  pop     rbx
0x1800c6f5a  pop     rbp
0x1800c6f5b  retn
```
