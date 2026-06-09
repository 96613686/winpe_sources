# Autoplay::DispatchDeviceEvent(Autoplay::CDispatchDeviceEvent *)

- ea: `0x1800046c0`
- end: `0x18000477b`
- name: `?DispatchDeviceEvent@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z`
- size: `187`
- prototype: `__int64 __fastcall(Autoplay *__hidden this, struct Autoplay::CDispatchDeviceEvent *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800036e0`
- `0x180004790`
- `0x1800197a4`
- `0x180019d40`
- `0x18001a064`

## callees

- `0x180003570`
- `0x1800046c0`
- `0x180004b50`
- `0x18001951c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800046ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800046ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004725`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x180004739`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x180004739`

## pseudocode

```c
__int64 __fastcall Autoplay::DispatchDeviceEvent(Autoplay *this, struct Autoplay::CDispatchDeviceEvent *a2)
{
  _DWORD *v2; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  CRefCounted *v6; // rcx
  DWORD v7; // eax
  struct Autoplay::CDispatchDeviceEvent *v8; // rdx

  v2 = Autoplay::g_pmreDispatchDeviceEvents;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  v4 = (struct _RTL_CRITICAL_SECTION *)(v2 + 44);
  v5 = (struct _RTL_CRITICAL_SECTION *)(v2 + 44);
  if ( v2 == (_DWORD *)-168LL )
    v5 = 0;
  EnterCriticalSection(v5);
  v6 = *(CRefCounted **)&v2[2 * *v2 + 2];
  if ( v6 )
    CRefCounted::Release(v6);
  *(_QWORD *)&v2[2 * (*v2)++ + 2] = this;
  if ( *v2 == 20 )
    *v2 = 0;
  if ( v2 == (_DWORD *)-168LL )
    v4 = 0;
  LeaveCriticalSection(v4);
  if ( !*((_DWORD *)this + 172) )
    return 1;
  v7 = CMP_WaitNoPendingInstallEvents(0x493E0u);
  switch ( v7 )
  {
    case 0u:
      return Autoplay::_DispatchToHandler(this, v8);
    case 0x102u:
      return 1;
    case 0xFFFFFFFF:
      return ResultFromKnownLastError();
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800046c0  push    rbx
0x1800046c2  push    rbp
0x1800046c3  push    rsi
0x1800046c4  push    rdi
0x1800046c5  sub     rsp, 28h
0x1800046c9  mov     rbx, cs:?g_pmreDispatchDeviceEvents@Autoplay@@3PEAV?$CMostRecentEvents@VCDispatchDeviceEvent@Autoplay@@$0BE@@@EA; CMostRecentEvents<Autoplay::CDispatchDeviceEvent,20> * Autoplay::g_pmreDispatchDeviceEvents
0x1800046d0  mov     rdi, rcx
0x1800046d3  lock inc dword ptr [rcx+8]
0x1800046d7  xor     eax, eax
0x1800046d9  lea     rbp, [rbx+0A8h]
0x1800046e0  lea     rsi, [rbp+8]
0x1800046e4  test    rbp, rbp
0x1800046e7  mov     rcx, rsi
0x1800046ea  cmovz   rcx, rax; lpCriticalSection
0x1800046ee  call    cs:__imp_EnterCriticalSection
0x1800046f4  mov     eax, [rbx]
0x1800046f6  mov     rcx, [rbx+rax*8+8]; this
0x1800046fb  test    rcx, rcx
0x1800046fe  jz      short loc_180004705
0x180004700  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180004705  mov     eax, [rbx]
0x180004707  mov     [rbx+rax*8+8], rdi
0x18000470c  inc     dword ptr [rbx]
0x18000470e  cmp     dword ptr [rbx], 14h
0x180004711  jnz     short loc_180004719
0x180004713  mov     dword ptr [rbx], 0
0x180004719  xor     eax, eax
0x18000471b  test    rbp, rbp
0x18000471e  cmovz   rsi, rax
0x180004722  mov     rcx, rsi; lpCriticalSection
0x180004725  call    cs:__imp_LeaveCriticalSection
0x18000472b  cmp     dword ptr [rdi+2B0h], 0
0x180004732  jz      short loc_18000476D
0x180004734  mov     ecx, 493E0h; dwTimeout
0x180004739  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x18000473f  test    eax, eax
0x180004741  jnz     short loc_180004753
0x180004743  mov     rcx, rdi; this
0x180004746  add     rsp, 28h
0x18000474a  pop     rdi
0x18000474b  pop     rsi
0x18000474c  pop     rbp
0x18000474d  pop     rbx
0x18000474e  jmp     ?_DispatchToHandler@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z; Autoplay::_DispatchToHandler(Autoplay::CDispatchDeviceEvent *)
0x180004753  cmp     eax, 102h
0x180004758  jz      short loc_18000476D
0x18000475a  cmp     eax, 0FFFFFFFFh
0x18000475d  jnz     short loc_180004766
0x18000475f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004764  jmp     short loc_180004772
0x180004766  mov     eax, 80004005h
0x18000476b  jmp     short loc_180004772
0x18000476d  mov     eax, 1
0x180004772  add     rsp, 28h
0x180004776  pop     rdi
0x180004777  pop     rsi
0x180004778  pop     rbp
0x180004779  pop     rbx
0x18000477a  retn
```
