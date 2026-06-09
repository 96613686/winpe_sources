# ResourceStringCoAllocFormatMessageVA

- ea: `0x1800e1b88`
- end: `0x1800e1c92`
- name: `ResourceStringCoAllocFormatMessageVA`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050fc0`

## callees

- `0x1800162f0`
- `0x1800e19f8`
- `0x1800e1adc`
- `0x1800e1b88`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800e1bee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800e1bee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e1c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e1c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e1c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e1c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1c4f`

## pseudocode

```c
__int64 ResourceStringCoAllocFormatMessageVA(int a1, int a2, _QWORD *a3, ...)
{
  int ErrorError; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  void *v8; // r10
  LPWSTR lpBuffer; // [rsp+20h] [rbp-58h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  LPCVOID lpSource[6]; // [rsp+48h] [rbp-30h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  lpSource[0] = 0;
  ErrorError = TResourceStringAllocCopyEx<unsigned short *>(
                 a1,
                 a2,
                 (int)a3,
                 (int)ResourceStringAllocCopyExLocalAlloc,
                 lpBuffer,
                 lpSource);
  if ( ErrorError >= 0 )
  {
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0x500u, lpSource[0], 0, 0, Buffer, 0, (va_list *)va) )
    {
      ErrorError = -2147024882;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v5) );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      if ( v7 )
      {
        ErrorError = StringCchCopyW(v7, (unsigned int)v6, *(const unsigned __int16 **)Buffer);
        if ( ErrorError >= 0 )
        {
          *a3 = v8;
          v8 = 0;
        }
        CoTaskMemFree(v8);
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else
    {
      ErrorError = HRESULTFromLastErrorError();
    }
    LocalFree((HLOCAL)lpSource[0]);
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x1800e1b88  mov     r11, rsp
0x1800e1b8b  mov     [r11+20h], r9
0x1800e1b8f  push    rbx
0x1800e1b90  push    rbp
0x1800e1b91  push    rsi
0x1800e1b92  push    rdi
0x1800e1b93  sub     rsp, 58h
0x1800e1b97  lea     rax, [r11-30h]
0x1800e1b9b  xor     ebp, ebp
0x1800e1b9d  lea     r9, _ResourceStringAllocCopyExLocalAlloc; int
0x1800e1ba4  mov     [r11-30h], rbp
0x1800e1ba8  mov     [r11-50h], rax
0x1800e1bac  mov     rsi, r8
0x1800e1baf  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800e1bb4  mov     ebx, eax
0x1800e1bb6  test    eax, eax
0x1800e1bb8  js      loc_1800E1C86
0x1800e1bbe  mov     rdx, [rsp+78h+lpSource]; lpSource
0x1800e1bc3  lea     rax, [rsp+78h+arg_18]
0x1800e1bcb  mov     [rsp+78h+Arguments], rax; Arguments
0x1800e1bd0  xor     r9d, r9d; dwLanguageId
0x1800e1bd3  lea     rax, [rsp+78h+Buffer]
0x1800e1bd8  mov     [rsp+78h+nSize], ebp; nSize
0x1800e1bdc  xor     r8d, r8d; dwMessageId
0x1800e1bdf  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x1800e1be4  mov     ecx, 500h; dwFlags
0x1800e1be9  mov     qword ptr [rsp+78h+Buffer], rbp
0x1800e1bee  call    cs:__imp_FormatMessageW
0x1800e1bf5  nop     dword ptr [rax+rax+00h]
0x1800e1bfa  test    eax, eax
0x1800e1bfc  jz      short loc_1800E1C6E
0x1800e1bfe  mov     rcx, qword ptr [rsp+78h+Buffer]
0x1800e1c03  mov     ebx, 8007000Eh
0x1800e1c08  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e1c0c  inc     rax
0x1800e1c0f  cmp     [rcx+rax*2], bp
0x1800e1c13  jnz     short loc_1800E1C0C
0x1800e1c15  inc     eax
0x1800e1c17  mov     edi, eax
0x1800e1c19  lea     rcx, [rax+rax]; cb
0x1800e1c1d  call    cs:__imp_CoTaskMemAlloc
0x1800e1c24  nop     dword ptr [rax+rax+00h]
0x1800e1c29  mov     r10, rax
0x1800e1c2c  test    rax, rax
0x1800e1c2f  jz      short loc_1800E1C5B
0x1800e1c31  mov     r8, qword ptr [rsp+78h+Buffer]; unsigned __int16 *
0x1800e1c36  mov     edx, edi; unsigned __int64
0x1800e1c38  mov     rcx, rax; unsigned __int16 *
0x1800e1c3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e1c40  mov     ebx, eax
0x1800e1c42  test    eax, eax
0x1800e1c44  js      short loc_1800E1C4C
0x1800e1c46  mov     [rsi], r10
0x1800e1c49  mov     r10, rbp
0x1800e1c4c  mov     rcx, r10; pv
0x1800e1c4f  call    cs:__imp_CoTaskMemFree
0x1800e1c56  nop     dword ptr [rax+rax+00h]
0x1800e1c5b  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x1800e1c60  call    cs:__imp_LocalFree
0x1800e1c67  nop     dword ptr [rax+rax+00h]
0x1800e1c6c  jmp     short loc_1800E1C75
0x1800e1c6e  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800e1c73  mov     ebx, eax
0x1800e1c75  mov     rcx, [rsp+78h+lpSource]; hMem
0x1800e1c7a  call    cs:__imp_LocalFree
0x1800e1c81  nop     dword ptr [rax+rax+00h]
0x1800e1c86  mov     eax, ebx
0x1800e1c88  add     rsp, 58h
0x1800e1c8c  pop     rdi
0x1800e1c8d  pop     rsi
0x1800e1c8e  pop     rbp
0x1800e1c8f  pop     rbx
0x1800e1c90  retn
```
