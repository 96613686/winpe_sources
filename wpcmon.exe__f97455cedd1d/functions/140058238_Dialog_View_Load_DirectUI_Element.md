# Dialog::View::Load(DirectUI::Element &)

- ea: `0x140058238`
- end: `0x140058420`
- name: `?Load@View@Dialog@@QEBAXAEAVElement@DirectUI@@@Z`
- size: `488`
- prototype: `void __fastcall(Dialog::View *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14005a6ec`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001f6b4`
- `0x140057a50`
- `0x140058238`
- `0x14005bbac`
- `0x140060f58`
- `0x1400a8010`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x14005827d`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x14005827d`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1400582c3`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1400582c3`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140058305`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140058305`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Dialog::View::Load(Dialog::View *this, struct DirectUI::Element *a2)
{
  int v4; // eax
  int v5; // ebx
  HINSTANCE v6; // rax
  int v7; // eax
  int v8; // ebx
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  int v11; // ebx
  struct DirectUI::DUIXmlParser *v12; // [rsp+30h] [rbp-49h] BYREF
  struct DirectUI::DUIXmlParser *v13; // [rsp+38h] [rbp-41h] BYREF
  struct DirectUI::Element *v14; // [rsp+40h] [rbp-39h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v16[64]; // [rsp+70h] [rbp-9h] BYREF

  v12 = 0;
  v4 = DirectUI::DUIXmlParser::Create(&v12, 0, 0, 0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_3acaceed2b2a313cc827601c5575da02_Traceguids,
        (unsigned int)v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v13 = v12;
  ScopeGuard::ScopeGuard__lambda_05ca8d340832b7c9767cf5b3be4c43cc___(v16, &v13);
  v6 = (HINSTANCE)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  v7 = DirectUI::DUIXmlParser::SetXMLFromResource(v12, *((_DWORD *)this + 10), v6, &_ImageBase);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_3acaceed2b2a313cc827601c5575da02_Traceguids,
        (unsigned int)v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v14 = 0;
  v9 = (const unsigned __int16 *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) > 7u )
    v9 = *(const unsigned __int16 **)v9;
  v10 = DirectUI::DUIXmlParser::CreateElement(v12, v9, a2, 0, 0, &v14);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_3acaceed2b2a313cc827601c5575da02_Traceguids,
        (unsigned int)v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ScopeGuard::~ScopeGuard((ScopeGuard *)v16);
}

```

## disassembly

```asm
0x140058238  mov     [rsp-8+arg_10], rbx
0x14005823d  push    rbp
0x14005823e  push    rsi
0x14005823f  push    rdi
0x140058240  lea     rbp, [rsp-47h]
0x140058245  sub     rsp, 0C0h
0x14005824c  mov     rax, cs:__security_cookie
0x140058253  xor     rax, rsp
0x140058256  mov     [rbp+57h+var_20], rax
0x14005825a  mov     rsi, rdx
0x14005825d  mov     rdi, rcx
0x140058260  mov     [rbp+57h+var_A0], 0
0x140058268  mov     [rsp+0D0h+var_B0], 0
0x140058271  xor     r9d, r9d
0x140058274  xor     r8d, r8d
0x140058277  xor     edx, edx
0x140058279  lea     rcx, [rbp+57h+var_A0]
0x14005827d  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x140058283  mov     ebx, eax
0x140058285  test    eax, eax
0x140058287  js      loc_140058386
0x14005828d  mov     rax, [rbp+57h+var_A0]
0x140058291  mov     [rbp+57h+var_98], rax
0x140058295  lea     rdx, [rbp+57h+var_98]
0x140058299  lea     rcx, [rbp+57h+var_60]
0x14005829d  call    ScopeGuard__ScopeGuard__lambda_05ca8d340832b7c9767cf5b3be4c43cc___
0x1400582a2  nop
0x1400582a3  mov     rcx, [rdi]
0x1400582a6  mov     rax, [rcx]
0x1400582a9  mov     rax, [rax+8]
0x1400582ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400582b2  lea     r9, __ImageBase
0x1400582b9  mov     r8, rax
0x1400582bc  mov     edx, [rdi+28h]
0x1400582bf  mov     rcx, [rbp+57h+var_A0]
0x1400582c3  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1400582c9  mov     ebx, eax
0x1400582cb  test    eax, eax
0x1400582cd  js      loc_1400583D3
0x1400582d3  mov     [rbp+57h+var_90], 0
0x1400582db  lea     rdx, [rdi+30h]
0x1400582df  cmp     qword ptr [rdx+18h], 7
0x1400582e4  jbe     short loc_1400582E9
0x1400582e6  mov     rdx, [rdx]
0x1400582e9  lea     rax, [rbp+57h+var_90]
0x1400582ed  mov     [rsp+0D0h+var_A8], rax
0x1400582f2  mov     [rsp+0D0h+var_B0], 0
0x1400582fb  xor     r9d, r9d
0x1400582fe  mov     r8, rsi
0x140058301  mov     rcx, [rbp+57h+var_A0]
0x140058305  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14005830b  mov     ebx, eax
0x14005830d  test    eax, eax
0x14005830f  js      short loc_140058339
0x140058311  lea     rcx, [rbp+57h+var_60]; this
0x140058315  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x14005831a  mov     rcx, [rbp+57h+var_20]
0x14005831e  xor     rcx, rsp; StackCookie
0x140058321  call    __security_check_cookie
0x140058326  mov     rbx, [rsp+0D0h+arg_10]
0x14005832e  add     rsp, 0C0h
0x140058335  pop     rdi
0x140058336  pop     rsi
0x140058337  pop     rbp
0x140058338  retn
0x140058339  lea     rdx, WPP_GLOBAL_Control
0x140058340  mov     rcx, cs:WPP_GLOBAL_Control
0x140058347  cmp     rcx, rdx
0x14005834a  jz      short loc_14005836A
0x14005834c  test    byte ptr [rcx+1Ch], 1
0x140058350  jz      short loc_14005836A
0x140058352  mov     edx, 0Dh
0x140058357  mov     r9d, ebx
0x14005835a  lea     r8, WPP_3acaceed2b2a313cc827601c5575da02_Traceguids
0x140058361  mov     rcx, [rcx+10h]
0x140058365  call    WPP_SF_d
0x14005836a  mov     edx, ebx; int
0x14005836c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140058370  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140058375  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14005837c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140058380  call    _CxxThrowException_0
0x140058386  lea     rdx, WPP_GLOBAL_Control
0x14005838d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058394  cmp     rcx, rdx
0x140058397  jz      short loc_1400583B7
0x140058399  test    byte ptr [rcx+1Ch], 1
0x14005839d  jz      short loc_1400583B7
0x14005839f  mov     edx, 0Bh
0x1400583a4  mov     r9d, ebx
0x1400583a7  lea     r8, WPP_3acaceed2b2a313cc827601c5575da02_Traceguids
0x1400583ae  mov     rcx, [rcx+10h]
0x1400583b2  call    WPP_SF_d
0x1400583b7  mov     edx, ebx; int
0x1400583b9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400583bd  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400583c2  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400583c9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400583cd  call    _CxxThrowException_0
0x1400583d3  lea     rdx, WPP_GLOBAL_Control
0x1400583da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400583e1  cmp     rcx, rdx
0x1400583e4  jz      short loc_140058404
0x1400583e6  test    byte ptr [rcx+1Ch], 1
0x1400583ea  jz      short loc_140058404
0x1400583ec  mov     edx, 0Ch
0x1400583f1  mov     r9d, ebx
0x1400583f4  lea     r8, WPP_3acaceed2b2a313cc827601c5575da02_Traceguids
0x1400583fb  mov     rcx, [rcx+10h]
0x1400583ff  call    WPP_SF_d
0x140058404  mov     edx, ebx; int
0x140058406  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14005840a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14005840f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140058416  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14005841a  call    _CxxThrowException_0
```
