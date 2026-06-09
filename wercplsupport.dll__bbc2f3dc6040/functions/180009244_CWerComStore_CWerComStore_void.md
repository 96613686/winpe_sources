# CWerComStore::~CWerComStore(void)

- ea: `0x180009244`
- end: `0x1800092f1`
- name: `??1CWerComStore@@UEAA@XZ`
- size: `173`
- prototype: `void __fastcall(CWerComStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009b00`

## callees

- `0x180002850`
- `0x180007624`
- `0x180007d20`
- `0x180007fe0`
- `0x180009244`

## import_xrefs

- `wer!WerpCloseStore` at `0x1800092b7`
- `wer!WerpCloseStore` at `0x1800092d0`
- `wer!WerpCloseStore` at `0x1800092b7`
- `wer!WerpCloseStore` at `0x1800092d0`

## pseudocode

```c
void __fastcall CWerComStore::~CWerComStore(CWerComStore *this)
{
  __int64 v2; // rcx
  int v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 2;
  *(_QWORD *)this = &CWerComStore::`vftable'{for `CManagedObj'};
  *((_QWORD *)this + 3) = &CWerComStore::`vftable'{for `IWerStore'};
  if ( (int)CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v3) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  }
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
    WerpCloseStore();
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v3);
  if ( *((_QWORD *)this + 4) )
    WerpCloseStore();
  *(_QWORD *)this = &CManagedObj::`vftable';
  CObjectManager::UnLockServer((CObjectManager *)&CObjectManager::ms_instance);
}

```

## disassembly

```asm
0x180009244  push    rbx
0x180009246  sub     rsp, 20h
0x18000924a  lea     rax, ??_7CWerComStore@@6BCManagedObj@@@; const CWerComStore::`vftable'{for `CManagedObj'}
0x180009251  mov     [rsp+28h+arg_0], 2
0x180009259  mov     [rcx], rax
0x18000925c  mov     rbx, rcx
0x18000925f  lea     rax, ??_7CWerComStore@@6BIWerStore@@@; const CWerComStore::`vftable'{for `IWerStore'}
0x180009266  mov     [rcx+18h], rax
0x18000926a  lea     rcx, [rsp+28h+arg_0]; this
0x18000926f  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180009274  test    eax, eax
0x180009276  jns     short loc_1800092A6
0x180009278  mov     rcx, cs:WPP_GLOBAL_Control
0x18000927f  lea     rax, WPP_GLOBAL_Control
0x180009286  cmp     rcx, rax
0x180009289  jz      short loc_1800092A6
0x18000928b  test    byte ptr [rcx+1Ch], 1
0x18000928f  jz      short loc_1800092A6
0x180009291  mov     rcx, [rcx+10h]
0x180009295  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000929c  mov     edx, 53h ; 'S'
0x1800092a1  call    WPP_SF_
0x1800092a6  mov     rcx, [rbx+20h]
0x1800092aa  mov     qword ptr [rbx+20h], 0
0x1800092b2  test    rcx, rcx
0x1800092b5  jz      short loc_1800092BD
0x1800092b7  call    cs:__imp_WerpCloseStore
0x1800092bd  lea     rcx, [rsp+28h+arg_0]; this
0x1800092c2  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800092c7  mov     rcx, [rbx+20h]
0x1800092cb  test    rcx, rcx
0x1800092ce  jz      short loc_1800092D6
0x1800092d0  call    cs:__imp_WerpCloseStore
0x1800092d6  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x1800092dd  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x1800092e4  mov     [rbx], rax
0x1800092e7  add     rsp, 20h
0x1800092eb  pop     rbx
0x1800092ec  jmp     ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
```
