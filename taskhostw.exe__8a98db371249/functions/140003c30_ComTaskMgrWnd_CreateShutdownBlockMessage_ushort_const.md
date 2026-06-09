# ComTaskMgrWnd::CreateShutdownBlockMessage(ushort const *)

- ea: `0x140003c30`
- end: `0x140003e0c`
- name: `?CreateShutdownBlockMessage@ComTaskMgrWnd@@AEBAJPEBG@Z`
- size: `476`
- prototype: `int __fastcall(HWND *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003b10`

## callees

- `0x140003c30`
- `0x140003e54`
- `0x140007b4f`
- `0x14000a2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003dd3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003c82`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140003c82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003c67`
- `ext-ms-win-ntuser-misc-l1-1-0!ShutdownBlockReasonCreate` at `0x140003dc9`
- `ext-ms-win-ntuser-misc-l1-1-0!ShutdownBlockReasonCreate` at `0x140003dc9`

## pseudocode

```c
int __fastcall ComTaskMgrWnd::CreateShutdownBlockMessage(HWND *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  int result; // eax
  WCHAR *v6; // rax
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  const wchar_t *v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // rax
  _WORD *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // rcx
  WCHAR *v17; // rax
  const wchar_t *v18; // rdx
  __int64 v19; // rbp
  WCHAR *v20; // rdx
  WCHAR Buffer[512]; // [rsp+20h] [rbp-428h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, 0xC9u, Buffer, 512) )
  {
    if ( a2 )
    {
      v6 = Buffer;
      v7 = 512;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v7;
      }
      while ( v7 );
      v8 = 512 - v7;
      v9 = 2147483646;
      if ( v7 )
      {
        v10 = L" (";
        v11 = 2147483646;
        v7 = (unsigned __int64)&Buffer[v8];
        v12 = 512 - v8;
        if ( v8 != 512 )
        {
          do
          {
            if ( !v11 )
              break;
            if ( !*v10 )
              break;
            *(_WORD *)v7 = *v10++;
            v7 += 2LL;
            --v11;
            --v12;
          }
          while ( v12 );
        }
        v13 = (_WORD *)(v7 - 2);
        if ( v12 )
          v13 = (_WORD *)v7;
        *v13 = 0;
      }
      StringCchCatW(Buffer, v7, a2);
      v14 = 512;
      v15 = Buffer;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      v16 = 512 - v14;
      if ( v14 )
      {
        v17 = &Buffer[v16];
        v18 = L" )";
        v19 = 512 - v16;
        if ( 512 != v16 )
        {
          do
          {
            if ( !v9 )
              break;
            if ( !*v18 )
              break;
            *v17++ = *v18++;
            --v9;
            --v19;
          }
          while ( v19 );
        }
        v20 = v17 - 1;
        if ( v19 )
          v20 = v17;
        *v20 = 0;
      }
    }
    if ( ShutdownBlockReasonCreate(this[3], Buffer) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140003c30  push    rbp
0x140003c32  push    rsi
0x140003c33  push    rdi
0x140003c34  sub     rsp, 430h
0x140003c3b  mov     rax, cs:__security_cookie
0x140003c42  xor     rax, rsp
0x140003c45  mov     [rsp+448h+var_28], rax
0x140003c4d  mov     rdi, rdx
0x140003c50  mov     rsi, rcx
0x140003c53  xor     edx, edx; Val
0x140003c55  lea     rcx, [rsp+448h+Buffer]; void *
0x140003c5a  mov     r8d, 400h; Size
0x140003c60  call    memset_0
0x140003c65  xor     ecx, ecx; lpModuleName
0x140003c67  call    cs:__imp_GetModuleHandleW
0x140003c6d  mov     ebp, 200h
0x140003c72  lea     r8, [rsp+448h+Buffer]; lpBuffer
0x140003c77  mov     rcx, rax; hInstance
0x140003c7a  mov     r9d, ebp; cchBufferMax
0x140003c7d  mov     edx, 0C9h; uID
0x140003c82  call    cs:__imp_LoadStringW
0x140003c88  test    eax, eax
0x140003c8a  jnz     short loc_140003CA7
0x140003c8c  call    cs:__imp_GetLastError
0x140003c92  test    eax, eax
0x140003c94  jle     loc_140003DF1
0x140003c9a  movzx   eax, ax
0x140003c9d  or      eax, 80070000h
0x140003ca2  jmp     loc_140003DF1
0x140003ca7  mov     [rsp+448h+arg_10], rbx
0x140003caf  xor     ebx, ebx
0x140003cb1  test    rdi, rdi
0x140003cb4  jz      loc_140003DC0
0x140003cba  mov     [rsp+448h+arg_18], r14
0x140003cc2  lea     rax, [rsp+448h+Buffer]
0x140003cc7  mov     rdx, rbp
0x140003cca  cmp     [rax], bx
0x140003ccd  jz      short loc_140003CD9
0x140003ccf  add     rax, 2
0x140003cd3  sub     rdx, 1
0x140003cd7  jnz     short loc_140003CCA
0x140003cd9  xor     eax, eax
0x140003cdb  mov     rcx, rbp
0x140003cde  sub     rcx, rdx
0x140003ce1  mov     r14d, 7FFFFFFEh
0x140003ce7  test    rdx, rdx
0x140003cea  cmovz   rcx, rax
0x140003cee  jz      short loc_140003D3D
0x140003cf0  mov     rax, rbp
0x140003cf3  lea     rdx, [rsp+448h+Buffer]
0x140003cf8  lea     r9, asc_14000EBF8; " ("
0x140003cff  mov     r8d, r14d
0x140003d02  lea     rdx, [rdx+rcx*2]
0x140003d06  sub     rax, rcx
0x140003d09  jz      short loc_140003D2D
0x140003d0b  test    r8, r8
0x140003d0e  jz      short loc_140003D2D
0x140003d10  movzx   ecx, word ptr [r9]
0x140003d14  test    cx, cx
0x140003d17  jz      short loc_140003D2D
0x140003d19  mov     [rdx], cx
0x140003d1c  add     r9, 2
0x140003d20  add     rdx, 2; unsigned __int64
0x140003d24  dec     r8
0x140003d27  sub     rax, 1
0x140003d2b  jnz     short loc_140003D0B
0x140003d2d  test    rax, rax
0x140003d30  lea     rcx, [rdx-2]
0x140003d34  cmovnz  rcx, rdx
0x140003d38  xor     eax, eax
0x140003d3a  mov     [rcx], ax
0x140003d3d  mov     r8, rdi; unsigned __int16 *
0x140003d40  lea     rcx, [rsp+448h+Buffer]; unsigned __int16 *
0x140003d45  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003d4a  mov     rdx, rbp
0x140003d4d  lea     rax, [rsp+448h+Buffer]
0x140003d52  cmp     [rax], bx
0x140003d55  jz      short loc_140003D61
0x140003d57  add     rax, 2
0x140003d5b  sub     rdx, 1
0x140003d5f  jnz     short loc_140003D52
0x140003d61  xor     eax, eax
0x140003d63  mov     rcx, rbp
0x140003d66  sub     rcx, rdx
0x140003d69  test    rdx, rdx
0x140003d6c  cmovz   rcx, rax
0x140003d70  jz      short loc_140003DB8
0x140003d72  lea     rax, [rsp+448h+Buffer]
0x140003d77  lea     rax, [rax+rcx*2]
0x140003d7b  lea     rdx, asc_14000EC00; " )"
0x140003d82  sub     rbp, rcx
0x140003d85  jz      short loc_140003DA8
0x140003d87  test    r14, r14
0x140003d8a  jz      short loc_140003DA8
0x140003d8c  movzx   ecx, word ptr [rdx]
0x140003d8f  test    cx, cx
0x140003d92  jz      short loc_140003DA8
0x140003d94  mov     [rax], cx
0x140003d97  add     rdx, 2
0x140003d9b  add     rax, 2
0x140003d9f  dec     r14
0x140003da2  sub     rbp, 1
0x140003da6  jnz     short loc_140003D87
0x140003da8  test    rbp, rbp
0x140003dab  lea     rdx, [rax-2]
0x140003daf  cmovnz  rdx, rax
0x140003db3  xor     eax, eax
0x140003db5  mov     [rdx], ax
0x140003db8  mov     r14, [rsp+448h+arg_18]
0x140003dc0  mov     rcx, [rsi+18h]; hWnd
0x140003dc4  lea     rdx, [rsp+448h+Buffer]; pwszReason
0x140003dc9  call    cs:__imp_ShutdownBlockReasonCreate
0x140003dcf  test    eax, eax
0x140003dd1  jnz     short loc_140003DE7
0x140003dd3  call    cs:__imp_GetLastError
0x140003dd9  test    eax, eax
0x140003ddb  jle     short loc_140003DE9
0x140003ddd  movzx   eax, ax
0x140003de0  or      eax, 80070000h
0x140003de5  jmp     short loc_140003DE9
0x140003de7  mov     eax, ebx
0x140003de9  mov     rbx, [rsp+448h+arg_10]
0x140003df1  mov     rcx, [rsp+448h+var_28]
0x140003df9  xor     rcx, rsp; StackCookie
0x140003dfc  call    __security_check_cookie
0x140003e01  add     rsp, 430h
0x140003e08  pop     rdi
0x140003e09  pop     rsi
0x140003e0a  pop     rbp
0x140003e0b  retn
```
