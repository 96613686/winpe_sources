# CVolume::ReopenVolumeHandles(void)

- ea: `0x18000756c`
- end: `0x1800077aa`
- name: `?ReopenVolumeHandles@CVolume@@QEAAHXZ`
- size: `574`
- prototype: `__int64 __fastcall(CVolume *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18000747c`
- `0x18000d0a4`

## callees

- `0x18000131c`
- `0x180001448`
- `0x180002488`
- `0x180004f34`
- `0x1800073a0`
- `0x18000756c`
- `0x1800077b0`
- `0x180008718`
- `0x1800099ec`
- `0x18000a1bc`
- `0x18000b5b0`
- `0x18000c430`
- `0x18000c548`
- `0x18000d39c`
- `0x18000ed1c`
- `0x18000f440`
- `0x18000f6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000759b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000759b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800075bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000763d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011536`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000763d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800077a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011536`

## pseudocode

```c
__int64 __fastcall CVolume::ReopenVolumeHandles(CVolume *this)
{
  unsigned int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // r13
  _DWORD *v4; // r15
  _BYTE *v5; // r12
  _QWORD *v6; // rbx
  int v7; // eax
  unsigned __int16 v8; // ax
  int v9; // ebx
  int v10; // ebx
  int v12; // [rsp+34h] [rbp-54h]

  v2 = 0;
  CTrkWksSvc::RaiseIfStopped(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ++*((_DWORD *)this + 13);
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v4 = (_DWORD *)((char *)this + 56);
  ++*((_DWORD *)this + 14);
  v5 = (char *)this + 16;
  if ( (*((_BYTE *)this + 16) & 8) != 0 || (*v5 & 0x10) != 0 )
    goto LABEL_24;
  v6 = (_QWORD *)((char *)this + 24);
  if ( !*((_QWORD *)this + 3) )
  {
    v10 = OpenVolume((const unsigned __int16 *)this + 30, (void **)this + 3);
    if ( v10 < 0 )
    {
      if ( v10 == -1073741772 )
        CVolume::MarkSelfForDelete(this);
      TrkRaiseNtStatus(v10);
    }
    v6 = (_QWORD *)((char *)this + 24);
  }
  if ( (unsigned int)CObjIdIndexChangeNotifier::AsyncListen((CVolume *)((char *)this + 576)) )
  {
    --*v4;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
    CVolume::RegisterPnPVolumeNotification(this);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
    ++*v4;
  }
  if ( !*v6 )
  {
    TrkRaiseException(-2147467259);
    v7 = v12 + 1;
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
    v5 = (char *)this + 16;
    v4 = (_DWORD *)((char *)this + 56);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)this + 41) )
  {
    v7 = 0;
LABEL_9:
    if ( v7 < 2 )
    {
      v8 = VolChar(*((_DWORD *)this + 12));
      CLogFile::Initialize(
        (CVolume *)((char *)this + 312),
        (const unsigned __int16 *)this + 30,
        *((const struct CTrkWksConfiguration **)this + 4),
        this,
        v8);
      CLog::Initialize(
        (CVolume *)((char *)this + 512),
        *((const struct CTrkWksConfiguration **)this + 4),
        (CVolume *)((char *)this + 312));
    }
    v9 = 1;
    goto LABEL_12;
  }
  v9 = 0;
LABEL_12:
  if ( (*v5 & 4) == 0 )
  {
    CVolume::LoadVolInfo(this);
    *(_DWORD *)v5 |= 4u;
  }
  if ( v9 )
    CVolume::VolumeSanityCheck(this, 0);
  v2 = 1;
LABEL_24:
  --*v4;
  LeaveCriticalSection(v3);
  CVolume::Unlock(this);
  return v2;
}

```

## disassembly

```asm
0x18000756c  mov     rax, rsp
0x18000756f  mov     [rax+8], rcx
0x180007573  push    rbx
0x180007574  push    rsi
0x180007575  push    rdi
0x180007576  push    r12
0x180007578  push    r13
0x18000757a  push    r14
0x18000757c  push    r15
0x18000757e  sub     rsp, 50h
0x180007582  mov     rdi, rcx
0x180007585  xor     esi, esi
0x180007587  mov     [rax-58h], esi
0x18000758a  mov     ebx, esi
0x18000758c  mov     [rax+10h], esi
0x18000758f  call    ?RaiseIfStopped@CTrkWksSvc@@QEBAXXZ; CTrkWksSvc::RaiseIfStopped(void)
0x180007594  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x18000759b  call    cs:__imp_EnterCriticalSection
0x1800075a1  lea     r14d, [rsi+1]
0x1800075a5  add     [rdi+34h], r14d
0x1800075a9  lea     r13, [rdi+0D0h]
0x1800075b0  mov     [rsp+88h+arg_10], r13
0x1800075b8  mov     rcx, r13; lpCriticalSection
0x1800075bb  call    cs:__imp_EnterCriticalSection
0x1800075c1  lea     r15, [rdi+38h]
0x1800075c5  mov     [rsp+88h+var_48], r15
0x1800075ca  add     [r15], r14d
0x1800075cd  mov     eax, r14d
0x1800075d0  mov     [rsp+88h+var_58], eax
0x1800075d4  lea     r12, [rdi+10h]
0x1800075d8  test    byte ptr [r12], 8
0x1800075dd  jnz     loc_18000777E
0x1800075e3  test    byte ptr [r12], 10h
0x1800075e8  jnz     loc_18000777E
0x1800075ee  mov     [rsp+88h+arg_18], r12
0x1800075f6  lea     rbx, [rdi+18h]
0x1800075fa  cmp     [rbx], rsi
0x1800075fd  jz      loc_1800076FA
0x180007603  lea     rcx, [rdi+240h]; this
0x18000760a  call    ?AsyncListen@CObjIdIndexChangeNotifier@@QEAAHXZ; CObjIdIndexChangeNotifier::AsyncListen(void)
0x18000760f  mov     [rsp+88h+var_50], eax
0x180007613  jmp     short loc_180007633
0x180007615  mov     ebx, eax
0x180007617  cmp     eax, 80070003h
0x18000761c  jnz     short loc_18000762B
0x18000761e  mov     rcx, [rsp+88h+arg_0]; this
0x180007626  call    ?MarkSelfForDelete@CVolume@@AEAAXXZ; CVolume::MarkSelfForDelete(void)
0x18000762b  mov     ecx, ebx; int
0x18000762d  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x180007632  nop
0x180007633  test    eax, eax
0x180007635  jz      short loc_180007660
0x180007637  dec     dword ptr [r15]
0x18000763a  mov     rcx, r13; lpCriticalSection
0x18000763d  call    cs:__imp_LeaveCriticalSection
0x180007643  mov     [rsp+88h+var_58], esi
0x180007647  mov     rcx, rdi; this
0x18000764a  call    ?RegisterPnPVolumeNotification@CVolume@@AEAAXXZ; CVolume::RegisterPnPVolumeNotification(void)
0x18000764f  mov     rcx, r13; lpCriticalSection
0x180007652  call    cs:__imp_EnterCriticalSection
0x180007658  add     [r15], r14d
0x18000765b  mov     [rsp+88h+var_58], r14d
0x180007660  cmp     [rbx], rsi
0x180007663  jz      loc_18000772C
0x180007669  cmp     [rdi+148h], rsi
0x180007670  jnz     short loc_1800076F1
0x180007672  mov     eax, esi
0x180007674  mov     [rsp+88h+var_54], eax
0x180007678  cmp     eax, 2
0x18000767b  jge     short loc_1800076CF
0x18000767d  lea     rbx, [rdi+138h]
0x180007684  mov     ecx, [rdi+30h]; int
0x180007687  call    ?VolChar@@YAGJ@Z; VolChar(long)
0x18000768c  lea     rdx, [rdi+3Ch]; unsigned __int16 *
0x180007690  mov     [rsp+88h+var_68], ax; unsigned __int16
0x180007695  mov     r9, rdi; struct PLogFileNotify *
0x180007698  mov     r8, [rdi+20h]; struct CTrkWksConfiguration *
0x18000769c  mov     rcx, rbx; this
0x18000769f  call    ?Initialize@CLogFile@@QEAAXPEBGPEBVCTrkWksConfiguration@@PEAVPLogFileNotify@@G@Z; CLogFile::Initialize(ushort const *,CTrkWksConfiguration const *,PLogFileNotify *,ushort)
0x1800076a4  lea     rcx, [rdi+200h]; this
0x1800076ab  mov     r8, rbx; struct CLogFile *
0x1800076ae  mov     rdx, [rdi+20h]; struct CTrkWksConfiguration *
0x1800076b2  call    ?Initialize@CLog@@QEAAXPEBVCTrkWksConfiguration@@PEAVCLogFile@@@Z; CLog::Initialize(CTrkWksConfiguration const *,CLogFile *)
0x1800076b7  jmp     short loc_1800076CF
0x1800076b9  mov     rdi, [rsp+88h+arg_0]
0x1800076c1  lea     rcx, [rdi+138h]; this
0x1800076c8  call    ?Delete@CLogFile@@QEAAXXZ; CLogFile::Delete(void)
0x1800076cd  jmp     short loc_180007736
0x1800076cf  mov     ebx, r14d
0x1800076d2  test    byte ptr [r12], 4
0x1800076d7  jz      loc_18000775D
0x1800076dd  test    ebx, ebx
0x1800076df  jnz     loc_18000776F
0x1800076e5  mov     ebx, r14d
0x1800076e8  mov     eax, [rsp+88h+var_58]
0x1800076ec  jmp     loc_18000777E
0x1800076f1  mov     ebx, [rsp+88h+arg_8]
0x1800076f8  jmp     short loc_1800076D2
0x1800076fa  lea     rcx, [rdi+3Ch]; unsigned __int16 *
0x1800076fe  mov     rdx, rbx; void **
0x180007701  call    ?OpenVolume@@YAJPEBGPEAPEAX@Z; OpenVolume(ushort const *,void * *)
0x180007706  mov     ebx, eax
0x180007708  test    eax, eax
0x18000770a  js      short loc_180007715
0x18000770c  lea     rbx, [rdi+18h]
0x180007710  jmp     loc_180007603
0x180007715  cmp     ebx, 0C0000034h
0x18000771b  jnz     short loc_180007725
0x18000771d  mov     rcx, rdi; this
0x180007720  call    ?MarkSelfForDelete@CVolume@@AEAAXXZ; CVolume::MarkSelfForDelete(void)
0x180007725  mov     ecx, ebx; int
0x180007727  call    ?TrkRaiseNtStatus@@YAXJ@Z; TrkRaiseNtStatus(long)
0x18000772c  mov     ecx, 80004005h; int
0x180007731  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x180007736  mov     eax, [rsp+88h+var_54]
0x18000773a  mov     r14d, 1
0x180007740  add     eax, r14d
0x180007743  mov     r13, [rsp+88h+arg_10]
0x18000774b  mov     r12, [rsp+88h+arg_18]
0x180007753  mov     r15, [rsp+88h+var_48]
0x180007758  jmp     loc_180007674
0x18000775d  mov     rcx, rdi; this
0x180007760  call    ?LoadVolInfo@CVolume@@AEAAXXZ; CVolume::LoadVolInfo(void)
0x180007765  or      dword ptr [r12], 4
0x18000776a  jmp     loc_1800076DD
0x18000776f  xor     edx, edx; int
0x180007771  mov     rcx, rdi; this
0x180007774  call    ?VolumeSanityCheck@CVolume@@AEAAXH@Z; CVolume::VolumeSanityCheck(int)
0x180007779  jmp     loc_1800076E5
0x18000777e  test    eax, eax
0x180007780  jnz     short loc_18000779C
0x180007782  mov     rcx, rdi; this
0x180007785  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x18000778a  mov     eax, ebx
0x18000778c  add     rsp, 50h
0x180007790  pop     r15
0x180007792  pop     r14
0x180007794  pop     r13
0x180007796  pop     r12
0x180007798  pop     rdi
0x180007799  pop     rsi
0x18000779a  pop     rbx
0x18000779b  retn
0x18000779c  dec     dword ptr [r15]
0x18000779f  mov     rcx, r13; lpCriticalSection
0x1800077a2  call    cs:__imp_LeaveCriticalSection
0x1800077a8  jmp     short loc_180007782
0x18001149c  push    rbp
0x18001149e  sub     rsp, 30h
0x1800114a2  mov     rbp, rdx
0x1800114a5  mov     eax, 1
0x1800114aa  add     rsp, 30h
0x1800114ae  pop     rbp
0x1800114af  retn
0x1800114b1  push    rbp
0x1800114b3  sub     rsp, 30h
0x1800114b7  mov     rbp, rdx
0x1800114ba  mov     rax, [rcx]
0x1800114bd  cmp     dword ptr [rbp+34h], 0
0x1800114c1  jnz     short loc_1800114D2
0x1800114c3  cmp     dword ptr [rax], 8DEAD001h
0x1800114c9  jnz     short loc_1800114D2
0x1800114cb  mov     eax, 1
0x1800114d0  jmp     short loc_1800114D4
0x1800114d2  xor     eax, eax
0x1800114d4  add     rsp, 30h
0x1800114d8  pop     rbp
0x1800114d9  retn
0x1800114db  push    rbp
0x1800114dd  sub     rsp, 30h
0x1800114e1  mov     rbp, rdx
0x1800114e4  movzx   eax, cl
0x1800114e7  test    cl, cl
0x1800114e9  jz      short loc_18001151A
0x1800114eb  xor     edx, edx
0x1800114ed  lea     r8d, [rdx+2]
0x1800114f1  mov     rcx, [rbp+90h]
0x1800114f8  call    ?CloseVolumeHandles@CVolume@@QEAAXPEAXW4EHandleChangeReason@1@@Z; CVolume::CloseVolumeHandles(void *,CVolume::EHandleChangeReason)
0x1800114fd  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180011504  test    byte ptr [rcx+254h], 1
0x18001150b  jz      short loc_18001151A
0x18001150d  add     rcx, 258h; this
0x180011514  call    ?SetRecurring@CNewTimer@@QEAAXXZ; CNewTimer::SetRecurring(void)
0x180011519  nop
0x18001151a  cmp     dword ptr [rbp+30h], 0
0x18001151e  jz      short loc_18001153D
0x180011520  mov     rcx, [rbp+90h]
0x180011527  mov     eax, [rcx+38h]
0x18001152a  dec     eax
0x18001152c  mov     [rcx+38h], eax
0x18001152f  add     rcx, 0D0h; lpCriticalSection
0x180011536  call    cs:__imp_LeaveCriticalSection
0x18001153c  nop
0x18001153d  mov     rcx, [rbp+90h]; this
0x180011544  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x180011549  nop
0x18001154a  add     rsp, 30h
0x18001154e  pop     rbp
0x18001154f  retn
```
