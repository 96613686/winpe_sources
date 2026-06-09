# HmgDecrementShareReferenceCount

- ea: `0x140024cc0`
- end: `0x140024ee8`
- name: `HmgDecrementShareReferenceCount`
- size: `552`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `66`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e328`
- `0x14000e5e0`
- `0x14000f0c0`
- `0x14000f660`
- `0x1400103b0`
- `0x140010868`
- `0x140010f20`
- `0x140010ff4`
- `0x1400111d4`
- `0x140015360`
- `0x140019540`
- `0x140019704`
- `0x14001a450`
- `0x14001f380`
- `0x14001f670`
- `0x14001ffb0`
- `0x140021d40`
- `0x140022690`
- `0x140023110`
- `0x1400247c0`
- `0x14002b00c`
- `0x14002b390`
- `0x14002b664`
- `0x14002ebe8`
- `0x14003b3b0`
- `0x14003c9f4`
- `0x14003d260`
- `0x14003dac0`
- `0x14003de9c`
- `0x14003e2a0`
- `0x14003e3e0`
- `0x14003e820`
- `0x14003ef3c`
- `0x14003f37c`
- `0x14003f490`
- `0x14003f570`
- `0x14003fc50`
- `0x14003ff90`
- `0x140040ba0`
- `0x1400411b0`
- `0x1400420e0`
- `0x140045e04`
- `0x140066150`
- `0x140066990`
- `0x1400dbf3c`
- `0x1400ecea0`
- `0x14010cea0`
- `0x14012bbe0`
- `0x14014829c`
- `0x140165a10`

## callees

- `0x140024cc0`
- `0x140024ef0`
- `0x140026270`
- `0x140043e04`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140024ea0`
- `ntoskrnl!PsGetCurrentProcess` at `0x140024ea0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024ddf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024e3a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024ddf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024e3a`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024eaf`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024ecc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024eaf`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024ecc`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024ebd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024ebd`
- `ntoskrnl!KeIsAttachedProcess` at `0x140024d1a`
- `ntoskrnl!KeIsAttachedProcess` at `0x140024d1a`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140024d0b`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x140024d0b`

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
0x140024cc0  mov     [rsp+arg_8], rbx
0x140024cc5  mov     [rsp+arg_10], rbp
0x140024cca  push    rsi
0x140024ccb  push    rdi
0x140024ccc  push    r13
0x140024cce  push    r14
0x140024cd0  push    r15
0x140024cd2  sub     rsp, 40h
0x140024cd6  mov     eax, [rdx]
0x140024cd8  mov     rbp, rcx
0x140024cdb  mov     edi, eax
0x140024cdd  mov     [rsp+68h+var_38], rcx
0x140024ce2  shr     edi, 8
0x140024ce5  mov     r13, rcx
0x140024ce8  movzx   eax, ax
0x140024ceb  lea     rcx, [rsp+68h+arg_0]
0x140024cf0  and     edi, 0FF0000h
0x140024cf6  mov     [rsp+68h+var_3C], 0
0x140024cfd  or      edi, eax
0x140024cff  mov     [rsp+68h+arg_0], 0
0x140024d08  mov     r14, rdx
0x140024d0b  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x140024d12  nop     dword ptr [rax+rax+00h]
0x140024d17  mov     rsi, rax
0x140024d1a  call    cs:__imp_KeIsAttachedProcess
0x140024d21  nop     dword ptr [rax+rax+00h]
0x140024d26  test    al, al
0x140024d28  jnz     loc_140024EA0
0x140024d2e  test    rsi, rsi
0x140024d31  jz      loc_140024EE0
0x140024d37  mov     rax, [rsi]
0x140024d3a  test    rax, rax
0x140024d3d  jz      loc_140024EE0
0x140024d43  lea     r15, [rax+8]
0x140024d47  mov     rcx, [rbp+8]
0x140024d4b  mov     ebx, 1
0x140024d50  mov     edx, edi
0x140024d52  mov     [rsp+68h+var_40], ebx
0x140024d56  mov     rax, [rcx]
0x140024d59  mov     rax, [rax+28h]
0x140024d5d  call    _guard_dispatch_icall
0x140024d62  mov     [rsp+68h+var_48], rax
0x140024d67  mov     rsi, rax
0x140024d6a  test    rax, rax
0x140024d6d  jz      loc_140024E38
0x140024d73  prefetchw byte ptr [rax+8]
0x140024d77  mov     rcx, [rbp+8]
0x140024d7b  mov     edx, [rsi]
0x140024d7d  mov     rax, [rcx]
0x140024d80  mov     rax, [rax+60h]
0x140024d84  call    _guard_dispatch_icall
0x140024d89  test    byte ptr [rax+0Eh], 20h
0x140024d8d  jnz     loc_140024E59
0x140024d93  test    ebx, ebx
0x140024d95  jz      short loc_140024E09
0x140024d97  movzx   eax, byte ptr [rsi+0Eh]
0x140024d9b  mov     r15d, [r14+8]
0x140024d9f  cmp     al, 5
0x140024da1  jnz     short loc_140024E22
0x140024da3  mov     r8, [r14+2D8h]
0x140024daa  mov     edx, 3
0x140024daf  mov     rcx, rbp
0x140024db2  call    ?TrackObjectReferenceDecrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceDecrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140024db7  dec     dword ptr [r14+8]
0x140024dbb  mov     rdi, [r13+8]
0x140024dbf  mov     edx, [rsi]
0x140024dc1  mov     rcx, rdi
0x140024dc4  mov     rbx, [rdi]
0x140024dc7  mov     rax, [rbx+60h]
0x140024dcb  call    _guard_dispatch_icall
0x140024dd0  mov     rdx, rax
0x140024dd3  mov     rcx, rdi
0x140024dd6  mov     rax, [rbx+30h]
0x140024dda  call    _guard_dispatch_icall
0x140024ddf  call    cs:__imp_KeLeaveCriticalRegion
0x140024de6  nop     dword ptr [rax+rax+00h]
0x140024deb  mov     eax, r15d
0x140024dee  mov     rbx, [rsp+68h+arg_8]
0x140024df3  mov     rbp, [rsp+68h+arg_10]
0x140024dfb  add     rsp, 40h
0x140024dff  pop     r15
0x140024e01  pop     r14
0x140024e03  pop     r13
0x140024e05  pop     rdi
0x140024e06  pop     rsi
0x140024e07  retn
0x140024e09  mov     rcx, [rbp+8]
0x140024e0d  xor     ebx, ebx
0x140024e0f  mov     rdx, [rcx]
0x140024e12  mov     rax, [rdx+8]
0x140024e16  mov     rdx, r14
0x140024e19  call    _guard_dispatch_icall
0x140024e1e  mov     eax, ebx
0x140024e20  jmp     short loc_140024DEE
0x140024e22  cmp     al, 4
0x140024e24  jz      short loc_140024E4B
0x140024e26  cmp     al, 10h
0x140024e28  jnz     short loc_140024DB7
0x140024e2a  mov     r8, [r14+88h]
0x140024e31  xor     edx, edx
0x140024e33  jmp     loc_140024DAF
0x140024e38  xor     ebx, ebx
0x140024e3a  call    cs:__imp_KeLeaveCriticalRegion
0x140024e41  nop     dword ptr [rax+rax+00h]
0x140024e46  jmp     loc_140024D93
0x140024e4b  mov     r8, [r14+70h]
0x140024e4f  mov     edx, 2
0x140024e54  jmp     loc_140024DAF
0x140024e59  test    r15, r15
0x140024e5c  jz      short loc_140024E7F
0x140024e5e  mov     rcx, [r15+148h]; this
0x140024e65  test    rcx, rcx
0x140024e68  jz      short loc_140024E7F
0x140024e6a  cmp     byte ptr [rcx+50h], 0
0x140024e6e  jz      short loc_140024E7F
0x140024e70  mov     edx, edi; unsigned int
0x140024e72  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x140024e77  test    al, al
0x140024e79  jnz     loc_140024D93
0x140024e7f  mov     byte ptr [rsp+68h+var_3C], bl
0x140024e83  lea     rcx, [rsp+68h+var_48]; this
0x140024e88  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140024e8d  mov     r13, [rsp+68h+var_38]
0x140024e92  mov     ebx, [rsp+68h+var_40]
0x140024e96  mov     rsi, [rsp+68h+var_48]
0x140024e9b  jmp     loc_140024D93
0x140024ea0  call    cs:__imp_PsGetCurrentProcess
0x140024ea7  nop     dword ptr [rax+rax+00h]
0x140024eac  mov     rcx, rax
0x140024eaf  call    cs:__imp_PsGetProcessSessionIdEx
0x140024eb6  nop     dword ptr [rax+rax+00h]
0x140024ebb  mov     ebx, eax
0x140024ebd  call    cs:__imp_PsGetCurrentThreadProcess
0x140024ec4  nop     dword ptr [rax+rax+00h]
0x140024ec9  mov     rcx, rax
0x140024ecc  call    cs:__imp_PsGetProcessSessionIdEx
0x140024ed3  nop     dword ptr [rax+rax+00h]
0x140024ed8  cmp     ebx, eax
0x140024eda  jz      loc_140024D2E
0x140024ee0  xor     r15d, r15d
0x140024ee3  jmp     loc_140024D47
```
