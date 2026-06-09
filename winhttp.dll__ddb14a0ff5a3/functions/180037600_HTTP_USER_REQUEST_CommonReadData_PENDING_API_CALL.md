# HTTP_USER_REQUEST::_CommonReadData(PENDING_API_CALL *)

- ea: `0x180037600`
- end: `0x180037b10`
- name: `?_CommonReadData@HTTP_USER_REQUEST@@AEAAKPEAVPENDING_API_CALL@@@Z`
- size: `1296`
- prototype: `unsigned int __fastcall(struct _RTL_CRITICAL_SECTION *this, struct PENDING_API_CALL *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003dd30`

## callees

- `0x180010f50`
- `0x1800250ec`
- `0x18002e6e8`
- `0x180035c4c`
- `0x180037600`
- `0x180037d40`
- `0x180039120`
- `0x18008f484`
- `0x1800a1d10`
- `0x1800d5a68`
- `0x1800db704`
- `0x1800dba18`
- `0x1800dd554`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037999`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800376b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800378af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800376dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800378c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800376dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800378c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800379ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037a11`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037915`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037915`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037927`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800378e1`
- `ntdll!EtwEventActivityIdControl` at `0x180037778`
- `ntdll!EtwEventActivityIdControl` at `0x1800377d9`
- `ntdll!EtwEventActivityIdControl` at `0x180037778`
- `ntdll!EtwEventActivityIdControl` at `0x1800377d9`

## pseudocode

```c
unsigned int __fastcall HTTP_USER_REQUEST::_CommonReadData(
        struct _RTL_CRITICAL_SECTION *this,
        struct PENDING_API_CALL *a2)
{
  ULONG_PTR SpinCount; // rax
  HANDLE_OBJECT *v5; // rbx
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  __int64 v9; // rbp
  __int64 v10; // r14
  unsigned int v11; // r12d
  void (__fastcall ***v12)(ULONG_PTR); // rbx
  bool v13; // zf
  __int64 v14; // rcx
  struct _GUID *v15; // rax
  __int64 v16; // rdx
  struct _GUID *v17; // rax
  int v18; // eax
  bool v19; // sf
  __int64 v20; // rdx
  ULONG_PTR v21; // rcx
  void (__fastcall *v22)(ULONG_PTR, __int64, __int64, _QWORD, _DWORD); // rax
  int v23; // eax
  bool v24; // sf
  unsigned int result; // eax
  unsigned int v26; // ebx
  int v27; // esi
  int v28; // ebx
  int v29; // ebx
  void *v30; // rcx
  unsigned int Data; // eax
  int v32; // eax
  int v33; // edx
  int v34; // r8d
  __int64 v35; // rax
  int v36; // r8d
  unsigned int v37[3]; // [rsp+50h] [rbp-88h] BYREF
  int v38; // [rsp+5Ch] [rbp-7Ch]
  struct _GUID v39; // [rsp+60h] [rbp-78h] BYREF
  int v40; // [rsp+70h] [rbp-68h]
  struct _GUID v41; // [rsp+78h] [rbp-60h] BYREF
  __int128 v42; // [rsp+88h] [rbp-50h]

  SpinCount = this->SpinCount;
  v37[0] = 0;
  v5 = *(HANDLE_OBJECT **)(SpinCount + 24);
  if ( (*(unsigned int (__fastcall **)(HANDLE_OBJECT *))(*(_QWORD *)v5 + 8LL))(v5) != 1952804425 )
    v5 = (HANDLE_OBJECT *)*((_QWORD *)v5 + 3);
  if ( (unsigned int)HANDLE_OBJECT::IsInvalidated(v5) )
  {
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
      WPP_SF_q(769, 176, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    if ( (xmmword_180107A60 & 2) != 0 )
    {
      v35 = HTTP_USER_REQUEST::MapState(v7, LODWORD(this[1].OwningThread));
      WPP_SF_qss((unsigned int)"_DONE", 14, v36, (_DWORD)this, v35, (__int64)"_DONE");
    }
    EnterCriticalSection(this + 6);
    LODWORD(this[1].OwningThread) = 5;
    LeaveCriticalSection(this + 6);
    goto LABEL_30;
  }
  v9 = *((unsigned int *)a2 + 31);
  v10 = *((_QWORD *)a2 + 14);
  v11 = *((_DWORD *)a2 + 30) - v9;
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_qqqdddl(*((_DWORD *)a2 + 30), v6, v8, (_DWORD)this, (__int64)a2, v10);
  if ( !this[4].SpinCount )
  {
LABEL_49:
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
      WPP_SF_q(769, 178, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    HTTP_USER_REQUEST::_TransitToState(this, 5);
LABEL_30:
    v27 = 12017;
    v28 = 12017;
    goto LABEL_31;
  }
  EnterCriticalSection(this + 6);
  v12 = (void (__fastcall ***)(ULONG_PTR))this[4].SpinCount;
  if ( !v12 )
  {
    LeaveCriticalSection(this + 6);
    goto LABEL_49;
  }
  (**v12)(this[4].SpinCount);
  LeaveCriticalSection(this + 6);
  v13 = (*((_BYTE *)a2 + 56) & 0xC0) == 0;
  *((_QWORD *)a2 + 16) = v12;
  if ( !v13 )
  {
    v39 = 0;
    v40 = 0;
    if ( !*((_DWORD *)a2 + 10) || (v29 = *((_DWORD *)a2 + 11), GetCurrentThreadId() == v29) )
    {
      v14 = 16;
      v15 = &v39;
      v16 = 16;
      do
      {
        LOBYTE(v15->Data1) = 0;
        v15 = (struct _GUID *)((char *)v15 + 1);
        --v16;
      }
      while ( v16 );
      v40 = 0;
      v17 = &v39;
      v42 = 0;
      v41 = 0;
      do
      {
        LOBYTE(v17->Data1) = 0;
        v17 = (struct _GUID *)((char *)v17 + 1);
        --v14;
      }
      while ( v14 );
      WxEtwGetActivityId(&v41);
      v38 = 0;
      v18 = EtwEventActivityIdControl(2, &WinHttpEtwNullActivityId);
      v19 = v18 < 0;
      if ( v18 > 0 )
        v19 = 1;
      if ( v19 )
        v38 = 144;
      v20 = *((_QWORD *)a2 + 8);
      v21 = this->SpinCount;
      v22 = (void (__fastcall *)(ULONG_PTR, __int64, __int64, _QWORD, _DWORD))*((_QWORD *)a2 + 6);
      v39 = v41;
      v40 = 1;
      v22(v21, v20, 64, 0, 0);
      if ( v40 )
      {
        v38 = 0;
        v23 = EtwEventActivityIdControl(2, &v39);
        v24 = v23 < 0;
        if ( v23 > 0 )
          v24 = 1;
        if ( v24 )
          v38 = 144;
      }
    }
    else
    {
      v30 = (void *)*((_QWORD *)a2 + 9);
      *((_DWORD *)a2 + 35) = 1;
      *((_DWORD *)a2 + 36) = 64;
      *((_QWORD *)a2 + 19) = 0;
      *((_DWORD *)a2 + 40) = 0;
      SetEvent(v30);
      WaitForSingleObjectEx(*((HANDLE *)a2 + 10), 0xFFFFFFFF, 0);
      *(_QWORD *)((char *)a2 + 140) = 0;
      *((_QWORD *)a2 + 19) = 0;
      *((_DWORD *)a2 + 40) = 0;
    }
  }
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->Type)(this);
  (**(void (__fastcall ***)(struct PENDING_API_CALL *))a2)(a2);
  result = WEBIO_REQUEST::ReadData(
             *((WEBIO_REQUEST **)a2 + 16),
             (unsigned __int8 *)(v10 + v9),
             v11,
             v37,
             *((_DWORD *)a2 + 41),
             *(_DWORD *)(this->SpinCount + 924),
             (unsigned __int64)a2);
  v26 = result;
  if ( result != 997 )
  {
    (*(void (__fastcall **)(struct PENDING_API_CALL *))(*(_QWORD *)a2 + 8LL))(a2);
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->CriticalSection)(this);
    Data = HTTP_USER_REQUEST::_PostProcessReadData((HTTP_USER_REQUEST *)this, v26, a2, v37);
    v28 = Data;
    if ( Data == 997 || !Data )
    {
      v27 = 12017;
LABEL_37:
      if ( !a2 )
        return v28;
      EnterCriticalSection(this + 6);
      v32 = *((_DWORD *)a2 + 7);
      if ( v32 )
      {
        if ( v32 == 1 )
        {
          LODWORD(this[1].OwningThread) = 5;
          LeaveCriticalSection(this + 6);
          *((_DWORD *)a2 + 8) = 12017;
LABEL_42:
          if ( (xmmword_180107A60 & 2) != 0 )
            WPP_SF_qqqdd(*((_QWORD *)a2 + 14), v33, v34, (_DWORD)this, (__int64)a2, *((_QWORD *)a2 + 14));
          return v27;
        }
      }
      else
      {
        *((_DWORD *)a2 + 7) = 2;
      }
      LeaveCriticalSection(this + 6);
      *((_DWORD *)a2 + 8) = v28;
      v27 = v28;
      if ( !v28 )
      {
        *((_DWORD *)a2 + 31) += v37[0];
        *((_DWORD *)a2 + 9) = *((_DWORD *)a2 + 31);
      }
      goto LABEL_42;
    }
    v27 = 12017;
LABEL_31:
    HTTP_USER_REQUEST::_SafeDetachSysReq((HTTP_USER_REQUEST *)this);
    goto LABEL_37;
  }
  return result;
}

```

## disassembly

```asm
0x180037600  push    rbx
0x180037602  push    rdi
0x180037603  push    r13
0x180037605  push    r15
0x180037607  sub     rsp, 0B8h
0x18003760e  mov     rax, cs:__security_cookie
0x180037615  xor     rax, rsp
0x180037618  mov     [rsp+0D8h+var_40], rax
0x180037620  mov     rax, [rcx+20h]
0x180037624  mov     r15, rcx
0x180037627  xor     r13d, r13d
0x18003762a  mov     rdi, rdx
0x18003762d  mov     [rsp+0D8h+var_88], r13d
0x180037632  mov     rbx, [rax+18h]
0x180037636  mov     rcx, rbx
0x180037639  mov     rax, [rbx]
0x18003763c  mov     rax, [rax+8]
0x180037640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037645  cmp     eax, 74656E49h
0x18003764a  jz      short loc_180037650
0x18003764c  mov     rbx, [rbx+18h]
0x180037650  mov     [rsp+0D8h+arg_10], rbp
0x180037658  mov     rcx, rbx; this
0x18003765b  mov     [rsp+0D8h+var_28], rsi
0x180037663  mov     [rsp+0D8h+var_30], r12
0x18003766b  mov     [rsp+0D8h+var_38], r14
0x180037673  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x180037678  test    eax, eax
0x18003767a  jnz     loc_18003788E
0x180037680  mov     ecx, [rdi+78h]
0x180037683  mov     r12d, ecx
0x180037686  mov     ebp, [rdi+7Ch]
0x180037689  mov     r14, [rdi+70h]
0x18003768d  sub     r12d, ebp
0x180037690  test    byte ptr cs:xmmword_180107A60, 2
0x180037697  jnz     loc_180037A58
0x18003769d  cmp     [r15+0C0h], r13
0x1800376a4  jz      loc_180037A17
0x1800376aa  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800376b1  call    cs:__imp_EnterCriticalSection
0x1800376b7  mov     rbx, [r15+0C0h]
0x1800376be  test    rbx, rbx
0x1800376c1  jz      loc_180037A0A
0x1800376c7  mov     rax, [rbx]
0x1800376ca  mov     rcx, rbx
0x1800376cd  mov     rax, [rax]
0x1800376d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d5  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800376dc  call    cs:__imp_LeaveCriticalSection
0x1800376e2  test    byte ptr [rdi+38h], 0C0h
0x1800376e6  lea     rsi, [r14+rbp]
0x1800376ea  mov     [rdi+80h], rbx
0x1800376f1  jz      loc_1800377F3
0x1800376f7  xor     eax, eax
0x1800376f9  xorps   xmm0, xmm0
0x1800376fc  movups  [rsp+0D8h+var_78], xmm0
0x180037701  mov     [rsp+0D8h+var_68], eax
0x180037705  cmp     [rdi+28h], eax
0x180037708  jnz     loc_1800378DE
0x18003770e  mov     ecx, 10h
0x180037713  lea     rax, [rsp+0D8h+var_78]
0x180037718  mov     edx, ecx
0x18003771a  nop     word ptr [rax+rax+00h]
0x180037720  mov     [rax], r13b
0x180037723  lea     rax, [rax+1]
0x180037727  sub     rdx, 1
0x18003772b  jnz     short loc_180037720
0x18003772d  xorps   xmm0, xmm0
0x180037730  mov     [rsp+0D8h+var_68], r13d
0x180037735  xorps   xmm1, xmm1
0x180037738  lea     rax, [rsp+0D8h+var_78]
0x18003773d  movups  [rsp+0D8h+var_50], xmm0
0x180037745  movups  xmmword ptr [rsp+0D8h+var_60.Data1], xmm1
0x18003774a  nop     word ptr [rax+rax+00h]
0x180037750  mov     [rax], r13b
0x180037753  lea     rax, [rax+1]
0x180037757  sub     rcx, 1
0x18003775b  jnz     short loc_180037750
0x18003775d  lea     rcx, [rsp+0D8h+var_60]; struct _GUID *
0x180037762  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180037767  lea     rdx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; _GUID const WinHttpEtwNullActivityId
0x18003776e  mov     [rsp+0D8h+var_7C], r13d
0x180037773  mov     ecx, 2
0x180037778  call    cs:__imp_EtwEventActivityIdControl
0x18003777e  test    eax, eax
0x180037780  jle     short loc_18003778C
0x180037782  movzx   eax, ax
0x180037785  or      eax, 80070000h
0x18003778a  test    eax, eax
0x18003778c  js      loc_180037AD0
0x180037792  movups  xmm0, xmmword ptr [rsp+0D8h+var_60.Data1]
0x180037797  mov     rdx, [rdi+40h]
0x18003779b  xor     r9d, r9d
0x18003779e  mov     rcx, [r15+20h]
0x1800377a2  mov     r8d, 40h ; '@'
0x1800377a8  mov     rax, [rdi+30h]
0x1800377ac  movups  [rsp+0D8h+var_78], xmm0
0x1800377b1  mov     [rsp+0D8h+var_68], 1
0x1800377b9  mov     [rsp+0D8h+var_B8], r13d
0x1800377be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377c3  cmp     [rsp+0D8h+var_68], r13d
0x1800377c8  jz      short loc_1800377F3
0x1800377ca  lea     rdx, [rsp+0D8h+var_78]
0x1800377cf  mov     [rsp+0D8h+var_7C], r13d
0x1800377d4  mov     ecx, 2
0x1800377d9  call    cs:__imp_EtwEventActivityIdControl
0x1800377df  test    eax, eax
0x1800377e1  jle     short loc_1800377ED
0x1800377e3  movzx   eax, ax
0x1800377e6  or      eax, 80070000h
0x1800377eb  test    eax, eax
0x1800377ed  js      loc_180037A4B
0x1800377f3  mov     rax, [r15]
0x1800377f6  mov     rcx, r15
0x1800377f9  mov     rax, [rax]
0x1800377fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037801  mov     rax, [rdi]
0x180037804  mov     rcx, rdi
0x180037807  mov     rax, [rax]
0x18003780a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003780f  mov     rax, [r15+20h]
0x180037813  lea     r9, [rsp+0D8h+var_88]; unsigned int *
0x180037818  mov     rcx, [rdi+80h]; this
0x18003781f  mov     r8d, r12d; unsigned int
0x180037822  mov     [rsp+0D8h+var_A8], rdi; unsigned __int64
0x180037827  mov     rdx, rsi; unsigned __int8 *
0x18003782a  mov     eax, [rax+39Ch]
0x180037830  mov     [rsp+0D8h+var_B0], eax; unsigned int
0x180037834  mov     eax, [rdi+0A4h]
0x18003783a  mov     [rsp+0D8h+var_B8], eax; int
0x18003783e  call    ?ReadData@WEBIO_REQUEST@@QEAAKPEAEKPEAKHK_K@Z; WEBIO_REQUEST::ReadData(uchar *,ulong,ulong *,int,ulong,unsigned __int64)
0x180037843  mov     ebx, eax
0x180037845  cmp     eax, 3E5h
0x18003784a  jnz     loc_180037947
0x180037850  mov     r14, [rsp+0D8h+var_38]
0x180037858  mov     r12, [rsp+0D8h+var_30]
0x180037860  mov     rsi, [rsp+0D8h+var_28]
0x180037868  mov     rbp, [rsp+0D8h+arg_10]
0x180037870  mov     rcx, [rsp+0D8h+var_40]
0x180037878  xor     rcx, rsp; StackCookie
0x18003787b  call    __security_check_cookie
0x180037880  add     rsp, 0B8h
0x180037887  pop     r15
0x180037889  pop     r13
0x18003788b  pop     rdi
0x18003788c  pop     rbx
0x18003788d  retn
0x18003788e  test    byte ptr cs:xmmword_180107A50+8, 2
0x180037895  jnz     loc_180037A86
0x18003789b  test    byte ptr cs:xmmword_180107A60, 2
0x1800378a2  jnz     loc_180037AA4
0x1800378a8  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800378af  call    cs:__imp_EnterCriticalSection
0x1800378b5  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800378bc  mov     dword ptr [r15+38h], 5
0x1800378c4  call    cs:__imp_LeaveCriticalSection
0x1800378ca  mov     esi, 2EF1h
0x1800378cf  mov     ebx, esi
0x1800378d1  mov     rcx, r15; this
0x1800378d4  call    ?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_SafeDetachSysReq(void)
0x1800378d9  jmp     loc_18003798D
0x1800378de  mov     ebx, [rdi+2Ch]
0x1800378e1  call    cs:__imp_GetCurrentThreadId
0x1800378e7  cmp     eax, ebx
0x1800378e9  jz      loc_18003770E
0x1800378ef  mov     rcx, [rdi+48h]; hEvent
0x1800378f3  mov     dword ptr [rdi+8Ch], 1
0x1800378fd  mov     dword ptr [rdi+90h], 40h ; '@'
0x180037907  mov     [rdi+98h], r13
0x18003790e  mov     [rdi+0A0h], r13d
0x180037915  call    cs:__imp_SetEvent
0x18003791b  mov     rcx, [rdi+50h]; hHandle
0x18003791f  xor     r8d, r8d; bAlertable
0x180037922  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180037927  call    cs:__imp_WaitForSingleObjectEx
0x18003792d  mov     [rdi+8Ch], r13
0x180037934  mov     [rdi+98h], r13
0x18003793b  mov     [rdi+0A0h], r13d
0x180037942  jmp     loc_1800377F3
0x180037947  mov     rcx, [rdi]
0x18003794a  mov     rax, [rcx+8]
0x18003794e  mov     rcx, rdi
0x180037951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037956  mov     rcx, [r15]
0x180037959  mov     rax, [rcx+8]
0x18003795d  mov     rcx, r15
0x180037960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037965  lea     r9, [rsp+0D8h+var_88]; unsigned int *
0x18003796a  mov     r8, rdi; struct PENDING_API_CALL *
0x18003796d  mov     edx, ebx; unsigned int
0x18003796f  mov     rcx, r15; this
0x180037972  call    ?_PostProcessReadData@HTTP_USER_REQUEST@@AEAAKKPEAVPENDING_API_CALL@@PEAK@Z; HTTP_USER_REQUEST::_PostProcessReadData(ulong,PENDING_API_CALL *,ulong *)
0x180037977  mov     ebx, eax
0x180037979  cmp     eax, 3E5h
0x18003797e  jz      short loc_180037988
0x180037980  test    eax, eax
0x180037982  jnz     loc_180037ADD
0x180037988  mov     esi, 2EF1h
0x18003798d  test    rdi, rdi
0x180037990  jz      short loc_1800379E4
0x180037992  lea     rcx, [r15+0F0h]; lpCriticalSection
0x180037999  call    cs:__imp_EnterCriticalSection
0x18003799f  mov     eax, [rdi+1Ch]
0x1800379a2  test    eax, eax
0x1800379a4  jnz     short loc_1800379EB
0x1800379a6  mov     dword ptr [rdi+1Ch], 2
0x1800379ad  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800379b4  call    cs:__imp_LeaveCriticalSection
0x1800379ba  mov     [rdi+20h], ebx
0x1800379bd  mov     esi, ebx
0x1800379bf  test    ebx, ebx
0x1800379c1  jnz     short loc_1800379D0
0x1800379c3  mov     eax, [rsp+0D8h+var_88]
0x1800379c7  add     [rdi+7Ch], eax
0x1800379ca  mov     eax, [rdi+7Ch]
0x1800379cd  mov     [rdi+24h], eax
0x1800379d0  test    byte ptr cs:xmmword_180107A60, 2
0x1800379d7  jnz     loc_180037AE7
0x1800379dd  mov     eax, esi
0x1800379df  jmp     loc_180037850
0x1800379e4  mov     eax, ebx
0x1800379e6  jmp     loc_180037850
0x1800379eb  cmp     eax, 1
0x1800379ee  jnz     short loc_1800379AD
0x1800379f0  lea     rcx, [r15+0F0h]; lpCriticalSection
0x1800379f7  mov     dword ptr [r15+38h], 5
0x1800379ff  call    cs:__imp_LeaveCriticalSection
0x180037a05  mov     [rdi+20h], esi
0x180037a08  jmp     short loc_1800379D0
0x180037a0a  lea     rcx, [r15+0F0h]; lpCriticalSection
0x180037a11  call    cs:__imp_LeaveCriticalSection
0x180037a17  test    byte ptr cs:xmmword_180107A50+8, 2
0x180037a1e  jz      short loc_180037A39
0x180037a20  mov     edx, 0B2h
0x180037a25  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180037a2c  mov     ecx, 301h
0x180037a31  mov     r9, r15
0x180037a34  call    WPP_SF_q
0x180037a39  mov     edx, 5
0x180037a3e  mov     rcx, r15
0x180037a41  call    ?_TransitToState@HTTP_USER_REQUEST@@AEAAXW4_STATE@1@@Z; HTTP_USER_REQUEST::_TransitToState(HTTP_USER_REQUEST::_STATE)
0x180037a46  jmp     loc_1800378CA
0x180037a4b  mov     [rsp+0D8h+var_7C], 90h
0x180037a53  jmp     loc_1800377F3
0x180037a58  mov     eax, [rdi+0A4h]
0x180037a5e  mov     r9, r15
0x180037a61  mov     [rsp+0D8h+var_90], eax
0x180037a65  mov     [rsp+0D8h+var_98], r12d
0x180037a6a  mov     [rsp+0D8h+var_A0], ebp
0x180037a6e  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x180037a72  mov     qword ptr [rsp+0D8h+var_B0], r14
0x180037a77  mov     qword ptr [rsp+0D8h+var_B8], rdi
0x180037a7c  call    WPP_SF_qqqdddl
0x180037a81  jmp     loc_18003769D
0x180037a86  mov     edx, 0B0h
0x180037a8b  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180037a92  mov     ecx, 301h
0x180037a97  mov     r9, r15
0x180037a9a  call    WPP_SF_q
0x180037a9f  jmp     loc_18003789B
0x180037aa4  mov     edx, [r15+38h]
0x180037aa8  call    ?MapState@HTTP_USER_REQUEST@@AEAAPEADW4_STATE@1@@Z; HTTP_USER_REQUEST::MapState(HTTP_USER_REQUEST::_STATE)
0x180037aad  lea     rcx, aDone; "_DONE"
0x180037ab4  mov     edx, 0Eh
0x180037ab9  mov     qword ptr [rsp+0D8h+var_B0], rcx
0x180037abe  mov     r9, r15
0x180037ac1  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180037ac6  call    WPP_SF_qss
0x180037acb  jmp     loc_1800378A8
0x180037ad0  mov     [rsp+0D8h+var_7C], 90h
0x180037ad8  jmp     loc_180037792
0x180037add  mov     esi, 2EF1h
0x180037ae2  jmp     loc_1800378D1
0x180037ae7  mov     ecx, [rdi+7Ch]
0x180037aea  mov     r9, r15
0x180037aed  mov     [rsp+0D8h+var_A0], ecx
0x180037af1  mov     ecx, [rdi+78h]
0x180037af4  mov     dword ptr [rsp+0D8h+var_A8], ecx
0x180037af8  mov     rcx, [rdi+70h]
0x180037afc  mov     qword ptr [rsp+0D8h+var_B0], rcx
0x180037b01  mov     qword ptr [rsp+0D8h+var_B8], rdi
0x180037b06  call    WPP_SF_qqqdd
0x180037b0b  jmp     loc_1800379DD
```
