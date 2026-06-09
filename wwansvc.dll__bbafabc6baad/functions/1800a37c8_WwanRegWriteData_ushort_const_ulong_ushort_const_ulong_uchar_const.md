# WwanRegWriteData(ushort const *,ulong,ushort const *,ulong,uchar const *)

- ea: `0x1800a37c8`
- end: `0x1800a38bc`
- name: `?WwanRegWriteData@@YAKPEBGK0KPEBE@Z`
- size: `244`
- prototype: `unsigned int __usercall@<eax>(LPCWSTR lpSubKey@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18009e7ac`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a37c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a382e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a382e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a388f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a388f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3865`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a3865`

## string_xrefs

- `0x1800a383a`: `RegCreateKeyEx failed, dwError (0x%8x)`
- `0x1800a37d4`: `WwanRegWriteData`
- `0x1800a3871`: `RegSetValueEx failed, dwError (0x%8x)`

## pseudocode

```c
__int64 __fastcall WwanRegWriteData(LPCWSTR lpSubKey, __int64 a2, const unsigned __int16 *a3, DWORD a4, BYTE *lpData)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  WwanLog::Enter("WwanRegWriteData");
  hKey = 0;
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v9 = v8;
  if ( v8 )
  {
    WwanLog::Error("WwanRegWriteData", 0, L"RegCreateKeyEx failed, dwError (0x%8x)", v8);
  }
  else
  {
    v10 = RegSetValueExW(hKey, a3, 0, 3u, lpData, a4);
    v9 = v10;
    if ( v10 )
      WwanLog::Error("WwanRegWriteData", 0, L"RegSetValueEx failed, dwError (0x%8x)", v10);
  }
  if ( hKey )
    RegCloseKey(hKey);
  WwanLog::Verbose("WwanRegWriteData", 0, L"dwError (0x%8x)", v9);
  WwanLog::Exit("WwanRegWriteData");
  return v9;
}

```

## disassembly

```asm
0x1800a37c8  push    rbx
0x1800a37ca  push    rbp
0x1800a37cb  push    rsi
0x1800a37cc  push    rdi
0x1800a37cd  sub     rsp, 68h
0x1800a37d1  mov     rbx, rcx
0x1800a37d4  lea     rbp, aWwanregwriteda; "WwanRegWriteData"
0x1800a37db  mov     rcx, rbp; char *
0x1800a37de  mov     edi, r9d
0x1800a37e1  mov     rsi, r8
0x1800a37e4  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a37e9  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800a37f2  lea     rax, [rsp+88h+hKey]
0x1800a37f7  mov     [rsp+88h+phkResult], rax; phkResult
0x1800a37fc  xor     r9d, r9d; lpClass
0x1800a37ff  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a3808  xor     r8d, r8d; Reserved
0x1800a380b  mov     [rsp+88h+samDesired], 20006h; samDesired
0x1800a3813  mov     rdx, rbx; lpSubKey
0x1800a3816  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a381d  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800a3825  mov     [rsp+88h+hKey], 0
0x1800a382e  call    cs:__imp_RegCreateKeyExW
0x1800a3834  mov     ebx, eax
0x1800a3836  test    eax, eax
0x1800a3838  jz      short loc_1800A3843
0x1800a383a  lea     r8, aRegcreatekeyex; "RegCreateKeyEx failed, dwError (0x%8x)"
0x1800a3841  jmp     short loc_1800A3878
0x1800a3843  mov     rax, [rsp+88h+lpData]
0x1800a384b  mov     r9d, 3; dwType
0x1800a3851  mov     rcx, [rsp+88h+hKey]; hKey
0x1800a3856  xor     r8d, r8d; Reserved
0x1800a3859  mov     [rsp+88h+samDesired], edi; cbData
0x1800a385d  mov     rdx, rsi; lpValueName
0x1800a3860  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800a3865  call    cs:__imp_RegSetValueExW
0x1800a386b  mov     ebx, eax
0x1800a386d  test    eax, eax
0x1800a386f  jz      short loc_1800A3885
0x1800a3871  lea     r8, aRegsetvalueexF; "RegSetValueEx failed, dwError (0x%8x)"
0x1800a3878  mov     r9d, eax
0x1800a387b  xor     edx, edx; struct _GUID *
0x1800a387d  mov     rcx, rbp; char *
0x1800a3880  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3885  mov     rcx, [rsp+88h+hKey]; hKey
0x1800a388a  test    rcx, rcx
0x1800a388d  jz      short loc_1800A3895
0x1800a388f  call    cs:__imp_RegCloseKey
0x1800a3895  mov     r9d, ebx
0x1800a3898  lea     r8, aDwerror0x8x; "dwError (0x%8x)"
0x1800a389f  xor     edx, edx; struct _GUID *
0x1800a38a1  mov     rcx, rbp; char *
0x1800a38a4  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800a38a9  mov     rcx, rbp; char *
0x1800a38ac  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a38b1  mov     eax, ebx
0x1800a38b3  add     rsp, 68h
0x1800a38b7  pop     rdi
0x1800a38b8  pop     rsi
0x1800a38b9  pop     rbp
0x1800a38ba  pop     rbx
0x1800a38bb  retn
```
