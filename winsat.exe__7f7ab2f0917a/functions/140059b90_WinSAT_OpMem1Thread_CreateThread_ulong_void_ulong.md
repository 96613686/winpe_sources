# WinSAT::OpMem1Thread::CreateThread(ulong,void * &,ulong)

- ea: `0x140059b90`
- end: `0x140059d3a`
- name: `?CreateThread@OpMem1Thread@WinSAT@@QEAAKKAEAPEAXK@Z`
- size: `426`
- prototype: `unsigned int __fastcall(WinSAT::OpMem1Thread *__hidden this, DWORD_PTR dwThreadAffinityMask, void **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005f020`

## callees

- `0x140004348`
- `0x140007f14`
- `0x140017af0`
- `0x14004fe00`
- `0x1400530a8`
- `0x140059b90`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140059c19`
- `KERNEL32!GetLastError` at `0x140059c62`
- `KERNEL32!GetLastError` at `0x140059c9e`
- `KERNEL32!GetLastError` at `0x140059c19`
- `KERNEL32!GetLastError` at `0x140059c62`
- `KERNEL32!GetLastError` at `0x140059c9e`
- `KERNEL32!SetThreadIdealProcessor` at `0x140059c57`
- `KERNEL32!SetThreadIdealProcessor` at `0x140059c57`
- `KERNEL32!SetThreadAffinityMask` at `0x140059c0e`
- `KERNEL32!SetThreadAffinityMask` at `0x140059c0e`
- `msvcrt!_beginthreadex` at `0x140059bf2`
- `msvcrt!_beginthreadex` at `0x140059bf2`

## pseudocode

```c
__int64 __fastcall WinSAT::OpMem1Thread::CreateThread(
        WinSAT::OpMem1Thread *this,
        DWORD_PTR dwThreadAffinityMask,
        void **a3,
        DWORD a4)
{
  unsigned int v4; // edi
  char *v8; // rax
  void *v9; // rbx
  DWORD v10; // eax
  unsigned __int16 v11; // r9
  __int64 v12; // rdx
  int v13; // r8d
  DWORD v14; // eax
  DWORD LastError; // eax
  __int64 v17; // rbx
  const unsigned __int16 *v18; // rax
  __int64 *v19; // rax
  __int64 *v20; // rax
  __int64 *v21; // rax
  unsigned int ThrdAddr[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v24; // [rsp+240h] [rbp+140h]
  char v25; // [rsp+244h] [rbp+144h]
  __int64 v26; // [rsp+248h] [rbp+148h]

  v4 = dwThreadAffinityMask;
  *((_DWORD *)this + 68) = dwThreadAffinityMask;
  ThrdAddr[0] = 0;
  v8 = (char *)_beginthreadex(0, 0, WinSAT::OpMem1Thread::DoOperationThreadEntryPoint, this, 4u, ThrdAddr);
  v9 = v8;
  if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v25 = 1;
    v24 = LastError;
    v26 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v12 = 1296;
    v13 = 636;
  }
  else if ( SetThreadAffinityMask(v8, v4) )
  {
    if ( SetThreadIdealProcessor(v9, a4) != -1 )
    {
      *a3 = v9;
      return 0;
    }
    v14 = GetLastError();
    v25 = 1;
    v24 = v14;
    v26 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v12 = 1310;
    v13 = 638;
  }
  else
  {
    v10 = GetLastError();
    v25 = 1;
    v24 = v10;
    v26 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v12 = 1303;
    v13 = 637;
  }
  v17 = *((_QWORD *)this + 17);
  v18 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v12, v13, v11);
  v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v17 + 240), (__int64)v18);
  v20 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v19, 10);
  v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, (__int64)Buffer);
  std::endl(v21);
  return v24;
}

```

## disassembly

```asm
0x140059b90  push    rbp
0x140059b92  push    rbx
0x140059b93  push    rsi
0x140059b94  push    rdi
0x140059b95  push    r14
0x140059b97  push    r15
0x140059b99  lea     rbp, [rsp-168h]
0x140059ba1  sub     rsp, 268h
0x140059ba8  mov     rax, cs:__security_cookie
0x140059baf  xor     rax, rsp
0x140059bb2  mov     [rbp+190h+var_40], rax
0x140059bb9  mov     edi, edx
0x140059bbb  lea     rax, [rsp+290h+var_260]
0x140059bc0  mov     r15d, r9d
0x140059bc3  mov     [rcx+110h], edi
0x140059bc9  mov     r14, r8
0x140059bcc  mov     [rsp+290h+ThrdAddr], rax; ThrdAddr
0x140059bd1  mov     rsi, rcx
0x140059bd4  mov     [rsp+290h+var_260], 0
0x140059bdc  mov     r9, rcx; ArgList
0x140059bdf  mov     [rsp+290h+InitFlag], 4; InitFlag
0x140059be7  xor     ecx, ecx; Security
0x140059be9  lea     r8, ?DoOperationThreadEntryPoint@OpMem1Thread@WinSAT@@SAIPEAX@Z; StartAddress
0x140059bf0  xor     edx, edx; StackSize
0x140059bf2  call    cs:__imp__beginthreadex
0x140059bf8  mov     rbx, rax
0x140059bfb  lea     rcx, [rax-1]
0x140059bff  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140059c03  ja      loc_140059C9E
0x140059c09  mov     edx, edi; dwThreadAffinityMask
0x140059c0b  mov     rcx, rax; hThread
0x140059c0e  call    cs:__imp_SetThreadAffinityMask
0x140059c14  test    rax, rax
0x140059c17  jnz     short loc_140059C51
0x140059c19  call    cs:__imp_GetLastError
0x140059c1f  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x140059c24  mov     [rbp+190h+var_4C], 1
0x140059c2b  mov     [rbp+190h+var_50], eax
0x140059c31  mov     [rbp+190h+var_48], 0
0x140059c3c  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140059c41  mov     edx, 517h
0x140059c46  mov     r8d, 27Dh
0x140059c4c  jmp     loc_140059CD1
0x140059c51  mov     edx, r15d; dwIdealProcessor
0x140059c54  mov     rcx, rbx; hThread
0x140059c57  call    cs:__imp_SetThreadIdealProcessor
0x140059c5d  cmp     eax, 0FFFFFFFFh
0x140059c60  jnz     short loc_140059C97
0x140059c62  call    cs:__imp_GetLastError
0x140059c68  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x140059c6d  mov     [rbp+190h+var_4C], 1
0x140059c74  mov     [rbp+190h+var_50], eax
0x140059c7a  mov     [rbp+190h+var_48], 0
0x140059c85  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140059c8a  mov     edx, 51Eh
0x140059c8f  mov     r8d, 27Eh
0x140059c95  jmp     short loc_140059CD1
0x140059c97  mov     [r14], rbx
0x140059c9a  xor     eax, eax
0x140059c9c  jmp     short loc_140059D1B
0x140059c9e  call    cs:__imp_GetLastError
0x140059ca4  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x140059ca9  mov     [rbp+190h+var_4C], 1
0x140059cb0  mov     [rbp+190h+var_50], eax
0x140059cb6  mov     [rbp+190h+var_48], 0
0x140059cc1  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140059cc6  mov     edx, 510h; char *
0x140059ccb  mov     r8d, 27Ch; int
0x140059cd1  mov     rbx, [rsi+88h]
0x140059cd8  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x140059cdf  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140059ce4  mov     rdx, rax
0x140059ce7  lea     rcx, [rbx+0F0h]
0x140059cee  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140059cf3  mov     edx, 0Ah
0x140059cf8  mov     rcx, rax
0x140059cfb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140059d00  lea     rdx, [rsp+290h+Buffer]
0x140059d05  mov     rcx, rax
0x140059d08  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140059d0d  mov     rcx, rax
0x140059d10  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140059d15  mov     eax, [rbp+190h+var_50]
0x140059d1b  mov     rcx, [rbp+190h+var_40]
0x140059d22  xor     rcx, rsp; StackCookie
0x140059d25  call    __security_check_cookie
0x140059d2a  add     rsp, 268h
0x140059d31  pop     r15
0x140059d33  pop     r14
0x140059d35  pop     rdi
0x140059d36  pop     rsi
0x140059d37  pop     rbx
0x140059d38  pop     rbp
0x140059d39  retn
```
