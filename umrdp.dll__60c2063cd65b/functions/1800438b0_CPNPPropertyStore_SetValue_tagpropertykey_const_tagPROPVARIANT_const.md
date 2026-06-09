# CPNPPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x1800438b0`
- end: `0x180043a84`
- name: `?SetValue@CPNPPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CPNPPropertyStore *__hidden this, const struct _tagpropertykey *, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18001ba64`
- `0x180042e90`
- `0x1800438b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800438e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800438e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800439f2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004396c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180043a22`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004396c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180043a22`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043a16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043a16`

## string_xrefs

- `0x18004399c`: `PropVariantCopy failed`
- `0x180043a52`: `PropVariantCopy failed`

## pseudocode

```c
__int64 __fastcall CPNPPropertyStore::SetValue(
        CPNPPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *pvarSrc)
{
  struct tagPROP_ENTRY *Internal; // rax
  GUID *v7; // rax
  GUID *v8; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT v10; // ebx
  unsigned int v11; // eax
  GUID **v12; // rax
  PROPVARIANT *v14; // rbx
  unsigned int v15; // eax
  char *v16; // [rsp+60h] [rbp+8h] BYREF

  v16 = (char *)this + 56;
  CTSCriticalSection::Lock((CPNPPropertyStore *)((char *)this + 56));
  Internal = CPNPPropertyStore::FindInternal(this, a2);
  if ( !Internal )
  {
    v7 = (GUID *)CoTaskMemAlloc(0x40u);
    v8 = v7;
    if ( !v7 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          14,
          (unsigned int)WPP_5f88aba614d73b89cb99d805b1377907_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"PROP_ENTRY");
      }
      v10 = -2147024882;
      goto LABEL_17;
    }
    v7[1] = a2->fmtid;
    v7[2].Data1 = a2->pid;
    *(_OWORD *)v7[2].Data4 = 0;
    *(_QWORD *)v7[3].Data4 = 0;
    v10 = PropVariantCopy((PROPVARIANT *)v7[2].Data4, pvarSrc);
    if ( v10 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)WPP_5f88aba614d73b89cb99d805b1377907_Traceguids,
          v11,
          (__int64)"PropVariantCopy failed",
          v10);
      }
      goto LABEL_16;
    }
    v12 = (GUID **)*((_QWORD *)this + 11);
    *(_QWORD *)&v8->Data1 = (char *)this + 80;
    *(_QWORD *)v8->Data4 = v12;
    *v12 = v8;
    ++*((_DWORD *)this + 18);
    *((_QWORD *)this + 11) = v8;
LABEL_14:
    if ( !v10 || !v8 )
      goto LABEL_17;
LABEL_16:
    CoTaskMemFree(v8);
    goto LABEL_17;
  }
  v14 = (PROPVARIANT *)((char *)Internal + 40);
  v8 = 0;
  PropVariantClear((PROPVARIANT *)Internal + 5);
  v10 = PropVariantCopy(v14, pvarSrc);
  if ( v10 >= 0 )
    goto LABEL_14;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      16,
      (unsigned int)WPP_5f88aba614d73b89cb99d805b1377907_Traceguids,
      v15,
      (__int64)"PropVariantCopy failed",
      v10);
  }
LABEL_17:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800438b0  push    rbx
0x1800438b2  push    rbp
0x1800438b3  push    rsi
0x1800438b4  push    rdi
0x1800438b5  sub     rsp, 38h
0x1800438b9  mov     rsi, rcx
0x1800438bc  mov     rbp, r8
0x1800438bf  add     rcx, 38h ; '8'; this
0x1800438c3  mov     rbx, rdx
0x1800438c6  mov     [rsp+58h+arg_0], rcx
0x1800438cb  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800438d0  mov     rdx, rbx; struct _tagpropertykey *
0x1800438d3  mov     rcx, rsi; this
0x1800438d6  call    ?FindInternal@CPNPPropertyStore@@AEAAPEAUtagPROP_ENTRY@@AEBU_tagpropertykey@@@Z; CPNPPropertyStore::FindInternal(_tagpropertykey const &)
0x1800438db  test    rax, rax
0x1800438de  jnz     loc_180043A0D
0x1800438e4  lea     ecx, [rax+40h]; cb
0x1800438e7  call    cs:__imp_CoTaskMemAlloc
0x1800438ed  mov     rdi, rax
0x1800438f0  test    rax, rax
0x1800438f3  jnz     short loc_18004394C
0x1800438f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438fc  lea     rax, WPP_GLOBAL_Control
0x180043903  cmp     rcx, rax
0x180043906  jz      short loc_180043942
0x180043908  test    byte ptr [rcx+1Ch], 8
0x18004390c  jz      short loc_180043942
0x18004390e  cmp     byte ptr [rcx+19h], 2
0x180043912  jb      short loc_180043942
0x180043914  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043919  lea     rcx, aPropEntry; "PROP_ENTRY"
0x180043920  mov     r9d, eax
0x180043923  mov     [rsp+58h+var_38], rcx
0x180043928  lea     edx, [rdi+0Eh]
0x18004392b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043932  lea     r8, WPP_5f88aba614d73b89cb99d805b1377907_Traceguids
0x180043939  mov     rcx, [rcx+10h]
0x18004393d  call    WPP_SF_Ds
0x180043942  mov     ebx, 8007000Eh
0x180043947  jmp     loc_1800439F8
0x18004394c  movups  xmm0, xmmword ptr [rbx]
0x18004394f  lea     rcx, [rdi+28h]; pvarDest
0x180043953  mov     rdx, rbp; pvarSrc
0x180043956  movups  xmmword ptr [rax+10h], xmm0
0x18004395a  mov     eax, [rbx+10h]
0x18004395d  mov     [rdi+20h], eax
0x180043960  xorps   xmm0, xmm0
0x180043963  xor     eax, eax
0x180043965  movups  xmmword ptr [rcx], xmm0
0x180043968  mov     [rcx+10h], rax
0x18004396c  call    cs:__imp_PropVariantCopy
0x180043972  mov     ebx, eax
0x180043974  test    eax, eax
0x180043976  jns     short loc_1800439CD
0x180043978  mov     rcx, cs:WPP_GLOBAL_Control
0x18004397f  lea     rax, WPP_GLOBAL_Control
0x180043986  cmp     rcx, rax
0x180043989  jz      short loc_1800439EF
0x18004398b  test    byte ptr [rcx+1Ch], 8
0x18004398f  jz      short loc_1800439EF
0x180043991  cmp     byte ptr [rcx+19h], 2
0x180043995  jb      short loc_1800439EF
0x180043997  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004399c  lea     rcx, aPropvariantcop_1; "PropVariantCopy failed"
0x1800439a3  mov     [rsp+58h+var_30], ebx
0x1800439a7  mov     [rsp+58h+var_38], rcx
0x1800439ac  lea     r8, WPP_5f88aba614d73b89cb99d805b1377907_Traceguids
0x1800439b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439ba  mov     edx, 0Fh
0x1800439bf  mov     r9d, eax
0x1800439c2  mov     rcx, [rcx+10h]
0x1800439c6  call    WPP_SF_DsD
0x1800439cb  jmp     short loc_1800439EF
0x1800439cd  lea     rcx, [rsi+50h]
0x1800439d1  mov     rax, [rcx+8]
0x1800439d5  mov     [rdi], rcx
0x1800439d8  mov     [rdi+8], rax
0x1800439dc  mov     [rax], rdi
0x1800439df  inc     dword ptr [rsi+48h]
0x1800439e2  mov     [rcx+8], rdi
0x1800439e6  test    ebx, ebx
0x1800439e8  jz      short loc_1800439F8
0x1800439ea  test    rdi, rdi
0x1800439ed  jz      short loc_1800439F8
0x1800439ef  mov     rcx, rdi; pv
0x1800439f2  call    cs:__imp_CoTaskMemFree
0x1800439f8  lea     rcx, [rsp+58h+arg_0]; this
0x1800439fd  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180043a02  mov     eax, ebx
0x180043a04  add     rsp, 38h
0x180043a08  pop     rdi
0x180043a09  pop     rsi
0x180043a0a  pop     rbp
0x180043a0b  pop     rbx
0x180043a0c  retn
0x180043a0d  lea     rbx, [rax+28h]
0x180043a11  xor     edi, edi
0x180043a13  mov     rcx, rbx; pvar
0x180043a16  call    cs:__imp_PropVariantClear
0x180043a1c  mov     rdx, rbp; pvarSrc
0x180043a1f  mov     rcx, rbx; pvarDest
0x180043a22  call    cs:__imp_PropVariantCopy
0x180043a28  mov     ebx, eax
0x180043a2a  test    eax, eax
0x180043a2c  jns     short loc_1800439E6
0x180043a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a35  lea     rax, WPP_GLOBAL_Control
0x180043a3c  cmp     rcx, rax
0x180043a3f  jz      short loc_1800439F8
0x180043a41  test    byte ptr [rcx+1Ch], 8
0x180043a45  jz      short loc_1800439F8
0x180043a47  cmp     byte ptr [rcx+19h], 2
0x180043a4b  jb      short loc_1800439F8
0x180043a4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043a52  lea     rcx, aPropvariantcop_1; "PropVariantCopy failed"
0x180043a59  mov     [rsp+58h+var_30], ebx
0x180043a5d  mov     [rsp+58h+var_38], rcx
0x180043a62  lea     edx, [rdi+10h]
0x180043a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a6c  lea     r8, WPP_5f88aba614d73b89cb99d805b1377907_Traceguids
0x180043a73  mov     r9d, eax
0x180043a76  mov     rcx, [rcx+10h]
0x180043a7a  call    WPP_SF_DsD
0x180043a7f  jmp     loc_1800439F8
```
