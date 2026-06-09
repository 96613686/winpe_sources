# CompatibilityAdapter::GetUserInfo(ushort const *,_bstr_t &,bool &)

- ea: `0x18000aabc`
- end: `0x18000abc1`
- name: `?GetUserInfo@CompatibilityAdapter@@QEAAJPEBGAEAV_bstr_t@@AEA_N@Z`
- size: `261`
- prototype: `__int64 __fastcall(CompatibilityAdapter *this, const unsigned __int16 *, struct _bstr_t *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004820`
- `0x18000ac28`

## callees

- `0x180007488`
- `0x180009c00`
- `0x180009cd4`
- `0x180009d18`
- `0x18000a994`
- `0x18000aabc`
- `0x18000bd7c`
- `0x18001c0f4`
- `0x180020118`
- `0x18002352c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab9a`

## pseudocode

```c
__int64 __fastcall CompatibilityAdapter::GetUserInfo(
        CompatibilityAdapter *this,
        const unsigned __int16 *a2,
        struct _bstr_t *a3,
        bool *a4)
{
  const unsigned __int16 *v7; // r8
  int Task; // ebx
  volatile signed __int32 *v9; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  RpcSession *v13; // [rsp+40h] [rbp-38h] BYREF
  volatile signed __int32 *v14; // [rsp+48h] [rbp-30h] BYREF
  _QWORD v15[5]; // [rsp+50h] [rbp-28h] BYREF
  CompatibilityAdapter *v16; // [rsp+A0h] [rbp+28h] BYREF

  v16 = this;
  CompatibilityAdapter::GetSession(this, &v13);
  LODWORD(v16) = 0;
  hMem = 0;
  Task = RpcSession::RetrieveTask(v13, a2, v7, (unsigned int *)&v16, (struct RpcString *)&hMem);
  if ( Task >= 0 )
  {
    v12 = 0;
    Task = StringReader::CreateStream(hMem, &v12);
    if ( Task >= 0 )
    {
      v9 = (volatile signed __int32 *)operator new(0x460u);
      v14 = v9;
      if ( v9 )
      {
        v9 = (volatile signed __int32 *)TaskXmlReader::TaskXmlReader(v9, &v12);
        v14 = v9;
        if ( v9 )
          _InterlockedIncrement(v9 + 2);
      }
      else
      {
        v14 = 0;
      }
      v15[0] = &UserXmlHandler::`vftable';
      v15[1] = a3;
      v15[2] = a4;
      *a4 = 0;
      Task = TaskXmlReader::ProcessXml((TaskXmlReader *)v9, (struct ITaskXmlHandler *)v15);
      wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v14);
    }
    ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v12);
  }
  LocalFree(hMem);
  hMem = 0;
  if ( v13 )
    wmi::RefBase::Release(v13);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x18000aabc  mov     [rsp-20h+arg_0], rcx
0x18000aac1  push    rbp
0x18000aac2  push    rbx
0x18000aac3  push    rsi
0x18000aac4  push    rdi
0x18000aac5  mov     rbp, rsp
0x18000aac8  sub     rsp, 78h
0x18000aacc  mov     rdi, r9
0x18000aacf  mov     rsi, r8
0x18000aad2  mov     rbx, rdx
0x18000aad5  lea     rdx, [rbp+var_38]
0x18000aad9  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x18000aade  nop
0x18000aadf  mov     dword ptr [rbp+arg_0], 0
0x18000aae6  mov     [rbp+hMem], 0
0x18000aaee  lea     rax, [rbp+hMem]
0x18000aaf2  mov     [rsp+78h+var_58], rax; struct RpcString *
0x18000aaf7  lea     r9, [rbp+arg_0]; unsigned int *
0x18000aafb  mov     rdx, rbx; unsigned __int16 *
0x18000aafe  mov     rcx, [rbp+var_38]; this
0x18000ab02  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18000ab07  mov     ebx, eax
0x18000ab09  test    eax, eax
0x18000ab0b  js      loc_18000AB96
0x18000ab11  mov     [rbp+var_40], 0
0x18000ab19  lea     rdx, [rbp+var_40]
0x18000ab1d  mov     rcx, [rbp+hMem]
0x18000ab21  call    ?CreateStream@StringReader@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; StringReader::CreateStream(ushort const *,_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> &)
0x18000ab26  mov     ebx, eax
0x18000ab28  test    eax, eax
0x18000ab2a  js      short loc_18000AB8C
0x18000ab2c  mov     ecx, 460h; Size
0x18000ab31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab36  mov     [rbp+var_30], rax
0x18000ab3a  test    rax, rax
0x18000ab3d  jz      short loc_18000AB5A
0x18000ab3f  lea     rdx, [rbp+var_40]
0x18000ab43  mov     rcx, rax
0x18000ab46  call    ??0TaskXmlReader@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@PEAPEAE_N@Z; TaskXmlReader::TaskXmlReader(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,uchar * *,bool)
0x18000ab4b  mov     [rbp+var_30], rax
0x18000ab4f  test    rax, rax
0x18000ab52  jz      short loc_18000AB5E
0x18000ab54  lock inc dword ptr [rax+8]
0x18000ab58  jmp     short loc_18000AB5E
0x18000ab5a  mov     [rbp+var_30], rax
0x18000ab5e  lea     rcx, ??_7UserXmlHandler@@6B@; const UserXmlHandler::`vftable'
0x18000ab65  mov     [rbp+var_28], rcx
0x18000ab69  mov     [rbp+var_20], rsi
0x18000ab6d  mov     [rbp+var_18], rdi
0x18000ab71  mov     byte ptr [rdi], 0
0x18000ab74  lea     rdx, [rbp+var_28]; struct ITaskXmlHandler *
0x18000ab78  mov     rcx, rax; this
0x18000ab7b  call    ?ProcessXml@TaskXmlReader@@QEAAJPEAUITaskXmlHandler@@@Z; TaskXmlReader::ProcessXml(ITaskXmlHandler *)
0x18000ab80  mov     ebx, eax
0x18000ab82  lea     rcx, [rbp+var_30]
0x18000ab86  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000ab8b  nop
0x18000ab8c  lea     rcx, [rbp+var_40]
0x18000ab90  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18000ab95  nop
0x18000ab96  mov     rcx, [rbp+hMem]; hMem
0x18000ab9a  call    cs:__imp_LocalFree
0x18000aba0  mov     [rbp+hMem], 0
0x18000aba8  mov     rcx, [rbp+var_38]; this
0x18000abac  test    rcx, rcx
0x18000abaf  jz      short loc_18000ABB6
0x18000abb1  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000abb6  mov     eax, ebx
0x18000abb8  add     rsp, 78h
0x18000abbc  pop     rdi
0x18000abbd  pop     rsi
0x18000abbe  pop     rbx
0x18000abbf  pop     rbp
0x18000abc0  retn
```
