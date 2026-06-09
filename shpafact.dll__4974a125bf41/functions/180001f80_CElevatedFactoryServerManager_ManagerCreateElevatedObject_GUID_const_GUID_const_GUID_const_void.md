# CElevatedFactoryServerManager::ManagerCreateElevatedObject(_GUID const &,_GUID const &,_GUID const &,void * *)

- ea: `0x180001f80`
- end: `0x18000204d`
- name: `?ManagerCreateElevatedObject@CElevatedFactoryServerManager@@UEAAJAEBU_GUID@@00PEAPEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(CElevatedFactoryServerManager *__hidden this, const struct _GUID *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001f80`
- `0x1800023cc`
- `0x1800026ac`
- `0x1800026d4`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryServerManager::ManagerCreateElevatedObject(
        CElevatedFactoryServerManager *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  struct IElevatedFactoryServer *v7; // rbx
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  struct IElevatedFactoryServer *v11; // [rsp+30h] [rbp-38h] BYREF

  v11 = 0;
  CElevatedFactoryServerManager::_GetExistingFactory(this, a2, &v11);
  v7 = v11;
  if ( !v11 )
  {
    v9 = WPP_GLOBAL_Control;
    v8 = -2147467259;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_8;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids);
LABEL_7:
    v9 = WPP_GLOBAL_Control;
LABEL_8:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
      WPP_SF_d(v9[2], 17, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids, v8);
    goto LABEL_11;
  }
  v8 = (*(__int64 (__fastcall **)(struct IElevatedFactoryServer *, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v11 + 24LL))(
         v11,
         a3,
         a4,
         a5);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_7;
LABEL_11:
  if ( v7 )
    (*(void (__fastcall **)(struct IElevatedFactoryServer *))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x180001f80  push    rbx
0x180001f82  push    rbp
0x180001f83  push    rsi
0x180001f84  push    rdi
0x180001f85  sub     rsp, 48h
0x180001f89  mov     rsi, r8
0x180001f8c  mov     [rsp+68h+var_38], 0
0x180001f95  lea     r8, [rsp+68h+var_38]; struct IElevatedFactoryServer **
0x180001f9a  mov     rdi, r9
0x180001f9d  call    ?_GetExistingFactory@CElevatedFactoryServerManager@@IEAAXAEBU_GUID@@PEAPEAUIElevatedFactoryServer@@@Z; CElevatedFactoryServerManager::_GetExistingFactory(_GUID const &,IElevatedFactoryServer * *)
0x180001fa2  mov     rbx, [rsp+68h+var_38]
0x180001fa7  lea     rbp, WPP_GLOBAL_Control
0x180001fae  test    rbx, rbx
0x180001fb1  jz      short loc_180001FD8
0x180001fb3  mov     rax, [rbx]
0x180001fb6  mov     r8, rdi
0x180001fb9  mov     r9, [rsp+68h+arg_20]
0x180001fc1  mov     rdx, rsi
0x180001fc4  mov     rcx, rbx
0x180001fc7  mov     rax, [rax+18h]
0x180001fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd0  mov     edi, eax
0x180001fd2  test    eax, eax
0x180001fd4  jns     short loc_18000202E
0x180001fd6  jmp     short loc_180002004
0x180001fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fdf  mov     edi, 80004005h
0x180001fe4  cmp     rcx, rbp
0x180001fe7  jz      short loc_180002042
0x180001fe9  test    byte ptr [rcx+1Ch], 4
0x180001fed  jz      short loc_18000200B
0x180001fef  mov     rcx, [rcx+10h]
0x180001ff3  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180001ffa  mov     edx, 10h
0x180001fff  call    WPP_SF_
0x180002004  mov     rcx, cs:WPP_GLOBAL_Control
0x18000200b  cmp     rcx, rbp
0x18000200e  jz      short loc_18000202E
0x180002010  test    byte ptr [rcx+1Ch], 4
0x180002014  jz      short loc_18000202E
0x180002016  mov     rcx, [rcx+10h]
0x18000201a  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180002021  mov     edx, 11h
0x180002026  mov     r9d, edi
0x180002029  call    WPP_SF_d
0x18000202e  test    rbx, rbx
0x180002031  jz      short loc_180002042
0x180002033  mov     rcx, [rbx]
0x180002036  mov     rax, [rcx+10h]
0x18000203a  mov     rcx, rbx
0x18000203d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002042  mov     eax, edi
0x180002044  add     rsp, 48h
0x180002048  pop     rdi
0x180002049  pop     rsi
0x18000204a  pop     rbp
0x18000204b  pop     rbx
0x18000204c  retn
```
