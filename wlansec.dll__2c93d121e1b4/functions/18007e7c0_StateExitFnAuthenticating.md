# StateExitFnAuthenticating

- ea: `0x18007e7c0`
- end: `0x18007e8f1`
- name: `StateExitFnAuthenticating`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b3e0`
- `0x18007e7c0`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007e88e`
- `MobileNetworking!ReleaseWriteLock` at `0x18007e88e`
- `MobileNetworking!AcquireWriteLock` at `0x18007e85c`
- `MobileNetworking!AcquireWriteLock` at `0x18007e85c`

## pseudocode

```c
__int64 __fastcall StateExitFnAuthenticating(__int64 a1)
{
  __int64 v2; // rsi
  unsigned int v3; // eax
  unsigned int v4; // edi
  PVOID *v5; // rcx
  __int64 v6; // rbp

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids);
  v2 = *(_QWORD *)(a1 + 64);
  v3 = TmChangeTimer(*(HANDLE *)(a1 + 120), 0x7FFFFFFFu);
  v4 = v3;
  if ( !v3 )
  {
    AcquireWriteLock(v2, v2 + 24, "StateExitFnAuthenticating", 279);
    v6 = *(_QWORD *)(v2 + 288);
    *(_QWORD *)(v2 + 288) = 0;
    ReleaseWriteLock(v2, v2 + 24, "StateExitFnAuthenticating", 282);
    if ( v6 )
      (*(void (__fastcall **)(__int64, __int64))(qword_1800BB5A8 + 24))(v6, v2 + 296);
    goto LABEL_10;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v3);
LABEL_10:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_d(v5[2], 34, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18007e7c0  push    rbx
0x18007e7c2  push    rbp
0x18007e7c3  push    rsi
0x18007e7c4  push    rdi
0x18007e7c5  push    r14
0x18007e7c7  sub     rsp, 20h
0x18007e7cb  mov     rbx, rcx
0x18007e7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e7d5  lea     r14, WPP_GLOBAL_Control
0x18007e7dc  cmp     rcx, r14
0x18007e7df  jz      short loc_18007E7FC
0x18007e7e1  test    byte ptr [rcx+1Ch], 1
0x18007e7e5  jz      short loc_18007E7FC
0x18007e7e7  mov     rcx, [rcx+10h]
0x18007e7eb  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007e7f2  mov     edx, 20h ; ' '
0x18007e7f7  call    WPP_SF_
0x18007e7fc  mov     rcx, [rbx+78h]; Timer
0x18007e800  mov     edx, 7FFFFFFFh; DueTime
0x18007e805  mov     rsi, [rbx+40h]
0x18007e809  call    TmChangeTimer
0x18007e80e  mov     edi, eax
0x18007e810  test    eax, eax
0x18007e812  jz      short loc_18007E848
0x18007e814  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e81b  cmp     rcx, r14
0x18007e81e  jz      loc_18007E8E3
0x18007e824  test    byte ptr [rcx+1Ch], 2
0x18007e828  jz      loc_18007E8C0
0x18007e82e  mov     rcx, [rcx+10h]
0x18007e832  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007e839  mov     edx, 21h ; '!'
0x18007e83e  mov     r9d, eax
0x18007e841  call    WPP_SF_d
0x18007e846  jmp     short loc_18007E8B9
0x18007e848  mov     r9d, 117h
0x18007e84e  lea     r8, aStateexitfnaut; "StateExitFnAuthenticating"
0x18007e855  lea     rdx, [rsi+18h]
0x18007e859  mov     rcx, rsi
0x18007e85c  call    cs:__imp_AcquireWriteLock
0x18007e863  nop     dword ptr [rax+rax+00h]
0x18007e868  mov     rbp, [rsi+120h]
0x18007e86f  lea     r8, aStateexitfnaut; "StateExitFnAuthenticating"
0x18007e876  mov     r9d, 11Ah
0x18007e87c  mov     qword ptr [rsi+120h], 0
0x18007e887  lea     rdx, [rsi+18h]
0x18007e88b  mov     rcx, rsi
0x18007e88e  call    cs:__imp_ReleaseWriteLock
0x18007e895  nop     dword ptr [rax+rax+00h]
0x18007e89a  test    rbp, rbp
0x18007e89d  jz      short loc_18007E8B9
0x18007e89f  mov     rax, cs:qword_1800BB5A8
0x18007e8a6  lea     rdx, [rsi+128h]
0x18007e8ad  mov     rcx, rbp
0x18007e8b0  mov     rax, [rax+18h]
0x18007e8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e8c0  cmp     rcx, r14
0x18007e8c3  jz      short loc_18007E8E3
0x18007e8c5  test    byte ptr [rcx+1Ch], 1
0x18007e8c9  jz      short loc_18007E8E3
0x18007e8cb  mov     rcx, [rcx+10h]
0x18007e8cf  lea     r8, WPP_87a55f4cd6b03852b7487db516ff9926_Traceguids
0x18007e8d6  mov     edx, 22h ; '"'
0x18007e8db  mov     r9d, edi
0x18007e8de  call    WPP_SF_d
0x18007e8e3  mov     eax, edi
0x18007e8e5  add     rsp, 20h
0x18007e8e9  pop     r14
0x18007e8eb  pop     rdi
0x18007e8ec  pop     rsi
0x18007e8ed  pop     rbp
0x18007e8ee  pop     rbx
0x18007e8ef  retn
```
