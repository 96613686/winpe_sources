# WusaGetErrorMessage(ulong,ushort * *)

- ea: `0x14000e280`
- end: `0x14000e35a`
- name: `?WusaGetErrorMessage@@YAJKPEAPEAG@Z`
- size: `218`
- prototype: `__int64 __fastcall(DWORD dwMessageId, unsigned __int16 **)`
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x140005794`
- `0x140005860`
- `0x140005c70`
- `0x140006fb8`
- `0x1400075b0`
- `0x140008ff8`
- `0x14000afc0`
- `0x14000b84c`
- `0x14000c488`
- `0x14000d25c`
- `0x14000d44c`
- `0x14000e360`
- `0x14000e4c4`
- `0x14000e9ac`
- `0x14000eb0c`
- `0x14000ec58`
- `0x14000ee88`
- `0x14000f8f0`
- `0x14000fdf8`
- `0x140010aa0`
- `0x140010c94`
- `0x140010e88`
- `0x140011004`
- `0x140011190`
- `0x14001150c`
- `0x140011dcc`
- `0x1400121f0`
- `0x140012320`
- `0x14001259c`
- `0x140012818`
- `0x140012b00`
- `0x140013020`
- `0x140013a90`

## callees

- `0x14000e280`
- `0x140013490`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000e342`
- `KERNEL32!LocalFree` at `0x14000e342`
- `KERNEL32!GetLastError` at `0x14000e2d3`
- `KERNEL32!GetLastError` at `0x14000e2d3`
- `KERNEL32!FormatMessageW` at `0x14000e2c9`
- `KERNEL32!FormatMessageW` at `0x14000e2c9`
- `msvcrt!wcsrchr` at `0x14000e31e`
- `msvcrt!wcsrchr` at `0x14000e31e`

## pseudocode

```c
__int64 __fastcall WusaGetErrorMessage(DWORD dwMessageId, unsigned __int16 **a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  wchar_t *v6; // rcx
  wchar_t *v7; // rax
  wchar_t *Str; // [rsp+58h] [rbp+10h] BYREF

  Str = 0;
  *a2 = 0;
  if ( FormatMessageW(0x1300u, 0, dwMessageId, 0, (LPWSTR)&Str, 0, 0) )
  {
    v5 = 0;
    v7 = wcsrchr(Str, 0xDu);
    if ( v7 )
      *v7 = 0;
    *a2 = Str;
    v6 = 0;
    Str = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    WusaLogDebugEventA((__int64)L"WusaGetErrorMessage", 326, "Failed to get message for error 0x%x", dwMessageId);
    v6 = Str;
  }
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e280  mov     rax, rsp
0x14000e283  mov     [rax+8], rbx
0x14000e287  mov     [rax+18h], rsi
0x14000e28b  push    rdi
0x14000e28c  sub     rsp, 40h
0x14000e290  mov     qword ptr [rax-18h], 0
0x14000e298  mov     rdi, rdx
0x14000e29b  mov     dword ptr [rax-20h], 0
0x14000e2a2  mov     esi, ecx
0x14000e2a4  mov     qword ptr [rax+10h], 0
0x14000e2ac  lea     rax, [rax+10h]
0x14000e2b0  mov     qword ptr [rdx], 0
0x14000e2b7  mov     r8d, ecx; dwMessageId
0x14000e2ba  xor     r9d, r9d; dwLanguageId
0x14000e2bd  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x14000e2c2  xor     edx, edx; lpSource
0x14000e2c4  mov     ecx, 1300h; dwFlags
0x14000e2c9  call    cs:__imp_FormatMessageW
0x14000e2cf  test    eax, eax
0x14000e2d1  jnz     short loc_14000E314
0x14000e2d3  call    cs:__imp_GetLastError
0x14000e2d9  mov     ebx, eax
0x14000e2db  test    eax, eax
0x14000e2dd  jle     short loc_14000E2E8
0x14000e2df  movzx   ebx, ax
0x14000e2e2  or      ebx, 80070000h
0x14000e2e8  test    ebx, ebx
0x14000e2ea  lea     r8, aFailedToGetMes; "Failed to get message for error 0x%x"
0x14000e2f1  mov     eax, 80004005h
0x14000e2f6  lea     rcx, aWusageterrorme; "WusaGetErrorMessage"
0x14000e2fd  mov     r9d, esi
0x14000e300  mov     edx, 146h
0x14000e305  cmovns  ebx, eax
0x14000e308  call    WusaLogDebugEventA
0x14000e30d  mov     rcx, [rsp+48h+Str]
0x14000e312  jmp     short loc_14000E33D
0x14000e314  mov     rcx, [rsp+48h+Str]; Str
0x14000e319  xor     ebx, ebx
0x14000e31b  lea     edx, [rbx+0Dh]; Ch
0x14000e31e  call    cs:__imp_wcsrchr
0x14000e324  test    rax, rax
0x14000e327  jz      short loc_14000E32E
0x14000e329  xor     ecx, ecx
0x14000e32b  mov     [rax], cx
0x14000e32e  mov     rcx, [rsp+48h+Str]
0x14000e333  mov     [rdi], rcx
0x14000e336  xor     ecx, ecx; hMem
0x14000e338  mov     [rsp+48h+Str], rcx
0x14000e33d  test    rcx, rcx
0x14000e340  jz      short loc_14000E348
0x14000e342  call    cs:__imp_LocalFree
0x14000e348  mov     rsi, [rsp+48h+arg_10]
0x14000e34d  mov     eax, ebx
0x14000e34f  mov     rbx, [rsp+48h+arg_0]
0x14000e354  add     rsp, 40h
0x14000e358  pop     rdi
0x14000e359  retn
```
