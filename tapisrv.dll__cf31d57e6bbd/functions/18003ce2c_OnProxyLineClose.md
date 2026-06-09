# OnProxyLineClose

- ea: `0x18003ce2c`
- end: `0x18003cf7f`
- name: `OnProxyLineClose`
- size: `339`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005378`

## callees

- `0x18001c7c0`
- `0x18003a938`
- `0x18003ce2c`
- `0x18003fb88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003cec7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003cec7`
- `KERNEL32!GetCurrentThreadId` at `0x18003ce84`
- `KERNEL32!GetCurrentThreadId` at `0x18003cf46`
- `KERNEL32!GetCurrentThreadId` at `0x18003ce84`
- `KERNEL32!GetCurrentThreadId` at `0x18003cf46`
- `KERNEL32!LeaveCriticalSection` at `0x18003cf6c`
- `KERNEL32!LeaveCriticalSection` at `0x18003cf6c`
- `KERNEL32!EnterCriticalSection` at `0x18003ce74`
- `KERNEL32!EnterCriticalSection` at `0x18003ce74`

## pseudocode

```c
__int64 __fastcall OnProxyLineClose(_WORD *a1)
{
  unsigned __int64 v2; // rax
  unsigned int v3; // esi
  size_t v4; // rdx
  unsigned int i; // edi
  __int64 v6; // r14
  HRESULT v7; // eax
  int v8; // edx
  size_t v9; // rdx

  while ( *a1 == 32 || *a1 == 9 )
    ++a1;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 <= 0x28 )
  {
    v3 = 0;
    EnterCriticalSection(&CriticalSection);
    dword_1800519E0 = 2706;
    dword_1800519E4 = GetCurrentThreadId();
    StringCbCopyA(pszDest, v4, "erver\\dspub.cpp");
    for ( i = 0; i < *(&gProxyScps + 1); ++i )
    {
      v6 = 196LL * i;
      if ( !(unsigned int)_o__wcsicmp(v6 + *(&gProxyScps + 1), a1) )
      {
        if ( !--*(_DWORD *)(v6 + *(&gProxyScps + 1) + 192) )
        {
          v7 = RemoveProxySCP((STRSAFE_LPCWSTR)(v6 + *(&gProxyScps + 1)));
          v8 = *(&gProxyScps + 1);
          v3 = v7;
          if ( i < *(&gProxyScps + 1) - 1 )
          {
            memmove_0(
              (void *)(v6 + *(&gProxyScps + 1)),
              (const void *)(v6 + *(&gProxyScps + 1) + 196),
              196LL * (*(&gProxyScps + 1) - i - 1));
            v8 = *(&gProxyScps + 1);
          }
          *(&gProxyScps + 1) = v8 - 1;
        }
        break;
      }
    }
    dword_1800519F8 = 2740;
    dword_1800519FC = GetCurrentThreadId();
    StringCbCopyA(byte_1800519E8, v9, "erver\\dspub.cpp");
    LeaveCriticalSection(&CriticalSection);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18003ce2c  push    rbx
0x18003ce2e  push    rbp
0x18003ce2f  push    rsi
0x18003ce30  push    rdi
0x18003ce31  push    r14
0x18003ce33  sub     rsp, 20h
0x18003ce37  mov     rbx, rcx
0x18003ce3a  cmp     word ptr [rbx], 20h ; ' '
0x18003ce3e  jz      short loc_18003CE46
0x18003ce40  cmp     word ptr [rbx], 9
0x18003ce44  jnz     short loc_18003CE4C
0x18003ce46  add     rbx, 2
0x18003ce4a  jmp     short loc_18003CE3A
0x18003ce4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ce50  xor     ebp, ebp
0x18003ce52  inc     rax
0x18003ce55  cmp     [rbx+rax*2], bp
0x18003ce59  jnz     short loc_18003CE52
0x18003ce5b  cmp     rax, 28h ; '('
0x18003ce5f  jbe     short loc_18003CE6B
0x18003ce61  mov     esi, 80070057h
0x18003ce66  jmp     loc_18003CF72
0x18003ce6b  lea     rcx, CriticalSection; lpCriticalSection
0x18003ce72  mov     esi, ebp
0x18003ce74  call    cs:__imp_EnterCriticalSection
0x18003ce7a  mov     cs:dword_1800519E0, 0A92h
0x18003ce84  call    cs:__imp_GetCurrentThreadId
0x18003ce8a  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003ce91  mov     cs:dword_1800519E4, eax
0x18003ce97  lea     rcx, pszDest; pszDest
0x18003ce9e  call    StringCbCopyA
0x18003cea3  mov     edi, ebp
0x18003cea5  cmp     edi, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003ceab  jnb     loc_18003CF3C
0x18003ceb1  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003ceb8  mov     rdx, rbx
0x18003cebb  mov     eax, edi
0x18003cebd  imul    r14, rax, 0C4h
0x18003cec4  add     rcx, r14
0x18003cec7  call    cs:__imp__o__wcsicmp
0x18003cecd  test    eax, eax
0x18003cecf  jz      short loc_18003CED5
0x18003ced1  inc     edi
0x18003ced3  jmp     short loc_18003CEA5
0x18003ced5  mov     rax, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003cedc  or      ebx, 0FFFFFFFFh
0x18003cedf  add     [r14+rax+0C0h], ebx
0x18003cee7  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003ceee  add     rcx, r14; pszSrc
0x18003cef1  cmp     [rcx+0C0h], ebp
0x18003cef7  jnz     short loc_18003CF3C
0x18003cef9  call    ?RemoveProxySCP@@YAJPEBG@Z; RemoveProxySCP(ushort const *)
0x18003cefe  mov     edx, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003cf04  mov     esi, eax
0x18003cf06  lea     ecx, [rdx-1]
0x18003cf09  cmp     edi, ecx
0x18003cf0b  jnb     short loc_18003CF34
0x18003cf0d  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003cf14  sub     edx, edi
0x18003cf16  dec     edx
0x18003cf18  add     rcx, r14; void *
0x18003cf1b  imul    r8, rdx, 0C4h; Size
0x18003cf22  lea     rdx, [rcx+0C4h]; Src
0x18003cf29  call    memmove_0
0x18003cf2e  mov     edx, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003cf34  add     edx, ebx
0x18003cf36  mov     dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4, edx; _PROXY_SCPS gProxyScps
0x18003cf3c  mov     cs:dword_1800519F8, 0AB4h
0x18003cf46  call    cs:__imp_GetCurrentThreadId
0x18003cf4c  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003cf53  mov     cs:dword_1800519FC, eax
0x18003cf59  lea     rcx, byte_1800519E8; pszDest
0x18003cf60  call    StringCbCopyA
0x18003cf65  lea     rcx, CriticalSection; lpCriticalSection
0x18003cf6c  call    cs:__imp_LeaveCriticalSection
0x18003cf72  mov     eax, esi
0x18003cf74  add     rsp, 20h
0x18003cf78  pop     r14
0x18003cf7a  pop     rdi
0x18003cf7b  pop     rsi
0x18003cf7c  pop     rbp
0x18003cf7d  pop     rbx
0x18003cf7e  retn
```
