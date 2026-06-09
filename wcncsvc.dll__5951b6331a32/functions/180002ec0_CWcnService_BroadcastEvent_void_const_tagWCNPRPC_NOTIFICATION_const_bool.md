# CWcnService::BroadcastEvent(void const *,tagWCNPRPC_NOTIFICATION const *,bool)

- ea: `0x180002ec0`
- end: `0x18000303d`
- name: `?BroadcastEvent@CWcnService@@QEAAXPEBXPEBUtagWCNPRPC_NOTIFICATION@@_N@Z`
- size: `381`
- prototype: `void __fastcall(CWcnService *this, const void *, const struct tagWCNPRPC_NOTIFICATION *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000f184`
- `0x180015db4`

## callees

- `0x180002ec0`
- `0x180004fb8`
- `0x180005014`
- `0x18003a250`
- `0x18003cad0`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fce`

## pseudocode

```c
void __fastcall CWcnService::BroadcastEvent(
        CWcnService *this,
        const void *a2,
        const struct tagWCNPRPC_NOTIFICATION *a3,
        char a4)
{
  __int64 v4; // rsi
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 *v11; // rcx
  __int64 *v12; // rbx
  __int64 *v13; // rax
  CWcnEventSink *v14; // r8
  __int64 *i; // rax
  __int64 *v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // r10

  v4 = *((_QWORD *)this + 7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 19, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 1360));
  v11 = *(__int64 **)(v4 + 1328);
  v12 = v11;
  v13 = (__int64 *)v11[1];
  if ( *((_BYTE *)v13 + 25) )
    goto LABEL_11;
  do
  {
    if ( v13[4] >= (unsigned __int64)a2 )
    {
      v12 = v13;
      v13 = (__int64 *)*v13;
    }
    else
    {
      v13 = (__int64 *)v13[2];
    }
  }
  while ( !*((_BYTE *)v13 + 25) );
  if ( v12 == v11 || (unsigned __int64)a2 < v12[4] )
LABEL_11:
    v12 = *(__int64 **)(v4 + 1328);
  while ( v12 != *(__int64 **)(v4 + 1328) && (const void *)v12[4] == a2 )
  {
    v14 = (CWcnEventSink *)v12[5];
    if ( *((_BYTE *)v12 + 25) )
      goto LABEL_24;
    i = (__int64 *)v12[2];
    if ( *((_BYTE *)i + 25) )
    {
      for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v12 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v12 = i;
LABEL_23:
      v12 = i;
      goto LABEL_24;
    }
    v16 = (__int64 *)*i;
    if ( *(_BYTE *)(*i + 25) )
      goto LABEL_23;
    do
    {
      v12 = v16;
      v16 = (__int64 *)*v16;
    }
    while ( !*((_BYTE *)v16 + 25) );
LABEL_24:
    CWcnEventSink::QueueNotification(v14, a3);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 1360));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v17 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v18 + 16), 20, (unsigned int)WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, v17, 0);
  }
  if ( a4 )
    CWcnEventManager::DeleteEventSource((CWcnEventManager *)(*((_QWORD *)this + 7) + 1312LL), a2);
}

```

## disassembly

```asm
0x180002ec0  push    rbx
0x180002ec2  push    rbp
0x180002ec3  push    rsi
0x180002ec4  push    rdi
0x180002ec5  push    r12
0x180002ec7  push    r14
0x180002ec9  push    r15
0x180002ecb  sub     rsp, 30h
0x180002ecf  mov     rsi, [rcx+38h]
0x180002ed3  mov     r15b, r9b
0x180002ed6  mov     r12, r8
0x180002ed9  mov     rdi, rdx
0x180002edc  mov     rbp, rcx
0x180002edf  mov     r10, cs:WPP_GLOBAL_Control
0x180002ee6  lea     rax, WPP_GLOBAL_Control
0x180002eed  cmp     r10, rax
0x180002ef0  jz      short loc_180002F1B
0x180002ef2  cmp     byte ptr [r10+19h], 6
0x180002ef7  jb      short loc_180002F1B
0x180002ef9  mov     ecx, 1; int
0x180002efe  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180002f03  mov     rcx, [r10+10h]
0x180002f07  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x180002f0e  mov     edx, 13h
0x180002f13  mov     r9, rax
0x180002f16  call    WPP_SF_s
0x180002f1b  lea     r14, [rsi+550h]
0x180002f22  mov     rcx, r14; lpCriticalSection
0x180002f25  call    cs:__imp_EnterCriticalSection
0x180002f2b  mov     rcx, [rsi+530h]
0x180002f32  mov     rbx, rcx
0x180002f35  mov     rax, [rcx+8]
0x180002f39  cmp     byte ptr [rax+19h], 0
0x180002f3d  jnz     short loc_180002F62
0x180002f3f  cmp     [rax+20h], rdi
0x180002f43  jnb     short loc_180002F4B
0x180002f45  mov     rax, [rax+10h]
0x180002f49  jmp     short loc_180002F51
0x180002f4b  mov     rbx, rax
0x180002f4e  mov     rax, [rax]
0x180002f51  cmp     byte ptr [rax+19h], 0
0x180002f55  jz      short loc_180002F3F
0x180002f57  cmp     rbx, rcx
0x180002f5a  jz      short loc_180002F62
0x180002f5c  cmp     rdi, [rbx+20h]
0x180002f60  jnb     short loc_180002F65
0x180002f62  mov     rbx, rcx
0x180002f65  cmp     rbx, [rsi+530h]
0x180002f6c  jz      short loc_180002FCB
0x180002f6e  cmp     [rbx+20h], rdi
0x180002f72  jnz     short loc_180002FCB
0x180002f74  cmp     byte ptr [rbx+19h], 0
0x180002f78  mov     r8, [rbx+28h]
0x180002f7c  jnz     short loc_180002FBE
0x180002f7e  mov     rax, [rbx+10h]
0x180002f82  cmp     byte ptr [rax+19h], 0
0x180002f86  jnz     short loc_180002FA2
0x180002f88  mov     rcx, [rax]
0x180002f8b  cmp     byte ptr [rcx+19h], 0
0x180002f8f  jnz     short loc_180002FBB
0x180002f91  mov     rax, [rcx]
0x180002f94  mov     rbx, rcx
0x180002f97  mov     rcx, rax
0x180002f9a  cmp     byte ptr [rax+19h], 0
0x180002f9e  jz      short loc_180002F91
0x180002fa0  jmp     short loc_180002FBE
0x180002fa2  mov     rax, [rbx+8]
0x180002fa6  jmp     short loc_180002FB5
0x180002fa8  cmp     rbx, [rax+10h]
0x180002fac  jnz     short loc_180002FBB
0x180002fae  mov     rbx, rax
0x180002fb1  mov     rax, [rax+8]
0x180002fb5  cmp     byte ptr [rax+19h], 0
0x180002fb9  jz      short loc_180002FA8
0x180002fbb  mov     rbx, rax
0x180002fbe  mov     rdx, r12; struct tagWCNPRPC_NOTIFICATION *
0x180002fc1  mov     rcx, r8; this
0x180002fc4  call    ?QueueNotification@CWcnEventSink@@QEAAJPEBUtagWCNPRPC_NOTIFICATION@@@Z; CWcnEventSink::QueueNotification(tagWCNPRPC_NOTIFICATION const *)
0x180002fc9  jmp     short loc_180002F65
0x180002fcb  mov     rcx, r14; lpCriticalSection
0x180002fce  call    cs:__imp_LeaveCriticalSection
0x180002fd4  mov     r10, cs:WPP_GLOBAL_Control
0x180002fdb  lea     rax, WPP_GLOBAL_Control
0x180002fe2  cmp     r10, rax
0x180002fe5  jz      short loc_180003016
0x180002fe7  cmp     byte ptr [r10+19h], 6
0x180002fec  jb      short loc_180003016
0x180002fee  or      ecx, 0FFFFFFFFh; int
0x180002ff1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180002ff6  mov     rcx, [r10+10h]
0x180002ffa  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x180003001  mov     edx, 14h
0x180003006  mov     [rsp+68h+var_48], 0
0x18000300e  mov     r9, rax
0x180003011  call    WPP_SF_sd
0x180003016  test    r15b, r15b
0x180003019  jz      short loc_18000302E
0x18000301b  mov     rcx, [rbp+38h]
0x18000301f  mov     rdx, rdi; void *
0x180003022  add     rcx, 520h; this
0x180003029  call    ?DeleteEventSource@CWcnEventManager@@QEAAXPEBX@Z; CWcnEventManager::DeleteEventSource(void const *)
0x18000302e  add     rsp, 30h
0x180003032  pop     r15
0x180003034  pop     r14
0x180003036  pop     r12
0x180003038  pop     rdi
0x180003039  pop     rsi
0x18000303a  pop     rbp
0x18000303b  pop     rbx
0x18000303c  retn
```
