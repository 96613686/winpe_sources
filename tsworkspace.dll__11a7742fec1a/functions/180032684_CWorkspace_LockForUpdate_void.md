# CWorkspace::LockForUpdate(void)

- ea: `0x180032684`
- end: `0x180032836`
- name: `?LockForUpdate@CWorkspace@@QEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800387e4`
- `0x1800504c4`
- `0x18007525c`
- `0x180075d30`
- `0x1800761c0`

## callees

- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x1800208a8`
- `0x180020bf0`
- `0x180032684`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800327d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800327d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800327eb`
- `KERNEL32!CreateMutexW` at `0x180032753`
- `KERNEL32!CreateMutexW` at `0x180032753`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWorkspace::LockForUpdate(CWorkspace *this)
{
  __int64 v2; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE MutexW; // rax
  const WCHAR *v5; // rax
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // eax
  signed int LastError; // eax
  _BYTE v14[32]; // [rsp+38h] [rbp-30h] BYREF

  std::wstring::wstring(v14);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 64);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix,
      v2);
  }
  std::wstring::assign(v14, L"Local\\workspace.");
  std::wstring::append(v14, (char *)this + 64, 0, -1);
  MutexW = (HANDLE)*((_QWORD *)this + 22);
  if ( MutexW
    || (v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14),
        MutexW = CreateMutexW(0, 0, v5),
        (*((_QWORD *)this + 22) = MutexW) != 0) )
  {
    v11 = WaitForSingleObject(MutexW, 0);
    if ( !v11 || v11 == 128 )
    {
      v10 = 0;
    }
    else if ( v11 == 258 )
    {
      v10 = -2147220992;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v8, v7);
    }
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  std::wstring::~wstring(v14);
  return v10;
}

```

## disassembly

```asm
0x180032684  mov     r11, rsp
0x180032687  push    rdi
0x180032688  sub     rsp, 60h
0x18003268c  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180032694  mov     [r11+10h], rbx
0x180032698  mov     [r11+18h], rsi
0x18003269c  mov     rax, cs:__security_cookie
0x1800326a3  xor     rax, rsp
0x1800326a6  mov     [rsp+68h+var_10], rax
0x1800326ab  mov     rdi, rcx
0x1800326ae  lea     rcx, [r11-30h]
0x1800326b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800326b7  nop
0x1800326b8  lea     rsi, WPP_GLOBAL_Control
0x1800326bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800326c6  cmp     rax, rsi
0x1800326c9  jz      short loc_18003270C
0x1800326cb  test    byte ptr [rax+1Ch], 1
0x1800326cf  jz      short loc_18003270C
0x1800326d1  cmp     byte ptr [rax+19h], 4
0x1800326d5  jb      short loc_18003270C
0x1800326d7  lea     rcx, [rdi+40h]
0x1800326db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800326e0  mov     rbx, rax
0x1800326e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800326e8  mov     edx, 55h ; 'U'
0x1800326ed  mov     [rsp+68h+var_48], rbx
0x1800326f2  mov     r9d, eax
0x1800326f5  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800326fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180032703  mov     rcx, [rcx+10h]
0x180032707  call    WPP_SF_DS
0x18003270c  lea     rdx, aLocalWorkspace_0; "Local\\workspace."
0x180032713  lea     rcx, [rsp+68h+var_30]
0x180032718  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18003271d  lea     rdx, [rdi+40h]
0x180032721  or      r9, 0FFFFFFFFFFFFFFFFh
0x180032725  xor     r8d, r8d
0x180032728  lea     rcx, [rsp+68h+var_30]
0x18003272d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180032732  mov     rax, [rdi+0B0h]
0x180032739  test    rax, rax
0x18003273c  jnz     loc_1800327CE
0x180032742  lea     rcx, [rsp+68h+var_30]
0x180032747  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003274c  mov     r8, rax; lpName
0x18003274f  xor     edx, edx; bInitialOwner
0x180032751  xor     ecx, ecx; lpMutexAttributes
0x180032753  call    cs:__imp_CreateMutexW
0x180032759  mov     [rdi+0B0h], rax
0x180032760  test    rax, rax
0x180032763  jnz     short loc_1800327CE
0x180032765  mov     edi, 80070000h
0x18003276a  mov     rax, cs:WPP_GLOBAL_Control
0x180032771  cmp     rax, rsi
0x180032774  jz      short loc_1800327BB
0x180032776  test    byte ptr [rax+1Ch], 8
0x18003277a  jz      short loc_1800327BB
0x18003277c  cmp     byte ptr [rax+19h], 2
0x180032780  jb      short loc_1800327BB
0x180032782  call    cs:__imp_GetLastError
0x180032788  mov     ebx, eax
0x18003278a  test    eax, eax
0x18003278c  jle     short loc_180032793
0x18003278e  movzx   ebx, ax
0x180032791  or      ebx, edi
0x180032793  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032798  mov     edx, 56h ; 'V'
0x18003279d  mov     dword ptr [rsp+68h+var_48], ebx
0x1800327a1  mov     r9d, eax
0x1800327a4  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800327ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327b2  mov     rcx, [rcx+10h]
0x1800327b6  call    WPP_SF_Dd
0x1800327bb  call    cs:__imp_GetLastError
0x1800327c1  mov     ebx, eax
0x1800327c3  test    eax, eax
0x1800327c5  jle     short loc_18003280B
0x1800327c7  movzx   ebx, ax
0x1800327ca  or      ebx, edi
0x1800327cc  jmp     short loc_18003280B
0x1800327ce  xor     edx, edx; dwMilliseconds
0x1800327d0  mov     rcx, rax; hHandle
0x1800327d3  call    cs:__imp_WaitForSingleObject
0x1800327d9  test    eax, eax
0x1800327db  jz      short loc_180032809
0x1800327dd  cmp     eax, 80h
0x1800327e2  jz      short loc_180032809
0x1800327e4  cmp     eax, 102h
0x1800327e9  jz      short loc_180032802
0x1800327eb  call    cs:__imp_GetLastError
0x1800327f1  mov     ebx, eax
0x1800327f3  test    eax, eax
0x1800327f5  jle     short loc_18003280B
0x1800327f7  movzx   ebx, ax
0x1800327fa  or      ebx, 80070000h
0x180032800  jmp     short loc_18003280B
0x180032802  mov     ebx, 80040200h
0x180032807  jmp     short loc_18003280B
0x180032809  xor     ebx, ebx
0x18003280b  lea     rcx, [rsp+68h+var_30]; void *
0x180032810  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032815  mov     eax, ebx
0x180032817  mov     rcx, [rsp+68h+var_10]
0x18003281c  xor     rcx, rsp; StackCookie
0x18003281f  call    __security_check_cookie
0x180032824  lea     r11, [rsp+68h+var_8]
0x180032829  mov     rbx, [r11+18h]
0x18003282d  mov     rsi, [r11+20h]
0x180032831  mov     rsp, r11
0x180032834  pop     rdi
0x180032835  retn
```
