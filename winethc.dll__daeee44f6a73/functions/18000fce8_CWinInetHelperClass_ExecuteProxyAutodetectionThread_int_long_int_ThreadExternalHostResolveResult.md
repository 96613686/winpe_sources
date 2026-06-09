# CWinInetHelperClass::ExecuteProxyAutodetectionThread(int,long *,int *,ThreadExternalHostResolveResult *)

- ea: `0x18000fce8`
- end: `0x180010005`
- name: `?ExecuteProxyAutodetectionThread@CWinInetHelperClass@@AEAAJHPEAJPEAHPEAW4ThreadExternalHostResolveResult@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, int, int *, int *, enum ThreadExternalHostResolveResult *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180009528`
- `0x180009ae4`
- `0x18000d160`

## callees

- `0x18000fce8`
- `0x18001000c`
- `0x180010174`
- `0x180014010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000fd98`
- `KERNEL32!CloseHandle` at `0x18000ff67`
- `KERNEL32!CloseHandle` at `0x18000fd98`
- `KERNEL32!CloseHandle` at `0x18000ff67`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fd46`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ff09`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ff32`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000fd46`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ff09`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000ff32`
- `KERNEL32!CreateThread` at `0x18000fec4`
- `KERNEL32!CreateThread` at `0x18000fec4`

## string_xrefs

- `0x18000ffd8`: `We've reached the maximum number of proxy auto-detection threads allowed, proceeding as if we timed out.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::ExecuteProxyAutodetectionThread(
        CWinInetHelperClass *this,
        int a2,
        int *a3,
        int *a4,
        enum ThreadExternalHostResolveResult *a5)
{
  unsigned int v9; // r15d
  unsigned __int64 v10; // r14
  void *v11; // rcx
  unsigned __int64 v12; // rdi
  void *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdi
  _DWORD *v16; // r15
  void *v17; // rcx
  __int64 v18; // rcx

  if ( !a3 && !a4 )
    return 2147942487LL;
  v9 = 0;
  v10 = (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 4448;
  v11 = *(void **)((char *)this + v10);
  if ( v11 )
  {
    if ( WaitForSingleObjectEx(v11, 0x1388u, 0) == 258 )
    {
      *a3 = -2147024638;
      v12 = (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 264;
    }
    else
    {
      v13 = *(void **)((char *)this + v10);
      v12 = (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 264;
      *a3 = *(_DWORD *)((char *)this + v12 + 4484);
      CloseHandle(v13);
      *(_QWORD *)((char *)this + v10) = 0;
      v14 = -(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( *(int *)((char *)&qword_18001BDC8[1] + v14 + 4) >= 0 )
        _InterlockedDecrement((volatile signed __int32 *)((char *)&qword_18001BDC8[1] + v14 + 4));
    }
    if ( a5 )
      *(_DWORD *)a5 = *(_DWORD *)((char *)this + v12 + 4512);
  }
  else
  {
    v15 = -(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( *(int *)((char *)&qword_18001BDC8[1] + v15 + 4) >= 2 )
    {
      v18 = *((_QWORD *)this + 602);
      *a3 = -2147024638;
      if ( v18 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v18 + 24LL))(
          v18,
          2,
          0,
          L"WinInetHelperClass",
          L"We've reached the maximum number of proxy auto-detection threads allowed, proceeding as if we timed out.");
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)((char *)&qword_18001BDC8[1] + v15 + 4));
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4720) = (char *)this + 1152;
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4760) = (char *)this + 4896;
      *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4768) = (char *)this + 4920;
      if ( a5 )
      {
        v16 = (_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4776);
      }
      else
      {
        v16 = (_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4776);
        *v16 = 4;
      }
      NetTraceMarkContextActivityStart((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4720, 2u);
      *(_QWORD *)((char *)this + v10) = CreateThread(
                                          0,
                                          0,
                                          ProxyAutodetectionThread,
                                          (char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4720,
                                          0,
                                          0);
      NetTraceMarkContextActivityStop((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4720, 2u);
      if ( *(_QWORD *)((char *)this + v10) )
      {
        *((_DWORD *)this + 791) = 1;
        if ( WaitForSingleObjectEx(*(HANDLE *)((char *)this + v10), 0x8CA0u, 0) == 258
          && (*v16 != 2 || WaitForSingleObjectEx(*(HANDLE *)((char *)this + v10), 0x1388u, 0) == 258) )
        {
          *a3 = -2147024638;
        }
        else
        {
          v17 = *(void **)((char *)this + v10);
          *a3 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4748);
          CloseHandle(v17);
          *(_QWORD *)((char *)this + v10) = 0;
          if ( *(int *)((char *)&qword_18001BDC8[1] + v15 + 4) >= 0 )
            _InterlockedDecrement((volatile signed __int32 *)((char *)&qword_18001BDC8[1] + v15 + 4));
          *a4 = *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFA8uLL) + 4792);
        }
        if ( a5 )
          *(_DWORD *)a5 = *v16;
        return 0;
      }
      else
      {
        return (unsigned int)-2147023842;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000fce8  mov     [rsp+arg_18], r9
0x18000fced  push    rbx
0x18000fcee  push    rbp
0x18000fcef  push    rsi
0x18000fcf0  push    rdi
0x18000fcf1  push    r12
0x18000fcf3  push    r13
0x18000fcf5  push    r14
0x18000fcf7  push    r15
0x18000fcf9  sub     rsp, 38h
0x18000fcfd  mov     rax, r9
0x18000fd00  mov     r12, r8
0x18000fd03  mov     esi, edx
0x18000fd05  mov     rbx, rcx
0x18000fd08  test    r8, r8
0x18000fd0b  jnz     short loc_18000FD1C
0x18000fd0d  test    rax, rax
0x18000fd10  jnz     short loc_18000FD1C
0x18000fd12  mov     eax, 80070057h
0x18000fd17  jmp     loc_18000FFF3
0x18000fd1c  xor     r15d, r15d
0x18000fd1f  mov     eax, esi
0x18000fd21  neg     eax
0x18000fd23  sbb     r14, r14
0x18000fd26  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000fd2a  add     r14, 1160h
0x18000fd31  mov     rcx, [r14+rcx]; hHandle
0x18000fd35  test    rcx, rcx
0x18000fd38  jz      loc_18000FDE3
0x18000fd3e  xor     r8d, r8d; bAlertable
0x18000fd41  mov     edx, 1388h; dwMilliseconds
0x18000fd46  call    cs:__imp_WaitForSingleObjectEx
0x18000fd4d  nop     dword ptr [rax+rax+00h]
0x18000fd52  mov     r13d, 102h
0x18000fd58  cmp     eax, r13d
0x18000fd5b  jnz     short loc_18000FD77
0x18000fd5d  neg     esi
0x18000fd5f  mov     dword ptr [r12], 80070102h
0x18000fd67  sbb     rdi, rdi
0x18000fd6a  and     rdi, 0FFFFFFFFFFFFFFA8h
0x18000fd6e  add     rdi, 108h
0x18000fd75  jmp     short loc_18000FDC4
0x18000fd77  mov     rcx, [r14+rbx]; hObject
0x18000fd7b  mov     eax, esi
0x18000fd7d  neg     eax
0x18000fd7f  sbb     rdi, rdi
0x18000fd82  and     rdi, 0FFFFFFFFFFFFFFA8h
0x18000fd86  add     rdi, 108h
0x18000fd8d  mov     eax, [rdi+rbx+1184h]
0x18000fd94  mov     [r12], eax
0x18000fd98  call    cs:__imp_CloseHandle
0x18000fd9f  nop     dword ptr [rax+rax+00h]
0x18000fda4  neg     esi
0x18000fda6  mov     [r14+rbx], r15
0x18000fdaa  lea     rbp, qword_18001BDC8
0x18000fdb1  sbb     rax, rax
0x18000fdb4  and     rax, 0FFFFFFFFFFFFFFFCh
0x18000fdb8  cmp     [rax+rbp+0Ch], r15d
0x18000fdbd  jl      short loc_18000FDC4
0x18000fdbf  lock dec dword ptr [rax+rbp+0Ch]
0x18000fdc4  mov     rcx, [rsp+78h+arg_20]
0x18000fdcc  test    rcx, rcx
0x18000fdcf  jz      loc_18000FFF0
0x18000fdd5  mov     eax, [rdi+rbx+11A0h]
0x18000fddc  mov     [rcx], eax
0x18000fdde  jmp     loc_18000FFF0
0x18000fde3  mov     eax, esi
0x18000fde5  lea     rbp, qword_18001BDC8
0x18000fdec  neg     eax
0x18000fdee  mov     r10d, 2
0x18000fdf4  sbb     rdi, rdi
0x18000fdf7  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18000fdfb  cmp     [rdi+rbp+0Ch], r10d
0x18000fe00  jge     loc_18000FFB8
0x18000fe06  lock inc dword ptr [rdi+rbp+0Ch]
0x18000fe0b  mov     eax, esi
0x18000fe0d  lea     rdx, [rbx+1320h]
0x18000fe14  neg     eax
0x18000fe16  lea     r13, [rbx+1270h]
0x18000fe1d  lea     rax, [rbx+480h]
0x18000fe24  sbb     rcx, rcx
0x18000fe27  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fe2b  add     r13, rcx
0x18000fe2e  mov     [r13+0], rax
0x18000fe32  mov     eax, esi
0x18000fe34  neg     eax
0x18000fe36  mov     eax, esi
0x18000fe38  sbb     rcx, rcx
0x18000fe3b  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fe3f  neg     eax
0x18000fe41  mov     eax, esi
0x18000fe43  mov     [rcx+rbx+1298h], rdx
0x18000fe4b  sbb     rcx, rcx
0x18000fe4e  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fe52  lea     rdx, [rbx+1338h]
0x18000fe59  mov     [rcx+rbx+12A0h], rdx
0x18000fe61  cmp     [rsp+78h+arg_20], r15
0x18000fe69  jnz     short loc_18000FE87
0x18000fe6b  neg     eax
0x18000fe6d  lea     r15, [rbx+12A8h]
0x18000fe74  sbb     rcx, rcx
0x18000fe77  and     rcx, 0FFFFFFFFFFFFFFA8h
0x18000fe7b  add     r15, rcx
0x18000fe7e  mov     dword ptr [r15], 4
0x18000fe85  jmp     short loc_18000FE9A
0x18000fe87  neg     eax
0x18000fe89  sbb     r15, r15
0x18000fe8c  and     r15, 0FFFFFFFFFFFFFFA8h
0x18000fe90  add     r15, 12A8h
0x18000fe97  add     r15, rbx
0x18000fe9a  mov     edx, r10d; unsigned int
0x18000fe9d  mov     rcx, r13; void *
0x18000fea0  call    ?NetTraceMarkContextActivityStart@@YAXPEAXI@Z; NetTraceMarkContextActivityStart(void *,uint)
0x18000fea5  mov     r9, r13; lpParameter
0x18000fea8  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18000feb1  lea     r8, ?ProxyAutodetectionThread@@YAKPEAX@Z; lpStartAddress
0x18000feb8  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18000fec0  xor     edx, edx; dwStackSize
0x18000fec2  xor     ecx, ecx; lpThreadAttributes
0x18000fec4  call    cs:__imp_CreateThread
0x18000fecb  nop     dword ptr [rax+rax+00h]
0x18000fed0  mov     edx, 2; unsigned int
0x18000fed5  mov     rcx, r13; void *
0x18000fed8  mov     [r14+rbx], rax
0x18000fedc  call    ?NetTraceMarkContextActivityStop@@YAXPEAXI@Z; NetTraceMarkContextActivityStop(void *,uint)
0x18000fee1  cmp     qword ptr [r14+rbx], 0
0x18000fee6  jnz     short loc_18000FEF3
0x18000fee8  mov     r15d, 8007041Eh
0x18000feee  jmp     loc_18000FFF0
0x18000fef3  mov     dword ptr [rbx+0C5Ch], 1
0x18000fefd  xor     r8d, r8d; bAlertable
0x18000ff00  mov     rcx, [r14+rbx]; hHandle
0x18000ff04  mov     edx, 8CA0h; dwMilliseconds
0x18000ff09  call    cs:__imp_WaitForSingleObjectEx
0x18000ff10  nop     dword ptr [rax+rax+00h]
0x18000ff15  mov     r13d, 102h
0x18000ff1b  cmp     eax, r13d
0x18000ff1e  jnz     short loc_18000FF4D
0x18000ff20  cmp     dword ptr [r15], 2
0x18000ff24  jnz     short loc_18000FF43
0x18000ff26  mov     rcx, [r14+rbx]; hHandle
0x18000ff2a  xor     r8d, r8d; bAlertable
0x18000ff2d  mov     edx, 1388h; dwMilliseconds
0x18000ff32  call    cs:__imp_WaitForSingleObjectEx
0x18000ff39  nop     dword ptr [rax+rax+00h]
0x18000ff3e  cmp     eax, r13d
0x18000ff41  jnz     short loc_18000FF4D
0x18000ff43  mov     dword ptr [r12], 80070102h
0x18000ff4b  jmp     short loc_18000FFA1
0x18000ff4d  mov     rcx, [r14+rbx]; hObject
0x18000ff51  mov     eax, esi
0x18000ff53  neg     eax
0x18000ff55  sbb     rax, rax
0x18000ff58  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000ff5c  mov     eax, [rax+rbx+128Ch]
0x18000ff63  mov     [r12], eax
0x18000ff67  call    cs:__imp_CloseHandle
0x18000ff6e  nop     dword ptr [rax+rax+00h]
0x18000ff73  mov     qword ptr [r14+rbx], 0
0x18000ff7b  cmp     dword ptr [rdi+rbp+0Ch], 0
0x18000ff80  jl      short loc_18000FF87
0x18000ff82  lock dec dword ptr [rdi+rbp+0Ch]
0x18000ff87  mov     rcx, [rsp+78h+arg_18]
0x18000ff8f  neg     esi
0x18000ff91  sbb     rax, rax
0x18000ff94  and     rax, 0FFFFFFFFFFFFFFA8h
0x18000ff98  mov     eax, [rax+rbx+12B8h]
0x18000ff9f  mov     [rcx], eax
0x18000ffa1  mov     rcx, [rsp+78h+arg_20]
0x18000ffa9  test    rcx, rcx
0x18000ffac  jz      short loc_18000FFB3
0x18000ffae  mov     eax, [r15]
0x18000ffb1  mov     [rcx], eax
0x18000ffb3  xor     r15d, r15d
0x18000ffb6  jmp     short loc_18000FFF0
0x18000ffb8  mov     rcx, [rbx+12D0h]
0x18000ffbf  mov     dword ptr [r8], 80070102h
0x18000ffc6  test    rcx, rcx
0x18000ffc9  jz      short loc_18000FFF0
0x18000ffcb  mov     r9, [rcx]
0x18000ffce  xor     r8d, r8d
0x18000ffd1  mov     edx, r10d
0x18000ffd4  mov     rax, [r9+18h]
0x18000ffd8  lea     r9, aWeVeReachedThe_0; "We've reached the maximum number of pro"...
0x18000ffdf  mov     qword ptr [rsp+78h+dwCreationFlags], r9
0x18000ffe4  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000ffeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff0  mov     eax, r15d
0x18000fff3  add     rsp, 38h
0x18000fff7  pop     r15
0x18000fff9  pop     r14
0x18000fffb  pop     r13
0x18000fffd  pop     r12
0x18000ffff  pop     rdi
0x180010000  pop     rsi
0x180010001  pop     rbp
0x180010002  pop     rbx
0x180010003  retn
```
