# ConvertNtPathToDosPath<ushort>(ushort const *,ushort,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180059e7c`
- end: `0x180059fe0`
- name: `??$ConvertNtPathToDosPath@G@@YAJPEBGGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(const void *, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x18005c004`

## callees

- `0x180036f50`
- `0x180039109`
- `0x180048b18`
- `0x180048dac`
- `0x180059e7c`
- `0x18005b910`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180059f13`
- `ntdll!RtlpEnsureBufferSize` at `0x180059f13`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180059f7b`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180059f7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertNtPathToDosPath<unsigned short>(const void *a1, unsigned __int16 a2, __int64 a3)
{
  size_t v4; // rbx
  WCHAR *p_ReservedForAllocatedSize; // r9
  USHORT Length; // cx
  unsigned __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  _RTL_UNICODE_STRING_BUFFER *p_Path; // [rsp+20h] [rbp-50h] BYREF
  char v15; // [rsp+28h] [rbp-48h]
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+30h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v4 = a2;
  *(_QWORD *)&Path.String.Length = 0x20000;
  Path.ByteBuffer.ReservedForAllocatedSize = 0;
  p_ReservedForAllocatedSize = (WCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.Size = 2;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.ByteBuffer.ReservedForAllocatedSize;
  Path.ByteBuffer.StaticSize = 2;
  Path.String.Buffer = (PWSTR)&Path.ByteBuffer.ReservedForAllocatedSize;
  p_Path = &Path;
  v15 = 1;
  Length = 0;
  v8 = a2 + 2LL;
  if ( v8 > 0xFFFE )
  {
    v9 = 3221225734LL;
LABEL_6:
    v10 = 1225;
    goto LABEL_10;
  }
  if ( v8 > 2 )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v8) < 0 )
    {
      v9 = 3221225495LL;
      goto LABEL_6;
    }
    p_ReservedForAllocatedSize = (WCHAR *)Path.ByteBuffer.Buffer;
    Length = Path.String.Length;
  }
  Path.String.Buffer = p_ReservedForAllocatedSize;
  memmove_0(&p_ReservedForAllocatedSize[(unsigned __int64)Length >> 1], a1, v4);
  Path.String.MaximumLength = v4 + Path.String.Length + 2;
  Path.String.Length += v4;
  Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
  v11 = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
  if ( v11 >= 0 )
  {
    std::wstring::_Assign<unsigned short>(a3, Path.String.Buffer, (unsigned __int64)Path.String.Length >> 1);
    v12 = 0;
    goto LABEL_12;
  }
  v9 = (unsigned int)v11;
  v10 = 1226;
LABEL_10:
  v12 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v10, v8, (const char *)v9, (int)p_Path);
LABEL_12:
  v15 = 0;
  _lambda_1cd5c0ee81a67f2b50ad52212c6810aa_::operator()(&p_Path);
  return v12;
}

```

## disassembly

```asm
0x180059e7c  mov     [rsp-18h+arg_0], rbx
0x180059e81  mov     [rsp-18h+arg_8], rsi
0x180059e86  push    rbp
0x180059e87  push    rdi
0x180059e88  push    r15
0x180059e8a  mov     rbp, rsp
0x180059e8d  sub     rsp, 70h
0x180059e91  mov     rax, cs:__security_cookie
0x180059e98  xor     rax, rsp
0x180059e9b  mov     [rbp+Path.ByteBuffer.ReservedForIMalloc], rax
0x180059e9f  mov     rdi, r8
0x180059ea2  movzx   ebx, dx
0x180059ea5  mov     rsi, rcx
0x180059ea8  mov     qword ptr [rbp+Path.String.Length], 20000h
0x180059eb0  mov     dword ptr [rbp+Path.ByteBuffer.ReservedForAllocatedSize+2], 0
0x180059eb7  xor     eax, eax
0x180059eb9  mov     word ptr [rbp+Path.ByteBuffer.ReservedForAllocatedSize+6], ax
0x180059ebd  lea     r9, [rbp+Path.ByteBuffer.ReservedForAllocatedSize]
0x180059ec1  mov     [rbp+Path.ByteBuffer.Buffer], r9
0x180059ec5  lea     r15d, [rax+2]
0x180059ec9  mov     [rbp+Path.ByteBuffer.Size], r15
0x180059ecd  lea     rax, [rbp+Path.ByteBuffer.ReservedForAllocatedSize]
0x180059ed1  mov     [rbp+Path.ByteBuffer.StaticBuffer], rax
0x180059ed5  mov     [rbp+Path.ByteBuffer.StaticSize], r15
0x180059ed9  lea     rax, [rbp+Path.ByteBuffer.ReservedForAllocatedSize]
0x180059edd  mov     [rbp+Path.String.Buffer], rax
0x180059ee1  xor     eax, eax
0x180059ee3  mov     word ptr [rbp+Path.ByteBuffer.ReservedForAllocatedSize], ax
0x180059ee7  lea     rax, [rbp+Path]
0x180059eeb  mov     [rbp+var_50], rax
0x180059eef  mov     [rbp+var_48], 1
0x180059ef3  xor     ecx, ecx; Flags
0x180059ef5  lea     r8, [rbx+2]; RequiredSize
0x180059ef9  cmp     r8, 0FFFEh
0x180059f00  jbe     short loc_180059F0A
0x180059f02  mov     r9d, 0C0000106h
0x180059f08  jmp     short loc_180059F23
0x180059f0a  cmp     r8, r15
0x180059f0d  jbe     short loc_180059F32
0x180059f0f  lea     rdx, [rbp+Path.ByteBuffer]; Buffer
0x180059f13  call    cs:__imp_RtlpEnsureBufferSize
0x180059f19  test    eax, eax
0x180059f1b  jns     short loc_180059F2A
0x180059f1d  mov     r9d, 0C0000017h
0x180059f23  mov     edx, 4C9h
0x180059f28  jmp     short loc_180059F8D
0x180059f2a  mov     r9, [rbp+Path.ByteBuffer.Buffer]
0x180059f2e  movzx   ecx, [rbp+Path.String.Length]
0x180059f32  mov     [rbp+Path.String.Buffer], r9
0x180059f36  mov     r8, rbx; Size
0x180059f39  movzx   eax, cx
0x180059f3c  shr     rax, 1
0x180059f3f  lea     rcx, [r9+rax*2]; void *
0x180059f43  mov     rdx, rsi; Src
0x180059f46  call    memmove_0
0x180059f4b  movzx   ecx, [rbp+Path.String.Length]
0x180059f4f  lea     eax, [rbx+rcx]
0x180059f52  add     ax, r15w
0x180059f56  mov     [rbp+Path.String.MaximumLength], ax
0x180059f5a  add     cx, bx
0x180059f5d  movzx   edx, cx
0x180059f60  mov     [rbp+Path.String.Length], dx
0x180059f64  shr     rdx, 1
0x180059f67  xor     ecx, ecx; Flags
0x180059f69  mov     rax, [rbp+Path.String.Buffer]
0x180059f6d  mov     [rax+rdx*2], cx
0x180059f71  xor     r9d, r9d; Unknown
0x180059f74  xor     r8d, r8d; PathType
0x180059f77  lea     rdx, [rbp+Path]; Path
0x180059f7b  call    cs:__imp_RtlNtPathNameToDosPathName
0x180059f81  test    eax, eax
0x180059f83  jns     short loc_180059F9A
0x180059f85  mov     r9d, eax; char *
0x180059f88  mov     edx, 4CAh; void *
0x180059f8d  mov     rcx, [rbp+18h]; this
0x180059f91  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180059f96  mov     ebx, eax
0x180059f98  jmp     short loc_180059FB0
0x180059f9a  movzx   r8d, [rbp+Path.String.Length]
0x180059f9f  shr     r8, 1
0x180059fa2  mov     rdx, [rbp+Path.String.Buffer]
0x180059fa6  mov     rcx, rdi
0x180059fa9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180059fae  xor     ebx, ebx
0x180059fb0  mov     [rbp+var_48], 0
0x180059fb4  lea     rcx, [rbp+var_50]
0x180059fb8  call    ??R_lambda_1cd5c0ee81a67f2b50ad52212c6810aa_@@QEBA@XZ; _lambda_1cd5c0ee81a67f2b50ad52212c6810aa_::operator()(void)
0x180059fbd  mov     eax, ebx
0x180059fbf  mov     rcx, [rbp+Path.ByteBuffer.ReservedForIMalloc]
0x180059fc3  xor     rcx, rsp; StackCookie
0x180059fc6  call    __security_check_cookie
0x180059fcb  lea     r11, [rsp+70h+Path.MinimumStaticBufferForTerminalNul]
0x180059fd0  mov     rbx, [r11+20h]
0x180059fd4  mov     rsi, [r11+28h]
0x180059fd8  mov     rsp, r11
0x180059fdb  pop     r15
0x180059fdd  pop     rdi
0x180059fde  pop     rbp
0x180059fdf  retn
```
