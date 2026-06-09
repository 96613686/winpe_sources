# CJsonParser::GetString(ushort const *,ushort const * *)

- ea: `0x180019144`
- end: `0x180019232`
- name: `?GetString@CJsonParser@@QEAAJPEBGPEAPEBG@Z`
- size: `238`
- prototype: `__int64 __fastcall(CJsonParser *this, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d620`

## callees

- `0x18000c1d4`
- `0x180019144`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800191b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800191b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800191e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800191e5`

## pseudocode

```c
__int64 __fastcall CJsonParser::GetString(CJsonParser *this, const unsigned __int16 *a2, const unsigned __int16 **a3)
{
  __int64 *v5; // rbx
  __int64 v6; // rsi
  unsigned __int64 v7; // rdx
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int v11; // ebx
  UINT32 length; // [rsp+20h] [rbp-58h] BYREF
  HSTRING v14; // [rsp+28h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF

  *a3 = 0;
  v5 = (__int64 *)*((_QWORD *)this + 1);
  v14 = 0;
  length = 0;
  if ( v5 && a2 )
  {
    v6 = *v5;
    v7 = -1;
    string = 0;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v7, (unsigned int)a3);
      __debugbreak();
    }
    if ( (int)v7 + 1 < (unsigned int)v7 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v7, (unsigned int)a3);
      __debugbreak();
    }
    v8 = WindowsCreateStringReference(a2, v7, &hstringHeader, &string);
    if ( v8 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
      JUMPOUT(0x180019231LL);
    }
    v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v6 + 80))(v5, string, &v14);
    if ( v11 >= 0 )
      *a3 = WindowsGetStringRawBuffer(v14, &length);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019144  mov     [rsp+arg_18], rbx
0x180019149  push    rbp
0x18001914a  push    rsi
0x18001914b  push    rdi
0x18001914c  sub     rsp, 60h
0x180019150  mov     rax, cs:__security_cookie
0x180019157  xor     rax, rsp
0x18001915a  mov     [rsp+78h+var_28], rax
0x18001915f  xor     ebp, ebp
0x180019161  mov     rdi, r8
0x180019164  mov     [r8], rbp
0x180019167  mov     r10, rdx
0x18001916a  mov     rbx, [rcx+8]
0x18001916e  mov     [rsp+78h+var_50], rbp
0x180019173  mov     [rsp+78h+length], ebp
0x180019177  test    rbx, rbx
0x18001917a  jz      short loc_1800191F0
0x18001917c  test    rdx, rdx
0x18001917f  jz      short loc_1800191F0
0x180019181  mov     rsi, [rbx]
0x180019184  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019188  mov     [rsp+78h+string], rbp
0x18001918d  inc     rdx; int
0x180019190  cmp     [r10+rdx*2], bp
0x180019195  jnz     short loc_18001918D
0x180019197  mov     eax, 0FFFFFFFFh
0x18001919c  cmp     rdx, rax
0x18001919f  ja      short loc_180019214
0x1800191a1  lea     eax, [rdx+1]
0x1800191a4  cmp     eax, edx
0x1800191a6  jb      short loc_18001921F
0x1800191a8  lea     r9, [rsp+78h+string]; string
0x1800191ad  mov     rcx, r10; sourceString
0x1800191b0  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1800191b5  call    cs:__imp_WindowsCreateStringReference
0x1800191bb  test    eax, eax
0x1800191bd  js      short loc_18001922A
0x1800191bf  mov     rdx, [rsp+78h+string]
0x1800191c4  lea     r8, [rsp+78h+var_50]
0x1800191c9  mov     rax, [rsi+50h]
0x1800191cd  mov     rcx, rbx
0x1800191d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d5  mov     ebx, eax
0x1800191d7  test    eax, eax
0x1800191d9  js      short loc_1800191F5
0x1800191db  mov     rcx, [rsp+78h+var_50]; string
0x1800191e0  lea     rdx, [rsp+78h+length]; length
0x1800191e5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800191eb  mov     [rdi], rax
0x1800191ee  jmp     short loc_1800191F5
0x1800191f0  mov     ebx, 80070057h
0x1800191f5  mov     eax, ebx
0x1800191f7  mov     rcx, [rsp+78h+var_28]
0x1800191fc  xor     rcx, rsp; StackCookie
0x1800191ff  call    __security_check_cookie
0x180019204  mov     rbx, [rsp+78h+arg_18]
0x18001920c  add     rsp, 60h
0x180019210  pop     rdi
0x180019211  pop     rsi
0x180019212  pop     rbp
0x180019213  retn
0x180019214  mov     ecx, 80070216h; this
0x180019219  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001921e  int     3; Trap to Debugger
0x18001921f  mov     ecx, 80070216h; this
0x180019224  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180019229  int     3; Trap to Debugger
0x18001922a  mov     ecx, eax; this
0x18001922c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
