# W3WP_HOST::CheckConfigFile(void)

- ea: `0x180003914`
- end: `0x180003ab3`
- name: `?CheckConfigFile@W3WP_HOST@@QEAAJXZ`
- size: `415`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800067f4`
- `0x18000c490`

## callees

- `0x180003914`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `msvcrt!_ultow` at `0x180003a13`
- `msvcrt!_ultow` at `0x180003a13`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003a51`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180003a51`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::CheckConfigFile(W3WP_HOST *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v8; // [rsp+48h] [rbp-9h] BYREF
  unsigned int Value; // [rsp+50h] [rbp-1h] BYREF
  __int64 v10; // [rsp+58h] [rbp+7h] BYREF
  __int128 v11; // [rsp+60h] [rbp+Fh] BYREF
  __int128 v12; // [rsp+70h] [rbp+1Fh] BYREF
  wchar_t Buffer[16]; // [rsp+80h] [rbp+2Fh] BYREF

  v10 = 0;
  v2 = *((_QWORD *)this + 24);
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v2 + 24LL))(
         v2,
         L"system.applicationHost/sites",
         L"MACHINE/WEBROOT/APPHOST",
         &v10,
         &v8,
         0);
  if ( v3 < 0 )
  {
    v4 = *((_QWORD *)this + 39);
    v5 = 0;
    v11 = 0;
    Value = 0;
    v12 = 0;
    *(_QWORD *)&v11 = *(_QWORD *)(v4 + 24);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 24LL))(v8, (char *)&v11 + 8);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 40LL))(v8, &v12);
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 32LL))(v8, &Value);
      v5 = Value;
    }
    else
    {
      *((_QWORD *)&v11 + 1) = L"Unknown Error";
      *(_QWORD *)&v12 = L"Unknown File";
    }
    _ultow(v5, Buffer, 10);
    *((_QWORD *)&v12 + 1) = Buffer;
    v6 = (unsigned __int16)v3;
    if ( (v3 & 0x1FFF0000) != 0x70000 )
      v6 = v3;
    EVENT_LOG::LogEvent((W3WP_HOST *)((char *)this + 80), 0xC0000903, 4u, (const unsigned __int16 **const)&v11, v6);
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003914  mov     r11, rsp
0x180003917  mov     [r11+10h], rbx
0x18000391b  mov     [r11+18h], rdi
0x18000391f  push    rbp
0x180003920  lea     rbp, [r11-5Fh]
0x180003924  sub     rsp, 0A0h
0x18000392b  mov     rax, cs:__security_cookie
0x180003932  xor     rax, rsp
0x180003935  mov     [rbp+57h+var_8], rax
0x180003939  mov     rdi, rcx
0x18000393c  mov     [rbp+57h+var_50], 0
0x180003944  mov     rcx, [rcx+0C0h]
0x18000394b  lea     rdx, [rbp+57h+var_60]
0x18000394f  mov     [rbp+57h+var_60], 0
0x180003957  lea     r9, [rbp+57h+var_50]
0x18000395b  mov     qword ptr [r11-80h], 0
0x180003963  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000396a  mov     [rsp+0A0h+var_80], rdx
0x18000396f  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x180003976  mov     rax, [rcx]
0x180003979  mov     rax, [rax+18h]
0x18000397d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003982  mov     ebx, eax
0x180003984  test    eax, eax
0x180003986  jns     loc_180003A5D
0x18000398c  mov     rcx, [rdi+138h]
0x180003993  xorps   xmm0, xmm0
0x180003996  xor     eax, eax
0x180003998  movups  [rbp+57h+var_48], xmm0
0x18000399c  mov     [rbp+57h+Value], eax
0x18000399f  movups  [rbp+57h+var_38], xmm0
0x1800039a3  mov     rdx, [rcx+18h]
0x1800039a7  mov     rcx, [rbp+57h+var_60]
0x1800039ab  mov     qword ptr [rbp+57h+var_48], rdx
0x1800039af  test    rcx, rcx
0x1800039b2  jz      short loc_1800039F1
0x1800039b4  mov     rax, [rcx]
0x1800039b7  lea     rdx, [rbp+57h+var_48+8]
0x1800039bb  mov     rax, [rax+18h]
0x1800039bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c4  mov     rcx, [rbp+57h+var_60]
0x1800039c8  lea     rdx, [rbp+57h+var_38]
0x1800039cc  mov     rax, [rcx]
0x1800039cf  mov     rax, [rax+28h]
0x1800039d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d8  mov     rcx, [rbp+57h+var_60]
0x1800039dc  lea     rdx, [rbp+57h+Value]
0x1800039e0  mov     rax, [rcx]
0x1800039e3  mov     rax, [rax+20h]
0x1800039e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ec  mov     eax, [rbp+57h+Value]
0x1800039ef  jmp     short loc_180003A07
0x1800039f1  lea     rcx, aUnknownError; "Unknown Error"
0x1800039f8  mov     qword ptr [rbp+57h+var_48+8], rcx
0x1800039fc  lea     rcx, aUnknownFile; "Unknown File"
0x180003a03  mov     qword ptr [rbp+57h+var_38], rcx
0x180003a07  mov     r8d, 0Ah; Radix
0x180003a0d  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180003a11  mov     ecx, eax; Value
0x180003a13  call    cs:__imp__ultow
0x180003a1a  nop     dword ptr [rax+rax+00h]
0x180003a1f  lea     rax, [rbp+57h+Buffer]
0x180003a23  mov     qword ptr [rbp+57h+var_38+8], rax
0x180003a27  mov     eax, ebx
0x180003a29  and     eax, 1FFF0000h
0x180003a2e  cmp     eax, 70000h
0x180003a33  movzx   eax, bx
0x180003a36  jz      short loc_180003A3A
0x180003a38  mov     eax, ebx
0x180003a3a  mov     r8d, 4
0x180003a40  mov     dword ptr [rsp+0A0h+var_80], eax
0x180003a44  lea     rcx, [rdi+50h]
0x180003a48  mov     edx, 0C0000903h
0x180003a4d  lea     r9, [rbp+57h+var_48]
0x180003a51  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003a58  nop     dword ptr [rax+rax+00h]
0x180003a5d  mov     rcx, [rbp+57h+var_60]
0x180003a61  test    rcx, rcx
0x180003a64  jz      short loc_180003A7A
0x180003a66  mov     rax, [rcx]
0x180003a69  mov     rax, [rax+10h]
0x180003a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a72  mov     [rbp+57h+var_60], 0
0x180003a7a  mov     rcx, [rbp+57h+var_50]
0x180003a7e  test    rcx, rcx
0x180003a81  jz      short loc_180003A8F
0x180003a83  mov     rax, [rcx]
0x180003a86  mov     rax, [rax+10h]
0x180003a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8f  mov     eax, ebx
0x180003a91  mov     rcx, [rbp+57h+var_8]
0x180003a95  xor     rcx, rsp; StackCookie
0x180003a98  call    __security_check_cookie
0x180003a9d  lea     r11, [rsp+0A0h+var_s0]
0x180003aa5  mov     rbx, [r11+18h]
0x180003aa9  mov     rdi, [r11+20h]
0x180003aad  mov     rsp, r11
0x180003ab0  pop     rbp
0x180003ab1  retn
```
