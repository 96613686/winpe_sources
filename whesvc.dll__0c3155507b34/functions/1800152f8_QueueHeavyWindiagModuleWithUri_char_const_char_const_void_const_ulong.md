# QueueHeavyWindiagModuleWithUri(char const *,char const *,void * const,ulong)

- ea: `0x1800152f8`
- end: `0x1800153d6`
- name: `?QueueHeavyWindiagModuleWithUri@@YAJPEBD0QEAXK@Z`
- size: `222`
- prototype: `__int64 __fastcall(char *, const char *, void *const, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020dc4`

## callees

- `0x180003304`
- `0x180009044`
- `0x180011578`
- `0x1800142e0`
- `0x180014f94`
- `0x1800152f8`
- `0x18001c9c8`

## pseudocode

```c
__int64 __fastcall QueueHeavyWindiagModuleWithUri(char *a1, const char *a2, void *const a3, unsigned int a4)
{
  int v5; // eax
  unsigned int v6; // edi
  void **v7; // rbx
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  struct OrchestratorSingleton *Instance; // rax
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // [rsp+20h] [rbp-18h] BYREF
  void *v15; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v14 = 0;
  v5 = WindiagModuleWrapper::CreateWithUri((void ***)&v14, a1, a3, a4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    Instance = OrchestratorSingleton::GetInstance();
    v15 = v14;
    v12 = OrchestratorSingleton::QueueHeavyModule(Instance, &v15, a2);
    v13 = v12;
    if ( v12 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BA,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
        (const char *)(unsigned int)v12,
        (int)v14);
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)(unsigned int)v5,
      (int)v14);
    v7 = (void **)v14;
    if ( v14 )
    {
      std::string::~string((char *)v14 + 56);
      std::string::~string(v7 + 3);
      v9 = v7[1];
      if ( v9 )
        operator delete(v9, v8);
      if ( *v7 )
        operator delete(*v7, 0x18u);
      operator delete(v7, 0x58u);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x1800152f8  mov     [rsp+arg_0], rbx
0x1800152fd  push    rdi
0x1800152fe  sub     rsp, 30h
0x180015302  mov     rbx, rdx
0x180015305  mov     [rsp+38h+var_18], 0; int
0x18001530e  mov     rdx, rcx
0x180015311  lea     rcx, [rsp+38h+var_18]
0x180015316  call    ?CreateWithUri@WindiagModuleWrapper@@SAJAEAV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBDQEAXK@Z; WindiagModuleWrapper::CreateWithUri(std::unique_ptr<WindiagModuleWrapper> &,char const *,void * const,ulong)
0x18001531b  mov     edi, eax
0x18001531d  test    eax, eax
0x18001531f  jns     short loc_180015387
0x180015321  mov     rcx, [rsp+38h]; this
0x180015326  mov     r9d, eax; char *
0x180015329  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180015330  mov     edx, 2B9h; void *
0x180015335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001533a  mov     rbx, [rsp+38h+var_18]
0x18001533f  test    rbx, rbx
0x180015342  jz      short loc_180015383
0x180015344  lea     rcx, [rbx+38h]
0x180015348  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001534d  lea     rcx, [rbx+18h]
0x180015351  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015356  mov     rcx, [rbx+8]; void *
0x18001535a  test    rcx, rcx
0x18001535d  jz      short loc_180015364
0x18001535f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015364  mov     rcx, [rbx]; void *
0x180015367  test    rcx, rcx
0x18001536a  jz      short loc_180015376
0x18001536c  mov     edx, 18h; unsigned __int64
0x180015371  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015376  mov     edx, 58h ; 'X'; unsigned __int64
0x18001537b  mov     rcx, rbx; void *
0x18001537e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015383  mov     eax, edi
0x180015385  jmp     short loc_1800153CB
0x180015387  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x18001538c  mov     rcx, [rsp+38h+var_18]
0x180015391  mov     [rsp+38h+var_10], rcx
0x180015396  mov     r8, rbx
0x180015399  lea     rdx, [rsp+38h+var_10]
0x18001539e  mov     rcx, rax
0x1800153a1  call    ?QueueHeavyModule@OrchestratorSingleton@@QEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBD@Z; OrchestratorSingleton::QueueHeavyModule(std::unique_ptr<WindiagModuleWrapper>,char const *)
0x1800153a6  mov     ebx, eax
0x1800153a8  test    eax, eax
0x1800153aa  jns     short loc_1800153C9
0x1800153ac  mov     rcx, [rsp+38h]; this
0x1800153b1  mov     r9d, eax; char *
0x1800153b4  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x1800153bb  mov     edx, 2BAh; void *
0x1800153c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800153c5  mov     eax, ebx
0x1800153c7  jmp     short loc_1800153CB
0x1800153c9  xor     eax, eax
0x1800153cb  mov     rbx, [rsp+38h+arg_0]
0x1800153d0  add     rsp, 30h
0x1800153d4  pop     rdi
0x1800153d5  retn
```
