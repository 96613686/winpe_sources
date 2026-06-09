# SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x180052974`
- end: `0x180052b63`
- name: `?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `495`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `11`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006ae0`
- `0x180008e20`
- `0x1800090e0`
- `0x1800097b0`
- `0x18000a760`
- `0x18000ab90`
- `0x18000b78c`
- `0x180013af0`
- `0x180061ac4`
- `0x180066168`
- `0x180067010`

## callees

- `0x18000ab10`
- `0x1800358c0`
- `0x18003633c`
- `0x18005276c`
- `0x180052974`
- `0x18006ad80`
- `0x18006add4`

## import_xrefs

- `SHCORE!__imp_PathIsNetworkPathW` at `0x180052aa1`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x180052aa1`
- `SHLWAPI!PathIsURLW` at `0x1800529d3`
- `SHLWAPI!PathIsURLW` at `0x1800529d3`
- `SHLWAPI!StrStrIW` at `0x180052a72`
- `SHLWAPI!StrStrIW` at `0x180052a8d`
- `SHLWAPI!StrStrIW` at `0x180052ab7`
- `SHLWAPI!StrStrIW` at `0x180052ace`
- `SHLWAPI!StrStrIW` at `0x180052a72`
- `SHLWAPI!StrStrIW` at `0x180052a8d`
- `SHLWAPI!StrStrIW` at `0x180052ab7`
- `SHLWAPI!StrStrIW` at `0x180052ace`
- `SHLWAPI!PathStripToRootW` at `0x180052ade`
- `SHLWAPI!PathStripToRootW` at `0x180052ade`
- `SHLWAPI!PathIsRootW` at `0x180052aed`
- `SHLWAPI!PathIsRootW` at `0x180052aed`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800529ed`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800529ed`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZoneEx(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  const WCHAR *v5; // rdi
  struct IUnknown *v6; // rdx
  __int64 result; // rax
  WCHAR v8; // r10
  WCHAR *v9; // rax
  unsigned int v10; // eax
  WCHAR pszFirst[2088]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v12[4176]; // [rsp+1070h] [rbp+F70h] BYREF

  v5 = a1;
  if ( !a1 )
  {
    if ( a4 )
      *a4 = -1;
    return 2147942487LL;
  }
  if ( !a4 )
    return 2147942487LL;
  memset_0(v12, 0, 0x1048u);
  if ( !PathIsURLW(v5) && (unsigned int)SHExpandEnvironmentStringsW(v5, v12, 2084) )
    v5 = (const WCHAR *)v12;
  result = SHMapUrlToZone(v5, v6, 1u, a4);
  if ( (int)result < 0 )
  {
    memset_0(pszFirst, 0, 0x1048u);
    StringCchCopyW(pszFirst, 0x824u, v5);
    v8 = pszFirst[0];
    if ( pszFirst[0] )
    {
      v9 = pszFirst;
      do
      {
        if ( v8 == 47 )
          *v9 = 92;
        v8 = *++v9;
      }
      while ( *v9 );
    }
    if ( StrStrIW(pszFirst, L"\\??")
      || StrStrIW(pszFirst, L"\\\\?\\GLOBAL")
      || PathIsNetworkPathW(pszFirst)
      || (StrStrIW(pszFirst, L"\\\\") || StrStrIW(pszFirst, L"//"))
      && (!PathStripToRootW(pszFirst)
       || !PathIsRootW(pszFirst)
       || !wcscmp_0(pszFirst, L"\\\\?")
       || !wcscmp_0(pszFirst, L"\\\\.")) )
    {
      v10 = 4;
    }
    else
    {
      v10 = 0;
    }
    *a4 = v10;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180052974  mov     [rsp-8+arg_8], rbx
0x180052979  push    rbp
0x18005297a  push    rsi
0x18005297b  push    rdi
0x18005297c  lea     rbp, [rsp-1FD0h]
0x180052984  mov     eax, 20D0h
0x180052989  call    _alloca_probe
0x18005298e  sub     rsp, rax
0x180052991  mov     rax, cs:__security_cookie
0x180052998  xor     rax, rsp
0x18005299b  mov     [rbp+1FE0h+var_20], rax
0x1800529a2  xor     esi, esi
0x1800529a4  mov     rbx, r9
0x1800529a7  mov     rdi, rcx
0x1800529aa  test    rcx, rcx
0x1800529ad  jz      loc_180052B30
0x1800529b3  test    rbx, rbx
0x1800529b6  jz      loc_180052B3C
0x1800529bc  xor     edx, edx; Val
0x1800529be  lea     rcx, [rbp+1FE0h+var_1070]; void *
0x1800529c5  mov     r8d, 1048h; Size
0x1800529cb  call    memset_0
0x1800529d0  mov     rcx, rdi; pszPath
0x1800529d3  call    cs:__imp_PathIsURLW
0x1800529d9  test    eax, eax
0x1800529db  jnz     short loc_1800529FE
0x1800529dd  mov     r8d, 824h
0x1800529e3  lea     rdx, [rbp+1FE0h+var_1070]
0x1800529ea  mov     rcx, rdi
0x1800529ed  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800529f3  test    eax, eax
0x1800529f5  jz      short loc_1800529FE
0x1800529f7  lea     rdi, [rbp+1FE0h+var_1070]
0x1800529fe  mov     r9, rbx; unsigned int *
0x180052a01  mov     r8d, 1; unsigned int
0x180052a07  mov     rcx, rdi; unsigned __int16 *
0x180052a0a  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x180052a0f  test    eax, eax
0x180052a11  jns     loc_180052B41
0x180052a17  xor     edx, edx; Val
0x180052a19  lea     rcx, [rsp+20E0h+pszFirst]; void *
0x180052a1e  mov     r8d, 1048h; Size
0x180052a24  call    memset_0
0x180052a29  mov     r8, rdi; unsigned __int16 *
0x180052a2c  lea     rcx, [rsp+20E0h+pszFirst]; unsigned __int16 *
0x180052a31  mov     edx, 824h; unsigned __int64
0x180052a36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052a3b  movzx   r10d, [rsp+20E0h+pszFirst]
0x180052a41  test    r10w, r10w
0x180052a45  jz      short loc_180052A66
0x180052a47  lea     rax, [rsp+20E0h+pszFirst]
0x180052a4c  cmp     r10w, 2Fh ; '/'
0x180052a51  jnz     short loc_180052A58
0x180052a53  mov     word ptr [rax], 5Ch ; '\'
0x180052a58  add     rax, 2
0x180052a5c  movzx   r10d, word ptr [rax]
0x180052a60  test    r10w, r10w
0x180052a64  jnz     short loc_180052A4C
0x180052a66  lea     rdx, asc_180078250; "\\??"
0x180052a6d  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x180052a72  call    cs:__imp_StrStrIW
0x180052a78  test    rax, rax
0x180052a7b  jnz     loc_180052B25
0x180052a81  lea     rdx, aGlobal; "\\\\?\\GLOBAL"
0x180052a88  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x180052a8d  call    cs:__imp_StrStrIW
0x180052a93  test    rax, rax
0x180052a96  jnz     loc_180052B25
0x180052a9c  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x180052aa1  call    cs:__imp_PathIsNetworkPathW
0x180052aa7  test    eax, eax
0x180052aa9  jnz     short loc_180052B25
0x180052aab  lea     rdx, asc_180078278; "\\\\"
0x180052ab2  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x180052ab7  call    cs:__imp_StrStrIW
0x180052abd  test    rax, rax
0x180052ac0  jnz     short loc_180052AD9
0x180052ac2  lea     rdx, asc_1800782A0; "//"
0x180052ac9  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x180052ace  call    cs:__imp_StrStrIW
0x180052ad4  test    rax, rax
0x180052ad7  jz      short loc_180052B21
0x180052ad9  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x180052ade  call    cs:__imp_PathStripToRootW
0x180052ae4  test    eax, eax
0x180052ae6  jz      short loc_180052B25
0x180052ae8  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x180052aed  call    cs:__imp_PathIsRootW
0x180052af3  test    eax, eax
0x180052af5  jz      short loc_180052B25
0x180052af7  lea     rdx, asc_180078298; "\\\\?"
0x180052afe  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x180052b03  call    wcscmp_0
0x180052b08  test    eax, eax
0x180052b0a  jz      short loc_180052B25
0x180052b0c  lea     rdx, asc_1800782A8; "\\\\."
0x180052b13  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x180052b18  call    wcscmp_0
0x180052b1d  test    eax, eax
0x180052b1f  jz      short loc_180052B25
0x180052b21  mov     eax, esi
0x180052b23  jmp     short loc_180052B2A
0x180052b25  mov     eax, 4
0x180052b2a  mov     [rbx], eax
0x180052b2c  mov     eax, esi
0x180052b2e  jmp     short loc_180052B41
0x180052b30  test    rbx, rbx
0x180052b33  jz      short loc_180052B3C
0x180052b35  mov     dword ptr [r9], 0FFFFFFFFh
0x180052b3c  mov     eax, 80070057h
0x180052b41  mov     rcx, [rbp+1FE0h+var_20]
0x180052b48  xor     rcx, rsp; StackCookie
0x180052b4b  call    __security_check_cookie
0x180052b50  mov     rbx, [rsp+20E0h+arg_8]
0x180052b58  add     rsp, 20D0h
0x180052b5f  pop     rdi
0x180052b60  pop     rsi
0x180052b61  pop     rbp
0x180052b62  retn
```
