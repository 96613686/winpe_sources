# SNI_Conn::StartReadAsyncTimeout(void)

- ea: `0x100423ce0`
- end: `0x100423f5b`
- name: `?StartReadAsyncTimeout@SNI_Conn@@QEAAKXZ`
- size: `635`
- prototype: `unsigned int __fastcall(SNI_Conn *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100426110`
- `0x100426350`
- `0x100447930`

## callees

- `0x100423ce0`
- `0x10042c270`
- `0x10042c430`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100423f23`
- `KERNEL32!QueryPerformanceCounter` at `0x100423f23`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100423f12`
- `sqldk!SystemThread_TlsIndex` at `0x100423de7`
- `sqldk!SystemThread_TlsIndex` at `0x100423e67`
- `sqldk!SystemThread_TlsOffset` at `0x100423df0`
- `sqldk!SystemThread_TlsOffset` at `0x100423e70`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423e0b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423e8b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423e0b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100423e8b`

## string_xrefs

- `0x100423d02`: `sql\common\dk\sni\src\sni.cpp`
- `0x100423d0d`: `SNI_Conn::StartReadAsyncTimeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNI_Conn::StartReadAsyncTimeout(SNI_Conn *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  unsigned int v5; // r14d
  struct SNI_ReadTimeoutListBlock *v6; // rbx
  unsigned int v7; // edx
  __int64 v8; // r8
  _QWORD *v9; // rdi
  volatile signed __int64 *v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, __int64); // rcx
  void *v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  char *v19; // rdi
  LARGE_INTEGER v20; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+8h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::StartReadAsyncTimeout",
      1579,
      L"API|SNI",
      -2,
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::StartReadAsyncTimeout",
      1579);
  v5 = 0;
  if ( !*((_BYTE *)this + 12568) || *((_BYTE *)this + 12584) )
    goto LABEL_24;
  v6 = g_pReadTimeoutBlockHead;
  while ( (unsigned __int64)*((__int16 *)v6 + 4) >= 0xC4 )
  {
LABEL_13:
    if ( !*(_QWORD *)v6 )
    {
      v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v12 = *(_QWORD *)(v11 + 256);
      if ( !v12 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v12 = *(_QWORD *)(v11 + 256);
      }
      v13 = *(__int64 (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 992) + 56LL) + 8LL)
                                                        + 64LL);
      v14 = (void *)(**v13)(v13, 1);
      memset(v14, 0, 0x1FF0u);
      if ( v14
        && _InterlockedCompareExchange64((volatile signed __int64 *)v6, (signed __int64)v14, 0)
        && _InterlockedCompareExchange64(*(volatile signed __int64 **)v6, (signed __int64)v14, 0) )
      {
        v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v16 = *(_QWORD *)(v15 + 256);
        if ( !v16 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v16 = *(_QWORD *)(v15 + 256);
        }
        v17 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 992) + 56LL) + 8LL) + 64LL);
        (*(void (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v17 + 16LL))(v17, v14, 1);
      }
    }
    v6 = *(struct SNI_ReadTimeoutListBlock **)v6;
    if ( !v6 )
    {
      v5 = 14;
      goto LABEL_24;
    }
  }
  if ( (unsigned __int64)_InterlockedIncrement16((volatile signed __int16 *)v6 + 4) > 0xCC )
  {
LABEL_12:
    _InterlockedDecrement16((volatile signed __int16 *)v6 + 4);
    goto LABEL_13;
  }
  v7 = 0;
  v8 = 0;
  v9 = (_QWORD *)((char *)v6 + 16);
  while ( 1 )
  {
    if ( !*v9 )
    {
      v10 = (volatile signed __int64 *)((char *)v6 + 40 * (int)v7);
      if ( !_InterlockedCompareExchange64(v10 + 2, (signed __int64)this, 0) )
        break;
    }
    ++v7;
    ++v8;
    v9 += 5;
    if ( v7 >= 0xCC )
      goto LABEL_12;
  }
  v19 = (char *)v6 + 40 * v8;
  *((_WORD *)v19 + 20) = 2;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v20 = PerformanceCount;
  }
  else
  {
    v20.QuadPart = MEMORY[0x7FFE0008];
  }
  *((LARGE_INTEGER *)v19 + 3) = v20;
  *((_QWORD *)v19 + 3) = v20.QuadPart + *((_QWORD *)this + 1572);
  *((_QWORD *)this + 1570) = v10 + 2;
LABEL_24:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNI_Conn::StartReadAsyncTimeout", 1579, a4);
  return v5;
}

```

## disassembly

```asm
0x100423ce0  mov     rax, rsp
0x100423ce3  push    rsi
0x100423ce4  push    rdi
0x100423ce5  push    r12
0x100423ce7  push    r14
0x100423ce9  push    r15
0x100423ceb  sub     rsp, 40h
0x100423cef  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100423cf7  mov     [rax+10h], rbx
0x100423cfb  mov     [rax+18h], rbp
0x100423cff  mov     rbp, rcx
0x100423d02  lea     r15, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100423d09  mov     [rax-40h], r15
0x100423d0d  lea     r12, aSniConnStartre; "SNI_Conn::StartReadAsyncTimeout"
0x100423d14  mov     [rax-38h], r12
0x100423d18  mov     dword ptr [rax-30h], 62Bh
0x100423d1f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423d26  jz      short loc_100423D40
0x100423d28  lea     r9, aApiSni; "API|SNI"
0x100423d2f  mov     r8d, 62Bh; int
0x100423d35  mov     rdx, r12; char *
0x100423d38  mov     rcx, r15; char *
0x100423d3b  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100423d40  xor     r14d, r14d
0x100423d43  cmp     [rbp+3118h], r14b
0x100423d4a  jz      loc_100423ECA
0x100423d50  cmp     [rbp+3128h], r14b
0x100423d57  jnz     loc_100423ECA
0x100423d5d  mov     rbx, cs:?g_pReadTimeoutBlockHead@@3PEAVSNI_ReadTimeoutListBlock@@EA; SNI_ReadTimeoutListBlock * g_pReadTimeoutBlockHead
0x100423d64  nop     dword ptr [rax+00h]
0x100423d68  nop     dword ptr [rax+rax+00000000h]
0x100423d70  movsx   rax, word ptr [rbx+8]
0x100423d75  cmp     rax, 0C4h
0x100423d7b  jnb     short loc_100423DD5
0x100423d7d  mov     eax, 1
0x100423d82  lock xadd [rbx+8], ax
0x100423d88  inc     ax
0x100423d8b  movsx   rax, ax
0x100423d8f  cmp     rax, 0CCh
0x100423d95  ja      short loc_100423DD0
0x100423d97  mov     edx, r14d
0x100423d9a  mov     r8, r14
0x100423d9d  lea     rdi, [rbx+10h]
0x100423da1  cmp     [rdi], r14
0x100423da4  jnz     short loc_100423DBF
0x100423da6  movsxd  rax, edx
0x100423da9  lea     rcx, [rax+rax*4]
0x100423dad  lea     rsi, [rbx+rcx*8]
0x100423db1  xor     eax, eax
0x100423db3  lock cmpxchg [rsi+10h], rbp
0x100423db9  jz      loc_100423F01
0x100423dbf  inc     edx
0x100423dc1  inc     r8
0x100423dc4  add     rdi, 28h ; '('
0x100423dc8  cmp     edx, 0CCh
0x100423dce  jb      short loc_100423DA1
0x100423dd0  lock dec word ptr [rbx+8]
0x100423dd5  cmp     [rbx], r14
0x100423dd8  jnz     loc_100423EBA
0x100423dde  mov     rdx, gs:58h
0x100423de7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423dee  mov     ecx, [rax]
0x100423df0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100423df7  mov     edi, [rax]
0x100423df9  add     rdi, [rdx+rcx*8]
0x100423dfd  mov     rax, [rdi+100h]
0x100423e04  test    rax, rax
0x100423e07  jnz     short loc_100423E18
0x100423e09  xor     ecx, ecx
0x100423e0b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100423e11  mov     rax, [rdi+100h]
0x100423e18  mov     rax, [rax+3E0h]
0x100423e1f  mov     rcx, [rax+38h]
0x100423e23  mov     rax, [rcx+8]
0x100423e27  mov     rcx, [rax+40h]
0x100423e2b  mov     rax, [rcx]
0x100423e2e  xor     r8d, r8d
0x100423e31  lea     edx, [r8+1]
0x100423e35  call    qword ptr [rax]
0x100423e37  mov     rsi, rax
0x100423e3a  mov     rdi, rax
0x100423e3d  xor     eax, eax
0x100423e3f  mov     ecx, 1FF0h
0x100423e44  rep stosb
0x100423e46  test    rsi, rsi
0x100423e49  jz      short loc_100423EBA
0x100423e4b  lock cmpxchg [rbx], rsi
0x100423e50  jz      short loc_100423EBA
0x100423e52  mov     rcx, [rbx]
0x100423e55  xor     eax, eax
0x100423e57  lock cmpxchg [rcx], rsi
0x100423e5c  jz      short loc_100423EBA
0x100423e5e  mov     rdx, gs:58h
0x100423e67  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423e6e  mov     ecx, [rax]
0x100423e70  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100423e77  mov     edi, [rax]
0x100423e79  add     rdi, [rdx+rcx*8]
0x100423e7d  mov     rax, [rdi+100h]
0x100423e84  test    rax, rax
0x100423e87  jnz     short loc_100423E98
0x100423e89  xor     ecx, ecx
0x100423e8b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100423e91  mov     rax, [rdi+100h]
0x100423e98  mov     rax, [rax+3E0h]
0x100423e9f  mov     rcx, [rax+38h]
0x100423ea3  mov     rax, [rcx+8]
0x100423ea7  mov     rcx, [rax+40h]
0x100423eab  mov     rax, [rcx]
0x100423eae  mov     r8d, 1
0x100423eb4  mov     rdx, rsi
0x100423eb7  call    qword ptr [rax+10h]
0x100423eba  mov     rbx, [rbx]
0x100423ebd  test    rbx, rbx
0x100423ec0  jnz     loc_100423D70
0x100423ec6  lea     r14d, [rbx+0Eh]
0x100423eca  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423ed1  jz      short loc_100423EE4
0x100423ed3  mov     r8d, 62Bh; int
0x100423ed9  mov     rdx, r12; char *
0x100423edc  mov     rcx, r15; char *
0x100423edf  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100423ee4  mov     eax, r14d
0x100423ee7  mov     rbx, [rsp+68h+arg_8]
0x100423eec  mov     rbp, [rsp+68h+arg_10]
0x100423ef4  add     rsp, 40h
0x100423ef8  pop     r15
0x100423efa  pop     r14
0x100423efc  pop     r12
0x100423efe  pop     rdi
0x100423eff  pop     rsi
0x100423f00  retn
0x100423f01  lea     rax, [r8+r8*4]
0x100423f05  lea     rdi, [rbx+rax*8]
0x100423f09  mov     eax, 2
0x100423f0e  mov     [rdi+28h], ax
0x100423f12  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100423f19  cmp     [rax], r14d
0x100423f1c  jz      short loc_100423F30
0x100423f1e  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x100423f23  call    cs:__imp_QueryPerformanceCounter
0x100423f29  mov     rax, qword ptr [rsp+68h+PerformanceCount]
0x100423f2e  jmp     short loc_100423F38
0x100423f30  mov     rax, ds:7FFE0008h
0x100423f38  mov     [rdi+18h], rax
0x100423f3c  mov     rdx, [rbp+3120h]
0x100423f43  add     rdx, rax
0x100423f46  mov     [rdi+18h], rdx
0x100423f4a  lea     rax, [rsi+10h]
0x100423f4e  mov     [rbp+3110h], rax
0x100423f55  jmp     loc_100423ECA
```
