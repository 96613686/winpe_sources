# CEmptyVolumeCache::Initialize(HKEY__ *,ushort const *,ushort * *,ushort * *,ulong *)

- ea: `0x180038da0`
- end: `0x180038f0b`
- name: `?Initialize@CEmptyVolumeCache@@UEAAJPEAUHKEY__@@PEBGPEAPEAG2PEAK@Z`
- size: `363`
- prototype: `int(CEmptyVolumeCache *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180035830`
- `0x1800364ac`
- `0x180038da0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038e87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038eb5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038e87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038eb5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180038e19`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180038e19`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180038e95`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180038ec3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180038e95`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180038ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038edb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038edb`

## pseudocode

```c
__int64 __fastcall CEmptyVolumeCache::Initialize(
        CEmptyVolumeCache *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **ppwsz,
        unsigned int *a6)
{
  HRESULT v9; // ebx
  _QWORD *v10; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[1022]; // [rsp+32h] [rbp-CEh] BYREF
  WCHAR psz2[264]; // [rsp+430h] [rbp+330h] BYREF

  v9 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64))(**((_QWORD **)this + 2) + 32LL))(
         *((_QWORD *)this + 2),
         psz2,
         260);
  if ( v9 >= 0 )
  {
    if ( !StrCmpNIW(a3, psz2, 3)
      && (v10 = *(_QWORD **)this,
          v12 = 0,
          ((void (__fastcall *)(CEmptyVolumeCache *, __int64 *, _QWORD))v10[4])(this, &v12, 0),
          v12) )
    {
      Buffer = 0;
      memset_0(v14, 0, sizeof(v14));
      LoadStringW(g_hmodThisDll, 0x3E8u, &Buffer, 512);
      v9 = SHStrDupW(&Buffer, a4);
      if ( v9 >= 0 )
      {
        LoadStringW(g_hmodThisDll, 0x3E9u, &Buffer, 512);
        v9 = SHStrDupW(&Buffer, ppwsz);
        if ( v9 < 0 )
        {
          CoTaskMemFree(*a4);
          *a4 = 0;
        }
        else
        {
          *a6 = 2;
        }
      }
    }
    else
    {
      return 1;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180038da0  push    rbp
0x180038da2  push    rbx
0x180038da3  push    rsi
0x180038da4  push    rdi
0x180038da5  push    r12
0x180038da7  push    r14
0x180038da9  push    r15
0x180038dab  lea     rbp, [rsp-550h]
0x180038db3  sub     rsp, 650h
0x180038dba  mov     rax, cs:__security_cookie
0x180038dc1  xor     rax, rsp
0x180038dc4  mov     [rbp+580h+var_40], rax
0x180038dcb  mov     r12, [rbp+580h+ppwsz]
0x180038dd2  lea     rdx, [rbp+580h+psz2]
0x180038dd9  mov     r14, [rbp+580h+arg_28]
0x180038de0  mov     rsi, rcx
0x180038de3  mov     rcx, [rcx+10h]
0x180038de7  mov     r15, r8
0x180038dea  mov     r8d, 104h
0x180038df0  mov     rdi, r9
0x180038df3  mov     rax, [rcx]
0x180038df6  mov     rax, [rax+20h]
0x180038dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dff  mov     ebx, eax
0x180038e01  test    eax, eax
0x180038e03  js      loc_180038EE8
0x180038e09  mov     r8d, 3; nChar
0x180038e0f  lea     rdx, [rbp+580h+psz2]; psz2
0x180038e16  mov     rcx, r15; psz1
0x180038e19  call    cs:__imp_StrCmpNIW
0x180038e1f  test    eax, eax
0x180038e21  jnz     short loc_180038E4B
0x180038e23  mov     rax, [rsi]
0x180038e26  lea     rdx, [rsp+680h+var_660]
0x180038e2b  xor     r8d, r8d
0x180038e2e  mov     [rsp+680h+var_660], 0
0x180038e37  mov     rcx, rsi
0x180038e3a  mov     rax, [rax+20h]
0x180038e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e43  cmp     [rsp+680h+var_660], 0
0x180038e49  jnz     short loc_180038E55
0x180038e4b  mov     ebx, 1
0x180038e50  jmp     loc_180038EE8
0x180038e55  xor     eax, eax
0x180038e57  lea     rcx, [rsp+680h+var_64E]; void *
0x180038e5c  xor     edx, edx; Val
0x180038e5e  mov     [rsp+680h+Buffer], ax
0x180038e63  mov     r8d, 3FEh; Size
0x180038e69  call    memset_0
0x180038e6e  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180038e75  lea     r8, [rsp+680h+Buffer]; lpBuffer
0x180038e7a  mov     esi, 200h
0x180038e7f  mov     edx, 3E8h; uID
0x180038e84  mov     r9d, esi; cchBufferMax
0x180038e87  call    cs:__imp_LoadStringW
0x180038e8d  mov     rdx, rdi; ppwsz
0x180038e90  lea     rcx, [rsp+680h+Buffer]; psz
0x180038e95  call    cs:__imp_SHStrDupW
0x180038e9b  mov     ebx, eax
0x180038e9d  test    eax, eax
0x180038e9f  js      short loc_180038EE8
0x180038ea1  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180038ea8  lea     r8, [rsp+680h+Buffer]; lpBuffer
0x180038ead  mov     r9d, esi; cchBufferMax
0x180038eb0  mov     edx, 3E9h; uID
0x180038eb5  call    cs:__imp_LoadStringW
0x180038ebb  mov     rdx, r12; ppwsz
0x180038ebe  lea     rcx, [rsp+680h+Buffer]; psz
0x180038ec3  call    cs:__imp_SHStrDupW
0x180038ec9  mov     ebx, eax
0x180038ecb  test    eax, eax
0x180038ecd  js      short loc_180038ED8
0x180038ecf  mov     dword ptr [r14], 2
0x180038ed6  jmp     short loc_180038EE8
0x180038ed8  mov     rcx, [rdi]; pv
0x180038edb  call    cs:__imp_CoTaskMemFree
0x180038ee1  mov     qword ptr [rdi], 0
0x180038ee8  mov     eax, ebx
0x180038eea  mov     rcx, [rbp+580h+var_40]
0x180038ef1  xor     rcx, rsp; StackCookie
0x180038ef4  call    __security_check_cookie
0x180038ef9  add     rsp, 650h
0x180038f00  pop     r15
0x180038f02  pop     r14
0x180038f04  pop     r12
0x180038f06  pop     rdi
0x180038f07  pop     rsi
0x180038f08  pop     rbx
0x180038f09  pop     rbp
0x180038f0a  retn
```
