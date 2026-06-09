# CProtocolHandler::GetWitnessNodeInformation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,uchar *,ulong *)

- ea: `0x180033e28`
- end: `0x180033f08`
- name: `?GetWitnessNodeInformation@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAEPEAK@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800333f0`

## callees

- `0x18001d694`
- `0x18001fbd0`
- `0x180033e28`
- `0x180034944`
- `0x180034f58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ed2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033ed2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProtocolHandler::GetWitnessNodeInformation(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  CProtocolHandler *v8; // rsi
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  CClusterConnection *v12; // rcx
  unsigned int WitnessNodeInformation; // ebx
  _BYTE v15[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h]

  v16 = a2;
  v8 = WitnessProtocolHandler;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  v9 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                    (char *)v8 + 8,
                    v15,
                    a2);
  v10 = *v9;
  if ( *v9 == *((_QWORD *)v8 + 1)
    && (v11 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                           (char *)v8 + 40,
                           v15,
                           a2),
        v10 = *v11,
        *v11 == *((_QWORD *)v8 + 5))
    || (v12 = *(CClusterConnection **)(v10 + 64)) == 0 )
  {
    WitnessNodeInformation = 1168;
    *a5 = 0;
  }
  else
  {
    WitnessNodeInformation = CClusterConnection::GetWitnessNodeInformation(v12, a3, a4, a5);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)v8 + 10));
  std::wstring::~wstring(a2);
  return WitnessNodeInformation;
}

```

## disassembly

```asm
0x180033e28  mov     [rsp+arg_0], rbx
0x180033e2d  push    rbp
0x180033e2e  push    rsi
0x180033e2f  push    rdi
0x180033e30  push    r14
0x180033e32  push    r15
0x180033e34  sub     rsp, 40h
0x180033e38  mov     rax, cs:__security_cookie
0x180033e3f  xor     rax, rsp
0x180033e42  mov     [rsp+68h+var_38], rax
0x180033e47  mov     r15, r9
0x180033e4a  mov     ebp, r8d
0x180033e4d  mov     rdi, rdx
0x180033e50  mov     [rsp+68h+var_40], rdx
0x180033e55  mov     r14, [rsp+68h+arg_20]
0x180033e5d  mov     rsi, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x180033e64  mov     rcx, [rsi+50h]; lpCriticalSection
0x180033e68  call    cs:__imp_EnterCriticalSection
0x180033e6f  nop     dword ptr [rax+rax+00h]
0x180033e74  mov     r8, rdi
0x180033e77  lea     rdx, [rsp+68h+var_48]
0x180033e7c  lea     rcx, [rsi+8]
0x180033e80  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x180033e85  mov     rcx, [rax]
0x180033e88  cmp     rcx, [rsi+8]
0x180033e8c  jnz     short loc_180033EA8
0x180033e8e  mov     r8, rdi
0x180033e91  lea     rdx, [rsp+68h+var_48]
0x180033e96  lea     rcx, [rsi+28h]
0x180033e9a  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x180033e9f  mov     rcx, [rax]
0x180033ea2  cmp     rcx, [rsi+28h]
0x180033ea6  jz      short loc_180033EC2
0x180033ea8  mov     rcx, [rcx+40h]; this
0x180033eac  test    rcx, rcx
0x180033eaf  jz      short loc_180033EC2
0x180033eb1  mov     r9, r14; unsigned int *
0x180033eb4  mov     r8, r15; unsigned __int8 *
0x180033eb7  mov     edx, ebp; unsigned int
0x180033eb9  call    ?GetWitnessNodeInformation@CClusterConnection@@QEAAKKPEAEPEAK@Z; CClusterConnection::GetWitnessNodeInformation(ulong,uchar *,ulong *)
0x180033ebe  mov     ebx, eax
0x180033ec0  jmp     short loc_180033ECE
0x180033ec2  mov     ebx, 490h
0x180033ec7  mov     dword ptr [r14], 0
0x180033ece  mov     rcx, [rsi+50h]; lpCriticalSection
0x180033ed2  call    cs:__imp_LeaveCriticalSection
0x180033ed9  nop     dword ptr [rax+rax+00h]
0x180033ede  nop
0x180033edf  mov     rcx, rdi
0x180033ee2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033ee7  mov     eax, ebx
0x180033ee9  mov     rcx, [rsp+68h+var_38]
0x180033eee  xor     rcx, rsp; StackCookie
0x180033ef1  call    __security_check_cookie
0x180033ef6  mov     rbx, [rsp+68h+arg_0]
0x180033efb  add     rsp, 40h
0x180033eff  pop     r15
0x180033f01  pop     r14
0x180033f03  pop     rdi
0x180033f04  pop     rsi
0x180033f05  pop     rbp
0x180033f06  retn
```
