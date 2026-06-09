# CSQLSatelliteConnection::AcceptCallBack(SNI_Conn *,void *)

- ea: `0x100472580`
- end: `0x100472880`
- name: `?AcceptCallBack@CSQLSatelliteConnection@@SAXPEAVSNI_Conn@@PEAX@Z`
- size: `768`
- prototype: `void __fastcall(struct SNI_Conn *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x100407f40`
- `0x10040bbb0`
- `0x10040bd60`
- `0x100419e30`
- `0x100426760`
- `0x1004269b0`
- `0x100427e60`
- `0x100472580`
- `0x1004737e0`
- `0x1004759c0`
- `0x100477b20`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100472626`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100472626`
- `sqldk!SystemThread_TlsIndex` at `0x1004725b6`
- `sqldk!SystemThread_TlsIndex` at `0x1004726c3`
- `sqldk!SystemThread_TlsOffset` at `0x1004725bf`
- `sqldk!SystemThread_TlsOffset` at `0x1004726cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004725da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004726f7`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004725da`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004726f7`

## string_xrefs

- `0x100472611`: `Sql\Ntdbms\extensibility\common\src\communisatellite.cpp`
- `0x100472739`: `Failed to start a SOS task for error! at CSQLSatelliteConnection::AcceptCallBack`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSQLSatelliteConnection::AcceptCallBack(struct SNI_Conn *a1, void *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  struct IMemObj *v5; // rdi
  CSQLSatelliteSessionBasedMsgQueueConnection *v6; // rax
  CSQLSatelliteSessionBasedMsgQueueConnection *v7; // rbx
  const wchar_t *v8; // r9
  _QWORD *ThreadLocalStoragePointer; // rdx
  void *(*v10)(void *); // rsi
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // [rsp+38h] [rbp-D0h] BYREF
  CSQLSatelliteSessionBasedMsgQueueConnection *v15; // [rsp+40h] [rbp-C8h]
  __int64 v16; // [rsp+48h] [rbp-C0h]
  struct IMemObj *v17; // [rsp+50h] [rbp-B8h]
  CSQLSatelliteSessionBasedMsgQueueConnection *v18; // [rsp+58h] [rbp-B0h]
  _DWORD v19[6]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD **v20; // [rsp+80h] [rbp-88h]
  char *v21; // [rsp+88h] [rbp-80h]
  __int64 v22; // [rsp+90h] [rbp-78h]
  _QWORD *v23; // [rsp+98h] [rbp-70h] BYREF
  int v24; // [rsp+A0h] [rbp-68h]
  int v25; // [rsp+A4h] [rbp-64h]
  const wchar_t *v26; // [rsp+A8h] [rbp-60h]
  int v27; // [rsp+B0h] [rbp-58h]
  int v28; // [rsp+B4h] [rbp-54h]
  char v29; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v30; // [rsp+2B8h] [rbp+1B0h]
  __int64 v31; // [rsp+2C0h] [rbp+1B8h]
  _QWORD v32[4]; // [rsp+2C8h] [rbp+1C0h] BYREF
  int v33; // [rsp+328h] [rbp+220h] BYREF
  int v34; // [rsp+330h] [rbp+228h]

  v16 = -2;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = *(struct IMemObj **)(*(_QWORD *)(v4 + 992) + 320LL);
  v17 = v5;
  v34 = 2834;
  v6 = (CSQLSatelliteSessionBasedMsgQueueConnection *)operator new(
                                                        0x450u,
                                                        v5,
                                                        1,
                                                        "Sql\\Ntdbms\\extensibility\\common\\src\\communisatellite.cpp",
                                                        2834,
                                                        6u);
  v18 = v6;
  if ( v6 )
    v7 = CSQLSatelliteSessionBasedMsgQueueConnection::CSQLSatelliteSessionBasedMsgQueueConnection(v6);
  else
    v7 = 0;
  v15 = v7;
  if ( v7 && (int)CSQLSatelliteSessionBasedMsgQueueConnection::Init(v7, v5) >= 0 )
  {
    v15 = 0;
    SNISetInfo(a1, 2, v7);
    *((_QWORD *)v7 + 8) = a1;
    v33 = 10;
    SNIGetInfo((__int64)a1, 45, (__int64)&v33, v8);
    if ( v33 == 1 )
      *((_BYTE *)v7 + 56) = 0;
    v14 = 0;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v10 = CSQLSatelliteConnection::m_pLaunchTask;
    if ( v33 != 1 )
      v10 = CSQLSatelliteConnection::m_pDataCargoTask;
    v11 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v12 = *(_QWORD *)(v11 + 256);
    if ( !v12 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v12 = *(_QWORD *)(v11 + 256);
    }
    v13 = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v12 + 992), v10, v7, 544, &v14, 0);
    if ( v13 )
    {
      CSQLSatelliteConnection::AbortConnection(
        v7,
        L"Failed to start a SOS task for error! at CSQLSatelliteConnection::AcceptCallBack",
        v13);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 8, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v7 + 2) )
          TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)v7 + 3), v7);
        (*(void (__fastcall **)(CSQLSatelliteSessionBasedMsgQueueConnection *))(*(_QWORD *)v7 + 24LL))(v7);
      }
    }
    CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(&v14);
    v7 = v15;
  }
  else
  {
    if ( (g_XeSQLSatellitePkg_enabledBitmap & 0x80u) != 0 )
    {
      v19[2] = 0x20000;
      v19[4] = 0;
      v20 = &v23;
      v21 = &v29;
      v30 = 0;
      v22 = 0;
      v31 = 0;
      v23 = v32;
      v24 = 32;
      v25 = 1;
      v32[0] = a1;
      v32[1] = 0;
      v32[2] = 0;
      v26 = L"Out of memory, at CSQLSatelliteConnection::AcceptCallBack!";
      v27 = 116;
      v28 = 4;
      XeSQLSatellitePkg::satellite_abort_connection::Publish((XeSQLSatellitePkg::satellite_abort_connection *)v19);
    }
    SNISetInfo(a1, 2, -1);
    SNICloseEx(a1, 0);
  }
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 8, 0xFFFFFFFF) == 1 )
  {
    if ( *((_QWORD *)v7 + 2) )
      TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)v7 + 3), v7);
    (*(void (__fastcall **)(CSQLSatelliteSessionBasedMsgQueueConnection *))(*(_QWORD *)v7 + 24LL))(v7);
  }
}

```

## disassembly

```asm
0x100472580  mov     rax, rsp
0x100472583  push    rbp
0x100472584  push    rdi
0x100472585  push    r12
0x100472587  push    r14
0x100472589  push    r15
0x10047258b  lea     rbp, [rax-208h]
0x100472592  sub     rsp, 2E0h
0x100472599  mov     [rsp+300h+var_2C0], 0FFFFFFFFFFFFFFFEh
0x1004725a2  mov     [rax+8], rbx
0x1004725a6  mov     [rax+10h], rsi
0x1004725aa  mov     rsi, rcx
0x1004725ad  mov     r8, gs:58h
0x1004725b6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004725bd  mov     edx, [rax]
0x1004725bf  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004725c6  mov     ebx, [rax]
0x1004725c8  add     rbx, [r8+rdx*8]
0x1004725cc  mov     rax, [rbx+100h]
0x1004725d3  test    rax, rax
0x1004725d6  jnz     short loc_1004725E7
0x1004725d8  xor     ecx, ecx
0x1004725da  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004725e0  mov     rax, [rbx+100h]
0x1004725e7  mov     rax, [rax+3E0h]
0x1004725ee  mov     rdi, [rax+140h]
0x1004725f5  mov     [rsp+300h+var_2B8], rdi
0x1004725fa  mov     [rbp+200h+arg_18], 0B12h
0x100472604  mov     byte ptr [rsp+300h+var_2D8], 6
0x100472609  mov     dword ptr [rsp+300h+var_2E0], 0B12h
0x100472611  lea     r9, aSqlNtdbmsExten_8; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100472618  mov     r8d, 1
0x10047261e  mov     rdx, rdi
0x100472621  mov     ecx, 450h
0x100472626  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047262c  mov     [rsp+300h+var_2B0], rax
0x100472631  xor     r15d, r15d
0x100472634  test    rax, rax
0x100472637  jz      short loc_100472646
0x100472639  mov     rcx, rax; this
0x10047263c  call    ??0CSQLSatelliteSessionBasedMsgQueueConnection@@QEAA@XZ; CSQLSatelliteSessionBasedMsgQueueConnection::CSQLSatelliteSessionBasedMsgQueueConnection(void)
0x100472641  mov     rbx, rax
0x100472644  jmp     short loc_100472649
0x100472646  mov     rbx, r15
0x100472649  mov     [rsp+300h+var_2C8], rbx
0x10047264e  test    rbx, rbx
0x100472651  jz      loc_100472785
0x100472657  mov     rdx, rdi; struct IMemObj *
0x10047265a  mov     rcx, rbx; this
0x10047265d  call    ?Init@CSQLSatelliteSessionBasedMsgQueueConnection@@QEAAJPEAVIMemObj@@@Z; CSQLSatelliteSessionBasedMsgQueueConnection::Init(IMemObj *)
0x100472662  test    eax, eax
0x100472664  js      loc_100472785
0x10047266a  mov     [rsp+300h+var_2C8], r15
0x10047266f  mov     r8, rbx
0x100472672  mov     edx, 2
0x100472677  mov     rcx, rsi
0x10047267a  call    SNISetInfo
0x10047267f  mov     [rbx+40h], rsi
0x100472683  mov     [rbp+200h+arg_10], 0Ah
0x10047268d  lea     r8, [rbp+200h+arg_10]
0x100472694  mov     edx, 2Dh ; '-'
0x100472699  mov     rcx, rsi
0x10047269c  call    SNIGetInfo
0x1004726a1  cmp     [rbp+200h+arg_10], 1
0x1004726a8  jnz     short loc_1004726AE
0x1004726aa  mov     byte ptr [rbx+38h], 0
0x1004726ae  mov     [rsp+300h+var_2D0], r15
0x1004726b3  cmp     [rbp+200h+arg_10], 1
0x1004726ba  mov     rdx, gs:58h
0x1004726c3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004726ca  mov     ecx, [rax]
0x1004726cc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004726d3  mov     edi, [rax]
0x1004726d5  mov     rsi, cs:?m_pLaunchTask@CSQLSatelliteConnection@@2P6APEAXPEAX@ZEA; void * (*CSQLSatelliteConnection::m_pLaunchTask)(void *)
0x1004726dc  jz      short loc_1004726E5
0x1004726de  mov     rsi, cs:?m_pDataCargoTask@CSQLSatelliteConnection@@2P6APEAXPEAX@ZEA; void * (*CSQLSatelliteConnection::m_pDataCargoTask)(void *)
0x1004726e5  add     rdi, [rdx+rcx*8]
0x1004726e9  mov     rax, [rdi+100h]
0x1004726f0  test    rax, rax
0x1004726f3  jnz     short loc_100472704
0x1004726f5  xor     ecx, ecx
0x1004726f7  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004726fd  mov     rax, [rdi+100h]
0x100472704  mov     rcx, [rax+3E0h]
0x10047270b  mov     [rsp+300h+var_2D8], r15
0x100472710  lea     rax, [rsp+300h+var_2D0]
0x100472715  mov     [rsp+300h+var_2E0], rax
0x10047271a  mov     r9d, 220h
0x100472720  mov     r8, rbx
0x100472723  mov     rdx, rsi
0x100472726  call    ?EnqueueTaskDirect@SOS_Node@@QEAA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@PEAPEAX@Z; SOS_Node::EnqueueTaskDirect(void * (*)(void *),void *,ulong,SOS_Task * *,void * *)
0x10047272b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100472732  test    eax, eax
0x100472734  jz      short loc_100472771
0x100472736  mov     r8d, eax
0x100472739  lea     rdx, aFailedToStartA; "Failed to start a SOS task for error! a"...
0x100472740  mov     rcx, rbx; this
0x100472743  call    ?AbortConnection@CSQLSatelliteConnection@@QEAAXPEB_WZZ; CSQLSatelliteConnection::AbortConnection(wchar_t const *,...)
0x100472748  mov     eax, edi
0x10047274a  lock xadd [rbx+20h], eax
0x10047274f  cmp     eax, 1
0x100472752  jnz     short loc_100472771
0x100472754  cmp     qword ptr [rbx+10h], 0
0x100472759  jz      short loc_100472767
0x10047275b  mov     rdx, rbx
0x10047275e  mov     rcx, [rbx+18h]
0x100472762  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100472767  mov     rax, [rbx]
0x10047276a  mov     rcx, rbx
0x10047276d  call    qword ptr [rax+18h]
0x100472770  nop
0x100472771  lea     rcx, [rsp+300h+var_2D0]
0x100472776  call    ??1?$CAutoRefc@VSOS_Task@@@@QEAA@XZ; CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(void)
0x10047277b  mov     rbx, [rsp+300h+var_2C8]
0x100472780  jmp     loc_100472839
0x100472785  mov     r14d, 2
0x10047278b  test    byte ptr cs:?g_XeSQLSatellitePkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0DM@@@@@A, 80h; XBitmap<StaticStorage<60>> g_XeSQLSatellitePkg_enabledBitmap
0x100472792  jz      loc_100472819
0x100472798  mov     [rsp+300h+var_298], 20000h
0x1004727a0  mov     dword ptr [rsp+300h+var_290], r15d
0x1004727a5  lea     rax, [rbp+200h+var_270]
0x1004727a9  mov     [rsp+300h+var_288], rax
0x1004727ae  lea     rax, [rbp+200h+var_250]
0x1004727b2  mov     [rbp+200h+var_280], rax
0x1004727b6  mov     [rbp+200h+var_50], r15
0x1004727bd  mov     [rbp+200h+var_278], r15
0x1004727c1  mov     [rbp+200h+var_48], r15
0x1004727c8  lea     rax, [rbp+200h+var_40]
0x1004727cf  mov     [rbp+200h+var_270], rax
0x1004727d3  mov     [rbp+200h+var_268], 20h ; ' '
0x1004727da  mov     [rbp+200h+var_264], 1
0x1004727e1  mov     [rbp+200h+var_40], rsi
0x1004727e8  mov     [rbp+200h+var_38], r15
0x1004727ef  mov     [rbp+200h+var_30], r15
0x1004727f6  lea     rax, aOutOfMemoryAtC; "Out of memory, at CSQLSatelliteConnecti"...
0x1004727fd  mov     [rbp+200h+var_260], rax
0x100472801  mov     [rbp+200h+var_258], 74h ; 't'
0x100472808  mov     [rbp+200h+var_254], 4
0x10047280f  lea     rcx, [rsp+300h+var_2A0]; this
0x100472814  call    ?Publish@satellite_abort_connection@XeSQLSatellitePkg@@QEAAXXZ; XeSQLSatellitePkg::satellite_abort_connection::Publish(void)
0x100472819  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x100472820  mov     r8, rdi
0x100472823  mov     edx, r14d
0x100472826  mov     rcx, rsi
0x100472829  call    SNISetInfo
0x10047282e  xor     edx, edx
0x100472830  mov     rcx, rsi
0x100472833  call    SNICloseEx
0x100472838  nop
0x100472839  test    rbx, rbx
0x10047283c  jz      short loc_100472864
0x10047283e  lock xadd [rbx+20h], edi
0x100472843  cmp     edi, 1
0x100472846  jnz     short loc_100472864
0x100472848  cmp     qword ptr [rbx+10h], 0
0x10047284d  jz      short loc_10047285B
0x10047284f  mov     rdx, rbx
0x100472852  mov     rcx, [rbx+18h]
0x100472856  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x10047285b  mov     rax, [rbx]
0x10047285e  mov     rcx, rbx
0x100472861  call    qword ptr [rax+18h]
0x100472864  lea     r11, [rsp+300h+var_20]
0x10047286c  mov     rbx, [r11+30h]
0x100472870  mov     rsi, [r11+38h]
0x100472874  mov     rsp, r11
0x100472877  pop     r15
0x100472879  pop     r14
0x10047287b  pop     r12
0x10047287d  pop     rdi
0x10047287e  pop     rbp
0x10047287f  retn
```
