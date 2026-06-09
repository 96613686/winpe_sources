# THREAD_INFO::~THREAD_INFO(void)

- ea: `0x1800553a4`
- end: `0x180055471`
- name: `??1THREAD_INFO@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(THREAD_INFO *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180055514`

## callees

- `0x18000cb90`
- `0x1800285c8`
- `0x18002ff5c`
- `0x1800553a4`
- `0x180078010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1800553c1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1800553c1`
- `ole32!CoCreateInstance` at `0x18005542d`
- `ole32!CoCreateInstance` at `0x18005542d`

## pseudocode

```c
void __fastcall THREAD_INFO::~THREAD_INFO(THREAD_INFO *this, __int64 a2, __int64 a3)
{
  THREAD_INFO *v3; // rbx
  int v4; // edi
  void *v5; // rdx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  v3 = this;
  v4 = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    DeleteTimerQueueTimer(0, v5, 0);
    *((_QWORD *)v3 + 1) = 0;
    v4 = 1;
    this = (THREAD_INFO *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids,
        *((unsigned int *)v3 + 5));
  }
  if ( *((_DWORD *)v3 + 5) )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)v3 + 5));
      *((_DWORD *)v3 + 5) = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  }
  if ( v4 )
    DllRelease(this, v5, a3);
}

```

## disassembly

```asm
0x1800553a4  mov     [rsp+arg_8], rbx
0x1800553a9  push    rdi
0x1800553aa  sub     rsp, 30h
0x1800553ae  mov     rbx, rcx
0x1800553b1  xor     edi, edi
0x1800553b3  mov     rdx, [rcx+8]; Timer
0x1800553b7  test    rdx, rdx
0x1800553ba  jz      short loc_180055400
0x1800553bc  xor     r8d, r8d; CompletionEvent
0x1800553bf  xor     ecx, ecx; TimerQueue
0x1800553c1  call    cs:__imp_DeleteTimerQueueTimer
0x1800553c7  mov     [rbx+8], rdi
0x1800553cb  mov     edi, 1
0x1800553d0  lea     rax, WPP_GLOBAL_Control
0x1800553d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553de  cmp     rcx, rax
0x1800553e1  jz      short loc_180055400
0x1800553e3  test    byte ptr [rcx+1Ch], 40h
0x1800553e7  jz      short loc_180055400
0x1800553e9  lea     edx, [rdi+9]
0x1800553ec  mov     r9d, [rbx+14h]
0x1800553f0  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x1800553f7  mov     rcx, [rcx+10h]
0x1800553fb  call    WPP_SF_d
0x180055400  cmp     dword ptr [rbx+14h], 0
0x180055404  jz      short loc_18005545C
0x180055406  mov     [rsp+38h+arg_0], 0
0x18005540f  lea     rax, [rsp+38h+arg_0]
0x180055414  mov     [rsp+38h+ppv], rax; ppv
0x180055419  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180055420  xor     edx, edx; pUnkOuter
0x180055422  lea     r8d, [rdx+1]; dwClsContext
0x180055426  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18005542d  call    cs:__imp_CoCreateInstance
0x180055433  test    eax, eax
0x180055435  js      short loc_180055452
0x180055437  mov     rcx, [rsp+38h+arg_0]
0x18005543c  mov     rax, [rcx]
0x18005543f  mov     edx, [rbx+14h]
0x180055442  mov     rax, [rax+20h]
0x180055446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005544b  mov     dword ptr [rbx+14h], 0
0x180055452  lea     rcx, [rsp+38h+arg_0]
0x180055457  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005545c  test    edi, edi
0x18005545e  jz      short loc_180055466
0x180055460  call    DllRelease
0x180055465  nop
0x180055466  mov     rbx, [rsp+38h+arg_8]
0x18005546b  add     rsp, 30h
0x18005546f  pop     rdi
0x180055470  retn
```
