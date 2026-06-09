# CSdController::_AddAllUsersDataPathsToEngine(ISdBackup2 *,_SD_BACKUP_CONFIG *,long *)

- ea: `0x1800106f4`
- end: `0x180010978`
- name: `?_AddAllUsersDataPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_SD_BACKUP_CONFIG@@PEAJ@Z`
- size: `644`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct ISdBackup2 *, struct _SD_BACKUP_CONFIG *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800115dc`

## callees

- `0x1800106f4`
- `0x180010c80`
- `0x180011224`
- `0x18001586c`
- `0x180015974`
- `0x180015f34`
- `0x180018a50`
- `0x180018c18`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001085f`
- `msvcrt!_wcsicmp` at `0x18001085f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001094f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001094f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800107ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800107ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800108ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010934`

## string_xrefs

- `0x18001071c`: `CSdController::_AddAllUsersDataPathsToEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_AddAllUsersDataPathsToEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        struct _SD_BACKUP_CONFIG *a3,
        int *a4)
{
  __int16 v8; // ax
  int v9; // eax
  bool v10; // sf
  int v11; // eax
  CSdController *v12; // rcx
  unsigned int v13; // ebx
  unsigned __int16 **v14; // rbx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  int v21; // [rsp+40h] [rbp-49h] BYREF
  __int16 v22; // [rsp+44h] [rbp-45h]
  __int16 v23; // [rsp+46h] [rbp-43h]
  unsigned __int16 *v24[2]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v25; // [rsp+88h] [rbp-1h]
  __int64 v26; // [rsp+98h] [rbp+Fh]
  unsigned int v27; // [rsp+F8h] [rbp+6Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v21,
    "CSdController::_AddAllUsersDataPathsToEngine",
    606,
    0);
  v26 = 0;
  hKey = 0;
  v8 = 615;
  pv = 0;
  v27 = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  if ( a2 && (v22 = 615, v8 = 616, a3) && (v22 = 616, v8 = 617, a4) )
  {
    v22 = 617;
    v21 = 0;
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           0,
           0x20019u,
           &hKey);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v21 = v9;
    v10 = v9 < 0;
    v8 = 632;
    if ( !v10 )
    {
      v22 = 632;
      while ( 1 )
      {
        FreeUserProfileData((struct _UserProfileData *)pv);
        CoTaskMemFree(pv);
        pv = 0;
        v11 = EnumUserProfilePaths(hKey, &v27, (struct _UserProfileData **)&pv);
        v21 = v11;
        if ( v11 < 0 )
        {
          v23 = 639;
          goto LABEL_28;
        }
        v22 = 639;
        if ( v11 == 1 )
        {
          v21 = 0;
          goto LABEL_28;
        }
        v21 = SdSafeDuplicateStr(v24, *((const unsigned __int16 **)pv + 2));
        if ( v21 < 0 )
        {
          v23 = 649;
          goto LABEL_28;
        }
        v22 = 649;
        v13 = 0;
        if ( *((_DWORD *)a3 + 48) )
        {
          while ( _wcsicmp(*((const wchar_t **)pv + 2), *(const wchar_t **)(*((_QWORD *)a3 + 23) + 40LL * v13)) )
          {
            if ( ++v13 >= *((_DWORD *)a3 + 48) )
              goto LABEL_14;
          }
          v14 = (unsigned __int16 **)(*((_QWORD *)a3 + 23) + 40LL * v13);
        }
        else
        {
LABEL_14:
          v14 = v24;
          if ( !*((_DWORD *)a3 + 59) )
            goto LABEL_19;
        }
        if ( !*((_DWORD *)v14 + 7) )
        {
          v15 = CSdController::_AddUserLibraryPathsToEngine(
                  this,
                  a2,
                  *(_DWORD *)a3 & 0x10000000,
                  (struct _UserProfileData *)pv,
                  (struct _SD_BACKUP_USER_DATA *)v14);
          v21 = v15;
          if ( v15 < 0 )
          {
            *a4 = v15;
            v8 = 674;
            v21 = -2130706383;
            break;
          }
        }
        if ( *((_DWORD *)v14 + 6) != 255 )
        {
          v16 = CSdController::_AddUserShellPathsToEngine(
                  v12,
                  a2,
                  (struct _UserProfileData *)pv,
                  (struct _SD_BACKUP_USER_DATA *)v14);
          v21 = v16;
          if ( v16 < 0 )
          {
            *a4 = v16;
            v8 = 688;
            v21 = -2130706376;
            break;
          }
        }
LABEL_19:
        CoTaskMemFree(v24[0]);
        v24[0] = 0;
      }
    }
  }
  else
  {
    v21 = -2147024809;
  }
  v23 = v8;
LABEL_28:
  FreeUserProfileData((struct _UserProfileData *)pv);
  CoTaskMemFree(pv);
  pv = 0;
  v17 = v21;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return v17;
}

```

## disassembly

```asm
0x1800106f4  push    rbp
0x1800106f6  push    rbx
0x1800106f7  push    rsi
0x1800106f8  push    rdi
0x1800106f9  push    r12
0x1800106fb  push    r13
0x1800106fd  push    r14
0x1800106ff  push    r15
0x180010701  lea     rbp, [rsp-1Fh]
0x180010706  sub     rsp, 0A8h
0x18001070d  mov     rsi, r9
0x180010710  mov     rdi, r8
0x180010713  mov     r15, rdx
0x180010716  mov     r12, rcx
0x180010719  xor     r9d, r9d; unsigned __int16
0x18001071c  lea     rdx, aCsdcontrollerA_1; "CSdController::_AddAllUsersDataPathsToE"...
0x180010723  mov     r8d, 25Eh; unsigned __int16
0x180010729  lea     rcx, [rbp+57h+var_A0]; this
0x18001072d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010732  xor     r13d, r13d
0x180010735  xor     eax, eax
0x180010737  mov     [rbp+57h+var_48], rax
0x18001073b  xorps   xmm0, xmm0
0x18001073e  mov     [rbp+57h+hKey], r13
0x180010742  mov     eax, 267h
0x180010747  mov     [rbp+57h+pv], r13
0x18001074b  mov     [rbp+57h+arg_8], r13d
0x18001074f  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180010753  movups  [rbp+57h+var_58], xmm0
0x180010757  test    r15, r15
0x18001075a  jz      loc_18001091C
0x180010760  mov     [rbp+57h+var_9C], ax
0x180010764  mov     eax, 268h
0x180010769  test    rdi, rdi
0x18001076c  jz      loc_18001091C
0x180010772  mov     [rbp+57h+var_9C], ax
0x180010776  mov     eax, 269h
0x18001077b  test    rsi, rsi
0x18001077e  jz      loc_18001091C
0x180010784  mov     [rbp+57h+var_9C], ax
0x180010788  lea     rdx, c_wszProfileList; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001078f  lea     rax, [rbp+57h+hKey]
0x180010793  mov     [rbp+57h+var_A0], r13d
0x180010797  mov     r9d, 20019h; samDesired
0x18001079d  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800107a2  xor     r8d, r8d; ulOptions
0x1800107a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800107ac  call    cs:__imp_RegOpenKeyExW
0x1800107b2  test    eax, eax
0x1800107b4  jle     short loc_1800107BE
0x1800107b6  movzx   eax, ax
0x1800107b9  or      eax, 80070000h
0x1800107be  mov     [rbp+57h+var_A0], eax
0x1800107c1  test    eax, eax
0x1800107c3  mov     eax, 278h
0x1800107c8  js      loc_180010923
0x1800107ce  mov     [rbp+57h+var_9C], ax
0x1800107d2  mov     rcx, [rbp+57h+pv]; struct _UserProfileData *
0x1800107d6  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x1800107db  mov     rcx, [rbp+57h+pv]; pv
0x1800107df  call    cs:__imp_CoTaskMemFree
0x1800107e5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800107e9  lea     r8, [rbp+57h+pv]; struct _UserProfileData **
0x1800107ed  lea     rdx, [rbp+57h+arg_8]; unsigned int *
0x1800107f1  mov     [rbp+57h+pv], r13
0x1800107f5  call    ?EnumUserProfilePaths@@YAJPEAUHKEY__@@PEAKPEAPEAU_UserProfileData@@@Z; EnumUserProfilePaths(HKEY__ *,ulong *,_UserProfileData * *)
0x1800107fa  mov     [rbp+57h+var_A0], eax
0x1800107fd  mov     ecx, 27Fh
0x180010802  test    eax, eax
0x180010804  js      loc_180010916
0x18001080a  mov     [rbp+57h+var_9C], cx
0x18001080e  lea     ebx, [rcx+0Ah]
0x180010811  cmp     eax, 1
0x180010814  jz      loc_180010910
0x18001081a  mov     rdx, [rbp+57h+pv]
0x18001081e  lea     rcx, [rbp+57h+var_68]; unsigned __int16 **
0x180010822  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180010826  call    ?SdSafeDuplicateStr@@YAJPEAPEAGPEBG@Z; SdSafeDuplicateStr(ushort * *,ushort const *)
0x18001082b  mov     [rbp+57h+var_A0], eax
0x18001082e  test    eax, eax
0x180010830  js      loc_18001090A
0x180010836  mov     [rbp+57h+var_9C], bx
0x18001083a  mov     ebx, r13d
0x18001083d  cmp     [rdi+0C0h], r13d
0x180010844  jbe     short loc_180010873
0x180010846  mov     rdx, [rdi+0B8h]
0x18001084d  mov     rcx, [rbp+57h+pv]
0x180010851  mov     eax, ebx
0x180010853  mov     rcx, [rcx+10h]; String1
0x180010857  lea     r14, [rax+rax*4]
0x18001085b  mov     rdx, [rdx+r14*8]; String2
0x18001085f  call    cs:__imp__wcsicmp
0x180010865  test    eax, eax
0x180010867  jz      short loc_1800108DD
0x180010869  inc     ebx
0x18001086b  cmp     ebx, [rdi+0C0h]
0x180010871  jb      short loc_180010846
0x180010873  lea     rbx, [rbp+57h+var_68]
0x180010877  cmp     [rdi+0ECh], r13d
0x18001087e  jz      short loc_1800108CA
0x180010880  cmp     [rbx+1Ch], r13d
0x180010884  jnz     short loc_1800108AB
0x180010886  mov     r8d, [rdi]
0x180010889  mov     rdx, r15; struct ISdBackup2 *
0x18001088c  mov     r9, [rbp+57h+pv]; struct _UserProfileData *
0x180010890  and     r8d, 10000000h; int
0x180010897  mov     rcx, r12; this
0x18001089a  mov     [rsp+0E0h+phkResult], rbx; struct _SD_BACKUP_USER_DATA *
0x18001089f  call    ?_AddUserLibraryPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@HPEAU_UserProfileData@@PEAU_SD_BACKUP_USER_DATA@@@Z; CSdController::_AddUserLibraryPathsToEngine(ISdBackup2 *,int,_UserProfileData *,_SD_BACKUP_USER_DATA *)
0x1800108a4  mov     [rbp+57h+var_A0], eax
0x1800108a7  test    eax, eax
0x1800108a9  js      short loc_1800108EA
0x1800108ab  cmp     dword ptr [rbx+18h], 0FFh
0x1800108b2  jz      short loc_1800108CA
0x1800108b4  mov     r8, [rbp+57h+pv]; struct _UserProfileData *
0x1800108b8  mov     r9, rbx; struct _SD_BACKUP_USER_DATA *
0x1800108bb  mov     rdx, r15; struct ISdBackup2 *
0x1800108be  call    ?_AddUserShellPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@PEAU_SD_BACKUP_USER_DATA@@@Z; CSdController::_AddUserShellPathsToEngine(ISdBackup2 *,_UserProfileData *,_SD_BACKUP_USER_DATA *)
0x1800108c3  mov     [rbp+57h+var_A0], eax
0x1800108c6  test    eax, eax
0x1800108c8  js      short loc_1800108FA
0x1800108ca  mov     rcx, [rbp+57h+var_68]; pv
0x1800108ce  call    cs:__imp_CoTaskMemFree
0x1800108d4  mov     [rbp+57h+var_68], r13
0x1800108d8  jmp     loc_1800107D2
0x1800108dd  mov     rax, [rdi+0B8h]
0x1800108e4  lea     rbx, [rax+r14*8]
0x1800108e8  jmp     short loc_180010880
0x1800108ea  mov     [rsi], eax
0x1800108ec  mov     eax, 2A2h
0x1800108f1  mov     [rbp+57h+var_A0], 81000031h
0x1800108f8  jmp     short loc_180010923
0x1800108fa  mov     [rsi], eax
0x1800108fc  mov     eax, 2B0h
0x180010901  mov     [rbp+57h+var_A0], 81000038h
0x180010908  jmp     short loc_180010923
0x18001090a  mov     [rbp+57h+var_9A], bx
0x18001090e  jmp     short loc_180010927
0x180010910  mov     [rbp+57h+var_A0], r13d
0x180010914  jmp     short loc_180010927
0x180010916  mov     [rbp+57h+var_9A], cx
0x18001091a  jmp     short loc_180010927
0x18001091c  mov     [rbp+57h+var_A0], 80070057h
0x180010923  mov     [rbp+57h+var_9A], ax
0x180010927  mov     rcx, [rbp+57h+pv]; struct _UserProfileData *
0x18001092b  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x180010930  mov     rcx, [rbp+57h+pv]; pv
0x180010934  call    cs:__imp_CoTaskMemFree
0x18001093a  mov     [rbp+57h+pv], r13
0x18001093e  mov     rcx, [rbp+57h+hKey]; hKey
0x180010942  mov     ebx, [rbp+57h+var_A0]
0x180010945  lea     rdx, [rcx-1]
0x180010949  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001094d  ja      short loc_180010959
0x18001094f  call    cs:__imp_RegCloseKey
0x180010955  mov     [rbp+57h+hKey], r13
0x180010959  lea     rcx, [rbp+57h+var_A0]; this
0x18001095d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010962  mov     eax, ebx
0x180010964  add     rsp, 0A8h
0x18001096b  pop     r15
0x18001096d  pop     r14
0x18001096f  pop     r13
0x180010971  pop     r12
0x180010973  pop     rdi
0x180010974  pop     rsi
0x180010975  pop     rbx
0x180010976  pop     rbp
0x180010977  retn
```
