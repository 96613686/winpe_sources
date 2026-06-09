# CWcnUpnpTransport::CreateAsyncFindInner(void)

- ea: `0x18003ed30`
- end: `0x18003ef32`
- name: `?CreateAsyncFindInner@CWcnUpnpTransport@@AEAAJXZ`
- size: `514`
- prototype: `__int64 __fastcall(CWcnUpnpTransport *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003f6c0`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003ed30`
- `0x180043208`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003ee2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003ee2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eec7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003eec7`

## pseudocode

```c
__int64 __fastcall CWcnUpnpTransport::CreateAsyncFindInner(CWcnUpnpTransport *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  int Item; // eax
  int v5; // ebx
  _BYTE *v6; // r10
  int v7; // eax
  OLECHAR *v8; // rsi
  const char *v9; // rax
  __int64 v10; // r10
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r10
  void *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 36, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, Indent);
  }
  Item = CWcnUpnpGit::GetItem(this, *((_DWORD *)this + 10), &GUID_415a984a_88b3_49f3_92af_0508bedf0d6c, &v15);
  v5 = Item;
  if ( Item < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_25;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids,
      (unsigned int)Item);
    goto LABEL_24;
  }
  if ( *((_BYTE *)this + 17) )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 80LL))(
           *((_QWORD *)this + 3),
           *((unsigned int *)this + 5));
    if ( v7 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids,
        (unsigned int)v7);
    *((_BYTE *)this + 17) = 0;
  }
  v8 = SysAllocString(L"urn:schemas-wifialliance-org:device:WFADevice:1");
  if ( v8 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, void *, char *))(**((_QWORD **)this + 3) + 64LL))(
            *((_QWORD *)this + 3),
            v8,
            0,
            v15,
            (char *)this + 20);
    v5 = v11;
    if ( v11 >= 0 )
    {
      *((_BYTE *)this + 17) = 1;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids,
        (unsigned int)v11);
    }
    SysFreeString(v8);
    goto LABEL_24;
  }
  v5 = -2147024882;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 39, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, v9);
LABEL_24:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_25:
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v5 < 0 || v6[25] >= 6u) )
  {
    v12 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v13 + 16), 41, (unsigned int)WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids, v12, v5);
  }
LABEL_29:
  if ( v15 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ed30  mov     [rsp+arg_8], rbx
0x18003ed35  mov     [rsp+arg_10], rsi
0x18003ed3a  push    rdi
0x18003ed3b  push    r14
0x18003ed3d  push    r15
0x18003ed3f  sub     rsp, 30h
0x18003ed43  mov     rdi, rcx
0x18003ed46  mov     [rsp+48h+arg_0], 0
0x18003ed4f  lea     r14, WPP_GLOBAL_Control
0x18003ed56  lea     r15, WPP_1038bd85cc6033fecb4c6bfd5194080f_Traceguids
0x18003ed5d  mov     r10, cs:WPP_GLOBAL_Control
0x18003ed64  cmp     r10, r14
0x18003ed67  jz      short loc_18003ED8E
0x18003ed69  cmp     byte ptr [r10+19h], 6
0x18003ed6e  jb      short loc_18003ED8E
0x18003ed70  mov     ecx, 1; int
0x18003ed75  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ed7a  mov     edx, 24h ; '$'
0x18003ed7f  mov     r9, rax
0x18003ed82  mov     r8, r15
0x18003ed85  mov     rcx, [r10+10h]
0x18003ed89  call    WPP_SF_s
0x18003ed8e  lea     r9, [rsp+48h+arg_0]; void **
0x18003ed93  lea     r8, _GUID_415a984a_88b3_49f3_92af_0508bedf0d6c; struct _GUID *
0x18003ed9a  mov     edx, [rdi+28h]; unsigned int
0x18003ed9d  call    ?GetItem@CWcnUpnpGit@@QEAAJKAEBU_GUID@@PEAPEAX@Z; CWcnUpnpGit::GetItem(ulong,_GUID const &,void * *)
0x18003eda2  mov     ebx, eax
0x18003eda4  test    eax, eax
0x18003eda6  jns     short loc_18003EDDC
0x18003eda8  mov     r10, cs:WPP_GLOBAL_Control
0x18003edaf  cmp     r10, r14
0x18003edb2  jz      loc_18003EF05
0x18003edb8  cmp     byte ptr [r10+19h], 2
0x18003edbd  jb      loc_18003EED4
0x18003edc3  mov     edx, 25h ; '%'
0x18003edc8  mov     r9d, eax
0x18003edcb  mov     r8, r15
0x18003edce  mov     rcx, [r10+10h]
0x18003edd2  call    WPP_SF_d
0x18003edd7  jmp     loc_18003EECD
0x18003eddc  lea     rbx, [rdi+14h]
0x18003ede0  cmp     byte ptr [rdi+11h], 0
0x18003ede4  jz      short loc_18003EE26
0x18003ede6  mov     rcx, [rdi+18h]
0x18003edea  mov     rax, [rcx]
0x18003eded  mov     edx, [rbx]
0x18003edef  mov     rax, [rax+50h]
0x18003edf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edf8  test    eax, eax
0x18003edfa  jns     short loc_18003EE22
0x18003edfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee03  cmp     rcx, r14
0x18003ee06  jz      short loc_18003EE22
0x18003ee08  cmp     byte ptr [rcx+19h], 3
0x18003ee0c  jb      short loc_18003EE22
0x18003ee0e  mov     edx, 26h ; '&'
0x18003ee13  mov     r9d, eax
0x18003ee16  mov     r8, r15
0x18003ee19  mov     rcx, [rcx+10h]
0x18003ee1d  call    WPP_SF_d
0x18003ee22  mov     byte ptr [rdi+11h], 0
0x18003ee26  lea     rcx, aUrnSchemasWifi; "urn:schemas-wifialliance-org:device:WFA"...
0x18003ee2d  call    cs:__imp_SysAllocString
0x18003ee33  mov     rsi, rax
0x18003ee36  test    rax, rax
0x18003ee39  jnz     short loc_18003EE72
0x18003ee3b  mov     ebx, 8007000Eh
0x18003ee40  mov     r10, cs:WPP_GLOBAL_Control
0x18003ee47  cmp     r10, r14
0x18003ee4a  jz      loc_18003EF05
0x18003ee50  cmp     byte ptr [r10+19h], 2
0x18003ee55  jb      short loc_18003EED4
0x18003ee57  xor     ecx, ecx; int
0x18003ee59  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ee5e  lea     edx, [rsi+27h]
0x18003ee61  mov     r9, rax
0x18003ee64  mov     r8, r15
0x18003ee67  mov     rcx, [r10+10h]
0x18003ee6b  call    WPP_SF_s
0x18003ee70  jmp     short loc_18003EECD
0x18003ee72  mov     rcx, [rdi+18h]
0x18003ee76  mov     rax, [rcx]
0x18003ee79  mov     [rsp+48h+var_28], rbx
0x18003ee7e  mov     r9, [rsp+48h+arg_0]
0x18003ee83  xor     r8d, r8d
0x18003ee86  mov     rdx, rsi
0x18003ee89  mov     rax, [rax+40h]
0x18003ee8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee92  mov     ebx, eax
0x18003ee94  test    eax, eax
0x18003ee96  jns     short loc_18003EEC0
0x18003ee98  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee9f  cmp     rcx, r14
0x18003eea2  jz      short loc_18003EEC4
0x18003eea4  cmp     byte ptr [rcx+19h], 2
0x18003eea8  jb      short loc_18003EEC4
0x18003eeaa  mov     edx, 28h ; '('
0x18003eeaf  mov     r9d, eax
0x18003eeb2  mov     r8, r15
0x18003eeb5  mov     rcx, [rcx+10h]
0x18003eeb9  call    WPP_SF_d
0x18003eebe  jmp     short loc_18003EEC4
0x18003eec0  mov     byte ptr [rdi+11h], 1
0x18003eec4  mov     rcx, rsi; bstrString
0x18003eec7  call    cs:__imp_SysFreeString
0x18003eecd  mov     r10, cs:WPP_GLOBAL_Control
0x18003eed4  cmp     r10, r14
0x18003eed7  jz      short loc_18003EF05
0x18003eed9  test    ebx, ebx
0x18003eedb  js      short loc_18003EEE4
0x18003eedd  cmp     byte ptr [r10+19h], 6
0x18003eee2  jb      short loc_18003EF05
0x18003eee4  or      ecx, 0FFFFFFFFh; int
0x18003eee7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003eeec  mov     edx, 29h ; ')'
0x18003eef1  mov     dword ptr [rsp+48h+var_28], ebx
0x18003eef5  mov     r9, rax
0x18003eef8  mov     r8, r15
0x18003eefb  mov     rcx, [r10+10h]
0x18003eeff  call    WPP_SF_sd
0x18003ef04  nop
0x18003ef05  mov     rcx, [rsp+48h+arg_0]
0x18003ef0a  test    rcx, rcx
0x18003ef0d  jz      short loc_18003EF1C
0x18003ef0f  mov     rax, [rcx]
0x18003ef12  mov     rax, [rax+10h]
0x18003ef16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef1b  nop
0x18003ef1c  mov     eax, ebx
0x18003ef1e  mov     rbx, [rsp+48h+arg_8]
0x18003ef23  mov     rsi, [rsp+48h+arg_10]
0x18003ef28  add     rsp, 30h
0x18003ef2c  pop     r15
0x18003ef2e  pop     r14
0x18003ef30  pop     rdi
0x18003ef31  retn
```
