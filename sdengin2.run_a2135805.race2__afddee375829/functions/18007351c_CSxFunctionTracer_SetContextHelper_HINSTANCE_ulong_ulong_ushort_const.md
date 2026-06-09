# CSxFunctionTracer::_SetContextHelper(HINSTANCE__ *,ulong,ulong,ushort const * *)

- ea: `0x18007351c`
- end: `0x180073712`
- name: `?_SetContextHelper@CSxFunctionTracer@@AEAAJPEAUHINSTANCE__@@KKPEAPEBG@Z`
- size: `502`
- prototype: `int(CSxFunctionTracer *__hidden this, HINSTANCE, unsigned int, unsigned int, const unsigned __int16 **)`
- caller_count: `39`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180018874`
- `0x180018db0`
- `0x180019028`
- `0x1800193c0`
- `0x180019b24`
- `0x18001a040`
- `0x18001b4f4`
- `0x18001cf40`
- `0x18001d2f8`
- `0x18001d464`
- `0x18001dd8c`
- `0x18001e410`
- `0x18001f894`
- `0x1800288ac`
- `0x180028a4c`
- `0x18002935c`
- `0x18002c62c`
- `0x18002d16c`
- `0x18002e350`
- `0x18002e620`
- `0x18002ed94`
- `0x18002fb48`
- `0x18002feac`
- `0x180030064`
- `0x180030494`
- `0x180030bfc`
- `0x180031ed4`
- `0x180032428`
- `0x18003260c`
- `0x1800329b4`
- `0x18003f5f0`
- `0x1800433d8`
- `0x1800650a8`
- `0x180073344`
- `0x1800b61c0`
- `0x1800b6e60`
- `0x1800b6f70`
- `0x1800b7250`
- `0x1800b8be0`

## callees

- `0x18006fd18`
- `0x18007351c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180073690`
- `KERNEL32!LocalFree` at `0x1800736bb`
- `KERNEL32!LocalFree` at `0x1800736f6`
- `KERNEL32!LocalFree` at `0x180073690`
- `KERNEL32!LocalFree` at `0x1800736bb`
- `KERNEL32!LocalFree` at `0x1800736f6`
- `KERNEL32!FormatMessageW` at `0x180073647`
- `KERNEL32!FormatMessageW` at `0x180073647`
- `KERNEL32!GetLastError` at `0x1800735b1`
- `KERNEL32!GetLastError` at `0x180073657`
- `KERNEL32!GetLastError` at `0x1800735b1`
- `KERNEL32!GetLastError` at `0x180073657`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007359f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007359f`
- `ole32!CoTaskMemFree` at `0x1800736e0`
- `ole32!CoTaskMemFree` at `0x1800736e0`
- `ole32!CoTaskMemAlloc` at `0x1800735f1`
- `ole32!CoTaskMemAlloc` at `0x1800735f1`

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
0x18007351c  push    rbx
0x18007351e  push    rbp
0x18007351f  push    rsi
0x180073520  push    rdi
0x180073521  push    r14
0x180073523  push    r15
0x180073525  sub     rsp, 58h
0x180073529  mov     rbp, [rsp+88h+arg_20]
0x180073531  xor     r10d, r10d
0x180073534  test    r9d, r9d
0x180073537  mov     qword ptr [rsp+88h+var_48], 0
0x180073540  mov     r15d, r8d
0x180073543  mov     qword ptr [rsp+88h+Buffer], 0
0x18007354c  setz    r10b
0x180073550  mov     r11, rdx
0x180073553  xor     eax, eax
0x180073555  mov     rdi, rcx
0x180073558  test    rbp, rbp
0x18007355b  setz    al
0x18007355e  cmp     r10d, eax
0x180073561  jz      short loc_18007356D
0x180073563  mov     ebx, 80070057h
0x180073568  jmp     loc_180073702
0x18007356d  xor     ecx, ecx
0x18007356f  cmp     ecx, r9d
0x180073572  jnb     short loc_180073580
0x180073574  cmp     qword ptr [rbp+rcx*8+0], 0
0x18007357a  jz      short loc_180073563
0x18007357c  inc     ecx
0x18007357e  jmp     short loc_18007356F
0x180073580  cmp     qword ptr [rdi+20h], 0
0x180073585  jnz     short loc_180073591
0x180073587  mov     ebx, 1
0x18007358c  jmp     loc_180073702
0x180073591  xor     r9d, r9d; cchBufferMax
0x180073594  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x180073599  mov     edx, r15d; uID
0x18007359c  mov     rcx, r11; hInstance
0x18007359f  call    cs:__imp_LoadStringW
0x1800735a6  nop     dword ptr [rax+rax+00h]
0x1800735ab  mov     ebx, eax
0x1800735ad  test    eax, eax
0x1800735af  jnz     short loc_1800735D5
0x1800735b1  call    cs:__imp_GetLastError
0x1800735b8  nop     dword ptr [rax+rax+00h]
0x1800735bd  mov     ebx, eax
0x1800735bf  test    eax, eax
0x1800735c1  jle     loc_1800736EC
0x1800735c7  movzx   ebx, ax
0x1800735ca  or      ebx, 80070000h
0x1800735d0  jmp     loc_1800736EC
0x1800735d5  cmp     qword ptr [rsp+88h+Buffer], 0
0x1800735db  jnz     short loc_1800735E7
0x1800735dd  mov     ebx, 80004005h
0x1800735e2  jmp     loc_1800736EC
0x1800735e7  lea     eax, [rbx+1]
0x1800735ea  lea     rcx, [rax+rax]; cb
0x1800735ee  mov     r14d, eax
0x1800735f1  call    cs:__imp_CoTaskMemAlloc
0x1800735f8  nop     dword ptr [rax+rax+00h]
0x1800735fd  mov     rsi, rax
0x180073600  test    rax, rax
0x180073603  jz      short loc_1800735B1
0x180073605  mov     r8, qword ptr [rsp+88h+Buffer]; unsigned __int16 *
0x18007360a  mov     r9, rbx; unsigned __int64
0x18007360d  mov     edx, r14d; unsigned __int64
0x180073610  mov     rcx, rax; unsigned __int16 *
0x180073613  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180073618  mov     ebx, eax
0x18007361a  test    eax, eax
0x18007361c  js      loc_1800736DD
0x180073622  mov     [rsp+88h+Arguments], rbp; Arguments
0x180073627  lea     rax, [rsp+88h+var_48]
0x18007362c  mov     [rsp+88h+nSize], 1; nSize
0x180073634  xor     r9d, r9d; dwLanguageId
0x180073637  xor     r8d, r8d; dwMessageId
0x18007363a  mov     [rsp+88h+lpBuffer], rax; lpBuffer
0x18007363f  mov     rdx, rsi; lpSource
0x180073642  mov     ecx, 2500h; dwFlags
0x180073647  call    cs:__imp_FormatMessageW
0x18007364e  nop     dword ptr [rax+rax+00h]
0x180073653  test    eax, eax
0x180073655  jnz     short loc_180073674
0x180073657  call    cs:__imp_GetLastError
0x18007365e  nop     dword ptr [rax+rax+00h]
0x180073663  mov     ebx, eax
0x180073665  test    eax, eax
0x180073667  jle     short loc_1800736DD
0x180073669  movzx   ebx, ax
0x18007366c  or      ebx, 80070000h
0x180073672  jmp     short loc_1800736DD
0x180073674  mov     rax, qword ptr [rsp+88h+var_48]
0x180073679  test    rax, rax
0x18007367c  jnz     short loc_180073685
0x18007367e  mov     ebx, 80004005h
0x180073683  jmp     short loc_1800736DD
0x180073685  mov     rcx, [rdi+28h]; hMem
0x180073689  xor     ebx, ebx
0x18007368b  test    rcx, rcx
0x18007368e  jz      short loc_1800736A1
0x180073690  call    cs:__imp_LocalFree
0x180073697  nop     dword ptr [rax+rax+00h]
0x18007369c  mov     rax, qword ptr [rsp+88h+var_48]
0x1800736a1  mov     [rdi+28h], rax
0x1800736a5  mov     rax, [rdi+20h]
0x1800736a9  mov     [rdi+30h], r15d
0x1800736ad  mov     qword ptr [rsp+88h+var_48], rbx
0x1800736b2  mov     rcx, [rax+10h]; hMem
0x1800736b6  test    rcx, rcx
0x1800736b9  jz      short loc_1800736CF
0x1800736bb  call    cs:__imp_LocalFree
0x1800736c2  nop     dword ptr [rax+rax+00h]
0x1800736c7  mov     rax, [rdi+20h]
0x1800736cb  mov     [rax+10h], rbx
0x1800736cf  mov     rax, [rdi+20h]
0x1800736d3  mov     [rax+4], ebx
0x1800736d6  mov     rax, [rdi+20h]
0x1800736da  mov     [rax+18h], ebx
0x1800736dd  mov     rcx, rsi; pv
0x1800736e0  call    cs:__imp_CoTaskMemFree
0x1800736e7  nop     dword ptr [rax+rax+00h]
0x1800736ec  mov     rcx, qword ptr [rsp+88h+var_48]; hMem
0x1800736f1  test    rcx, rcx
0x1800736f4  jz      short loc_180073702
0x1800736f6  call    cs:__imp_LocalFree
0x1800736fd  nop     dword ptr [rax+rax+00h]
0x180073702  mov     eax, ebx
0x180073704  add     rsp, 58h
0x180073708  pop     r15
0x18007370a  pop     r14
0x18007370c  pop     rdi
0x18007370d  pop     rsi
0x18007370e  pop     rbp
0x18007370f  pop     rbx
0x180073710  retn
```
