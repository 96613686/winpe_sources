# CTransportServer::JoinClient(void *,CTptControlPacket *,CTptControlPacket *)

- ea: `0x1800156f0`
- end: `0x180015a9a`
- name: `?JoinClient@CTransportServer@@QEAAKPEAXPEAVCTptControlPacket@@1@Z`
- size: `938`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *, struct CTptControlPacket *, struct CTptControlPacket *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800175b4`

## callees

- `0x1800156f0`
- `0x18001a9a8`
- `0x180020558`
- `0x180020840`
- `0x180020f9c`
- `0x1800255f4`
- `0x180025850`
- `0x180025c98`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180015a7a`
- `KERNEL32!LeaveCriticalSection` at `0x180015a7a`
- `KERNEL32!EnterCriticalSection` at `0x180015734`
- `KERNEL32!EnterCriticalSection` at `0x180015734`
- `WDSSRV!WdsImpersonateClient` at `0x1800159b2`
- `WDSSRV!WdsImpersonateClient` at `0x1800159b2`
- `WDSSRV!WdsRevertToSelf` at `0x180015a4a`
- `WDSSRV!WdsRevertToSelf` at `0x180015a4a`

## string_xrefs

- `0x180015a12`: `UserSid`

## pseudocode

```c
__int64 __fastcall CTransportServer::JoinClient(
        LPCRITICAL_SECTION lpCriticalSection,
        void *a2,
        struct CTptControlPacket *a3,
        struct CTptControlPacket *a4)
{
  void *v5; // r14
  void *v6; // rsi
  void *v7; // r12
  const unsigned __int16 *v10; // r8
  __int64 v11; // r9
  unsigned int CurrentUserSid; // ebx
  const char *v13; // rdx
  const unsigned __int16 *v14; // r8
  __int64 v15; // r9
  const char *v16; // rdx
  const char *v17; // rdx
  unsigned int v18; // r9d
  unsigned int RecursionCount; // eax
  int v20; // ecx
  unsigned int v21; // eax
  const char *v22; // rdx
  unsigned int v23; // eax
  const char *v24; // rdx
  struct CCryptKey *v25; // rdx
  unsigned int v26; // r9d
  const char *v27; // rdx
  unsigned int v28; // eax
  const char *v29; // rdx
  const char *v30; // rdx
  const char *v31; // rdx
  unsigned int v32; // eax
  const char *v33; // rdx
  const char *v34; // rdx
  unsigned int v35; // eax
  const char *v36; // rdx
  int v38; // [rsp+20h] [rbp-40h]
  int v39; // [rsp+20h] [rbp-40h]
  int v40; // [rsp+20h] [rbp-40h]
  size_t Size; // [rsp+28h] [rbp-38h]
  size_t Sizea; // [rsp+28h] [rbp-38h]
  size_t Sizeb; // [rsp+28h] [rbp-38h]
  size_t v44; // [rsp+40h] [rbp-20h] BYREF
  void *v45; // [rsp+48h] [rbp-18h] BYREF
  void *Src; // [rsp+50h] [rbp-10h] BYREF
  void *v47; // [rsp+58h] [rbp-8h] BYREF
  size_t v48; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v49; // [rsp+B0h] [rbp+50h] BYREF
  int v50; // [rsp+B4h] [rbp+54h]

  v50 = HIDWORD(a3);
  v5 = 0;
  Src = 0;
  v6 = 0;
  v45 = 0;
  v49 = 0;
  v7 = 0;
  LODWORD(v48) = 0;
  v47 = 0;
  LODWORD(v44) = 0;
  EnterCriticalSection(lpCriticalSection);
  CurrentUserSid = CControlPacket::AddUdpEndpoint(
                     a4,
                     L"TpMcAddress",
                     v10,
                     v11,
                     (struct tagWDS_ENDPOINT *)((char *)&lpCriticalSection[28].SpinCount + 4));
  if ( !ElValidateWin32(CurrentUserSid, v13, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x454u) )
  {
    CurrentUserSid = CControlPacket::AddUdpEndpoint(
                       a4,
                       L"TpUniAddress",
                       v14,
                       v15,
                       (struct tagWDS_ENDPOINT *)&lpCriticalSection[2].LockSemaphore);
    if ( !ElValidateWin32(CurrentUserSid, v16, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x45Fu) )
    {
      CurrentUserSid = CControlPacket::AddULONG(a4, L"SecMode", 0, 0xFFFFFFFF, lpCriticalSection[58].RecursionCount);
      if ( !ElValidateWin32(CurrentUserSid, v17, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x46Au) )
      {
        RecursionCount = lpCriticalSection[58].RecursionCount;
        v20 = (unsigned __int16)RecursionCount;
        if ( (unsigned __int16)RecursionCount != 1 )
        {
          v21 = HIWORD(RecursionCount);
          if ( (_WORD)v21 != 1 && v20 != 2 && (_WORD)v21 != 2 )
            goto LABEL_15;
        }
        CurrentUserSid = CCryptKey::ExportKey(
                           (CCryptKey *)lpCriticalSection[353].DebugInfo,
                           (struct CCryptKey *)2,
                           8u,
                           v18,
                           &Src,
                           &v49);
        v23 = ElValidateWin32(CurrentUserSid, v22, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x474u);
        v5 = Src;
        if ( !v23 )
        {
          LODWORD(Sizea) = v49;
          CurrentUserSid = CControlPacket::AddVariable<unsigned char>((int)a4, (int)L"SymKey", 0, -1, v39, Sizea, Src);
          if ( !ElValidateWin32(
                  CurrentUserSid,
                  v24,
                  "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                  0x47Du) )
          {
            if ( HIWORD(lpCriticalSection[58].RecursionCount) != 2
              || (CurrentUserSid = CCryptKey::ExportKey(
                                     *(CCryptKey **)&lpCriticalSection[353].LockCount,
                                     v25,
                                     6u,
                                     v26,
                                     &v45,
                                     (unsigned int *)&v48),
                  v28 = ElValidateWin32(
                          CurrentUserSid,
                          v27,
                          "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                          0x486u),
                  v6 = v45,
                  !v28)
              && (LODWORD(Sizeb) = v48,
                  CurrentUserSid = CControlPacket::AddVariable<unsigned char>(
                                     (int)a4,
                                     (int)L"SignKey",
                                     0,
                                     -1,
                                     v40,
                                     Sizeb,
                                     v45),
                  !ElValidateWin32(
                     CurrentUserSid,
                     v29,
                     "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                     0x48Fu)) )
            {
              CurrentUserSid = CControlPacket::AddULONG(
                                 a4,
                                 L"HMACAlgId",
                                 0,
                                 0xFFFFFFFF,
                                 (unsigned int)lpCriticalSection[58].LockSemaphore);
              if ( !ElValidateWin32(
                      CurrentUserSid,
                      v30,
                      "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                      0x49Bu) )
              {
                CurrentUserSid = CControlPacket::AddULONG(
                                   a4,
                                   L"HashAlgId",
                                   0,
                                   0xFFFFFFFF,
                                   HIDWORD(lpCriticalSection[58].OwningThread));
                if ( !ElValidateWin32(
                        CurrentUserSid,
                        v31,
                        "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                        0x4A6u) )
                {
LABEL_15:
                  v32 = WdsImpersonateClient(a2);
                  CurrentUserSid = v32;
                  if ( v32 )
                  {
                    if ( v32 == 50 || v32 == 1244 )
                      CurrentUserSid = 0;
                    else
                      ElValidateWin32(v32, v33, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x4B3u);
                  }
                  else
                  {
                    CurrentUserSid = GetCurrentUserSid(&v47, (unsigned int *)&v44);
                    v35 = ElValidateWin32(
                            CurrentUserSid,
                            v34,
                            "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                            0x4BBu);
                    v7 = v47;
                    if ( !v35 )
                    {
                      LODWORD(Size) = v44;
                      CurrentUserSid = CControlPacket::AddVariable<unsigned char>(
                                         (int)a4,
                                         (int)L"UserSid",
                                         0,
                                         -1,
                                         v38,
                                         Size,
                                         v47);
                      ElValidateWin32(
                        CurrentUserSid,
                        v36,
                        "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                        0x4C7u);
                    }
                    WdsRevertToSelf(a2);
                  }
                }
              }
            }
          }
        }
        if ( v5 )
          operator delete(v5);
        if ( v6 )
          operator delete(v6);
        if ( v7 )
          operator delete(v7);
      }
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return CurrentUserSid;
}

```

## disassembly

```asm
0x1800156f0  mov     [rsp-38h+arg_8], rbx
0x1800156f5  mov     [rsp-38h+arg_10], r8
0x1800156fa  push    rbp
0x1800156fb  push    rsi
0x1800156fc  push    rdi
0x1800156fd  push    r12
0x1800156ff  push    r13
0x180015701  push    r14
0x180015703  push    r15
0x180015705  mov     rbp, rsp
0x180015708  sub     rsp, 60h
0x18001570c  xor     eax, eax
0x18001570e  mov     r15, r9
0x180015711  mov     r14d, eax
0x180015714  mov     [rbp+var_10], rax
0x180015718  mov     esi, eax
0x18001571a  mov     [rbp+var_18], rax
0x18001571e  mov     dword ptr [rbp+arg_10], eax
0x180015721  mov     r12d, eax
0x180015724  mov     dword ptr [rbp+arg_0], eax
0x180015727  mov     r13, rdx
0x18001572a  mov     [rbp+var_8], rax
0x18001572e  mov     rdi, rcx
0x180015731  mov     dword ptr [rbp+var_20], eax
0x180015734  call    cs:__imp_EnterCriticalSection
0x18001573a  lea     rax, [rdi+484h]
0x180015741  mov     rcx, r15; this
0x180015744  lea     rdx, aTpmcaddress; "TpMcAddress"
0x18001574b  mov     [rsp+60h+var_40], rax; struct tagWDS_ENDPOINT *
0x180015750  call    ?AddUdpEndpoint@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_ENDPOINT@@@Z; CControlPacket::AddUdpEndpoint(ushort const *,ushort const *,ulong,tagWDS_ENDPOINT *)
0x180015755  mov     r9d, 454h; unsigned int
0x18001575b  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015762  mov     ecx, eax; unsigned int
0x180015764  mov     ebx, eax
0x180015766  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001576b  test    eax, eax
0x18001576d  jnz     loc_180015A77
0x180015773  lea     rax, [rdi+68h]
0x180015777  mov     rcx, r15; this
0x18001577a  lea     rdx, aTpuniaddress; "TpUniAddress"
0x180015781  mov     [rsp+60h+var_40], rax; struct tagWDS_ENDPOINT *
0x180015786  call    ?AddUdpEndpoint@CControlPacket@@QEAAKPEBG0KPEAUtagWDS_ENDPOINT@@@Z; CControlPacket::AddUdpEndpoint(ushort const *,ushort const *,ulong,tagWDS_ENDPOINT *)
0x18001578b  mov     r9d, 45Fh; unsigned int
0x180015791  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015798  mov     ecx, eax; unsigned int
0x18001579a  mov     ebx, eax
0x18001579c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800157a1  test    eax, eax
0x1800157a3  jnz     loc_180015A77
0x1800157a9  mov     eax, [rdi+91Ch]
0x1800157af  lea     rdx, aSecmode; "SecMode"
0x1800157b6  or      r9d, 0FFFFFFFFh; unsigned int
0x1800157ba  mov     dword ptr [rsp+60h+var_40], eax; Src
0x1800157be  xor     r8d, r8d; unsigned __int16 *
0x1800157c1  mov     rcx, r15; this
0x1800157c4  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x1800157c9  mov     r9d, 46Ah; unsigned int
0x1800157cf  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800157d6  mov     ecx, eax; unsigned int
0x1800157d8  mov     ebx, eax
0x1800157da  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800157df  test    eax, eax
0x1800157e1  jnz     loc_180015A77
0x1800157e7  mov     eax, [rdi+91Ch]
0x1800157ed  lea     r8d, [r12+1]
0x1800157f2  movzx   ecx, ax
0x1800157f5  lea     edx, [r12+2]; struct CCryptKey *
0x1800157fa  cmp     ecx, r8d
0x1800157fd  jz      short loc_180015815
0x1800157ff  shr     eax, 10h
0x180015802  cmp     ax, r8w
0x180015806  jz      short loc_180015815
0x180015808  cmp     ecx, edx
0x18001580a  jz      short loc_180015815
0x18001580c  cmp     ax, dx
0x18001580f  jnz     loc_1800159AF
0x180015815  mov     rcx, [rdi+3728h]; this
0x18001581c  lea     rax, [rbp+arg_10]
0x180015820  mov     [rsp+60h+Size], rax; unsigned int *
0x180015825  mov     r8d, 8; unsigned int
0x18001582b  lea     rax, [rbp+var_10]
0x18001582f  mov     [rsp+60h+var_40], rax; int
0x180015834  call    ?ExportKey@CCryptKey@@QEAAKPEAV1@KKPEAPEAXPEAK@Z; CCryptKey::ExportKey(CCryptKey *,ulong,ulong,void * *,ulong *)
0x180015839  mov     r9d, 474h; unsigned int
0x18001583f  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015846  mov     ecx, eax; unsigned int
0x180015848  mov     ebx, eax
0x18001584a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001584f  mov     r14, [rbp+var_10]
0x180015853  test    eax, eax
0x180015855  jnz     loc_180015A50
0x18001585b  mov     eax, dword ptr [rbp+arg_10]
0x18001585e  lea     rdx, aSymkey; "SymKey"
0x180015865  mov     [rsp+60h+Src], r14; Src
0x18001586a  or      r9d, 0FFFFFFFFh; int
0x18001586e  xor     r8d, r8d; int
0x180015871  mov     dword ptr [rsp+60h+Size], eax; Size
0x180015875  mov     rcx, r15; int
0x180015878  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x18001587d  mov     r9d, 47Dh; unsigned int
0x180015883  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001588a  mov     ecx, eax; unsigned int
0x18001588c  mov     ebx, eax
0x18001588e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015893  test    eax, eax
0x180015895  jnz     loc_180015A50
0x18001589b  mov     eax, 2
0x1800158a0  cmp     [rdi+91Eh], ax
0x1800158a7  jnz     loc_180015933
0x1800158ad  mov     rcx, [rdi+3730h]; this
0x1800158b4  lea     rax, [rbp+arg_0]
0x1800158b8  mov     [rsp+60h+Size], rax; unsigned int *
0x1800158bd  mov     r8d, 6; unsigned int
0x1800158c3  lea     rax, [rbp+var_18]
0x1800158c7  mov     [rsp+60h+var_40], rax; int
0x1800158cc  call    ?ExportKey@CCryptKey@@QEAAKPEAV1@KKPEAPEAXPEAK@Z; CCryptKey::ExportKey(CCryptKey *,ulong,ulong,void * *,ulong *)
0x1800158d1  mov     r9d, 486h; unsigned int
0x1800158d7  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800158de  mov     ecx, eax; unsigned int
0x1800158e0  mov     ebx, eax
0x1800158e2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800158e7  mov     rsi, [rbp+var_18]
0x1800158eb  test    eax, eax
0x1800158ed  jnz     loc_180015A50
0x1800158f3  mov     eax, dword ptr [rbp+arg_0]
0x1800158f6  lea     rdx, aSignkey; "SignKey"
0x1800158fd  mov     [rsp+60h+Src], rsi; Src
0x180015902  or      r9d, 0FFFFFFFFh; int
0x180015906  xor     r8d, r8d; int
0x180015909  mov     dword ptr [rsp+60h+Size], eax; Size
0x18001590d  mov     rcx, r15; int
0x180015910  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180015915  mov     r9d, 48Fh; unsigned int
0x18001591b  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015922  mov     ecx, eax; unsigned int
0x180015924  mov     ebx, eax
0x180015926  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001592b  test    eax, eax
0x18001592d  jnz     loc_180015A50
0x180015933  mov     eax, [rdi+928h]
0x180015939  lea     rdx, aHmacalgid; "HMACAlgId"
0x180015940  or      r9d, 0FFFFFFFFh; unsigned int
0x180015944  mov     dword ptr [rsp+60h+var_40], eax; Src
0x180015948  xor     r8d, r8d; unsigned __int16 *
0x18001594b  mov     rcx, r15; this
0x18001594e  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180015953  mov     r9d, 49Bh; unsigned int
0x180015959  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015960  mov     ecx, eax; unsigned int
0x180015962  mov     ebx, eax
0x180015964  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015969  test    eax, eax
0x18001596b  jnz     loc_180015A50
0x180015971  mov     eax, [rdi+924h]
0x180015977  lea     rdx, aHashalgid; "HashAlgId"
0x18001597e  or      r9d, 0FFFFFFFFh; unsigned int
0x180015982  mov     dword ptr [rsp+60h+var_40], eax; int
0x180015986  xor     r8d, r8d; unsigned __int16 *
0x180015989  mov     rcx, r15; this
0x18001598c  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180015991  mov     r9d, 4A6h; unsigned int
0x180015997  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001599e  mov     ecx, eax; unsigned int
0x1800159a0  mov     ebx, eax
0x1800159a2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800159a7  test    eax, eax
0x1800159a9  jnz     loc_180015A50
0x1800159af  mov     rcx, r13
0x1800159b2  call    cs:__imp_WdsImpersonateClient
0x1800159b8  mov     ebx, eax
0x1800159ba  test    eax, eax
0x1800159bc  jz      short loc_1800159E4
0x1800159be  cmp     eax, 32h ; '2'
0x1800159c1  jz      short loc_1800159E0
0x1800159c3  cmp     eax, 4DCh
0x1800159c8  jz      short loc_1800159E0
0x1800159ca  mov     r9d, 4B3h; unsigned int
0x1800159d0  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800159d7  mov     ecx, eax; unsigned int
0x1800159d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800159de  jmp     short loc_180015A50
0x1800159e0  xor     ebx, ebx
0x1800159e2  jmp     short loc_180015A50
0x1800159e4  lea     rdx, [rbp+var_20]; unsigned int *
0x1800159e8  lea     rcx, [rbp+var_8]; void **
0x1800159ec  call    ?GetCurrentUserSid@@YAKPEAPEAXPEAK@Z; GetCurrentUserSid(void * *,ulong *)
0x1800159f1  mov     r9d, 4BBh; unsigned int
0x1800159f7  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800159fe  mov     ecx, eax; unsigned int
0x180015a00  mov     ebx, eax
0x180015a02  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015a07  mov     r12, [rbp+var_8]
0x180015a0b  test    eax, eax
0x180015a0d  jnz     short loc_180015A47
0x180015a0f  mov     eax, dword ptr [rbp+var_20]
0x180015a12  lea     rdx, aUsersid; "UserSid"
0x180015a19  mov     [rsp+60h+Src], r12; Src
0x180015a1e  or      r9d, 0FFFFFFFFh; int
0x180015a22  xor     r8d, r8d; int
0x180015a25  mov     dword ptr [rsp+60h+Size], eax; Size
0x180015a29  mov     rcx, r15; int
0x180015a2c  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180015a31  mov     r9d, 4C7h; unsigned int
0x180015a37  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180015a3e  mov     ecx, eax; unsigned int
0x180015a40  mov     ebx, eax
0x180015a42  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180015a47  mov     rcx, r13
0x180015a4a  call    cs:__imp_WdsRevertToSelf
0x180015a50  test    r14, r14
0x180015a53  jz      short loc_180015A5D
0x180015a55  mov     rcx, r14; void *
0x180015a58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a5d  test    rsi, rsi
0x180015a60  jz      short loc_180015A6A
0x180015a62  mov     rcx, rsi; void *
0x180015a65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a6a  test    r12, r12
0x180015a6d  jz      short loc_180015A77
0x180015a6f  mov     rcx, r12; void *
0x180015a72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015a77  mov     rcx, rdi; lpCriticalSection
0x180015a7a  call    cs:__imp_LeaveCriticalSection
0x180015a80  mov     eax, ebx
0x180015a82  mov     rbx, [rsp+60h+arg_8]
0x180015a8a  add     rsp, 60h
0x180015a8e  pop     r15
0x180015a90  pop     r14
0x180015a92  pop     r13
0x180015a94  pop     r12
0x180015a96  pop     rdi
0x180015a97  pop     rsi
0x180015a98  pop     rbp
0x180015a99  retn
```
