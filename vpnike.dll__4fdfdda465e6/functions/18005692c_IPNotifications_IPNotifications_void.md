# IPNotifications::IPNotifications(void)

- ea: `0x18005692c`
- end: `0x180056b90`
- name: `??0IPNotifications@@IEAA@XZ`
- size: `612`
- prototype: `IPNotifications *__fastcall(IPNotifications *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180057744`

## callees

- `0x180001f78`
- `0x180007794`
- `0x1800077bc`
- `0x18005692c`
- `0x1800570e0`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180056ab3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180056ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ac6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056a14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056a66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056a14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056a66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IPNotifications *__fastcall IPNotifications::IPNotifications(IPNotifications *this)
{
  DWORD LastError; // eax
  ulong v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  PTP_WORK ThreadpoolWork; // rax
  __int64 v8; // [rsp+20h] [rbp-68h] BYREF
  __int128 v9; // [rsp+28h] [rbp-60h]
  __int128 v10; // [rsp+38h] [rbp-50h]
  __int64 v11; // [rsp+48h] [rbp-40h]
  int v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+54h] [rbp-34h]
  ulong pExceptionObject; // [rsp+90h] [rbp+8h] BYREF

  *(_QWORD *)this = &IPNotifications::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"IPNotifications::IPNotifications",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_BYTE *)this + 128) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 18) = (char *)this + 136;
  *((_QWORD *)this + 17) = (char *)this + 136;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 32), 0xFA0u) )
  {
    *((_BYTE *)this + 72) = 1;
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 88), 0xFA0u) )
    {
      *((_BYTE *)this + 128) = 1;
      ThreadpoolWork = CreateThreadpoolWork(IPNotifications::s_ProcessNsiCallback, this, 0);
      *((_QWORD *)this + 10) = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v5 = 13;
            goto LABEL_25;
          }
          goto LABEL_26;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 12;
          goto LABEL_25;
        }
LABEL_26:
        IPNotifications::Cleanup(this);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, v3);
        }
        pExceptionObject = v3;
        throw &pExceptionObject;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 11;
LABEL_25:
        WPP_SF_d(v4[2], v5, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids, LastError);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return this;
}

```

## disassembly

```asm
0x18005692c  push    rbx
0x18005692e  push    rdi
0x18005692f  push    r14
0x180056931  push    r15
0x180056933  sub     rsp, 68h
0x180056937  mov     rdi, rcx
0x18005693a  lea     rax, ??_7IPNotifications@@6B@; const IPNotifications::`vftable'
0x180056941  mov     [rcx], rax
0x180056944  lea     r14, WPP_GLOBAL_Control
0x18005694b  lea     r15, WPP_d23f83cd04063ba912a1d720026fb887_Traceguids
0x180056952  mov     rcx, cs:WPP_GLOBAL_Control
0x180056959  cmp     rcx, r14
0x18005695c  jz      short loc_18005697B
0x18005695e  test    byte ptr [rcx+1Ch], 1
0x180056962  jz      short loc_18005697B
0x180056964  cmp     byte ptr [rcx+19h], 6
0x180056968  jb      short loc_18005697B
0x18005696a  mov     edx, 0Ah
0x18005696f  mov     r8, r15
0x180056972  mov     rcx, [rcx+10h]
0x180056976  call    WPP_SF_
0x18005697b  xorps   xmm0, xmm0
0x18005697e  movdqu  [rsp+88h+var_60], xmm0
0x180056984  mov     [rsp+88h+var_68], 0
0x18005698d  movdqu  [rsp+88h+var_50], xmm0
0x180056993  mov     [rsp+88h+var_40], 0
0x18005699c  mov     [rsp+88h+var_38], 0FFFFFFFFh
0x1800569a4  mov     [rsp+88h+var_34], 0
0x1800569ac  test    cs:byte_1800AA941, 8
0x1800569b3  jz      short loc_1800569D0
0x1800569b5  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800569bc  xor     r8d, r8d; unsigned int *
0x1800569bf  lea     rdx, aIpnotification_2; "IPNotifications::IPNotifications"
0x1800569c6  lea     rcx, [rsp+88h+var_68]; this
0x1800569cb  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800569d0  mov     qword ptr [rdi+8], 0
0x1800569d8  mov     qword ptr [rdi+10h], 0
0x1800569e0  mov     qword ptr [rdi+18h], 0
0x1800569e8  mov     byte ptr [rdi+48h], 0
0x1800569ec  mov     byte ptr [rdi+80h], 0
0x1800569f3  mov     qword ptr [rdi+50h], 0
0x1800569fb  lea     rax, [rdi+88h]
0x180056a02  mov     [rax+8], rax
0x180056a06  mov     [rax], rax
0x180056a09  lea     rcx, [rdi+20h]; lpCriticalSection
0x180056a0d  mov     ebx, 0FA0h
0x180056a12  mov     edx, ebx; dwSpinCount
0x180056a14  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180056a1a  test    eax, eax
0x180056a1c  jnz     short loc_180056A5C
0x180056a1e  call    cs:__imp_GetLastError
0x180056a24  mov     ebx, eax
0x180056a26  test    eax, eax
0x180056a28  jz      loc_180056B4E
0x180056a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a35  cmp     rcx, r14
0x180056a38  jz      loc_180056AFE
0x180056a3e  test    byte ptr [rcx+1Ch], 1
0x180056a42  jz      loc_180056AFE
0x180056a48  cmp     byte ptr [rcx+19h], 2
0x180056a4c  jb      loc_180056AFE
0x180056a52  mov     edx, 0Bh
0x180056a57  jmp     loc_180056AEF
0x180056a5c  mov     byte ptr [rdi+48h], 1
0x180056a60  lea     rcx, [rdi+58h]; lpCriticalSection
0x180056a64  mov     edx, ebx; dwSpinCount
0x180056a66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180056a6c  test    eax, eax
0x180056a6e  jnz     short loc_180056A9F
0x180056a70  call    cs:__imp_GetLastError
0x180056a76  mov     ebx, eax
0x180056a78  test    eax, eax
0x180056a7a  jz      loc_180056B4E
0x180056a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180056a87  cmp     rcx, r14
0x180056a8a  jz      short loc_180056AFE
0x180056a8c  test    byte ptr [rcx+1Ch], 1
0x180056a90  jz      short loc_180056AFE
0x180056a92  cmp     byte ptr [rcx+19h], 2
0x180056a96  jb      short loc_180056AFE
0x180056a98  mov     edx, 0Ch
0x180056a9d  jmp     short loc_180056AEF
0x180056a9f  mov     byte ptr [rdi+80h], 1
0x180056aa6  xor     r8d, r8d; pcbe
0x180056aa9  mov     rdx, rdi; pv
0x180056aac  lea     rcx, ?s_ProcessNsiCallback@IPNotifications@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180056ab3  call    cs:__imp_CreateThreadpoolWork
0x180056ab9  mov     [rdi+50h], rax
0x180056abd  test    rax, rax
0x180056ac0  jnz     loc_180056B4E
0x180056ac6  call    cs:__imp_GetLastError
0x180056acc  mov     ebx, eax
0x180056ace  test    eax, eax
0x180056ad0  jz      short loc_180056B4E
0x180056ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ad9  cmp     rcx, r14
0x180056adc  jz      short loc_180056AFE
0x180056ade  test    byte ptr [rcx+1Ch], 1
0x180056ae2  jz      short loc_180056AFE
0x180056ae4  cmp     byte ptr [rcx+19h], 2
0x180056ae8  jb      short loc_180056AFE
0x180056aea  mov     edx, 0Dh
0x180056aef  mov     r9d, eax
0x180056af2  mov     r8, r15
0x180056af5  mov     rcx, [rcx+10h]
0x180056af9  call    WPP_SF_d
0x180056afe  mov     rcx, rdi; this
0x180056b01  call    ?Cleanup@IPNotifications@@MEAAXXZ; IPNotifications::Cleanup(void)
0x180056b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b0d  cmp     rcx, r14
0x180056b10  jz      short loc_180056B32
0x180056b12  test    byte ptr [rcx+1Ch], 1
0x180056b16  jz      short loc_180056B32
0x180056b18  cmp     byte ptr [rcx+19h], 6
0x180056b1c  jb      short loc_180056B32
0x180056b1e  mov     edx, 0Eh
0x180056b23  mov     r9d, ebx
0x180056b26  mov     r8, r15
0x180056b29  mov     rcx, [rcx+10h]
0x180056b2d  call    WPP_SF_d
0x180056b32  mov     [rsp+88h+pExceptionObject], ebx
0x180056b39  lea     rdx, _TI1K; pThrowInfo
0x180056b40  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180056b48  call    _CxxThrowException_0
0x180056b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056b55  cmp     rcx, r14
0x180056b58  jz      short loc_180056B78
0x180056b5a  test    byte ptr [rcx+1Ch], 1
0x180056b5e  jz      short loc_180056B78
0x180056b60  cmp     byte ptr [rcx+19h], 6
0x180056b64  jb      short loc_180056B78
0x180056b66  mov     edx, 0Fh
0x180056b6b  mov     r8, r15
0x180056b6e  mov     rcx, [rcx+10h]
0x180056b72  call    WPP_SF_
0x180056b77  nop
0x180056b78  lea     rcx, [rsp+88h+var_68]; this
0x180056b7d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056b82  mov     rax, rdi
0x180056b85  add     rsp, 68h
0x180056b89  pop     r15
0x180056b8b  pop     r14
0x180056b8d  pop     rdi
0x180056b8e  pop     rbx
0x180056b8f  retn
```
