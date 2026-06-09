# VhdmpiDismountDependenciesForUnsurface(_VHD_SURFACE *)

- ea: `0x1400ba8e8`
- end: `0x1400bab3b`
- name: `?VhdmpiDismountDependenciesForUnsurface@@YAXPEAU_VHD_SURFACE@@@Z`
- size: `595`
- prototype: `void __fastcall(struct _VHD_SURFACE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400bbd54`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001bc1c`
- `0x14001c088`
- `0x14001dfd4`
- `0x140023980`
- `0x140036284`
- `0x14005dbb0`
- `0x1400ba8e8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400ba952`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400ba952`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400bab09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400bab09`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ba970`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ba970`
- `FSDEPENDS!DependentFSDismountForUnsurface` at `0x1400ba9fb`
- `FSDEPENDS!DependentFSDismountForUnsurface` at `0x1400ba9fb`

## string_xrefs

- `0x1400baae3`: `Vhdmpi: returned 0x%x from DependentFSDismountForUnsurface for disk %p`
- `0x1400baaea`: `VhdmpiDismountDependenciesForUnsurface`

## pseudocode

```c
void __fastcall VhdmpiDismountDependenciesForUnsurface(struct _VHD_SURFACE *a1)
{
  int v2; // eax
  _QWORD *v3; // rdi
  const wchar_t *v4; // rsi
  __int64 v5; // rcx
  const wchar_t *v6; // rax
  int v7; // ebx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // edx
  const wchar_t *v12; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]

  if ( *((_QWORD *)a1 + 37) )
  {
    v2 = *((_DWORD *)a1 + 14);
    if ( (v2 & 0x200) == 0 && (v2 & 0x40) == 0 )
    {
      v3 = (_QWORD *)*((_QWORD *)a1 + 2);
      ActivityId = 0;
      v15 = 0;
      ExAcquirePushLockSharedEx(v3 + 112, 0);
      VhdmpiAcquirePassiveLock(v3 + 14);
      EtwActivityIdControl(3u, &ActivityId);
      v4 = L"Unknown";
      v15 = 0;
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v5 = *(_QWORD *)(v3[18] + 120LL);
        v6 = L"Unknown";
        if ( v5 )
          v6 = *(const wchar_t **)(v3[18] + 120LL);
        v12 = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v5,
          (unsigned int)byte_14007D85D,
          (unsigned int)&ActivityId,
          0,
          (__int64)&v12);
      }
      v7 = DependentFSDismountForUnsurface(*((_QWORD *)a1 + 37), 0, v3[18], *(_QWORD *)(v3[18] + 1040LL));
      if ( v7 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        LODWORD(v12) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v8,
          (unsigned int)word_14007D8E2,
          (unsigned int)&ActivityId,
          v15,
          (__int64)&v12);
      }
      if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
      {
        v9 = v3[18];
        LODWORD(v12) = v7;
        v10 = *(_QWORD *)(v9 + 120);
        if ( v10 )
          v4 = *(const wchar_t **)(v9 + 120);
        v13 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)byte_14007D89B,
          (unsigned int)&ActivityId,
          v15,
          (__int64)&v13,
          (__int64)&v12);
      }
      if ( v7 < 0 && (unsigned int)dword_1400876D0 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiDismountDependenciesForUnsurface",
            0x20Du,
            v11 - 14,
            v11,
            "Vhdmpi: returned 0x%x from DependentFSDismountForUnsurface for disk %p",
            v7,
            v3);
      }
      VhdmpiReleasePassiveLock(v3 + 14);
      ExReleasePushLockSharedEx(v3 + 112, 0);
    }
  }
}

```

## disassembly

```asm
0x1400ba8e8  mov     [rsp-28h+arg_8], rbx
0x1400ba8ed  mov     [rsp-28h+arg_10], rsi
0x1400ba8f2  push    rbp
0x1400ba8f3  push    rdi
0x1400ba8f4  push    r12
0x1400ba8f6  push    r14
0x1400ba8f8  push    r15
0x1400ba8fa  mov     rbp, rsp
0x1400ba8fd  sub     rsp, 70h
0x1400ba901  mov     rax, cs:__security_cookie
0x1400ba908  xor     rax, rsp
0x1400ba90b  mov     [rbp+var_8], rax
0x1400ba90f  cmp     qword ptr [rcx+128h], 0
0x1400ba917  mov     rbx, rcx
0x1400ba91a  jz      loc_1400BAB15
0x1400ba920  mov     eax, [rcx+38h]
0x1400ba923  bt      eax, 9
0x1400ba927  jb      loc_1400BAB15
0x1400ba92d  test    al, 40h
0x1400ba92f  jnz     loc_1400BAB15
0x1400ba935  mov     rdi, [rcx+10h]
0x1400ba939  xorps   xmm0, xmm0
0x1400ba93c  xor     eax, eax
0x1400ba93e  xor     edx, edx
0x1400ba940  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1400ba944  mov     [rbp+var_10], rax
0x1400ba948  lea     r14, [rdi+380h]
0x1400ba94f  mov     rcx, r14
0x1400ba952  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400ba959  nop     dword ptr [rax+rax+00h]
0x1400ba95e  lea     rcx, [rdi+70h]
0x1400ba962  call    VhdmpiAcquirePassiveLock
0x1400ba967  lea     rdx, [rbp+ActivityId]; ActivityId
0x1400ba96b  mov     ecx, 3; ControlCode
0x1400ba970  call    cs:__imp_EtwActivityIdControl
0x1400ba977  nop     dword ptr [rax+rax+00h]
0x1400ba97c  mov     eax, cs:dword_140087708
0x1400ba982  lea     rsi, aUnknown; "Unknown"
0x1400ba989  mov     [rbp+var_10], 0
0x1400ba991  mov     r12d, 10000h
0x1400ba997  cmp     eax, 4
0x1400ba99a  jbe     short loc_1400BA9E4
0x1400ba99c  mov     edx, r12d
0x1400ba99f  lea     rcx, dword_140087708
0x1400ba9a6  call    _tlgKeywordOn
0x1400ba9ab  test    al, al
0x1400ba9ad  jz      short loc_1400BA9E4
0x1400ba9af  mov     rax, [rdi+90h]
0x1400ba9b6  lea     r8, [rbp+ActivityId]
0x1400ba9ba  lea     rdx, byte_14007D85D
0x1400ba9c1  mov     rcx, [rax+78h]
0x1400ba9c5  mov     rax, rsi
0x1400ba9c8  test    rcx, rcx
0x1400ba9cb  cmovnz  rax, rcx
0x1400ba9cf  xor     r9d, r9d
0x1400ba9d2  mov     [rbp+var_30], rax
0x1400ba9d6  lea     rax, [rbp+var_30]
0x1400ba9da  mov     [rsp+70h+var_50], rax
0x1400ba9df  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400ba9e4  mov     r8, [rdi+90h]
0x1400ba9eb  xor     edx, edx
0x1400ba9ed  mov     rcx, [rbx+128h]
0x1400ba9f4  mov     r9, [r8+410h]
0x1400ba9fb  call    cs:__imp_DependentFSDismountForUnsurface
0x1400baa02  nop     dword ptr [rax+rax+00h]
0x1400baa07  mov     ebx, eax
0x1400baa09  test    eax, eax
0x1400baa0b  jns     short loc_1400BAA4B
0x1400baa0d  mov     ecx, cs:dword_140087708
0x1400baa13  cmp     ecx, 2
0x1400baa16  jbe     short loc_1400BAA4B
0x1400baa18  mov     rdx, r12
0x1400baa1b  lea     rcx, dword_140087708
0x1400baa22  call    _tlgKeywordOn
0x1400baa27  test    al, al
0x1400baa29  jz      short loc_1400BAA4B
0x1400baa2b  mov     r9, [rbp+var_10]
0x1400baa2f  lea     rax, [rbp+var_30]
0x1400baa33  lea     r8, [rbp+ActivityId]
0x1400baa37  mov     [rsp+70h+var_50], rax
0x1400baa3c  lea     rdx, word_14007D8E2
0x1400baa43  mov     dword ptr [rbp+var_30], ebx
0x1400baa46  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400baa4b  mov     eax, cs:dword_140087708
0x1400baa51  cmp     eax, 4
0x1400baa54  jbe     short loc_1400BAAA8
0x1400baa56  mov     rdx, r12
0x1400baa59  lea     rcx, dword_140087708
0x1400baa60  call    _tlgKeywordOn
0x1400baa65  test    al, al
0x1400baa67  jz      short loc_1400BAAA8
0x1400baa69  mov     rax, [rdi+90h]
0x1400baa70  lea     r8, [rbp+ActivityId]
0x1400baa74  mov     r9, [rbp+var_10]
0x1400baa78  lea     rdx, byte_14007D89B
0x1400baa7f  mov     dword ptr [rbp+var_30], ebx
0x1400baa82  mov     rcx, [rax+78h]
0x1400baa86  lea     rax, [rbp+var_30]
0x1400baa8a  mov     qword ptr [rsp+70h+var_48], rax
0x1400baa8f  test    rcx, rcx
0x1400baa92  lea     rax, [rbp+var_28]
0x1400baa96  cmovnz  rsi, rcx
0x1400baa9a  mov     [rsp+70h+var_50], rax
0x1400baa9f  mov     [rbp+var_28], rsi
0x1400baaa3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400baaa8  test    ebx, ebx
0x1400baaaa  jns     short loc_1400BAAFB
0x1400baaac  mov     eax, cs:dword_1400876D0
0x1400baab2  cmp     eax, 2
0x1400baab5  jbe     short loc_1400BAAFB
0x1400baab7  mov     edx, 10h
0x1400baabc  lea     rcx, dword_1400876D0
0x1400baac3  call    _tlgKeywordOn
0x1400baac8  test    al, al
0x1400baaca  jz      short loc_1400BAAFB
0x1400baacc  mov     ecx, 20Dh
0x1400baad1  mov     [rsp+70h+var_40], rdi
0x1400baad6  mov     r9d, edx; int
0x1400baad9  mov     dword ptr [rsp+70h+var_48], ebx; char
0x1400baadd  lea     r8d, [rdx-0Eh]; int
0x1400baae1  mov     edx, ecx; int
0x1400baae3  lea     rax, aVhdmpiReturned; "Vhdmpi: returned 0x%x from DependentFSD"...
0x1400baaea  lea     rcx, aVhdmpidismount; "VhdmpiDismountDependenciesForUnsurface"
0x1400baaf1  mov     [rsp+70h+var_50], rax; char *
0x1400baaf6  call    TraceEvents
0x1400baafb  lea     rcx, [rdi+70h]
0x1400baaff  call    VhdmpiReleasePassiveLock
0x1400bab04  xor     edx, edx
0x1400bab06  mov     rcx, r14
0x1400bab09  call    cs:__imp_ExReleasePushLockSharedEx
0x1400bab10  nop     dword ptr [rax+rax+00h]
0x1400bab15  mov     rcx, [rbp+var_8]
0x1400bab19  xor     rcx, rsp; StackCookie
0x1400bab1c  call    __security_check_cookie
0x1400bab21  lea     r11, [rsp+70h+var_s0]
0x1400bab26  mov     rbx, [r11+38h]
0x1400bab2a  mov     rsi, [r11+40h]
0x1400bab2e  mov     rsp, r11
0x1400bab31  pop     r15
0x1400bab33  pop     r14
0x1400bab35  pop     r12
0x1400bab37  pop     rdi
0x1400bab38  pop     rbp
0x1400bab39  retn
```
