# IPNotifications::AddOrModifyIPAddressChangeForConnection(_CONNECTION_ID_ &,_SOCKADDR_INET &,ulong)

- ea: `0x180056d30`
- end: `0x1800570d9`
- name: `?AddOrModifyIPAddressChangeForConnection@IPNotifications@@UEAAKAEAT_CONNECTION_ID_@@AEAT_SOCKADDR_INET@@K@Z`
- size: `937`
- prototype: `__int64 __fastcall(char *CallerContext, union _CONNECTION_ID_ *, const SOCKADDR *, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x1800095f8`
- `0x180056d30`
- `0x1800587ac`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057060`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057060`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056eaa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056f1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056eaa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056f1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057034`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056e98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056f09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057034`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057052`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056e18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056e18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057022`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057022`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180056e3b`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x180056e3b`

## string_xrefs

- `0x180056f57`: `DELETE List: Insert IP Address[%S]`
- `0x180056fee`: `DELETE List: Insert ConnectionID[0x%X] for IP Address[%S]`

## pseudocode

```c
__int64 __fastcall IPNotifications::AddOrModifyIPAddressChangeForConnection(
        char *CallerContext,
        union _CONNECTION_ID_ *a2,
        const SOCKADDR *a3,
        int a4)
{
  unsigned int *v7; // rdi
  char v8; // r15
  char *i; // rbx
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 *v12; // rdx
  HANDLE ProcessHeap; // rax
  const wchar_t *v14; // r8
  HANDLE v15; // rax
  char *v16; // rax
  __int64 v17; // rcx
  HANDLE v18; // rax
  HANDLE v19; // rax
  unsigned int v20; // ebx
  unsigned int v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  __int128 v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v23 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  v7 = 0;
  v22 = 0;
  v8 = 0;
  i = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v28 = -1;
  v29 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v24,
      L"IPNotifications::AddOrModifyIPAddressChangeForConnection",
      &v22,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  EnterCriticalSection((LPCRITICAL_SECTION)(CallerContext + 32));
  if ( *((_QWORD *)CallerContext + 1)
    || (v11 = NotifyUnicastIpAddressChange(
                0,
                IPNotifications::IPNotificationsCallback,
                CallerContext,
                0,
                (HANDLE *)CallerContext + 1),
        v10 = v11,
        (v22 = v11) == 0) )
  {
    (*(void (__fastcall **)(char *, union _CONNECTION_ID_ *, __int64))(*(_QWORD *)CallerContext + 8LL))(
      CallerContext,
      a2,
      v10);
    ProcessHeap = GetProcessHeap();
    v7 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( !v7 )
    {
LABEL_13:
      v22 = 8;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_30;
      v14 = L"VPNIKE_MALLOC failed.";
      v12 = RasVpnIkeTraceError;
      goto LABEL_29;
    }
    for ( i = (char *)*((_QWORD *)CallerContext + 2); i; i = (char *)*((_QWORD *)i + 141) )
    {
      if ( INETADDR_ISEQUAL((const SOCKADDR *)i, a3) )
      {
        v8 = 1;
        goto LABEL_25;
      }
    }
    v15 = GetProcessHeap();
    v16 = (char *)HeapAlloc(v15, 8u, 0x470u);
    i = v16;
    if ( !v16 )
      goto LABEL_13;
    LOBYTE(v17) = a3->sa_family == 2;
    IPToString(v17, &a3->sa_data[2], &a3->sa_data[6], v16 + 32);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"DELETE List: Insert IP Address[%S]", i + 32);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v30);
    }
    *((_DWORD *)i + 7) = v23;
    *(SOCKADDR *)i = *a3;
    *(SOCKADDR *)(i + 12) = *(SOCKADDR *)&a3->sa_data[10];
    *((_QWORD *)i + 141) = *((_QWORD *)CallerContext + 2);
    *((_QWORD *)CallerContext + 2) = i;
    v8 = 0;
LABEL_25:
    *(_QWORD *)v7 = *(_QWORD *)a2;
    *((_QWORD *)v7 + 1) = *(_QWORD *)&i[8 * (*(_DWORD *)a2 & 0x7F) + 104];
    *(_QWORD *)&i[8 * (*(_DWORD *)a2 & 0x7F) + 104] = v7;
    ++*((_DWORD *)i + 25);
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"DELETE List: Insert ConnectionID[0x%X] for IP Address[%S]", *v7, i + 32);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v12 = RasVpnIkeTraceInfo;
        goto LABEL_28;
      }
    }
  }
  else if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"NotifyUnicastIpAddressChange failed: %d", v11);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v12 = RasVpnIkeTraceError;
LABEL_28:
      v14 = (const wchar_t *)&v30;
LABEL_29:
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v12, v14);
    }
  }
LABEL_30:
  LeaveCriticalSection((LPCRITICAL_SECTION)(CallerContext + 32));
  if ( v22 )
  {
    if ( v7 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v7);
    }
    if ( !v8 && i )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, i);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, v22);
  }
  v20 = v22;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v24);
  return v20;
}

```

## disassembly

```asm
0x180056d30  mov     [rsp-8+arg_18], rbx
0x180056d35  push    rbp
0x180056d36  push    rsi
0x180056d37  push    rdi
0x180056d38  push    r12
0x180056d3a  push    r13
0x180056d3c  push    r14
0x180056d3e  push    r15
0x180056d40  lea     rbp, [rsp-790h]
0x180056d48  sub     rsp, 890h
0x180056d4f  mov     rax, cs:__security_cookie
0x180056d56  xor     rax, rsp
0x180056d59  mov     [rbp+7C0h+var_40], rax
0x180056d60  mov     [rsp+8C0h+var_888], r9d
0x180056d65  mov     r14, r8
0x180056d68  mov     r12, rdx
0x180056d6b  mov     rsi, rcx
0x180056d6e  lea     rax, WPP_GLOBAL_Control
0x180056d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d7c  cmp     rcx, rax
0x180056d7f  jz      short loc_180056DA2
0x180056d81  test    byte ptr [rcx+1Ch], 1
0x180056d85  jz      short loc_180056DA2
0x180056d87  cmp     byte ptr [rcx+19h], 6
0x180056d8b  jb      short loc_180056DA2
0x180056d8d  mov     edx, 2Ah ; '*'
0x180056d92  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180056d99  mov     rcx, [rcx+10h]
0x180056d9d  call    WPP_SF_
0x180056da2  xor     edi, edi
0x180056da4  mov     [rsp+8C0h+var_88C], edi
0x180056da8  mov     r15b, dil
0x180056dab  mov     [rsp+8C0h+var_890], dil
0x180056db0  mov     ebx, edi
0x180056db2  mov     [rbp+7C0h+var_840], edi
0x180056db5  xor     edx, edx; Val
0x180056db7  mov     r8d, 7FCh; Size
0x180056dbd  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180056dc1  call    memset_0
0x180056dc6  xorps   xmm0, xmm0
0x180056dc9  movdqu  [rsp+8C0h+var_878], xmm0
0x180056dcf  mov     [rsp+8C0h+var_880], rdi
0x180056dd4  xorps   xmm1, xmm1
0x180056dd7  movdqu  [rsp+8C0h+var_868], xmm1
0x180056ddd  mov     [rsp+8C0h+var_858], rdi
0x180056de2  mov     [rsp+8C0h+var_850], 0FFFFFFFFh
0x180056dea  mov     [rsp+8C0h+var_84C], edi
0x180056dee  test    cs:byte_1800AA941, 8
0x180056df5  jz      short loc_180056E14
0x180056df7  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180056dfe  lea     r8, [rsp+8C0h+var_88C]; unsigned int *
0x180056e03  lea     rdx, aIpnotification; "IPNotifications::AddOrModifyIPAddressCh"...
0x180056e0a  lea     rcx, [rsp+8C0h+var_880]; this
0x180056e0f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180056e14  lea     rcx, [rsi+20h]; lpCriticalSection
0x180056e18  call    cs:__imp_EnterCriticalSection
0x180056e1e  lea     rax, [rsi+8]
0x180056e22  cmp     [rax], rdi
0x180056e25  jnz     short loc_180056E86
0x180056e27  xor     ecx, ecx; Family
0x180056e29  mov     [rsp+8C0h+NotificationHandle], rax; NotificationHandle
0x180056e2e  xor     r9d, r9d; InitialNotification
0x180056e31  mov     r8, rsi; CallerContext
0x180056e34  lea     rdx, ?IPNotificationsCallback@IPNotifications@@SAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x180056e3b  call    cs:__imp_NotifyUnicastIpAddressChange
0x180056e41  mov     r8d, eax
0x180056e44  mov     [rsp+8C0h+var_88C], eax
0x180056e48  test    eax, eax
0x180056e4a  jz      short loc_180056E86
0x180056e4c  test    cs:byte_1800AA941, 4
0x180056e53  jz      loc_18005701E
0x180056e59  mov     word ptr [rbp+7C0h+var_840], di
0x180056e5d  lea     rdx, aNotifyunicasti; "NotifyUnicastIpAddressChange failed: %d"
0x180056e64  lea     rcx, [rbp+7C0h+var_840]
0x180056e68  call    FormatRRASErrorString
0x180056e6d  test    cs:byte_1800AA941, 4
0x180056e74  jz      loc_18005701E
0x180056e7a  lea     rdx, RasVpnIkeTraceError
0x180056e81  jmp     loc_18005700E
0x180056e86  mov     rax, [rsi]
0x180056e89  mov     rdx, r12
0x180056e8c  mov     rcx, rsi
0x180056e8f  mov     rax, [rax+8]
0x180056e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e98  call    cs:__imp_GetProcessHeap
0x180056e9e  mov     rcx, rax; hHeap
0x180056ea1  mov     edx, 8; dwFlags
0x180056ea6  lea     r8d, [rdx+8]; dwBytes
0x180056eaa  call    cs:__imp_HeapAlloc
0x180056eb0  mov     rdi, rax
0x180056eb3  test    rax, rax
0x180056eb6  jnz     short loc_180056EE0
0x180056eb8  mov     [rsp+8C0h+var_88C], 8
0x180056ec0  test    cs:byte_1800AA941, 4
0x180056ec7  jz      loc_18005701E
0x180056ecd  lea     r8, aVpnikeMallocFa_4; "VPNIKE_MALLOC failed."
0x180056ed4  lea     rdx, RasVpnIkeTraceError
0x180056edb  jmp     loc_180057012
0x180056ee0  mov     rbx, [rsi+10h]
0x180056ee4  test    rbx, rbx
0x180056ee7  jz      short loc_180056F09
0x180056ee9  mov     rdx, r14; b
0x180056eec  mov     rcx, rbx; a
0x180056eef  call    INETADDR_ISEQUAL
0x180056ef4  test    al, al
0x180056ef6  jnz     short loc_180056F01
0x180056ef8  mov     rbx, [rbx+468h]
0x180056eff  jmp     short loc_180056EE4
0x180056f01  mov     r15b, 1
0x180056f04  jmp     loc_180056FB2
0x180056f09  call    cs:__imp_GetProcessHeap
0x180056f0f  mov     rcx, rax; hHeap
0x180056f12  mov     edx, 8; dwFlags
0x180056f17  mov     r8d, 470h; dwBytes
0x180056f1d  call    cs:__imp_HeapAlloc
0x180056f23  mov     rbx, rax
0x180056f26  test    rax, rax
0x180056f29  jz      short loc_180056EB8
0x180056f2b  lea     r8, [r14+8]
0x180056f2f  lea     rdx, [r14+4]
0x180056f33  cmp     word ptr [r14], 2
0x180056f38  setz    cl
0x180056f3b  lea     r9, [rax+20h]
0x180056f3f  call    IPToString
0x180056f44  test    cs:byte_1800AA941, 8
0x180056f4b  jz      short loc_180056F87
0x180056f4d  xor     eax, eax
0x180056f4f  mov     word ptr [rbp+7C0h+var_840], ax
0x180056f53  lea     r8, [rbx+20h]
0x180056f57  lea     rdx, aDeleteListInse_0; "DELETE List: Insert IP Address[%S]"
0x180056f5e  lea     rcx, [rbp+7C0h+var_840]
0x180056f62  call    FormatRRASErrorString
0x180056f67  test    cs:byte_1800AA941, 8
0x180056f6e  jz      short loc_180056F87
0x180056f70  lea     r8, [rbp+7C0h+var_840]
0x180056f74  lea     rdx, RasVpnIkeTraceInfo
0x180056f7b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180056f82  call    McTemplateU0z_EventWriteTransfer
0x180056f87  mov     eax, [rsp+8C0h+var_888]
0x180056f8b  mov     [rbx+1Ch], eax
0x180056f8e  movups  xmm0, xmmword ptr [r14]
0x180056f92  movups  xmmword ptr [rbx], xmm0
0x180056f95  movups  xmm1, xmmword ptr [r14+0Ch]
0x180056f9a  movups  xmmword ptr [rbx+0Ch], xmm1
0x180056f9e  mov     rax, [rsi+10h]
0x180056fa2  mov     [rbx+468h], rax
0x180056fa9  mov     [rsi+10h], rbx
0x180056fad  mov     r15b, [rsp+8C0h+var_890]
0x180056fb2  mov     rax, [r12]
0x180056fb6  mov     [rdi], rax
0x180056fb9  mov     eax, [r12]
0x180056fbd  and     eax, 7Fh
0x180056fc0  mov     rax, [rbx+rax*8+68h]
0x180056fc5  mov     [rdi+8], rax
0x180056fc9  mov     eax, [r12]
0x180056fcd  and     eax, 7Fh
0x180056fd0  mov     [rbx+rax*8+68h], rdi
0x180056fd5  inc     dword ptr [rbx+64h]
0x180056fd8  test    cs:byte_1800AA941, 8
0x180056fdf  jz      short loc_18005701E
0x180056fe1  xor     eax, eax
0x180056fe3  mov     word ptr [rbp+7C0h+var_840], ax
0x180056fe7  lea     r9, [rbx+20h]
0x180056feb  mov     r8d, [rdi]
0x180056fee  lea     rdx, aDeleteListInse; "DELETE List: Insert ConnectionID[0x%X] "...
0x180056ff5  lea     rcx, [rbp+7C0h+var_840]
0x180056ff9  call    FormatRRASErrorString
0x180056ffe  test    cs:byte_1800AA941, 8
0x180057005  jz      short loc_18005701E
0x180057007  lea     rdx, RasVpnIkeTraceInfo
0x18005700e  lea     r8, [rbp+7C0h+var_840]
0x180057012  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180057019  call    McTemplateU0z_EventWriteTransfer
0x18005701e  lea     rcx, [rsi+20h]; lpCriticalSection
0x180057022  call    cs:__imp_LeaveCriticalSection
0x180057028  cmp     [rsp+8C0h+var_88C], 0
0x18005702d  jz      short loc_180057066
0x18005702f  test    rdi, rdi
0x180057032  jz      short loc_180057048
0x180057034  call    cs:__imp_GetProcessHeap
0x18005703a  mov     rcx, rax; hHeap
0x18005703d  mov     r8, rdi; lpMem
0x180057040  xor     edx, edx; dwFlags
0x180057042  call    cs:__imp_HeapFree
0x180057048  test    r15b, r15b
0x18005704b  jnz     short loc_180057066
0x18005704d  test    rbx, rbx
0x180057050  jz      short loc_180057066
0x180057052  call    cs:__imp_GetProcessHeap
0x180057058  mov     rcx, rax; hHeap
0x18005705b  mov     r8, rbx; lpMem
0x18005705e  xor     edx, edx; dwFlags
0x180057060  call    cs:__imp_HeapFree
0x180057066  mov     rcx, cs:WPP_GLOBAL_Control
0x18005706d  lea     rax, WPP_GLOBAL_Control
0x180057074  cmp     rcx, rax
0x180057077  jz      short loc_18005709F
0x180057079  test    byte ptr [rcx+1Ch], 1
0x18005707d  jz      short loc_18005709F
0x18005707f  cmp     byte ptr [rcx+19h], 6
0x180057083  jb      short loc_18005709F
0x180057085  mov     edx, 2Bh ; '+'
0x18005708a  mov     r9d, [rsp+8C0h+var_88C]
0x18005708f  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180057096  mov     rcx, [rcx+10h]
0x18005709a  call    WPP_SF_d
0x18005709f  mov     ebx, [rsp+8C0h+var_88C]
0x1800570a3  lea     rcx, [rsp+8C0h+var_880]; this
0x1800570a8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800570ad  mov     eax, ebx
0x1800570af  mov     rcx, [rbp+7C0h+var_40]
0x1800570b6  xor     rcx, rsp; StackCookie
0x1800570b9  call    __security_check_cookie
0x1800570be  mov     rbx, [rsp+8C0h+arg_18]
0x1800570c6  add     rsp, 890h
0x1800570cd  pop     r15
0x1800570cf  pop     r14
0x1800570d1  pop     r13
0x1800570d3  pop     r12
0x1800570d5  pop     rdi
0x1800570d6  pop     rsi
0x1800570d7  pop     rbp
0x1800570d8  retn
```
