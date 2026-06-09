# CSxGlobalTracer::_InitializeOnThread(void)

- ea: `0x180026600`
- end: `0x1800267ac`
- name: `?_InitializeOnThread@CSxGlobalTracer@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CSxGlobalTracer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026004`
- `0x1800260dc`

## callees

- `0x180026600`
- `0x180026874`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180026685`
- `KERNEL32!GetCurrentThreadId` at `0x180026685`
- `KERNEL32!TlsSetValue` at `0x180026611`
- `KERNEL32!TlsSetValue` at `0x1800266be`
- `KERNEL32!TlsSetValue` at `0x18002670c`
- `KERNEL32!TlsSetValue` at `0x180026611`
- `KERNEL32!TlsSetValue` at `0x1800266be`
- `KERNEL32!TlsSetValue` at `0x18002670c`

## pseudocode

```c
__int64 __fastcall CSxGlobalTracer::_InitializeOnThread(CSxGlobalTracer *this)
{
  __int64 v1; // rcx
  unsigned int LastFailureAsHRESULT; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  signed __int32 v7; // esi
  unsigned int v8; // edi
  unsigned int v9; // ebp
  int *v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // eax
  int v13; // esi

  if ( !TlsSetValue(dwTlsIndex, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v1);
    v3 = LastFailureAsHRESULT;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 16;
      v6 = LastFailureAsHRESULT;
LABEL_19:
      WPP_SF_d(v4[2], v5, &WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, v6);
      return v3;
    }
    return v3;
  }
  v7 = dword_1800471F0;
  v8 = dword_1800471F0;
  v9 = dword_1800471F0 + 512;
  if ( dword_1800471F0 < (unsigned int)(dword_1800471F0 + 512) )
  {
    do
    {
      v10 = &g_Trace[10 * (v8 & 0x1FF) + 4];
      if ( !*v10 && !_InterlockedCompareExchange(v10, GetCurrentThreadId(), 0) )
        break;
      v10 = 0;
      ++v8;
    }
    while ( v8 < v9 );
    if ( v10 )
    {
      *((_QWORD *)v10 + 4) = 0;
      v10[2] = 0;
      if ( TlsSetValue(dwTlsIndex, v10) )
      {
        _InterlockedCompareExchange(&dword_1800471F0, ((_WORD)v8 + 1) & 0x1FF, v7);
        return 0;
      }
      v12 = GetLastFailureAsHRESULT(v11);
      v13 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, v12);
      TlsSetValue(dwTlsIndex, 0);
      _InterlockedExchange(v10, 0);
      v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_15:
      v3 = v13;
      if ( v13 >= 0 )
        return v3;
      goto LABEL_16;
    }
  }
  v3 = -2147467259;
  v13 = -2147467259;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_15;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids, 2147500037LL);
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    v5 = 17;
    v6 = (unsigned int)v13;
    goto LABEL_19;
  }
  return v3;
}

```

## disassembly

```asm
0x180026600  push    rbx
0x180026602  push    rbp
0x180026603  push    rsi
0x180026604  push    rdi
0x180026605  sub     rsp, 28h
0x180026609  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002660f  xor     edx, edx; lpTlsValue
0x180026611  call    cs:__imp_TlsSetValue
0x180026617  test    eax, eax
0x180026619  jnz     short loc_180026650
0x18002661b  call    GetLastFailureAsHRESULT
0x180026620  mov     ebx, eax
0x180026622  mov     rcx, cs:WPP_GLOBAL_Control
0x180026629  lea     rdi, WPP_GLOBAL_Control
0x180026630  cmp     rcx, rdi
0x180026633  jz      loc_180026746
0x180026639  test    byte ptr [rcx+1Ch], 1
0x18002663d  jz      loc_180026746
0x180026643  mov     edx, 10h
0x180026648  mov     r9d, eax
0x18002664b  jmp     loc_180026736
0x180026650  mov     esi, cs:dword_1800471F0
0x180026656  mov     edi, esi
0x180026658  lea     ebp, [rsi+200h]
0x18002665e  cmp     esi, ebp
0x180026660  jnb     loc_180026768
0x180026666  mov     eax, edi
0x180026668  and     eax, 1FFh
0x18002666d  lea     rbx, [rax+rax*4]
0x180026671  lea     rbx, [rbx+2]
0x180026675  lea     rax, ?g_Trace@@3VCSxGlobalTracer@@A; CSxGlobalTracer g_Trace
0x18002667c  lea     rbx, [rax+rbx*8]
0x180026680  cmp     dword ptr [rbx], 0
0x180026683  jnz     short loc_180026695
0x180026685  call    cs:__imp_GetCurrentThreadId
0x18002668b  mov     ecx, eax
0x18002668d  xor     eax, eax
0x18002668f  lock cmpxchg [rbx], ecx
0x180026693  jz      short loc_18002669D
0x180026695  xor     ebx, ebx
0x180026697  inc     edi
0x180026699  cmp     edi, ebp
0x18002669b  jb      short loc_180026666
0x18002669d  test    rbx, rbx
0x1800266a0  jz      loc_180026768
0x1800266a6  mov     qword ptr [rbx+20h], 0
0x1800266ae  mov     rdx, rbx; lpTlsValue
0x1800266b1  mov     dword ptr [rbx+8], 0
0x1800266b8  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800266be  call    cs:__imp_TlsSetValue
0x1800266c4  test    eax, eax
0x1800266c6  jnz     loc_180026751
0x1800266cc  call    GetLastFailureAsHRESULT
0x1800266d1  mov     esi, eax
0x1800266d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266da  lea     rdi, WPP_GLOBAL_Control
0x1800266e1  cmp     rcx, rdi
0x1800266e4  jz      short loc_180026704
0x1800266e6  test    byte ptr [rcx+1Ch], 1
0x1800266ea  jz      short loc_180026704
0x1800266ec  mov     rcx, [rcx+10h]
0x1800266f0  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x1800266f7  mov     edx, 18h
0x1800266fc  mov     r9d, eax
0x1800266ff  call    WPP_SF_d
0x180026704  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002670a  xor     edx, edx; lpTlsValue
0x18002670c  call    cs:__imp_TlsSetValue
0x180026712  xor     eax, eax
0x180026714  xchg    eax, [rbx]
0x180026716  mov     rcx, cs:WPP_GLOBAL_Control
0x18002671d  mov     ebx, esi
0x18002671f  test    esi, esi
0x180026721  jns     short loc_180026746
0x180026723  cmp     rcx, rdi
0x180026726  jz      short loc_180026746
0x180026728  test    byte ptr [rcx+1Ch], 1
0x18002672c  jz      short loc_180026746
0x18002672e  mov     edx, 11h
0x180026733  mov     r9d, esi
0x180026736  mov     rcx, [rcx+10h]
0x18002673a  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180026741  call    WPP_SF_d
0x180026746  mov     eax, ebx
0x180026748  add     rsp, 28h
0x18002674c  pop     rdi
0x18002674d  pop     rsi
0x18002674e  pop     rbp
0x18002674f  pop     rbx
0x180026750  retn
0x180026751  lea     ecx, [rdi+1]
0x180026754  mov     eax, esi
0x180026756  and     ecx, 1FFh
0x18002675c  lock cmpxchg cs:dword_1800471F0, ecx
0x180026764  xor     ebx, ebx
0x180026766  jmp     short loc_180026746
0x180026768  mov     ebx, 80004005h
0x18002676d  mov     esi, ebx
0x18002676f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026776  lea     rdi, WPP_GLOBAL_Control
0x18002677d  cmp     rcx, rdi
0x180026780  jz      short loc_18002671D
0x180026782  test    byte ptr [rcx+1Ch], 1
0x180026786  jz      short loc_18002671D
0x180026788  mov     rcx, [rcx+10h]
0x18002678c  lea     r8, WPP_055d85bb404b3f338e9cfb5d09159c0f_Traceguids
0x180026793  mov     edx, 17h
0x180026798  mov     r9d, ebx
0x18002679b  call    WPP_SF_d
0x1800267a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267a7  jmp     loc_180026723
```
