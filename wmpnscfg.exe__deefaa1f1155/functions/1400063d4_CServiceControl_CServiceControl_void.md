# CServiceControl::~CServiceControl(void)

- ea: `0x1400063d4`
- end: `0x14000646c`
- name: `??1CServiceControl@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(CServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140005658`

## callees

- `0x1400053b4`
- `0x1400063d4`
- `0x140006474`
- `0x140008010`

## pseudocode

```c
void __fastcall CServiceControl::~CServiceControl(CServiceControl *this)
{
  volatile signed __int32 *v2; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  CServiceControl::CloseServiceManager(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  v2 = (volatile signed __int32 *)(*(_QWORD *)this - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
}

```

## disassembly

```asm
0x1400063d4  mov     [rsp+arg_0], rbx
0x1400063d9  push    rdi
0x1400063da  sub     rsp, 20h
0x1400063de  mov     rbx, rcx
0x1400063e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063e8  lea     rdi, WPP_GLOBAL_Control
0x1400063ef  cmp     rcx, rdi
0x1400063f2  jz      short loc_14000640F
0x1400063f4  test    byte ptr [rcx+1Ch], 1
0x1400063f8  jz      short loc_14000640F
0x1400063fa  mov     rcx, [rcx+10h]
0x1400063fe  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140006405  mov     edx, 0Dh
0x14000640a  call    WPP_SF_
0x14000640f  mov     rcx, rbx; this
0x140006412  call    ?CloseServiceManager@CServiceControl@@AEAAXXZ; CServiceControl::CloseServiceManager(void)
0x140006417  mov     rcx, cs:WPP_GLOBAL_Control
0x14000641e  cmp     rcx, rdi
0x140006421  jz      short loc_14000643E
0x140006423  test    byte ptr [rcx+1Ch], 1
0x140006427  jz      short loc_14000643E
0x140006429  mov     rcx, [rcx+10h]
0x14000642d  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140006434  mov     edx, 0Eh
0x140006439  call    WPP_SF_
0x14000643e  mov     rdx, [rbx]
0x140006441  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006445  or      eax, 0FFFFFFFFh
0x140006448  lock xadd [rdx+10h], eax
0x14000644d  sub     eax, 1
0x140006450  jg      short loc_140006461
0x140006452  mov     rcx, [rdx]
0x140006455  mov     rax, [rcx]
0x140006458  mov     rax, [rax+8]
0x14000645c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006461  mov     rbx, [rsp+28h+arg_0]
0x140006466  add     rsp, 20h
0x14000646a  pop     rdi
0x14000646b  retn
```
