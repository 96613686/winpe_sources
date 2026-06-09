# Tcp::FCloseTransport(void)

- ea: `0x10043a650`
- end: `0x10043a8cb`
- name: `?FCloseTransport@Tcp@@MEAA_NXZ`
- size: `635`
- prototype: `bool __fastcall(Tcp *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x100459070`

## callees

- `0x100405270`
- `0x100405390`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10043a650`
- `0x10045d370`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043a760`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10043a760`
- `sqldk!SystemThread_TlsIndex` at `0x10043a720`
- `sqldk!SystemThread_TlsIndex` at `0x10043a779`
- `sqldk!SystemThread_TlsOffset` at `0x10043a729`
- `sqldk!SystemThread_TlsOffset` at `0x10043a782`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a742`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a79d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a742`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a79d`
- `WS2_32!__imp_closesocket` at `0x10043a7ea`
- `WS2_32!__imp_closesocket` at `0x10043a7ea`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a813`
- `WS2_32!__imp_WSAGetLastError` at `0x10043a813`

## string_xrefs

- `0x10043a676`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Tcp::FCloseTransport(Tcp *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  SOCKET v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rdx
  int v11; // ebx
  __int64 Error; // rbx
  unsigned __int8 v13; // bl
  __int64 v15; // [rsp+20h] [rbp-B8h]
  int v16; // [rsp+40h] [rbp-98h] BYREF
  __int64 v17; // [rsp+48h] [rbp-90h]
  int v18; // [rsp+50h] [rbp-88h] BYREF
  int v19; // [rsp+54h] [rbp-84h]
  __int64 v20; // [rsp+58h] [rbp-80h]
  int v21; // [rsp+60h] [rbp-78h] BYREF
  __int64 v22; // [rsp+68h] [rbp-70h]
  __int64 v23; // [rsp+70h] [rbp-68h]
  __int64 v24; // [rsp+78h] [rbp-60h]
  __int64 v25; // [rsp+80h] [rbp-58h]
  bool v26; // [rsp+90h] [rbp-48h]
  __int64 v27; // [rsp+A0h] [rbp-38h]
  const char *v28; // [rsp+A8h] [rbp-30h]
  const char *v29; // [rsp+B0h] [rbp-28h]
  int v30; // [rsp+B8h] [rbp-20h]

  v27 = -2;
  v28 = "sql\\common\\dk\\sni\\src\\tcp.cpp";
  v29 = "Tcp::FCloseTransport";
  v30 = 7668;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::FCloseTransport",
      7668,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
  v5 = _InterlockedExchange64((volatile __int64 *)this + 8, -1);
  if ( v5 == -1 )
    goto LABEL_20;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v16, 1);
  v21 = 536871474;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 600);
  if ( v8 )
    v26 = (unsigned int)SOS_Task::PushWait(v8, &v21) == 0;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v10 = *(_QWORD *)(v9 + 256);
  if ( !v10 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v10 = *(_QWORD *)(v9 + 256);
  }
  v20 = v10;
  v19 = (*(_DWORD *)(v10 + 800) >> 11) & 1;
  if ( v19 || (*(_BYTE *)(v10 + 800) & 4) == 0 )
  {
    v18 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 608) + 8LL))(*(_QWORD *)(v10 + 608));
  }
  else
  {
    v18 = 0;
  }
  v11 = closesocket(v5);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v18);
  *(_DWORD *)(v17 + 616) &= ~v16;
  if ( v11 != -1 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::FCloseTransport", 7704, L"RET|SNI1\n");
LABEL_20:
    v13 = 1;
    goto LABEL_21;
  }
  Error = (unsigned int)WSAGetLastError();
  scierrlog(0x65B3u, Error);
  if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
  {
    LODWORD(v15) = Error;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::FCloseTransport",
      7701,
      L"ERR|SNIwinsock closesocket failed:%d{WINERR}, m_pOvSendNotification for connection %u#, provider %u#, ovl %p{LPWSAOVERLAPPED}\n",
      v15,
      *(_DWORD *)(*((_QWORD *)this + 4) + 76LL),
      *((_DWORD *)this + 11),
      *((_QWORD *)this + 39));
  }
  v13 = 0;
LABEL_21:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::FCloseTransport", 7668, a4);
  return v13;
}

```

## disassembly

```asm
0x10043a650  mov     rax, rsp
0x10043a653  push    rdi
0x10043a654  push    r14
0x10043a656  push    r15
0x10043a658  sub     rsp, 0C0h
0x10043a65f  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x10043a667  mov     [rax+10h], rbx
0x10043a66b  mov     [rax+18h], rbp
0x10043a66f  mov     [rax+20h], rsi
0x10043a673  mov     rdi, rcx
0x10043a676  lea     rbp, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x10043a67d  mov     [rax-30h], rbp
0x10043a681  lea     r14, aTcpFclosetrans; "Tcp::FCloseTransport"
0x10043a688  mov     [rax-28h], r14
0x10043a68c  mov     dword ptr [rax-20h], 1DF4h
0x10043a693  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a69a  jz      short loc_10043A6BB
0x10043a69c  mov     eax, [rcx+2Ch]
0x10043a69f  mov     dword ptr [rsp+0D8h+var_B8], eax
0x10043a6a3  lea     r9, aApiSniU; "API|SNI%u#\n"
0x10043a6aa  mov     r8d, 1DF4h; int
0x10043a6b0  mov     rdx, r14; char *
0x10043a6b3  mov     rcx, rbp; char *
0x10043a6b6  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043a6bb  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x10043a6c2  xchg    rbx, [rdi+40h]
0x10043a6c6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x10043a6ca  jz      loc_10043A88F
0x10043a6d0  mov     edx, 1
0x10043a6d5  lea     rcx, [rsp+0D8h+var_98]
0x10043a6da  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10043a6df  nop
0x10043a6e0  lea     rax, [rsp+0D8h+var_88]
0x10043a6e5  mov     [rsp+0D8h+arg_0], rax
0x10043a6ed  mov     [rsp+0D8h+var_78], 20000232h
0x10043a6f5  xor     r15d, r15d
0x10043a6f8  mov     [rsp+0D8h+var_70], r15
0x10043a6fd  mov     [rsp+0D8h+var_60], r15
0x10043a702  mov     [rsp+0D8h+var_68], r15
0x10043a707  mov     [rsp+0D8h+var_58], r15
0x10043a70f  mov     [rsp+0D8h+var_48], r15b
0x10043a717  mov     rdx, gs:58h
0x10043a720  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a727  mov     ecx, [rax]
0x10043a729  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a730  mov     esi, [rax]
0x10043a732  add     rsi, [rdx+rcx*8]
0x10043a736  mov     rcx, [rsi+100h]
0x10043a73d  test    rcx, rcx
0x10043a740  jnz     short loc_10043A74F
0x10043a742  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a748  mov     rcx, [rsi+100h]
0x10043a74f  mov     rcx, [rcx+258h]
0x10043a756  test    rcx, rcx
0x10043a759  jz      short loc_10043A770
0x10043a75b  lea     rdx, [rsp+0D8h+var_78]
0x10043a760  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10043a766  test    eax, eax
0x10043a768  setz    [rsp+0D8h+var_48]
0x10043a770  mov     rdx, gs:58h
0x10043a779  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a780  mov     ecx, [rax]
0x10043a782  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a789  mov     esi, [rax]
0x10043a78b  add     rsi, [rdx+rcx*8]
0x10043a78f  mov     rdx, [rsi+100h]
0x10043a796  test    rdx, rdx
0x10043a799  jnz     short loc_10043A7AA
0x10043a79b  xor     ecx, ecx
0x10043a79d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a7a3  mov     rdx, [rsi+100h]
0x10043a7aa  mov     [rsp+0D8h+var_80], rdx
0x10043a7af  mov     eax, [rdx+320h]
0x10043a7b5  shr     eax, 0Bh
0x10043a7b8  and     eax, 1
0x10043a7bb  mov     [rsp+0D8h+var_84], eax
0x10043a7bf  jnz     short loc_10043A7D1
0x10043a7c1  test    byte ptr [rdx+320h], 4
0x10043a7c8  jz      short loc_10043A7D1
0x10043a7ca  mov     [rsp+0D8h+var_88], r15d
0x10043a7cf  jmp     short loc_10043A7E7
0x10043a7d1  mov     [rsp+0D8h+var_88], 1
0x10043a7d9  mov     rcx, [rdx+260h]
0x10043a7e0  mov     rax, [rcx]
0x10043a7e3  call    qword ptr [rax+8]
0x10043a7e6  nop
0x10043a7e7  mov     rcx, rbx; s
0x10043a7ea  call    cs:__imp_closesocket
0x10043a7f0  mov     ebx, eax
0x10043a7f2  lea     rcx, [rsp+0D8h+var_88]; this
0x10043a7f7  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10043a7fc  nop
0x10043a7fd  mov     edx, [rsp+0D8h+var_98]
0x10043a801  not     edx
0x10043a803  mov     rcx, [rsp+0D8h+var_90]
0x10043a808  and     [rcx+268h], edx
0x10043a80e  cmp     ebx, 0FFFFFFFFh
0x10043a811  jnz     short loc_10043A86E
0x10043a813  call    cs:__imp_WSAGetLastError
0x10043a819  mov     ebx, eax
0x10043a81b  mov     edx, eax
0x10043a81d  mov     ecx, 65B3h; unsigned int
0x10043a822  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043a827  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a82e  jz      short loc_10043A86A
0x10043a830  mov     rdx, [rdi+20h]
0x10043a834  mov     rcx, [rdi+138h]
0x10043a83b  mov     [rsp+0D8h+var_A0], rcx
0x10043a840  mov     ecx, [rdi+2Ch]
0x10043a843  mov     [rsp+0D8h+var_A8], ecx
0x10043a847  mov     ecx, [rdx+4Ch]
0x10043a84a  mov     [rsp+0D8h+var_B0], ecx
0x10043a84e  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x10043a852  lea     r9, aErrSniwinsockC; "ERR|SNIwinsock closesocket failed:%d{WI"...
0x10043a859  mov     r8d, 1E15h; int
0x10043a85f  mov     rdx, r14; char *
0x10043a862  mov     rcx, rbp; char *
0x10043a865  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043a86a  xor     bl, bl
0x10043a86c  jmp     short loc_10043A891
0x10043a86e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a875  jz      short loc_10043A88F
0x10043a877  lea     r9, aRetSni1; "RET|SNI1\n"
0x10043a87e  mov     r8d, 1E18h; int
0x10043a884  mov     rdx, r14; char *
0x10043a887  mov     rcx, rbp; char *
0x10043a88a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043a88f  mov     bl, 1
0x10043a891  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043a898  jz      short loc_10043A8AB
0x10043a89a  mov     r8d, 1DF4h; int
0x10043a8a0  mov     rdx, r14; char *
0x10043a8a3  mov     rcx, rbp; char *
0x10043a8a6  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043a8ab  movzx   eax, bl
0x10043a8ae  lea     r11, [rsp+0D8h+var_18]
0x10043a8b6  mov     rbx, [r11+28h]
0x10043a8ba  mov     rbp, [r11+30h]
0x10043a8be  mov     rsi, [r11+38h]
0x10043a8c2  mov     rsp, r11
0x10043a8c5  pop     r15
0x10043a8c7  pop     r14
0x10043a8c9  pop     rdi
0x10043a8ca  retn
```
