# DllUnregisterServer

- ea: `0x1800035b0`
- end: `0x180003642`
- name: `DllUnregisterServer`
- size: `146`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002fe8`
- `0x1800035b0`
- `0x180008ff4`
- `0x1800090b4`

## string_xrefs

- `0x1800035bb`: `CLSID\{84e04a55-2d42-4909-86e3-62fd11483e8b}`
- `0x1800035d5`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Temporary Setup Files`
- `0x1800035e6`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Previous Installations`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // edi
  unsigned __int64 v1; // rbx
  const WCHAR *v2; // rsi
  HKEY v3; // rbp
  int v4; // eax
  HKEY hKey; // [rsp+20h] [rbp-58h]
  LPCWSTR lpSubKey[10]; // [rsp+28h] [rbp-50h]

  hKey = HKEY_CLASSES_ROOT;
  lpSubKey[0] = L"CLSID\\{84e04a55-2d42-4909-86e3-62fd11483e8b}";
  lpSubKey[1] = (LPCWSTR)-2147483646LL;
  lpSubKey[2] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Temporary Setup Files";
  v0 = 0;
  lpSubKey[3] = (LPCWSTR)-2147483646LL;
  lpSubKey[4] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Previous Installations";
  v1 = 0;
  do
  {
    if ( v1 >= 3 )
      break;
    v2 = lpSubKey[2 * v1];
    v3 = (HKEY)lpSubKey[2 * v1 - 1];
    if ( (unsigned int)RegExists(v3, v2) )
    {
      v4 = RegDeleteRecursive(v3, v2);
      v0 = HrBool(v4);
    }
    ++v1;
  }
  while ( v0 >= 0 );
  return v0;
}

```

## disassembly

```asm
0x1800035b0  mov     r11, rsp
0x1800035b3  push    rbx
0x1800035b4  push    rbp
0x1800035b5  push    rsi
0x1800035b6  push    rdi
0x1800035b7  sub     rsp, 58h
0x1800035bb  lea     rax, aClsid84e04a552_0; "CLSID\\{84e04a55-2d42-4909-86e3-62fd114"...
0x1800035c2  mov     qword ptr [r11-58h], 0FFFFFFFF80000000h
0x1800035ca  mov     [r11-50h], rax
0x1800035ce  mov     rcx, 0FFFFFFFF80000002h
0x1800035d5  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800035dc  mov     [r11-48h], rcx
0x1800035e0  mov     [r11-40h], rax
0x1800035e4  xor     edi, edi
0x1800035e6  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800035ed  mov     [r11-38h], rcx
0x1800035f1  mov     [r11-30h], rax
0x1800035f5  xor     ebx, ebx
0x1800035f7  cmp     rbx, 3
0x1800035fb  jnb     short loc_180003637
0x1800035fd  mov     rax, rbx
0x180003600  add     rax, rax
0x180003603  mov     rsi, [rsp+rax*8+78h+lpSubKey]
0x180003608  mov     rbp, [rsp+rax*8+78h+hKey]
0x18000360d  mov     rdx, rsi
0x180003610  mov     rcx, rbp
0x180003613  call    RegExists
0x180003618  test    eax, eax
0x18000361a  jz      short loc_180003630
0x18000361c  mov     rdx, rsi; lpSubKey
0x18000361f  mov     rcx, rbp; hKey
0x180003622  call    RegDeleteRecursive
0x180003627  mov     ecx, eax; int
0x180003629  call    ?HrBool@@YAJH@Z; HrBool(int)
0x18000362e  mov     edi, eax
0x180003630  inc     rbx
0x180003633  test    edi, edi
0x180003635  jns     short loc_1800035F7
0x180003637  mov     eax, edi
0x180003639  add     rsp, 58h
0x18000363d  pop     rdi
0x18000363e  pop     rsi
0x18000363f  pop     rbp
0x180003640  pop     rbx
0x180003641  retn
```
