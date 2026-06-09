# CreateEmptyWebConfig(IBaseFileSystem *,ushort const *,ushort const *)

- ea: `0x18001ad3c`
- end: `0x18001aecd`
- name: `?CreateEmptyWebConfig@@YAJPEAVIBaseFileSystem@@PEBG1@Z`
- size: `401`
- prototype: `signed int __fastcall(struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000bc4c`
- `0x180011aec`

## callees

- `0x18001ad3c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aea6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ae17`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ae17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae39`

## string_xrefs

- `0x18001ad5d`: `<?xml version="1.0" encoding="UTF-8"?>\n<configuration />\n`

## pseudocode

```c
signed int __fastcall CreateEmptyWebConfig(
        struct IBaseFileSystem *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IBaseFileSystem *, const unsigned __int16 *, __int64, _QWORD, _QWORD, int, int, _QWORD); // rax
  void *v8; // rax
  void *v9; // rbp
  signed int result; // eax
  signed int v11; // ebx
  signed int LastError; // eax
  signed int v13; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-78h] BYREF
  _OWORD Buffer[4]; // [rsp+58h] [rbp-70h] BYREF

  v3 = *(_QWORD *)a1;
  strcpy((char *)Buffer, "<?xml version=\"1.0\" encoding=\"UTF-8\"?>\r\n<configuration />\r\n");
  v6 = *(__int64 (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, __int64, _QWORD, _QWORD, int, int, _QWORD))(v3 + 72);
  NumberOfBytesWritten = 0;
  v8 = (void *)v6(a1, a3, 1179926, 0, 0, 2, 128, 0);
  v9 = v8;
  if ( v8 != (void *)-1LL )
  {
    v11 = 0;
    if ( !WriteFile(v8, Buffer, 0x3Bu, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v9);
    if ( v11 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, int))(*(_QWORD *)a1 + 128LL))(
             a1,
             a3,
             a2,
             0,
             0,
             3) )
      {
        return 0;
      }
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
      if ( v11 >= 0 )
        return v11;
    }
    if ( !(*(unsigned int (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *))(*(_QWORD *)a1 + 104LL))(
            a1,
            a3) )
      GetLastError();
    return v11;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001ad3c  push    rbx
0x18001ad3e  push    rbp
0x18001ad3f  push    rsi
0x18001ad40  push    r14
0x18001ad42  push    r15
0x18001ad44  sub     rsp, 0A0h
0x18001ad4b  mov     rax, cs:__security_cookie
0x18001ad52  xor     rax, rsp
0x18001ad55  mov     [rsp+0C8h+var_30], rax
0x18001ad5d  movups  xmm0, xmmword ptr cs:aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x18001ad64  mov     rax, [rcx]
0x18001ad67  mov     r14, r8
0x18001ad6a  movups  xmm1, xmmword ptr cs:aXmlVersion10En+10h; ".0\" encoding=\"UTF-8\"?>\r\n<configura"...
0x18001ad71  mov     [rsp+0C8h+var_90], 0
0x18001ad7a  mov     r15, rdx
0x18001ad7d  movups  [rsp+0C8h+Buffer], xmm0
0x18001ad82  mov     rax, [rax+48h]
0x18001ad86  xor     r9d, r9d
0x18001ad89  movups  xmm0, xmmword ptr cs:aXmlVersion10En+20h; "F-8\"?>\r\n<configuration />\r\n"
0x18001ad90  mov     [rsp+0C8h+var_98], 80h
0x18001ad98  mov     r8d, 120116h
0x18001ad9e  movups  [rsp+0C8h+var_60], xmm1
0x18001ada3  mov     [rsp+0C8h+var_A0], 2
0x18001adab  mov     rdx, r14
0x18001adae  movups  xmm1, xmmword ptr cs:aXmlVersion10En+2Ch; "figuration />\r\n"
0x18001adb5  mov     rsi, rcx
0x18001adb8  mov     [rsp+0C8h+NumberOfBytesWritten], 0
0x18001adc0  movups  [rsp+0C8h+var_50], xmm0
0x18001adc5  mov     [rsp+0C8h+lpOverlapped], 0
0x18001adce  movups  [rsp+0C8h+var_50+0Ch], xmm1
0x18001add6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001addb  mov     rbp, rax
0x18001adde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ade2  jnz     short loc_18001ADFF
0x18001ade4  call    cs:__imp_GetLastError
0x18001adea  test    eax, eax
0x18001adec  jle     loc_18001AEAE
0x18001adf2  movzx   eax, ax
0x18001adf5  or      eax, 80070000h
0x18001adfa  jmp     loc_18001AEAE
0x18001adff  xor     ebx, ebx
0x18001ae01  lea     r9, [rsp+0C8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ae06  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x18001ae0b  mov     [rsp+0C8h+lpOverlapped], rbx; lpOverlapped
0x18001ae10  mov     rcx, rbp; hFile
0x18001ae13  lea     r8d, [rbx+3Bh]; nNumberOfBytesToWrite
0x18001ae17  call    cs:__imp_WriteFile
0x18001ae1d  test    eax, eax
0x18001ae1f  jnz     short loc_18001AE36
0x18001ae21  call    cs:__imp_GetLastError
0x18001ae27  mov     ebx, eax
0x18001ae29  test    eax, eax
0x18001ae2b  jle     short loc_18001AE36
0x18001ae2d  movzx   ebx, ax
0x18001ae30  or      ebx, 80070000h
0x18001ae36  mov     rcx, rbp; hObject
0x18001ae39  call    cs:__imp_CloseHandle
0x18001ae3f  test    ebx, ebx
0x18001ae41  js      short loc_18001AE90
0x18001ae43  mov     rax, [rsi]
0x18001ae46  xor     r9d, r9d
0x18001ae49  mov     [rsp+0C8h+var_A0], 3
0x18001ae51  mov     r8, r15
0x18001ae54  mov     rdx, r14
0x18001ae57  mov     [rsp+0C8h+lpOverlapped], 0
0x18001ae60  mov     rcx, rsi
0x18001ae63  mov     rax, [rax+80h]
0x18001ae6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae6f  test    eax, eax
0x18001ae71  jz      short loc_18001AE77
0x18001ae73  xor     ebx, ebx
0x18001ae75  jmp     short loc_18001AEAC
0x18001ae77  call    cs:__imp_GetLastError
0x18001ae7d  mov     ebx, eax
0x18001ae7f  test    eax, eax
0x18001ae81  jle     short loc_18001AE8C
0x18001ae83  movzx   ebx, ax
0x18001ae86  or      ebx, 80070000h
0x18001ae8c  test    ebx, ebx
0x18001ae8e  jns     short loc_18001AEAC
0x18001ae90  mov     r8, [rsi]
0x18001ae93  mov     rdx, r14
0x18001ae96  mov     rcx, rsi
0x18001ae99  mov     rax, [r8+68h]
0x18001ae9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aea2  test    eax, eax
0x18001aea4  jnz     short loc_18001AEAC
0x18001aea6  call    cs:__imp_GetLastError
0x18001aeac  mov     eax, ebx
0x18001aeae  mov     rcx, [rsp+0C8h+var_30]
0x18001aeb6  xor     rcx, rsp; StackCookie
0x18001aeb9  call    __security_check_cookie
0x18001aebe  add     rsp, 0A0h
0x18001aec5  pop     r15
0x18001aec7  pop     r14
0x18001aec9  pop     rsi
0x18001aeca  pop     rbp
0x18001aecb  pop     rbx
0x18001aecc  retn
```
