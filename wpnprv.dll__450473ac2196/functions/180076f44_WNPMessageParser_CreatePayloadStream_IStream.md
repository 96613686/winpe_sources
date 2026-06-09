# WNPMessageParser::CreatePayloadStream(IStream * *)

- ea: `0x180076f44`
- end: `0x1800771e5`
- name: `?CreatePayloadStream@WNPMessageParser@@AEAAJPEAPEAUIStream@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(WNPMessageParser *__hidden this, struct IStream **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007862c`
- `0x180078c40`

## callees

- `0x180008b67`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180076f44`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180076fbe`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180076fbe`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800771a3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800771a3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007705f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007705f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077043`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077043`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180077072`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180077072`

## pseudocode

```c
__int64 __fastcall WNPMessageParser::CreatePayloadStream(WNPMessageParser *this, struct IStream **a2)
{
  PVOID *v4; // rcx
  bool v5; // zf
  SIZE_T v6; // rbx
  HGLOBAL v7; // rax
  void *v8; // rdi
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  void *v13; // rax
  HRESULT v14; // eax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPSTREAM ppstm; // [rsp+60h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, WPP_21a3201469733e5c8660b272590c09d0_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_DWORD *)this + 4) == 0;
  ppstm = 0;
  if ( v5 || (v6 = *((unsigned int *)this + 4) - *((_QWORD *)this + 3)) == 0 )
  {
    v8 = 0;
    v9 = -2147019873;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(v4[2], 216, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147947423LL);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)0x8007139FLL,
      v16);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 217;
      v12 = 2147947423LL;
      goto LABEL_31;
    }
  }
  else
  {
    v7 = GlobalAlloc(2u, v6);
    v8 = v7;
    if ( v7 )
    {
      v13 = GlobalLock(v7);
      memcpy_0(v13, (const void *)(*((_QWORD *)this + 3) + *((_QWORD *)this + 1)), v6);
      GlobalUnlock(v8);
      v14 = CreateStreamOnHGlobal(v8, 1, &ppstm);
      v9 = v14;
      if ( v14 >= 0 )
      {
        *a2 = ppstm;
        ppstm = 0;
LABEL_36:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_37;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          220,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          (unsigned int)v14);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5C4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)v9,
        v16);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 221;
        v12 = v9;
        goto LABEL_31;
      }
    }
    else
    {
      v9 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          218,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          2147942414LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)0x8007000ELL,
        v16);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 219;
        v12 = 2147942414LL;
LABEL_31:
        WPP_SF_d(v10[2], v11, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v12);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    ppstm = 0;
  }
  if ( v8 )
  {
    GlobalFree(v8);
    goto LABEL_36;
  }
LABEL_37:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 222, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180076f44  push    rbx
0x180076f46  push    rsi
0x180076f47  push    rdi
0x180076f48  push    r12
0x180076f4a  push    r13
0x180076f4c  push    r14
0x180076f4e  sub     rsp, 28h
0x180076f52  mov     r14, rdx
0x180076f55  mov     rsi, rcx
0x180076f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f5f  lea     r12, WPP_GLOBAL_Control
0x180076f66  lea     r13, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x180076f6d  cmp     rcx, r12
0x180076f70  jz      short loc_180076F96
0x180076f72  test    byte ptr [rcx+1Ch], 2
0x180076f76  jz      short loc_180076F96
0x180076f78  cmp     byte ptr [rcx+19h], 6
0x180076f7c  jb      short loc_180076F96
0x180076f7e  mov     rcx, [rcx+10h]
0x180076f82  mov     edx, 0D7h
0x180076f87  mov     r8, r13
0x180076f8a  call    WPP_SF_
0x180076f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f96  cmp     dword ptr [rsi+10h], 0
0x180076f9a  mov     [rsp+58h+ppstm], 0
0x180076fa3  jz      loc_1800770FD
0x180076fa9  mov     ebx, [rsi+10h]
0x180076fac  sub     rbx, [rsi+18h]
0x180076fb0  jz      loc_1800770FD
0x180076fb6  mov     rdx, rbx; dwBytes
0x180076fb9  mov     ecx, 2; uFlags
0x180076fbe  call    cs:__imp_GlobalAlloc
0x180076fc4  mov     rdi, rax
0x180076fc7  test    rax, rax
0x180076fca  jnz     short loc_180077040
0x180076fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180076fd3  mov     ebx, 8007000Eh
0x180076fd8  cmp     rcx, r12
0x180076fdb  jz      short loc_180076FFD
0x180076fdd  test    byte ptr [rcx+1Ch], 2
0x180076fe1  jz      short loc_180076FFD
0x180076fe3  cmp     byte ptr [rcx+19h], 2
0x180076fe7  jb      short loc_180076FFD
0x180076fe9  mov     rcx, [rcx+10h]
0x180076fed  mov     edx, 0DAh
0x180076ff2  mov     r9d, ebx
0x180076ff5  mov     r8, r13
0x180076ff8  call    WPP_SF_d
0x180076ffd  mov     rcx, [rsp+58h]; this
0x180077002  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180077009  mov     r9d, ebx; char *
0x18007700c  mov     edx, 5BBh; void *
0x180077011  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180077016  mov     rcx, cs:WPP_GLOBAL_Control
0x18007701d  cmp     rcx, r12
0x180077020  jz      loc_180077172
0x180077026  test    byte ptr [rcx+1Ch], 80h
0x18007702a  jz      loc_180077172
0x180077030  mov     edx, 0DBh
0x180077035  mov     r9d, 8007000Eh
0x18007703b  jmp     loc_18007715F
0x180077040  mov     rcx, rdi; hMem
0x180077043  call    cs:__imp_GlobalLock
0x180077049  mov     rdx, [rsi+8]
0x18007704d  mov     r8, rbx; Size
0x180077050  add     rdx, [rsi+18h]; Src
0x180077054  mov     rcx, rax; void *
0x180077057  call    memcpy_0
0x18007705c  mov     rcx, rdi; hMem
0x18007705f  call    cs:__imp_GlobalUnlock
0x180077065  lea     r8, [rsp+58h+ppstm]; ppstm
0x18007706a  mov     edx, 1; fDeleteOnRelease
0x18007706f  mov     rcx, rdi; hGlobal
0x180077072  call    cs:__imp_CreateStreamOnHGlobal
0x180077078  mov     ebx, eax
0x18007707a  test    eax, eax
0x18007707c  jns     short loc_1800770E7
0x18007707e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077085  cmp     rcx, r12
0x180077088  jz      short loc_1800770AA
0x18007708a  test    byte ptr [rcx+1Ch], 2
0x18007708e  jz      short loc_1800770AA
0x180077090  cmp     byte ptr [rcx+19h], 2
0x180077094  jb      short loc_1800770AA
0x180077096  mov     rcx, [rcx+10h]
0x18007709a  mov     edx, 0DCh
0x18007709f  mov     r9d, eax
0x1800770a2  mov     r8, r13
0x1800770a5  call    WPP_SF_d
0x1800770aa  mov     rcx, [rsp+58h]; this
0x1800770af  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800770b6  mov     r9d, ebx; char *
0x1800770b9  mov     edx, 5C4h; void *
0x1800770be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800770c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800770ca  cmp     rcx, r12
0x1800770cd  jz      loc_180077172
0x1800770d3  test    byte ptr [rcx+1Ch], 80h
0x1800770d7  jz      loc_180077172
0x1800770dd  mov     edx, 0DDh
0x1800770e2  mov     r9d, ebx
0x1800770e5  jmp     short loc_18007715F
0x1800770e7  mov     rax, [rsp+58h+ppstm]
0x1800770ec  mov     [r14], rax
0x1800770ef  mov     [rsp+58h+ppstm], 0
0x1800770f8  jmp     loc_1800771A9
0x1800770fd  xor     edi, edi
0x1800770ff  mov     ebx, 8007139Fh
0x180077104  cmp     rcx, r12
0x180077107  jz      short loc_180077129
0x180077109  test    byte ptr [rcx+1Ch], 2
0x18007710d  jz      short loc_180077129
0x18007710f  cmp     byte ptr [rcx+19h], 2
0x180077113  jb      short loc_180077129
0x180077115  mov     rcx, [rcx+10h]
0x180077119  mov     edx, 0D8h
0x18007711e  mov     r9d, ebx
0x180077121  mov     r8, r13
0x180077124  call    WPP_SF_d
0x180077129  mov     rcx, [rsp+58h]; this
0x18007712e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180077135  mov     r9d, ebx; char *
0x180077138  mov     edx, 5B2h; void *
0x18007713d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180077142  mov     rcx, cs:WPP_GLOBAL_Control
0x180077149  cmp     rcx, r12
0x18007714c  jz      short loc_180077172
0x18007714e  test    byte ptr [rcx+1Ch], 80h
0x180077152  jz      short loc_180077172
0x180077154  mov     edx, 0D9h
0x180077159  mov     r9d, 8007139Fh
0x18007715f  mov     rcx, [rcx+10h]
0x180077163  mov     r8, r13
0x180077166  call    WPP_SF_d
0x18007716b  mov     rcx, cs:WPP_GLOBAL_Control
0x180077172  mov     rdx, [rsp+58h+ppstm]
0x180077177  test    rdx, rdx
0x18007717a  jz      short loc_18007719B
0x18007717c  mov     rax, [rdx]
0x18007717f  mov     rcx, rdx
0x180077182  mov     rax, [rax+10h]
0x180077186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007718b  mov     rcx, cs:WPP_GLOBAL_Control
0x180077192  mov     [rsp+58h+ppstm], 0
0x18007719b  test    rdi, rdi
0x18007719e  jz      short loc_1800771B0
0x1800771a0  mov     rcx, rdi; hMem
0x1800771a3  call    cs:__imp_GlobalFree
0x1800771a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800771b0  cmp     rcx, r12
0x1800771b3  jz      short loc_1800771D5
0x1800771b5  test    byte ptr [rcx+1Ch], 2
0x1800771b9  jz      short loc_1800771D5
0x1800771bb  cmp     byte ptr [rcx+19h], 6
0x1800771bf  jb      short loc_1800771D5
0x1800771c1  mov     rcx, [rcx+10h]
0x1800771c5  mov     edx, 0DEh
0x1800771ca  mov     r9d, ebx
0x1800771cd  mov     r8, r13
0x1800771d0  call    WPP_SF_d
0x1800771d5  mov     eax, ebx
0x1800771d7  add     rsp, 28h
0x1800771db  pop     r14
0x1800771dd  pop     r13
0x1800771df  pop     r12
0x1800771e1  pop     rdi
0x1800771e2  pop     rsi
0x1800771e3  pop     rbx
0x1800771e4  retn
```
