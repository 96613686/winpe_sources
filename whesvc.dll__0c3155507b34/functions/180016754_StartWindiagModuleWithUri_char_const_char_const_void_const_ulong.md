# StartWindiagModuleWithUri(char const *,char const *,void * const,ulong)

- ea: `0x180016754`
- end: `0x180016832`
- name: `?StartWindiagModuleWithUri@@YAJPEBD0QEAXK@Z`
- size: `222`
- prototype: `__int64 __fastcall(char *, const char *, void *const, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b380`
- `0x1800158e8`
- `0x180020dc4`

## callees

- `0x180003304`
- `0x180009044`
- `0x180011578`
- `0x1800142e0`
- `0x180016208`
- `0x180016754`
- `0x18001c9c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartWindiagModuleWithUri(char *a1, const char *a2, void *const a3, unsigned int a4)
{
  int v4; // eax
  unsigned int v5; // edi
  void **v6; // rbx
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  struct _Mtx_internal_imp_t *Instance; // rax
  int started; // eax
  unsigned int v12; // ebx
  void *v13[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v13[0] = 0;
  v4 = WindiagModuleWrapper::CreateWithUri((void ***)v13, a1, a3, a4);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Instance = OrchestratorSingleton::GetInstance();
    v13[1] = v13[0];
    started = OrchestratorSingleton::StartModule(Instance);
    v12 = started;
    if ( started >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B1,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
        (const char *)(unsigned int)started,
        (int)v13[0]);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)(unsigned int)v4,
      (int)v13[0]);
    v6 = (void **)v13[0];
    if ( v13[0] )
    {
      std::string::~string((char *)v13[0] + 56);
      std::string::~string(v6 + 3);
      v8 = v6[1];
      if ( v8 )
        operator delete(v8, v7);
      if ( *v6 )
        operator delete(*v6, 0x18u);
      operator delete(v6, 0x58u);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180016754  mov     [rsp+arg_0], rbx
0x180016759  push    rdi
0x18001675a  sub     rsp, 30h
0x18001675e  mov     rbx, rdx
0x180016761  mov     [rsp+38h+var_18], 0; int
0x18001676a  mov     rdx, rcx
0x18001676d  lea     rcx, [rsp+38h+var_18]
0x180016772  call    ?CreateWithUri@WindiagModuleWrapper@@SAJAEAV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBDQEAXK@Z; WindiagModuleWrapper::CreateWithUri(std::unique_ptr<WindiagModuleWrapper> &,char const *,void * const,ulong)
0x180016777  mov     edi, eax
0x180016779  test    eax, eax
0x18001677b  jns     short loc_1800167E3
0x18001677d  mov     rcx, [rsp+38h]; this
0x180016782  mov     r9d, eax; char *
0x180016785  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x18001678c  mov     edx, 2B0h; void *
0x180016791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016796  mov     rbx, [rsp+38h+var_18]
0x18001679b  test    rbx, rbx
0x18001679e  jz      short loc_1800167DF
0x1800167a0  lea     rcx, [rbx+38h]
0x1800167a4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800167a9  lea     rcx, [rbx+18h]
0x1800167ad  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800167b2  mov     rcx, [rbx+8]; void *
0x1800167b6  test    rcx, rcx
0x1800167b9  jz      short loc_1800167C0
0x1800167bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800167c0  mov     rcx, [rbx]; void *
0x1800167c3  test    rcx, rcx
0x1800167c6  jz      short loc_1800167D2
0x1800167c8  mov     edx, 18h; unsigned __int64
0x1800167cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800167d2  mov     edx, 58h ; 'X'; unsigned __int64
0x1800167d7  mov     rcx, rbx; void *
0x1800167da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800167df  mov     eax, edi
0x1800167e1  jmp     short loc_180016827
0x1800167e3  call    ?GetInstance@OrchestratorSingleton@@SAAEAV1@XZ; OrchestratorSingleton::GetInstance(void)
0x1800167e8  mov     rcx, [rsp+38h+var_18]
0x1800167ed  mov     [rsp+38h+var_10], rcx
0x1800167f2  mov     r8, rbx
0x1800167f5  lea     rdx, [rsp+38h+var_10]
0x1800167fa  mov     rcx, rax; _Mtx_t
0x1800167fd  call    ?StartModule@OrchestratorSingleton@@QEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBD@Z; OrchestratorSingleton::StartModule(std::unique_ptr<WindiagModuleWrapper>,char const *)
0x180016802  mov     ebx, eax
0x180016804  test    eax, eax
0x180016806  jns     short loc_180016825
0x180016808  mov     rcx, [rsp+38h]; this
0x18001680d  mov     r9d, eax; char *
0x180016810  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180016817  mov     edx, 2B1h; void *
0x18001681c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016821  mov     eax, ebx
0x180016823  jmp     short loc_180016827
0x180016825  xor     eax, eax
0x180016827  mov     rbx, [rsp+38h+arg_0]
0x18001682c  add     rsp, 30h
0x180016830  pop     rdi
0x180016831  retn
```
