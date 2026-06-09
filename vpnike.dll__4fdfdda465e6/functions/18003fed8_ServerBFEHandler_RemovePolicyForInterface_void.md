# ServerBFEHandler::RemovePolicyForInterface(void *)

- ea: `0x18003fed8`
- end: `0x1800400a2`
- name: `?RemovePolicyForInterface@ServerBFEHandler@@KAKPEAX@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a470`
- `0x180040308`
- `0x180040454`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x18003fed8`
- `0x1800400a8`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004002b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004002b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004001d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004001d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ff83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ff83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040038`

## string_xrefs

- `0x18003ff69`: `ServerBFEHandler::RemovePolicyForInterface`
- `0x18003ffcb`: `RemovePolicy failed: %d`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::RemovePolicyForInterface(void *a1)
{
  struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *v2; // rdi
  struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *i; // rbx
  unsigned int v4; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v10; // [rsp+30h] [rbp-D0h]
  __int128 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  int v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v8 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v10 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = -1;
  v14 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v9,
      L"ServerBFEHandler::RemovePolicyForInterface",
      &v8,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  v2 = 0;
  EnterCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
  for ( i = ServerBFEHandler::interfacePolicyMapping; i; i = *(struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP **)i )
  {
    if ( *((void **)i + 1) == a1 )
    {
      v4 = ServerBFEHandler::RemovePolicyForMap(i);
      v8 = v4;
      if ( v4 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"RemovePolicy failed: %d", v4);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v15);
        }
      }
      else
      {
        if ( v2 )
          *(_QWORD *)v2 = *(_QWORD *)i;
        else
          ServerBFEHandler::interfacePolicyMapping = *(struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP **)ServerBFEHandler::interfacePolicyMapping;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, i);
      }
      break;
    }
    v2 = i;
  }
  LeaveCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v8);
  }
  v6 = v8;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v9);
  return v6;
}

```

## disassembly

```asm
0x18003fed8  push    rbp
0x18003feda  push    rbx
0x18003fedb  push    rsi
0x18003fedc  push    rdi
0x18003fedd  lea     rbp, [rsp-778h]
0x18003fee5  sub     rsp, 878h
0x18003feec  mov     rax, cs:__security_cookie
0x18003fef3  xor     rax, rsp
0x18003fef6  mov     [rbp+790h+var_30], rax
0x18003fefd  mov     rsi, rcx
0x18003ff00  mov     [rsp+890h+var_870], 0
0x18003ff08  xor     eax, eax
0x18003ff0a  mov     [rsp+890h+var_830], eax
0x18003ff0e  xor     edx, edx; Val
0x18003ff10  mov     r8d, 7FCh; Size
0x18003ff16  lea     rcx, [rsp+890h+var_82C]; void *
0x18003ff1b  call    memset_0
0x18003ff20  xorps   xmm0, xmm0
0x18003ff23  movdqu  [rsp+890h+var_860], xmm0
0x18003ff29  mov     [rsp+890h+var_868], 0
0x18003ff32  xorps   xmm1, xmm1
0x18003ff35  movdqu  [rsp+890h+var_850], xmm1
0x18003ff3b  mov     [rsp+890h+var_840], 0
0x18003ff44  mov     [rsp+890h+var_838], 0FFFFFFFFh
0x18003ff4c  mov     [rsp+890h+var_834], 0
0x18003ff54  test    cs:byte_1800AA941, 8
0x18003ff5b  jz      short loc_18003FF7A
0x18003ff5d  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003ff64  lea     r8, [rsp+890h+var_870]; unsigned int *
0x18003ff69  lea     rdx, aServerbfehandl_13; "ServerBFEHandler::RemovePolicyForInterf"...
0x18003ff70  lea     rcx, [rsp+890h+var_868]; this
0x18003ff75  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003ff7a  xor     edi, edi
0x18003ff7c  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ff83  call    cs:__imp_EnterCriticalSection
0x18003ff89  mov     rbx, cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18003ff90  jmp     short loc_18003FF9E
0x18003ff92  cmp     [rbx+8], rsi
0x18003ff96  jz      short loc_18003FFA8
0x18003ff98  mov     rdi, rbx
0x18003ff9b  mov     rbx, [rbx]
0x18003ff9e  test    rbx, rbx
0x18003ffa1  jnz     short loc_18003FF92
0x18003ffa3  jmp     loc_180040031
0x18003ffa8  mov     rcx, rbx; struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *
0x18003ffab  call    ?RemovePolicyForMap@ServerBFEHandler@@KAKPEAU_VPNIKE_INTERFACE_POLICY_MAP@1@@Z; ServerBFEHandler::RemovePolicyForMap(ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *)
0x18003ffb0  mov     r8d, eax
0x18003ffb3  mov     [rsp+890h+var_870], eax
0x18003ffb7  test    eax, eax
0x18003ffb9  jz      short loc_18003FFFF
0x18003ffbb  test    cs:byte_1800AA941, 4
0x18003ffc2  jz      short loc_180040031
0x18003ffc4  xor     eax, eax
0x18003ffc6  mov     word ptr [rsp+890h+var_830], ax
0x18003ffcb  lea     rdx, aRemovepolicyFa_0; "RemovePolicy failed: %d"
0x18003ffd2  lea     rcx, [rsp+890h+var_830]
0x18003ffd7  call    FormatRRASErrorString
0x18003ffdc  test    cs:byte_1800AA941, 4
0x18003ffe3  jz      short loc_180040031
0x18003ffe5  lea     r8, [rsp+890h+var_830]
0x18003ffea  lea     rdx, RasVpnIkeTraceError
0x18003fff1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003fff8  call    McTemplateU0z_EventWriteTransfer
0x18003fffd  jmp     short loc_180040031
0x18003ffff  test    rdi, rdi
0x180040002  jnz     short loc_180040017
0x180040004  mov     rax, cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18004000b  mov     rcx, [rax]
0x18004000e  mov     cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA, rcx; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x180040015  jmp     short loc_18004001D
0x180040017  mov     rax, [rbx]
0x18004001a  mov     [rdi], rax
0x18004001d  call    cs:__imp_GetProcessHeap
0x180040023  mov     rcx, rax; hHeap
0x180040026  mov     r8, rbx; lpMem
0x180040029  xor     edx, edx; dwFlags
0x18004002b  call    cs:__imp_HeapFree
0x180040031  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180040038  call    cs:__imp_LeaveCriticalSection
0x18004003e  lea     rax, WPP_GLOBAL_Control
0x180040045  mov     rcx, cs:WPP_GLOBAL_Control
0x18004004c  cmp     rcx, rax
0x18004004f  jz      short loc_180040077
0x180040051  test    byte ptr [rcx+1Ch], 1
0x180040055  jz      short loc_180040077
0x180040057  cmp     byte ptr [rcx+19h], 6
0x18004005b  jb      short loc_180040077
0x18004005d  mov     edx, 3Dh ; '='
0x180040062  mov     r9d, [rsp+890h+var_870]
0x180040067  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18004006e  mov     rcx, [rcx+10h]
0x180040072  call    WPP_SF_d
0x180040077  mov     ebx, [rsp+890h+var_870]
0x18004007b  lea     rcx, [rsp+890h+var_868]; this
0x180040080  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040085  mov     eax, ebx
0x180040087  mov     rcx, [rbp+790h+var_30]
0x18004008e  xor     rcx, rsp; StackCookie
0x180040091  call    __security_check_cookie
0x180040096  add     rsp, 878h
0x18004009d  pop     rdi
0x18004009e  pop     rsi
0x18004009f  pop     rbx
0x1800400a0  pop     rbp
0x1800400a1  retn
```
