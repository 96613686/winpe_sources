# SynchronizationEventManager::Cleanup(void)

- ea: `0x180058d30`
- end: `0x180058f64`
- name: `?Cleanup@SynchronizationEventManager@@MEAAKXZ`
- size: `564`
- prototype: `__int64 __fastcall(SynchronizationEventManager *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180058bb0`

## callees

- `0x180001564`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180058d30`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058ecd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058ecd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058e1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058e98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058e1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058e98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058eba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058ef1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058eba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058ef1`

## pseudocode

```c
__int64 __fastcall SynchronizationEventManager::Cleanup(SynchronizationEventManager *this)
{
  struct _RTL_CRITICAL_SECTION *i; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  struct _RTL_CRITICAL_SECTION *OwningThread; // rbx
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v9; // [rsp+30h] [rbp-D0h]
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v7 = 0;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  v13 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"SynchronizationEventManager::Cleanup",
      &v7,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  for ( i = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 311); i; i = OwningThread )
  {
    if ( i->DebugInfo )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v14) = 0;
        FormatRRASErrorString(
          &v14,
          L"SynchronizationEventManager::Cleanup: Signaling the event for connectionId %d",
          LODWORD(i->SpinCount));
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v14);
      }
      (**(void (__fastcall ***)(PRTL_CRITICAL_SECTION_DEBUG))i->DebugInfo)(i->DebugInfo);
      v3 = i + 1;
      EnterCriticalSection(i + 1);
      if ( i->DebugInfo )
        (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, __int64))(*(_QWORD *)i->DebugInfo + 24LL))(i->DebugInfo, 1);
      LeaveCriticalSection(i + 1);
    }
    else
    {
      v3 = i + 1;
    }
    OwningThread = (struct _RTL_CRITICAL_SECTION *)i->OwningThread;
    DeleteCriticalSection(v3);
    operator delete(i);
  }
  *((_QWORD *)this + 311) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids, v7);
  }
  v5 = v7;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return v5;
}

```

## disassembly

```asm
0x180058d30  mov     [rsp-8+arg_8], rbx
0x180058d35  mov     [rsp-8+arg_10], rsi
0x180058d3a  push    rbp
0x180058d3b  push    rdi
0x180058d3c  push    r13
0x180058d3e  push    r14
0x180058d40  push    r15
0x180058d42  lea     rbp, [rsp-770h]
0x180058d4a  sub     rsp, 870h
0x180058d51  mov     rax, cs:__security_cookie
0x180058d58  xor     rax, rsp
0x180058d5b  mov     [rbp+790h+var_30], rax
0x180058d62  mov     r14, rcx
0x180058d65  lea     r13, WPP_GLOBAL_Control
0x180058d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058d73  cmp     rcx, r13
0x180058d76  jz      short loc_180058D99
0x180058d78  test    byte ptr [rcx+1Ch], 1
0x180058d7c  jz      short loc_180058D99
0x180058d7e  cmp     byte ptr [rcx+19h], 6
0x180058d82  jb      short loc_180058D99
0x180058d84  mov     edx, 23h ; '#'
0x180058d89  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058d90  mov     rcx, [rcx+10h]
0x180058d94  call    WPP_SF_
0x180058d99  xor     eax, eax
0x180058d9b  mov     [rsp+890h+var_830], eax
0x180058d9f  xor     edx, edx; Val
0x180058da1  mov     r8d, 7FCh; Size
0x180058da7  lea     rcx, [rsp+890h+var_82C]; void *
0x180058dac  call    memset_0
0x180058db1  mov     [rsp+890h+var_870], 0
0x180058db9  xorps   xmm0, xmm0
0x180058dbc  movdqu  [rsp+890h+var_860], xmm0
0x180058dc2  mov     [rsp+890h+var_868], 0
0x180058dcb  xorps   xmm1, xmm1
0x180058dce  movdqu  [rsp+890h+var_850], xmm1
0x180058dd4  mov     [rsp+890h+var_840], 0
0x180058ddd  mov     [rsp+890h+var_838], 0FFFFFFFFh
0x180058de5  mov     [rsp+890h+var_834], 0
0x180058ded  test    cs:byte_1800AA941, 8
0x180058df4  jz      short loc_180058E13
0x180058df6  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180058dfd  lea     r8, [rsp+890h+var_870]; unsigned int *
0x180058e02  lea     rdx, aSynchronizatio_3; "SynchronizationEventManager::Cleanup"
0x180058e09  lea     rcx, [rsp+890h+var_868]; this
0x180058e0e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180058e13  lea     r15, [r14+9C0h]
0x180058e1a  mov     rcx, r15; lpCriticalSection
0x180058e1d  call    cs:__imp_EnterCriticalSection
0x180058e23  mov     rdi, [r14+9B8h]
0x180058e2a  test    rdi, rdi
0x180058e2d  jz      loc_180058EE3
0x180058e33  cmp     qword ptr [rdi], 0
0x180058e37  jz      loc_180058EC2
0x180058e3d  test    cs:byte_1800AA941, 8
0x180058e44  jz      short loc_180058E83
0x180058e46  xor     eax, eax
0x180058e48  mov     word ptr [rsp+890h+var_830], ax
0x180058e4d  mov     r8d, [rdi+20h]
0x180058e51  lea     rdx, aSynchronizatio_5; "SynchronizationEventManager::Cleanup: S"...
0x180058e58  lea     rcx, [rsp+890h+var_830]
0x180058e5d  call    FormatRRASErrorString
0x180058e62  test    cs:byte_1800AA941, 8
0x180058e69  jz      short loc_180058E83
0x180058e6b  lea     r8, [rsp+890h+var_830]
0x180058e70  lea     rdx, RasVpnIkeTraceInfo
0x180058e77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180058e7e  call    McTemplateU0z_EventWriteTransfer
0x180058e83  mov     rcx, [rdi]
0x180058e86  mov     rax, [rcx]
0x180058e89  mov     rax, [rax]
0x180058e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e91  lea     rsi, [rdi+28h]
0x180058e95  mov     rcx, rsi; lpCriticalSection
0x180058e98  call    cs:__imp_EnterCriticalSection
0x180058e9e  mov     rcx, [rdi]
0x180058ea1  test    rcx, rcx
0x180058ea4  jz      short loc_180058EB7
0x180058ea6  mov     rax, [rcx]
0x180058ea9  mov     edx, 1
0x180058eae  mov     rax, [rax+18h]
0x180058eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eb7  mov     rcx, rsi; lpCriticalSection
0x180058eba  call    cs:__imp_LeaveCriticalSection
0x180058ec0  jmp     short loc_180058EC6
0x180058ec2  lea     rsi, [rdi+28h]
0x180058ec6  mov     rbx, [rdi+10h]
0x180058eca  mov     rcx, rsi; lpCriticalSection
0x180058ecd  call    cs:__imp_DeleteCriticalSection
0x180058ed3  mov     rcx, rdi; Block
0x180058ed6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180058edb  mov     rdi, rbx
0x180058ede  jmp     loc_180058E2A
0x180058ee3  mov     qword ptr [r14+9B8h], 0
0x180058eee  mov     rcx, r15; lpCriticalSection
0x180058ef1  call    cs:__imp_LeaveCriticalSection
0x180058ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180058efe  cmp     rcx, r13
0x180058f01  jz      short loc_180058F29
0x180058f03  test    byte ptr [rcx+1Ch], 1
0x180058f07  jz      short loc_180058F29
0x180058f09  cmp     byte ptr [rcx+19h], 6
0x180058f0d  jb      short loc_180058F29
0x180058f0f  mov     edx, 24h ; '$'
0x180058f14  mov     r9d, [rsp+890h+var_870]
0x180058f19  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058f20  mov     rcx, [rcx+10h]
0x180058f24  call    WPP_SF_d
0x180058f29  mov     ebx, [rsp+890h+var_870]
0x180058f2d  lea     rcx, [rsp+890h+var_868]; this
0x180058f32  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180058f37  mov     eax, ebx
0x180058f39  mov     rcx, [rbp+790h+var_30]
0x180058f40  xor     rcx, rsp; StackCookie
0x180058f43  call    __security_check_cookie
0x180058f48  lea     r11, [rsp+890h+var_20]
0x180058f50  mov     rbx, [r11+38h]
0x180058f54  mov     rsi, [r11+40h]
0x180058f58  mov     rsp, r11
0x180058f5b  pop     r15
0x180058f5d  pop     r14
0x180058f5f  pop     r13
0x180058f61  pop     rdi
0x180058f62  pop     rbp
0x180058f63  retn
```
