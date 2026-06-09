# CVssHardwareProviderWrapper::SaveData(void)

- ea: `0x140079510`
- end: `0x140079a3c`
- name: `?SaveData@CVssHardwareProviderWrapper@@AEAAXXZ`
- size: `1324`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1400b1e18`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x140031730`
- `0x14003c174`
- `0x14003fc04`
- `0x14003fcac`
- `0x14005eb64`
- `0x14005f190`
- `0x140073a40`
- `0x140079510`
- `0x14007b544`
- `0x140091560`
- `0x1400921dc`
- `0x1400b1bd4`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400796bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007992a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400796bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007992a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400796ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14007987c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14007990e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400796ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14007987c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14007990e`
- `OLEAUT32!__imp_SysFreeString` at `0x140079997`
- `OLEAUT32!__imp_SysFreeString` at `0x140079997`

## string_xrefs

- `0x140079714`: `WriteFile`
- `0x1400798dd`: `WriteFile`
- `0x14007997a`: `WriteFile`
- `0x140079814`: `IVssSnapshotSetDescription::SaveAsXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVssHardwareProviderWrapper::SaveData(CVssHardwareProviderWrapper *this)
{
  CVssHardwareProviderWrapper *v1; // rdi
  HANDLE v2; // rsi
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  signed int LastError; // eax
  __int64 *v6; // rbx
  __int64 v7; // rax
  signed int v8; // eax
  signed int v9; // eax
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  CVssHardwareProviderWrapper *v12; // rcx
  CVssHardwareProviderWrapper *v13; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  LPCVOID lpBuffer[2]; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v17; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v18; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[120]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+E8h] [rbp-18h]
  CVssHardwareProviderWrapper *v25; // [rsp+F0h] [rbp-10h]
  _QWORD v26[3]; // [rsp+F8h] [rbp-8h] BYREF
  LPVOID v27; // [rsp+110h] [rbp+10h] BYREF
  signed int v28; // [rsp+118h] [rbp+18h]
  int Buffer; // [rsp+180h] [rbp+80h] BYREF
  __int64 v30; // [rsp+184h] [rbp+84h]
  _OWORD v31[2]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v32[328]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v33[328]; // [rsp+440h] [rbp+340h] BYREF

  v1 = this;
  v25 = this;
  v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
  v18 = L"CVssHardwareProviderWrapper::SaveData";
  v19 = L"CORHWDBC";
  v20 = 593;
  v21 = 1;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v27, (__int64)&v17, 0);
  v2 = CVssHardwareProviderWrapper::OpenAlternateDatabase(v1);
  lpBuffer[0] = v2;
  v26[0] = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v26[1] = v2;
  NumberOfBytesWritten = 0;
  Buffer = -1655705611;
  v30 = 1;
  v3 = (_QWORD *)*((_QWORD *)v1 + 22);
  if ( v3 )
  {
    do
    {
      v4 = v3[3];
      v15 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 80LL))(v4, &v15);
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v18 = L"CVssHardwareProviderWrapper::SaveData";
      v19 = L"CORHWDBC";
      v20 = 613;
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::CheckForError(&v27, &v17, L"IVssSnapshotSetDescription::GetContext");
      if ( (v15 & 8) != 0 )
        ++HIDWORD(v30);
      v3 = (_QWORD *)*v3;
    }
    while ( v3 );
    v1 = v25;
    v2 = (HANDLE)lpBuffer[0];
  }
  if ( !WriteFile(v2, &Buffer, 0xCu, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 12 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v28 = LastError;
    v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
    v18 = L"CVssHardwareProviderWrapper::SaveData";
    v19 = L"CORHWDBC";
    v20 = 625;
    v21 = 1;
    v22 = 255;
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::CheckForError(&v27, &v17, L"WriteFile");
  }
  v6 = (__int64 *)*((_QWORD *)v1 + 22);
  if ( v6 )
  {
    do
    {
      v15 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6[3] + 80LL))(v6[3], &v15);
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
      v18 = L"CVssHardwareProviderWrapper::SaveData";
      v19 = L"CORHWDBC";
      v20 = 635;
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::CheckForError(&v27, &v17, L"IVssSnapshotSetDescription::GetContext");
      if ( (v15 & 8) != 0 )
      {
        lpBuffer[0] = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, LPCVOID *))(*(_QWORD *)v6[3] + 24LL))(v6[3], lpBuffer);
        v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
        v18 = L"CVssHardwareProviderWrapper::SaveData";
        v19 = L"CORHWDBC";
        v20 = 649;
        v21 = 1;
        v22 = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::CheckForErrorInternal(&v27, &v17, L"IVssSnapshotSetDescription::SaveAsXML");
        memset(v31, 0, 20);
        v7 = -1;
        do
          ++v7;
        while ( *((_WORD *)lpBuffer[0] + v7) );
        LODWORD(v31[0]) = v7 + 1;
        *(_OWORD *)((char *)v31 + 4) = *(_OWORD *)(v6 + 1);
        if ( !WriteFile(v2, v31, 0x14u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 20 )
        {
          v8 = GetLastError();
          if ( v8 > 0 )
            v8 = (unsigned __int16)v8 | 0x80070000;
          v28 = v8;
          v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
          v18 = L"CVssHardwareProviderWrapper::SaveData";
          v19 = L"CORHWDBC";
          v20 = 662;
          v21 = 1;
          v22 = 255;
          v24 = 0x1000000;
          memset_0(v23, 0, sizeof(v23));
          CVssFunctionTracer::CheckForError(&v27, &v17, L"WriteFile");
        }
        if ( !WriteFile(v2, lpBuffer[0], 2 * LODWORD(v31[0]), &NumberOfBytesWritten, 0)
          || NumberOfBytesWritten != 2LL * LODWORD(v31[0]) )
        {
          v9 = GetLastError();
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          v28 = v9;
          v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwwrpdb.cxx";
          v18 = L"CVssHardwareProviderWrapper::SaveData";
          v19 = L"CORHWDBC";
          v20 = 670;
          v21 = 1;
          v22 = 255;
          v24 = 0x1000000;
          memset_0(v23, 0, sizeof(v23));
          CVssFunctionTracer::CheckForError(&v27, &v17, L"WriteFile");
        }
        v6 = (__int64 *)*v6;
        SysFreeString((BSTR)lpBuffer[0]);
      }
      else
      {
        v6 = (__int64 *)*v6;
      }
    }
    while ( v6 );
    v1 = v25;
  }
  CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(v26);
  CVssHardwareProviderWrapper::GetDatabasePath(v1, 0, v32, v10);
  CVssHardwareProviderWrapper::GetDatabasePath(v1, 1, v33, v11);
  if ( CVssHardwareProviderWrapper::DoesPathExists(v12, v32) )
    CVssHardwareProviderWrapper::DeleteDatabase(v13, v32);
  CVssHardwareProviderWrapper::MoveDatabase(v13, v33, v32);
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(v26);
  CVssFunctionTracer::~CVssFunctionTracer(&v27);
}

```

## disassembly

```asm
0x140079510  push    rbp
0x140079512  push    rbx
0x140079513  push    rsi
0x140079514  push    rdi
0x140079515  push    r12
0x140079517  push    r13
0x140079519  push    r14
0x14007951b  push    r15
0x14007951d  lea     rbp, [rsp-5E8h]
0x140079525  sub     rsp, 6E8h
0x14007952c  mov     rax, cs:__security_cookie
0x140079533  xor     rax, rsp
0x140079536  mov     [rbp+620h+var_50], rax
0x14007953d  mov     rdi, rcx
0x140079540  mov     [rbp+620h+var_630], rcx
0x140079544  lea     r12, aBaseStorVssMod_20; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14007954b  mov     [rsp+720h+var_6D8], r12
0x140079550  lea     r13, aCvsshardwarepr_198; "CVssHardwareProviderWrapper::SaveData"
0x140079557  mov     [rsp+720h+var_6D0], r13
0x14007955c  lea     rax, aCorhwdbc; "CORHWDBC"
0x140079563  mov     [rsp+720h+var_6C8], rax
0x140079568  mov     [rsp+720h+var_6C0], 251h
0x140079570  mov     r15d, 1
0x140079576  mov     [rsp+720h+var_6BC], r15d
0x14007957b  mov     [rsp+720h+var_6B8], 0FFh
0x140079583  xor     r14d, r14d
0x140079586  mov     [rbp+620h+var_638], 1000000h
0x14007958d  xor     edx, edx; Val
0x14007958f  lea     r8d, [r15+77h]; Size
0x140079593  lea     rcx, [rsp+720h+var_6B0]; void *
0x140079598  call    memset_0
0x14007959d  xor     r8d, r8d
0x1400795a0  lea     rdx, [rsp+720h+var_6D8]
0x1400795a5  lea     rcx, [rbp+620h+var_610]
0x1400795a9  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400795ae  nop
0x1400795af  mov     rcx, rdi; this
0x1400795b2  call    ?OpenAlternateDatabase@CVssHardwareProviderWrapper@@AEAAPEAXXZ; CVssHardwareProviderWrapper::OpenAlternateDatabase(void)
0x1400795b7  mov     rsi, rax
0x1400795ba  mov     [rsp+720h+lpBuffer], rax
0x1400795bf  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1400795c6  mov     [rbp+620h+var_628], rax
0x1400795ca  mov     [rbp+620h+var_620], rsi
0x1400795ce  mov     [rsp+720h+NumberOfBytesWritten], r14d
0x1400795d3  mov     [rbp+620h+Buffer], 9D4FEFF5h
0x1400795dd  mov     [rbp+620h+var_59C], 1
0x1400795e8  mov     rbx, [rdi+0B0h]
0x1400795ef  test    rbx, rbx
0x1400795f2  jz      loc_140079692
0x1400795f8  lea     rdi, aCorhwdbc; "CORHWDBC"
0x1400795ff  lea     rsi, [rsp+720h+var_6B0]
0x140079604  mov     rcx, [rbx+18h]
0x140079608  mov     [rsp+720h+var_6EC], r14d
0x14007960d  mov     rax, [rcx]
0x140079610  lea     rdx, [rsp+720h+var_6EC]
0x140079615  mov     rax, [rax+50h]
0x140079619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007961e  mov     [rbp+620h+var_608], eax
0x140079621  mov     [rsp+720h+var_6D8], r12
0x140079626  mov     [rsp+720h+var_6D0], r13
0x14007962b  mov     [rsp+720h+var_6C8], rdi
0x140079630  mov     [rsp+720h+var_6C0], 265h
0x140079638  mov     [rsp+720h+var_6BC], r15d
0x14007963d  mov     [rsp+720h+var_6B8], 0FFh
0x140079645  mov     [rbp+620h+var_638], 1000000h
0x14007964c  xor     edx, edx; Val
0x14007964e  lea     r8d, [rdx+78h]; Size
0x140079652  mov     rcx, rsi; void *
0x140079655  call    memset_0
0x14007965a  lea     r8, aIvsssnapshotse_7; "IVssSnapshotSetDescription::GetContext"
0x140079661  lea     rdx, [rsp+720h+var_6D8]
0x140079666  lea     rcx, [rbp+620h+var_610]
0x14007966a  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x14007966f  test    byte ptr [rsp+720h+var_6EC], 8
0x140079674  jz      short loc_14007967D
0x140079676  add     dword ptr [rbp+620h+var_59C+4], r15d
0x14007967d  mov     rbx, [rbx]
0x140079680  test    rbx, rbx
0x140079683  jnz     loc_140079604
0x140079689  mov     rdi, [rbp+620h+var_630]
0x14007968d  mov     rsi, [rsp+720h+lpBuffer]
0x140079692  mov     [rsp+720h+lpOverlapped], r14; lpOverlapped
0x140079697  lea     r9, [rsp+720h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14007969c  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1400796a2  lea     rdx, [rbp+620h+Buffer]; lpBuffer
0x1400796a9  mov     rcx, rsi; hFile
0x1400796ac  call    cs:__imp_WriteFile
0x1400796b2  test    eax, eax
0x1400796b4  jz      short loc_1400796BD
0x1400796b6  cmp     [rsp+720h+NumberOfBytesWritten], 0Ch
0x1400796bb  jz      short loc_140079729
0x1400796bd  call    cs:__imp_GetLastError
0x1400796c3  test    eax, eax
0x1400796c5  jle     short loc_1400796CF
0x1400796c7  movzx   eax, ax
0x1400796ca  or      eax, 80070000h
0x1400796cf  mov     [rbp+620h+var_608], eax
0x1400796d2  mov     [rsp+720h+var_6D8], r12
0x1400796d7  mov     [rsp+720h+var_6D0], r13
0x1400796dc  lea     rax, aCorhwdbc; "CORHWDBC"
0x1400796e3  mov     [rsp+720h+var_6C8], rax
0x1400796e8  mov     [rsp+720h+var_6C0], 271h
0x1400796f0  mov     [rsp+720h+var_6BC], r15d
0x1400796f5  mov     [rsp+720h+var_6B8], 0FFh
0x1400796fd  mov     [rbp+620h+var_638], 1000000h
0x140079704  xor     edx, edx; Val
0x140079706  lea     r8d, [rdx+78h]; Size
0x14007970a  lea     rcx, [rsp+720h+var_6B0]; void *
0x14007970f  call    memset_0
0x140079714  lea     r8, aWritefile; "WriteFile"
0x14007971b  lea     rdx, [rsp+720h+var_6D8]
0x140079720  lea     rcx, [rbp+620h+var_610]
0x140079724  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x140079729  mov     rbx, [rdi+0B0h]
0x140079730  test    rbx, rbx
0x140079733  jz      loc_1400799AA
0x140079739  lea     rdi, aCorhwdbc; "CORHWDBC"
0x140079740  mov     [rsp+720h+var_6EC], r14d
0x140079745  mov     rcx, [rbx+18h]
0x140079749  mov     rax, [rcx]
0x14007974c  lea     rdx, [rsp+720h+var_6EC]
0x140079751  mov     rax, [rax+50h]
0x140079755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007975a  mov     [rbp+620h+var_608], eax
0x14007975d  mov     [rsp+720h+var_6D8], r12
0x140079762  mov     [rsp+720h+var_6D0], r13
0x140079767  mov     [rsp+720h+var_6C8], rdi
0x14007976c  mov     [rsp+720h+var_6C0], 27Bh
0x140079774  mov     [rsp+720h+var_6BC], r15d
0x140079779  mov     [rsp+720h+var_6B8], 0FFh
0x140079781  mov     [rbp+620h+var_638], 1000000h
0x140079788  xor     edx, edx; Val
0x14007978a  lea     r8d, [rdx+78h]; Size
0x14007978e  lea     rcx, [rsp+720h+var_6B0]; void *
0x140079793  call    memset_0
0x140079798  lea     r8, aIvsssnapshotse_7; "IVssSnapshotSetDescription::GetContext"
0x14007979f  lea     rdx, [rsp+720h+var_6D8]
0x1400797a4  lea     rcx, [rbp+620h+var_610]
0x1400797a8  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x1400797ad  test    byte ptr [rsp+720h+var_6EC], 8
0x1400797b2  jnz     short loc_1400797BC
0x1400797b4  mov     rbx, [rbx]
0x1400797b7  jmp     loc_14007999D
0x1400797bc  mov     [rsp+720h+lpBuffer], r14
0x1400797c1  mov     rcx, [rbx+18h]
0x1400797c5  mov     rax, [rcx]
0x1400797c8  lea     rdx, [rsp+720h+lpBuffer]
0x1400797cd  mov     rax, [rax+18h]
0x1400797d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400797d6  mov     [rbp+620h+var_608], eax
0x1400797d9  mov     [rsp+720h+var_6D8], r12
0x1400797de  mov     [rsp+720h+var_6D0], r13
0x1400797e3  mov     [rsp+720h+var_6C8], rdi
0x1400797e8  mov     [rsp+720h+var_6C0], 289h
0x1400797f0  mov     [rsp+720h+var_6BC], r15d
0x1400797f5  mov     [rsp+720h+var_6B8], 0FFh
0x1400797fd  mov     [rbp+620h+var_638], 1000000h
0x140079804  xor     edx, edx; Val
0x140079806  lea     r8d, [rdx+78h]; Size
0x14007980a  lea     rcx, [rsp+720h+var_6B0]; void *
0x14007980f  call    memset_0
0x140079814  lea     r8, aIvsssnapshotse_4; "IVssSnapshotSetDescription::SaveAsXML"
0x14007981b  lea     rdx, [rsp+720h+var_6D8]
0x140079820  lea     rcx, [rbp+620h+var_610]
0x140079824  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140079829  xorps   xmm0, xmm0
0x14007982c  xor     eax, eax
0x14007982e  movups  [rbp+620h+var_590], xmm0
0x140079835  mov     [rbp+620h+var_580], eax
0x14007983b  mov     rcx, [rsp+720h+lpBuffer]
0x140079840  or      rax, 0FFFFFFFFFFFFFFFFh
0x140079844  inc     rax
0x140079847  cmp     [rcx+rax*2], r14w
0x14007984c  jnz     short loc_140079844
0x14007984e  inc     eax
0x140079850  mov     dword ptr [rbp+620h+var_590], eax
0x140079856  movups  xmm0, xmmword ptr [rbx+8]
0x14007985a  movdqu  [rbp+620h+var_590+4], xmm0
0x140079862  mov     [rsp+720h+lpOverlapped], r14; lpOverlapped
0x140079867  lea     r9, [rsp+720h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14007986c  mov     r8d, 14h; nNumberOfBytesToWrite
0x140079872  lea     rdx, [rbp+620h+var_590]; lpBuffer
0x140079879  mov     rcx, rsi; hFile
0x14007987c  call    cs:__imp_WriteFile
0x140079882  test    eax, eax
0x140079884  jz      short loc_14007988D
0x140079886  cmp     [rsp+720h+NumberOfBytesWritten], 14h
0x14007988b  jz      short loc_1400798F2
0x14007988d  call    cs:__imp_GetLastError
0x140079893  test    eax, eax
0x140079895  jle     short loc_14007989F
0x140079897  movzx   eax, ax
0x14007989a  or      eax, 80070000h
0x14007989f  mov     [rbp+620h+var_608], eax
0x1400798a2  mov     [rsp+720h+var_6D8], r12
0x1400798a7  mov     [rsp+720h+var_6D0], r13
0x1400798ac  mov     [rsp+720h+var_6C8], rdi
0x1400798b1  mov     [rsp+720h+var_6C0], 296h
0x1400798b9  mov     [rsp+720h+var_6BC], r15d
0x1400798be  mov     [rsp+720h+var_6B8], 0FFh
0x1400798c6  mov     [rbp+620h+var_638], 1000000h
0x1400798cd  xor     edx, edx; Val
0x1400798cf  lea     r8d, [rdx+78h]; Size
0x1400798d3  lea     rcx, [rsp+720h+var_6B0]; void *
0x1400798d8  call    memset_0
0x1400798dd  lea     r8, aWritefile; "WriteFile"
0x1400798e4  lea     rdx, [rsp+720h+var_6D8]
0x1400798e9  lea     rcx, [rbp+620h+var_610]
0x1400798ed  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x1400798f2  mov     r8d, dword ptr [rbp+620h+var_590]
0x1400798f9  add     r8d, r8d; nNumberOfBytesToWrite
0x1400798fc  mov     [rsp+720h+lpOverlapped], r14; lpOverlapped
0x140079901  lea     r9, [rsp+720h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140079906  mov     rdx, [rsp+720h+lpBuffer]; lpBuffer
0x14007990b  mov     rcx, rsi; hFile
0x14007990e  call    cs:__imp_WriteFile
0x140079914  test    eax, eax
0x140079916  jz      short loc_14007992A
0x140079918  mov     ecx, dword ptr [rbp+620h+var_590]
0x14007991e  add     rcx, rcx
0x140079921  mov     eax, [rsp+720h+NumberOfBytesWritten]
0x140079925  cmp     rax, rcx
0x140079928  jz      short loc_14007998F
0x14007992a  call    cs:__imp_GetLastError
0x140079930  test    eax, eax
0x140079932  jle     short loc_14007993C
0x140079934  movzx   eax, ax
0x140079937  or      eax, 80070000h
0x14007993c  mov     [rbp+620h+var_608], eax
0x14007993f  mov     [rsp+720h+var_6D8], r12
0x140079944  mov     [rsp+720h+var_6D0], r13
0x140079949  mov     [rsp+720h+var_6C8], rdi
0x14007994e  mov     [rsp+720h+var_6C0], 29Eh
0x140079956  mov     [rsp+720h+var_6BC], r15d
0x14007995b  mov     [rsp+720h+var_6B8], 0FFh
0x140079963  mov     [rbp+620h+var_638], 1000000h
0x14007996a  xor     edx, edx; Val
0x14007996c  lea     r8d, [rdx+78h]; Size
0x140079970  lea     rcx, [rsp+720h+var_6B0]; void *
0x140079975  call    memset_0
0x14007997a  lea     r8, aWritefile; "WriteFile"
0x140079981  lea     rdx, [rsp+720h+var_6D8]
0x140079986  lea     rcx, [rbp+620h+var_610]
0x14007998a  call    ?CheckForError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForError(CVssDebugInfo,ushort const *)
0x14007998f  mov     rbx, [rbx]
0x140079992  mov     rcx, [rsp+720h+lpBuffer]; bstrString
0x140079997  call    cs:__imp_SysFreeString
0x14007999d  test    rbx, rbx
0x1400799a0  jnz     loc_140079740
0x1400799a6  mov     rdi, [rbp+620h+var_630]
0x1400799aa  lea     rcx, [rbp+620h+var_628]
0x1400799ae  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x1400799b3  lea     r8, [rbp+620h+var_570]; unsigned __int16 *
0x1400799ba  xor     edx, edx; bool
0x1400799bc  mov     rcx, rdi; this
0x1400799bf  call    ?GetDatabasePath@CVssHardwareProviderWrapper@@AEAAX_NPEAGK@Z; CVssHardwareProviderWrapper::GetDatabasePath(bool,ushort *,ulong)
0x1400799c4  lea     r8, [rbp+620h+var_2E0]; unsigned __int16 *
0x1400799cb  mov     dl, r15b; bool
0x1400799ce  mov     rcx, rdi; this
0x1400799d1  call    ?GetDatabasePath@CVssHardwareProviderWrapper@@AEAAX_NPEAGK@Z; CVssHardwareProviderWrapper::GetDatabasePath(bool,ushort *,ulong)
0x1400799d6  lea     rdx, [rbp+620h+var_570]; unsigned __int16 *
0x1400799dd  call    ?DoesPathExists@CVssHardwareProviderWrapper@@AEAA_NPEAG@Z; CVssHardwareProviderWrapper::DoesPathExists(ushort *)
0x1400799e2  test    al, al
0x1400799e4  jz      short loc_1400799F2
0x1400799e6  lea     rdx, [rbp+620h+var_570]; unsigned __int16 *
0x1400799ed  call    ?DeleteDatabase@CVssHardwareProviderWrapper@@AEAAXPEAG@Z; CVssHardwareProviderWrapper::DeleteDatabase(ushort *)
0x1400799f2  lea     r8, [rbp+620h+var_570]; unsigned __int16 *
0x1400799f9  lea     rdx, [rbp+620h+var_2E0]; unsigned __int16 *
0x140079a00  call    ?MoveDatabase@CVssHardwareProviderWrapper@@AEAAXPEAG0@Z; CVssHardwareProviderWrapper::MoveDatabase(ushort *,ushort *)
0x140079a05  nop
0x140079a06  lea     rcx, [rbp+620h+var_628]
0x140079a0a  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x140079a0f  nop
0x140079a10  lea     rcx, [rbp+620h+var_610]; this
0x140079a14  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140079a19  mov     rcx, [rbp+620h+var_50]
0x140079a20  xor     rcx, rsp; StackCookie
0x140079a23  call    __security_check_cookie
0x140079a28  add     rsp, 6E8h
0x140079a2f  pop     r15
0x140079a31  pop     r14
0x140079a33  pop     r13
0x140079a35  pop     r12
0x140079a37  pop     rdi
0x140079a38  pop     rsi
0x140079a39  pop     rbx
0x140079a3a  pop     rbp
0x140079a3b  retn
```
