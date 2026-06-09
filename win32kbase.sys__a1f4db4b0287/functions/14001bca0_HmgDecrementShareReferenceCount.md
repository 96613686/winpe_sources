# HmgDecrementShareReferenceCount

- ea: `0x14001bca0`
- end: `0x14001bec8`
- name: `HmgDecrementShareReferenceCount`
- size: `552`
- prototype: ``
- caller_count: `65`
- callee_count: `5`
- tags: ``

## callers

- `0x1400071a4`
- `0x140007278`
- `0x1400072dc`
- `0x140007b60`
- `0x14000c1f0`
- `0x1400103d0`
- `0x140010594`
- `0x1400112e0`
- `0x1400160c0`
- `0x140016500`
- `0x140016e40`
- `0x140018d20`
- `0x140019670`
- `0x14001a0f0`
- `0x14001b7a0`
- `0x140021fec`
- `0x140022370`
- `0x140022644`
- `0x140025bf8`
- `0x140032c4c`
- `0x140033530`
- `0x1400352a0`
- `0x1400355d8`
- `0x140035900`
- `0x140036160`
- `0x14003653c`
- `0x140036940`
- `0x140036a80`
- `0x140036f30`
- `0x14003764c`
- `0x140037a8c`
- `0x140037ba0`
- `0x140037c80`
- `0x140038360`
- `0x1400386a0`
- `0x1400392b0`
- `0x1400398c0`
- `0x14003a7a0`
- `0x14003cef4`
- `0x1400927a0`
- `0x140092a60`
- `0x140093540`
- `0x140093ae0`
- `0x1400b2d50`
- `0x1400b3bb0`
- `0x1400ef820`
- `0x1400ffa80`
- `0x14010bc30`
- `0x140148dec`
- `0x140165170`

## callees

- `0x14001bca0`
- `0x14001bed0`
- `0x14001d250`
- `0x14003bf24`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001be80`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001be80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bdbf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001be1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001bdbf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001be1a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001be8f`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001beac`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001be8f`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001beac`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001be9d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001be9d`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001bcfa`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001bcfa`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001bceb`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x14001bceb`

## pseudocode

```c
__int64 __fastcall HmgDecrementShareReferenceCount(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  __int64 v5; // r13
  unsigned int v6; // edi
  _QWORD *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r15
  __int64 v13; // rcx
  int v14; // ebx
  unsigned int *v15; // rax
  unsigned int *v16; // rsi
  char v17; // al
  unsigned int v18; // r15d
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
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
  v31 = 0;
  v6 = (unsigned __int16)v2 | (v4 >> 8) & 0xFF0000;
  v33 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (_QWORD *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v33);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v10, v9, v11),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && *CurrentThreadWin32ThreadAndEnterCriticalRegion )
  {
    v12 = *CurrentThreadWin32ThreadAndEnterCriticalRegion + 8LL;
  }
  else
  {
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 8);
  v14 = 1;
  v30 = 1;
  v15 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, v6);
  v29 = v15;
  v16 = v15;
  if ( v15 )
  {
    _m_prefetchw(v15 + 2);
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *v15)
                   + 14)
        & 0x20) != 0
      && (!v12
       || (v25 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) == 0
       || !*((_BYTE *)v25 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v25, v6)) )
    {
      LOBYTE(v31) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v29);
      v5 = v32;
      v14 = v30;
      v16 = v29;
    }
  }
  else
  {
    v14 = 0;
    KeLeaveCriticalRegion();
  }
  if ( v14 )
  {
    v17 = *((_BYTE *)v16 + 14);
    v18 = a2[2];
    switch ( v17 )
    {
      case 5:
        v19 = *((_QWORD *)a2 + 91);
        v20 = 3;
        break;
      case 4:
        v19 = *((_QWORD *)a2 + 14);
        v20 = 2;
        break;
      case 16:
        v19 = *((_QWORD *)a2 + 17);
        v20 = 0;
        break;
      default:
        goto LABEL_11;
    }
    TrackObjectReferenceDecrement(a1, v20, v19);
LABEL_11:
    --a2[2];
    v21 = *(__int64 **)(v5 + 8);
    v22 = *v21;
    v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v21 + 96))(v21, *v16);
    (*(void (__fastcall **)(__int64 *, __int64))(v22 + 48))(v21, v23);
    KeLeaveCriticalRegion();
    return v18;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a2);
  return 0;
}

```

## disassembly

```asm
0x14001bca0  mov     [rsp+arg_8], rbx
0x14001bca5  mov     [rsp+arg_10], rbp
0x14001bcaa  push    rsi
0x14001bcab  push    rdi
0x14001bcac  push    r13
0x14001bcae  push    r14
0x14001bcb0  push    r15
0x14001bcb2  sub     rsp, 40h
0x14001bcb6  mov     eax, [rdx]
0x14001bcb8  mov     rbp, rcx
0x14001bcbb  mov     edi, eax
0x14001bcbd  mov     [rsp+68h+var_38], rcx
0x14001bcc2  shr     edi, 8
0x14001bcc5  mov     r13, rcx
0x14001bcc8  movzx   eax, ax
0x14001bccb  lea     rcx, [rsp+68h+arg_0]
0x14001bcd0  and     edi, 0FF0000h
0x14001bcd6  mov     [rsp+68h+var_3C], 0
0x14001bcdd  or      edi, eax
0x14001bcdf  mov     [rsp+68h+arg_0], 0
0x14001bce8  mov     r14, rdx
0x14001bceb  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x14001bcf2  nop     dword ptr [rax+rax+00h]
0x14001bcf7  mov     rsi, rax
0x14001bcfa  call    cs:__imp_KeIsAttachedProcess
0x14001bd01  nop     dword ptr [rax+rax+00h]
0x14001bd06  test    al, al
0x14001bd08  jnz     loc_14001BE80
0x14001bd0e  test    rsi, rsi
0x14001bd11  jz      loc_14001BEC0
0x14001bd17  mov     rax, [rsi]
0x14001bd1a  test    rax, rax
0x14001bd1d  jz      loc_14001BEC0
0x14001bd23  lea     r15, [rax+8]
0x14001bd27  mov     rcx, [rbp+8]
0x14001bd2b  mov     ebx, 1
0x14001bd30  mov     edx, edi
0x14001bd32  mov     [rsp+68h+var_40], ebx
0x14001bd36  mov     rax, [rcx]
0x14001bd39  mov     rax, [rax+28h]
0x14001bd3d  call    _guard_dispatch_icall
0x14001bd42  mov     [rsp+68h+var_48], rax
0x14001bd47  mov     rsi, rax
0x14001bd4a  test    rax, rax
0x14001bd4d  jz      loc_14001BE18
0x14001bd53  prefetchw byte ptr [rax+8]
0x14001bd57  mov     rcx, [rbp+8]
0x14001bd5b  mov     edx, [rsi]
0x14001bd5d  mov     rax, [rcx]
0x14001bd60  mov     rax, [rax+60h]
0x14001bd64  call    _guard_dispatch_icall
0x14001bd69  test    byte ptr [rax+0Eh], 20h
0x14001bd6d  jnz     loc_14001BE39
0x14001bd73  test    ebx, ebx
0x14001bd75  jz      short loc_14001BDE9
0x14001bd77  movzx   eax, byte ptr [rsi+0Eh]
0x14001bd7b  mov     r15d, [r14+8]
0x14001bd7f  cmp     al, 5
0x14001bd81  jnz     short loc_14001BE02
0x14001bd83  mov     r8, [r14+2D8h]
0x14001bd8a  mov     edx, 3
0x14001bd8f  mov     rcx, rbp
0x14001bd92  call    ?TrackObjectReferenceDecrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceDecrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x14001bd97  dec     dword ptr [r14+8]
0x14001bd9b  mov     rdi, [r13+8]
0x14001bd9f  mov     edx, [rsi]
0x14001bda1  mov     rcx, rdi
0x14001bda4  mov     rbx, [rdi]
0x14001bda7  mov     rax, [rbx+60h]
0x14001bdab  call    _guard_dispatch_icall
0x14001bdb0  mov     rdx, rax
0x14001bdb3  mov     rcx, rdi
0x14001bdb6  mov     rax, [rbx+30h]
0x14001bdba  call    _guard_dispatch_icall
0x14001bdbf  call    cs:__imp_KeLeaveCriticalRegion
0x14001bdc6  nop     dword ptr [rax+rax+00h]
0x14001bdcb  mov     eax, r15d
0x14001bdce  mov     rbx, [rsp+68h+arg_8]
0x14001bdd3  mov     rbp, [rsp+68h+arg_10]
0x14001bddb  add     rsp, 40h
0x14001bddf  pop     r15
0x14001bde1  pop     r14
0x14001bde3  pop     r13
0x14001bde5  pop     rdi
0x14001bde6  pop     rsi
0x14001bde7  retn
0x14001bde9  mov     rcx, [rbp+8]
0x14001bded  xor     ebx, ebx
0x14001bdef  mov     rdx, [rcx]
0x14001bdf2  mov     rax, [rdx+8]
0x14001bdf6  mov     rdx, r14
0x14001bdf9  call    _guard_dispatch_icall
0x14001bdfe  mov     eax, ebx
0x14001be00  jmp     short loc_14001BDCE
0x14001be02  cmp     al, 4
0x14001be04  jz      short loc_14001BE2B
0x14001be06  cmp     al, 10h
0x14001be08  jnz     short loc_14001BD97
0x14001be0a  mov     r8, [r14+88h]
0x14001be11  xor     edx, edx
0x14001be13  jmp     loc_14001BD8F
0x14001be18  xor     ebx, ebx
0x14001be1a  call    cs:__imp_KeLeaveCriticalRegion
0x14001be21  nop     dword ptr [rax+rax+00h]
0x14001be26  jmp     loc_14001BD73
0x14001be2b  mov     r8, [r14+70h]
0x14001be2f  mov     edx, 2
0x14001be34  jmp     loc_14001BD8F
0x14001be39  test    r15, r15
0x14001be3c  jz      short loc_14001BE5F
0x14001be3e  mov     rcx, [r15+148h]; this
0x14001be45  test    rcx, rcx
0x14001be48  jz      short loc_14001BE5F
0x14001be4a  cmp     byte ptr [rcx+50h], 0
0x14001be4e  jz      short loc_14001BE5F
0x14001be50  mov     edx, edi; unsigned int
0x14001be52  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14001be57  test    al, al
0x14001be59  jnz     loc_14001BD73
0x14001be5f  mov     byte ptr [rsp+68h+var_3C], bl
0x14001be63  lea     rcx, [rsp+68h+var_48]; this
0x14001be68  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x14001be6d  mov     r13, [rsp+68h+var_38]
0x14001be72  mov     ebx, [rsp+68h+var_40]
0x14001be76  mov     rsi, [rsp+68h+var_48]
0x14001be7b  jmp     loc_14001BD73
0x14001be80  call    cs:__imp_PsGetCurrentProcess
0x14001be87  nop     dword ptr [rax+rax+00h]
0x14001be8c  mov     rcx, rax
0x14001be8f  call    cs:__imp_PsGetProcessSessionIdEx
0x14001be96  nop     dword ptr [rax+rax+00h]
0x14001be9b  mov     ebx, eax
0x14001be9d  call    cs:__imp_PsGetCurrentThreadProcess
0x14001bea4  nop     dword ptr [rax+rax+00h]
0x14001bea9  mov     rcx, rax
0x14001beac  call    cs:__imp_PsGetProcessSessionIdEx
0x14001beb3  nop     dword ptr [rax+rax+00h]
0x14001beb8  cmp     ebx, eax
0x14001beba  jz      loc_14001BD0E
0x14001bec0  xor     r15d, r15d
0x14001bec3  jmp     loc_14001BD27
```
