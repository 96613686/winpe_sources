# SynchronizationEventManager::CreateEventHandle(uint)

- ea: `0x180058f70`
- end: `0x18005927a`
- name: `?CreateEventHandle@SynchronizationEventManager@@UEAAKI@Z`
- size: `778`
- prototype: `__int64 __fastcall(SynchronizationEventManager *this, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001514`
- `0x180001564`
- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x1800587f4`
- `0x180058f70`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005913d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005913d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800591e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800591e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059177`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059177`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005910b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005910b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059119`

## string_xrefs

- `0x180059039`: `SynchronizationEventManager::CreateEventHandle`
- `0x1800590b0`: `SynchronizationEventManager::CreateEventHandle: Found the SyncEventEntry object %d at index %d`

## pseudocode

```c
__int64 __fastcall SynchronizationEventManager::CreateEventHandle(SynchronizationEventManager *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *i; // rbx
  int v5; // r14d
  SynchronizationEventHandle *v6; // rax
  SynchronizationEventHandle *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // esi
  unsigned int v12; // [rsp+20h] [rbp-8A8h] BYREF
  int v13; // [rsp+24h] [rbp-8A4h]
  unsigned int v14; // [rsp+28h] [rbp-8A0h]
  unsigned int v15; // [rsp+30h] [rbp-898h]
  struct _RTL_CRITICAL_SECTION *v16; // [rsp+38h] [rbp-890h]
  __int64 v17; // [rsp+40h] [rbp-888h]
  __int64 v18; // [rsp+48h] [rbp-880h] BYREF
  __int128 v19; // [rsp+50h] [rbp-878h]
  __int128 v20; // [rsp+60h] [rbp-868h]
  __int64 v21; // [rsp+70h] [rbp-858h]
  int v22; // [rsp+78h] [rbp-850h]
  int v23; // [rsp+7Ch] [rbp-84Ch]
  SynchronizationEventHandle *v24; // [rsp+80h] [rbp-848h]
  int v25; // [rsp+90h] [rbp-838h] BYREF
  char v26[2044]; // [rsp+94h] [rbp-834h] BYREF

  v15 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids);
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v12 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"SynchronizationEventManager::CreateEventHandle",
      &v12,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  v14 = (*(__int64 (__fastcall **)(SynchronizationEventManager *, _QWORD))(*(_QWORD *)this + 48LL))(this, a2);
  v17 = 80LL * v14;
  for ( i = *(struct _RTL_CRITICAL_SECTION **)((char *)this + v17 + 16);
        ;
        i = *(struct _RTL_CRITICAL_SECTION **)&i->LockCount )
  {
    v16 = i;
    if ( !i )
      goto LABEL_14;
    if ( a2 == LODWORD(i->SpinCount) )
      break;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(
      &v25,
      L"SynchronizationEventManager::CreateEventHandle: Found the SyncEventEntry object %d at index %d",
      a2);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
      v5 = 0;
LABEL_15:
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)i->DebugInfo + 8LL))(i->DebugInfo);
      goto LABEL_16;
    }
  }
LABEL_14:
  v5 = 0;
  v13 = 0;
  if ( i )
    goto LABEL_15;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  try
  {
    i = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u);
    v16 = i;
    LODWORD(i->SpinCount) = a2;
    i->DebugInfo = 0;
    InitializeCriticalSection(i + 1);
    v5 = 1;
    v13 = 1;
    v6 = (SynchronizationEventHandle *)operator new(0x10u);
    v24 = v6;
    if ( v6 )
      v7 = SynchronizationEventHandle::SynchronizationEventHandle(v6);
    else
      v7 = 0;
    i->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v7;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
    v8 = v17;
    *(_QWORD *)&i->LockCount = *(_QWORD *)((char *)this + v17 + 16);
    *(_QWORD *)((char *)this + v8 + 16) = i;
    i->OwningThread = (HANDLE)*((_QWORD *)this + 311);
    v9 = *((_QWORD *)this + 311);
    if ( v9 )
      *(_QWORD *)(v9 + 24) = i;
    i->LockSemaphore = 0;
    *((_QWORD *)this + 311) = i;
  }
  catch ( ... )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"Memory allocation failure when creating Connection entry with Id %d at index %d",
        v15,
        v14);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
    }
    v12 = 14;
    i = v16;
    v5 = v13;
    goto LABEL_24;
  }
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
LABEL_24:
  v10 = v12;
  if ( v12 && i )
  {
    if ( v5 )
      DeleteCriticalSection(i + 1);
    if ( i->DebugInfo )
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, __int64))(*(_QWORD *)i->DebugInfo + 24LL))(i->DebugInfo, 1);
    operator delete(i);
    v10 = v12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids, v10);
    v10 = v12;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v10;
}

```

## disassembly

```asm
0x180058f70  mov     [rsp+arg_10], rbx
0x180058f75  mov     [rsp+arg_18], rsi
0x180058f7a  push    rdi
0x180058f7b  push    r12
0x180058f7d  push    r13
0x180058f7f  push    r14
0x180058f81  push    r15
0x180058f83  sub     rsp, 8A0h
0x180058f8a  mov     rax, cs:__security_cookie
0x180058f91  xor     rax, rsp
0x180058f94  mov     [rsp+8C8h+var_38], rax
0x180058f9c  mov     r15d, edx
0x180058f9f  mov     rsi, rcx
0x180058fa2  mov     [rsp+8C8h+var_898], edx
0x180058fa6  lea     r13, WPP_GLOBAL_Control
0x180058fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180058fb4  cmp     rcx, r13
0x180058fb7  jz      short loc_180058FDA
0x180058fb9  test    byte ptr [rcx+1Ch], 1
0x180058fbd  jz      short loc_180058FDA
0x180058fbf  cmp     byte ptr [rcx+19h], 6
0x180058fc3  jb      short loc_180058FDA
0x180058fc5  mov     edx, 18h
0x180058fca  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180058fd1  mov     rcx, [rcx+10h]
0x180058fd5  call    WPP_SF_
0x180058fda  xor     edi, edi
0x180058fdc  mov     [rsp+8C8h+var_838], edi
0x180058fe3  xor     edx, edx; Val
0x180058fe5  mov     r8d, 7FCh; Size
0x180058feb  lea     rcx, [rsp+8C8h+var_834]; void *
0x180058ff3  call    memset_0
0x180058ff8  mov     [rsp+8C8h+var_8A8], edi
0x180058ffc  xorps   xmm0, xmm0
0x180058fff  movdqu  [rsp+8C8h+var_878], xmm0
0x180059005  mov     [rsp+8C8h+var_880], rdi
0x18005900a  xorps   xmm1, xmm1
0x18005900d  movdqu  [rsp+8C8h+var_868], xmm1
0x180059013  mov     [rsp+8C8h+var_858], rdi
0x180059018  mov     [rsp+8C8h+var_850], 0FFFFFFFFh
0x180059020  mov     [rsp+8C8h+var_84C], edi
0x180059024  test    cs:byte_1800AA941, 8
0x18005902b  jz      short loc_18005904A
0x18005902d  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180059034  lea     r8, [rsp+8C8h+var_8A8]; unsigned int *
0x180059039  lea     rdx, aSynchronizatio_10; "SynchronizationEventManager::CreateEven"...
0x180059040  lea     rcx, [rsp+8C8h+var_880]; this
0x180059045  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005904a  lea     r12, [rsi+9C0h]
0x180059051  mov     rcx, r12; lpCriticalSection
0x180059054  call    cs:__imp_EnterCriticalSection
0x18005905a  mov     rax, [rsi]
0x18005905d  mov     edx, r15d
0x180059060  mov     rcx, rsi
0x180059063  mov     rax, [rax+30h]
0x180059067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005906c  mov     r9d, eax
0x18005906f  mov     [rsp+8C8h+var_8A0], r9d
0x180059074  lea     rax, [r9+r9*4]
0x180059078  shl     rax, 4
0x18005907c  mov     [rsp+8C8h+var_888], rax
0x180059081  mov     rbx, [rax+rsi+10h]
0x180059086  mov     [rsp+8C8h+var_890], rbx
0x18005908b  test    rbx, rbx
0x18005908e  jz      short loc_1800590ED
0x180059090  cmp     r15d, [rbx+20h]
0x180059094  jz      short loc_18005909C
0x180059096  mov     rbx, [rbx+8]
0x18005909a  jmp     short loc_180059086
0x18005909c  test    cs:byte_1800AA941, 4
0x1800590a3  jz      short loc_1800590ED
0x1800590a5  mov     word ptr [rsp+8C8h+var_838], di
0x1800590ad  mov     r8d, r15d
0x1800590b0  lea     rdx, aSynchronizatio_11; "SynchronizationEventManager::CreateEven"...
0x1800590b7  lea     rcx, [rsp+8C8h+var_838]
0x1800590bf  call    FormatRRASErrorString
0x1800590c4  test    cs:byte_1800AA941, 4
0x1800590cb  jz      short loc_1800590ED
0x1800590cd  lea     r8, [rsp+8C8h+var_838]
0x1800590d5  lea     rdx, RasVpnIkeTraceError
0x1800590dc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800590e3  call    McTemplateU0z_EventWriteTransfer
0x1800590e8  mov     r14d, edi
0x1800590eb  jmp     short loc_1800590F9
0x1800590ed  mov     r14d, edi
0x1800590f0  mov     [rsp+8C8h+var_8A4], edi
0x1800590f4  test    rbx, rbx
0x1800590f7  jz      short loc_180059116
0x1800590f9  mov     rcx, [rbx]
0x1800590fc  mov     rax, [rcx]
0x1800590ff  mov     rax, [rax+8]
0x180059103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059108  mov     rcx, r12; lpCriticalSection
0x18005910b  call    cs:__imp_LeaveCriticalSection
0x180059111  jmp     loc_1800591CC
0x180059116  mov     rcx, r12; lpCriticalSection
0x180059119  call    cs:__imp_LeaveCriticalSection
0x18005911f  nop
0x180059120  mov     ecx, 50h ; 'P'; Size
0x180059125  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005912a  mov     rbx, rax
0x18005912d  mov     [rsp+8C8h+var_890], rax
0x180059132  mov     [rax+20h], r15d
0x180059136  mov     [rax], rdi
0x180059139  lea     rcx, [rax+28h]; lpCriticalSection
0x18005913d  call    cs:__imp_InitializeCriticalSection
0x180059143  mov     r14d, 1
0x180059149  mov     [rsp+8C8h+var_8A4], r14d
0x18005914e  lea     ecx, [r14+0Fh]; Size
0x180059152  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059157  mov     [rsp+8C8h+var_848], rax
0x18005915f  test    rax, rax
0x180059162  jz      short loc_18005916E
0x180059164  mov     rcx, rax; this
0x180059167  call    ??0SynchronizationEventHandle@@QEAA@XZ; SynchronizationEventHandle::SynchronizationEventHandle(void)
0x18005916c  jmp     short loc_180059171
0x18005916e  mov     rax, rdi
0x180059171  mov     [rbx], rax
0x180059174  mov     rcx, r12; lpCriticalSection
0x180059177  call    cs:__imp_EnterCriticalSection
0x18005917d  mov     rcx, [rsp+8C8h+var_888]
0x180059182  mov     rax, [rcx+rsi+10h]
0x180059187  mov     [rbx+8], rax
0x18005918b  mov     [rcx+rsi+10h], rbx
0x180059190  mov     rax, [rsi+9B8h]
0x180059197  mov     [rbx+10h], rax
0x18005919b  mov     rax, [rsi+9B8h]
0x1800591a2  test    rax, rax
0x1800591a5  jz      short loc_1800591AB
0x1800591a7  mov     [rax+18h], rbx
0x1800591ab  mov     [rbx+18h], rdi
0x1800591af  mov     [rsi+9B8h], rbx
0x1800591b6  jmp     loc_180059108
0x1800591bb  lea     r13, WPP_GLOBAL_Control
0x1800591c2  mov     rbx, [rsp+8C8h+var_890]
0x1800591c7  mov     r14d, [rsp+8C8h+var_8A4]
0x1800591cc  mov     esi, [rsp+8C8h+var_8A8]
0x1800591d0  test    esi, esi
0x1800591d2  jz      short loc_18005920D
0x1800591d4  test    rbx, rbx
0x1800591d7  jz      short loc_18005920D
0x1800591d9  test    r14d, r14d
0x1800591dc  jz      short loc_1800591E8
0x1800591de  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800591e2  call    cs:__imp_DeleteCriticalSection
0x1800591e8  mov     rcx, [rbx]
0x1800591eb  test    rcx, rcx
0x1800591ee  jz      short loc_180059201
0x1800591f0  mov     rax, [rcx]
0x1800591f3  mov     edx, 1
0x1800591f8  mov     rax, [rax+18h]
0x1800591fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059201  mov     rcx, rbx; Block
0x180059204  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180059209  mov     esi, [rsp+8C8h+var_8A8]
0x18005920d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059214  cmp     rcx, r13
0x180059217  jz      short loc_180059241
0x180059219  test    byte ptr [rcx+1Ch], 1
0x18005921d  jz      short loc_180059241
0x18005921f  cmp     byte ptr [rcx+19h], 6
0x180059223  jb      short loc_180059241
0x180059225  mov     edx, 19h
0x18005922a  mov     r9d, esi
0x18005922d  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x180059234  mov     rcx, [rcx+10h]
0x180059238  call    WPP_SF_d
0x18005923d  mov     esi, [rsp+8C8h+var_8A8]
0x180059241  lea     rcx, [rsp+8C8h+var_880]; this
0x180059246  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005924b  mov     eax, esi
0x18005924d  mov     rcx, [rsp+8C8h+var_38]
0x180059255  xor     rcx, rsp; StackCookie
0x180059258  call    __security_check_cookie
0x18005925d  lea     r11, [rsp+8C8h+var_28]
0x180059265  mov     rbx, [r11+40h]
0x180059269  mov     rsi, [r11+48h]
0x18005926d  mov     rsp, r11
0x180059270  pop     r15
0x180059272  pop     r14
0x180059274  pop     r13
0x180059276  pop     r12
0x180059278  pop     rdi
0x180059279  retn
```
