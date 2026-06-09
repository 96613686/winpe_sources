# Log_Text_F

- ea: `0x18000e6ac`
- end: `0x18000e85d`
- name: `Log_Text_F`
- size: `433`
- prototype: `__int64(_QWORD, _QWORD, const char *, ...)`
- caller_count: `21`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800039c0`
- `0x18000f134`
- `0x18001b7b4`
- `0x180020428`
- `0x180020830`
- `0x1800209a0`
- `0x1800209d0`
- `0x1800209fc`
- `0x180020ad0`
- `0x180020d60`
- `0x180020dcc`
- `0x1800211f8`
- `0x180021904`
- `0x180023a94`
- `0x18002fb41`
- `0x18002fcbc`
- `0x18002fcf0`
- `0x18002fd2a`
- `0x18002fd5e`
- `0x180030160`
- `0x1800301c3`

## callees

- `0x18000e6ac`
- `0x180013e58`
- `0x180013ec8`
- `0x18001ba10`
- `0x18001c1a8`
- `0x18002dec0`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x18000e7cd`
- `msvcrt!_vsnprintf_s` at `0x18000e7cd`
- `msvcrt!_snprintf_s` at `0x18000e780`
- `msvcrt!_snprintf_s` at `0x18000e780`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000e7e7`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000e7e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e752`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e752`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e73f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e73f`

## pseudocode

```c
char Log_Text_F(__int64 a1, int a2, const char *a3, ...)
{
  int v5; // eax
  DWORD CurrentProcessId; // edi
  const char *v7; // rbx
  DWORD TickCount; // eax
  unsigned __int64 v9; // rdx
  char *p_Buffer; // rcx
  size_t v11; // rdi
  char *v12; // rax
  int v13; // ebx
  __int64 v14; // rdx
  char *v15; // r9
  char Buffer; // [rsp+50h] [rbp-438h] BYREF
  char v18; // [rsp+51h] [rbp-437h] BYREF
  va_list va; // [rsp+4A8h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( dword_18004E570 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18004E570);
    if ( dword_18004E570 == -1 )
    {
      byte_18004E560 = *a3;
      Init_thread_footer(&dword_18004E570);
    }
  }
  LOBYTE(v5) = (_BYTE)a3;
  if ( *a3 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v7 = (const char *)mlib::efn<char>(a1);
    TickCount = GetTickCount();
    v5 = _snprintf_s(
           &Buffer,
           0x400u,
           0xFFFFFFFFFFFFFFFFuLL,
           "%06u (%04u) - %s:%04d: ",
           TickCount,
           CurrentProcessId,
           v7,
           a2);
    if ( v5 > 0 )
    {
      v9 = v5;
      p_Buffer = &Buffer;
      v11 = 1024LL - v5;
      if ( (unsigned __int64)v5 >= 0x400 )
        v11 = 1024;
      v12 = &Buffer + v5;
      if ( v9 < 0x400 )
        p_Buffer = v12;
      v5 = _vsnprintf_s(p_Buffer, v11, 0xFFFFFFFFFFFFFFFFuLL, a3, va);
      v13 = v5;
      if ( v5 > 0 )
      {
        LOBYTE(v5) = EventEnabled(WINSATAPI_ETW_PROVIDER_Context, &AnsiTextMessageEv);
        if ( (_BYTE)v5 )
        {
          v15 = &v18;
          LOWORD(v13) = v13 - v11 + 1023;
          LOBYTE(v5) = 1;
          while ( (_WORD)v13 )
          {
            if ( *v15 == 32 && *(v15 - 1) == 45 )
            {
              ++v15;
              LOWORD(v13) = v13 - 1;
              break;
            }
            ++v15;
            LOWORD(v13) = v13 - 1;
          }
          if ( (WINSATAPI_ETW_PROVIDEREnableBits & 1) != 0 )
            LOBYTE(v5) = McTemplateU0hsr0_EventWriteTransfer(
                           &WINSATAPI_ETW_PROVIDER_Context,
                           v14,
                           (unsigned int)(v13 + 1),
                           v15);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000e6ac  mov     [rsp+Format], r8
0x18000e6b1  mov     qword ptr [rsp+arg_18], r9
0x18000e6b6  push    rbx
0x18000e6b7  push    rbp
0x18000e6b8  push    rsi
0x18000e6b9  push    rdi
0x18000e6ba  sub     rsp, 468h
0x18000e6c1  mov     rax, cs:__security_cookie
0x18000e6c8  xor     rax, rsp
0x18000e6cb  mov     [rsp+488h+var_38], rax
0x18000e6d3  mov     rax, gs:58h
0x18000e6dc  mov     rbx, rcx
0x18000e6df  mov     ecx, cs:_tls_index
0x18000e6e5  mov     esi, edx
0x18000e6e7  mov     edx, 4
0x18000e6ec  mov     rax, [rax+rcx*8]
0x18000e6f0  mov     eax, [rdx+rax]
0x18000e6f3  cmp     cs:dword_18004E570, eax
0x18000e6f9  jle     short loc_18000E72C
0x18000e6fb  lea     rcx, dword_18004E570
0x18000e702  call    _Init_thread_header
0x18000e707  cmp     cs:dword_18004E570, 0FFFFFFFFh
0x18000e70e  jnz     short loc_18000E72C
0x18000e710  mov     rax, [rsp+488h+Format]
0x18000e718  lea     rcx, dword_18004E570
0x18000e71f  mov     dl, [rax]
0x18000e721  mov     cs:byte_18004E560, dl
0x18000e727  call    _Init_thread_footer
0x18000e72c  mov     rax, [rsp+488h+Format]
0x18000e734  xor     ebp, ebp
0x18000e736  cmp     [rax], bpl
0x18000e739  jz      loc_18000E841
0x18000e73f  call    cs:__imp_GetCurrentProcessId
0x18000e745  mov     rcx, rbx
0x18000e748  mov     edi, eax
0x18000e74a  call    ??$efn@D@mlib@@YAPEBDPEBD@Z; mlib::efn<char>(char const *)
0x18000e74f  mov     rbx, rax
0x18000e752  call    cs:__imp_GetTickCount
0x18000e758  mov     [rsp+488h+var_450], esi
0x18000e75c  lea     r9, Format; "%06u (%04u) - %s:%04d: "
0x18000e763  mov     [rsp+488h+var_458], rbx
0x18000e768  lea     rcx, [rsp+488h+Buffer]; Buffer
0x18000e76d  mov     ebx, 400h
0x18000e772  mov     [rsp+488h+var_460], edi
0x18000e776  mov     edx, ebx; BufferCount
0x18000e778  mov     dword ptr [rsp+488h+ArgList], eax
0x18000e77c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000e780  call    cs:__imp__snprintf_s
0x18000e786  test    eax, eax
0x18000e788  jle     loc_18000E841
0x18000e78e  movsxd  rdx, eax
0x18000e791  lea     r9, [rsp+488h+arg_18]
0x18000e799  mov     [rsp+488h+ArgList], r9; ArgList
0x18000e79e  lea     rax, [rsp+488h+Buffer]
0x18000e7a3  mov     r9, [rsp+488h+Format]; Format
0x18000e7ab  lea     rcx, [rsp+488h+Buffer]
0x18000e7b0  mov     edi, ebx
0x18000e7b2  sub     rdi, rdx
0x18000e7b5  cmp     rdx, rbx
0x18000e7b8  cmovnb  rdi, rbx
0x18000e7bc  add     rax, rdx
0x18000e7bf  cmp     rdx, rbx
0x18000e7c2  mov     rdx, rdi; BufferCount
0x18000e7c5  cmovb   rcx, rax; Buffer
0x18000e7c9  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000e7cd  call    cs:__imp__vsnprintf_s
0x18000e7d3  mov     ebx, eax
0x18000e7d5  test    eax, eax
0x18000e7d7  jle     short loc_18000E841
0x18000e7d9  mov     rcx, cs:WINSATAPI_ETW_PROVIDER_Context; RegHandle
0x18000e7e0  lea     rdx, AnsiTextMessageEv; EventDescriptor
0x18000e7e7  call    cs:__imp_EventEnabled
0x18000e7ed  test    al, al
0x18000e7ef  jz      short loc_18000E841
0x18000e7f1  mov     eax, 3FFh
0x18000e7f6  lea     r9, [rsp+488h+var_437]
0x18000e7fb  sub     bx, di
0x18000e7fe  mov     ecx, 0FFFFh
0x18000e803  add     bx, ax
0x18000e806  lea     eax, [rbp+1]
0x18000e809  test    bx, bx
0x18000e80c  jz      short loc_18000E829
0x18000e80e  cmp     byte ptr [r9], 20h ; ' '
0x18000e812  jnz     short loc_18000E81B
0x18000e814  cmp     byte ptr [r9-1], 2Dh ; '-'
0x18000e819  jz      short loc_18000E823
0x18000e81b  add     r9, rax
0x18000e81e  add     bx, cx
0x18000e821  jmp     short loc_18000E809
0x18000e823  add     r9, rax
0x18000e826  add     bx, cx
0x18000e829  test    cs:WINSATAPI_ETW_PROVIDEREnableBits, al
0x18000e82f  jz      short loc_18000E841
0x18000e831  lea     r8d, [rax+rbx]
0x18000e835  lea     rcx, WINSATAPI_ETW_PROVIDER_Context
0x18000e83c  call    McTemplateU0hsr0_EventWriteTransfer
0x18000e841  mov     rcx, [rsp+488h+var_38]
0x18000e849  xor     rcx, rsp; StackCookie
0x18000e84c  call    __security_check_cookie
0x18000e851  add     rsp, 468h
0x18000e858  pop     rdi
0x18000e859  pop     rsi
0x18000e85a  pop     rbp
0x18000e85b  pop     rbx
0x18000e85c  retn
```
