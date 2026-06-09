# CSxGlobalTracer::GetThreadContext(SxThreadContext * *)

- ea: `0x180025dd0`
- end: `0x180025ffb`
- name: `?GetThreadContext@CSxGlobalTracer@@QEAAJPEAPEAUSxThreadContext@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(CSxGlobalTracer *__hidden this, struct SxThreadContext **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800206f0`
- `0x1800268b4`

## callees

- `0x180025dd0`
- `0x180026874`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025e8c`
- `KERNEL32!GetLastError` at `0x180025e8c`
- `KERNEL32!GetCurrentThreadId` at `0x180025f13`
- `KERNEL32!GetCurrentThreadId` at `0x180025f13`
- `KERNEL32!TlsSetValue` at `0x180025f4c`
- `KERNEL32!TlsSetValue` at `0x180025f96`
- `KERNEL32!TlsSetValue` at `0x180025f4c`
- `KERNEL32!TlsSetValue` at `0x180025f96`
- `KERNEL32!TlsGetValue` at `0x180025e7d`
- `KERNEL32!TlsGetValue` at `0x180025e7d`

## pseudocode

```c
__int64 __fastcall CSxGlobalTracer::GetThreadContext(CSxGlobalTracer *this, struct SxThreadContext **a2)
{
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  struct SxThreadContext *Value; // rax
  signed int LastError; // eax
  signed __int32 v9; // r14d
  unsigned int v10; // ebp
  unsigned int v11; // ebx
  int *v12; // rdi
  __int64 v13; // rcx

  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  if ( g_Trace[0] )
  {
    if ( dwTlsIndex == -1 )
    {
      v4 = 2147500037LL;
      LastFailureAsHRESULT = -2147467259;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 26;
        goto LABEL_7;
      }
    }
    else
    {
      Value = (struct SxThreadContext *)TlsGetValue(dwTlsIndex);
      if ( Value )
      {
        *a2 = Value;
        return 0;
      }
      LastError = GetLastError();
      LastFailureAsHRESULT = LastError;
      if ( LastError > 0 )
        LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
      if ( (LastFailureAsHRESULT & 0x80000000) == 0 )
      {
        *a2 = 0;
        v9 = dword_1800471F0;
        v10 = dword_1800471F0;
        v11 = dword_1800471F0 + 512;
        if ( dword_1800471F0 >= (unsigned int)(dword_1800471F0 + 512) )
          goto LABEL_30;
        do
        {
          v12 = &g_Trace[10 * (v10 & 0x1FF) + 4];
          if ( !*v12 && !_InterlockedCompareExchange(v12, GetCurrentThreadId(), 0) )
            break;
          v12 = 0;
          ++v10;
        }
        while ( v10 < v11 );
        if ( v12 )
        {
          *((_QWORD *)v12 + 4) = 0;
          v12[2] = 0;
          if ( TlsSetValue(dwTlsIndex, v12) )
          {
            LastFailureAsHRESULT = 0;
            _InterlockedCompareExchange(&dword_1800471F0, ((_WORD)v10 + 1) & 0x1FF, v9);
            *a2 = (struct SxThreadContext *)v12;
          }
          else
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                &WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids,
                LastFailureAsHRESULT);
            TlsSetValue(dwTlsIndex, 0);
            _InterlockedExchange(v12, 0);
          }
        }
        else
        {
LABEL_30:
          v4 = 2147500037LL;
          LastFailureAsHRESULT = -2147467259;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 23;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 22;
          v4 = LastFailureAsHRESULT;
          goto LABEL_7;
        }
      }
    }
  }
  else
  {
    v4 = 2147500037LL;
    LastFailureAsHRESULT = -2147467259;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 25;
LABEL_7:
      WPP_SF_d(v5[2], v6, &WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, v4);
    }
  }
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180025dd0  push    rbx
0x180025dd2  push    rbp
0x180025dd3  push    rsi
0x180025dd4  push    rdi
0x180025dd5  push    r14
0x180025dd7  sub     rsp, 20h
0x180025ddb  mov     rsi, rdx
0x180025dde  test    rdx, rdx
0x180025de1  jnz     short loc_180025DED
0x180025de3  mov     ebx, 80070057h
0x180025de8  jmp     loc_180025FEE
0x180025ded  mov     qword ptr [rdx], 0
0x180025df4  cmp     cs:?g_Trace@@3VCSxGlobalTracer@@A, 0; CSxGlobalTracer g_Trace
0x180025dfb  jnz     short loc_180025E41
0x180025dfd  mov     r9d, 80004005h
0x180025e03  mov     ebx, r9d
0x180025e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e0d  lea     rax, WPP_GLOBAL_Control
0x180025e14  cmp     rcx, rax
0x180025e17  jz      loc_180025FEE
0x180025e1d  test    byte ptr [rcx+1Ch], 1
0x180025e21  jz      loc_180025FEE
0x180025e27  mov     edx, 19h
0x180025e2c  mov     rcx, [rcx+10h]
0x180025e30  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180025e37  call    WPP_SF_d
0x180025e3c  jmp     loc_180025FEE
0x180025e41  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180025e47  cmp     ecx, 0FFFFFFFFh
0x180025e4a  jnz     short loc_180025E7D
0x180025e4c  mov     r9d, 80004005h
0x180025e52  mov     ebx, r9d
0x180025e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e5c  lea     rax, WPP_GLOBAL_Control
0x180025e63  cmp     rcx, rax
0x180025e66  jz      loc_180025FEE
0x180025e6c  test    byte ptr [rcx+1Ch], 1
0x180025e70  jz      loc_180025FEE
0x180025e76  mov     edx, 1Ah
0x180025e7b  jmp     short loc_180025E2C
0x180025e7d  call    cs:__imp_TlsGetValue
0x180025e83  test    rax, rax
0x180025e86  jnz     loc_180025FE9
0x180025e8c  call    cs:__imp_GetLastError
0x180025e92  mov     ebx, eax
0x180025e94  test    eax, eax
0x180025e96  jle     short loc_180025EA1
0x180025e98  movzx   ebx, ax
0x180025e9b  or      ebx, 80070000h
0x180025ea1  test    ebx, ebx
0x180025ea3  jns     short loc_180025ED3
0x180025ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025eac  lea     rax, WPP_GLOBAL_Control
0x180025eb3  cmp     rcx, rax
0x180025eb6  jz      loc_180025FEE
0x180025ebc  test    byte ptr [rcx+1Ch], 1
0x180025ec0  jz      loc_180025FEE
0x180025ec6  mov     edx, 16h
0x180025ecb  mov     r9d, ebx
0x180025ece  jmp     loc_180025E2C
0x180025ed3  mov     qword ptr [rsi], 0
0x180025eda  mov     r14d, cs:dword_1800471F0
0x180025ee1  mov     ebp, r14d
0x180025ee4  lea     ebx, [r14+200h]
0x180025eeb  cmp     r14d, ebx
0x180025eee  jnb     loc_180025FBD
0x180025ef4  mov     eax, ebp
0x180025ef6  and     eax, 1FFh
0x180025efb  lea     rdi, [rax+rax*4]
0x180025eff  lea     rdi, [rdi+2]
0x180025f03  lea     rax, ?g_Trace@@3VCSxGlobalTracer@@A; CSxGlobalTracer g_Trace
0x180025f0a  lea     rdi, [rax+rdi*8]
0x180025f0e  cmp     dword ptr [rdi], 0
0x180025f11  jnz     short loc_180025F23
0x180025f13  call    cs:__imp_GetCurrentThreadId
0x180025f19  mov     ecx, eax
0x180025f1b  xor     eax, eax
0x180025f1d  lock cmpxchg [rdi], ecx
0x180025f21  jz      short loc_180025F2B
0x180025f23  xor     edi, edi
0x180025f25  inc     ebp
0x180025f27  cmp     ebp, ebx
0x180025f29  jb      short loc_180025EF4
0x180025f2b  test    rdi, rdi
0x180025f2e  jz      loc_180025FBD
0x180025f34  mov     qword ptr [rdi+20h], 0
0x180025f3c  mov     rdx, rdi; lpTlsValue
0x180025f3f  mov     dword ptr [rdi+8], 0
0x180025f46  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180025f4c  call    cs:__imp_TlsSetValue
0x180025f52  test    eax, eax
0x180025f54  jnz     short loc_180025FA2
0x180025f56  call    GetLastFailureAsHRESULT
0x180025f5b  mov     ebx, eax
0x180025f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f64  lea     rax, WPP_GLOBAL_Control
0x180025f6b  cmp     rcx, rax
0x180025f6e  jz      short loc_180025F8E
0x180025f70  test    byte ptr [rcx+1Ch], 1
0x180025f74  jz      short loc_180025F8E
0x180025f76  mov     rcx, [rcx+10h]
0x180025f7a  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180025f81  mov     edx, 18h
0x180025f86  mov     r9d, ebx
0x180025f89  call    WPP_SF_d
0x180025f8e  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180025f94  xor     edx, edx; lpTlsValue
0x180025f96  call    cs:__imp_TlsSetValue
0x180025f9c  xor     eax, eax
0x180025f9e  xchg    eax, [rdi]
0x180025fa0  jmp     short loc_180025FEE
0x180025fa2  xor     ebx, ebx
0x180025fa4  lea     ecx, [rbp+1]
0x180025fa7  and     ecx, 1FFh
0x180025fad  mov     eax, r14d
0x180025fb0  lock cmpxchg cs:dword_1800471F0, ecx
0x180025fb8  mov     [rsi], rdi
0x180025fbb  jmp     short loc_180025FEE
0x180025fbd  mov     r9d, 80004005h
0x180025fc3  mov     ebx, r9d
0x180025fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fcd  lea     rax, WPP_GLOBAL_Control
0x180025fd4  cmp     rcx, rax
0x180025fd7  jz      short loc_180025FEE
0x180025fd9  test    byte ptr [rcx+1Ch], 1
0x180025fdd  jz      short loc_180025FEE
0x180025fdf  mov     edx, 17h
0x180025fe4  jmp     loc_180025E2C
0x180025fe9  mov     [rsi], rax
0x180025fec  xor     ebx, ebx
0x180025fee  mov     eax, ebx
0x180025ff0  add     rsp, 20h
0x180025ff4  pop     r14
0x180025ff6  pop     rdi
0x180025ff7  pop     rsi
0x180025ff8  pop     rbp
0x180025ff9  pop     rbx
0x180025ffa  retn
```
