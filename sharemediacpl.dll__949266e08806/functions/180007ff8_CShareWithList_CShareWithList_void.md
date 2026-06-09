# CShareWithList::~CShareWithList(void)

- ea: `0x180007ff8`
- end: `0x1800080c3`
- name: `??1CShareWithList@@AEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CShareWithList *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d0b0`

## callees

- `0x180003860`
- `0x180007ff8`
- `0x180016414`
- `0x18001e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000808b`
- `KERNEL32!DeleteCriticalSection` at `0x18000808b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180008079`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180008079`

## pseudocode

```c
void __fastcall CShareWithList::~CShareWithList(CShareWithList *this)
{
  __int64 v2; // rcx
  struct _DPA *v3; // rcx
  DirectUI::DUIXmlParser *v4; // rcx

  *(_QWORD *)this = &CShareWithList::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    *((_QWORD *)this + 5) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = (struct _DPA *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    DPA_Destroy(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    DirectUI::DUIXmlParser::Destroy(v4);
    *((_QWORD *)this + 4) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
}

```

## disassembly

```asm
0x180007ff8  mov     [rsp+arg_0], rbx
0x180007ffd  push    rsi
0x180007ffe  sub     rsp, 20h
0x180008002  lea     rax, ??_7CShareWithList@@6B@; const CShareWithList::`vftable'
0x180008009  mov     rbx, rcx
0x18000800c  mov     [rcx], rax
0x18000800f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008016  lea     rsi, WPP_GLOBAL_Control
0x18000801d  cmp     rcx, rsi
0x180008020  jz      short loc_18000803D
0x180008022  test    byte ptr [rcx+1Ch], 20h
0x180008026  jz      short loc_18000803D
0x180008028  mov     rcx, [rcx+10h]
0x18000802c  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180008033  mov     edx, 66h ; 'f'
0x180008038  call    WPP_SF_
0x18000803d  mov     rcx, [rbx+28h]
0x180008041  test    rcx, rcx
0x180008044  jz      short loc_18000805A
0x180008046  mov     qword ptr [rbx+28h], 0
0x18000804e  mov     rax, [rcx]
0x180008051  mov     rax, [rax+10h]
0x180008055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805a  mov     rcx, [rbx+18h]; hdpa
0x18000805e  test    rcx, rcx
0x180008061  jz      short loc_180008070
0x180008063  call    DPA_Destroy
0x180008068  mov     qword ptr [rbx+18h], 0
0x180008070  mov     rcx, [rbx+20h]
0x180008074  test    rcx, rcx
0x180008077  jz      short loc_180008087
0x180008079  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000807f  mov     qword ptr [rbx+20h], 0
0x180008087  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000808b  call    cs:__imp_DeleteCriticalSection
0x180008091  mov     rcx, cs:WPP_GLOBAL_Control
0x180008098  cmp     rcx, rsi
0x18000809b  jz      short loc_1800080B8
0x18000809d  test    byte ptr [rcx+1Ch], 20h
0x1800080a1  jz      short loc_1800080B8
0x1800080a3  mov     rcx, [rcx+10h]
0x1800080a7  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800080ae  mov     edx, 67h ; 'g'
0x1800080b3  call    WPP_SF_
0x1800080b8  mov     rbx, [rsp+28h+arg_0]
0x1800080bd  add     rsp, 20h
0x1800080c1  pop     rsi
0x1800080c2  retn
```
