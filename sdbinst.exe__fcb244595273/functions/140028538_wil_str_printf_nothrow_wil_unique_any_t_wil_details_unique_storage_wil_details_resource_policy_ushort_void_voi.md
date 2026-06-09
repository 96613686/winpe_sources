# wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)

- ea: `0x140028538`
- end: `0x1400286c7`
- name: `??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ`
- size: `399`
- prototype: `__int64(char *, const wchar_t *, ...)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140029c80`
- `0x14002be40`

## callees

- `0x140006844`
- `0x14002474c`
- `0x140028538`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140028613`
- `KERNEL32!GetLastError` at `0x140028613`
- `KERNEL32!GetProcessHeap` at `0x14002861b`
- `KERNEL32!GetProcessHeap` at `0x140028641`
- `KERNEL32!GetProcessHeap` at `0x1400286a2`
- `KERNEL32!GetProcessHeap` at `0x14002861b`
- `KERNEL32!GetProcessHeap` at `0x140028641`
- `KERNEL32!GetProcessHeap` at `0x1400286a2`
- `KERNEL32!SetLastError` at `0x140028631`
- `KERNEL32!SetLastError` at `0x140028631`
- `KERNEL32!HeapFree` at `0x140028629`
- `KERNEL32!HeapFree` at `0x14002864f`
- `KERNEL32!HeapFree` at `0x1400286b0`
- `KERNEL32!HeapFree` at `0x140028629`
- `KERNEL32!HeapFree` at `0x14002864f`
- `KERNEL32!HeapFree` at `0x1400286b0`
- `msvcrt!_vscwprintf` at `0x14002856d`
- `msvcrt!_vscwprintf` at `0x14002856d`
- `msvcrt!_vsnwprintf` at `0x1400285e8`
- `msvcrt!_vsnwprintf` at `0x1400285e8`

## string_xrefs

- `0x140028599`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140028689`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        char *a1,
        const wchar_t *a2,
        ...)
{
  size_t v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  wchar_t *v7; // rdi
  unsigned __int64 v8; // rbp
  int v9; // eax
  void *v10; // rsi
  DWORD LastError; // ebx
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *Buffer; // [rsp+20h] [rbp-48h] BYREF
  char v17; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  va_list va; // [rsp+80h] [rbp+18h] BYREF

  va_start(va, a2);
  Buffer = 0;
  v4 = _vscwprintf(a2, va);
  v5 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &Buffer,
         0,
         v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v5,
      (int)Buffer);
    v7 = Buffer;
    goto LABEL_22;
  }
  v7 = Buffer;
  v8 = v4 + 1;
  if ( v4 == -1 )
  {
    v6 = -2147024809;
    goto LABEL_21;
  }
  if ( v8 > 0x7FFFFFFF )
  {
    v6 = -2147024809;
LABEL_20:
    *v7 = 0;
    goto LABEL_21;
  }
  v9 = _vsnwprintf(Buffer, v4, a2, va);
  if ( v9 < 0 || v9 > v4 )
  {
    v6 = -2147024774;
    v7[v4] = 0;
    if ( (v8 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_20;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v6,
      (int)Buffer);
LABEL_22:
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    return v6;
  }
  if ( v9 == v4 )
    v7[v4] = 0;
  if ( a1 == &v17 )
  {
    if ( v7 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v7);
    }
  }
  else
  {
    v10 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v10);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x140028538  mov     rax, rsp
0x14002853b  mov     [rax+10h], rdx
0x14002853f  mov     [rax+18h], r8
0x140028543  mov     [rax+20h], r9
0x140028547  push    rbx
0x140028548  push    rbp
0x140028549  push    rsi
0x14002854a  push    rdi
0x14002854b  push    r12
0x14002854d  push    r14
0x14002854f  push    r15
0x140028551  sub     rsp, 30h
0x140028555  mov     r15, rdx
0x140028558  mov     qword ptr [rax-48h], 0
0x140028560  lea     r12, [rax+18h]
0x140028564  mov     r14, rcx
0x140028567  mov     rdx, r12; ArgList
0x14002856a  mov     rcx, r15; Format
0x14002856d  call    cs:__imp__vscwprintf
0x140028573  xor     edx, edx
0x140028575  mov     [rsp+68h+Buffer], 0; int
0x14002857e  movsxd  rsi, eax
0x140028581  lea     rcx, [rsp+68h+Buffer]
0x140028586  mov     r8, rsi
0x140028589  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x14002858e  mov     ebx, eax
0x140028590  test    eax, eax
0x140028592  jns     short loc_1400285B7
0x140028594  mov     rcx, [rsp+68h]; this
0x140028599  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400285a0  mov     r9d, eax; char *
0x1400285a3  mov     edx, 7CDh; void *
0x1400285a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400285ad  mov     rdi, [rsp+68h+Buffer]
0x1400285b2  jmp     loc_14002869D
0x1400285b7  mov     rdi, [rsp+68h+Buffer]
0x1400285bc  lea     rbp, [rsi+1]
0x1400285c0  test    rbp, rbp
0x1400285c3  jz      loc_140028675
0x1400285c9  cmp     rbp, 7FFFFFFFh
0x1400285d0  jbe     short loc_1400285DC
0x1400285d2  mov     ebx, 80070057h
0x1400285d7  jmp     loc_14002867F
0x1400285dc  mov     r9, r12; Args
0x1400285df  mov     r8, r15; Format
0x1400285e2  mov     rdx, rsi; BufferCount
0x1400285e5  mov     rcx, rdi; Buffer
0x1400285e8  call    cs:__imp__vsnwprintf
0x1400285ee  test    eax, eax
0x1400285f0  js      short loc_140028659
0x1400285f2  cdqe
0x1400285f4  cmp     rax, rsi
0x1400285f7  ja      short loc_140028659
0x1400285f9  jnz     short loc_140028601
0x1400285fb  xor     eax, eax
0x1400285fd  mov     [rdi+rsi*2], ax
0x140028601  lea     rax, [rsp+68h+var_40]
0x140028606  cmp     r14, rax
0x140028609  jz      short loc_14002863C
0x14002860b  mov     rsi, [r14]
0x14002860e  test    rsi, rsi
0x140028611  jz      short loc_140028637
0x140028613  call    cs:__imp_GetLastError
0x140028619  mov     ebx, eax
0x14002861b  call    cs:__imp_GetProcessHeap
0x140028621  mov     r8, rsi; lpMem
0x140028624  xor     edx, edx; dwFlags
0x140028626  mov     rcx, rax; hHeap
0x140028629  call    cs:__imp_HeapFree
0x14002862f  mov     ecx, ebx; dwErrCode
0x140028631  call    cs:__imp_SetLastError
0x140028637  mov     [r14], rdi
0x14002863a  jmp     short loc_140028655
0x14002863c  test    rdi, rdi
0x14002863f  jz      short loc_140028655
0x140028641  call    cs:__imp_GetProcessHeap
0x140028647  mov     r8, rdi; lpMem
0x14002864a  xor     edx, edx; dwFlags
0x14002864c  mov     rcx, rax; hHeap
0x14002864f  call    cs:__imp_HeapFree
0x140028655  xor     ebx, ebx
0x140028657  jmp     short loc_1400286B6
0x140028659  xor     eax, eax
0x14002865b  mov     ebx, 8007007Ah
0x140028660  mov     [rdi+rsi*2], ax
0x140028664  mov     rax, 7FFFFFFFFFFFFFFFh
0x14002866e  test    rax, rbp
0x140028671  jbe     short loc_140028684
0x140028673  jmp     short loc_14002867F
0x140028675  mov     ebx, 80070057h
0x14002867a  test    rbp, rbp
0x14002867d  jz      short loc_140028684
0x14002867f  xor     eax, eax
0x140028681  mov     [rdi], ax
0x140028684  mov     rcx, [rsp+68h]; this
0x140028689  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140028690  mov     r9d, ebx; char *
0x140028693  mov     edx, 7D1h; void *
0x140028698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002869d  test    rdi, rdi
0x1400286a0  jz      short loc_1400286B6
0x1400286a2  call    cs:__imp_GetProcessHeap
0x1400286a8  mov     r8, rdi; lpMem
0x1400286ab  xor     edx, edx; dwFlags
0x1400286ad  mov     rcx, rax; hHeap
0x1400286b0  call    cs:__imp_HeapFree
0x1400286b6  mov     eax, ebx
0x1400286b8  add     rsp, 30h
0x1400286bc  pop     r15
0x1400286be  pop     r14
0x1400286c0  pop     r12
0x1400286c2  pop     rdi
0x1400286c3  pop     rsi
0x1400286c4  pop     rbp
0x1400286c5  pop     rbx
0x1400286c6  retn
```
