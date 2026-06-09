# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x1800655e0`
- end: `0x18006578f`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `431`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006585c`

## callees

- `0x18000de14`
- `0x180054760`
- `0x180055880`
- `0x1800655e0`
- `0x180065b47`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800656e9`
- `KERNEL32!GetLastError` at `0x1800656e9`
- `KERNEL32!GetCurrentThreadId` at `0x180065635`
- `KERNEL32!GetCurrentThreadId` at `0x180065635`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800656bc`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x18006573d`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800656bc`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x18006573d`

## pseudocode

```c
void __fastcall FormatMsgToBuffer(
        char **this,
        struct _DEBUG_PRINTS *a2,
        const char *a3,
        int a4,
        const char *a5,
        char *Format,
        char **a7)
{
  char *v11; // rax
  int v12; // ebp
  const char *v13; // rdi
  const char *v14; // rbx
  DWORD CurrentThreadId; // eax
  int v16; // eax
  __int64 v18; // r15
  va_list ArgList; // rsi
  unsigned int v20; // ebx
  char *v21; // rdi
  int v22; // eax
  signed int LastError; // eax
  signed int v24; // ecx
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 *v27; // [rsp+A0h] [rbp+38h]

  v11 = strrchr_0(a3, 92);
  v12 = 0;
  if ( v11 )
    v13 = v11 + 1;
  else
    v13 = a3;
  v14 = "??";
  if ( a2 )
    v14 = (const char *)a2;
  CurrentThreadId = GetCurrentThreadId();
  v16 = sprintf_s(this[4], *((unsigned int *)this + 10), "%lu %hs!%hs [%hs @ %d]:", CurrentThreadId, v14, a5, v13, a4);
  v18 = v16;
  ArgList = *a7;
  v20 = *((_DWORD *)this + 10) - v16;
  v21 = &this[4][v16];
  v27 = _local_stdio_printf_options();
  v22 = __stdio_common_vsnprintf_s(*v27, v21, v20, v20 - 1, Format, 0, ArgList);
  if ( v22 < 0 )
    v22 = -1;
  if ( v22 == -1 )
  {
    if ( *((_DWORD *)this + 10) < 0x2800u && !BUFFER::ReallocStorage((BUFFER *)this, 0x2800u) )
    {
      LastError = GetLastError();
      v24 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v24 = LastError;
      if ( v24 < 0 )
      {
        *this[4] = 0;
        goto LABEL_22;
      }
    }
    v25 = __stdio_common_vsnprintf_s(
            *v27,
            &this[4][v18],
            (unsigned int)(*((_DWORD *)this + 10) - v18),
            (unsigned int)(*((_DWORD *)this + 10) - v18 - 1),
            Format,
            0,
            *a7);
    if ( v25 < 0 )
      v25 = -1;
    if ( v25 == -1 )
      this[4][*((_DWORD *)this + 10) - 1] = 0;
  }
  v26 = -1;
  do
    ++v26;
  while ( this[4][v26] );
  v12 = v26;
LABEL_22:
  *((_DWORD *)this + 12) = v12;
}

```

## disassembly

```asm
0x1800655e0  mov     [rsp+arg_0], rbx
0x1800655e5  mov     [rsp+arg_8], rbp
0x1800655ea  mov     [rsp+arg_10], rsi
0x1800655ef  push    rdi
0x1800655f0  push    r12
0x1800655f2  push    r13
0x1800655f4  push    r14
0x1800655f6  push    r15
0x1800655f8  sub     rsp, 40h
0x1800655fc  mov     rsi, rdx
0x1800655ff  mov     r14, rcx
0x180065602  mov     edx, 5Ch ; '\'; Ch
0x180065607  mov     rcx, r8; Str
0x18006560a  mov     r15d, r9d
0x18006560d  mov     rbx, r8
0x180065610  call    strrchr_0
0x180065615  xor     ebp, ebp
0x180065617  mov     rdi, rax
0x18006561a  test    rax, rax
0x18006561d  jnz     short loc_180065624
0x18006561f  mov     rdi, rbx
0x180065622  jmp     short loc_180065627
0x180065624  inc     rdi
0x180065627  test    rsi, rsi
0x18006562a  lea     rbx, asc_18007C01C; "??"
0x180065631  cmovnz  rbx, rsi
0x180065635  call    cs:__imp_GetCurrentThreadId
0x18006563b  mov     edx, [r14+28h]; BufferCount
0x18006563f  lea     r8, aLuHsHsHsD; "%lu %hs!%hs [%hs @ %d]:"
0x180065646  mov     rcx, [r14+20h]; Buffer
0x18006564a  mov     r9d, eax
0x18006564d  mov     rax, [rsp+68h+arg_20]
0x180065655  mov     [rsp+68h+var_30], r15d
0x18006565a  mov     [rsp+68h+ArgList], rdi
0x18006565f  mov     [rsp+68h+Locale], rax
0x180065664  mov     [rsp+68h+Format], rbx
0x180065669  call    sprintf_s
0x18006566e  mov     r12, [rsp+68h+arg_30]
0x180065676  mov     ebx, [r14+28h]
0x18006567a  mov     rdi, [r14+20h]
0x18006567e  movsxd  r15, eax
0x180065681  mov     rsi, [r12]
0x180065685  sub     ebx, r15d
0x180065688  add     rdi, r15
0x18006568b  call    __local_stdio_printf_options
0x180065690  lea     r9d, [rbx-1]; MaxCount
0x180065694  mov     [rsp+68h+ArgList], rsi; ArgList
0x180065699  mov     r8d, ebx; BufferCount
0x18006569c  mov     [rsp+68h+Locale], rbp; Locale
0x1800656a1  mov     rbx, [rsp+68h+arg_28]
0x1800656a9  mov     rdx, rdi; Buffer
0x1800656ac  mov     rcx, [rax]; Options
0x1800656af  mov     [rsp+68h+arg_30], rax
0x1800656b7  mov     [rsp+68h+Format], rbx; Format
0x1800656bc  call    cs:__imp___stdio_common_vsnprintf_s
0x1800656c2  or      edi, 0FFFFFFFFh
0x1800656c5  test    eax, eax
0x1800656c7  cmovs   eax, edi
0x1800656ca  cmp     eax, edi
0x1800656cc  jnz     loc_18006575A
0x1800656d2  mov     edx, 2800h; unsigned int
0x1800656d7  cmp     [r14+28h], edx
0x1800656db  jnb     short loc_18006570A
0x1800656dd  mov     rcx, r14; this
0x1800656e0  call    ?ReallocStorage@BUFFER@@AEAAHI@Z; BUFFER::ReallocStorage(uint)
0x1800656e5  test    eax, eax
0x1800656e7  jnz     short loc_18006570A
0x1800656e9  call    cs:__imp_GetLastError
0x1800656ef  movzx   ecx, ax
0x1800656f2  or      ecx, 80070000h
0x1800656f8  test    eax, eax
0x1800656fa  cmovle  ecx, eax
0x1800656fd  test    ecx, ecx
0x1800656ff  jns     short loc_18006570A
0x180065701  mov     rax, [r14+20h]
0x180065705  mov     [rax], bpl
0x180065708  jmp     short loc_18006576D
0x18006570a  mov     rcx, [r12]
0x18006570e  mov     eax, [r14+28h]
0x180065712  mov     rdx, [r14+20h]
0x180065716  sub     eax, r15d
0x180065719  mov     [rsp+68h+ArgList], rcx; ArgList
0x18006571e  add     rdx, r15; Buffer
0x180065721  mov     rcx, [rsp+68h+arg_30]
0x180065729  mov     r8d, eax; BufferCount
0x18006572c  lea     r9d, [rax-1]; MaxCount
0x180065730  mov     [rsp+68h+Locale], rbp; Locale
0x180065735  mov     [rsp+68h+Format], rbx; Format
0x18006573a  mov     rcx, [rcx]; Options
0x18006573d  call    cs:__imp___stdio_common_vsnprintf_s
0x180065743  test    eax, eax
0x180065745  cmovs   eax, edi
0x180065748  cmp     eax, edi
0x18006574a  jnz     short loc_18006575A
0x18006574c  mov     ecx, [r14+28h]
0x180065750  mov     rax, [r14+20h]
0x180065754  dec     ecx
0x180065756  mov     [rcx+rax], bpl
0x18006575a  mov     rcx, [r14+20h]
0x18006575e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065762  inc     rax
0x180065765  cmp     [rcx+rax], bpl
0x180065769  jnz     short loc_180065762
0x18006576b  mov     ebp, eax
0x18006576d  lea     r11, [rsp+68h+var_28]
0x180065772  mov     [r14+30h], ebp
0x180065776  mov     rbx, [r11+30h]
0x18006577a  mov     rbp, [r11+38h]
0x18006577e  mov     rsi, [r11+40h]
0x180065782  mov     rsp, r11
0x180065785  pop     r15
0x180065787  pop     r14
0x180065789  pop     r13
0x18006578b  pop     r12
0x18006578d  pop     rdi
0x18006578e  retn
```
