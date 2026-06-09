# CProgressUI::_EndProgressUI(void)

- ea: `0x180032298`
- end: `0x1800323e0`
- name: `?_EndProgressUI@CProgressUI@@QEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(CProgressUI *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016780`
- `0x1800311d8`
- `0x18003c074`
- `0x18003cce4`
- `0x180049d20`
- `0x1800518a4`
- `0x18006fcd0`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x180032298`
- `0x180078010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800322ea`
- `KERNEL32!CloseHandle` at `0x1800322ea`
- `KERNEL32!EnterCriticalSection` at `0x180032301`
- `KERNEL32!EnterCriticalSection` at `0x180032301`
- `KERNEL32!LeaveCriticalSection` at `0x180032391`
- `KERNEL32!LeaveCriticalSection` at `0x180032391`
- `KERNEL32!SetEvent` at `0x1800322c5`
- `KERNEL32!SetEvent` at `0x1800322c5`
- `ole32!CoCreateInstance` at `0x180032335`
- `ole32!CoCreateInstance` at `0x180032335`
- `ole32!CoWaitForMultipleHandles` at `0x1800322e1`
- `ole32!CoWaitForMultipleHandles` at `0x1800322e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProgressUI::_EndProgressUI(CProgressUI *this)
{
  int v2; // edi
  HANDLE *v3; // rsi
  HRESULT v4; // eax
  DWORD dwindex; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  ppv = 0;
  v3 = (HANDLE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    if ( *((_DWORD *)this + 28) )
    {
      dwindex = 0;
      SetEvent(*((HANDLE *)this + 4));
      CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, v3, &dwindex);
    }
    CloseHandle(*v3);
    *v3 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2776));
  if ( *((_DWORD *)this + 704) )
  {
    v4 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    v2 = v4;
    if ( v4 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)this + 704));
      *((_DWORD *)this + 704) = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)v4);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2776));
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      124,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)v2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180032298  mov     [rsp+arg_10], rbx
0x18003229d  push    rsi
0x18003229e  push    rdi
0x18003229f  push    r14
0x1800322a1  sub     rsp, 30h
0x1800322a5  mov     rbx, rcx
0x1800322a8  xor     edi, edi
0x1800322aa  mov     [rsp+48h+ppv], rdi
0x1800322af  lea     rsi, [rcx+8]
0x1800322b3  cmp     [rsi], rdi
0x1800322b6  jz      short loc_1800322F7
0x1800322b8  cmp     [rcx+70h], edi
0x1800322bb  jz      short loc_1800322E7
0x1800322bd  mov     [rsp+48h+dwindex], edi
0x1800322c1  mov     rcx, [rcx+20h]; hEvent
0x1800322c5  call    cs:__imp_SetEvent
0x1800322cb  lea     rax, [rsp+48h+dwindex]
0x1800322d0  mov     [rsp+48h+lpdwindex], rax; lpdwindex
0x1800322d5  mov     r9, rsi; pHandles
0x1800322d8  lea     r8d, [rdi+1]; cHandles
0x1800322dc  or      edx, 0FFFFFFFFh; dwTimeout
0x1800322df  xor     ecx, ecx; dwFlags
0x1800322e1  call    cs:__imp_CoWaitForMultipleHandles
0x1800322e7  mov     rcx, [rsi]; hObject
0x1800322ea  call    cs:__imp_CloseHandle
0x1800322f0  mov     qword ptr [rsi], 0
0x1800322f7  lea     rsi, [rbx+0AD8h]
0x1800322fe  mov     rcx, rsi; lpCriticalSection
0x180032301  call    cs:__imp_EnterCriticalSection
0x180032307  lea     r14, WPP_GLOBAL_Control
0x18003230e  cmp     dword ptr [rbx+0B00h], 0
0x180032315  jz      short loc_18003238E
0x180032317  lea     rax, [rsp+48h+ppv]
0x18003231c  mov     [rsp+48h+lpdwindex], rax; ppv
0x180032321  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180032328  xor     edx, edx; pUnkOuter
0x18003232a  lea     r8d, [rdx+1]; dwClsContext
0x18003232e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180032335  call    cs:__imp_CoCreateInstance
0x18003233b  mov     edi, eax
0x18003233d  test    eax, eax
0x18003233f  jns     short loc_18003236D
0x180032341  mov     rcx, cs:WPP_GLOBAL_Control
0x180032348  cmp     rcx, r14
0x18003234b  jz      short loc_18003238E
0x18003234d  test    byte ptr [rcx+1Ch], 2
0x180032351  jz      short loc_18003238E
0x180032353  mov     edx, 7Bh ; '{'
0x180032358  mov     r9d, eax
0x18003235b  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180032362  mov     rcx, [rcx+10h]
0x180032366  call    WPP_SF_d
0x18003236b  jmp     short loc_18003238E
0x18003236d  mov     rcx, [rsp+48h+ppv]
0x180032372  mov     rax, [rcx]
0x180032375  mov     edx, [rbx+0B00h]
0x18003237b  mov     rax, [rax+20h]
0x18003237f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032384  mov     dword ptr [rbx+0B00h], 0
0x18003238e  mov     rcx, rsi; lpCriticalSection
0x180032391  call    cs:__imp_LeaveCriticalSection
0x180032397  test    edi, edi
0x180032399  jns     short loc_1800323C6
0x18003239b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800323a2  cmp     rcx, r14
0x1800323a5  jz      short loc_1800323C6
0x1800323a7  test    byte ptr [rcx+1Ch], 2
0x1800323ab  jz      short loc_1800323C6
0x1800323ad  mov     edx, 7Ch ; '|'
0x1800323b2  mov     r9d, edi
0x1800323b5  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x1800323bc  mov     rcx, [rcx+10h]
0x1800323c0  call    WPP_SF_d
0x1800323c5  nop
0x1800323c6  lea     rcx, [rsp+48h+ppv]
0x1800323cb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800323d0  mov     eax, edi
0x1800323d2  mov     rbx, [rsp+48h+arg_10]
0x1800323d7  add     rsp, 30h
0x1800323db  pop     r14
0x1800323dd  pop     rdi
0x1800323de  pop     rsi
0x1800323df  retn
```
