# WinHttpConnectInternal(void *,ushort const *,ushort,ulong,ulong)

- ea: `0x1800237b4`
- end: `0x180023bc5`
- name: `?WinHttpConnectInternal@@YAPEAXPEAXPEBGGKK@Z`
- size: `1041`
- prototype: `void *__usercall@<rax>(HANDLE_OBJECT *this@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x180040010`
- `0x180046ee0`

## callees

- `0x180004720`
- `0x1800065a0`
- `0x180012ad0`
- `0x180013680`
- `0x1800237b4`
- `0x1800241a0`
- `0x1800254ec`
- `0x180039120`
- `0x18003b0e0`
- `0x18003bc60`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800d368c`
- `0x1800db6b0`
- `0x1800db758`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800239e7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800239e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800238ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800238ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023982`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002398a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002398a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023a3e`

## pseudocode

```c
HINTERNET *__fastcall WinHttpConnectInternal(
        HANDLE_OBJECT *this,
        const unsigned __int16 *a2,
        __int16 a3,
        __int64 a4,
        unsigned int a5)
{
  HANDLE_OBJECT *v7; // rdi
  HINTERNET *v8; // r14
  unsigned int v9; // eax
  DWORD IsValid; // ebx
  char v11; // cl
  struct INTERNET_HANDLE_BASE *v12; // rbx
  HINTERNET *v13; // rax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  unsigned int v17; // edi
  signed __int32 v18; // esi
  DWORD CurrentProcessId; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v21; // r9d
  int v22; // edi
  void *v23; // rcx
  int v25; // edx
  __int64 v26; // [rsp+20h] [rbp-78h]
  struct INTERNET_HANDLE_BASE *v27; // [rsp+40h] [rbp-58h] BYREF
  HINTERNET hInternet; // [rsp+48h] [rbp-50h] BYREF

  v7 = this;
  v27 = 0;
  v8 = 0;
  if ( !GlobalDataInitialized )
  {
    IsValid = 12172;
    goto LABEL_38;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)this, (__int64)&v27);
  if ( !v7 || (unsigned int)HANDLE_OBJECT::IsValid(v7, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) == 0 )
    {
LABEL_40:
      v7 = 0;
      IsValid = 6;
      goto LABEL_10;
    }
    v25 = 11;
LABEL_45:
    WPP_SF_qq(529, v25, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v7, (__int64)v7);
    goto LABEL_40;
  }
  v9 = HANDLE_OBJECT::Reference(v7);
  IsValid = v9;
  v11 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, v9, v26);
    v11 = BYTE2(xmmword_180107A50);
  }
  if ( IsValid && IsValid != 6 )
  {
    if ( (v11 & 2) == 0 )
      goto LABEL_40;
    v25 = 13;
    goto LABEL_45;
  }
LABEL_10:
  v27 = v7;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v26);
  if ( IsValid )
    goto LABEL_36;
  IsValid = HANDLE_OBJECT::IsValid(v27, 1952804425);
  if ( IsValid )
    goto LABEL_36;
  if ( (a5 & 0xFFFFFFFE) != 0 || !a2 || !*a2 )
  {
    IsValid = 87;
    goto LABEL_36;
  }
  v12 = v27;
  v13 = (HINTERNET *)HeapAlloc(g_hWxProcessHeap, 0, 0x1B0u);
  v8 = v13;
  if ( !v13 )
  {
    v8 = 0;
LABEL_52:
    IsValid = 8;
    goto LABEL_36;
  }
  memset_0(v13, 0, 0x1B0u);
  INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE((INTERNET_HANDLE_BASE *)v8, v12);
  *v8 = &INTERNET_CONNECT_HANDLE_OBJECT::`vftable';
  v8[47] = 0;
  v8[48] = 0;
  v8[49] = 0;
  v8[50] = 0;
  v8[53] = 0;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_qqSdD(v15, v14, v16, (_DWORD)v12, 0, (__int64)a2, a3, a5);
  if ( !*((_DWORD *)v8 + 18) )
    *((_DWORD *)v8 + 18) = INTERNET_CONNECT_HANDLE_OBJECT::SetHostName((INTERNET_CONNECT_HANDLE_OBJECT *)v8, a2);
  *((_WORD *)v8 + 206) = a3;
  *((_DWORD *)v8 + 104) = 1;
  *((_DWORD *)v8 + 10) = 1852785480;
  if ( v8 != (HINTERNET *)-184LL )
  {
    v17 = *((_DWORD *)v8 + 8);
    v18 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    CurrentProcessId = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)v8 + 46) = v17;
    *((_DWORD *)v8 + 48) = CurrentProcessId ^ (CurrentThreadId << 16);
    *((_DWORD *)v8 + 47) = v18;
    *((_DWORD *)v8 + 49) = (_DWORD)v8;
  }
  *((_DWORD *)v8 + 105) = 0;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 13, WPP_b99d9a08caaa3540d9ac478cfb7595e4_Traceguids, *((unsigned int *)v8 + 18), v26);
  if ( !v8 )
    goto LABEL_52;
  HANDLE_OBJECT::Reference((HANDLE_OBJECT *)v8);
  v22 = *((_DWORD *)v8 + 18);
  IsValid = 12017;
  if ( v22 )
  {
    v23 = v8[11];
    *((_DWORD *)v8 + 12) = 1;
    if ( v23 )
      SetEvent(v23);
    v8[21] = 0;
    v8[22] = 0;
    HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v8);
    HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v8);
  }
  else
  {
    if ( (a5 & 1) != 0 )
      goto LABEL_32;
    hInternet = v8[4];
    INTERNET_HANDLE_BASE::IndicateStatus((INTERNET_HANDLE_BASE *)v8, 0x400u, &hInternet, v21);
    if ( !(unsigned int)HANDLE_OBJECT::IsInvalidated((HANDLE_OBJECT *)v8) )
      goto LABEL_32;
    WinHttpCloseHandle(hInternet);
    HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v8);
    v22 = 12017;
  }
  v8 = 0;
LABEL_32:
  if ( v22 )
  {
LABEL_35:
    IsValid = v22;
    goto LABEL_36;
  }
  if ( !(unsigned int)HANDLE_OBJECT::Dereference((HANDLE_OBJECT *)v8) )
  {
    v8 = (HINTERNET *)v8[4];
    goto LABEL_35;
  }
  v8 = 0;
LABEL_36:
  if ( v27 )
  {
    DereferenceObject(v27);
    v27 = 0;
  }
LABEL_38:
  SetLastError(IsValid);
  return v8;
}

```

## disassembly

```asm
0x1800237b4  mov     [rsp+arg_10], rbx
0x1800237b9  push    rbp
0x1800237ba  push    rsi
0x1800237bb  push    rdi
0x1800237bc  push    r12
0x1800237be  push    r13
0x1800237c0  push    r14
0x1800237c2  push    r15
0x1800237c4  sub     rsp, 60h
0x1800237c8  mov     rax, cs:__security_cookie
0x1800237cf  xor     rax, rsp
0x1800237d2  mov     [rsp+98h+var_48], rax
0x1800237d7  xor     r12d, r12d
0x1800237da  movzx   r15d, r8w
0x1800237de  cmp     cs:?GlobalDataInitialized@@3HA, r12d; int GlobalDataInitialized
0x1800237e5  mov     rsi, rdx
0x1800237e8  mov     rdi, rcx
0x1800237eb  mov     [rsp+98h+var_58], r12
0x1800237f0  mov     r14d, r12d
0x1800237f3  jz      loc_180023B67
0x1800237f9  mov     bpl, 2
0x1800237fc  lea     r13, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x180023803  test    byte ptr cs:xmmword_180107A60+2, bpl
0x18002380a  jnz     loc_180023AF1
0x180023810  test    rdi, rdi
0x180023813  jz      loc_180023A6C
0x180023819  mov     edx, 646C6957h
0x18002381e  mov     rcx, rdi
0x180023821  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180023826  test    eax, eax
0x180023828  jnz     loc_180023A6C
0x18002382e  mov     rcx, rdi; this
0x180023831  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x180023836  mov     ebx, eax
0x180023838  mov     cl, byte ptr cs:xmmword_180107A50+2
0x18002383e  test    bpl, cl
0x180023841  jnz     loc_180023B34
0x180023847  mov     eax, ebx
0x180023849  test    ebx, ebx
0x18002384b  jz      short loc_18002385F
0x18002384d  sub     eax, 5
0x180023850  jz      loc_180023B54
0x180023856  cmp     eax, 1
0x180023859  jnz     loc_180023B54
0x18002385f  mov     [rsp+98h+var_58], rdi
0x180023864  test    byte ptr cs:xmmword_180107A60+2, bpl
0x18002386b  jnz     loc_180023B1A
0x180023871  test    ebx, ebx
0x180023873  jnz     loc_180023A28
0x180023879  mov     rcx, [rsp+98h+var_58]
0x18002387e  mov     edx, 74656E49h
0x180023883  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180023888  mov     ebx, eax
0x18002388a  test    eax, eax
0x18002388c  jnz     loc_180023A28
0x180023892  mov     ebp, [rsp+98h+arg_20]
0x180023899  test    ebp, 0FFFFFFFEh
0x18002389f  jnz     loc_180023AE7
0x1800238a5  test    rsi, rsi
0x1800238a8  jz      loc_180023AE7
0x1800238ae  cmp     [rsi], r12w
0x1800238b2  jz      loc_180023AE7
0x1800238b8  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800238bf  mov     edi, 1B0h
0x1800238c4  mov     rbx, [rsp+98h+var_58]
0x1800238c9  mov     r8d, edi; dwBytes
0x1800238cc  xor     edx, edx; dwFlags
0x1800238ce  call    cs:__imp_HeapAlloc
0x1800238d4  mov     r14, rax
0x1800238d7  test    rax, rax
0x1800238da  jz      loc_180023BB8
0x1800238e0  mov     r8d, edi; Size
0x1800238e3  xor     edx, edx; Val
0x1800238e5  mov     rcx, rax; void *
0x1800238e8  call    memset_0
0x1800238ed  mov     rdx, rbx; struct INTERNET_HANDLE_BASE *
0x1800238f0  mov     rcx, r14; this
0x1800238f3  call    ??0INTERNET_HANDLE_BASE@@QEAA@PEAV0@@Z; INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(INTERNET_HANDLE_BASE *)
0x1800238f8  lea     rax, ??_7INTERNET_CONNECT_HANDLE_OBJECT@@6B@; const INTERNET_CONNECT_HANDLE_OBJECT::`vftable'
0x1800238ff  mov     [r14], rax
0x180023902  mov     [r14+178h], r12
0x180023909  mov     [r14+180h], r12
0x180023910  mov     [r14+188h], r12
0x180023917  mov     [r14+190h], r12
0x18002391e  mov     [r14+1A8h], r12
0x180023925  mov     r13d, 1
0x18002392b  test    byte ptr cs:xmmword_180107A60+1, r13b
0x180023932  jnz     loc_180023B71
0x180023938  cmp     [r14+48h], r12d
0x18002393c  jnz     short loc_18002394D
0x18002393e  mov     rdx, rsi; unsigned __int16 *
0x180023941  mov     rcx, r14; this
0x180023944  call    ?SetHostName@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAKPEBG@Z; INTERNET_CONNECT_HANDLE_OBJECT::SetHostName(ushort const *)
0x180023949  mov     [r14+48h], eax
0x18002394d  mov     [r14+19Ch], r15w
0x180023955  lea     r15, [r14+0B8h]
0x18002395c  mov     [r14+1A0h], r13d
0x180023963  mov     dword ptr [r14+28h], 6E6F4348h
0x18002396b  test    r15, r15
0x18002396e  jz      short loc_1800239A4
0x180023970  mov     edi, [r14+20h]
0x180023974  mov     esi, r13d
0x180023977  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18002397f  add     esi, r13d
0x180023982  call    cs:__imp_GetCurrentProcessId
0x180023988  mov     ebx, eax
0x18002398a  call    cs:__imp_GetCurrentThreadId
0x180023990  shl     eax, 10h
0x180023993  xor     eax, ebx
0x180023995  mov     [r15], edi
0x180023998  mov     [r15+8], eax
0x18002399c  mov     [r15+4], esi
0x1800239a0  mov     [r15+0Ch], r14d
0x1800239a4  mov     [r14+1A4h], r12d
0x1800239ab  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800239b2  jnz     loc_180023B91
0x1800239b8  test    r14, r14
0x1800239bb  jz      loc_180023BBB
0x1800239c1  mov     rcx, r14; this
0x1800239c4  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x1800239c9  mov     edi, [r14+48h]
0x1800239cd  mov     ebx, 2EF1h
0x1800239d2  test    edi, edi
0x1800239d4  jz      loc_180023A82
0x1800239da  mov     rcx, [r14+58h]; hEvent
0x1800239de  mov     [r14+30h], r13d
0x1800239e2  test    rcx, rcx
0x1800239e5  jz      short loc_1800239ED
0x1800239e7  call    cs:__imp_SetEvent
0x1800239ed  mov     rcx, r14; this
0x1800239f0  mov     [r14+0A8h], r12
0x1800239f7  mov     [r14+0B0h], r12
0x1800239fe  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180023a03  mov     rcx, r14; this
0x180023a06  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180023a0b  mov     r14, r12
0x180023a0e  test    edi, edi
0x180023a10  jnz     short loc_180023A26
0x180023a12  mov     rcx, r14; this
0x180023a15  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180023a1a  test    eax, eax
0x180023a1c  jnz     loc_180023BB0
0x180023a22  mov     r14, [r14+20h]
0x180023a26  mov     ebx, edi
0x180023a28  mov     rcx, [rsp+98h+var_58]; void *
0x180023a2d  test    rcx, rcx
0x180023a30  jz      short loc_180023A3C
0x180023a32  call    ?DereferenceObject@@YAKPEAX@Z; DereferenceObject(void *)
0x180023a37  mov     [rsp+98h+var_58], r12
0x180023a3c  mov     ecx, ebx; dwErrCode
0x180023a3e  call    cs:__imp_SetLastError
0x180023a44  mov     rax, r14
0x180023a47  mov     rcx, [rsp+98h+var_48]
0x180023a4c  xor     rcx, rsp; StackCookie
0x180023a4f  call    __security_check_cookie
0x180023a54  mov     rbx, [rsp+98h+arg_10]
0x180023a5c  add     rsp, 60h
0x180023a60  pop     r15
0x180023a62  pop     r14
0x180023a64  pop     r13
0x180023a66  pop     r12
0x180023a68  pop     rdi
0x180023a69  pop     rsi
0x180023a6a  pop     rbp
0x180023a6b  retn
0x180023a6c  test    byte ptr cs:xmmword_180107A50+2, bpl
0x180023a73  jnz     short loc_180023ACB
0x180023a75  mov     rdi, r12
0x180023a78  mov     ebx, 6
0x180023a7d  jmp     loc_18002385F
0x180023a82  test    r13b, bpl
0x180023a85  jnz     short loc_180023A0E
0x180023a87  mov     rax, [r14+20h]
0x180023a8b  lea     r8, [rsp+98h+hInternet]; void *
0x180023a90  mov     edx, 400h; unsigned int
0x180023a95  mov     [rsp+98h+hInternet], rax
0x180023a9a  mov     rcx, r14; this
0x180023a9d  call    ?IndicateStatus@INTERNET_HANDLE_BASE@@QEAAXKPEAXK@Z; INTERNET_HANDLE_BASE::IndicateStatus(ulong,void *,ulong)
0x180023aa2  mov     rcx, r14; this
0x180023aa5  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x180023aaa  test    eax, eax
0x180023aac  jz      loc_180023A0E
0x180023ab2  mov     rcx, [rsp+98h+hInternet]; hInternet
0x180023ab7  call    WinHttpCloseHandle
0x180023abc  mov     rcx, r14; this
0x180023abf  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180023ac4  mov     edi, ebx
0x180023ac6  jmp     loc_180023A0B
0x180023acb  mov     edx, 0Bh
0x180023ad0  mov     r9, rdi
0x180023ad3  mov     [rsp+98h+var_78], rdi
0x180023ad8  mov     r8, r13
0x180023adb  mov     ecx, 211h
0x180023ae0  call    WPP_SF_qq
0x180023ae5  jmp     short loc_180023A75
0x180023ae7  mov     ebx, 57h ; 'W'
0x180023aec  jmp     loc_180023A28
0x180023af1  lea     rax, [rsp+98h+var_58]
0x180023af6  mov     dword ptr [rsp+98h+var_70], r12d
0x180023afb  mov     edx, 0Ah
0x180023b00  mov     [rsp+98h+var_78], rax
0x180023b05  mov     ecx, 411h
0x180023b0a  mov     r9, rdi
0x180023b0d  mov     r8, r13
0x180023b10  call    WPP_SF_qqD
0x180023b15  jmp     loc_180023810
0x180023b1a  mov     edx, 0Eh
0x180023b1f  mov     ecx, 411h
0x180023b24  mov     r9d, ebx
0x180023b27  mov     r8, r13
0x180023b2a  call    WPP_SF_d
0x180023b2f  jmp     loc_180023871
0x180023b34  mov     edx, 0Ch
0x180023b39  mov     ecx, 211h
0x180023b3e  mov     r9d, ebx
0x180023b41  mov     r8, r13
0x180023b44  call    WPP_SF_d
0x180023b49  mov     cl, byte ptr cs:xmmword_180107A50+2
0x180023b4f  jmp     loc_180023847
0x180023b54  test    bpl, cl
0x180023b57  jz      loc_180023A75
0x180023b5d  mov     edx, 0Dh
0x180023b62  jmp     loc_180023AD0
0x180023b67  mov     ebx, 2F8Ch
0x180023b6c  jmp     loc_180023A3C
0x180023b71  mov     [rsp+98h+var_60], ebp
0x180023b75  mov     r9, rbx
0x180023b78  mov     [rsp+98h+var_68], r15d
0x180023b7d  mov     [rsp+98h+var_70], rsi
0x180023b82  mov     [rsp+98h+var_78], r12
0x180023b87  call    WPP_SF_qqSdD
0x180023b8c  jmp     loc_180023938
0x180023b91  mov     r9d, [r14+48h]
0x180023b95  lea     r8, WPP_b99d9a08caaa3540d9ac478cfb7595e4_Traceguids
0x180023b9c  mov     edx, 0Dh
0x180023ba1  mov     ecx, 411h
0x180023ba6  call    WPP_SF_d
0x180023bab  jmp     loc_1800239B8
0x180023bb0  mov     r14, r12
0x180023bb3  jmp     loc_180023A28
0x180023bb8  mov     r14, r12
0x180023bbb  mov     ebx, 8
0x180023bc0  jmp     loc_180023A28
```
