# OncRpcDrcTableCreate

- ea: `0x140011010`
- end: `0x14001117c`
- name: `OncRpcDrcTableCreate`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140010da8`

## callees

- `0x1400020c0`
- `0x140010228`
- `0x1400102b4`
- `0x140011010`
- `0x140012838`
- `0x1400128ac`
- `0x1400129c4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001107a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001107a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011124`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011124`

## pseudocode

```c
__int64 __fastcall OncRpcDrcTableCreate(_QWORD *a1, __int64 a2)
{
  int v3; // eax
  __int64 v4; // rbx
  int v5; // edi
  _QWORD *v6; // rsi
  unsigned int v7; // edx
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  void *v10; // rcx
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  v3 = NfsMemMgrStructureAllocate(1413698116, a2, &v12);
  v4 = v12;
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_7;
  v6 = (_QWORD *)(v12 + 24);
  *(_QWORD *)(v12 + 24) = 0;
  v5 = NfsMemMgrBufferAllocate(512, 1279480388, (unsigned int)(16 * dword_14001AA30), v4 + 24);
  if ( v5 < 0 )
    goto LABEL_7;
  KeInitializeSpinLock((PKSPIN_LOCK)(v4 + 56));
  v7 = 0;
  *(_DWORD *)(v4 + 32) = dword_14001AA30;
  *(_DWORD *)(v4 + 72) = dword_14001AA34;
  *(_DWORD *)(v4 + 80) = dword_14001AA38;
  if ( *(_DWORD *)(v4 + 32) )
  {
    do
    {
      v8 = v7++;
      v9 = (_QWORD *)(*v6 + 16 * v8);
      v9[1] = v9;
      *v9 = v9;
    }
    while ( v7 < *(_DWORD *)(v4 + 32) );
  }
  *(_QWORD *)(v4 + 48) = v4 + 40;
  *(_QWORD *)(v4 + 40) = v4 + 40;
  *(_QWORD *)(v4 + 88) = 63236;
  *(_DWORD *)(v4 + 84) = 65028;
  v5 = OncRpcWiMgrTimerCreate(OncRpcDrcpCachePurgeThread, v4, v4 + 64);
  if ( v5 < 0 )
  {
LABEL_7:
    if ( v4 )
    {
      v10 = *(void **)(v4 + 24);
      if ( v10 )
        ExFreePoolWithTag(v10, 0x4C435244u);
      NfsMemMgrStructureFree(1413698116, v4);
    }
  }
  else
  {
    OncRpcWiMgrSetTimer(
      *(_QWORD *)(v4 + 64),
      -10000000LL * *(unsigned int *)(v4 + 72),
      (unsigned int)(1000 * *(_DWORD *)(v4 + 72)));
    *a1 = v4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_632595d04f6b3e7c902667290836fce3_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140011010  push    rbx
0x140011012  push    rsi
0x140011013  push    rdi
0x140011014  push    r14
0x140011016  sub     rsp, 28h
0x14001101a  mov     r14, rcx
0x14001101d  mov     [rsp+48h+arg_8], 0
0x140011026  mov     ecx, 54435244h
0x14001102b  lea     r8, [rsp+48h+arg_8]
0x140011030  call    NfsMemMgrStructureAllocate
0x140011035  mov     rbx, [rsp+48h+arg_8]
0x14001103a  mov     edi, eax
0x14001103c  test    eax, eax
0x14001103e  js      loc_140011111
0x140011044  lea     rsi, [rbx+18h]
0x140011048  mov     edx, 4C435244h
0x14001104d  mov     qword ptr [rsi], 0
0x140011054  mov     r9, rsi
0x140011057  mov     r8d, cs:dword_14001AA30
0x14001105e  mov     ecx, 200h
0x140011063  shl     r8d, 4
0x140011067  call    NfsMemMgrBufferAllocate
0x14001106c  mov     edi, eax
0x14001106e  test    eax, eax
0x140011070  js      loc_140011111
0x140011076  lea     rcx, [rbx+38h]; SpinLock
0x14001107a  call    cs:__imp_KeInitializeSpinLock
0x140011081  nop     dword ptr [rax+rax+00h]
0x140011086  mov     eax, cs:dword_14001AA30
0x14001108c  xor     edx, edx
0x14001108e  mov     [rbx+20h], eax
0x140011091  mov     eax, cs:dword_14001AA34
0x140011097  mov     [rbx+48h], eax
0x14001109a  mov     eax, cs:dword_14001AA38
0x1400110a0  mov     [rbx+50h], eax
0x1400110a3  cmp     [rbx+20h], edx
0x1400110a6  jbe     short loc_1400110BF
0x1400110a8  mov     ecx, edx
0x1400110aa  inc     edx
0x1400110ac  shl     rcx, 4
0x1400110b0  add     rcx, [rsi]
0x1400110b3  mov     [rcx+8], rcx
0x1400110b7  mov     [rcx], rcx
0x1400110ba  cmp     edx, [rbx+20h]
0x1400110bd  jb      short loc_1400110A8
0x1400110bf  lea     rax, [rbx+28h]
0x1400110c3  mov     rdx, rbx
0x1400110c6  mov     [rax+8], rax
0x1400110ca  lea     r8, [rbx+40h]
0x1400110ce  mov     [rax], rax
0x1400110d1  lea     rcx, OncRpcDrcpCachePurgeThread
0x1400110d8  mov     qword ptr [rbx+58h], 0F704h
0x1400110e0  mov     dword ptr [rbx+54h], 0FE04h
0x1400110e7  call    OncRpcWiMgrTimerCreate
0x1400110ec  mov     edi, eax
0x1400110ee  test    eax, eax
0x1400110f0  js      short loc_140011111
0x1400110f2  mov     eax, [rbx+48h]
0x1400110f5  mov     rcx, [rbx+40h]
0x1400110f9  imul    rdx, rax, 0FFFFFFFFFF676980h
0x140011100  imul    r8d, eax, 3E8h
0x140011107  call    OncRpcWiMgrSetTimer
0x14001110c  mov     [r14], rbx
0x14001110f  jmp     short loc_14001113D
0x140011111  test    rbx, rbx
0x140011114  jz      short loc_14001113D
0x140011116  mov     rcx, [rbx+18h]; P
0x14001111a  test    rcx, rcx
0x14001111d  jz      short loc_140011130
0x14001111f  mov     edx, 4C435244h; Tag
0x140011124  call    cs:__imp_ExFreePoolWithTag
0x14001112b  nop     dword ptr [rax+rax+00h]
0x140011130  mov     rdx, rbx
0x140011133  mov     ecx, 54435244h
0x140011138  call    NfsMemMgrStructureFree
0x14001113d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011144  lea     rax, WPP_GLOBAL_Control
0x14001114b  cmp     rcx, rax
0x14001114e  jz      short loc_14001116F
0x140011150  mov     eax, [rcx+2Ch]
0x140011153  test    al, 1
0x140011155  jz      short loc_14001116F
0x140011157  mov     rcx, [rcx+18h]
0x14001115b  lea     r8, WPP_632595d04f6b3e7c902667290836fce3_Traceguids
0x140011162  mov     edx, 0Dh
0x140011167  mov     r9d, edi
0x14001116a  call    WPP_SF_d
0x14001116f  mov     eax, edi
0x140011171  add     rsp, 28h
0x140011175  pop     r14
0x140011177  pop     rdi
0x140011178  pop     rsi
0x140011179  pop     rbx
0x14001117a  retn
```
