# SynchronizationEventManager::DeleteEventHandle(uint)

- ea: `0x180059280`
- end: `0x180059516`
- name: `?DeleteEventHandle@SynchronizationEventManager@@UEAAKI@Z`
- size: `662`
- prototype: `__int64 __fastcall(SynchronizationEventManager *this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001564`
- `0x180007590`
- `0x1800077bc`
- `0x180059280`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059495`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180059495`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005932d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800593b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005932d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800593b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059487`

## string_xrefs

- `0x180059312`: `SynchronizationEventManager::DeleteEventHandle`

## pseudocode

```c
__int64 __fastcall SynchronizationEventManager::DeleteEventHandle(SynchronizationEventManager *this, unsigned int a2)
{
  int v4; // r15d
  __int64 v5; // r9
  __int64 v6; // r12
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  __int64 v9; // rdi
  __int64 v10; // rax
  _QWORD *LockSemaphore; // rcx
  _QWORD *OwningThread; // rcx
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+5Ch] [rbp-A4h]
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  char v23[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v4 = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"SynchronizationEventManager::DeleteEventHandle",
      &v15,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  v5 = (*(unsigned int (__fastcall **)(SynchronizationEventManager *, _QWORD))(*(_QWORD *)this + 48LL))(this, a2);
  v6 = 10 * v5;
  v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 10 * v5 + 2);
  v8 = 0;
  while ( v7 )
  {
    if ( a2 == LODWORD(v7->SpinCount) )
    {
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v22) = 0;
        FormatRRASErrorString(&v22, L"Found the SyncEventEntry object %d at index %d", a2);
        if ( (byte_1800AA941 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceInfo, &v22);
      }
      v9 = (__int64)&v7[1];
      EnterCriticalSection(v7 + 1);
      v4 = 1;
      if ( v7->DebugInfo )
        (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)v7->DebugInfo + 24LL))(v7->DebugInfo);
      v10 = *(_QWORD *)&v7->LockCount;
      if ( v8 )
        *(_QWORD *)&v8->LockCount = v10;
      else
        *((_QWORD *)this + v6 + 2) = v10;
      LockSemaphore = v7->LockSemaphore;
      if ( LockSemaphore )
        LockSemaphore[2] = v7->OwningThread;
      OwningThread = v7->OwningThread;
      if ( OwningThread )
        OwningThread[3] = v7->LockSemaphore;
      if ( *((struct _RTL_CRITICAL_SECTION **)this + 311) == v7 )
        *((_QWORD *)this + 311) = v7->OwningThread;
      goto LABEL_25;
    }
    v8 = v7;
    v7 = *(struct _RTL_CRITICAL_SECTION **)&v7->LockCount;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v22, L"SyncEventEntry object with %d could NOT be found", a2);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v22);
  }
  v15 = 1168;
  v9 = 40;
LABEL_25:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2496));
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v9);
  if ( v7 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v9);
    operator delete(v7);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids, v15);
  }
  v13 = v15;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v13;
}

```

## disassembly

```asm
0x180059280  mov     [rsp-8+arg_10], rbx
0x180059285  push    rbp
0x180059286  push    rsi
0x180059287  push    rdi
0x180059288  push    r12
0x18005928a  push    r13
0x18005928c  push    r14
0x18005928e  push    r15
0x180059290  lea     rbp, [rsp-770h]
0x180059298  sub     rsp, 870h
0x18005929f  mov     rax, cs:__security_cookie
0x1800592a6  xor     rax, rsp
0x1800592a9  mov     [rbp+7A0h+var_40], rax
0x1800592b0  mov     edi, edx
0x1800592b2  mov     rsi, rcx
0x1800592b5  xor     r15d, r15d
0x1800592b8  mov     [rsp+8A0h+var_840], r15d
0x1800592bd  xor     edx, edx; Val
0x1800592bf  mov     r8d, 7FCh; Size
0x1800592c5  lea     rcx, [rsp+8A0h+var_83C]; void *
0x1800592ca  call    memset_0
0x1800592cf  mov     [rsp+8A0h+var_880], r15d
0x1800592d4  xorps   xmm0, xmm0
0x1800592d7  movdqu  [rsp+8A0h+var_870], xmm0
0x1800592dd  mov     [rsp+8A0h+var_878], r15
0x1800592e2  xorps   xmm1, xmm1
0x1800592e5  movdqu  [rsp+8A0h+var_860], xmm1
0x1800592eb  mov     [rsp+8A0h+var_850], r15
0x1800592f0  mov     [rsp+8A0h+var_848], 0FFFFFFFFh
0x1800592f8  mov     [rsp+8A0h+var_844], r15d
0x1800592fd  test    cs:byte_1800AA941, 8
0x180059304  jz      short loc_180059323
0x180059306  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005930d  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x180059312  lea     rdx, aSynchronizatio_12; "SynchronizationEventManager::DeleteEven"...
0x180059319  lea     rcx, [rsp+8A0h+var_878]; this
0x18005931e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180059323  lea     r13, [rsi+9C0h]
0x18005932a  mov     rcx, r13; lpCriticalSection
0x18005932d  call    cs:__imp_EnterCriticalSection
0x180059333  mov     rax, [rsi]
0x180059336  mov     edx, edi
0x180059338  mov     rcx, rsi
0x18005933b  mov     rax, [rax+30h]
0x18005933f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059344  mov     r9d, eax
0x180059347  lea     r12, [r9+r9*4]
0x18005934b  add     r12, r12
0x18005934e  mov     rbx, [rsi+r12*8+10h]
0x180059353  mov     r14, r15
0x180059356  test    rbx, rbx
0x180059359  jz      loc_180059426
0x18005935f  cmp     edi, [rbx+20h]
0x180059362  jz      short loc_18005936D
0x180059364  mov     r14, rbx
0x180059367  mov     rbx, [rbx+8]
0x18005936b  jmp     short loc_180059356
0x18005936d  test    cs:byte_1800AA941, 8
0x180059374  jz      short loc_1800593B1
0x180059376  mov     word ptr [rsp+8A0h+var_840], r15w
0x18005937c  mov     r8d, edi
0x18005937f  lea     rdx, aFoundTheSyncev; "Found the SyncEventEntry object %d at i"...
0x180059386  lea     rcx, [rsp+8A0h+var_840]
0x18005938b  call    FormatRRASErrorString
0x180059390  test    cs:byte_1800AA941, 8
0x180059397  jz      short loc_1800593B1
0x180059399  lea     r8, [rsp+8A0h+var_840]
0x18005939e  lea     rdx, RasVpnIkeTraceInfo
0x1800593a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800593ac  call    McTemplateU0z_EventWriteTransfer
0x1800593b1  lea     rdi, [rbx+28h]
0x1800593b5  mov     rcx, rdi; lpCriticalSection
0x1800593b8  call    cs:__imp_EnterCriticalSection
0x1800593be  mov     edx, 1
0x1800593c3  mov     r15d, edx
0x1800593c6  mov     rcx, [rbx]
0x1800593c9  test    rcx, rcx
0x1800593cc  jz      short loc_1800593DA
0x1800593ce  mov     rax, [rcx]
0x1800593d1  mov     rax, [rax+18h]
0x1800593d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593da  mov     rax, [rbx+8]
0x1800593de  test    r14, r14
0x1800593e1  jz      short loc_1800593E9
0x1800593e3  mov     [r14+8], rax
0x1800593e7  jmp     short loc_1800593EE
0x1800593e9  mov     [rsi+r12*8+10h], rax
0x1800593ee  mov     rcx, [rbx+18h]
0x1800593f2  test    rcx, rcx
0x1800593f5  jz      short loc_1800593FF
0x1800593f7  mov     rax, [rbx+10h]
0x1800593fb  mov     [rcx+10h], rax
0x1800593ff  mov     rcx, [rbx+10h]
0x180059403  test    rcx, rcx
0x180059406  jz      short loc_180059410
0x180059408  mov     rax, [rbx+18h]
0x18005940c  mov     [rcx+18h], rax
0x180059410  cmp     [rsi+9B8h], rbx
0x180059417  jnz     short loc_180059476
0x180059419  mov     rax, [rbx+10h]
0x18005941d  mov     [rsi+9B8h], rax
0x180059424  jmp     short loc_180059476
0x180059426  test    cs:byte_1800AA941, 4
0x18005942d  jz      short loc_18005946A
0x18005942f  mov     word ptr [rsp+8A0h+var_840], r15w
0x180059435  mov     r8d, edi
0x180059438  lea     rdx, aSyncevententry; "SyncEventEntry object with %d could NOT"...
0x18005943f  lea     rcx, [rsp+8A0h+var_840]
0x180059444  call    FormatRRASErrorString
0x180059449  test    cs:byte_1800AA941, 4
0x180059450  jz      short loc_18005946A
0x180059452  lea     r8, [rsp+8A0h+var_840]
0x180059457  lea     rdx, RasVpnIkeTraceError
0x18005945e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180059465  call    McTemplateU0z_EventWriteTransfer
0x18005946a  mov     [rsp+8A0h+var_880], 490h
0x180059472  lea     rdi, [rbx+28h]
0x180059476  mov     rcx, r13; lpCriticalSection
0x180059479  call    cs:__imp_LeaveCriticalSection
0x18005947f  test    r15d, r15d
0x180059482  jz      short loc_18005948D
0x180059484  mov     rcx, rdi; lpCriticalSection
0x180059487  call    cs:__imp_LeaveCriticalSection
0x18005948d  test    rbx, rbx
0x180059490  jz      short loc_1800594A3
0x180059492  mov     rcx, rdi; lpCriticalSection
0x180059495  call    cs:__imp_DeleteCriticalSection
0x18005949b  mov     rcx, rbx; Block
0x18005949e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800594a3  lea     rax, WPP_GLOBAL_Control
0x1800594aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800594b1  cmp     rcx, rax
0x1800594b4  jz      short loc_1800594DC
0x1800594b6  test    byte ptr [rcx+1Ch], 1
0x1800594ba  jz      short loc_1800594DC
0x1800594bc  cmp     byte ptr [rcx+19h], 6
0x1800594c0  jb      short loc_1800594DC
0x1800594c2  mov     edx, 1Eh
0x1800594c7  mov     r9d, [rsp+8A0h+var_880]
0x1800594cc  lea     r8, WPP_7e40c4649329339b12845c07cbf8f42f_Traceguids
0x1800594d3  mov     rcx, [rcx+10h]
0x1800594d7  call    WPP_SF_d
0x1800594dc  mov     ebx, [rsp+8A0h+var_880]
0x1800594e0  lea     rcx, [rsp+8A0h+var_878]; this
0x1800594e5  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800594ea  mov     eax, ebx
0x1800594ec  mov     rcx, [rbp+7A0h+var_40]
0x1800594f3  xor     rcx, rsp; StackCookie
0x1800594f6  call    __security_check_cookie
0x1800594fb  mov     rbx, [rsp+8A0h+arg_10]
0x180059503  add     rsp, 870h
0x18005950a  pop     r15
0x18005950c  pop     r14
0x18005950e  pop     r13
0x180059510  pop     r12
0x180059512  pop     rdi
0x180059513  pop     rsi
0x180059514  pop     rbp
0x180059515  retn
```
