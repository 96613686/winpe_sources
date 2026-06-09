# HandleFontChangeEvent

- ea: `0x180002aec`
- end: `0x180002d1a`
- name: `HandleFontChangeEvent`
- size: `558`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180003650`

## callees

- `0x1800020dc`
- `0x180002aec`
- `0x1800035c0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180002b77`
- `KERNELBASE!LocalAlloc` at `0x180002bdf`
- `KERNELBASE!LocalAlloc` at `0x180002b77`
- `KERNELBASE!LocalAlloc` at `0x180002bdf`
- `ntdll!NtEnumerateKey` at `0x180002bb5`
- `ntdll!NtEnumerateKey` at `0x180002c2a`
- `ntdll!NtEnumerateKey` at `0x180002bb5`
- `ntdll!NtEnumerateKey` at `0x180002c2a`
- `ntdll!NtClose` at `0x180002c7b`
- `ntdll!NtClose` at `0x180002c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002bfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002c92`
- `win32u!NtUserSetInformationThread` at `0x180002b4c`
- `win32u!NtUserSetInformationThread` at `0x180002cf5`
- `win32u!NtUserSetInformationThread` at `0x180002b4c`
- `win32u!NtUserSetInformationThread` at `0x180002cf5`
- `USER32!SendNotifyMessageW` at `0x180002cd4`
- `USER32!SendNotifyMessageW` at `0x180002cd4`
- `GDI32!GdiAddFontResourceW` at `0x180002cb3`
- `GDI32!GdiAddFontResourceW` at `0x180002cb3`

## pseudocode

```c
unsigned int *__fastcall HandleFontChangeEvent(HANDLE KeyHandle)
{
  int v2; // esi
  unsigned int *result; // rax
  unsigned int v4; // ebx
  unsigned int *v5; // rdi
  ULONG v6; // r14d
  ULONG v7; // r13d
  NTSTATUS v8; // eax
  unsigned int *v9; // r12
  __int128 v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h]
  ULONG ResultLength; // [rsp+90h] [rbp+40h] BYREF
  int v13; // [rsp+98h] [rbp+48h]
  HANDLE Handle; // [rsp+A0h] [rbp+50h] BYREF

  Handle = 0;
  v13 = KeyHandle == ghFontRegistryHKCU;
  v10 = 0;
  v2 = -v13 & 0x500;
  v11 = 0;
  ResultLength = 0;
  result = (unsigned int *)NtUserSetInformationThread(-2, 7, &v10);
  if ( (int)result < 0 )
    return result;
  v4 = (unsigned int)AddFontsFromRegistry(KeyHandle, v2 + 64);
  result = (unsigned int *)LocalAlloc(0x40u, 0x220u);
  v5 = result;
  if ( !result )
    return result;
  v6 = 0;
  v7 = 544;
  while ( 1 )
  {
    v8 = NtEnumerateKey(KeyHandle, v6, KeyBasicInformation, v5, v7 - 2, &ResultLength);
    if ( v8 != -2147483643 && v8 != -1073741789 )
      break;
    ResultLength += 2;
    v9 = (unsigned int *)LocalAlloc(0x40u, ResultLength);
    if ( v9 )
    {
      LocalFree(v5);
      v7 = ResultLength;
      v5 = v9;
      v8 = NtEnumerateKey(KeyHandle, v6, KeyBasicInformation, v9, ResultLength - 2, &ResultLength);
      if ( v8 != -2147483643 && v8 != -1073741789 )
        break;
    }
LABEL_12:
    ++v6;
  }
  if ( v8 >= 0 )
  {
    *((_WORD *)v5 + ((unsigned __int64)v5[3] >> 1) + 8) = 0;
    if ( (int)MyRegOpenKey(KeyHandle, v5 + 4, &Handle) >= 0 )
    {
      v4 += (unsigned int)AddFontsFromRegistry(Handle, v2 + 64);
      NtClose(Handle);
    }
    goto LABEL_12;
  }
  LocalFree(v5);
  if ( v13 )
    v4 += GdiAddFontResourceW(L"ARIAL.TTF", 1600, 0);
  if ( v4 )
    SendNotifyMessageW(HWND_BROADCAST, 0x1Du, 0, 0);
  return (unsigned int *)NtUserSetInformationThread(-2, 9, &v10);
}

```

## disassembly

```asm
0x180002aec  mov     [rsp-38h+arg_18], rbx
0x180002af1  push    rbp
0x180002af2  push    rsi
0x180002af3  push    rdi
0x180002af4  push    r12
0x180002af6  push    r13
0x180002af8  push    r14
0x180002afa  push    r15
0x180002afc  mov     rbp, rsp
0x180002aff  sub     rsp, 50h
0x180002b03  xor     r13d, r13d
0x180002b06  mov     [rbp+Handle], 0
0x180002b0e  cmp     rcx, cs:ghFontRegistryHKCU
0x180002b15  lea     r8, [rbp+var_20]
0x180002b19  mov     r15, rcx
0x180002b1c  xorps   xmm0, xmm0
0x180002b1f  setz    r13b
0x180002b23  mov     eax, r13d
0x180002b26  mov     [rbp+arg_8], r13d
0x180002b2a  neg     eax
0x180002b2c  movups  [rbp+var_20], xmm0
0x180002b30  sbb     esi, esi
0x180002b32  xor     eax, eax
0x180002b34  and     esi, 500h
0x180002b3a  mov     [rbp+var_10], rax
0x180002b3e  mov     [rbp+arg_0], eax
0x180002b41  lea     r9d, [rax+18h]
0x180002b45  lea     edx, [rax+7]
0x180002b48  lea     rcx, [rax-2]
0x180002b4c  call    cs:__imp_NtUserSetInformationThread
0x180002b53  nop     dword ptr [rax+rax+00h]
0x180002b58  test    eax, eax
0x180002b5a  js      loc_180002D01
0x180002b60  lea     edx, [rsi+40h]
0x180002b63  mov     rcx, r15; KeyHandle
0x180002b66  call    AddFontsFromRegistry
0x180002b6b  mov     edx, 220h; uBytes
0x180002b70  mov     ecx, 40h ; '@'; uFlags
0x180002b75  mov     ebx, eax
0x180002b77  call    cs:__imp_LocalAlloc
0x180002b7e  nop     dword ptr [rax+rax+00h]
0x180002b83  mov     rdi, rax
0x180002b86  test    rax, rax
0x180002b89  jz      loc_180002D01
0x180002b8f  xor     r14d, r14d
0x180002b92  mov     r13d, 220h
0x180002b98  lea     rax, [rbp+arg_0]
0x180002b9c  mov     r9, rdi; KeyInformation
0x180002b9f  lea     ecx, [r13-2]
0x180002ba3  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180002ba8  mov     [rsp+50h+Length], ecx; Length
0x180002bac  xor     r8d, r8d; KeyInformationClass
0x180002baf  mov     rcx, r15; KeyHandle
0x180002bb2  mov     edx, r14d; Index
0x180002bb5  call    cs:__imp_NtEnumerateKey
0x180002bbc  nop     dword ptr [rax+rax+00h]
0x180002bc1  cmp     eax, 80000005h
0x180002bc6  jz      short loc_180002BCF
0x180002bc8  cmp     eax, 0C0000023h
0x180002bcd  jnz     short loc_180002C44
0x180002bcf  mov     eax, [rbp+arg_0]
0x180002bd2  mov     ecx, 40h ; '@'; uFlags
0x180002bd7  add     eax, 2
0x180002bda  mov     edx, eax; uBytes
0x180002bdc  mov     [rbp+arg_0], eax
0x180002bdf  call    cs:__imp_LocalAlloc
0x180002be6  nop     dword ptr [rax+rax+00h]
0x180002beb  mov     r12, rax
0x180002bee  test    rax, rax
0x180002bf1  jz      loc_180002C87
0x180002bf7  mov     rcx, rdi; hMem
0x180002bfa  call    cs:__imp_LocalFree
0x180002c01  nop     dword ptr [rax+rax+00h]
0x180002c06  mov     r13d, [rbp+arg_0]
0x180002c0a  lea     rax, [rbp+arg_0]
0x180002c0e  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180002c13  mov     r9, r12; KeyInformation
0x180002c16  xor     r8d, r8d; KeyInformationClass
0x180002c19  mov     edx, r14d; Index
0x180002c1c  mov     rdi, r12
0x180002c1f  lea     ecx, [r13-2]
0x180002c23  mov     [rsp+50h+Length], ecx; Length
0x180002c27  mov     rcx, r15; KeyHandle
0x180002c2a  call    cs:__imp_NtEnumerateKey
0x180002c31  nop     dword ptr [rax+rax+00h]
0x180002c36  cmp     eax, 80000005h
0x180002c3b  jz      short loc_180002C87
0x180002c3d  cmp     eax, 0C0000023h
0x180002c42  jz      short loc_180002C87
0x180002c44  test    eax, eax
0x180002c46  js      short loc_180002C8F
0x180002c48  mov     ecx, [rdi+0Ch]
0x180002c4b  lea     rdx, [rdi+10h]
0x180002c4f  shr     rcx, 1
0x180002c52  lea     r8, [rbp+Handle]
0x180002c56  xor     eax, eax
0x180002c58  mov     [rdi+rcx*2+10h], ax
0x180002c5d  mov     rcx, r15
0x180002c60  call    MyRegOpenKey
0x180002c65  test    eax, eax
0x180002c67  js      short loc_180002C87
0x180002c69  mov     rcx, [rbp+Handle]; KeyHandle
0x180002c6d  lea     edx, [rsi+40h]
0x180002c70  call    AddFontsFromRegistry
0x180002c75  mov     rcx, [rbp+Handle]; Handle
0x180002c79  add     ebx, eax
0x180002c7b  call    cs:__imp_NtClose
0x180002c82  nop     dword ptr [rax+rax+00h]
0x180002c87  inc     r14d
0x180002c8a  jmp     loc_180002B98
0x180002c8f  mov     rcx, rdi; hMem
0x180002c92  call    cs:__imp_LocalFree
0x180002c99  nop     dword ptr [rax+rax+00h]
0x180002c9e  cmp     [rbp+arg_8], 0
0x180002ca2  jz      short loc_180002CC1
0x180002ca4  xor     r8d, r8d
0x180002ca7  lea     rcx, aArialTtf; "ARIAL.TTF"
0x180002cae  mov     edx, 640h
0x180002cb3  call    cs:__imp_GdiAddFontResourceW
0x180002cba  nop     dword ptr [rax+rax+00h]
0x180002cbf  add     ebx, eax
0x180002cc1  test    ebx, ebx
0x180002cc3  jz      short loc_180002CE0
0x180002cc5  xor     r9d, r9d; lParam
0x180002cc8  xor     r8d, r8d; wParam
0x180002ccb  mov     ecx, 0FFFFh; hWnd
0x180002cd0  lea     edx, [r9+1Dh]; Msg
0x180002cd4  call    cs:__imp_SendNotifyMessageW
0x180002cdb  nop     dword ptr [rax+rax+00h]
0x180002ce0  mov     r9d, 18h
0x180002ce6  lea     r8, [rbp+var_20]
0x180002cea  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180002cf1  lea     edx, [r9-0Fh]
0x180002cf5  call    cs:__imp_NtUserSetInformationThread
0x180002cfc  nop     dword ptr [rax+rax+00h]
0x180002d01  mov     rbx, [rsp+50h+arg_18]
0x180002d09  add     rsp, 50h
0x180002d0d  pop     r15
0x180002d0f  pop     r14
0x180002d11  pop     r13
0x180002d13  pop     r12
0x180002d15  pop     rdi
0x180002d16  pop     rsi
0x180002d17  pop     rbp
0x180002d18  retn
```
