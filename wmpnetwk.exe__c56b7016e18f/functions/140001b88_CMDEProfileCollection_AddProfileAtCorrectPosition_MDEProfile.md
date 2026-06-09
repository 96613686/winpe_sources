# CMDEProfileCollection::AddProfileAtCorrectPosition(MDEProfile *)

- ea: `0x140001b88`
- end: `0x14000218c`
- name: `?AddProfileAtCorrectPosition@CMDEProfileCollection@@AEAAJPEAUMDEProfile@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(CMDEProfileCollection *__hidden this, struct MDEProfile *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14009a650`

## callees

- `0x1400016c4`
- `0x140001b88`
- `0x140003750`
- `0x1400065e0`
- `0x14002ec54`
- `0x14003f17c`
- `0x14003f1bc`
- `0x14005ea04`
- `0x140065698`
- `0x14009a7d8`
- `0x14009a938`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140001c38`
- `KERNEL32!CompareStringW` at `0x140001c83`
- `KERNEL32!CompareStringW` at `0x140001cb4`
- `KERNEL32!CompareStringW` at `0x140001ce5`
- `KERNEL32!CompareStringW` at `0x140001d30`
- `KERNEL32!CompareStringW` at `0x140001d61`
- `KERNEL32!CompareStringW` at `0x140001d92`
- `KERNEL32!CompareStringW` at `0x140001dc3`
- `KERNEL32!CompareStringW` at `0x140001df4`
- `KERNEL32!CompareStringW` at `0x140001e46`
- `KERNEL32!CompareStringW` at `0x140001e77`
- `KERNEL32!CompareStringW` at `0x140001ea8`
- `KERNEL32!CompareStringW` at `0x140001ed9`
- `KERNEL32!CompareStringW` at `0x140001f0a`
- `KERNEL32!CompareStringW` at `0x140001f3c`
- `KERNEL32!CompareStringW` at `0x140001f98`
- `KERNEL32!CompareStringW` at `0x140001c38`
- `KERNEL32!CompareStringW` at `0x140001c83`
- `KERNEL32!CompareStringW` at `0x140001cb4`
- `KERNEL32!CompareStringW` at `0x140001ce5`
- `KERNEL32!CompareStringW` at `0x140001d30`
- `KERNEL32!CompareStringW` at `0x140001d61`
- `KERNEL32!CompareStringW` at `0x140001d92`
- `KERNEL32!CompareStringW` at `0x140001dc3`
- `KERNEL32!CompareStringW` at `0x140001df4`
- `KERNEL32!CompareStringW` at `0x140001e46`
- `KERNEL32!CompareStringW` at `0x140001e77`
- `KERNEL32!CompareStringW` at `0x140001ea8`
- `KERNEL32!CompareStringW` at `0x140001ed9`
- `KERNEL32!CompareStringW` at `0x140001f0a`
- `KERNEL32!CompareStringW` at `0x140001f3c`
- `KERNEL32!CompareStringW` at `0x140001f98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMDEProfileCollection::AddProfileAtCorrectPosition(
        CMDEProfileCollection *this,
        struct MDEProfile *a2)
{
  PCNZWCH *v4; // r14
  const WCHAR *v5; // rbx
  unsigned int v6; // edi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rax
  _QWORD *i; // rdx
  __int64 v10; // rbp
  PVOID *v11; // rcx
  __int64 v12; // rdx
  PCNZWCH lpString1; // [rsp+80h] [rbp+8h] BYREF
  struct MDEProfile *v15; // [rsp+88h] [rbp+10h] BYREF

  v15 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, a2);
  }
  v4 = (PCNZWCH *)((char *)a2 + 32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
    (char *)a2 + 32,
    &lpString1,
    5);
  v5 = lpString1;
  if ( *((_DWORD *)a2 + 19) )
  {
    v6 = 50;
  }
  else if ( CompareStringW(0x7Fu, 1u, lpString1, 5, L"image", 5) == 2 )
  {
    v6 = 3;
    if ( !*((_DWORD *)a2 + 14) )
    {
      if ( *((_DWORD *)a2 + 5) )
      {
        if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"image/jpeg", -1) == 2 )
        {
          v6 = 1;
        }
        else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"image/x-ycbcr-yuv420", -1) == 2 )
        {
          v6 = 2;
        }
      }
      else
      {
        v6 = 0;
      }
    }
  }
  else if ( CompareStringW(0x7Fu, 1u, v5, 5, L"audio", 5) == 2 )
  {
    v6 = 26;
    if ( *((_DWORD *)a2 + 14) )
    {
      if ( *((_DWORD *)a2 + 14) == 1 )
      {
        if ( *((_DWORD *)a2 + 5) )
        {
          if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=8", -1) == 2 )
          {
            v6 = 21;
          }
          else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=6", -1) == 2 )
          {
            v6 = 22;
          }
          else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=4", -1) == 2 )
          {
            v6 = 23;
          }
          else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=2", -1) == 2 )
          {
            v6 = 24;
          }
          else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=1", -1) == 2 )
          {
            v6 = 25;
          }
        }
        else
        {
          v6 = 20;
        }
      }
    }
    else if ( *((_DWORD *)a2 + 5) )
    {
      if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=8", -1) == 2 )
      {
        v6 = 11;
      }
      else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=6", -1) == 2 )
      {
        v6 = 12;
      }
      else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=4", -1) == 2 )
      {
        v6 = 13;
      }
      else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=2", -1) == 2 )
      {
        v6 = 14;
      }
      else if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"audio/L16;rate=44100;channels=1", -1) == 2 )
      {
        v6 = 15;
      }
    }
    else
    {
      v6 = 10;
    }
  }
  else if ( CompareStringW(0x7Fu, 1u, v5, 5, L"video", 5) == 2 )
  {
    if ( *((_DWORD *)a2 + 14) )
    {
      v6 = 34;
      if ( *((_DWORD *)a2 + 14) == 1 && !*((_DWORD *)a2 + 5) )
        v6 = 32;
    }
    else
    {
      v6 = *((_DWORD *)a2 + 5) != 0 ? 34 : 30;
    }
  }
  else
  {
    v6 = 40;
    if ( CompareStringW(0x7Fu, 1u, *v4, -1, L"application/octet-stream", -1) == 2 && !*((_DWORD *)a2 + 14) )
      v6 = *((_DWORD *)a2 + 5) != 0 ? 0x28 : 0;
  }
  *((_DWORD *)a2 + 47) = v6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( *((_DWORD *)a2 + 14) )
    {
      v7 = L"RTSP";
      if ( *((_DWORD *)a2 + 14) != 1 )
        v7 = L"Unknown";
    }
    else
    {
      v7 = (const wchar_t *)L"HTTP";
    }
    v8 = L"transcoding";
    if ( !*((_DWORD *)a2 + 5) )
      v8 = (const wchar_t *)L"non-transcoding";
    WPP_SF_qSSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v8, (__int64)v7, (__int64)*v4, v6);
  }
  for ( i = *(_QWORD **)this; i; i = (_QWORD *)*i )
  {
    v10 = i[2];
    if ( *(_DWORD *)(v10 + 188) > v6 )
    {
      ATL::CAtlList<MDEProfile *,ATL::CElementTraits<MDEProfile *>>::InsertBefore(this, i, &v15);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qdqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_12d29b41b149367017654092f21a41cc_Traceguids,
          a2,
          v6,
          v10,
          *(_DWORD *)(v10 + 188));
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_69;
    }
  }
  ATL::CAtlList<MDEProfile *,ATL::CElementTraits<MDEProfile *>>::AddTail(this, &v15);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, a2, v6);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_69:
  v12 = *((_QWORD *)a2 + 6);
  if ( *(_DWORD *)(v12 - 16) )
  {
    ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<MDEProfile const *>>::RBInsert(
      (char *)this + 48,
      v12,
      &v15);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    WPP_SF_d(v11[2], 60, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, 0);
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  return 0;
}

```

## disassembly

```asm
0x140001b88  mov     [rsp+arg_10], rbx
0x140001b8d  mov     [rsp+arg_8], rdx
0x140001b92  push    rbp
0x140001b93  push    rsi
0x140001b94  push    rdi
0x140001b95  push    r12
0x140001b97  push    r13
0x140001b99  push    r14
0x140001b9b  push    r15
0x140001b9d  sub     rsp, 40h
0x140001ba1  mov     rsi, rdx
0x140001ba4  mov     r15, rcx
0x140001ba7  lea     rax, WPP_GLOBAL_Control
0x140001bae  mov     ebp, 5
0x140001bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bba  cmp     rcx, rax
0x140001bbd  jz      short loc_140001BE1
0x140001bbf  test    byte ptr [rcx+1Ch], 2
0x140001bc3  jz      short loc_140001BE1
0x140001bc5  cmp     [rcx+19h], bpl
0x140001bc9  jb      short loc_140001BE1
0x140001bcb  lea     edx, [rbp+33h]
0x140001bce  mov     r9, rsi
0x140001bd1  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x140001bd8  mov     rcx, [rcx+10h]
0x140001bdc  call    WPP_SF_q
0x140001be1  lea     r14, [rsi+20h]
0x140001be5  mov     r8d, ebp
0x140001be8  lea     rdx, [rsp+78h+lpString1]
0x140001bf0  mov     rcx, r14
0x140001bf3  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x140001bf8  mov     r13d, 1
0x140001bfe  mov     rbx, [rsp+78h+lpString1]
0x140001c06  xor     r12d, r12d
0x140001c09  cmp     [rsi+4Ch], r12d
0x140001c0d  jz      short loc_140001C18
0x140001c0f  lea     edi, [r13+31h]
0x140001c13  jmp     loc_140001FB2
0x140001c18  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001c1c  lea     rax, String2; "image"
0x140001c23  mov     [rsp+78h+lpString2], rax; lpString2
0x140001c28  mov     r9d, ebp; cchCount1
0x140001c2b  mov     r8, rbx; lpString1
0x140001c2e  mov     edx, r13d; dwCmpFlags
0x140001c31  mov     edi, 7Fh
0x140001c36  mov     ecx, edi; Locale
0x140001c38  call    cs:__imp_CompareStringW
0x140001c3e  cmp     eax, 2
0x140001c41  jnz     loc_140001CCA
0x140001c47  lea     edi, [rax+1]
0x140001c4a  cmp     [rsi+38h], r12d
0x140001c4e  jnz     loc_140001FB2
0x140001c54  cmp     [rsi+14h], r12d
0x140001c58  jnz     short loc_140001C62
0x140001c5a  mov     edi, r12d
0x140001c5d  jmp     loc_140001FB2
0x140001c62  or      ebp, 0FFFFFFFFh
0x140001c65  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001c69  lea     rax, aImageJpeg; "image/jpeg"
0x140001c70  mov     [rsp+78h+lpString2], rax; lpString2
0x140001c75  mov     r9d, ebp; cchCount1
0x140001c78  mov     r8, [r14]; lpString1
0x140001c7b  mov     edx, r13d; dwCmpFlags
0x140001c7e  mov     ecx, 7Fh; Locale
0x140001c83  call    cs:__imp_CompareStringW
0x140001c89  cmp     eax, 2
0x140001c8c  jnz     short loc_140001C96
0x140001c8e  mov     edi, r13d
0x140001c91  jmp     loc_140001FB2
0x140001c96  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001c9a  lea     rax, aImageXYcbcrYuv; "image/x-ycbcr-yuv420"
0x140001ca1  mov     [rsp+78h+lpString2], rax; lpString2
0x140001ca6  mov     r9d, ebp; cchCount1
0x140001ca9  mov     r8, [r14]; lpString1
0x140001cac  mov     edx, r13d; dwCmpFlags
0x140001caf  mov     ecx, 7Fh; Locale
0x140001cb4  call    cs:__imp_CompareStringW
0x140001cba  cmp     eax, 2
0x140001cbd  jnz     loc_140001FB2
0x140001cc3  mov     edi, eax
0x140001cc5  jmp     loc_140001FB2
0x140001cca  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001cce  lea     rax, aAudio_1; "audio"
0x140001cd5  mov     [rsp+78h+lpString2], rax; lpString2
0x140001cda  mov     r9d, ebp; cchCount1
0x140001cdd  mov     r8, rbx; lpString1
0x140001ce0  mov     edx, r13d; dwCmpFlags
0x140001ce3  mov     ecx, edi; Locale
0x140001ce5  call    cs:__imp_CompareStringW
0x140001ceb  cmp     eax, 2
0x140001cee  jnz     loc_140001F21
0x140001cf4  lea     edi, [rax+18h]
0x140001cf7  cmp     [rsi+38h], r12d
0x140001cfb  jnz     loc_140001E0B
0x140001d01  cmp     [rsi+14h], r12d
0x140001d05  jnz     short loc_140001D0F
0x140001d07  lea     edi, [rax+8]
0x140001d0a  jmp     loc_140001FB2
0x140001d0f  or      ebp, 0FFFFFFFFh
0x140001d12  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001d16  lea     rax, aAudioL16Rate44_1; "audio/L16;rate=44100;channels=8"
0x140001d1d  mov     [rsp+78h+lpString2], rax; lpString2
0x140001d22  mov     r9d, ebp; cchCount1
0x140001d25  mov     r8, [r14]; lpString1
0x140001d28  mov     edx, r13d; dwCmpFlags
0x140001d2b  mov     ecx, 7Fh; Locale
0x140001d30  call    cs:__imp_CompareStringW
0x140001d36  cmp     eax, 2
0x140001d39  jnz     short loc_140001D43
0x140001d3b  lea     edi, [rbp+0Ch]
0x140001d3e  jmp     loc_140001FB2
0x140001d43  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001d47  lea     rax, aAudioL16Rate44_3; "audio/L16;rate=44100;channels=6"
0x140001d4e  mov     [rsp+78h+lpString2], rax; lpString2
0x140001d53  mov     r9d, ebp; cchCount1
0x140001d56  mov     r8, [r14]; lpString1
0x140001d59  mov     edx, r13d; dwCmpFlags
0x140001d5c  mov     ecx, 7Fh; Locale
0x140001d61  call    cs:__imp_CompareStringW
0x140001d67  cmp     eax, 2
0x140001d6a  jnz     short loc_140001D74
0x140001d6c  lea     edi, [rax+0Ah]
0x140001d6f  jmp     loc_140001FB2
0x140001d74  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001d78  lea     rax, aAudioL16Rate44_4; "audio/L16;rate=44100;channels=4"
0x140001d7f  mov     [rsp+78h+lpString2], rax; lpString2
0x140001d84  mov     r9d, ebp; cchCount1
0x140001d87  mov     r8, [r14]; lpString1
0x140001d8a  mov     edx, r13d; dwCmpFlags
0x140001d8d  mov     ecx, 7Fh; Locale
0x140001d92  call    cs:__imp_CompareStringW
0x140001d98  cmp     eax, 2
0x140001d9b  jnz     short loc_140001DA5
0x140001d9d  lea     edi, [rax+0Bh]
0x140001da0  jmp     loc_140001FB2
0x140001da5  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001da9  lea     rax, aAudioL16Rate44; "audio/L16;rate=44100;channels=2"
0x140001db0  mov     [rsp+78h+lpString2], rax; lpString2
0x140001db5  mov     r9d, ebp; cchCount1
0x140001db8  mov     r8, [r14]; lpString1
0x140001dbb  mov     edx, r13d; dwCmpFlags
0x140001dbe  mov     ecx, 7Fh; Locale
0x140001dc3  call    cs:__imp_CompareStringW
0x140001dc9  cmp     eax, 2
0x140001dcc  jnz     short loc_140001DD6
0x140001dce  lea     edi, [rax+0Ch]
0x140001dd1  jmp     loc_140001FB2
0x140001dd6  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001dda  lea     rax, aAudioL16Rate44_0; "audio/L16;rate=44100;channels=1"
0x140001de1  mov     [rsp+78h+lpString2], rax; lpString2
0x140001de6  mov     r9d, ebp; cchCount1
0x140001de9  mov     r8, [r14]; lpString1
0x140001dec  mov     edx, r13d; dwCmpFlags
0x140001def  mov     ecx, 7Fh; Locale
0x140001df4  call    cs:__imp_CompareStringW
0x140001dfa  cmp     eax, 2
0x140001dfd  jnz     loc_140001FB2
0x140001e03  lea     edi, [rax+0Dh]
0x140001e06  jmp     loc_140001FB2
0x140001e0b  cmp     [rsi+38h], r13d
0x140001e0f  jnz     loc_140001FB2
0x140001e15  cmp     [rsi+14h], r12d
0x140001e19  jnz     short loc_140001E25
0x140001e1b  mov     edi, 14h
0x140001e20  jmp     loc_140001FB2
0x140001e25  or      ebp, 0FFFFFFFFh
0x140001e28  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001e2c  lea     rax, aAudioL16Rate44_1; "audio/L16;rate=44100;channels=8"
0x140001e33  mov     [rsp+78h+lpString2], rax; lpString2
0x140001e38  mov     r9d, ebp; cchCount1
0x140001e3b  mov     r8, [r14]; lpString1
0x140001e3e  mov     edx, r13d; dwCmpFlags
0x140001e41  mov     ecx, 7Fh; Locale
0x140001e46  call    cs:__imp_CompareStringW
0x140001e4c  cmp     eax, 2
0x140001e4f  jnz     short loc_140001E59
0x140001e51  lea     edi, [rbp+16h]
0x140001e54  jmp     loc_140001FB2
0x140001e59  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001e5d  lea     rax, aAudioL16Rate44_3; "audio/L16;rate=44100;channels=6"
0x140001e64  mov     [rsp+78h+lpString2], rax; lpString2
0x140001e69  mov     r9d, ebp; cchCount1
0x140001e6c  mov     r8, [r14]; lpString1
0x140001e6f  mov     edx, r13d; dwCmpFlags
0x140001e72  mov     ecx, 7Fh; Locale
0x140001e77  call    cs:__imp_CompareStringW
0x140001e7d  cmp     eax, 2
0x140001e80  jnz     short loc_140001E8A
0x140001e82  lea     edi, [rax+14h]
0x140001e85  jmp     loc_140001FB2
0x140001e8a  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001e8e  lea     rax, aAudioL16Rate44_4; "audio/L16;rate=44100;channels=4"
0x140001e95  mov     [rsp+78h+lpString2], rax; lpString2
0x140001e9a  mov     r9d, ebp; cchCount1
0x140001e9d  mov     r8, [r14]; lpString1
0x140001ea0  mov     edx, r13d; dwCmpFlags
0x140001ea3  mov     ecx, 7Fh; Locale
0x140001ea8  call    cs:__imp_CompareStringW
0x140001eae  cmp     eax, 2
0x140001eb1  jnz     short loc_140001EBB
0x140001eb3  lea     edi, [rax+15h]
0x140001eb6  jmp     loc_140001FB2
0x140001ebb  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001ebf  lea     rax, aAudioL16Rate44; "audio/L16;rate=44100;channels=2"
0x140001ec6  mov     [rsp+78h+lpString2], rax; lpString2
0x140001ecb  mov     r9d, ebp; cchCount1
0x140001ece  mov     r8, [r14]; lpString1
0x140001ed1  mov     edx, r13d; dwCmpFlags
0x140001ed4  mov     ecx, 7Fh; Locale
0x140001ed9  call    cs:__imp_CompareStringW
0x140001edf  cmp     eax, 2
0x140001ee2  jnz     short loc_140001EEC
0x140001ee4  lea     edi, [rax+16h]
0x140001ee7  jmp     loc_140001FB2
0x140001eec  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001ef0  lea     rax, aAudioL16Rate44_0; "audio/L16;rate=44100;channels=1"
0x140001ef7  mov     [rsp+78h+lpString2], rax; lpString2
0x140001efc  mov     r9d, ebp; cchCount1
0x140001eff  mov     r8, [r14]; lpString1
0x140001f02  mov     edx, r13d; dwCmpFlags
0x140001f05  mov     ecx, 7Fh; Locale
0x140001f0a  call    cs:__imp_CompareStringW
0x140001f10  cmp     eax, 2
0x140001f13  jnz     loc_140001FB2
0x140001f19  lea     edi, [rax+17h]
0x140001f1c  jmp     loc_140001FB2
0x140001f21  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001f25  lea     rax, aVideo_0; "video"
0x140001f2c  mov     [rsp+78h+lpString2], rax; lpString2
0x140001f31  mov     r9d, ebp; cchCount1
0x140001f34  mov     r8, rbx; lpString1
0x140001f37  mov     edx, r13d; dwCmpFlags
0x140001f3a  mov     ecx, edi; Locale
0x140001f3c  call    cs:__imp_CompareStringW
0x140001f42  cmp     eax, 2
0x140001f45  jnz     short loc_140001F74
0x140001f47  cmp     [rsi+38h], r12d
0x140001f4b  jnz     short loc_140001F5C
0x140001f4d  mov     eax, [rsi+14h]
0x140001f50  neg     eax
0x140001f52  sbb     edi, edi
0x140001f54  and     edi, 4
0x140001f57  add     edi, 1Eh
0x140001f5a  jmp     short loc_140001FB2
0x140001f5c  mov     edi, 22h ; '"'
0x140001f61  cmp     [rsi+38h], r13d
0x140001f65  jnz     short loc_140001FB2
0x140001f67  cmp     [rsi+14h], r12d
0x140001f6b  jnz     short loc_140001FB2
0x140001f6d  mov     edi, 20h ; ' '
0x140001f72  jmp     short loc_140001FB2
0x140001f74  mov     edi, 28h ; '('
0x140001f79  or      ebp, 0FFFFFFFFh
0x140001f7c  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x140001f80  lea     rax, aApplicationOct; "application/octet-stream"
0x140001f87  mov     [rsp+78h+lpString2], rax; lpString2
0x140001f8c  mov     r9d, ebp; cchCount1
0x140001f8f  mov     r8, [r14]; lpString1
0x140001f92  mov     edx, r13d; dwCmpFlags
0x140001f95  lea     ecx, [rdi+57h]; Locale
0x140001f98  call    cs:__imp_CompareStringW
0x140001f9e  cmp     eax, 2
0x140001fa1  jnz     short loc_140001FB2
0x140001fa3  cmp     [rsi+38h], r12d
0x140001fa7  jnz     short loc_140001FB2
0x140001fa9  mov     eax, [rsi+14h]
0x140001fac  neg     eax
0x140001fae  sbb     ecx, ecx
0x140001fb0  and     edi, ecx
0x140001fb2  mov     [rsi+0BCh], edi
0x140001fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fbf  lea     rbp, WPP_GLOBAL_Control
0x140001fc6  cmp     rcx, rbp
0x140001fc9  jz      short loc_140002034
0x140001fcb  test    byte ptr [rcx+1Ch], 20h
0x140001fcf  jz      short loc_140002034
0x140001fd1  cmp     byte ptr [rcx+19h], 4
0x140001fd5  jb      short loc_140002034
0x140001fd7  mov     r8, [r14]
0x140001fda  cmp     [rsi+38h], r12d
0x140001fde  jnz     short loc_140001FE9
0x140001fe0  lea     rdx, aHttp; "HTTP"
0x140001fe7  jmp     short loc_140001FFF
0x140001fe9  lea     rdx, aRtsp_0; "RTSP"
0x140001ff0  lea     rax, aUnknown; "Unknown"
0x140001ff7  cmp     [rsi+38h], r13d
0x140001ffb  cmovnz  rdx, rax
0x140001fff  lea     r9, aNonTranscoding; "non-transcoding"
0x140002006  lea     rax, aTranscoding; "transcoding"
0x14000200d  cmp     [rsi+14h], r12d
0x140002011  cmovz   rax, r9
0x140002015  mov     dword ptr [rsp+78h+var_40], edi; char
0x140002019  mov     [rsp+78h+var_48], r8; __int64
0x14000201e  mov     qword ptr [rsp+78h+cchCount2], rdx; __int64
0x140002023  mov     [rsp+78h+lpString2], rax; __int64
0x140002028  mov     r9, rsi
0x14000202b  mov     rcx, [rcx+10h]; LoggerHandle
0x14000202f  call    WPP_SF_qSSSD
0x140002034  mov     rdx, [r15]
0x140002037  test    rdx, rdx
  ... truncated ...
```
