# CreateMultiLanguage(IMultiLanguage * *)

- ea: `0x3839bf180`
- end: `0x3839bf232`
- name: `?CreateMultiLanguage@@YAJPEAPEAUIMultiLanguage@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct IMultiLanguage **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3839bf080`
- `0x3839bf700`

## callees

- `0x3839bf180`

## import_xrefs

- `KERNEL32!Sleep` at `0x3839bf218`
- `KERNEL32!Sleep` at `0x3839bf218`
- `ole32!CoCreateInstance` at `0x3839bf1da`
- `ole32!CoCreateInstance` at `0x3839bf200`
- `ole32!CoCreateInstance` at `0x3839bf1da`
- `ole32!CoCreateInstance` at `0x3839bf200`

## pseudocode

```c
__int64 __fastcall CreateMultiLanguage(struct IMultiLanguage **a1)
{
  unsigned int v1; // ebx
  HRESULT Instance; // [rsp+40h] [rbp+8h]

  v1 = 0;
  Instance = 0;
  if ( !g_pMultiLanguage )
  {
    while ( _InterlockedCompareExchange(&g_fMultiLanguageInitLock, 1, 0) )
      Sleep(0);
    if ( !g_pMultiLanguage )
    {
      Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &g_pMultiLanguage);
      if ( Instance < 0 )
        Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, &g_pMultiLanguage);
    }
    _InterlockedExchange(&g_fMultiLanguageInitLock, 0);
    return (unsigned int)Instance;
  }
  return v1;
}

```

## disassembly

```asm
0x3839bf180  mov     [rsp+arg_8], rbx
0x3839bf185  mov     [rsp+arg_10], rsi
0x3839bf18a  push    rdi
0x3839bf18b  sub     rsp, 30h
0x3839bf18f  lea     rdi, ?g_pMultiLanguage@@3PEAUIMultiLanguage@@EA; IMultiLanguage * g_pMultiLanguage
0x3839bf196  xor     ebx, ebx
0x3839bf198  mov     [rsp+38h+arg_0], ebx
0x3839bf19c  cmp     cs:?g_pMultiLanguage@@3PEAUIMultiLanguage@@EA, rbx; IMultiLanguage * g_pMultiLanguage
0x3839bf1a3  jnz     short loc_3839BF220
0x3839bf1a5  mov     esi, 1
0x3839bf1aa  nop     word ptr [rax+rax+00h]
0x3839bf1b0  xor     eax, eax
0x3839bf1b2  lock cmpxchg cs:?g_fMultiLanguageInitLock@@3JC, esi; long volatile g_fMultiLanguageInitLock
0x3839bf1ba  jnz     short loc_3839BF216
0x3839bf1bc  cmp     qword ptr [rdi], 0
0x3839bf1c0  jnz     short loc_3839BF20A
0x3839bf1c2  mov     [rsp+38h+ppv], rdi; ppv
0x3839bf1c7  lea     r9, IID_IMultiLanguage2; riid
0x3839bf1ce  mov     r8d, esi; dwClsContext
0x3839bf1d1  xor     edx, edx; pUnkOuter
0x3839bf1d3  lea     rcx, CLSID_CMultiLanguage; rclsid
0x3839bf1da  call    cs:__imp_CoCreateInstance
0x3839bf1e0  mov     [rsp+38h+arg_0], eax
0x3839bf1e4  test    eax, eax
0x3839bf1e6  jns     short loc_3839BF20A
0x3839bf1e8  mov     [rsp+38h+ppv], rdi; ppv
0x3839bf1ed  lea     r9, IID_IMultiLanguage; riid
0x3839bf1f4  mov     r8d, esi; dwClsContext
0x3839bf1f7  xor     edx, edx; pUnkOuter
0x3839bf1f9  lea     rcx, CLSID_CMultiLanguage; rclsid
0x3839bf200  call    cs:__imp_CoCreateInstance
0x3839bf206  mov     [rsp+38h+arg_0], eax
0x3839bf20a  xchg    ebx, cs:?g_fMultiLanguageInitLock@@3JC; long volatile g_fMultiLanguageInitLock
0x3839bf210  mov     ebx, [rsp+38h+arg_0]
0x3839bf214  jmp     short loc_3839BF220
0x3839bf216  xor     ecx, ecx; dwMilliseconds
0x3839bf218  call    cs:__imp_Sleep
0x3839bf21e  jmp     short loc_3839BF1B0
0x3839bf220  mov     eax, ebx
0x3839bf222  mov     rbx, [rsp+38h+arg_8]
0x3839bf227  mov     rsi, [rsp+38h+arg_10]
0x3839bf22c  add     rsp, 30h
0x3839bf230  pop     rdi
0x3839bf231  retn
0x383adf0e0  push    rbp
0x383adf0e2  sub     rsp, 30h
0x383adf0e6  mov     rbp, rdx
0x383adf0e9  xor     eax, eax
0x383adf0eb  xchg    eax, cs:?g_fMultiLanguageInitLock@@3JC; long volatile g_fMultiLanguageInitLock
0x383adf0f1  add     rsp, 30h
0x383adf0f5  pop     rbp
0x383adf0f6  retn
```
