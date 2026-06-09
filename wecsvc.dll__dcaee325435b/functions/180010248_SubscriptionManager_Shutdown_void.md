# SubscriptionManager::Shutdown(void)

- ea: `0x180010248`
- end: `0x180010314`
- name: `?Shutdown@SubscriptionManager@@QEAAXXZ`
- size: `204`
- prototype: `void __fastcall(SubscriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008330`

## callees

- `0x180010248`
- `0x18001075c`
- `0x180010b20`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010259`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010259`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102ef`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180010303`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180010303`
- `ADVAPI32!PerfStopProvider` at `0x1800102da`
- `ADVAPI32!PerfStopProvider` at `0x1800102da`

## pseudocode

```c
void __fastcall SubscriptionManager::Shutdown(SubscriptionManager *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // rcx
  _QWORD *i; // rax
  void *v5; // rbx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (_QWORD *)**((_QWORD **)this + 12);
  while ( v2 != *((_QWORD **)this + 12) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2[8] + 24LL))(v2[8]);
    if ( !*((_BYTE *)v2 + 25) )
    {
      v3 = v2[2];
      if ( *(_BYTE *)(v3 + 25) )
      {
        for ( i = (_QWORD *)v2[1]; !*((_BYTE *)i + 25) && v2 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v2 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min((_QWORD *)v3);
      }
      v2 = i;
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::clear((char *)this + 96);
  v5 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = -1;
  if ( WecPerfCounter )
  {
    PerfStopProvider(WecPerfCounter);
    WecPerfCounter = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 )
    DeleteTimerQueueTimer(0, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
}

```

## disassembly

```asm
0x180010248  push    rbx
0x18001024a  push    rsi
0x18001024b  push    rdi
0x18001024c  push    r14
0x18001024e  sub     rsp, 28h
0x180010252  mov     rsi, rcx
0x180010255  add     rcx, 10h; lpCriticalSection
0x180010259  call    cs:__imp_EnterCriticalSection
0x18001025f  lea     r14, [rsi+60h]
0x180010263  mov     rbx, [r14]
0x180010266  mov     rbx, [rbx]
0x180010269  cmp     rbx, [r14]
0x18001026c  jz      short loc_1800102B3
0x18001026e  mov     rcx, [rbx+40h]
0x180010272  mov     rax, [rcx]
0x180010275  mov     rax, [rax+18h]
0x180010279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001027e  cmp     byte ptr [rbx+19h], 0
0x180010282  jnz     short loc_180010269
0x180010284  mov     rcx, [rbx+10h]
0x180010288  cmp     byte ptr [rcx+19h], 0
0x18001028c  jnz     short loc_180010295
0x18001028e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,wmi::AutoRef<Subscription>>,void *> *)
0x180010293  jmp     short loc_1800102AE
0x180010295  mov     rax, [rbx+8]
0x180010299  jmp     short loc_1800102A8
0x18001029b  cmp     rbx, [rax+10h]
0x18001029f  jnz     short loc_1800102AE
0x1800102a1  mov     rbx, rax
0x1800102a4  mov     rax, [rax+8]
0x1800102a8  cmp     byte ptr [rax+19h], 0
0x1800102ac  jz      short loc_18001029B
0x1800102ae  mov     rbx, rax
0x1800102b1  jmp     short loc_180010269
0x1800102b3  mov     rcx, r14
0x1800102b6  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VBoundSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<BoundSubscription>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wmi::AutoRef<BoundSubscription>>>,0>>::clear(void)
0x1800102bb  mov     rbx, [rsi+70h]
0x1800102bf  mov     qword ptr [rsi+70h], 0
0x1800102c7  mov     dword ptr [rsi+78h], 0FFFFFFFFh
0x1800102ce  mov     rcx, cs:WecPerfCounter; ProviderHandle
0x1800102d5  test    rcx, rcx
0x1800102d8  jz      short loc_1800102EB
0x1800102da  call    cs:__imp_PerfStopProvider
0x1800102e0  mov     cs:WecPerfCounter, 0
0x1800102eb  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800102ef  call    cs:__imp_LeaveCriticalSection
0x1800102f5  test    rbx, rbx
0x1800102f8  jz      short loc_18001030A
0x1800102fa  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800102fe  mov     rdx, rbx; Timer
0x180010301  xor     ecx, ecx; TimerQueue
0x180010303  call    cs:__imp_DeleteTimerQueueTimer
0x180010309  nop
0x18001030a  add     rsp, 28h
0x18001030e  pop     r14
0x180010310  pop     rdi
0x180010311  pop     rsi
0x180010312  pop     rbx
0x180010313  retn
```
