# CMediaUiRequestSubscriber::Unsubscribe(void)

- ea: `0x18005e24c`
- end: `0x18005e332`
- name: `?Unsubscribe@CMediaUiRequestSubscriber@@QEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(CMediaUiRequestSubscriber *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032bcc`
- `0x18005dba4`

## callees

- `0x18005daf0`
- `0x18005e24c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005e2b6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005e2fc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005e2b6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18005e2fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e2c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e307`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e280`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e2c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e307`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e29c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e2ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e317`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e29c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e2ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e317`

## pseudocode

```c
__int64 __fastcall CMediaUiRequestSubscriber::Unsubscribe(CMediaUiRequestSubscriber *this)
{
  unsigned int v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbp
  char v9; // [rsp+40h] [rbp+8h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 5, 1, 0) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v4 = v3;
    if ( *((_BYTE *)this + 16) )
    {
      v2 = 0;
      LeaveCriticalSection(v3);
      v5 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 9) = ATL::CRegObject::Release;
      if ( v5 )
      {
        ((void (*)(void))RtlUnsubscribeWnfNotificationWaitForCompletion)();
        *((_QWORD *)this + 1) = 0;
      }
      while ( 1 )
      {
        EnterCriticalSection(v3);
        v6 = *((_QWORD *)this + 12);
        if ( *(_QWORD *)v6 == v6 )
        {
          v7 = 0;
        }
        else
        {
          v7 = *(_QWORD *)(*(_QWORD *)v6 + 40LL);
          std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>,0>(
            (char *)this + 96,
            &v9);
        }
        LeaveCriticalSection(v3);
        if ( !v7 )
          break;
        RtlUnsubscribeWnfNotificationWaitForCompletion(v7);
      }
      EnterCriticalSection(v3);
      *((_BYTE *)this + 16) = 0;
      v4 = v3;
      *((_DWORD *)this + 5) = 0;
    }
    else
    {
      *((_BYTE *)this + 16) = 1;
      v2 = -2147019873;
    }
    LeaveCriticalSection(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18005e24c  mov     [rsp+arg_8], rbx
0x18005e251  mov     [rsp+arg_10], rbp
0x18005e256  push    rsi
0x18005e257  push    rdi
0x18005e258  push    r14
0x18005e25a  sub     rsp, 20h
0x18005e25e  mov     rbx, rcx
0x18005e261  mov     esi, 1
0x18005e266  xor     eax, eax
0x18005e268  lock cmpxchg [rcx+14h], esi
0x18005e26d  jz      short loc_18005E279
0x18005e26f  mov     esi, 8007139Fh
0x18005e274  jmp     loc_18005E31D
0x18005e279  lea     rdi, [rcx+20h]
0x18005e27d  mov     rcx, rdi; lpCriticalSection
0x18005e280  call    cs:__imp_EnterCriticalSection
0x18005e286  cmp     byte ptr [rbx+10h], 0
0x18005e28a  mov     rcx, rdi; lpCriticalSection
0x18005e28d  jnz     short loc_18005E29A
0x18005e28f  mov     [rbx+10h], sil
0x18005e293  mov     esi, 8007139Fh
0x18005e298  jmp     short loc_18005E317
0x18005e29a  xor     esi, esi
0x18005e29c  call    cs:__imp_LeaveCriticalSection
0x18005e2a2  mov     rcx, [rbx+8]
0x18005e2a6  lea     rax, ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18005e2ad  mov     [rbx+48h], rax
0x18005e2b1  test    rcx, rcx
0x18005e2b4  jz      short loc_18005E2C0
0x18005e2b6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18005e2bc  mov     [rbx+8], rsi
0x18005e2c0  mov     rcx, rdi; lpCriticalSection
0x18005e2c3  call    cs:__imp_EnterCriticalSection
0x18005e2c9  mov     rax, [rbx+60h]
0x18005e2cd  mov     r8, [rax]
0x18005e2d0  cmp     r8, rax
0x18005e2d3  jnz     short loc_18005E2D9
0x18005e2d5  xor     ebp, ebp
0x18005e2d7  jmp     short loc_18005E2EB
0x18005e2d9  mov     rbp, [r8+28h]
0x18005e2dd  lea     rdx, [rsp+38h+arg_0]
0x18005e2e2  lea     rcx, [rbx+60h]
0x18005e2e6  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@U_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@UWnfStateNameCompare@@V?$allocator@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_WNF_STATE_NAME@@PEAU_WNF_USER_SUBSCRIPTION@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<_WNF_STATE_NAME,_WNF_USER_SUBSCRIPTION *,WnfStateNameCompare,std::allocator<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_WNF_STATE_NAME const,_WNF_USER_SUBSCRIPTION *>>>>)
0x18005e2eb  mov     rcx, rdi; lpCriticalSection
0x18005e2ee  call    cs:__imp_LeaveCriticalSection
0x18005e2f4  test    rbp, rbp
0x18005e2f7  jz      short loc_18005E304
0x18005e2f9  mov     rcx, rbp
0x18005e2fc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18005e302  jmp     short loc_18005E2C0
0x18005e304  mov     rcx, rdi; lpCriticalSection
0x18005e307  call    cs:__imp_EnterCriticalSection
0x18005e30d  mov     [rbx+10h], sil
0x18005e311  mov     rcx, rdi; lpCriticalSection
0x18005e314  mov     [rbx+14h], esi
0x18005e317  call    cs:__imp_LeaveCriticalSection
0x18005e31d  mov     rbx, [rsp+38h+arg_8]
0x18005e322  mov     eax, esi
0x18005e324  mov     rbp, [rsp+38h+arg_10]
0x18005e329  add     rsp, 20h
0x18005e32d  pop     r14
0x18005e32f  pop     rdi
0x18005e330  pop     rsi
0x18005e331  retn
```
