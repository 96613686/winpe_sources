# HmgIncrementShareReferenceCount

- ea: `0x1400309d0`
- end: `0x140030bec`
- name: `HmgIncrementShareReferenceCount`
- size: `540`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x14000fce8`
- `0x14001a99c`
- `0x14001ac50`
- `0x140027d70`
- `0x140039f10`
- `0x14003eb30`
- `0x1401028b0`
- `0x140166a0c`
- `0x140170390`
- `0x14017761c`
- `0x140188868`
- `0x1401e5b88`
- `0x1401f22b4`

## callees

- `0x14001e034`
- `0x1400309d0`
- `0x140031784`
- `0x140079330`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140030b96`
- `ntoskrnl!PsGetCurrentProcess` at `0x140030b96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030aef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030b3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030aef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140030b3e`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140030ba5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140030bc2`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140030ba5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140030bc2`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140030bb3`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140030bb3`
- `ntoskrnl!KeIsAttachedProcess` at `0x140030a29`
- `ntoskrnl!KeIsAttachedProcess` at `0x140030a29`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140030a1a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140030a1a`

## pseudocode

```c
void __fastcall HmgIncrementShareReferenceCount(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  __int64 v5; // r13
  unsigned int v6; // edi
  _QWORD *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r15
  __int64 v15; // rcx
  int v16; // ebx
  unsigned int *v17; // rax
  unsigned int *v18; // rsi
  char v19; // al
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 *v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rax
  ThreadRestrictNewHandlesRegion *v25; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v29; // [rsp+20h] [rbp-48h] BYREF
  int v30; // [rsp+28h] [rbp-40h]
  __int16 v31; // [rsp+2Ch] [rbp-3Ch]
  __int64 v32; // [rsp+30h] [rbp-38h]
  __int64 v33; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a2;
  v4 = *a2;
  v32 = a1;
  v5 = a1;
  v6 = (unsigned __int16)v2 | (v4 >> 8) & 0xFF0000;
  v31 = 0;
  v33 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (_QWORD *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v33);
  if ( (!(unsigned __int8)KeIsAttachedProcess(v10, v9)
     || (CurrentProcess = PsGetCurrentProcess(v12, v11, v13),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && *CurrentThreadWin32ThreadAndEnterCriticalRegion )
  {
    v14 = *CurrentThreadWin32ThreadAndEnterCriticalRegion + 8LL;
  }
  else
  {
    v14 = 0;
  }
  v15 = *(_QWORD *)(a1 + 8);
  v16 = 1;
  v30 = 1;
  v17 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 40LL))(v15, v6);
  v29 = v17;
  v18 = v17;
  if ( v17 )
  {
    _m_prefetchw(v17 + 2);
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *v17)
                   + 14)
        & 0x20) != 0
      && (!v14
       || (v25 = *(ThreadRestrictNewHandlesRegion **)(v14 + 328)) == 0
       || !*((_BYTE *)v25 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v25, v6)) )
    {
      LOBYTE(v31) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v29);
      v5 = v32;
      v16 = v30;
      v18 = v29;
    }
  }
  else
  {
    v16 = 0;
    KeLeaveCriticalRegion();
  }
  if ( v16 )
  {
    v19 = *((_BYTE *)v18 + 14);
    switch ( v19 )
    {
      case 5:
        v20 = *((_QWORD *)a2 + 89);
        v21 = 3;
        break;
      case 4:
        v20 = *((_QWORD *)a2 + 14);
        v21 = 2;
        break;
      case 16:
        v20 = *((_QWORD *)a2 + 17);
        v21 = 0;
        break;
      default:
        goto LABEL_11;
    }
    TrackObjectReferenceIncrement(a1, v21, v20);
LABEL_11:
    ++a2[2];
    v22 = *(__int64 **)(v5 + 8);
    v23 = *v22;
    v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v22 + 96))(v22, *v18);
    (*(void (__fastcall **)(__int64 *, __int64))(v23 + 48))(v22, v24);
    KeLeaveCriticalRegion();
    return;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x1400309d0  mov     [rsp+arg_10], rbx
0x1400309d5  push    rbp
0x1400309d6  push    rsi
0x1400309d7  push    rdi
0x1400309d8  push    r13
0x1400309da  push    r14
0x1400309dc  sub     rsp, 40h
0x1400309e0  mov     eax, [rdx]
0x1400309e2  mov     rbp, rcx
0x1400309e5  mov     edi, eax
0x1400309e7  mov     [rsp+68h+var_38], rcx
0x1400309ec  shr     edi, 8
0x1400309ef  mov     r13, rcx
0x1400309f2  movzx   eax, ax
0x1400309f5  lea     rcx, [rsp+68h+arg_0]
0x1400309fa  and     edi, 0FF0000h
0x140030a00  mov     [rsp+68h+arg_8], r15
0x140030a05  or      edi, eax
0x140030a07  mov     [rsp+68h+var_3C], 0
0x140030a0e  mov     r14, rdx
0x140030a11  mov     [rsp+68h+arg_0], 0
0x140030a1a  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140030a21  nop     dword ptr [rax+rax+00h]
0x140030a26  mov     rsi, rax
0x140030a29  call    cs:__imp_KeIsAttachedProcess
0x140030a30  nop     dword ptr [rax+rax+00h]
0x140030a35  test    al, al
0x140030a37  jnz     loc_140030B96
0x140030a3d  test    rsi, rsi
0x140030a40  jz      loc_140030BD6
0x140030a46  mov     rax, [rsi]
0x140030a49  test    rax, rax
0x140030a4c  jz      loc_140030BD6
0x140030a52  lea     r15, [rax+8]
0x140030a56  mov     rcx, [rbp+8]
0x140030a5a  mov     ebx, 1
0x140030a5f  mov     edx, edi
0x140030a61  mov     [rsp+68h+var_40], ebx
0x140030a65  mov     rax, [rcx]
0x140030a68  mov     rax, [rax+28h]
0x140030a6c  call    _guard_dispatch_icall
0x140030a71  mov     [rsp+68h+var_48], rax
0x140030a76  mov     rsi, rax
0x140030a79  test    rax, rax
0x140030a7c  jz      loc_140030B3C
0x140030a82  prefetchw byte ptr [rax+8]
0x140030a86  mov     rcx, [rbp+8]
0x140030a8a  mov     edx, [rsi]
0x140030a8c  mov     rax, [rcx]
0x140030a8f  mov     rax, [rax+60h]
0x140030a93  call    _guard_dispatch_icall
0x140030a98  test    byte ptr [rax+0Eh], 20h
0x140030a9c  jnz     loc_140030B4F
0x140030aa2  mov     r15, [rsp+68h+arg_8]
0x140030aa7  test    ebx, ebx
0x140030aa9  jz      short loc_140030B10
0x140030aab  movzx   eax, byte ptr [rsi+0Eh]
0x140030aaf  cmp     al, 5
0x140030ab1  jnz     short loc_140030B25
0x140030ab3  mov     r8, [r14+2C8h]
0x140030aba  mov     edx, 3
0x140030abf  mov     rcx, rbp
0x140030ac2  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140030ac7  inc     dword ptr [r14+8]
0x140030acb  mov     rdi, [r13+8]
0x140030acf  mov     edx, [rsi]
0x140030ad1  mov     rcx, rdi
0x140030ad4  mov     rbx, [rdi]
0x140030ad7  mov     rax, [rbx+60h]
0x140030adb  call    _guard_dispatch_icall
0x140030ae0  mov     rdx, rax
0x140030ae3  mov     rcx, rdi
0x140030ae6  mov     rax, [rbx+30h]
0x140030aea  call    _guard_dispatch_icall
0x140030aef  call    cs:__imp_KeLeaveCriticalRegion
0x140030af6  nop     dword ptr [rax+rax+00h]
0x140030afb  mov     rbx, [rsp+68h+arg_10]
0x140030b03  add     rsp, 40h
0x140030b07  pop     r14
0x140030b09  pop     r13
0x140030b0b  pop     rdi
0x140030b0c  pop     rsi
0x140030b0d  pop     rbp
0x140030b0e  retn
0x140030b10  mov     rcx, [rbp+8]
0x140030b14  mov     rdx, r14
0x140030b17  mov     rax, [rcx]
0x140030b1a  mov     rax, [rax+8]
0x140030b1e  call    _guard_dispatch_icall
0x140030b23  jmp     short loc_140030AFB
0x140030b25  cmp     al, 4
0x140030b27  jz      loc_140030BDE
0x140030b2d  cmp     al, 10h
0x140030b2f  jnz     short loc_140030AC7
0x140030b31  mov     r8, [r14+88h]
0x140030b38  xor     edx, edx
0x140030b3a  jmp     short loc_140030ABF
0x140030b3c  xor     ebx, ebx
0x140030b3e  call    cs:__imp_KeLeaveCriticalRegion
0x140030b45  nop     dword ptr [rax+rax+00h]
0x140030b4a  jmp     loc_140030AA2
0x140030b4f  test    r15, r15
0x140030b52  jz      short loc_140030B75
0x140030b54  mov     rcx, [r15+148h]; this
0x140030b5b  test    rcx, rcx
0x140030b5e  jz      short loc_140030B75
0x140030b60  cmp     byte ptr [rcx+50h], 0
0x140030b64  jz      short loc_140030B75
0x140030b66  mov     edx, edi; unsigned int
0x140030b68  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140030b6d  test    al, al
0x140030b6f  jnz     loc_140030AA2
0x140030b75  mov     byte ptr [rsp+68h+var_3C], bl
0x140030b79  lea     rcx, [rsp+68h+var_48]; this
0x140030b7e  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140030b83  mov     r13, [rsp+68h+var_38]
0x140030b88  mov     ebx, [rsp+68h+var_40]
0x140030b8c  mov     rsi, [rsp+68h+var_48]
0x140030b91  jmp     loc_140030AA2
0x140030b96  call    cs:__imp_PsGetCurrentProcess
0x140030b9d  nop     dword ptr [rax+rax+00h]
0x140030ba2  mov     rcx, rax
0x140030ba5  call    cs:__imp_PsGetProcessSessionIdEx
0x140030bac  nop     dword ptr [rax+rax+00h]
0x140030bb1  mov     ebx, eax
0x140030bb3  call    cs:__imp_PsGetCurrentThreadProcess
0x140030bba  nop     dword ptr [rax+rax+00h]
0x140030bbf  mov     rcx, rax
0x140030bc2  call    cs:__imp_PsGetProcessSessionIdEx
0x140030bc9  nop     dword ptr [rax+rax+00h]
0x140030bce  cmp     ebx, eax
0x140030bd0  jz      loc_140030A3D
0x140030bd6  xor     r15d, r15d
0x140030bd9  jmp     loc_140030A56
0x140030bde  mov     r8, [r14+70h]
0x140030be2  mov     edx, 2
0x140030be7  jmp     loc_140030ABF
```
