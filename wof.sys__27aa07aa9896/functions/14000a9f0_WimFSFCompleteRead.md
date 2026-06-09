# WimFSFCompleteRead

- ea: `0x14000a9f0`
- end: `0x14000ac2c`
- name: `WimFSFCompleteRead`
- size: `572`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000afc0`
- `0x14000c400`
- `0x14000cae0`

## callees

- `0x14000a9f0`
- `0x14000cfe0`
- `0x14000d3b8`
- `0x14000fb60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000abe4`
- `ntoskrnl!KeSetEvent` at `0x14000abe4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000ab09`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000ab09`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14000abc3`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14000abc3`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000ab20`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000ab20`
- `FLTMGR!FltFreeCallbackData` at `0x14000ab7d`
- `FLTMGR!FltFreeCallbackData` at `0x14000ab7d`

## pseudocode

```c
__int64 __fastcall WimFSFCompleteRead(char *Entry, unsigned int a2, int a3)
{
  struct _FLT_INSTANCE *v3; // r12
  void *v5; // r14
  void *v7; // r15
  __int64 v8; // rdi
  struct _KEVENT *v9; // rbp
  __int64 v10; // rcx
  struct _EX_RUNDOWN_REF *v11; // rcx
  __int64 v12; // rcx
  __int64 result; // rax

  v3 = (struct _FLT_INSTANCE *)*((_QWORD *)Entry + 5);
  v5 = (void *)*((_QWORD *)Entry + 21);
  v7 = (void *)*((_QWORD *)Entry + 22);
  v8 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  if ( Entry[201] )
  {
    *((_DWORD *)Entry + 2) = a3;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    v9 = (struct _KEVENT *)(Entry + 208);
    if ( a3 < 0 )
      LODWORD(v8) = 0;
    *((_DWORD *)Entry + 29) = v8;
  }
  else
  {
    v9 = 0;
    *(_DWORD *)(*((_QWORD *)Entry + 3) + 24LL) = a3;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    v10 = *((_QWORD *)Entry + 3);
    if ( a3 >= 0 )
    {
      *(_QWORD *)(v10 + 32) = v8;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
          *(unsigned int *)(*((_QWORD *)Entry + 3) + 32LL));
    }
    else
    {
      *(_QWORD *)(v10 + 32) = 0;
    }
    v11 = (struct _EX_RUNDOWN_REF *)*((_QWORD *)Entry + 4);
    if ( v11 )
      ExReleaseRundownProtection(v11);
    FltCompletePendedPreOperation(*((PFLT_CALLBACK_DATA *)Entry + 3), FLT_PREOP_COMPLETE, 0);
  }
  if ( Entry[200] )
  {
    v12 = *(_QWORD *)(*(_QWORD *)Entry + 16LL);
    if ( *(_QWORD *)(v12 + 56) == *((_QWORD *)Entry + 24) )
      *(_QWORD *)(v12 + 56) = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    FltFreeCallbackData(*(PFLT_CALLBACK_DATA *)Entry);
  }
  if ( v5 != v7 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    FltFreePoolAlignedWithTag(v3, v5, 0x44527077u);
  }
  WimFSFReleaseReadCompletionContext((volatile signed __int32 *)Entry);
  if ( v9 )
    KeSetEvent(v9, 0, 0);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(
             WPP_GLOBAL_Control->AttachedDevice,
             23,
             WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
             (unsigned int)a3);
  return result;
}

```

## disassembly

```asm
0x14000a9f0  push    rbx
0x14000a9f2  push    rbp
0x14000a9f3  push    rsi
0x14000a9f4  push    rdi
0x14000a9f5  push    r12
0x14000a9f7  push    r14
0x14000a9f9  push    r15
0x14000a9fb  sub     rsp, 20h
0x14000a9ff  mov     r12, [rcx+28h]
0x14000aa03  mov     esi, r8d
0x14000aa06  mov     r14, [rcx+0A8h]
0x14000aa0d  mov     rbx, rcx
0x14000aa10  mov     r15, [rcx+0B0h]
0x14000aa17  mov     edi, edx
0x14000aa19  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa20  mov     eax, [rcx+2Ch]
0x14000aa23  test    al, 20h
0x14000aa25  jz      short loc_14000AA42
0x14000aa27  cmp     byte ptr [rcx+29h], 4
0x14000aa2b  jb      short loc_14000AA42
0x14000aa2d  mov     rcx, [rcx+18h]
0x14000aa31  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000aa38  mov     edx, 11h
0x14000aa3d  call    WPP_SF_
0x14000aa42  cmp     byte ptr [rbx+0C9h], 0
0x14000aa49  jz      short loc_14000AA8D
0x14000aa4b  mov     [rbx+8], esi
0x14000aa4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa55  mov     eax, [rcx+2Ch]
0x14000aa58  test    al, 20h
0x14000aa5a  jz      short loc_14000AA77
0x14000aa5c  cmp     byte ptr [rcx+29h], 4
0x14000aa60  jb      short loc_14000AA77
0x14000aa62  mov     rcx, [rcx+18h]
0x14000aa66  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000aa6d  mov     edx, 12h
0x14000aa72  call    WPP_SF_
0x14000aa77  xor     eax, eax
0x14000aa79  lea     rbp, [rbx+0D0h]
0x14000aa80  test    esi, esi
0x14000aa82  cmovs   edi, eax
0x14000aa85  mov     [rbx+74h], edi
0x14000aa88  jmp     loc_14000AB2C
0x14000aa8d  mov     rax, [rbx+18h]
0x14000aa91  xor     ebp, ebp
0x14000aa93  mov     [rax+18h], esi
0x14000aa96  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa9d  mov     eax, [rcx+2Ch]
0x14000aaa0  test    al, 20h
0x14000aaa2  jz      short loc_14000AABD
0x14000aaa4  cmp     byte ptr [rcx+29h], 4
0x14000aaa8  jb      short loc_14000AABD
0x14000aaaa  mov     rcx, [rcx+18h]
0x14000aaae  lea     edx, [rbp+13h]
0x14000aab1  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000aab8  call    WPP_SF_
0x14000aabd  mov     rcx, [rbx+18h]
0x14000aac1  test    esi, esi
0x14000aac3  jns     short loc_14000AACB
0x14000aac5  mov     [rcx+20h], rbp
0x14000aac9  jmp     short loc_14000AB00
0x14000aacb  mov     [rcx+20h], rdi
0x14000aacf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aad6  mov     eax, [rcx+2Ch]
0x14000aad9  test    al, 4
0x14000aadb  jz      short loc_14000AB00
0x14000aadd  cmp     byte ptr [rcx+29h], 5
0x14000aae1  jb      short loc_14000AB00
0x14000aae3  mov     r9, [rbx+18h]
0x14000aae7  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000aaee  mov     rcx, [rcx+18h]
0x14000aaf2  mov     edx, 14h
0x14000aaf7  mov     r9d, [r9+20h]
0x14000aafb  call    WPP_SF_d
0x14000ab00  mov     rcx, [rbx+20h]; RunRef
0x14000ab04  test    rcx, rcx
0x14000ab07  jz      short loc_14000AB15
0x14000ab09  call    cs:__imp_ExReleaseRundownProtection
0x14000ab10  nop     dword ptr [rax+rax+00h]
0x14000ab15  mov     rcx, [rbx+18h]; CallbackData
0x14000ab19  xor     r8d, r8d; Context
0x14000ab1c  lea     edx, [r8+4]; CallbackStatus
0x14000ab20  call    cs:__imp_FltCompletePendedPreOperation
0x14000ab27  nop     dword ptr [rax+rax+00h]
0x14000ab2c  cmp     byte ptr [rbx+0C8h], 0
0x14000ab33  jz      short loc_14000AB89
0x14000ab35  mov     rax, [rbx]
0x14000ab38  mov     rcx, [rax+10h]
0x14000ab3c  mov     rax, [rbx+0C0h]
0x14000ab43  cmp     [rcx+38h], rax
0x14000ab47  jnz     short loc_14000AB51
0x14000ab49  mov     qword ptr [rcx+38h], 0
0x14000ab51  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab58  mov     eax, [rcx+2Ch]
0x14000ab5b  test    al, 20h
0x14000ab5d  jz      short loc_14000AB7A
0x14000ab5f  cmp     byte ptr [rcx+29h], 4
0x14000ab63  jb      short loc_14000AB7A
0x14000ab65  mov     rcx, [rcx+18h]
0x14000ab69  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000ab70  mov     edx, 15h
0x14000ab75  call    WPP_SF_
0x14000ab7a  mov     rcx, [rbx]; CallbackData
0x14000ab7d  call    cs:__imp_FltFreeCallbackData
0x14000ab84  nop     dword ptr [rax+rax+00h]
0x14000ab89  cmp     r14, r15
0x14000ab8c  jz      short loc_14000ABCF
0x14000ab8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab95  mov     eax, [rcx+2Ch]
0x14000ab98  test    al, 20h
0x14000ab9a  jz      short loc_14000ABB7
0x14000ab9c  cmp     byte ptr [rcx+29h], 4
0x14000aba0  jb      short loc_14000ABB7
0x14000aba2  mov     rcx, [rcx+18h]
0x14000aba6  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000abad  mov     edx, 16h
0x14000abb2  call    WPP_SF_
0x14000abb7  mov     r8d, 44527077h; Tag
0x14000abbd  mov     rdx, r14; Buffer
0x14000abc0  mov     rcx, r12; Instance
0x14000abc3  call    cs:__imp_FltFreePoolAlignedWithTag
0x14000abca  nop     dword ptr [rax+rax+00h]
0x14000abcf  mov     rcx, rbx; Entry
0x14000abd2  call    WimFSFReleaseReadCompletionContext
0x14000abd7  test    rbp, rbp
0x14000abda  jz      short loc_14000ABF0
0x14000abdc  xor     r8d, r8d; Wait
0x14000abdf  xor     edx, edx; Increment
0x14000abe1  mov     rcx, rbp; Event
0x14000abe4  call    cs:__imp_KeSetEvent
0x14000abeb  nop     dword ptr [rax+rax+00h]
0x14000abf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000abf7  mov     eax, [rcx+2Ch]
0x14000abfa  test    al, 20h
0x14000abfc  jz      short loc_14000AC1C
0x14000abfe  cmp     byte ptr [rcx+29h], 4
0x14000ac02  jb      short loc_14000AC1C
0x14000ac04  mov     rcx, [rcx+18h]
0x14000ac08  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14000ac0f  mov     edx, 17h
0x14000ac14  mov     r9d, esi
0x14000ac17  call    WPP_SF_d
0x14000ac1c  add     rsp, 20h
0x14000ac20  pop     r15
0x14000ac22  pop     r14
0x14000ac24  pop     r12
0x14000ac26  pop     rdi
0x14000ac27  pop     rsi
0x14000ac28  pop     rbp
0x14000ac29  pop     rbx
0x14000ac2a  retn
```
