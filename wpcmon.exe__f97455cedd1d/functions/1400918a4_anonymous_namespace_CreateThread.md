# _anonymous_namespace_::CreateThread

- ea: `0x1400918a4`
- end: `0x140091a51`
- name: `_anonymous_namespace_::CreateThread`
- size: `429`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140090810`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006338`
- `0x14001f6b4`
- `0x1400237ac`
- `0x140060f58`
- `0x1400918a4`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400919ed`
- `KERNEL32!GetLastError` at `0x1400919ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140091910`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140091910`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall anonymous_namespace_::CreateThread(_QWORD *a1, __int64 a2)
{
  void *v4; // rax
  HANDLE Thread; // rbx
  _DWORD *v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rdx
  signed int LastError; // eax
  unsigned int v11; // ebx
  void *v12; // [rsp+38h] [rbp-70h]
  _BYTE pExceptionObject[40]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v14; // [rsp+88h] [rbp-20h]

  v14 = a2;
  v4 = operator new(0x40u);
  v12 = (void *)std::function<Optional<__int64> (unsigned __int64,__int64)>::function<Optional<__int64> (unsigned __int64,__int64)>(
                  (__int64)v4,
                  a2);
  Thread = CreateThread(0, 0, lambda_bd4c2e6933d74f9cf7255d18d4c42609_::_lambda_invoker_cdecl_, v12, 0, 0);
  v6 = operator new(0x20u);
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = std::_Ref_count_obj2<`anonymous namespace'::Thread>::`vftable';
  *((_QWORD *)v6 + 2) = &`anonymous namespace'::Thread::`vftable';
  *((_QWORD *)v6 + 3) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a2b9167f53db33939d66b183a0ffce6e_Traceguids, v11);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *a1 = v6 + 4;
  a1[1] = v6;
  if ( v6 == (_DWORD *)-16LL )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v7 = *(__int64 **)(a2 + 56);
  if ( v7 )
  {
    v8 = *v7;
    LOBYTE(v8) = v7 != (__int64 *)a2;
    (*(void (__fastcall **)(__int64 *, __int64))(*v7 + 32))(v7, v8);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1400918a4  mov     r11, rsp
0x1400918a7  mov     [r11+18h], rbx
0x1400918ab  mov     [r11+20h], rsi
0x1400918af  push    rdi
0x1400918b0  sub     rsp, 0A0h
0x1400918b7  mov     rax, cs:__security_cookie
0x1400918be  xor     rax, rsp
0x1400918c1  mov     [rsp+0A8h+var_18], rax
0x1400918c9  mov     rsi, rdx
0x1400918cc  mov     rdi, rcx
0x1400918cf  mov     [r11-68h], rcx
0x1400918d3  mov     [r11-20h], rdx
0x1400918d7  mov     ecx, 40h ; '@'; Size
0x1400918dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400918e1  mov     rdx, rsi
0x1400918e4  mov     rcx, rax
0x1400918e7  call    ??0?$function@$$A6A?AV?$Optional@_J@@_K_J@Z@std@@QEAA@$$QEAV01@@Z; std::function<Optional<__int64> (unsigned __int64,__int64)>::function<Optional<__int64> (unsigned __int64,__int64)>(std::function<Optional<__int64> (unsigned __int64,__int64)> &&)
0x1400918ec  mov     [rsp+0A8h+var_70], rax
0x1400918f1  mov     [rsp+0A8h+lpThreadId], 0; lpThreadId
0x1400918fa  mov     [rsp+0A8h+dwCreationFlags], 0; dwCreationFlags
0x140091902  mov     r9, rax; lpParameter
0x140091905  lea     r8, _lambda_bd4c2e6933d74f9cf7255d18d4c42609____lambda_invoker_cdecl_; lpStartAddress
0x14009190c  xor     edx, edx; dwStackSize
0x14009190e  xor     ecx, ecx; lpThreadAttributes
0x140091910  call    cs:__imp_CreateThread
0x140091916  mov     rbx, rax
0x140091919  mov     ecx, 20h ; ' '; Size
0x14009191e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140091923  mov     [rsp+0A8h+var_60], rax
0x140091928  xorps   xmm0, xmm0
0x14009192b  movups  xmmword ptr [rax], xmm0
0x14009192e  mov     dword ptr [rax+8], 1
0x140091935  mov     dword ptr [rax+0Ch], 1
0x14009193c  lea     rcx, ??_7?$_Ref_count_obj2@VThread@?A0x6aa9c5e5@@@std@@6B@; const std::_Ref_count_obj2<`anonymous namespace'::Thread>::`vftable'
0x140091943  mov     [rax], rcx
0x140091946  lea     rcx, [rax+10h]
0x14009194a  mov     qword ptr [rsp+0A8h+var_58], rcx
0x14009194f  lea     rdx, ??_7Thread@?A0x6aa9c5e5@@6B@; const `anonymous namespace'::Thread::`vftable'
0x140091956  mov     [rcx], rdx
0x140091959  mov     [rcx+8], rbx
0x14009195d  test    rbx, rbx
0x140091960  jz      loc_1400919ED
0x140091966  mov     [rsp+0A8h+var_70], 0
0x14009196f  mov     [rdi], rcx
0x140091972  mov     [rdi+8], rax
0x140091976  movdqu  [rsp+0A8h+var_58], xmm0
0x14009197c  test    rcx, rcx
0x14009197f  jz      short loc_1400919CC
0x140091981  mov     rcx, [rsi+38h]
0x140091985  test    rcx, rcx
0x140091988  jz      short loc_1400919A4
0x14009198a  mov     rdx, [rcx]
0x14009198d  mov     rax, [rdx+20h]
0x140091991  cmp     rcx, rsi
0x140091994  setnz   dl
0x140091997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009199c  mov     qword ptr [rsi+38h], 0
0x1400919a4  mov     rax, rdi
0x1400919a7  mov     rcx, [rsp+0A8h+var_18]
0x1400919af  xor     rcx, rsp; StackCookie
0x1400919b2  call    __security_check_cookie
0x1400919b7  lea     r11, [rsp+0A8h+var_8]
0x1400919bf  mov     rbx, [r11+20h]
0x1400919c3  mov     rsi, [r11+28h]
0x1400919c7  mov     rsp, r11
0x1400919ca  pop     rdi
0x1400919cb  retn
0x1400919cc  mov     edx, 8000FFFFh; int
0x1400919d1  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1400919d6  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400919db  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400919e2  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1400919e7  call    _CxxThrowException_0
0x1400919ed  call    cs:__imp_GetLastError
0x1400919f3  mov     ebx, eax
0x1400919f5  test    eax, eax
0x1400919f7  jle     short loc_140091A02
0x1400919f9  movzx   ebx, ax
0x1400919fc  or      ebx, 80070000h
0x140091a02  lea     rax, WPP_GLOBAL_Control
0x140091a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140091a10  cmp     rcx, rax
0x140091a13  jz      short loc_140091A33
0x140091a15  test    byte ptr [rcx+1Ch], 1
0x140091a19  jz      short loc_140091A33
0x140091a1b  mov     edx, 0Ah
0x140091a20  mov     r9d, ebx
0x140091a23  lea     r8, WPP_a2b9167f53db33939d66b183a0ffce6e_Traceguids
0x140091a2a  mov     rcx, [rcx+10h]
0x140091a2e  call    WPP_SF_d
0x140091a33  mov     edx, ebx; int
0x140091a35  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x140091a3a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140091a3f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140091a46  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140091a4b  call    _CxxThrowException_0
```
