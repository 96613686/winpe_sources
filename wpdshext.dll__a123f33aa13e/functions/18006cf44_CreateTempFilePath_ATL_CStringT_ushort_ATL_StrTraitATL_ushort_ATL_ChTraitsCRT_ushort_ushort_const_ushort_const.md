# CreateTempFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,ushort const *)

- ea: `0x18006cf44`
- end: `0x18006d092`
- name: `?CreateTempFilePath@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG1@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005b288`
- `0x18005f698`

## callees

- `0x18000d610`
- `0x180015700`
- `0x180035590`
- `0x1800361ba`
- `0x180069dc0`
- `0x18006cf44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006cfe5`
- `KERNEL32!GetLastError` at `0x18006cfe5`
- `KERNEL32!GetTempPath2W` at `0x18006cf82`
- `KERNEL32!GetTempPath2W` at `0x18006cfc7`
- `KERNEL32!GetTempPath2W` at `0x18006cf82`
- `KERNEL32!GetTempPath2W` at `0x18006cfc7`
- `ole32!StringFromGUID2` at `0x18006d022`
- `ole32!StringFromGUID2` at `0x18006d022`
- `ole32!CoCreateGuid` at `0x18006d003`
- `ole32!CoCreateGuid` at `0x18006d003`

## pseudocode

```c
__int64 __fastcall CreateTempFilePath(_QWORD *a1)
{
  unsigned int TempPath2W; // eax
  unsigned int v3; // ebx
  unsigned __int64 v4; // rsi
  unsigned __int128 v5; // rax
  void *v6; // rax
  void *v7; // rdi
  unsigned int v8; // eax
  int v9; // ebx
  signed int LastError; // eax
  __int16 v12; // [rsp+30h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+38h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-88h] BYREF

  v12 = 0;
  pguid = GUID_NULL;
  TempPath2W = GetTempPath2W(1, &v12);
  v3 = TempPath2W;
  if ( !TempPath2W )
  {
    v7 = 0;
LABEL_10:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
    if ( v9 < 0 )
      goto LABEL_18;
    goto LABEL_13;
  }
  v4 = TempPath2W + 1;
  v5 = (TempPath2W + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v4, 2u) )
    *(_QWORD *)&v5 = -1;
  v6 = operator new(v5, *((const struct std::nothrow_t **)&v5 + 1));
  v7 = v6;
  if ( !v6 )
  {
    v9 = -2147024882;
    goto LABEL_12;
  }
  memset_0(v6, 0, 2 * v4);
  v8 = GetTempPath2W(v3, v7);
  if ( v8 > v3 )
  {
    if ( v8 )
    {
      v9 = -2147418113;
      goto LABEL_12;
    }
    goto LABEL_10;
  }
LABEL_13:
  v9 = CoCreateGuid(&pguid);
  if ( !v9 && v7 )
  {
    StringFromGUID2(&pguid, sz, 39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a1,
      L"%ws%ws%ws%ws",
      v7,
      L"wpd062674",
      sz,
      L".tmp");
  }
  if ( !*(_DWORD *)(*a1 - 16LL) )
    v9 = -2147467259;
LABEL_18:
  if ( v7 )
    operator delete(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006cf44  push    rbx
0x18006cf46  push    rsi
0x18006cf47  push    rdi
0x18006cf48  push    r14
0x18006cf4a  sub     rsp, 0B8h
0x18006cf51  mov     rax, cs:__security_cookie
0x18006cf58  xor     rax, rsp
0x18006cf5b  mov     [rsp+0D8h+var_38], rax
0x18006cf63  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006cf6a  xor     eax, eax
0x18006cf6c  lea     rdx, [rsp+0D8h+var_A8]
0x18006cf71  mov     r14, rcx
0x18006cf74  mov     [rsp+0D8h+var_A8], ax
0x18006cf79  movdqu  xmmword ptr [rsp+0D8h+pguid.Data1], xmm0
0x18006cf7f  lea     ecx, [rax+1]
0x18006cf82  call    cs:__imp_GetTempPath2W
0x18006cf88  mov     ebx, eax
0x18006cf8a  test    eax, eax
0x18006cf8c  jz      short loc_18006CFE3
0x18006cf8e  lea     esi, [rax+1]
0x18006cf91  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006cf98  mov     eax, 2
0x18006cf9d  mul     rsi
0x18006cfa0  cmovb   rax, rcx
0x18006cfa4  mov     rcx, rax; unsigned __int64
0x18006cfa7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006cfac  mov     rdi, rax
0x18006cfaf  test    rax, rax
0x18006cfb2  jz      short loc_18006CFDC
0x18006cfb4  lea     r8, [rsi+rsi]; Size
0x18006cfb8  xor     edx, edx; Val
0x18006cfba  mov     rcx, rax; void *
0x18006cfbd  call    memset_0
0x18006cfc2  mov     rdx, rdi
0x18006cfc5  mov     ecx, ebx
0x18006cfc7  call    cs:__imp_GetTempPath2W
0x18006cfcd  cmp     eax, ebx
0x18006cfcf  jbe     short loc_18006CFFE
0x18006cfd1  test    eax, eax
0x18006cfd3  jz      short loc_18006CFE5
0x18006cfd5  mov     ebx, 8000FFFFh
0x18006cfda  jmp     short loc_18006CFFA
0x18006cfdc  mov     ebx, 8007000Eh
0x18006cfe1  jmp     short loc_18006CFFA
0x18006cfe3  xor     edi, edi
0x18006cfe5  call    cs:__imp_GetLastError
0x18006cfeb  mov     ebx, eax
0x18006cfed  test    eax, eax
0x18006cfef  jle     short loc_18006CFFA
0x18006cff1  movzx   ebx, ax
0x18006cff4  or      ebx, 80070000h
0x18006cffa  test    ebx, ebx
0x18006cffc  js      short loc_18006D066
0x18006cffe  lea     rcx, [rsp+0D8h+pguid]; pguid
0x18006d003  call    cs:__imp_CoCreateGuid
0x18006d009  mov     ebx, eax
0x18006d00b  test    eax, eax
0x18006d00d  jnz     short loc_18006D057
0x18006d00f  test    rdi, rdi
0x18006d012  jz      short loc_18006D057
0x18006d014  lea     r8d, [rax+27h]; cchMax
0x18006d018  lea     rdx, [rsp+0D8h+sz]; lpsz
0x18006d01d  lea     rcx, [rsp+0D8h+pguid]; rguid
0x18006d022  call    cs:__imp_StringFromGUID2
0x18006d028  lea     rax, aTmp; ".tmp"
0x18006d02f  mov     r8, rdi
0x18006d032  mov     [rsp+0D8h+var_B0], rax
0x18006d037  lea     r9, aWpd062674; "wpd062674"
0x18006d03e  lea     rax, [rsp+0D8h+sz]
0x18006d043  mov     rcx, r14
0x18006d046  lea     rdx, aWsWsWsWs; "%ws%ws%ws%ws"
0x18006d04d  mov     [rsp+0D8h+var_B8], rax
0x18006d052  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18006d057  mov     rcx, [r14]
0x18006d05a  mov     eax, 80004005h
0x18006d05f  cmp     dword ptr [rcx-10h], 0
0x18006d063  cmovz   ebx, eax
0x18006d066  test    rdi, rdi
0x18006d069  jz      short loc_18006D073
0x18006d06b  mov     rcx, rdi; lpMem
0x18006d06e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006d073  mov     eax, ebx
0x18006d075  mov     rcx, [rsp+0D8h+var_38]
0x18006d07d  xor     rcx, rsp; StackCookie
0x18006d080  call    __security_check_cookie
0x18006d085  add     rsp, 0B8h
0x18006d08c  pop     r14
0x18006d08e  pop     rdi
0x18006d08f  pop     rsi
0x18006d090  pop     rbx
0x18006d091  retn
```
