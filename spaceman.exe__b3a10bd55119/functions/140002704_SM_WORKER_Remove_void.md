# SM_WORKER::Remove(void)

- ea: `0x140002704`
- end: `0x1400027d3`
- name: `?Remove@SM_WORKER@@QEAAPEAU_SU_WORK_OBJECT@@XZ`
- size: `207`
- prototype: `DWORD *__fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140002230`

## callees

- `0x140001008`
- `0x140002704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000277a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000277a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002754`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002754`

## string_xrefs

- `0x14000271a`: `SM_WORKER::Remove`

## pseudocode

```c
DWORD *__fastcall SM_WORKER::Remove(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, __int64 a3, __int64 a4)
{
  LPCRITICAL_SECTION v5; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // [rsp+40h] [rbp+8h] BYREF
  const char *v13; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    v12 = 246;
    v13 = "SM_WORKER::Remove";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)lpCriticalSection,
      (__int64)byte_140010933,
      a3,
      a4,
      (const unsigned __int16 **)&v13,
      (__int64)&v12);
  }
  EnterCriticalSection(lpCriticalSection);
  v5 = lpCriticalSection + 1;
  DebugInfo = lpCriticalSection[1].DebugInfo;
  if ( DebugInfo->CriticalSection != &lpCriticalSection[1]
    || (v7 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&DebugInfo->Type,
        *(PRTL_CRITICAL_SECTION_DEBUG *)(*(_QWORD *)&DebugInfo->Type + 8LL) != DebugInfo) )
  {
    __fastfail(3u);
  }
  v5->DebugInfo = v7;
  v7->CriticalSection = v5;
  LeaveCriticalSection(lpCriticalSection);
  if ( (unsigned int)dword_140014048 > 5 )
  {
    v12 = 258;
    v13 = "SM_WORKER::Remove";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (__int64)qword_140010A78,
      v9,
      v10,
      (const unsigned __int16 **)&v13,
      (__int64)&v12);
  }
  return &DebugInfo[-1].Flags;
}

```

## disassembly

```asm
0x140002704  mov     r11, rsp
0x140002707  mov     [r11+18h], rbx
0x14000270b  mov     [r11+20h], rsi
0x14000270f  push    rdi
0x140002710  sub     rsp, 30h
0x140002714  mov     eax, cs:dword_140014048
0x14000271a  lea     rsi, aSmWorkerRemove; "SM_WORKER::Remove"
0x140002721  mov     rdi, rcx
0x140002724  cmp     eax, 5
0x140002727  jbe     short loc_140002751
0x140002729  lea     rax, [r11+8]
0x14000272d  mov     [rsp+38h+arg_0], 0F6h
0x140002735  mov     [r11-10h], rax
0x140002739  lea     rdx, byte_140010933
0x140002740  lea     rax, [r11+10h]
0x140002744  mov     [r11+10h], rsi
0x140002748  mov     [r11-18h], rax
0x14000274c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002751  mov     rcx, rdi; lpCriticalSection
0x140002754  call    cs:__imp_EnterCriticalSection
0x14000275a  lea     rax, [rdi+28h]
0x14000275e  mov     rbx, [rax]
0x140002761  cmp     [rbx+8], rax
0x140002765  jnz     short loc_1400027CC
0x140002767  mov     rcx, [rbx]
0x14000276a  cmp     [rcx+8], rbx
0x14000276e  jnz     short loc_1400027CC
0x140002770  mov     [rax], rcx
0x140002773  mov     [rcx+8], rax
0x140002777  mov     rcx, rdi; lpCriticalSection
0x14000277a  call    cs:__imp_LeaveCriticalSection
0x140002780  mov     eax, cs:dword_140014048
0x140002786  cmp     eax, 5
0x140002789  jbe     short loc_1400027B8
0x14000278b  lea     rax, [rsp+38h+arg_0]
0x140002790  mov     [rsp+38h+arg_0], 102h
0x140002798  mov     [rsp+38h+var_10], rax
0x14000279d  lea     rdx, qword_140010A78
0x1400027a4  lea     rax, [rsp+38h+arg_8]
0x1400027a9  mov     [rsp+38h+arg_8], rsi
0x1400027ae  mov     [rsp+38h+var_18], rax
0x1400027b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400027b8  mov     rsi, [rsp+38h+arg_18]
0x1400027bd  lea     rax, [rbx-8]
0x1400027c1  mov     rbx, [rsp+38h+arg_10]
0x1400027c6  add     rsp, 30h
0x1400027ca  pop     rdi
0x1400027cb  retn
0x1400027cc  mov     ecx, 3
0x1400027d1  int     29h; Win8: RtlFailFast(ecx)
```
