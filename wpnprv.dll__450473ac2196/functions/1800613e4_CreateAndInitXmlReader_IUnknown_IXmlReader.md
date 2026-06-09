# CreateAndInitXmlReader(IUnknown *,IXmlReader * *)

- ea: `0x1800613e4`
- end: `0x180061668`
- name: `?CreateAndInitXmlReader@@YAJPEAUIUnknown@@PEAPEAUIXmlReader@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IXmlReader **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061670`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800613e4`
- `0x180096010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180061466`
- `XmlLite!CreateXmlReader` at `0x180061466`

## string_xrefs

- `0x1800614a3`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x180061535`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x1800615bc`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateAndInitXmlReader(struct IUnknown *a1, struct IXmlReader **a2)
{
  PVOID v4; // rcx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppvObject; // [rsp+40h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids);
  }
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  if ( !a2 || *a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  ppvObject = 0;
  v5 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(void *, struct IUnknown *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a1);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
      v6 = v10;
      if ( v10 >= 0 )
      {
        *a2 = (struct IXmlReader *)ppvObject;
        ppvObject = 0;
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
          (unsigned int)v10);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x85,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
        (const char *)v6);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 26;
        goto LABEL_18;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
          (unsigned int)v9);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
        (const char *)v6);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 24;
        goto LABEL_18;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
        (unsigned int)v5);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7D,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
      (const char *)v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v8 = 22;
LABEL_18:
      WPP_SF_d(v7[2], v8, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v6);
LABEL_36:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( ppvObject )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    ppvObject = 0;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 27, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800613e4  mov     [rsp+arg_8], rbx
0x1800613e9  mov     [rsp+arg_10], rsi
0x1800613ee  push    rdi
0x1800613ef  push    r14
0x1800613f1  push    r15; int
0x1800613f3  sub     rsp, 20h
0x1800613f7  mov     rdi, rdx
0x1800613fa  mov     rsi, rcx
0x1800613fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180061404  lea     r14, WPP_GLOBAL_Control
0x18006140b  lea     r15, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids
0x180061412  cmp     rcx, r14
0x180061415  jz      short loc_180061434
0x180061417  test    byte ptr [rcx+1Ch], 4
0x18006141b  jz      short loc_180061434
0x18006141d  cmp     byte ptr [rcx+19h], 6
0x180061421  jb      short loc_180061434
0x180061423  mov     rcx, [rcx+10h]
0x180061427  mov     edx, 14h
0x18006142c  mov     r8, r15
0x18006142f  call    WPP_SF_
0x180061434  test    rsi, rsi
0x180061437  jnz     short loc_18006143E
0x180061439  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006143e  test    rdi, rdi
0x180061441  jz      short loc_180061449
0x180061443  cmp     qword ptr [rdi], 0
0x180061447  jz      short loc_18006144E
0x180061449  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006144e  xor     r8d, r8d; pMalloc
0x180061451  mov     [rsp+38h+ppvObject], 0
0x18006145a  lea     rdx, [rsp+38h+ppvObject]; ppvObject
0x18006145f  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180061466  call    cs:__imp_CreateXmlReader
0x18006146c  mov     ebx, eax
0x18006146e  test    eax, eax
0x180061470  jns     short loc_1800614EA
0x180061472  mov     rcx, cs:WPP_GLOBAL_Control
0x180061479  cmp     rcx, r14
0x18006147c  jz      short loc_18006149E
0x18006147e  test    byte ptr [rcx+1Ch], 4
0x180061482  jz      short loc_18006149E
0x180061484  cmp     byte ptr [rcx+19h], 2
0x180061488  jb      short loc_18006149E
0x18006148a  mov     rcx, [rcx+10h]
0x18006148e  mov     edx, 15h
0x180061493  mov     r9d, eax
0x180061496  mov     r8, r15
0x180061499  call    WPP_SF_d
0x18006149e  mov     rcx, [rsp+38h]; this
0x1800614a3  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800614aa  mov     r9d, ebx; char *
0x1800614ad  mov     edx, 7Dh ; '}'; void *
0x1800614b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800614b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800614be  cmp     rcx, r14
0x1800614c1  jz      loc_180061604
0x1800614c7  test    byte ptr [rcx+1Ch], 80h
0x1800614cb  jz      loc_180061604
0x1800614d1  mov     edx, 16h
0x1800614d6  mov     rcx, [rcx+10h]
0x1800614da  mov     r9d, ebx
0x1800614dd  mov     r8, r15
0x1800614e0  call    WPP_SF_d
0x1800614e5  jmp     loc_1800615FD
0x1800614ea  mov     rcx, [rsp+38h+ppvObject]
0x1800614ef  mov     rdx, rsi
0x1800614f2  mov     rax, [rcx]
0x1800614f5  mov     rax, [rax+18h]
0x1800614f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800614fe  mov     ebx, eax
0x180061500  test    eax, eax
0x180061502  jns     short loc_18006156D
0x180061504  mov     rcx, cs:WPP_GLOBAL_Control
0x18006150b  cmp     rcx, r14
0x18006150e  jz      short loc_180061530
0x180061510  test    byte ptr [rcx+1Ch], 4
0x180061514  jz      short loc_180061530
0x180061516  cmp     byte ptr [rcx+19h], 2
0x18006151a  jb      short loc_180061530
0x18006151c  mov     rcx, [rcx+10h]
0x180061520  mov     edx, 17h
0x180061525  mov     r9d, eax
0x180061528  mov     r8, r15
0x18006152b  call    WPP_SF_d
0x180061530  mov     rcx, [rsp+38h]; this
0x180061535  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006153c  mov     r9d, ebx; char *
0x18006153f  mov     edx, 81h; void *
0x180061544  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061549  mov     rcx, cs:WPP_GLOBAL_Control
0x180061550  cmp     rcx, r14
0x180061553  jz      loc_180061604
0x180061559  test    byte ptr [rcx+1Ch], 80h
0x18006155d  jz      loc_180061604
0x180061563  mov     edx, 18h
0x180061568  jmp     loc_1800614D6
0x18006156d  mov     rcx, [rsp+38h+ppvObject]
0x180061572  xor     r8d, r8d
0x180061575  mov     rax, [rcx]
0x180061578  lea     edx, [r8+4]
0x18006157c  mov     rax, [rax+28h]
0x180061580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061585  mov     ebx, eax
0x180061587  test    eax, eax
0x180061589  jns     short loc_1800615EC
0x18006158b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061592  cmp     rcx, r14
0x180061595  jz      short loc_1800615B7
0x180061597  test    byte ptr [rcx+1Ch], 4
0x18006159b  jz      short loc_1800615B7
0x18006159d  cmp     byte ptr [rcx+19h], 2
0x1800615a1  jb      short loc_1800615B7
0x1800615a3  mov     rcx, [rcx+10h]
0x1800615a7  mov     edx, 19h
0x1800615ac  mov     r9d, eax
0x1800615af  mov     r8, r15
0x1800615b2  call    WPP_SF_d
0x1800615b7  mov     rcx, [rsp+38h]; this
0x1800615bc  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800615c3  mov     r9d, ebx; char *
0x1800615c6  mov     edx, 85h; void *
0x1800615cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800615d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800615d7  cmp     rcx, r14
0x1800615da  jz      short loc_180061604
0x1800615dc  test    byte ptr [rcx+1Ch], 80h
0x1800615e0  jz      short loc_180061604
0x1800615e2  mov     edx, 1Ah
0x1800615e7  jmp     loc_1800614D6
0x1800615ec  mov     rax, [rsp+38h+ppvObject]
0x1800615f1  mov     [rdi], rax
0x1800615f4  mov     [rsp+38h+ppvObject], 0
0x1800615fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180061604  mov     rdx, [rsp+38h+ppvObject]
0x180061609  test    rdx, rdx
0x18006160c  jz      short loc_18006162D
0x18006160e  mov     rax, [rdx]
0x180061611  mov     rcx, rdx
0x180061614  mov     rax, [rax+10h]
0x180061618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006161d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061624  mov     [rsp+38h+ppvObject], 0
0x18006162d  cmp     rcx, r14
0x180061630  jz      short loc_180061652
0x180061632  test    byte ptr [rcx+1Ch], 4
0x180061636  jz      short loc_180061652
0x180061638  cmp     byte ptr [rcx+19h], 6
0x18006163c  jb      short loc_180061652
0x18006163e  mov     rcx, [rcx+10h]
0x180061642  mov     edx, 1Bh
0x180061647  mov     r9d, ebx
0x18006164a  mov     r8, r15
0x18006164d  call    WPP_SF_d
0x180061652  mov     rsi, [rsp+38h+arg_10]
0x180061657  mov     eax, ebx
0x180061659  mov     rbx, [rsp+38h+arg_8]
0x18006165e  add     rsp, 20h
0x180061662  pop     r15
0x180061664  pop     r14
0x180061666  pop     rdi
0x180061667  retn
```
