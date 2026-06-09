# CSsdpNotifyRequest::HrEndSendPropChangeSubscription(_SSDP_REGISTER_INFO * *)

- ea: `0x18001ddf4`
- end: `0x18001e051`
- name: `?HrEndSendPropChangeSubscription@CSsdpNotifyRequest@@QEAAJPEAPEAU_SSDP_REGISTER_INFO@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(CSsdpNotifyRequest *__hidden this, struct _SSDP_REGISTER_INFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dc44`

## callees

- `0x180006880`
- `0x18000a9ac`
- `0x180016620`
- `0x18001ddf4`
- `0x180026a54`
- `0x18002e8ac`
- `0x18002e8f0`
- `0x180031018`
- `0x1800312cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001de87`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001de87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df06`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001de6e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001de6e`

## string_xrefs

- `0x18001dfac`: `CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP timed out.`
- `0x18001dfdc`: `CSsdpNotifyRequest::HrSendPropChangeSubscription -  Wait for completion of WinHTTP failed.`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequest::HrEndSendPropChangeSubscription(
        CSsdpNotifyRequest *this,
        struct _SSDP_REGISTER_INFO **a2)
{
  signed int v4; // eax
  int Results; // edi
  void *v6; // rax
  unsigned int *v7; // r9
  __int64 *v8; // rsi
  LPCSTR v9; // rcx
  int v10; // edx
  const char *v11; // r9
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  Handles[0] = *((HANDLE *)this + 40);
  Handles[1] = *((HANDLE *)this + 39);
  *a2 = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
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
    WPP_SF_Dd(*((_QWORD *)v9 + 2), 167, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, (unsigned int)Results, Results);
  return (unsigned int)Results;
}

```

## disassembly

```asm
0x18001ddf4  push    rbx
0x18001ddf6  push    rbp
0x18001ddf7  push    rsi
0x18001ddf8  push    rdi
0x18001ddf9  push    r12
0x18001ddfb  push    r14
0x18001ddfd  push    r15
0x18001ddff  sub     rsp, 40h
0x18001de03  mov     rax, [rcx+140h]
0x18001de0a  mov     r14, rdx
0x18001de0d  mov     [rsp+78h+Handles], rax
0x18001de12  mov     rbp, rcx
0x18001de15  mov     rax, [rcx+138h]
0x18001de1c  mov     [rsp+78h+var_40], rax
0x18001de21  mov     qword ptr [rdx], 0
0x18001de28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de2f  lea     r15, WPP_GLOBAL_Control
0x18001de36  lea     r12, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18001de3d  cmp     rcx, r15
0x18001de40  jz      short loc_18001DE5C
0x18001de42  test    byte ptr [rcx+1Ch], 8
0x18001de46  jz      short loc_18001DE5C
0x18001de48  mov     rcx, [rcx+10h]
0x18001de4c  mov     edx, 0A2h
0x18001de51  mov     r9, rbp
0x18001de54  mov     r8, r12
0x18001de57  call    WPP_SF_q
0x18001de5c  xor     r8d, r8d; bWaitAll
0x18001de5f  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18001de64  mov     r9d, 0AFC8h; dwMilliseconds
0x18001de6a  lea     ecx, [r8+2]; nCount
0x18001de6e  call    cs:__imp_WaitForMultipleObjects
0x18001de75  nop     dword ptr [rax+rax+00h]
0x18001de7a  mov     edi, eax
0x18001de7c  test    eax, eax
0x18001de7e  jnz     loc_18001DF43
0x18001de84  lea     ecx, [rax+10h]; Size
0x18001de87  call    cs:__imp_malloc
0x18001de8e  nop     dword ptr [rax+rax+00h]
0x18001de93  mov     rsi, rax
0x18001de96  test    rax, rax
0x18001de99  jnz     short loc_18001DEA5
0x18001de9b  mov     edi, 8007000Eh
0x18001dea0  jmp     loc_18001E015
0x18001dea5  lea     rdx, [rax+8]; unsigned int *
0x18001dea9  mov     r8, rsi; char **
0x18001deac  mov     rcx, rbp; this
0x18001deaf  call    ?GetResults@CSsdpNotifyRequest@@QEAAJPEAKPEAPEAD0@Z; CSsdpNotifyRequest::GetResults(ulong *,char * *,ulong *)
0x18001deb4  mov     edi, eax
0x18001deb6  test    eax, eax
0x18001deb8  js      loc_18001E009
0x18001debe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dec5  cmp     rcx, r15
0x18001dec8  jz      short loc_18001DEEC
0x18001deca  test    byte ptr [rcx+1Ch], 8
0x18001dece  jz      short loc_18001DEEC
0x18001ded0  mov     rax, [rsi]
0x18001ded3  mov     edx, 0A3h
0x18001ded8  mov     rcx, [rcx+10h]
0x18001dedc  mov     r9, rbp
0x18001dedf  mov     r8, r12
0x18001dee2  mov     [rsp+78h+var_58], rax
0x18001dee7  call    WPP_SF_qs
0x18001deec  mov     rdx, [rsi]; char *
0x18001deef  lea     rcx, [rbp+48h]; this
0x18001def3  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x18001def8  mov     edi, eax
0x18001defa  test    eax, eax
0x18001defc  js      loc_18001E009
0x18001df02  lea     rcx, [rbp+8]; lpCriticalSection
0x18001df06  call    cs:__imp_EnterCriticalSection
0x18001df0d  nop     dword ptr [rax+rax+00h]
0x18001df12  imul    edx, [rbp+40h], 0FDE8h
0x18001df19  lea     rcx, [rbp+68h]; Parameter
0x18001df1d  mov     eax, 51EB851Fh
0x18001df22  mul     edx
0x18001df24  shr     edx, 5; DueTime
0x18001df27  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x18001df2c  lea     rcx, [rbp+8]; lpCriticalSection
0x18001df30  mov     edi, eax
0x18001df32  call    cs:__imp_LeaveCriticalSection
0x18001df39  nop     dword ptr [rax+rax+00h]
0x18001df3e  jmp     loc_18001DFF4
0x18001df43  cmp     eax, 1
0x18001df46  jnz     short loc_18001DF87
0x18001df48  mov     edi, 80004004h
0x18001df4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df54  cmp     rcx, r15
0x18001df57  jz      loc_18001E03F
0x18001df5d  test    [rcx+1Ch], al
0x18001df60  jz      loc_18001E01C
0x18001df66  mov     edx, 0A4h
0x18001df6b  lea     r9, aCssdpnotifyreq_3; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001df72  mov     rcx, [rcx+10h]
0x18001df76  mov     r8, r12
0x18001df79  mov     dword ptr [rsp+78h+var_58], edi
0x18001df7d  call    WPP_SF_sd
0x18001df82  jmp     loc_18001E015
0x18001df87  cmp     eax, 102h
0x18001df8c  jnz     short loc_18001DFB5
0x18001df8e  mov     edi, 80070102h
0x18001df93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df9a  cmp     rcx, r15
0x18001df9d  jz      loc_18001E03F
0x18001dfa3  test    byte ptr [rcx+1Ch], 1
0x18001dfa7  jz      short loc_18001E01C
0x18001dfa9  lea     edx, [rax-5Dh]
0x18001dfac  lea     r9, aCssdpnotifyreq_4; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001dfb3  jmp     short loc_18001DF72
0x18001dfb5  xor     esi, esi
0x18001dfb7  test    eax, eax
0x18001dfb9  jle     short loc_18001DFC6
0x18001dfbb  movzx   edi, ax
0x18001dfbe  or      edi, 80070000h
0x18001dfc4  mov     eax, edi
0x18001dfc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfcd  cmp     rcx, r15
0x18001dfd0  jz      short loc_18001DFFB
0x18001dfd2  test    byte ptr [rcx+1Ch], 1
0x18001dfd6  jz      short loc_18001DFFB
0x18001dfd8  mov     rcx, [rcx+10h]
0x18001dfdc  lea     r9, aCssdpnotifyreq; "CSsdpNotifyRequest::HrSendPropChangeSub"...
0x18001dfe3  mov     edx, 0A6h
0x18001dfe8  mov     dword ptr [rsp+78h+var_58], eax
0x18001dfec  mov     r8, r12
0x18001dfef  call    WPP_SF_sd
0x18001dff4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dffb  test    edi, edi
0x18001dffd  js      short loc_18001E004
0x18001dfff  mov     [r14], rsi
0x18001e002  jmp     short loc_18001E011
0x18001e004  test    rsi, rsi
0x18001e007  jz      short loc_18001E01C
0x18001e009  mov     rcx, rsi; void *
0x18001e00c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e011  test    edi, edi
0x18001e013  jz      short loc_18001E03F
0x18001e015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e01c  cmp     rcx, r15
0x18001e01f  jz      short loc_18001E03F
0x18001e021  test    byte ptr [rcx+1Ch], 1
0x18001e025  jz      short loc_18001E03F
0x18001e027  mov     rcx, [rcx+10h]
0x18001e02b  mov     edx, 0A7h
0x18001e030  mov     r9d, edi
0x18001e033  mov     dword ptr [rsp+78h+var_58], edi
0x18001e037  mov     r8, r12
0x18001e03a  call    WPP_SF_Dd
0x18001e03f  mov     eax, edi
0x18001e041  add     rsp, 40h
0x18001e045  pop     r15
0x18001e047  pop     r14
0x18001e049  pop     r12
0x18001e04b  pop     rdi
0x18001e04c  pop     rsi
0x18001e04d  pop     rbp
0x18001e04e  pop     rbx
0x18001e04f  retn
```
