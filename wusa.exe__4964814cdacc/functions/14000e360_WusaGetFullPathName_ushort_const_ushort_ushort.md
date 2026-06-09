# WusaGetFullPathName(ushort const *,ushort * *,ushort * *)

- ea: `0x14000e360`
- end: `0x14000e4bb`
- name: `?WusaGetFullPathName@@YAJPEBGPEAPEAG1@Z`
- size: `347`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000fdf8`

## callees

- `0x14000e280`
- `0x14000e360`
- `0x140013490`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000e4a5`
- `KERNEL32!LocalFree` at `0x14000e4a5`
- `KERNEL32!GetFullPathNameW` at `0x14000e389`
- `KERNEL32!GetFullPathNameW` at `0x14000e40c`
- `KERNEL32!GetFullPathNameW` at `0x14000e389`
- `KERNEL32!GetFullPathNameW` at `0x14000e40c`
- `KERNEL32!GetLastError` at `0x14000e395`
- `KERNEL32!GetLastError` at `0x14000e416`
- `KERNEL32!GetLastError` at `0x14000e395`
- `KERNEL32!GetLastError` at `0x14000e416`
- `ServicingCommon!SczFree` at `0x14000e450`
- `ServicingCommon!SczFree` at `0x14000e450`
- `ServicingCommon!SczAlloc` at `0x14000e3d9`
- `ServicingCommon!SczAlloc` at `0x14000e3d9`

## string_xrefs

- `0x14000e3b1`: `Failed: GetFullPathName() failed for %S`
- `0x14000e3bd`: `WusaGetFullPathName`
- `0x14000e3f1`: `WusaGetFullPathName`
- `0x14000e491`: `WusaGetFullPathName`
- `0x14000e3e5`: `Failed to allocate memory for full path.`

## pseudocode

```c
__int64 __fastcall WusaGetFullPathName(LPCWSTR lpFileName, unsigned __int16 **a2, unsigned __int16 **a3)
{
  DWORD FullPathNameW; // eax
  DWORD v6; // edi
  signed int v7; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  signed int LastError; // eax
  HLOCAL v13; // rdi
  LPWSTR lpBuffer; // [rsp+60h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  lpBuffer = 0;
  FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
  v6 = FullPathNameW;
  if ( FullPathNameW )
  {
    v8 = SczAlloc(&lpBuffer, FullPathNameW);
    if ( v8 < 0 )
    {
      WusaLogDebugEventA(L"WusaGetFullPathName", 444, "Failed to allocate memory for full path.");
      goto LABEL_15;
    }
    if ( GetFullPathNameW(lpFileName, v6, lpBuffer, 0) )
    {
      *a2 = lpBuffer;
      lpBuffer = 0;
      goto LABEL_15;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = 449;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v9 = 440;
  }
  if ( v8 >= 0 )
    v8 = -2147467259;
  WusaLogDebugEventA(L"WusaGetFullPathName", v9, "Failed: GetFullPathName() failed for %S", lpFileName);
LABEL_15:
  if ( lpBuffer )
  {
    SczFree(lpBuffer, v10, v11);
    lpBuffer = 0;
  }
  if ( v8 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v8, (unsigned __int16 **)&hMem);
    v13 = hMem;
    WusaLogDebugEventA(L"WusaGetFullPathName", 459, "Exit with error code 0X%x (%ls)", v8, (const wchar_t *)hMem);
    if ( v13 )
      LocalFree(v13);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e360  mov     [rsp+arg_0], rbx
0x14000e365  mov     [rsp+lpBuffer], r8
0x14000e36a  push    rsi
0x14000e36b  push    rdi
0x14000e36c  push    r14
0x14000e36e  sub     rsp, 30h
0x14000e372  mov     r14, rdx
0x14000e375  mov     [rsp+48h+lpBuffer], 0
0x14000e37e  xor     edx, edx; nBufferLength
0x14000e380  xor     r9d, r9d; lpFilePart
0x14000e383  xor     r8d, r8d; lpBuffer
0x14000e386  mov     rsi, rcx
0x14000e389  call    cs:__imp_GetFullPathNameW
0x14000e38f  mov     edi, eax
0x14000e391  test    eax, eax
0x14000e393  jnz     short loc_14000E3D1
0x14000e395  call    cs:__imp_GetLastError
0x14000e39b  mov     ebx, eax
0x14000e39d  test    eax, eax
0x14000e39f  jle     short loc_14000E3AA
0x14000e3a1  movzx   ebx, ax
0x14000e3a4  or      ebx, 80070000h
0x14000e3aa  mov     edx, 1B8h
0x14000e3af  test    ebx, ebx
0x14000e3b1  lea     r8, aFailedGetfullp; "Failed: GetFullPathName() failed for %S"
0x14000e3b8  mov     eax, 80004005h
0x14000e3bd  lea     rcx, aWusagetfullpat; "WusaGetFullPathName"
0x14000e3c4  mov     r9, rsi
0x14000e3c7  cmovns  ebx, eax
0x14000e3ca  call    WusaLogDebugEventA
0x14000e3cf  jmp     short loc_14000E446
0x14000e3d1  mov     rdx, rdi
0x14000e3d4  lea     rcx, [rsp+48h+lpBuffer]
0x14000e3d9  call    cs:__imp_SczAlloc
0x14000e3df  mov     ebx, eax
0x14000e3e1  test    eax, eax
0x14000e3e3  jns     short loc_14000E3FF
0x14000e3e5  lea     r8, aFailedToAlloca_18; "Failed to allocate memory for full path"...
0x14000e3ec  mov     edx, 1BCh
0x14000e3f1  lea     rcx, aWusagetfullpat; "WusaGetFullPathName"
0x14000e3f8  call    WusaLogDebugEventA
0x14000e3fd  jmp     short loc_14000E446
0x14000e3ff  mov     r8, [rsp+48h+lpBuffer]; lpBuffer
0x14000e404  xor     r9d, r9d; lpFilePart
0x14000e407  mov     edx, edi; nBufferLength
0x14000e409  mov     rcx, rsi; lpFileName
0x14000e40c  call    cs:__imp_GetFullPathNameW
0x14000e412  test    eax, eax
0x14000e414  jnz     short loc_14000E435
0x14000e416  call    cs:__imp_GetLastError
0x14000e41c  mov     ebx, eax
0x14000e41e  test    eax, eax
0x14000e420  jle     short loc_14000E42B
0x14000e422  movzx   ebx, ax
0x14000e425  or      ebx, 80070000h
0x14000e42b  mov     edx, 1C1h
0x14000e430  jmp     loc_14000E3AF
0x14000e435  mov     rax, [rsp+48h+lpBuffer]
0x14000e43a  mov     [r14], rax
0x14000e43d  mov     [rsp+48h+lpBuffer], 0
0x14000e446  mov     rcx, [rsp+48h+lpBuffer]
0x14000e44b  test    rcx, rcx
0x14000e44e  jz      short loc_14000E45F
0x14000e450  call    cs:__imp_SczFree
0x14000e456  mov     [rsp+48h+lpBuffer], 0
0x14000e45f  test    ebx, ebx
0x14000e461  jns     short loc_14000E4AB
0x14000e463  lea     rdx, [rsp+48h+hMem]; unsigned __int16 **
0x14000e468  mov     [rsp+48h+hMem], 0
0x14000e471  mov     ecx, ebx; dwMessageId
0x14000e473  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000e478  mov     rdi, [rsp+48h+hMem]
0x14000e47d  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000e484  mov     r9d, ebx
0x14000e487  mov     [rsp+48h+var_28], rdi
0x14000e48c  mov     edx, 1CBh
0x14000e491  lea     rcx, aWusagetfullpat; "WusaGetFullPathName"
0x14000e498  call    WusaLogDebugEventA
0x14000e49d  test    rdi, rdi
0x14000e4a0  jz      short loc_14000E4AB
0x14000e4a2  mov     rcx, rdi; hMem
0x14000e4a5  call    cs:__imp_LocalFree
0x14000e4ab  mov     eax, ebx
0x14000e4ad  mov     rbx, [rsp+48h+arg_0]
0x14000e4b2  add     rsp, 30h
0x14000e4b6  pop     r14
0x14000e4b8  pop     rdi
0x14000e4b9  pop     rsi
0x14000e4ba  retn
```
