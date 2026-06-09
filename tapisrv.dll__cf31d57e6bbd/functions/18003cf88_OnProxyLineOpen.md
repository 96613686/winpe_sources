# OnProxyLineOpen

- ea: `0x18003cf88`
- end: `0x18003d1a6`
- name: `OnProxyLineOpen`
- size: `542`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001fb28`

## callees

- `0x18001c7c0`
- `0x18001c854`
- `0x18002c8d4`
- `0x180037264`
- `0x18003cf88`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d01b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d01b`
- `KERNEL32!HeapAlloc` at `0x18003d08f`
- `KERNEL32!HeapAlloc` at `0x18003d08f`
- `KERNEL32!GetCurrentThreadId` at `0x18003cfdc`
- `KERNEL32!GetCurrentThreadId` at `0x18003d16f`
- `KERNEL32!GetCurrentThreadId` at `0x18003cfdc`
- `KERNEL32!GetCurrentThreadId` at `0x18003d16f`
- `KERNEL32!LeaveCriticalSection` at `0x18003d195`
- `KERNEL32!LeaveCriticalSection` at `0x18003d195`
- `KERNEL32!EnterCriticalSection` at `0x18003cfcc`
- `KERNEL32!EnterCriticalSection` at `0x18003cfcc`

## pseudocode

```c
__int64 __fastcall OnProxyLineOpen(unsigned __int16 *a1)
{
  unsigned __int64 v2; // rax
  HRESULT ProxySCP; // edi
  size_t v4; // rdx
  unsigned int i; // edi
  __int64 v6; // rsi
  unsigned int v7; // ecx
  void *v8; // rdi
  __int64 v9; // r11
  wchar_t *v10; // rcx
  size_t v11; // rdx
  STRSAFE_LPCWSTR pszSrc; // [rsp+50h] [rbp+8h] BYREF

  while ( *a1 == 32 || *a1 == 9 )
    ++a1;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 <= 0x28 )
  {
    EnterCriticalSection(&CriticalSection);
    dword_1800519E0 = 2613;
    dword_1800519E4 = GetCurrentThreadId();
    StringCbCopyA(pszDest, v4, "erver\\dspub.cpp");
    for ( i = 0; i < *(&gProxyScps + 1); ++i )
    {
      v6 = 196LL * i;
      if ( !(unsigned int)_o__wcsicmp(v6 + *(&gProxyScps + 1), a1) )
      {
        ProxySCP = 0;
        ++*(_DWORD *)(v6 + *(&gProxyScps + 1) + 192);
        goto LABEL_23;
      }
    }
    pszSrc = 0;
    ProxySCP = CreateProxySCP(a1, (unsigned __int16 **)&pszSrc);
    if ( ProxySCP < 0 )
    {
      dword_1800519F8 = 2640;
      goto LABEL_24;
    }
    v7 = *(&gProxyScps + 1);
    if ( *(&gProxyScps + 1) < gProxyScps )
    {
      v8 = (void *)*(&gProxyScps + 1);
    }
    else
    {
      v8 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(196 * (gProxyScps + 16)));
      if ( !v8 )
      {
        ProxySCP = -2147483580;
        ServerFree((LPVOID)pszSrc);
        dword_1800519F8 = 2656;
        goto LABEL_24;
      }
      memcpy_0(v8, *(&gProxyScps + 1), 196LL * gProxyScps);
      ServerFree(*(&gProxyScps + 1));
      gProxyScps += 16;
      v7 = *(&gProxyScps + 1);
      *(&gProxyScps + 1) = v8;
    }
    *(&gProxyScps + 1) = v7 + 1;
    ProxySCP = StringCbCopyW((STRSAFE_LPWSTR)v8 + 98 * v7, 0x50u, a1);
    if ( ProxySCP >= 0 )
      ProxySCP = StringCbCopyW((STRSAFE_LPWSTR)(v9 + *(&gProxyScps + 1) + 80LL), 0x70u, pszSrc);
    v10 = (wchar_t *)pszSrc;
    *(_DWORD *)(v9 + *(&gProxyScps + 1) + 192) = 1;
    ServerFree(v10);
LABEL_23:
    dword_1800519F8 = 2682;
LABEL_24:
    dword_1800519FC = GetCurrentThreadId();
    StringCbCopyA(byte_1800519E8, v11, "erver\\dspub.cpp");
    LeaveCriticalSection(&CriticalSection);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ProxySCP;
}

```

## disassembly

```asm
0x18003cf88  push    rbx
0x18003cf8a  push    rbp
0x18003cf8b  push    rsi
0x18003cf8c  push    rdi
0x18003cf8d  sub     rsp, 28h
0x18003cf91  mov     rbx, rcx
0x18003cf94  cmp     word ptr [rbx], 20h ; ' '
0x18003cf98  jz      short loc_18003CFA0
0x18003cf9a  cmp     word ptr [rbx], 9
0x18003cf9e  jnz     short loc_18003CFA6
0x18003cfa0  add     rbx, 2
0x18003cfa4  jmp     short loc_18003CF94
0x18003cfa6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003cfaa  xor     ebp, ebp
0x18003cfac  inc     rax
0x18003cfaf  cmp     [rbx+rax*2], bp
0x18003cfb3  jnz     short loc_18003CFAC
0x18003cfb5  cmp     rax, 28h ; '('
0x18003cfb9  jbe     short loc_18003CFC5
0x18003cfbb  mov     edi, 80070057h
0x18003cfc0  jmp     loc_18003D19B
0x18003cfc5  lea     rcx, CriticalSection; lpCriticalSection
0x18003cfcc  call    cs:__imp_EnterCriticalSection
0x18003cfd2  mov     cs:dword_1800519E0, 0A35h
0x18003cfdc  call    cs:__imp_GetCurrentThreadId
0x18003cfe2  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003cfe9  mov     cs:dword_1800519E4, eax
0x18003cfef  lea     rcx, pszDest; pszDest
0x18003cff6  call    StringCbCopyA
0x18003cffb  mov     edi, ebp
0x18003cffd  cmp     edi, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003d003  jnb     short loc_18003D03E
0x18003d005  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003d00c  mov     rdx, rbx
0x18003d00f  mov     eax, edi
0x18003d011  imul    rsi, rax, 0C4h
0x18003d018  add     rcx, rsi
0x18003d01b  call    cs:__imp__o__wcsicmp
0x18003d021  test    eax, eax
0x18003d023  jz      short loc_18003D029
0x18003d025  inc     edi
0x18003d027  jmp     short loc_18003CFFD
0x18003d029  mov     rax, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003d030  mov     edi, ebp
0x18003d032  inc     dword ptr [rsi+rax+0C0h]
0x18003d039  jmp     loc_18003D165
0x18003d03e  lea     rdx, [rsp+48h+pszSrc]; unsigned __int16 **
0x18003d043  mov     [rsp+48h+pszSrc], rbp
0x18003d048  mov     rcx, rbx; unsigned __int16 *
0x18003d04b  call    ?CreateProxySCP@@YAJPEBGPEAPEAG@Z; CreateProxySCP(ushort const *,ushort * *)
0x18003d050  mov     edi, eax
0x18003d052  test    eax, eax
0x18003d054  jns     short loc_18003D065
0x18003d056  mov     cs:dword_1800519F8, 0A50h
0x18003d060  jmp     loc_18003D16F
0x18003d065  mov     ecx, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003d06b  mov     eax, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A; _PROXY_SCPS gProxyScps
0x18003d071  cmp     ecx, eax
0x18003d073  jb      loc_18003D0F9
0x18003d079  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003d080  add     eax, 10h
0x18003d083  imul    r8d, eax, 0C4h; dwBytes
0x18003d08a  mov     edx, 8; dwFlags
0x18003d08f  call    cs:__imp_HeapAlloc
0x18003d095  mov     rdi, rax
0x18003d098  test    rax, rax
0x18003d09b  jnz     short loc_18003D0BB
0x18003d09d  mov     rcx, [rsp+48h+pszSrc]; lpMem
0x18003d0a2  mov     edi, 80000044h
0x18003d0a7  call    ServerFree
0x18003d0ac  mov     cs:dword_1800519F8, 0A60h
0x18003d0b6  jmp     loc_18003D16F
0x18003d0bb  mov     eax, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A; _PROXY_SCPS gProxyScps
0x18003d0c1  mov     rcx, rdi; void *
0x18003d0c4  mov     rdx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; Src
0x18003d0cb  imul    r8, rax, 0C4h; Size
0x18003d0d2  call    memcpy_0
0x18003d0d7  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; lpMem
0x18003d0de  call    ServerFree
0x18003d0e3  add     dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A, 10h; _PROXY_SCPS gProxyScps
0x18003d0ea  mov     ecx, dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4; _PROXY_SCPS gProxyScps
0x18003d0f0  mov     qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8, rdi; _PROXY_SCPS gProxyScps
0x18003d0f7  jmp     short loc_18003D100
0x18003d0f9  mov     rdi, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003d100  lea     eax, [rcx+1]
0x18003d103  mov     r8, rbx; pszSrc
0x18003d106  mov     dword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+4, eax; _PROXY_SCPS gProxyScps
0x18003d10c  mov     edx, 50h ; 'P'; cbDest
0x18003d111  mov     eax, ecx
0x18003d113  imul    r11, rax, 0C4h
0x18003d11a  lea     rcx, [r11+rdi]; pszDest
0x18003d11e  call    StringCbCopyW
0x18003d123  mov     edi, eax
0x18003d125  test    eax, eax
0x18003d127  js      short loc_18003D148
0x18003d129  mov     rcx, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003d130  mov     edx, 70h ; 'p'; cbDest
0x18003d135  mov     r8, [rsp+48h+pszSrc]; pszSrc
0x18003d13a  add     rcx, 50h ; 'P'
0x18003d13e  add     rcx, r11; pszDest
0x18003d141  call    StringCbCopyW
0x18003d146  mov     edi, eax
0x18003d148  mov     rax, qword ptr cs:?gProxyScps@@3U_PROXY_SCPS@@A+8; _PROXY_SCPS gProxyScps
0x18003d14f  mov     rcx, [rsp+48h+pszSrc]; lpMem
0x18003d154  mov     dword ptr [r11+rax+0C0h], 1
0x18003d160  call    ServerFree
0x18003d165  mov     cs:dword_1800519F8, 0A7Ah
0x18003d16f  call    cs:__imp_GetCurrentThreadId
0x18003d175  lea     r8, aPrintscanTapiS_0+10h; pszSrc
0x18003d17c  mov     cs:dword_1800519FC, eax
0x18003d182  lea     rcx, byte_1800519E8; pszDest
0x18003d189  call    StringCbCopyA
0x18003d18e  lea     rcx, CriticalSection; lpCriticalSection
0x18003d195  call    cs:__imp_LeaveCriticalSection
0x18003d19b  mov     eax, edi
0x18003d19d  add     rsp, 28h
0x18003d1a1  pop     rdi
0x18003d1a2  pop     rsi
0x18003d1a3  pop     rbp
0x18003d1a4  pop     rbx
0x18003d1a5  retn
```
