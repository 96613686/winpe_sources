# WxNewStringAtoWCch<WxCoTaskAllocator>(char const *,ulong,ushort * *)

- ea: `0x18000bd94`
- end: `0x18000bf79`
- name: `??$WxNewStringAtoWCch@VWxCoTaskAllocator@@@@YAJPEBDKPEAPEAG@Z`
- size: `485`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b914`
- `0x18001f610`
- `0x18004c090`
- `0x18005c52c`
- `0x18007b1e8`

## callees

- `0x18000bd94`
- `0x18000bfd0`
- `0x18000c4d0`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf2d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000bdf9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000be63`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000bdf9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000be63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be23`

## pseudocode

```c
__int64 __fastcall WxNewStringAtoWCch<WxCoTaskAllocator>(LPCCH lpMultiByteStr, int cbMultiByte, _QWORD *a3)
{
  void *v3; // rbx
  int v7; // r13d
  void *v8; // rdi
  int v9; // eax
  unsigned int v10; // ecx
  size_t v11; // rax
  void *v12; // rax
  void *lpWideCharStr; // rsi
  int v14; // eax
  signed int v15; // esi
  void *v16; // rax
  signed int LastError; // eax
  int cchWideChar; // [rsp+30h] [rbp-20h]
  void *v20; // [rsp+38h] [rbp-18h] BYREF
  void *v21; // [rsp+40h] [rbp-10h] BYREF
  size_t v22; // [rsp+48h] [rbp-8h]

  v3 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  *a3 = 0;
  if ( !lpMultiByteStr )
    return (unsigned int)-2147024809;
  v20 = 0;
  v7 = -1;
  if ( cbMultiByte != -1 )
    v7 = cbMultiByte;
  v8 = 0;
  v9 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v7, 0, 0);
  cchWideChar = v9;
  if ( v9 )
  {
    v10 = 2 * v9;
    HIDWORD(v22) = 0;
    v11 = (unsigned int)(2 * v9 + 2);
    v21 = 0;
    if ( cbMultiByte == -1 )
      v11 = v10;
    v22 = v11;
    v12 = CoTaskMemAlloc((unsigned int)v11);
    lpWideCharStr = v12;
    if ( v12 )
    {
      memset_0(v12, 0, v22);
      v3 = lpWideCharStr;
      v21 = lpWideCharStr;
      v14 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v7, (LPWSTR)lpWideCharStr, cchWideChar);
      if ( v14 )
      {
        if ( cbMultiByte != -1 )
          *((_WORD *)lpWideCharStr + v14) = 0;
        v8 = lpWideCharStr;
        v20 = lpWideCharStr;
        v3 = 0;
        v21 = 0;
        v15 = 0;
      }
      else
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( v15 >= 0 )
          v15 = -2147418113;
      }
    }
    else
    {
      HIDWORD(v22) = 76;
      v15 = -2147024882;
    }
    if ( v3 )
      WxCoTaskAllocator::Free(&v21);
    if ( v15 >= 0 )
      goto LABEL_16;
  }
  else
  {
    GetLastError();
  }
  v15 = WxNewStringAtoWCchCp<WxCoTaskAllocator>(lpMultiByteStr, cbMultiByte, 0);
  if ( v15 >= 0 )
  {
    v8 = v20;
LABEL_16:
    *a3 = v8;
    v16 = 0;
    v20 = 0;
    goto LABEL_17;
  }
  v16 = v20;
LABEL_17:
  if ( v16 )
    WxCoTaskAllocator::Free(&v20);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000bd94  mov     [rsp-38h+arg_18], rbx
0x18000bd99  push    rbp
0x18000bd9a  push    rsi
0x18000bd9b  push    rdi
0x18000bd9c  push    r12
0x18000bd9e  push    r13
0x18000bda0  push    r14
0x18000bda2  push    r15
0x18000bda4  mov     rbp, rsp
0x18000bda7  sub     rsp, 50h
0x18000bdab  xor     ebx, ebx
0x18000bdad  mov     r15, r8
0x18000bdb0  mov     [rbp+var_1C], ebx
0x18000bdb3  mov     r14d, edx
0x18000bdb6  mov     r12, rcx
0x18000bdb9  test    r8, r8
0x18000bdbc  jz      loc_18000BEEB
0x18000bdc2  mov     [r8], rbx
0x18000bdc5  test    rcx, rcx
0x18000bdc8  jz      loc_18000BF24
0x18000bdce  or      esi, 0FFFFFFFFh
0x18000bdd1  mov     [rsp+50h+cchWideChar], ebx; cchWideChar
0x18000bdd5  cmp     edx, esi
0x18000bdd7  mov     [rbp+var_1C], ebx
0x18000bdda  mov     r8, rcx; lpMultiByteStr
0x18000bddd  mov     [rbp+var_18], rbx
0x18000bde1  mov     r13d, esi
0x18000bde4  mov     [rsp+50h+lpWideCharStr], rbx; lpWideCharStr
0x18000bde9  cmovnz  r13d, edx
0x18000bded  mov     ecx, 0FDE9h; CodePage
0x18000bdf2  mov     r9d, r13d; cbMultiByte
0x18000bdf5  xor     edx, edx; dwFlags
0x18000bdf7  mov     edi, ebx
0x18000bdf9  call    cs:__imp_MultiByteToWideChar
0x18000bdff  mov     [rbp+var_20], eax
0x18000be02  test    eax, eax
0x18000be04  jz      loc_18000BF2D
0x18000be0a  lea     ecx, [rax+rax]
0x18000be0d  mov     [rbp+var_4], ebx
0x18000be10  lea     eax, [rcx+2]
0x18000be13  mov     [rbp+var_10], rbx
0x18000be17  cmp     r14d, esi
0x18000be1a  cmovz   eax, ecx
0x18000be1d  mov     ecx, eax; cb
0x18000be1f  mov     [rbp-8], rax
0x18000be23  call    cs:__imp_CoTaskMemAlloc
0x18000be29  mov     rsi, rax
0x18000be2c  test    rax, rax
0x18000be2f  jz      loc_18000BED6
0x18000be35  mov     r8, [rbp-8]; Size
0x18000be39  xor     edx, edx; Val
0x18000be3b  mov     rcx, rax; void *
0x18000be3e  call    memset_0
0x18000be43  mov     rbx, rsi
0x18000be46  mov     [rbp+var_10], rbx
0x18000be4a  mov     eax, [rbp+var_20]
0x18000be4d  mov     r9d, r13d; cbMultiByte
0x18000be50  mov     [rsp+50h+cchWideChar], eax; cchWideChar
0x18000be54  mov     r8, r12; lpMultiByteStr
0x18000be57  xor     edx, edx; dwFlags
0x18000be59  mov     [rsp+50h+lpWideCharStr], rbx; lpWideCharStr
0x18000be5e  mov     ecx, 0FDE9h; CodePage
0x18000be63  call    cs:__imp_MultiByteToWideChar
0x18000be69  test    eax, eax
0x18000be6b  jz      loc_18000BEF9
0x18000be71  cmp     r14d, 0FFFFFFFFh
0x18000be75  jnz     loc_18000BF62
0x18000be7b  mov     rdi, rbx
0x18000be7e  mov     [rbp+var_18], rbx
0x18000be82  xor     ebx, ebx
0x18000be84  mov     [rbp+var_10], rbx
0x18000be88  xor     esi, esi
0x18000be8a  test    rbx, rbx
0x18000be8d  jnz     short loc_18000BECB
0x18000be8f  xor     ebx, ebx
0x18000be91  test    esi, esi
0x18000be93  js      loc_18000BF3A
0x18000be99  mov     [r15], rdi
0x18000be9c  mov     rax, rbx
0x18000be9f  mov     [rbp+var_18], rbx
0x18000bea3  test    rax, rax
0x18000bea6  jz      short loc_18000BEB1
0x18000bea8  lea     rcx, [rbp+var_18]; void **
0x18000beac  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000beb1  mov     rbx, [rsp+50h+arg_18]
0x18000beb9  mov     eax, esi
0x18000bebb  add     rsp, 50h
0x18000bebf  pop     r15
0x18000bec1  pop     r14
0x18000bec3  pop     r13
0x18000bec5  pop     r12
0x18000bec7  pop     rdi
0x18000bec8  pop     rsi
0x18000bec9  pop     rbp
0x18000beca  retn
0x18000becb  lea     rcx, [rbp+var_10]; void **
0x18000becf  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000bed4  jmp     short loc_18000BE8F
0x18000bed6  mov     [rbp+var_4], 4Ch ; 'L'
0x18000bedd  mov     esi, 8007000Eh
0x18000bee2  mov     [rbp+var_1C], 0C5h
0x18000bee9  jmp     short loc_18000BE8A
0x18000beeb  mov     [rbp+var_1C], 0ECh
0x18000bef2  mov     esi, 80070057h
0x18000bef7  jmp     short loc_18000BEB1
0x18000bef9  call    cs:__imp_GetLastError
0x18000beff  mov     esi, eax
0x18000bf01  test    eax, eax
0x18000bf03  jle     short loc_18000BF0E
0x18000bf05  movzx   esi, ax
0x18000bf08  or      esi, 80070000h
0x18000bf0e  test    esi, esi
0x18000bf10  mov     [rbp+var_1C], 0D1h
0x18000bf17  mov     ecx, 8000FFFFh
0x18000bf1c  cmovns  esi, ecx
0x18000bf1f  jmp     loc_18000BE8A
0x18000bf24  mov     [rbp+var_1C], 0EFh
0x18000bf2b  jmp     short loc_18000BEF2
0x18000bf2d  call    cs:__imp_GetLastError
0x18000bf33  mov     [rbp+var_1C], 0B6h
0x18000bf3a  lea     r9, [rbp+var_18]
0x18000bf3e  xor     r8d, r8d; CodePage
0x18000bf41  mov     edx, r14d; cbMultiByte
0x18000bf44  mov     rcx, r12; lpMultiByteStr
0x18000bf47  call    ??$WxNewStringAtoWCchCp@VWxCoTaskAllocator@@@@YAJPEBDKKPEAPEAG@Z; WxNewStringAtoWCchCp<WxCoTaskAllocator>(char const *,ulong,ulong,ushort * *)
0x18000bf4c  mov     esi, eax
0x18000bf4e  test    eax, eax
0x18000bf50  jns     short loc_18000BF70
0x18000bf52  mov     rax, [rbp+var_18]
0x18000bf56  mov     [rbp+var_1C], 106h
0x18000bf5d  jmp     loc_18000BEA3
0x18000bf62  movsxd  rcx, eax
0x18000bf65  xor     eax, eax
0x18000bf67  mov     [rsi+rcx*2], ax
0x18000bf6b  jmp     loc_18000BE7B
0x18000bf70  mov     rdi, [rbp+var_18]
0x18000bf74  jmp     loc_18000BE99
```
