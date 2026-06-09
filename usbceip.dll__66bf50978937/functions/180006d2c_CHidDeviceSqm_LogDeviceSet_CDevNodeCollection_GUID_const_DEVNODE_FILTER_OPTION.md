# CHidDeviceSqm::LogDeviceSet(CDevNodeCollection &,_GUID const &,DEVNODE_FILTER_OPTION)

- ea: `0x180006d2c`
- end: `0x180006f0f`
- name: `?LogDeviceSet@CHidDeviceSqm@@AEAAXAEAVCDevNodeCollection@@AEBU_GUID@@W4DEVNODE_FILTER_OPTION@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(__int64, __int64, CDevNode *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800065f8`

## callees

- `0x180003c6c`
- `0x180003fec`
- `0x180004060`
- `0x1800040cc`
- `0x180006c28`
- `0x180006d2c`
- `0x180006f18`
- `0x180008290`
- `0x18000ab84`
- `0x18000ace8`
- `0x18000ad38`
- `0x18000aeac`
- `0x18000b240`
- `0x18000b464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006e03`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006e03`

## pseudocode

```c
__int64 __fastcall CHidDeviceSqm::LogDeviceSet(__int64 a1, __int64 a2, CDevNode *a3, int a4)
{
  CDevNode *v6; // rbx
  CDevNode *v7; // rbx
  CHidDeviceSqm *v8; // rcx
  FILETIME FileTime2; // [rsp+20h] [rbp-40h] BYREF
  FILETIME *v11; // [rsp+28h] [rbp-38h] BYREF
  char v12; // [rsp+30h] [rbp-30h]
  bool v13; // [rsp+31h] [rbp-2Fh]
  unsigned __int8 HasChildren; // [rsp+32h] [rbp-2Eh]
  __int64 v15; // [rsp+38h] [rbp-28h] BYREF
  CDevNode *v16; // [rsp+40h] [rbp-20h] BYREF
  char v17; // [rsp+48h] [rbp-18h]
  _QWORD v18[2]; // [rsp+50h] [rbp-10h] BYREF
  CDevNode *v19; // [rsp+98h] [rbp+38h] BYREF
  CDevNode *v20; // [rsp+A0h] [rbp+40h] BYREF
  int v21; // [rsp+A8h] [rbp+48h] BYREF

  v20 = a3;
  v19 = 0;
  *(_QWORD *)(a2 + 16) = &GUID_DEVINTERFACE_HID;
  *(_DWORD *)(a2 + 12) = 0;
  *(_DWORD *)(a2 + 8) = a4;
  while ( (unsigned __int8)CDevNodeCollection::GetNextDevNode(a2, &v19) == 1 )
  {
    FileTime2 = 0;
    v6 = v19;
    v16 = v19;
    v18[0] = 0;
    LOBYTE(v21) = 0;
    CDevNode::GetProperty(v19, &DEVPKEY_Device_IsPresent, (unsigned __int8 *)&v21);
    v17 = v21;
    CDevNode::GetServiceName(v6, (struct _bstr_t *)v18);
    LOBYTE(v21) = 0;
    CDevNode::GetProperty(v6, &DEVPKEY_Device_IsPresent, (unsigned __int8 *)&v21);
    if ( (_BYTE)v21 )
      goto LABEL_6;
    std::vector<_bstr_t>::vector<_bstr_t>(&v11);
    v21 = 0;
    CDevNode::QueryDeviceProperty(v6, &DEVPKEY_Device_LastArrivalDate, &v21, &v11);
    FileTime2 = *v11;
    if ( v11 )
      std::_Deallocate<16>(v11, v15 - (_QWORD)v11);
    if ( CompareFileTime((const FILETIME *)(a1 + 4), &FileTime2) <= 0 )
    {
LABEL_6:
      v20 = 0;
      CDevNode::GetParent(v6, &GUID_DUMMY_HID_DEVICE, &v20);
      if ( v20 && !(unsigned __int8)CHidDeviceSqm::IsParentVisited(a1, &v20) )
      {
        LOBYTE(v21) = 0;
        v7 = v20;
        CDevNode::GetProperty(v20, &DEVPKEY_Device_IsPresent, (unsigned __int8 *)&v21);
        if ( (_BYTE)v21 == 1 )
          ++*(_DWORD *)(a1 + 36);
        else
          ++*(_DWORD *)(a1 + 40);
        v11 = (FILETIME *)v7;
        v15 = 0;
        LOBYTE(v21) = 0;
        CDevNode::GetProperty(v7, &DEVPKEY_Device_IsPresent, (unsigned __int8 *)&v21);
        v12 = v21;
        v13 = CDevNode::GetProblemCode(v7) != 0;
        HasChildren = CDevNode::HasChildren(v7);
        CDevNode::GetServiceName(v7, (struct _bstr_t *)&v15);
        CHidDeviceSqm::LogStreamEntry(v8, (struct CHidCollection *)&v16, (struct CHidDevice *)&v11);
        _bstr_t::_Free((_bstr_t *)&v15);
      }
      ++*(_DWORD *)(a1 + 32);
      std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(&v20);
    }
    _bstr_t::_Free((_bstr_t *)v18);
  }
  return std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(&v19);
}

```

## disassembly

```asm
0x180006d2c  mov     [rsp-28h+arg_10], r8
0x180006d31  push    rbp
0x180006d32  push    rbx
0x180006d33  push    rsi
0x180006d34  push    rdi
0x180006d35  push    r14
0x180006d37  mov     rbp, rsp
0x180006d3a  sub     rsp, 60h
0x180006d3e  mov     rsi, rdx
0x180006d41  mov     rdi, rcx
0x180006d44  xor     r14d, r14d
0x180006d47  mov     [rbp+arg_8], r14
0x180006d4b  lea     rax, GUID_DEVINTERFACE_HID
0x180006d52  mov     [rdx+10h], rax
0x180006d56  mov     [rdx+0Ch], r14d
0x180006d5a  mov     [rdx+8], r9d
0x180006d5e  jmp     loc_180006EE7
0x180006d63  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r14
0x180006d67  mov     rbx, [rbp+arg_8]
0x180006d6b  mov     [rbp+var_20], rbx
0x180006d6f  mov     [rbp+var_10], r14
0x180006d73  mov     byte ptr [rbp+arg_18], r14b
0x180006d77  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x180006d7b  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x180006d82  mov     rcx, rbx; this
0x180006d85  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x180006d8a  mov     al, byte ptr [rbp+arg_18]
0x180006d8d  mov     [rbp+var_18], al
0x180006d90  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x180006d94  mov     rcx, rbx; this
0x180006d97  call    ?GetServiceName@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetServiceName(_bstr_t &)
0x180006d9c  nop
0x180006d9d  mov     byte ptr [rbp+arg_18], r14b
0x180006da1  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x180006da5  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x180006dac  mov     rcx, rbx; this
0x180006daf  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x180006db4  cmp     byte ptr [rbp+arg_18], r14b
0x180006db8  jnz     short loc_180006E11
0x180006dba  lea     rcx, [rbp+var_38]
0x180006dbe  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x180006dc3  nop
0x180006dc4  mov     [rbp+arg_18], r14d
0x180006dc8  lea     r9, [rbp+var_38]
0x180006dcc  lea     r8, [rbp+arg_18]
0x180006dd0  lea     rdx, DEVPKEY_Device_LastArrivalDate
0x180006dd7  mov     rcx, rbx
0x180006dda  call    ?QueryDeviceProperty@CDevNode@@AEAAXAEBU_DEVPROPKEY@@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CDevNode::QueryDeviceProperty(_DEVPROPKEY const &,ulong &,std::vector<uchar> &)
0x180006ddf  mov     rcx, [rbp+var_38]
0x180006de3  mov     rax, [rcx]
0x180006de6  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180006dea  test    rcx, rcx
0x180006ded  jz      short loc_180006DFB
0x180006def  mov     rdx, [rbp+var_28]
0x180006df3  sub     rdx, rcx
0x180006df6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006dfb  lea     rcx, [rdi+4]; lpFileTime1
0x180006dff  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180006e03  call    cs:__imp_CompareFileTime
0x180006e09  test    eax, eax
0x180006e0b  jg      loc_180006EDE
0x180006e11  mov     [rbp+arg_10], r14
0x180006e15  lea     r8, [rbp+arg_10]
0x180006e19  lea     rdx, GUID_DUMMY_HID_DEVICE
0x180006e20  mov     rcx, rbx
0x180006e23  call    ?GetParent@CDevNode@@QEAAXAEBU_GUID@@AEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z; CDevNode::GetParent(_GUID const &,std::unique_ptr<CDevNode> &)
0x180006e28  cmp     [rbp+arg_10], r14
0x180006e2c  jz      loc_180006ED1
0x180006e32  lea     rdx, [rbp+arg_10]
0x180006e36  mov     rcx, rdi
0x180006e39  call    ?IsParentVisited@CHidDeviceSqm@@AEAA_NAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z; CHidDeviceSqm::IsParentVisited(std::unique_ptr<CDevNode> &)
0x180006e3e  test    al, al
0x180006e40  jnz     loc_180006ED1
0x180006e46  mov     byte ptr [rbp+arg_18], r14b
0x180006e4a  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x180006e4e  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x180006e55  mov     rbx, [rbp+arg_10]
0x180006e59  mov     rcx, rbx; this
0x180006e5c  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x180006e61  cmp     byte ptr [rbp+arg_18], 1
0x180006e65  jnz     short loc_180006E6C
0x180006e67  inc     dword ptr [rdi+24h]
0x180006e6a  jmp     short loc_180006E6F
0x180006e6c  inc     dword ptr [rdi+28h]
0x180006e6f  mov     [rbp+var_38], rbx
0x180006e73  mov     [rbp+var_28], r14
0x180006e77  mov     byte ptr [rbp+arg_18], r14b
0x180006e7b  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x180006e7f  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x180006e86  mov     rcx, rbx; this
0x180006e89  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x180006e8e  mov     al, byte ptr [rbp+arg_18]
0x180006e91  mov     [rbp+var_30], al
0x180006e94  mov     rcx, rbx; this
0x180006e97  call    ?GetProblemCode@CDevNode@@QEAAKXZ; CDevNode::GetProblemCode(void)
0x180006e9c  test    eax, eax
0x180006e9e  setnz   [rbp+var_2F]
0x180006ea2  mov     rcx, rbx; this
0x180006ea5  call    ?HasChildren@CDevNode@@QEAAEXZ; CDevNode::HasChildren(void)
0x180006eaa  mov     [rbp+var_2E], al
0x180006ead  lea     rdx, [rbp+var_28]; struct _bstr_t *
0x180006eb1  mov     rcx, rbx; this
0x180006eb4  call    ?GetServiceName@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetServiceName(_bstr_t &)
0x180006eb9  nop
0x180006eba  lea     r8, [rbp+var_38]; struct CHidDevice *
0x180006ebe  lea     rdx, [rbp+var_20]; struct CHidCollection *
0x180006ec2  call    ?LogStreamEntry@CHidDeviceSqm@@AEAAXAEAVCHidCollection@@AEAVCHidDevice@@@Z; CHidDeviceSqm::LogStreamEntry(CHidCollection &,CHidDevice &)
0x180006ec7  nop
0x180006ec8  lea     rcx, [rbp+var_28]; this
0x180006ecc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006ed1  inc     dword ptr [rdi+20h]
0x180006ed4  lea     rcx, [rbp+arg_10]
0x180006ed8  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x180006edd  nop
0x180006ede  lea     rcx, [rbp+var_10]; this
0x180006ee2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180006ee7  lea     rdx, [rbp+arg_8]
0x180006eeb  mov     rcx, rsi
0x180006eee  call    ?GetNextDevNode@CDevNodeCollection@@QEAAEAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z; CDevNodeCollection::GetNextDevNode(std::unique_ptr<CDevNode> &)
0x180006ef3  cmp     al, 1
0x180006ef5  jz      loc_180006D63
0x180006efb  lea     rcx, [rbp+arg_8]
0x180006eff  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x180006f04  add     rsp, 60h
0x180006f08  pop     r14
0x180006f0a  pop     rdi
0x180006f0b  pop     rsi
0x180006f0c  pop     rbx
0x180006f0d  pop     rbp
0x180006f0e  retn
```
