# TmpDispatchPropagateRequest

- ea: `0x14001904c`
- end: `0x14001932e`
- name: `TmpDispatchPropagateRequest`
- size: `738`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140018810`
- `0x140018b0c`
- `0x140018f20`

## callees

- `0x140002640`
- `0x14001904c`
- `0x1400193ac`
- `0x14001953c`
- `0x140019810`
- `0x14001c010`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140019079`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400191af`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019225`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019079`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400191af`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019225`
- `ntoskrnl!KeReleaseMutex` at `0x140019115`
- `ntoskrnl!KeReleaseMutex` at `0x1400191e5`
- `ntoskrnl!KeReleaseMutex` at `0x14001925c`
- `ntoskrnl!KeReleaseMutex` at `0x140019115`
- `ntoskrnl!KeReleaseMutex` at `0x1400191e5`
- `ntoskrnl!KeReleaseMutex` at `0x14001925c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400192d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400192d4`
- `ntoskrnl!ObfDereferenceObject` at `0x140019166`
- `ntoskrnl!ObfDereferenceObject` at `0x1400191f4`
- `ntoskrnl!ObfDereferenceObject` at `0x140019166`
- `ntoskrnl!ObfDereferenceObject` at `0x1400191f4`
- `ntoskrnl!ObfReferenceObject` at `0x140019100`
- `ntoskrnl!ObfReferenceObject` at `0x140019100`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001914f`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001914f`

## pseudocode

```c
__int64 __fastcall TmpDispatchPropagateRequest(_DWORD *P)
{
  char *v2; // rbp
  __int64 ProtocolHeader; // r13
  unsigned int v4; // r14d
  unsigned int v5; // esi
  struct _DEVICE_OBJECT *DeviceObject; // rcx
  PVOID *v7; // rdx
  PVOID *p_SystemArgument1; // rbx
  unsigned __int64 v9; // r8
  unsigned int v10; // r12d
  char *Src; // rbx
  _QWORD *v13; // r14
  __int64 v14; // r15
  _QWORD *v15; // rsi
  __int64 v16; // rdx
  _QWORD *v17; // rax
  PRKEVENT *v18; // r15
  PVOID *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  size_t v22; // r8
  __int64 v23; // rdx
  int v24; // esi
  __int64 v25; // rcx
  int v26; // r9d
  unsigned int v27; // ebx
  size_t Size; // [rsp+28h] [rbp-60h]

  v2 = 0;
  ProtocolHeader = 0;
  KeWaitForSingleObject(&WPP_MAIN_CB.DeviceExtension, Executive, 0, 0, 0);
  v4 = P[84];
  while ( 1 )
  {
    v5 = P[12];
    if ( v5 >= v4 )
      break;
    DeviceObject = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Queue.Wcb.DeviceObject;
    if ( WPP_MAIN_CB.Queue.Wcb.DeviceObject != &WPP_MAIN_CB.Queue.Wcb.DeviceObject )
    {
      v7 = (PVOID *)(*((_QWORD *)P + 43) + 16LL * v5);
      while ( 1 )
      {
        p_SystemArgument1 = &DeviceObject[-1].Dpc.SystemArgument1;
        v9 = (_BYTE *)*v7 - (char *)DeviceObject[-1].Dpc.SystemArgument2;
        if ( *v7 == DeviceObject[-1].Dpc.SystemArgument2 )
          v9 = (_BYTE *)v7[1] - (_BYTE *)p_SystemArgument1[2];
        if ( !v9 )
          break;
        DeviceObject = *(struct _DEVICE_OBJECT **)&DeviceObject->Type;
        if ( DeviceObject == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject )
          goto LABEL_12;
      }
      if ( DeviceObject != (struct _DEVICE_OBJECT *)96 )
      {
        ProtocolHeader = TmpFindProtocolHeader(p_SystemArgument1 + 1, (__int64)P);
        if ( ProtocolHeader )
        {
          v2 = (char *)p_SystemArgument1[14];
          ObfReferenceObject(v2);
          break;
        }
      }
    }
LABEL_12:
    P[12] = v5 + 1;
  }
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.DeviceExtension, 0);
  if ( P[12] == P[84] || !ProtocolHeader )
  {
    v26 = -1072103408;
    v25 = (__int64)P;
  }
  else
  {
    v10 = *(_DWORD *)(ProtocolHeader + 16) + 40;
    Src = (char *)ExAllocatePoolWithQuotaTag((POOL_TYPE)9, v10, 0x61506D54u);
    if ( !Src )
    {
      ObfDereferenceObject(v2);
      TmpSchedulePropagateRequest((char *)P);
      return 259;
    }
    v13 = P + 14;
    *((_DWORD *)Src + 9) = *(_DWORD *)(ProtocolHeader + 16);
    ++P[12];
    v14 = *((_QWORD *)P + 7);
    if ( v14 )
    {
      KeWaitForSingleObject((PVOID)(v14 + 40), Executive, 0, 0, 0);
      v15 = P + 4;
      v16 = *((_QWORD *)P + 2);
      if ( *(_DWORD **)(v16 + 8) != P + 4 || (v17 = (_QWORD *)*((_QWORD *)P + 3), (_QWORD *)*v17 != v15) )
LABEL_24:
        __fastfail(3u);
      *v17 = v16;
      *(_QWORD *)(v16 + 8) = v17;
      *v13 = 0;
      KeReleaseMutex((PRKMUTEX)(v14 + 40), 0);
      ObfDereferenceObject((PVOID)v14);
      v18 = (PRKEVENT *)(P + 14);
    }
    else
    {
      v15 = P + 4;
      v18 = (PRKEVENT *)(P + 14);
    }
    *v13 = v2;
    KeWaitForSingleObject(v2 + 40, Executive, 0, 0, 0);
    v19 = (PVOID *)*((_QWORD *)v2 + 42);
    if ( *v19 != v2 + 328 )
      goto LABEL_24;
    v15[1] = v19;
    *v15 = v2 + 328;
    *v19 = v15;
    *((_QWORD *)v2 + 42) = v15;
    KeReleaseMutex((PRKMUTEX)(v2 + 40), 0);
    v20 = *((_QWORD *)P + 8);
    if ( v20 )
    {
      *(_OWORD *)(Src + 4) = *(_OWORD *)(v20 + 176);
    }
    else
    {
      v21 = *((_QWORD *)P + 45);
      *(_OWORD *)(Src + 4) = *(_OWORD *)(v21 + 16);
      *(_OWORD *)(Src + 20) = *(_OWORD *)(v21 + 32);
    }
    v22 = *((unsigned int *)Src + 9);
    *(_DWORD *)Src = P[1];
    memmove(Src + 40, (const void *)(ProtocolHeader + 32), v22);
    LODWORD(Size) = v10;
    v24 = TmpSetNotificationResourceManager(*v18, v23, 0, 0, P[22], Size, Src);
    ExFreePoolWithTag(Src, 0);
    v25 = (__int64)P;
    if ( v24 >= 0 )
    {
      v27 = *((_BYTE *)P + 384) == 0 ? 0x103 : 0;
      TmpSchedulePropagateRequest((char *)P);
      return v27;
    }
    v26 = v24;
  }
  TmpPropagationComplete(v25, 0, 0, v26);
  return 0;
}

```

## disassembly

```asm
0x14001904c  push    rbx
0x14001904e  push    rbp
0x14001904f  push    rsi
0x140019050  push    rdi
0x140019051  push    r12
0x140019053  push    r13
0x140019055  push    r14
0x140019057  push    r15
0x140019059  sub     rsp, 48h
0x14001905d  mov     rdi, rcx
0x140019060  xor     ebp, ebp
0x140019062  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x140019069  mov     [rsp+88h+Timeout], rbp; Timeout
0x14001906e  xor     r13d, r13d
0x140019071  xor     r9d, r9d; Alertable
0x140019074  xor     r8d, r8d; WaitMode
0x140019077  xor     edx, edx; WaitReason
0x140019079  call    cs:__imp_KeWaitForSingleObject
0x140019080  nop     dword ptr [rax+rax+00h]
0x140019085  mov     r14d, [rdi+150h]
0x14001908c  lea     r15, WPP_MAIN_CB.Queue+30h
0x140019093  mov     esi, [rdi+30h]
0x140019096  cmp     esi, r14d
0x140019099  jnb     short loc_14001910C
0x14001909b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400190a2  cmp     rcx, r15
0x1400190a5  jz      short loc_1400190F1
0x1400190a7  mov     edx, esi
0x1400190a9  shl     rdx, 4
0x1400190ad  add     rdx, [rdi+158h]
0x1400190b4  mov     r8, [rdx]
0x1400190b7  lea     rbx, [rcx-60h]
0x1400190bb  sub     r8, [rbx+8]
0x1400190bf  jnz     short loc_1400190C9
0x1400190c1  mov     r8, [rdx+8]
0x1400190c5  sub     r8, [rbx+10h]
0x1400190c9  test    r8, r8
0x1400190cc  jz      short loc_1400190D8
0x1400190ce  mov     rcx, [rcx]
0x1400190d1  cmp     rcx, r15
0x1400190d4  jnz     short loc_1400190B4
0x1400190d6  jmp     short loc_1400190F1
0x1400190d8  test    rbx, rbx
0x1400190db  jz      short loc_1400190F1
0x1400190dd  mov     rdx, rdi
0x1400190e0  lea     rcx, [rbx+8]
0x1400190e4  call    TmpFindProtocolHeader
0x1400190e9  mov     r13, rax
0x1400190ec  test    rax, rax
0x1400190ef  jnz     short loc_1400190F9
0x1400190f1  lea     ecx, [rsi+1]
0x1400190f4  mov     [rdi+30h], ecx
0x1400190f7  jmp     short loc_140019093
0x1400190f9  mov     rbp, [rbx+70h]
0x1400190fd  mov     rcx, rbp; Object
0x140019100  call    cs:__imp_ObfReferenceObject
0x140019107  nop     dword ptr [rax+rax+00h]
0x14001910c  xor     edx, edx; Wait
0x14001910e  lea     rcx, WPP_MAIN_CB.DeviceExtension; Mutex
0x140019115  call    cs:__imp_KeReleaseMutex
0x14001911c  nop     dword ptr [rax+rax+00h]
0x140019121  mov     eax, [rdi+150h]
0x140019127  cmp     [rdi+30h], eax
0x14001912a  jz      loc_140019307
0x140019130  test    r13, r13
0x140019133  jz      loc_140019307
0x140019139  mov     r12d, [r13+10h]
0x14001913d  mov     ecx, 9; PoolType
0x140019142  add     r12d, 28h ; '('
0x140019146  mov     r8d, 61506D54h; Tag
0x14001914c  mov     edx, r12d; NumberOfBytes
0x14001914f  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140019156  nop     dword ptr [rax+rax+00h]
0x14001915b  mov     rbx, rax
0x14001915e  test    rax, rax
0x140019161  jnz     short loc_140019184
0x140019163  mov     rcx, rbp; Object
0x140019166  call    cs:__imp_ObfDereferenceObject
0x14001916d  nop     dword ptr [rax+rax+00h]
0x140019172  mov     rcx, rdi; P
0x140019175  call    TmpSchedulePropagateRequest
0x14001917a  mov     eax, 103h
0x14001917f  jmp     loc_14001931C
0x140019184  mov     eax, [r13+10h]
0x140019188  lea     r14, [rdi+38h]
0x14001918c  mov     [rbx+24h], eax
0x14001918f  inc     dword ptr [rdi+30h]
0x140019192  mov     r15, [r14]
0x140019195  test    r15, r15
0x140019198  jz      short loc_140019206
0x14001919a  xor     r9d, r9d; Alertable
0x14001919d  mov     [rsp+88h+Timeout], 0; Timeout
0x1400191a6  xor     r8d, r8d; WaitMode
0x1400191a9  lea     rcx, [r15+28h]; Object
0x1400191ad  xor     edx, edx; WaitReason
0x1400191af  call    cs:__imp_KeWaitForSingleObject
0x1400191b6  nop     dword ptr [rax+rax+00h]
0x1400191bb  lea     rsi, [rdi+10h]
0x1400191bf  mov     rdx, [rsi]
0x1400191c2  cmp     [rdx+8], rsi
0x1400191c6  jnz     short loc_140019241
0x1400191c8  mov     rax, [rsi+8]
0x1400191cc  cmp     [rax], rsi
0x1400191cf  jnz     short loc_140019241
0x1400191d1  mov     [rax], rdx
0x1400191d4  lea     rcx, [r15+28h]; Mutex
0x1400191d8  mov     [rdx+8], rax
0x1400191dc  xor     edx, edx; Wait
0x1400191de  mov     qword ptr [r14], 0
0x1400191e5  call    cs:__imp_KeReleaseMutex
0x1400191ec  nop     dword ptr [rax+rax+00h]
0x1400191f1  mov     rcx, r15; Object
0x1400191f4  call    cs:__imp_ObfDereferenceObject
0x1400191fb  nop     dword ptr [rax+rax+00h]
0x140019200  lea     r15, [rdi+38h]
0x140019204  jmp     short loc_14001920D
0x140019206  lea     rsi, [rdi+10h]
0x14001920a  mov     r15, r14
0x14001920d  xor     r9d, r9d; Alertable
0x140019210  mov     [r14], rbp
0x140019213  xor     r8d, r8d; WaitMode
0x140019216  mov     [rsp+88h+Timeout], 0; Timeout
0x14001921f  xor     edx, edx; WaitReason
0x140019221  lea     rcx, [rbp+28h]; Object
0x140019225  call    cs:__imp_KeWaitForSingleObject
0x14001922c  nop     dword ptr [rax+rax+00h]
0x140019231  lea     rax, [rbp+148h]
0x140019238  mov     rcx, [rax+8]
0x14001923c  cmp     [rcx], rax
0x14001923f  jz      short loc_140019248
0x140019241  mov     ecx, 3
0x140019246  int     29h; Win8: RtlFailFast(ecx)
0x140019248  mov     [rsi+8], rcx
0x14001924c  xor     edx, edx; Wait
0x14001924e  mov     [rsi], rax
0x140019251  mov     [rcx], rsi
0x140019254  lea     rcx, [rbp+28h]; Mutex
0x140019258  mov     [rax+8], rsi
0x14001925c  call    cs:__imp_KeReleaseMutex
0x140019263  nop     dword ptr [rax+rax+00h]
0x140019268  mov     rax, [rdi+40h]
0x14001926c  test    rax, rax
0x14001926f  jz      short loc_14001927F
0x140019271  movups  xmm0, xmmword ptr [rax+0B0h]
0x140019278  movdqu  xmmword ptr [rbx+4], xmm0
0x14001927d  jmp     short loc_140019298
0x14001927f  mov     rax, [rdi+168h]
0x140019286  movups  xmm0, xmmword ptr [rax+10h]
0x14001928a  movdqu  xmmword ptr [rbx+4], xmm0
0x14001928f  movups  xmm1, xmmword ptr [rax+20h]
0x140019293  movdqu  xmmword ptr [rbx+14h], xmm1
0x140019298  mov     eax, [rdi+4]
0x14001929b  lea     rdx, [r13+20h]; Src
0x14001929f  mov     r8d, [rbx+24h]; Size
0x1400192a3  lea     rcx, [rbx+28h]; void *
0x1400192a7  mov     [rbx], eax
0x1400192a9  call    memmove
0x1400192ae  mov     eax, [rdi+58h]
0x1400192b1  xor     r9d, r9d
0x1400192b4  mov     rcx, [r15]; Event
0x1400192b7  xor     r8d, r8d
0x1400192ba  mov     [rsp+88h+Src], rbx; Src
0x1400192bf  mov     dword ptr [rsp+88h+Size], r12d; Size
0x1400192c4  mov     dword ptr [rsp+88h+Timeout], eax; int
0x1400192c8  call    TmpSetNotificationResourceManager
0x1400192cd  xor     edx, edx; Tag
0x1400192cf  mov     rcx, rbx; P
0x1400192d2  mov     esi, eax
0x1400192d4  call    cs:__imp_ExFreePoolWithTag
0x1400192db  nop     dword ptr [rax+rax+00h]
0x1400192e0  mov     rcx, rdi; P
0x1400192e3  test    esi, esi
0x1400192e5  jns     short loc_1400192EC
0x1400192e7  mov     r9d, esi
0x1400192ea  jmp     short loc_140019310
0x1400192ec  mov     al, [rdi+180h]
0x1400192f2  neg     al
0x1400192f4  sbb     ebx, ebx
0x1400192f6  not     ebx
0x1400192f8  and     ebx, 103h
0x1400192fe  call    TmpSchedulePropagateRequest
0x140019303  mov     eax, ebx
0x140019305  jmp     short loc_14001931C
0x140019307  mov     r9d, 0C0190010h
0x14001930d  mov     rcx, rdi
0x140019310  xor     r8d, r8d
0x140019313  xor     edx, edx
0x140019315  call    TmpPropagationComplete
0x14001931a  xor     eax, eax
0x14001931c  add     rsp, 48h
0x140019320  pop     r15
0x140019322  pop     r14
0x140019324  pop     r13
0x140019326  pop     r12
0x140019328  pop     rdi
0x140019329  pop     rsi
0x14001932a  pop     rbp
0x14001932b  pop     rbx
0x14001932c  retn
```
