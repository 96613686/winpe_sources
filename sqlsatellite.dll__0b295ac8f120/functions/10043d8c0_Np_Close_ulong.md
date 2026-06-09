# Np::Close(ulong)

- ea: `0x10043d8c0`
- end: `0x10043dd49`
- name: `?Close@Np@@UEAAKK@Z`
- size: `1161`
- prototype: `unsigned int __fastcall(Np *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x100405270`
- `0x100405390`
- `0x10041f180`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10043d8c0`
- `0x10045a1b0`

## import_xrefs

- `KERNEL32!DisconnectNamedPipe` at `0x10043da48`
- `KERNEL32!DisconnectNamedPipe` at `0x10043da48`
- `KERNEL32!WaitForSingleObject` at `0x10043da8c`
- `KERNEL32!WaitForSingleObject` at `0x10043daea`
- `KERNEL32!WaitForSingleObject` at `0x10043dc24`
- `KERNEL32!WaitForSingleObject` at `0x10043da8c`
- `KERNEL32!WaitForSingleObject` at `0x10043daea`
- `KERNEL32!WaitForSingleObject` at `0x10043dc24`
- `KERNEL32!GetLastError` at `0x10043daa5`
- `KERNEL32!GetLastError` at `0x10043dc64`
- `KERNEL32!GetLastError` at `0x10043dcbe`
- `KERNEL32!GetLastError` at `0x10043daa5`
- `KERNEL32!GetLastError` at `0x10043dc64`
- `KERNEL32!GetLastError` at `0x10043dcbe`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043d9c2`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043db9d`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043d9c2`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043db9d`
- `sqldk!SystemThread_TlsIndex` at `0x10043d982`
- `sqldk!SystemThread_TlsIndex` at `0x10043d9d7`
- `sqldk!SystemThread_TlsIndex` at `0x10043db5e`
- `sqldk!SystemThread_TlsIndex` at `0x10043dbb2`
- `sqldk!SystemThread_TlsOffset` at `0x10043d98b`
- `sqldk!SystemThread_TlsOffset` at `0x10043d9e0`
- `sqldk!SystemThread_TlsOffset` at `0x10043db67`
- `sqldk!SystemThread_TlsOffset` at `0x10043dbbb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d9a4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d9fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043db80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043dbd6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d9a4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043d9fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043db80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043dbd6`

## string_xrefs

- `0x10043d8ea`: `sql\common\dk\sni\src\np.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Np::Close(Np *this)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rdx
  bool v7; // al
  const wchar_t *v8; // r9
  bool v9; // di
  __int64 v10; // rcx
  DWORD LastError; // eax
  DWORD v12; // eax
  DWORD v13; // edi
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rdx
  DWORD v19; // eax
  DWORD v20; // edi
  DWORD v21; // eax
  DWORD v22; // eax
  __int64 v24; // [rsp+28h] [rbp-E0h]
  __int64 v25; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C8h]
  int v27; // [rsp+48h] [rbp-C0h] BYREF
  int v28; // [rsp+4Ch] [rbp-BCh]
  __int64 v29; // [rsp+50h] [rbp-B8h]
  _QWORD v30[6]; // [rsp+58h] [rbp-B0h] BYREF
  bool v31; // [rsp+88h] [rbp-80h]
  int v32; // [rsp+98h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-68h]
  int v34; // [rsp+A8h] [rbp-60h] BYREF
  int v35; // [rsp+ACh] [rbp-5Ch]
  __int64 v36; // [rsp+B0h] [rbp-58h]
  int v37; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-40h]
  __int64 v40; // [rsp+D0h] [rbp-38h]
  __int64 v41; // [rsp+D8h] [rbp-30h]
  bool v42; // [rsp+E8h] [rbp-20h]
  __int64 v43; // [rsp+F8h] [rbp-10h]
  const char *v44; // [rsp+100h] [rbp-8h]
  const char *v45; // [rsp+108h] [rbp+0h]
  int v46; // [rsp+110h] [rbp+8h]

  v43 = -2;
  v44 = "sql\\common\\dk\\sni\\src\\np.cpp";
  v45 = "Np::Close";
  v46 = 2890;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Close", 2890, L"API|SNI%u#\n", *((_DWORD *)this + 11));
  if ( (*(_BYTE *)(*((_QWORD *)this + 4) + 12804LL) & 2) == 0 )
  {
    Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v25, 1);
    LODWORD(v30[0]) = 536871518;
    memset(&v30[1], 0, 32);
    v31 = 0;
    v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v3 = *(_QWORD *)(v2 + 256);
    if ( !v3 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v3 = *(_QWORD *)(v2 + 256);
    }
    v4 = *(_QWORD *)(v3 + 600);
    if ( v4 )
      v31 = (unsigned int)SOS_Task::PushWait(v4, v30) == 0;
    v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v6 = *(_QWORD *)(v5 + 256);
    if ( !v6 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v6 = *(_QWORD *)(v5 + 256);
    }
    v29 = v6;
    v28 = (*(_DWORD *)(v6 + 800) >> 11) & 1;
    if ( v28 || (*(_BYTE *)(v6 + 800) & 4) == 0 )
    {
      v27 = 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 608) + 8LL))(*(_QWORD *)(v6 + 608));
    }
    else
    {
      v27 = 0;
    }
    DisconnectNamedPipe(*((HANDLE *)this + 8));
    AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v27);
    *(_DWORD *)(v26 + 616) &= ~(_DWORD)v25;
  }
  v7 = SNI::detail::Transport::FCloseRefHandle(this);
  v9 = v7;
  v10 = *((_QWORD *)this + 10);
  if ( v10 && v7 )
  {
    if ( WaitForSingleObject(*(HANDLE *)(v10 + 40), 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v24) = LastError;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::Close",
          2927,
          L"ERR|SNIWaitForSingleObject failed:%d{WINERR}\n",
          v24);
      }
    }
    else
    {
      SNIPacketRelease(*((struct SNI_Packet **)this + 10));
      *((_QWORD *)this + 10) = 0;
    }
  }
  if ( *((_QWORD *)this + 15) && v9 )
  {
    v12 = WaitForSingleObject(*((HANDLE *)this + 14), 0);
    v13 = v12;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v24) = v12;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::Close",
        2938,
        L"API|SNIWaitForSingleObject 1 returned %d.\n",
        v24);
    }
    if ( v13 == 258 )
    {
      Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v32, 1);
      v37 = 536871529;
      v38 = 0;
      v40 = 0;
      v39 = 0;
      v41 = 0;
      v42 = 0;
      v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v15 = *(_QWORD *)(v14 + 256);
      if ( !v15 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v15 = *(_QWORD *)(v14 + 256);
      }
      v16 = *(_QWORD *)(v15 + 600);
      if ( v16 )
        v42 = (unsigned int)SOS_Task::PushWait(v16, &v37) == 0;
      v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v18 = *(_QWORD *)(v17 + 256);
      if ( !v18 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v18 = *(_QWORD *)(v17 + 256);
      }
      v36 = v18;
      v35 = (*(_DWORD *)(v18 + 800) >> 11) & 1;
      if ( v35 || (*(_BYTE *)(v18 + 800) & 4) == 0 )
      {
        v34 = 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 608) + 8LL))(*(_QWORD *)(v18 + 608));
      }
      else
      {
        v34 = 0;
      }
      v19 = WaitForSingleObject(*((HANDLE *)this + 14), 0xFFFFFFFF);
      v20 = v19;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v24) = v19;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::Close",
          2951,
          L"API|SNIWaitForSingleObject 2 returned %d.\n",
          v24);
      }
      if ( v20 )
      {
        v21 = GetLastError();
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v24) = v21;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::Close",
            2963,
            L"ERR|SNIWaitForSingleObject 2 failed:%d{WINERR}\n",
            v24);
        }
      }
      else
      {
        SNIPacketRelease(*((struct SNI_Packet **)this + 15));
        *((_QWORD *)this + 15) = 0;
      }
      AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v34);
      *(_DWORD *)(v33 + 616) &= ~v32;
    }
    else if ( v13 )
    {
      v22 = GetLastError();
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v24) = v22;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::Close",
          2979,
          L"ERR|SNIWaitForSingleObject 2 failed:%d{WINERR}\n",
          v24);
      }
    }
    else
    {
      SNIPacketRelease(*((struct SNI_Packet **)this + 15));
      *((_QWORD *)this + 15) = 0;
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Close", 2983, L"RET|SNI%d{WINERR}\n", 0);
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Close", 2890, v8);
  return 0;
}

```

## disassembly

```asm
0x10043d8c0  mov     rax, rsp
0x10043d8c3  push    rbp
0x10043d8c4  push    r14
0x10043d8c6  push    r15
0x10043d8c8  lea     rbp, [rax-28h]
0x10043d8cc  sub     rsp, 110h
0x10043d8d3  mov     [rbp+20h+var_30], 0FFFFFFFFFFFFFFFEh
0x10043d8db  mov     [rax+10h], rbx
0x10043d8df  mov     [rax+18h], rsi
0x10043d8e3  mov     [rax+20h], rdi
0x10043d8e7  mov     rbx, rcx
0x10043d8ea  lea     r14, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043d8f1  mov     [rbp+20h+var_28], r14
0x10043d8f5  lea     r15, aNpClose; "Np::Close"
0x10043d8fc  mov     [rbp+20h+var_20], r15
0x10043d900  mov     [rbp+20h+var_18], 0B4Ah
0x10043d907  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043d90e  jz      short loc_10043D92F
0x10043d910  mov     eax, [rcx+2Ch]
0x10043d913  mov     dword ptr [rsp+120h+var_100], eax
0x10043d917  lea     r9, aApiSniU; "API|SNI%u#\n"
0x10043d91e  mov     r8d, 0B4Ah; int
0x10043d924  mov     rdx, r15; char *
0x10043d927  mov     rcx, r14; char *
0x10043d92a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043d92f  mov     rax, [rbx+20h]
0x10043d933  xor     esi, esi
0x10043d935  test    byte ptr [rax+3204h], 2
0x10043d93c  jnz     loc_10043DA6B
0x10043d942  lea     edx, [rsi+1]
0x10043d945  lea     rcx, [rsp+120h+var_F0]
0x10043d94a  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043d94f  nop
0x10043d950  lea     rax, [rsp+120h+var_E0]
0x10043d955  mov     [rbp+20h+arg_0], rax
0x10043d959  mov     dword ptr [rsp+120h+var_D0], 2000025Eh
0x10043d961  mov     [rsp+120h+var_C8], rsi
0x10043d966  mov     [rsp+120h+var_B8], rsi
0x10043d96b  mov     [rsp+120h+var_C0], rsi
0x10043d970  mov     [rsp+120h+var_B0], rsi
0x10043d975  mov     [rbp+20h+var_A0], sil
0x10043d979  mov     rdx, gs:58h
0x10043d982  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043d989  mov     ecx, [rax]
0x10043d98b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043d992  mov     edi, [rax]
0x10043d994  add     rdi, [rdx+rcx*8]
0x10043d998  mov     rcx, [rdi+100h]
0x10043d99f  test    rcx, rcx
0x10043d9a2  jnz     short loc_10043D9B1
0x10043d9a4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043d9aa  mov     rcx, [rdi+100h]
0x10043d9b1  mov     rcx, [rcx+258h]
0x10043d9b8  test    rcx, rcx
0x10043d9bb  jz      short loc_10043D9CE
0x10043d9bd  lea     rdx, [rsp+120h+var_D0]
0x10043d9c2  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043d9c8  test    eax, eax
0x10043d9ca  setz    [rbp+20h+var_A0]
0x10043d9ce  mov     rdx, gs:58h
0x10043d9d7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043d9de  mov     ecx, [rax]
0x10043d9e0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043d9e7  mov     edi, [rax]
0x10043d9e9  add     rdi, [rdx+rcx*8]
0x10043d9ed  mov     rdx, [rdi+100h]
0x10043d9f4  test    rdx, rdx
0x10043d9f7  jnz     short loc_10043DA08
0x10043d9f9  xor     ecx, ecx
0x10043d9fb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043da01  mov     rdx, [rdi+100h]
0x10043da08  mov     [rsp+120h+var_D8], rdx
0x10043da0d  mov     eax, [rdx+320h]
0x10043da13  shr     eax, 0Bh
0x10043da16  and     eax, 1
0x10043da19  mov     dword ptr [rsp+120h+var_E0+4], eax
0x10043da1d  jnz     short loc_10043DA2E
0x10043da1f  test    byte ptr [rdx+320h], 4
0x10043da26  jz      short loc_10043DA2E
0x10043da28  mov     dword ptr [rsp+120h+var_E0], esi
0x10043da2c  jmp     short loc_10043DA44
0x10043da2e  mov     dword ptr [rsp+120h+var_E0], 1
0x10043da36  mov     rcx, [rdx+260h]
0x10043da3d  mov     rax, [rcx]
0x10043da40  call    qword ptr [rax+8]
0x10043da43  nop
0x10043da44  mov     rcx, [rbx+40h]; hNamedPipe
0x10043da48  call    cs:__imp_DisconnectNamedPipe
0x10043da4e  nop
0x10043da4f  lea     rcx, [rsp+120h+var_E0]; this
0x10043da54  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043da59  nop
0x10043da5a  mov     ecx, dword ptr [rsp+120h+var_F0]
0x10043da5e  not     ecx
0x10043da60  mov     rax, [rsp+120h+var_E8]
0x10043da65  and     [rax+268h], ecx
0x10043da6b  mov     rcx, rbx; this
0x10043da6e  call    ?FCloseRefHandle@Transport@detail@SNI@@IEAA_NXZ; SNI::detail::Transport::FCloseRefHandle(void)
0x10043da73  movzx   edi, al
0x10043da76  mov     rcx, [rbx+50h]
0x10043da7a  test    rcx, rcx
0x10043da7d  jz      short loc_10043DAD0
0x10043da7f  test    al, al
0x10043da81  jz      short loc_10043DAD0
0x10043da83  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x10043da88  mov     rcx, [rcx+28h]; hHandle
0x10043da8c  call    cs:__imp_WaitForSingleObject
0x10043da92  test    eax, eax
0x10043da94  jnz     short loc_10043DAA5
0x10043da96  mov     rcx, [rbx+50h]; struct SNI_Packet *
0x10043da9a  call    SNIPacketRelease
0x10043da9f  mov     [rbx+50h], rsi
0x10043daa3  jmp     short loc_10043DAD0
0x10043daa5  call    cs:__imp_GetLastError
0x10043daab  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dab2  jz      short loc_10043DAD0
0x10043dab4  mov     dword ptr [rsp+120h+var_100], eax
0x10043dab8  lea     r9, aErrSniwaitfors; "ERR|SNIWaitForSingleObject failed:%d{WI"...
0x10043dabf  mov     r8d, 0B6Fh; int
0x10043dac5  mov     rdx, r15; char *
0x10043dac8  mov     rcx, r14; char *
0x10043dacb  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043dad0  cmp     qword ptr [rbx+78h], 0
0x10043dad5  jz      loc_10043DCE9
0x10043dadb  test    dil, dil
0x10043dade  jz      loc_10043DCE9
0x10043dae4  xor     edx, edx; dwMilliseconds
0x10043dae6  mov     rcx, [rbx+70h]; hHandle
0x10043daea  call    cs:__imp_WaitForSingleObject
0x10043daf0  mov     edi, eax
0x10043daf2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043daf9  jz      short loc_10043DB17
0x10043dafb  mov     dword ptr [rsp+120h+var_100], eax
0x10043daff  lea     r9, aApiSniwaitfors; "API|SNIWaitForSingleObject 1 returned %"...
0x10043db06  mov     r8d, 0B7Ah; int
0x10043db0c  mov     rdx, r15; char *
0x10043db0f  mov     rcx, r14; char *
0x10043db12  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043db17  cmp     edi, 102h
0x10043db1d  jnz     loc_10043DCAB
0x10043db23  mov     edx, 1
0x10043db28  lea     rcx, [rbp+20h+var_90]
0x10043db2c  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043db31  nop
0x10043db32  lea     rax, [rbp+20h+var_80]
0x10043db36  mov     [rbp+20h+arg_0], rax
0x10043db3a  mov     [rbp+20h+var_70], 20000269h
0x10043db41  mov     [rbp+20h+var_68], rsi
0x10043db45  mov     [rbp+20h+var_58], rsi
0x10043db49  mov     [rbp+20h+var_60], rsi
0x10043db4d  mov     [rbp+20h+var_50], rsi
0x10043db51  mov     [rbp+20h+var_40], 0
0x10043db55  mov     rdx, gs:58h
0x10043db5e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043db65  mov     ecx, [rax]
0x10043db67  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043db6e  mov     edi, [rax]
0x10043db70  add     rdi, [rdx+rcx*8]
0x10043db74  mov     rcx, [rdi+100h]
0x10043db7b  test    rcx, rcx
0x10043db7e  jnz     short loc_10043DB8D
0x10043db80  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043db86  mov     rcx, [rdi+100h]
0x10043db8d  mov     rcx, [rcx+258h]
0x10043db94  test    rcx, rcx
0x10043db97  jz      short loc_10043DBA9
0x10043db99  lea     rdx, [rbp+20h+var_70]
0x10043db9d  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043dba3  test    eax, eax
0x10043dba5  setz    [rbp+20h+var_40]
0x10043dba9  mov     rdx, gs:58h
0x10043dbb2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043dbb9  mov     ecx, [rax]
0x10043dbbb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043dbc2  mov     edi, [rax]
0x10043dbc4  add     rdi, [rdx+rcx*8]
0x10043dbc8  mov     rdx, [rdi+100h]
0x10043dbcf  test    rdx, rdx
0x10043dbd2  jnz     short loc_10043DBE3
0x10043dbd4  xor     ecx, ecx
0x10043dbd6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043dbdc  mov     rdx, [rdi+100h]
0x10043dbe3  mov     [rbp+20h+var_78], rdx
0x10043dbe7  mov     eax, [rdx+320h]
0x10043dbed  shr     eax, 0Bh
0x10043dbf0  and     eax, 1
0x10043dbf3  mov     [rbp+20h+var_7C], eax
0x10043dbf6  jnz     short loc_10043DC06
0x10043dbf8  test    byte ptr [rdx+320h], 4
0x10043dbff  jz      short loc_10043DC06
0x10043dc01  mov     [rbp+20h+var_80], esi
0x10043dc04  jmp     short loc_10043DC1B
0x10043dc06  mov     [rbp+20h+var_80], 1
0x10043dc0d  mov     rcx, [rdx+260h]
0x10043dc14  mov     rax, [rcx]
0x10043dc17  call    qword ptr [rax+8]
0x10043dc1a  nop
0x10043dc1b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x10043dc20  mov     rcx, [rbx+70h]; hHandle
0x10043dc24  call    cs:__imp_WaitForSingleObject
0x10043dc2a  mov     edi, eax
0x10043dc2c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dc33  jz      short loc_10043DC51
0x10043dc35  mov     dword ptr [rsp+120h+var_100], eax
0x10043dc39  lea     r9, aApiSniwaitfors_0; "API|SNIWaitForSingleObject 2 returned %"...
0x10043dc40  mov     r8d, 0B87h; int
0x10043dc46  mov     rdx, r15; char *
0x10043dc49  mov     rcx, r14; char *
0x10043dc4c  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043dc51  test    edi, edi
0x10043dc53  jnz     short loc_10043DC64
0x10043dc55  mov     rcx, [rbx+78h]; struct SNI_Packet *
0x10043dc59  call    SNIPacketRelease
0x10043dc5e  mov     [rbx+78h], rsi
0x10043dc62  jmp     short loc_10043DC90
0x10043dc64  call    cs:__imp_GetLastError
0x10043dc6a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dc71  jz      short loc_10043DC90
0x10043dc73  mov     dword ptr [rsp+120h+var_100], eax
0x10043dc77  lea     r9, aErrSniwaitfors_2; "ERR|SNIWaitForSingleObject 2 failed:%d{"...
0x10043dc7e  mov     r8d, 0B93h; int
0x10043dc84  mov     rdx, r15; char *
0x10043dc87  mov     rcx, r14; char *
0x10043dc8a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043dc8f  nop
0x10043dc90  lea     rcx, [rbp+20h+var_80]; this
0x10043dc94  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043dc99  nop
0x10043dc9a  mov     ecx, [rbp+20h+var_90]
0x10043dc9d  not     ecx
0x10043dc9f  mov     rax, [rbp+20h+var_88]
0x10043dca3  and     [rax+268h], ecx
0x10043dca9  jmp     short loc_10043DCE9
0x10043dcab  test    edi, edi
0x10043dcad  jnz     short loc_10043DCBE
0x10043dcaf  mov     rcx, [rbx+78h]; struct SNI_Packet *
0x10043dcb3  call    SNIPacketRelease
0x10043dcb8  mov     [rbx+78h], rsi
0x10043dcbc  jmp     short loc_10043DCE9
0x10043dcbe  call    cs:__imp_GetLastError
0x10043dcc4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dccb  jz      short loc_10043DCE9
0x10043dccd  mov     dword ptr [rsp+120h+var_100], eax
0x10043dcd1  lea     r9, aErrSniwaitfors_2; "ERR|SNIWaitForSingleObject 2 failed:%d{"...
0x10043dcd8  mov     r8d, 0BA3h; int
0x10043dcde  mov     rdx, r15; char *
0x10043dce1  mov     rcx, r14; char *
0x10043dce4  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043dce9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dcf0  jz      short loc_10043DD10
0x10043dcf2  mov     [rsp+120h+var_100], rsi
0x10043dcf7  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043dcfe  mov     r8d, 0BA7h; int
0x10043dd04  mov     rdx, r15; char *
0x10043dd07  mov     rcx, r14; char *
0x10043dd0a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043dd0f  nop
0x10043dd10  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043dd17  jz      short loc_10043DD2A
0x10043dd19  mov     r8d, 0B4Ah; int
0x10043dd1f  mov     rdx, r15; char *
0x10043dd22  mov     rcx, r14; char *
0x10043dd25  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043dd2a  xor     eax, eax
0x10043dd2c  lea     r11, [rsp+120h+var_10]
0x10043dd34  mov     rbx, [r11+28h]
0x10043dd38  mov     rsi, [r11+30h]
0x10043dd3c  mov     rdi, [r11+38h]
0x10043dd40  mov     rsp, r11
0x10043dd43  pop     r15
0x10043dd45  pop     r14
0x10043dd47  pop     rbp
0x10043dd48  retn
```
