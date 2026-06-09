# CThirdPartyMonitoring::HandleTimerNotification(ulong)

- ea: `0x180038500`
- end: `0x1800387d3`
- name: `?HandleTimerNotification@CThirdPartyMonitoring@@AEAAXK@Z`
- size: `723`
- prototype: `void __fastcall(CThirdPartyMonitoring *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000a740`

## callees

- `0x180002e30`
- `0x18000760c`
- `0x180008cc0`
- `0x180009f40`
- `0x18001aee0`
- `0x18001bf70`
- `0x18001ffe4`
- `0x18002047c`
- `0x180023a90`
- `0x180029e74`
- `0x180038470`
- `0x180038500`
- `0x180038824`
- `0x180038940`
- `0x180038a1c`
- `0x18003ab48`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003856a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003856a`

## pseudocode

```c
void __fastcall CThirdPartyMonitoring::HandleTimerNotification(CThirdPartyMonitoring *this)
{
  int v1; // r12d
  int v3; // r13d
  CThirdPartyMonitoring *v4; // rcx
  __int64 *v5; // rax
  _QWORD *HeadPosition; // rax
  char *v7; // rsi
  __int64 v8; // r8
  int v9; // r14d
  int v10; // r15d
  __int64 v11; // rdi
  struct CDetectoid *Next; // rax
  CRecheckQueue *v13; // rcx
  CThirdPartyMonitoring *v14; // rcx
  __int64 v15; // rsi
  int v16; // r15d
  CRecheckQueue *v17; // rcx
  CRecheckQueue *v18; // rcx
  __int64 v19; // r8
  int v20; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+48h] [rbp-18h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp-10h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-8h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF
  _QWORD *v25; // [rsp+B0h] [rbp+50h] BYREF
  struct _FILETIME v26; // [rsp+B8h] [rbp+58h] BYREF

  v1 = 0;
  FileTime1 = 0;
  v24 = 0;
  v3 = 1;
  do
  {
    if ( (unsigned int)CRecheckQueue::Peek(*((CRecheckQueue **)this + 136), (enum RECHECK_TYPE *)&v24, &FileTime1) )
      break;
    FileTime2 = 0;
    if ( (int)CThirdPartyMonitoring::CalculateNowPlusSeconds(v4, 5u, &FileTime2) >= 0 )
    {
      if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
      {
        v3 = 0;
        CThirdPartyMonitoring::ResetTimer(this);
      }
      else
      {
        v5 = (__int64 *)*((_QWORD *)this + 136);
        if ( *v5 && *(int *)(*v5 + 48) > 0 )
        {
          HeadPosition = CList<unsigned short *,unsigned short *>::GetHeadPosition(*v5);
          v7 = (char *)HeadPosition[2];
          CList<CExternalBase *,CExternalBase *>::RemoveAt(v8, HeadPosition);
          if ( v7 )
          {
            v9 = *((_DWORD *)v7 + 2);
            v10 = 0;
            v11 = *(_QWORD *)v7;
            FileTime1 = *(FILETIME *)(v7 + 12);
            v24 = v9;
            operator delete(v7);
          }
          else
          {
            v9 = v24;
            v11 = 0;
            v10 = -2147467259;
          }
          if ( !v10 )
          {
            if ( v9 == 2 )
            {
              v25 = CList<unsigned short *,unsigned short *>::GetHeadPosition(*((_QWORD *)this + 135));
              while ( v25 )
              {
                Next = (struct CDetectoid *)CList<CDetectoid *,CDetectoid *>::GetNext(*((_QWORD *)this + 135), &v25);
                CThirdPartyMonitoring::CheckDetectoidState(this, Next);
              }
              v13 = (CRecheckQueue *)*((_QWORD *)this + 136);
              v26 = 0;
              LODWORD(v25) = 2;
              if ( !(unsigned int)CRecheckQueue::Contains(v13, 0, (enum RECHECK_TYPE *)&v25)
                && (int)CThirdPartyMonitoring::CalculateNowPlusSeconds(v14, 0x15180u, &v26) >= 0 )
              {
                CRecheckQueue::Push(*((_QWORD *)this + 136), 0, 2, &v26);
              }
            }
            else if ( *(_DWORD *)(v11 + 56) )
            {
              v26.dwLowDateTime = 0;
              LODWORD(v25) = 0;
              if ( (*(int (__fastcall **)(__int64, struct _FILETIME *, _QWORD **))(*(_QWORD *)v11 + 56LL))(
                     v11,
                     &v26,
                     &v25) >= 0 )
              {
                v15 = *(_QWORD *)(v11 + 32);
                v16 = 0;
                if ( v9 != 1 && (_DWORD)v25 && (*(_BYTE *)(v15 + 80) & 0x10) != 0 )
                {
                  v17 = (CRecheckQueue *)*((_QWORD *)this + 136);
                  v20 = 1;
                  if ( (unsigned int)CRecheckQueue::Contains(v17, (struct CDetectoid *)v11, (enum RECHECK_TYPE *)&v20) )
                    *(_DWORD *)(v15 + 80) &= 0xFFFFFF0F;
                  else
                    v1 = 1;
                }
                if ( v9 && v26.dwLowDateTime && (unsigned int)CExternalBase::GetProductState(v15) != 4096 )
                {
                  v18 = (CRecheckQueue *)*((_QWORD *)this + 136);
                  v20 = 0;
                  if ( (unsigned int)CRecheckQueue::Contains(v18, (struct CDetectoid *)v11, (enum RECHECK_TYPE *)&v20) )
                    CExternalBase::SetProductState(v15, 4096, v19);
                  else
                    v16 = 1;
                }
                if ( v1 || v16 )
                {
                  v21 = 0;
                  v20 = 0;
                  CThirdPartyMonitoring::PushRecheckQueue(this, 0, (struct CDetectoid *)v11, v1, v16, 0, &v21, &v20);
                }
                CThirdPartyMonitoring::UpdateThirdPartyManager(this, 1, v11);
                v1 = 0;
              }
            }
          }
        }
      }
    }
    CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 140), 0);
  }
  while ( v3 );
}

```

## disassembly

```asm
0x180038500  mov     [rsp-38h+arg_0], rbx
0x180038505  mov     [rsp-38h+arg_8], edx
0x180038509  push    rbp
0x18003850a  push    rsi
0x18003850b  push    rdi
0x18003850c  push    r12
0x18003850e  push    r13
0x180038510  push    r14
0x180038512  push    r15
0x180038514  mov     rbp, rsp
0x180038517  sub     rsp, 60h
0x18003851b  xor     r12d, r12d
0x18003851e  mov     rbx, rcx
0x180038521  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r12
0x180038525  mov     [rbp+arg_8], r12d
0x180038529  lea     r13d, [r12+1]
0x18003852e  mov     rcx, [rbx+440h]; this
0x180038535  lea     r8, [rbp+FileTime1]; struct _FILETIME *
0x180038539  lea     rdx, [rbp+arg_8]; enum RECHECK_TYPE *
0x18003853d  call    ?Peek@CRecheckQueue@@QEAAJPEAW4RECHECK_TYPE@@PEAU_FILETIME@@@Z; CRecheckQueue::Peek(RECHECK_TYPE *,_FILETIME *)
0x180038542  test    eax, eax
0x180038544  jnz     loc_1800387BB
0x18003854a  lea     r8, [rbp+FileTime2]; struct _FILETIME *
0x18003854e  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x180038552  lea     edx, [rax+5]; unsigned int
0x180038555  call    ?CalculateNowPlusSeconds@CThirdPartyMonitoring@@AEAAJKPEAU_FILETIME@@@Z; CThirdPartyMonitoring::CalculateNowPlusSeconds(ulong,_FILETIME *)
0x18003855a  test    eax, eax
0x18003855c  js      loc_1800387A4
0x180038562  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180038566  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18003856a  call    cs:__imp_CompareFileTime
0x180038570  test    eax, eax
0x180038572  jg      loc_180038799
0x180038578  mov     rax, [rbx+440h]
0x18003857f  mov     r8, [rax]
0x180038582  test    r8, r8
0x180038585  jz      loc_1800387A4
0x18003858b  cmp     [r8+30h], r12d
0x18003858f  jle     loc_1800387A4
0x180038595  mov     rcx, r8
0x180038598  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x18003859d  mov     rdx, rax
0x1800385a0  mov     rcx, r8
0x1800385a3  mov     rsi, [rax+10h]
0x1800385a7  call    ?RemoveAt@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAXPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::RemoveAt(_CListElement *)
0x1800385ac  test    rsi, rsi
0x1800385af  jz      short loc_1800385D1
0x1800385b1  mov     r14d, [rsi+8]
0x1800385b5  mov     rcx, rsi; Block
0x1800385b8  mov     rax, [rsi+0Ch]
0x1800385bc  mov     r15d, r12d
0x1800385bf  mov     rdi, [rsi]
0x1800385c2  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x1800385c6  mov     [rbp+arg_8], r14d
0x1800385ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800385cf  jmp     short loc_1800385DE
0x1800385d1  mov     r14d, [rbp+arg_8]
0x1800385d5  mov     rdi, r12
0x1800385d8  mov     r15d, 80004005h
0x1800385de  test    r15d, r15d
0x1800385e1  jnz     loc_1800387A4
0x1800385e7  cmp     r14d, 2
0x1800385eb  jnz     loc_18003867D
0x1800385f1  mov     rcx, [rbx+438h]
0x1800385f8  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x1800385fd  mov     [rbp+arg_10], rax
0x180038601  test    rax, rax
0x180038604  jz      short loc_180038627
0x180038606  mov     rcx, [rbx+438h]
0x18003860d  lea     rdx, [rbp+arg_10]
0x180038611  call    ?GetNext@?$CList@PEAVCDetectoid@@PEAV1@@@QEAAPEAVCDetectoid@@AEAPEAU_CListElement@@@Z; CList<CDetectoid *,CDetectoid *>::GetNext(_CListElement * &)
0x180038616  mov     rdx, rax; struct CDetectoid *
0x180038619  mov     rcx, rbx; this
0x18003861c  call    ?CheckDetectoidState@CThirdPartyMonitoring@@AEAAJPEAVCDetectoid@@@Z; CThirdPartyMonitoring::CheckDetectoidState(CDetectoid *)
0x180038621  cmp     [rbp+arg_10], r12
0x180038625  jnz     short loc_180038606
0x180038627  mov     rcx, [rbx+440h]; this
0x18003862e  lea     r8, [rbp+arg_10]; enum RECHECK_TYPE *
0x180038632  xor     edx, edx; struct CDetectoid *
0x180038634  mov     qword ptr [rbp+arg_18.dwLowDateTime], r12
0x180038638  mov     dword ptr [rbp+arg_10], 2
0x18003863f  call    ?Contains@CRecheckQueue@@AEAAHPEAVCDetectoid@@PEAW4RECHECK_TYPE@@@Z; CRecheckQueue::Contains(CDetectoid *,RECHECK_TYPE *)
0x180038644  test    eax, eax
0x180038646  jnz     loc_1800387A4
0x18003864c  lea     r8, [rbp+arg_18]; struct _FILETIME *
0x180038650  mov     edx, 15180h; unsigned int
0x180038655  call    ?CalculateNowPlusSeconds@CThirdPartyMonitoring@@AEAAJKPEAU_FILETIME@@@Z; CThirdPartyMonitoring::CalculateNowPlusSeconds(ulong,_FILETIME *)
0x18003865a  test    eax, eax
0x18003865c  js      loc_1800387A4
0x180038662  mov     rcx, [rbx+440h]
0x180038669  lea     r9, [rbp+arg_18]
0x18003866d  xor     edx, edx
0x18003866f  lea     r8d, [rdx+2]
0x180038673  call    ?Push@CRecheckQueue@@QEAAJPEAVCDetectoid@@W4RECHECK_TYPE@@PEBU_FILETIME@@@Z; CRecheckQueue::Push(CDetectoid *,RECHECK_TYPE,_FILETIME const *)
0x180038678  jmp     loc_1800387A4
0x18003867d  cmp     [rdi+38h], r12d
0x180038681  jz      loc_1800387A4
0x180038687  mov     [rbp+arg_18.dwLowDateTime], r12d
0x18003868b  lea     r8, [rbp+arg_10]
0x18003868f  mov     dword ptr [rbp+arg_10], r12d
0x180038693  lea     rdx, [rbp+arg_18]
0x180038697  mov     rax, [rdi]
0x18003869a  mov     rcx, rdi
0x18003869d  mov     rax, [rax+38h]
0x1800386a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a6  test    eax, eax
0x1800386a8  js      loc_1800387A4
0x1800386ae  mov     rsi, [rdi+20h]
0x1800386b2  xor     r15d, r15d
0x1800386b5  cmp     r14d, 1
0x1800386b9  jz      short loc_1800386F4
0x1800386bb  cmp     dword ptr [rbp+arg_10], r15d
0x1800386bf  jz      short loc_1800386F4
0x1800386c1  test    byte ptr [rsi+50h], 10h
0x1800386c5  jz      short loc_1800386F4
0x1800386c7  mov     rcx, [rbx+440h]; this
0x1800386ce  lea     r8, [rbp+var_20]; enum RECHECK_TYPE *
0x1800386d2  mov     rdx, rdi; struct CDetectoid *
0x1800386d5  mov     [rbp+var_20], 1
0x1800386dc  call    ?Contains@CRecheckQueue@@AEAAHPEAVCDetectoid@@PEAW4RECHECK_TYPE@@@Z; CRecheckQueue::Contains(CDetectoid *,RECHECK_TYPE *)
0x1800386e1  test    eax, eax
0x1800386e3  jz      short loc_1800386EE
0x1800386e5  and     dword ptr [rsi+50h], 0FFFFFF0Fh
0x1800386ec  jmp     short loc_1800386F4
0x1800386ee  mov     r12d, 1
0x1800386f4  test    r14d, r14d
0x1800386f7  jz      short loc_180038743
0x1800386f9  xor     r14d, r14d
0x1800386fc  cmp     [rbp+arg_18.dwLowDateTime], r14d
0x180038700  jz      short loc_180038746
0x180038702  mov     rcx, rsi
0x180038705  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x18003870a  cmp     eax, 1000h
0x18003870f  jz      short loc_180038746
0x180038711  mov     rcx, [rbx+440h]; this
0x180038718  lea     r8, [rbp+var_20]; enum RECHECK_TYPE *
0x18003871c  mov     rdx, rdi; struct CDetectoid *
0x18003871f  mov     [rbp+var_20], r14d
0x180038723  call    ?Contains@CRecheckQueue@@AEAAHPEAVCDetectoid@@PEAW4RECHECK_TYPE@@@Z; CRecheckQueue::Contains(CDetectoid *,RECHECK_TYPE *)
0x180038728  test    eax, eax
0x18003872a  jz      short loc_18003873B
0x18003872c  mov     edx, 1000h
0x180038731  mov     rcx, rsi
0x180038734  call    ?SetProductState@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductState(ProductState)
0x180038739  jmp     short loc_180038746
0x18003873b  mov     r15d, 1
0x180038741  jmp     short loc_180038746
0x180038743  xor     r14d, r14d
0x180038746  test    r12d, r12d
0x180038749  jnz     short loc_180038750
0x18003874b  test    r15d, r15d
0x18003874e  jz      short loc_180038784
0x180038750  lea     rax, [rbp+var_20]
0x180038754  mov     [rbp+var_18], r14d
0x180038758  mov     [rsp+60h+var_28], rax; int *
0x18003875d  mov     r9d, r12d; int
0x180038760  lea     rax, [rbp+var_18]
0x180038764  mov     [rbp+var_20], r14d
0x180038768  mov     [rsp+60h+var_30], rax; int *
0x18003876d  mov     r8, rdi; struct CDetectoid *
0x180038770  mov     [rsp+60h+var_38], r14d; int
0x180038775  xor     edx, edx; int
0x180038777  mov     rcx, rbx; this
0x18003877a  mov     [rsp+60h+var_40], r15d; int
0x18003877f  call    ?PushRecheckQueue@CThirdPartyMonitoring@@AEAAJHPEAVCDetectoid@@HHHPEAH1@Z; CThirdPartyMonitoring::PushRecheckQueue(int,CDetectoid *,int,int,int,int *,int *)
0x180038784  mov     r8, rdi
0x180038787  mov     edx, 1
0x18003878c  mov     rcx, rbx
0x18003878f  call    ?UpdateThirdPartyManager@CThirdPartyMonitoring@@AEAAJW4THIRDPARTYACTION@@PEAVCDetectoid@@@Z; CThirdPartyMonitoring::UpdateThirdPartyManager(THIRDPARTYACTION,CDetectoid *)
0x180038794  xor     r12d, r12d
0x180038797  jmp     short loc_1800387A4
0x180038799  mov     rcx, rbx; this
0x18003879c  mov     r13d, r12d
0x18003879f  call    ?ResetTimer@CThirdPartyMonitoring@@AEAAJXZ; CThirdPartyMonitoring::ResetTimer(void)
0x1800387a4  mov     rcx, [rbx+460h]; lpCriticalSection
0x1800387ab  xor     edx, edx; int
0x1800387ad  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x1800387b2  test    r13d, r13d
0x1800387b5  jnz     loc_18003852E
0x1800387bb  mov     rbx, [rsp+60h+arg_0]
0x1800387c3  add     rsp, 60h
0x1800387c7  pop     r15
0x1800387c9  pop     r14
0x1800387cb  pop     r13
0x1800387cd  pop     r12
0x1800387cf  pop     rdi
0x1800387d0  pop     rsi
0x1800387d1  pop     rbp
0x1800387d2  retn
```
