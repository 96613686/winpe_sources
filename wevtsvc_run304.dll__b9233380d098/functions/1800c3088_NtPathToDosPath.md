# NtPathToDosPath

- ea: `0x1800c3088`
- end: `0x1800c3262`
- name: `NtPathToDosPath`
- size: `474`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800c3500`
- `0x1800c3aa0`
- `0x1800c4170`

## callees

- `0x18002d204`
- `0x18002de9c`
- `0x18009aee0`
- `0x1800c3088`
- `0x1800d337c`

## import_xrefs

- `ntdll!RtlNtPathNameToDosPathName` at `0x1800c31d1`
- `ntdll!RtlNtPathNameToDosPathName` at `0x1800c31d1`
- `ntdll!RtlFreeUnicodeString` at `0x1800c3224`
- `ntdll!RtlFreeUnicodeString` at `0x1800c3224`
- `ntdll!RtlpEnsureBufferSize` at `0x1800c3170`
- `ntdll!RtlpEnsureBufferSize` at `0x1800c3170`

## pseudocode

```c
NTSTATUS __fastcall NtPathToDosPath(__int64 a1, __int64 a2)
{
  UCHAR *v3; // rcx
  __int64 v5; // rdx
  NTSTATUS result; // eax
  UCHAR *p_ReservedForAllocatedSize; // rcx
  __int64 v8; // rdx
  SIZE_T Size; // r9
  unsigned __int16 v10; // ax
  size_t v11; // rbx
  USHORT Length; // ax
  SIZE_T v13; // r8
  const void *v15; // rdx
  int v16; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-50h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+30h] [rbp-40h] BYREF

  v3 = *(UCHAR **)a2;
  *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
  memset(&Path, 0, 56);
  v5 = *(_QWORD *)(a1 + 8);
  *(_WORD *)v3 = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(a2, v5) )
    return -1073741801;
  p_ReservedForAllocatedSize = (UCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  v8 = 2;
  if ( (unsigned __int64)(2 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) + 2) >= 2 )
    p_ReservedForAllocatedSize = *(UCHAR **)a2;
  if ( (unsigned __int64)(2 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1)) < 0xFFFFFFFFFFFFFFFEuLL )
    v8 = 2 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 1) + 2;
  Path.ByteBuffer.Buffer = p_ReservedForAllocatedSize;
  Size = v8;
  Path.ByteBuffer.Size = v8;
  Path.ByteBuffer.StaticBuffer = p_ReservedForAllocatedSize;
  Path.ByteBuffer.StaticSize = v8;
  Path.String.Buffer = (PWSTR)p_ReservedForAllocatedSize;
  if ( p_ReservedForAllocatedSize )
  {
    *(_WORD *)p_ReservedForAllocatedSize = 0;
    Size = Path.ByteBuffer.Size;
    p_ReservedForAllocatedSize = Path.ByteBuffer.Buffer;
  }
  v10 = 2 * *(_WORD *)(a1 + 8);
  Path.String.MaximumLength = v8;
  v11 = v10;
  Length = 0;
  Path.String.Length = 0;
  v13 = v11 + 2;
  if ( v11 + 2 > 0xFFFE )
    return -1073741562;
  if ( v13 > Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v13) < 0 )
      return -1073741801;
    p_ReservedForAllocatedSize = Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  v15 = *(const void **)a1;
  Path.String.Buffer = (PWSTR)p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[2 * ((unsigned __int64)Length >> 1)], v15, v11);
  Path.String.Length += v11;
  Path.String.MaximumLength = Path.String.Length + 2;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  result = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
  v16 = result;
  if ( result >= 0 )
  {
    if ( Path.ByteBuffer.Buffer == Path.ByteBuffer.StaticBuffer )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
        a2,
        (unsigned __int64)Path.String.Length >> 1);
      return 0;
    }
    else
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a2,
                               Path.String.Buffer) )
        v16 = -1073741801;
      if ( Path.ByteBuffer.Buffer && Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
      {
        *(_QWORD *)&UnicodeString.Length = 0;
        UnicodeString.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
        RtlFreeUnicodeString(&UnicodeString);
      }
      result = 0;
      if ( v16 < 0 )
        return v16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c3088  mov     [rsp-18h+arg_10], rbx
0x1800c308d  mov     [rsp-18h+arg_18], rsi
0x1800c3092  push    rbp
0x1800c3093  push    rdi
0x1800c3094  push    r14
0x1800c3096  mov     rbp, rsp
0x1800c3099  sub     rsp, 70h
0x1800c309d  mov     rax, cs:__security_cookie
0x1800c30a4  xor     rax, rsp
0x1800c30a7  mov     [rbp+Path.ByteBuffer.ReservedForIMalloc], rax
0x1800c30ab  mov     rsi, rcx
0x1800c30ae  xorps   xmm0, xmm0
0x1800c30b1  mov     rcx, [rdx]
0x1800c30b4  xor     eax, eax
0x1800c30b6  mov     [rdx+8], rcx
0x1800c30ba  mov     rdi, rdx
0x1800c30bd  movups  xmmword ptr [rbp+Path.String.Length], xmm0
0x1800c30c1  mov     rdx, [rsi+8]
0x1800c30c5  movups  xmmword ptr [rbp+Path.ByteBuffer.Buffer], xmm0
0x1800c30c9  mov     [rbp+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x1800c30cd  movups  xmmword ptr [rbp+Path.ByteBuffer.Size], xmm0
0x1800c30d1  mov     [rcx], ax
0x1800c30d4  mov     rcx, rdi
0x1800c30d7  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800c30dc  test    al, al
0x1800c30de  jnz     short loc_1800C30EA
0x1800c30e0  mov     eax, 0C0000017h
0x1800c30e5  jmp     loc_1800C3241
0x1800c30ea  mov     rax, [rdi+8]
0x1800c30ee  lea     rcx, [rbp+Path.ByteBuffer.ReservedForAllocatedSize]
0x1800c30f2  sub     rax, [rdi]
0x1800c30f5  mov     r14d, 2
0x1800c30fb  sar     rax, 1
0x1800c30fe  mov     edx, r14d
0x1800c3101  lea     rax, ds:2[rax*2]
0x1800c3109  cmp     rax, r14
0x1800c310c  cmovnb  rcx, [rdi]
0x1800c3110  cmovnb  rdx, rax
0x1800c3114  mov     [rbp+Path.ByteBuffer.Buffer], rcx
0x1800c3118  mov     r9, rdx
0x1800c311b  mov     [rbp+Path.ByteBuffer.Size], rdx
0x1800c311f  mov     [rbp+Path.ByteBuffer.StaticBuffer], rcx
0x1800c3123  mov     [rbp+Path.ByteBuffer.StaticSize], rdx
0x1800c3127  mov     [rbp+Path.String.Buffer], rcx
0x1800c312b  test    rcx, rcx
0x1800c312e  jz      short loc_1800C313D
0x1800c3130  xor     eax, eax
0x1800c3132  mov     [rcx], ax
0x1800c3135  mov     r9, [rbp+Path.ByteBuffer.Size]
0x1800c3139  mov     rcx, [rbp+Path.ByteBuffer.Buffer]
0x1800c313d  movzx   eax, word ptr [rsi+8]
0x1800c3141  add     ax, ax
0x1800c3144  mov     [rbp+Path.String.MaximumLength], dx
0x1800c3148  movzx   ebx, ax
0x1800c314b  xor     eax, eax
0x1800c314d  mov     [rbp+Path.String.Length], ax
0x1800c3151  lea     r8, [rbx+2]; RequiredSize
0x1800c3155  cmp     r8, 0FFFEh
0x1800c315c  jbe     short loc_1800C3165
0x1800c315e  mov     ecx, 0C0000106h
0x1800c3163  jmp     short loc_1800C317F
0x1800c3165  cmp     r8, r9
0x1800c3168  jbe     short loc_1800C318E
0x1800c316a  lea     rdx, [rbp+Path.ByteBuffer]; Buffer
0x1800c316e  xor     ecx, ecx; Flags
0x1800c3170  call    cs:__imp_RtlpEnsureBufferSize
0x1800c3176  test    eax, eax
0x1800c3178  jns     short loc_1800C3186
0x1800c317a  mov     ecx, 0C0000017h
0x1800c317f  mov     eax, ecx
0x1800c3181  jmp     loc_1800C3241
0x1800c3186  mov     rcx, [rbp+Path.ByteBuffer.Buffer]
0x1800c318a  movzx   eax, [rbp+Path.String.Length]
0x1800c318e  mov     rdx, [rsi]; Src
0x1800c3191  mov     r8, rbx; Size
0x1800c3194  movzx   eax, ax
0x1800c3197  shr     rax, 1
0x1800c319a  mov     [rbp+Path.String.Buffer], rcx
0x1800c319e  lea     rcx, [rcx+rax*2]; void *
0x1800c31a2  call    memmove_0
0x1800c31a7  add     bx, [rbp+Path.String.Length]
0x1800c31ab  xor     ecx, ecx; Flags
0x1800c31ad  movzx   edx, bx
0x1800c31b0  xor     r9d, r9d; Unknown
0x1800c31b3  mov     [rbp+Path.String.Length], dx
0x1800c31b7  xor     r8d, r8d; PathType
0x1800c31ba  lea     eax, [r14+rdx]
0x1800c31be  shr     rdx, 1
0x1800c31c1  mov     [rbp+Path.String.MaximumLength], ax
0x1800c31c5  mov     rax, [rbp+Path.String.Buffer]
0x1800c31c9  mov     [rax+rdx*2], cx
0x1800c31cd  lea     rdx, [rbp+Path]; Path
0x1800c31d1  call    cs:__imp_RtlNtPathNameToDosPathName
0x1800c31d7  mov     ebx, eax
0x1800c31d9  test    eax, eax
0x1800c31db  js      short loc_1800C3241
0x1800c31dd  mov     rax, [rbp+Path.ByteBuffer.StaticBuffer]
0x1800c31e1  mov     rcx, rdi
0x1800c31e4  cmp     [rbp+Path.ByteBuffer.Buffer], rax
0x1800c31e8  jz      short loc_1800C3233
0x1800c31ea  movzx   r8d, [rbp+Path.String.Length]
0x1800c31ef  mov     rdx, [rbp+Path.String.Buffer]
0x1800c31f3  shr     r8, 1
0x1800c31f6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800c31fb  test    al, al
0x1800c31fd  mov     ecx, 0C0000017h
0x1800c3202  mov     rax, [rbp+Path.ByteBuffer.Buffer]
0x1800c3206  cmovz   ebx, ecx
0x1800c3209  test    rax, rax
0x1800c320c  jz      short loc_1800C322A
0x1800c320e  cmp     rax, [rbp+Path.ByteBuffer.StaticBuffer]
0x1800c3212  jz      short loc_1800C322A
0x1800c3214  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800c3218  mov     qword ptr [rbp+UnicodeString.Length], 0
0x1800c3220  mov     [rbp+UnicodeString.Buffer], rax
0x1800c3224  call    cs:__imp_RtlFreeUnicodeString
0x1800c322a  xor     eax, eax
0x1800c322c  test    ebx, ebx
0x1800c322e  cmovs   eax, ebx
0x1800c3231  jmp     short loc_1800C3241
0x1800c3233  movzx   edx, [rbp+Path.String.Length]
0x1800c3237  shr     rdx, 1
0x1800c323a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800c323f  xor     eax, eax
0x1800c3241  mov     rcx, [rbp+Path.ByteBuffer.ReservedForIMalloc]
0x1800c3245  xor     rcx, rsp; StackCookie
0x1800c3248  call    __security_check_cookie
0x1800c324d  lea     r11, [rsp+70h+Path.MinimumStaticBufferForTerminalNul]
0x1800c3252  mov     rbx, [r11+30h]
0x1800c3256  mov     rsi, [r11+38h]
0x1800c325a  mov     rsp, r11
0x1800c325d  pop     r14
0x1800c325f  pop     rdi
0x1800c3260  pop     rbp
0x1800c3261  retn
```
