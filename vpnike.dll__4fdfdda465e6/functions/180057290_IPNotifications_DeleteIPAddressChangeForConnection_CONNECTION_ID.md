# IPNotifications::DeleteIPAddressChangeForConnection(_CONNECTION_ID_ &)

- ea: `0x180057290`
- end: `0x18005764e`
- name: `?DeleteIPAddressChangeForConnection@IPNotifications@@UEAAKAEAT_CONNECTION_ID_@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(IPNotifications *this, union _CONNECTION_ID_ *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007590`
- `0x180007794`
- `0x180057290`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800574b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800575d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800574b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180057558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800575d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800574a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005754a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800575c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800574a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005754a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800575c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005737f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005737f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800575dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800575dd`

## string_xrefs

- `0x18005736a`: `IPNotifications::DeleteIPAddressChangeForConnection`
- `0x1800573ed`: `DELETE List: Remove ConnectionID[0x%X] for IP Address[%S]`
- `0x180057460`: `DELETE List: Remove IP Address [%S]`
- `0x18005750e`: `ADD List: Remove ConnectionID[0x%X] for IP Address[%S]`
- `0x180057581`: `ADD List: Remove IP Address [%S]`

## pseudocode

```c
__int64 __fastcall IPNotifications::DeleteIPAddressChangeForConnection(
        IPNotifications *this,
        union _CONNECTION_ID_ *a2)
{
  __int64 v4; // rdi
  char *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rdi
  __int64 i; // r14
  unsigned int *v10; // rsi
  HANDLE ProcessHeap; // rax
  char *v12; // rsi
  HANDLE v13; // rax
  char *v14; // rbx
  __int64 j; // rsi
  unsigned int *v16; // rdi
  HANDLE v17; // rax
  char *v18; // rdi
  HANDLE v19; // rax
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h]
  __int128 v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  LODWORD(v21) = 0;
  v4 = *(_DWORD *)a2 & 0x7F;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0xFFFFFFFFLL;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v22,
      L"IPNotifications::DeleteIPAddressChangeForConnection",
      (unsigned int *)&v21,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = (char *)this + 16;
  v6 = (unsigned int)v4;
  v7 = 8 * v4;
  v8 = 8 * v4;
LABEL_8:
  if ( *(_QWORD *)v5 )
  {
    v8 = 8 * v6;
    for ( i = *(_QWORD *)v5 + 8 * v6 + 104; ; i = (__int64)(v10 + 2) )
    {
      v10 = *(unsigned int **)i;
      if ( !*(_QWORD *)i )
      {
        v5 = (char *)(*(_QWORD *)v5 + 1128LL);
        goto LABEL_8;
      }
      if ( *v10 == *(_DWORD *)a2 )
        break;
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v27,
        L"DELETE List: Remove ConnectionID[0x%X] for IP Address[%S]",
        *v10,
        *(_QWORD *)v5 + 32LL,
        v21,
        v22,
        v23,
        v24,
        v25,
        v26);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v27);
    }
    *(_QWORD *)i = *(_QWORD *)(*(_QWORD *)i + 8LL);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
    --*(_DWORD *)(*(_QWORD *)v5 + 100LL);
    v12 = *(char **)v5;
    if ( !*(_DWORD *)(*(_QWORD *)v5 + 100LL) )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v27, L"DELETE List: Remove IP Address [%S]", v12 + 32);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v27);
      }
      *(_QWORD *)v5 = *(_QWORD *)(*(_QWORD *)v5 + 1128LL);
      if ( v12 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
      }
    }
  }
  v14 = (char *)this + 24;
LABEL_24:
  if ( *(_QWORD *)v14 )
  {
    for ( j = *(_QWORD *)v14 + v8 + 104; ; j = (__int64)(v16 + 2) )
    {
      v16 = *(unsigned int **)j;
      if ( !*(_QWORD *)j )
      {
        v14 = (char *)(*(_QWORD *)v14 + 1128LL);
        v8 = v7;
        goto LABEL_24;
      }
      if ( *(_DWORD *)a2 == *v16 )
        break;
    }
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(
        &v27,
        L"ADD List: Remove ConnectionID[0x%X] for IP Address[%S]",
        *v16,
        *(_QWORD *)v14 + 32LL);
      if ( (byte_1800AA941 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v27);
    }
    *(_QWORD *)j = *(_QWORD *)(*(_QWORD *)j + 8LL);
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    --*(_DWORD *)(*(_QWORD *)v14 + 100LL);
    v18 = *(char **)v14;
    if ( !*(_DWORD *)(*(_QWORD *)v14 + 100LL) )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v27, L"ADD List: Remove IP Address [%S]", v18 + 32);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v27);
      }
      *(_QWORD *)v14 = *(_QWORD *)(*(_QWORD *)v14 + 1128LL);
      if ( v18 )
      {
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v18);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return 0;
}

```

## disassembly

```asm
0x180057290  mov     [rsp-8+arg_10], rbx
0x180057295  push    rbp
0x180057296  push    rsi
0x180057297  push    rdi
0x180057298  push    r12
0x18005729a  push    r13
0x18005729c  push    r14
0x18005729e  push    r15
0x1800572a0  lea     rbp, [rsp-770h]
0x1800572a8  sub     rsp, 870h
0x1800572af  mov     rax, cs:__security_cookie
0x1800572b6  xor     rax, rsp
0x1800572b9  mov     [rbp+7A0h+var_40], rax
0x1800572c0  mov     r12, rdx
0x1800572c3  mov     r15, rcx
0x1800572c6  lea     rax, WPP_GLOBAL_Control
0x1800572cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800572d4  cmp     rcx, rax
0x1800572d7  jz      short loc_1800572FA
0x1800572d9  test    byte ptr [rcx+1Ch], 1
0x1800572dd  jz      short loc_1800572FA
0x1800572df  cmp     byte ptr [rcx+19h], 6
0x1800572e3  jb      short loc_1800572FA
0x1800572e5  mov     edx, 2Ch ; ','
0x1800572ea  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x1800572f1  mov     rcx, [rcx+10h]
0x1800572f5  call    WPP_SF_
0x1800572fa  mov     dword ptr [rsp+8A0h+var_880], 0
0x180057302  mov     edi, [r12]
0x180057306  and     edi, 7Fh
0x180057309  xor     eax, eax
0x18005730b  mov     [rsp+8A0h+var_840], eax
0x18005730f  xor     edx, edx; Val
0x180057311  mov     r8d, 7FCh; Size
0x180057317  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18005731c  call    memset_0
0x180057321  xorps   xmm0, xmm0
0x180057324  movdqu  [rsp+8A0h+var_870], xmm0
0x18005732a  mov     [rsp+8A0h+var_878], 0
0x180057333  xorps   xmm1, xmm1
0x180057336  movdqu  [rsp+8A0h+var_860], xmm1
0x18005733c  mov     [rsp+8A0h+var_850], 0
0x180057345  mov     [rsp+8A0h+var_848], 0FFFFFFFFh
0x18005734d  mov     [rsp+8A0h+var_844], 0
0x180057355  test    cs:byte_1800AA941, 8
0x18005735c  jz      short loc_18005737B
0x18005735e  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180057365  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x18005736a  lea     rdx, aIpnotification_0; "IPNotifications::DeleteIPAddressChangeF"...
0x180057371  lea     rcx, [rsp+8A0h+var_878]; this
0x180057376  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005737b  lea     rcx, [r15+20h]; lpCriticalSection
0x18005737f  call    cs:__imp_EnterCriticalSection
0x180057385  lea     rbx, [r15+10h]
0x180057389  mov     ecx, edi
0x18005738b  lea     r13, ds:0[rdi*8]
0x180057393  mov     rdi, r13
0x180057396  mov     rax, [rbx]
0x180057399  test    rax, rax
0x18005739c  jz      loc_1800574B8
0x1800573a2  lea     rdi, ds:0[rcx*8]
0x1800573aa  lea     r14, [rdi+68h]
0x1800573ae  add     r14, rax
0x1800573b1  mov     rsi, [r14]
0x1800573b4  test    rsi, rsi
0x1800573b7  jz      short loc_1800573C7
0x1800573b9  mov     eax, [r12]
0x1800573bd  xor     eax, [rsi]
0x1800573bf  jz      short loc_1800573D3
0x1800573c1  lea     r14, [rsi+8]
0x1800573c5  jmp     short loc_1800573B1
0x1800573c7  mov     rbx, [rbx]
0x1800573ca  add     rbx, 468h
0x1800573d1  jmp     short loc_180057396
0x1800573d3  test    cs:byte_1800AA941, 8
0x1800573da  jz      short loc_18005741F
0x1800573dc  xor     eax, eax
0x1800573de  mov     word ptr [rsp+8A0h+var_840], ax
0x1800573e3  mov     r9, [rbx]
0x1800573e6  add     r9, 20h ; ' '
0x1800573ea  mov     r8d, [rsi]
0x1800573ed  lea     rdx, aDeleteListRemo_0; "DELETE List: Remove ConnectionID[0x%X] "...
0x1800573f4  lea     rcx, [rsp+8A0h+var_840]
0x1800573f9  call    FormatRRASErrorString
0x1800573fe  test    cs:byte_1800AA941, 8
0x180057405  jz      short loc_18005741F
0x180057407  lea     r8, [rsp+8A0h+var_840]
0x18005740c  lea     rdx, RasVpnIkeTraceInfo
0x180057413  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005741a  call    McTemplateU0z_EventWriteTransfer
0x18005741f  mov     rax, [r14]
0x180057422  mov     rcx, [rax+8]
0x180057426  mov     [r14], rcx
0x180057429  call    cs:__imp_GetProcessHeap
0x18005742f  mov     rcx, rax; hHeap
0x180057432  mov     r8, rsi; lpMem
0x180057435  xor     edx, edx; dwFlags
0x180057437  call    cs:__imp_HeapFree
0x18005743d  mov     rax, [rbx]
0x180057440  dec     dword ptr [rax+64h]
0x180057443  mov     rsi, [rbx]
0x180057446  cmp     dword ptr [rsi+64h], 0
0x18005744a  jnz     short loc_1800574B8
0x18005744c  test    cs:byte_1800AA941, 8
0x180057453  jz      short loc_180057492
0x180057455  xor     eax, eax
0x180057457  mov     word ptr [rsp+8A0h+var_840], ax
0x18005745c  lea     r8, [rsi+20h]
0x180057460  lea     rdx, aDeleteListRemo; "DELETE List: Remove IP Address [%S]"
0x180057467  lea     rcx, [rsp+8A0h+var_840]
0x18005746c  call    FormatRRASErrorString
0x180057471  test    cs:byte_1800AA941, 8
0x180057478  jz      short loc_180057492
0x18005747a  lea     r8, [rsp+8A0h+var_840]
0x18005747f  lea     rdx, RasVpnIkeTraceInfo
0x180057486  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005748d  call    McTemplateU0z_EventWriteTransfer
0x180057492  mov     rax, [rbx]
0x180057495  mov     rcx, [rax+468h]
0x18005749c  mov     [rbx], rcx
0x18005749f  test    rsi, rsi
0x1800574a2  jz      short loc_1800574B8
0x1800574a4  call    cs:__imp_GetProcessHeap
0x1800574aa  mov     rcx, rax; hHeap
0x1800574ad  mov     r8, rsi; lpMem
0x1800574b0  xor     edx, edx; dwFlags
0x1800574b2  call    cs:__imp_HeapFree
0x1800574b8  lea     rbx, [r15+18h]
0x1800574bc  mov     rax, [rbx]
0x1800574bf  test    rax, rax
0x1800574c2  jz      loc_1800575D9
0x1800574c8  lea     rsi, [rdi+68h]
0x1800574cc  add     rsi, rax
0x1800574cf  mov     rdi, [rsi]
0x1800574d2  test    rdi, rdi
0x1800574d5  jz      short loc_1800574E5
0x1800574d7  mov     eax, [rdi]
0x1800574d9  xor     eax, [r12]
0x1800574dd  jz      short loc_1800574F4
0x1800574df  lea     rsi, [rdi+8]
0x1800574e3  jmp     short loc_1800574CF
0x1800574e5  mov     rbx, [rbx]
0x1800574e8  add     rbx, 468h
0x1800574ef  mov     rdi, r13
0x1800574f2  jmp     short loc_1800574BC
0x1800574f4  test    cs:byte_1800AA941, 8
0x1800574fb  jz      short loc_180057540
0x1800574fd  xor     eax, eax
0x1800574ff  mov     word ptr [rsp+8A0h+var_840], ax
0x180057504  mov     r9, [rbx]
0x180057507  add     r9, 20h ; ' '
0x18005750b  mov     r8d, [rdi]
0x18005750e  lea     rdx, aAddListRemoveC; "ADD List: Remove ConnectionID[0x%X] for"...
0x180057515  lea     rcx, [rsp+8A0h+var_840]
0x18005751a  call    FormatRRASErrorString
0x18005751f  test    cs:byte_1800AA941, 8
0x180057526  jz      short loc_180057540
0x180057528  lea     r8, [rsp+8A0h+var_840]
0x18005752d  lea     rdx, RasVpnIkeTraceInfo
0x180057534  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005753b  call    McTemplateU0z_EventWriteTransfer
0x180057540  mov     rax, [rsi]
0x180057543  mov     rcx, [rax+8]
0x180057547  mov     [rsi], rcx
0x18005754a  call    cs:__imp_GetProcessHeap
0x180057550  mov     rcx, rax; hHeap
0x180057553  mov     r8, rdi; lpMem
0x180057556  xor     edx, edx; dwFlags
0x180057558  call    cs:__imp_HeapFree
0x18005755e  mov     rax, [rbx]
0x180057561  dec     dword ptr [rax+64h]
0x180057564  mov     rdi, [rbx]
0x180057567  cmp     dword ptr [rdi+64h], 0
0x18005756b  jnz     short loc_1800575D9
0x18005756d  test    cs:byte_1800AA941, 8
0x180057574  jz      short loc_1800575B3
0x180057576  xor     eax, eax
0x180057578  mov     word ptr [rsp+8A0h+var_840], ax
0x18005757d  lea     r8, [rdi+20h]
0x180057581  lea     rdx, aAddListRemoveI; "ADD List: Remove IP Address [%S]"
0x180057588  lea     rcx, [rsp+8A0h+var_840]
0x18005758d  call    FormatRRASErrorString
0x180057592  test    cs:byte_1800AA941, 8
0x180057599  jz      short loc_1800575B3
0x18005759b  lea     r8, [rsp+8A0h+var_840]
0x1800575a0  lea     rdx, RasVpnIkeTraceInfo
0x1800575a7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800575ae  call    McTemplateU0z_EventWriteTransfer
0x1800575b3  mov     rax, [rbx]
0x1800575b6  mov     rdx, [rax+468h]
0x1800575bd  mov     [rbx], rdx
0x1800575c0  test    rdi, rdi
0x1800575c3  jz      short loc_1800575D9
0x1800575c5  call    cs:__imp_GetProcessHeap
0x1800575cb  mov     rcx, rax; hHeap
0x1800575ce  mov     r8, rdi; lpMem
0x1800575d1  xor     edx, edx; dwFlags
0x1800575d3  call    cs:__imp_HeapFree
0x1800575d9  lea     rcx, [r15+20h]; lpCriticalSection
0x1800575dd  call    cs:__imp_LeaveCriticalSection
0x1800575e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800575ea  lea     rax, WPP_GLOBAL_Control
0x1800575f1  cmp     rcx, rax
0x1800575f4  jz      short loc_180057618
0x1800575f6  test    byte ptr [rcx+1Ch], 1
0x1800575fa  jz      short loc_180057618
0x1800575fc  cmp     byte ptr [rcx+19h], 6
0x180057600  jb      short loc_180057618
0x180057602  mov     edx, 2Dh ; '-'
0x180057607  lea     r8, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x18005760e  mov     rcx, [rcx+10h]
0x180057612  call    WPP_SF_
0x180057617  nop
0x180057618  lea     rcx, [rsp+8A0h+var_878]; this
0x18005761d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180057622  xor     eax, eax
0x180057624  mov     rcx, [rbp+7A0h+var_40]
0x18005762b  xor     rcx, rsp; StackCookie
0x18005762e  call    __security_check_cookie
0x180057633  mov     rbx, [rsp+8A0h+arg_10]
0x18005763b  add     rsp, 870h
0x180057642  pop     r15
0x180057644  pop     r14
0x180057646  pop     r13
0x180057648  pop     r12
0x18005764a  pop     rdi
0x18005764b  pop     rsi
0x18005764c  pop     rbp
0x18005764d  retn
```
