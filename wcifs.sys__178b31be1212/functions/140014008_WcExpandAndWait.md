# WcExpandAndWait

- ea: `0x140014008`
- end: `0x140014143`
- name: `WcExpandAndWait`
- size: `315`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PVOID FltObject, PVOID Object, __int64, int, int)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140003930`
- `0x140018e28`
- `0x140023890`
- `0x140026e30`
- `0x140028820`
- `0x14002898c`
- `0x14002ef90`

## callees

- `0x140001ffc`
- `0x1400053f8`
- `0x140014008`
- `0x140018970`

## import_xrefs

- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140014085`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140014085`

## pseudocode

```c
__int64 __fastcall WcExpandAndWait(
        PFLT_CALLBACK_DATA CallbackData,
        PVOID FltObject,
        PVOID Object,
        __int64 a4,
        int a5,
        int a6)
{
  int v11; // ebx
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // edx

  if ( (unsigned __int8)WcIsExpanded(a4) )
    return 0;
  v11 = WcLaunchExpansion(FltObject, Object, a5, a6);
  if ( v11 >= 0 )
  {
    v12 = FltCancellableWaitForSingleObject((PVOID)(*(_QWORD *)(a4 + 80) + 8LL), 0, CallbackData);
    v11 = v12;
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_sDqd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v13,
        10,
        22,
        (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
        60,
        (char)Object,
        v12);
    }
  }
  if ( (unsigned __int8)WcIsExpanded(a4) )
  {
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_sDqd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v14,
        10,
        23,
        (__int64)WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\expansion.c",
        73,
        (char)Object,
        v11);
    }
    if ( v11 >= 0 )
      return (unsigned int)-1073741823;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140014008  push    rbx
0x14001400a  push    rbp
0x14001400b  push    rsi
0x14001400c  push    rdi
0x14001400d  push    r12
0x14001400f  push    r13
0x140014011  push    r14
0x140014013  sub     rsp, 50h
0x140014017  mov     rbp, rcx
0x14001401a  mov     rdi, r9
0x14001401d  mov     rcx, r9
0x140014020  mov     rsi, r8
0x140014023  mov     rbx, rdx
0x140014026  call    WcIsExpanded
0x14001402b  test    al, al
0x14001402d  jz      short loc_140014036
0x14001402f  xor     eax, eax
0x140014031  jmp     loc_140014133
0x140014036  mov     eax, [rsp+88h+arg_28]
0x14001403d  xor     r9d, r9d
0x140014040  mov     [rsp+88h+var_60], eax; int
0x140014044  mov     r8, rdi
0x140014047  mov     eax, [rsp+88h+arg_20]
0x14001404e  mov     rdx, rsi; Object
0x140014051  mov     rcx, rbx; FltObject
0x140014054  mov     [rsp+88h+var_68], eax; int
0x140014058  call    WcLaunchExpansion
0x14001405d  lea     r12, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\wcifs\\expansio"...
0x140014064  mov     ebx, eax
0x140014066  lea     r13, WPP_c8ed118f3d633d749a651abfa78156c7_Traceguids
0x14001406d  lea     r14, WPP_RECORDER_INITIALIZED
0x140014074  test    eax, eax
0x140014076  js      short loc_1400140D7
0x140014078  mov     rcx, [rdi+50h]
0x14001407c  mov     r8, rbp; CallbackData
0x14001407f  add     rcx, 8; Object
0x140014083  xor     edx, edx; Timeout
0x140014085  call    cs:__imp_FltCancellableWaitForSingleObject
0x14001408c  nop     dword ptr [rax+rax+00h]
0x140014091  mov     ebx, eax
0x140014093  test    eax, eax
0x140014095  jns     short loc_1400140D7
0x140014097  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001409e  jz      short loc_1400140D7
0x1400140a0  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400140a7  mov     r9d, 16h
0x1400140ad  mov     [rsp+88h+var_48], eax
0x1400140b1  mov     dl, 4
0x1400140b3  mov     [rsp+88h+var_50], rsi
0x1400140b8  mov     [rsp+88h+var_58], 63Ch
0x1400140c0  mov     rcx, [rcx+40h]
0x1400140c4  lea     r8d, [r9-0Ch]
0x1400140c8  mov     qword ptr [rsp+88h+var_60], r12
0x1400140cd  mov     qword ptr [rsp+88h+var_68], r13
0x1400140d2  call    WPP_RECORDER_SF_sDqd
0x1400140d7  mov     rcx, rdi
0x1400140da  call    WcIsExpanded
0x1400140df  test    al, al
0x1400140e1  jz      short loc_1400140E7
0x1400140e3  xor     ebx, ebx
0x1400140e5  jmp     short loc_140014131
0x1400140e7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400140ee  jz      short loc_140014127
0x1400140f0  mov     rcx, cs:wil_details_featureDescriptors_a
0x1400140f7  mov     r9d, 17h
0x1400140fd  mov     [rsp+88h+var_48], ebx
0x140014101  mov     dl, 2
0x140014103  mov     [rsp+88h+var_50], rsi
0x140014108  mov     [rsp+88h+var_58], 649h
0x140014110  mov     rcx, [rcx+40h]
0x140014114  lea     r8d, [r9-0Dh]
0x140014118  mov     qword ptr [rsp+88h+var_60], r12
0x14001411d  mov     qword ptr [rsp+88h+var_68], r13
0x140014122  call    WPP_RECORDER_SF_sDqd
0x140014127  test    ebx, ebx
0x140014129  mov     eax, 0C0000001h
0x14001412e  cmovns  ebx, eax
0x140014131  mov     eax, ebx
0x140014133  add     rsp, 50h
0x140014137  pop     r14
0x140014139  pop     r13
0x14001413b  pop     r12
0x14001413d  pop     rdi
0x14001413e  pop     rsi
0x14001413f  pop     rbp
0x140014140  pop     rbx
0x140014141  retn
```
