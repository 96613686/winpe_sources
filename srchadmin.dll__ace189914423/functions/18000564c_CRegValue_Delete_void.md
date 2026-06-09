# CRegValue::Delete(void)

- ea: `0x18000564c`
- end: `0x1800056d8`
- name: `?Delete@CRegValue@@QEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(CRegValue *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800056e0`
- `0x180012870`
- `0x180012a30`
- `0x180012c00`
- `0x180012de0`
- `0x180012e40`
- `0x180012ef0`

## callees

- `0x18000564c`
- `0x1800057a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005681`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005681`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005696`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005696`

## pseudocode

```c
__int64 __fastcall CRegValue::Delete(CRegValue *this)
{
  LSTATUS v1; // ebx
  const WCHAR *v3; // rdx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  if ( !*(_DWORD *)this )
    return (unsigned int)v1;
  v3 = (const WCHAR *)*((_QWORD *)this + 2);
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x2000000u, &hKey);
  if ( !v1 )
    v1 = RegDeleteValueW(hKey, *((LPCWSTR *)this + 1));
  if ( (unsigned int)(v1 - 2) > 1 )
  {
    if ( v1 )
      goto LABEL_8;
  }
  else
  {
    v1 = 0;
  }
  *(_DWORD *)this = 0;
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( v1 > 0 )
    return (unsigned __int16)v1 | 0x80070000;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000564c  mov     r11, rsp
0x18000564f  mov     [r11+10h], rbx
0x180005653  push    rdi
0x180005654  sub     rsp, 30h
0x180005658  xor     ebx, ebx
0x18000565a  mov     rdi, rcx
0x18000565d  cmp     [rcx], ebx
0x18000565f  jz      short loc_1800056CB
0x180005661  mov     rdx, [rcx+10h]; lpSubKey
0x180005665  lea     rax, [r11+8]
0x180005669  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005670  mov     [r11-18h], rax
0x180005674  mov     r9d, 2000000h; samDesired
0x18000567a  mov     [r11+8], rbx
0x18000567e  xor     r8d, r8d; ulOptions
0x180005681  call    cs:__imp_RegOpenKeyExW
0x180005687  mov     ebx, eax
0x180005689  test    eax, eax
0x18000568b  jnz     short loc_18000569E
0x18000568d  mov     rdx, [rdi+8]; lpValueName
0x180005691  mov     rcx, [rsp+38h+hKey]; hKey
0x180005696  call    cs:__imp_RegDeleteValueW
0x18000569c  mov     ebx, eax
0x18000569e  lea     eax, [rbx-2]
0x1800056a1  cmp     eax, 1
0x1800056a4  ja      short loc_1800056AA
0x1800056a6  xor     ebx, ebx
0x1800056a8  jmp     short loc_1800056AE
0x1800056aa  test    ebx, ebx
0x1800056ac  jnz     short loc_1800056B4
0x1800056ae  mov     dword ptr [rdi], 0
0x1800056b4  lea     rcx, [rsp+38h+hKey]
0x1800056b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800056be  test    ebx, ebx
0x1800056c0  jle     short loc_1800056CB
0x1800056c2  movzx   ebx, bx
0x1800056c5  or      ebx, 80070000h
0x1800056cb  mov     eax, ebx
0x1800056cd  mov     rbx, [rsp+38h+arg_8]
0x1800056d2  add     rsp, 30h
0x1800056d6  pop     rdi
0x1800056d7  retn
```
