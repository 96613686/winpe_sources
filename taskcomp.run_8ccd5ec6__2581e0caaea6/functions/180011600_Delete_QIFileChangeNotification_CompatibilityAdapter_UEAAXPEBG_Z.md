# ?Delete@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x180011600`
- end: `0x18001188d`
- name: `?Delete@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001b00`
- `0x180005010`
- `0x180005650`
- `0x180005c10`
- `0x180006764`
- `0x1800068e4`
- `0x18000af88`
- `0x18000c588`
- `0x18000cf80`
- `0x18000d0e8`
- `0x18000d128`
- `0x180010ec4`
- `0x180011600`
- `0x180011894`
- `0x180011e6c`
- `0x180024a30`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011774`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011774`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800116a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800116a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001178a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001178a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011726`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001184c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011726`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001184c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall _Delete__QIFileChangeNotification__CompatibilityAdapter__UEAAXPEBG_Z(__int64 a1, RpcSession *a2)
{
  RpcSession *v4; // rdi
  int v5; // edx
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  unsigned __int16 *v9; // rsi
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  unsigned int v11; // r8d
  EventManager *v12; // rcx
  _BYTE v13[4]; // [rsp+34h] [rbp-474h] BYREF
  RpcSession *v14[5]; // [rsp+38h] [rbp-470h] BYREF
  _BYTE v15[528]; // [rsp+60h] [rbp-448h] BYREF
  unsigned __int16 v16; // [rsp+270h] [rbp-238h] BYREF
  char v17; // [rsp+272h] [rbp-236h] BYREF

  v14[1] = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
  }
  if ( CompatibilityAdapter::GetAdapter() )
  {
    TaskLock::TaskLock((TaskLock *)v15, (const unsigned __int16 *)a2);
    v4 = (RpcSession *)(a1 + 16);
    v14[2] = v4;
    v14[3] = v4;
    WaitForSingleObject(*(HANDLE *)v4, 0xFFFFFFFF);
    v6 = SignatureStore::Exists((const unsigned __int16 *)a2);
    if ( v6 >= 0 )
    {
      memset_0(&v16, 0, 0x20Au);
      v7 = FilenameToUri((const unsigned __int16 *)a2, &v16);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
            (unsigned int)v7);
        }
        ReleaseMutex(*(HANDLE *)v4);
        TaskLock::~TaskLock((TaskLock *)v15);
        return;
      }
      CompatibilityAdapter::GetSession(v8, v14);
      v9 = (unsigned __int16 *)&v17;
      if ( v16 != 92 )
        v9 = &v16;
      v10 = DeletionGuard::s_pLock;
      EnterCriticalSection(DeletionGuard::s_pLock);
      DeletionGuard::s_name = v9;
      LeaveCriticalSection(v10);
      v6 = RpcSession::Delete(v14[0], &v16, v11);
      if ( v6 >= 0 )
        v6 = SignatureStore::Delete((OLECHAR *)a2);
      DeletionGuard::~DeletionGuard((DeletionGuard *)v13);
      if ( v14[0] )
        wmi::RefBase::Release(v14[0]);
    }
    if ( v6 < 0 && !tsched::IsErrorNotFound((tsched *)(unsigned int)v6, v5) )
    {
      v12 = (EventManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v6);
      }
      EventManager::EvtReport(v12, &COMPAT_TASK_DELETE_FAILED, (const unsigned __int16 *)a2, v6);
    }
    ReleaseMutex(*(HANDLE *)v4);
    TaskLock::~TaskLock((TaskLock *)v15);
  }
}

```

## disassembly

```asm
0x180011600  mov     [rsp+arg_0], rbx
0x180011605  mov     [rsp+arg_10], rsi
0x18001160a  push    rdi
0x18001160b  push    r14
0x18001160d  push    r15
0x18001160f  sub     rsp, 490h
0x180011616  mov     rax, cs:__security_cookie
0x18001161d  xor     rax, rsp
0x180011620  mov     [rsp+4A8h+var_28], rax
0x180011628  mov     r14, rdx
0x18001162b  mov     rdi, rcx
0x18001162e  mov     [rsp+4A8h+var_468], rdx
0x180011633  mov     [rsp+4A8h+var_478], 0
0x18001163b  lea     r15, WPP_GLOBAL_Control
0x180011642  mov     rcx, cs:WPP_GLOBAL_Control
0x180011649  cmp     rcx, r15
0x18001164c  jz      short loc_180011672
0x18001164e  test    byte ptr [rcx+1Ch], 2
0x180011652  jz      short loc_180011672
0x180011654  cmp     byte ptr [rcx+19h], 4
0x180011658  jb      short loc_180011672
0x18001165a  mov     edx, 24h ; '$'
0x18001165f  mov     r9, r14
0x180011662  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011669  mov     rcx, [rcx+10h]
0x18001166d  call    WPP_SF_S
0x180011672  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180011677  test    rax, rax
0x18001167a  jz      loc_180011863
0x180011680  mov     rdx, r14; unsigned __int16 *
0x180011683  lea     rcx, [rsp+4A8h+var_448]; this
0x180011688  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x18001168d  nop
0x18001168e  add     rdi, 10h
0x180011692  mov     [rsp+4A8h+var_460], rdi
0x180011697  mov     [rsp+4A8h+var_458], rdi
0x18001169c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001169f  mov     rcx, [rdi]; hHandle
0x1800116a2  call    cs:__imp_WaitForSingleObject
0x1800116a9  nop     dword ptr [rax+rax+00h]
0x1800116ae  nop
0x1800116af  mov     rcx, r14; unsigned __int16 *
0x1800116b2  call    ?Exists@SignatureStore@@SAJPEBG@Z; SignatureStore::Exists(ushort const *)
0x1800116b7  mov     ebx, eax
0x1800116b9  mov     [rsp+4A8h+var_478], eax
0x1800116bd  test    eax, eax
0x1800116bf  js      loc_1800117DC
0x1800116c5  xor     edx, edx; Val
0x1800116c7  mov     r8d, 20Ah; Size
0x1800116cd  lea     rcx, [rsp+4A8h+var_238]; void *
0x1800116d5  call    memset_0
0x1800116da  lea     rdx, [rsp+4A8h+var_238]; unsigned __int16 *
0x1800116e2  mov     rcx, r14; unsigned __int16 *
0x1800116e5  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x1800116ea  mov     [rsp+4A8h+var_478], eax
0x1800116ee  test    eax, eax
0x1800116f0  jns     short loc_180011742
0x1800116f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116f9  cmp     rcx, r15
0x1800116fc  jz      short loc_180011723
0x1800116fe  test    byte ptr [rcx+1Ch], 2
0x180011702  jz      short loc_180011723
0x180011704  cmp     byte ptr [rcx+19h], 2
0x180011708  jb      short loc_180011723
0x18001170a  mov     edx, 25h ; '%'
0x18001170f  mov     r9d, eax
0x180011712  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011719  mov     rcx, [rcx+10h]
0x18001171d  call    WPP_SF_d
0x180011722  nop
0x180011723  mov     rcx, [rdi]; hMutex
0x180011726  call    cs:__imp_ReleaseMutex
0x18001172d  nop     dword ptr [rax+rax+00h]
0x180011732  nop
0x180011733  lea     rcx, [rsp+4A8h+var_448]; this
0x180011738  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001173d  jmp     loc_180011863
0x180011742  lea     rdx, [rsp+4A8h+var_470]
0x180011747  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x18001174c  nop
0x18001174d  lea     rsi, [rsp+4A8h+var_236]
0x180011755  lea     rax, [rsp+4A8h+var_238]
0x18001175d  cmp     [rsp+4A8h+var_238], 5Ch ; '\'
0x180011766  cmovnz  rsi, rax
0x18001176a  mov     rbx, cs:?s_pLock@DeletionGuard@@0PEAVCritSec@wmi@@EA; wmi::CritSec * DeletionGuard::s_pLock
0x180011771  mov     rcx, rbx; lpCriticalSection
0x180011774  call    cs:__imp_EnterCriticalSection
0x18001177b  nop     dword ptr [rax+rax+00h]
0x180011780  mov     cs:?s_name@DeletionGuard@@0PEBGEB, rsi; ushort const * const DeletionGuard::s_name
0x180011787  mov     rcx, rbx; lpCriticalSection
0x18001178a  call    cs:__imp_LeaveCriticalSection
0x180011791  nop     dword ptr [rax+rax+00h]
0x180011796  nop
0x180011797  lea     rdx, [rsp+4A8h+var_238]; unsigned __int16 *
0x18001179f  mov     rcx, [rsp+4A8h+var_470]; this
0x1800117a4  call    ?Delete@RpcSession@@QEBAJPEBGK@Z; RpcSession::Delete(ushort const *,ulong)
0x1800117a9  mov     ebx, eax
0x1800117ab  mov     [rsp+4A8h+var_478], eax
0x1800117af  test    eax, eax
0x1800117b1  js      short loc_1800117C1
0x1800117b3  mov     rcx, r14; psz
0x1800117b6  call    ?Delete@SignatureStore@@SAJPEBG@Z; SignatureStore::Delete(ushort const *)
0x1800117bb  mov     ebx, eax
0x1800117bd  mov     [rsp+4A8h+var_478], eax
0x1800117c1  lea     rcx, [rsp+4A8h+var_474]; this
0x1800117c6  call    ??1DeletionGuard@@QEAA@XZ; DeletionGuard::~DeletionGuard(void)
0x1800117cb  nop
0x1800117cc  mov     rcx, [rsp+4A8h+var_470]; this
0x1800117d1  test    rcx, rcx
0x1800117d4  jz      short loc_1800117DC
0x1800117d6  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800117db  nop
0x1800117dc  jmp     short loc_1800117F3
0x1800117de  lea     r15, WPP_GLOBAL_Control
0x1800117e5  mov     ebx, [rsp+4A8h+var_478]
0x1800117e9  mov     r14, [rsp+4A8h+var_468]
0x1800117ee  mov     rdi, [rsp+4A8h+var_460]
0x1800117f3  test    ebx, ebx
0x1800117f5  jns     short loc_180011849
0x1800117f7  mov     ecx, ebx; this
0x1800117f9  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x1800117fe  test    al, al
0x180011800  jnz     short loc_180011849
0x180011802  mov     rcx, cs:WPP_GLOBAL_Control
0x180011809  cmp     rcx, r15
0x18001180c  jz      short loc_180011836
0x18001180e  test    byte ptr [rcx+1Ch], 2
0x180011812  jz      short loc_180011836
0x180011814  cmp     byte ptr [rcx+19h], 2
0x180011818  jb      short loc_180011836
0x18001181a  mov     edx, 26h ; '&'
0x18001181f  mov     dword ptr [rsp+4A8h+var_488], ebx; void *
0x180011823  mov     r9, r14
0x180011826  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001182d  mov     rcx, [rcx+10h]
0x180011831  call    WPP_SF_SD
0x180011836  mov     r9d, ebx; unsigned int
0x180011839  mov     r8, r14; unsigned __int16 *
0x18001183c  lea     rdx, COMPAT_TASK_DELETE_FAILED; struct _EVENT_DESCRIPTOR *
0x180011843  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180011848  nop
0x180011849  mov     rcx, [rdi]; hMutex
0x18001184c  call    cs:__imp_ReleaseMutex
0x180011853  nop     dword ptr [rax+rax+00h]
0x180011858  nop
0x180011859  lea     rcx, [rsp+4A8h+var_448]; this
0x18001185e  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180011863  mov     rcx, [rsp+4A8h+var_28]
0x18001186b  xor     rcx, rsp; StackCookie
0x18001186e  call    __security_check_cookie
0x180011873  lea     r11, [rsp+4A8h+var_18]
0x18001187b  mov     rbx, [r11+20h]
0x18001187f  mov     rsi, [r11+30h]
0x180011883  mov     rsp, r11
0x180011886  pop     r15
0x180011888  pop     r14
0x18001188a  pop     rdi
0x18001188b  retn
```
