# ShutdownContinuation

- ea: `0x180011440`
- end: `0x180011647`
- name: `ShutdownContinuation`
- size: `519`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000738c`
- `0x18000e700`
- `0x180011130`
- `0x180011440`
- `0x18001bf40`
- `0x18001c3c8`
- `0x1800435a0`
- `0x1800456c8`
- `0x180052aa4`
- `0x180053050`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x180011514`
- `KERNEL32!DebugBreak` at `0x180011514`
- `ntdll!WinSqmAddToStream` at `0x1800115de`
- `ntdll!WinSqmAddToStream` at `0x1800115de`
- `ole32!CoTaskMemFree` at `0x1800115f6`
- `ole32!CoTaskMemFree` at `0x1800115f6`
- `ADVAPI32!RegCloseKey` at `0x1800114c0`
- `ADVAPI32!RegCloseKey` at `0x180011542`
- `ADVAPI32!RegCloseKey` at `0x180011620`
- `ADVAPI32!RegCloseKey` at `0x1800114c0`
- `ADVAPI32!RegCloseKey` at `0x180011542`
- `ADVAPI32!RegCloseKey` at `0x180011620`
- `ADVAPI32!RegOpenKeyExW` at `0x1800114ea`
- `ADVAPI32!RegOpenKeyExW` at `0x1800114ea`

## pseudocode

```c
LSTATUS __fastcall ShutdownContinuation(__int64 a1)
{
  int v2; // ebx
  void *v3; // rcx
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-19h] BYREF
  int v6; // [rsp+38h] [rbp-11h]
  LPVOID pv; // [rsp+40h] [rbp-9h] BYREF
  __int64 v8[2]; // [rsp+48h] [rbp-1h] BYREF
  LPCWSTR lpszVolumeName[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v10; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v11; // [rsp+70h] [rbp+27h]
  int v12; // [rsp+78h] [rbp+2Fh]
  __int64 v13; // [rsp+80h] [rbp+37h]
  int v14; // [rsp+88h] [rbp+3Fh]
  __int64 v15; // [rsp+90h] [rbp+47h]

  v10 = 1;
  hKey = 0;
  lpszVolumeName[0] = (LPCWSTR)qword_1800654F0;
  lpszVolumeName[1] = 0;
  v8[0] = (__int64)qword_1800654F0;
  v8[1] = 0;
  v6 = 0;
  pv = 0;
  v11 = 0;
  v13 = 0;
  v15 = 0;
  v12 = 1;
  v14 = 1;
  sub_180011130();
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
          0,
          0x2001Fu,
          &hKey) )
  {
    if ( !(unsigned int)sub_1800456C8(hKey, L"Debug") && v6 )
      DebugBreak();
    sub_1800456C8(hKey, L"BreakOnAV");
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (int)sub_1800435A0(L"%SystemRoot%", lpszVolumeName, v8) >= 0 )
    sub_18001BF40(lpszVolumeName[0], v8[0], &pv);
  v2 = sub_18000E700(a1, pv);
  if ( v2 < 0 && RequestContext != &RequestContext && (*((_DWORD *)RequestContext + 7) & 0x2000000) != 0 )
    sub_18000738C(*((_QWORD *)RequestContext + 2), 67, &stru_18005CE08, (unsigned int)v2);
  LODWORD(v13) = v2;
  LODWORD(v15) = 1;
  LODWORD(v11) = v2 == 0;
  WinSqmAddToStream(0, 4253, 3, &v10);
  v3 = pv;
  if ( pv )
  {
    sub_18001C3C8((LPCWSTR)pv);
    v3 = pv;
  }
  CoTaskMemFree(v3);
  pv = 0;
  sub_180052AA4(v8);
  sub_180052AA4(lpszVolumeName);
  result = (_DWORD)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180011440  mov     [rsp-8+arg_8], rbx
0x180011445  mov     [rsp-8+arg_10], rdi
0x18001144a  push    rbp
0x18001144b  lea     rbp, [rsp-57h]
0x180011450  sub     rsp, 0A0h
0x180011457  mov     rax, cs:__security_cookie
0x18001145e  xor     rax, rsp
0x180011461  mov     [rbp+57h+var_8], rax
0x180011465  xor     edi, edi
0x180011467  mov     [rbp+57h+var_38], 1
0x18001146e  lea     rax, qword_1800654F0
0x180011475  mov     [rbp+57h+hKey], rdi
0x180011479  mov     [rbp+57h+lpszVolumeName], rax
0x18001147d  mov     rbx, rcx
0x180011480  mov     [rbp+57h+var_40], rdi
0x180011484  mov     [rbp+57h+var_58], rax
0x180011488  mov     [rbp+57h+var_50], rdi
0x18001148c  mov     [rbp+57h+var_68], edi
0x18001148f  mov     [rbp+57h+pv], rdi
0x180011493  mov     [rbp+57h+var_30], rdi
0x180011497  mov     [rbp+57h+var_20], rdi
0x18001149b  mov     [rbp+57h+var_10], rdi
0x18001149f  mov     [rbp+57h+var_28], 1
0x1800114a6  mov     [rbp+57h+var_18], 1
0x1800114ad  call    sub_180011130
0x1800114b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800114b6  lea     rax, [rcx-1]
0x1800114ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800114be  ja      short loc_1800114CA
0x1800114c0  call    cs:RegCloseKey
0x1800114c6  mov     [rbp+57h+hKey], rdi
0x1800114ca  lea     rax, [rbp+57h+hKey]
0x1800114ce  mov     r9d, 2001Fh; samDesired
0x1800114d4  xor     r8d, r8d; ulOptions
0x1800114d7  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800114dc  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800114e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800114ea  call    cs:RegOpenKeyExW
0x1800114f0  test    eax, eax
0x1800114f2  jnz     short loc_180011534
0x1800114f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800114f8  lea     r8, [rbp+57h+var_68]
0x1800114fc  xor     r9d, r9d
0x1800114ff  lea     rdx, aDebug; "Debug"
0x180011506  call    sub_1800456C8
0x18001150b  test    eax, eax
0x18001150d  jnz     short loc_18001151A
0x18001150f  cmp     [rbp+57h+var_68], edi
0x180011512  jz      short loc_18001151A
0x180011514  call    cs:__imp_DebugBreak
0x18001151a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001151e  lea     r8, dword_18006B8C8
0x180011525  xor     r9d, r9d
0x180011528  lea     rdx, aBreakonav; "BreakOnAV"
0x18001152f  call    sub_1800456C8
0x180011534  mov     rcx, [rbp+57h+hKey]; hKey
0x180011538  lea     rax, [rcx-1]
0x18001153c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011540  ja      short loc_18001154C
0x180011542  call    cs:RegCloseKey
0x180011548  mov     [rbp+57h+hKey], rdi
0x18001154c  lea     r8, [rbp+57h+var_58]
0x180011550  lea     rdx, [rbp+57h+lpszVolumeName]
0x180011554  lea     rcx, aSystemroot; "%SystemRoot%"
0x18001155b  call    sub_1800435A0
0x180011560  test    eax, eax
0x180011562  js      short loc_180011575
0x180011564  mov     rdx, [rbp+57h+var_58]
0x180011568  lea     r8, [rbp+57h+pv]
0x18001156c  mov     rcx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x180011570  call    sub_18001BF40
0x180011575  mov     rdx, [rbp+57h+pv]
0x180011579  mov     rcx, rbx
0x18001157c  call    sub_18000E700
0x180011581  mov     ebx, eax
0x180011583  test    eax, eax
0x180011585  jns     short loc_1800115BB
0x180011587  mov     rcx, cs:RequestContext
0x18001158e  lea     rax, RequestContext
0x180011595  cmp     rcx, rax
0x180011598  jz      short loc_1800115BB
0x18001159a  test    dword ptr [rcx+1Ch], 2000000h
0x1800115a1  jz      short loc_1800115BB
0x1800115a3  mov     rcx, [rcx+10h]
0x1800115a7  lea     r8, stru_18005CE08
0x1800115ae  mov     edx, 43h ; 'C'
0x1800115b3  mov     r9d, ebx
0x1800115b6  call    sub_18000738C
0x1800115bb  mov     eax, edi
0x1800115bd  mov     dword ptr [rbp+57h+var_20], ebx
0x1800115c0  test    ebx, ebx
0x1800115c2  mov     dword ptr [rbp+57h+var_10], 1
0x1800115c9  lea     r9, [rbp+57h+var_38]
0x1800115cd  mov     edx, 109Dh
0x1800115d2  setz    al
0x1800115d5  xor     ecx, ecx
0x1800115d7  mov     dword ptr [rbp+57h+var_30], eax
0x1800115da  lea     r8d, [rcx+3]
0x1800115de  call    cs:WinSqmAddToStream
0x1800115e4  mov     rcx, [rbp+57h+pv]; lpFileName
0x1800115e8  test    rcx, rcx
0x1800115eb  jz      short loc_1800115F6
0x1800115ed  call    sub_18001C3C8
0x1800115f2  mov     rcx, [rbp+57h+pv]; pv
0x1800115f6  call    cs:__imp_CoTaskMemFree
0x1800115fc  lea     rcx, [rbp+57h+var_58]
0x180011600  mov     [rbp+57h+pv], rdi
0x180011604  call    sub_180052AA4
0x180011609  lea     rcx, [rbp+57h+lpszVolumeName]
0x18001160d  call    sub_180052AA4
0x180011612  mov     rcx, [rbp+57h+hKey]; hKey
0x180011616  lea     rax, [rcx-1]
0x18001161a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001161e  ja      short loc_180011626
0x180011620  call    cs:RegCloseKey
0x180011626  mov     rcx, [rbp+57h+var_8]
0x18001162a  xor     rcx, rsp; StackCookie
0x18001162d  call    __security_check_cookie
0x180011632  lea     r11, [rsp+0A0h+var_s0]
0x18001163a  mov     rbx, [r11+18h]
0x18001163e  mov     rdi, [r11+20h]
0x180011642  mov     rsp, r11
0x180011645  pop     rbp
0x180011646  retn
```
