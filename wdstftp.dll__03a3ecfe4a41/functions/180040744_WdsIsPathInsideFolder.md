# WdsIsPathInsideFolder

- ea: `0x180040744`
- end: `0x180040a12`
- name: `WdsIsPathInsideFolder`
- size: `718`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800153d0`

## callees

- `0x18000fd58`
- `0x180010658`
- `0x180040464`
- `0x180040744`
- `0x1800607b0`
- `0x180060cd6`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800407ad`
- `KERNEL32!GetLastError` at `0x1800407ad`
- `KERNEL32!CompareStringW` at `0x18004081f`
- `KERNEL32!CompareStringW` at `0x180040855`
- `KERNEL32!CompareStringW` at `0x180040966`
- `KERNEL32!CompareStringW` at `0x18004081f`
- `KERNEL32!CompareStringW` at `0x180040855`
- `KERNEL32!CompareStringW` at `0x180040966`

## pseudocode

```c
_BOOL8 __fastcall WdsIsPathInsideFolder(wchar_t *String1, unsigned __int16 *a2, __int64 a3)
{
  BOOL v5; // edi
  int v6; // r14d
  __int64 v7; // r8
  signed int LastError; // eax
  unsigned __int64 v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  size_t v12; // r8
  size_t v13; // r8
  wchar_t v15[264]; // [rsp+50h] [rbp-A88h] BYREF
  WCHAR lpString2[264]; // [rsp+260h] [rbp-878h] BYREF
  wchar_t pszDest[264]; // [rsp+470h] [rbp-668h] BYREF
  WCHAR String2[264]; // [rsp+680h] [rbp-458h] BYREF
  WCHAR String1a[264]; // [rsp+890h] [rbp-248h] BYREF

  v5 = 0;
  v6 = 0;
  if ( String1 && a2 )
  {
    if ( (unsigned int)WdsGetVolumeNameFromPath(String1, String1a, a3, v15)
      && (unsigned int)WdsGetVolumeNameFromPath(a2, String2, v7, lpString2) )
    {
      v9 = -1;
      if ( CompareStringW(0x409u, 1u, String1a, -1, String2, -1) == 2 )
      {
        if ( CompareStringW(0x409u, 1u, v15, -1, lpString2, -1) == 2 )
          goto LABEL_10;
        v10 = -1;
        do
          ++v10;
        while ( lpString2[v10] );
        if ( !v10 )
        {
LABEL_10:
          v5 = 1;
        }
        else
        {
          v6 = StringCchCopyW(pszDest, 0x104u, lpString2);
          if ( v6 >= 0 )
          {
            v6 = StringCchCatW(pszDest, 0x104u, L"\\");
            if ( v6 >= 0 )
            {
              v11 = -1;
              do
                ++v11;
              while ( v15[v11] );
              v12 = -1;
              do
                ++v12;
              while ( pszDest[v12] );
              v5 = v12 <= v11;
              if ( v12 <= v11 )
                v5 = wcsnicmp_0(v15, pszDest, v12) == 0;
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      v9 = -1;
    }
    if ( v6 < 0 )
    {
      if ( CompareStringW(0x409u, 1u, String1, -1, a2, -1) == 2 )
      {
        return 1;
      }
      else if ( (int)StringCchCopyW(v15, 0x104u, a2) >= 0 && StringCchCatW(v15, 0x104u, L"\\") >= 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v15[v13] );
        do
          ++v9;
        while ( String1[v9] );
        v5 = v13 <= v9;
        if ( v13 <= v9 )
          return wcsnicmp_0(String1, v15, v13) == 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180040744  mov     [rsp+arg_10], rbx
0x180040749  push    rsi
0x18004074a  push    rdi
0x18004074b  push    r12
0x18004074d  push    r14
0x18004074f  push    r15
0x180040751  sub     rsp, 0AB0h
0x180040758  mov     rax, cs:__security_cookie
0x18004075f  xor     rax, rsp
0x180040762  mov     [rsp+0AD8h+var_38], rax
0x18004076a  mov     r12, rdx
0x18004076d  mov     r15, rcx
0x180040770  mov     [rsp+0AD8h+var_AA0], rcx
0x180040775  mov     [rsp+0AD8h+var_A98], rdx
0x18004077a  xor     ebx, ebx
0x18004077c  mov     edi, ebx
0x18004077e  mov     [rsp+0AD8h+var_AA4], ebx
0x180040782  mov     r14d, ebx
0x180040785  test    rcx, rcx
0x180040788  jz      loc_1800409E8
0x18004078e  test    rdx, rdx
0x180040791  jz      loc_1800409E8
0x180040797  lea     r9, [rsp+0AD8h+var_A88]
0x18004079c  lea     rdx, [rsp+0AD8h+String1]; unsigned __int16 *
0x1800407a4  call    WdsGetVolumeNameFromPath
0x1800407a9  test    eax, eax
0x1800407ab  jnz     short loc_1800407DB
0x1800407ad  call    cs:__imp_GetLastError
0x1800407b4  nop     dword ptr [rax+rax+00h]
0x1800407b9  movzx   r14d, ax
0x1800407bd  or      r14d, 80070000h
0x1800407c4  test    eax, eax
0x1800407c6  cmovle  r14d, eax
0x1800407ca  mov     [rsp+0AD8h+var_AA8], r14d
0x1800407cf  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800407d6  jmp     loc_180040921
0x1800407db  lea     r9, [rsp+0AD8h+var_878]
0x1800407e3  lea     rdx, [rsp+0AD8h+String2]; unsigned __int16 *
0x1800407eb  mov     rcx, r12; unsigned __int16 *
0x1800407ee  call    WdsGetVolumeNameFromPath
0x1800407f3  test    eax, eax
0x1800407f5  jz      short loc_1800407AD
0x1800407f7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800407fb  mov     [rsp+0AD8h+cchCount2], esi; cchCount2
0x1800407ff  lea     rax, [rsp+0AD8h+String2]
0x180040807  mov     [rsp+0AD8h+lpString2], rax; lpString2
0x18004080c  mov     r9d, esi; cchCount1
0x18004080f  lea     r8, [rsp+0AD8h+String1]; lpString1
0x180040817  lea     edx, [rsi+2]; dwCmpFlags
0x18004081a  mov     ecx, 409h; Locale
0x18004081f  call    cs:__imp_CompareStringW
0x180040826  nop     dword ptr [rax+rax+00h]
0x18004082b  cmp     eax, 2
0x18004082e  jnz     loc_180040921
0x180040834  mov     [rsp+0AD8h+cchCount2], esi; cchCount2
0x180040838  lea     rax, [rsp+0AD8h+var_878]
0x180040840  mov     [rsp+0AD8h+lpString2], rax; lpString2
0x180040845  mov     r9d, esi; cchCount1
0x180040848  lea     r8, [rsp+0AD8h+var_A88]; lpString1
0x18004084d  lea     edx, [rsi+2]; dwCmpFlags
0x180040850  mov     ecx, 409h; Locale
0x180040855  call    cs:__imp_CompareStringW
0x18004085c  nop     dword ptr [rax+rax+00h]
0x180040861  cmp     eax, 2
0x180040864  jnz     short loc_180040870
0x180040866  mov     edi, 1
0x18004086b  jmp     loc_18004091D
0x180040870  lea     rcx, [rsp+0AD8h+var_878]
0x180040878  mov     rax, rsi
0x18004087b  inc     rax
0x18004087e  cmp     [rcx+rax*2], bx
0x180040882  jnz     short loc_18004087B
0x180040884  test    rax, rax
0x180040887  jz      short loc_180040866
0x180040889  lea     r8, [rsp+0AD8h+var_878]; unsigned __int16 *
0x180040891  mov     edx, 104h; unsigned __int64
0x180040896  lea     rcx, [rsp+0AD8h+pszDest]; unsigned __int16 *
0x18004089e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800408a3  mov     r14d, eax
0x1800408a6  mov     [rsp+0AD8h+var_AA8], eax
0x1800408aa  test    eax, eax
0x1800408ac  js      short loc_180040921
0x1800408ae  lea     r8, asc_180065EC0; "\\"
0x1800408b5  mov     edx, 104h; cchDest
0x1800408ba  lea     rcx, [rsp+0AD8h+pszDest]; pszDest
0x1800408c2  call    StringCchCatW
0x1800408c7  mov     r14d, eax
0x1800408ca  mov     [rsp+0AD8h+var_AA8], eax
0x1800408ce  test    eax, eax
0x1800408d0  js      short loc_180040921
0x1800408d2  lea     rcx, [rsp+0AD8h+var_A88]
0x1800408d7  mov     rax, rsi
0x1800408da  inc     rax
0x1800408dd  cmp     [rcx+rax*2], bx
0x1800408e1  jnz     short loc_1800408DA
0x1800408e3  lea     rcx, [rsp+0AD8h+pszDest]
0x1800408eb  mov     r8, rsi
0x1800408ee  inc     r8; MaxCount
0x1800408f1  cmp     [rcx+r8*2], bx
0x1800408f6  jnz     short loc_1800408EE
0x1800408f8  mov     edi, ebx
0x1800408fa  cmp     r8, rax
0x1800408fd  setbe   dil
0x180040901  ja      short loc_18004091D
0x180040903  lea     rdx, [rsp+0AD8h+pszDest]; String2
0x18004090b  lea     rcx, [rsp+0AD8h+var_A88]; String1
0x180040910  call    _wcsnicmp_0
0x180040915  mov     edi, ebx
0x180040917  test    eax, eax
0x180040919  setz    dil
0x18004091d  mov     [rsp+0AD8h+var_AA4], edi
0x180040921  jmp     short loc_180040944
0x180040923  mov     r14d, eax
0x180040926  bts     r14d, 1Ch
0x18004092b  mov     [rsp+0AD8h+var_AA8], r14d
0x180040930  xor     ebx, ebx
0x180040932  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180040936  mov     edi, [rsp+0AD8h+var_AA4]
0x18004093a  mov     r15, [rsp+0AD8h+var_AA0]
0x18004093f  mov     r12, [rsp+0AD8h+var_A98]
0x180040944  test    r14d, r14d
0x180040947  jns     loc_1800409E8
0x18004094d  mov     [rsp+0AD8h+cchCount2], esi; cchCount2
0x180040951  mov     [rsp+0AD8h+lpString2], r12; lpString2
0x180040956  mov     r9d, esi; cchCount1
0x180040959  mov     r8, r15; lpString1
0x18004095c  mov     edx, 1; dwCmpFlags
0x180040961  mov     ecx, 409h; Locale
0x180040966  call    cs:__imp_CompareStringW
0x18004096d  nop     dword ptr [rax+rax+00h]
0x180040972  cmp     eax, 2
0x180040975  jnz     short loc_18004097C
0x180040977  lea     edi, [rax-1]
0x18004097a  jmp     short loc_1800409E8
0x18004097c  mov     r8, r12; unsigned __int16 *
0x18004097f  mov     edx, 104h; unsigned __int64
0x180040984  lea     rcx, [rsp+0AD8h+var_A88]; unsigned __int16 *
0x180040989  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004098e  test    eax, eax
0x180040990  js      short loc_1800409E8
0x180040992  lea     r8, asc_180065EC0; "\\"
0x180040999  mov     edx, 104h; cchDest
0x18004099e  lea     rcx, [rsp+0AD8h+var_A88]; pszDest
0x1800409a3  call    StringCchCatW
0x1800409a8  test    eax, eax
0x1800409aa  js      short loc_1800409E8
0x1800409ac  lea     rax, [rsp+0AD8h+var_A88]
0x1800409b1  mov     r8, rsi
0x1800409b4  inc     r8; MaxCount
0x1800409b7  cmp     [rax+r8*2], bx
0x1800409bc  jnz     short loc_1800409B4
0x1800409be  inc     rsi
0x1800409c1  cmp     [r15+rsi*2], bx
0x1800409c6  jnz     short loc_1800409BE
0x1800409c8  mov     edi, ebx
0x1800409ca  cmp     r8, rsi
0x1800409cd  setbe   dil
0x1800409d1  ja      short loc_1800409E8
0x1800409d3  lea     rdx, [rsp+0AD8h+var_A88]; String2
0x1800409d8  mov     rcx, r15; String1
0x1800409db  call    _wcsnicmp_0
0x1800409e0  mov     edi, ebx
0x1800409e2  test    eax, eax
0x1800409e4  setz    dil
0x1800409e8  mov     eax, edi
0x1800409ea  mov     rcx, [rsp+0AD8h+var_38]
0x1800409f2  xor     rcx, rsp; StackCookie
0x1800409f5  call    __security_check_cookie
0x1800409fa  mov     rbx, [rsp+0AD8h+arg_10]
0x180040a02  add     rsp, 0AB0h
0x180040a09  pop     r15
0x180040a0b  pop     r14
0x180040a0d  pop     r12
0x180040a0f  pop     rdi
0x180040a10  pop     rsi
0x180040a11  retn
```
