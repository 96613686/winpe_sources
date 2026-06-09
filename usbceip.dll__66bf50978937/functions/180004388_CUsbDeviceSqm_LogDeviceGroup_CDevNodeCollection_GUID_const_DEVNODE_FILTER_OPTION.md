# CUsbDeviceSqm::LogDeviceGroup(CDevNodeCollection &,_GUID const &,DEVNODE_FILTER_OPTION)

- ea: `0x180004388`
- end: `0x180004505`
- name: `?LogDeviceGroup@CUsbDeviceSqm@@AEAAXAEAVCDevNodeCollection@@AEBU_GUID@@W4DEVNODE_FILTER_OPTION@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000450c`

## callees

- `0x180002410`
- `0x180003c6c`
- `0x180004060`
- `0x1800040cc`
- `0x1800041b4`
- `0x180004388`
- `0x1800045d0`
- `0x180008290`
- `0x180008ac0`
- `0x1800093d0`
- `0x180009adc`
- `0x180009af8`
- `0x18000ad38`
- `0x18000b464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004442`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004442`

## pseudocode

```c
__int64 __fastcall CUsbDeviceSqm::LogDeviceGroup(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v6; // eax
  unsigned int HubDepth; // eax
  unsigned __int8 v9; // [rsp+20h] [rbp-69h] BYREF
  CDevNode *v10; // [rsp+28h] [rbp-61h] BYREF
  int v11; // [rsp+30h] [rbp-59h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v13[4]; // [rsp+40h] [rbp-49h] BYREF
  CUsbDevice *v14[4]; // [rsp+60h] [rbp-29h] BYREF
  int v15; // [rsp+80h] [rbp-9h]
  char v16; // [rsp+ACh] [rbp+23h]

  v10 = 0;
  FileTime2 = 0;
  *(_QWORD *)(a2 + 16) = a3;
  *(_DWORD *)(a2 + 12) = 0;
  *(_DWORD *)(a2 + 8) = a4;
  while ( CDevNodeCollection::GetNextDevNode((_QWORD *)a2, (__int64 *)&v10) )
  {
    v9 = 0;
    CDevNode::GetProperty(v10, &DEVPKEY_Device_IsPresent, (bool *)&v9);
    if ( !v9 )
    {
      std::vector<_bstr_t>::vector<_bstr_t>(v13);
      v11 = 0;
      CDevNode::QueryDeviceProperty(v10, (__int64)&DEVPKEY_Device_LastArrivalDate, (__int64)&v11, (__int64 *)v13);
      FileTime2 = (FILETIME)*v13[0];
      if ( v13[0] )
        std::_Deallocate<16>(v13[0], (char *)v13[2] - (char *)v13[0]);
      if ( CompareFileTime((const FILETIME *)(a1 + 4), &FileTime2) > 0 )
        continue;
    }
    CUsbDevice::CUsbDevice((CUsbDevice *)v14, v10);
    if ( v15 != 3 )
    {
      v6 = *(_DWORD *)(a1 + 12);
      if ( v6 != 50 )
      {
        *(_DWORD *)(a1 + 12) = v6 + 1;
        CUsbDeviceSqm::LogStreamEntry((CUsbDeviceSqm *)a1, v14);
      }
      if ( v16 )
        ++*(_DWORD *)(a1 + 16);
      else
        ++*(_DWORD *)(a1 + 20);
      if ( CUsbDevice::IsFunctional((CUsbDevice *)v14) )
      {
        HubDepth = CUsbDevice::GetHubDepth((CUsbDevice *)v14);
        if ( HubDepth > *(_DWORD *)(a1 + 32) )
          *(_DWORD *)(a1 + 32) = HubDepth;
        if ( CUsbDevice::IsOnXhci((CUsbDevice *)v14) )
          ++*(_DWORD *)(a1 + 28);
        if ( v15 == 2 )
          ++*(_DWORD *)(a1 + 24);
      }
    }
    CUsbDevice::~CUsbDevice((CUsbDevice *)v14);
  }
  return std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(&v10);
}

```

## disassembly

```asm
0x180004388  mov     [rsp-8+arg_10], rbx
0x18000438d  mov     [rsp-8+arg_18], rsi
0x180004392  push    rbp
0x180004393  lea     rbp, [rsp-57h]
0x180004398  sub     rsp, 0E0h
0x18000439f  mov     rax, cs:__security_cookie
0x1800043a6  xor     rax, rsp
0x1800043a9  mov     [rbp+57h+var_10], rax
0x1800043ad  mov     rsi, rdx
0x1800043b0  mov     rbx, rcx
0x1800043b3  mov     [rbp+57h+var_B8], 0
0x1800043bb  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], 0
0x1800043c3  mov     [rdx+10h], r8
0x1800043c7  mov     dword ptr [rdx+0Ch], 0
0x1800043ce  mov     [rdx+8], r9d
0x1800043d2  jmp     loc_1800044C7
0x1800043d7  mov     [rbp+57h+var_C0], 0
0x1800043db  lea     r8, [rbp+57h+var_C0]; unsigned __int8 *
0x1800043df  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x1800043e6  mov     rcx, [rbp+57h+var_B8]; this
0x1800043ea  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x1800043ef  cmp     [rbp+57h+var_C0], 0
0x1800043f3  jnz     short loc_18000444C
0x1800043f5  lea     rcx, [rbp+57h+var_A0]
0x1800043f9  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x1800043fe  nop
0x1800043ff  mov     [rbp+57h+var_B0], 0
0x180004406  lea     r9, [rbp+57h+var_A0]
0x18000440a  lea     r8, [rbp+57h+var_B0]
0x18000440e  lea     rdx, DEVPKEY_Device_LastArrivalDate
0x180004415  mov     rcx, [rbp+57h+var_B8]
0x180004419  call    ?QueryDeviceProperty@CDevNode@@AEAAXAEBU_DEVPROPKEY@@AEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CDevNode::QueryDeviceProperty(_DEVPROPKEY const &,ulong &,std::vector<uchar> &)
0x18000441e  mov     rcx, [rbp+57h+var_A0]
0x180004422  mov     rax, [rcx]
0x180004425  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x180004429  test    rcx, rcx
0x18000442c  jz      short loc_18000443A
0x18000442e  mov     rdx, [rbp+57h+var_90]
0x180004432  sub     rdx, rcx
0x180004435  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000443a  lea     rcx, [rbx+4]; lpFileTime1
0x18000443e  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180004442  call    cs:__imp_CompareFileTime
0x180004448  test    eax, eax
0x18000444a  jg      short loc_1800044C7
0x18000444c  mov     rdx, [rbp+57h+var_B8]; struct CDevNode *
0x180004450  lea     rcx, [rbp+57h+var_80]; this
0x180004454  call    ??0CUsbDevice@@QEAA@AEAVCDevNode@@@Z; CUsbDevice::CUsbDevice(CDevNode &)
0x180004459  nop
0x18000445a  cmp     [rbp+57h+var_60], 3
0x18000445e  jz      short loc_1800044BE
0x180004460  mov     eax, [rbx+0Ch]
0x180004463  cmp     eax, 32h ; '2'
0x180004466  jz      short loc_180004479
0x180004468  inc     eax
0x18000446a  mov     [rbx+0Ch], eax
0x18000446d  lea     rdx, [rbp+57h+var_80]; struct CUsbDevice *
0x180004471  mov     rcx, rbx; this
0x180004474  call    ?LogStreamEntry@CUsbDeviceSqm@@AEAAXAEAVCUsbDevice@@@Z; CUsbDeviceSqm::LogStreamEntry(CUsbDevice &)
0x180004479  cmp     [rbp+57h+var_34], 0
0x18000447d  jz      short loc_180004484
0x18000447f  inc     dword ptr [rbx+10h]
0x180004482  jmp     short loc_180004487
0x180004484  inc     dword ptr [rbx+14h]
0x180004487  lea     rcx, [rbp+57h+var_80]; this
0x18000448b  call    ?IsFunctional@CUsbDevice@@QEAAEXZ; CUsbDevice::IsFunctional(void)
0x180004490  test    al, al
0x180004492  jz      short loc_1800044BE
0x180004494  lea     rcx, [rbp+57h+var_80]; this
0x180004498  call    ?GetHubDepth@CUsbDevice@@QEAAKXZ; CUsbDevice::GetHubDepth(void)
0x18000449d  cmp     eax, [rbx+20h]
0x1800044a0  jbe     short loc_1800044A5
0x1800044a2  mov     [rbx+20h], eax
0x1800044a5  lea     rcx, [rbp+57h+var_80]; this
0x1800044a9  call    ?IsOnXhci@CUsbDevice@@QEAAEXZ; CUsbDevice::IsOnXhci(void)
0x1800044ae  test    al, al
0x1800044b0  jz      short loc_1800044B5
0x1800044b2  inc     dword ptr [rbx+1Ch]
0x1800044b5  cmp     [rbp+57h+var_60], 2
0x1800044b9  jnz     short loc_1800044BE
0x1800044bb  inc     dword ptr [rbx+18h]
0x1800044be  lea     rcx, [rbp+57h+var_80]; this
0x1800044c2  call    ??1CUsbDevice@@QEAA@XZ; CUsbDevice::~CUsbDevice(void)
0x1800044c7  lea     rdx, [rbp+57h+var_B8]
0x1800044cb  mov     rcx, rsi
0x1800044ce  call    ?GetNextDevNode@CDevNodeCollection@@QEAAEAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z; CDevNodeCollection::GetNextDevNode(std::unique_ptr<CDevNode> &)
0x1800044d3  test    al, al
0x1800044d5  jnz     loc_1800043D7
0x1800044db  lea     rcx, [rbp+57h+var_B8]
0x1800044df  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x1800044e4  mov     rcx, [rbp+57h+var_10]
0x1800044e8  xor     rcx, rsp; StackCookie
0x1800044eb  call    __security_check_cookie
0x1800044f0  lea     r11, [rsp+0E0h+var_s0]
0x1800044f8  mov     rbx, [r11+20h]
0x1800044fc  mov     rsi, [r11+28h]
0x180004500  mov     rsp, r11
0x180004503  pop     rbp
0x180004504  retn
```
