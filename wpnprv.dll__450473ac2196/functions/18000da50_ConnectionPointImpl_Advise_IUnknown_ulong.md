# ConnectionPointImpl::Advise(IUnknown *,ulong *)

- ea: `0x18000da50`
- end: `0x18000dd7c`
- name: `?Advise@ConnectionPointImpl@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `812`
- prototype: `__int64 __fastcall(ConnectionPointImpl *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000da50`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbe7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbe7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dcf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000db53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dcf0`

## string_xrefs

- `0x18000dab1`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`
- `0x18000db0b`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`
- `0x18000db9a`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`
- `0x18000dc77`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`
- `0x18000dcba`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionpointimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConnectionPointImpl::Advise(ConnectionPointImpl *this, struct IUnknown *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  PVOID *v11; // rcx
  unsigned int v12; // eax
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids);
  }
  v16 = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
      (const char *)0x80004003LL,
      v14);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v8 = 21;
LABEL_9:
      v9 = 2147500035LL;
LABEL_10:
      WPP_SF_d(v7[2], v8, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, v9);
LABEL_43:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  if ( a3 )
  {
    *a3 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( *((_QWORD *)this + 8) )
    {
      v6 = -2147220991;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_38e46b42a633320096f95707e4b470ab_Traceguids,
          2147746305LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
        (const char *)0x80040201LL,
        v14);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_38e46b42a633320096f95707e4b470ab_Traceguids,
          2147746305LL);
      goto LABEL_42;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d6c20092_c56b_4e98_bb90_23876155d3dd,
            &v16);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_38e46b42a633320096f95707e4b470ab_Traceguids,
        (unsigned int)v10);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
    if ( v6 == -2147467262 )
    {
      v6 = -2147220990;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        WPP_SF_d(v11[2], 26, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, 2147746306LL);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
        (const char *)0x80040202LL,
        v14);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 27;
        v9 = 2147746306LL;
        goto LABEL_10;
      }
      goto LABEL_44;
    }
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
        (const char *)v6,
        v14);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 28;
        v9 = v6;
        goto LABEL_10;
      }
      goto LABEL_44;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v12 = v16;
    *((_QWORD *)this + 8) = v16;
    *((_DWORD *)this + 18) = v12;
    *a3 = v12;
    v16 = 0;
LABEL_42:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    goto LABEL_43;
  }
  v6 = -2147467261;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x9E,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionpointimpl.cpp",
    (const char *)0x80004003LL,
    v14);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v8 = 22;
    goto LABEL_9;
  }
LABEL_44:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v16 = 0;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 29, &WPP_38e46b42a633320096f95707e4b470ab_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000da50  push    rbx
0x18000da52  push    rsi
0x18000da53  push    rdi
0x18000da54  push    r12
0x18000da56  push    r14
0x18000da58  push    r15
0x18000da5a  sub     rsp, 28h
0x18000da5e  mov     r14, r8
0x18000da61  mov     rbx, rdx
0x18000da64  mov     rdi, rcx
0x18000da67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da6e  lea     r15, WPP_GLOBAL_Control
0x18000da75  lea     r12, WPP_38e46b42a633320096f95707e4b470ab_Traceguids
0x18000da7c  cmp     rcx, r15
0x18000da7f  jz      short loc_18000DA9E
0x18000da81  test    byte ptr [rcx+1Ch], 1
0x18000da85  jz      short loc_18000DA9E
0x18000da87  cmp     byte ptr [rcx+19h], 6
0x18000da8b  jb      short loc_18000DA9E
0x18000da8d  mov     rcx, [rcx+10h]
0x18000da91  mov     edx, 14h
0x18000da96  mov     r8, r12
0x18000da99  call    WPP_SF_
0x18000da9e  mov     [rsp+58h+arg_8], 0
0x18000daa7  test    rbx, rbx
0x18000daaa  jnz     short loc_18000DB01
0x18000daac  mov     rcx, [rsp+58h]; this
0x18000dab1  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dab8  mov     r9d, 80004003h; char *
0x18000dabe  mov     edx, 9Dh; void *
0x18000dac3  mov     ebx, r9d
0x18000dac6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dacb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dad2  cmp     rcx, r15
0x18000dad5  jz      loc_18000DD1E
0x18000dadb  test    byte ptr [rcx+1Ch], 80h
0x18000dadf  jz      loc_18000DD1E
0x18000dae5  mov     edx, 15h
0x18000daea  mov     r9d, 80004003h
0x18000daf0  mov     rcx, [rcx+10h]
0x18000daf4  mov     r8, r12
0x18000daf7  call    WPP_SF_d
0x18000dafc  jmp     loc_18000DD17
0x18000db01  test    r14, r14
0x18000db04  jnz     short loc_18000DB45
0x18000db06  mov     rcx, [rsp+58h]; this
0x18000db0b  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000db12  mov     r9d, 80004003h; char *
0x18000db18  mov     edx, 9Eh; void *
0x18000db1d  mov     ebx, r9d
0x18000db20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000db25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db2c  cmp     rcx, r15
0x18000db2f  jz      loc_18000DD1E
0x18000db35  test    byte ptr [rcx+1Ch], 80h
0x18000db39  jz      loc_18000DD1E
0x18000db3f  lea     edx, [r14+16h]
0x18000db43  jmp     short loc_18000DAEA
0x18000db45  lea     rsi, [rdi+10h]
0x18000db49  mov     dword ptr [r14], 0
0x18000db50  mov     rcx, rsi; lpCriticalSection
0x18000db53  call    cs:__imp_EnterCriticalSection
0x18000db59  cmp     qword ptr [rdi+40h], 0
0x18000db5e  jz      loc_18000DBE4
0x18000db64  mov     ebx, 80040201h
0x18000db69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db70  cmp     rcx, r15
0x18000db73  jz      short loc_18000DB95
0x18000db75  test    byte ptr [rcx+1Ch], 1
0x18000db79  jz      short loc_18000DB95
0x18000db7b  cmp     byte ptr [rcx+19h], 2
0x18000db7f  jb      short loc_18000DB95
0x18000db81  mov     rcx, [rcx+10h]
0x18000db85  mov     edx, 17h
0x18000db8a  mov     r9d, ebx
0x18000db8d  mov     r8, r12
0x18000db90  call    WPP_SF_d
0x18000db95  mov     rcx, [rsp+58h]; this
0x18000db9a  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dba1  mov     r9d, ebx; char *
0x18000dba4  mov     edx, 0A9h; void *
0x18000dba9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dbae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbb5  cmp     rcx, r15
0x18000dbb8  jz      loc_18000DD0E
0x18000dbbe  test    byte ptr [rcx+1Ch], 80h
0x18000dbc2  jz      loc_18000DD0E
0x18000dbc8  mov     rcx, [rcx+10h]
0x18000dbcc  mov     edx, 18h
0x18000dbd1  mov     r9d, 80040201h
0x18000dbd7  mov     r8, r12
0x18000dbda  call    WPP_SF_d
0x18000dbdf  jmp     loc_18000DD0E
0x18000dbe4  mov     rcx, rsi; lpCriticalSection
0x18000dbe7  call    cs:__imp_LeaveCriticalSection
0x18000dbed  mov     rax, [rbx]
0x18000dbf0  lea     r8, [rsp+58h+arg_8]
0x18000dbf5  lea     rdx, _GUID_d6c20092_c56b_4e98_bb90_23876155d3dd
0x18000dbfc  mov     rcx, rbx
0x18000dbff  mov     rax, [rax]
0x18000dc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc07  mov     ebx, eax
0x18000dc09  test    eax, eax
0x18000dc0b  jns     short loc_18000DC39
0x18000dc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc14  cmp     rcx, r15
0x18000dc17  jz      short loc_18000DC40
0x18000dc19  test    byte ptr [rcx+1Ch], 1
0x18000dc1d  jz      short loc_18000DC40
0x18000dc1f  cmp     byte ptr [rcx+19h], 2
0x18000dc23  jb      short loc_18000DC40
0x18000dc25  mov     rcx, [rcx+10h]
0x18000dc29  mov     edx, 19h
0x18000dc2e  mov     r9d, eax
0x18000dc31  mov     r8, r12
0x18000dc34  call    WPP_SF_d
0x18000dc39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc40  cmp     ebx, 80004002h
0x18000dc46  jnz     short loc_18000DCB1
0x18000dc48  mov     ebx, 80040202h
0x18000dc4d  cmp     rcx, r15
0x18000dc50  jz      short loc_18000DC72
0x18000dc52  test    byte ptr [rcx+1Ch], 1
0x18000dc56  jz      short loc_18000DC72
0x18000dc58  cmp     byte ptr [rcx+19h], 2
0x18000dc5c  jb      short loc_18000DC72
0x18000dc5e  mov     rcx, [rcx+10h]
0x18000dc62  mov     edx, 1Ah
0x18000dc67  mov     r9d, ebx
0x18000dc6a  mov     r8, r12
0x18000dc6d  call    WPP_SF_d
0x18000dc72  mov     rcx, [rsp+58h]; this
0x18000dc77  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dc7e  mov     r9d, ebx; char *
0x18000dc81  mov     edx, 0B8h; void *
0x18000dc86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dc8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc92  cmp     rcx, r15
0x18000dc95  jz      loc_18000DD1E
0x18000dc9b  test    byte ptr [rcx+1Ch], 80h
0x18000dc9f  jz      short loc_18000DD1E
0x18000dca1  mov     edx, 1Bh
0x18000dca6  mov     r9d, 80040202h
0x18000dcac  jmp     loc_18000DAF0
0x18000dcb1  test    ebx, ebx
0x18000dcb3  jns     short loc_18000DCED
0x18000dcb5  mov     rcx, [rsp+58h]; this
0x18000dcba  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000dcc1  mov     r9d, ebx; char *
0x18000dcc4  mov     edx, 0BBh; void *
0x18000dcc9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dcce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd5  cmp     rcx, r15
0x18000dcd8  jz      short loc_18000DD1E
0x18000dcda  test    byte ptr [rcx+1Ch], 80h
0x18000dcde  jz      short loc_18000DD1E
0x18000dce0  mov     edx, 1Ch
0x18000dce5  mov     r9d, ebx
0x18000dce8  jmp     loc_18000DAF0
0x18000dced  mov     rcx, rsi; lpCriticalSection
0x18000dcf0  call    cs:__imp_EnterCriticalSection
0x18000dcf6  mov     rax, [rsp+58h+arg_8]
0x18000dcfb  mov     [rdi+40h], rax
0x18000dcff  mov     [rdi+48h], eax
0x18000dd02  mov     [r14], eax
0x18000dd05  mov     [rsp+58h+arg_8], 0
0x18000dd0e  mov     rcx, rsi; lpCriticalSection
0x18000dd11  call    cs:__imp_LeaveCriticalSection
0x18000dd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd1e  mov     rdx, [rsp+58h+arg_8]
0x18000dd23  test    rdx, rdx
0x18000dd26  jz      short loc_18000DD47
0x18000dd28  mov     rax, [rdx]
0x18000dd2b  mov     rcx, rdx
0x18000dd2e  mov     rax, [rax+10h]
0x18000dd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd3e  mov     [rsp+58h+arg_8], 0
0x18000dd47  cmp     rcx, r15
0x18000dd4a  jz      short loc_18000DD6C
0x18000dd4c  test    byte ptr [rcx+1Ch], 1
0x18000dd50  jz      short loc_18000DD6C
0x18000dd52  cmp     byte ptr [rcx+19h], 6
0x18000dd56  jb      short loc_18000DD6C
0x18000dd58  mov     rcx, [rcx+10h]
0x18000dd5c  mov     edx, 1Dh
0x18000dd61  mov     r9d, ebx
0x18000dd64  mov     r8, r12
0x18000dd67  call    WPP_SF_d
0x18000dd6c  mov     eax, ebx
0x18000dd6e  add     rsp, 28h
0x18000dd72  pop     r15
0x18000dd74  pop     r14
0x18000dd76  pop     r12
0x18000dd78  pop     rdi
0x18000dd79  pop     rsi
0x18000dd7a  pop     rbx
0x18000dd7b  retn
```
