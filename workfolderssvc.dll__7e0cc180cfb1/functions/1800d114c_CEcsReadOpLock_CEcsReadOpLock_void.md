# CEcsReadOpLock::~CEcsReadOpLock(void)

- ea: `0x1800d114c`
- end: `0x1800d128f`
- name: `??1CEcsReadOpLock@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(CEcsReadOpLock *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800d25d0`

## callees

- `0x180007e10`
- `0x1800110fc`
- `0x180011314`
- `0x18003f2d0`
- `0x1800d114c`
- `0x1800d25e0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1800d11f2`
- `KERNEL32!SetThreadpoolWait` at `0x1800d11f2`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800d1200`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x1800d1200`
- `KERNEL32!WaitForSingleObject` at `0x1800d1222`
- `KERNEL32!WaitForSingleObject` at `0x1800d1222`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d1237`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d1237`

## string_xrefs

- `0x1800d11ce`: `CEcsReadOpLock::~CEcsReadOpLock`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CEcsReadOpLock::~CEcsReadOpLock(CEcsReadOpLock *this)
{
  _BYTE *v2; // rax
  char v3; // cl
  struct _TP_WAIT *v4; // rcx
  _DWORD v5[2]; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  const char *v7; // [rsp+30h] [rbp-10h]
  __int64 v8; // [rsp+38h] [rbp-8h]
  __int64 v9; // [rsp+50h] [rbp+10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+18h] BYREF

  v9 = (__int64)this;
  *(_QWORD *)this = &CEcsReadOpLock::`vftable';
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[68] & 2) != 0 && v2[65] >= 6u )
  {
    v3 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v3 = 0;
LABEL_9:
  v5[0] = 0;
  v5[1] = 30;
  v6 = v3;
  v7 = "CEcsReadOpLock::~CEcsReadOpLock";
  v8 = 0;
  v4 = (struct _TP_WAIT *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 3), 1);
    v10 = -1;
    EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset((char *)this + 8, &v10);
    WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF);
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v10 = 0;
  EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset((char *)this + 24, &v10);
  v10 = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset((char *)this + 16, &v10);
  v9 = -1;
  EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset((char *)this + 8, &v9);
}

```

## disassembly

```asm
0x1800d114c  mov     [rsp-8+arg_10], rbx
0x1800d1151  mov     [rsp-8+arg_18], rdi
0x1800d1156  mov     [rsp-8+arg_0], rcx
0x1800d115b  push    rbp
0x1800d115c  mov     rbp, rsp
0x1800d115f  sub     rsp, 40h
0x1800d1163  mov     rbx, rcx
0x1800d1166  lea     rax, ??_7CEcsReadOpLock@@6B@; const CEcsReadOpLock::`vftable'
0x1800d116d  mov     [rcx], rax
0x1800d1170  lea     rcx, WPP_GLOBAL_Control
0x1800d1177  mov     rax, cs:WPP_GLOBAL_Control
0x1800d117e  cmp     rax, rcx
0x1800d1181  jz      short loc_1800D11AB
0x1800d1183  test    byte ptr [rax+44h], 2
0x1800d1187  jz      short loc_1800D11BB
0x1800d1189  cmp     byte ptr [rax+41h], 6
0x1800d118d  jb      short loc_1800D11AB
0x1800d118f  mov     edx, 0Bh
0x1800d1194  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d119b  mov     rcx, [rax+38h]
0x1800d119f  call    WPP_SF_
0x1800d11a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800d11ab  test    byte ptr [rax+44h], 2
0x1800d11af  jz      short loc_1800D11BB
0x1800d11b1  cmp     byte ptr [rax+41h], 6
0x1800d11b5  jb      short loc_1800D11BB
0x1800d11b7  mov     cl, 1
0x1800d11b9  jmp     short loc_1800D11BD
0x1800d11bb  xor     cl, cl
0x1800d11bd  mov     [rbp+var_20], 0
0x1800d11c4  mov     [rbp+var_1C], 1Eh
0x1800d11cb  mov     [rbp+var_18], cl
0x1800d11ce  lea     rax, aCecsreadoplock_3; "CEcsReadOpLock::~CEcsReadOpLock"
0x1800d11d5  mov     [rbp+var_10], rax
0x1800d11d9  mov     [rbp+var_8], 0
0x1800d11e1  lea     rdi, [rbx+18h]
0x1800d11e5  mov     rcx, [rdi]; pwa
0x1800d11e8  test    rcx, rcx
0x1800d11eb  jz      short loc_1800D1229
0x1800d11ed  xor     r8d, r8d; pftTimeout
0x1800d11f0  xor     edx, edx; h
0x1800d11f2  call    cs:__imp_SetThreadpoolWait
0x1800d11f8  mov     edx, 1; fCancelPendingCallbacks
0x1800d11fd  mov     rcx, [rdi]; pwa
0x1800d1200  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800d1206  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x1800d120e  lea     rcx, [rbx+8]
0x1800d1212  lea     rdx, [rbp+arg_8]
0x1800d1216  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(void * const &)
0x1800d121b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800d121e  mov     rcx, [rbx+38h]; hHandle
0x1800d1222  call    cs:__imp_WaitForSingleObject
0x1800d1228  nop
0x1800d1229  lea     rcx, [rbp+var_20]; this
0x1800d122d  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d1232  nop
0x1800d1233  lea     rcx, [rbx+68h]; lpCriticalSection
0x1800d1237  call    cs:__imp_DeleteCriticalSection
0x1800d123d  nop
0x1800d123e  mov     [rbp+arg_8], 0
0x1800d1246  lea     rdx, [rbp+arg_8]
0x1800d124a  mov     rcx, rdi
0x1800d124d  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WAIT@@UWin32ThreadPoolWaitDeleter@@$0A@@@QEAAXAEBQEAU_TP_WAIT@@@Z; EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(_TP_WAIT * const &)
0x1800d1252  nop
0x1800d1253  mov     [rbp+arg_8], 0
0x1800d125b  lea     rcx, [rbx+10h]
0x1800d125f  lea     rdx, [rbp+arg_8]
0x1800d1263  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x1800d1268  nop
0x1800d1269  mov     [rbp+arg_0], 0FFFFFFFFFFFFFFFFh
0x1800d1271  lea     rcx, [rbx+8]
0x1800d1275  lea     rdx, [rbp+arg_0]
0x1800d1279  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(void * const &)
0x1800d127e  nop
0x1800d127f  mov     rbx, [rsp+40h+arg_10]
0x1800d1284  mov     rdi, [rsp+40h+arg_18]
0x1800d1289  add     rsp, 40h
0x1800d128d  pop     rbp
0x1800d128e  retn
```
