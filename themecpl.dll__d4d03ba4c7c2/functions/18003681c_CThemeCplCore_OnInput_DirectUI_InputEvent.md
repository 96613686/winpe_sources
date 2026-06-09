# CThemeCplCore::OnInput(DirectUI::InputEvent *)

- ea: `0x18003681c`
- end: `0x1800369f5`
- name: `?OnInput@CThemeCplCore@@QEAAXPEAUInputEvent@DirectUI@@@Z`
- size: `473`
- prototype: `void(CThemeCplCore *__hidden this, struct DirectUI::InputEvent *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800390a0`

## callees

- `0x1800207c4`
- `0x18003681c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036874`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800368b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003697b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036874`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800368b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003697b`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180036901`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180036901`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369a3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369b4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369ca`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369a3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369b4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800369ca`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180036840`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003694a`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x180036840`
- `DUI70!?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18003694a`

## pseudocode

```c
void __fastcall CThemeCplCore::OnInput(CThemeCplCore *this, DirectUI::Element **a2)
{
  const WCHAR *Class; // rax
  const WCHAR *v5; // rdi
  __int16 v6; // ax
  DirectUI::Element *v7; // rcx
  _DWORD *Children; // rax
  DirectUI::Element **v9; // rbx
  DirectUI::Element *v10; // rbx
  const WCHAR *v11; // rax
  struct DirectUI::Value *v12; // [rsp+58h] [rbp+10h] BYREF
  DirectUI::Value *v13; // [rsp+60h] [rbp+18h] BYREF
  struct DirectUI::Value *v14; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  Class = DirectUI::Element::GetClass(*a2, &v14);
  v5 = Class;
  if ( !Class )
    goto LABEL_20;
  if ( CompareStringOrdinal(Class, -1, L"ThemeButton", -1, 1) == 2 )
  {
    CGallery::OnInput((CThemeCplCore *)((char *)this + 48), (struct DirectUI::InputEvent *)a2);
    goto LABEL_20;
  }
  if ( *((_DWORD *)a2 + 4) != 1
    || CompareStringOrdinal(v5, -1, L"ThemeElementGroup", -1, 1) != 2
    || *((_DWORD *)a2 + 3) != 1 )
  {
    goto LABEL_20;
  }
  if ( *((_DWORD *)a2 + 5) == 1 )
  {
    v6 = 32;
  }
  else
  {
    if ( *((_DWORD *)a2 + 5) )
      goto LABEL_20;
    v6 = 13;
  }
  if ( v6 == *((_WORD *)a2 + 16) )
  {
    v7 = *a2;
    v13 = 0;
    Children = (_DWORD *)DirectUI::Element::GetChildren(v7, &v13);
    if ( Children )
    {
      if ( (*Children & 0xFFFFFFF) != 0 )
      {
        v9 = (DirectUI::Element **)(Children + 2);
        if ( (*Children & 0x10000000) != 0 )
          v9 = (DirectUI::Element **)*v9;
        v10 = *v9;
        if ( v10 )
        {
          v12 = 0;
          v11 = DirectUI::Element::GetClass(v10, &v12);
          if ( v12 )
          {
            if ( v11 && CompareStringOrdinal(v11, -1, L"ThemeElementIcon", -1, 1) == 2 )
            {
              (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v10 + 296LL))(v10);
              DirectUI::Value::Release(v12);
            }
          }
        }
        DirectUI::Value::Release(v13);
      }
    }
  }
LABEL_20:
  if ( v14 )
    DirectUI::Value::Release(v14);
}

```

## disassembly

```asm
0x18003681c  mov     [rsp+arg_0], rbx
0x180036821  push    rsi
0x180036822  push    rdi
0x180036823  push    r15
0x180036825  sub     rsp, 30h
0x180036829  mov     rbx, rdx
0x18003682c  mov     [rsp+48h+arg_18], 0
0x180036835  mov     rsi, rcx
0x180036838  lea     rdx, [rsp+48h+arg_18]
0x18003683d  mov     rcx, [rbx]
0x180036840  call    cs:__imp_?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetClass(DirectUI::Value * *)
0x180036847  nop     dword ptr [rax+rax+00h]
0x18003684c  mov     rdi, rax
0x18003684f  test    rax, rax
0x180036852  jz      loc_1800369C0
0x180036858  or      r15d, 0FFFFFFFFh
0x18003685c  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180036864  mov     r9d, r15d; cchCount2
0x180036867  lea     r8, aThemebutton; "ThemeButton"
0x18003686e  mov     edx, r15d; cchCount1
0x180036871  mov     rcx, rax; lpString1
0x180036874  call    cs:__imp_CompareStringOrdinal
0x18003687b  nop     dword ptr [rax+rax+00h]
0x180036880  cmp     eax, 2
0x180036883  jnz     short loc_180036896
0x180036885  lea     rcx, [rsi+30h]; this
0x180036889  mov     rdx, rbx; struct DirectUI::InputEvent *
0x18003688c  call    ?OnInput@CGallery@@QEAAXPEAUInputEvent@DirectUI@@@Z; CGallery::OnInput(DirectUI::InputEvent *)
0x180036891  jmp     loc_1800369C0
0x180036896  cmp     dword ptr [rbx+10h], 1
0x18003689a  jnz     loc_1800369C0
0x1800368a0  mov     r9d, r15d; cchCount2
0x1800368a3  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x1800368ab  lea     r8, aThemeelementgr; "ThemeElementGroup"
0x1800368b2  mov     edx, r15d; cchCount1
0x1800368b5  mov     rcx, rdi; lpString1
0x1800368b8  call    cs:__imp_CompareStringOrdinal
0x1800368bf  nop     dword ptr [rax+rax+00h]
0x1800368c4  cmp     eax, 2
0x1800368c7  jnz     loc_1800369C0
0x1800368cd  cmp     dword ptr [rbx+0Ch], 1
0x1800368d1  jnz     loc_1800369C0
0x1800368d7  cmp     dword ptr [rbx+14h], 1
0x1800368db  jnz     loc_1800369E5
0x1800368e1  mov     eax, 20h ; ' '
0x1800368e6  cmp     ax, [rbx+20h]
0x1800368ea  jnz     loc_1800369C0
0x1800368f0  mov     rcx, [rbx]
0x1800368f3  lea     rdx, [rsp+48h+arg_10]
0x1800368f8  mov     [rsp+48h+arg_10], 0
0x180036901  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180036908  nop     dword ptr [rax+rax+00h]
0x18003690d  test    rax, rax
0x180036910  jz      loc_1800369C0
0x180036916  test    dword ptr [rax], 0FFFFFFFh
0x18003691c  jbe     loc_1800369C0
0x180036922  test    dword ptr [rax], 10000000h
0x180036928  lea     rbx, [rax+8]
0x18003692c  jz      short loc_180036931
0x18003692e  mov     rbx, [rbx]
0x180036931  mov     rbx, [rbx]
0x180036934  test    rbx, rbx
0x180036937  jz      short loc_1800369AF
0x180036939  lea     rdx, [rsp+48h+arg_8]
0x18003693e  mov     [rsp+48h+arg_8], 0
0x180036947  mov     rcx, rbx
0x18003694a  call    cs:__imp_?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetClass(DirectUI::Value * *)
0x180036951  nop     dword ptr [rax+rax+00h]
0x180036956  cmp     [rsp+48h+arg_8], 0
0x18003695c  jz      short loc_1800369AF
0x18003695e  test    rax, rax
0x180036961  jz      short loc_1800369AF
0x180036963  mov     r9d, r15d; cchCount2
0x180036966  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18003696e  lea     r8, aThemeelementic; "ThemeElementIcon"
0x180036975  mov     edx, r15d; cchCount1
0x180036978  mov     rcx, rax; lpString1
0x18003697b  call    cs:__imp_CompareStringOrdinal
0x180036982  nop     dword ptr [rax+rax+00h]
0x180036987  cmp     eax, 2
0x18003698a  jnz     short loc_1800369AF
0x18003698c  mov     rax, [rbx]
0x18003698f  mov     rcx, rbx
0x180036992  mov     rax, [rax+128h]
0x180036999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003699e  mov     rcx, [rsp+48h+arg_8]
0x1800369a3  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800369aa  nop     dword ptr [rax+rax+00h]
0x1800369af  mov     rcx, [rsp+48h+arg_10]
0x1800369b4  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800369bb  nop     dword ptr [rax+rax+00h]
0x1800369c0  mov     rcx, [rsp+48h+arg_18]
0x1800369c5  test    rcx, rcx
0x1800369c8  jz      short loc_1800369D6
0x1800369ca  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800369d1  nop     dword ptr [rax+rax+00h]
0x1800369d6  mov     rbx, [rsp+48h+arg_0]
0x1800369db  add     rsp, 30h
0x1800369df  pop     r15
0x1800369e1  pop     rdi
0x1800369e2  pop     rsi
0x1800369e3  retn
0x1800369e5  cmp     dword ptr [rbx+14h], 0
0x1800369e9  jnz     short loc_1800369C0
0x1800369eb  mov     eax, 0Dh
0x1800369f0  jmp     loc_1800368E6
```
