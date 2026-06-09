# CWmiEventManager::CompileMofFile(void)

- ea: `0x180036198`
- end: `0x18003635e`
- name: `?CompileMofFile@CWmiEventManager@@CAJXZ`
- size: `454`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002067c`

## callees

- `0x180002db0`
- `0x18001b3a0`
- `0x180036198`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036212`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036206`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036206`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800361ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800361ea`

## pseudocode

```c
__int64 CWmiEventManager::CompileMofFile(void)
{
  int v0; // ebx
  UINT SystemDirectoryW; // edi
  signed int LastError; // eax
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v8; // [rsp+68h] [rbp-98h] BYREF
  __int64 v9; // [rsp+78h] [rbp-88h]
  unsigned __int16 v10[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  ppv = 0;
  v0 = CoCreateInstance(&CLSID_MofCompiler, 0, 1u, &IID_IMofCompiler, &ppv);
  if ( v0 >= 0 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW )
      goto LABEL_6;
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError > 0 )
      v0 = (unsigned __int16)LastError | 0x80070000;
    if ( v0 >= 0 )
    {
LABEL_6:
      v0 = StringCchCopyW(v10, 0x104u, Buffer);
      if ( v0 >= 0 )
      {
        if ( v10[SystemDirectoryW - 1] == 92 || (v0 = StringCchCatW(v10, v3, L"\\"), v0 >= 0) )
        {
          v0 = StringCchCatW(v10, v3, L"wbem");
          if ( v0 >= 0 )
          {
            v0 = StringCchCatW(v10, v4, L"\\");
            if ( v0 >= 0 )
            {
              v0 = StringCchCatW(v10, v5, L"Wscenter.mof");
              if ( v0 >= 0 )
              {
                v9 = 0;
                v8 = 0;
                v0 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, __int128 *))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       v10,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       &v8);
                if ( v0 == 1 )
                  v0 = -2147467259;
              }
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180036198  mov     [rsp-8+arg_0], rbx
0x18003619d  mov     [rsp-8+arg_8], rdi
0x1800361a2  push    rbp
0x1800361a3  lea     rbp, [rsp-3B0h]
0x1800361ab  sub     rsp, 4B0h
0x1800361b2  mov     rax, cs:__security_cookie
0x1800361b9  xor     rax, rsp
0x1800361bc  mov     [rbp+3B0h+var_10], rax
0x1800361c3  xor     edx, edx; pUnkOuter
0x1800361c5  mov     [rsp+4B0h+var_450], 0
0x1800361ce  lea     rax, [rsp+4B0h+var_450]
0x1800361d3  lea     r9, IID_IMofCompiler; riid
0x1800361da  mov     [rsp+4B0h+ppv], rax; ppv
0x1800361df  lea     rcx, CLSID_MofCompiler; rclsid
0x1800361e6  lea     r8d, [rdx+1]; dwClsContext
0x1800361ea  call    cs:__imp_CoCreateInstance
0x1800361f0  mov     ebx, eax
0x1800361f2  test    eax, eax
0x1800361f4  js      loc_180036338
0x1800361fa  mov     edx, 104h; uSize
0x1800361ff  lea     rcx, [rbp+3B0h+Buffer]; lpBuffer
0x180036206  call    cs:__imp_GetSystemDirectoryW
0x18003620c  mov     edi, eax
0x18003620e  test    eax, eax
0x180036210  jnz     short loc_18003622F
0x180036212  call    cs:__imp_GetLastError
0x180036218  mov     ebx, eax
0x18003621a  test    eax, eax
0x18003621c  jle     short loc_180036227
0x18003621e  movzx   ebx, ax
0x180036221  or      ebx, 80070000h
0x180036227  test    ebx, ebx
0x180036229  js      loc_180036327
0x18003622f  lea     r8, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180036236  mov     edx, 104h; unsigned __int64
0x18003623b  lea     rcx, [rbp+3B0h+var_430]; unsigned __int16 *
0x18003623f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036244  mov     ebx, eax
0x180036246  test    eax, eax
0x180036248  js      loc_180036327
0x18003624e  lea     eax, [rdi-1]
0x180036251  cmp     [rbp+rax*2+3B0h+var_430], 5Ch ; '\'
0x180036257  jz      short loc_180036273
0x180036259  lea     r8, asc_1800465F0; "\\"
0x180036260  lea     rcx, [rbp+3B0h+var_430]; unsigned __int16 *
0x180036264  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036269  mov     ebx, eax
0x18003626b  test    eax, eax
0x18003626d  js      loc_180036327
0x180036273  lea     r8, aWbem; "wbem"
0x18003627a  lea     rcx, [rbp+3B0h+var_430]; unsigned __int16 *
0x18003627e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036283  mov     ebx, eax
0x180036285  test    eax, eax
0x180036287  js      loc_180036327
0x18003628d  lea     r8, asc_1800465F0; "\\"
0x180036294  lea     rcx, [rbp+3B0h+var_430]; unsigned __int16 *
0x180036298  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003629d  mov     ebx, eax
0x18003629f  test    eax, eax
0x1800362a1  js      loc_180036327
0x1800362a7  lea     r8, aWscenterMof; "Wscenter.mof"
0x1800362ae  lea     rcx, [rbp+3B0h+var_430]; unsigned __int16 *
0x1800362b2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800362b7  mov     ebx, eax
0x1800362b9  test    eax, eax
0x1800362bb  js      short loc_180036327
0x1800362bd  mov     rcx, [rsp+4B0h+var_450]
0x1800362c2  lea     rdx, [rsp+4B0h+var_448]
0x1800362c7  mov     [rsp+4B0h+var_468], rdx
0x1800362cc  xor     eax, eax
0x1800362ce  mov     [rsp+4B0h+var_470], 0
0x1800362d6  lea     rdx, [rbp+3B0h+var_430]
0x1800362da  mov     [rsp+4B0h+var_438], rax
0x1800362df  xorps   xmm0, xmm0
0x1800362e2  mov     [rsp+4B0h+var_478], 0
0x1800362ea  xor     r9d, r9d
0x1800362ed  movups  [rsp+4B0h+var_448], xmm0
0x1800362f2  mov     rax, [rcx]
0x1800362f5  xor     r8d, r8d
0x1800362f8  mov     [rsp+4B0h+var_480], 0
0x180036300  mov     [rsp+4B0h+var_488], 0
0x180036309  mov     [rsp+4B0h+ppv], 0
0x180036312  mov     rax, [rax+18h]
0x180036316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003631b  mov     ebx, eax
0x18003631d  cmp     eax, 1
0x180036320  jnz     short loc_180036327
0x180036322  mov     ebx, 80004005h
0x180036327  mov     rcx, [rsp+4B0h+var_450]
0x18003632c  mov     rax, [rcx]
0x18003632f  mov     rax, [rax+10h]
0x180036333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036338  mov     eax, ebx
0x18003633a  mov     rcx, [rbp+3B0h+var_10]
0x180036341  xor     rcx, rsp; StackCookie
0x180036344  call    __security_check_cookie
0x180036349  lea     r11, [rsp+4B0h+var_s0]
0x180036351  mov     rbx, [r11+10h]
0x180036355  mov     rdi, [r11+18h]
0x180036359  mov     rsp, r11
0x18003635c  pop     rbp
0x18003635d  retn
```
