# ResourceStringCoAllocFormatMessageVA

- ea: `0x18002fda8`
- end: `0x18002fe93`
- name: `ResourceStringCoAllocFormatMessageVA`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fd7c`

## callees

- `0x18002fda8`
- `0x18002ff20`
- `0x180030120`
- `0x180089e08`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fe79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fe63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002fe0e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002fe0e`

## pseudocode

```c
__int64 ResourceStringCoAllocFormatMessageVA(HMODULE a1, unsigned int a2, _QWORD *a3, ...)
{
  int ErrorError; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  void *v8; // r10
  int lpBuffer; // [rsp+20h] [rbp-58h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  LPCVOID lpSource[6]; // [rsp+48h] [rbp-30h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  lpSource[0] = 0;
  ErrorError = TResourceStringAllocCopyEx<unsigned short *>(
                 a1,
                 a2,
                 (__int64)a3,
                 (__int64 (__fastcall *)(_QWORD, size_t, char **))ResourceStringAllocCopyExLocalAlloc,
                 lpBuffer,
                 (char *)lpSource);
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
0x18002fda8  mov     r11, rsp
0x18002fdab  mov     [r11+20h], r9
0x18002fdaf  push    rbx
0x18002fdb0  push    rbp
0x18002fdb1  push    rsi
0x18002fdb2  push    rdi
0x18002fdb3  sub     rsp, 58h
0x18002fdb7  lea     rax, [r11-30h]
0x18002fdbb  xor     ebp, ebp
0x18002fdbd  lea     r9, _ResourceStringAllocCopyExLocalAlloc
0x18002fdc4  mov     [r11-30h], rbp
0x18002fdc8  mov     [r11-50h], rax
0x18002fdcc  mov     rsi, r8
0x18002fdcf  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18002fdd4  mov     ebx, eax
0x18002fdd6  test    eax, eax
0x18002fdd8  js      loc_18002FE7F
0x18002fdde  mov     rdx, [rsp+78h+lpSource]; lpSource
0x18002fde3  lea     rax, [rsp+78h+arg_18]
0x18002fdeb  mov     [rsp+78h+Arguments], rax; Arguments
0x18002fdf0  xor     r9d, r9d; dwLanguageId
0x18002fdf3  lea     rax, [rsp+78h+Buffer]
0x18002fdf8  mov     [rsp+78h+nSize], ebp; nSize
0x18002fdfc  xor     r8d, r8d; dwMessageId
0x18002fdff  mov     [rsp+78h+lpBuffer], rax; lpBuffer
0x18002fe04  mov     ecx, 500h; dwFlags
0x18002fe09  mov     qword ptr [rsp+78h+Buffer], rbp
0x18002fe0e  call    cs:__imp_FormatMessageW
0x18002fe14  test    eax, eax
0x18002fe16  jz      short loc_18002FE8A
0x18002fe18  mov     rcx, qword ptr [rsp+78h+Buffer]
0x18002fe1d  mov     ebx, 8007000Eh
0x18002fe22  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fe26  inc     rax
0x18002fe29  cmp     [rcx+rax*2], bp
0x18002fe2d  jnz     short loc_18002FE26
0x18002fe2f  inc     eax
0x18002fe31  mov     edi, eax
0x18002fe33  lea     rcx, [rax+rax]; cb
0x18002fe37  call    cs:__imp_CoTaskMemAlloc
0x18002fe3d  mov     r10, rax
0x18002fe40  test    rax, rax
0x18002fe43  jz      short loc_18002FE69
0x18002fe45  mov     r8, qword ptr [rsp+78h+Buffer]; unsigned __int16 *
0x18002fe4a  mov     edx, edi; unsigned __int64
0x18002fe4c  mov     rcx, rax; unsigned __int16 *
0x18002fe4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fe54  mov     ebx, eax
0x18002fe56  test    eax, eax
0x18002fe58  js      short loc_18002FE60
0x18002fe5a  mov     [rsi], r10
0x18002fe5d  mov     r10, rbp
0x18002fe60  mov     rcx, r10; pv
0x18002fe63  call    cs:__imp_CoTaskMemFree
0x18002fe69  mov     rcx, qword ptr [rsp+78h+Buffer]; hMem
0x18002fe6e  call    cs:__imp_LocalFree
0x18002fe74  mov     rcx, [rsp+78h+lpSource]; hMem
0x18002fe79  call    cs:__imp_LocalFree
0x18002fe7f  mov     eax, ebx
0x18002fe81  add     rsp, 58h
0x18002fe85  pop     rdi
0x18002fe86  pop     rsi
0x18002fe87  pop     rbp
0x18002fe88  pop     rbx
0x18002fe89  retn
0x18002fe8a  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18002fe8f  mov     ebx, eax
0x18002fe91  jmp     short loc_18002FE74
```
