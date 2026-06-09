# CWdsSimpleDeviceController::DelayedInitialize(void)

- ea: `0x18000592c`
- end: `0x180005afe`
- name: `?DelayedInitialize@CWdsSimpleDeviceController@@AEAAKXZ`
- size: `466`
- prototype: `unsigned int __fastcall(CWdsSimpleDeviceController *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005ef0`
- `0x180005f70`

## callees

- `0x1800015d4`
- `0x180005508`
- `0x18000592c`
- `0x180006dd8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005a29`
- `KERNEL32!GetLastError` at `0x180005a84`
- `KERNEL32!GetLastError` at `0x180005a29`
- `KERNEL32!GetLastError` at `0x180005a84`
- `KERNEL32!CreateDirectoryW` at `0x180005a19`
- `KERNEL32!CreateDirectoryW` at `0x180005a19`
- `KERNEL32!GetFileAttributesW` at `0x180005a51`
- `KERNEL32!GetFileAttributesW` at `0x180005a51`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180005a74`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180005a74`
- `KERNEL32!EnterCriticalSection` at `0x180005944`
- `KERNEL32!EnterCriticalSection` at `0x180005944`
- `WdsCommonLib!WdsDirectoryExists` at `0x180005a03`
- `WdsCommonLib!WdsDirectoryExists` at `0x180005a03`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059aa`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059dc`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059aa`
- `WdsCommonLib!ConcatenatePaths` at `0x1800059dc`
- `WdsCommonLib!?GetNetSharePath@@YAKPEBGPEAPEAG@Z` at `0x180005978`
- `WdsCommonLib!?GetNetSharePath@@YAKPEBGPEAPEAG@Z` at `0x180005978`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::DelayedInitialize(CWdsSimpleDeviceController *this)
{
  __int64 NetSharePath; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v14; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+28h] [rbp-8h]
  LPCWSTR lpFileName; // [rsp+50h] [rbp+20h] BYREF
  LPCWSTR lpPathName; // [rsp+58h] [rbp+28h] BYREF
  void *Block; // [rsp+60h] [rbp+30h] BYREF

  LODWORD(NetSharePath) = 0;
  v14 = (char *)this + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v15 = 1;
  Block = 0;
  lpPathName = 0;
  lpFileName = 0;
  if ( *((_QWORD *)this + 14) )
    goto LABEL_20;
  NetSharePath = GetNetSharePath(L"REMINST", (unsigned __int16 **)&Block);
  if ( !(unsigned int)ElValidateWin32(NetSharePath, v3, v4, 154) )
  {
    NetSharePath = (unsigned int)ConcatenatePaths(Block, L"Stores\\wdssdc", &lpPathName);
    if ( !(unsigned int)ElValidateWin32(NetSharePath, v5, v6, 159) )
    {
      NetSharePath = (unsigned int)ConcatenatePaths(lpPathName, L"wdssdc.ini", &lpFileName);
      if ( !(unsigned int)ElValidateWin32(NetSharePath, v7, v8, 164) )
      {
        if ( !(unsigned int)WdsDirectoryExists(lpPathName) && !CreateDirectoryW(lpPathName, 0) )
        {
          LastError = GetLastError();
          v12 = 175;
          goto LABEL_8;
        }
        if ( GetFileAttributesW(lpFileName) == -1 && !WritePrivateProfileSectionW(L"WDSSDC", L"Version=1.0", lpFileName) )
        {
          LastError = GetLastError();
          v12 = 185;
LABEL_8:
          LODWORD(NetSharePath) = ElValidateWin32(LastError, v10, v11, v12);
          if ( !(_DWORD)NetSharePath )
            LODWORD(NetSharePath) = 31;
          goto LABEL_14;
        }
        *((_QWORD *)this + 14) = lpFileName;
        lpFileName = 0;
      }
    }
  }
LABEL_14:
  if ( Block )
  {
    operator delete(Block);
    Block = 0;
  }
  if ( lpPathName )
  {
    operator delete((void *)lpPathName);
    lpPathName = 0;
  }
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
LABEL_20:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v14);
  return (unsigned int)NetSharePath;
}

```

## disassembly

```asm
0x18000592c  push    rbp
0x18000592e  push    rbx
0x18000592f  push    rdi
0x180005930  mov     rbp, rsp
0x180005933  sub     rsp, 30h
0x180005937  mov     rdi, rcx
0x18000593a  xor     ebx, ebx
0x18000593c  add     rcx, 48h ; 'H'; lpCriticalSection
0x180005940  mov     [rbp+var_10], rcx
0x180005944  call    cs:__imp_EnterCriticalSection
0x18000594b  nop     dword ptr [rax+rax+00h]
0x180005950  mov     [rbp+var_8], 1
0x180005957  mov     [rbp+Block], rbx
0x18000595b  mov     [rbp+lpPathName], rbx
0x18000595f  mov     [rbp+lpFileName], rbx
0x180005963  cmp     [rdi+70h], rbx
0x180005967  jnz     loc_180005AEA
0x18000596d  lea     rdx, [rbp+Block]
0x180005971  lea     rcx, aReminst; "REMINST"
0x180005978  call    cs:__imp_?GetNetSharePath@@YAKPEBGPEAPEAG@Z; GetNetSharePath(ushort const *,ushort * *)
0x18000597f  nop     dword ptr [rax+rax+00h]
0x180005984  mov     ecx, eax
0x180005986  mov     r9d, 9Ah
0x18000598c  mov     ebx, eax
0x18000598e  call    ElValidateWin32
0x180005993  test    eax, eax
0x180005995  jnz     loc_180005AA8
0x18000599b  mov     rcx, [rbp+Block]
0x18000599f  lea     r8, [rbp+lpPathName]
0x1800059a3  lea     rdx, aStoresWdssdc; "Stores\\wdssdc"
0x1800059aa  call    cs:__imp_ConcatenatePaths
0x1800059b1  nop     dword ptr [rax+rax+00h]
0x1800059b6  mov     ecx, eax
0x1800059b8  mov     r9d, 9Fh
0x1800059be  mov     ebx, eax
0x1800059c0  call    ElValidateWin32
0x1800059c5  test    eax, eax
0x1800059c7  jnz     loc_180005AA8
0x1800059cd  mov     rcx, [rbp+lpPathName]
0x1800059d1  lea     r8, [rbp+lpFileName]
0x1800059d5  lea     rdx, aWdssdcIni; "wdssdc.ini"
0x1800059dc  call    cs:__imp_ConcatenatePaths
0x1800059e3  nop     dword ptr [rax+rax+00h]
0x1800059e8  mov     ecx, eax
0x1800059ea  mov     r9d, 0A4h
0x1800059f0  mov     ebx, eax
0x1800059f2  call    ElValidateWin32
0x1800059f7  test    eax, eax
0x1800059f9  jnz     loc_180005AA8
0x1800059ff  mov     rcx, [rbp+lpPathName]
0x180005a03  call    cs:__imp_WdsDirectoryExists
0x180005a0a  nop     dword ptr [rax+rax+00h]
0x180005a0f  test    eax, eax
0x180005a11  jnz     short loc_180005A4D
0x180005a13  mov     rcx, [rbp+lpPathName]; lpPathName
0x180005a17  xor     edx, edx; lpSecurityAttributes
0x180005a19  call    cs:__imp_CreateDirectoryW
0x180005a20  nop     dword ptr [rax+rax+00h]
0x180005a25  test    eax, eax
0x180005a27  jnz     short loc_180005A4D
0x180005a29  call    cs:__imp_GetLastError
0x180005a30  nop     dword ptr [rax+rax+00h]
0x180005a35  mov     r9d, 0AFh
0x180005a3b  mov     ecx, eax
0x180005a3d  call    ElValidateWin32
0x180005a42  mov     ebx, eax
0x180005a44  test    eax, eax
0x180005a46  jnz     short loc_180005AA8
0x180005a48  lea     ebx, [rax+1Fh]
0x180005a4b  jmp     short loc_180005AA8
0x180005a4d  mov     rcx, [rbp+lpFileName]; lpFileName
0x180005a51  call    cs:__imp_GetFileAttributesW
0x180005a58  nop     dword ptr [rax+rax+00h]
0x180005a5d  cmp     eax, 0FFFFFFFFh
0x180005a60  jnz     short loc_180005A98
0x180005a62  mov     r8, [rbp+lpFileName]; lpFileName
0x180005a66  lea     rdx, String; "Version=1.0"
0x180005a6d  lea     rcx, AppName; "WDSSDC"
0x180005a74  call    cs:__imp_WritePrivateProfileSectionW
0x180005a7b  nop     dword ptr [rax+rax+00h]
0x180005a80  test    eax, eax
0x180005a82  jnz     short loc_180005A98
0x180005a84  call    cs:__imp_GetLastError
0x180005a8b  nop     dword ptr [rax+rax+00h]
0x180005a90  mov     r9d, 0B9h
0x180005a96  jmp     short loc_180005A3B
0x180005a98  mov     rax, [rbp+lpFileName]
0x180005a9c  mov     [rdi+70h], rax
0x180005aa0  mov     [rbp+lpFileName], 0
0x180005aa8  mov     rcx, [rbp+Block]; Block
0x180005aac  test    rcx, rcx
0x180005aaf  jz      short loc_180005ABE
0x180005ab1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005ab6  mov     [rbp+Block], 0
0x180005abe  mov     rcx, [rbp+lpPathName]; Block
0x180005ac2  test    rcx, rcx
0x180005ac5  jz      short loc_180005AD4
0x180005ac7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005acc  mov     [rbp+lpPathName], 0
0x180005ad4  mov     rcx, [rbp+lpFileName]; Block
0x180005ad8  test    rcx, rcx
0x180005adb  jz      short loc_180005AEA
0x180005add  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005ae2  mov     [rbp+lpFileName], 0
0x180005aea  lea     rcx, [rbp+var_10]
0x180005aee  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180005af3  mov     eax, ebx
0x180005af5  add     rsp, 30h
0x180005af9  pop     rdi
0x180005afa  pop     rbx
0x180005afb  pop     rbp
0x180005afc  retn
```
