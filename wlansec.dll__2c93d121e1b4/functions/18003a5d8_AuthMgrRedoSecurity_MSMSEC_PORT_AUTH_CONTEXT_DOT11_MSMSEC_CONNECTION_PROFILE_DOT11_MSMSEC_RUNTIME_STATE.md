# AuthMgrRedoSecurity(MSMSEC_PORT_AUTH_CONTEXT *,DOT11_MSMSEC_CONNECTION_PROFILE *,DOT11_MSMSEC_RUNTIME_STATE *)

- ea: `0x18003a5d8`
- end: `0x18003a868`
- name: `?AuthMgrRedoSecurity@@YAKPEAUMSMSEC_PORT_AUTH_CONTEXT@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUDOT11_MSMSEC_RUNTIME_STATE@@@Z`
- size: `656`
- prototype: `unsigned int(struct MSMSEC_PORT_AUTH_CONTEXT *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, struct DOT11_MSMSEC_RUNTIME_STATE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a48c`
- `0x1800540d0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c444`
- `0x1800262ac`
- `0x18002bb08`
- `0x18003a5d8`
- `0x180096010`

## import_xrefs

- `OneX!OneXStartAuthentication` at `0x18003a710`
- `OneX!OneXStartAuthentication` at `0x18003a710`
- `OneX!OneXStopAuthentication` at `0x18003a661`
- `OneX!OneXStopAuthentication` at `0x18003a661`
- `MobileNetworking!ReleaseWriteLock` at `0x18003a821`
- `MobileNetworking!ReleaseWriteLock` at `0x18003a821`
- `MobileNetworking!AcquireWriteLock` at `0x18003a7cb`
- `MobileNetworking!AcquireWriteLock` at `0x18003a7cb`

## string_xrefs

- `0x18003a7c1`: `AuthMgrRedoSecurity`
- `0x18003a814`: `AuthMgrRedoSecurity`

## pseudocode

```c
__int64 __fastcall AuthMgrRedoSecurity(
        struct MSMSEC_PORT_AUTH_CONTEXT *a1,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a2,
        struct DOT11_MSMSEC_RUNTIME_STATE *a3)
{
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned __int32 v11; // eax
  __int64 v12; // r8
  char *v13; // rdi

  v6 = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 165, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)a1 + 1) )
    goto LABEL_31;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 2) != 0 )
    WPP_SF_(v7[7], 166, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  v8 = OneXStopAuthentication(1, *((_QWORD *)a1 + 1));
  if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 167, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v8);
  v9 = AuthMgrPreConnectConfigureOneX(
         *((void **)a1 + 1),
         *((_DWORD *)a2 + 10),
         *((void **)a2 + 6),
         a3,
         **((_DWORD **)a2 + 3) == 8);
  v6 = v9;
  if ( !v9 )
  {
    v11 = _InterlockedExchangeAdd((volatile signed __int32 *)&qword_1800AEFB0, 1u);
    v12 = *((_QWORD *)a1 + 1);
    *((_DWORD *)a1 + 4) = ++v11;
    v9 = OneXStartAuthentication(1, v11, v12, 0);
    v6 = v9;
    if ( v9 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_31;
      v10 = 169;
    }
    else
    {
      v13 = (char *)a1 - 920;
      v9 = CreateAndQueuePortEvent(v13, 13, 1);
      v6 = v9;
      if ( !v9 )
      {
        if ( *((_QWORD *)v13 + 36) && *((_DWORD *)v13 + 77) == 1 )
        {
          TracePortId(*((_DWORD *)v13 + 78), ">>> Locking >>>");
          AcquireWriteLock(v13, v13 + 320, "AuthMgrRedoSecurity", 1806);
          if ( !(*((unsigned int (__fastcall **)(__int64, __int64, _QWORD))v13 + 36))(*((_QWORD *)v13 + 3) + 32LL, 1, 0) )
            ++*((_DWORD *)v13 + 506);
          TracePortId(*((_DWORD *)v13 + 78), "<<< Unlocking <<<");
          ReleaseWriteLock(v13, v13 + 320, "AuthMgrRedoSecurity", 1820);
        }
        goto LABEL_30;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_31;
      v10 = 170;
    }
LABEL_16:
    WPP_SF_d(v7[7], v10, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v9);
LABEL_30:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v10 = 168;
    goto LABEL_16;
  }
LABEL_31:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_d(v7[7], 171, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18003a5d8  push    rbx
0x18003a5da  push    rbp
0x18003a5db  push    rsi
0x18003a5dc  push    rdi
0x18003a5dd  push    r12
0x18003a5df  push    r14
0x18003a5e1  push    r15
0x18003a5e3  sub     rsp, 30h
0x18003a5e7  mov     rbp, r8
0x18003a5ea  mov     rsi, rdx
0x18003a5ed  mov     rdi, rcx
0x18003a5f0  xor     ebx, ebx
0x18003a5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a5f9  lea     r15, WPP_GLOBAL_Control
0x18003a600  lea     r12, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x18003a607  cmp     rcx, r15
0x18003a60a  jz      short loc_18003A62D
0x18003a60c  test    dword ptr [rcx+44h], 100h
0x18003a613  jz      short loc_18003A62D
0x18003a615  mov     rcx, [rcx+38h]
0x18003a619  mov     edx, 0A5h
0x18003a61e  mov     r8, r12
0x18003a621  call    WPP_SF_
0x18003a626  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a62d  cmp     [rdi+8], rbx
0x18003a631  jz      loc_18003A834
0x18003a637  cmp     rcx, r15
0x18003a63a  jz      short loc_18003A653
0x18003a63c  test    byte ptr [rcx+44h], 2
0x18003a640  jz      short loc_18003A653
0x18003a642  mov     rcx, [rcx+38h]
0x18003a646  mov     edx, 0A6h
0x18003a64b  mov     r8, r12
0x18003a64e  call    WPP_SF_
0x18003a653  mov     rdx, [rdi+8]
0x18003a657  xor     r8d, r8d
0x18003a65a  lea     r14d, [r8+1]
0x18003a65e  mov     ecx, r14d
0x18003a661  call    cs:__imp_OneXStopAuthentication
0x18003a668  nop     dword ptr [rax+rax+00h]
0x18003a66d  test    eax, eax
0x18003a66f  jz      short loc_18003A697
0x18003a671  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a678  cmp     rcx, r15
0x18003a67b  jz      short loc_18003A697
0x18003a67d  test    [rcx+44h], r14b
0x18003a681  jz      short loc_18003A697
0x18003a683  mov     rcx, [rcx+38h]
0x18003a687  mov     edx, 0A7h
0x18003a68c  mov     r9d, eax
0x18003a68f  mov     r8, r12
0x18003a692  call    WPP_SF_d
0x18003a697  mov     rax, [rsi+18h]
0x18003a69b  xor     ecx, ecx
0x18003a69d  mov     r8, [rsi+30h]; void *
0x18003a6a1  mov     r9, rbp; struct DOT11_MSMSEC_RUNTIME_STATE *
0x18003a6a4  mov     edx, [rsi+28h]; unsigned int
0x18003a6a7  cmp     dword ptr [rax], 8
0x18003a6aa  setz    cl
0x18003a6ad  mov     [rsp+68h+var_48], ecx; int
0x18003a6b1  mov     rcx, [rdi+8]; void *
0x18003a6b5  call    ?AuthMgrPreConnectConfigureOneX@@YAKPEAXK0PEAUDOT11_MSMSEC_RUNTIME_STATE@@H@Z; AuthMgrPreConnectConfigureOneX(void *,ulong,void *,DOT11_MSMSEC_RUNTIME_STATE *,int)
0x18003a6ba  mov     ebx, eax
0x18003a6bc  test    eax, eax
0x18003a6be  jz      short loc_18003A6F3
0x18003a6c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6c7  cmp     rcx, r15
0x18003a6ca  jz      loc_18003A856
0x18003a6d0  test    [rcx+44h], r14b
0x18003a6d4  jz      loc_18003A834
0x18003a6da  mov     edx, 0A8h
0x18003a6df  mov     rcx, [rcx+38h]
0x18003a6e3  mov     r9d, eax
0x18003a6e6  mov     r8, r12
0x18003a6e9  call    WPP_SF_d
0x18003a6ee  jmp     loc_18003A82D
0x18003a6f3  mov     eax, r14d
0x18003a6f6  lock xadd dword ptr cs:qword_1800AEFB0, eax
0x18003a6fe  mov     r8, [rdi+8]
0x18003a702  add     eax, r14d
0x18003a705  mov     edx, eax
0x18003a707  xor     r9d, r9d
0x18003a70a  mov     ecx, r14d
0x18003a70d  mov     [rdi+10h], eax
0x18003a710  call    cs:__imp_OneXStartAuthentication
0x18003a717  nop     dword ptr [rax+rax+00h]
0x18003a71c  mov     ebx, eax
0x18003a71e  test    eax, eax
0x18003a720  jz      short loc_18003A743
0x18003a722  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a729  cmp     rcx, r15
0x18003a72c  jz      loc_18003A856
0x18003a732  test    [rcx+44h], r14b
0x18003a736  jz      loc_18003A834
0x18003a73c  mov     edx, 0A9h
0x18003a741  jmp     short loc_18003A6DF
0x18003a743  add     rdi, 0FFFFFFFFFFFFFC68h
0x18003a74a  mov     r8d, r14d
0x18003a74d  mov     rcx, rdi
0x18003a750  mov     edx, 0Dh
0x18003a755  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x18003a75a  mov     ebx, eax
0x18003a75c  test    eax, eax
0x18003a75e  jz      short loc_18003A784
0x18003a760  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a767  cmp     rcx, r15
0x18003a76a  jz      loc_18003A856
0x18003a770  test    [rcx+44h], r14b
0x18003a774  jz      loc_18003A834
0x18003a77a  mov     edx, 0AAh
0x18003a77f  jmp     loc_18003A6DF
0x18003a784  cmp     qword ptr [rdi+120h], 0
0x18003a78c  jz      loc_18003A82D
0x18003a792  cmp     [rdi+134h], r14d
0x18003a799  jnz     loc_18003A82D
0x18003a79f  mov     ecx, [rdi+138h]; unsigned int
0x18003a7a5  lea     rdx, aLocking; ">>> Locking >>>"
0x18003a7ac  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18003a7b1  lea     rsi, [rdi+140h]
0x18003a7b8  mov     r9d, 70Eh
0x18003a7be  mov     rdx, rsi
0x18003a7c1  lea     r8, aAuthmgrredosec; "AuthMgrRedoSecurity"
0x18003a7c8  mov     rcx, rdi
0x18003a7cb  call    cs:__imp_AcquireWriteLock
0x18003a7d2  nop     dword ptr [rax+rax+00h]
0x18003a7d7  mov     rcx, [rdi+18h]
0x18003a7db  xor     r8d, r8d
0x18003a7de  mov     rax, [rdi+120h]
0x18003a7e5  add     rcx, 20h ; ' '
0x18003a7e9  mov     edx, r14d
0x18003a7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f1  test    eax, eax
0x18003a7f3  jnz     short loc_18003A7FC
0x18003a7f5  add     [rdi+7E8h], r14d
0x18003a7fc  mov     ecx, [rdi+138h]; unsigned int
0x18003a802  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003a809  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18003a80e  mov     r9d, 71Ch
0x18003a814  lea     r8, aAuthmgrredosec; "AuthMgrRedoSecurity"
0x18003a81b  mov     rdx, rsi
0x18003a81e  mov     rcx, rdi
0x18003a821  call    cs:__imp_ReleaseWriteLock
0x18003a828  nop     dword ptr [rax+rax+00h]
0x18003a82d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a834  cmp     rcx, r15
0x18003a837  jz      short loc_18003A856
0x18003a839  test    dword ptr [rcx+44h], 100h
0x18003a840  jz      short loc_18003A856
0x18003a842  mov     rcx, [rcx+38h]
0x18003a846  mov     edx, 0ABh
0x18003a84b  mov     r9d, ebx
0x18003a84e  mov     r8, r12
0x18003a851  call    WPP_SF_d
0x18003a856  mov     eax, ebx
0x18003a858  add     rsp, 30h
0x18003a85c  pop     r15
0x18003a85e  pop     r14
0x18003a860  pop     r12
0x18003a862  pop     rdi
0x18003a863  pop     rsi
0x18003a864  pop     rbp
0x18003a865  pop     rbx
0x18003a866  retn
```
