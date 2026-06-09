# CWNPConnection::LogSendNetMsg(ulong,ulong,char const *,char const *,long,unsigned __int64,unsigned __int64)

- ea: `0x18004ca68`
- end: `0x18004cc98`
- name: `?LogSendNetMsg@CWNPConnection@@AEAAXKKPEBD0J_K1@Z`
- size: `560`
- prototype: `void __usercall(CWNPConnection *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const char *@<r9>, const char *, int, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004d530`

## callees

- `0x180007440`
- `0x18000fe0c`
- `0x180010698`
- `0x180013308`
- `0x18004a8b0`
- `0x18004a9b8`
- `0x18004ca68`
- `0x180060a78`
- `0x180060a90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004cb99`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004cb99`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWNPConnection::LogSendNetMsg(
        CWNPConnection *this,
        int a2,
        int a3,
        const char *a4,
        const char *a5,
        int a6,
        unsigned __int64 a7,
        unsigned __int64 a8)
{
  const unsigned __int16 *v11; // rdi
  int v12; // edi
  int v13; // eax
  HRESULT Guid; // eax
  int v15; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-E8h]
  int IsLongRunning; // [rsp+60h] [rbp-A8h] BYREF
  int v19; // [rsp+64h] [rbp-A4h] BYREF
  int v20; // [rsp+68h] [rbp-A0h] BYREF
  int v21; // [rsp+70h] [rbp-98h] BYREF
  int v22; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v23[4]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v24[20]; // [rsp+84h] [rbp-84h] BYREF
  _BYTE v25[32]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v26[32]; // [rsp+B8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v11 = (const unsigned __int16 *)a5;
  v22 = a2;
  v21 = a3;
  CAbstractConnection::GetPrecommandRetryProperties(this, v23);
  try
  {
    if ( a2 == 541544016 )
    {
      IsLongRunning = CAbstractConnection::GetIsLongRunning(this);
      v19 = *((_DWORD *)this + 48);
      v20 = *((_DWORD *)this + 22);
      if ( !a5 )
        v11 = &byte_18009A357;
      v12 = std::string::string((__int64)v25, (__int64)v11);
      if ( !a4 )
        a4 = (const char *)&byte_18009A357;
      v13 = std::string::string((__int64)v26, (__int64)a4);
      WpnVerboseTelemetry::SendNetPNGMessage<unsigned long &,std::string,std::string,enum ACSTATE,unsigned int &,_GUID &,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0008,int,long &>(
        (unsigned int)&v21,
        v13,
        v12,
        (unsigned int)&v20,
        (__int64)this + 168,
        (__int64)v24,
        (__int64)&v19,
        (__int64)&IsLongRunning,
        (__int64)&a6);
      std::string::_Tidy_deallocate((__int64)v26);
    }
    else
    {
      if ( a2 == 542395971 )
      {
        if ( *((_BYTE *)this + 188) )
        {
          *((_DWORD *)this + 42) = 1;
          *((_BYTE *)this + 188) = 0;
          Guid = CoCreateGuid((GUID *)((char *)this + 172));
          if ( Guid < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x43B,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconn.cpp",
              (const char *)(unsigned int)Guid,
              v17);
        }
        else
        {
          ++*((_DWORD *)this + 42);
        }
      }
      v20 = CAbstractConnection::GetIsLongRunning(this);
      v19 = *((_DWORD *)this + 48);
      IsLongRunning = *((_DWORD *)this + 22);
      if ( !a5 )
        v11 = &byte_18009A357;
      v15 = std::string::string((__int64)v25, (__int64)v11);
      WpnprvTelemetry::SendNetMsg<unsigned long &,unsigned long &,std::string,enum ACSTATE,unsigned int &,_GUID &,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0008,int,long &,unsigned __int64 &,unsigned __int64 &>(
        (unsigned int)&v22,
        (unsigned int)&v21,
        v15,
        (unsigned int)&IsLongRunning,
        (__int64)this + 168,
        (__int64)v24,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&a6,
        (__int64)&a7,
        (__int64)&a8);
    }
    std::string::_Tidy_deallocate((__int64)v25);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x451,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconn.cpp",
      v16);
  }
}

```

## disassembly

```asm
0x18004ca68  push    rbx
0x18004ca6a  push    rsi
0x18004ca6b  push    rdi
0x18004ca6c  push    r14
0x18004ca6e  sub     rsp, 0E8h
0x18004ca75  mov     rax, cs:__security_cookie
0x18004ca7c  xor     rax, rsp
0x18004ca7f  mov     [rsp+108h+var_30], rax
0x18004ca87  mov     r14, r9
0x18004ca8a  mov     esi, edx
0x18004ca8c  mov     rbx, rcx
0x18004ca8f  mov     rdi, [rsp+108h+arg_20]
0x18004ca97  mov     [rsp+108h+var_90], edx
0x18004ca9b  mov     [rsp+108h+var_98], r8d
0x18004caa0  lea     rdx, [rsp+108h+var_88]
0x18004caa8  call    ?GetPrecommandRetryProperties@CAbstractConnection@@QEAA?AUPrecommandRetryProperties@@XZ; CAbstractConnection::GetPrecommandRetryProperties(void)
0x18004caad  cmp     esi, 20474E50h
0x18004cab3  jnz     loc_18004CB70
0x18004cab9  mov     rcx, rbx; this
0x18004cabc  call    ?GetIsLongRunning@CAbstractConnection@@QEAAHXZ; CAbstractConnection::GetIsLongRunning(void)
0x18004cac1  mov     [rsp+108h+var_A8], eax
0x18004cac5  mov     eax, [rbx+0C0h]
0x18004cacb  mov     [rsp+108h+var_A4], eax
0x18004cacf  mov     eax, [rbx+58h]
0x18004cad2  mov     [rsp+108h+var_A0], eax
0x18004cad6  lea     rsi, byte_18009A357
0x18004cadd  test    rdi, rdi
0x18004cae0  cmovz   rdi, rsi
0x18004cae4  mov     rdx, rdi
0x18004cae7  lea     rcx, [rsp+108h+var_70]
0x18004caef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004caf4  mov     rdi, rax
0x18004caf7  test    r14, r14
0x18004cafa  cmovz   r14, rsi
0x18004cafe  mov     rdx, r14
0x18004cb01  lea     rcx, [rsp+108h+var_50]
0x18004cb09  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004cb0e  lea     rcx, [rbx+0A8h]
0x18004cb15  lea     rdx, [rsp+108h+arg_28]
0x18004cb1d  mov     [rsp+108h+var_C8], rdx
0x18004cb22  lea     rdx, [rsp+108h+var_A8]
0x18004cb27  mov     [rsp+108h+var_D0], rdx
0x18004cb2c  lea     rdx, [rsp+108h+var_A4]
0x18004cb31  mov     [rsp+108h+var_D8], rdx
0x18004cb36  lea     rdx, [rsp+108h+var_84]
0x18004cb3e  mov     [rsp+108h+var_E0], rdx
0x18004cb43  mov     [rsp+108h+var_E8], rcx
0x18004cb48  lea     r9, [rsp+108h+var_A0]
0x18004cb4d  mov     r8, rdi
0x18004cb50  mov     rdx, rax
0x18004cb53  lea     rcx, [rsp+108h+var_98]
0x18004cb58  call    ??$SendNetPNGMessage@AEAKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@W4ACSTATE@@AEAIAEAU_GUID@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@HAEAJ@WpnVerboseTelemetry@@SAXAEAK$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1$$QEAW4ACSTATE@@AEAIAEAU_GUID@@$$QEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@$$QEAHAEAJ@Z; WpnVerboseTelemetry::SendNetPNGMessage<ulong &,std::string,std::string,ACSTATE,uint &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008,int,long &>(ulong &,std::string &&,std::string &&,ACSTATE &&,uint &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008 &&,int &&,long &)
0x18004cb5d  lea     rcx, [rsp+108h+var_50]
0x18004cb65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004cb6a  nop
0x18004cb6b  jmp     loc_18004CC6B
0x18004cb70  cmp     esi, 20544E43h
0x18004cb76  jnz     short loc_18004CBC5
0x18004cb78  cmp     byte ptr [rbx+0BCh], 0
0x18004cb7f  jz      short loc_18004CBBF
0x18004cb81  mov     dword ptr [rbx+0A8h], 1
0x18004cb8b  mov     byte ptr [rbx+0BCh], 0
0x18004cb92  lea     rcx, [rbx+0ACh]; pguid
0x18004cb99  call    cs:__imp_CoCreateGuid
0x18004cb9f  mov     rcx, [rsp+108h]; this
0x18004cba7  test    eax, eax
0x18004cba9  jns     short loc_18004CBC5
0x18004cbab  mov     r9d, eax; char *
0x18004cbae  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004cbb5  mov     edx, 43Bh; void *
0x18004cbba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cbbf  inc     dword ptr [rbx+0A8h]
0x18004cbc5  mov     rcx, rbx; this
0x18004cbc8  call    ?GetIsLongRunning@CAbstractConnection@@QEAAHXZ; CAbstractConnection::GetIsLongRunning(void)
0x18004cbcd  mov     [rsp+108h+var_A0], eax
0x18004cbd1  mov     eax, [rbx+0C0h]
0x18004cbd7  mov     [rsp+108h+var_A4], eax
0x18004cbdb  mov     eax, [rbx+58h]
0x18004cbde  mov     [rsp+108h+var_A8], eax
0x18004cbe2  lea     rsi, byte_18009A357
0x18004cbe9  test    rdi, rdi
0x18004cbec  cmovz   rdi, rsi
0x18004cbf0  mov     rdx, rdi
0x18004cbf3  lea     rcx, [rsp+108h+var_70]
0x18004cbfb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18004cc00  lea     rcx, [rbx+0A8h]
0x18004cc07  lea     rdx, [rsp+108h+arg_38]
0x18004cc0f  mov     [rsp+108h+var_B8], rdx
0x18004cc14  lea     rdx, [rsp+108h+arg_30]
0x18004cc1c  mov     [rsp+108h+var_C0], rdx
0x18004cc21  lea     rdx, [rsp+108h+arg_28]
0x18004cc29  mov     [rsp+108h+var_C8], rdx
0x18004cc2e  lea     rdx, [rsp+108h+var_A0]
0x18004cc33  mov     [rsp+108h+var_D0], rdx
0x18004cc38  lea     rdx, [rsp+108h+var_A4]
0x18004cc3d  mov     [rsp+108h+var_D8], rdx
0x18004cc42  lea     rdx, [rsp+108h+var_84]
0x18004cc4a  mov     [rsp+108h+var_E0], rdx
0x18004cc4f  mov     [rsp+108h+var_E8], rcx
0x18004cc54  lea     r9, [rsp+108h+var_A8]
0x18004cc59  mov     r8, rax
0x18004cc5c  lea     rdx, [rsp+108h+var_98]
0x18004cc61  lea     rcx, [rsp+108h+var_90]
0x18004cc66  call    ??$SendNetMsg@AEAKAEAKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4ACSTATE@@AEAIAEAU_GUID@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@HAEAJAEA_KAEA_K@WpnprvTelemetry@@SAXAEAK0$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAW4ACSTATE@@AEAIAEAU_GUID@@$$QEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@$$QEAHAEAJAEA_K8@Z; WpnprvTelemetry::SendNetMsg<ulong &,ulong &,std::string,ACSTATE,uint &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008,int,long &,unsigned __int64 &,unsigned __int64 &>(ulong &,ulong &,std::string &&,ACSTATE &&,uint &,_GUID &,__MIDL___MIDL_itf_wpntypes_0000_0000_0008 &&,int &&,long &,unsigned __int64 &,unsigned __int64 &)
0x18004cc6b  lea     rcx, [rsp+108h+var_70]
0x18004cc73  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004cc78  nop
0x18004cc79  jmp     short $+2
0x18004cc7b  mov     rcx, [rsp+108h+var_30]
0x18004cc83  xor     rcx, rsp; StackCookie
0x18004cc86  call    __security_check_cookie
0x18004cc8b  add     rsp, 0E8h
0x18004cc92  pop     r14
0x18004cc94  pop     rdi
0x18004cc95  pop     rsi
0x18004cc96  pop     rbx
0x18004cc97  retn
```
