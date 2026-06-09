# CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)

- ea: `0x180070564`
- end: `0x180070723`
- name: `?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z`
- size: `447`
- prototype: `int(CSxFunctionTracer *__hidden this, HINSTANCE, unsigned int, unsigned int, const unsigned __int16 **)`
- caller_count: `39`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017e74`
- `0x18001839c`
- `0x180018614`
- `0x1800189ac`
- `0x1800190e8`
- `0x1800195ec`
- `0x18001aa60`
- `0x18001c468`
- `0x18001c818`
- `0x18001c978`
- `0x18001d298`
- `0x18001d918`
- `0x18001ed20`
- `0x180027870`
- `0x180027a10`
- `0x180028300`
- `0x18002b578`
- `0x18002c07c`
- `0x18002d1a4`
- `0x18002d470`
- `0x18002dbbc`
- `0x18002e8c8`
- `0x18002ec28`
- `0x18002eddc`
- `0x18002f208`
- `0x18002f968`
- `0x180030bf4`
- `0x180031134`
- `0x180031310`
- `0x1800316a4`
- `0x18003dee0`
- `0x180041b90`
- `0x180062814`
- `0x18007038c`
- `0x1800b08e0`
- `0x1800b14e0`
- `0x1800b15f0`
- `0x1800b18d0`
- `0x1800b3250`

## callees

- `0x18006d058`
- `0x180070564`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800706ba`
- `KERNEL32!LocalFree` at `0x1800706df`
- `KERNEL32!LocalFree` at `0x18007070e`
- `KERNEL32!LocalFree` at `0x1800706ba`
- `KERNEL32!LocalFree` at `0x1800706df`
- `KERNEL32!LocalFree` at `0x18007070e`
- `KERNEL32!FormatMessageW` at `0x18007067d`
- `KERNEL32!FormatMessageW` at `0x18007067d`
- `KERNEL32!GetLastError` at `0x1800705f3`
- `KERNEL32!GetLastError` at `0x180070687`
- `KERNEL32!GetLastError` at `0x1800705f3`
- `KERNEL32!GetLastError` at `0x180070687`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800705e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800705e7`
- `ole32!CoTaskMemFree` at `0x1800706fe`
- `ole32!CoTaskMemFree` at `0x1800706fe`
- `ole32!CoTaskMemAlloc` at `0x18007062d`
- `ole32!CoTaskMemAlloc` at `0x18007062d`

## pseudocode

```c
__int64 __fastcall CSxFunctionTracer::_SetContextHelper(
        CSxFunctionTracer *this,
        HINSTANCE a2,
        UINT a3,
        unsigned int a4,
        va_list *Arguments)
{
  signed int v7; // ebx
  __int64 i; // rcx
  unsigned int StringW; // eax
  unsigned __int64 v10; // rbx
  signed int LastError; // eax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rsi
  signed int v14; // eax
  HLOCAL v15; // rax
  void *v16; // rcx
  __int64 v17; // rax
  void *v18; // rcx
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-48h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-40h] BYREF

  *(_QWORD *)lpBuffer = 0;
  *(_QWORD *)Buffer = 0;
  if ( (a4 == 0) != (Arguments == 0) )
    return (unsigned int)-2147024809;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( !Arguments[i] )
      return (unsigned int)-2147024809;
  }
  if ( !*((_QWORD *)this + 4) )
    return 1;
  StringW = LoadStringW(a2, a3, Buffer, 0);
  v10 = StringW;
  if ( !StringW )
  {
LABEL_10:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  if ( *(_QWORD *)Buffer )
  {
    v12 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (StringW + 1));
    v13 = v12;
    if ( v12 )
    {
      v7 = StringCchCopyNW(v12, (unsigned int)(v10 + 1), *(const unsigned __int16 **)Buffer, v10);
      if ( v7 >= 0 )
      {
        if ( FormatMessageW(0x2500u, v13, 0, 0, lpBuffer, 1u, Arguments) )
        {
          v15 = *(HLOCAL *)lpBuffer;
          if ( *(_QWORD *)lpBuffer )
          {
            v16 = (void *)*((_QWORD *)this + 5);
            v7 = 0;
            if ( v16 )
            {
              LocalFree(v16);
              v15 = *(HLOCAL *)lpBuffer;
            }
            *((_QWORD *)this + 5) = v15;
            v17 = *((_QWORD *)this + 4);
            *((_DWORD *)this + 12) = a3;
            *(_QWORD *)lpBuffer = 0;
            v18 = *(void **)(v17 + 16);
            if ( v18 )
            {
              LocalFree(v18);
              *(_QWORD *)(*((_QWORD *)this + 4) + 16LL) = 0;
            }
            *(_DWORD *)(*((_QWORD *)this + 4) + 4LL) = 0;
            *(_DWORD *)(*((_QWORD *)this + 4) + 24LL) = 0;
          }
          else
          {
            v7 = -2147467259;
          }
        }
        else
        {
          v14 = GetLastError();
          v7 = v14;
          if ( v14 > 0 )
            v7 = (unsigned __int16)v14 | 0x80070000;
        }
      }
      CoTaskMemFree(v13);
      goto LABEL_27;
    }
    goto LABEL_10;
  }
  v7 = -2147467259;
LABEL_27:
  if ( *(_QWORD *)lpBuffer )
    LocalFree(*(HLOCAL *)lpBuffer);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180070564  push    rbx
0x180070566  push    rbp
0x180070567  push    rsi
0x180070568  push    rdi
0x180070569  push    r14
0x18007056b  push    r15
0x18007056d  sub     rsp, 58h
0x180070571  mov     rbp, [rsp+88h+arg_20]
0x180070579  xor     r10d, r10d
0x18007057c  test    r9d, r9d
0x18007057f  mov     qword ptr [rsp+88h+var_48], 0
0x180070588  mov     r15d, r8d
0x18007058b  mov     qword ptr [rsp+88h+Buffer], 0
0x180070594  setz    r10b
0x180070598  mov     r11, rdx
0x18007059b  xor     eax, eax
0x18007059d  mov     rdi, rcx
0x1800705a0  test    rbp, rbp
0x1800705a3  setz    al
0x1800705a6  cmp     r10d, eax
0x1800705a9  jz      short loc_1800705B5
0x1800705ab  mov     ebx, 80070057h
0x1800705b0  jmp     loc_180070714
0x1800705b5  xor     ecx, ecx
0x1800705b7  cmp     ecx, r9d
0x1800705ba  jnb     short loc_1800705C8
0x1800705bc  cmp     qword ptr [rbp+rcx*8+0], 0
0x1800705c2  jz      short loc_1800705AB
0x1800705c4  inc     ecx
0x1800705c6  jmp     short loc_1800705B7
0x1800705c8  cmp     qword ptr [rdi+20h], 0
0x1800705cd  jnz     short loc_1800705D9
0x1800705cf  mov     ebx, 1
0x1800705d4  jmp     loc_180070714
0x1800705d9  xor     r9d, r9d; cchBufferMax
0x1800705dc  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x1800705e1  mov     edx, r15d; uID
0x1800705e4  mov     rcx, r11; hInstance
0x1800705e7  call    cs:__imp_LoadStringW
0x1800705ed  mov     ebx, eax
0x1800705ef  test    eax, eax
0x1800705f1  jnz     short loc_180070611
0x1800705f3  call    cs:__imp_GetLastError
0x1800705f9  mov     ebx, eax
0x1800705fb  test    eax, eax
0x1800705fd  jle     loc_180070704
0x180070603  movzx   ebx, ax
0x180070606  or      ebx, 80070000h
0x18007060c  jmp     loc_180070704
0x180070611  cmp     qword ptr [rsp+88h+Buffer], 0
0x180070617  jnz     short loc_180070623
0x180070619  mov     ebx, 80004005h
0x18007061e  jmp     loc_180070704
0x180070623  lea     eax, [rbx+1]
0x180070626  lea     rcx, [rax+rax]; cb
0x18007062a  mov     r14d, eax
0x18007062d  call    cs:__imp_CoTaskMemAlloc
0x180070633  mov     rsi, rax
0x180070636  test    rax, rax
0x180070639  jz      short loc_1800705F3
0x18007063b  mov     r8, qword ptr [rsp+88h+Buffer]; unsigned __int16 *
0x180070640  mov     r9, rbx; unsigned __int64
0x180070643  mov     edx, r14d; unsigned __int64
0x180070646  mov     rcx, rax; unsigned __int16 *
0x180070649  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007064e  mov     ebx, eax
0x180070650  test    eax, eax
0x180070652  js      loc_1800706FB
0x180070658  mov     [rsp+88h+Arguments], rbp; Arguments
0x18007065d  lea     rax, [rsp+88h+var_48]
0x180070662  mov     [rsp+88h+nSize], 1; nSize
0x18007066a  xor     r9d, r9d; dwLanguageId
0x18007066d  xor     r8d, r8d; dwMessageId
0x180070670  mov     [rsp+88h+lpBuffer], rax; lpBuffer
0x180070675  mov     rdx, rsi; lpSource
0x180070678  mov     ecx, 2500h; dwFlags
0x18007067d  call    cs:__imp_FormatMessageW
0x180070683  test    eax, eax
0x180070685  jnz     short loc_18007069E
0x180070687  call    cs:__imp_GetLastError
0x18007068d  mov     ebx, eax
0x18007068f  test    eax, eax
0x180070691  jle     short loc_1800706FB
0x180070693  movzx   ebx, ax
0x180070696  or      ebx, 80070000h
0x18007069c  jmp     short loc_1800706FB
0x18007069e  mov     rax, qword ptr [rsp+88h+var_48]
0x1800706a3  test    rax, rax
0x1800706a6  jnz     short loc_1800706AF
0x1800706a8  mov     ebx, 80004005h
0x1800706ad  jmp     short loc_1800706FB
0x1800706af  mov     rcx, [rdi+28h]; hMem
0x1800706b3  xor     ebx, ebx
0x1800706b5  test    rcx, rcx
0x1800706b8  jz      short loc_1800706C5
0x1800706ba  call    cs:__imp_LocalFree
0x1800706c0  mov     rax, qword ptr [rsp+88h+var_48]
0x1800706c5  mov     [rdi+28h], rax
0x1800706c9  mov     rax, [rdi+20h]
0x1800706cd  mov     [rdi+30h], r15d
0x1800706d1  mov     qword ptr [rsp+88h+var_48], rbx
0x1800706d6  mov     rcx, [rax+10h]; hMem
0x1800706da  test    rcx, rcx
0x1800706dd  jz      short loc_1800706ED
0x1800706df  call    cs:__imp_LocalFree
0x1800706e5  mov     rax, [rdi+20h]
0x1800706e9  mov     [rax+10h], rbx
0x1800706ed  mov     rax, [rdi+20h]
0x1800706f1  mov     [rax+4], ebx
0x1800706f4  mov     rax, [rdi+20h]
0x1800706f8  mov     [rax+18h], ebx
0x1800706fb  mov     rcx, rsi; pv
0x1800706fe  call    cs:__imp_CoTaskMemFree
0x180070704  mov     rcx, qword ptr [rsp+88h+var_48]; hMem
0x180070709  test    rcx, rcx
0x18007070c  jz      short loc_180070714
0x18007070e  call    cs:__imp_LocalFree
0x180070714  mov     eax, ebx
0x180070716  add     rsp, 58h
0x18007071a  pop     r15
0x18007071c  pop     r14
0x18007071e  pop     rdi
0x18007071f  pop     rsi
0x180070720  pop     rbp
0x180070721  pop     rbx
0x180070722  retn
```
