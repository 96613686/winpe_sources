# HTTP_LOG_CONTEXT::CopyAppContext(ulong,char const *)

- ea: `0x180009f6c`
- end: `0x18000a11b`
- name: `?CopyAppContext@HTTP_LOG_CONTEXT@@QEAAJKPEBD@Z`
- size: `431`
- prototype: `__int64 __fastcall(HTTP_LOG_CONTEXT *this, int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a36c`

## callees

- `0x180009f6c`
- `0x18000e96e`
- `0x18000e9a0`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18000a004`
- `msvcrt!strncpy_s` at `0x18000a0ad`
- `msvcrt!strncpy_s` at `0x18000a004`
- `msvcrt!strncpy_s` at `0x18000a0ad`
- `msvcrt!strtoul` at `0x18000a024`
- `msvcrt!strtoul` at `0x18000a0c7`
- `msvcrt!strtoul` at `0x18000a024`
- `msvcrt!strtoul` at `0x18000a0c7`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_CONTEXT::CopyAppContext(HTTP_LOG_CONTEXT *this, int a2, const char *a3)
{
  const char *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  size_t v9; // rbp
  const char *v10; // rax
  __int64 v11; // rcx
  size_t v12; // rbp
  char Destination[8]; // [rsp+20h] [rbp-38h] BYREF
  char v15; // [rsp+28h] [rbp-30h]

  *(_QWORD *)Destination = 0;
  v15 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( *a3 == 49 )
  {
    v6 = a3;
    v7 = 98;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v7;
    }
    while ( v7 );
    v8 = v7 == 0 ? 0x80070057 : 0;
    v9 = (98 - v7) & -(__int64)(v7 != 0);
    if ( v7 )
    {
      if ( strncpy_s(Destination, 9u, a3 + 57, 8u) != 22 && a2 == strtoul(Destination, 0, 16) )
      {
        *((_DWORD *)this + 298) = a3[1] == 49;
        memcpy_0((char *)this + 824, a3, v9);
        return v8;
      }
      return (unsigned int)-2147024883;
    }
    return v8;
  }
  if ( *a3 != 50 )
    return (unsigned int)-2147024809;
  v10 = a3;
  v11 = 256;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v8 = v11 == 0 ? 0x80070057 : 0;
  v12 = (256 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    if ( strncpy_s(Destination, 9u, a3 + 2, 8u) != 22 && a2 == strtoul(Destination, 0, 16) )
    {
      memcpy_0((char *)this + 922, a3, v12);
      *((_DWORD *)this + 295) = 1;
      return v8;
    }
    return (unsigned int)-2147024883;
  }
  return v8;
}

```

## disassembly

```asm
0x180009f6c  mov     [rsp+arg_8], rbx
0x180009f71  mov     [rsp+arg_18], rbp
0x180009f76  push    rsi
0x180009f77  push    rdi
0x180009f78  push    r14
0x180009f7a  sub     rsp, 40h
0x180009f7e  mov     rax, cs:__security_cookie
0x180009f85  xor     rax, rsp
0x180009f88  mov     [rsp+58h+var_28], rax
0x180009f8d  xor     eax, eax
0x180009f8f  mov     rdi, r8
0x180009f92  mov     qword ptr [rsp+58h+Destination], rax
0x180009f97  mov     r14d, edx
0x180009f9a  mov     [rsp+58h+var_30], al
0x180009f9e  mov     rsi, rcx
0x180009fa1  test    r8, r8
0x180009fa4  jz      loc_18000A0F4
0x180009faa  cmp     byte ptr [r8], 31h ; '1'
0x180009fae  jnz     loc_18000A055
0x180009fb4  lea     edx, [rax+62h]
0x180009fb7  mov     rax, r8
0x180009fba  mov     ecx, edx
0x180009fbc  cmp     byte ptr [rax], 0
0x180009fbf  jz      short loc_180009FCA
0x180009fc1  inc     rax
0x180009fc4  sub     rcx, 1
0x180009fc8  jnz     short loc_180009FBC
0x180009fca  mov     rax, rcx
0x180009fcd  neg     rax
0x180009fd0  mov     rax, rcx
0x180009fd3  sbb     ebx, ebx
0x180009fd5  sub     rdx, rcx
0x180009fd8  not     ebx
0x180009fda  and     ebx, 80070057h
0x180009fe0  neg     rax
0x180009fe3  sbb     rbp, rbp
0x180009fe6  and     rbp, rdx
0x180009fe9  test    rcx, rcx
0x180009fec  jz      loc_18000A0F9
0x180009ff2  mov     edx, 9; SizeInBytes
0x180009ff7  lea     rcx, [rsp+58h+Destination]; Destination
0x180009ffc  add     r8, 39h ; '9'; Source
0x18000a000  lea     r9d, [rdx-1]; MaxCount
0x18000a004  call    cs:__imp_strncpy_s
0x18000a00a  cmp     eax, 16h
0x18000a00d  jnz     short loc_18000A019
0x18000a00f  mov     ebx, 8007000Dh
0x18000a014  jmp     loc_18000A0F9
0x18000a019  xor     edx, edx; EndPtr
0x18000a01b  lea     rcx, [rsp+58h+Destination]; String
0x18000a020  lea     r8d, [rdx+10h]; Radix
0x18000a024  call    cs:__imp_strtoul
0x18000a02a  cmp     r14d, eax
0x18000a02d  jnz     short loc_18000A00F
0x18000a02f  xor     eax, eax
0x18000a031  lea     rcx, [rsi+338h]; void *
0x18000a038  cmp     byte ptr [rdi+1], 31h ; '1'
0x18000a03c  mov     r8, rbp; Size
0x18000a03f  mov     rdx, rdi; Src
0x18000a042  setz    al
0x18000a045  mov     [rsi+4A8h], eax
0x18000a04b  call    memcpy_0
0x18000a050  jmp     loc_18000A0F9
0x18000a055  cmp     byte ptr [r8], 32h ; '2'
0x18000a059  jnz     loc_18000A0F4
0x18000a05f  mov     edx, 100h
0x18000a064  mov     rax, rdi
0x18000a067  mov     ecx, edx
0x18000a069  cmp     byte ptr [rax], 0
0x18000a06c  jz      short loc_18000A077
0x18000a06e  inc     rax
0x18000a071  sub     rcx, 1
0x18000a075  jnz     short loc_18000A069
0x18000a077  mov     rax, rcx
0x18000a07a  neg     rax
0x18000a07d  mov     rax, rcx
0x18000a080  sbb     ebx, ebx
0x18000a082  sub     rdx, rcx
0x18000a085  not     ebx
0x18000a087  and     ebx, 80070057h
0x18000a08d  neg     rax
0x18000a090  sbb     rbp, rbp
0x18000a093  and     rbp, rdx
0x18000a096  test    rcx, rcx
0x18000a099  jz      short loc_18000A0F9
0x18000a09b  mov     edx, 9; SizeInBytes
0x18000a0a0  lea     rcx, [rsp+58h+Destination]; Destination
0x18000a0a5  add     r8, 2; Source
0x18000a0a9  lea     r9d, [rdx-1]; MaxCount
0x18000a0ad  call    cs:__imp_strncpy_s
0x18000a0b3  cmp     eax, 16h
0x18000a0b6  jz      loc_18000A00F
0x18000a0bc  xor     edx, edx; EndPtr
0x18000a0be  lea     rcx, [rsp+58h+Destination]; String
0x18000a0c3  lea     r8d, [rdx+10h]; Radix
0x18000a0c7  call    cs:__imp_strtoul
0x18000a0cd  cmp     r14d, eax
0x18000a0d0  jnz     loc_18000A00F
0x18000a0d6  lea     rcx, [rsi+39Ah]; void *
0x18000a0dd  mov     r8, rbp; Size
0x18000a0e0  mov     rdx, rdi; Src
0x18000a0e3  call    memcpy_0
0x18000a0e8  mov     dword ptr [rsi+49Ch], 1
0x18000a0f2  jmp     short loc_18000A0F9
0x18000a0f4  mov     ebx, 80070057h
0x18000a0f9  mov     eax, ebx
0x18000a0fb  mov     rcx, [rsp+58h+var_28]
0x18000a100  xor     rcx, rsp; StackCookie
0x18000a103  call    __security_check_cookie
0x18000a108  mov     rbx, [rsp+58h+arg_8]
0x18000a10d  mov     rbp, [rsp+58h+arg_18]
0x18000a112  add     rsp, 40h
0x18000a116  pop     r14
0x18000a118  pop     rdi
0x18000a119  pop     rsi
0x18000a11a  retn
```
