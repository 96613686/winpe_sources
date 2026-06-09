# CVirtualFileCache::Item::Initialize(ushort const *,ushort const *,ushort const *)

- ea: `0x180069ef8`
- end: `0x18006a08e`
- name: `?Initialize@Item@CVirtualFileCache@@QEAAJPEBG00@Z`
- size: `406`
- prototype: `__int64 __fastcall(PVOID pv, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006974c`

## callees

- `0x18002950c`
- `0x18002ff5c`
- `0x180035ad0`
- `0x180035b38`
- `0x180069dc0`
- `0x180069ef8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006a012`
- `KERNEL32!GetLastError` at `0x18006a012`
- `KERNEL32!CreateThreadpoolTimer` at `0x18006a003`
- `KERNEL32!CreateThreadpoolTimer` at `0x18006a003`
- `KERNEL32!SetThreadpoolTimer` at `0x18006a039`
- `KERNEL32!SetThreadpoolTimer` at `0x18006a039`

## pseudocode

```c
__int64 __fastcall CVirtualFileCache::Item::Initialize(
        _QWORD *pv,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  _QWORD *v6; // r14
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // r8
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  unsigned int v13; // [rsp+20h] [rbp-38h]
  int v14; // [rsp+24h] [rbp-34h] BYREF

  v6 = pv;
  if ( dword_180095CB0 <= *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                    + 4LL) )
  {
    v7 = -1;
  }
  else
  {
    Init_thread_header(&dword_180095CB0);
    v7 = -1;
    if ( dword_180095CB0 == -1 )
    {
      pftDueTime = (struct _FILETIME)qword_180095610;
      Init_thread_footer(&dword_180095CB0);
    }
  }
  v8 = 0;
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      v6 + 2,
      L"%ws\\%ws");
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
    }
    else
    {
      v9 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(v6 + 3, a3, v9);
    if ( a4 )
    {
      do
        ++v7;
      while ( a4[v7] );
    }
    else
    {
      LODWORD(v7) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(v6 + 4, a4, (unsigned int)v7);
  }
  catch ( ATL::CAtlException v14 )
  {
    v13 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_d08d68109c073cdceb0fe354085e5f25_Traceguids,
          (unsigned int)v14);
      v8 = v13;
      goto LABEL_18;
    }
    v6 = pv;
    v8 = v14;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(CVirtualFileCache::Item::TimerCallback, v6, 0);
  v6[5] = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_18:
  if ( (v8 & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d08d68109c073cdceb0fe354085e5f25_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180069ef8  mov     [rsp+arg_8], rbx
0x180069efd  mov     [rsp+arg_10], rsi
0x180069f02  mov     [rsp+arg_0], rcx
0x180069f07  push    rdi
0x180069f08  push    r12
0x180069f0a  push    r13
0x180069f0c  push    r14
0x180069f0e  push    r15
0x180069f10  sub     rsp, 30h
0x180069f14  mov     r15, r9
0x180069f17  mov     r12, r8
0x180069f1a  mov     r13, rdx
0x180069f1d  mov     r14, rcx
0x180069f20  mov     r10d, cs:_tls_index
0x180069f27  mov     rax, gs:58h
0x180069f30  mov     ecx, 4
0x180069f35  mov     rax, [rax+r10*8]
0x180069f39  mov     eax, [rcx+rax]
0x180069f3c  cmp     cs:dword_180095CB0, eax
0x180069f42  jle     short loc_180069F81
0x180069f44  lea     rcx, dword_180095CB0
0x180069f4b  call    _Init_thread_header
0x180069f50  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180069f54  cmp     cs:dword_180095CB0, esi
0x180069f5a  jnz     short loc_180069F85
0x180069f5c  mov     rax, cs:qword_180095610
0x180069f63  mov     cs:pftDueTime.dwLowDateTime, eax
0x180069f69  sar     rax, 20h
0x180069f6d  mov     cs:pftDueTime.dwHighDateTime, eax
0x180069f73  lea     rcx, dword_180095CB0
0x180069f7a  call    _Init_thread_footer
0x180069f7f  jmp     short loc_180069F85
0x180069f81  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180069f85  xor     edi, edi
0x180069f87  mov     ebx, edi
0x180069f89  lea     rcx, [r14+10h]
0x180069f8d  mov     r9, r15
0x180069f90  mov     r8, r13
0x180069f93  lea     rdx, aWsWs_0; "%ws\\%ws"
0x180069f9a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180069f9f  test    r12, r12
0x180069fa2  jnz     short loc_180069FA9
0x180069fa4  mov     r8d, edi
0x180069fa7  jmp     short loc_180069FB6
0x180069fa9  mov     r8, rsi
0x180069fac  inc     r8
0x180069faf  cmp     [r12+r8*2], di
0x180069fb4  jnz     short loc_180069FAC
0x180069fb6  lea     rcx, [r14+18h]
0x180069fba  mov     rdx, r12
0x180069fbd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180069fc2  test    r15, r15
0x180069fc5  jnz     short loc_180069FCB
0x180069fc7  mov     esi, edi
0x180069fc9  jmp     short loc_180069FD5
0x180069fcb  inc     rsi
0x180069fce  cmp     [r15+rsi*2], di
0x180069fd3  jnz     short loc_180069FCB
0x180069fd5  lea     rcx, [r14+20h]
0x180069fd9  mov     r8d, esi
0x180069fdc  mov     rdx, r15
0x180069fdf  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180069fe4  nop
0x180069fe5  jmp     short loc_180069FF6
0x180069fe7  mov     ebx, [rsp+58h+var_38]
0x180069feb  jmp     short loc_18006A03F
0x180069fed  mov     r14, [rsp+58h+arg_0]
0x180069ff2  mov     ebx, [rsp+58h+var_38]
0x180069ff6  xor     r8d, r8d; pcbe
0x180069ff9  mov     rdx, r14; pv
0x180069ffc  lea     rcx, ?TimerCallback@Item@CVirtualFileCache@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006a003  call    cs:__imp_CreateThreadpoolTimer
0x18006a009  mov     [r14+28h], rax
0x18006a00d  test    rax, rax
0x18006a010  jnz     short loc_18006A029
0x18006a012  call    cs:__imp_GetLastError
0x18006a018  mov     ebx, eax
0x18006a01a  test    eax, eax
0x18006a01c  jle     short loc_18006A03F
0x18006a01e  movzx   ebx, ax
0x18006a021  or      ebx, 80070000h
0x18006a027  jmp     short loc_18006A03F
0x18006a029  xor     r9d, r9d; msWindowLength
0x18006a02c  xor     r8d, r8d; msPeriod
0x18006a02f  lea     rdx, pftDueTime; pftDueTime
0x18006a036  mov     rcx, rax; pti
0x18006a039  call    cs:__imp_SetThreadpoolTimer
0x18006a03f  test    ebx, ebx
0x18006a041  jns     short loc_18006A074
0x18006a043  lea     rax, WPP_GLOBAL_Control
0x18006a04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a051  cmp     rcx, rax
0x18006a054  jz      short loc_18006A074
0x18006a056  test    byte ptr [rcx+1Ch], 2
0x18006a05a  jz      short loc_18006A074
0x18006a05c  mov     edx, 0Eh
0x18006a061  mov     r9d, ebx
0x18006a064  lea     r8, WPP_d08d68109c073cdceb0fe354085e5f25_Traceguids
0x18006a06b  mov     rcx, [rcx+10h]
0x18006a06f  call    WPP_SF_d
0x18006a074  mov     eax, ebx
0x18006a076  mov     rbx, [rsp+58h+arg_8]
0x18006a07b  mov     rsi, [rsp+58h+arg_10]
0x18006a080  add     rsp, 30h
0x18006a084  pop     r15
0x18006a086  pop     r14
0x18006a088  pop     r13
0x18006a08a  pop     r12
0x18006a08c  pop     rdi
0x18006a08d  retn
```
