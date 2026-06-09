# CFilterImpContentHandler::GetChunk(tagSTAT_CHUNK *)

- ea: `0x18000ef7c`
- end: `0x18000f133`
- name: `?GetChunk@CFilterImpContentHandler@@QEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(CFilterImpContentHandler *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800073d0`

## callees

- `0x18000596c`
- `0x180008a10`
- `0x18000b724`
- `0x18000b744`
- `0x18000ef7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000efc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000eff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f0cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000eff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000f0cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f00b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f09a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f0a7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f00b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f09a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f0a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efdf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f0b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000efdf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000f0b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f021`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f021`

## string_xrefs

- `0x18000f030`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f05e`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f072`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::GetChunk():Could not resume parsing hr=%#x`
- `0x18000f07e`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::GetChunk(CFilterImpContentHandler *this, struct tagSTAT_CHUNK *a2)
{
  RTL_SRWLOCK *v4; // rbx
  _DWORD *v5; // rbp
  int LastError; // esi
  int v7; // r15d
  const char *v8; // r9
  int v9; // ebp
  ULONG v10; // ecx
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  TVarString<16>::Cpy((char *)this + 48, 0, byte_1800194F0);
  *((_DWORD *)this + 28) = 0;
  *((_BYTE *)this + 116) = 0;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  v5 = (_DWORD *)((char *)this + 56);
LABEL_4:
  LastError = 0;
  while ( !*((_BYTE *)this + 40) )
  {
    AcquireSRWLockShared(v4);
    v5 = (_DWORD *)((char *)this + 56);
    v7 = *((_DWORD *)this + 14);
    if ( v4 )
      ReleaseSRWLockShared(v4);
    if ( v7 )
    {
      if ( !*((_BYTE *)this + 40) )
        goto LABEL_21;
      break;
    }
    SetEvent(*((HANDLE *)this + 52));
    if ( *((_BYTE *)this + 40) )
      goto LABEL_4;
    if ( !WaitForSingleObject(*((HANDLE *)this + 51), 0xFFFFFFFF) )
    {
      LastError = *((_DWORD *)this + 106);
      if ( LastError >= 0 )
        goto LABEL_4;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
        (const char *)(unsigned int)LastError,
        v12);
LABEL_15:
      SearchIndexerTrace::Information(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
        (const wchar_t *)0x52,
        (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::GetChunk():Could not "
                       "resume parsing hr=%#x",
        (const wchar_t *)(unsigned int)LastError);
      LastError = -2147215616;
      *((_BYTE *)this + 40) = 1;
      SetEvent(*((HANDLE *)this + 52));
      SetEvent(*((HANDLE *)this + 51));
      return (unsigned int)LastError;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x69,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
                  v8);
    if ( LastError < 0 )
      goto LABEL_15;
  }
  AcquireSRWLockShared(v4);
  v9 = *v5 - *((_DWORD *)this + 28);
  if ( v4 )
    ReleaseSRWLockShared(v4);
  if ( !v9 )
    return (unsigned int)-2147215616;
LABEL_21:
  v10 = *((_DWORD *)this + 8);
  *((_DWORD *)this + 8) = v10 + 1;
  a2->idChunk = v10;
  a2->breakType = CHUNK_NO_BREAK;
  a2->flags = CHUNK_TEXT;
  a2->attribute.guidPropSet = (GUID)xmmword_18001AF20;
  a2->attribute.psProperty = (PROPSPEC)xmmword_18001AF30;
  a2->idChunkSource = v10;
  *(_QWORD *)&a2->cwcStartSource = 0;
  a2->locale = *((_DWORD *)this + 9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000ef7c  push    rbx
0x18000ef7e  push    rbp
0x18000ef7f  push    rsi
0x18000ef80  push    rdi
0x18000ef81  push    r14
0x18000ef83  push    r15
0x18000ef85  sub     rsp, 28h
0x18000ef89  mov     r14, rdx
0x18000ef8c  mov     rdi, rcx
0x18000ef8f  lea     rbx, [rcx+18h]
0x18000ef93  mov     rcx, rbx; SRWLock
0x18000ef96  call    cs:__imp_AcquireSRWLockExclusive
0x18000ef9c  mov     [rsp+58h+arg_0], rbx
0x18000efa1  lea     rcx, [rdi+30h]
0x18000efa5  lea     r8, byte_1800194F0
0x18000efac  xor     edx, edx
0x18000efae  call    ?Cpy@?$TVarString@$0BA@@@QEAAAEAV1@_KPEB_W@Z; TVarString<16>::Cpy(unsigned __int64,wchar_t const *)
0x18000efb3  mov     dword ptr [rdi+70h], 0
0x18000efba  mov     byte ptr [rdi+74h], 0
0x18000efbe  test    rbx, rbx
0x18000efc1  jz      short loc_18000EFCC
0x18000efc3  mov     rcx, rbx; SRWLock
0x18000efc6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000efcc  lea     rbp, [rdi+38h]
0x18000efd0  xor     esi, esi
0x18000efd2  cmp     byte ptr [rdi+28h], 0
0x18000efd6  jnz     loc_18000F0B5
0x18000efdc  mov     rcx, rbx; SRWLock
0x18000efdf  call    cs:__imp_AcquireSRWLockShared
0x18000efe5  lea     rbp, [rdi+38h]
0x18000efe9  mov     r15d, [rbp+0]
0x18000efed  test    rbx, rbx
0x18000eff0  jz      short loc_18000EFFB
0x18000eff2  mov     rcx, rbx; SRWLock
0x18000eff5  call    cs:__imp_ReleaseSRWLockShared
0x18000effb  test    r15d, r15d
0x18000effe  jnz     loc_18000F0AF
0x18000f004  mov     rcx, [rdi+1A0h]; hEvent
0x18000f00b  call    cs:__imp_SetEvent
0x18000f011  cmp     [rdi+28h], r15b
0x18000f015  jnz     short loc_18000EFD0
0x18000f017  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f01a  mov     rcx, [rdi+198h]; hHandle
0x18000f021  call    cs:__imp_WaitForSingleObject
0x18000f027  test    eax, eax
0x18000f029  jz      short loc_18000F048
0x18000f02b  mov     rcx, [rsp+58h]; this
0x18000f030  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f037  lea     edx, [r15+69h]; void *
0x18000f03b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f040  mov     esi, eax
0x18000f042  test    eax, eax
0x18000f044  js      short loc_18000F06F
0x18000f046  jmp     short loc_18000EFD2
0x18000f048  mov     esi, [rdi+1A8h]
0x18000f04e  test    esi, esi
0x18000f050  jns     loc_18000EFD0
0x18000f056  mov     rcx, [rsp+58h]; this
0x18000f05b  mov     r9d, esi; char *
0x18000f05e  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f065  mov     edx, 6Eh ; 'n'; void *
0x18000f06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f06f  mov     r9d, esi; wchar_t *
0x18000f072  lea     r8, aXmlfilterIfilt; "[XmlFilter IFilter implementation Conte"...
0x18000f079  mov     edx, 52h ; 'R'; wchar_t *
0x18000f07e  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f085  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000f08a  mov     esi, 80041700h
0x18000f08f  mov     byte ptr [rdi+28h], 1
0x18000f093  mov     rcx, [rdi+1A0h]; hEvent
0x18000f09a  call    cs:__imp_SetEvent
0x18000f0a0  mov     rcx, [rdi+198h]; hEvent
0x18000f0a7  call    cs:__imp_SetEvent
0x18000f0ad  jmp     short loc_18000F124
0x18000f0af  cmp     byte ptr [rdi+28h], 0
0x18000f0b3  jz      short loc_18000F0DD
0x18000f0b5  mov     rcx, rbx; SRWLock
0x18000f0b8  call    cs:__imp_AcquireSRWLockShared
0x18000f0be  mov     ebp, [rbp+0]
0x18000f0c1  sub     ebp, [rdi+70h]
0x18000f0c4  test    rbx, rbx
0x18000f0c7  jz      short loc_18000F0D2
0x18000f0c9  mov     rcx, rbx; SRWLock
0x18000f0cc  call    cs:__imp_ReleaseSRWLockShared
0x18000f0d2  test    ebp, ebp
0x18000f0d4  jnz     short loc_18000F0DD
0x18000f0d6  mov     esi, 80041700h
0x18000f0db  jmp     short loc_18000F124
0x18000f0dd  mov     ecx, [rdi+20h]
0x18000f0e0  lea     eax, [rcx+1]
0x18000f0e3  mov     [rdi+20h], eax
0x18000f0e6  mov     [r14], ecx
0x18000f0e9  mov     dword ptr [r14+4], 0
0x18000f0f1  mov     dword ptr [r14+8], 1
0x18000f0f9  movups  xmm0, cs:xmmword_18001AF20
0x18000f100  movups  xmmword ptr [r14+10h], xmm0
0x18000f105  movups  xmm1, cs:xmmword_18001AF30
0x18000f10c  movups  xmmword ptr [r14+20h], xmm1
0x18000f111  mov     [r14+30h], ecx
0x18000f115  mov     qword ptr [r14+34h], 0
0x18000f11d  mov     ecx, [rdi+24h]
0x18000f120  mov     [r14+0Ch], ecx
0x18000f124  mov     eax, esi
0x18000f126  add     rsp, 28h
0x18000f12a  pop     r15
0x18000f12c  pop     r14
0x18000f12e  pop     rdi
0x18000f12f  pop     rsi
0x18000f130  pop     rbp
0x18000f131  pop     rbx
0x18000f132  retn
```
