# GetW32TimeServer(int,ushort *,ulong)

- ea: `0x180016928`
- end: `0x180016a3d`
- name: `?GetW32TimeServer@@YAJHPEAGK@Z`
- size: `277`
- prototype: `int(int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001d1a0`

## callees

- `0x1800166b0`
- `0x180016928`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x1800169f5`
- `SHLWAPI!StrStrW` at `0x180016a0f`
- `SHLWAPI!StrStrW` at `0x1800169f5`
- `SHLWAPI!StrStrW` at `0x180016a0f`
- `SHLWAPI!SHGetValueW` at `0x1800169ce`
- `SHLWAPI!SHGetValueW` at `0x1800169ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a22`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016967`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016967`

## string_xrefs

- `0x1800169c0`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18001693f`: `w32time.dll`

## pseudocode

```c
__int64 __fastcall GetW32TimeServer(int a1, unsigned __int16 *a2, int a3)
{
  signed int v6; // ebx
  HMODULE LibraryW; // rax
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rax
  DWORD v10; // r14d
  LSTATUS v11; // eax
  PWSTR v12; // rax
  PWSTR v13; // rax
  int v15[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  v6 = -2147467259;
  LibraryW = IsolationAwareLoadLibraryW(L"w32time.dll");
  v8 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x11);
    if ( ProcAddress )
    {
      v10 = 2 * a3;
      v15[0] = 1;
      pcbData = v10;
      v6 = ((__int64 (__fastcall *)(__int64, int *, unsigned __int16 *, DWORD *))ProcAddress)(1, v15, a2, &pcbData);
      if ( v6 == -2147024769 )
      {
        pcbData = v10;
        v11 = SHGetValueW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
                L"NtpServer",
                0,
                a2,
                &pcbData);
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
      }
      if ( v6 >= 0 && a1 )
      {
        v12 = StrStrW(a2, L",0x");
        if ( v12 )
          *v12 = 0;
        v13 = StrStrW(a2, L" ");
        if ( v13 )
          *v13 = 0;
      }
    }
    FreeLibrary(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016928  mov     [rsp+arg_0], rbx
0x18001692d  mov     [rsp+arg_8], rbp
0x180016932  push    rsi
0x180016933  push    rdi
0x180016934  push    r14
0x180016936  sub     rsp, 40h
0x18001693a  mov     ebp, ecx
0x18001693c  mov     r14d, r8d
0x18001693f  lea     rcx, aW32timeDll_0; "w32time.dll"
0x180016946  mov     rdi, rdx
0x180016949  mov     ebx, 80004005h
0x18001694e  call    IsolationAwareLoadLibraryW
0x180016953  mov     rsi, rax
0x180016956  test    rax, rax
0x180016959  jz      loc_180016A28
0x18001695f  mov     edx, 11h; lpProcName
0x180016964  mov     rcx, rax; hModule
0x180016967  call    cs:__imp_GetProcAddress
0x18001696d  test    rax, rax
0x180016970  jz      loc_180016A1F
0x180016976  mov     ecx, 1
0x18001697b  lea     r9, [rsp+58h+arg_18]
0x180016980  add     r14d, r14d
0x180016983  mov     [rsp+58h+var_28], ecx
0x180016987  mov     r8, rdi
0x18001698a  mov     [rsp+58h+arg_18], r14d
0x18001698f  lea     rdx, [rsp+58h+var_28]
0x180016994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016999  mov     ebx, eax
0x18001699b  cmp     eax, 8007007Fh
0x1800169a0  jnz     short loc_1800169E3
0x1800169a2  lea     rax, [rsp+58h+arg_18]
0x1800169a7  mov     [rsp+58h+arg_18], r14d
0x1800169ac  mov     [rsp+58h+pcbData], rax; pcbData
0x1800169b1  lea     r8, aNtpserver; "NtpServer"
0x1800169b8  xor     r9d, r9d; pdwType
0x1800169bb  mov     [rsp+58h+pvData], rdi; pvData
0x1800169c0  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x1800169c7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800169ce  call    cs:__imp_SHGetValueW
0x1800169d4  mov     ebx, eax
0x1800169d6  test    eax, eax
0x1800169d8  jle     short loc_1800169E3
0x1800169da  movzx   ebx, ax
0x1800169dd  or      ebx, 80070000h
0x1800169e3  test    ebx, ebx
0x1800169e5  js      short loc_180016A1F
0x1800169e7  test    ebp, ebp
0x1800169e9  jz      short loc_180016A1F
0x1800169eb  lea     rdx, pszSrch; ",0x"
0x1800169f2  mov     rcx, rdi; pszFirst
0x1800169f5  call    cs:__imp_StrStrW
0x1800169fb  test    rax, rax
0x1800169fe  jz      short loc_180016A05
0x180016a00  xor     ecx, ecx
0x180016a02  mov     [rax], cx
0x180016a05  lea     rdx, asc_18002F1D4; " "
0x180016a0c  mov     rcx, rdi; pszFirst
0x180016a0f  call    cs:__imp_StrStrW
0x180016a15  test    rax, rax
0x180016a18  jz      short loc_180016A1F
0x180016a1a  xor     ecx, ecx
0x180016a1c  mov     [rax], cx
0x180016a1f  mov     rcx, rsi; hLibModule
0x180016a22  call    cs:__imp_FreeLibrary
0x180016a28  mov     rbp, [rsp+58h+arg_8]
0x180016a2d  mov     eax, ebx
0x180016a2f  mov     rbx, [rsp+58h+arg_0]
0x180016a34  add     rsp, 40h
0x180016a38  pop     r14
0x180016a3a  pop     rdi
0x180016a3b  pop     rsi
0x180016a3c  retn
```
