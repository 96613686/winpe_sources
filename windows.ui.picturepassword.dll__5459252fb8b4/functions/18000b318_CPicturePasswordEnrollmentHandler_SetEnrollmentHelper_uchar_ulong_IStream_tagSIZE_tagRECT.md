# CPicturePasswordEnrollmentHandler::_SetEnrollmentHelper(uchar *,ulong,IStream *,tagSIZE,tagRECT)

- ea: `0x18000b318`
- end: `0x18000b596`
- name: `?_SetEnrollmentHelper@CPicturePasswordEnrollmentHandler@@IEAAJPEAEKPEAUIStream@@UtagSIZE@@UtagRECT@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(CPicturePasswordEnrollmentHandler *this, unsigned __int8 *, unsigned int, struct IStream *, struct tagSIZE, struct tagRECT *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009710`
- `0x180009750`

## callees

- `0x180005a10`
- `0x180005a2c`
- `0x180006d54`
- `0x1800092b8`
- `0x180009520`
- `0x18000ad34`
- `0x18000b000`
- `0x18000b318`
- `0x18000b59c`
- `0x18000c6d4`
- `0x180019274`
- `0x1800197cc`
- `0x1800198d4`
- `0x1800199b8`
- `0x180019bc0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b3ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b3ae`

## string_xrefs

- `0x18000b4ad`: `bgPath`

## pseudocode

```c
__int64 __fastcall CPicturePasswordEnrollmentHandler::_SetEnrollmentHelper(
        CPicturePasswordEnrollmentHandler *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IStream *a4,
        struct tagSIZE a5,
        struct tagRECT *a6)
{
  struct tagRECT *v6; // rsi
  int CallerSID; // edi
  __int64 v11; // r13
  PSID v12; // rbx
  const unsigned __int16 *v13; // r8
  struct GESTURE_SIGNATURE *v14; // r14
  unsigned __int64 v15; // r15
  int v16; // eax
  unsigned __int64 v17; // r9
  LPWSTR StringSid; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-51h] BYREF
  struct GESTURE_SIGNATURE *Src; // [rsp+40h] [rbp-49h] BYREF
  PSID Sid; // [rsp+48h] [rbp-41h] BYREF
  CPicturePasswordEnrollmentHandler *v23; // [rsp+50h] [rbp-39h]
  void **v24; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-29h]
  int v26; // [rsp+78h] [rbp-11h]
  HKEY v27; // [rsp+80h] [rbp-9h]

  v6 = a6;
  v23 = this;
  CallerSID = -2147024809;
  if ( a3 > 0x3C && (a3 & 0xF) == 0 )
  {
    Sid = 0;
    CallerSID = CImpersonateCaller::GetCallerSID(&Sid);
    if ( CallerSID >= 0 )
    {
      Src = 0;
      v11 = a3;
      CallerSID = UnprotectMemory(1, a2, a3, (unsigned __int8 **)&Src);
      if ( CallerSID >= 0 )
      {
        v12 = Sid;
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid, &StringSid) )
          CallerSID = 0;
        else
          CallerSID = ResultFromKnownLastError();
        v14 = Src;
        if ( CallerSID >= 0 )
        {
          CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(
            (CConvenienceLogonEnrollmentData *)&v24,
            StringSid,
            v13);
          v24 = &CPicturePasswordUserData::`vftable';
          if ( !a4 )
          {
            CallerSID = CPicturePasswordUserData::GetImageSize((CPicturePasswordUserData *)&v24, &a5);
            if ( CallerSID >= 0 )
            {
              *(struct tagSIZE *)&v6->right = a5;
              *(_QWORD *)&v6->left = 0;
            }
          }
          v15 = 0;
          if ( CallerSID >= 0 )
          {
            while ( v15 < 3 )
            {
              v16 = _ValidateGesture((struct GESTURE_SIGNATURE *)((char *)v14 + 20 * v15++), v6);
              CallerSID = v16;
              if ( v16 < 0 )
                goto LABEL_28;
            }
            CallerSID = _ConfirmPasswordBufferPadding(
                          (const unsigned __int16 *)v14 + 30,
                          (unsigned __int64)(v11 - 60) >> 1);
            if ( CallerSID >= 0 )
            {
              CallerSID = CPicturePasswordVault::SetEnrollment(v12, (const unsigned __int16 *)v14 + 30, v14, v17);
              if ( CallerSID < 0 )
                goto LABEL_27;
              if ( !a4 )
                goto LABEL_26;
              v20 = 0;
              CallerSID = _CacheUserImage(v12, a4, &a5, v6, &v20);
              if ( CallerSID >= 0 )
              {
                CallerSID = v26;
                if ( v26 >= 0 )
                {
                  CallerSID = SHRegSetString(v27, v25, L"bgPath", v20);
                  if ( CallerSID >= 0 )
                  {
                    CallerSID = v26;
                    if ( v26 >= 0 )
                    {
                      CallerSID = SHRegSetDWORD(v27, v25, L"bgcx", v6->right - v6->left);
                      if ( CallerSID >= 0 )
                        CallerSID = SHRegSetDWORD(v27, v25, L"bgcy", v6->bottom - v6->top);
                    }
                  }
                }
              }
              CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v20);
              if ( CallerSID < 0 )
LABEL_27:
                (*(void (__fastcall **)(CPicturePasswordEnrollmentHandler *))(*(_QWORD *)v23 + 56LL))(v23);
              else
LABEL_26:
                SHRegSetString(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\UserTile",
                  StringSid,
                  L"{2135f72a-90b5-4ed3-a7f1-8bb705ac276a}");
            }
          }
LABEL_28:
          CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData((CConvenienceLogonEnrollmentData *)&v24);
        }
        for ( ; v11; --v11 )
        {
          *(_BYTE *)v14 = 0;
          v14 = (struct GESTURE_SIGNATURE *)((char *)v14 + 1);
        }
        CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&StringSid);
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&Src);
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&Sid);
  }
  return (unsigned int)CallerSID;
}

```

## disassembly

```asm
0x18000b318  push    rbp
0x18000b31a  push    rbx
0x18000b31b  push    rsi
0x18000b31c  push    rdi
0x18000b31d  push    r12
0x18000b31f  push    r13
0x18000b321  push    r14
0x18000b323  push    r15
0x18000b325  lea     rbp, [rsp-0Fh]
0x18000b32a  sub     rsp, 98h
0x18000b331  mov     rsi, [rbp+47h+arg_28]
0x18000b335  mov     r12, r9
0x18000b338  mov     ebx, r8d
0x18000b33b  mov     r14, rdx
0x18000b33e  mov     [rbp+47h+var_80], rcx
0x18000b342  mov     edi, 80070057h
0x18000b347  cmp     r8d, 3Ch ; '<'
0x18000b34b  jbe     loc_18000B580
0x18000b351  test    bl, 0Fh
0x18000b354  jnz     loc_18000B580
0x18000b35a  lea     rcx, [rbp+47h+Sid]; void **
0x18000b35e  mov     [rbp+47h+Sid], 0
0x18000b366  call    ?GetCallerSID@CImpersonateCaller@@SAJPEAPEAX@Z; CImpersonateCaller::GetCallerSID(void * *)
0x18000b36b  mov     edi, eax
0x18000b36d  test    eax, eax
0x18000b36f  js      loc_18000B577
0x18000b375  lea     r9, [rbp+47h+Src]; unsigned __int8 **
0x18000b379  mov     [rbp+47h+Src], 0
0x18000b381  mov     r8d, ebx; unsigned __int64
0x18000b384  mov     rdx, r14; unsigned __int8 *
0x18000b387  mov     cl, 1; bool
0x18000b389  mov     r13d, ebx
0x18000b38c  call    ?UnprotectMemory@@YAJ_NPEAE_KPEAPEAE@Z; UnprotectMemory(bool,uchar *,unsigned __int64,uchar * *)
0x18000b391  mov     edi, eax
0x18000b393  test    eax, eax
0x18000b395  js      loc_18000B56E
0x18000b39b  mov     rbx, [rbp+47h+Sid]
0x18000b39f  lea     rdx, [rbp+47h+StringSid]; StringSid
0x18000b3a3  mov     rcx, rbx; Sid
0x18000b3a6  mov     [rbp+47h+StringSid], 0
0x18000b3ae  call    cs:__imp_ConvertSidToStringSidW
0x18000b3b4  test    eax, eax
0x18000b3b6  jz      short loc_18000B3BC
0x18000b3b8  xor     edi, edi
0x18000b3ba  jmp     short loc_18000B3C3
0x18000b3bc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b3c1  mov     edi, eax
0x18000b3c3  mov     r14, [rbp+47h+Src]
0x18000b3c7  test    edi, edi
0x18000b3c9  js      loc_18000B553
0x18000b3cf  mov     rdx, [rbp+47h+StringSid]; unsigned __int16 *
0x18000b3d3  lea     rcx, [rbp+47h+var_78]; this
0x18000b3d7  call    ??0CConvenienceLogonEnrollmentData@@QEAA@PEBG0@Z; CConvenienceLogonEnrollmentData::CConvenienceLogonEnrollmentData(ushort const *,ushort const *)
0x18000b3dc  lea     rax, ??_7CPicturePasswordUserData@@6B@; const CPicturePasswordUserData::`vftable'
0x18000b3e3  mov     [rbp+47h+var_78], rax
0x18000b3e7  test    r12, r12
0x18000b3ea  jnz     short loc_18000B40E
0x18000b3ec  lea     rdx, [rbp+47h+arg_20]; struct tagSIZE *
0x18000b3f0  lea     rcx, [rbp+47h+var_78]; this
0x18000b3f4  call    ?GetImageSize@CPicturePasswordUserData@@QEBAJPEAUtagSIZE@@@Z; CPicturePasswordUserData::GetImageSize(tagSIZE *)
0x18000b3f9  mov     edi, eax
0x18000b3fb  test    eax, eax
0x18000b3fd  js      short loc_18000B40E
0x18000b3ff  mov     eax, [rbp+47h+arg_20.cx]
0x18000b402  mov     [rsi+8], eax
0x18000b405  mov     eax, [rbp+47h+arg_20.cy]
0x18000b408  mov     [rsi+0Ch], eax
0x18000b40b  mov     [rsi], r12
0x18000b40e  xor     r15d, r15d
0x18000b411  test    edi, edi
0x18000b413  js      loc_18000B54A
0x18000b419  cmp     r15, 3
0x18000b41d  jnb     short loc_18000B43D
0x18000b41f  lea     rax, [r15+r15*4]
0x18000b423  mov     rdx, rsi; struct tagRECT *
0x18000b426  lea     rcx, [r14+rax*4]; struct GESTURE_SIGNATURE *
0x18000b42a  call    ?_ValidateGesture@@YAJAEBUGESTURE_SIGNATURE@@AEBUtagRECT@@@Z; _ValidateGesture(GESTURE_SIGNATURE const &,tagRECT const &)
0x18000b42f  inc     r15
0x18000b432  mov     edi, eax
0x18000b434  test    eax, eax
0x18000b436  jns     short loc_18000B419
0x18000b438  jmp     loc_18000B54A
0x18000b43d  lea     rdx, [r13-3Ch]
0x18000b441  shr     rdx, 1; unsigned __int64
0x18000b444  lea     rcx, [r14+3Ch]; unsigned __int16 *
0x18000b448  call    ?_ConfirmPasswordBufferPadding@@YAJPEBG_K@Z; _ConfirmPasswordBufferPadding(ushort const *,unsigned __int64)
0x18000b44d  mov     edi, eax
0x18000b44f  test    eax, eax
0x18000b451  js      loc_18000B54A
0x18000b457  mov     r8, r14; Src
0x18000b45a  lea     rdx, [r14+3Ch]; unsigned __int16 *
0x18000b45e  mov     rcx, rbx; Sid
0x18000b461  call    ?SetEnrollment@CPicturePasswordVault@@SAJPEAXPEBGPEBUGESTURE_SIGNATURE@@_K@Z; CPicturePasswordVault::SetEnrollment(void *,ushort const *,GESTURE_SIGNATURE const *,unsigned __int64)
0x18000b466  mov     edi, eax
0x18000b468  test    eax, eax
0x18000b46a  js      loc_18000B53A
0x18000b470  test    r12, r12
0x18000b473  jz      loc_18000B51A
0x18000b479  lea     rax, [rbp+47h+var_98]
0x18000b47d  mov     [rbp+47h+var_98], 0
0x18000b485  mov     r9, rsi; struct tagRECT *
0x18000b488  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 **
0x18000b48d  lea     r8, [rbp+47h+arg_20]; struct tagSIZE *
0x18000b491  mov     rdx, r12; struct IStream *
0x18000b494  mov     rcx, rbx; void *
0x18000b497  call    ?_CacheUserImage@@YAJPEAXPEAUIStream@@AEBUtagSIZE@@AEBUtagRECT@@PEAPEAG@Z; _CacheUserImage(void *,IStream *,tagSIZE const &,tagRECT const &,ushort * *)
0x18000b49c  mov     edi, eax
0x18000b49e  test    eax, eax
0x18000b4a0  js      short loc_18000B50D
0x18000b4a2  mov     edi, [rbp+47h+var_58]
0x18000b4a5  test    edi, edi
0x18000b4a7  js      short loc_18000B50D
0x18000b4a9  mov     r9, [rbp+47h+var_98]; unsigned __int16 *
0x18000b4ad  lea     r8, Value; "bgPath"
0x18000b4b4  mov     rdx, [rbp+47h+var_70]; unsigned __int16 *
0x18000b4b8  mov     rcx, [rbp+47h+var_50]; HKEY
0x18000b4bc  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000b4c1  mov     edi, eax
0x18000b4c3  test    eax, eax
0x18000b4c5  js      short loc_18000B50D
0x18000b4c7  mov     edi, [rbp+47h+var_58]
0x18000b4ca  test    edi, edi
0x18000b4cc  js      short loc_18000B50D
0x18000b4ce  mov     r9d, [rsi+8]
0x18000b4d2  lea     r8, aBgcx; "bgcx"
0x18000b4d9  sub     r9d, [rsi]; unsigned int
0x18000b4dc  mov     rdx, [rbp+47h+var_70]; unsigned __int16 *
0x18000b4e0  mov     rcx, [rbp+47h+var_50]; HKEY
0x18000b4e4  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000b4e9  mov     edi, eax
0x18000b4eb  test    eax, eax
0x18000b4ed  js      short loc_18000B50D
0x18000b4ef  mov     r9d, [rsi+0Ch]
0x18000b4f3  lea     r8, aBgcy; "bgcy"
0x18000b4fa  sub     r9d, [rsi+4]; unsigned int
0x18000b4fe  mov     rdx, [rbp+47h+var_70]; unsigned __int16 *
0x18000b502  mov     rcx, [rbp+47h+var_50]; HKEY
0x18000b506  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000b50b  mov     edi, eax
0x18000b50d  lea     rcx, [rbp+47h+var_98]
0x18000b511  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000b516  test    edi, edi
0x18000b518  js      short loc_18000B53A
0x18000b51a  mov     r8, [rbp+47h+StringSid]; unsigned __int16 *
0x18000b51e  lea     r9, a2135f72a90b54e; "{2135f72a-90b5-4ed3-a7f1-8bb705ac276a}"
0x18000b525  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000b52c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18000b533  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000b538  jmp     short loc_18000B54A
0x18000b53a  mov     rcx, [rbp+47h+var_80]
0x18000b53e  mov     rax, [rcx]
0x18000b541  mov     rax, [rax+38h]
0x18000b545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54a  lea     rcx, [rbp+47h+var_78]; this
0x18000b54e  call    ??1CConvenienceLogonEnrollmentData@@UEAA@XZ; CConvenienceLogonEnrollmentData::~CConvenienceLogonEnrollmentData(void)
0x18000b553  test    r13, r13
0x18000b556  jz      short loc_18000B565
0x18000b558  mov     byte ptr [r14], 0
0x18000b55c  inc     r14
0x18000b55f  sub     r13, 1
0x18000b563  jnz     short loc_18000B558
0x18000b565  lea     rcx, [rbp+47h+StringSid]
0x18000b569  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18000b56e  lea     rcx, [rbp+47h+Src]
0x18000b572  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000b577  lea     rcx, [rbp+47h+Sid]
0x18000b57b  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000b580  mov     eax, edi
0x18000b582  add     rsp, 98h
0x18000b589  pop     r15
0x18000b58b  pop     r14
0x18000b58d  pop     r13
0x18000b58f  pop     r12
0x18000b591  pop     rdi
0x18000b592  pop     rsi
0x18000b593  pop     rbx
0x18000b594  pop     rbp
0x18000b595  retn
```
