# CSsdpNotifyRequest::HrEndSendPropChangeSubscription(_SSDP_REGISTER_INFO * *)

- ea: `0x18001c974`
- end: `0x18001cbb8`
- name: `?HrEndSendPropChangeSubscription@CSsdpNotifyRequest@@QEAAJPEAPEAU_SSDP_REGISTER_INFO@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(CSsdpNotifyRequest *__hidden this, struct _SSDP_REGISTER_INFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001c7e8`

## callees

- `0x180005588`
- `0x18000936c`
- `0x1800140e0`
- `0x18001c974`
- `0x180024e8c`
- `0x18002c8cc`
- `0x18002c90c`
- `0x18002edf0`
- `0x18002f078`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ca01`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ca01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001caa0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001caa0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ca7a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001c9ee`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001c9ee`

## string_xrefs

- `0x18001cb14`: `CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP timed out.`
- `0x18001cb44`: `CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP failed.`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequest::HrEndSendPropChangeSubscription(
        CSsdpNotifyRequest *this,
        struct _SSDP_REGISTER_INFO **a2)
{
  signed int v4; // eax
  signed int Results; // edi
  void *v6; // rax
  unsigned int *v7; // r9
  __int64 *v8; // rsi
  LPCSTR v9; // rcx
  int v10; // edx
  const char *v11; // r9
  __int64 v13; // [rsp+20h] [rbp-58h]
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  Handles[0] = *((HANDLE *)this + 40);
  Handles[1] = *((HANDLE *)this + 39);
  *a2 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, this);
  v4 = WaitForMultipleObjects(2u, Handles, 0, 0xAFC8u);
  Results = v4;
  switch ( v4 )
  {
    case 0:
      v6 = malloc(0x10u);
      v8 = (__int64 *)v6;
      if ( !v6 )
      {
        Results = -2147024882;
LABEL_33:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_34;
      }
      Results = CSsdpNotifyRequest::GetResults(this, (unsigned int *)v6 + 2, (char **)v6, v7);
      if ( Results < 0 )
        goto LABEL_31;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
          (_DWORD)this,
          *v8);
      Results = CUString::HrAssign((CSsdpNotifyRequest *)((char *)this + 72), (const char *)*v8);
      if ( Results < 0 )
        goto LABEL_31;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      Results = CTimerBase::HrSetTimer((char *)this + 104, 65000 * *((_DWORD *)this + 16) / 0x64u);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      goto LABEL_27;
    case 1:
      Results = -2147467260;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
        return (unsigned int)Results;
      if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_34;
      v10 = 164;
      v11 = "CSsdpNotifyRequest::HrSendPropChangeSubscription - request got cancelled.";
LABEL_17:
      WPP_SF_sd(
        *((_QWORD *)v9 + 2),
        v10,
        (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
        (_DWORD)v11,
        Results);
      goto LABEL_33;
    case 258:
      Results = -2147024638;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
        return (unsigned int)Results;
      if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_34;
      v10 = 165;
      v11 = "CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP timed out.";
      goto LABEL_17;
  }
  v8 = 0;
  if ( v4 > 0 )
    Results = (unsigned __int16)v4 | 0x80070000;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      166,
      (unsigned int)WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
      (unsigned int)"CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP failed.",
      v4);
LABEL_27:
    v9 = WPP_GLOBAL_Control;
  }
  if ( Results >= 0 )
  {
    *a2 = (struct _SSDP_REGISTER_INFO *)v8;
    goto LABEL_32;
  }
  if ( v8 )
  {
LABEL_31:
    operator delete(v8);
LABEL_32:
    if ( !Results )
      return (unsigned int)Results;
    goto LABEL_33;
  }
LABEL_34:
  if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
  {
    LODWORD(v13) = Results;
    WPP_SF_Dd(*((_QWORD *)v9 + 2), 167, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, (unsigned int)Results, v13);
  }
  return (unsigned int)Results;
}

```

## disassembly

```asm
0x18001c974  push    rbx
0x18001c976  push    rbp
0x18001c977  push    rsi
0x18001c978  push    rdi
0x18001c979  push    r12
0x18001c97b  push    r14
0x18001c97d  push    r15
0x18001c97f  sub     rsp, 40h
0x18001c983  mov     rax, [rcx+140h]
0x18001c98a  mov     r14, rdx
0x18001c98d  mov     [rsp+78h+Handles], rax
0x18001c992  mov     rbp, rcx
0x18001c995  mov     rax, [rcx+138h]
0x18001c99c  mov     [rsp+78h+var_40], rax
0x18001c9a1  mov     qword ptr [rdx], 0
0x18001c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9af  lea     r15, WPP_GLOBAL_Control
0x18001c9b6  lea     r12, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18001c9bd  cmp     rcx, r15
0x18001c9c0  jz      short loc_18001C9DC
0x18001c9c2  test    byte ptr [rcx+1Ch], 8
0x18001c9c6  jz      short loc_18001C9DC
0x18001c9c8  mov     rcx, [rcx+10h]
0x18001c9cc  mov     edx, 0A2h
0x18001c9d1  mov     r9, rbp
0x18001c9d4  mov     r8, r12
0x18001c9d7  call    WPP_SF_q
0x18001c9dc  xor     r8d, r8d; bWaitAll
0x18001c9df  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18001c9e4  mov     r9d, 0AFC8h; dwMilliseconds
0x18001c9ea  lea     ecx, [r8+2]; nCount
0x18001c9ee  call    cs:__imp_WaitForMultipleObjects
0x18001c9f4  mov     edi, eax
0x18001c9f6  test    eax, eax
0x18001c9f8  jnz     loc_18001CAAB
0x18001c9fe  lea     ecx, [rax+10h]; Size
0x18001ca01  call    cs:__imp_malloc
0x18001ca07  mov     rsi, rax
0x18001ca0a  test    rax, rax
0x18001ca0d  jnz     short loc_18001CA19
0x18001ca0f  mov     edi, 8007000Eh
0x18001ca14  jmp     loc_18001CB7D
0x18001ca19  lea     rdx, [rax+8]; unsigned int *
0x18001ca1d  mov     r8, rsi; char **
0x18001ca20  mov     rcx, rbp; this
0x18001ca23  call    ?GetResults@CSsdpNotifyRequest@@QEAAJPEAKPEAPEAD0@Z; CSsdpNotifyRequest::GetResults(ulong *,char * *,ulong *)
0x18001ca28  mov     edi, eax
0x18001ca2a  test    eax, eax
0x18001ca2c  js      loc_18001CB71
0x18001ca32  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca39  cmp     rcx, r15
0x18001ca3c  jz      short loc_18001CA60
0x18001ca3e  test    byte ptr [rcx+1Ch], 8
0x18001ca42  jz      short loc_18001CA60
0x18001ca44  mov     rax, [rsi]
0x18001ca47  mov     edx, 0A3h
0x18001ca4c  mov     rcx, [rcx+10h]
0x18001ca50  mov     r9, rbp
0x18001ca53  mov     r8, r12
0x18001ca56  mov     [rsp+78h+var_58], rax
0x18001ca5b  call    WPP_SF_qs
0x18001ca60  mov     rdx, [rsi]; char *
0x18001ca63  lea     rcx, [rbp+48h]; this
0x18001ca67  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x18001ca6c  mov     edi, eax
0x18001ca6e  test    eax, eax
0x18001ca70  js      loc_18001CB71
0x18001ca76  lea     rcx, [rbp+8]; lpCriticalSection
0x18001ca7a  call    cs:__imp_EnterCriticalSection
0x18001ca80  imul    edx, [rbp+40h], 0FDE8h
0x18001ca87  lea     rcx, [rbp+68h]; Parameter
0x18001ca8b  mov     eax, 51EB851Fh
0x18001ca90  mul     edx
0x18001ca92  shr     edx, 5; DueTime
0x18001ca95  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x18001ca9a  lea     rcx, [rbp+8]; lpCriticalSection
0x18001ca9e  mov     edi, eax
0x18001caa0  call    cs:__imp_LeaveCriticalSection
0x18001caa6  jmp     loc_18001CB5C
0x18001caab  cmp     eax, 1
0x18001caae  jnz     short loc_18001CAEF
0x18001cab0  mov     edi, 80004004h
0x18001cab5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cabc  cmp     rcx, r15
0x18001cabf  jz      loc_18001CBA7
0x18001cac5  test    [rcx+1Ch], al
0x18001cac8  jz      loc_18001CB84
0x18001cace  mov     edx, 0A4h
0x18001cad3  lea     r9, aCssdpnotifyreq_3; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001cada  mov     rcx, [rcx+10h]
0x18001cade  mov     r8, r12
0x18001cae1  mov     dword ptr [rsp+78h+var_58], edi
0x18001cae5  call    WPP_SF_sd
0x18001caea  jmp     loc_18001CB7D
0x18001caef  cmp     eax, 102h
0x18001caf4  jnz     short loc_18001CB1D
0x18001caf6  mov     edi, 80070102h
0x18001cafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb02  cmp     rcx, r15
0x18001cb05  jz      loc_18001CBA7
0x18001cb0b  test    byte ptr [rcx+1Ch], 1
0x18001cb0f  jz      short loc_18001CB84
0x18001cb11  lea     edx, [rax-5Dh]
0x18001cb14  lea     r9, aCssdpnotifyreq_4; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001cb1b  jmp     short loc_18001CADA
0x18001cb1d  xor     esi, esi
0x18001cb1f  test    eax, eax
0x18001cb21  jle     short loc_18001CB2E
0x18001cb23  movzx   edi, ax
0x18001cb26  or      edi, 80070000h
0x18001cb2c  mov     eax, edi
0x18001cb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb35  cmp     rcx, r15
0x18001cb38  jz      short loc_18001CB63
0x18001cb3a  test    byte ptr [rcx+1Ch], 1
0x18001cb3e  jz      short loc_18001CB63
0x18001cb40  mov     rcx, [rcx+10h]
0x18001cb44  lea     r9, aCssdpnotifyreq; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001cb4b  mov     edx, 0A6h
0x18001cb50  mov     dword ptr [rsp+78h+var_58], eax
0x18001cb54  mov     r8, r12
0x18001cb57  call    WPP_SF_sd
0x18001cb5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb63  test    edi, edi
0x18001cb65  js      short loc_18001CB6C
0x18001cb67  mov     [r14], rsi
0x18001cb6a  jmp     short loc_18001CB79
0x18001cb6c  test    rsi, rsi
0x18001cb6f  jz      short loc_18001CB84
0x18001cb71  mov     rcx, rsi; void *
0x18001cb74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb79  test    edi, edi
0x18001cb7b  jz      short loc_18001CBA7
0x18001cb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb84  cmp     rcx, r15
0x18001cb87  jz      short loc_18001CBA7
0x18001cb89  test    byte ptr [rcx+1Ch], 1
0x18001cb8d  jz      short loc_18001CBA7
0x18001cb8f  mov     rcx, [rcx+10h]
0x18001cb93  mov     edx, 0A7h
0x18001cb98  mov     r9d, edi
0x18001cb9b  mov     dword ptr [rsp+78h+var_58], edi
0x18001cb9f  mov     r8, r12
0x18001cba2  call    WPP_SF_Dd
0x18001cba7  mov     eax, edi
0x18001cba9  add     rsp, 40h
0x18001cbad  pop     r15
0x18001cbaf  pop     r14
0x18001cbb1  pop     r12
0x18001cbb3  pop     rdi
0x18001cbb4  pop     rsi
0x18001cbb5  pop     rbp
0x18001cbb6  pop     rbx
0x18001cbb7  retn
```
