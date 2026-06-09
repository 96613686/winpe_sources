# SAGetNSAccountInformation

- ea: `0x180003500`
- end: `0x1800036ac`
- name: `SAGetNSAccountInformation`
- size: `428`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003500`
- `0x180003ec0`
- `0x180003ef0`
- `0x180003f64`
- `0x180004d84`
- `0x180004e50`
- `0x180005034`
- `0x1800050fc`
- `0x1800053b8`
- `0x1800058f0`
- `0x1800177d0`
- `0x18002b1b4`
- `0x18002b330`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800035b2`
- `RPCRT4!RpcImpersonateClient` at `0x18000356d`
- `RPCRT4!RpcImpersonateClient` at `0x18000356d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SAGetNSAccountInformation(__int64 a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // r14
  bool v5; // r8
  __int64 result; // rax
  RPC_STATUS v7; // eax
  EventManager *v8; // rcx
  int v9; // ebx
  const unsigned __int16 *v10; // rdx
  int v11; // edi
  _bstr_t *DomainAccount; // rax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // r8
  void *v15; // [rsp+20h] [rbp-58h]
  const struct _GUID *v16; // [rsp+28h] [rbp-50h]
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-40h] BYREF
  RPC_STATUS (__stdcall *v19)(); // [rsp+40h] [rbp-38h]

  v4 = a2;
  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  if ( !(_DWORD)v4 )
    return 2147942487LL;
  result = RPCFolderAccessCheck(g_TasksFolderInfo, 1u, v5);
  if ( (int)result >= 0 )
  {
    if ( a3 )
    {
      v7 = RpcImpersonateClient(0);
      v9 = v7;
      if ( v7 )
      {
        EventManager::EvtReport(v8, &IMPERSONATION_FAILURE, L"SAGetNSAccountInformation", v7, v15, v16);
        if ( (v9 & 0x1FFF0000) == 0 && v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return (unsigned int)v9;
      }
      else
      {
        v18[0] = 0;
        v19 = RpcRevertToSelf;
        if ( (unsigned int)IsThreadCallerAnAdmin(0) )
        {
          wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v18);
          v17 = 0;
          v11 = CredStore::ResolveAlias((CredStore *)CredStore::g_pCommonStore, v10, (struct User *)&v17);
          if ( v11 >= 0 )
          {
            if ( User::IsLocalSystem((User *)&v17) )
            {
              *a3 = 0;
              v11 = 1;
            }
            else
            {
              DomainAccount = (_bstr_t *)User::GetDomainAccount(&v17, v18);
              v13 = _bstr_t::length(DomainAccount);
              _bstr_t::~_bstr_t((_bstr_t *)v18);
              if ( (unsigned int)v4 <= v13 )
              {
                v11 = -2147024774;
              }
              else
              {
                v14 = *(const unsigned __int16 **)User::GetDomainAccount(&v17, v18);
                if ( v14 )
                  v14 = *(const unsigned __int16 **)v14;
                StringCchCopyW(a3, v4, v14);
                _bstr_t::~_bstr_t((_bstr_t *)v18);
              }
            }
          }
          wmi::AutoRef<User::UserEntry>::Release(&v17);
          return (unsigned int)v11;
        }
        else
        {
          wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v18);
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
0x180003500  mov     rax, rsp
0x180003503  push    rbx
0x180003504  push    rsi
0x180003505  push    rdi
0x180003506  push    r14
0x180003508  sub     rsp, 58h
0x18000350c  mov     rsi, r8
0x18000350f  mov     r14d, edx
0x180003512  mov     dword ptr [rax+20h], 0
0x180003519  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x18000351e  test    rax, rax
0x180003521  jnz     short loc_18000352D
0x180003523  mov     eax, 80004005h
0x180003528  jmp     loc_1800036A1
0x18000352d  test    r14d, r14d
0x180003530  jnz     short loc_18000353C
0x180003532  mov     eax, 80070057h
0x180003537  jmp     loc_1800036A1
0x18000353c  mov     edx, 1; DesiredAccess
0x180003541  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; lpFileName
0x180003548  call    ?RPCFolderAccessCheck@@YAJPEBGK_N@Z; RPCFolderAccessCheck(ushort const *,ulong,bool)
0x18000354d  mov     [rsp+78h+arg_18], eax
0x180003554  test    eax, eax
0x180003556  js      loc_1800036A1
0x18000355c  test    rsi, rsi
0x18000355f  jnz     short loc_18000356B
0x180003561  mov     eax, 80070057h
0x180003566  jmp     loc_1800036A1
0x18000356b  xor     ecx, ecx; BindingHandle
0x18000356d  call    cs:__imp_RpcImpersonateClient
0x180003573  mov     ebx, eax
0x180003575  test    eax, eax
0x180003577  jz      short loc_1800035B2
0x180003579  mov     r9d, eax; unsigned int
0x18000357c  lea     r8, aSagetnsaccount; "SAGetNSAccountInformation"
0x180003583  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18000358a  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18000358f  test    ebx, 1FFF0000h
0x180003595  jnz     short loc_1800035A4
0x180003597  test    ebx, ebx
0x180003599  jle     short loc_1800035A4
0x18000359b  movzx   ebx, bx
0x18000359e  or      ebx, 80070000h
0x1800035a4  mov     [rsp+78h+arg_18], ebx
0x1800035ab  mov     eax, ebx
0x1800035ad  jmp     loc_1800036A1
0x1800035b2  mov     rax, cs:__imp_RpcRevertToSelf
0x1800035b9  mov     [rsp+78h+var_40], 0
0x1800035be  mov     [rsp+78h+var_38], rax
0x1800035c3  xor     ecx, ecx; void *
0x1800035c5  call    ?IsThreadCallerAnAdmin@@YAHPEAX@Z; IsThreadCallerAnAdmin(void *)
0x1800035ca  lea     rcx, [rsp+78h+var_40]
0x1800035cf  test    eax, eax
0x1800035d1  jnz     short loc_1800035E2
0x1800035d3  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x1800035d8  mov     eax, 80070005h
0x1800035dd  jmp     loc_1800036A1
0x1800035e2  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x1800035e7  mov     [rsp+78h+var_48], 0
0x1800035f0  lea     r8, [rsp+78h+var_48]; struct User *
0x1800035f5  mov     rcx, cs:?g_pCommonStore@CredStore@@0PEAV1@EA; this
0x1800035fc  call    ?ResolveAlias@CredStore@@QEAAJPEBGAEAVUser@@@Z; CredStore::ResolveAlias(ushort const *,User &)
0x180003601  mov     edi, eax
0x180003603  mov     [rsp+78h+arg_18], eax
0x18000360a  test    eax, eax
0x18000360c  js      short loc_18000368B
0x18000360e  lea     rcx, [rsp+78h+var_48]; this
0x180003613  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180003618  test    al, al
0x18000361a  jz      short loc_180003626
0x18000361c  xor     eax, eax
0x18000361e  mov     [rsi], ax
0x180003621  lea     edi, [rax+1]
0x180003624  jmp     short loc_180003684
0x180003626  lea     rdx, [rsp+78h+var_40]
0x18000362b  lea     rcx, [rsp+78h+var_48]
0x180003630  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x180003635  mov     rcx, rax; this
0x180003638  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000363d  mov     ebx, eax
0x18000363f  lea     rcx, [rsp+78h+var_40]; this
0x180003644  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003649  cmp     r14d, ebx
0x18000364c  jbe     short loc_18000367F
0x18000364e  lea     rdx, [rsp+78h+var_40]
0x180003653  lea     rcx, [rsp+78h+var_48]
0x180003658  call    ?GetDomainAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetDomainAccount(void)
0x18000365d  mov     r8, [rax]
0x180003660  test    r8, r8
0x180003663  jz      short loc_180003668
0x180003665  mov     r8, [r8]; unsigned __int16 *
0x180003668  mov     rdx, r14; unsigned __int64
0x18000366b  mov     rcx, rsi; unsigned __int16 *
0x18000366e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003673  lea     rcx, [rsp+78h+var_40]; this
0x180003678  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000367d  jmp     short loc_18000368B
0x18000367f  mov     edi, 8007007Ah
0x180003684  mov     [rsp+78h+arg_18], edi
0x18000368b  lea     rcx, [rsp+78h+var_48]
0x180003690  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180003695  nop
0x180003696  jmp     short loc_18000369F
0x180003698  mov     edi, [rsp+78h+arg_18]
0x18000369f  mov     eax, edi
0x1800036a1  add     rsp, 58h
0x1800036a5  pop     r14
0x1800036a7  pop     rdi
0x1800036a8  pop     rsi
0x1800036a9  pop     rbx
0x1800036aa  retn
```
