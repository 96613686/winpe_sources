# CCodeDownload::UpdateFileList(HKEY__ *,ulong *,ushort const * * *,int * *)

- ea: `0x1800cf1cc`
- end: `0x1800cf5d3`
- name: `?UpdateFileList@CCodeDownload@@AEAAJPEAUHKEY__@@PEAKPEAPEAPEBGPEAPEAH@Z`
- size: `1031`
- prototype: `int(CCodeDownload *__hidden this, HKEY, unsigned int *, const unsigned __int16 ***, int **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800ce660`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18004d7f0`
- `0x1800cf1cc`
- `0x1800cffe0`
- `0x1800d0108`
- `0x18011a3d8`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf32d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf4a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf32d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800cf4a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf45d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf526`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf45d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800cf526`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf53b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf5a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf53b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf5a1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800cf414`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800cf414`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf372`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf4e7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf372`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800cf4e7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x1800cf3d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x1800cf3d8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800cf3f8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800cf3f8`

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
  signed int v11; // ebx
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
            v11 = Ansi2Unicode(v15);
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
0x1800cf1cc  push    rbp
0x1800cf1ce  push    rbx
0x1800cf1cf  push    rsi
0x1800cf1d0  push    rdi
0x1800cf1d1  push    r12
0x1800cf1d3  push    r13
0x1800cf1d5  push    r14
0x1800cf1d7  push    r15
0x1800cf1d9  lea     rbp, [rsp-0B8h]
0x1800cf1e1  sub     rsp, 1B8h
0x1800cf1e8  mov     rax, cs:__security_cookie
0x1800cf1ef  xor     rax, rsp
0x1800cf1f2  mov     [rbp+0F0h+var_50], rax
0x1800cf1f9  mov     r13, [rbp+0F0h+arg_20]
0x1800cf200  mov     rbx, rdx
0x1800cf203  movsxd  r15, dword ptr [rcx+60h]
0x1800cf207  mov     r12, [rcx+50h]
0x1800cf20b  mov     [rbp+0F0h+var_170], r13
0x1800cf20f  mov     [rsp+1F0h+var_178], r9
0x1800cf214  mov     [rsp+1F0h+var_180], r8
0x1800cf219  mov     [rsp+1F0h+var_188], rdx
0x1800cf21e  mov     [rsp+1F0h+hKey], 0
0x1800cf227  call    ?InstallBrokerIsNeeded@@YAHK@Z; InstallBrokerIsNeeded(ulong)
0x1800cf22c  xor     edi, edi
0x1800cf22e  mov     [rsp+1F0h+var_1A0], eax
0x1800cf232  xor     r14d, r14d
0x1800cf235  mov     ecx, eax
0x1800cf237  lea     esi, [rdi+1]
0x1800cf23a  test    eax, eax
0x1800cf23c  jz      loc_1800CF310
0x1800cf242  test    r15d, r15d
0x1800cf245  jle     short loc_1800CF2C0
0x1800cf247  lea     eax, [rdi+8]
0x1800cf24a  mov     rbx, r15
0x1800cf24d  mul     r15
0x1800cf250  lea     rdi, [r14-1]
0x1800cf254  cmovb   rax, rdi
0x1800cf258  mov     rcx, rax; Size
0x1800cf25b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cf260  mov     r14, rax
0x1800cf263  test    rax, rax
0x1800cf266  jnz     short loc_1800CF272
0x1800cf268  mov     ebx, 8007000Eh
0x1800cf26d  jmp     loc_1800CF597
0x1800cf272  mov     eax, 4
0x1800cf277  mul     rbx
0x1800cf27a  cmovb   rax, rdi
0x1800cf27e  mov     rcx, rax; Size
0x1800cf281  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cf286  mov     rdi, rax
0x1800cf289  test    rax, rax
0x1800cf28c  jnz     short loc_1800CF298
0x1800cf28e  mov     ebx, 8007000Eh
0x1800cf293  jmp     loc_1800CF57F
0x1800cf298  lea     r8, ds:0[r15*8]; Size
0x1800cf2a0  xor     edx, edx; Val
0x1800cf2a2  mov     rcx, r14; void *
0x1800cf2a5  call    memset_0
0x1800cf2aa  lea     r8, ds:0[r15*4]; Size
0x1800cf2b2  xor     edx, edx; Val
0x1800cf2b4  mov     rcx, rdi; void *
0x1800cf2b7  call    memset_0
0x1800cf2bc  mov     ecx, [rsp+1F0h+var_1A0]
0x1800cf2c0  xor     ebx, ebx
0x1800cf2c2  xor     esi, esi
0x1800cf2c4  cmp     esi, r15d
0x1800cf2c7  jge     loc_1800CF55F
0x1800cf2cd  mov     rax, [r12+10h]
0x1800cf2d2  mov     r13, [r12]
0x1800cf2d6  mov     r8, [rax+8]; char *
0x1800cf2da  mov     r12d, [rax+14h]
0x1800cf2de  test    ecx, ecx
0x1800cf2e0  jz      loc_1800CF42B
0x1800cf2e6  test    r8, r8
0x1800cf2e9  jz      short loc_1800CF304
0x1800cf2eb  movsxd  rax, esi
0x1800cf2ee  mov     rcx, r8; lpMultiByteStr
0x1800cf2f1  lea     rdx, [r14+rax*8]
0x1800cf2f5  call    Ansi2Unicode
0x1800cf2fa  mov     ebx, eax
0x1800cf2fc  test    eax, eax
0x1800cf2fe  js      loc_1800CF57A
0x1800cf304  movsxd  rcx, esi
0x1800cf307  mov     [rdi+rcx*4], r12d
0x1800cf30b  jmp     loc_1800CF547
0x1800cf310  lea     rax, [rsp+1F0h+hKey]
0x1800cf315  mov     r9d, 0F003Fh; samDesired
0x1800cf31b  xor     r8d, r8d; ulOptions
0x1800cf31e  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800cf323  lea     rdx, aFiles; "Files"
0x1800cf32a  mov     rcx, rbx; hKey
0x1800cf32d  call    cs:__imp_RegOpenKeyExA
0x1800cf334  nop     dword ptr [rax+rax+00h]
0x1800cf339  test    eax, eax
0x1800cf33b  jz      short loc_1800CF398
0x1800cf33d  test    r15d, r15d
0x1800cf340  jz      short loc_1800CF398
0x1800cf342  mov     [rsp+1F0h+lpdwDisposition], rdi; lpdwDisposition
0x1800cf347  lea     rax, [rsp+1F0h+hKey]
0x1800cf34c  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x1800cf351  lea     rdx, aFiles; "Files"
0x1800cf358  mov     [rsp+1F0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800cf35d  xor     r9d, r9d; lpClass
0x1800cf360  mov     [rsp+1F0h+samDesired], 2000000h; samDesired
0x1800cf368  xor     r8d, r8d; Reserved
0x1800cf36b  mov     rcx, rbx; hKey
0x1800cf36e  mov     dword ptr [rsp+1F0h+phkResult], edi; dwOptions
0x1800cf372  call    cs:__imp_RegCreateKeyExA
0x1800cf379  nop     dword ptr [rax+rax+00h]
0x1800cf37e  mov     ebx, eax
0x1800cf380  test    eax, eax
0x1800cf382  jz      short loc_1800CF398
0x1800cf384  jle     loc_1800CF576
0x1800cf38a  movzx   ebx, ax
0x1800cf38d  or      ebx, 80070000h
0x1800cf393  jmp     loc_1800CF576
0x1800cf398  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800cf39d  test    rcx, rcx
0x1800cf3a0  jz      loc_1800CF2BC
0x1800cf3a6  mov     [rsp+1F0h+Type], esi
0x1800cf3aa  mov     ebx, esi
0x1800cf3ac  mov     [rsp+1F0h+cchValueName], 104h
0x1800cf3b4  xor     edx, edx; dwIndex
0x1800cf3b6  mov     [rsp+1F0h+var_1B8], rdi; lpcbData
0x1800cf3bb  lea     rax, [rsp+1F0h+Type]
0x1800cf3c0  mov     [rsp+1F0h+lpSecurityAttributes], rdi; lpData
0x1800cf3c5  lea     r9, [rsp+1F0h+cchValueName]; lpcchValueName
0x1800cf3ca  mov     qword ptr [rsp+1F0h+samDesired], rax; lpType
0x1800cf3cf  lea     r8, [rbp+0F0h+ValueName]; lpValueName
0x1800cf3d3  mov     [rsp+1F0h+phkResult], rdi; lpReserved
0x1800cf3d8  call    cs:__imp_RegEnumValueA
0x1800cf3df  nop     dword ptr [rax+rax+00h]
0x1800cf3e4  test    eax, eax
0x1800cf3e6  jnz     loc_1800CF2BC
0x1800cf3ec  lea     rcx, [rbp+0F0h+ValueName]; lpFileName
0x1800cf3f0  mov     [rsp+1F0h+cchValueName], 104h
0x1800cf3f8  call    cs:__imp_GetFileAttributesA
0x1800cf3ff  nop     dword ptr [rax+rax+00h]
0x1800cf404  cmp     eax, 0FFFFFFFFh
0x1800cf407  jnz     short loc_1800CF420
0x1800cf409  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800cf40e  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x1800cf412  xor     ebx, ebx
0x1800cf414  call    cs:__imp_RegDeleteValueA
0x1800cf41b  nop     dword ptr [rax+rax+00h]
0x1800cf420  mov     rcx, [rsp+1F0h+hKey]
0x1800cf425  mov     edx, ebx
0x1800cf427  add     ebx, esi
0x1800cf429  jmp     short loc_1800CF3B6
0x1800cf42b  mov     edx, 104h; unsigned __int64
0x1800cf430  lea     rcx, [rbp+0F0h+ValueName]; char *
0x1800cf434  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800cf439  mov     ecx, 1
0x1800cf43e  lea     rax, Default
0x1800cf445  mov     [rsp+1F0h+samDesired], ecx; cbData
0x1800cf449  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x1800cf44d  mov     r9d, ecx; dwType
0x1800cf450  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800cf455  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800cf45a  xor     r8d, r8d; Reserved
0x1800cf45d  call    cs:__imp_RegSetValueExA
0x1800cf464  nop     dword ptr [rax+rax+00h]
0x1800cf469  test    eax, eax
0x1800cf46b  jnz     loc_1800CF555
0x1800cf471  test    r12d, r12d
0x1800cf474  jz      loc_1800CF547
0x1800cf47a  mov     r12, [rsp+1F0h+var_188]
0x1800cf47f  lea     rax, [rsp+1F0h+cchValueName]
0x1800cf484  mov     rcx, r12; hKey
0x1800cf487  mov     qword ptr [rsp+1F0h+cchValueName], 0
0x1800cf490  mov     r9d, 0F003Fh; samDesired
0x1800cf496  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800cf49b  xor     r8d, r8d; ulOptions
0x1800cf49e  lea     rdx, aFilesflags; "FilesFlags"
0x1800cf4a5  call    cs:__imp_RegOpenKeyExA
0x1800cf4ac  nop     dword ptr [rax+rax+00h]
0x1800cf4b1  xor     ecx, ecx
0x1800cf4b3  test    eax, eax
0x1800cf4b5  jz      short loc_1800CF4F7
0x1800cf4b7  mov     [rsp+1F0h+lpdwDisposition], rcx; lpdwDisposition
0x1800cf4bc  lea     rax, [rsp+1F0h+cchValueName]
0x1800cf4c1  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x1800cf4c6  lea     rdx, aFiles; "Files"
0x1800cf4cd  mov     [rsp+1F0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800cf4d2  xor     r9d, r9d; lpClass
0x1800cf4d5  mov     [rsp+1F0h+samDesired], 2000000h; samDesired
0x1800cf4dd  xor     r8d, r8d; Reserved
0x1800cf4e0  mov     dword ptr [rsp+1F0h+phkResult], ecx; dwOptions
0x1800cf4e4  mov     rcx, r12; hKey
0x1800cf4e7  call    cs:__imp_RegCreateKeyExA
0x1800cf4ee  nop     dword ptr [rax+rax+00h]
0x1800cf4f3  test    eax, eax
0x1800cf4f5  jnz     short loc_1800CF555
0x1800cf4f7  mov     rcx, qword ptr [rsp+1F0h+cchValueName]; hKey
0x1800cf4fc  lea     rax, [rsp+1F0h+Type]
0x1800cf501  mov     [rsp+1F0h+samDesired], 4; cbData
0x1800cf509  lea     rdx, aRedirecttohkcu; "RedirectToHKCU"
0x1800cf510  mov     r9d, 4; dwType
0x1800cf516  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800cf51b  xor     r8d, r8d; Reserved
0x1800cf51e  mov     [rsp+1F0h+Type], 1
0x1800cf526  call    cs:__imp_RegSetValueExA
0x1800cf52d  nop     dword ptr [rax+rax+00h]
0x1800cf532  test    eax, eax
0x1800cf534  jnz     short loc_1800CF555
0x1800cf536  mov     rcx, qword ptr [rsp+1F0h+cchValueName]; hKey
0x1800cf53b  call    cs:__imp_RegCloseKey
0x1800cf542  nop     dword ptr [rax+rax+00h]
0x1800cf547  mov     ecx, [rsp+1F0h+var_1A0]
0x1800cf54b  mov     r12, r13
0x1800cf54e  inc     esi
0x1800cf550  jmp     loc_1800CF2C4
0x1800cf555  jg      loc_1800CF38A
0x1800cf55b  mov     ebx, eax
0x1800cf55d  jmp     short loc_1800CF576
0x1800cf55f  mov     rax, [rsp+1F0h+var_180]
0x1800cf564  mov     [rax], r15d
0x1800cf567  mov     rax, [rsp+1F0h+var_178]
0x1800cf56c  mov     [rax], r14
0x1800cf56f  mov     rax, [rbp+0F0h+var_170]
0x1800cf573  mov     [rax], rdi
0x1800cf576  test    ebx, ebx
0x1800cf578  jns     short loc_1800CF597
0x1800cf57a  test    r14, r14
0x1800cf57d  jz      short loc_1800CF58A
0x1800cf57f  mov     rdx, r14
0x1800cf582  mov     ecx, r15d
0x1800cf585  call    CDLFreeStringArray
0x1800cf58a  test    rdi, rdi
0x1800cf58d  jz      short loc_1800CF597
0x1800cf58f  mov     rcx, rdi; void *
0x1800cf592  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf597  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800cf59c  test    rcx, rcx
0x1800cf59f  jz      short loc_1800CF5AD
0x1800cf5a1  call    cs:__imp_RegCloseKey
0x1800cf5a8  nop     dword ptr [rax+rax+00h]
0x1800cf5ad  mov     eax, ebx
0x1800cf5af  mov     rcx, [rbp+0F0h+var_50]
0x1800cf5b6  xor     rcx, rsp; StackCookie
0x1800cf5b9  call    __security_check_cookie
0x1800cf5be  add     rsp, 1B8h
0x1800cf5c5  pop     r15
0x1800cf5c7  pop     r14
0x1800cf5c9  pop     r13
0x1800cf5cb  pop     r12
0x1800cf5cd  pop     rdi
0x1800cf5ce  pop     rsi
0x1800cf5cf  pop     rbx
0x1800cf5d0  pop     rbp
0x1800cf5d1  retn
```
