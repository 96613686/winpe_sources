# SNICloseEx

- ea: `0x100426760`
- end: `0x1004269a0`
- name: `SNICloseEx`
- size: `576`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x100432820`
- `0x100472580`
- `0x100473630`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x100423130`
- `0x100426760`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`

## import_xrefs

- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10042691d`
- `sqldk!?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z` at `0x10042691d`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x1004268bf`
- `sqldk!?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z` at `0x1004268bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100426867`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100426867`
- `sqldk!SystemThread_TlsIndex` at `0x10042680f`
- `sqldk!SystemThread_TlsOffset` at `0x100426818`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100426833`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100426833`

## string_xrefs

- `0x10042678d`: `sql\common\dk\sni\src\sni.cpp`
- `0x100426854`: `Sql\DkTemp\sos\include\sossync.inl`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SNICloseEx(__int64 a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rax
  SOS_UnfairRecursiveMutexExtendedGuarantee **v8; // rbx
  unsigned int v9; // esi
  const wchar_t *v10; // r9
  __int64 v12; // [rsp+20h] [rbp-98h]
  int v13; // [rsp+60h] [rbp-58h] BYREF
  __int64 v14; // [rsp+68h] [rbp-50h]
  __int64 v15; // [rsp+70h] [rbp-48h]
  __int64 v16; // [rsp+78h] [rbp-40h]
  __int64 v17; // [rsp+80h] [rbp-38h]
  char v18; // [rsp+C0h] [rbp+8h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNICloseEx",
      4675,
      L"API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Conn*}\n",
      *(_DWORD *)(a1 + 76),
      a1,
      -2);
  v13 = 4194679;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  if ( *(_BYTE *)(a1 + 12904) )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v5 = *(_QWORD *)(v4 + 256);
    if ( !v5 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v5 = *(_QWORD *)(v4 + 256);
    }
    if ( *(_QWORD *)(a1 + 12936) == v5 )
      utassert_fail(1u, "m_pExclusiveOwner != pWorker", "Sql\\DkTemp\\sos\\include\\sossync.inl", 1833, 0);
    v6 = *(_QWORD *)(v5 + 600);
    if ( !v6
      || !*(_QWORD *)(v6 + 152)
      || (*(_DWORD *)(v6 + 188) & 4) == 0
      || (v7 = *(_QWORD *)(v6 + 152), (*(_BYTE *)(v7 + 616) & 1) != 0)
      || (*(_DWORD *)(v7 + 800) & 0x180) != 0 )
    {
      if ( !(unsigned int)SOS_RWLock::GetLongWait(a1 + 12912, 2, 0xFFFFFFFFLL, &v13) )
        *(_QWORD *)(a1 + 12936) = v5;
    }
  }
  v8 = *(SOS_UnfairRecursiveMutexExtendedGuarantee ***)(a1 + 64);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v8);
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 12616) + 8LL))(*(_QWORD *)(a1 + 12616), a2);
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v8[1]);
  if ( *(_BYTE *)(a1 + 12904) )
    SOS_RWLock::ReleaseLock(a1 + 12912, 2);
  v18 = 0;
  SNI_Conn::ReleaseUnderForceCloseLock(a1, 0, &v18);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v12) = v9;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNICloseEx", 4708, L"RET|SNI%d{WINERR}\n", v12);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNICloseEx", 4675, v10);
  return v9;
}

```

## disassembly

```asm
0x100426760  mov     rax, rsp
0x100426763  push    rdi
0x100426764  push    r12
0x100426766  push    r13
0x100426768  push    r14
0x10042676a  push    r15
0x10042676c  sub     rsp, 90h
0x100426773  mov     [rsp+0B8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10042677c  mov     [rax+10h], rbx
0x100426780  mov     [rax+18h], rbp
0x100426784  mov     [rax+20h], rsi
0x100426788  mov     ebp, edx
0x10042678a  mov     rdi, rcx
0x10042678d  lea     r12, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100426794  mov     [rax-70h], r12
0x100426798  lea     r13, aSnicloseex; "SNICloseEx"
0x10042679f  mov     [rax-68h], r13
0x1004267a3  mov     dword ptr [rax-60h], 1243h
0x1004267aa  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004267b1  jz      short loc_1004267D7
0x1004267b3  mov     [rsp+0B8h+var_90], rcx
0x1004267b8  mov     eax, [rcx+4Ch]
0x1004267bb  mov     dword ptr [rsp+0B8h+var_98], eax
0x1004267bf  lea     r9, aApiSniUSniConn_6; "API|SNI%u#{SNI_Conn}, pConn: %p{SNI_Con"...
0x1004267c6  mov     r8d, 1243h; int
0x1004267cc  mov     rdx, r13; char *
0x1004267cf  mov     rcx, r12; char *
0x1004267d2  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004267d7  mov     [rsp+0B8h+var_58], 400177h
0x1004267df  xor     r15d, r15d
0x1004267e2  mov     [rsp+0B8h+var_50], r15
0x1004267e7  mov     [rsp+0B8h+var_40], r15
0x1004267ec  mov     [rsp+0B8h+var_48], r15
0x1004267f1  mov     [rsp+0B8h+var_38], r15
0x1004267f9  cmp     [rdi+3268h], r15b
0x100426800  jz      loc_1004268D0
0x100426806  mov     rdx, gs:58h
0x10042680f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100426816  mov     ecx, [rax]
0x100426818  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042681f  mov     esi, [rax]
0x100426821  add     rsi, [rdx+rcx*8]
0x100426825  mov     rbx, [rsi+100h]
0x10042682c  test    rbx, rbx
0x10042682f  jnz     short loc_100426840
0x100426831  xor     ecx, ecx
0x100426833  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100426839  mov     rbx, [rsi+100h]
0x100426840  cmp     [rdi+3288h], rbx
0x100426847  jnz     short loc_10042686D
0x100426849  mov     [rsp+0B8h+var_98], r15
0x10042684e  mov     r9d, 729h
0x100426854  lea     r8, ?szFileName@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "Sql\\DkTemp\\sos\\include\\sossync.inl"
0x10042685b  lea     rdx, ?szExpression@?6??GetLock@SOS_RWLock@@QEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z@4QBDB; "m_pExclusiveOwner != pWorker"
0x100426862  mov     ecx, 1
0x100426867  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10042686d  mov     rdx, [rbx+258h]
0x100426874  test    rdx, rdx
0x100426877  jz      short loc_1004268A8
0x100426879  cmp     [rdx+98h], r15
0x100426880  jz      short loc_1004268A8
0x100426882  mov     eax, [rdx+0BCh]
0x100426888  test    al, 4
0x10042688a  jz      short loc_1004268A8
0x10042688c  mov     rax, [rdx+98h]
0x100426893  test    byte ptr [rax+268h], 1
0x10042689a  jnz     short loc_1004268A8
0x10042689c  test    dword ptr [rax+320h], 180h
0x1004268a6  jz      short loc_1004268D0
0x1004268a8  lea     r9, [rsp+0B8h+var_58]
0x1004268ad  mov     edx, 2
0x1004268b2  mov     r8d, 0FFFFFFFFh
0x1004268b8  lea     rcx, [rdi+3270h]
0x1004268bf  call    cs:__imp_?GetLongWait@SOS_RWLock@@AEAA?AW4SOS_RESULT@@W4RWLockMode@@KPEBVSOS_WaitInfo@@@Z; SOS_RWLock::GetLongWait(RWLockMode,ulong,SOS_WaitInfo const *)
0x1004268c5  test    eax, eax
0x1004268c7  jnz     short loc_1004268D0
0x1004268c9  mov     [rdi+3288h], rbx
0x1004268d0  mov     rbx, [rdi+40h]
0x1004268d4  mov     [rsp+0B8h+var_80], rbx
0x1004268d9  mov     [rsp+0B8h+var_78], r15d
0x1004268de  mov     rcx, rbx; this
0x1004268e1  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x1004268e6  mov     [rsp+0B8h+var_78], 1
0x1004268ee  mov     rcx, [rdi+3148h]
0x1004268f5  mov     rax, [rcx]
0x1004268f8  mov     edx, ebp
0x1004268fa  call    qword ptr [rax+8]
0x1004268fd  mov     esi, eax
0x1004268ff  mov     rcx, [rbx+8]; this
0x100426903  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100426908  cmp     byte ptr [rdi+3268h], 0
0x10042690f  jz      short loc_100426923
0x100426911  lea     rcx, [rdi+3270h]
0x100426918  mov     edx, 2
0x10042691d  call    cs:__imp_?ReleaseLock@SOS_RWLock@@QEAAXW4RWLockMode@@@Z; SOS_RWLock::ReleaseLock(RWLockMode)
0x100426923  mov     [rsp+0B8h+arg_0], 0
0x10042692b  lea     r8, [rsp+0B8h+arg_0]
0x100426933  xor     edx, edx
0x100426935  mov     rcx, rdi
0x100426938  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x10042693d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100426944  jz      short loc_100426963
0x100426946  mov     dword ptr [rsp+0B8h+var_98], esi
0x10042694a  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100426951  mov     r8d, 1264h; int
0x100426957  mov     rdx, r13; char *
0x10042695a  mov     rcx, r12; char *
0x10042695d  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100426962  nop
0x100426963  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042696a  jz      short loc_10042697D
0x10042696c  mov     r8d, 1243h; int
0x100426972  mov     rdx, r13; char *
0x100426975  mov     rcx, r12; char *
0x100426978  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10042697d  mov     eax, esi
0x10042697f  lea     r11, [rsp+0B8h+var_28]
0x100426987  mov     rbx, [r11+38h]
0x10042698b  mov     rbp, [r11+40h]
0x10042698f  mov     rsi, [r11+48h]
0x100426993  mov     rsp, r11
0x100426996  pop     r15
0x100426998  pop     r14
0x10042699a  pop     r13
0x10042699c  pop     r12
0x10042699e  pop     rdi
0x10042699f  retn
```
