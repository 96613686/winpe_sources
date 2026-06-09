# ?Delete@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x180010bd0`
- end: `0x180010e3e`
- name: `?Delete@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `622`
- prototype: `void __fastcall(__int64, RpcSession *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001ab0`
- `0x180004da4`
- `0x1800053b8`
- `0x1800058f0`
- `0x18000635c`
- `0x1800064bc`
- `0x18000a994`
- `0x18000bd7c`
- `0x18000c760`
- `0x18000c8b4`
- `0x18000c8f4`
- `0x1800104d0`
- `0x180010bd0`
- `0x180010e44`
- `0x1800113cc`
- `0x180023400`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010d38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010e04`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010e04`

## pseudocode

```c
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
  void *v13; // [rsp+20h] [rbp-488h]
  const struct _GUID *v14; // [rsp+28h] [rbp-480h]
  _BYTE v15[4]; // [rsp+34h] [rbp-474h] BYREF
  RpcSession *v16[5]; // [rsp+38h] [rbp-470h] BYREF
  _BYTE v17[528]; // [rsp+60h] [rbp-448h] BYREF
  unsigned __int16 v18; // [rsp+270h] [rbp-238h] BYREF
  char v19; // [rsp+272h] [rbp-236h] BYREF

  v16[1] = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
  }
  if ( CompatibilityAdapter::GetAdapter() )
  {
    TaskLock::TaskLock((TaskLock *)v17, (const unsigned __int16 *)a2);
    v4 = (RpcSession *)(a1 + 16);
    v16[2] = v4;
    v16[3] = v4;
    WaitForSingleObject(*(HANDLE *)v4, 0xFFFFFFFF);
    v6 = SignatureStore::Exists((const unsigned __int16 *)a2);
    if ( v6 >= 0 )
    {
      memset_0(&v18, 0, 0x20Au);
      v7 = FilenameToUri((const unsigned __int16 *)a2, &v18);
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
        TaskLock::~TaskLock((TaskLock *)v17);
        return;
      }
      CompatibilityAdapter::GetSession(v8, v16);
      v9 = (unsigned __int16 *)&v19;
      if ( v18 != 92 )
        v9 = &v18;
      v10 = DeletionGuard::s_pLock;
      EnterCriticalSection(DeletionGuard::s_pLock);
      DeletionGuard::s_name = v9;
      LeaveCriticalSection(v10);
      v6 = RpcSession::Delete(v16[0], &v18, v11);
      if ( v6 >= 0 )
        v6 = SignatureStore::Delete((OLECHAR *)a2);
      DeletionGuard::~DeletionGuard((DeletionGuard *)v15);
      if ( v16[0] )
        wmi::RefBase::Release(v16[0]);
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
      EventManager::EvtReport(v12, &COMPAT_TASK_DELETE_FAILED, (const unsigned __int16 *)a2, v6, v13, v14);
    }
    ReleaseMutex(*(HANDLE *)v4);
    TaskLock::~TaskLock((TaskLock *)v17);
  }
}

```

## disassembly

```asm
0x180010bd0  mov     [rsp+arg_0], rbx
0x180010bd5  mov     [rsp+arg_10], rsi
0x180010bda  push    rdi
0x180010bdb  push    r14
0x180010bdd  push    r15
0x180010bdf  sub     rsp, 490h
0x180010be6  mov     rax, cs:__security_cookie
0x180010bed  xor     rax, rsp
0x180010bf0  mov     [rsp+4A8h+var_28], rax
0x180010bf8  mov     r14, rdx
0x180010bfb  mov     rdi, rcx
0x180010bfe  mov     [rsp+4A8h+var_468], rdx
0x180010c03  mov     [rsp+4A8h+var_478], 0
0x180010c0b  lea     r15, WPP_GLOBAL_Control
0x180010c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c19  cmp     rcx, r15
0x180010c1c  jz      short loc_180010C42
0x180010c1e  test    byte ptr [rcx+1Ch], 2
0x180010c22  jz      short loc_180010C42
0x180010c24  cmp     byte ptr [rcx+19h], 4
0x180010c28  jb      short loc_180010C42
0x180010c2a  mov     edx, 24h ; '$'
0x180010c2f  mov     r9, r14
0x180010c32  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010c39  mov     rcx, [rcx+10h]
0x180010c3d  call    WPP_SF_S
0x180010c42  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180010c47  test    rax, rax
0x180010c4a  jz      loc_180010E15
0x180010c50  mov     rdx, r14; unsigned __int16 *
0x180010c53  lea     rcx, [rsp+4A8h+var_448]; this
0x180010c58  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x180010c5d  nop
0x180010c5e  add     rdi, 10h
0x180010c62  mov     [rsp+4A8h+var_460], rdi
0x180010c67  mov     [rsp+4A8h+var_458], rdi
0x180010c6c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010c6f  mov     rcx, [rdi]; hHandle
0x180010c72  call    cs:__imp_WaitForSingleObject
0x180010c78  nop
0x180010c79  mov     rcx, r14; unsigned __int16 *
0x180010c7c  call    ?Exists@SignatureStore@@SAJPEBG@Z; SignatureStore::Exists(ushort const *)
0x180010c81  mov     ebx, eax
0x180010c83  mov     [rsp+4A8h+var_478], eax
0x180010c87  test    eax, eax
0x180010c89  js      loc_180010D94
0x180010c8f  xor     edx, edx; Val
0x180010c91  mov     r8d, 20Ah; Size
0x180010c97  lea     rcx, [rsp+4A8h+var_238]; void *
0x180010c9f  call    memset_0
0x180010ca4  lea     rdx, [rsp+4A8h+var_238]; unsigned __int16 *
0x180010cac  mov     rcx, r14; unsigned __int16 *
0x180010caf  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x180010cb4  mov     [rsp+4A8h+var_478], eax
0x180010cb8  test    eax, eax
0x180010cba  jns     short loc_180010D06
0x180010cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cc3  cmp     rcx, r15
0x180010cc6  jz      short loc_180010CED
0x180010cc8  test    byte ptr [rcx+1Ch], 2
0x180010ccc  jz      short loc_180010CED
0x180010cce  cmp     byte ptr [rcx+19h], 2
0x180010cd2  jb      short loc_180010CED
0x180010cd4  mov     edx, 25h ; '%'
0x180010cd9  mov     r9d, eax
0x180010cdc  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010ce3  mov     rcx, [rcx+10h]
0x180010ce7  call    WPP_SF_d
0x180010cec  nop
0x180010ced  mov     rcx, [rdi]; hMutex
0x180010cf0  call    cs:__imp_ReleaseMutex
0x180010cf6  nop
0x180010cf7  lea     rcx, [rsp+4A8h+var_448]; this
0x180010cfc  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180010d01  jmp     loc_180010E15
0x180010d06  lea     rdx, [rsp+4A8h+var_470]
0x180010d0b  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x180010d10  nop
0x180010d11  lea     rsi, [rsp+4A8h+var_236]
0x180010d19  lea     rax, [rsp+4A8h+var_238]
0x180010d21  cmp     [rsp+4A8h+var_238], 5Ch ; '\'
0x180010d2a  cmovnz  rsi, rax
0x180010d2e  mov     rbx, cs:?s_pLock@DeletionGuard@@0PEAVCritSec@wmi@@EA; wmi::CritSec * DeletionGuard::s_pLock
0x180010d35  mov     rcx, rbx; lpCriticalSection
0x180010d38  call    cs:__imp_EnterCriticalSection
0x180010d3e  mov     cs:?s_name@DeletionGuard@@0PEBGEB, rsi; ushort const * const DeletionGuard::s_name
0x180010d45  mov     rcx, rbx; lpCriticalSection
0x180010d48  call    cs:__imp_LeaveCriticalSection
0x180010d4e  nop
0x180010d4f  lea     rdx, [rsp+4A8h+var_238]; unsigned __int16 *
0x180010d57  mov     rcx, [rsp+4A8h+var_470]; this
0x180010d5c  call    ?Delete@RpcSession@@QEBAJPEBGK@Z; RpcSession::Delete(ushort const *,ulong)
0x180010d61  mov     ebx, eax
0x180010d63  mov     [rsp+4A8h+var_478], eax
0x180010d67  test    eax, eax
0x180010d69  js      short loc_180010D79
0x180010d6b  mov     rcx, r14; psz
0x180010d6e  call    ?Delete@SignatureStore@@SAJPEBG@Z; SignatureStore::Delete(ushort const *)
0x180010d73  mov     ebx, eax
0x180010d75  mov     [rsp+4A8h+var_478], eax
0x180010d79  lea     rcx, [rsp+4A8h+var_474]; this
0x180010d7e  call    ??1DeletionGuard@@QEAA@XZ; DeletionGuard::~DeletionGuard(void)
0x180010d83  nop
0x180010d84  mov     rcx, [rsp+4A8h+var_470]; this
0x180010d89  test    rcx, rcx
0x180010d8c  jz      short loc_180010D94
0x180010d8e  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180010d93  nop
0x180010d94  jmp     short loc_180010DAB
0x180010d96  lea     r15, WPP_GLOBAL_Control
0x180010d9d  mov     ebx, [rsp+4A8h+var_478]
0x180010da1  mov     r14, [rsp+4A8h+var_468]
0x180010da6  mov     rdi, [rsp+4A8h+var_460]
0x180010dab  test    ebx, ebx
0x180010dad  jns     short loc_180010E01
0x180010daf  mov     ecx, ebx; this
0x180010db1  call    ?IsErrorNotFound@tsched@@YA_NJ@Z; tsched::IsErrorNotFound(long)
0x180010db6  test    al, al
0x180010db8  jnz     short loc_180010E01
0x180010dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dc1  cmp     rcx, r15
0x180010dc4  jz      short loc_180010DEE
0x180010dc6  test    byte ptr [rcx+1Ch], 2
0x180010dca  jz      short loc_180010DEE
0x180010dcc  cmp     byte ptr [rcx+19h], 2
0x180010dd0  jb      short loc_180010DEE
0x180010dd2  mov     edx, 26h ; '&'
0x180010dd7  mov     dword ptr [rsp+4A8h+var_488], ebx; void *
0x180010ddb  mov     r9, r14
0x180010dde  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010de5  mov     rcx, [rcx+10h]
0x180010de9  call    WPP_SF_SD
0x180010dee  mov     r9d, ebx; unsigned int
0x180010df1  mov     r8, r14; unsigned __int16 *
0x180010df4  lea     rdx, COMPAT_TASK_DELETE_FAILED; struct _EVENT_DESCRIPTOR *
0x180010dfb  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180010e00  nop
0x180010e01  mov     rcx, [rdi]; hMutex
0x180010e04  call    cs:__imp_ReleaseMutex
0x180010e0a  nop
0x180010e0b  lea     rcx, [rsp+4A8h+var_448]; this
0x180010e10  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180010e15  mov     rcx, [rsp+4A8h+var_28]
0x180010e1d  xor     rcx, rsp; StackCookie
0x180010e20  call    __security_check_cookie
0x180010e25  lea     r11, [rsp+4A8h+var_18]
0x180010e2d  mov     rbx, [r11+20h]
0x180010e31  mov     rsi, [r11+30h]
0x180010e35  mov     rsp, r11
0x180010e38  pop     r15
0x180010e3a  pop     r14
0x180010e3c  pop     rdi
0x180010e3d  retn
```
