# _PROG_RESOURCES::_RegisterBackup(tagComCallData *)

- ea: `0x18000b8f0`
- end: `0x18000ba04`
- name: `?_RegisterBackup@_PROG_RESOURCES@@SAJPEAUtagComCallData@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180012c34`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b944`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b9c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b944`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000b9c3`
- `wbemcomn!GetMemLogObject` at `0x18000b934`
- `wbemcomn!GetMemLogObject` at `0x18000b9b8`
- `wbemcomn!GetMemLogObject` at `0x18000b934`
- `wbemcomn!GetMemLogObject` at `0x18000b9b8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b8fb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000b8fb`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000b9a8`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000b9a8`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::_RegisterBackup(struct tagComCallData *a1)
{
  char *v1; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  HRESULT v8; // eax
  CMemoryLog *v9; // rax

  v1 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
  if ( v1 )
  {
    *(_QWORD *)v1 = &CForwardFactory::`vftable';
    *((_DWORD *)v1 + 2) = 1;
    *(GUID *)(v1 + 12) = CLSID_WbemBackupRestore;
  }
  *(&pUnk + 1) = (LPUNKNOWN)v1;
  if ( !v1 )
  {
    MemLogObject = GetMemLogObject();
    v3 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 12;
    v6 = 2147749894LL;
LABEL_8:
    WPP_SF_d(v4[2], v5, WPP_2716f4bd31e130f967505b342dce5479_Traceguids, v6);
    return v3;
  }
  v8 = CoRegisterClassObject(&CLSID_WbemBackupRestore, (LPUNKNOWN)v1, 0x14u, 1u, &dwRegister + 1);
  v3 = v8;
  if ( v8 )
  {
    if ( v8 < 0 )
    {
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, v3);
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 13;
    v6 = v3;
    goto LABEL_8;
  }
  dword_180032A28 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000b8f0  push    rbx
0x18000b8f2  sub     rsp, 30h
0x18000b8f6  mov     ecx, 20h ; ' '
0x18000b8fb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000b901  mov     [rsp+38h+arg_8], rax
0x18000b906  test    rax, rax
0x18000b909  jz      short loc_18000B928
0x18000b90b  lea     rcx, ??_7CForwardFactory@@6B@; const CForwardFactory::`vftable'
0x18000b912  mov     [rax], rcx
0x18000b915  mov     dword ptr [rax+8], 1
0x18000b91c  movups  xmm0, xmmword ptr cs:CLSID_WbemBackupRestore.Data1
0x18000b923  movdqu  xmmword ptr [rax+0Ch], xmm0
0x18000b928  mov     qword ptr cs:pUnk+8, rax
0x18000b92f  test    rax, rax
0x18000b932  jnz     short loc_18000B988
0x18000b934  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b93a  mov     ebx, 80041006h
0x18000b93f  mov     edx, ebx
0x18000b941  mov     rcx, rax
0x18000b944  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b94a  lea     rax, WPP_GLOBAL_Control
0x18000b951  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b958  cmp     rcx, rax
0x18000b95b  jz      short loc_18000B984
0x18000b95d  test    byte ptr [rcx+1Ch], 1
0x18000b961  jz      short loc_18000B984
0x18000b963  cmp     byte ptr [rcx+19h], 2
0x18000b967  jb      short loc_18000B984
0x18000b969  mov     edx, 0Ch
0x18000b96e  mov     r9d, 80041006h
0x18000b974  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x18000b97b  mov     rcx, [rcx+10h]
0x18000b97f  call    WPP_SF_d
0x18000b984  mov     eax, ebx
0x18000b986  jmp     short loc_18000B9FE
0x18000b988  lea     rcx, dwRegister+4
0x18000b98f  mov     [rsp+38h+lpdwRegister], rcx; lpdwRegister
0x18000b994  mov     r9d, 1; flags
0x18000b99a  lea     r8d, [r9+13h]; dwClsContext
0x18000b99e  mov     rdx, rax; pUnk
0x18000b9a1  lea     rcx, CLSID_WbemBackupRestore; rclsid
0x18000b9a8  call    cs:__imp_CoRegisterClassObject
0x18000b9ae  mov     ebx, eax
0x18000b9b0  test    eax, eax
0x18000b9b2  jz      short loc_18000B9F2
0x18000b9b4  test    eax, eax
0x18000b9b6  jns     short loc_18000B9C9
0x18000b9b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000b9be  mov     edx, ebx
0x18000b9c0  mov     rcx, rax
0x18000b9c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000b9c9  lea     rax, WPP_GLOBAL_Control
0x18000b9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9d7  cmp     rcx, rax
0x18000b9da  jz      short loc_18000B984
0x18000b9dc  test    byte ptr [rcx+1Ch], 1
0x18000b9e0  jz      short loc_18000B984
0x18000b9e2  cmp     byte ptr [rcx+19h], 2
0x18000b9e6  jb      short loc_18000B984
0x18000b9e8  mov     edx, 0Dh
0x18000b9ed  mov     r9d, ebx
0x18000b9f0  jmp     short loc_18000B974
0x18000b9f2  mov     cs:dword_180032A28, 1
0x18000b9fc  xor     eax, eax
0x18000b9fe  add     rsp, 30h
0x18000ba02  pop     rbx
0x18000ba03  retn
```
