# HrGetExtDLLInfo(_ExtDisplayDLLInfo * *,ulong *,int,_GUID *)

- ea: `0x18005b760`
- end: `0x18005b9ce`
- name: `?HrGetExtDLLInfo@@YAJPEAPEAU_ExtDisplayDLLInfo@@PEAKHPEAU_GUID@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(struct _ExtDisplayDLLInfo **, unsigned int *, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b418`

## callees

- `0x1800045e4`
- `0x18005b760`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18005b7f0`
- `ADVAPI32!RegOpenKeyExW` at `0x18005b7f0`
- `ADVAPI32!RegEnumValueW` at `0x18005b84d`
- `ADVAPI32!RegEnumValueW` at `0x18005b84d`
- `ADVAPI32!RegCloseKey` at `0x18005b99c`
- `ADVAPI32!RegCloseKey` at `0x18005b99c`
- `ADVAPI32!RegQueryValueExW` at `0x18005b90d`
- `ADVAPI32!RegQueryValueExW` at `0x18005b90d`
- `KERNEL32!lstrcmpiW` at `0x18005b923`
- `KERNEL32!lstrcmpiW` at `0x18005b923`
- `KERNEL32!LocalAlloc` at `0x18005b951`
- `KERNEL32!LocalAlloc` at `0x18005b951`
- `ole32!CLSIDFromString` at `0x18005b8b8`
- `ole32!CLSIDFromString` at `0x18005b8b8`

## pseudocode

```c
__int64 __fastcall HrGetExtDLLInfo(struct _ExtDisplayDLLInfo **a1, unsigned int *a2, int a3, struct _GUID *a4)
{
  DWORD v4; // r15d
  unsigned int v9; // ebx
  const WCHAR *v10; // rdx
  struct _ExtDisplayDLLInfo *v11; // r14
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  GUID v16; // xmm0
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v22; // [rsp+58h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v4 = 0;
  hKey = 0;
  v9 = -2147467259;
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    v10 = L"Software\\Microsoft\\WAB\\WAB4\\ExtDisplay\\MailUser";
    if ( !a3 )
      v10 = L"Software\\Microsoft\\WAB\\WAB4\\ExtDisplay\\DistList";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, &hKey) )
    {
      v11 = 0;
      v12 = 0;
      memset_0(ValueName, 0, 0x208u);
      Type = 0;
      while ( 1 )
      {
        cchValueName = 260;
        if ( RegEnumValueW(hKey, v4, ValueName, &cchValueName, 0, &Type, 0, 0) )
          break;
        pclsid = 0;
        memset_0(sz, 0, 0x208u);
        StringCchCopyW(sz, 0x104u, ValueName);
        v13 = -1;
        do
          ++v13;
        while ( sz[v13] );
        if ( v13 && CLSIDFromString(sz, &pclsid) >= 0 )
        {
          memset_0(Data, 0, sizeof(Data));
          cbData = 32;
          v22 = 0;
          if ( RegQueryValueExW(hKey, ValueName, 0, &v22, (LPBYTE)Data, &cbData) || lstrcmpiW(Data, L"1") )
            goto LABEL_17;
          v14 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a4->Data1;
          if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a4->Data1 )
            v14 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a4->Data4;
          if ( !v14 )
          {
LABEL_17:
            v15 = LocalAlloc(0x40u, 0x30u);
            if ( !v15 )
            {
              v9 = -2147024882;
              goto LABEL_22;
            }
            v16 = pclsid;
            v15[5] = v11;
            ++v12;
            *((_DWORD *)v15 + 4) = a3;
            v11 = (struct _ExtDisplayDLLInfo *)v15;
            *(GUID *)v15 = v16;
          }
        }
        ++v4;
        ValueName[0] = 0;
      }
      *a1 = v11;
      *a2 = v12;
      v9 = 0;
    }
LABEL_22:
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v9;
}

```

## disassembly

```asm
0x18005b760  mov     [rsp-8+arg_10], rbx
0x18005b765  push    rbp
0x18005b766  push    rsi
0x18005b767  push    rdi
0x18005b768  push    r12
0x18005b76a  push    r13
0x18005b76c  push    r14
0x18005b76e  push    r15
0x18005b770  lea     rbp, [rsp-3E0h]
0x18005b778  sub     rsp, 4E0h
0x18005b77f  mov     rax, cs:__security_cookie
0x18005b786  xor     rax, rsp
0x18005b789  mov     [rbp+410h+var_40], rax
0x18005b790  xor     r15d, r15d
0x18005b793  mov     r12, r9
0x18005b796  mov     [rsp+510h+hKey], r15
0x18005b79b  mov     r13d, r8d
0x18005b79e  mov     rdi, rdx
0x18005b7a1  mov     rsi, rcx
0x18005b7a4  mov     ebx, 80004005h
0x18005b7a9  test    rcx, rcx
0x18005b7ac  jz      loc_18005B9A2
0x18005b7b2  test    rdx, rdx
0x18005b7b5  jz      loc_18005B9A2
0x18005b7bb  mov     [rcx], r15
0x18005b7be  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\WAB\\WAB4\\ExtDisp"...
0x18005b7c5  mov     [rdx], r15d
0x18005b7c8  test    r8d, r8d
0x18005b7cb  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\WAB\\WAB4\\ExtDisp"...
0x18005b7d2  mov     r9d, 20019h; samDesired
0x18005b7d8  cmovz   rdx, rax; lpSubKey
0x18005b7dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b7e3  lea     rax, [rsp+510h+hKey]
0x18005b7e8  xor     r8d, r8d; ulOptions
0x18005b7eb  mov     [rsp+510h+phkResult], rax; phkResult
0x18005b7f0  call    cs:__imp_RegOpenKeyExW
0x18005b7f6  test    eax, eax
0x18005b7f8  jnz     loc_18005B992
0x18005b7fe  xor     edx, edx; Val
0x18005b800  lea     rcx, [rbp+410h+ValueName]; void *
0x18005b804  mov     r8d, 208h; Size
0x18005b80a  mov     r14d, r15d
0x18005b80d  mov     ebx, r15d
0x18005b810  call    memset_0
0x18005b815  xor     ecx, ecx
0x18005b817  mov     [rsp+510h+Type], ecx
0x18005b81b  mov     [rsp+510h+lpcbData], rcx; lpcbData
0x18005b820  lea     rax, [rsp+510h+Type]
0x18005b825  mov     [rsp+510h+lpData], rcx; lpData
0x18005b82a  lea     r9, [rsp+510h+cchValueName]; lpcchValueName
0x18005b82f  mov     [rsp+510h+lpType], rax; lpType
0x18005b834  lea     r8, [rbp+410h+ValueName]; lpValueName
0x18005b838  mov     [rsp+510h+phkResult], rcx; lpReserved
0x18005b83d  mov     edx, r15d; dwIndex
0x18005b840  mov     rcx, [rsp+510h+hKey]; hKey
0x18005b845  mov     [rsp+510h+cchValueName], 104h
0x18005b84d  call    cs:__imp_RegEnumValueW
0x18005b853  test    eax, eax
0x18005b855  jnz     loc_18005B987
0x18005b85b  xorps   xmm0, xmm0
0x18005b85e  lea     rcx, [rbp+410h+sz]; void *
0x18005b865  xor     edx, edx; Val
0x18005b867  mov     r8d, 208h; Size
0x18005b86d  movups  xmmword ptr [rsp+510h+pclsid.Data1], xmm0
0x18005b872  call    memset_0
0x18005b877  lea     r8, [rbp+410h+ValueName]; unsigned __int16 *
0x18005b87b  mov     edx, 104h; unsigned __int64
0x18005b880  lea     rcx, [rbp+410h+sz]; unsigned __int16 *
0x18005b887  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005b88c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005b890  lea     r11, [rbp+410h+sz]
0x18005b897  xor     ecx, ecx
0x18005b899  inc     rax
0x18005b89c  cmp     [r11+rax*2], cx
0x18005b8a1  jnz     short loc_18005B899
0x18005b8a3  test    rax, rax
0x18005b8a6  jz      loc_18005B974
0x18005b8ac  lea     rdx, [rsp+510h+pclsid]; pclsid
0x18005b8b1  lea     rcx, [rbp+410h+sz]; lpsz
0x18005b8b8  call    cs:__imp_CLSIDFromString
0x18005b8be  xor     ecx, ecx
0x18005b8c0  test    eax, eax
0x18005b8c2  js      loc_18005B974
0x18005b8c8  lea     r8d, [rcx+40h]; Size
0x18005b8cc  xor     edx, edx; Val
0x18005b8ce  lea     rcx, [rsp+510h+Data]; void *
0x18005b8d3  call    memset_0
0x18005b8d8  mov     rcx, [rsp+510h+hKey]; hKey
0x18005b8dd  lea     rax, [rsp+510h+cbData]
0x18005b8e2  mov     [rsp+510h+lpType], rax; lpcbData
0x18005b8e7  lea     r9, [rsp+510h+var_4B8]; lpType
0x18005b8ec  lea     rax, [rsp+510h+Data]
0x18005b8f1  mov     [rsp+510h+cbData], 20h ; ' '
0x18005b8f9  xor     r8d, r8d; lpReserved
0x18005b8fc  mov     [rsp+510h+phkResult], rax; lpData
0x18005b901  lea     rdx, [rbp+410h+ValueName]; lpValueName
0x18005b905  mov     [rsp+510h+var_4B8], 0
0x18005b90d  call    cs:__imp_RegQueryValueExW
0x18005b913  test    eax, eax
0x18005b915  jnz     short loc_18005B949
0x18005b917  lea     rdx, pszSrch; "1"
0x18005b91e  lea     rcx, [rsp+510h+Data]; lpString1
0x18005b923  call    cs:__imp_lstrcmpiW
0x18005b929  xor     ecx, ecx
0x18005b92b  test    eax, eax
0x18005b92d  jnz     short loc_18005B949
0x18005b92f  mov     rax, qword ptr [rsp+510h+pclsid.Data1]
0x18005b934  sub     rax, [r12]
0x18005b938  jnz     short loc_18005B944
0x18005b93a  mov     rax, qword ptr [rsp+510h+pclsid.Data4]
0x18005b93f  sub     rax, [r12+8]
0x18005b944  test    rax, rax
0x18005b947  jnz     short loc_18005B974
0x18005b949  mov     edx, 30h ; '0'; uBytes
0x18005b94e  lea     ecx, [rdx+10h]; uFlags
0x18005b951  call    cs:__imp_LocalAlloc
0x18005b957  xor     ecx, ecx
0x18005b959  test    rax, rax
0x18005b95c  jz      short loc_18005B980
0x18005b95e  movups  xmm0, xmmword ptr [rsp+510h+pclsid.Data1]
0x18005b963  mov     [rax+28h], r14
0x18005b967  inc     ebx
0x18005b969  mov     [rax+10h], r13d
0x18005b96d  mov     r14, rax
0x18005b970  movdqu  xmmword ptr [rax], xmm0
0x18005b974  inc     r15d
0x18005b977  mov     [rbp+410h+ValueName], cx
0x18005b97b  jmp     loc_18005B81B
0x18005b980  mov     ebx, 8007000Eh
0x18005b985  jmp     short loc_18005B992
0x18005b987  mov     [rsi], r14
0x18005b98a  xor     r15d, r15d
0x18005b98d  mov     [rdi], ebx
0x18005b98f  mov     ebx, r15d
0x18005b992  mov     rcx, [rsp+510h+hKey]; hKey
0x18005b997  test    rcx, rcx
0x18005b99a  jz      short loc_18005B9A2
0x18005b99c  call    cs:__imp_RegCloseKey
0x18005b9a2  mov     eax, ebx
0x18005b9a4  mov     rcx, [rbp+410h+var_40]
0x18005b9ab  xor     rcx, rsp; StackCookie
0x18005b9ae  call    __security_check_cookie
0x18005b9b3  mov     rbx, [rsp+510h+arg_10]
0x18005b9bb  add     rsp, 4E0h
0x18005b9c2  pop     r15
0x18005b9c4  pop     r14
0x18005b9c6  pop     r13
0x18005b9c8  pop     r12
0x18005b9ca  pop     rdi
0x18005b9cb  pop     rsi
0x18005b9cc  pop     rbp
0x18005b9cd  retn
```
