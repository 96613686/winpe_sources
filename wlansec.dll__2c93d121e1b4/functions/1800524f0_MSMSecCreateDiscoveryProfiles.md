# MSMSecCreateDiscoveryProfiles

- ea: `0x1800524f0`
- end: `0x180052af4`
- name: `MSMSecCreateDiscoveryProfiles`
- size: `1540`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000e020`
- `0x18000e140`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x1800163e0`
- `0x1800169c0`
- `0x18001fa98`
- `0x18001fad8`
- `0x180038dd0`
- `0x180043a30`
- `0x180044554`
- `0x1800511c4`
- `0x1800524f0`
- `0x18005ca3c`
- `0x18005ed48`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180052a57`
- `MobileNetworking!ReleaseWriteLock` at `0x180052a57`

## string_xrefs

- `0x1800525c7`: `MSMSecCreateDiscoveryProfiles`
- `0x180052a4d`: `MSMSecCreateDiscoveryProfiles`
- `0x180052a7b`: `MSMSecCreateDiscoveryProfiles`
- `0x180052a8f`: `MSMSecCreateDiscoveryProfiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MSMSecCreateDiscoveryProfiles(
        int a1,
        void *a2,
        unsigned int *a3,
        __int64 a4,
        struct _DOT11_BSS_LIST *a5,
        _QWORD *a6,
        _DWORD *a7,
        int a8,
        int a9)
{
  _DWORD *v10; // r12
  unsigned int *v11; // rsi
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // ecx
  unsigned int DiscoveryProfiles; // eax
  unsigned int MSMSecMemory; // eax
  __int64 v20; // rax
  _DWORD *v21; // r15
  __int64 v22; // r12
  wil *v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rax
  wil *v27; // rcx
  wil *v28; // rcx
  unsigned int v30; // [rsp+50h] [rbp-D8h]
  struct MSMSEC_INTF_CONTEXT *v31; // [rsp+58h] [rbp-D0h] BYREF
  int v32; // [rsp+60h] [rbp-C8h] BYREF
  int v33; // [rsp+64h] [rbp-C4h]
  wil *v34; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-B8h]
  __int64 v36; // [rsp+78h] [rbp-B0h]
  _DWORD *v37; // [rsp+80h] [rbp-A8h]
  __int64 v38; // [rsp+88h] [rbp-A0h]
  struct _DOT11_BSS_LIST *v39; // [rsp+90h] [rbp-98h]
  __int64 v40; // [rsp+98h] [rbp-90h]
  void *v41; // [rsp+A0h] [rbp-88h]
  struct MSMSEC_NW_DESC *v42; // [rsp+A8h] [rbp-80h]
  __int64 v43; // [rsp+B0h] [rbp-78h]
  _QWORD *v44; // [rsp+B8h] [rbp-70h]
  _QWORD *v45; // [rsp+C0h] [rbp-68h]
  _OWORD v46[2]; // [rsp+C8h] [rbp-60h] BYREF
  char v47; // [rsp+E8h] [rbp-40h]

  v40 = a4;
  v42 = (struct MSMSEC_NW_DESC *)a3;
  v41 = a2;
  v39 = a5;
  v44 = a6;
  v45 = a6;
  v10 = a7;
  v43 = (__int64)a7;
  v38 = (__int64)a7;
  v11 = 0;
  v31 = 0;
  v33 = 0;
  v32 = 327679;
  v37 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 157, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v12 = IncThreadCountAndCheckInitializedEx("MSMSecCreateDiscoveryProfiles", 1478);
  v13 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 158, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v12);
    goto LABEL_61;
  }
  if ( !v41
    || !a3
    || !(unsigned int)IsNwDescValid(a3)
    || !v40
    || !v39
    || !(unsigned int)IsBSSListValid(v39)
    || !a6
    || *a6
    || !a7 )
  {
    v13 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 159, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
LABEL_61:
    if ( !a7 )
      goto LABEL_64;
    goto LABEL_62;
  }
  v14 = SecMgrValidateRefAndLockAdapter((void ***)v41, &v31);
  v13 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 160, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v14);
    v11 = (unsigned int *)v31;
  }
  else
  {
    v33 = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
    {
      v11 = (unsigned int *)v31;
    }
    else
    {
      v11 = (unsigned int *)v31;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        161,
        &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
        *((unsigned int *)v31 + 624));
    }
    memset(v46, 0, sizeof(v46));
    v47 = 0;
    memcpy_0(v46, a3 + 1, *a3);
    if ( (byte_1800AED45 & 1) != 0 )
      McTemplateU0qjsqt_EventWriteTransfer(v16, v15, v11[624], (_DWORD)v11 + 32, (__int64)v46, a3[9], a1 == 0);
    std::vector<DOT11_AUTH_CIPHER_PAIR>::vector<DOT11_AUTH_CIPHER_PAIR>(&v34);
    LOBYTE(v17) = a1 != 0;
    DiscoveryProfiles = CreateDiscoveryProfiles(
                          v17,
                          (_DWORD)v11,
                          (_DWORD)a3,
                          v40,
                          (__int64)v39,
                          (__int64)&v34,
                          (__int64)&v32,
                          a8 != 0,
                          a9 != 0);
    v13 = DiscoveryProfiles;
    if ( DiscoveryProfiles )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          162,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          DiscoveryProfiles);
      if ( v34 )
      {
        std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&void msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>(
          v34,
          v35);
        std::_Deallocate<16>(v34, (v36 - (_QWORD)v34) & 0xFFFFFFFFFFFFFFF8uLL);
      }
    }
    else
    {
      MSMSecMemory = AllocateMSMSecMemory(8 * (unsigned int)((v35 - (__int64)v34) >> 3) + 8);
      v13 = MSMSecMemory;
      if ( MSMSecMemory )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            163,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            MSMSecMemory);
        if ( v34 )
        {
          std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&void msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>(
            v34,
            v35);
          std::_Deallocate<16>(v34, (v36 - (_QWORD)v34) & 0xFFFFFFFFFFFFFFF8uLL);
        }
      }
      else
      {
        v20 = (v35 - (__int64)v34) >> 3;
        v21 = v37;
        *v37 = v20;
        v22 = 0;
        try
        {
          while ( 1 )
          {
            v23 = v34;
            if ( (unsigned int)v22 >= (unsigned __int64)((v35 - (__int64)v34) >> 3) )
              break;
            v24 = *((_QWORD *)v34 + v22);
            *((_QWORD *)v34 + v22) = 0;
            *(_QWORD *)&v21[2 * v22 + 2] = v24;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                164,
                &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
                (unsigned int)v22);
            MSMSecLogProfile(*(struct DOT11_MSMSEC_CONNECTION_PROFILE **)&v21[2 * v22 + 2], v42);
            v22 = (unsigned int)(v22 + 1);
          }
          if ( v34 )
          {
            ((void (*)(void))std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&void msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>)();
            std::_Deallocate<16>(v34, (v36 - (_QWORD)v34) & 0xFFFFFFFFFFFFFFF8uLL);
          }
          v10 = (_DWORD *)v43;
          v25 = v44;
        }
        catch ( ... )
        {
          if ( (int)wil::ResultFromCaughtException(v23) < 0 )
          {
            if ( (wil::ResultFromCaughtException(v27) & 0x1FFF0000) == 0x70000 )
              v30 = (unsigned __int16)wil::ResultFromCaughtException(v28);
            else
              v30 = wil::ResultFromCaughtException(v28);
          }
          else
          {
            v30 = 0;
          }
          v13 = v30;
          if ( v30 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 165, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v30);
            v11 = (unsigned int *)v31;
            v10 = (_DWORD *)v38;
            goto LABEL_62;
          }
          v11 = (unsigned int *)v31;
          v21 = v37;
          v25 = v45;
          v10 = (_DWORD *)v38;
        }
        *v25 = v21;
      }
    }
  }
LABEL_62:
  *v10 = v32;
  if ( v33 )
  {
    TraceAdapterId(v11[624], "<<< Unlocking <<<");
    ReleaseWriteLock(v11, v11 + 628, "MSMSecCreateDiscoveryProfiles", 1543);
    TraceAdapterId(v11[624], "<<< Derefing <<<");
    SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v11, "MSMSecCreateDiscoveryProfiles", 1543);
  }
LABEL_64:
  DecThreadCountEx("MSMSecCreateDiscoveryProfiles", 1545);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x1800524f0  mov     [rsp+arg_0], rsi
0x1800524f5  push    rdi
0x1800524f6  push    r12
0x1800524f8  push    r13
0x1800524fa  push    r14
0x1800524fc  push    r15
0x1800524fe  sub     rsp, 100h
0x180052505  mov     rax, cs:__security_cookie
0x18005250c  xor     rax, rsp
0x18005250f  mov     [rsp+128h+var_38], rax
0x180052517  mov     [rsp+128h+var_90], r9
0x18005251f  mov     r15, r8
0x180052522  mov     [rsp+128h+var_80], r8
0x18005252a  mov     [rsp+128h+var_88], rdx
0x180052532  mov     [rsp+128h+var_D8], ecx
0x180052536  mov     rax, [rsp+128h+arg_20]
0x18005253e  mov     [rsp+128h+var_98], rax
0x180052546  mov     r13, [rsp+128h+arg_28]
0x18005254e  mov     [rsp+128h+var_70], r13
0x180052556  mov     [rsp+128h+var_68], r13
0x18005255e  mov     r12, [rsp+128h+arg_30]
0x180052566  mov     [rsp+128h+var_78], r12
0x18005256e  mov     [rsp+128h+var_A0], r12
0x180052576  xor     esi, esi
0x180052578  mov     [rsp+128h+var_D0], rsi
0x18005257d  mov     [rsp+128h+var_C4], esi
0x180052581  mov     [rsp+128h+var_C8], 4FFFFh
0x180052589  mov     [rsp+128h+var_A8], rsi
0x180052591  lea     r14, WPP_GLOBAL_Control
0x180052598  mov     rcx, cs:WPP_GLOBAL_Control
0x18005259f  cmp     rcx, r14
0x1800525a2  jz      short loc_1800525C2
0x1800525a4  test    dword ptr [rcx+44h], 100h
0x1800525ab  jz      short loc_1800525C2
0x1800525ad  mov     edx, 9Dh
0x1800525b2  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800525b9  mov     rcx, [rcx+38h]
0x1800525bd  call    WPP_SF_
0x1800525c2  mov     edx, 5C6h; int
0x1800525c7  lea     rcx, aMsmseccreatedi_0; "MSMSecCreateDiscoveryProfiles"
0x1800525ce  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x1800525d3  mov     edi, eax
0x1800525d5  test    eax, eax
0x1800525d7  jz      short loc_180052610
0x1800525d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525e0  cmp     rcx, r14
0x1800525e3  jz      loc_180052A1A
0x1800525e9  test    byte ptr [rcx+44h], 1
0x1800525ed  jz      loc_180052A1A
0x1800525f3  mov     edx, 9Eh
0x1800525f8  mov     r9d, eax
0x1800525fb  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052602  mov     rcx, [rcx+38h]
0x180052606  call    WPP_SF_d
0x18005260b  jmp     loc_180052A1A
0x180052610  mov     rdi, [rsp+128h+var_88]
0x180052618  test    rdi, rdi
0x18005261b  jz      loc_1800529F0
0x180052621  test    r15, r15
0x180052624  jz      loc_1800529F0
0x18005262a  mov     rcx, r15
0x18005262d  call    IsNwDescValid
0x180052632  test    eax, eax
0x180052634  jz      loc_1800529F0
0x18005263a  cmp     [rsp+128h+var_90], rsi
0x180052642  jz      loc_1800529F0
0x180052648  mov     rax, [rsp+128h+var_98]
0x180052650  test    rax, rax
0x180052653  jz      loc_1800529F0
0x180052659  mov     rcx, rax; struct _DOT11_BSS_LIST *
0x18005265c  call    ?IsBSSListValid@@YAHPEAU_DOT11_BSS_LIST@@@Z; IsBSSListValid(_DOT11_BSS_LIST *)
0x180052661  test    eax, eax
0x180052663  jz      loc_1800529F0
0x180052669  test    r13, r13
0x18005266c  jz      loc_1800529F0
0x180052672  cmp     [r13+0], rsi
0x180052676  jnz     loc_1800529F0
0x18005267c  test    r12, r12
0x18005267f  jz      loc_1800529F0
0x180052685  lea     rdx, [rsp+128h+var_D0]; struct MSMSEC_INTF_CONTEXT **
0x18005268a  mov     rcx, rdi; void *
0x18005268d  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180052692  mov     edi, eax
0x180052694  test    eax, eax
0x180052696  jz      short loc_1800526CC
0x180052698  mov     rcx, cs:WPP_GLOBAL_Control
0x18005269f  cmp     rcx, r14
0x1800526a2  jz      short loc_1800526C2
0x1800526a4  test    byte ptr [rcx+44h], 1
0x1800526a8  jz      short loc_1800526C2
0x1800526aa  mov     edx, 0A0h
0x1800526af  mov     r9d, eax
0x1800526b2  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800526b9  mov     rcx, [rcx+38h]
0x1800526bd  call    WPP_SF_d
0x1800526c2  mov     rsi, [rsp+128h+var_D0]
0x1800526c7  jmp     loc_180052A1F
0x1800526cc  mov     [rsp+128h+var_C4], 1
0x1800526d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526db  cmp     rcx, r14
0x1800526de  jz      short loc_180052709
0x1800526e0  test    byte ptr [rcx+44h], 20h
0x1800526e4  jz      short loc_180052709
0x1800526e6  mov     edx, 0A1h
0x1800526eb  mov     rsi, [rsp+128h+var_D0]
0x1800526f0  mov     r9d, [rsi+9C0h]
0x1800526f7  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800526fe  mov     rcx, [rcx+38h]
0x180052702  call    WPP_SF_d
0x180052707  jmp     short loc_18005270E
0x180052709  mov     rsi, [rsp+128h+var_D0]
0x18005270e  xorps   xmm0, xmm0
0x180052711  xor     eax, eax
0x180052713  movups  [rsp+128h+var_60], xmm0
0x18005271b  movups  [rsp+128h+var_50], xmm0
0x180052723  mov     [rsp+128h+var_40], al
0x18005272a  mov     r8d, [r15]; Size
0x18005272d  lea     rdx, [r15+4]; Src
0x180052731  lea     rcx, [rsp+128h+var_60]; void *
0x180052739  call    memcpy_0
0x18005273e  mov     edi, [rsp+128h+var_D8]
0x180052742  test    cs:byte_1800AED45, 1
0x180052749  jz      short loc_18005277C
0x18005274b  xor     eax, eax
0x18005274d  test    edi, edi
0x18005274f  setz    al
0x180052752  lea     r9, [rsi+20h]
0x180052756  mov     dword ptr [rsp+128h+var_F8], eax
0x18005275a  mov     eax, [r15+24h]
0x18005275e  mov     dword ptr [rsp+128h+var_100], eax
0x180052762  lea     rax, [rsp+128h+var_60]
0x18005276a  mov     [rsp+128h+var_108], rax
0x18005276f  mov     r8d, [rsi+9C0h]
0x180052776  call    McTemplateU0qjsqt_EventWriteTransfer
0x18005277b  nop
0x18005277c  lea     rcx, [rsp+128h+var_C0]
0x180052781  call    ??0?$vector@UDOT11_AUTH_CIPHER_PAIR@@V?$allocator@UDOT11_AUTH_CIPHER_PAIR@@@std@@@std@@QEAA@XZ; std::vector<DOT11_AUTH_CIPHER_PAIR>::vector<DOT11_AUTH_CIPHER_PAIR>(void)
0x180052786  nop
0x180052787  cmp     [rsp+128h+arg_40], 0
0x18005278f  setnz   dl
0x180052792  cmp     [rsp+128h+arg_38], 0
0x18005279a  setnz   al
0x18005279d  test    edi, edi
0x18005279f  setnz   cl
0x1800527a2  mov     [rsp+128h+var_E8], dl
0x1800527a6  mov     [rsp+128h+var_F0], al
0x1800527aa  lea     rax, [rsp+128h+var_C8]
0x1800527af  mov     [rsp+128h+var_F8], rax
0x1800527b4  lea     rax, [rsp+128h+var_C0]
0x1800527b9  mov     [rsp+128h+var_100], rax
0x1800527be  mov     rax, [rsp+128h+var_98]
0x1800527c6  mov     [rsp+128h+var_108], rax
0x1800527cb  mov     r9, [rsp+128h+var_90]
0x1800527d3  mov     r8, r15
0x1800527d6  mov     rdx, rsi
0x1800527d9  call    ?CreateDiscoveryProfiles@@YAK_NAEBUMSMSEC_INTF_CONTEXT@@AEAUMSMSEC_NW_DESC@@AEAUMSMSEC_HOST_DESC@@AEAU_DOT11_BSS_LIST@@AEAV?$vector@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@V?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@2@@std@@PEAK00@Z; CreateDiscoveryProfiles(bool,MSMSEC_INTF_CONTEXT const &,MSMSEC_NW_DESC &,MSMSEC_HOST_DESC &,_DOT11_BSS_LIST &,std::vector<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>> &,ulong *,bool,bool)
0x1800527de  mov     edi, eax
0x1800527e0  test    eax, eax
0x1800527e2  jz      short loc_18005283F
0x1800527e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800527eb  cmp     rcx, r14
0x1800527ee  jz      short loc_18005280F
0x1800527f0  test    byte ptr [rcx+44h], 1
0x1800527f4  jz      short loc_18005280F
0x1800527f6  mov     edx, 0A2h
0x1800527fb  mov     r9d, eax
0x1800527fe  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052805  mov     rcx, [rcx+38h]
0x180052809  call    WPP_SF_d
0x18005280e  nop
0x18005280f  mov     rcx, [rsp+128h+var_C0]
0x180052814  test    rcx, rcx
0x180052817  jz      short loc_18005283A
0x180052819  mov     rdx, [rsp+128h+var_B8]
0x18005281e  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>(std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> *,std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> * const,std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>> &)
0x180052823  mov     rcx, [rsp+128h+var_C0]
0x180052828  mov     rdx, [rsp+128h+var_B0]
0x18005282d  sub     rdx, rcx
0x180052830  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052834  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052839  nop
0x18005283a  jmp     loc_180052A1F
0x18005283f  mov     rcx, [rsp+128h+var_B8]
0x180052844  sub     rcx, [rsp+128h+var_C0]
0x180052849  sar     rcx, 3
0x18005284d  lea     ecx, ds:8[rcx*8]; dwBytes
0x180052854  lea     rdx, [rsp+128h+var_A8]
0x18005285c  call    AllocateMSMSecMemory
0x180052861  mov     edi, eax
0x180052863  test    eax, eax
0x180052865  jz      short loc_1800528C2
0x180052867  mov     rcx, cs:WPP_GLOBAL_Control
0x18005286e  cmp     rcx, r14
0x180052871  jz      short loc_180052892
0x180052873  test    byte ptr [rcx+44h], 1
0x180052877  jz      short loc_180052892
0x180052879  mov     edx, 0A3h
0x18005287e  mov     r9d, eax
0x180052881  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052888  mov     rcx, [rcx+38h]
0x18005288c  call    WPP_SF_d
0x180052891  nop
0x180052892  mov     rcx, [rsp+128h+var_C0]
0x180052897  test    rcx, rcx
0x18005289a  jz      short loc_1800528BD
0x18005289c  mov     rdx, [rsp+128h+var_B8]
0x1800528a1  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>(std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> *,std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> * const,std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>> &)
0x1800528a6  mov     rcx, [rsp+128h+var_C0]
0x1800528ab  mov     rdx, [rsp+128h+var_B0]
0x1800528b0  sub     rdx, rcx
0x1800528b3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800528b7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800528bc  nop
0x1800528bd  jmp     loc_180052A1F
0x1800528c2  mov     rax, [rsp+128h+var_B8]
0x1800528c7  sub     rax, [rsp+128h+var_C0]
0x1800528cc  sar     rax, 3
0x1800528d0  mov     r15, [rsp+128h+var_A8]
0x1800528d8  mov     [r15], eax
0x1800528db  xor     r12d, r12d
0x1800528de  mov     r13d, r12d
0x1800528e1  mov     rdx, [rsp+128h+var_B8]
0x1800528e6  mov     rax, rdx
0x1800528e9  mov     rcx, [rsp+128h+var_C0]
0x1800528ee  sub     rax, rcx
0x1800528f1  sar     rax, 3
0x1800528f5  cmp     r13, rax
0x1800528f8  jnb     short loc_18005294C
0x1800528fa  mov     rax, [rcx+r12*8]
0x1800528fe  mov     qword ptr [rcx+r12*8], 0
0x180052906  mov     [r15+r12*8+8], rax
0x18005290b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052912  cmp     rcx, r14
0x180052915  jz      short loc_180052935
0x180052917  test    byte ptr [rcx+44h], 2
0x18005291b  jz      short loc_180052935
0x18005291d  mov     edx, 0A4h
0x180052922  mov     r9d, r12d
0x180052925  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x18005292c  mov     rcx, [rcx+38h]
0x180052930  call    WPP_SF_d
0x180052935  mov     rdx, [rsp+128h+var_80]; struct MSMSEC_NW_DESC *
0x18005293d  mov     rcx, [r15+r12*8+8]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180052942  call    ?MSMSecLogProfile@@YAXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUMSMSEC_NW_DESC@@@Z; MSMSecLogProfile(DOT11_MSMSEC_CONNECTION_PROFILE *,MSMSEC_NW_DESC *)
0x180052947  inc     r12d
0x18005294a  jmp     short loc_1800528DE
0x18005294c  test    rcx, rcx
0x18005294f  jz      short loc_18005296D
0x180052951  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UDOT11_MSMSEC_CONNECTION_PROFILE@@U?$integral_constant@P6AXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z$1?FreeMSMSecConfig@details@msmsec@@YAX0@Z@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>>>(std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> *,std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>> * const,std::allocator<std::unique_ptr<DOT11_MSMSEC_CONNECTION_PROFILE,std::integral_constant<void (*)(DOT11_MSMSEC_CONNECTION_PROFILE *),&msmsec::details::FreeMSMSecConfig(DOT11_MSMSEC_CONNECTION_PROFILE *)>>> &)
0x180052956  mov     rcx, [rsp+128h+var_C0]
0x18005295b  mov     rdx, [rsp+128h+var_B0]
0x180052960  sub     rdx, rcx
0x180052963  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180052967  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005296c  nop
0x18005296d  mov     r12, [rsp+128h+var_78]
0x180052975  mov     rax, [rsp+128h+var_70]
0x18005297d  jmp     short loc_1800529EB
0x18005297f  mov     edi, [rsp+128h+var_D8]
0x180052983  test    edi, edi
0x180052985  jz      short loc_1800529C7
0x180052987  lea     r14, WPP_GLOBAL_Control
0x18005298e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052995  cmp     rcx, r14
0x180052998  jz      short loc_1800529B8
0x18005299a  test    byte ptr [rcx+44h], 1
0x18005299e  jz      short loc_1800529B8
0x1800529a0  mov     edx, 0A5h
0x1800529a5  mov     r9d, edi
0x1800529a8  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x1800529af  mov     rcx, [rcx+38h]
0x1800529b3  call    WPP_SF_d
0x1800529b8  mov     rsi, [rsp+128h+var_D0]
0x1800529bd  mov     r12, [rsp+128h+var_A0]
0x1800529c5  jmp     short loc_180052A1F
0x1800529c7  lea     r14, WPP_GLOBAL_Control
0x1800529ce  mov     rsi, [rsp+128h+var_D0]
0x1800529d3  mov     r15, [rsp+128h+var_A8]
0x1800529db  mov     rax, [rsp+128h+var_68]
0x1800529e3  mov     r12, [rsp+128h+var_A0]
0x1800529eb  mov     [rax], r15
0x1800529ee  jmp     short loc_180052A1F
0x1800529f0  mov     edi, 57h ; 'W'
0x1800529f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529fc  cmp     rcx, r14
0x1800529ff  jz      short loc_180052A1A
0x180052a01  test    byte ptr [rcx+44h], 1
0x180052a05  jz      short loc_180052A1A
0x180052a07  lea     edx, [rdi+48h]
0x180052a0a  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180052a11  mov     rcx, [rcx+38h]
0x180052a15  call    WPP_SF_
0x180052a1a  test    r12, r12
0x180052a1d  jz      short loc_180052A8A
0x180052a1f  mov     eax, [rsp+128h+var_C8]
0x180052a23  mov     [r12], eax
0x180052a27  cmp     [rsp+128h+var_C4], 0
0x180052a2c  jz      short loc_180052A8A
0x180052a2e  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180052a35  mov     ecx, [rsi+9C0h]; unsigned int
  ... truncated ...
```
