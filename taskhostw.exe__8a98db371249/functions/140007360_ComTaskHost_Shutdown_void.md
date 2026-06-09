# ComTaskHost::Shutdown(void)

- ea: `0x140007360`
- end: `0x1400073e6`
- name: `?Shutdown@ComTaskHost@@QEAAJXZ`
- size: `134`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003b10`

## callees

- `0x140004ec0`
- `0x1400050c0`
- `0x140007360`
- `0x140009370`

## pseudocode

```c
__int64 __fastcall ComTaskHost::Shutdown(ComTaskHost *this)
{
  signed __int32 v2; // eax
  unsigned int v3; // edi
  bool v4; // zf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this);
  v2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 9, 1);
  if ( v2 == 1 )
  {
    v3 = ComTaskHost::StopTaskWorker(this);
    v4 = v3 == -2147009395;
  }
  else
  {
    v3 = 0;
    if ( v2 == 4 )
    {
LABEL_9:
      ComTaskHost::ReleaseLifetimeRef(this, L"Shutdown");
      return v3;
    }
    v4 = v2 == 7;
  }
  if ( v4 )
    goto LABEL_9;
  return v3;
}

```

## disassembly

```asm
0x140007360  mov     [rsp+arg_0], rbx
0x140007365  push    rdi
0x140007366  sub     rsp, 20h
0x14000736a  mov     rbx, rcx
0x14000736d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007374  lea     rax, WPP_GLOBAL_Control
0x14000737b  cmp     rcx, rax
0x14000737e  jz      short loc_14000739E
0x140007380  test    byte ptr [rcx+1Ch], 4
0x140007384  jz      short loc_14000739E
0x140007386  mov     rcx, [rcx+10h]
0x14000738a  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140007391  mov     edx, 17h
0x140007396  mov     r9, rbx
0x140007399  call    WPP_SF_q
0x14000739e  mov     ecx, 9
0x1400073a3  lea     eax, [rcx-8]
0x1400073a6  lock cmpxchg [rbx+10h], ecx
0x1400073ab  jnz     short loc_1400073BE
0x1400073ad  mov     rcx, rbx; this
0x1400073b0  call    ?StopTaskWorker@ComTaskHost@@AEAAJXZ; ComTaskHost::StopTaskWorker(void)
0x1400073b5  mov     edi, eax
0x1400073b7  cmp     eax, 80073C8Dh
0x1400073bc  jmp     short loc_1400073C8
0x1400073be  xor     edi, edi
0x1400073c0  cmp     eax, 4
0x1400073c3  jz      short loc_1400073CA
0x1400073c5  cmp     eax, 7
0x1400073c8  jnz     short loc_1400073D9
0x1400073ca  lea     rdx, aShutdown; "Shutdown"
0x1400073d1  mov     rcx, rbx; this
0x1400073d4  call    ?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z; ComTaskHost::ReleaseLifetimeRef(ushort const *)
0x1400073d9  mov     rbx, [rsp+28h+arg_0]
0x1400073de  mov     eax, edi
0x1400073e0  add     rsp, 20h
0x1400073e4  pop     rdi
0x1400073e5  retn
```
