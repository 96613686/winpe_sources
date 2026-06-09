# CApSrvDataState::Initialize(CMulticastSession *,CTransportServer *)

- ea: `0x18000ce38`
- end: `0x18000cf97`
- name: `?Initialize@CApSrvDataState@@QEAAKPEAVCMulticastSession@@PEAVCTransportServer@@@Z`
- size: `351`
- prototype: `unsigned int(CApSrvDataState *__hidden this, struct CMulticastSession *, struct CTransportServer *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016e70`

## callees

- `0x18000a160`
- `0x18000ce38`
- `0x1800248d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000ced0`
- `KERNEL32!CreateEventW` at `0x18000ced0`
- `KERNEL32!GetLastError` at `0x18000cedf`
- `KERNEL32!GetLastError` at `0x18000cedf`
- `KERNEL32!LeaveCriticalSection` at `0x18000ce98`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf66`
- `KERNEL32!LeaveCriticalSection` at `0x18000ce98`
- `KERNEL32!LeaveCriticalSection` at `0x18000cf66`
- `KERNEL32!EnterCriticalSection` at `0x18000ce7b`
- `KERNEL32!EnterCriticalSection` at `0x18000ceb4`
- `KERNEL32!EnterCriticalSection` at `0x18000ce7b`
- `KERNEL32!EnterCriticalSection` at `0x18000ceb4`

## string_xrefs

- `0x18000cf29`: `base\eco\wds\transport\server\mc\contentcache.cpp`
- `0x18000cf52`: `base\eco\wds\transport\server\mc\contentcache.cpp`

## pseudocode

```c
__int64 __fastcall CApSrvDataState::Initialize(
        CApSrvDataState *this,
        struct CMulticastSession *a2,
        struct _RTL_CRITICAL_SECTION *a3)
{
  int DebugInfo_high; // edi
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rbx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  const char *v11; // rdx
  const char *v12; // rdx
  unsigned int ContentSize; // ebx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx

  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 1) = (char *)a2 + 8;
  *((_QWORD *)this + 3) = a3;
  *((_QWORD *)this + 168) = (char *)a2 + 104;
  *((_QWORD *)this + 33) = *((_QWORD *)a2 + 11);
  EnterCriticalSection(a3);
  if ( LODWORD(a3[1].LockSemaphore) == 16 )
    DebugInfo_high = HIDWORD(a3[60].DebugInfo);
  else
    DebugInfo_high = (int)a3[60].DebugInfo;
  LeaveCriticalSection(a3);
  *((_DWORD *)this + 70) = DebugInfo_high;
  v6 = *((_QWORD *)this + 2);
  v7 = *(_QWORD *)(v6 + 80);
  v8 = *(_QWORD *)(v6 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_QWORD *)this + 9) = v6;
  *((_QWORD *)this + 10) = v8;
  *((_QWORD *)this + 11) = v7;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 14) = EventW;
  if ( EventW )
  {
    ContentSize = CMRSWLock::Initialize((CApSrvDataState *)((char *)this + 120));
    ElValidateWin32(ContentSize, v14, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD9u);
  }
  else
  {
    LastError = GetLastError();
    ContentSize = ElValidateWin32(LastError, v11, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD5u);
    if ( !ContentSize )
      ContentSize = 31;
  }
  if ( !ElValidateWin32(ContentSize, v12, "base\\eco\\wds\\transport\\server\\mc\\contentcache.cpp", 0x49u) )
  {
    ContentSize = CContentProvider::GetContentSize(
                    *((LPCRITICAL_SECTION *)this + 10),
                    *((void **)this + 11),
                    (unsigned __int64 *)this + 12);
    ElValidateWin32(ContentSize, v15, "base\\eco\\wds\\transport\\server\\mc\\contentcache.cpp", 0x4Du);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ElValidateWin32(ContentSize, v16, "base\\eco\\wds\\transport\\server\\mc\\apsrvdatastate.cpp", 0x55u);
  return ContentSize;
}

```

## disassembly

```asm
0x18000ce38  mov     [rsp+arg_0], rbx
0x18000ce3d  mov     [rsp+arg_8], rbp
0x18000ce42  mov     [rsp+arg_10], rsi
0x18000ce47  push    rdi
0x18000ce48  sub     rsp, 20h
0x18000ce4c  lea     rax, [rdx+8]
0x18000ce50  mov     [rcx+10h], rdx
0x18000ce54  mov     [rcx+8], rax
0x18000ce58  mov     rbx, r8
0x18000ce5b  lea     rax, [rdx+68h]
0x18000ce5f  mov     [rcx+18h], rbx
0x18000ce63  mov     [rcx+540h], rax
0x18000ce6a  mov     rbp, rcx
0x18000ce6d  mov     rax, [rdx+58h]
0x18000ce71  mov     [rcx+108h], rax
0x18000ce78  mov     rcx, r8; lpCriticalSection
0x18000ce7b  call    cs:__imp_EnterCriticalSection
0x18000ce81  cmp     dword ptr [rbx+40h], 10h
0x18000ce85  jnz     short loc_18000CE8F
0x18000ce87  mov     edi, [rbx+964h]
0x18000ce8d  jmp     short loc_18000CE95
0x18000ce8f  mov     edi, [rbx+960h]
0x18000ce95  mov     rcx, rbx; lpCriticalSection
0x18000ce98  call    cs:__imp_LeaveCriticalSection
0x18000ce9e  mov     [rbp+118h], edi
0x18000cea4  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000cea8  mov     rdi, [rbp+10h]
0x18000ceac  mov     rsi, [rdi+50h]
0x18000ceb0  mov     rbx, [rdi+48h]
0x18000ceb4  call    cs:__imp_EnterCriticalSection
0x18000ceba  xor     r9d, r9d; lpName
0x18000cebd  mov     [rbp+48h], rdi
0x18000cec1  xor     r8d, r8d; bInitialState
0x18000cec4  mov     [rbp+50h], rbx
0x18000cec8  xor     edx, edx; bManualReset
0x18000ceca  mov     [rbp+58h], rsi
0x18000cece  xor     ecx, ecx; lpEventAttributes
0x18000ced0  call    cs:__imp_CreateEventW
0x18000ced6  mov     [rbp+70h], rax
0x18000ceda  test    rax, rax
0x18000cedd  jnz     short loc_18000CF04
0x18000cedf  call    cs:__imp_GetLastError
0x18000cee5  mov     r9d, 0D5h; unsigned int
0x18000ceeb  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x18000cef2  mov     ecx, eax; unsigned int
0x18000cef4  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cef9  mov     ebx, eax
0x18000cefb  test    eax, eax
0x18000cefd  jnz     short loc_18000CF23
0x18000ceff  lea     ebx, [rax+1Fh]
0x18000cf02  jmp     short loc_18000CF23
0x18000cf04  lea     rcx, [rbp+78h]; this
0x18000cf08  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18000cf0d  mov     r9d, 0D9h; unsigned int
0x18000cf13  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x18000cf1a  mov     ecx, eax; unsigned int
0x18000cf1c  mov     ebx, eax
0x18000cf1e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cf23  mov     r9d, 49h ; 'I'; unsigned int
0x18000cf29  lea     r8, aBaseEcoWdsTran_23; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000cf30  mov     ecx, ebx; unsigned int
0x18000cf32  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cf37  test    eax, eax
0x18000cf39  jnz     short loc_18000CF62
0x18000cf3b  mov     rdx, [rbp+58h]; void *
0x18000cf3f  lea     r8, [rbp+60h]; unsigned __int64 *
0x18000cf43  mov     rcx, [rbp+50h]; lpCriticalSection
0x18000cf47  call    ?GetContentSize@CContentProvider@@QEAAKPEAXPEA_K@Z; CContentProvider::GetContentSize(void *,unsigned __int64 *)
0x18000cf4c  mov     r9d, 4Dh ; 'M'; unsigned int
0x18000cf52  lea     r8, aBaseEcoWdsTran_23; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000cf59  mov     ecx, eax; unsigned int
0x18000cf5b  mov     ebx, eax
0x18000cf5d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cf62  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000cf66  call    cs:__imp_LeaveCriticalSection
0x18000cf6c  mov     r9d, 55h ; 'U'; unsigned int
0x18000cf72  lea     r8, aBaseEcoWdsTran_24; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000cf79  mov     ecx, ebx; unsigned int
0x18000cf7b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000cf80  mov     rbp, [rsp+28h+arg_8]
0x18000cf85  mov     eax, ebx
0x18000cf87  mov     rbx, [rsp+28h+arg_0]
0x18000cf8c  mov     rsi, [rsp+28h+arg_10]
0x18000cf91  add     rsp, 20h
0x18000cf95  pop     rdi
0x18000cf96  retn
```
