# SAGetNSAccountInformation

- ea: `0x1800036a0`
- end: `0x180003852`
- name: `SAGetNSAccountInformation`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800036a0`
- `0x180004090`
- `0x1800040c0`
- `0x180004138`
- `0x180004ff0`
- `0x1800050d0`
- `0x1800052d8`
- `0x1800053bc`
- `0x180005650`
- `0x180005c10`
- `0x180018870`
- `0x18002cdb0`
- `0x18002cf68`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180003758`
- `RPCRT4!RpcImpersonateClient` at `0x18000370d`
- `RPCRT4!RpcImpersonateClient` at `0x18000370d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall SAGetNSAccountInformation(__int64 a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // r14
  __int64 result; // rax
  RPC_STATUS v6; // eax
  EventManager *v7; // rcx
  int v8; // ebx
  const unsigned __int16 *v9; // rdx
  LSTATUS v10; // edi
  _bstr_t *DomainAccount; // rax
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // r8
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-40h] BYREF
  RPC_STATUS (__stdcall *v16)(); // [rsp+40h] [rbp-38h]

  v4 = a2;
  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  if ( !(_DWORD)v4 )
    return 2147942487LL;
  result = RPCFolderAccessCheck(g_TasksFolderInfo, 1u);
  if ( (int)result >= 0 )
  {
    if ( a3 )
    {
      v6 = RpcImpersonateClient(0);
      v8 = v6;
      if ( v6 )
      {
        EventManager::EvtReport(v7, &IMPERSONATION_FAILURE, L"SAGetNSAccountInformation", v6);
        if ( (v8 & 0x1FFF0000) == 0 && v8 > 0 )
          return (unsigned __int16)v8 | 0x80070000;
        return (unsigned int)v8;
      }
      else
      {
        v15[0] = 0;
        v16 = RpcRevertToSelf;
        if ( (unsigned int)IsThreadCallerAnAdmin(0) )
        {
          wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v15);
          v14 = 0;
          v10 = CredStore::ResolveAlias((HKEY *)CredStore::g_pCommonStore, v9, (struct User *)&v14);
          if ( v10 >= 0 )
          {
            if ( User::IsLocalSystem((User *)&v14) )
            {
              *a3 = 0;
              v10 = 1;
            }
            else
            {
              DomainAccount = (_bstr_t *)User::GetDomainAccount(&v14, v15);
              v12 = _bstr_t::length(DomainAccount);
              _bstr_t::~_bstr_t((_bstr_t *)v15);
              if ( (unsigned int)v4 <= v12 )
              {
                v10 = -2147024774;
              }
              else
              {
                v13 = *(const unsigned __int16 **)User::GetDomainAccount(&v14, v15);
                if ( v13 )
                  v13 = *(const unsigned __int16 **)v13;
                StringCchCopyW(a3, v4, v13);
                _bstr_t::~_bstr_t((_bstr_t *)v15);
              }
            }
          }
          wmi::AutoRef<User::UserEntry>::Release(&v14);
          return (unsigned int)v10;
        }
        else
        {
          wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v15);
          return 2147942405LL;
        }
      }
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800036a0  mov     rax, rsp
0x1800036a3  push    rbx
0x1800036a4  push    rsi
0x1800036a5  push    rdi
0x1800036a6  push    r14
0x1800036a8  sub     rsp, 58h
0x1800036ac  mov     rsi, r8
0x1800036af  mov     r14d, edx
0x1800036b2  mov     dword ptr [rax+20h], 0
0x1800036b9  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800036be  test    rax, rax
0x1800036c1  jnz     short loc_1800036CD
0x1800036c3  mov     eax, 80004005h
0x1800036c8  jmp     loc_180003847
0x1800036cd  test    r14d, r14d
0x1800036d0  jnz     short loc_1800036DC
0x1800036d2  mov     eax, 80070057h
0x1800036d7  jmp     loc_180003847
0x1800036dc  mov     edx, 1; DesiredAccess
0x1800036e1  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x1800036e8  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x1800036ed  mov     [rsp+78h+arg_18], eax
0x1800036f4  test    eax, eax
0x1800036f6  js      loc_180003847
0x1800036fc  test    rsi, rsi
0x1800036ff  jnz     short loc_18000370B
0x180003701  mov     eax, 80070057h
0x180003706  jmp     loc_180003847
0x18000370b  xor     ecx, ecx; BindingHandle
0x18000370d  call    cs:__imp_RpcImpersonateClient
0x180003714  nop     dword ptr [rax+rax+00h]
0x180003719  mov     ebx, eax
0x18000371b  test    eax, eax
0x18000371d  jz      short loc_180003758
0x18000371f  mov     r9d, eax; unsigned int
0x180003722  lea     r8, aSagetnsaccount; "SAGetNSAccountInformation"
0x180003729  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180003730  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180003735  test    ebx, 1FFF0000h
0x18000373b  jnz     short loc_18000374A
0x18000373d  test    ebx, ebx
0x18000373f  jle     short loc_18000374A
0x180003741  movzx   ebx, bx
0x180003744  or      ebx, 80070000h
0x18000374a  mov     [rsp+78h+arg_18], ebx
0x180003751  mov     eax, ebx
0x180003753  jmp     loc_180003847
0x180003758  mov     rax, cs:__imp_RpcRevertToSelf
0x18000375f  mov     [rsp+78h+var_40], 0
0x180003764  mov     [rsp+78h+var_38], rax
0x180003769  xor     ecx, ecx; void *
0x18000376b  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x180003770  lea     rcx, [rsp+78h+var_40]
0x180003775  test    eax, eax
0x180003777  jnz     short loc_180003788
0x180003779  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18000377e  mov     eax, 80070005h
0x180003783  jmp     loc_180003847
0x180003788  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18000378d  mov     [rsp+78h+var_48], 0
0x180003796  lea     r8, [rsp+78h+var_48]; struct User *
0x18000379b  mov     rcx, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; this
0x1800037a2  call    ?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z; CredStore::ResolveAlias(ushort const *,User &)
0x1800037a7  mov     edi, eax
0x1800037a9  mov     [rsp+78h+arg_18], eax
0x1800037b0  test    eax, eax
0x1800037b2  js      short loc_180003831
0x1800037b4  lea     rcx, [rsp+78h+var_48]; this
0x1800037b9  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x1800037be  test    al, al
0x1800037c0  jz      short loc_1800037CC
0x1800037c2  xor     eax, eax
0x1800037c4  mov     [rsi], ax
0x1800037c7  lea     edi, [rax+1]
0x1800037ca  jmp     short loc_18000382A
0x1800037cc  lea     rdx, [rsp+78h+var_40]
0x1800037d1  lea     rcx, [rsp+78h+var_48]
0x1800037d6  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x1800037db  mov     rcx, rax; this
0x1800037de  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800037e3  mov     ebx, eax
0x1800037e5  lea     rcx, [rsp+78h+var_40]; this
0x1800037ea  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800037ef  cmp     r14d, ebx
0x1800037f2  jbe     short loc_180003825
0x1800037f4  lea     rdx, [rsp+78h+var_40]
0x1800037f9  lea     rcx, [rsp+78h+var_48]
0x1800037fe  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180003803  mov     r8, [rax]
0x180003806  test    r8, r8
0x180003809  jz      short loc_18000380E
0x18000380b  mov     r8, [r8]; unsigned __int16 *
0x18000380e  mov     rdx, r14; unsigned __int64
0x180003811  mov     rcx, rsi; unsigned __int16 *
0x180003814  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003819  lea     rcx, [rsp+78h+var_40]; this
0x18000381e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003823  jmp     short loc_180003831
0x180003825  mov     edi, 8007007Ah
0x18000382a  mov     [rsp+78h+arg_18], edi
0x180003831  lea     rcx, [rsp+78h+var_48]
0x180003836  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18000383b  nop
0x18000383c  jmp     short loc_180003845
0x18000383e  mov     edi, [rsp+78h+arg_18]
0x180003845  mov     eax, edi
0x180003847  add     rsp, 58h
0x18000384b  pop     r14
0x18000384d  pop     rdi
0x18000384e  pop     rsi
0x18000384f  pop     rbx
0x180003850  retn
```
