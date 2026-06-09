# MyRegisterAppId(ushort const *)

- ea: `0x140003a88`
- end: `0x140003c3e`
- name: `?MyRegisterAppId@@YAJPEBG@Z`
- size: `438`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140005c80`

## callees

- `0x140001490`
- `0x140001e30`
- `0x140003298`
- `0x1400033b4`
- `0x140003a88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140003b1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140003b1a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003b3b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140003b3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003ad5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003ba0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003bf4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003ba0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003bf4`

## pseudocode

```c
__int64 __fastcall MyRegisterAppId(const unsigned __int16 *a1)
{
  HKEY v1; // rbx
  DWORD FullPathNameW; // eax
  unsigned __int16 *v3; // r9
  unsigned __int16 *v4; // r9
  int v5; // eax
  HKEY v6; // rdi
  __int64 v7; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v12; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  v12 = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, 0x20019u, &v12) )
  {
    v1 = v12;
    memset_0(Filename, 0, 0x20Au);
    FilePart = (LPWSTR)qword_140008A50;
    if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
    {
      FullPathNameW = GetFullPathNameW(Filename, 0x104u, Buffer, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x105 )
        {
          memset(hKey, 0, 24);
          if ( !(unsigned int)ATL::CRegKey::Create(hKey, v1, FilePart, v3, phkResult) )
            RegSetValueExW(hKey[0], L"AppID", 0, 1u, L"{4F0AC159-5804-4aa7-AE91-117D6E67BB9B}", 0x4Eu);
          v5 = ATL::CRegKey::Create(hKey, v1, L"{4F0AC159-5804-4aa7-AE91-117D6E67BB9B}", v4, phkResulta);
          v6 = hKey[0];
          if ( !v5 )
          {
            if ( !FilePart )
              ATL::AtlThrowImpl(-2147467259);
            v7 = -1;
            do
              ++v7;
            while ( FilePart[v7] );
            RegSetValueExW(hKey[0], 0, 0, 1u, (const BYTE *)FilePart, 2 * v7 + 2);
          }
          if ( v6 )
            RegCloseKey(v6);
        }
      }
    }
    if ( v1 )
      RegCloseKey(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x140003a88  push    rbp
0x140003a8a  push    rbx
0x140003a8b  push    rsi
0x140003a8c  push    rdi
0x140003a8d  lea     rbp, [rsp-3A8h]
0x140003a95  sub     rsp, 4A8h
0x140003a9c  mov     rax, cs:__security_cookie
0x140003aa3  xor     rax, rsp
0x140003aa6  mov     [rbp+3C0h+var_30], rax
0x140003aad  lea     rax, [rsp+4C0h+var_478]
0x140003ab2  xor     esi, esi
0x140003ab4  mov     r9d, 20019h; samDesired
0x140003aba  mov     [rsp+4C0h+var_478], rsi
0x140003abf  xor     r8d, r8d; ulOptions
0x140003ac2  mov     [rsp+4C0h+phkResult], rax; unsigned int
0x140003ac7  lea     rdx, SubKey; "AppID"
0x140003ace  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140003ad5  call    cs:__imp_RegOpenKeyExW
0x140003adb  test    eax, eax
0x140003add  jnz     loc_140003C16
0x140003ae3  mov     rbx, [rsp+4C0h+var_478]
0x140003ae8  lea     rcx, [rsp+4C0h+Filename]; void *
0x140003aed  xor     edx, edx; Val
0x140003aef  mov     r8d, 20Ah; Size
0x140003af5  call    memset_0
0x140003afa  mov     rcx, cs:hModule; hModule
0x140003b01  lea     rax, qword_140008A50
0x140003b08  mov     edi, 104h
0x140003b0d  mov     [rsp+4C0h+FilePart], rax
0x140003b12  mov     r8d, edi; nSize
0x140003b15  lea     rdx, [rsp+4C0h+Filename]; lpFilename
0x140003b1a  call    cs:__imp_GetModuleFileNameW
0x140003b20  test    eax, eax
0x140003b22  jz      loc_140003C08
0x140003b28  lea     r9, [rsp+4C0h+FilePart]; lpFilePart
0x140003b2d  mov     edx, edi; nBufferLength
0x140003b2f  lea     r8, [rbp+3C0h+Buffer]; lpBuffer
0x140003b36  lea     rcx, [rsp+4C0h+Filename]; lpFileName
0x140003b3b  call    cs:__imp_GetFullPathNameW
0x140003b41  test    eax, eax
0x140003b43  jz      loc_140003C08
0x140003b49  cmp     eax, 105h
0x140003b4e  jnb     loc_140003C08
0x140003b54  mov     r8, [rsp+4C0h+FilePart]; unsigned __int16 *
0x140003b59  lea     rcx, [rsp+4C0h+hKey]; this
0x140003b5e  mov     rdx, rbx; HKEY
0x140003b61  mov     [rsp+4C0h+hKey], rsi
0x140003b66  mov     [rsp+4C0h+var_468], rsi
0x140003b6b  mov     [rsp+4C0h+var_460], rsi
0x140003b70  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140003b75  lea     rdi, Data; "{4F0AC159-5804-4aa7-AE91-117D6E67BB9B}"
0x140003b7c  test    eax, eax
0x140003b7e  jnz     short loc_140003BA6
0x140003b80  mov     rcx, [rsp+4C0h+hKey]; hKey
0x140003b85  lea     r9d, [rsi+1]; dwType
0x140003b89  mov     [rsp+4C0h+cbData], 4Eh ; 'N'; unsigned int
0x140003b91  lea     rdx, SubKey; "AppID"
0x140003b98  xor     r8d, r8d; Reserved
0x140003b9b  mov     [rsp+4C0h+phkResult], rdi; unsigned int
0x140003ba0  call    cs:__imp_RegSetValueExW
0x140003ba6  mov     r8, rdi; unsigned __int16 *
0x140003ba9  lea     rcx, [rsp+4C0h+hKey]; this
0x140003bae  mov     rdx, rbx; HKEY
0x140003bb1  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140003bb6  mov     rdi, [rsp+4C0h+hKey]
0x140003bbb  test    eax, eax
0x140003bbd  jnz     short loc_140003BFA
0x140003bbf  mov     rcx, [rsp+4C0h+FilePart]
0x140003bc4  test    rcx, rcx
0x140003bc7  jz      short loc_140003C33
0x140003bc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003bcd  inc     rax
0x140003bd0  cmp     [rcx+rax*2], si
0x140003bd4  jnz     short loc_140003BCD
0x140003bd6  lea     eax, ds:2[rax*2]
0x140003bdd  mov     r9d, 1; dwType
0x140003be3  mov     [rsp+4C0h+cbData], eax; cbData
0x140003be7  xor     r8d, r8d; Reserved
0x140003bea  mov     [rsp+4C0h+phkResult], rcx; lpData
0x140003bef  xor     edx, edx; lpValueName
0x140003bf1  mov     rcx, rdi; hKey
0x140003bf4  call    cs:__imp_RegSetValueExW
0x140003bfa  test    rdi, rdi
0x140003bfd  jz      short loc_140003C08
0x140003bff  mov     rcx, rdi; hKey
0x140003c02  call    cs:__imp_RegCloseKey
0x140003c08  test    rbx, rbx
0x140003c0b  jz      short loc_140003C16
0x140003c0d  mov     rcx, rbx; hKey
0x140003c10  call    cs:__imp_RegCloseKey
0x140003c16  xor     eax, eax
0x140003c18  mov     rcx, [rbp+3C0h+var_30]
0x140003c1f  xor     rcx, rsp; StackCookie
0x140003c22  call    __security_check_cookie
0x140003c27  add     rsp, 4A8h
0x140003c2e  pop     rdi
0x140003c2f  pop     rsi
0x140003c30  pop     rbx
0x140003c31  pop     rbp
0x140003c32  retn
0x140003c33  mov     ecx, 80004005h; int
0x140003c38  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
