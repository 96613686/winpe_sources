# GetUserProfileListRootKeyName(ushort * *,int *)

- ea: `0x180003d70`
- end: `0x180003f51`
- name: `?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z`
- size: `481`
- prototype: `__int64 __fastcall(unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002ad0`
- `0x180003410`

## callees

- `0x180003d70`
- `0x180003f60`
- `0x180007130`
- `0x18000cea0`
- `0x18000e330`
- `0x1800178ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003e04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003dde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003db7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ef3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ef3`

## string_xrefs

- `0x180003eb9`: `OneCore\internal\DS\inc\profiles\sid.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUserProfileListRootKeyName(unsigned __int16 **a1, int *a2)
{
  BYTE *v3; // rsi
  int v4; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // r8
  int v7; // ebx
  __int64 v8; // rcx
  const wchar_t *v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r10
  unsigned __int16 *v12; // r11
  __int64 v13; // r14
  HANDLE v14; // rax
  __int64 v16; // rdx
  int v17; // ebx
  int v18; // [rsp+20h] [rbp-48h]
  BYTE *v19[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  *a1 = 0;
  memset(v19, 0, 24);
  hKey = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProfileList", 0, 0x20019u, &hKey);
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 >= 0 )
  {
    v17 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
            v19,
            hKey,
            L"RedirectionKey");
    RegCloseKey(hKey);
    if ( v17 >= 0 )
    {
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
             (__int64)v19,
             a1);
      if ( v7 < 0 )
      {
        v16 = 82;
        goto LABEL_18;
      }
      v3 = v19[0];
      goto LABEL_13;
    }
    v3 = v19[0];
  }
  ProcessHeap = GetProcessHeap();
  *a1 = 0;
  if ( !is_mul_ok(0x39u, 2u) )
  {
    v7 = -2147024362;
    goto LABEL_17;
  }
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, (0x39 * (unsigned __int128)2uLL) >> 64, 0x72u);
  *a1 = v6;
  if ( !v6 )
  {
    v7 = -2147024882;
LABEL_17:
    v16 = 90;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
      (const char *)(unsigned int)v7,
      v18);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v19);
    return (unsigned int)v7;
  }
  v8 = 56;
  v9 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  v10 = 57;
  v11 = 0;
  v12 = v6;
  while ( v8 && *v9 )
  {
    *v6++ = *v9++;
    --v8;
    ++v11;
    if ( !--v10 )
    {
      *(v6 - 1) = 0;
      goto LABEL_13;
    }
  }
  v13 = 57 - v11;
  *v6 = 0;
  if ( (unsigned __int64)(57 - v11) > 1 && (unsigned __int64)(2 * v13) > 2 )
    memset_0(&v12[v11 + 1], 0, 2 * v13 - 2);
LABEL_13:
  if ( v3 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180003d70  mov     r11, rsp
0x180003d73  mov     [r11+10h], rdx
0x180003d77  push    rbp
0x180003d78  push    rsi
0x180003d79  push    rdi
0x180003d7a  sub     rsp, 50h
0x180003d7e  xor     ebp, ebp
0x180003d80  lea     rax, [r11+10h]
0x180003d84  mov     [rcx], rbp
0x180003d87  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pro"...
0x180003d8e  mov     rdi, rcx
0x180003d91  mov     [r11-38h], rbp
0x180003d95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003d9c  mov     [r11-30h], rbp
0x180003da0  mov     r9d, 20019h; samDesired
0x180003da6  mov     [r11-28h], rbp
0x180003daa  xor     r8d, r8d; ulOptions
0x180003dad  mov     [r11+10h], rbp
0x180003db1  mov     esi, ebp
0x180003db3  mov     [r11-48h], rax
0x180003db7  call    cs:__imp_RegOpenKeyExW
0x180003dbd  test    eax, eax
0x180003dbf  jle     short loc_180003DC9
0x180003dc1  movzx   eax, ax
0x180003dc4  or      eax, 80070000h
0x180003dc9  mov     [rsp+68h+arg_0], rbx
0x180003dce  mov     [rsp+68h+arg_10], r14
0x180003dd6  test    eax, eax
0x180003dd8  jns     loc_180003ED6
0x180003dde  call    cs:__imp_GetProcessHeap
0x180003de4  mov     r14d, 39h ; '9'
0x180003dea  mov     [rdi], rbp
0x180003ded  mov     rcx, rax; hHeap
0x180003df0  mov     eax, 2
0x180003df5  mul     r14
0x180003df8  test    rdx, rdx
0x180003dfb  jnz     loc_180003EAA
0x180003e01  mov     r8, rax; dwBytes
0x180003e04  call    cs:__imp_HeapAlloc
0x180003e0a  mov     r8, rax
0x180003e0d  mov     [rdi], rax
0x180003e10  test    r8, r8
0x180003e13  mov     ebx, ebp
0x180003e15  mov     eax, 8007000Eh
0x180003e1a  cmovz   ebx, eax
0x180003e1d  jz      loc_180003EAF
0x180003e23  mov     ecx, 38h ; '8'
0x180003e28  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003e2f  mov     r9d, r14d
0x180003e32  mov     r10, rbp
0x180003e35  mov     r11, r8
0x180003e38  test    rcx, rcx
0x180003e3b  jz      short loc_180003E69
0x180003e3d  movzx   eax, word ptr [rdx]
0x180003e40  test    ax, ax
0x180003e43  jz      short loc_180003E64
0x180003e45  mov     [r8], ax
0x180003e49  add     rdx, 2
0x180003e4d  add     r8, 2
0x180003e51  dec     rcx
0x180003e54  inc     r10
0x180003e57  sub     r9, 1
0x180003e5b  jnz     short loc_180003E38
0x180003e5d  mov     [r8-2], bp
0x180003e62  jmp     short loc_180003E7A
0x180003e64  test    r9, r9
0x180003e67  jz      short loc_180003E5D
0x180003e69  sub     r14, r10
0x180003e6c  mov     [r8], bp
0x180003e70  cmp     r14, 1
0x180003e74  ja      loc_180003F2B
0x180003e7a  test    rsi, rsi
0x180003e7d  jz      short loc_180003E93
0x180003e7f  call    cs:__imp_GetProcessHeap
0x180003e85  mov     r8, rsi; lpMem
0x180003e88  xor     edx, edx; dwFlags
0x180003e8a  mov     rcx, rax; hHeap
0x180003e8d  call    cs:__imp_HeapFree
0x180003e93  xor     eax, eax
0x180003e95  mov     r14, [rsp+68h+arg_10]
0x180003e9d  mov     rbx, [rsp+68h+arg_0]
0x180003ea2  add     rsp, 50h
0x180003ea6  pop     rdi
0x180003ea7  pop     rsi
0x180003ea8  pop     rbp
0x180003ea9  retn
0x180003eaa  mov     ebx, 80070216h
0x180003eaf  mov     edx, 5Ah ; 'Z'; void *
0x180003eb4  mov     rcx, [rsp+68h]; this
0x180003eb9  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x180003ec0  mov     r9d, ebx; char *
0x180003ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ec8  lea     rcx, [rsp+68h+var_38]
0x180003ecd  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003ed2  mov     eax, ebx
0x180003ed4  jmp     short loc_180003E95
0x180003ed6  mov     rdx, [rsp+68h+hKey]
0x180003edb  lea     r8, aRedirectionkey; "RedirectionKey"
0x180003ee2  lea     rcx, [rsp+68h+var_38]
0x180003ee7  call    ?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x180003eec  mov     rcx, [rsp+68h+hKey]; hKey
0x180003ef1  mov     ebx, eax
0x180003ef3  call    cs:__imp_RegCloseKey
0x180003ef9  test    ebx, ebx
0x180003efb  jns     short loc_180003F07
0x180003efd  mov     rsi, [rsp+68h+var_38]
0x180003f02  jmp     loc_180003DDE
0x180003f07  mov     rdx, rdi
0x180003f0a  lea     rcx, [rsp+68h+var_38]
0x180003f0f  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180003f14  mov     ebx, eax
0x180003f16  test    eax, eax
0x180003f18  jns     short loc_180003F21
0x180003f1a  mov     edx, 52h ; 'R'
0x180003f1f  jmp     short loc_180003EB4
0x180003f21  mov     rsi, [rsp+68h+var_38]
0x180003f26  jmp     loc_180003E7A
0x180003f2b  lea     r8, [r14+r14]
0x180003f2f  cmp     r8, 2
0x180003f33  jbe     loc_180003E7A
0x180003f39  add     r11, 2
0x180003f3d  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180003f41  xor     edx, edx; Val
0x180003f43  lea     rcx, [r11+r10*2]; void *
0x180003f47  call    memset_0
0x180003f4c  jmp     loc_180003E7A
```
