# CThirdPartyMonitoring::UpdateThirdPartyManager(THIRDPARTYACTION,CDetectoid *)

- ea: `0x180038a1c`
- end: `0x180038ac6`
- name: `?UpdateThirdPartyManager@CThirdPartyMonitoring@@AEAAJW4THIRDPARTYACTION@@PEAVCDetectoid@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a570`
- `0x18000a740`
- `0x18001aee0`
- `0x180038500`

## callees

- `0x180018b60`
- `0x18001c6dc`
- `0x18001fdd8`
- `0x18001fe40`
- `0x180020018`
- `0x180038a1c`

## pseudocode

```c
__int64 __fastcall CThirdPartyMonitoring::UpdateThirdPartyManager(_QWORD *a1, int a2, __int64 a3)
{
  unsigned int v3; // esi
  CThirdPartyManager *v5; // rdi
  int v6; // edx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  int IsAlerted; // eax

  v3 = 1;
  if ( *(_DWORD *)(a3 + 60) == 1 )
  {
    v5 = (CThirdPartyManager *)a1[138];
  }
  else
  {
    v3 = 2;
    if ( *(_DWORD *)(a3 + 60) == 2 )
    {
      v5 = (CThirdPartyManager *)a1[139];
      v3 = 8;
    }
    else
    {
      v5 = (CThirdPartyManager *)a1[137];
    }
  }
  if ( a2 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      if ( v6 == 1 )
        CThirdPartyManager::RemoveExternalProduct(v5, *(struct CExternalBase **)(a3 + 32));
    }
    else
    {
      CThirdPartyManager::UpdateExternalProduct(v5, *(struct CExternalBase **)(a3 + 32));
    }
  }
  else
  {
    CThirdPartyManager::AddExternalProduct(v5, *(struct CExternalBase **)(a3 + 32));
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)a1[140];
  IsAlerted = CThirdPartyManager::IsAlerted(v5);
  CAlertStatus::SetComponentAlerted(v7, v3, IsAlerted);
  return 0;
}

```

## disassembly

```asm
0x180038a1c  mov     [rsp+arg_0], rbx
0x180038a21  mov     [rsp+arg_8], rsi
0x180038a26  push    rdi
0x180038a27  sub     rsp, 20h
0x180038a2b  mov     esi, 1
0x180038a30  mov     rbx, rcx
0x180038a33  cmp     [r8+3Ch], esi
0x180038a37  jnz     short loc_180038A42
0x180038a39  mov     rdi, [rcx+450h]
0x180038a40  jmp     short loc_180038A62
0x180038a42  mov     esi, 2
0x180038a47  cmp     [r8+3Ch], esi
0x180038a4b  jnz     short loc_180038A5B
0x180038a4d  mov     rdi, [rcx+458h]
0x180038a54  mov     esi, 8
0x180038a59  jmp     short loc_180038A62
0x180038a5b  mov     rdi, [rcx+448h]
0x180038a62  test    edx, edx
0x180038a64  jz      short loc_180038A8C
0x180038a66  sub     edx, 1
0x180038a69  jz      short loc_180038A7E
0x180038a6b  cmp     edx, 1
0x180038a6e  jnz     short loc_180038A98
0x180038a70  mov     rdx, [r8+20h]; struct CExternalBase *
0x180038a74  mov     rcx, rdi; this
0x180038a77  call    ?RemoveExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::RemoveExternalProduct(CExternalBase *)
0x180038a7c  jmp     short loc_180038A98
0x180038a7e  mov     rdx, [r8+20h]; struct CExternalBase *
0x180038a82  mov     rcx, rdi; this
0x180038a85  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x180038a8a  jmp     short loc_180038A98
0x180038a8c  mov     rdx, [r8+20h]; struct CExternalBase *
0x180038a90  mov     rcx, rdi; this
0x180038a93  call    ?AddExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::AddExternalProduct(CExternalBase *)
0x180038a98  mov     rbx, [rbx+460h]
0x180038a9f  mov     rcx, rdi; this
0x180038aa2  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180038aa7  mov     r8d, eax; int
0x180038aaa  mov     edx, esi; unsigned int
0x180038aac  mov     rcx, rbx; lpCriticalSection
0x180038aaf  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180038ab4  mov     rbx, [rsp+28h+arg_0]
0x180038ab9  xor     eax, eax
0x180038abb  mov     rsi, [rsp+28h+arg_8]
0x180038ac0  add     rsp, 20h
0x180038ac4  pop     rdi
0x180038ac5  retn
```
