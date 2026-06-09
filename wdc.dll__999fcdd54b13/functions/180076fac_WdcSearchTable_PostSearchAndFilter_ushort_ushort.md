# WdcSearchTable::PostSearchAndFilter(ushort,ushort)

- ea: `0x180076fac`
- end: `0x18007722c`
- name: `?PostSearchAndFilter@WdcSearchTable@@QEAAJGG@Z`
- size: `640`
- prototype: `__int64 __fastcall(WdcSearchTable *__hidden this, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180021c10`

## callees

- `0x180006a80`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x180072e18`
- `0x180076fac`
- `0x180077260`
- `0x180086010`

## import_xrefs

- `USER32!SendMessageW` at `0x180077008`
- `USER32!SendMessageW` at `0x18007702f`
- `USER32!SendMessageW` at `0x180077008`
- `USER32!SendMessageW` at `0x18007702f`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800771ab`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800771ab`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18007705b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18007705b`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077098`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800770af`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077098`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800770af`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800771be`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800771be`
- `DUI70!?AccDescProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800770a4`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18007708d`

## pseudocode

```c
__int64 __fastcall WdcSearchTable::PostSearchAndFilter(WdcSearchTable *this, const char *a2, unsigned __int16 a3)
{
  unsigned int v3; // ebp
  int v5; // ebx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  HWND v8; // rax
  HWND v9; // rax
  DirectUI::Element *v10; // rcx
  int v11; // eax
  unsigned __int16 *v12; // rsi
  WdcStringMap *v13; // rcx
  int v14; // eax
  const char *v15; // rdx
  int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v20; // [rsp+20h] [rbp-28h]
  int v21; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v22; // [rsp+50h] [rbp+8h] BYREF

  v3 = a3;
  v5 = (unsigned __int16)a2;
  v22 = 0;
  if ( a3 != *((_WORD *)this + 116) )
    goto LABEL_2;
  v7 = *((_QWORD *)this + 8);
  if ( v7 )
  {
    *((_WORD *)this + 88) = (_WORD)a2;
    v8 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 360LL))(v7);
    SendMessageW(v8, 0x1054u, 0, 0);
    v9 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 360LL))(*((_QWORD *)this + 8));
    SendMessageW(v9, 0x1009u, 0, 0);
    WdcDataPortal::Render(this, 0xFu);
  }
  if ( (_WORD)v5 || (v10 = (DirectUI::Element *)*((_QWORD *)this + 6)) == 0 || !*((_QWORD *)this + 7) )
  {
    v12 = (unsigned __int16 *)WdcAlloc(0x800u, a2, a3);
    if ( !v12 )
    {
      v6 = -2147024882;
      v21 = -2147024882;
      goto LABEL_10;
    }
    *v12 = 0;
    if ( v5 == 1 )
    {
      v14 = WdcStringMap::LoadStringW((WdcStringMap *)(unsigned int)(v5 - 1), 0x7F1Eu, &v22);
      v6 = v14;
      if ( v14 < 0 )
        goto LABEL_31;
      v18 = *((_QWORD *)this + 28);
    }
    else
    {
      v13 = (WdcStringMap *)(unsigned int)(v5 - 2);
      if ( v5 != 2 )
      {
        if ( v5 != 3 )
        {
LABEL_29:
          v14 = DirectUI::Element::SetContentString(*((DirectUI::Element **)this + 7), v12);
          v6 = v14;
          if ( v14 >= 0 )
          {
            v14 = DirectUI::Element::SetAccDesc(*((DirectUI::Element **)this + 7), v12);
            v6 = v14;
            if ( v14 >= 0 )
              goto LABEL_32;
          }
          goto LABEL_31;
        }
        v14 = WdcStringMap::LoadStringW(v13, 0x7F25u, &v22);
        v6 = v14;
        if ( v14 >= 0 )
        {
          v17 = *((_QWORD *)this + 1);
          if ( *(_QWORD *)(v17 + 1248) && *((_QWORD *)this + 28) )
          {
            v20 = *(_QWORD *)(v17 + 1248);
            StringCchPrintfW(v12, 0x400u, v22);
            goto LABEL_29;
          }
LABEL_25:
          v6 = -2147467259;
LABEL_32:
          WdcFree(v12, v15, v16);
          goto LABEL_33;
        }
LABEL_31:
        LODWORD(v20) = v14;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
          "WdcSearchTable::PostSearchAndFilter",
          0,
          L"FAILURE: 0x%08x",
          v20);
        goto LABEL_32;
      }
      v14 = WdcStringMap::LoadStringW(v13, 0x7F1Fu, &v22);
      v6 = v14;
      if ( v14 < 0 )
        goto LABEL_31;
      v18 = *(_QWORD *)(*((_QWORD *)this + 1) + 1248LL);
      if ( !v18 )
        goto LABEL_25;
    }
    StringCchPrintfW(v12, 0x400u, v22, v18);
    goto LABEL_29;
  }
  v11 = DirectUI::Element::SetLayoutPos(v10, -3);
  v6 = v11;
  if ( v11 < 0
    || (v11 = DirectUI::Element::RemoveLocalValue(
                *((DirectUI::Element **)this + 7),
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp),
        v6 = v11,
        v11 < 0)
    || (v11 = DirectUI::Element::RemoveLocalValue(
                *((DirectUI::Element **)this + 7),
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::AccDescProp),
        v6 = v11,
        v11 < 0) )
  {
    v21 = v11;
LABEL_10:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
      "WdcSearchTable::PostSearchAndFilter",
      0,
      L"FAILURE: 0x%08x",
      v21);
    goto LABEL_33;
  }
LABEL_2:
  v6 = 0;
LABEL_33:
  if ( (_WORD)v3 == *((_WORD *)this + 116)
    && *((_DWORD *)this + 40) == 3
    && (Microsoft_Windows_Diagnosis_WDCEnableBits & 8) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(this, HandleSearch_Stop, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x180076fac  mov     [rsp+arg_8], rbx
0x180076fb1  push    rbp
0x180076fb2  push    rsi
0x180076fb3  push    rdi
0x180076fb4  sub     rsp, 30h
0x180076fb8  movzx   ebp, r8w
0x180076fbc  mov     rdi, rcx
0x180076fbf  movzx   ebx, dx
0x180076fc2  mov     [rsp+48h+arg_0], 0
0x180076fcb  cmp     bp, [rcx+0E8h]
0x180076fd2  jz      short loc_180076FDB
0x180076fd4  xor     ebx, ebx
0x180076fd6  jmp     loc_1800771F3
0x180076fdb  mov     rcx, [rcx+40h]
0x180076fdf  test    rcx, rcx
0x180076fe2  jz      short loc_180077042
0x180076fe4  mov     [rdi+0B0h], bx
0x180076feb  mov     rax, [rcx]
0x180076fee  mov     rax, [rax+168h]
0x180076ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ffa  mov     rcx, rax; hWnd
0x180076ffd  xor     r9d, r9d; lParam
0x180077000  xor     r8d, r8d; wParam
0x180077003  mov     edx, 1054h; Msg
0x180077008  call    cs:__imp_SendMessageW
0x18007700e  mov     rcx, [rdi+40h]
0x180077012  mov     rax, [rcx]
0x180077015  mov     rax, [rax+168h]
0x18007701c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077021  mov     rcx, rax; hWnd
0x180077024  xor     r9d, r9d; lParam
0x180077027  xor     r8d, r8d; wParam
0x18007702a  mov     edx, 1009h; Msg
0x18007702f  call    cs:__imp_SendMessageW
0x180077035  mov     edx, 0Fh; unsigned int
0x18007703a  mov     rcx, rdi; this
0x18007703d  call    ?Render@WdcDataPortal@@QEAAJK@Z; WdcDataPortal::Render(ulong)
0x180077042  xor     eax, eax
0x180077044  cmp     ax, bx
0x180077047  jnz     short loc_1800770C1
0x180077049  mov     rcx, [rdi+30h]
0x18007704d  test    rcx, rcx
0x180077050  jz      short loc_1800770C1
0x180077052  cmp     [rdi+38h], rax
0x180077056  jz      short loc_1800770C1
0x180077058  lea     edx, [rax-3]
0x18007705b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180077061  mov     ebx, eax
0x180077063  test    eax, eax
0x180077065  jns     short loc_18007708D
0x180077067  mov     [rsp+48h+var_28], eax
0x18007706b  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180077072  xor     r8d, r8d; int
0x180077075  lea     rdx, aWdcsearchtable_1; "WdcSearchTable::PostSearchAndFilter"
0x18007707c  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180077083  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180077088  jmp     loc_1800771F3
0x18007708d  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180077094  mov     rcx, [rdi+38h]
0x180077098  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18007709e  mov     ebx, eax
0x1800770a0  test    eax, eax
0x1800770a2  js      short loc_180077067
0x1800770a4  mov     rdx, cs:__imp_?AccDescProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::AccDescProp(void)
0x1800770ab  mov     rcx, [rdi+38h]
0x1800770af  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800770b5  mov     ebx, eax
0x1800770b7  test    eax, eax
0x1800770b9  jns     loc_180076FD4
0x1800770bf  jmp     short loc_180077067
0x1800770c1  mov     ecx, 800h; dwBytes
0x1800770c6  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800770cb  mov     rsi, rax
0x1800770ce  test    rax, rax
0x1800770d1  jnz     short loc_1800770DE
0x1800770d3  mov     ebx, 8007000Eh
0x1800770d8  mov     [rsp+48h+var_28], ebx
0x1800770dc  jmp     short loc_18007706B
0x1800770de  xor     eax, eax
0x1800770e0  mov     ecx, ebx
0x1800770e2  mov     [rsi], ax
0x1800770e5  sub     ecx, 1; this
0x1800770e8  jz      loc_180077176
0x1800770ee  sub     ecx, 1; this
0x1800770f1  jz      short loc_18007714A
0x1800770f3  cmp     ecx, 1
0x1800770f6  jnz     loc_1800771A4
0x1800770fc  lea     r8, [rsp+48h+arg_0]; unsigned __int16 **
0x180077101  mov     edx, 7F25h; unsigned int
0x180077106  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x18007710b  mov     ebx, eax
0x18007710d  test    eax, eax
0x18007710f  js      loc_1800771CA
0x180077115  mov     rax, [rdi+8]
0x180077119  mov     rcx, [rax+4E0h]
0x180077120  test    rcx, rcx
0x180077123  jz      short loc_18007716F
0x180077125  mov     r9, [rdi+0E0h]
0x18007712c  test    r9, r9
0x18007712f  jz      short loc_18007716F
0x180077131  mov     r8, [rsp+48h+arg_0]; unsigned __int16 *
0x180077136  mov     edx, 400h; unsigned __int64
0x18007713b  mov     qword ptr [rsp+48h+var_28], rcx
0x180077140  mov     rcx, rsi; unsigned __int16 *
0x180077143  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077148  jmp     short loc_1800771A4
0x18007714a  lea     r8, [rsp+48h+arg_0]; unsigned __int16 **
0x18007714f  mov     edx, 7F1Fh; unsigned int
0x180077154  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x180077159  mov     ebx, eax
0x18007715b  test    eax, eax
0x18007715d  js      short loc_1800771CA
0x18007715f  mov     rax, [rdi+8]
0x180077163  mov     r9, [rax+4E0h]
0x18007716a  test    r9, r9
0x18007716d  jnz     short loc_180077192
0x18007716f  mov     ebx, 80004005h
0x180077174  jmp     short loc_1800771EB
0x180077176  lea     r8, [rsp+48h+arg_0]; unsigned __int16 **
0x18007717b  mov     edx, 7F1Eh; unsigned int
0x180077180  call    ?LoadStringW@WdcStringMap@@QEAAJKPEAPEAG@Z; WdcStringMap::LoadStringW(ulong,ushort * *)
0x180077185  mov     ebx, eax
0x180077187  test    eax, eax
0x180077189  js      short loc_1800771CA
0x18007718b  mov     r9, [rdi+0E0h]
0x180077192  mov     r8, [rsp+48h+arg_0]; unsigned __int16 *
0x180077197  mov     edx, 400h; unsigned __int64
0x18007719c  mov     rcx, rsi; unsigned __int16 *
0x18007719f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800771a4  mov     rcx, [rdi+38h]
0x1800771a8  mov     rdx, rsi
0x1800771ab  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800771b1  mov     ebx, eax
0x1800771b3  test    eax, eax
0x1800771b5  js      short loc_1800771CA
0x1800771b7  mov     rcx, [rdi+38h]
0x1800771bb  mov     rdx, rsi
0x1800771be  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x1800771c4  mov     ebx, eax
0x1800771c6  test    eax, eax
0x1800771c8  jns     short loc_1800771EB
0x1800771ca  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800771d1  mov     [rsp+48h+var_28], eax
0x1800771d5  xor     r8d, r8d; int
0x1800771d8  lea     rdx, aWdcsearchtable_1; "WdcSearchTable::PostSearchAndFilter"
0x1800771df  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x1800771e6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800771eb  mov     rcx, rsi; void *
0x1800771ee  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x1800771f3  cmp     bp, [rdi+0E8h]
0x1800771fa  jnz     short loc_18007721D
0x1800771fc  cmp     dword ptr [rdi+0A0h], 3
0x180077203  jnz     short loc_18007721D
0x180077205  test    cs:Microsoft_Windows_Diagnosis_WDCEnableBits, 8
0x18007720c  jz      short loc_18007721D
0x18007720e  mov     r8d, ebp
0x180077211  lea     rdx, HandleSearch_Stop
0x180077218  call    McTemplateU0q_EventWriteTransfer
0x18007721d  mov     eax, ebx
0x18007721f  mov     rbx, [rsp+48h+arg_8]
0x180077224  add     rsp, 30h
0x180077228  pop     rdi
0x180077229  pop     rsi
0x18007722a  pop     rbp
0x18007722b  retn
```
