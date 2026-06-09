# INTERNET_SESSION_HANDLE_OBJECT::CreateWebIOSession(void)

- ea: `0x18006d61c`
- end: `0x18006d773`
- name: `?CreateWebIOSession@INTERNET_SESSION_HANDLE_OBJECT@@QEAAKXZ`
- size: `343`
- prototype: `unsigned int __fastcall(INTERNET_SESSION_HANDLE_OBJECT *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18006d23c`
- `0x18006d3cc`
- `0x18006d54c`

## callees

- `0x18006d61c`
- `0x18006d77c`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d694`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d6e5`
- `webio!__imp_WebCloseSession` at `0x18006d747`
- `webio!__imp_WebCloseSession` at `0x18006d747`
- `webio!__imp_WebCreateSession` at `0x18006d6b3`
- `webio!__imp_WebCreateSession` at `0x18006d6b3`

## pseudocode

```c
__int64 __fastcall INTERNET_SESSION_HANDLE_OBJECT::CreateWebIOSession(INTERNET_SESSION_HANDLE_OBJECT *this)
{
  unsigned int WebIOApiHandle; // ebx
  unsigned int v3; // ebx
  signed __int32 v5[8]; // [rsp+0h] [rbp-48h] BYREF
  unsigned __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF

  v6 = 0;
  v7 = 0;
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_(1025, 54, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  if ( *((_DWORD *)this + 142) )
  {
    _InterlockedOr(v5, 0);
    WebIOApiHandle = 0;
  }
  else
  {
    WebIOApiHandle = WINHTTP_GLOBALS::GetWebIOApiHandle(this, &v6);
    if ( !WebIOApiHandle )
    {
      v3 = *((_DWORD *)this + 35) == 0 ? 0x80000000 : 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
      if ( *((_DWORD *)this + 142) )
      {
        WebIOApiHandle = 0;
      }
      else
      {
        WebIOApiHandle = WebCreateSession(v6, v3, &v7);
        if ( !WebIOApiHandle )
        {
          *((_QWORD *)this + 70) = v7;
          v7 = 0;
          _InterlockedOr(v5, 0);
          *((_DWORD *)this + 142) = 1;
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
    }
  }
  if ( v7 )
  {
    WebCloseSession(v7, 0);
    v7 = 0;
  }
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_d(1025, 55, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, WebIOApiHandle, v6);
  return WebIOApiHandle;
}

```

## disassembly

```asm
0x18006d61c  mov     r11, rsp
0x18006d61f  mov     [r11+10h], rbx
0x18006d623  mov     [r11+18h], rsi
0x18006d627  push    rdi
0x18006d628  sub     rsp, 40h
0x18006d62c  mov     rax, cs:__security_cookie
0x18006d633  xor     rax, rsp
0x18006d636  mov     [rsp+48h+var_18], rax
0x18006d63b  mov     rdi, rcx
0x18006d63e  mov     qword ptr [r11-28h], 0
0x18006d646  mov     qword ptr [r11-20h], 0
0x18006d64e  test    byte ptr cs:xmmword_180107A60, 2
0x18006d655  jnz     loc_18006D726
0x18006d65b  cmp     dword ptr [rdi+238h], 0
0x18006d662  jnz     loc_18006D71D
0x18006d668  lea     rdx, [rsp+48h+var_28]; unsigned __int64 *
0x18006d66d  call    ?GetWebIOApiHandle@WINHTTP_GLOBALS@@QEAAKPEA_K@Z; WINHTTP_GLOBALS::GetWebIOApiHandle(unsigned __int64 *)
0x18006d672  mov     ebx, eax
0x18006d674  test    eax, eax
0x18006d676  jnz     short loc_18006D6EB
0x18006d678  mov     eax, [rdi+8Ch]
0x18006d67e  lea     rsi, [rdi+148h]
0x18006d685  neg     eax
0x18006d687  mov     rcx, rsi; lpCriticalSection
0x18006d68a  sbb     ebx, ebx
0x18006d68c  not     ebx
0x18006d68e  and     ebx, 80000000h
0x18006d694  call    cs:__imp_EnterCriticalSection
0x18006d69a  cmp     dword ptr [rdi+238h], 0
0x18006d6a1  jnz     loc_18006D741
0x18006d6a7  mov     rcx, [rsp+48h+var_28]
0x18006d6ac  lea     r8, [rsp+48h+var_20]
0x18006d6b1  mov     edx, ebx
0x18006d6b3  call    cs:__imp_WebCreateSession
0x18006d6b9  mov     ebx, eax
0x18006d6bb  test    eax, eax
0x18006d6bd  jnz     short loc_18006D6E2
0x18006d6bf  mov     rax, [rsp+48h+var_20]
0x18006d6c4  mov     [rdi+230h], rax
0x18006d6cb  mov     [rsp+48h+var_20], 0
0x18006d6d4  lock or [rsp+48h+var_48], ebx
0x18006d6d8  mov     dword ptr [rdi+238h], 1
0x18006d6e2  mov     rcx, rsi; lpCriticalSection
0x18006d6e5  call    cs:__imp_LeaveCriticalSection
0x18006d6eb  mov     rcx, [rsp+48h+var_20]
0x18006d6f0  test    rcx, rcx
0x18006d6f3  jnz     short loc_18006D745
0x18006d6f5  test    byte ptr cs:xmmword_180107A60, 2
0x18006d6fc  jnz     short loc_18006D758
0x18006d6fe  mov     eax, ebx
0x18006d700  mov     rcx, [rsp+48h+var_18]
0x18006d705  xor     rcx, rsp; StackCookie
0x18006d708  call    __security_check_cookie
0x18006d70d  mov     rbx, [rsp+48h+arg_8]
0x18006d712  mov     rsi, [rsp+48h+arg_10]
0x18006d717  add     rsp, 40h
0x18006d71b  pop     rdi
0x18006d71c  retn
0x18006d71d  lock or [rsp+48h+var_48], 0
0x18006d722  xor     ebx, ebx
0x18006d724  jmp     short loc_18006D6EB
0x18006d726  mov     edx, 36h ; '6'
0x18006d72b  lea     r8, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x18006d732  mov     ecx, 401h
0x18006d737  call    WPP_SF_
0x18006d73c  jmp     loc_18006D65B
0x18006d741  xor     ebx, ebx
0x18006d743  jmp     short loc_18006D6E2
0x18006d745  xor     edx, edx
0x18006d747  call    cs:__imp_WebCloseSession
0x18006d74d  mov     [rsp+48h+var_20], 0
0x18006d756  jmp     short loc_18006D6F5
0x18006d758  mov     edx, 37h ; '7'
0x18006d75d  lea     r8, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x18006d764  mov     ecx, 401h
0x18006d769  mov     r9d, ebx
0x18006d76c  call    WPP_SF_d
0x18006d771  jmp     short loc_18006D6FE
```
