# CProgressUI::_AssociateDevice(IPortableDevice *)

- ea: `0x1800535f8`
- end: `0x18005378e`
- name: `?_AssociateDevice@CProgressUI@@QEAAJPEAUIPortableDevice@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(CProgressUI *__hidden this, struct IPortableDevice *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016780`
- `0x1800311d8`
- `0x180049d20`
- `0x180070520`
- `0x1800705f0`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x1800535f8`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005362a`
- `KERNEL32!EnterCriticalSection` at `0x18005362a`
- `KERNEL32!LeaveCriticalSection` at `0x18005373a`
- `KERNEL32!LeaveCriticalSection` at `0x18005373a`
- `ole32!CoCreateInstance` at `0x180053664`
- `ole32!CoCreateInstance` at `0x180053664`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProgressUI::_AssociateDevice(CProgressUI *this, struct IPortableDevice *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  int v5; // ebx
  HRESULT v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  v10 = 0;
  ppv = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2776);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2776));
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_19;
  }
  v6 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 119;
LABEL_7:
      WPP_SF_d(v7[2], v8, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v6);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( !*((_DWORD *)this + 704) )
  {
LABEL_14:
    v6 = (*(__int64 (__fastcall **)(LPVOID, struct IPortableDevice *, GUID *, int *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           a2,
           &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c,
           &v10);
    v5 = v6;
    if ( v6 >= 0 )
    {
      *((_DWORD *)this + 704) = v10;
      goto LABEL_19;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 121;
      goto LABEL_7;
    }
    goto LABEL_19;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
  v5 = v6;
  if ( v6 >= 0 )
  {
    *((_DWORD *)this + 704) = 0;
    goto LABEL_14;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = 120;
    goto LABEL_7;
  }
LABEL_19:
  LeaveCriticalSection(v4);
  if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)v5);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800535f8  mov     rax, rsp
0x1800535fb  mov     [rax+18h], rbx
0x1800535ff  mov     [rax+20h], rbp
0x180053603  push    rsi
0x180053604  push    rdi
0x180053605  push    r12
0x180053607  sub     rsp, 30h
0x18005360b  mov     rsi, rdx
0x18005360e  mov     rdi, rcx
0x180053611  mov     dword ptr [rax+8], 0
0x180053618  mov     qword ptr [rax+10h], 0
0x180053620  lea     rbp, [rcx+0AD8h]
0x180053627  mov     rcx, rbp; lpCriticalSection
0x18005362a  call    cs:__imp_EnterCriticalSection
0x180053630  lea     r12, WPP_GLOBAL_Control
0x180053637  test    rsi, rsi
0x18005363a  jnz     short loc_180053646
0x18005363c  mov     ebx, 80070057h
0x180053641  jmp     loc_180053737
0x180053646  lea     rax, [rsp+48h+arg_8]
0x18005364b  mov     [rsp+48h+ppv], rax; ppv
0x180053650  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180053657  xor     edx, edx; pUnkOuter
0x180053659  lea     r8d, [rdx+1]; dwClsContext
0x18005365d  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180053664  call    cs:__imp_CoCreateInstance
0x18005366a  mov     ebx, eax
0x18005366c  test    eax, eax
0x18005366e  jns     short loc_1800536A7
0x180053670  mov     rcx, cs:WPP_GLOBAL_Control
0x180053677  cmp     rcx, r12
0x18005367a  jz      loc_180053737
0x180053680  test    byte ptr [rcx+1Ch], 2
0x180053684  jz      loc_180053737
0x18005368a  mov     edx, 77h ; 'w'
0x18005368f  mov     r9d, eax
0x180053692  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053699  mov     rcx, [rcx+10h]
0x18005369d  call    WPP_SF_d
0x1800536a2  jmp     loc_180053737
0x1800536a7  mov     edx, [rdi+0B00h]
0x1800536ad  test    edx, edx
0x1800536af  jz      short loc_1800536EB
0x1800536b1  mov     rcx, [rsp+48h+arg_8]
0x1800536b6  mov     rax, [rcx]
0x1800536b9  mov     rax, [rax+20h]
0x1800536bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536c2  mov     ebx, eax
0x1800536c4  test    eax, eax
0x1800536c6  jns     short loc_1800536E1
0x1800536c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800536cf  cmp     rcx, r12
0x1800536d2  jz      short loc_180053737
0x1800536d4  test    byte ptr [rcx+1Ch], 2
0x1800536d8  jz      short loc_180053737
0x1800536da  mov     edx, 78h ; 'x'
0x1800536df  jmp     short loc_18005368F
0x1800536e1  mov     dword ptr [rdi+0B00h], 0
0x1800536eb  mov     rcx, [rsp+48h+arg_8]
0x1800536f0  mov     rax, [rcx]
0x1800536f3  lea     r9, [rsp+48h+arg_0]
0x1800536f8  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x1800536ff  mov     rdx, rsi
0x180053702  mov     rax, [rax+18h]
0x180053706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005370b  mov     ebx, eax
0x18005370d  test    eax, eax
0x18005370f  jns     short loc_18005372D
0x180053711  mov     rcx, cs:WPP_GLOBAL_Control
0x180053718  cmp     rcx, r12
0x18005371b  jz      short loc_180053737
0x18005371d  test    byte ptr [rcx+1Ch], 2
0x180053721  jz      short loc_180053737
0x180053723  mov     edx, 79h ; 'y'
0x180053728  jmp     loc_18005368F
0x18005372d  mov     eax, [rsp+48h+arg_0]
0x180053731  mov     [rdi+0B00h], eax
0x180053737  mov     rcx, rbp; lpCriticalSection
0x18005373a  call    cs:__imp_LeaveCriticalSection
0x180053740  test    ebx, ebx
0x180053742  jns     short loc_18005376F
0x180053744  mov     rcx, cs:WPP_GLOBAL_Control
0x18005374b  cmp     rcx, r12
0x18005374e  jz      short loc_18005376F
0x180053750  test    byte ptr [rcx+1Ch], 2
0x180053754  jz      short loc_18005376F
0x180053756  mov     edx, 7Ah ; 'z'
0x18005375b  mov     r9d, ebx
0x18005375e  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180053765  mov     rcx, [rcx+10h]
0x180053769  call    WPP_SF_d
0x18005376e  nop
0x18005376f  lea     rcx, [rsp+48h+arg_8]
0x180053774  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180053779  mov     eax, ebx
0x18005377b  mov     rbx, [rsp+48h+arg_10]
0x180053780  mov     rbp, [rsp+48h+arg_18]
0x180053785  add     rsp, 30h
0x180053789  pop     r12
0x18005378b  pop     rdi
0x18005378c  pop     rsi
0x18005378d  retn
```
