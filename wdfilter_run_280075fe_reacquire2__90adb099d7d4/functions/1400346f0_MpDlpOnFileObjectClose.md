# MpDlpOnFileObjectClose

- ea: `0x1400346f0`
- end: `0x140034b48`
- name: `MpDlpOnFileObjectClose`
- size: `1112`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140032780`
- `0x14005f510`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x140003950`
- `0x140003d20`
- `0x1400051bc`
- `0x1400118d0`
- `0x140011900`
- `0x1400346f0`
- `0x140034b50`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x140034818`
- `ntoskrnl!KeQueryPriorityThread` at `0x140034818`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034920`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034920`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x1400347f4`
- `FLTMGR!FltRetrieveIoPriorityInfo` at `0x1400347f4`

## pseudocode

```c
void __fastcall MpDlpOnFileObjectClose(__int64 a1, const void **a2, __int64 a3, int a4, char a5, int a6)
{
  unsigned int v9; // r15d
  __int64 PoolWithTag; // rax
  __int64 v11; // r14
  NTSTATUS v12; // eax
  KPRIORITY PriorityThread; // eax
  IO_PRIORITY_HINT IoPriority; // ecx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // ecx
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+30h] [rbp-58h] BYREF

  if ( *(_WORD *)a2 && a2[1] )
  {
    if ( a1 && a4 == 1 )
    {
      if ( *(_BYTE *)(a1 + 196) )
        __debugbreak();
      if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 192)) < 0 )
      {
        _mm_lfence();
        _InterlockedExchange((volatile __int32 *)(a1 + 192), 0);
      }
    }
    v9 = *(unsigned __int16 *)a2 + 66;
    if ( v9 < 0x18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
          KeGetCurrentThread());
      v17 = -1073741811;
    }
    else
    {
      _mm_lfence();
      PoolWithTag = MpAllocatePoolWithTag(1, (unsigned int)*(unsigned __int16 *)a2 + 90, 1835094093);
      v11 = PoolWithTag;
      if ( PoolWithTag )
      {
        *(_WORD *)PoolWithTag = 421;
        *(_DWORD *)(PoolWithTag + 4) = v9 + 24;
        PriorityInfo.Size = 16;
        *(_WORD *)(PoolWithTag + 2) = 2;
        *(_OWORD *)(PoolWithTag + 8) = 0;
        *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
        PriorityInfo.IoPriority = IoPriorityNormal;
        v12 = FltRetrieveIoPriorityInfo(0, 0, KeGetCurrentThread(), &PriorityInfo);
        if ( v12 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
            (unsigned int)v12);
        }
        PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
        IoPriority = PriorityInfo.IoPriority;
        *(_DWORD *)(v11 + 12) = PriorityThread;
        *(_DWORD *)(v11 + 16) = PriorityInfo.PagePriority;
        *(_DWORD *)(v11 + 8) = IoPriority;
        *(_DWORD *)(v11 + 36) = 1;
        *(_DWORD *)(v11 + 40) = 19;
        *(_DWORD *)(v11 + 32) = v9;
        *(_QWORD *)&PriorityInfo.Size = v11 + 36;
        if ( a1 )
        {
          *(_DWORD *)(v11 + 48) = *(_DWORD *)(a1 + 24);
          v15 = *(_QWORD *)(a1 + 32);
        }
        else
        {
          *(_DWORD *)(v11 + 48) = 0;
          v15 = 0;
          *(_QWORD *)&PriorityInfo.Size = v11 + 36;
        }
        *(_QWORD *)(v11 + 52) = MpFileTimeToUlong64(v15);
        *(_QWORD *)(v11 + 64) = 64;
        *(_DWORD *)(v11 + 72) = *(unsigned __int16 *)a2 + 2;
        *(_DWORD *)(v11 + 60) = a4;
        *(_BYTE *)(v11 + 80) = a5;
        *(_DWORD *)(v11 + 76) = a6;
        memmove((void *)(v11 + 88), a2[1], *(unsigned __int16 *)a2);
        *(_WORD *)(v11 + 24 + 2 * ((unsigned __int64)*(unsigned __int16 *)a2 >> 1) + *(_QWORD *)(v11 + 64)) = 0;
        v16 = MpAsyncSendNotification(v11 + 24, v9, 0, (unsigned int)(*(_QWORD *)(MpData + 432) != 0) + 1, 0);
        if ( v16 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            70,
            WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
            KeGetCurrentThread(),
            v16);
        }
        if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)&PriorityInfo.Size, 0xFFFFFFFF) == 1 )
          ExFreePoolWithTag((PVOID)v11, 0x6D61504Du);
        return;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
          KeGetCurrentThread());
      v17 = -1073741670;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        69,
        WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
        KeGetCurrentThread(),
        v17);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      68,
      WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
      KeGetCurrentThread());
  }
}

```

## disassembly

```asm
0x1400346f0  push    rbx
0x1400346f2  push    rbp
0x1400346f3  push    rsi
0x1400346f4  push    r13
0x1400346f6  sub     rsp, 68h
0x1400346fa  mov     rax, cs:__security_cookie
0x140034701  xor     rax, rsp
0x140034704  mov     [rsp+88h+var_48], rax
0x140034709  xor     r13d, r13d
0x14003470c  mov     ebp, r9d
0x14003470f  mov     rsi, rdx
0x140034712  mov     rbx, rcx
0x140034715  cmp     r13w, [rdx]
0x140034719  jz      loc_140034AFC
0x14003471f  cmp     [rdx+8], r13
0x140034723  jz      loc_140034AFC
0x140034729  mov     [rsp+88h+var_38], r15
0x14003472e  mov     [rsp+88h+arg_10], rdi
0x140034736  test    rcx, rcx
0x140034739  jz      loc_1400349E4
0x14003473f  cmp     r9d, 1
0x140034743  jnz     loc_1400349E4
0x140034749  movzx   eax, byte ptr [rcx+0C4h]
0x140034750  test    al, al
0x140034752  jnz     loc_1400349CD
0x140034758  mov     edi, 0FFFFFFFFh
0x14003475d  mov     eax, edi
0x14003475f  lock xadd [rcx+0C0h], eax
0x140034767  cmp     eax, 1
0x14003476a  js      loc_1400349D3
0x140034770  movzx   r15d, word ptr [rdx]
0x140034774  add     r15d, 42h ; 'B'
0x140034778  mov     [rsp+88h+var_28], r12
0x14003477d  mov     [rsp+88h+var_30], r14
0x140034782  cmp     r15d, 18h
0x140034786  jb      loc_14003496D
0x14003478c  lfence
0x14003478f  lea     r12d, [r15+18h]
0x140034793  mov     ecx, 1
0x140034798  mov     edx, r12d
0x14003479b  mov     r8d, 6D61504Dh
0x1400347a1  call    MpAllocatePoolWithTag
0x1400347a6  mov     r14, rax
0x1400347a9  test    rax, rax
0x1400347ac  jz      loc_1400349EE
0x1400347b2  mov     word ptr [rax], 1A5h
0x1400347b7  lea     r9, [rsp+88h+PriorityInfo]; PriorityInfo
0x1400347bc  mov     [rax+4], r12d
0x1400347c0  xorps   xmm0, xmm0
0x1400347c3  mov     eax, 2
0x1400347c8  mov     [rsp+88h+PriorityInfo.Size], 10h
0x1400347d0  mov     [r14+2], ax
0x1400347d5  xor     edx, edx; FileObject
0x1400347d7  movups  xmmword ptr [r14+8], xmm0
0x1400347dc  mov     qword ptr [rsp+88h+PriorityInfo.ThreadPriority], 0FFFFh
0x1400347e5  xor     ecx, ecx; Data
0x1400347e7  mov     [rsp+88h+PriorityInfo.IoPriority], eax
0x1400347eb  mov     r8, gs:188h; Thread
0x1400347f4  call    cs:__imp_FltRetrieveIoPriorityInfo
0x1400347fb  nop     dword ptr [rax+rax+00h]
0x140034800  lea     r13, WPP_GLOBAL_Control
0x140034807  test    eax, eax
0x140034809  js      loc_140034A37
0x14003480f  mov     rcx, gs:188h; Thread
0x140034818  call    cs:__imp_KeQueryPriorityThread
0x14003481f  nop     dword ptr [rax+rax+00h]
0x140034824  mov     ecx, [rsp+88h+PriorityInfo.IoPriority]
0x140034828  lea     r12, [r14+18h]
0x14003482c  mov     [r14+0Ch], eax
0x140034830  mov     [rsp+88h+PriorityInfo.ThreadPriority], eax
0x140034834  mov     eax, [rsp+88h+PriorityInfo.PagePriority]
0x140034838  mov     [r14+10h], eax
0x14003483c  lea     rax, [r14+24h]
0x140034840  mov     [r14+8], ecx
0x140034844  mov     dword ptr [rax], 1
0x14003484a  mov     dword ptr [r12+10h], 13h
0x140034853  mov     [r12+8], r15d
0x140034858  mov     qword ptr [rsp+88h+PriorityInfo.Size], rax
0x14003485d  test    rbx, rbx
0x140034860  jz      loc_14003495B
0x140034866  mov     eax, [rbx+18h]
0x140034869  mov     [r12+18h], eax
0x14003486e  mov     rcx, [rbx+20h]
0x140034872  xor     ebx, ebx
0x140034874  call    MpFileTimeToUlong64
0x140034879  mov     [r12+1Ch], rax
0x14003487e  lea     rcx, [r12+40h]; void *
0x140034883  mov     qword ptr [r12+28h], 40h ; '@'
0x14003488c  movzx   eax, word ptr [rsi]
0x14003488f  add     eax, 2
0x140034892  mov     [r12+30h], eax
0x140034897  movzx   eax, [rsp+88h+arg_20]
0x14003489f  mov     [r12+24h], ebp
0x1400348a4  mov     [r12+38h], al
0x1400348a9  mov     eax, [rsp+88h+arg_28]
0x1400348b0  mov     [r12+34h], eax
0x1400348b5  movzx   r8d, word ptr [rsi]; Size
0x1400348b9  mov     rdx, [rsi+8]; Src
0x1400348bd  call    memmove
0x1400348c2  movzx   eax, word ptr [rsi]
0x1400348c5  mov     r9d, ebx
0x1400348c8  shr     rax, 1
0x1400348cb  mov     edx, r15d
0x1400348ce  mov     rcx, r12
0x1400348d1  mov     [rsp+88h+var_68], rbx
0x1400348d6  lea     r8, [r12+rax*2]
0x1400348da  mov     rax, [r12+28h]
0x1400348df  mov     [r8+rax], bx
0x1400348e4  mov     rax, cs:MpData
0x1400348eb  cmp     qword ptr [rax+1B0h], 0
0x1400348f3  setnz   r9b
0x1400348f7  xor     r8d, r8d
0x1400348fa  inc     r9d
0x1400348fd  call    MpAsyncSendNotification
0x140034902  test    eax, eax
0x140034904  js      loc_140034A7A
0x14003490a  mov     rax, qword ptr [rsp+88h+PriorityInfo.Size]
0x14003490f  lock xadd [rax], edi
0x140034913  cmp     edi, 1
0x140034916  jnz     short loc_14003492C
0x140034918  mov     edx, 6D61504Dh; Tag
0x14003491d  mov     rcx, r14; P
0x140034920  call    cs:__imp_ExFreePoolWithTag
0x140034927  nop     dword ptr [rax+rax+00h]
0x14003492c  mov     r14, [rsp+88h+var_30]
0x140034931  mov     r12, [rsp+88h+var_28]
0x140034936  mov     rdi, [rsp+88h+arg_10]
0x14003493e  mov     r15, [rsp+88h+var_38]
0x140034943  mov     rcx, [rsp+88h+var_48]
0x140034948  xor     rcx, rsp; StackCookie
0x14003494b  call    __security_check_cookie
0x140034950  add     rsp, 68h
0x140034954  pop     r13
0x140034956  pop     rsi
0x140034957  pop     rbp
0x140034958  pop     rbx
0x140034959  retn
0x14003495b  mov     [r12+18h], ebx
0x140034960  mov     rcx, rbx
0x140034963  mov     qword ptr [rsp+88h+PriorityInfo.Size], rax
0x140034968  jmp     loc_140034874
0x14003496d  mov     rax, cs:WPP_GLOBAL_Control
0x140034974  lea     r13, WPP_GLOBAL_Control
0x14003497b  cmp     rax, r13
0x14003497e  jnz     loc_140034AC7
0x140034984  mov     ecx, 0C000000Dh
0x140034989  mov     rax, cs:WPP_GLOBAL_Control
0x140034990  cmp     rax, r13
0x140034993  jz      short loc_14003492C
0x140034995  mov     eax, [rax+2Ch]
0x140034998  test    al, 1
0x14003499a  jz      short loc_14003492C
0x14003499c  lfence
0x14003499f  mov     r9, gs:188h
0x1400349a8  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x1400349af  mov     dword ptr [rsp+88h+var_68], ecx
0x1400349b3  mov     edx, 45h ; 'E'
0x1400349b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400349bf  mov     rcx, [rcx+18h]
0x1400349c3  call    WPP_SF_qD
0x1400349c8  jmp     loc_14003492C
0x1400349cd  int     3; Trap to Debugger
0x1400349ce  jmp     loc_140034758
0x1400349d3  lfence
0x1400349d6  mov     eax, r13d
0x1400349d9  xchg    eax, [rcx+0C0h]
0x1400349df  jmp     loc_140034770
0x1400349e4  mov     edi, 0FFFFFFFFh
0x1400349e9  jmp     loc_140034770
0x1400349ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400349f5  lea     r13, WPP_GLOBAL_Control
0x1400349fc  cmp     rax, r13
0x1400349ff  jz      short loc_140034A2D
0x140034a01  mov     eax, [rax+2Ch]
0x140034a04  test    al, 1
0x140034a06  jz      short loc_140034A2D
0x140034a08  mov     r9, gs:188h
0x140034a11  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140034a18  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a1f  mov     edx, 1Bh
0x140034a24  mov     rcx, [rcx+18h]
0x140034a28  call    WPP_SF_q
0x140034a2d  mov     ecx, 0C000009Ah
0x140034a32  jmp     loc_140034989
0x140034a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a3e  cmp     rcx, r13
0x140034a41  jz      loc_14003480F
0x140034a47  mov     ecx, [rcx+2Ch]
0x140034a4a  test    cl, 1
0x140034a4d  jz      loc_14003480F
0x140034a53  lfence
0x140034a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a5d  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140034a64  mov     edx, 21h ; '!'
0x140034a69  mov     r9d, eax
0x140034a6c  mov     rcx, [rcx+18h]
0x140034a70  call    WPP_SF_d
0x140034a75  jmp     loc_14003480F
0x140034a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a81  cmp     rcx, r13
0x140034a84  jz      loc_14003490A
0x140034a8a  mov     ecx, [rcx+2Ch]
0x140034a8d  test    cl, 1
0x140034a90  jz      loc_14003490A
0x140034a96  lfence
0x140034a99  mov     r9, gs:188h
0x140034aa2  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140034aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ab0  mov     edx, 46h ; 'F'
0x140034ab5  mov     dword ptr [rsp+88h+var_68], eax
0x140034ab9  mov     rcx, [rcx+18h]
0x140034abd  call    WPP_SF_qD
0x140034ac2  jmp     loc_14003490A
0x140034ac7  mov     eax, [rax+2Ch]
0x140034aca  test    al, 1
0x140034acc  jz      loc_140034984
0x140034ad2  mov     r9, gs:188h
0x140034adb  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140034ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ae9  mov     edx, 1Ah
0x140034aee  mov     rcx, [rcx+18h]
0x140034af2  call    WPP_SF_q
0x140034af7  jmp     loc_140034984
0x140034afc  mov     rax, cs:WPP_GLOBAL_Control
0x140034b03  lea     r13, WPP_GLOBAL_Control
0x140034b0a  cmp     rax, r13
0x140034b0d  jz      loc_140034943
0x140034b13  mov     eax, [rax+2Ch]
0x140034b16  test    al, 1
0x140034b18  jz      loc_140034943
0x140034b1e  mov     r9, gs:188h
0x140034b27  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x140034b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034b35  mov     edx, 44h ; 'D'
0x140034b3a  mov     rcx, [rcx+18h]
0x140034b3e  call    WPP_SF_q
0x140034b43  jmp     loc_140034943
```
