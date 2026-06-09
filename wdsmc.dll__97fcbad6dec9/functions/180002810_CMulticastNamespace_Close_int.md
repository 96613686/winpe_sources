# CMulticastNamespace::Close(int)

- ea: `0x180002810`
- end: `0x18000295a`
- name: `?Close@CMulticastNamespace@@QEAAKH@Z`
- size: `330`
- prototype: `unsigned int __fastcall(CMulticastNamespace *__hidden this, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180005a4c`
- `0x180005f18`
- `0x180006488`
- `0x1800067f0`
- `0x180007a24`

## callees

- `0x180002810`
- `0x180003b08`
- `0x180004184`
- `0x18000433c`
- `0x1800044e8`
- `0x18000b430`
- `0x180018da4`
- `0x18001a9a8`
- `0x1800227d4`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180002842`
- `KERNEL32!GetSystemTime` at `0x180002842`
- `KERNEL32!LeaveCriticalSection` at `0x180002939`
- `KERNEL32!LeaveCriticalSection` at `0x180002939`
- `KERNEL32!EnterCriticalSection` at `0x180002831`
- `KERNEL32!EnterCriticalSection` at `0x180002831`
- `KERNEL32!DeleteCriticalSection` at `0x1800028de`
- `KERNEL32!DeleteCriticalSection` at `0x1800028de`

## string_xrefs

- `0x180002884`: `pContent->CanDelete()`

## pseudocode

```c
__int64 __fastcall CMulticastNamespace::Close(CMulticastNamespace *this, int a2)
{
  void *v4; // r9
  __int64 *v5; // r14
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  const unsigned __int16 *v10; // r8
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 30) = 1;
  GetSystemTime((LPSYSTEMTIME)((char *)this + 124));
  v5 = (__int64 *)((char *)this + 424);
  DebugInfo = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 53);
  while ( DebugInfo )
  {
    v7 = DebugInfo;
    DebugInfo = (struct _RTL_CRITICAL_SECTION *)DebugInfo[77].DebugInfo;
    CMulticastContent::Close(v7, a2);
    if ( a2 )
    {
      CMulticastContent::Shutdown(v7);
      if ( !(unsigned int)CMulticastContent::CanDelete(v7) )
        WdsAssert("base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x136u, "pContent->CanDelete()", (int)v4, 0);
    }
  }
  if ( a2 && *v5 )
  {
    v12 = *v5;
    do
    {
      v8 = (struct _RTL_CRITICAL_SECTION *)CList<CMulticastContent,CNoLock>::DeleteAt((char *)this + 424, &v12);
      v9 = v8;
      if ( v8 )
      {
        CMulticastContent::Shutdown(v8);
        CMcCoClients::Shutdown((CMcCoClients *)&v9[7].SpinCount);
        DeleteCriticalSection(v9);
        operator delete(v9);
      }
    }
    while ( v12 );
  }
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 10);
  if ( v10 )
  {
    if ( g_ErrLibTraceFunction )
    {
      g_ErrLibTraceFunction(L"WDSMCNS[%u:%s] Closing...", *((unsigned int *)this + 14));
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 10);
    }
    CMulticastNotification::AddNotification((CMRSWLock *)((char *)qword_1800336E8 + 864), 2u, v10, v4);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return 0;
}

```

## disassembly

```asm
0x180002810  mov     [rsp+arg_8], rbx
0x180002815  mov     [rsp+arg_10], rbp
0x18000281a  mov     [rsp+arg_18], rsi
0x18000281f  push    rdi
0x180002820  push    r14
0x180002822  push    r15
0x180002824  sub     rsp, 30h
0x180002828  mov     rdi, rcx
0x18000282b  mov     esi, edx
0x18000282d  add     rcx, 10h; lpCriticalSection
0x180002831  call    cs:__imp_EnterCriticalSection
0x180002837  lea     rcx, [rdi+7Ch]; lpSystemTime
0x18000283b  mov     dword ptr [rdi+78h], 1
0x180002842  call    cs:__imp_GetSystemTime
0x180002848  lea     r14, [rdi+1A8h]
0x18000284f  mov     rbx, [r14]
0x180002852  jmp     short loc_18000289C
0x180002854  mov     rbp, rbx
0x180002857  mov     edx, esi; int
0x180002859  mov     rbx, [rbx+0C08h]
0x180002860  mov     rcx, rbp; lpCriticalSection
0x180002863  call    ?Close@CMulticastContent@@QEAAKH@Z; CMulticastContent::Close(int)
0x180002868  test    esi, esi
0x18000286a  jz      short loc_18000289C
0x18000286c  mov     rcx, rbp; lpCriticalSection
0x18000286f  call    ?Shutdown@CMulticastContent@@QEAAKXZ; CMulticastContent::Shutdown(void)
0x180002874  mov     rcx, rbp; lpCriticalSection
0x180002877  call    ?CanDelete@CMulticastContent@@QEAAHXZ; CMulticastContent::CanDelete(void)
0x18000287c  test    eax, eax
0x18000287e  jnz     short loc_18000289C
0x180002880  and     [rsp+48h+var_28], eax
0x180002884  lea     r8, aPcontentCandel; "pContent->CanDelete()"
0x18000288b  mov     edx, 136h; unsigned int
0x180002890  lea     rcx, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002897  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000289c  test    rbx, rbx
0x18000289f  jnz     short loc_180002854
0x1800028a1  test    esi, esi
0x1800028a3  jz      short loc_1800028F4
0x1800028a5  mov     rax, [r14]
0x1800028a8  test    rax, rax
0x1800028ab  jz      short loc_1800028F4
0x1800028ad  mov     [rsp+48h+arg_0], rax
0x1800028b2  lea     rdx, [rsp+48h+arg_0]
0x1800028b7  mov     rcx, r14
0x1800028ba  call    ?DeleteAt@?$CList@VCMulticastContent@@VCNoLock@@@@QEAAPEAVCMulticastContent@@AEAPEAX@Z; CList<CMulticastContent,CNoLock>::DeleteAt(void * &)
0x1800028bf  mov     rbx, rax
0x1800028c2  test    rax, rax
0x1800028c5  jz      short loc_1800028EC
0x1800028c7  mov     rcx, rax; lpCriticalSection
0x1800028ca  call    ?Shutdown@CMulticastContent@@QEAAKXZ; CMulticastContent::Shutdown(void)
0x1800028cf  lea     rcx, [rbx+138h]; this
0x1800028d6  call    ?Shutdown@CMcCoClients@@QEAAKXZ; CMcCoClients::Shutdown(void)
0x1800028db  mov     rcx, rbx; lpCriticalSection
0x1800028de  call    cs:__imp_DeleteCriticalSection
0x1800028e4  mov     rcx, rbx; void *
0x1800028e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028ec  cmp     [rsp+48h+arg_0], 0
0x1800028f2  jnz     short loc_1800028B2
0x1800028f4  mov     r8, [rdi+50h]
0x1800028f8  test    r8, r8
0x1800028fb  jz      short loc_180002935
0x1800028fd  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180002904  test    rax, rax
0x180002907  jz      short loc_18000291D
0x180002909  mov     edx, [rdi+38h]
0x18000290c  lea     rcx, aWdsmcnsUSClosi; "WDSMCNS[%u:%s] Closing..."
0x180002913  call    cs:__guard_dispatch_icall_fptr
0x180002919  mov     r8, [rdi+50h]; unsigned __int16 *
0x18000291d  mov     rcx, cs:qword_1800336E8
0x180002924  mov     edx, 2; unsigned int
0x180002929  add     rcx, 360h; this
0x180002930  call    ?AddNotification@CMulticastNotification@@QEAAKKPEBGPEAX@Z; CMulticastNotification::AddNotification(ulong,ushort const *,void *)
0x180002935  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002939  call    cs:__imp_LeaveCriticalSection
0x18000293f  mov     rbx, [rsp+48h+arg_8]
0x180002944  xor     eax, eax
0x180002946  mov     rbp, [rsp+48h+arg_10]
0x18000294b  mov     rsi, [rsp+48h+arg_18]
0x180002950  add     rsp, 30h
0x180002954  pop     r15
0x180002956  pop     r14
0x180002958  pop     rdi
0x180002959  retn
```
