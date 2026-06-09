# ScExtpTriggerArrived(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)

- ea: `0x140018b50`
- end: `0x140018d7f`
- name: `?ScExtpTriggerArrived@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z`
- size: `559`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003e54`
- `0x1400188fc`
- `0x140018b50`
- `0x140018d90`
- `0x140019014`
- `0x1400575b0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140018bfc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x140018bfc`
- `ntdll!RtlReleaseSRWLockShared` at `0x140018c35`
- `ntdll!RtlReleaseSRWLockShared` at `0x140018c35`
- `ntdll!RtlAcquireSRWLockShared` at `0x140018bc1`
- `ntdll!RtlAcquireSRWLockShared` at `0x140018bc1`
- `EventAggregation!EAQueryAggregateEventData` at `0x140018bb0`
- `EventAggregation!EAQueryAggregateEventData` at `0x140018be2`
- `EventAggregation!EAQueryAggregateEventData` at `0x140018bb0`
- `EventAggregation!EAQueryAggregateEventData` at `0x140018be2`

## pseudocode

```c
__int64 __fastcall ScExtpTriggerArrived(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 result; // rax
  __int64 *i; // rsi
  int v8; // eax
  unsigned int v9; // eax
  _OWORD Source2[3]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v11; // [rsp+60h] [rbp-11h]
  _OWORD Source1[3]; // [rsp+68h] [rbp-9h] BYREF
  __int64 v13; // [rsp+98h] [rbp+27h]

  result = 0;
  v13 = 0;
  v11 = 0;
  memset(Source1, 0, sizeof(Source1));
  memset(Source2, 0, sizeof(Source2));
  if ( a4 && a5 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      return WPP_SF_S(
               WPP_GLOBAL_Control->StubInfo,
               90,
               WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
               *(_QWORD *)(a3 + 24));
  }
  else
  {
    result = EAQueryAggregateEventData(a1, Source1);
    if ( (_DWORD)result )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        return WPP_SF_Sd(
                 WPP_GLOBAL_Control->StubInfo,
                 91,
                 (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
                 *(_QWORD *)(a3 + 24),
                 result);
    }
    else
    {
      RtlAcquireSRWLockShared(a3);
      for ( i = *(__int64 **)(a3 + 32); i != (__int64 *)(a3 + 32); i = (__int64 *)*i )
      {
        v8 = EAQueryAggregateEventData(i[3], Source2);
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              92,
              (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
              *(_QWORD *)(a3 + 24),
              v8);
          }
        }
        else if ( RtlCompareMemory(Source1, Source2, 8u) == 8 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_SLd(
              WPP_GLOBAL_Control->StubInfo,
              93,
              (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
              *(_QWORD *)(a3 + 24),
              *((_DWORD *)i + 16),
              *((_DWORD *)i + 4));
          }
          v9 = ScExtpExecuteTriggerAction((struct _SERVICE_TRIGGER_SUBSCRIPTION *)i, *(unsigned __int16 **)(a3 + 24));
          if ( v9
            && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->StubInfo,
              94,
              (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
              *(_QWORD *)(a3 + 24),
              v9);
          }
          return RtlReleaseSRWLockShared(a3);
        }
      }
      return RtlReleaseSRWLockShared(a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018b50  mov     [rsp-8+arg_8], rbx
0x140018b55  mov     [rsp-8+arg_18], rsi
0x140018b5a  push    rbp
0x140018b5b  push    rdi
0x140018b5c  push    r14
0x140018b5e  lea     rbp, [rsp-3Fh]
0x140018b63  sub     rsp, 0B0h
0x140018b6a  mov     rax, cs:__security_cookie
0x140018b71  xor     rax, rsp
0x140018b74  mov     [rbp+4Fh+var_20], rax
0x140018b78  xor     eax, eax
0x140018b7a  xorps   xmm0, xmm0
0x140018b7d  mov     [rbp+4Fh+var_28], rax
0x140018b81  xorps   xmm1, xmm1
0x140018b84  mov     [rbp+4Fh+var_60], rax
0x140018b88  mov     rbx, r8
0x140018b8b  movups  [rbp+4Fh+Source1], xmm0
0x140018b8f  movups  [rbp+4Fh+var_48], xmm0
0x140018b93  movups  [rbp+4Fh+var_38], xmm0
0x140018b97  movups  [rbp+4Fh+Source2], xmm1
0x140018b9b  movups  [rbp+4Fh+var_80], xmm1
0x140018b9f  movups  [rbp+4Fh+var_70], xmm1
0x140018ba3  test    r9, r9
0x140018ba6  jnz     loc_140018C5F
0x140018bac  lea     rdx, [rbp+4Fh+Source1]
0x140018bb0  call    cs:__imp_EAQueryAggregateEventData
0x140018bb6  test    eax, eax
0x140018bb8  jnz     loc_140018CC9
0x140018bbe  mov     rcx, rbx
0x140018bc1  call    cs:__imp_RtlAcquireSRWLockShared
0x140018bc7  lea     r14, [rbx+20h]
0x140018bcb  mov     rsi, [r14]
0x140018bce  lea     rdi, WPP_GLOBAL_Control
0x140018bd5  cmp     rsi, r14
0x140018bd8  jz      short loc_140018C32
0x140018bda  mov     rcx, [rsi+18h]
0x140018bde  lea     rdx, [rbp+4Fh+Source2]
0x140018be2  call    cs:__imp_EAQueryAggregateEventData
0x140018be8  test    eax, eax
0x140018bea  jnz     loc_140018D0C
0x140018bf0  lea     r8d, [rax+8]; Length
0x140018bf4  lea     rdx, [rbp+4Fh+Source2]; Source2
0x140018bf8  lea     rcx, [rbp+4Fh+Source1]; Source1
0x140018bfc  call    cs:__imp_RtlCompareMemory
0x140018c02  cmp     rax, 8
0x140018c06  jnz     loc_140018D3B
0x140018c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c13  cmp     rcx, rdi
0x140018c16  jz      short loc_140018C1E
0x140018c18  test    byte ptr [rcx+1Ch], 4
0x140018c1c  jnz     short loc_140018C9D
0x140018c1e  mov     rdx, [rbx+18h]; unsigned __int16 *
0x140018c22  mov     rcx, rsi; struct _SERVICE_TRIGGER_SUBSCRIPTION *
0x140018c25  call    ?ScExtpExecuteTriggerAction@@YAKPEAU_SERVICE_TRIGGER_SUBSCRIPTION@@PEAG@Z; ScExtpExecuteTriggerAction(_SERVICE_TRIGGER_SUBSCRIPTION *,ushort *)
0x140018c2a  test    eax, eax
0x140018c2c  jnz     loc_140018D43
0x140018c32  mov     rcx, rbx
0x140018c35  call    cs:__imp_RtlReleaseSRWLockShared
0x140018c3b  mov     rcx, [rbp+4Fh+var_20]
0x140018c3f  xor     rcx, rsp; StackCookie
0x140018c42  call    __security_check_cookie
0x140018c47  lea     r11, [rsp+0C0h+var_10]
0x140018c4f  mov     rbx, [r11+28h]
0x140018c53  mov     rsi, [r11+38h]
0x140018c57  mov     rsp, r11
0x140018c5a  pop     r14
0x140018c5c  pop     rdi
0x140018c5d  pop     rbp
0x140018c5e  retn
0x140018c5f  cmp     [rbp+4Fh+arg_20], 14h
0x140018c63  jnb     loc_140018BAC
0x140018c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c70  lea     rdi, WPP_GLOBAL_Control
0x140018c77  cmp     rcx, rdi
0x140018c7a  jz      short loc_140018C3B
0x140018c7c  test    byte ptr [rcx+1Ch], 1
0x140018c80  jz      short loc_140018C3B
0x140018c82  mov     r9, [r8+18h]
0x140018c86  mov     edx, 5Ah ; 'Z'
0x140018c8b  mov     rcx, [rcx+10h]
0x140018c8f  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018c96  call    WPP_SF_S
0x140018c9b  jmp     short loc_140018C3B
0x140018c9d  mov     eax, [rsi+10h]
0x140018ca0  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018ca7  mov     r9, [rbx+18h]
0x140018cab  mov     edx, 5Dh ; ']'
0x140018cb0  mov     rcx, [rcx+10h]
0x140018cb4  mov     [rsp+0C0h+var_98], eax
0x140018cb8  mov     eax, [rsi+40h]
0x140018cbb  mov     [rsp+0C0h+var_A0], eax
0x140018cbf  call    WPP_SF_SLd
0x140018cc4  jmp     loc_140018C1E
0x140018cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140018cd0  lea     rdi, WPP_GLOBAL_Control
0x140018cd7  cmp     rcx, rdi
0x140018cda  jz      loc_140018C3B
0x140018ce0  test    byte ptr [rcx+1Ch], 1
0x140018ce4  jz      loc_140018C3B
0x140018cea  mov     r9, [rbx+18h]
0x140018cee  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018cf5  mov     rcx, [rcx+10h]
0x140018cf9  mov     edx, 5Bh ; '['
0x140018cfe  mov     [rsp+0C0h+var_A0], eax
0x140018d02  call    WPP_SF_Sd
0x140018d07  jmp     loc_140018C3B
0x140018d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d13  cmp     rcx, rdi
0x140018d16  jz      short loc_140018D3B
0x140018d18  test    byte ptr [rcx+1Ch], 2
0x140018d1c  jz      short loc_140018D3B
0x140018d1e  mov     r9, [rbx+18h]
0x140018d22  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018d29  mov     rcx, [rcx+10h]
0x140018d2d  mov     edx, 5Ch ; '\'
0x140018d32  mov     [rsp+0C0h+var_A0], eax
0x140018d36  call    WPP_SF_Sd
0x140018d3b  mov     rsi, [rsi]
0x140018d3e  jmp     loc_140018BD5
0x140018d43  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d4a  cmp     rcx, rdi
0x140018d4d  jz      loc_140018C32
0x140018d53  test    byte ptr [rcx+1Ch], 2
0x140018d57  jz      loc_140018C32
0x140018d5d  mov     r9, [rbx+18h]
0x140018d61  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018d68  mov     rcx, [rcx+10h]
0x140018d6c  mov     edx, 5Eh ; '^'
0x140018d71  mov     [rsp+0C0h+var_A0], eax
0x140018d75  call    WPP_SF_Sd
0x140018d7a  jmp     loc_140018C32
```
