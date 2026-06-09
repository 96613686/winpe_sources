# CRegEndpoint::~CRegEndpoint(void)

- ea: `0x180014138`
- end: `0x1800141b6`
- name: `??1CRegEndpoint@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CRegEndpoint *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800141c0`
- `0x180014758`
- `0x180015730`

## callees

- `0x180014138`
- `0x18001d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014199`
- `KERNEL32!DeleteCriticalSection` at `0x180014199`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180014189`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180014189`

## pseudocode

```c
void __fastcall CRegEndpoint::~CRegEndpoint(CRegEndpoint *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CRegEndpoint::`vftable';
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 8) = 0;
  }
  if ( *((_DWORD *)this + 14) )
    WdsAssert("base\\eco\\wds\\wdssrv\\server\\src\\regendpoint.cpp", 0x74u, "m_uPendingRequests == 0", 1, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x180014138  push    rbx
0x18001413a  sub     rsp, 30h
0x18001413e  lea     rax, ??_7CRegEndpoint@@6B@; const CRegEndpoint::`vftable'
0x180014145  mov     rbx, rcx
0x180014148  mov     [rcx], rax
0x18001414b  mov     rcx, [rcx+40h]
0x18001414f  test    rcx, rcx
0x180014152  jz      short loc_180014165
0x180014154  mov     rax, [rcx]
0x180014157  mov     rax, [rax+8]
0x18001415b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014160  and     qword ptr [rbx+40h], 0
0x180014165  mov     eax, [rbx+38h]
0x180014168  test    eax, eax
0x18001416a  jz      short loc_180014195
0x18001416c  and     [rsp+38h+var_18], 0
0x180014171  lea     r8, aMUpendingreque; "m_uPendingRequests == 0"
0x180014178  mov     r9d, 1
0x18001417e  lea     rcx, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\server\\src\\re"...
0x180014185  lea     edx, [r9+73h]
0x180014189  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180014190  nop     dword ptr [rax+rax+00h]
0x180014195  lea     rcx, [rbx+10h]; lpCriticalSection
0x180014199  call    cs:__imp_DeleteCriticalSection
0x1800141a0  nop     dword ptr [rax+rax+00h]
0x1800141a5  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1800141ac  mov     [rbx], rax
0x1800141af  add     rsp, 30h
0x1800141b3  pop     rbx
0x1800141b4  retn
```
