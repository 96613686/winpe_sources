# wistd::__function::__func__lambda_9a4e4d60a8a88ac5372225d08fb3eee1__long___cdecl(unsigned_short___unsigned___int64_unsigned___int64__)_::operator()

- ea: `0x18003aa50`
- end: `0x18003aad5`
- name: `wistd::__function::__func__lambda_9a4e4d60a8a88ac5372225d08fb3eee1__long___cdecl(unsigned_short___unsigned___int64_unsigned___int64__)_::operator()`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180012734`
- `0x18003aa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa90`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18003aa7f`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x18003aa7f`

## string_xrefs

- `0x18003aab5`: `onecore\drivers\storage\storsvc\service\recursivedirectory.cpp`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func__lambda_9a4e4d60a8a88ac5372225d08fb3eee1__long___cdecl_unsigned_short___unsigned___int64_unsigned___int64____::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        _QWORD **a4)
{
  unsigned __int64 v4; // r8
  LPCWSTR *v5; // rcx
  _QWORD *v6; // rbx
  WCHAR *v7; // rdx
  BOOL VolumePathNamesForVolumeNameW; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD cchReturnLength; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a3;
  v5 = *(LPCWSTR **)(a1 + 8);
  v6 = *a4;
  v7 = *a2;
  if ( v4 > 0xFFFFFFFF )
    LODWORD(v4) = -1;
  cchReturnLength = 0;
  VolumePathNamesForVolumeNameW = GetVolumePathNamesForVolumeNameW(*v5, v7, v4, &cchReturnLength);
  *v6 = cchReturnLength;
  if ( VolumePathNamesForVolumeNameW )
    return 0;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError == 234 )
  {
    return 0;
  }
  else
  {
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (v10 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\recursivedirectory.cpp",
        (const char *)v10,
        v12);
  }
  return v10;
}

```

## disassembly

```asm
0x18003aa50  push    rbx; int
0x18003aa52  sub     rsp, 20h
0x18003aa56  mov     r8, [r8]
0x18003aa59  mov     eax, 0FFFFFFFFh
0x18003aa5e  mov     rcx, [rcx+8]
0x18003aa62  cmp     r8, rax
0x18003aa65  mov     rbx, [r9]
0x18003aa68  lea     r9, [rsp+28h+cchReturnLength]; lpcchReturnLength
0x18003aa6d  mov     rdx, [rdx]; lpszVolumePathNames
0x18003aa70  cmova   r8, rax; cchBufferLength
0x18003aa74  mov     [rsp+28h+cchReturnLength], 0
0x18003aa7c  mov     rcx, [rcx]; lpszVolumeName
0x18003aa7f  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18003aa85  mov     ecx, [rsp+28h+cchReturnLength]
0x18003aa89  mov     [rbx], rcx
0x18003aa8c  test    eax, eax
0x18003aa8e  jnz     short loc_18003AACB
0x18003aa90  call    cs:__imp_GetLastError
0x18003aa96  mov     ebx, eax
0x18003aa98  cmp     eax, 0EAh
0x18003aa9d  jz      short loc_18003AACB
0x18003aa9f  test    eax, eax
0x18003aaa1  jle     short loc_18003AAAC
0x18003aaa3  movzx   ebx, ax
0x18003aaa6  or      ebx, 80070000h
0x18003aaac  test    ebx, ebx
0x18003aaae  jns     short loc_18003AACD
0x18003aab0  mov     rcx, [rsp+28h]; this
0x18003aab5  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003aabc  mov     r9d, ebx; char *
0x18003aabf  mov     edx, 3Dh ; '='; void *
0x18003aac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aac9  jmp     short loc_18003AACD
0x18003aacb  xor     ebx, ebx
0x18003aacd  mov     eax, ebx
0x18003aacf  add     rsp, 20h
0x18003aad3  pop     rbx
0x18003aad4  retn
```
