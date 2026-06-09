# CUAMSettingsPageElement::_CustomizeConnectAccountDUI(IUserData *)

- ea: `0x18002947c`
- end: `0x1800296d8`
- name: `?_CustomizeConnectAccountDUI@CUAMSettingsPageElement@@AEAAXPEAUIUserData@@@Z`
- size: `604`
- prototype: `void __fastcall(CUAMSettingsPageElement *__hidden this, struct IUserData *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027dd0`
- `0x1800296e0`

## callees

- `0x180015f4c`
- `0x180024948`
- `0x18002947c`
- `0x1800704bc`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029534`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029620`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800294b8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800294df`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002959c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029657`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800296c1`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800294b8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800294df`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002959c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180029657`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800296c1`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800295c9`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002960b`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800295c9`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002960b`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800296b5`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800296b5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800295d5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029617`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800295d5`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180029617`
- `DUI70!StrToID` at `0x180029499`
- `DUI70!StrToID` at `0x1800294c5`
- `DUI70!StrToID` at `0x1800295ae`
- `DUI70!StrToID` at `0x1800295f0`
- `DUI70!StrToID` at `0x18002963f`
- `DUI70!StrToID` at `0x180029499`
- `DUI70!StrToID` at `0x1800294c5`
- `DUI70!StrToID` at `0x1800295ae`
- `DUI70!StrToID` at `0x1800295f0`
- `DUI70!StrToID` at `0x18002963f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800294a5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800294d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800295ba`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800295fc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002964b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800294a5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800294d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800295ba`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800295fc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002964b`
- `USER32!GetSystemMetrics` at `0x1800296a6`
- `USER32!GetSystemMetrics` at `0x1800296a6`

## string_xrefs

- `0x1800294be`: `idUAMSettingsPageMoreSettingsLink`

## pseudocode

```c
void __fastcall CUAMSettingsPageElement::_CustomizeConnectAccountDUI(
        CUAMSettingsPageElement *this,
        struct IUserData *a2)
{
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // r14
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rbx
  int v8; // eax
  char v9; // cl
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // rdi
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rax
  bool v18; // dl

  v4 = StrToID(L"idConnectOptions");
  Descendent = DirectUI::Element::FindDescendent(this, v4);
  DirectUI::Element::SetLayoutPos(Descendent, -3);
  v6 = StrToID(L"idUAMSettingsPageMoreSettingsLink");
  v7 = DirectUI::Element::FindDescendent(this, v6);
  DirectUI::Element::SetLayoutPos(v7, -3);
  v8 = (*(__int64 (__fastcall **)(struct IUserData *))(*(_QWORD *)a2 + 24LL))(a2);
  v9 = *((_BYTE *)this + 252);
  if ( v8 )
  {
    if ( !v9 )
      goto LABEL_11;
    v10 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2193);
    v11 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2194);
    DirectUI::Element::SetLayoutPos(v7, -1);
  }
  else if ( v9 )
  {
    CoTaskMemFree(0);
    v10 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2177);
    v11 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2168);
    CoTaskMemFree(0);
  }
  else
  {
    v10 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2165);
    v11 = (unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 2166);
  }
  if ( v10 )
  {
    v12 = StrToID(L"idConnectText");
    v13 = DirectUI::Element::FindDescendent(this, v12);
    DirectUI::Element::SetContentString(v13, v10);
    DirectUI::Element::SetAccName(v13, v10);
    LocalFree(v10);
  }
  if ( v11 )
  {
    v14 = StrToID(L"idConnectButton");
    v15 = DirectUI::Element::FindDescendent(this, v14);
    DirectUI::Element::SetContentString(v15, v11);
    DirectUI::Element::SetAccName(v15, v11);
    LocalFree(v11);
  }
LABEL_11:
  if ( (ConnectedUserGP() & 1) != 0 && !*((_BYTE *)this + 252) )
  {
    v16 = StrToID(L"idUAMSettingsPageGPRestrictionsText");
    v17 = DirectUI::Element::FindDescendent(this, v16);
    DirectUI::Element::SetLayoutPos(v17, -1);
    v18 = 0;
LABEL_19:
    DirectUI::Element::SetEnabled(Descendent, v18);
    DirectUI::Element::SetLayoutPos(Descendent, -1);
    return;
  }
  if ( !(unsigned int)IsOS_OS_ANYSERVER()
    && (*(unsigned int (__fastcall **)(_QWORD, struct IUserData *))(**((_QWORD **)this + 27) + 120LL))(
         *((_QWORD *)this + 27),
         a2)
    && (*(unsigned int (__fastcall **)(_QWORD, struct IUserData *))(**((_QWORD **)this + 27) + 128LL))(
         *((_QWORD *)this + 27),
         a2)
    && !GetSystemMetrics(67) )
  {
    v18 = 1;
    goto LABEL_19;
  }
}

```

## disassembly

```asm
0x18002947c  mov     [rsp+arg_10], rbx
0x180029481  push    rbp
0x180029482  push    rsi
0x180029483  push    rdi
0x180029484  push    r14
0x180029486  push    r15
0x180029488  sub     rsp, 20h
0x18002948c  mov     rbp, rcx
0x18002948f  mov     r15, rdx
0x180029492  lea     rcx, aIdconnectoptio; "idConnectOptions"
0x180029499  call    cs:__imp_StrToID
0x18002949f  movzx   edx, ax
0x1800294a2  mov     rcx, rbp
0x1800294a5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800294ab  mov     edi, 0FFFFFFFDh
0x1800294b0  mov     rcx, rax
0x1800294b3  mov     edx, edi
0x1800294b5  mov     r14, rax
0x1800294b8  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800294be  lea     rcx, aIduamsettingsp_2; "idUAMSettingsPageMoreSettingsLink"
0x1800294c5  call    cs:__imp_StrToID
0x1800294cb  movzx   edx, ax
0x1800294ce  mov     rcx, rbp
0x1800294d1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800294d7  mov     rcx, rax
0x1800294da  mov     edx, edi
0x1800294dc  mov     rbx, rax
0x1800294df  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800294e5  mov     rcx, [r15]
0x1800294e8  mov     rax, [rcx+18h]
0x1800294ec  mov     rcx, r15
0x1800294ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294f4  mov     cl, [rbp+0FCh]
0x1800294fa  test    eax, eax
0x1800294fc  jnz     short loc_180029566
0x1800294fe  test    cl, cl
0x180029500  jz      short loc_18002953C
0x180029502  xor     ecx, ecx; pv
0x180029504  call    cs:__imp_CoTaskMemFree
0x18002950a  mov     rcx, cs:g_hinst
0x180029511  mov     edx, 881h
0x180029516  call    ShellConstructMessageStringW
0x18002951b  mov     rcx, cs:g_hinst
0x180029522  mov     edx, 878h
0x180029527  mov     rsi, rax
0x18002952a  call    ShellConstructMessageStringW
0x18002952f  xor     ecx, ecx; pv
0x180029531  mov     rdi, rax
0x180029534  call    cs:__imp_CoTaskMemFree
0x18002953a  jmp     short loc_1800295A2
0x18002953c  mov     rcx, cs:g_hinst
0x180029543  mov     edx, 875h
0x180029548  call    ShellConstructMessageStringW
0x18002954d  mov     rcx, cs:g_hinst
0x180029554  mov     edx, 876h
0x180029559  mov     rsi, rax
0x18002955c  call    ShellConstructMessageStringW
0x180029561  mov     rdi, rax
0x180029564  jmp     short loc_1800295A2
0x180029566  test    cl, cl
0x180029568  jz      loc_180029626
0x18002956e  mov     rcx, cs:g_hinst
0x180029575  mov     edx, 891h
0x18002957a  call    ShellConstructMessageStringW
0x18002957f  mov     rcx, cs:g_hinst
0x180029586  mov     edx, 892h
0x18002958b  mov     rsi, rax
0x18002958e  call    ShellConstructMessageStringW
0x180029593  or      edx, 0FFFFFFFFh
0x180029596  mov     rcx, rbx
0x180029599  mov     rdi, rax
0x18002959c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800295a2  test    rsi, rsi
0x1800295a5  jz      short loc_1800295E4
0x1800295a7  lea     rcx, aIdconnecttext; "idConnectText"
0x1800295ae  call    cs:__imp_StrToID
0x1800295b4  movzx   edx, ax
0x1800295b7  mov     rcx, rbp
0x1800295ba  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800295c0  mov     rcx, rax
0x1800295c3  mov     rdx, rsi
0x1800295c6  mov     rbx, rax
0x1800295c9  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800295cf  mov     rdx, rsi
0x1800295d2  mov     rcx, rbx
0x1800295d5  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1800295db  mov     rcx, rsi; hMem
0x1800295de  call    cs:__imp_LocalFree
0x1800295e4  test    rdi, rdi
0x1800295e7  jz      short loc_180029626
0x1800295e9  lea     rcx, aIdconnectbutto; "idConnectButton"
0x1800295f0  call    cs:__imp_StrToID
0x1800295f6  movzx   edx, ax
0x1800295f9  mov     rcx, rbp
0x1800295fc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180029602  mov     rcx, rax
0x180029605  mov     rdx, rdi
0x180029608  mov     rbx, rax
0x18002960b  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180029611  mov     rdx, rdi
0x180029614  mov     rcx, rbx
0x180029617  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18002961d  mov     rcx, rdi; hMem
0x180029620  call    cs:__imp_LocalFree
0x180029626  call    ?ConnectedUserGP@@YA?AW4CONNECTED_USER_GPFLAGS@@XZ; ConnectedUserGP(void)
0x18002962b  test    al, 1
0x18002962d  jz      short loc_180029661
0x18002962f  cmp     byte ptr [rbp+0FCh], 0
0x180029636  jnz     short loc_180029661
0x180029638  lea     rcx, aIduamsettingsp; "idUAMSettingsPageGPRestrictionsText"
0x18002963f  call    cs:__imp_StrToID
0x180029645  movzx   edx, ax
0x180029648  mov     rcx, rbp
0x18002964b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180029651  mov     rcx, rax
0x180029654  or      edx, 0FFFFFFFFh
0x180029657  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18002965d  xor     edx, edx
0x18002965f  jmp     short loc_1800296B2
0x180029661  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x180029666  test    eax, eax
0x180029668  jnz     short loc_1800296C7
0x18002966a  mov     rcx, [rbp+0D8h]
0x180029671  mov     rdx, r15
0x180029674  mov     rax, [rcx]
0x180029677  mov     rax, [rax+78h]
0x18002967b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029680  test    eax, eax
0x180029682  jz      short loc_1800296C7
0x180029684  mov     rcx, [rbp+0D8h]
0x18002968b  mov     rdx, r15
0x18002968e  mov     rax, [rcx]
0x180029691  mov     rax, [rax+80h]
0x180029698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002969d  test    eax, eax
0x18002969f  jz      short loc_1800296C7
0x1800296a1  mov     ecx, 43h ; 'C'; nIndex
0x1800296a6  call    cs:__imp_GetSystemMetrics
0x1800296ac  test    eax, eax
0x1800296ae  jnz     short loc_1800296C7
0x1800296b0  mov     dl, 1
0x1800296b2  mov     rcx, r14
0x1800296b5  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x1800296bb  or      edx, 0FFFFFFFFh
0x1800296be  mov     rcx, r14
0x1800296c1  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800296c7  mov     rbx, [rsp+48h+arg_10]
0x1800296cc  add     rsp, 20h
0x1800296d0  pop     r15
0x1800296d2  pop     r14
0x1800296d4  pop     rdi
0x1800296d5  pop     rsi
0x1800296d6  pop     rbp
0x1800296d7  retn
```
