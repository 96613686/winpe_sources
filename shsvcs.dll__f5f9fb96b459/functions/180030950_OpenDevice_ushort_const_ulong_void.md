# OpenDevice(ushort const *,ulong,void * *)

- ea: `0x180030950`
- end: `0x180030a51`
- name: `?OpenDevice@@YAKPEBGKPEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002fbd0`

## callees

- `0x1800140f0`
- `0x180014c70`
- `0x180030950`
- `0x180032c90`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003098e`
- `msvcrt!_wcsnicmp` at `0x18003098e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030a0e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030a0e`

## pseudocode

```c
__int64 __fastcall OpenDevice(unsigned __int16 *a1, __int64 a2, void **a3)
{
  unsigned __int16 *v4; // rdi
  __int64 result; // rax
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-270h]
  unsigned __int64 v9; // [rsp+40h] [rbp-258h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 v11[280]; // [rsp+50h] [rbp-248h] BYREF

  *a3 = (void *)-1LL;
  v4 = a1;
  if ( !_wcsnicmp(a1, L"\\Device", 7u) )
  {
    v10 = 0;
    v9 = 0;
    LODWORD(result) = StringCchCopyExW(v11, 0x112u, L"\\\\?\\GLOBALROOT", &v10, &v9, dwFlagsAndAttributes);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    LODWORD(result) = StringCchCopyW(v10, v9, v4);
    if ( (int)result < 0 )
      return (unsigned __int16)result;
    v4 = v11;
  }
  v6 = 0;
  FileW = CreateFileW(v4, 0, 3u, 0, 3u, 0, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  *a3 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v6;
}

```

## disassembly

```asm
0x180030950  mov     [rsp+arg_8], rbx
0x180030955  mov     [rsp+arg_18], rsi
0x18003095a  push    rdi
0x18003095b  sub     rsp, 290h
0x180030962  mov     rax, cs:__security_cookie
0x180030969  xor     rax, rsp
0x18003096c  mov     [rsp+298h+var_18], rax
0x180030974  mov     rsi, r8
0x180030977  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x18003097e  mov     r8d, 7; MaxCount
0x180030984  lea     rdx, aDevice; "\\Device"
0x18003098b  mov     rdi, rcx
0x18003098e  call    cs:__imp__wcsnicmp
0x180030994  test    eax, eax
0x180030996  jnz     short loc_1800309EE
0x180030998  lea     rax, [rsp+298h+var_258]
0x18003099d  mov     [rsp+298h+var_250], 0
0x1800309a6  lea     r9, [rsp+298h+var_250]; unsigned __int16 **
0x1800309ab  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; unsigned __int64 *
0x1800309b0  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800309b7  mov     [rsp+298h+var_258], 0
0x1800309c0  mov     edx, 112h; unsigned __int64
0x1800309c5  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x1800309ca  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800309cf  test    eax, eax
0x1800309d1  js      short loc_180030A4C
0x1800309d3  mov     rdx, [rsp+298h+var_258]; unsigned __int64
0x1800309d8  mov     r8, rdi; unsigned __int16 *
0x1800309db  mov     rcx, [rsp+298h+var_250]; unsigned __int16 *
0x1800309e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800309e5  test    eax, eax
0x1800309e7  js      short loc_180030A4C
0x1800309e9  lea     rdi, [rsp+298h+var_248]
0x1800309ee  xor     ebx, ebx
0x1800309f0  mov     [rsp+298h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1800309f9  mov     [rsp+298h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800309fd  xor     r9d, r9d; lpSecurityAttributes
0x180030a00  xor     edx, edx; dwDesiredAccess
0x180030a02  mov     rcx, rdi; lpFileName
0x180030a05  lea     r8d, [rbx+3]; dwShareMode
0x180030a09  mov     [rsp+298h+dwCreationDisposition], r8d; dwCreationDisposition
0x180030a0e  call    cs:__imp_CreateFileW
0x180030a14  mov     [rsi], rax
0x180030a17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030a1b  jnz     short loc_180030A25
0x180030a1d  call    cs:__imp_GetLastError
0x180030a23  mov     ebx, eax
0x180030a25  mov     eax, ebx
0x180030a27  mov     rcx, [rsp+298h+var_18]
0x180030a2f  xor     rcx, rsp; StackCookie
0x180030a32  call    __security_check_cookie
0x180030a37  lea     r11, [rsp+298h+var_8]
0x180030a3f  mov     rbx, [r11+18h]
0x180030a43  mov     rsi, [r11+28h]
0x180030a47  mov     rsp, r11
0x180030a4a  pop     rdi
0x180030a4b  retn
0x180030a4c  movzx   eax, ax
0x180030a4f  jmp     short loc_180030A27
```
