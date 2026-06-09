# CSpp::_BuildCommonSnapshotProp(_SPP_CREATE_REASON,ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x18001176c`
- end: `0x180011b27`
- name: `?_BuildCommonSnapshotProp@CSpp@@AEAAJW4_SPP_CREATE_REASON@@PEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(CSpp *, int, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006730`
- `0x180013c7c`

## callees

- `0x18001176c`
- `0x180016d80`
- `0x1800185d0`
- `0x180018844`
- `0x180018f10`
- `0x180019a04`
- `0x180019bb4`
- `0x18001b70c`
- `0x1800214cc`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d408`
- `0x180034bd4`
- `0x180034f10`
- `0x180034f54`
- `0x18003532c`
- `0x180035b00`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180011ad1`
- `KERNEL32!CloseHandle` at `0x180011ad1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800118a9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800118a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011aa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011aa4`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180011a9a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180011a9a`

## string_xrefs

- `0x1800117d7`: `CSpp::_BuildCommonSnapshotProp`

## pseudocode

```c
__int64 __fastcall CSpp::_BuildCommonSnapshotProp(CSpp *a1, int a2, const unsigned __int16 *a3, __int64 a4)
{
  char *v8; // rbx
  int IsServerSku; // r15d
  __int16 v10; // ax
  DWORD dwLowDateTime; // r13d
  CSpp *v12; // rcx
  unsigned int v13; // ecx
  int v14; // eax
  CSpp *v15; // rcx
  bool v16; // sf
  struct _GUID v17; // xmm0
  unsigned int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v22; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-A5h] BYREF
  int NextIndex; // [rsp+38h] [rbp-A1h] BYREF
  __int16 v25; // [rsp+3Ch] [rbp-9Dh]
  __int16 v26; // [rsp+3Eh] [rbp-9Bh]
  PTOKEN_PRIVILEGES NewState; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int16 **v28; // [rsp+78h] [rbp-61h] BYREF
  DWORD dwHighDateTime; // [rsp+80h] [rbp-59h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-51h] BYREF
  void *v31; // [rsp+90h] [rbp-49h] BYREF
  _QWORD v32[2]; // [rsp+98h] [rbp-41h] BYREF
  _QWORD v33[2]; // [rsp+A8h] [rbp-31h] BYREF
  _QWORD v34[2]; // [rsp+B8h] [rbp-21h] BYREF
  _QWORD v35[2]; // [rsp+C8h] [rbp-11h] BYREF
  struct _GUID v36; // [rsp+D8h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_dSq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (_DWORD)a3, a2, (__int64)a3, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&NextIndex, "CSpp::_BuildCommonSnapshotProp", 4050, 1);
  v35[0] = &FileName;
  v8 = 0;
  v34[0] = &FileName;
  v33[0] = &FileName;
  v32[0] = &FileName;
  SystemTimeAsFileTime = 0;
  v23 = 0;
  v35[1] = 0;
  v34[1] = 0;
  v33[1] = 0;
  v32[1] = 0;
  v22 = 0;
  v28 = 0;
  NewState = 0;
  v31 = 0;
  v36 = GUID_NULL;
  if ( !a4 )
  {
    NextIndex = -2147024809;
    v26 = 4066;
    goto LABEL_24;
  }
  NextIndex = 0;
  v25 = 4066;
  IsServerSku = CSpp::_IsServerSku(0);
  NextIndex = IsServerSku;
  v10 = 4068;
  if ( IsServerSku < 0 )
    goto LABEL_7;
  v25 = 4068;
  NextIndex = CSpp::_GetNextIndex(a1, &v23);
  v10 = 4071;
  if ( NextIndex < 0 )
    goto LABEL_7;
  v25 = 4071;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
  dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
  NextIndex = CSpp::_GetCurrentSystemId(a1, &v36);
  v10 = 4077;
  if ( NextIndex < 0 )
    goto LABEL_7;
  v25 = 4077;
  if ( a3 )
  {
    NextIndex = CBsString::Set((CBsString *)v35, a3);
    v10 = 4081;
    if ( NextIndex < 0 )
      goto LABEL_7;
    v25 = 4081;
  }
  NextIndex = CBsString::ExpandEnvironmentStringsW((CBsString *)v32, L"%SystemRoot%\\");
  v10 = 4084;
  if ( NextIndex >= 0 )
  {
    v25 = 4084;
    NextIndex = CSpp::_GetComputerInfo(v12, (struct CBsString *)v34, (struct CBsString *)v33);
    v10 = 4086;
    if ( NextIndex >= 0 )
    {
      v25 = 4086;
      v14 = SxOpenThreadOrProcessToken(v13, &v31);
      v8 = (char *)v31;
      v16 = v14 < 0;
      NextIndex = v14;
      v10 = 4093;
      if ( !v16 )
      {
        v25 = 4093;
        NextIndex = CSpp::_EnableBackupRestorePrivs(v15, v31, &NewState);
        v10 = 4094;
        if ( NextIndex >= 0 )
        {
          v25 = 4094;
          NextIndex = CSpp::_GetPrograms(a1, L"SOFTWARE", &v22, &v28, 0, 0);
          v10 = 4096;
          if ( NextIndex >= 0 )
          {
            v17 = v36;
            v25 = 4096;
            *(_DWORD *)(a4 + 16) = v23;
            *(_DWORD *)(a4 + 28) = dwHighDateTime;
            *(_DWORD *)(a4 + 120) = v22;
            *(_QWORD *)(a4 + 128) = v28;
            *(_DWORD *)(a4 + 32) = a2;
            *(_DWORD *)(a4 + 24) = dwLowDateTime;
            *(struct _GUID *)(a4 + 48) = v17;
            v22 = 0;
            v28 = 0;
            CBsString::Detach((CBsString *)v35, (unsigned __int16 **)(a4 + 40));
            CBsString::Detach((CBsString *)v32, (unsigned __int16 **)(a4 + 64));
            CBsString::Detach((CBsString *)v34, (unsigned __int16 **)(a4 + 72));
            CBsString::Detach((CBsString *)v33, (unsigned __int16 **)(a4 + 80));
            if ( !IsServerSku )
              goto LABEL_21;
            NextIndex = CSpp::_GetEnvironmentVariables(
                          a1,
                          (unsigned int *)(a4 + 136),
                          (struct _SPP_ENVIRONMENT_PROP **)(a4 + 144));
            v10 = 4120;
            if ( NextIndex >= 0 )
            {
              v25 = 4120;
              goto LABEL_21;
            }
          }
        }
      }
    }
  }
LABEL_7:
  v26 = v10;
LABEL_21:
  if ( NewState && (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v8, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    NewState = 0;
  }
LABEL_24:
  Free_StringArray(&v22, (LPVOID *)&v28);
  v18 = NextIndex;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  CBsString::_Release((CBsString *)v32);
  CBsString::_Release((CBsString *)v33);
  CBsString::_Release((CBsString *)v34);
  CBsString::_Release((CBsString *)v35);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&NextIndex, v19, v20);
  return v18;
}

```

## disassembly

```asm
0x18001176c  push    rbp
0x18001176e  push    rbx
0x18001176f  push    rsi
0x180011770  push    rdi
0x180011771  push    r12
0x180011773  push    r13
0x180011775  push    r14
0x180011777  push    r15
0x180011779  lea     rbp, [rsp-1Fh]
0x18001177e  sub     rsp, 0F8h
0x180011785  mov     rax, cs:__security_cookie
0x18001178c  xor     rax, rsp
0x18001178f  mov     [rbp+57h+var_48], rax
0x180011793  mov     rdi, r9
0x180011796  mov     rsi, r8
0x180011799  mov     r12d, edx
0x18001179c  mov     r14, rcx
0x18001179f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117a6  lea     rax, WPP_GLOBAL_Control
0x1800117ad  cmp     rcx, rax
0x1800117b0  jz      short loc_1800117D1
0x1800117b2  test    dword ptr [rcx+1Ch], 20000000h
0x1800117b9  jz      short loc_1800117D1
0x1800117bb  mov     rcx, [rcx+10h]
0x1800117bf  mov     [rsp+130h+ReturnLength], r9
0x1800117c4  mov     r9d, edx
0x1800117c7  mov     [rsp+130h+PreviousState], r8
0x1800117cc  call    WPP_SF_dSq
0x1800117d1  mov     r9d, 1; unsigned __int16
0x1800117d7  lea     rdx, aCsppBuildcommo; "CSpp::_BuildCommonSnapshotProp"
0x1800117de  mov     r8d, 0FD2h; unsigned __int16
0x1800117e4  lea     rcx, [rsp+130h+var_F8]; this
0x1800117e9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800117ee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800117f5  xor     ecx, ecx; this
0x1800117f7  lea     rax, FileName
0x1800117fe  mov     [rbp+57h+var_68], rax
0x180011802  mov     ebx, ecx
0x180011804  mov     [rbp+57h+var_78], rax
0x180011808  mov     [rbp+57h+var_88], rax
0x18001180c  mov     [rbp+57h+var_98], rax
0x180011810  mov     eax, 0FE2h
0x180011815  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180011819  mov     [rsp+130h+var_FC], ecx
0x18001181d  mov     [rbp+57h+var_60], rcx
0x180011821  mov     [rbp+57h+var_70], rcx
0x180011825  mov     [rbp+57h+var_80], rcx
0x180011829  mov     [rbp+57h+var_90], rcx
0x18001182d  mov     [rsp+130h+var_100], ecx
0x180011831  mov     [rbp+57h+var_B8], rcx
0x180011835  mov     [rbp+57h+NewState], rcx
0x180011839  mov     [rbp+57h+var_A0], rcx
0x18001183d  movdqu  xmmword ptr [rbp+57h+var_58.Data1], xmm0
0x180011842  test    rdi, rdi
0x180011845  jnz     short loc_180011859
0x180011847  mov     [rsp+130h+var_F8], 80070057h
0x18001184f  mov     [rsp+130h+var_F2], ax
0x180011854  jmp     loc_180011AB2
0x180011859  mov     [rsp+130h+var_F8], ecx
0x18001185d  mov     [rsp+130h+var_F4], ax
0x180011862  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x180011867  mov     r15d, eax
0x18001186a  mov     [rsp+130h+var_F8], eax
0x18001186e  test    eax, eax
0x180011870  mov     eax, 0FE4h
0x180011875  jns     short loc_180011881
0x180011877  mov     [rsp+130h+var_F2], ax
0x18001187c  jmp     loc_180011A6D
0x180011881  lea     rdx, [rsp+130h+var_FC]; unsigned int *
0x180011886  mov     [rsp+130h+var_F4], ax
0x18001188b  mov     rcx, r14; this
0x18001188e  call    ?_GetNextIndex@CSpp@@AEAAJPEAK@Z; CSpp::_GetNextIndex(ulong *)
0x180011893  mov     [rsp+130h+var_F8], eax
0x180011897  test    eax, eax
0x180011899  mov     eax, 0FE7h
0x18001189e  js      short loc_180011877
0x1800118a0  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800118a4  mov     [rsp+130h+var_F4], ax
0x1800118a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800118af  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x1800118b2  lea     rdx, [rbp+57h+var_58]; struct _GUID *
0x1800118b6  mov     r13d, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800118ba  mov     rcx, r14; this
0x1800118bd  mov     [rbp+57h+var_B0], eax
0x1800118c0  call    ?_GetCurrentSystemId@CSpp@@AEAAJPEAU_GUID@@@Z; CSpp::_GetCurrentSystemId(_GUID *)
0x1800118c5  mov     [rsp+130h+var_F8], eax
0x1800118c9  test    eax, eax
0x1800118cb  mov     eax, 0FEDh
0x1800118d0  js      short loc_180011877
0x1800118d2  mov     [rsp+130h+var_F4], ax
0x1800118d7  test    rsi, rsi
0x1800118da  jz      short loc_1800118FA
0x1800118dc  mov     rdx, rsi; unsigned __int16 *
0x1800118df  lea     rcx, [rbp+57h+var_68]; this
0x1800118e3  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800118e8  mov     [rsp+130h+var_F8], eax
0x1800118ec  test    eax, eax
0x1800118ee  mov     eax, 0FF1h
0x1800118f3  js      short loc_180011877
0x1800118f5  mov     [rsp+130h+var_F4], ax
0x1800118fa  lea     rdx, aSystemroot; "%SystemRoot%\\"
0x180011901  lea     rcx, [rbp+57h+var_98]; this
0x180011905  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18001190a  mov     [rsp+130h+var_F8], eax
0x18001190e  test    eax, eax
0x180011910  mov     eax, 0FF4h
0x180011915  js      loc_180011877
0x18001191b  lea     r8, [rbp+57h+var_88]; struct CBsString *
0x18001191f  mov     [rsp+130h+var_F4], ax
0x180011924  lea     rdx, [rbp+57h+var_78]; struct CBsString *
0x180011928  call    ?_GetComputerInfo@CSpp@@AEAAJPEAVCBsString@@0@Z; CSpp::_GetComputerInfo(CBsString *,CBsString *)
0x18001192d  mov     [rsp+130h+var_F8], eax
0x180011931  test    eax, eax
0x180011933  mov     eax, 0FF6h
0x180011938  js      loc_180011877
0x18001193e  lea     rdx, [rbp+57h+var_A0]; void **
0x180011942  mov     [rsp+130h+var_F4], ax
0x180011947  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18001194c  mov     rbx, [rbp+57h+var_A0]
0x180011950  test    eax, eax
0x180011952  mov     [rsp+130h+var_F8], eax
0x180011956  mov     eax, 0FFDh
0x18001195b  js      loc_180011877
0x180011961  lea     r8, [rbp+57h+NewState]; struct _TOKEN_PRIVILEGES **
0x180011965  mov     [rsp+130h+var_F4], ax
0x18001196a  mov     rdx, rbx; void *
0x18001196d  call    ?_EnableBackupRestorePrivs@CSpp@@AEAAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; CSpp::_EnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x180011972  mov     [rsp+130h+var_F8], eax
0x180011976  test    eax, eax
0x180011978  mov     eax, 0FFEh
0x18001197d  js      loc_180011877
0x180011983  mov     [rsp+130h+ReturnLength], 0; unsigned __int16 ***
0x18001198c  lea     r9, [rbp+57h+var_B8]; unsigned __int16 ***
0x180011990  lea     r8, [rsp+130h+var_100]; unsigned int *
0x180011995  mov     [rsp+130h+PreviousState], 0; unsigned int *
0x18001199e  lea     rdx, aSoftware; "SOFTWARE"
0x1800119a5  mov     [rsp+130h+var_F4], ax
0x1800119aa  mov     rcx, r14; this
0x1800119ad  call    ?_GetPrograms@CSpp@@AEAAJPEBGPEAKPEAPEAPEAG12@Z; CSpp::_GetPrograms(ushort const *,ulong *,ushort * * *,ulong *,ushort * * *)
0x1800119b2  mov     [rsp+130h+var_F8], eax
0x1800119b6  test    eax, eax
0x1800119b8  mov     eax, 1000h
0x1800119bd  js      loc_180011877
0x1800119c3  movups  xmm0, xmmword ptr [rbp+57h+var_58.Data1]
0x1800119c7  mov     [rsp+130h+var_F4], ax
0x1800119cc  lea     rdx, [rdi+28h]; unsigned __int16 **
0x1800119d0  mov     eax, [rsp+130h+var_FC]
0x1800119d4  lea     rcx, [rbp+57h+var_68]; this
0x1800119d8  mov     [rdi+10h], eax
0x1800119db  mov     eax, [rbp+57h+var_B0]
0x1800119de  mov     [rdi+1Ch], eax
0x1800119e1  mov     eax, [rsp+130h+var_100]
0x1800119e5  mov     [rdi+78h], eax
0x1800119e8  mov     rax, [rbp+57h+var_B8]
0x1800119ec  mov     [rdi+80h], rax
0x1800119f3  mov     [rdi+20h], r12d
0x1800119f7  mov     [rdi+18h], r13d
0x1800119fb  movdqu  xmmword ptr [rdi+30h], xmm0
0x180011a00  mov     [rsp+130h+var_100], 0
0x180011a08  mov     [rbp+57h+var_B8], 0
0x180011a10  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180011a15  lea     rdx, [rdi+40h]; unsigned __int16 **
0x180011a19  lea     rcx, [rbp+57h+var_98]; this
0x180011a1d  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180011a22  lea     rdx, [rdi+48h]; unsigned __int16 **
0x180011a26  lea     rcx, [rbp+57h+var_78]; this
0x180011a2a  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180011a2f  lea     rdx, [rdi+50h]; unsigned __int16 **
0x180011a33  lea     rcx, [rbp+57h+var_88]; this
0x180011a37  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x180011a3c  test    r15d, r15d
0x180011a3f  jz      short loc_180011A6D
0x180011a41  lea     r8, [rdi+90h]; struct _SPP_ENVIRONMENT_PROP **
0x180011a48  mov     rcx, r14; this
0x180011a4b  lea     rdx, [rdi+88h]; unsigned int *
0x180011a52  call    ?_GetEnvironmentVariables@CSpp@@AEAAJPEAKPEAPEAU_SPP_ENVIRONMENT_PROP@@@Z; CSpp::_GetEnvironmentVariables(ulong *,_SPP_ENVIRONMENT_PROP * *)
0x180011a57  mov     [rsp+130h+var_F8], eax
0x180011a5b  test    eax, eax
0x180011a5d  mov     eax, 1018h
0x180011a62  js      loc_180011877
0x180011a68  mov     [rsp+130h+var_F4], ax
0x180011a6d  mov     r8, [rbp+57h+NewState]; NewState
0x180011a71  test    r8, r8
0x180011a74  jz      short loc_180011AB2
0x180011a76  lea     rax, [rbx-1]
0x180011a7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011a7e  ja      short loc_180011AB2
0x180011a80  mov     [rsp+130h+ReturnLength], 0; ReturnLength
0x180011a89  xor     r9d, r9d; BufferLength
0x180011a8c  xor     edx, edx; DisableAllPrivileges
0x180011a8e  mov     [rsp+130h+PreviousState], 0; PreviousState
0x180011a97  mov     rcx, rbx; TokenHandle
0x180011a9a  call    cs:__imp_AdjustTokenPrivileges
0x180011aa0  mov     rcx, [rbp+57h+NewState]; pv
0x180011aa4  call    cs:__imp_CoTaskMemFree
0x180011aaa  mov     [rbp+57h+NewState], 0
0x180011ab2  lea     rdx, [rbp+57h+var_B8]; unsigned __int16 ***
0x180011ab6  lea     rcx, [rsp+130h+var_100]; unsigned int *
0x180011abb  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x180011ac0  mov     edi, [rsp+130h+var_F8]
0x180011ac4  lea     rax, [rbx-1]
0x180011ac8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011acc  ja      short loc_180011AD7
0x180011ace  mov     rcx, rbx; hObject
0x180011ad1  call    cs:__imp_CloseHandle
0x180011ad7  lea     rcx, [rbp+57h+var_98]; this
0x180011adb  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180011ae0  lea     rcx, [rbp+57h+var_88]; this
0x180011ae4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180011ae9  lea     rcx, [rbp+57h+var_78]; this
0x180011aed  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180011af2  lea     rcx, [rbp+57h+var_68]; this
0x180011af6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180011afb  lea     rcx, [rsp+130h+var_F8]; this
0x180011b00  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011b05  mov     eax, edi
0x180011b07  mov     rcx, [rbp+57h+var_48]
0x180011b0b  xor     rcx, rsp; StackCookie
0x180011b0e  call    __security_check_cookie
0x180011b13  add     rsp, 0F8h
0x180011b1a  pop     r15
0x180011b1c  pop     r14
0x180011b1e  pop     r13
0x180011b20  pop     r12
0x180011b22  pop     rdi
0x180011b23  pop     rsi
0x180011b24  pop     rbx
0x180011b25  pop     rbp
0x180011b26  retn
```
