# ReadProperties(OOEBuf *)

- ea: `0x18000ce34`
- end: `0x18000d2e6`
- name: `?ReadProperties@@YAJPEAUOOEBuf@@@Z`
- size: `1202`
- prototype: `__int64 __fastcall(struct OOEBuf *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e150`

## callees

- `0x180003950`
- `0x18000ce34`
- `0x180019ae0`
- `0x18001d944`
- `0x18001dac0`
- `0x18001db30`
- `0x180027d0c`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ce90`
- `OLEAUT32!__imp_VariantInit` at `0x18000ce90`
- `OLEAUT32!__imp_VariantClear` at `0x18000cee0`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf2c`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf7e`
- `OLEAUT32!__imp_VariantClear` at `0x18000cfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18000cffc`
- `OLEAUT32!__imp_VariantClear` at `0x18000d03b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d07a`
- `OLEAUT32!__imp_VariantClear` at `0x18000d0b6`
- `OLEAUT32!__imp_VariantClear` at `0x18000d0f2`
- `OLEAUT32!__imp_VariantClear` at `0x18000d176`
- `OLEAUT32!__imp_VariantClear` at `0x18000d199`
- `OLEAUT32!__imp_VariantClear` at `0x18000cee0`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf2c`
- `OLEAUT32!__imp_VariantClear` at `0x18000cf7e`
- `OLEAUT32!__imp_VariantClear` at `0x18000cfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18000cffc`
- `OLEAUT32!__imp_VariantClear` at `0x18000d03b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d07a`
- `OLEAUT32!__imp_VariantClear` at `0x18000d0b6`
- `OLEAUT32!__imp_VariantClear` at `0x18000d0f2`
- `OLEAUT32!__imp_VariantClear` at `0x18000d176`
- `OLEAUT32!__imp_VariantClear` at `0x18000d199`

## string_xrefs

- `0x18000cf93`: `DesktopComponent`
- `0x18000d1af`: `CompletionTime`

## pseudocode

```c
__int64 __fastcall ReadProperties(struct OOEBuf *a1)
{
  int v2; // esi
  struct ISubscriptionItem *v3; // rdi
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  int v13; // r8d
  VARIANTARG pvarg; // [rsp+20h] [rbp-39h] BYREF
  struct ISubscriptionItem *v16; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v17[3]; // [rsp+40h] [rbp-19h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v16 = 0;
  if ( (int)SubscriptionItemFromCookie(0, (const struct _GUID *)((char *)a1 + 116), &v16) >= 0 )
  {
    v2 = 1;
    VariantInit(&pvarg);
    v3 = v16;
    if ( (*(_BYTE *)a1 & 0x10) != 0 )
    {
      if ( (int)ReadVariant(v16, L"URL", &pvarg) >= 0 && pvarg.vt == 8 )
        StringCchCopyW((unsigned __int16 *)a1 + 278, 0x824u, pvarg.bstrVal);
      else
        *((_WORD *)a1 + 278) = 0;
      VariantClear(&pvarg);
    }
    if ( (*(_BYTE *)a1 & 0x20) != 0 )
    {
      if ( (int)ReadVariant(v3, L"Name", &pvarg) >= 0 && pvarg.vt == 8 )
        StringCchCopyW((unsigned __int16 *)a1 + 2363, 0x104u, pvarg.bstrVal);
      else
        *((_WORD *)a1 + 2363) = 0;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x100) != 0 )
    {
      if ( (int)ReadVariant(v3, L"Username", &pvarg) >= 0 && pvarg.vt == 8 )
      {
        StringCchCopyW((unsigned __int16 *)a1 + 86, 0x7Fu, pvarg.bstrVal);
      }
      else
      {
        *((_WORD *)a1 + 86) = 0;
        v2 = 0;
      }
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x200) != 0 )
    {
      if ( (int)ReadVariant(v3, L"DesktopComponent", &pvarg) < 0 || pvarg.vt != 3 || (v4 = 1, pvarg.lVal != 1) )
        v4 = 0;
      *((_DWORD *)a1 + 10) = v4;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x4000) != 0 )
    {
      if ( (int)ReadVariant(v3, L"Channel", &pvarg) < 0 || pvarg.vt != 3 || (v5 = 1, pvarg.lVal != 1) )
        v5 = 0;
      *((_DWORD *)a1 + 11) = v5;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x10000) != 0 )
    {
      if ( (int)ReadVariant(v3, L"EnableShortcutGleam", &pvarg) < 0 || pvarg.vt != 3 || (v6 = 1, pvarg.lVal != 1) )
        v6 = 0;
      *((_DWORD *)a1 + 13) = v6;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x20000) != 0 )
    {
      if ( (int)ReadVariant(v3, L"CheckChangesOnly", &pvarg) < 0 || pvarg.vt != 3 || (v7 = 1, pvarg.lVal != 1) )
        v7 = 0;
      *((_DWORD *)a1 + 14) = v7;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x40000) != 0 )
    {
      if ( (int)ReadVariant(v3, L"ChannelFlags", &pvarg) >= 0 && pvarg.vt == 3 )
        *((_DWORD *)a1 + 28) = pvarg.lVal;
      else
        *((_DWORD *)a1 + 28) = 0;
      VariantClear(&pvarg);
    }
    if ( (*(_BYTE *)a1 & 0x40) != 0 )
    {
      if ( (int)ReadVariant(v3, L"EmailNotification", &pvarg) < 0 || pvarg.vt != 3 || (v8 = 1, pvarg.lVal != 1) )
        v8 = 0;
      *((_DWORD *)a1 + 12) = v8;
      VariantClear(&pvarg);
    }
    v9 = *(_DWORD *)a1;
    if ( (*(_DWORD *)a1 & 0x80u) != 0 && v2 )
      *((_WORD *)a1 + 214) = 0;
    if ( (v9 & 0x180) != 0 )
    {
      if ( *((_WORD *)a1 + 214) || (v10 = 0, *((_WORD *)a1 + 86)) )
        v10 = 1;
      *((_DWORD *)a1 + 15) = v10;
    }
    if ( (v9 & 0x2000) != 0 )
    {
      if ( (int)ReadVariant(v3, L"StatusString", &pvarg) >= 0 && pvarg.vt == 8 )
        StringCchCopyW((unsigned __int16 *)a1 + 2624, 0x7Fu, pvarg.bstrVal);
      else
        *((_WORD *)a1 + 2624) = 0;
      VariantClear(&pvarg);
      if ( (int)ReadSCODE(v3, v11, (int *)a1 + 42) < 0 )
        *((_DWORD *)a1 + 42) = 0;
      VariantClear(&pvarg);
    }
    if ( (*(_DWORD *)a1 & 0x1000) != 0 )
    {
      v16 = 0;
      if ( (int)ReadVariant(v3, L"CompletionTime", &pvarg) >= 0 && pvarg.vt == 7 )
      {
        VariantTimeToFileTime(v12, &v16);
        v13 = HIDWORD(v16);
        if ( (__int64)v16 > *(_QWORD *)((char *)a1 + 4) )
        {
          *((_DWORD *)a1 + 1) = (_DWORD)v16;
          *((_DWORD *)a1 + 2) = v13;
        }
      }
    }
    if ( (*(_BYTE *)a1 & 4) != 0 && (int)ReadDWORD(v3, L"RecurseLevels", (unsigned int *)a1 + 7) < 0 )
      *((_DWORD *)a1 + 7) = 0;
    if ( (*(_BYTE *)a1 & 2) != 0 && (int)ReadDWORD(v3, L"RecurseFlags", (unsigned int *)a1 + 8) < 0 )
      *((_DWORD *)a1 + 8) = 0;
    if ( (*(_BYTE *)a1 & 1) != 0 && (int)ReadDWORD(v3, L"MaxSizeKB", (unsigned int *)a1 + 5) < 0 )
      *((_DWORD *)a1 + 5) = 0;
    if ( (*(_BYTE *)a1 & 8) != 0 && (int)ReadDWORD(v3, L"ActualSizeKB", (unsigned int *)a1 + 6) < 0 )
      *((_DWORD *)a1 + 6) = 0;
    memset(v17, 0, 44);
    LODWORD(v17[0]) = 44;
    if ( ((int (__fastcall *)(struct ISubscriptionItem *, _OWORD *))v3->lpVtbl->GetSubscriptionItemInfo)(v3, v17) >= 0 )
      *((_DWORD *)a1 + 37) = DWORD1(v17[0]);
    ((void (__fastcall *)(struct ISubscriptionItem *))v3->lpVtbl->Release)(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce34  push    rbp
0x18000ce36  push    rbx
0x18000ce37  push    rsi
0x18000ce38  push    rdi
0x18000ce39  push    r14
0x18000ce3b  push    r15
0x18000ce3d  lea     rbp, [rsp-2Fh]
0x18000ce42  sub     rsp, 88h
0x18000ce49  mov     rax, cs:__security_cookie
0x18000ce50  xor     rax, rsp
0x18000ce53  mov     [rbp+57h+var_40], rax
0x18000ce57  mov     rbx, rcx
0x18000ce5a  lea     rdx, [rcx+74h]; struct _GUID *
0x18000ce5e  xorps   xmm0, xmm0
0x18000ce61  lea     r8, [rbp+57h+var_78]; struct ISubscriptionItem **
0x18000ce65  xor     eax, eax
0x18000ce67  xor     r14d, r14d
0x18000ce6a  xor     ecx, ecx; int
0x18000ce6c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000ce70  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000ce74  mov     [rbp+57h+var_78], r14
0x18000ce78  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18000ce7d  test    eax, eax
0x18000ce7f  js      loc_18000D2C8
0x18000ce85  lea     r15d, [r14+1]
0x18000ce89  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000ce8d  mov     esi, r15d
0x18000ce90  call    cs:__imp_VariantInit
0x18000ce96  test    byte ptr [rbx], 10h
0x18000ce99  mov     rdi, [rbp+57h+var_78]
0x18000ce9d  jz      short loc_18000CEE6
0x18000ce9f  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000cea3  mov     rcx, rdi; struct ISubscriptionItem *
0x18000cea6  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x18000cead  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000ceb2  test    eax, eax
0x18000ceb4  js      short loc_18000CED4
0x18000ceb6  cmp     word ptr [rbp+57h+pvarg], 8
0x18000cebb  jnz     short loc_18000CED4
0x18000cebd  mov     r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18000cec1  lea     rcx, [rbx+22Ch]; unsigned __int16 *
0x18000cec8  mov     edx, 824h; unsigned __int64
0x18000cecd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ced2  jmp     short loc_18000CEDC
0x18000ced4  mov     [rbx+22Ch], r14w
0x18000cedc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cee0  call    cs:__imp_VariantClear
0x18000cee6  test    byte ptr [rbx], 20h
0x18000cee9  jz      short loc_18000CF32
0x18000ceeb  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000ceef  mov     rcx, rdi; struct ISubscriptionItem *
0x18000cef2  lea     rdx, ?c_szPropName@@3QBGB; "Name"
0x18000cef9  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000cefe  test    eax, eax
0x18000cf00  js      short loc_18000CF20
0x18000cf02  cmp     word ptr [rbp+57h+pvarg], 8
0x18000cf07  jnz     short loc_18000CF20
0x18000cf09  mov     r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18000cf0d  lea     rcx, [rbx+1276h]; unsigned __int16 *
0x18000cf14  mov     edx, 104h; unsigned __int64
0x18000cf19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cf1e  jmp     short loc_18000CF28
0x18000cf20  mov     [rbx+1276h], r14w
0x18000cf28  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cf2c  call    cs:__imp_VariantClear
0x18000cf32  test    dword ptr [rbx], 100h
0x18000cf38  jz      short loc_18000CF84
0x18000cf3a  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000cf3e  mov     rcx, rdi; struct ISubscriptionItem *
0x18000cf41  lea     rdx, ?c_szPropCrawlUsername@@3QBGB; "Username"
0x18000cf48  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000cf4d  test    eax, eax
0x18000cf4f  js      short loc_18000CF6F
0x18000cf51  cmp     word ptr [rbp+57h+pvarg], 8
0x18000cf56  jnz     short loc_18000CF6F
0x18000cf58  mov     r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18000cf5c  lea     rcx, [rbx+0ACh]; unsigned __int16 *
0x18000cf63  mov     edx, 7Fh; unsigned __int64
0x18000cf68  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cf6d  jmp     short loc_18000CF7A
0x18000cf6f  mov     [rbx+0ACh], r14w
0x18000cf77  mov     esi, r14d
0x18000cf7a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cf7e  call    cs:__imp_VariantClear
0x18000cf84  test    dword ptr [rbx], 200h
0x18000cf8a  jz      short loc_18000CFC3
0x18000cf8c  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000cf90  mov     rcx, rdi; struct ISubscriptionItem *
0x18000cf93  lea     rdx, ?c_szPropDesktopComponent@@3QBGB; "DesktopComponent"
0x18000cf9a  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000cf9f  test    eax, eax
0x18000cfa1  js      short loc_18000CFB3
0x18000cfa3  cmp     word ptr [rbp+57h+pvarg], 3
0x18000cfa8  jnz     short loc_18000CFB3
0x18000cfaa  mov     eax, r15d
0x18000cfad  cmp     dword ptr [rbp+57h+pvarg+8], r15d
0x18000cfb1  jz      short loc_18000CFB6
0x18000cfb3  mov     eax, r14d
0x18000cfb6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cfba  mov     [rbx+28h], eax
0x18000cfbd  call    cs:__imp_VariantClear
0x18000cfc3  test    dword ptr [rbx], 4000h
0x18000cfc9  jz      short loc_18000D002
0x18000cfcb  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000cfcf  mov     rcx, rdi; struct ISubscriptionItem *
0x18000cfd2  lea     rdx, ?c_szPropChannel@@3QBGB; "Channel"
0x18000cfd9  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000cfde  test    eax, eax
0x18000cfe0  js      short loc_18000CFF2
0x18000cfe2  cmp     word ptr [rbp+57h+pvarg], 3
0x18000cfe7  jnz     short loc_18000CFF2
0x18000cfe9  mov     eax, r15d
0x18000cfec  cmp     dword ptr [rbp+57h+pvarg+8], r15d
0x18000cff0  jz      short loc_18000CFF5
0x18000cff2  mov     eax, r14d
0x18000cff5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000cff9  mov     [rbx+2Ch], eax
0x18000cffc  call    cs:__imp_VariantClear
0x18000d002  test    dword ptr [rbx], 10000h
0x18000d008  jz      short loc_18000D041
0x18000d00a  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d00e  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d011  lea     rdx, ?c_szPropEnableShortcutGleam@@3QBGB; "EnableShortcutGleam"
0x18000d018  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d01d  test    eax, eax
0x18000d01f  js      short loc_18000D031
0x18000d021  cmp     word ptr [rbp+57h+pvarg], 3
0x18000d026  jnz     short loc_18000D031
0x18000d028  mov     eax, r15d
0x18000d02b  cmp     dword ptr [rbp+57h+pvarg+8], r15d
0x18000d02f  jz      short loc_18000D034
0x18000d031  mov     eax, r14d
0x18000d034  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d038  mov     [rbx+34h], eax
0x18000d03b  call    cs:__imp_VariantClear
0x18000d041  test    dword ptr [rbx], 20000h
0x18000d047  jz      short loc_18000D080
0x18000d049  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d04d  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d050  lea     rdx, ?c_szPropCrawlChangesOnly@@3QBGB; "CheckChangesOnly"
0x18000d057  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d05c  test    eax, eax
0x18000d05e  js      short loc_18000D070
0x18000d060  cmp     word ptr [rbp+57h+pvarg], 3
0x18000d065  jnz     short loc_18000D070
0x18000d067  mov     eax, r15d
0x18000d06a  cmp     dword ptr [rbp+57h+pvarg+8], r15d
0x18000d06e  jz      short loc_18000D073
0x18000d070  mov     eax, r14d
0x18000d073  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d077  mov     [rbx+38h], eax
0x18000d07a  call    cs:__imp_VariantClear
0x18000d080  test    dword ptr [rbx], 40000h
0x18000d086  jz      short loc_18000D0BC
0x18000d088  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d08c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d08f  lea     rdx, ?c_szPropChannelFlags@@3QBGB; "ChannelFlags"
0x18000d096  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d09b  test    eax, eax
0x18000d09d  js      short loc_18000D0AE
0x18000d09f  cmp     word ptr [rbp+57h+pvarg], 3
0x18000d0a4  jnz     short loc_18000D0AE
0x18000d0a6  mov     eax, dword ptr [rbp+57h+pvarg+8]
0x18000d0a9  mov     [rbx+70h], eax
0x18000d0ac  jmp     short loc_18000D0B2
0x18000d0ae  mov     [rbx+70h], r14d
0x18000d0b2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d0b6  call    cs:__imp_VariantClear
0x18000d0bc  test    byte ptr [rbx], 40h
0x18000d0bf  jz      short loc_18000D0F8
0x18000d0c1  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d0c5  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d0c8  lea     rdx, ?c_szPropEmailNotf@@3QBGB; "EmailNotification"
0x18000d0cf  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d0d4  test    eax, eax
0x18000d0d6  js      short loc_18000D0E8
0x18000d0d8  cmp     word ptr [rbp+57h+pvarg], 3
0x18000d0dd  jnz     short loc_18000D0E8
0x18000d0df  mov     eax, r15d
0x18000d0e2  cmp     dword ptr [rbp+57h+pvarg+8], r15d
0x18000d0e6  jz      short loc_18000D0EB
0x18000d0e8  mov     eax, r14d
0x18000d0eb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d0ef  mov     [rbx+30h], eax
0x18000d0f2  call    cs:__imp_VariantClear
0x18000d0f8  mov     ecx, [rbx]
0x18000d0fa  test    cl, cl
0x18000d0fc  jns     short loc_18000D10A
0x18000d0fe  test    esi, esi
0x18000d100  jz      short loc_18000D10A
0x18000d102  mov     [rbx+1ACh], r14w
0x18000d10a  test    ecx, 180h
0x18000d110  jz      short loc_18000D12F
0x18000d112  cmp     [rbx+1ACh], r14w
0x18000d11a  jnz     short loc_18000D129
0x18000d11c  mov     eax, r14d
0x18000d11f  cmp     [rbx+0ACh], r14w
0x18000d127  jz      short loc_18000D12C
0x18000d129  mov     eax, r15d
0x18000d12c  mov     [rbx+3Ch], eax
0x18000d12f  bt      ecx, 0Dh
0x18000d133  jnb     short loc_18000D19F
0x18000d135  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d139  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d13c  lea     rdx, ?c_szPropStatusString@@3QBGB; "StatusString"
0x18000d143  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d148  test    eax, eax
0x18000d14a  js      short loc_18000D16A
0x18000d14c  cmp     word ptr [rbp+57h+pvarg], 8
0x18000d151  jnz     short loc_18000D16A
0x18000d153  mov     r8, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x18000d157  lea     rcx, [rbx+1480h]; unsigned __int16 *
0x18000d15e  mov     edx, 7Fh; unsigned __int64
0x18000d163  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d168  jmp     short loc_18000D172
0x18000d16a  mov     [rbx+1480h], r14w
0x18000d172  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d176  call    cs:__imp_VariantClear
0x18000d17c  lea     rsi, [rbx+0A8h]
0x18000d183  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d186  mov     r8, rsi; int *
0x18000d189  call    ?ReadSCODE@@YAJPEAUISubscriptionItem@@PEBGPEAJ@Z; ReadSCODE(ISubscriptionItem *,ushort const *,long *)
0x18000d18e  test    eax, eax
0x18000d190  jns     short loc_18000D195
0x18000d192  mov     [rsi], r14d
0x18000d195  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000d199  call    cs:__imp_VariantClear
0x18000d19f  test    dword ptr [rbx], 1000h
0x18000d1a5  jz      short loc_18000D203
0x18000d1a7  lea     r8, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000d1ab  mov     [rbp+57h+var_78], r14
0x18000d1af  lea     rdx, ?c_szPropCompletionTime@@3QBGB; "CompletionTime"
0x18000d1b6  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d1b9  call    ?ReadVariant@@YAJPEAUISubscriptionItem@@PEBGPEAUtagVARIANT@@@Z; ReadVariant(ISubscriptionItem *,ushort const *,tagVARIANT *)
0x18000d1be  test    eax, eax
0x18000d1c0  js      short loc_18000D203
0x18000d1c2  cmp     word ptr [rbp+57h+pvarg], 7
0x18000d1c7  jnz     short loc_18000D203
0x18000d1c9  movsd   xmm0, qword ptr [rbp+57h+pvarg+8]
0x18000d1ce  lea     rdx, [rbp+57h+var_78]
0x18000d1d2  call    VariantTimeToFileTime
0x18000d1d7  mov     r8d, dword ptr [rbp+57h+var_78+4]
0x18000d1db  mov     edx, [rbx+8]
0x18000d1de  mov     ecx, r8d
0x18000d1e1  mov     eax, [rbx+4]
0x18000d1e4  mov     r9d, dword ptr [rbp+57h+var_78]
0x18000d1e8  shl     rcx, 20h
0x18000d1ec  shl     rdx, 20h
0x18000d1f0  or      rcx, r9
0x18000d1f3  or      rdx, rax
0x18000d1f6  cmp     rcx, rdx
0x18000d1f9  jle     short loc_18000D203
0x18000d1fb  mov     [rbx+4], r9d
0x18000d1ff  mov     [rbx+8], r8d
0x18000d203  test    byte ptr [rbx], 4
0x18000d206  jz      short loc_18000D223
0x18000d208  lea     r8, [rbx+1Ch]; unsigned int *
0x18000d20c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d20f  lea     rdx, ?c_szPropCrawlLevels@@3QBGB; "RecurseLevels"
0x18000d216  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000d21b  test    eax, eax
0x18000d21d  jns     short loc_18000D223
0x18000d21f  mov     [rbx+1Ch], r14d
0x18000d223  test    byte ptr [rbx], 2
0x18000d226  jz      short loc_18000D243
0x18000d228  lea     r8, [rbx+20h]; unsigned int *
0x18000d22c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d22f  lea     rdx, ?c_szPropCrawlFlags@@3QBGB; "RecurseFlags"
0x18000d236  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000d23b  test    eax, eax
0x18000d23d  jns     short loc_18000D243
0x18000d23f  mov     [rbx+20h], r14d
0x18000d243  test    [rbx], r15b
0x18000d246  jz      short loc_18000D263
0x18000d248  lea     r8, [rbx+14h]; unsigned int *
0x18000d24c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d24f  lea     rdx, ?c_szPropCrawlMaxSize@@3QBGB; "MaxSizeKB"
0x18000d256  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000d25b  test    eax, eax
0x18000d25d  jns     short loc_18000D263
0x18000d25f  mov     [rbx+14h], r14d
0x18000d263  test    byte ptr [rbx], 8
0x18000d266  jz      short loc_18000D283
0x18000d268  lea     r8, [rbx+18h]; unsigned int *
0x18000d26c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000d26f  lea     rdx, ?c_szPropCrawlActualSize@@3QBGB; "ActualSizeKB"
0x18000d276  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000d27b  test    eax, eax
0x18000d27d  jns     short loc_18000D283
0x18000d27f  mov     [rbx+18h], r14d
0x18000d283  xorps   xmm0, xmm0
0x18000d286  lea     rdx, [rbp+57h+var_70]
0x18000d28a  movups  [rbp+57h+var_70], xmm0
0x18000d28e  mov     dword ptr [rbp+57h+var_70], 2Ch ; ','
0x18000d295  mov     rcx, rdi
0x18000d298  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18000d29c  movups  xmmword ptr [rbp+57h+var_60+0Ch], xmm0
0x18000d2a0  mov     rax, [rdi]
0x18000d2a3  mov     rax, [rax+20h]
0x18000d2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
