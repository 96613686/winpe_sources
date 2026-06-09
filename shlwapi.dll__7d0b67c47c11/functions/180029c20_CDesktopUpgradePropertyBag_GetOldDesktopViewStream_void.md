# CDesktopUpgradePropertyBag::_GetOldDesktopViewStream(void)

- ea: `0x180029c20`
- end: `0x180029d59`
- name: `?_GetOldDesktopViewStream@CDesktopUpgradePropertyBag@@AEAAPEAUIStream@@XZ`
- size: `313`
- prototype: `struct IStream *__fastcall(CDesktopUpgradePropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029800`

## callees

- `0x180005220`
- `0x180012550`
- `0x180029c20`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d38`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180029c8e`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x180029c8e`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180029d2f`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180029d2f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180029cca`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180029cca`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180029cab`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180029cfa`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180029cab`
- `api-ms-win-shcore-stream-l1-1-0!SHOpenRegStream2W` at `0x180029cfa`

## pseudocode

```c
struct IStream *__fastcall CDesktopUpgradePropertyBag::_GetOldDesktopViewStream(CDesktopUpgradePropertyBag *this)
{
  IStream *v1; // rbx
  HKEY v2; // rdi
  IStream *v3; // rax
  ULARGE_INTEGER pui; // [rsp+30h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  v2 = SHGetShellKeyEx(1, L"Streams\\Desktop", 0, 0x2001Fu);
  if ( v2 )
  {
    pui.LowPart = 0;
    pcbData = 4;
    if ( !SHGetValueW(v2, 0, L"Upgrade", 0, &pui, &pcbData) )
    {
LABEL_9:
      RegCloseKey(v2);
      return v1;
    }
    v3 = SHOpenRegStream2W(v2, 0, L"ViewView2", 0);
    v1 = v3;
    if ( v3 )
    {
      pui.QuadPart = 0;
      if ( IStream_Size(v3, &pui) < 0 || pui.QuadPart )
        goto LABEL_8;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v1 + 16LL))(v1);
    }
    v1 = SHOpenRegStream2W(v2, 0, L"ViewView", 0);
LABEL_8:
    pui.LowPart = 1;
    SHSetValueW(v2, 0, L"Upgrade", 4u, &pui, 4u);
    goto LABEL_9;
  }
  return v1;
}

```

## disassembly

```asm
0x180029c20  mov     [rsp+arg_0], rbx
0x180029c25  push    rdi
0x180029c26  sub     rsp, 50h
0x180029c2a  mov     rax, cs:__security_cookie
0x180029c31  xor     rax, rsp
0x180029c34  mov     [rsp+58h+var_18], rax
0x180029c39  xor     ebx, ebx
0x180029c3b  lea     rdx, aStreamsDesktop; "Streams\\Desktop"
0x180029c42  mov     r9d, 2001Fh
0x180029c48  xor     r8d, r8d
0x180029c4b  lea     ecx, [rbx+1]
0x180029c4e  call    SHGetShellKeyEx
0x180029c53  mov     rdi, rax
0x180029c56  test    rax, rax
0x180029c59  jz      loc_180029D3E
0x180029c5f  lea     rax, [rsp+58h+var_20]
0x180029c64  mov     dword ptr [rsp+58h+pui], ebx
0x180029c68  mov     [rsp+58h+pcbData], rax; pcbData
0x180029c6d  lea     r8, aUpgrade; "Upgrade"
0x180029c74  lea     rax, [rsp+58h+pui]
0x180029c79  mov     [rsp+58h+var_20], 4
0x180029c81  xor     r9d, r9d; pdwType
0x180029c84  mov     [rsp+58h+pvData], rax; pvData
0x180029c89  xor     edx, edx; pszSubKey
0x180029c8b  mov     rcx, rdi; hkey
0x180029c8e  call    cs:__imp_SHGetValueW
0x180029c94  test    eax, eax
0x180029c96  jz      loc_180029D35
0x180029c9c  xor     r9d, r9d; grfMode
0x180029c9f  lea     r8, aViewview2; "ViewView2"
0x180029ca6  xor     edx, edx; pszSubkey
0x180029ca8  mov     rcx, rdi; hkey
0x180029cab  call    cs:__imp_SHOpenRegStream2W
0x180029cb1  mov     rbx, rax
0x180029cb4  test    rax, rax
0x180029cb7  jz      short loc_180029CEB
0x180029cb9  lea     rdx, [rsp+58h+pui]; pui
0x180029cbe  mov     qword ptr [rsp+58h+pui], 0
0x180029cc7  mov     rcx, rax; pstm
0x180029cca  call    cs:__imp_IStream_Size
0x180029cd0  test    eax, eax
0x180029cd2  js      short loc_180029D03
0x180029cd4  cmp     qword ptr [rsp+58h+pui], 0
0x180029cda  jnz     short loc_180029D03
0x180029cdc  mov     rax, [rbx]
0x180029cdf  mov     rcx, rbx
0x180029ce2  mov     rax, [rax+10h]
0x180029ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ceb  xor     r9d, r9d; grfMode
0x180029cee  lea     r8, aViewview; "ViewView"
0x180029cf5  xor     edx, edx; pszSubkey
0x180029cf7  mov     rcx, rdi; hkey
0x180029cfa  call    cs:__imp_SHOpenRegStream2W
0x180029d00  mov     rbx, rax
0x180029d03  lea     rax, [rsp+58h+pui]
0x180029d08  mov     dword ptr [rsp+58h+pcbData], 4; cbData
0x180029d10  mov     r9d, 4; dwType
0x180029d16  mov     [rsp+58h+pvData], rax; pvData
0x180029d1b  lea     r8, aUpgrade; "Upgrade"
0x180029d22  mov     dword ptr [rsp+58h+pui], 1
0x180029d2a  xor     edx, edx; pszSubKey
0x180029d2c  mov     rcx, rdi; hkey
0x180029d2f  call    cs:__imp_SHSetValueW
0x180029d35  mov     rcx, rdi; hKey
0x180029d38  call    cs:__imp_RegCloseKey
0x180029d3e  mov     rax, rbx
0x180029d41  mov     rcx, [rsp+58h+var_18]
0x180029d46  xor     rcx, rsp; StackCookie
0x180029d49  call    __security_check_cookie
0x180029d4e  mov     rbx, [rsp+58h+arg_0]
0x180029d53  add     rsp, 50h
0x180029d57  pop     rdi
0x180029d58  retn
```
