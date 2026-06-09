# VPNIKEProtocolEngine::UpdateInterface(ulong,int)

- ea: `0x180007070`
- end: `0x180007466`
- name: `?UpdateInterface@VPNIKEProtocolEngine@@QEAAXKH@Z`
- size: `1014`
- prototype: `void(VPNIKEProtocolEngine *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180057c30`

## callees

- `0x180007070`
- `0x180007590`
- `0x180007794`
- `0x1800078d4`
- `0x180007924`
- `0x18001e0b0`
- `0x18005d9ac`
- `0x180066b00`
- `0x180066c0c`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007241`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007241`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800072f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000731d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000731d`

## string_xrefs

- `0x180007127`: `UpdateInterface dwInterfaceIndex: %d Tunnel is V4: %u`
- `0x18000718c`: `UpdateInterface looping through numberOfActiveConnections: %u`
- `0x180007205`: `UpdateInterface ignoring connection index:%u`
- `0x180007330`: `Connection %p is not using interface %d or is not using the same IP protocol as the tunnel. Skipping.`
- `0x1800072d6`: `UpdateInterface trying to roam`

## pseudocode

```c
void __fastcall VPNIKEProtocolEngine::UpdateInterface(VPNIKEProtocolEngine *this, unsigned int a2, unsigned int a3)
{
  VPNIKEProtocolEngine *v3; // rbx
  __int64 i; // rbx
  __int64 v7; // rsi
  __int64 *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r14d
  int v12; // edi
  unsigned int IPv4AddressFromIndex; // eax
  __int64 j; // rdi
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  int v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID lpMem[2]; // [rsp+38h] [rbp-C8h] BYREF
  VPNIKEProtocolEngine *v21; // [rsp+48h] [rbp-B8h]
  struct tagRASTUNNELENDPOINT v22; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v3 = VpnIkeProtocolEngine;
  v21 = VpnIkeProtocolEngine;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, a2, a3 != 0);
  }
  lpMem[0] = 0;
  v23 = 0;
  v18 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"UpdateInterface dwInterfaceIndex: %d Tunnel is V4: %u", a2, a3);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v23);
  }
  (*(void (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(**((_QWORD **)v3 + 1) + 64LL))(
    *((_QWORD *)v3 + 1),
    lpMem,
    &v18);
  if ( (byte_1800AA941 & 8) != 0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"UpdateInterface looping through numberOfActiveConnections: %u", v18);
    if ( (byte_1800AA941 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v23);
  }
  for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
  {
    v19 = 0;
    memset(&v22, 0, sizeof(v22));
    v7 = *((_QWORD *)lpMem[0] + i);
    if ( *(_DWORD *)(*(_QWORD *)(v7 + 112) + 40LL) == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 160));
      v11 = *(_DWORD *)(v7 + 108);
      v12 = *(unsigned __int8 *)(v7 + 16);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v17) = *(_BYTE *)(v7 + 16);
        WPP_SF_ddc(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v10,
          *(unsigned int *)(*(_QWORD *)(v7 + 32) + 48LL),
          v11,
          v17);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 160));
      if ( v11 == a2 && a3 == v12 )
      {
        if ( (_BYTE)v12 )
          IPv4AddressFromIndex = GetIPv4AddressFromIndex(a2, &v22.ipv4, &v19);
        else
          IPv4AddressFromIndex = GetIPv6AddressFromIndex(a2, &v22.ipv4, &v19);
        if ( IPv4AddressFromIndex )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v23) = 0;
            FormatRRASErrorString(&v23, L"GetIPvXAddressFromIndex failed. Error: %d", IPv4AddressFromIndex);
            if ( (byte_1800AA941 & 4) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v23);
          }
          break;
        }
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasVpnIkeTraceInfo,
            L"UpdateInterface trying to roam");
        EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 160));
        VPNIKEClientConnection::RoamToBestCostInterface(
          (VPNIKEClientConnection *)v7,
          a2,
          *((struct ThreadPoolHelper **)v21 + 3),
          &v22,
          v19);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 160));
      }
      else if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(
          &v23,
          L"Connection %p is not using interface %d or is not using the same IP protocol as the tunnel. Skipping.",
          v7,
          a2);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v8 = RasVpnIkeTraceError;
          goto LABEL_33;
        }
      }
    }
    else if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"UpdateInterface ignoring connection index:%u", (unsigned int)i);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v8 = RasVpnIkeTraceInfo;
LABEL_33:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v8, &v23);
        continue;
      }
    }
  }
  for ( j = 0; (unsigned int)j < v18; j = (unsigned int)(j + 1) )
  {
    BaseConnection::DeleteRef(*((BaseConnection **)lpMem[0] + j));
    *((_QWORD *)lpMem[0] + j) = 0;
  }
  v15 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
    lpMem[0] = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
}

```

## disassembly

```asm
0x180007070  mov     [rsp-8+arg_0], rbx
0x180007075  push    rbp
0x180007076  push    rsi
0x180007077  push    rdi
0x180007078  push    r12
0x18000707a  push    r13
0x18000707c  push    r14
0x18000707e  push    r15
0x180007080  lea     rbp, [rsp-780h]
0x180007088  sub     rsp, 880h
0x18000708f  mov     rax, cs:__security_cookie
0x180007096  xor     rax, rsp
0x180007099  mov     [rbp+7B0h+var_40], rax
0x1800070a0  mov     rbx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800070a7  mov     r13d, r8d
0x1800070aa  mov     [rsp+8B0h+var_868], rbx
0x1800070af  mov     r15d, edx
0x1800070b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070b9  lea     rsi, WPP_GLOBAL_Control
0x1800070c0  cmp     rcx, rsi
0x1800070c3  jz      short loc_1800070F3
0x1800070c5  test    byte ptr [rcx+1Ch], 1
0x1800070c9  jz      short loc_1800070F3
0x1800070cb  cmp     byte ptr [rcx+19h], 6
0x1800070cf  jb      short loc_1800070F3
0x1800070d1  mov     rcx, [rcx+10h]
0x1800070d5  test    r8d, r8d
0x1800070d8  mov     edx, 67h ; 'g'
0x1800070dd  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x1800070e4  setnz   al
0x1800070e7  mov     r9d, r15d
0x1800070ea  mov     byte ptr [rsp+8B0h+var_890], al
0x1800070ee  call    WPP_SF_dc
0x1800070f3  xor     eax, eax
0x1800070f5  mov     [rsp+8B0h+lpMem], 0
0x1800070fe  xor     edx, edx; Val
0x180007100  mov     [rsp+8B0h+var_840], eax
0x180007104  mov     r8d, 7FCh; Size
0x18000710a  mov     [rsp+8B0h+var_880], 0
0x180007112  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180007117  call    memset_0
0x18000711c  test    cs:byte_1800AA941, 8
0x180007123  jz      short loc_180007164
0x180007125  xor     eax, eax
0x180007127  lea     rdx, aUpdateinterfac_2; "UpdateInterface dwInterfaceIndex: %d Tu"...
0x18000712e  mov     r9d, r13d
0x180007131  mov     word ptr [rsp+8B0h+var_840], ax
0x180007136  mov     r8d, r15d
0x180007139  lea     rcx, [rsp+8B0h+var_840]
0x18000713e  call    FormatRRASErrorString
0x180007143  test    cs:byte_1800AA941, 8
0x18000714a  jz      short loc_180007164
0x18000714c  lea     r8, [rsp+8B0h+var_840]
0x180007151  lea     rdx, RasVpnIkeTraceInfo
0x180007158  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000715f  call    McTemplateU0z_EventWriteTransfer
0x180007164  mov     rcx, [rbx+8]
0x180007168  lea     r8, [rsp+8B0h+var_880]
0x18000716d  lea     rdx, [rsp+8B0h+lpMem]
0x180007172  mov     rax, [rcx]
0x180007175  mov     rax, [rax+40h]
0x180007179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717e  test    cs:byte_1800AA941, 8
0x180007185  jz      short loc_1800071C5
0x180007187  mov     r8d, [rsp+8B0h+var_880]
0x18000718c  lea     rdx, aUpdateinterfac; "UpdateInterface looping through numberO"...
0x180007193  xor     eax, eax
0x180007195  lea     rcx, [rsp+8B0h+var_840]
0x18000719a  mov     word ptr [rsp+8B0h+var_840], ax
0x18000719f  call    FormatRRASErrorString
0x1800071a4  test    cs:byte_1800AA941, 8
0x1800071ab  jz      short loc_1800071C5
0x1800071ad  lea     r8, [rsp+8B0h+var_840]
0x1800071b2  lea     rdx, RasVpnIkeTraceInfo
0x1800071b9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800071c0  call    McTemplateU0z_EventWriteTransfer
0x1800071c5  xor     ebx, ebx
0x1800071c7  cmp     ebx, [rsp+8B0h+var_880]
0x1800071cb  jnb     loc_1800073B6
0x1800071d1  xor     eax, eax
0x1800071d3  xorps   xmm0, xmm0
0x1800071d6  mov     dword ptr [rsp+8B0h+var_860.4+0Ch], eax
0x1800071da  mov     [rsp+8B0h+var_87C], eax
0x1800071de  mov     rax, [rsp+8B0h+lpMem]
0x1800071e3  movups  xmmword ptr [rsp+8B0h+var_860.dwType], xmm0
0x1800071e8  mov     rsi, [rax+rbx*8]
0x1800071ec  mov     rax, [rsi+70h]
0x1800071f0  cmp     dword ptr [rax+28h], 1
0x1800071f4  jz      short loc_180007237
0x1800071f6  test    cs:byte_1800AA941, 8
0x1800071fd  jz      loc_18000736D
0x180007203  xor     eax, eax
0x180007205  lea     rdx, aUpdateinterfac_0; "UpdateInterface ignoring connection ind"...
0x18000720c  mov     r8d, ebx
0x18000720f  mov     word ptr [rsp+8B0h+var_840], ax
0x180007214  lea     rcx, [rsp+8B0h+var_840]
0x180007219  call    FormatRRASErrorString
0x18000721e  test    cs:byte_1800AA941, 8
0x180007225  jz      loc_18000736D
0x18000722b  lea     rdx, RasVpnIkeTraceInfo
0x180007232  jmp     loc_18000735C
0x180007237  lea     r12, [rsi+0A0h]
0x18000723e  mov     rcx, r12; lpCriticalSection
0x180007241  call    cs:__imp_EnterCriticalSection
0x180007247  mov     r14d, [rsi+6Ch]
0x18000724b  movzx   edi, byte ptr [rsi+10h]
0x18000724f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007256  lea     rax, WPP_GLOBAL_Control
0x18000725d  cmp     rcx, rax
0x180007260  jz      short loc_180007289
0x180007262  test    byte ptr [rcx+1Ch], 1
0x180007266  jz      short loc_180007289
0x180007268  cmp     byte ptr [rcx+19h], 5
0x18000726c  jb      short loc_180007289
0x18000726e  mov     r9, [rsi+20h]
0x180007272  mov     rcx, [rcx+10h]
0x180007276  mov     [rsp+8B0h+var_888], dil
0x18000727b  mov     [rsp+8B0h+var_890], r14d
0x180007280  mov     r9d, [r9+30h]
0x180007284  call    WPP_SF_ddc
0x180007289  mov     rcx, r12; lpCriticalSection
0x18000728c  call    cs:__imp_LeaveCriticalSection
0x180007292  cmp     r14d, r15d
0x180007295  jnz     loc_180007325
0x18000729b  cmp     r13d, edi
0x18000729e  jnz     loc_180007325
0x1800072a4  lea     r8, [rsp+8B0h+var_87C]
0x1800072a9  mov     ecx, r15d
0x1800072ac  lea     rdx, [rsp+8B0h+var_860.4]
0x1800072b1  test    dil, dil
0x1800072b4  jz      short loc_1800072BD
0x1800072b6  call    GetIPv4AddressFromIndex
0x1800072bb  jmp     short loc_1800072C2
0x1800072bd  call    GetIPv6AddressFromIndex
0x1800072c2  mov     r8d, eax
0x1800072c5  test    eax, eax
0x1800072c7  jnz     loc_180007374
0x1800072cd  test    cs:byte_1800AA941, 8
0x1800072d4  jz      short loc_1800072F0
0x1800072d6  lea     r8, aUpdateinterfac_1; "UpdateInterface trying to roam"
0x1800072dd  lea     rdx, RasVpnIkeTraceInfo
0x1800072e4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800072eb  call    McTemplateU0z_EventWriteTransfer
0x1800072f0  mov     rcx, r12; lpCriticalSection
0x1800072f3  call    cs:__imp_EnterCriticalSection
0x1800072f9  mov     eax, [rsp+8B0h+var_87C]
0x1800072fd  lea     r9, [rsp+8B0h+var_860]; struct tagRASTUNNELENDPOINT *
0x180007302  mov     [rsp+8B0h+var_890], eax; unsigned int
0x180007306  mov     edx, r15d; unsigned int
0x180007309  mov     rax, [rsp+8B0h+var_868]
0x18000730e  mov     rcx, rsi; this
0x180007311  mov     r8, [rax+18h]; struct ThreadPoolHelper *
0x180007315  call    ?RoamToBestCostInterface@VPNIKEClientConnection@@QEAAXKPEAVThreadPoolHelper@@PEAUtagRASTUNNELENDPOINT@@K@Z; VPNIKEClientConnection::RoamToBestCostInterface(ulong,ThreadPoolHelper *,tagRASTUNNELENDPOINT *,ulong)
0x18000731a  mov     rcx, r12; lpCriticalSection
0x18000731d  call    cs:__imp_LeaveCriticalSection
0x180007323  jmp     short loc_18000736D
0x180007325  test    cs:byte_1800AA941, 4
0x18000732c  jz      short loc_18000736D
0x18000732e  xor     eax, eax
0x180007330  lea     rdx, aConnectionPIsN; "Connection %p is not using interface %d"...
0x180007337  mov     r9d, r15d
0x18000733a  mov     word ptr [rsp+8B0h+var_840], ax
0x18000733f  mov     r8, rsi
0x180007342  lea     rcx, [rsp+8B0h+var_840]
0x180007347  call    FormatRRASErrorString
0x18000734c  test    cs:byte_1800AA941, 4
0x180007353  jz      short loc_18000736D
0x180007355  lea     rdx, RasVpnIkeTraceError
0x18000735c  lea     r8, [rsp+8B0h+var_840]
0x180007361  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007368  call    McTemplateU0z_EventWriteTransfer
0x18000736d  inc     ebx
0x18000736f  jmp     loc_1800071C7
0x180007374  test    cs:byte_1800AA941, 4
0x18000737b  jz      short loc_1800073B6
0x18000737d  xor     eax, eax
0x18000737f  lea     rdx, aGetipvxaddress; "GetIPvXAddressFromIndex failed. Error: "...
0x180007386  lea     rcx, [rsp+8B0h+var_840]
0x18000738b  mov     word ptr [rsp+8B0h+var_840], ax
0x180007390  call    FormatRRASErrorString
0x180007395  test    cs:byte_1800AA941, 4
0x18000739c  jz      short loc_1800073B6
0x18000739e  lea     r8, [rsp+8B0h+var_840]
0x1800073a3  lea     rdx, RasVpnIkeTraceError
0x1800073aa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800073b1  call    McTemplateU0z_EventWriteTransfer
0x1800073b6  xor     edi, edi
0x1800073b8  cmp     [rsp+8B0h+var_880], edi
0x1800073bc  jbe     short loc_1800073E1
0x1800073be  mov     rcx, [rsp+8B0h+lpMem]
0x1800073c3  mov     rcx, [rcx+rdi*8]; this
0x1800073c7  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x1800073cc  mov     rax, [rsp+8B0h+lpMem]
0x1800073d1  mov     qword ptr [rax+rdi*8], 0
0x1800073d9  inc     edi
0x1800073db  cmp     edi, [rsp+8B0h+var_880]
0x1800073df  jb      short loc_1800073BE
0x1800073e1  mov     rbx, [rsp+8B0h+lpMem]
0x1800073e6  test    rbx, rbx
0x1800073e9  jz      short loc_180007408
0x1800073eb  call    cs:__imp_GetProcessHeap
0x1800073f1  mov     r8, rbx; lpMem
0x1800073f4  xor     edx, edx; dwFlags
0x1800073f6  mov     rcx, rax; hHeap
0x1800073f9  call    cs:__imp_HeapFree
0x1800073ff  mov     [rsp+8B0h+lpMem], 0
0x180007408  mov     rcx, cs:WPP_GLOBAL_Control
0x18000740f  lea     rax, WPP_GLOBAL_Control
0x180007416  cmp     rcx, rax
0x180007419  jz      short loc_18000743C
0x18000741b  test    byte ptr [rcx+1Ch], 1
0x18000741f  jz      short loc_18000743C
0x180007421  cmp     byte ptr [rcx+19h], 6
0x180007425  jb      short loc_18000743C
0x180007427  mov     rcx, [rcx+10h]
0x18000742b  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180007432  mov     edx, 69h ; 'i'
0x180007437  call    WPP_SF_
0x18000743c  mov     rcx, [rbp+7B0h+var_40]
0x180007443  xor     rcx, rsp; StackCookie
0x180007446  call    __security_check_cookie
0x18000744b  mov     rbx, [rsp+8B0h+arg_0]
0x180007453  add     rsp, 880h
0x18000745a  pop     r15
0x18000745c  pop     r14
0x18000745e  pop     r13
0x180007460  pop     r12
0x180007462  pop     rdi
0x180007463  pop     rsi
0x180007464  pop     rbp
0x180007465  retn
```
