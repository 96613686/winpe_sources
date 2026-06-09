# CompatibilityAdapter::GetUserInfo(ushort const *,_bstr_t &,bool &)

- ea: `0x18000b0ac`
- end: `0x18000b1b8`
- name: `?GetUserInfo@CompatibilityAdapter@@QEAAJPEBGAEAV_bstr_t@@AEA_N@Z`
- size: `268`
- prototype: `int(CompatibilityAdapter *__hidden this, const unsigned __int16 *, struct _bstr_t *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004a40`
- `0x18000b218`

## callees

- `0x180007948`
- `0x18000a15c`
- `0x18000a230`
- `0x18000a274`
- `0x18000af88`
- `0x18000b0ac`
- `0x18000c588`
- `0x18001d634`
- `0x180021710`
- `0x180024b70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b18a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b18a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
      Task = TaskXmlReader::ProcessXml((TaskXmlWriter **)v9, (struct ITaskXmlHandler *)v15);
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
0x18000b0ac  mov     [rsp-20h+arg_0], rcx
0x18000b0b1  push    rbp
0x18000b0b2  push    rbx
0x18000b0b3  push    rsi
0x18000b0b4  push    rdi
0x18000b0b5  mov     rbp, rsp
0x18000b0b8  sub     rsp, 78h
0x18000b0bc  mov     rdi, r9
0x18000b0bf  mov     rsi, r8
0x18000b0c2  mov     rbx, rdx
0x18000b0c5  lea     rdx, [rbp+var_38]
0x18000b0c9  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x18000b0ce  nop
0x18000b0cf  mov     dword ptr [rbp+arg_0], 0
0x18000b0d6  mov     [rbp+hMem], 0
0x18000b0de  lea     rax, [rbp+hMem]
0x18000b0e2  mov     [rsp+78h+var_58], rax; struct RpcString *
0x18000b0e7  lea     r9, [rbp+arg_0]; unsigned int *
0x18000b0eb  mov     rdx, rbx; unsigned __int16 *
0x18000b0ee  mov     rcx, [rbp+var_38]; this
0x18000b0f2  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18000b0f7  mov     ebx, eax
0x18000b0f9  test    eax, eax
0x18000b0fb  js      loc_18000B186
0x18000b101  mov     [rbp+var_40], 0
0x18000b109  lea     rdx, [rbp+var_40]
0x18000b10d  mov     rcx, [rbp+hMem]
0x18000b111  call    ?CreateStream@StringReader@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; StringReader::CreateStream(ushort const *,_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> &)
0x18000b116  mov     ebx, eax
0x18000b118  test    eax, eax
0x18000b11a  js      short loc_18000B17C
0x18000b11c  mov     ecx, 460h; Size
0x18000b121  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b126  mov     [rbp+var_30], rax
0x18000b12a  test    rax, rax
0x18000b12d  jz      short loc_18000B14A
0x18000b12f  lea     rdx, [rbp+var_40]
0x18000b133  mov     rcx, rax
0x18000b136  call    ??0TaskXmlReader@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@PEAPEAE_N@Z; TaskXmlReader::TaskXmlReader(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,uchar * *,bool)
0x18000b13b  mov     [rbp+var_30], rax
0x18000b13f  test    rax, rax
0x18000b142  jz      short loc_18000B14E
0x18000b144  lock inc dword ptr [rax+8]
0x18000b148  jmp     short loc_18000B14E
0x18000b14a  mov     [rbp+var_30], rax
0x18000b14e  lea     rcx, ??_7UserXmlHandler@@6B@; const UserXmlHandler::`vftable'
0x18000b155  mov     [rbp+var_28], rcx
0x18000b159  mov     [rbp+var_20], rsi
0x18000b15d  mov     [rbp+var_18], rdi
0x18000b161  mov     byte ptr [rdi], 0
0x18000b164  lea     rdx, [rbp+var_28]; struct ITaskXmlHandler *
0x18000b168  mov     rcx, rax; this
0x18000b16b  call    ?ProcessXml@TaskXmlReader@@QEAAJPEAUITaskXmlHandler@@@Z; TaskXmlReader::ProcessXml(ITaskXmlHandler *)
0x18000b170  mov     ebx, eax
0x18000b172  lea     rcx, [rbp+var_30]
0x18000b176  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x18000b17b  nop
0x18000b17c  lea     rcx, [rbp+var_40]
0x18000b180  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x18000b185  nop
0x18000b186  mov     rcx, [rbp+hMem]; hMem
0x18000b18a  call    cs:__imp_LocalFree
0x18000b191  nop     dword ptr [rax+rax+00h]
0x18000b196  mov     [rbp+hMem], 0
0x18000b19e  mov     rcx, [rbp+var_38]; this
0x18000b1a2  test    rcx, rcx
0x18000b1a5  jz      short loc_18000B1AC
0x18000b1a7  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000b1ac  mov     eax, ebx
0x18000b1ae  add     rsp, 78h
0x18000b1b2  pop     rdi
0x18000b1b3  pop     rsi
0x18000b1b4  pop     rbx
0x18000b1b5  pop     rbp
0x18000b1b6  retn
```
