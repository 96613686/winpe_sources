# OOBE::CompleteTime::TryGetTime

- ea: `0x18004b2d4`
- end: `0x18004b449`
- name: `OOBE::CompleteTime::TryGetTime`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c77c`

## callees

- `0x180037df8`
- `0x18004b2d4`
- `0x18004b450`
- `0x1800e34bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004b337`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b38f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b436`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b38f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004b436`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b3e1`

## string_xrefs

- `0x18004b382`: `OOBECompleteTimestamp`
- `0x18004b3c6`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OOBE::CompleteTime::TryGetTime(wchar_t *a1, wchar_t *a2)
{
  int RedirectionKeyPath; // eax
  LSTATUS v5; // eax
  signed int v6; // ebx
  int phkResult; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD pcbData; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+38h] BYREF

  *(_BYTE *)a1 = 0;
  pcbData = 16;
  *(_OWORD *)a2 = 0;
  hkey = 0;
  lpSubKey = 0;
  RedirectionKeyPath = GetRedirectionKeyPath(a1, a2, (wchar_t **)&lpSubKey);
  if ( RedirectionKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBECompleteTime.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResult);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
  }
  else
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hkey);
    v6 = v5;
    if ( !v5 )
    {
      if ( lpSubKey )
        CoTaskMemFree((LPVOID)lpSubKey);
LABEL_6:
      *(_BYTE *)a1 = RegGetValueW(hkey, 0, L"OOBECompleteTimestamp", 0x20000008u, 0, a2, &pcbData) == 0;
      goto LABEL_7;
    }
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&lpSubKey);
    if ( v6 >= 0 )
      goto LABEL_6;
  }
LABEL_7:
  if ( !*(_BYTE *)a1 )
  {
    pcbData = 16;
    *(_BYTE *)a1 = RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
                     L"EndTimeStamp",
                     0x20000008u,
                     0,
                     a2,
                     &pcbData) == 0;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x18004b2d4  mov     [rsp-18h+arg_8], rbx
0x18004b2d9  push    rbp
0x18004b2da  push    rsi
0x18004b2db  push    rdi
0x18004b2dc  mov     rbp, rsp
0x18004b2df  sub     rsp, 40h
0x18004b2e3  mov     rsi, rdx
0x18004b2e6  mov     rdi, rcx
0x18004b2e9  mov     byte ptr [rcx], 0
0x18004b2ec  mov     [rbp+arg_0], 10h
0x18004b2f3  xorps   xmm0, xmm0
0x18004b2f6  movups  xmmword ptr [rdx], xmm0
0x18004b2f9  mov     [rbp+hkey], 0
0x18004b301  mov     [rbp+lpSubKey], 0
0x18004b309  lea     r8, [rbp+lpSubKey]; wchar_t **
0x18004b30d  call    ?GetRedirectionKeyPath@@YAJPEB_W0PEAPEA_W@Z; GetRedirectionKeyPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x18004b312  test    eax, eax
0x18004b314  js      loc_18004B3BF
0x18004b31a  lea     rax, [rbp+hkey]
0x18004b31e  mov     [rsp+40h+phkResult], rax; phkResult
0x18004b323  mov     r9d, 2001Fh; samDesired
0x18004b329  xor     r8d, r8d; ulOptions
0x18004b32c  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18004b330  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004b337  call    cs:__imp_RegOpenKeyExW
0x18004b33d  mov     ebx, eax
0x18004b33f  test    eax, eax
0x18004b341  jnz     loc_18004B3E9
0x18004b347  mov     rcx, [rbp+lpSubKey]; pv
0x18004b34b  test    rcx, rcx
0x18004b34e  jz      short loc_18004B365
0x18004b350  call    cs:__imp_CoTaskMemFree
0x18004b356  jmp     short loc_18004B365
0x18004b358  lea     rcx, [rbp+lpSubKey]
0x18004b35c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18004b361  test    ebx, ebx
0x18004b363  js      short loc_18004B39C
0x18004b365  lea     rax, [rbp+arg_0]
0x18004b369  mov     [rsp+40h+pcbData], rax; pcbData
0x18004b36e  mov     [rsp+40h+pvData], rsi; pvData
0x18004b373  mov     [rsp+40h+phkResult], 0; pdwType
0x18004b37c  mov     r9d, 20000008h; dwFlags
0x18004b382  lea     r8, aOobecompleteti; "OOBECompleteTimestamp"
0x18004b389  xor     edx, edx; lpSubKey
0x18004b38b  mov     rcx, [rbp+hkey]; hkey
0x18004b38f  call    cs:__imp_RegGetValueW
0x18004b395  test    eax, eax
0x18004b397  setz    al
0x18004b39a  mov     [rdi], al
0x18004b39c  cmp     byte ptr [rdi], 0
0x18004b39f  jz      short loc_18004B3FD
0x18004b3a1  mov     rcx, [rbp+hkey]; hKey
0x18004b3a5  test    rcx, rcx
0x18004b3a8  jz      short loc_18004B3B0
0x18004b3aa  call    cs:__imp_RegCloseKey
0x18004b3b0  xor     eax, eax
0x18004b3b2  mov     rbx, [rsp+40h+arg_8]
0x18004b3b7  add     rsp, 40h
0x18004b3bb  pop     rdi
0x18004b3bc  pop     rsi
0x18004b3bd  pop     rbp
0x18004b3be  retn
0x18004b3bf  mov     rcx, [rbp+18h]; this
0x18004b3c3  mov     r9d, eax; char *
0x18004b3c6  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x18004b3cd  mov     edx, 16h; void *
0x18004b3d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b3d7  nop
0x18004b3d8  mov     rcx, [rbp+lpSubKey]; pv
0x18004b3dc  test    rcx, rcx
0x18004b3df  jz      short loc_18004B39C
0x18004b3e1  call    cs:__imp_CoTaskMemFree
0x18004b3e7  jmp     short loc_18004B39C
0x18004b3e9  jle     loc_18004B358
0x18004b3ef  movzx   ebx, ax
0x18004b3f2  or      ebx, 80070000h
0x18004b3f8  jmp     loc_18004B358
0x18004b3fd  mov     [rbp+arg_0], 10h
0x18004b404  lea     rax, [rbp+arg_0]
0x18004b408  mov     [rsp+40h+pcbData], rax; pcbData
0x18004b40d  mov     [rsp+40h+pvData], rsi; pvData
0x18004b412  mov     [rsp+40h+phkResult], 0; pdwType
0x18004b41b  mov     r9d, 20000008h; dwFlags
0x18004b421  lea     r8, aEndtimestamp; "EndTimeStamp"
0x18004b428  lea     rdx, aSoftwareMicros_55; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004b42f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004b436  call    cs:__imp_RegGetValueW
0x18004b43c  test    eax, eax
0x18004b43e  setz    al
0x18004b441  mov     [rdi], al
0x18004b443  jmp     loc_18004B3A1
```
