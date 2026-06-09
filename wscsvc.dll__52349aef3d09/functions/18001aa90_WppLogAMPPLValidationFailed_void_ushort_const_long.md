# WppLogAMPPLValidationFailed(void *,ushort const *,long)

- ea: `0x18001aa90`
- end: `0x18001aba2`
- name: `?WppLogAMPPLValidationFailed@@YAJPEAXPEBGJ@Z`
- size: `274`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180031cd0`

## callees

- `0x180008e48`
- `0x180019e00`
- `0x18001aa90`
- `0x18001abb0`
- `0x180029e74`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001aafe`
- `RPCRT4!RpcRevertToSelf` at `0x18001aafe`
- `RPCRT4!RpcImpersonateClient` at `0x18001aaa8`
- `RPCRT4!RpcImpersonateClient` at `0x18001aaa8`
- `RPCRT4!RpcRaiseException` at `0x18001aae8`
- `RPCRT4!RpcRaiseException` at `0x18001aae8`

## pseudocode

```c
__int64 __fastcall WppLogAMPPLValidationFailed(void *a1, const unsigned __int16 *a2)
{
  int v2; // ebp
  unsigned int v4; // eax
  int CallerProcessPath; // esi
  unsigned int v6; // eax
  int v7; // edx
  int v8; // r8d
  CThirdPartyManager *v9; // rcx
  void *v10; // rdi
  void *Block; // [rsp+78h] [rbp+20h] BYREF

  v2 = (int)a2;
  Block = 0;
  v4 = RpcImpersonateClient(a1);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v4);
    }
    RpcRaiseException(5);
  }
  CallerProcessPath = CSecurityVerificationManager::GetCallerProcessPath(a1, (unsigned __int16 **)&Block);
  v6 = RpcRevertToSelf();
  if ( !v6 )
    goto LABEL_10;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v6);
LABEL_10:
    v9 = WPP_GLOBAL_Control;
  }
  if ( CallerProcessPath >= 0 )
  {
    v10 = Block;
    if ( v9 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_SSl(*((_QWORD *)v9 + 2), v7, v8, v2, (__int64)Block);
    if ( v10 )
      operator delete(v10);
  }
  else if ( v9 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 2), 190, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, (unsigned int)CallerProcessPath);
  }
  return (unsigned int)CallerProcessPath;
}

```

## disassembly

```asm
0x18001aa90  push    rbx
0x18001aa92  push    rbp
0x18001aa93  push    rsi
0x18001aa94  push    rdi
0x18001aa95  sub     rsp, 38h
0x18001aa99  mov     rbp, rdx
0x18001aa9c  mov     [rsp+58h+Block], 0
0x18001aaa5  mov     rbx, rcx
0x18001aaa8  call    cs:__imp_RpcImpersonateClient
0x18001aaae  test    eax, eax
0x18001aab0  jz      short loc_18001AAEF
0x18001aab2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aab9  lea     rbx, WPP_GLOBAL_Control
0x18001aac0  cmp     rcx, rbx
0x18001aac3  jz      short loc_18001AAE3
0x18001aac5  test    byte ptr [rcx+1Ch], 1
0x18001aac9  jz      short loc_18001AAE3
0x18001aacb  mov     rcx, [rcx+10h]
0x18001aacf  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001aad6  mov     edx, 1Bh
0x18001aadb  mov     r9d, eax
0x18001aade  call    WPP_SF_d
0x18001aae3  mov     ecx, 5; exception
0x18001aae8  call    cs:__imp_RpcRaiseException
0x18001aaee  int     3; Trap to Debugger
0x18001aaef  lea     rdx, [rsp+58h+Block]; unsigned __int16 **
0x18001aaf4  mov     rcx, rbx; void *
0x18001aaf7  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x18001aafc  mov     esi, eax
0x18001aafe  call    cs:__imp_RpcRevertToSelf
0x18001ab04  lea     rbx, WPP_GLOBAL_Control
0x18001ab0b  test    eax, eax
0x18001ab0d  jz      short loc_18001AB39
0x18001ab0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab16  cmp     rcx, rbx
0x18001ab19  jz      short loc_18001AB40
0x18001ab1b  test    byte ptr [rcx+1Ch], 1
0x18001ab1f  jz      short loc_18001AB40
0x18001ab21  mov     rcx, [rcx+10h]
0x18001ab25  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001ab2c  mov     edx, 1Ch
0x18001ab31  mov     r9d, eax
0x18001ab34  call    WPP_SF_d
0x18001ab39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab40  test    esi, esi
0x18001ab42  jns     short loc_18001AB69
0x18001ab44  cmp     rcx, rbx
0x18001ab47  jz      short loc_18001AB97
0x18001ab49  test    byte ptr [rcx+1Ch], 1
0x18001ab4d  jz      short loc_18001AB97
0x18001ab4f  mov     rcx, [rcx+10h]
0x18001ab53  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x18001ab5a  mov     edx, 0BEh
0x18001ab5f  mov     r9d, esi
0x18001ab62  call    WPP_SF_d
0x18001ab67  jmp     short loc_18001AB97
0x18001ab69  mov     rdi, [rsp+58h+Block]
0x18001ab6e  cmp     rcx, rbx
0x18001ab71  jz      short loc_18001AB8A
0x18001ab73  test    byte ptr [rcx+1Ch], 1
0x18001ab77  jz      short loc_18001AB8A
0x18001ab79  mov     rcx, [rcx+10h]
0x18001ab7d  mov     r9, rbp
0x18001ab80  mov     [rsp+58h+var_38], rdi
0x18001ab85  call    WPP_SF_SSl
0x18001ab8a  test    rdi, rdi
0x18001ab8d  jz      short loc_18001AB97
0x18001ab8f  mov     rcx, rdi; Block
0x18001ab92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab97  mov     eax, esi
0x18001ab99  add     rsp, 38h
0x18001ab9d  pop     rdi
0x18001ab9e  pop     rsi
0x18001ab9f  pop     rbp
0x18001aba0  pop     rbx
0x18001aba1  retn
```
