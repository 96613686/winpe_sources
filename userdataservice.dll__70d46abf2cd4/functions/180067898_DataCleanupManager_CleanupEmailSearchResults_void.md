# DataCleanupManager::CleanupEmailSearchResults(void)

- ea: `0x180067898`
- end: `0x180067cf5`
- name: `?CleanupEmailSearchResults@DataCleanupManager@@QEAAJXZ`
- size: `1117`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004038c`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180057c64`
- `0x180067898`
- `0x18007e770`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800678cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800678cc`
- `CEMAPI!CreateMAPITableWalker` at `0x1800679b2`
- `CEMAPI!CreateMAPITableWalker` at `0x180067aaa`
- `CEMAPI!CreateMAPITableWalker` at `0x1800679b2`
- `CEMAPI!CreateMAPITableWalker` at `0x180067aaa`
- `CEMAPI!MAPILogonEx` at `0x18006791c`
- `CEMAPI!MAPILogonEx` at `0x18006791c`

## string_xrefs

- `0x1800678e7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x18006792e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180067981`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180067bb4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180067c27`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180067c42`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180067c60`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall DataCleanupManager::CleanupEmailSearchResults(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned __int64 v2; // rdx
  int v3; // eax
  unsigned int v4; // edi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // edi
  unsigned __int64 v16; // rcx
  unsigned int *v17; // r10
  __int64 v18; // rdx
  int v19; // r11d
  unsigned int v20; // r9d
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-29h]
  __int64 v26; // [rsp+40h] [rbp-9h] BYREF
  __int64 v27; // [rsp+48h] [rbp-1h] BYREF
  __int64 v28; // [rsp+50h] [rbp+7h] BYREF
  __int64 v29; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+60h] [rbp+17h] BYREF
  __int64 v31; // [rsp+68h] [rbp+1Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+27h] BYREF
  _DWORD v33[2]; // [rsp+78h] [rbp+2Fh] BYREF
  _DWORD v34[4]; // [rsp+80h] [rbp+37h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = FileTime64::Retreat((FileTime64 *)&SystemTimeAsFileTime, v2);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent(
      (unsigned int)v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      660);
    return v4;
  }
  v31 = 0;
  v6 = MAPILogonEx(0, 0, 0, 0, &v31);
  v4 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      664);
LABEL_45:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v31);
    return v4;
  }
  v33[0] = 1;
  v33[1] = 903872770;
  v27 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v31 + 32LL))(v31, 0x80000000LL, &v27);
  v4 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      669);
LABEL_44:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v27);
    goto LABEL_45;
  }
  v26 = 0;
  v8 = CreateMAPITableWalker(3, v27, v33, &v26);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 676;
    goto LABEL_42;
  }
LABEL_10:
  if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26) >= 0 )
  {
    v8 = DataCleanupManager::FailIfShutdownOrDc(lpCriticalSection);
    v4 = v8;
    if ( v8 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26);
      v28 = 0;
      LODWORD(v25) = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 72LL))(
              v31,
              *(unsigned int *)(*(_QWORD *)(v10 + 8) + 8LL),
              *(_QWORD *)(*(_QWORD *)(v10 + 8) + 16LL),
              0,
              v25,
              0,
              &v28);
      v4 = v11;
      if ( v11 < 0 )
      {
        Log_HREvent(
          (unsigned int)v11,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          692);
      }
      else
      {
        v30 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 120LL))(v28, 0, &v30);
        v4 = v12;
        if ( v12 < 0 )
        {
          Log_HREvent(
            (unsigned int)v12,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            696);
        }
        else
        {
          v34[0] = 3;
          v34[1] = 268370178;
          v34[2] = 906035203;
          v34[3] = 805765184;
          v29 = 0;
          v13 = CreateMAPITableWalker(2, v30, v34, &v29);
          v4 = v13;
          if ( v13 < 0 )
          {
            v22 = 706;
          }
          else
          {
            while ( 1 )
            {
              if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29) < 0 )
              {
                ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
                ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
                ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
                goto LABEL_10;
              }
              v13 = DataCleanupManager::FailIfShutdownOrDc(lpCriticalSection);
              v4 = v13;
              if ( v13 < 0 )
                break;
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 32LL))(v29);
              v15 = *(_DWORD *)(v14 + 4);
              if ( v15 )
              {
                v16 = 0;
                v17 = 0;
                v18 = *(_QWORD *)(v14 + 8);
                LOBYTE(v19) = 0;
                v20 = 0;
                v21 = 0;
                do
                {
                  switch ( *(_DWORD *)(v18 + 24 * v21) )
                  {
                    case 0xFFF0102:
                      v17 = (unsigned int *)(v18 + 8 + 24 * v21);
                      break;
                    case 0x30070040:
                      v16 = *(_QWORD *)(v18 + 24 * v21 + 8);
                      break;
                    case 0x36010003:
                      v19 = *(_DWORD *)(v18 + 24 * v21 + 8);
                      break;
                  }
                  ++v20;
                  ++v21;
                }
                while ( v20 < v15 );
                if ( (v19 & 4) != 0 && *(_QWORD *)&SystemTimeAsFileTime >= v16 )
                {
                  if ( !v17 )
                  {
                    v4 = -2147418113;
                    v22 = 742;
                    v24 = 2147549183LL;
                    v23 = 0;
                    goto LABEL_32;
                  }
                  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v28 + 192LL))(
                          v28,
                          *v17,
                          *((_QWORD *)v17 + 1),
                          0,
                          0,
                          261);
                  v4 = v13;
                  if ( v13 < 0 )
                  {
                    v22 = 749;
                    goto LABEL_31;
                  }
                }
              }
            }
            v22 = 710;
          }
LABEL_31:
          v23 = 1;
          v24 = (unsigned int)v13;
LABEL_32:
          Log_HREvent(
            v24,
            v23,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            v22);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v29);
        }
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v28);
      goto LABEL_43;
    }
    v9 = 680;
LABEL_42:
    Log_HREvent(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v9);
LABEL_43:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v26);
    goto LABEL_44;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  return 0;
}

```

## disassembly

```asm
0x180067898  mov     [rsp-8+arg_8], rsi
0x18006789d  mov     [rsp-8+arg_10], rdi
0x1800678a2  push    rbp
0x1800678a3  lea     rbp, [rsp-57h]
0x1800678a8  sub     rsp, 0A0h
0x1800678af  mov     rax, cs:__security_cookie
0x1800678b6  xor     rax, rsp
0x1800678b9  mov     [rbp+57h+var_10], rax
0x1800678bd  mov     rsi, rcx
0x1800678c0  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800678c8  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800678cc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800678d2  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; this
0x1800678d6  call    ?Retreat@FileTime64@@QEAAJ_K@Z; FileTime64::Retreat(unsigned __int64)
0x1800678db  mov     edi, eax
0x1800678dd  test    eax, eax
0x1800678df  jns     short loc_180067901
0x1800678e1  mov     r9d, 294h
0x1800678e7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800678ee  mov     edx, 1
0x1800678f3  mov     ecx, eax
0x1800678f5  call    Log_HREvent
0x1800678fa  mov     eax, edi
0x1800678fc  jmp     loc_180067CD4
0x180067901  lea     rax, [rbp+57h+var_38]
0x180067905  mov     [rbp+57h+var_38], 0
0x18006790d  xor     r9d, r9d
0x180067910  mov     [rsp+0A0h+var_80], rax
0x180067915  xor     r8d, r8d
0x180067918  xor     edx, edx
0x18006791a  xor     ecx, ecx
0x18006791c  call    cs:__imp_MAPILogonEx
0x180067922  mov     edi, eax
0x180067924  test    eax, eax
0x180067926  jns     short loc_180067946
0x180067928  mov     r9d, 298h
0x18006792e  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067935  mov     edx, 1
0x18006793a  mov     ecx, eax
0x18006793c  call    Log_HREvent
0x180067941  jmp     loc_180067C85
0x180067946  mov     rcx, [rbp+57h+var_38]
0x18006794a  lea     r8, [rbp+57h+var_58]
0x18006794e  mov     [rbp+57h+var_28], 1
0x180067955  mov     edx, 80000000h
0x18006795a  mov     [rbp+57h+var_24], 35E00102h
0x180067961  mov     [rbp+57h+var_58], 0
0x180067969  mov     rax, [rcx]
0x18006796c  mov     rax, [rax+20h]
0x180067970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067975  mov     edi, eax
0x180067977  test    eax, eax
0x180067979  jns     short loc_180067999
0x18006797b  mov     r9d, 29Dh
0x180067981  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067988  mov     edx, 1
0x18006798d  mov     ecx, eax
0x18006798f  call    Log_HREvent
0x180067994  jmp     loc_180067C7C
0x180067999  mov     rdx, [rbp+57h+var_58]
0x18006799d  lea     r9, [rbp+57h+var_60]
0x1800679a1  lea     r8, [rbp+57h+var_28]
0x1800679a5  mov     [rbp+57h+var_60], 0
0x1800679ad  mov     ecx, 3
0x1800679b2  call    cs:__imp_CreateMAPITableWalker
0x1800679b8  mov     edi, eax
0x1800679ba  test    eax, eax
0x1800679bc  jns     short loc_1800679C9
0x1800679be  mov     r9d, 2A4h
0x1800679c4  jmp     loc_180067C60
0x1800679c9  mov     rcx, [rbp+57h+var_60]
0x1800679cd  mov     rax, [rcx]
0x1800679d0  mov     rax, [rax+18h]
0x1800679d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679d9  test    eax, eax
0x1800679db  js      loc_180067C93
0x1800679e1  mov     rcx, rsi; lpCriticalSection
0x1800679e4  call    ?FailIfShutdownOrDc@DataCleanupManager@@AEAAJXZ; DataCleanupManager::FailIfShutdownOrDc(void)
0x1800679e9  mov     edi, eax
0x1800679eb  test    eax, eax
0x1800679ed  js      loc_180067C5A
0x1800679f3  mov     rcx, [rbp+57h+var_60]
0x1800679f7  mov     rax, [rcx]
0x1800679fa  mov     rax, [rax+20h]
0x1800679fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a03  mov     rcx, [rbp+57h+var_38]
0x180067a07  lea     r8, [rbp+57h+var_50]
0x180067a0b  mov     [rbp+57h+var_50], 0
0x180067a13  xor     r9d, r9d
0x180067a16  mov     [rsp+0A0h+var_70], r8
0x180067a1b  mov     rdx, [rax+8]
0x180067a1f  mov     rax, [rcx]
0x180067a22  mov     [rsp+0A0h+var_78], 0
0x180067a2b  mov     dword ptr [rsp+0A0h+var_80], 0
0x180067a33  mov     r8, [rdx+10h]
0x180067a37  mov     rax, [rax+48h]
0x180067a3b  mov     edx, [rdx+8]
0x180067a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a43  mov     edi, eax
0x180067a45  test    eax, eax
0x180067a47  js      loc_180067C3C
0x180067a4d  mov     rcx, [rbp+57h+var_50]
0x180067a51  lea     r8, [rbp+57h+var_40]
0x180067a55  mov     [rbp+57h+var_40], 0
0x180067a5d  xor     edx, edx
0x180067a5f  mov     rax, [rcx]
0x180067a62  mov     rax, [rax+78h]
0x180067a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a6b  mov     edi, eax
0x180067a6d  test    eax, eax
0x180067a6f  js      loc_180067C21
0x180067a75  mov     rdx, [rbp+57h+var_40]
0x180067a79  lea     r9, [rbp+57h+var_48]
0x180067a7d  lea     r8, [rbp+57h+var_20]
0x180067a81  mov     [rbp+57h+var_20], 3
0x180067a88  mov     ecx, 2
0x180067a8d  mov     [rbp+57h+var_1C], 0FFF0102h
0x180067a94  mov     [rbp+57h+var_18], 36010003h
0x180067a9b  mov     [rbp+57h+var_14], 30070040h
0x180067aa2  mov     [rbp+57h+var_48], 0
0x180067aaa  call    cs:__imp_CreateMAPITableWalker
0x180067ab0  mov     edi, eax
0x180067ab2  test    eax, eax
0x180067ab4  js      loc_180067C19
0x180067aba  mov     rcx, [rbp+57h+var_48]
0x180067abe  mov     rax, [rcx]
0x180067ac1  mov     rax, [rax+18h]
0x180067ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067aca  test    eax, eax
0x180067acc  js      loc_180067BE0
0x180067ad2  mov     rcx, rsi; lpCriticalSection
0x180067ad5  call    ?FailIfShutdownOrDc@DataCleanupManager@@AEAAJXZ; DataCleanupManager::FailIfShutdownOrDc(void)
0x180067ada  mov     edi, eax
0x180067adc  test    eax, eax
0x180067ade  js      loc_180067C11
0x180067ae4  mov     rcx, [rbp+57h+var_48]
0x180067ae8  mov     rax, [rcx]
0x180067aeb  mov     rax, [rax+20h]
0x180067aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067af4  mov     edi, [rax+4]
0x180067af7  test    edi, edi
0x180067af9  jz      short loc_180067ABA
0x180067afb  mov     rcx, cs:qword_18013EDA8
0x180067b02  xor     r10d, r10d
0x180067b05  mov     rdx, [rax+8]
0x180067b09  xor     r11d, r11d
0x180067b0c  xor     r9d, r9d
0x180067b0f  xor     r8d, r8d
0x180067b12  lea     rax, [r8+r8*2]
0x180067b16  cmp     dword ptr [rdx+rax*8], 0FFF0102h
0x180067b1d  jz      short loc_180067B3F
0x180067b1f  cmp     dword ptr [rdx+rax*8], 30070040h
0x180067b26  jz      short loc_180067B38
0x180067b28  cmp     dword ptr [rdx+rax*8], 36010003h
0x180067b2f  jnz     short loc_180067B47
0x180067b31  mov     r11d, [rdx+rax*8+8]
0x180067b36  jmp     short loc_180067B47
0x180067b38  mov     rcx, [rdx+rax*8+8]
0x180067b3d  jmp     short loc_180067B47
0x180067b3f  lea     r10, [rdx+8]
0x180067b43  lea     r10, [r10+rax*8]
0x180067b47  inc     r9d
0x180067b4a  inc     r8
0x180067b4d  cmp     r9d, edi
0x180067b50  jb      short loc_180067B12
0x180067b52  test    r11b, 4
0x180067b56  jz      loc_180067ABA
0x180067b5c  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180067b60  jb      loc_180067ABA
0x180067b66  test    r10, r10
0x180067b69  jz      loc_180067C00
0x180067b6f  mov     rcx, [rbp+57h+var_50]
0x180067b73  xor     r9d, r9d
0x180067b76  mov     r8, [r10+8]
0x180067b7a  mov     edx, [r10]
0x180067b7d  mov     dword ptr [rsp+0A0h+var_78], 105h
0x180067b85  mov     rax, [rcx]
0x180067b88  mov     [rsp+0A0h+var_80], 0
0x180067b91  mov     rax, [rax+0C0h]
0x180067b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b9d  mov     edi, eax
0x180067b9f  test    eax, eax
0x180067ba1  jns     loc_180067ABA
0x180067ba7  mov     r9d, 2EDh
0x180067bad  mov     edx, 1
0x180067bb2  mov     ecx, eax
0x180067bb4  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067bbb  call    Log_HREvent
0x180067bc0  lea     rcx, [rbp+57h+var_48]
0x180067bc4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067bc9  lea     rcx, [rbp+57h+var_40]
0x180067bcd  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067bd2  lea     rcx, [rbp+57h+var_50]
0x180067bd6  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067bdb  jmp     loc_180067C73
0x180067be0  lea     rcx, [rbp+57h+var_48]
0x180067be4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067be9  lea     rcx, [rbp+57h+var_40]
0x180067bed  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067bf2  lea     rcx, [rbp+57h+var_50]
0x180067bf6  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067bfb  jmp     loc_1800679C9
0x180067c00  mov     edi, 8000FFFFh
0x180067c05  mov     r9d, 2E6h
0x180067c0b  mov     ecx, edi
0x180067c0d  xor     edx, edx
0x180067c0f  jmp     short loc_180067BB4
0x180067c11  mov     r9d, 2C6h
0x180067c17  jmp     short loc_180067BAD
0x180067c19  mov     r9d, 2C2h
0x180067c1f  jmp     short loc_180067BAD
0x180067c21  mov     r9d, 2B8h
0x180067c27  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067c2e  mov     edx, 1
0x180067c33  mov     ecx, eax
0x180067c35  call    Log_HREvent
0x180067c3a  jmp     short loc_180067BC9
0x180067c3c  mov     r9d, 2B4h
0x180067c42  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067c49  mov     edx, 1
0x180067c4e  mov     ecx, eax
0x180067c50  call    Log_HREvent
0x180067c55  jmp     loc_180067BD2
0x180067c5a  mov     r9d, 2A8h
0x180067c60  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180067c67  mov     edx, 1
0x180067c6c  mov     ecx, eax
0x180067c6e  call    Log_HREvent
0x180067c73  lea     rcx, [rbp+57h+var_60]
0x180067c77  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067c7c  lea     rcx, [rbp+57h+var_58]
0x180067c80  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067c85  lea     rcx, [rbp+57h+var_38]
0x180067c89  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180067c8e  jmp     loc_1800678FA
0x180067c93  mov     rcx, [rbp+57h+var_60]
0x180067c97  test    rcx, rcx
0x180067c9a  jz      short loc_180067CA8
0x180067c9c  mov     rax, [rcx]
0x180067c9f  mov     rax, [rax+10h]
0x180067ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ca8  mov     rcx, [rbp+57h+var_58]
0x180067cac  test    rcx, rcx
0x180067caf  jz      short loc_180067CBD
0x180067cb1  mov     rax, [rcx]
0x180067cb4  mov     rax, [rax+10h]
0x180067cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cbd  mov     rcx, [rbp+57h+var_38]
0x180067cc1  test    rcx, rcx
0x180067cc4  jz      short loc_180067CD2
0x180067cc6  mov     rax, [rcx]
0x180067cc9  mov     rax, [rax+10h]
0x180067ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cd2  xor     eax, eax
0x180067cd4  mov     rcx, [rbp+57h+var_10]
0x180067cd8  xor     rcx, rsp; StackCookie
0x180067cdb  call    __security_check_cookie
0x180067ce0  lea     r11, [rsp+0A0h+var_s0]
0x180067ce8  mov     rsi, [r11+18h]
0x180067cec  mov     rdi, [r11+20h]
0x180067cf0  mov     rsp, r11
0x180067cf3  pop     rbp
0x180067cf4  retn
```
