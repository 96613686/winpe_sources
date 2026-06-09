# CInfraConnectPage::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x1800216ac`
- end: `0x1800219cf`
- name: `?OnInitDialog@CInfraConnectPage@@QEAA_JI_K_JAEAH@Z`
- size: `803`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009840`

## callees

- `0x1800036ac`
- `0x1800079b0`
- `0x180008484`
- `0x180020800`
- `0x180020ab0`
- `0x180021078`
- `0x1800216ac`
- `0x180023054`
- `0x180030010`

## import_xrefs

- `USER32!SendMessageW` at `0x1800217b5`
- `USER32!SendMessageW` at `0x180021853`
- `USER32!SendMessageW` at `0x18002186c`
- `USER32!SendMessageW` at `0x180021884`
- `USER32!SendMessageW` at `0x1800217b5`
- `USER32!SendMessageW` at `0x180021853`
- `USER32!SendMessageW` at `0x18002186c`
- `USER32!SendMessageW` at `0x180021884`
- `wlanapi!WlanQueryCreateAllUserProfileRestricted` at `0x18002195a`
- `wlanapi!WlanQueryCreateAllUserProfileRestricted` at `0x18002195a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInfraConnectPage::OnInitDialog(CInfraConnectPage *this, int a2, LPARAM a3, __int64 a4, int *a5)
{
  _OWORD **v6; // rbx
  int v7; // eax
  bool v8; // al
  int v10; // [rsp+58h] [rbp+28h] BYREF
  LPARAM lParam; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  v12 = a4;
  lParam = a3;
  v10 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 14, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  lParam = (LPARAM)WTL::_atltmpPchNil;
  *((_QWORD *)this + 36) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10304);
  *((_QWORD *)this + 37) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10307);
  *((_QWORD *)this + 38) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10305);
  *((_QWORD *)this + 39) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10306);
  *((_QWORD *)this + 40) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10303);
  *((_QWORD *)this + 35) = SendMessageW(*((HWND *)this + 36), 0xD2u, 0, 0);
  *((_QWORD *)this + 41) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10336);
  *((_QWORD *)this + 42) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10337);
  *((_QWORD *)this + 43) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10328);
  *((_QWORD *)this + 44) = *(_QWORD *)ATL::CWindow::GetDlgItem((char *)this + 104, &v12, 10334);
  WTL::CString::LoadStringW((WTL::CString *)&lParam, 0x2ABBu);
  SendMessageW(*((HWND *)this + 38), 0x1703u, 0, lParam);
  SendMessageW(*((HWND *)this + 40), 0xC5u, 0x20u, 0);
  SendMessageW(*((HWND *)this + 36), 0xCCu, 0, 0);
  CTooltip::Init((CInfraConnectPage *)((char *)this + 376), *((HWND *)this + 13));
  CTooltip::AddTool((CInfraConnectPage *)((char *)this + 376), 0x2840u, 0x2906u);
  CTooltip::AddTool((CInfraConnectPage *)((char *)this + 376), 0x283Fu, 0x2907u);
  v6 = (_OWORD **)((char *)this + 1512);
  v7 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, char *, _QWORD))(**((_QWORD **)this + 11) + 48LL))(
         *((_QWORD *)this + 11),
         (char *)this + 64,
         L"ProfileData",
         (char *)this + 1512,
         0);
  if ( v7 >= 0 )
  {
    if ( *v6 )
      *(_OWORD *)((char *)this + 360) = **v6;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 145)
         && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      15,
      WPP_1064fdabddc73196039d87943bb008b3_Traceguids,
      (unsigned int)v7);
  }
  LODWORD(v12) = 0;
  v10 = 0;
  WlanQueryCreateAllUserProfileRestricted(&v10, &v12);
  v8 = v10 != 0;
  *((_BYTE *)this + 1507) = v10 != 0;
  *((_BYTE *)this + 1502) = !v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  *a5 = 1;
  WTL::CString::~CString((WTL::CString *)&lParam);
  return 1;
}

```

## disassembly

```asm
0x1800216ac  mov     rax, rsp
0x1800216af  mov     [rax+8], rbx
0x1800216b3  mov     [rax+20h], r9
0x1800216b7  mov     [rax+18h], r8
0x1800216bb  mov     [rax+10h], edx
0x1800216be  push    rbp
0x1800216bf  push    rsi
0x1800216c0  push    rdi
0x1800216c1  mov     rbp, rsp
0x1800216c4  sub     rsp, 30h
0x1800216c8  mov     rsi, rcx
0x1800216cb  lea     rax, WPP_GLOBAL_Control
0x1800216d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216d9  cmp     rcx, rax
0x1800216dc  jz      short loc_180021708
0x1800216de  cmp     byte ptr [rcx+91h], 4
0x1800216e5  jb      short loc_180021708
0x1800216e7  test    byte ptr [rcx+94h], 1
0x1800216ee  jz      short loc_180021708
0x1800216f0  mov     edx, 0Eh
0x1800216f5  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x1800216fc  mov     rcx, [rcx+88h]
0x180021703  call    WPP_SF_
0x180021708  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18002170f  mov     [rbp+lParam], rax
0x180021713  lea     rdi, [rsi+68h]
0x180021717  mov     r8d, 2840h
0x18002171d  lea     rdx, [rbp+arg_18]
0x180021721  mov     rcx, rdi
0x180021724  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021729  mov     rax, [rax]
0x18002172c  mov     [rsi+120h], rax
0x180021733  mov     r8d, 2843h
0x180021739  lea     rdx, [rbp+arg_18]
0x18002173d  mov     rcx, rdi
0x180021740  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021745  mov     rcx, [rax]
0x180021748  mov     [rsi+128h], rcx
0x18002174f  mov     r8d, 2841h
0x180021755  lea     rdx, [rbp+arg_18]
0x180021759  mov     rcx, rdi
0x18002175c  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021761  mov     rax, [rax]
0x180021764  mov     [rsi+130h], rax
0x18002176b  mov     r8d, 2842h
0x180021771  lea     rdx, [rbp+arg_18]
0x180021775  mov     rcx, rdi
0x180021778  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002177d  mov     rcx, [rax]
0x180021780  mov     [rsi+138h], rcx
0x180021787  mov     r8d, 283Fh
0x18002178d  lea     rdx, [rbp+arg_18]
0x180021791  mov     rcx, rdi
0x180021794  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021799  mov     rax, [rax]
0x18002179c  mov     [rsi+140h], rax
0x1800217a3  xor     r9d, r9d; lParam
0x1800217a6  xor     r8d, r8d; wParam
0x1800217a9  mov     edx, 0D2h; Msg
0x1800217ae  mov     rcx, [rsi+120h]; hWnd
0x1800217b5  call    cs:__imp_SendMessageW
0x1800217bb  mov     [rsi+118h], rax
0x1800217c2  mov     r8d, 2860h
0x1800217c8  lea     rdx, [rbp+arg_18]
0x1800217cc  mov     rcx, rdi
0x1800217cf  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800217d4  mov     rcx, [rax]
0x1800217d7  mov     [rsi+148h], rcx
0x1800217de  mov     r8d, 2861h
0x1800217e4  lea     rdx, [rbp+arg_18]
0x1800217e8  mov     rcx, rdi
0x1800217eb  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800217f0  mov     rcx, [rax]
0x1800217f3  mov     [rsi+150h], rcx
0x1800217fa  mov     r8d, 2858h
0x180021800  lea     rdx, [rbp+arg_18]
0x180021804  mov     rcx, rdi
0x180021807  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002180c  mov     rcx, [rax]
0x18002180f  mov     [rsi+158h], rcx
0x180021816  mov     r8d, 285Eh
0x18002181c  lea     rdx, [rbp+arg_18]
0x180021820  mov     rcx, rdi
0x180021823  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180021828  mov     rcx, [rax]
0x18002182b  mov     [rsi+160h], rcx
0x180021832  mov     edx, 2ABBh; uID
0x180021837  lea     rcx, [rbp+lParam]; this
0x18002183b  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180021840  mov     r9, [rbp+lParam]; lParam
0x180021844  xor     r8d, r8d; wParam
0x180021847  mov     edx, 1703h; Msg
0x18002184c  mov     rcx, [rsi+130h]; hWnd
0x180021853  call    cs:__imp_SendMessageW
0x180021859  xor     r9d, r9d; lParam
0x18002185c  mov     edx, 0C5h; Msg
0x180021861  lea     r8d, [r9+20h]; wParam
0x180021865  mov     rcx, [rsi+140h]; hWnd
0x18002186c  call    cs:__imp_SendMessageW
0x180021872  xor     r9d, r9d; lParam
0x180021875  xor     r8d, r8d; wParam
0x180021878  mov     edx, 0CCh; Msg
0x18002187d  mov     rcx, [rsi+120h]; hWnd
0x180021884  call    cs:__imp_SendMessageW
0x18002188a  lea     rbx, [rsi+178h]
0x180021891  mov     rdx, [rdi]; HWND
0x180021894  mov     rcx, rbx; this
0x180021897  call    ?Init@CTooltip@@QEAAKPEAUHWND__@@@Z; CTooltip::Init(HWND__ *)
0x18002189c  mov     edx, 2840h; unsigned int
0x1800218a1  mov     r8d, 2906h; unsigned int
0x1800218a7  mov     rcx, rbx; this
0x1800218aa  call    ?AddTool@CTooltip@@QEBAXIIZZ; CTooltip::AddTool(uint,uint,...)
0x1800218af  mov     edx, 283Fh; unsigned int
0x1800218b4  mov     r8d, 2907h; unsigned int
0x1800218ba  mov     rcx, rbx; this
0x1800218bd  call    ?AddTool@CTooltip@@QEBAXIIZZ; CTooltip::AddTool(uint,uint,...)
0x1800218c2  mov     rcx, [rsi+58h]
0x1800218c6  lea     rbx, [rsi+5E8h]
0x1800218cd  mov     rax, [rcx]
0x1800218d0  lea     rdx, [rsi+40h]
0x1800218d4  xor     edi, edi
0x1800218d6  mov     [rsp+30h+var_10], rdi
0x1800218db  mov     r9, rbx
0x1800218de  lea     r8, aProfiledata; "ProfileData"
0x1800218e5  mov     rax, [rax+30h]
0x1800218e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ee  test    eax, eax
0x1800218f0  jns     short loc_180021932
0x1800218f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218f9  lea     rbx, WPP_GLOBAL_Control
0x180021900  cmp     rcx, rbx
0x180021903  jz      short loc_18002194C
0x180021905  cmp     byte ptr [rcx+91h], 1
0x18002190c  jb      short loc_18002194C
0x18002190e  test    byte ptr [rcx+94h], 1
0x180021915  jz      short loc_18002194C
0x180021917  lea     edx, [rdi+0Fh]
0x18002191a  mov     r9d, eax
0x18002191d  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180021924  mov     rcx, [rcx+88h]
0x18002192b  call    WPP_SF_d
0x180021930  jmp     short loc_18002194C
0x180021932  mov     rax, [rbx]
0x180021935  lea     rbx, WPP_GLOBAL_Control
0x18002193c  test    rax, rax
0x18002193f  jz      short loc_18002194C
0x180021941  movups  xmm0, xmmword ptr [rax]
0x180021944  movdqu  xmmword ptr [rsi+168h], xmm0
0x18002194c  mov     dword ptr [rbp+arg_18], edi
0x18002194f  mov     [rbp+arg_8], edi
0x180021952  lea     rdx, [rbp+arg_18]
0x180021956  lea     rcx, [rbp+arg_8]
0x18002195a  call    cs:__imp_WlanQueryCreateAllUserProfileRestricted
0x180021960  cmp     [rbp+arg_8], edi
0x180021963  setnz   al
0x180021966  mov     [rsi+5E3h], al
0x18002196c  xor     al, 1
0x18002196e  mov     [rsi+5DEh], al
0x180021974  mov     rcx, cs:WPP_GLOBAL_Control
0x18002197b  cmp     rcx, rbx
0x18002197e  jz      short loc_1800219AA
0x180021980  cmp     byte ptr [rcx+91h], 4
0x180021987  jb      short loc_1800219AA
0x180021989  test    byte ptr [rcx+94h], 1
0x180021990  jz      short loc_1800219AA
0x180021992  mov     edx, 10h
0x180021997  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x18002199e  mov     rcx, [rcx+88h]
0x1800219a5  call    WPP_SF_
0x1800219aa  mov     rcx, [rbp+arg_20]
0x1800219ae  mov     dword ptr [rcx], 1
0x1800219b4  lea     rcx, [rbp+lParam]; this
0x1800219b8  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800219bd  mov     eax, 1
0x1800219c2  mov     rbx, [rsp+30h+arg_0]
0x1800219c7  add     rsp, 30h
0x1800219cb  pop     rdi
0x1800219cc  pop     rsi
0x1800219cd  pop     rbp
0x1800219ce  retn
```
