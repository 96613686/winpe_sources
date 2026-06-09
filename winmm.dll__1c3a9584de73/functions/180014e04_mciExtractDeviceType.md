# mciExtractDeviceType

- ea: `0x180014e04`
- end: `0x180014f6b`
- name: `mciExtractDeviceType`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR lpKeyName, LPWSTR lpReturnedString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015480`

## callees

- `0x18000a02c`
- `0x18000c990`
- `0x180014e04`

## import_xrefs

- `ntdll!wcschr` at `0x180014e77`
- `ntdll!wcschr` at `0x180014e77`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180014eb6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180014eb6`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180014f30`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180014f30`

## string_xrefs

- `0x180014f29`: `Mci Extensions`

## pseudocode

```c
_BOOL8 __fastcall mciExtractDeviceType(LPCWSTR lpKeyName, LPWSTR lpReturnedString)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  DWORD PrivateProfileStringW; // eax
  __int64 v7; // rax
  const WCHAR *v8; // rax
  int i; // ecx
  const WCHAR *v10; // rdx
  WCHAR ReturnedString[40]; // [rsp+30h] [rbp-78h] BYREF

  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids, lpKeyName);
  }
  v4 = wcschr(lpKeyName, 0x21u);
  v5 = v4;
  if ( !v4
    || v4 == lpKeyName
    || (*v4 = 0,
        PrivateProfileStringW = GetPrivateProfileStringW(
                                  L"MCI32",
                                  lpKeyName,
                                  &wszNull,
                                  ReturnedString,
                                  0x21u,
                                  L"system.ini"),
        *v5 = 33,
        !PrivateProfileStringW) )
  {
    v7 = -1;
    do
      ++v7;
    while ( lpKeyName[v7] );
    if ( 2 * v7 >= 4 )
    {
      v8 = &lpKeyName[v7];
      for ( i = 1; i <= 32; ++i )
      {
        v10 = v8--;
        if ( *v8 == 47 || *v8 == 92 )
          break;
        if ( *v8 == 46 )
        {
          if ( i == 1 )
            return 0;
          return GetProfileStringW(wszMciExtensions, v10, &wszNull, lpReturnedString, 0x50u) != 0;
        }
        if ( v8 == lpKeyName )
          return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014e04  mov     [rsp+arg_10], rbx
0x180014e09  mov     [rsp+arg_18], rbp
0x180014e0e  push    rsi
0x180014e0f  push    rdi
0x180014e10  push    r14
0x180014e12  sub     rsp, 90h
0x180014e19  mov     rax, cs:__security_cookie
0x180014e20  xor     rax, rsp
0x180014e23  mov     [rsp+0A8h+var_28], rax
0x180014e2b  mov     rsi, rdx
0x180014e2e  mov     rbx, rcx
0x180014e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e38  lea     rax, WPP_GLOBAL_Control
0x180014e3f  cmp     rcx, rax
0x180014e42  jz      short loc_180014E6B
0x180014e44  test    dword ptr [rcx+1Ch], 400000h
0x180014e4b  jz      short loc_180014E6B
0x180014e4d  cmp     byte ptr [rcx+19h], 2
0x180014e51  jb      short loc_180014E6B
0x180014e53  mov     rcx, [rcx+10h]
0x180014e57  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180014e5e  mov     edx, 24h ; '$'
0x180014e63  mov     r9, rbx
0x180014e66  call    WPP_SF_S
0x180014e6b  mov     r14d, 21h ; '!'
0x180014e71  mov     rcx, rbx; Str
0x180014e74  mov     edx, r14d; Ch
0x180014e77  call    cs:__imp_wcschr
0x180014e7d  xor     ebp, ebp
0x180014e7f  mov     rdi, rax
0x180014e82  test    rax, rax
0x180014e85  jz      short loc_180014EC4
0x180014e87  cmp     rax, rbx
0x180014e8a  jz      short loc_180014EC4
0x180014e8c  mov     [rax], bp
0x180014e8f  lea     r9, [rsp+0A8h+ReturnedString]; lpReturnedString
0x180014e94  lea     rax, FileName; "system.ini"
0x180014e9b  mov     rdx, rbx; lpKeyName
0x180014e9e  mov     [rsp+0A8h+lpFileName], rax; lpFileName
0x180014ea3  lea     r8, wszNull; lpDefault
0x180014eaa  lea     rcx, AppName; "MCI32"
0x180014eb1  mov     [rsp+0A8h+nSize], r14d; nSize
0x180014eb6  call    cs:__imp_GetPrivateProfileStringW
0x180014ebc  mov     [rdi], r14w
0x180014ec0  test    eax, eax
0x180014ec2  jnz     short loc_180014F41
0x180014ec4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014ec8  inc     rax
0x180014ecb  cmp     [rbx+rax*2], bp
0x180014ecf  jnz     short loc_180014EC8
0x180014ed1  lea     rcx, [rax+rax]
0x180014ed5  mov     rax, rcx
0x180014ed8  and     rax, 0FFFFFFFFFFFFFFFEh
0x180014edc  cmp     rax, 4
0x180014ee0  jl      short loc_180014F41
0x180014ee2  lea     rax, [rcx+rbx]
0x180014ee6  mov     ecx, 1
0x180014eeb  cmp     ecx, 20h ; ' '
0x180014eee  jg      short loc_180014F41
0x180014ef0  mov     rdx, rax; lpKeyName
0x180014ef3  sub     rax, 2
0x180014ef7  cmp     word ptr [rax], 2Fh ; '/'
0x180014efb  jz      short loc_180014F41
0x180014efd  cmp     word ptr [rax], 5Ch ; '\'
0x180014f01  jz      short loc_180014F41
0x180014f03  cmp     word ptr [rax], 2Eh ; '.'
0x180014f07  jz      short loc_180014F12
0x180014f09  cmp     rax, rbx
0x180014f0c  jz      short loc_180014F41
0x180014f0e  inc     ecx
0x180014f10  jmp     short loc_180014EEB
0x180014f12  cmp     ecx, 1
0x180014f15  jz      short loc_180014F41
0x180014f17  mov     r9, rsi; lpReturnedString
0x180014f1a  mov     [rsp+0A8h+nSize], 50h ; 'P'; nSize
0x180014f22  lea     r8, wszNull; lpDefault
0x180014f29  lea     rcx, ?wszMciExtensions@@3PAGA; "Mci Extensions"
0x180014f30  call    cs:__imp_GetProfileStringW
0x180014f36  test    eax, eax
0x180014f38  mov     ecx, ebp
0x180014f3a  setnz   cl
0x180014f3d  mov     eax, ecx
0x180014f3f  jmp     short loc_180014F43
0x180014f41  xor     eax, eax
0x180014f43  mov     rcx, [rsp+0A8h+var_28]
0x180014f4b  xor     rcx, rsp; StackCookie
0x180014f4e  call    __security_check_cookie
0x180014f53  lea     r11, [rsp+0A8h+var_18]
0x180014f5b  mov     rbx, [r11+30h]
0x180014f5f  mov     rbp, [r11+38h]
0x180014f63  mov     rsp, r11
0x180014f66  pop     r14
0x180014f68  pop     rdi
0x180014f69  pop     rsi
0x180014f6a  retn
```
