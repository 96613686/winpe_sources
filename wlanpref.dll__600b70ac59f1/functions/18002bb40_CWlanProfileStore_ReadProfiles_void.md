# CWlanProfileStore::ReadProfiles(void)

- ea: `0x18002bb40`
- end: `0x18002bcd2`
- name: `?ReadProfiles@CWlanProfileStore@@MEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(CWlanProfileStore *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x1800036ac`
- `0x18000d4c8`
- `0x180011124`
- `0x18002749c`
- `0x180027594`
- `0x18002995c`
- `0x18002abf4`
- `0x18002bb40`
- `0x18002be90`
- `0x18002c8a8`
- `0x18002d840`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWlanProfileStore::ReadProfiles(CWlanProfileStore *this)
{
  int WlanProfiles; // ebx
  char *v3; // rsi
  char *v4; // r14
  _QWORD *i; // rdi
  CWlanProfileStore *v6; // rcx
  char *v7; // rcx
  _BYTE v9[16]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h]
  __int128 v12; // [rsp+48h] [rbp-B8h]
  int v13; // [rsp+58h] [rbp-A8h]
  _BYTE v14[28]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+7Ch] [rbp-84h]
  char v16; // [rsp+B1h] [rbp-4Fh]
  bool v17; // [rsp+B3h] [rbp-4Dh]
  _OWORD v18[33]; // [rsp+C0h] [rbp-40h] BYREF
  char v19; // [rsp+2D0h] [rbp+1D0h]
  const unsigned __int16 *v20; // [rsp+2D8h] [rbp+1D8h] BYREF
  int v21; // [rsp+2E0h] [rbp+1E0h]

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v9,
    (char *)this + 96);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 10;
  WlanProfiles = CWlanProfileStore::GetWlanProfiles(this, &CWlanProfileStore::m_adapter, &v10);
  if ( WlanProfiles >= 0 )
  {
    v3 = (char *)this + 136;
    ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll((char *)this + 136);
    v4 = (char *)this + 184;
    ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll((char *)this + 184);
    for ( i = (_QWORD *)v10; i; i = (_QWORD *)*i )
    {
      CWlanProfile::CWlanProfile((CWlanProfile *)v18, (const struct CWlanProfile *)(i + 2));
      CProfile::CProfile((CProfile *)v14);
      WlanProfiles = CWlanProfileStore::XmlToProfile(v6, &v20, (struct CProfile *)v14);
      if ( WlanProfiles < 0 )
      {
        CProfile::~CProfile((CProfile *)v14);
        WTL::CString::~CString((WTL::CString *)&v20);
        break;
      }
      v15 = v18[0];
      v17 = (v21 & 0x70023) == 458787;
      if ( (v19 & 1) != 0 )
      {
        v16 = 1;
        v7 = v3;
      }
      else
      {
        v16 = 0;
        v7 = v4;
      }
      ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(v7, v14);
      CProfile::~CProfile((CProfile *)v14);
      WTL::CString::~CString((WTL::CString *)&v20);
    }
  }
  ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(&v10);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v9);
  return (unsigned int)WlanProfiles;
}

```

## disassembly

```asm
0x18002bb40  mov     [rsp-8+arg_8], rbx
0x18002bb45  mov     [rsp-8+arg_10], rsi
0x18002bb4a  push    rbp
0x18002bb4b  push    rdi
0x18002bb4c  push    r14
0x18002bb4e  lea     rbp, [rsp-200h]
0x18002bb56  sub     rsp, 300h
0x18002bb5d  mov     rax, cs:__security_cookie
0x18002bb64  xor     rax, rsp
0x18002bb67  mov     [rbp+210h+var_20], rax
0x18002bb6e  mov     rdi, rcx
0x18002bb71  lea     rdx, [rcx+60h]
0x18002bb75  lea     rcx, [rsp+310h+var_2F0]
0x18002bb7a  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002bb7f  nop
0x18002bb80  xorps   xmm0, xmm0
0x18002bb83  movdqu  [rsp+310h+var_2E0], xmm0
0x18002bb89  mov     [rsp+310h+var_2D0], 0
0x18002bb92  movdqu  [rsp+310h+var_2C8], xmm0
0x18002bb98  mov     [rsp+310h+var_2B8], 0Ah
0x18002bba0  lea     r8, [rsp+310h+var_2E0]
0x18002bba5  lea     rdx, ?m_adapter@CWlanProfileStore@@0VCAdapter@@A; CAdapter CWlanProfileStore::m_adapter
0x18002bbac  mov     rcx, rdi
0x18002bbaf  call    ?GetWlanProfiles@CWlanProfileStore@@IEAAJAEBVCAdapter@@AEAV?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@@Z; CWlanProfileStore::GetWlanProfiles(CAdapter const &,ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>> &)
0x18002bbb4  mov     ebx, eax
0x18002bbb6  test    eax, eax
0x18002bbb8  js      loc_18002BC94
0x18002bbbe  lea     rsi, [rdi+88h]
0x18002bbc5  mov     rcx, rsi
0x18002bbc8  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x18002bbcd  lea     r14, [rdi+0B8h]
0x18002bbd4  mov     rcx, r14
0x18002bbd7  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x18002bbdc  mov     rdi, qword ptr [rsp+310h+var_2E0]
0x18002bbe1  test    rdi, rdi
0x18002bbe4  jz      loc_18002BC94
0x18002bbea  lea     rdx, [rdi+10h]; struct CWlanProfile *
0x18002bbee  lea     rcx, [rbp+210h+var_250]; this
0x18002bbf2  call    ??0CWlanProfile@@QEAA@AEBV0@@Z; CWlanProfile::CWlanProfile(CWlanProfile const &)
0x18002bbf7  nop
0x18002bbf8  lea     rcx, [rsp+310h+var_2B0]; this
0x18002bbfd  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x18002bc02  nop
0x18002bc03  lea     r8, [rsp+310h+var_2B0]; struct CProfile *
0x18002bc08  lea     rdx, [rbp+210h+var_38]; struct WTL::CString *
0x18002bc0f  call    ?XmlToProfile@CWlanProfileStore@@IEAAJAEBVCString@WTL@@AEAVCProfile@@@Z; CWlanProfileStore::XmlToProfile(WTL::CString const &,CProfile &)
0x18002bc14  mov     ebx, eax
0x18002bc16  test    eax, eax
0x18002bc18  js      short loc_18002BC7C
0x18002bc1a  movaps  xmm0, [rbp+210h+var_250]
0x18002bc1e  movdqu  [rsp+310h+var_294], xmm0
0x18002bc24  mov     eax, [rbp+210h+var_30]
0x18002bc2a  and     eax, 70023h
0x18002bc2f  cmp     eax, 70023h
0x18002bc34  setz    [rbp+210h+var_25D]
0x18002bc38  lea     rdx, [rsp+310h+var_2B0]
0x18002bc3d  test    [rbp+210h+var_40], 1
0x18002bc44  jz      short loc_18002BC4F
0x18002bc46  mov     [rbp+210h+var_25F], 1
0x18002bc4a  mov     rcx, rsi
0x18002bc4d  jmp     short loc_18002BC56
0x18002bc4f  mov     [rbp+210h+var_25F], 0
0x18002bc53  mov     rcx, r14
0x18002bc56  call    ?AddTail@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCProfile@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(CProfile const &)
0x18002bc5b  nop
0x18002bc5c  lea     rcx, [rsp+310h+var_2B0]; this
0x18002bc61  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18002bc66  nop
0x18002bc67  lea     rcx, [rbp+210h+var_38]; this
0x18002bc6e  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002bc73  nop
0x18002bc74  mov     rdi, [rdi]
0x18002bc77  jmp     loc_18002BBE1
0x18002bc7c  lea     rcx, [rsp+310h+var_2B0]; this
0x18002bc81  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18002bc86  nop
0x18002bc87  lea     rcx, [rbp+210h+var_38]; this
0x18002bc8e  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18002bc93  nop
0x18002bc94  lea     rcx, [rsp+310h+var_2E0]
0x18002bc99  call    ?RemoveAll@?$CAtlList@VCWlanProfile@@V?$CElementTraits@VCWlanProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CWlanProfile,ATL::CElementTraits<CWlanProfile>>::RemoveAll(void)
0x18002bc9e  nop
0x18002bc9f  lea     rcx, [rsp+310h+var_2F0]
0x18002bca4  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002bca9  mov     eax, ebx
0x18002bcab  mov     rcx, [rbp+210h+var_20]
0x18002bcb2  xor     rcx, rsp; StackCookie
0x18002bcb5  call    __security_check_cookie
0x18002bcba  lea     r11, [rsp+310h+var_10]
0x18002bcc2  mov     rbx, [r11+28h]
0x18002bcc6  mov     rsi, [r11+30h]
0x18002bcca  mov     rsp, r11
0x18002bccd  pop     r14
0x18002bccf  pop     rdi
0x18002bcd0  pop     rbp
0x18002bcd1  retn
```
