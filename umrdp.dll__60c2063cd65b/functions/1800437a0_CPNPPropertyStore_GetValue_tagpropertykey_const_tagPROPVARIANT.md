# CPNPPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x1800437a0`
- end: `0x180043875`
- name: `?GetValue@CPNPPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CPNPPropertyStore *__hidden this, const struct _tagpropertykey *, PROPVARIANT *pvarDest)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x180042e90`
- `0x1800437a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800437ec`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800437ec`

## string_xrefs

- `0x18004381c`: `PropVariantCopy FAILED`

## pseudocode

```c
__int64 __fastcall CPNPPropertyStore::GetValue(
        CPNPPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *pvarDest)
{
  struct tagPROP_ENTRY *Internal; // rax
  HRESULT v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v10; // [rsp+50h] [rbp+18h] BYREF

  if ( !pvarDest )
    return 2147500035LL;
  v10 = (char *)this + 56;
  CTSCriticalSection::Lock((CPNPPropertyStore *)((char *)this + 56));
  Internal = CPNPPropertyStore::FindInternal(this, a2);
  if ( Internal )
  {
    v8 = PropVariantCopy(pvarDest, (const PROPVARIANT *)Internal + 5);
    if ( v8 < 0
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        13,
        (unsigned int)WPP_5f88aba614d73b89cb99d805b1377907_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"PropVariantCopy FAILED",
        v8);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v10);
    return (unsigned int)v8;
  }
  else
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v10);
    return 0;
  }
}

```

## disassembly

```asm
0x1800437a0  mov     [rsp+arg_0], rbx
0x1800437a5  mov     [rsp+arg_8], rsi
0x1800437aa  push    rdi
0x1800437ab  sub     rsp, 30h
0x1800437af  mov     rbx, r8
0x1800437b2  mov     rsi, rdx
0x1800437b5  mov     rdi, rcx
0x1800437b8  test    r8, r8
0x1800437bb  jnz     short loc_1800437C7
0x1800437bd  mov     eax, 80004003h
0x1800437c2  jmp     loc_180043865
0x1800437c7  add     rcx, 38h ; '8'; this
0x1800437cb  mov     [rsp+38h+arg_10], rcx
0x1800437d0  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800437d5  mov     rdx, rsi; struct _tagpropertykey *
0x1800437d8  mov     rcx, rdi; this
0x1800437db  call    ?FindInternal@CPNPPropertyStore@@AEAAPEAUtagPROP_ENTRY@@AEBU_tagpropertykey@@@Z; CPNPPropertyStore::FindInternal(_tagpropertykey const &)
0x1800437e0  test    rax, rax
0x1800437e3  jz      short loc_180043859
0x1800437e5  lea     rdx, [rax+28h]; pvarSrc
0x1800437e9  mov     rcx, rbx; pvarDest
0x1800437ec  call    cs:__imp_PropVariantCopy
0x1800437f2  mov     ebx, eax
0x1800437f4  test    eax, eax
0x1800437f6  jns     short loc_18004384B
0x1800437f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437ff  lea     rax, WPP_GLOBAL_Control
0x180043806  cmp     rcx, rax
0x180043809  jz      short loc_18004384B
0x18004380b  test    byte ptr [rcx+1Ch], 8
0x18004380f  jz      short loc_18004384B
0x180043811  cmp     byte ptr [rcx+19h], 2
0x180043815  jb      short loc_18004384B
0x180043817  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004381c  lea     rcx, aPropvariantcop_0; "PropVariantCopy FAILED"
0x180043823  mov     [rsp+38h+var_10], ebx
0x180043827  mov     [rsp+38h+var_18], rcx
0x18004382c  lea     r8, WPP_5f88aba614d73b89cb99d805b1377907_Traceguids
0x180043833  mov     rcx, cs:WPP_GLOBAL_Control
0x18004383a  mov     edx, 0Dh
0x18004383f  mov     r9d, eax
0x180043842  mov     rcx, [rcx+10h]
0x180043846  call    WPP_SF_DsD
0x18004384b  lea     rcx, [rsp+38h+arg_10]; this
0x180043850  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180043855  mov     eax, ebx
0x180043857  jmp     short loc_180043865
0x180043859  lea     rcx, [rsp+38h+arg_10]; this
0x18004385e  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180043863  xor     eax, eax
0x180043865  mov     rbx, [rsp+38h+arg_0]
0x18004386a  mov     rsi, [rsp+38h+arg_8]
0x18004386f  add     rsp, 30h
0x180043873  pop     rdi
0x180043874  retn
```
