# DUIFramework_DisplayHelpDialog(ushort const *,ushort const *)

- ea: `0x180052be0`
- end: `0x180052d39`
- name: `?DUIFramework_DisplayHelpDialog@@YAJPEBG0@Z`
- size: `345`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036314`

## callees

- `0x180007fd8`
- `0x18000809c`
- `0x180052be0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180052c90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052cf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052cf3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052c73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052c73`
- `ntdll!WinSqmAddToStream` at `0x180052c41`
- `ntdll!WinSqmAddToStream` at `0x180052c41`
- `USER32!SetCursor` at `0x180052c0a`
- `USER32!SetCursor` at `0x180052d1a`
- `USER32!SetCursor` at `0x180052c0a`
- `USER32!SetCursor` at `0x180052d1a`
- `USER32!LoadCursorW` at `0x180052bfb`
- `USER32!LoadCursorW` at `0x180052bfb`

## pseudocode

```c
__int64 __fastcall DUIFramework_DisplayHelpDialog(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // rsi
  HRESULT v4; // ebx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned int v7; // r11d
  int v9; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-10h]
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  ppv = a2;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = 2;
  v3 = SetCursor(CursorW);
  v10 = L"PERSONALIZATION_THEMES_HELP_BUTTON_WHAT_AERO_STYLES";
  WinSqmAddToStream(0, 911, 1, &v9);
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v4 >= 0 )
  {
    v5 = (unsigned __int16 *)LocalAlloc(0, 0x74u);
    v6 = v5;
    if ( v5 )
    {
      v4 = StringCchCopyW(v5, 0x3Au, L"mshelp://windows/?id=");
      if ( v4 >= 0 )
      {
        v4 = StringCchCatW(v6, v7, L"22CE1F24-0318-46BD-BC17-D0EF889F466B");
        if ( v4 >= 0 )
          v4 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v6);
      }
      LocalFree(v6);
    }
    else
    {
      v4 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SetCursor(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180052be0  mov     [rsp+arg_0], rbx
0x180052be5  mov     [rsp+arg_10], rsi
0x180052bea  mov     [rsp+arg_8], rdx
0x180052bef  push    rdi
0x180052bf0  sub     rsp, 40h
0x180052bf4  mov     edx, 7F02h; lpCursorName
0x180052bf9  xor     ecx, ecx; hInstance
0x180052bfb  call    cs:__imp_LoadCursorW
0x180052c02  nop     dword ptr [rax+rax+00h]
0x180052c07  mov     rcx, rax; hCursor
0x180052c0a  call    cs:__imp_SetCursor
0x180052c11  nop     dword ptr [rax+rax+00h]
0x180052c16  mov     ebx, 1
0x180052c1b  mov     [rsp+48h+var_18], 2
0x180052c23  mov     rsi, rax
0x180052c26  lea     r9, [rsp+48h+var_18]
0x180052c2b  lea     rax, aPersonalizatio_0; "PERSONALIZATION_THEMES_HELP_BUTTON_WHAT"...
0x180052c32  mov     r8d, ebx
0x180052c35  mov     edx, 38Fh
0x180052c3a  mov     [rsp+48h+var_10], rax
0x180052c3f  xor     ecx, ecx
0x180052c41  call    cs:__imp_WinSqmAddToStream
0x180052c48  nop     dword ptr [rax+rax+00h]
0x180052c4d  lea     rax, [rsp+48h+arg_8]
0x180052c52  mov     [rsp+48h+arg_8], 0
0x180052c5b  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180052c62  mov     [rsp+48h+ppv], rax; ppv
0x180052c67  mov     r8d, ebx; dwClsContext
0x180052c6a  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180052c71  xor     edx, edx; pUnkOuter
0x180052c73  call    cs:__imp_CoCreateInstance
0x180052c7a  nop     dword ptr [rax+rax+00h]
0x180052c7f  mov     ebx, eax
0x180052c81  test    eax, eax
0x180052c83  js      loc_180052D17
0x180052c89  mov     edx, 74h ; 't'; uBytes
0x180052c8e  xor     ecx, ecx; uFlags
0x180052c90  call    cs:__imp_LocalAlloc
0x180052c97  nop     dword ptr [rax+rax+00h]
0x180052c9c  mov     rdi, rax
0x180052c9f  test    rax, rax
0x180052ca2  jz      short loc_180052D01
0x180052ca4  mov     r11d, 3Ah ; ':'
0x180052caa  lea     r8, aMshelpWindowsI; "mshelp://windows/?id="
0x180052cb1  mov     edx, r11d; unsigned __int64
0x180052cb4  mov     rcx, rax; unsigned __int16 *
0x180052cb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052cbc  mov     ebx, eax
0x180052cbe  test    eax, eax
0x180052cc0  js      short loc_180052CF0
0x180052cc2  lea     r8, a22ce1f24031846; "22CE1F24-0318-46BD-BC17-D0EF889F466B"
0x180052cc9  mov     edx, r11d; unsigned __int64
0x180052ccc  mov     rcx, rdi; unsigned __int16 *
0x180052ccf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180052cd4  mov     ebx, eax
0x180052cd6  test    eax, eax
0x180052cd8  js      short loc_180052CF0
0x180052cda  mov     rcx, [rsp+48h+arg_8]
0x180052cdf  mov     rdx, rdi
0x180052ce2  mov     rax, [rcx]
0x180052ce5  mov     rax, [rax+18h]
0x180052ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cee  mov     ebx, eax
0x180052cf0  mov     rcx, rdi; hMem
0x180052cf3  call    cs:__imp_LocalFree
0x180052cfa  nop     dword ptr [rax+rax+00h]
0x180052cff  jmp     short loc_180052D06
0x180052d01  mov     ebx, 8007000Eh
0x180052d06  mov     rcx, [rsp+48h+arg_8]
0x180052d0b  mov     rax, [rcx]
0x180052d0e  mov     rax, [rax+10h]
0x180052d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d17  mov     rcx, rsi; hCursor
0x180052d1a  call    cs:__imp_SetCursor
0x180052d21  nop     dword ptr [rax+rax+00h]
0x180052d26  mov     rsi, [rsp+48h+arg_10]
0x180052d2b  mov     eax, ebx
0x180052d2d  mov     rbx, [rsp+48h+arg_0]
0x180052d32  add     rsp, 40h
0x180052d36  pop     rdi
0x180052d37  retn
```
