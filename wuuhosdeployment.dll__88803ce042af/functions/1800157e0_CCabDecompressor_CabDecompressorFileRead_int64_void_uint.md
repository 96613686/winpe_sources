# CCabDecompressor::CabDecompressorFileRead(__int64,void *,uint)

- ea: `0x1800157e0`
- end: `0x180015952`
- name: `?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z`
- size: `370`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000956c`
- `0x1800157e0`
- `0x180042630`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158f6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800158cb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800158cb`

## string_xrefs

- `0x18001581e`: `CabDecompressorFileRead - invalid buffer`
- `0x180015866`: `CabDecompressorFileRead - invalid offset`
- `0x180015916`: `CabDecompressorFileRead - ReadFile`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileRead(INT_PTR hf, _BYTE *pv, UINT cb)
{
  bool v3; // zf
  _BYTE *v5; // rsi
  __int64 v7; // r14
  UINT v8; // ebx
  UINT v9; // ecx
  UINT v10; // ebx
  __int64 v11; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(_DWORD *)(hf + 16) == 0;
  v5 = pv;
  NumberOfBytesRead = -1;
  if ( v3 )
  {
    v7 = *(_QWORD *)(hf + 8);
    if ( !v7 )
    {
      WUTrace(0, 0, 32, 3);
      return NumberOfBytesRead;
    }
    v9 = *(_DWORD *)(hf + 20);
    v10 = *(_DWORD *)(v7 + 20);
    if ( v9 + cb >= v10 )
    {
      if ( v9 > v10 )
      {
        WUTrace(0, 0, 32, 3);
        v8 = -1;
      }
      else
      {
        v8 = v10 - v9;
      }
    }
    else
    {
      v8 = cb;
    }
    NumberOfBytesRead = v8;
    if ( v8 != -1 && v8 == cb )
    {
      memmove(v5, (const void *)(*(_QWORD *)(v7 + 8) + *(unsigned int *)(hf + 20)), v8);
      *(_DWORD *)(hf + 20) += v8;
    }
  }
  else
  {
    if ( !ReadFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesRead, 0) )
    {
      GetLastError();
      WUTrace(0, 0, 32, 3);
      return (UINT)-1;
    }
    if ( !*(_DWORD *)(hf + 24) )
      return NumberOfBytesRead;
    v8 = NumberOfBytesRead;
    if ( NumberOfBytesRead )
    {
      v11 = NumberOfBytesRead;
      do
      {
        *v5 = ~*v5;
        ++v5;
        --v11;
      }
      while ( v11 );
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800157e0  push    rbx
0x1800157e2  push    rbp
0x1800157e3  push    rsi
0x1800157e4  push    rdi
0x1800157e5  push    r14
0x1800157e7  sub     rsp, 40h
0x1800157eb  mov     rax, cs:__security_cookie
0x1800157f2  xor     rax, rsp
0x1800157f5  mov     [rsp+68h+var_30], rax
0x1800157fa  cmp     dword ptr [rcx+10h], 0
0x1800157fe  mov     ebp, r8d
0x180015801  mov     rsi, rdx
0x180015804  mov     [rsp+68h+NumberOfBytesRead], 0FFFFFFFFh
0x18001580c  mov     rdi, rcx
0x18001580f  jnz     loc_1800158B9
0x180015815  mov     r14, [rcx+8]
0x180015819  test    r14, r14
0x18001581c  jnz     short loc_180015849
0x18001581e  lea     rax, aCabdecompresso_0; "CabDecompressorFileRead - invalid buffe"...
0x180015825  xor     edx, edx
0x180015827  mov     [rsp+68h+var_40], rax
0x18001582c  lea     r9d, [r14+3]
0x180015830  xor     ecx, ecx
0x180015832  mov     [rsp+68h+lpOverlapped], r14
0x180015837  lea     r8d, [r14+20h]
0x18001583b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015840  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x180015844  jmp     loc_180015938
0x180015849  mov     ecx, [rcx+14h]
0x18001584c  mov     ebx, [r14+14h]
0x180015850  lea     eax, [rcx+r8]
0x180015854  cmp     eax, ebx
0x180015856  jnb     short loc_18001585C
0x180015858  mov     ebx, ebp
0x18001585a  jmp     short loc_18001588D
0x18001585c  cmp     ecx, ebx
0x18001585e  ja      short loc_180015864
0x180015860  sub     ebx, ecx
0x180015862  jmp     short loc_18001588D
0x180015864  xor     edx, edx
0x180015866  lea     rax, aCabdecompresso_2; "CabDecompressorFileRead - invalid offse"...
0x18001586d  mov     [rsp+68h+var_40], rax
0x180015872  xor     ecx, ecx
0x180015874  mov     [rsp+68h+lpOverlapped], 0
0x18001587d  lea     r9d, [rdx+3]
0x180015881  lea     r8d, [rdx+20h]
0x180015885  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001588a  or      ebx, 0FFFFFFFFh
0x18001588d  mov     [rsp+68h+NumberOfBytesRead], ebx
0x180015891  cmp     ebx, 0FFFFFFFFh
0x180015894  jz      loc_180015938
0x18001589a  cmp     ebx, ebp
0x18001589c  jnz     loc_180015938
0x1800158a2  mov     edx, [rdi+14h]
0x1800158a5  mov     rcx, rsi; void *
0x1800158a8  add     rdx, [r14+8]; Src
0x1800158ac  mov     r8d, ebx; Size
0x1800158af  call    memmove
0x1800158b4  add     [rdi+14h], ebx
0x1800158b7  jmp     short loc_180015938
0x1800158b9  mov     rcx, [rcx+8]; hFile
0x1800158bd  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800158c2  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800158cb  call    cs:__imp_ReadFile
0x1800158d1  test    eax, eax
0x1800158d3  jz      short loc_1800158F6
0x1800158d5  cmp     dword ptr [rdi+18h], 0
0x1800158d9  jz      loc_180015840
0x1800158df  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x1800158e3  test    ebx, ebx
0x1800158e5  jz      short loc_180015938
0x1800158e7  mov     ecx, ebx
0x1800158e9  not     byte ptr [rsi]
0x1800158eb  inc     rsi
0x1800158ee  sub     rcx, 1
0x1800158f2  jnz     short loc_1800158E9
0x1800158f4  jmp     short loc_180015938
0x1800158f6  call    cs:__imp_GetLastError
0x1800158fc  movzx   ecx, ax
0x1800158ff  or      ecx, 80070000h
0x180015905  test    eax, eax
0x180015907  cmovle  ecx, eax
0x18001590a  mov     eax, 8000FFFFh
0x18001590f  test    ecx, ecx
0x180015911  cmovns  ecx, eax
0x180015914  xor     edx, edx
0x180015916  lea     rax, aCabdecompresso; "CabDecompressorFileRead - ReadFile"
0x18001591d  mov     [rsp+68h+var_40], rax
0x180015922  mov     dword ptr [rsp+68h+lpOverlapped], ecx
0x180015926  xor     ecx, ecx
0x180015928  lea     r9d, [rdx+3]
0x18001592c  lea     r8d, [rdx+20h]
0x180015930  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015935  or      ebx, 0FFFFFFFFh
0x180015938  mov     eax, ebx
0x18001593a  mov     rcx, [rsp+68h+var_30]
0x18001593f  xor     rcx, rsp; StackCookie
0x180015942  call    __security_check_cookie
0x180015947  add     rsp, 40h
0x18001594b  pop     r14
0x18001594d  pop     rdi
0x18001594e  pop     rsi
0x18001594f  pop     rbp
0x180015950  pop     rbx
0x180015951  retn
```
