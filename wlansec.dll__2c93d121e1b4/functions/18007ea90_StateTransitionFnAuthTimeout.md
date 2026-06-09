# StateTransitionFnAuthTimeout

- ea: `0x18007ea90`
- end: `0x18007ebeb`
- name: `StateTransitionFnAuthTimeout`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007de24`
- `0x18007ea90`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseReadLock` at `0x18007eb30`
- `MobileNetworking!ReleaseReadLock` at `0x18007eb5d`
- `MobileNetworking!ReleaseReadLock` at `0x18007eb30`
- `MobileNetworking!ReleaseReadLock` at `0x18007eb5d`
- `MobileNetworking!AcquireReadLock` at `0x18007eae9`
- `MobileNetworking!AcquireReadLock` at `0x18007eae9`

## pseudocode

```c
__int64 __fastcall StateTransitionFnAuthTimeout(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // eax
  PVOID *v6; // rcx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids);
  v2 = *(_QWORD *)(a1 + 64);
  AcquireReadLock(v2 + 24);
  v3 = *(_QWORD *)(v2 + 288);
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids);
    v4 = 5023;
    ReleaseReadLock(v2 + 24);
    goto LABEL_14;
  }
  v4 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, int *))(qword_1800BB5A8 + 40))(v3, &v9, &v8);
  ReleaseReadLock(v2 + 24);
  if ( !v9 || (v5 = PktSendEap(v2, v9, (unsigned __int16)v8), (v4 = v5) == 0) )
  {
LABEL_14:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v5);
    goto LABEL_14;
  }
LABEL_15:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_d(v6[2], 42, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18007ea90  mov     [rsp+arg_8], rbx
0x18007ea95  push    rbp
0x18007ea96  push    rsi
0x18007ea97  push    rdi
0x18007ea98  sub     rsp, 20h
0x18007ea9c  mov     rdi, rcx
0x18007ea9f  mov     [rsp+38h+arg_18], 0
0x18007eaa8  mov     [rsp+38h+arg_0], 0
0x18007eab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eab7  lea     rbp, WPP_GLOBAL_Control
0x18007eabe  cmp     rcx, rbp
0x18007eac1  jz      short loc_18007EADE
0x18007eac3  test    byte ptr [rcx+1Ch], 1
0x18007eac7  jz      short loc_18007EADE
0x18007eac9  mov     rcx, [rcx+10h]
0x18007eacd  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007ead4  mov     edx, 27h ; '''
0x18007ead9  call    WPP_SF_
0x18007eade  mov     rdi, [rdi+40h]
0x18007eae2  lea     rsi, [rdi+18h]
0x18007eae6  mov     rcx, rsi
0x18007eae9  call    cs:__imp_AcquireReadLock
0x18007eaf0  nop     dword ptr [rax+rax+00h]
0x18007eaf5  mov     rcx, [rdi+120h]
0x18007eafc  test    rcx, rcx
0x18007eaff  jnz     short loc_18007EB3E
0x18007eb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb08  cmp     rcx, rbp
0x18007eb0b  jz      short loc_18007EB28
0x18007eb0d  test    byte ptr [rcx+1Ch], 2
0x18007eb11  jz      short loc_18007EB28
0x18007eb13  mov     rcx, [rcx+10h]
0x18007eb17  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007eb1e  mov     edx, 28h ; '('
0x18007eb23  call    WPP_SF_
0x18007eb28  mov     rcx, rsi
0x18007eb2b  mov     ebx, 139Fh
0x18007eb30  call    cs:__imp_ReleaseReadLock
0x18007eb37  nop     dword ptr [rax+rax+00h]
0x18007eb3c  jmp     short loc_18007EBB1
0x18007eb3e  mov     rax, cs:qword_1800BB5A8
0x18007eb45  lea     r8, [rsp+38h+arg_0]
0x18007eb4a  lea     rdx, [rsp+38h+arg_18]
0x18007eb4f  xor     ebx, ebx
0x18007eb51  mov     rax, [rax+28h]
0x18007eb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb5a  mov     rcx, rsi
0x18007eb5d  call    cs:__imp_ReleaseReadLock
0x18007eb64  nop     dword ptr [rax+rax+00h]
0x18007eb69  mov     rdx, [rsp+38h+arg_18]
0x18007eb6e  test    rdx, rdx
0x18007eb71  jz      short loc_18007EBB1
0x18007eb73  movzx   r8d, word ptr [rsp+38h+arg_0]
0x18007eb79  mov     rcx, rdi
0x18007eb7c  call    PktSendEap
0x18007eb81  mov     ebx, eax
0x18007eb83  test    eax, eax
0x18007eb85  jz      short loc_18007EBB1
0x18007eb87  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb8e  cmp     rcx, rbp
0x18007eb91  jz      short loc_18007EBDB
0x18007eb93  test    byte ptr [rcx+1Ch], 2
0x18007eb97  jz      short loc_18007EBB8
0x18007eb99  mov     rcx, [rcx+10h]
0x18007eb9d  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007eba4  mov     edx, 29h ; ')'
0x18007eba9  mov     r9d, eax
0x18007ebac  call    WPP_SF_d
0x18007ebb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ebb8  cmp     rcx, rbp
0x18007ebbb  jz      short loc_18007EBDB
0x18007ebbd  test    byte ptr [rcx+1Ch], 1
0x18007ebc1  jz      short loc_18007EBDB
0x18007ebc3  mov     rcx, [rcx+10h]
0x18007ebc7  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007ebce  mov     edx, 2Ah ; '*'
0x18007ebd3  mov     r9d, ebx
0x18007ebd6  call    WPP_SF_d
0x18007ebdb  mov     eax, ebx
0x18007ebdd  mov     rbx, [rsp+38h+arg_8]
0x18007ebe2  add     rsp, 20h
0x18007ebe6  pop     rdi
0x18007ebe7  pop     rsi
0x18007ebe8  pop     rbp
0x18007ebe9  retn
```
