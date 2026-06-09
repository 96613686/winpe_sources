# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x1800223c0`
- end: `0x18002252b`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `363`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003336c`

## callees

- `0x1800223c0`
- `0x1800358c0`
- `0x180036324`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800224ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800224ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022417`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022417`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002245e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800224bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002245e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800224bf`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v6; // esi
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v6 = 1;
    v7 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v8 = v7;
  }
  else
  {
    v8 = 0;
    v6 = 0;
  }
  if ( v8 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, a3, 2u, 0, Src, &pcbData);
  v8 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v8 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v8 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v8 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v8 = 14;
    }
  }
  if ( v6 )
    RegCloseKey(hkey);
  if ( v8 )
  {
LABEL_18:
    *a5 = 0;
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800223c0  mov     [rsp-8+arg_18], rbx
0x1800223c5  push    rbp
0x1800223c6  push    rsi
0x1800223c7  push    rdi
0x1800223c8  push    r14
0x1800223ca  push    r15
0x1800223cc  lea     rbp, [rsp-60h]
0x1800223d1  sub     rsp, 160h
0x1800223d8  mov     rax, cs:__security_cookie
0x1800223df  xor     rax, rsp
0x1800223e2  mov     [rbp+80h+var_30], rax
0x1800223e6  mov     rdi, [rbp+80h+arg_20]
0x1800223ed  xor     r15d, r15d
0x1800223f0  mov     [rsp+180h+hkey], rcx
0x1800223f5  mov     r14, r8
0x1800223f8  test    rdx, rdx
0x1800223fb  jz      short loc_180022426
0x1800223fd  cmp     [rdx], r15w
0x180022401  jz      short loc_180022426
0x180022403  lea     rax, [rsp+180h+hkey]
0x180022408  xor     r8d, r8d; ulOptions
0x18002240b  lea     esi, [r15+1]
0x18002240f  mov     [rsp+180h+phkResult], rax; phkResult
0x180022414  mov     r9d, esi; samDesired
0x180022417  call    cs:__imp_RegOpenKeyExW
0x18002241d  mov     rcx, [rsp+180h+hkey]; hkey
0x180022422  mov     ebx, eax
0x180022424  jmp     short loc_18002242C
0x180022426  mov     ebx, r15d
0x180022429  mov     esi, r15d
0x18002242c  test    ebx, ebx
0x18002242e  jnz     loc_1800224F6
0x180022434  lea     rax, [rsp+180h+var_140]
0x180022439  mov     [rsp+180h+var_140], 100h
0x180022441  mov     [rsp+180h+pcbData], rax; pcbData
0x180022446  lea     r9d, [rbx+2]; dwFlags
0x18002244a  lea     rax, [rsp+180h+Src]
0x18002244f  mov     r8, r14; lpValue
0x180022452  mov     [rsp+180h+pvData], rax; pvData
0x180022457  xor     edx, edx; lpSubKey
0x180022459  mov     [rsp+180h+phkResult], r15; pdwType
0x18002245e  call    cs:__imp_RegGetValueW
0x180022464  mov     ebx, eax
0x180022466  test    eax, eax
0x180022468  jz      short loc_180022471
0x18002246a  cmp     eax, 0EAh
0x18002246f  jnz     short loc_1800224E3
0x180022471  mov     ecx, [rsp+180h+var_140]; cb
0x180022475  call    cs:__imp_CoTaskMemAlloc
0x18002247b  mov     [rdi], rax
0x18002247e  test    rax, rax
0x180022481  jz      short loc_1800224DE
0x180022483  test    ebx, ebx
0x180022485  jnz     short loc_18002249B
0x180022487  mov     r8d, [rsp+180h+var_140]; Size
0x18002248c  lea     rdx, [rsp+180h+Src]; Src
0x180022491  mov     rcx, rax; void *
0x180022494  call    memcpy_0
0x180022499  jmp     short loc_1800224E3
0x18002249b  lea     rcx, [rsp+180h+var_140]
0x1800224a0  mov     r9d, 2; dwFlags
0x1800224a6  mov     [rsp+180h+pcbData], rcx; pcbData
0x1800224ab  mov     r8, r14; lpValue
0x1800224ae  mov     rcx, [rsp+180h+hkey]; hkey
0x1800224b3  xor     edx, edx; lpSubKey
0x1800224b5  mov     [rsp+180h+pvData], rax; pvData
0x1800224ba  mov     [rsp+180h+phkResult], r15; pdwType
0x1800224bf  call    cs:__imp_RegGetValueW
0x1800224c5  test    eax, eax
0x1800224c7  jnz     short loc_1800224CE
0x1800224c9  mov     ebx, r15d
0x1800224cc  jmp     short loc_1800224E3
0x1800224ce  mov     rcx, [rdi]; pv
0x1800224d1  mov     ebx, 3EBh
0x1800224d6  call    cs:__imp_CoTaskMemFree
0x1800224dc  jmp     short loc_1800224E3
0x1800224de  mov     ebx, 0Eh
0x1800224e3  test    esi, esi
0x1800224e5  jz      short loc_1800224F2
0x1800224e7  mov     rcx, [rsp+180h+hkey]; hKey
0x1800224ec  call    cs:__imp_RegCloseKey
0x1800224f2  test    ebx, ebx
0x1800224f4  jz      short loc_180022506
0x1800224f6  mov     [rdi], r15
0x1800224f9  test    ebx, ebx
0x1800224fb  jle     short loc_180022506
0x1800224fd  movzx   ebx, bx
0x180022500  or      ebx, 80070000h
0x180022506  mov     eax, ebx
0x180022508  mov     rcx, [rbp+80h+var_30]
0x18002250c  xor     rcx, rsp; StackCookie
0x18002250f  call    __security_check_cookie
0x180022514  mov     rbx, [rsp+180h+arg_18]
0x18002251c  add     rsp, 160h
0x180022523  pop     r15
0x180022525  pop     r14
0x180022527  pop     rdi
0x180022528  pop     rsi
0x180022529  pop     rbp
0x18002252a  retn
```
