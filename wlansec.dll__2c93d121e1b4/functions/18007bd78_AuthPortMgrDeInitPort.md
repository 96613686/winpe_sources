# AuthPortMgrDeInitPort

- ea: `0x18007bd78`
- end: `0x18007bef3`
- name: `AuthPortMgrDeInitPort`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007c15c`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007bd78`
- `0x18007c5d0`
- `0x180096010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007be2d`
- `MobileNetworking!ReleaseWriteLock` at `0x18007be2d`
- `MobileNetworking!AcquireWriteLock` at `0x18007bdfc`
- `MobileNetworking!AcquireWriteLock` at `0x18007bdfc`
- `MobileNetworking!DeleteReadWriteLock` at `0x18007be8d`
- `MobileNetworking!DeleteReadWriteLock` at `0x18007be8d`

## pseudocode

```c
__int64 __fastcall AuthPortMgrDeInitPort(__int64 a1)
{
  unsigned int v1; // edi
  PVOID *v3; // rcx
  __int64 v4; // rbp
  __int64 result; // rax
  PVOID *v6; // rcx

  v1 = *(_DWORD *)(a1 + 132);
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_d(v3[2], 24, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v1);
  }
  AcquireWriteLock(a1, a1 + 24, "AuthPortMgrDeInitPort", 198);
  v4 = *(_QWORD *)(a1 + 288);
  *(_QWORD *)(a1 + 288) = 0;
  ReleaseWriteLock(a1, a1 + 24, "AuthPortMgrDeInitPort", 201);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v1);
    (*(void (__fastcall **)(__int64, __int64))(qword_1800BB5A8 + 24))(v4, a1 + 296);
  }
  SMDeInitStateMachine(a1 + 136);
  result = DeleteReadWriteLock(a1 + 24);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, v1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      return WPP_SF_d(v6[2], 27, &WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18007bd78  push    rbx
0x18007bd7a  push    rbp
0x18007bd7b  push    rsi
0x18007bd7c  push    rdi
0x18007bd7d  push    r12
0x18007bd7f  push    r15
0x18007bd81  sub     rsp, 28h
0x18007bd85  mov     edi, [rcx+84h]
0x18007bd8b  mov     rbx, rcx
0x18007bd8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd95  lea     r15, WPP_GLOBAL_Control
0x18007bd9c  lea     r12, WPP_df62bc39d3fa3f55037d899eae87dea3_Traceguids
0x18007bda3  cmp     rcx, r15
0x18007bda6  jz      short loc_18007BDE5
0x18007bda8  test    byte ptr [rcx+1Ch], 1
0x18007bdac  jz      short loc_18007BDC6
0x18007bdae  mov     rcx, [rcx+10h]
0x18007bdb2  mov     edx, 17h
0x18007bdb7  mov     r8, r12
0x18007bdba  call    WPP_SF_
0x18007bdbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bdc6  cmp     rcx, r15
0x18007bdc9  jz      short loc_18007BDE5
0x18007bdcb  test    byte ptr [rcx+1Ch], 1
0x18007bdcf  jz      short loc_18007BDE5
0x18007bdd1  mov     rcx, [rcx+10h]
0x18007bdd5  mov     edx, 18h
0x18007bdda  mov     r9d, edi
0x18007bddd  mov     r8, r12
0x18007bde0  call    WPP_SF_d
0x18007bde5  lea     rsi, [rbx+18h]
0x18007bde9  mov     r9d, 0C6h
0x18007bdef  mov     rdx, rsi
0x18007bdf2  lea     r8, aAuthportmgrdei; "AuthPortMgrDeInitPort"
0x18007bdf9  mov     rcx, rbx
0x18007bdfc  call    cs:__imp_AcquireWriteLock
0x18007be03  nop     dword ptr [rax+rax+00h]
0x18007be08  mov     rbp, [rbx+120h]
0x18007be0f  lea     r8, aAuthportmgrdei; "AuthPortMgrDeInitPort"
0x18007be16  mov     r9d, 0C9h
0x18007be1c  mov     qword ptr [rbx+120h], 0
0x18007be27  mov     rdx, rsi
0x18007be2a  mov     rcx, rbx
0x18007be2d  call    cs:__imp_ReleaseWriteLock
0x18007be34  nop     dword ptr [rax+rax+00h]
0x18007be39  test    rbp, rbp
0x18007be3c  jz      short loc_18007BE7E
0x18007be3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007be45  cmp     rcx, r15
0x18007be48  jz      short loc_18007BE64
0x18007be4a  test    byte ptr [rcx+1Ch], 1
0x18007be4e  jz      short loc_18007BE64
0x18007be50  mov     rcx, [rcx+10h]
0x18007be54  mov     edx, 19h
0x18007be59  mov     r9d, edi
0x18007be5c  mov     r8, r12
0x18007be5f  call    WPP_SF_d
0x18007be64  mov     rax, cs:qword_1800BB5A8
0x18007be6b  lea     rdx, [rbx+128h]
0x18007be72  mov     rcx, rbp
0x18007be75  mov     rax, [rax+18h]
0x18007be79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be7e  lea     rcx, [rbx+88h]
0x18007be85  call    SMDeInitStateMachine
0x18007be8a  mov     rcx, rsi
0x18007be8d  call    cs:__imp_DeleteReadWriteLock
0x18007be94  nop     dword ptr [rax+rax+00h]
0x18007be99  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bea0  cmp     rcx, r15
0x18007bea3  jz      short loc_18007BEE5
0x18007bea5  test    byte ptr [rcx+1Ch], 1
0x18007bea9  jz      short loc_18007BEC6
0x18007beab  mov     rcx, [rcx+10h]
0x18007beaf  mov     edx, 1Ah
0x18007beb4  mov     r9d, edi
0x18007beb7  mov     r8, r12
0x18007beba  call    WPP_SF_d
0x18007bebf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bec6  cmp     rcx, r15
0x18007bec9  jz      short loc_18007BEE5
0x18007becb  test    byte ptr [rcx+1Ch], 1
0x18007becf  jz      short loc_18007BEE5
0x18007bed1  mov     rcx, [rcx+10h]
0x18007bed5  mov     edx, 1Bh
0x18007beda  xor     r9d, r9d
0x18007bedd  mov     r8, r12
0x18007bee0  call    WPP_SF_d
0x18007bee5  add     rsp, 28h
0x18007bee9  pop     r15
0x18007beeb  pop     r12
0x18007beed  pop     rdi
0x18007beee  pop     rsi
0x18007beef  pop     rbp
0x18007bef0  pop     rbx
0x18007bef1  retn
```
