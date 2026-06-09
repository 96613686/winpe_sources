# SXReader::SXReader(IMalloc *)

- ea: `0x100404210`
- end: `0x1004043b8`
- name: `??0SXReader@@IEAA@PEAUIMalloc@@@Z`
- size: `424`
- prototype: `SXReader *__fastcall(SXReader *__hidden this, struct IMalloc *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100404170`

## callees

- `0x100404210`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x10040438c`
- `KERNEL32!EnterCriticalSection` at `0x10040438c`
- `KERNEL32!LeaveCriticalSection` at `0x10040439f`
- `KERNEL32!LeaveCriticalSection` at `0x10040439f`
- `KERNEL32!GetTickCount` at `0x10040431d`
- `KERNEL32!GetTickCount` at `0x10040431d`

## pseudocode

```c
SXReader *__fastcall SXReader::SXReader(SXReader *this, struct IMalloc *a2)
{
  char *v4; // rcx
  DWORD TickCount; // eax

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &SXReadBase::`vftable';
  *((_QWORD *)this + 13) = a2;
  v4 = (char *)this + 128;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 14) = v4;
  *((_DWORD *)this + 31) = 10;
  memset(v4, 0, 0x1E0u);
  *((_QWORD *)this + 12) = &_stackZeroed<SXReadBase::XmlNsDecl,10>::`vftable';
  *((_QWORD *)this + 76) = 0;
  *((_DWORD *)this + 154) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_DWORD *)this + 162) = 0;
  *((_QWORD *)this + 92) = a2;
  *((_QWORD *)this + 93) = (char *)this + 760;
  *((_DWORD *)this + 188) = 0;
  *((_DWORD *)this + 189) = 10;
  memset((char *)this + 760, 0, 0x140u);
  *((_QWORD *)this + 91) = &_stackZeroed<ELEMENT_DATA,10>::`vftable';
  *((_QWORD *)this + 135) = &DataStream::`vftable';
  *((_QWORD *)this + 136) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_DWORD *)this + 276) = 0;
  *((_QWORD *)this + 147) = 0;
  *((_QWORD *)this + 148) = 0;
  *((_QWORD *)this + 149) = 0;
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_QWORD *)this + 155) = 0;
  *((_QWORD *)this + 159) = 0;
  TickCount = GetTickCount();
  *((_QWORD *)this + 136) = this;
  *((_DWORD *)this + 368) = 1;
  *((_BYTE *)this + 1476) = 0;
  *((_DWORD *)this + 20) = TickCount ^ ((TickCount ^ (TickCount << 7)) << 11);
  *(_QWORD *)this = &SXReader::`vftable'{for `SXReadBase'};
  *((_QWORD *)this + 182) = &SXReader::`vftable'{for `ISAXXMLReader'};
  *((_QWORD *)this + 183) = &SXReader::`vftable'{for `ISAXLocator'};
  if ( a2 )
    ((void (__fastcall *)(struct IMalloc *))a2->lpVtbl->AddRef)(a2);
  EnterCriticalSection(&s_cs);
  ++s_cComponents;
  LeaveCriticalSection(&s_cs);
  return this;
}

```

## disassembly

```asm
0x100404210  mov     [rsp+arg_0], rbx
0x100404215  mov     [rsp+arg_8], rsi
0x10040421a  push    rdi
0x10040421b  sub     rsp, 20h
0x10040421f  mov     rbx, rcx
0x100404222  mov     [rcx+8], rdx
0x100404226  lea     rax, ??_7SXReadBase@@6B@; const SXReadBase::`vftable'
0x10040422d  mov     rdi, rdx
0x100404230  mov     [rcx], rax
0x100404233  xor     esi, esi
0x100404235  mov     [rcx+68h], rdx
0x100404239  mov     r8d, 1E0h; Size
0x10040423f  sub     rcx, 0FFFFFFFFFFFFFF80h; void *
0x100404243  mov     [rbx+78h], esi
0x100404246  xor     edx, edx; Val
0x100404248  mov     [rbx+70h], rcx
0x10040424c  mov     dword ptr [rbx+7Ch], 0Ah
0x100404253  call    memset
0x100404258  lea     rax, ??_7?$_stackZeroed@UXmlNsDecl@SXReadBase@@$09@@6B@; const _stackZeroed<SXReadBase::XmlNsDecl,10>::`vftable'
0x10040425f  xor     edx, edx; Val
0x100404261  mov     [rbx+60h], rax
0x100404265  lea     rcx, [rbx+2F8h]; void *
0x10040426c  mov     r8d, 140h; Size
0x100404272  mov     [rbx+260h], rsi
0x100404279  mov     [rbx+268h], esi
0x10040427f  mov     [rbx+270h], rsi
0x100404286  mov     [rbx+278h], esi
0x10040428c  mov     [rbx+280h], rsi
0x100404293  mov     [rbx+288h], esi
0x100404299  mov     [rbx+2E0h], rdi
0x1004042a0  mov     [rbx+2E8h], rcx
0x1004042a7  mov     [rbx+2F0h], esi
0x1004042ad  mov     dword ptr [rbx+2F4h], 0Ah
0x1004042b7  call    memset
0x1004042bc  lea     rax, ??_7?$_stackZeroed@UELEMENT_DATA@@$09@@6B@; const _stackZeroed<ELEMENT_DATA,10>::`vftable'
0x1004042c3  mov     [rbx+2D8h], rax
0x1004042ca  lea     rax, ??_7DataStream@@6B@; const DataStream::`vftable'
0x1004042d1  mov     [rbx+438h], rax
0x1004042d8  mov     [rbx+440h], rsi
0x1004042df  mov     [rbx+448h], rsi
0x1004042e6  mov     [rbx+450h], esi
0x1004042ec  mov     [rbx+498h], rsi
0x1004042f3  mov     [rbx+4A0h], rsi
0x1004042fa  mov     [rbx+4A8h], rsi
0x100404301  mov     [rbx+4C8h], rsi
0x100404308  mov     [rbx+4D0h], rsi
0x10040430f  mov     [rbx+4D8h], rsi
0x100404316  mov     [rbx+4F8h], rsi
0x10040431d  call    cs:__imp_GetTickCount
0x100404323  mov     ecx, eax
0x100404325  mov     [rbx+440h], rbx
0x10040432c  shl     ecx, 7
0x10040432f  xor     ecx, eax
0x100404331  mov     dword ptr [rbx+5C0h], 1
0x10040433b  shl     ecx, 0Bh
0x10040433e  xor     ecx, eax
0x100404340  mov     [rbx+5C4h], sil
0x100404347  mov     [rbx+50h], ecx
0x10040434a  lea     rax, ??_7SXReader@@6BSXReadBase@@@; const SXReader::`vftable'{for `SXReadBase'}
0x100404351  mov     [rbx], rax
0x100404354  lea     rax, ??_7SXReader@@6BISAXXMLReader@@@; const SXReader::`vftable'{for `ISAXXMLReader'}
0x10040435b  mov     [rbx+5B0h], rax
0x100404362  lea     rax, ??_7SXReader@@6BISAXLocator@@@; const SXReader::`vftable'{for `ISAXLocator'}
0x100404369  mov     [rbx+5B8h], rax
0x100404370  test    rdi, rdi
0x100404373  jz      short loc_100404385
0x100404375  mov     rax, [rdi]
0x100404378  mov     rcx, rdi
0x10040437b  mov     rax, [rax+8]
0x10040437f  call    cs:__guard_dispatch_icall_fptr
0x100404385  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040438c  call    cs:__imp_EnterCriticalSection
0x100404392  inc     cs:?s_cComponents@@3JA; long s_cComponents
0x100404398  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x10040439f  call    cs:__imp_LeaveCriticalSection
0x1004043a5  mov     rsi, [rsp+28h+arg_8]
0x1004043aa  mov     rax, rbx
0x1004043ad  mov     rbx, [rsp+28h+arg_0]
0x1004043b2  add     rsp, 20h
0x1004043b6  pop     rdi
0x1004043b7  retn
```
